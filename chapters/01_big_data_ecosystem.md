# Chapter 1: Big Data Ecosystem

## Brief Information
Big Data refers to datasets that are too large or complex for traditional data-processing software. It is defined by the **4 Vs**: Volume, Variety, Velocity, and Veracity. Traditional systems scale vertically (up), while Big Data systems scale horizontally (out) using distributed architectures like Hadoop (HDFS + MapReduce).

### Key Concepts
- **HDFS (Hadoop Distributed File System):** Distributed storage that breaks data into blocks and replicates them for fault tolerance.
- **MapReduce:** A programming model for processing large datasets in parallel.
- **YARN (Yet Another Resource Negotiator):** The resource management layer of Hadoop.
- **Fault Tolerance:** Achieved through Replication Factors and Heartbeats.

## Practical Example: Word Count in MapReduce
Imagine you have a 1TB text file and want to count the occurrences of each word.
1. **Input:** The file is split into 128MB blocks across 100 nodes in HDFS.
2. **Map Phase:** Each node reads its blocks and outputs `(word, 1)` for every word found.
3. **Shuffle & Sort:** The system moves all instances of the same word to the same Reducer node.
4. **Reduce Phase:** Each Reducer node sums the counts for the words it received, e.g., `(apple, 5)`.
5. **Output:** The final counts are written back to HDFS.

## YouTube Tutorials
- [Hadoop Tutorial for Beginners (Playlist)](https://www.youtube.com/playlist?list=PLVHgQku8Z937wHNqd2z_8_ze_HBVhfBRt)
- [Big Data & Hadoop Full Course - Simplilearn](https://www.youtube.com/watch?v=1vbXmCrkT3Y)
- [MapReduce Explained Simply](https://www.youtube.com/watch?v=gfK4l_Y-HFk)
