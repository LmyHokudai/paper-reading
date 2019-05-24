# 1. 摘要
低光影像很有挑战性：低光子量和低信噪比

短曝：noise

长曝：blur且通常不实际

一系列去噪、去模糊和增强技术在极限条件下并不是很有效

文章为low-light image processing的learning-based pipeline提出了raw short-exposure low-light image和对应long-exposure reference images的dataset。

通过dataset，设计了处理低光影像的pipeline，基于end-to-end training的CNN。

网络直接操作raw sensor data，并替代了传统image processing pipeline的大多数（因为其在这种数据上的表现很差）

# 2. Introduction

Noise在低光下尤为棘手。高ISO可以提高亮度，也增强了noise。像是scaling或histogram stretching的后处理并不会解决低信噪比的问题（因为低光子量）。有物理的方法可以提高低光下的SNR，包括打开光圈、延长曝光时间、以及使用闪光灯，但这些方法也有自己的缺点。比如增加曝光时间会导致因相机抖动或物体运动而引起的模糊。

低光下的fast imaging是计算摄影学里面一个著名的挑战。研究者们已经提出了用于去噪、去模糊和增强的技术，但是这些技术通常假定是在稍微昏暗中的环境（带有中等水平的噪声）下拍摄的。但是本文关注点是极其有限光照的极限低光拍摄（如月光）+短曝（大约在摄影率下）。在这样的设定下，传统的camera processing pipeline崩溃掉，并且不得不从raw sensor data中重建。

