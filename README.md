# Physics Informed Neural Networks (PINNs) for predicting state variable dynamics and unknown parameters in Diesel Engines.

This repository contains the code and experiments developed during my Bachelor Thesis:
**"A Physics - Informed Neural Network approach to predicting dynamics and identifying unknown parameters in diesel engines"**,  
completed at National and Kapodistrian University of Athens / Physics Department under the supervision of Aris L. Moustakas. 

We developed a model that, given noisy or sparse data, is able to predict both the state variable dynamics and unknown parameters of a mean diesel engine system.

To achieve this, we embedded the system’s governing physics into the learning process using Physics-Informed Neural Networks (PINNs). This approach allows the model to remain physically consistent while improving robustness against limited or uncertain data.



## License

This repository is made publicly available for reference purposes only.  
All rights are reserved. No part of the code, documentation, or data may be copied, modified, or used without prior written permission from the author.  

For permission requests, please contact: dimkalkantzis@gmail.com.


## Documentation

[Data Generator](http://www.fs.isy.liu.se/Software)

[Mathematical Analysis of a Diesel Engine System](https://www.researchgate.net/publication/258176907_Modelling_diesel_engines_with_a_variable-geometry_turbocharger_and_exhaust_gas_recirculation_by_optimization_of_model_parameters_for_capturing_non-linear_system_dynamics)

[Related Work](https://www.nature.com/articles/s41598-023-39989-4)

[DeepONets for Diesel Engine System](https://arxiv.org/abs/2304.00567)





## Authors

- **Dimitrios Kalkantzis** – Bachelor Thesis, National and Kapodistrian University of Athens / Physics Department, 2025  
  Email: dimkalkantzis@gmail.com


## Badges

![Status](https://img.shields.io/badge/status-research-lightgrey)
![Python](https://img.shields.io/badge/python-3.10+-blue)
![PyTorch](https://img.shields.io/badge/pytorch-2.0+-red)
![License](https://img.shields.io/badge/license-All%20Rights%20Reserved-orange)


## Appendix

This work proposes a Physics-Informed Neural Network (PINN framework for simulating state dynamics and inferring unknown parameters of a mean diesel engine system. The underlying system is governed by six differential equations and two algebraic equations, involving a total of eight state variables. In addition, four unknown parameters are identified as quantities to be estimated. 

Normally, the loss function of the PINN consists of three principal components: the initial condition loss, the equation residual loss and the data loss. Without proper treatment, this imbalance can hinder optimization and lead to biased learning. To address this issue, each loss component is normalized by its characteristic order of magnitude at the initial operating condition, thereby ensuring that all terms contribute comparably during training. 

Furthermore, certain analytical functions embedded in the residual equations exhibit complex nonlinearities and are computationally expensive to evaluate directly. To address this, pre-trained neural networks were employed as surrogates, enabling efficient and accurate approximation of these terms within the loss function. Finally, in order to reduce the overall training complexity, the PINN framework was restricted to learn the dynamics of state variables whose governing equations are not coupled, thereby simplifying optimization while preserving predictive capability.

The proposed method demonstrated strong performance under both clean and noisy data conditions. Robustness was maintained for noise levels up to 4%, and additional tests were conducted under data sparsity scenarios. Across these settings, the framework successfully reproduced the dynamics of the state variables. Moreover, despite the challenging conditions, the model was able to reliably infer two out of the four unknown parameters.

