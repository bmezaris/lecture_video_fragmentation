# Artificially-generated Lecture Video Fragmentation Dataset and Ground Truth
We provide a large-scale lecture video dataset consisting of artificially-generated lectures, and the corresponding ground-truth fragmentation, for the purpose of evaluating lecture video fragmentation techniques. 

For creating this dataset, 1498 speech transcript files (generated automatically by ASR software) were used from the world's biggest academic online video repository, the VideoLectures.NET. These transcripts correspond to lectures from various fields of science, such as Computer science, Mathematics, Medicine, Politics etc. In order to create the synthetic video lectures, all transcripts were randomly split in fragments, the duration of which ranges between 4 and 8 minutes. Each synthetic lecture was then assembled by combining (stitching) exactly 20 randomly selected fragments. 300 such artificially-generated lectures are included in the released dataset. Each such lecture file has a mean duration of about 120 minutes, thus the dataset contains altogether about 600 hours of artificially-generated lectures. Every pair of consecutive fragments in these lectures originally comes from different videos, consequently the point in time where such two fragments are joined is a known ground-truth fragment boundary. All these boundaries form the dataset's ground truth. We should stress that we do not generate the corresponding video files for the artificially-generated lectures (only the transcripts), and one should not try to reverse-engineer the dataset creation process so as to use in some way the visual modality for detecting the fragments in this dataset.

## File format
After you download the provided .zip and unpack it, the extracted folder will contain two sub-folders: 
	
```
1. ALV_srt
2. ALV_srt_GT
```
Each of them contains 300 files.

The **ALV_srt** folder contains the transcripts of every artificially-generated lecture, in the standard SRT format:
```
1. A numeric counter identifying each sequential subtitle
2. The time that the subtitle should appear on the screen, followed by --> and the time it should disappear
3. Subtitle's text itself on one or more lines
4. A blank line containing no text
```
The **ALV_srt_GT** folder contains the ground truth (GT) fragments corresponding to the lectures (transcripts) of the **ALV_srt** folder. Each GT file consists of 3 tab-separated columns and 20 rows, in the following format:

```
<Fragment_ID_1>	<StartTime_1>	<EndTime_1>
<Fragment_ID_2>	<StartTime_2>	<EndTime_2>
<Fragment_ID_3>	<StartTime_3>	<EndTime_3>
.
.
.
<Fragment_ID_20>	<StartTime_20>	<EndTime_20>
```
Each row indicates a fragment. The first column indicates the ID of a fragment while the second and the third column indicate the start and the end time of the fragment respectively.

## License and Citation
This dataset is provided for academic, non-commercial use only. If you find this dataset useful in your work, please cite the following publication where the dataset is introduced:

*D. Galanopoulos, V. Mezaris, “Temporal Lecture Video Fragmentation using Word Embeddings”, Proc. 25th Int. Conf. on Multimedia Modeling (MMM2019), Thessaloniki, Greece, Jan. 2019.*
