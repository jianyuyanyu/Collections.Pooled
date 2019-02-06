``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|        Method | CountToAdd | InitialSetSize |           Mean |         Error |       StdDev |         Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|-------------- |----------- |--------------- |---------------:|--------------:|-------------:|---------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|   **HashSet_Add** |          **1** |              **0** |     **3,112.0 ns** |     **891.95 ns** |   **2,587.7 ns** |     **1,245.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                **24 B** |
| PooledSet_Add |          1 |              0 |     3,646.3 ns |   1,081.63 ns |   3,120.7 ns |     1,415.0 ns |  1.59 |    1.83 |           - |           - |           - |                24 B |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |          **1** |        **8000000** |       **595.9 ns** |      **63.02 ns** |     **161.6 ns** |       **605.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_Add |          1 |        8000000 |       613.4 ns |      69.58 ns |     178.4 ns |       590.0 ns |  1.09 |    0.40 |           - |           - |           - |                   - |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |        **100** |              **0** |    **18,954.4 ns** |   **2,798.27 ns** |   **8,162.7 ns** |    **17,285.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |              **8232 B** |
| PooledSet_Add |        100 |              0 |    15,018.7 ns |   2,028.77 ns |   5,788.2 ns |    13,490.0 ns |  0.94 |    0.55 |           - |           - |           - |              2400 B |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |        **100** |        **8000000** |     **8,176.2 ns** |   **1,108.70 ns** |   **3,163.2 ns** |     **6,940.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_Add |        100 |        8000000 |    11,982.6 ns |   3,117.63 ns |   8,945.1 ns |     6,950.0 ns |  1.56 |    1.20 |           - |           - |           - |                   - |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |      **10000** |              **0** |   **781,361.5 ns** |  **43,445.53 ns** | **126,732.7 ns** |   **762,985.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |            **538456 B** |
| PooledSet_Add |      10000 |              0 |   818,797.0 ns |  40,618.63 ns | 118,486.4 ns |   796,345.0 ns |  1.08 |    0.24 |           - |           - |           - |            240000 B |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |      **10000** |        **8000000** |   **423,049.9 ns** |  **29,730.28 ns** |  **84,822.2 ns** |   **404,485.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_Add |      10000 |        8000000 |   644,825.0 ns |  54,412.40 ns | 160,436.2 ns |   659,940.0 ns |  1.61 |    0.47 |           - |           - |           - |                   - |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |     **100000** |              **0** | **5,348,145.0 ns** | **282,304.55 ns** | **763,226.8 ns** | **5,171,825.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |           **2327112 B** |
| PooledSet_Add |     100000 |              0 | 4,723,294.4 ns | 347,818.59 ns | 969,579.2 ns | 4,364,290.0 ns |  0.89 |    0.16 |           - |           - |           - |                   - |
|               |            |                |                |               |              |                |       |         |             |             |             |                     |
|   **HashSet_Add** |     **100000** |        **8000000** | **3,336,310.0 ns** | **148,737.18 ns** | **429,140.8 ns** | **3,265,660.0 ns** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_Add |     100000 |        8000000 | 3,270,822.6 ns | 138,146.42 ns | 396,368.0 ns | 3,140,330.0 ns |  0.99 |    0.16 |           - |           - |           - |                   - |