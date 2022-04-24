# EdaoQuant -- Our closed-source quant-trading platform

My EdaoQuant team focuses on the potential profits in speculative HFT markets and targets building a proprietary trading firm within five years.

## Architecture Design

EdaoQuant comprises four main modules: Edaopipeline, Edaotrader, Edaoanalyzer, and object storage.

1. Edaopipeline: It extensively collects stock data from various data sources (security companies, exchanges, streaming data sources, etc.). It contains an ETL pipeline for converting those data into a unified parquet format.

2. Object storage: Stock data processed by Edaopipeline will be loaded into a cloud-native object-store platform for future use.
   Each object is stored in Parquet format and thus can be easily analyzed by typical data-science kits like Pandas, NumPy and PyArrow.
   We've detailed the trade-offs between object stores with the commonly-applied [DolphinDB](https://www.dolphindb.com) and [KDB+](https://code.kx.com/q/) in the quant industry and concluded that parquet in cloud-native objects is best suited for large-scale backtesting.

3. Edaoanalyzer: Backtesting in Edaoanalyzer can handle TB-scale L2 data, hundreds of stocks, and thousands of ML-optimizing iterations in a bounded time (e.g., tens of minutes).
   To ease the quant research and development and achieve high scalability, we leverage the strength of [Ray](https://docs.ray.io/en/master/index.html) as the distributed-computing framework to run L2 backtesting in parallel on a large-scale cluster.

4. Edaotrader: To run an online strategy, Edaotrader provides a low-latency deployment, exploiting the edge of Rust.
   Low-level system optimizations are integrated into the system for a well-tuned low-latency code path.

## Partner Wanted

Currently, we have ~20 members, mainly from top colleges in China and America, majoring in CS, statistics, and finance.
And we are expecting to have more partners to investigate the challenging technical problems and fancy market strategies.

A broad background is welcomed, including Statistics, Math, Physics, and Computer Science (especially experienced computer system researcher or machine learning researcher).

We offer a competitive remuneration for interns, with the chance to engage in a critical position in a prop trading firm from an early startup phase.

Join us if you are motivated and interested in my team. My email is zl31wang@gmail.com

<div align=center><img width=200 height=200 src="https://user-images.githubusercontent.com/46620760/162664743-cb2963cc-9761-4975-97ee-2736b39b6f9d.png"/></div>

