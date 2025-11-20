# HDFS_anomaly
🚀 HDFS Anomaly Detection with PyTorch Autoencoder

In large-scale distributed systems, like cloud storage or enterprise data platforms, monitoring HDFS logs is crucial. Even a single abnormal block can indicate potential failures, corrupted data, or bottlenecks. Manually analyzing millions of log entries is impossible — that’s where AI comes in! 🤖

I built an unsupervised anomaly detection model using a PyTorch autoencoder to automatically detect abnormal HDFS blocks from log events.



Workflow Overview:

1️⃣ Data Preprocessing

HDFS log dataset with 29 distinct event types per block

Cleaned missing values, normalized counts

Mapped labels: Normal = 0, Anomaly = 1

2️⃣ Training the Autoencoder

Trained only on normal blocks to learn typical patterns

Model compresses features into a low-dimensional bottleneck and reconstructs them

3️⃣ Anomaly Detection

Computed reconstruction error for each block

Blocks with error above threshold (mean + 3×std) are flagged as anomalies



Results:

Dataset size: ~575k blocks (~3% anomalies)

Performance:

✅ Precision = 1.00 → almost no false alarms

✅ Recall = 0.51 → catches ~51% of actual anomalies

✅ Overall accuracy = 99%

Takeaway: High precision ensures that flagged blocks are genuinely anomalous, helping engineers prioritize critical issues.
