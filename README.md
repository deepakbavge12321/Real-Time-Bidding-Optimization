# Optimal Real-Time Bidding for Display Advertising

---

## 🚀 Project Overview

Designed and built a **benchmarking framework** for real-time bidding (RTB) optimization in display advertising, based on the problem setup from [W. Zhang et al., 2014](http://arxiv.org/abs/1407.7073). The framework supports:

- **Feature engineering** for a logistic regression–based click-through rate (CTR) estimator  
- **Implementation** of standard bidding strategies  
- **Integration** of the state-of-the-art ORTB (Optimal Real-Time Bidding) function proposed in KDD’14 ([paper](http://www0.cs.ucl.ac.uk/staff/w.zhang/papers/ortb-kdd.pdf))

---

## 🔧 Key Components

1. **Data Preparation**  
   - Used the [make-ipinyou-data](https://github.com/wnzhang/make-ipinyou-data) repository to standardize raw RTB logs  
   - Ran `make all` to generate per-campaign training/test datasets

2. **CTR Estimation**  
   - Engineered features (user, publisher, ad, time) for logistic regression  
   - Trained and validated CTR models on campaign-specific data

3. **Bidding Strategies**  
   - **Constant**, **Linear**, **Mcpc**, **Random** — as baselines  
   - **ORTB**: Integrated the optimal bidding function from the KDD’14 paper  
   - Tuned parameters to maximize clicks under budget constraints

4. **Benchmarking & Results**  
   - Automated experiments with `scripts/demo.sh`  
   - Generated `results/rtb.results.{campaign}.best.perf.tsv` showing metrics:  
     ```
     prop   clks    bids    imps    budget   spend    algo   para
     16     51      227472  97784   2,826,028 2,826,032 const  55
     16     482     614,638 89,408  2,826,028 2,804,895 lin    130
     … (other campaigns & algorithms) …
     ```
   - Demonstrated how different algorithms perform under varying budget settings 

---

## 💡 Takeaways & Skills

- **Machine Learning:** Logistic regression for CTR prediction  
- **Data Engineering:** Preprocessing large-scale bid logs  
- **Algorithms:** Implementation and tuning of bidding strategies  
- **Scripting & Automation:** Bash scripting for end-to-end experiments  
- **Research Translation:** Applied cutting-edge academic methods to a working prototype

---

## 🔗 Links

- **Code Repository:** [wnzhang/optimal-rtb](https://github.com/wnzhang/optimal-rtb)  
- **Data Preparation:** [wnzhang/make-ipinyou-data](https://github.com/wnzhang/make-ipinyou-data)  
- **Benchmarking Paper:** http://arxiv.org/abs/1407.7073  
- **ORTB Algorithm:** http://www0.cs.ucl.ac.uk/staff/w.zhang/papers/ortb-kdd.pdf
