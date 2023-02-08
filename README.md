# Optimized channel selection algorithm using PSD

The objective of the research internship was to extract delta waves from sleeping babies to generate neuroacoustic music from them to make the babies relax and sleep to their own neuroacoustic music. The data is first cleaned using average referencing, filtering and epochs are created later to use the data with the MNE library of python.

Later Power Spectral Density (PSD) of the delta band (0.1 - 4 Hz) is calculated for all channels to select the channels which are abundant with delta waves. The selected channels are then checked for correlation to get rid of noise or any non-delta wave signals generated while data acquistion. The idea is that the EEG signals are synchronised when the baby relaxes and the correlation of those channels are higher compared to noisy channels. The channels with highest correlation are selected for delta wave extraction.

With the selected channels, delta waves are extracted using ADSR envelope method using relative thresholds. The extracted delta waves are then put in a text file based on their ADSR envelopes and sent for neuroacoustic music generation. The neuroacoustic sounds are modulated based on the ADSR envelope of the extracted delta waves.

## Installation instructions

```
# Create a virtual environment:
conda create --name Neuro --python=3.9
conda activate Neuro

# Install required packages:
pip install -r requirements.txt
```

## Usage instructions

Input data has to be in the form of .fdt and .set to be used with the MNE library. Other formats are also accepted; change the import statement based on your data. Output format is given with out1_test.txt file in the repository.

## References

1. ["Mapping of Cortical Activity in the First Two Decades of Life: A High-Density Sleep Electroencephalogram Study"](https://pubmed.ncbi.nlm.nih.gov/20926647/)