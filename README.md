# Machine-Learning-System-Design

## When to Use Machine Learning?
1. Machine learning is an approach to **learn** **complex** **patterns** from **existing data** and use these patterns to make **predictions** on **unseen data**.
    * ML can be especially appealing when you can benefit from a large quantity of cheap but approximate predictions.
1. ML is more suitable with following problem characteristics:
    * It's repetitive
    * The cost of wrong predictions is cheap
    * It's at scale
    * The patterns are constantly changing
1. Enterprise applications might have stricter accuracy requirements but less latency requirements.

## General ML Process
1. [The most successful approach to ML production I’ve seen in the industry is iterative and incremental development.](https://huyenchip.com/ml-interviews-book/contents/1.1.3.1-production-cycle.html)
1. Here is one common workflow that you might encounter when building an ML model to predict whether an ad should be shown when users enter a search query
   * Choose a metric to optimize. For example, you might want to optimize for impressions -- the number of times an ad is shown.
   * Collect data and obtain labels.
   * Engineer features.
   * Train models.
   * During error analysis, you realize that errors are caused by wrong labels, so you relabel data.
   * Train model again.
   * During error analysis, you realize that your model always predicts that an ad shouldn’t be shown, and the reason is that 99.99% of the data you have is a no-show (an ad shouldn’t be shown for most queries). So you have to collect more data on ads that should be shown.
   * Train model again.
   * The model performs well on your existing test data, which is by now two months ago. But it performs poorly on the test data from yesterday. Your model has degraded, so you need to collect more recent data.
   * Train model again.
   * Deploy model.
   * The model seems to be performing well but then the business people come knocking on your door asking why the revenue is decreasing. It turns out the ads are being shown but few people click on them. So you want to change your model to optimize for clickthrough rate instead.
   * Start over


# References
1. Designing Machine Learning Systems, Chip Huyen
