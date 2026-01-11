README.md
Courier Service – Coding Challenge (Everest Engineering)

This console application solves both parts of the courier service problem:

Problem 1 – Delivery Cost Estimation with Offers

Problem 2 – Delivery Time Estimation

The program reads input from standard input (stdin) and prints results to standard output (stdout).

Prerequisites

.NET 8 SDK

Visual Studio 2022 or later (or dotnet CLI)

Project Setup

Open the solution in Visual Studio

Ensure offers.json exists in the project

Set offers.json property:

Copy to Output Directory → Copy if newer

This file contains all offer rules (OFR001, OFR002, OFR003).

How to Run

From Visual Studio:

Press Ctrl + F5

From terminal:

dotnet run

Problem 1 – Delivery Cost Estimation
Input Format
base_delivery_cost no_of_packages
pkg_id weight_in_kg distance_in_km offer_code
pkg_id weight_in_kg distance_in_km offer_code
...

Input File: input_problem1.txt

Create a file named input_problem1.txt in the project folder with this content:

100 3
PKG1 5 5 OFR001
PKG2 15 5 OFR002
PKG3 10 100 OFR003

Run Problem 1
dotnet run < input_problem1.txt

Expected Output
PKG1 0 175
PKG2 0 275
PKG3 35 665

Problem 2 – Delivery Time Estimation

Problem 2 extends Problem 1 by adding vehicle and scheduling logic.

Input Format
base_delivery_cost no_of_packages
pkg_id weight_in_kg distance_in_km offer_code
...
no_of_vehicles max_speed max_carriable_weight

Input File: input_problem2.txt

Create a file named input_problem2.txt in the project folder with this content:

100 5
PKG1 50 30 OFR001
PKG2 75 125 OFFR0008
PKG3 175 100 OFFR003
PKG4 110 60 OFFR002
PKG5 155 95 NA
2 70 200

Run Problem 2
dotnet run < input_problem2.txt

Expected Output
PKG1 0 750 3.98
PKG2 0 1475 1.78
PKG3 0 2350 1.42
PKG4 105 1395 0.85
PKG5 0 2125 4.19

---------------------------Unit Tests Executed-------------------------

Problem-1: Cost & Discount Calculation

Validate base delivery cost calculation

Validate discount percentage application

Validate offer eligibility (weight & distance ranges)

Validate invalid / unknown offer handling

Validate sample PDF input vs expected output
---------------------------------------------------------------------
Problem-2: Vehicle Scheduling & Delivery Time

Validate package grouping into shipments based on:

Maximum number of packages

Maximum total weight

Shortest farthest-distance tie-break

Validate max-load constraint enforcement

Validate vehicle assignment and reuse

Validate round-trip travel time calculation

Validate per-package delivery time computation

Validate decimal truncation (not rounding) to 2 places

Validate scheduling against official sample PDF
