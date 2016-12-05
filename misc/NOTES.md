# notes

* 10 November 2016 meeting
  * data sets to consider: breastcancer (mlbench), mroz (car), boston housing

  * packages/methods to explore/discuss:
    * caret (esp. `createFolds`, but also various wrappers for modeling)
    * Super Learner and CV Super Learner
    * H2O, H2Oensemble, h2oFlow
    * mlr (just mention basic details)

  * classifiers to use (or consider): unpruned decision tree, random forests,
      logistic regression with elastic net penalty, logistic regression,
      gradient boosting machines, support vector machines (maybe), xgboost
      (maybe, likely not)

  * metrics for model evaluation: AUC (+ discussion of E. LeDell's `cvAUC` R
      package), other R packages include `pROC` and `ROCR`.

  * presentation medium: slide deck (max ~10 slides), Jupyter notebook for live
      coding (along with RMarkdown + compiled HTML for convenience of audience)

  * prepare handout to be distributed at beginning of presentation (Rmd/TeX)
