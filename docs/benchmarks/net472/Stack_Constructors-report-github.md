``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                       Method |      N |   Type |           Mean |         Error |        StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|--------------:|--------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackICollectionConstructor** |   **1000** |    **Int** |       **246.9 us** |      **1.655 us** |      **1.548 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.97 KB** |
| PooledICollectionConstructor |   1000 |    Int |     1,025.6 us |      3.252 us |      2.539 us |  4.16 |    0.02 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 |    Int |     7,517.0 us |     21.997 us |     20.576 us | 30.45 |    0.19 |   2687.5000 |           - |           - |          8274.58 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     8,863.3 us |     23.344 us |     21.836 us | 35.90 |    0.27 |     15.6250 |           - |           - |            78.13 KB |
|                              |        |        |                |               |               |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |   **1000** | **String** |       **731.9 us** |      **2.330 us** |      **2.065 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |          **7876.88 KB** |
| PooledICollectionConstructor |   1000 | String |     2,766.7 us |      6.955 us |      5.808 us |  3.78 |    0.01 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 | String |    12,834.1 us |     34.059 us |     30.193 us | 17.54 |    0.07 |   5281.2500 |           - |           - |         16271.19 KB |
| PooledIEnumerableConstructor |   1000 | String |    16,827.6 us |     42.295 us |     35.319 us | 22.99 |    0.07 |           - |           - |           - |               86 KB |
|                              |        |        |                |               |               |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** |    **Int** |     **2,702.1 us** |     **20.101 us** |     **18.802 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |         **39210.66 KB** |
| PooledICollectionConstructor |  10000 |    Int |    14,570.9 us |     42.940 us |     40.166 us |  5.39 |    0.04 |           - |           - |           - |            39.13 KB |
|  StackIEnumerableConstructor |  10000 |    Int |    74,988.9 us |    195.381 us |    182.759 us | 27.75 |    0.21 |  41571.4286 |           - |           - |        128520.07 KB |
| PooledIEnumerableConstructor |  10000 |    Int |    91,923.0 us |    475.421 us |    444.709 us | 34.02 |    0.35 |           - |           - |           - |            78.67 KB |
|                              |        |        |                |               |               |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** | **String** |     **7,202.5 us** |     **35.527 us** |     **33.232 us** |  **1.00** |    **0.00** |  **24992.1875** |           **-** |           **-** |         **78371.88 KB** |
| PooledICollectionConstructor |  10000 | String |    36,671.9 us |    128.213 us |    119.931 us |  5.09 |    0.03 |           - |           - |           - |            39.43 KB |
|  StackIEnumerableConstructor |  10000 | String |   188,601.2 us |    602.025 us |    563.135 us | 26.19 |    0.13 |  41333.3333 |  41333.3333 |  41333.3333 |        256378.94 KB |
| PooledIEnumerableConstructor |  10000 | String |   186,434.0 us |  1,093.395 us |  1,022.762 us | 25.89 |    0.18 |           - |           - |           - |               88 KB |
|                              |        |        |                |               |               |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** |    **Int** |    **63,799.1 us** |    **766.220 us** |    **716.722 us** |  **1.00** |    **0.00** |  **22444.4444** |  **22111.1111** |  **22111.1111** |        **390873.25 KB** |
| PooledICollectionConstructor | 100000 |    Int |   122,304.0 us |    201.676 us |    188.648 us |  1.92 |    0.02 |           - |           - |           - |               40 KB |
|  StackIEnumerableConstructor | 100000 |    Int |   841,217.4 us |  5,382.662 us |  4,771.590 us | 13.19 |    0.14 | 188000.0000 | 148000.0000 | 146000.0000 |       1027450.81 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   847,118.1 us |  1,588.554 us |  1,485.934 us | 13.28 |    0.14 |           - |           - |           - |               80 KB |
|                              |        |        |                |               |               |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** | **String** |   **481,162.5 us** |  **2,763.151 us** |  **2,584.653 us** |  **1.00** |    **0.00** |  **27000.0000** |  **27000.0000** |  **27000.0000** |        **781554.02 KB** |
| PooledICollectionConstructor | 100000 | String |   314,750.6 us |  1,533.576 us |  1,434.508 us |  0.65 |    0.00 |           - |           - |           - |               40 KB |
|  StackIEnumerableConstructor | 100000 | String | 1,675,026.1 us | 12,992.150 us | 11,517.203 us |  3.48 |    0.03 | 327000.0000 | 286000.0000 | 284000.0000 |       2053549.68 KB |
| PooledIEnumerableConstructor | 100000 | String | 1,696,917.0 us |  4,828.155 us |  4,280.034 us |  3.53 |    0.02 |           - |           - |           - |               88 KB |