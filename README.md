# TAA - The Advisors Alliance Network of Mixture of Experts

In the field of artificial intelligence, the combination of smaller AI models to form a larger, more complex model is a topic of ongoing research. Various strategies have been proposed and implemented to achieve this goal.

The Mixture of Experts (MoE) model [1] is a well-known approach that combines multiple "expert" models, each of which specializes in a different part of the input space. The idea is to weight the outputs of these experts according to their competence in the given input, thereby creating a more powerful and flexible model. The Switch Transformer (ST) [2] is a variant of the Transformer model that replaces the dense feed-forward network (FFN) layer in the Transformer with a sparse Switch FFN layer. This layer operates independently on tokens in the sequence and routes them to multiple FFN experts. The Switch FFN layer returns the output of the chosen FFN, multiplies it by the router threshold, and then merges it. This approach allows the model to dynamically allocate computational resources, focusing on the most relevant experts for each specific task. The Expert Choice (EC) method [3] sets up a group of experts with a predetermined buffer capacity. It assigns the top k tokens to the experts, generates a score matrix from the tokens to the experts, and then makes routing decisions based on this matrix. This approach ensures that each token can be routed to a variable number of experts, and each expert can have a fixed bucket size, improving training convergence time and performance in fine-tuning tasks. The Generalist Language Model (GLaM) [4] uses a sparsely-activated mixture-of-experts architecture to increase model capacity while significantly reducing training costs compared to dense variants. By focusing on the relative importance of different tokens and allowing each token to be routed to a variable number of experts, GLaM achieves higher performance in a range of tasks.

In addition to the Mixture of Experts (MoE) method, there are several other strategies for combining AI model such as bagging and boosting, involve training multiple models and combining their predictions to reduce overfitting and improve robustness. Stacking generalization combines models hierarchically, using the outputs of multiple models as inputs to a higher-level model. Federated learning trains models across multiple devices or servers, each with its own local dataset, and aggregates the learned parameters to form a global model. Neural Architecture Search (NAS) automatically finds the best neural network architecture for a given task, combining the best components from a search space of models.




References:

[1] @misc{gormley2018mixtures,
      title={Mixtures of Experts Models}, 
      author={Isobel Claire Gormley and Sylvia Frühwirth-Schnatter},
      year={2018},
      eprint={1806.08200},
      archivePrefix={arXiv},
      primaryClass={stat.ME}
}

[2] @misc{fedus2022switch,
      title={Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity}, 
      author={William Fedus and Barret Zoph and Noam Shazeer},
      year={2022},
      eprint={2101.03961},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}

[3] @misc{zhou2022mixtureofexperts,
      title={Mixture-of-Experts with Expert Choice Routing}, 
      author={Yanqi Zhou and Tao Lei and Hanxiao Liu and Nan Du and Yanping Huang and Vincent Zhao and Andrew Dai and Zhifeng Chen and Quoc Le and James Laudon},
      year={2022},
      eprint={2202.09368},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}

[4] @misc{du2022glam,
      title={GLaM: Efficient Scaling of Language Models with Mixture-of-Experts}, 
      author={Nan Du and Yanping Huang and Andrew M. Dai and Simon Tong and Dmitry Lepikhin and Yuanzhong Xu and Maxim Krikun and Yanqi Zhou and Adams Wei Yu and Orhan Firat and Barret Zoph and Liam Fedus and Maarten Bosma and Zongwei Zhou and Tao Wang and Yu Emma Wang and Kellie Webster and Marie Pellat and Kevin Robinson and Kathleen Meier-Hellstern and Toju Duke and Lucas Dixon and Kun Zhang and Quoc V Le and Yonghui Wu and Zhifeng Chen and Claire Cui},
      year={2022},
      eprint={2112.06905},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
