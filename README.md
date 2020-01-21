# spatial
All thing spatial, from MERFISH, to histology

To start discussion on spatial data generation, here are some notes from a recent Lung Seed Network call on designing probesets for targeted spatial methods for merFISH.

## Call on 2019.12.02:
### Background information:
MerFISH can deal with up to 128 probes

Computational probeset design from scRNA-seq data:
- can’t be high expression otherwise you get overlaps between pixels due to high-intensity
- medium to low expression (difficult to map from scRNA-seq)

Current common approach:
- use cell labels and combinatorially pick out low and medium expressed genes to maximize distances between clusters

Other approach:
- Jeff Moffit: Bio networks/pathways of interest and grab out all non-high-expression genes, and add some marker genes -> claims this works well


### Challenges:
Not clear yet what medium and low expression is yet (esp. when using scRNA-seq as reference)
- check out what Xiaowei Zhuang’s group used for “highly expressed”
-> Allen group has similar definition

Most of the probe selection has been done on brain:
-> in brain need to separate neuronal subtypes which share a lot of genes, different setup/challenge in lung

Defining markers manually means we face difficulty of cell type vs cell state delineation when we decide what to look for


### Ideas:
- Sasha: probe design to introns so that RNA counts are lower and localized to nucleus
- include TFs as low expressed genes


### Plans for data generation:
Location for spatial data generation:
- proximal airways or distal alveolar unit:
  - probably use latter, or both

What cell identities do we expect? Distal alveolar unit composition:
- Type I and Type II cells
- endothelial cells
- fibroblasts

Sasha: prefer combination of markers that determine a cell type, not just one
- BUT: difficulty of cell type vs cell state... what are we looking for?

Doug: could start data generation in Feb

Costs 20-30k for initial probeset, then can use this probeset again after establishing protocols for cheaper
-> need good gene set!


### Define scope for computational probeset inference:
- Fabian: should define a concrete target, i.e. identify cell type with X% accuracy 
- how to valiate? -> first within exp: split data, test on reconstruction performance on rest
