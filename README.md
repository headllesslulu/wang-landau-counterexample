# wang-landau-counterexample
This repository contains a white paper and Lean 4 proof of an explicit
eleven-state Wang-Landau counterexample. The construction uses uniform
proposals, an 80% histogram-flatness test checked after every update, and
the modification schedule f_k = exp((10^-7)^k). The true density ratio is 6/5.

On a measurable event of probability greater than 24%, every stage finishes,
the executed modification factor tends to one, and the density estimate
converges to a wrong limit. Its relative density-ratio error exceeds 15%,
and its log-ratio error exceeds 0.17. The estimate does not converge in
probability to the correct value; almost-sure convergence also fails.

The main theorem, WangLandau.closed_counterexample, has no input hypotheses.
The three former bridge assumptions are discharged by proved theorems:
  Initialization probability: WLStream.initial_probability
  First-failure bound: WLStageTail.first_failure_geometric
  Actual adaptive drift: WLSamplerBridge.actual_path_budget
WangLandau.closed_consumed_stream_law proves that the entire adaptively
consumed noise stream has exactly the conventional infinite iid law.
