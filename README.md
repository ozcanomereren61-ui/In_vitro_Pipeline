📂 Repository Structure
The analysis is broken down into four modular Python scripts:

1_sequence_alignment.py
Uses Biopython and the NCBI Entrez API to fetch protein sequences for Human SEPT9 and Yeast Cdc3. It performs local and global alignments to identify continuous identical sequence islands ("Fungal Islands") and calculates the affinity score of the most highly conserved regions.

2_molecular_docking.py
Automates the 3D structural preparation and docking simulation.

Downloads PDB structures (6UQS for Human, 2QAG for Yeast).

Uses OpenBabel to clean structures and generate a GTP ligand from a SMILES string.

Executes AutoDock Vina via Python's subprocess to calculate the binding affinity (kcal/mol) of the conserved GTP-binding pocket (P-loop) in both species.

3_evolutionary_network.py
Interfaces with the STRING Database API to construct the evolutionary network. It checks whether known human cancer drivers and cytoskeletal components (like FLNA, RTKN) possess ancient yeast orthologs, categorizing the protein "engine parts" into ancient or modern evolutionary additions.

4_bridge_hunt.py
Investigates indirect protein connections. When direct binding is absent between SEPT9 and downstream cancer pathways (like RHOA or CDC42), this script queries the STRING network to find overlapping secondary partners. It specifically tests the hypothesis that the SEPT7 complex acts as the evolutionary bridge connecting ancient septin engines to modern mammalian motility pathways.
