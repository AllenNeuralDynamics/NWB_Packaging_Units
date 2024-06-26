# Export units to NWB
## NWB_Packaging_Units


### Description

This capsule is designed to append units information to an existing NWB file.


### Inputs

The `data/` folder must include an input NWB file and the output of the 
[aind-ephys-result-collector](https://github.com/AllenNeuralDynamics/aind-ephys-results-collector) capsule, including:

- `spikesorted`: collected sorted folders from spike sorting
- `postprocessed`: collected postprocessed folders from postprocessing
- `curated`: collected curated folders from curation

In addition, the capsule needs the the original session data (e.g., "ecephys_664438_2023-04-12_14-59-51") and
all JSON files generated by the [aind-ephys-job-dispatch](https://github.com/AllenNeuralDynamics/aind-ephys-job-dispatch),
so that recordings can be reloaded.

### Parameters

The `code/run` script takes no arguments.

### Output

The output of this capsule is a series of NWB files in the `results/nwb` folder.

One NWB file is generated for each *block* (e.g., Open Ephys experiment) and *segment* (e.g., Open Ephys recording).
Each NWB file contains multiple streams, i.e., multiple probes.

The name of the NWB file is as follows:
`{nwb_original_file_name}_{block}_{recording_name}.nwb`
