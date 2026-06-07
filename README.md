# iEEG IED Detection and Amplitude Extraction Pipeline

This repository contains a Jupyter notebook that implements a supplementary pipeline for the detection, peak alignment, amplitude extraction, and clustering of intracranial electroencephalography (iEEG) interictal epileptiform discharges (IEDs).

## Repository Contents

* **`multichannel-detection-with_amp.ipynb`**
  * Complete processing pipeline for a single subject across all iEEG channels.
  * Refines detected IED events through peak alignment and amplitude extraction.
  * Calculates spike amplitudes relative to a pre-spike baseline.
  * Groups temporally overlapping spikes across channels into distinct multichannel events.
  * Saves detailed spike information, amplitude measurements, and event group labels into a single exportable CSV file.

* **`requirements.txt`**
  * List of Python packages and versions required to run the pipeline.

## Output CSV Structure

The pipeline outputs a detailed CSV file (e.g., `multichannel_spikes_detail.csv`) containing all successfully aligned and validated spike events:

* **`channel`**: Name of the channel on which the spike was detected.
* **`peak_index`**: Sample index of the detected spike peak in the continuous recording.
* **`relative_spike_amplitude`**: Z-scored spike amplitude calculated as the peak amplitude relative to the mean baseline amplitude in the pre-spike window.
* **`group_id`**: Identifier of the clustered multichannel event to which the spike belongs, grouping together overlapping spikes across channels within a 200 ms window.
