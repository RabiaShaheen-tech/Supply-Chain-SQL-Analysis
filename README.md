# Supply Chain SQL Analysis
**Tools used:** SQL (SQLite), DB Browser for SQLite  
**Dataset:** 200 orders | 20 products | 6 Ontario-based suppliers | 2023–2024

## Business Question
Which suppliers and products pose the greatest risk to supply 
chain continuity through delays and critically low stock levels?

## Dataset Overview
This analysis covers procurement orders for UV water treatment 
components across 6 Ontario suppliers including electronics, 
mechanical parts, and UV components categories.

## Key Findings

### 1. Delay Performance by Supplier
| Supplier | Delayed Orders |
|---|---|
| SealTech | 10 |
| Trojan UV | 9 |
| TechParts Inc | 9 |
| MetalWorks CA | 8 |
| SensorPro | 7 |
| AquaShield | 7 |

SealTech had the highest number of delayed orders (10), 
followed closely by Trojan UV and TechParts Inc (9 each).

### 2. Critical Risk Items — Delayed AND Below Reorder Point
14 products were identified as simultaneously delayed 
AND below their reorder point — requiring immediate action.

| Product | Supplier | Stock Left | Status |
|---|---|---|---|
| Power Supply Unit | TechParts Inc | 3 | ⚠️ CRITICAL |
| Sleeve Assembly | AquaShield | 1 | ⚠️ CRITICAL |
| Reactor Chamber | Trojan UV | 4 | ⚠️ CRITICAL |
| UV Sensor | SensorPro | 7 | ⚠️ CRITICAL |
| Cleaning Ring | SealTech | 14 | HIGH RISK |
| Inlet Valve | MetalWorks CA | 29 | HIGH RISK |
| Quartz Sleeve | AquaShield | 23 | HIGH RISK |
| Flow Sensor | SensorPro | 39 | MONITOR |

### 3. Supplier Risk Summary
- AquaShield appeared 4 times in critical items list — 
  highest risk supplier despite lower total delay count
- TechParts Inc has 3 critical items — electronics supply 
  chain most vulnerable
- Power Supply Unit (3 units remaining) is the single 
  most urgent restocking priority

## Recommendations
1. **Immediate action:** Raise emergency purchase orders for 
   Power Supply Unit (3 left), Sleeve Assembly (1 left), 
   and Reactor Chamber (4 left)
2. **Supplier review:** Initiate performance review with 
   AquaShield — 4 critical stock situations indicate 
   unreliable delivery
3. **SealTech monitoring:** Highest delay count (10) warrants 
   contract review and backup supplier identification
4. **Buffer stock policy:** Recommend increasing reorder points 
   for Electronics category given TechParts Inc delay pattern

## SQL Queries
See queries.sql for all 10 queries used in this analysis.

## Skills Demonstrated
- SQL filtering (WHERE, AND)
- Aggregation (COUNT, SUM, AVG, ROUND)
- Sorting and grouping (ORDER BY, GROUP BY)
- Multi-condition analysis
- Business insight communication
- Supply chain domain knowledge
