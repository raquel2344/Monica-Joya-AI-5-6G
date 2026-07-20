# Reflection 2: Applying AI to Telecommunications Problems

The second half of the course was about pointing AI at real network problems. This is where my earlier background in data and modeling paid off, and it is also where I learned the most, because the lessons came from things going wrong as much as from things working.

## My first model, and learning what the features actually do

In Module 03 I built my first machine learning model, a Random Forest that predicts hourly network traffic. The model itself was almost the easy part. What taught me the most was the feature engineering: the model could not do much with the raw time series until I gave it lag features and rolling averages so it could see recent history. When I looked at feature importance and saw that the traffic from one hour and twenty-four hours earlier mattered most, the daily and weekly rhythm of a network became something I could measure, not just describe. That was the moment machine learning stopped being a black box for me and became a tool whose inputs I am responsible for.

## Learning to distrust a good-looking result

Module 06 gave me the single most useful lesson of the course. I built three forecasting models, ARIMA, Linear Regression, and an LSTM, and the Linear Regression model scored almost perfectly, with error close to zero. My first instinct was that I had done something right. I had not. The moving-average features in the starter code included the current hour, so each average already contained the value the model was trying to predict. That is target leakage, and it makes a model look brilliant while teaching it nothing useful. I kept the provided code as it was, changed only the one line the newer pandas version required, and documented the leakage instead of quietly deleting it. The lesson stuck: a near-perfect score is a warning sign, not a trophy, and being honest about a flawed result is part of the work.

## Fixing code, not just running it

Module 07 pushed me from using AI to debugging it. The lab was about compressing a full model so it could run on a small edge device, and part of the starter code was broken. The knowledge distillation section, where a small student model is supposed to learn from a large teacher, was set up but never actually connected, so the student was training on its own and never saw the teacher. I connected them so the student trains on the teacher's softened predictions, corrected the temperature so it is applied the standard way, and marked the change clearly as mine. I also learned a practical habit here: after fighting through TensorFlow install problems, I started testing fragile steps on a tiny model before committing to a long full run, which is how I caught the broken distillation early.

## Making AI act, not just predict

The midterm in Module 10 tied everything together and taught me the difference between predicting and optimizing. I studied one network three ways: a SimPy discrete-event simulation that turned queueing into real latency and throughput numbers, a Mesa agent-based model where routers rerouted around congestion on their own, and a scikit-learn predictor that forecast traffic. The Mesa part taught me that useful behavior can emerge without a central controller, because the network recovered from congestion simply because each router acted on its own. The prediction part taught me the lesson I keep coming back to: forecasting traffic is only half the work. The value came from letting the forecast drive an actual routing decision, sending new flows to the quieter predicted path before congestion could form. That is what self-optimizing means in practice, and it is the idea I most want to build on.

## What this half of the course gave me

Across these projects I applied AI to prediction, anomaly detection, resource allocation, model compression, and self-optimizing control, all on network problems. More than any single model, what I gained is a way of working: engineer the inputs carefully, distrust results that look too clean, fix and document the code rather than hide its flaws, and always ask whether a prediction is actually driving a decision. Those habits are the real skill, and they carry well past this one course.
