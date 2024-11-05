# Seasonal Ice Velocity Predictions

This document outlines the relevance of machine learning to predicting ice velocity values at Zachariæ Isstrøm (ZI) in Northeast Greenland.

In its simplest form, the project involves taking time series data of the velocity values at points along flowlines on ZI and predicting what the velocity values will be along the flowlines 10 years into the future. Please see the [README](https://github.com/cjense/seasonal-icevelocity-prediction/blob/main/README.md) for further information about each tier.

At the first tier, this is a regression problem because the goal is to predict values into the future by identifying a trend in the data. Since it is the goal to estimate velocity values over time, it is not sufficient to classify points as speeding up, slowing down, etc. at a given time. These values vary seasonally and a further level of granularity is needed to analyze ice dynamics at ZI as the climate continues warming.

The work is supervised learning since it is a regression problem. Each point at a given timestep has the label of a velocity value associated with it which will be used to predit future velocity value "labels."

## Tier 1

I expect to be able to predict velocity values 10 years into the future but with low accuracy and temporal resolution. At this stage, it will be necessary to define a metric to measure the accuracy of the predictions to understand the performance of the model. Since the flowlines are not representative of all velocity values across the glacier, it will be difficult to analyze the future velocity values at ZI but it is a starting point.

## Tier 2

At Tier 2, I expect to be able to compare ZI with its neighbor, 79N, to make comparisons about what might be happening at both glaciers. With seasonal velocity predicitons rather than annual, I expect the model to produce inaccurate yet interesting results. The use of an LLM to predict annual velocity values is to take the project's initial results even further and test the ability of LLMs for time series forecasting.

## Tier 3

By incorporating predicitons of all Greenland glaciers, I expect there to be a large amount of error in the data. However, this tier could still produce interesting data that could be a start to a publication. The incorporation of velocity values on ZI's entire area could produce interesting results since the velocity varies greatly with space. However, without a fully coupled model that includes the external variables that influence velocity, it is difficult to trust these predictions.

## Tier 4

This tier indicates publication-worthy data. By incorporating other datasets into the model like terminus position and meltwater discharge, it is possible to perturb the system and create predictions based on what might happen at ZI based on the environmental variables hypothesized to affect velocity most. Additionally, seasonal velocity predictions for the entire area of all Greenland glaciers could be interesting to analyze trends among glaciers that are part of different systems.
