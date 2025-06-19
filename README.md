
# Trade Route Analysis using Ontology and Graph Analytics

## Objective
To analyze international trade routes between reporter and partner nations using real trade datasets. The project applies ontology-based data modeling in Palantir Foundry, enabling enriched visualizations and graph-based reasoning for trade dynamics.

## Data Source
Sample datasets were extracted from a global trade data CSV file containing the following fields:
- reporterISO
- partnerISO
- commodityCode
- fobvalue
- modeTransport
- year

## Tools and Technologies
- Language: Python (Pandas, NetworkX, Matplotlib, Seaborn)
- Data Platform: Palantir Foundry
- Ontology Manager: Used for defining custom object types and linkages
- Visualization: Heatmaps and Trade Network Graphs

## Graph Visualizations
1. Trade Heatmap: FOB value between reporterISO and partnerISO.
2. Trade Network Graph: Nodes represent countries; edges represent trade relationships, weighted by trade volume.

## Ontology Design in Palantir Foundry

### Object Types
| Object Name            | Description                                    |
|------------------------|------------------------------------------------|
| ri.trade.Country       | Represents a country involved in trade         |
| ri.trade.Commodity     | Represents traded goods (based on commodity code) |
| ri.trade.TransportMode | Represents the method of transport (e.g., sea, air) |
| ri.trade.TradeRoute    | Represents a directional trade path            |
| ri.trade.Reporter      | The reporting nation in trade                  |
| ri.trade.Partner       | The partner nation in trade                    |

### Linkages
- Reporter ➡ TradeRoute ➡ Partner
- TradeRoute ➡ Commodity
- TradeRoute ➡ TransportMode
- Country ➡ Country (bi-directional routes)

## Schema Fields
- reporterCode, reporterISO
- partnerCode, partnerISO
- commodityCode
- fobvalue
- year
- modeTransport

## Evaluation Criteria Mapping
| Criteria                           | Explanation |
|------------------------------------|-------------|
| Relevance of Objects & Linkages (30%) | The model captures key entities and their relationships for trade analysis |
| Data Modeling Quality (30%)          | Normalized schema supports future data expansion |
| Completeness (20%)                   | Accounts for all critical fields in trade analysis |
| Flexibility and Extensibility (10%)  | Easily extendable to include tariffs, treaties, etc. |
| Reasoning Capabilities (10%)         | Enables trend and path-based reasoning using graphs |

## How to Run
1. Open `project003.ipynb` in Jupyter Notebook or VSCode.
2. Install required Python packages:
   ```bash
   pip install pandas matplotlib networkx seaborn
   ```
3. Run all cells to generate visualizations.
4. Export datasets for import into Palantir Foundry.

## Future Work
- Add predictive modeling for trade disruptions
- Enable temporal analysis of trade routes
- Correlate trade data with economic indicators
