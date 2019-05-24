# 1. 摘要
低光影像很有挑战性：低光子量和低信噪比
短曝：noise
长曝：blur且通常不实际
一系列去噪、去模糊和增强技术在极限条件下并不是很有效
文章为low-light image processing的learning-based pipeline提出了raw short-exposure low-light image和对应long-exposure reference images的dataset。
通过dataset，设计了处理低光影像的pipeline，基于end-to-end training的CNN。
网络直接操作raw sensor data，并替代了传统image processing pipeline的大多数（因为其在这种数据上的表现很差）

