# Analysis notebooks

Jupyter notebooks for the two-photon imaging and connectome analyses.

## Setup

```
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

## Before running a notebook

Each notebook has a settings cell near the top. Replace every `your/path/here` with the location of the data files on your computer. The file names after `your/path/here/` are the names of the files in the data deposit.

`synapse_clusters_soma_anchored-finalIDs.ipynb` reads from neuPrint (optic-lobe:v1.1). Replace `"your neuPrint token here"` with your own token, which you can get from https://neuprint.janelia.org (Account > Auth Token).

## Notebooks

Organizing data
- `organize_snfr_to_hdf5.ipynb`: reads the iAChSnFR and iGluSnFR trace CSVs and writes them into one HDF5 file (`snfr.h5`).

Trace plots
- `plot_from_hdf5_lowpass.ipynb`: mean ± SEM traces per condition and per compartment (`cc.h5`).
- `plot_contrastseries_from_hdf5.ipynb`: mean responses to each contrast (`contrastseries_hylight2.h5`).
- `plot_stimlengths_from_hdf5_lowpass.ipynb`: responses to different stimulus durations (`durationseries-hylight.h5`).
- `plot_snfr_from_hdf5_lowpass.ipynb`: SnFR responses to different stimulus durations (`snfr.h5`).

AUC and tPeak
- `auc_from_hdf5.ipynb`: absolute AUC of Ca and HyLight responses and their ratio; saves an AUC table (CSV).
- `tpeak_from_hdf5.ipynb`: time to peak of Ca and HyLight responses; saves a tPeak table (CSV).
- `compare_auc_tpeak.ipynb`: compares the saved AUC and tPeak tables across conditions and compartments.
- `stimlengths_auc_tpeak.ipynb`: AUC and tPeak for the stimulus-duration recordings (`durationseries-hylight2.h5`).

Connectome
- `synapse_clusters_soma_anchored-finalIDs.ipynb`: clusters each neuron's synapses along its arbor, starting at the soma, and saves synapse counts per cluster (CSV).
- `auc_vs_synapse_fractions_clean_counts.ipynb`: correlates the HyLight/Ca AUC ratio of each compartment with the fraction of synapses in that compartment.
