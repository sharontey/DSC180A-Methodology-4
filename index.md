# DSC 180A – Methodology Assignment 4

**Sharon Tey** | stey@ucsd.edu

**Section D05** | Mentors: Prof. Haojian Jin (UCSD), Sylvia Downing (Azimuth AI), Michael Deisher (Azimuth AI)

---

**What is the most interesting topic covered in your domain this quarter?**
The most interesting idea was that a time-series foundation model can learn useful structure from purely synthetic data. We fine-tuned Chronos-2 only on SarSim0-generated series and never showed it real data. On M4 Monthly, which it had never seen, it still improved — our 500-step fine-tune lowered MASE by about 2% compared with pretrained Chronos-2, and a paired bootstrap backed this up.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**
I'd like to build a synthetic data generator for an electrical system and use it to train and test forecasting and anomaly detection models. This could include generating feeder-level load, voltage, and frequency at grid nodes, or solar output, then evaluating how well models trained on simulated data transfer to real grid signals.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**
Use real data in model selection sooner. The longer runs kept improving on simulated data but not on M4. We should pick checkpoints by M4 Quarterly validation score rather than by training loss. We could also mix a small share of real series into training to stop the model from overfitting to the simulator.

**What other techniques would you be interested in using in your project?**
Detecting anomalies with reconstruction — autoencoders or Anomaly Transformer–style models — compared against forecast-error baseline scores. I'm also interested in physics-informed constraints, for example penalising forecasts that violate power-balance limits.
