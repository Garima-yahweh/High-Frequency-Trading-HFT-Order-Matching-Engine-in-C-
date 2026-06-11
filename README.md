# High-Frequency Trading (HFT) Order Matching Engine in C++

## Overview

This project implements a low-latency trading simulation system in C++ that models the core functionality of a High-Frequency Trading (HFT) platform. The system processes market orders, maintains an order book, executes trades using matching algorithms, and generates transaction records.

## Features

### Market Data Analytics
- Processes historical market orders from CSV files.
- Generates ticker-wise order statistics.
- Calculates trader-level quantity exposure across multiple securities.

### Order Matching Engine
- Implements a real-time buy/sell order matching system.
- Uses price-time priority for trade execution.
- Supports partial order fills and remaining order management.
- Handles multiple stock tickers with independent order books.

### Trade Execution & Logging
- Matches compatible buy and sell orders automatically.
- Records executed trades with:
  - Ticker
  - Buyer
  - Seller
  - Quantity
  - Execution Price
  - Timestamp
- Exports transaction details into CSV logs.

## System Workflow

```
Market Orders
      |
      v
Order Processing
      |
      v
Order Book Management
      |
      v
Matching Engine
      |
      v
Trade Execution
      |
      v
Transaction Logs
```

## Matching Strategy

The engine follows exchange-style matching rules:

- Buy orders are matched with the lowest available sell price.
- Sell orders are matched with the highest available buy price.
- Orders with the same price follow time priority.
- Supports partial execution when order quantities differ.

## Technologies Used

- C++
- Object-Oriented Programming (OOP)
- Standard Template Library (STL)
- File I/O
- CSV Parsing
- Data Structures

## Data Structures Used

- `vector` for order storage and processing
- `map` for ticker and trader analytics
- `priority_queue` for efficient order matching
- STL algorithms for optimized data handling

## Sample Execution

### Input

```
BUY Rajesh INFY 100 2450.00
SELL Priya INFY 60 2440.00
```

### Output

```
Ticker,Seller,Buyer,Qty,Price,Time
INFY,Priya,Rajesh,60,2440.00,0
```

## Project Structure

```
HFT-Order-Matching-Engine/
│
├── src/
│   └── main.cpp
│
├── data/
│   └── market_orders.csv
│
├── output/
│   └── executed_trades.csv
│
└── README.md
```

## Key Highlights

- Designed an exchange-style order book and matching engine.
- Implemented efficient trade execution using STL-based data structures.
- Built market analytics modules for processing and analyzing trading data.
- Simulated core components of a real-world trading system.

## Future Enhancements

- Multi-threaded order processing.
- Network-based live market data ingestion.
- Latency benchmarking and performance optimization.
- Advanced order types such as market and stop orders.
