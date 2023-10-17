# Zoom-Engagement-Dataset 

This is the Multimodal Online Student Engagement Dataset. This dataset is a collaborative effort by Catherine (Jialin Li) and Alia (Alia Waleed), designed to support research on online student engagement. It includes a variety of multimedia components for in-depth analysis.

## Dataset Overview

### Quick Reference Slides
For a quick introduction to the dataset and its details, please review our presentation slides available at [this link](https://docs.google.com/presentation/d/1oICvGvWpDMS1Ro6-yWFDrBTs-GKh_TB4LxYbBjpdD5Y/edit?usp=sharing).

### Raw Videos

The raw video recordings downloaded straightly from zoom. Access these recordings in the [Raw Videos](https://drive.google.com/drive/folders/12e2aJ3oW91NYt9XyptG9BrYOB44ag_Xr?usp=drive_link) folder. Here's what you'll find:

- **Content**: There are a total of nine raw videos, with seven related to "Intro to AI" (averaging 32 minutes each) and two related to "Mathematics" (averaging 77 minutes each).
- **Naming Convention**: Each video is named in the format "date_Instructor Name," for example, "23092021_Pierre." If multiple videos were produced on the same day by the same instructor, the second video is labeled as "23092021_Pierre_2."
- **Consistent Subfolders**: Within each of the nine subfolders, consistently store the following five files:
  1. `audio_file.m4a`
  2. `share_screen.mp4`
  3. `speaker_view.mp4`
  4. `students_gallery_view.mp4`
  5. `chat_box.mp4`

### Preprocessed Data
Due to student's disconnect drop-off and reconnect join in, the window's arrangement in the recorded view may change back and forth. To solve this, we convert the raw grid_view video data into several unchanged grid_view Zoom recordings. Here's the sequence:

1. **Raw Video**: The original raw video data.
2. **Unchanged grid_view Zoom recordings**: Intermediate files created from the raw video.
3. **10-Second Unchanged grid_view Zoom Recordings**: A more granular version of the unchanged grid_view Zoom recordings, allowing for focused analysis.

Detailed timestamps to track window's change: [Time Stamp Spreadsheet](https://docs.google.com/spreadsheets/d/1pYKqmghlGIbarUW7rUkTX_hiaAkYlV_0R-ExDdXn0_c/edit#gid=0).
Python script for cropping [Python Script for cropping](https://drive.google.com/file/d/18RaKtyPWgcPoat-nhkxFzW_z0JOlKncx/view?usp=drive_link).
10-second unchanged grid_view Zoom recordings: [10-Second Unchanged grid_view Zoom Recordings](https://drive.google.com/drive/folders/1_FsZybzov4A_sJx9lNyhSHyO4Pg5Drr6?usp=drive_link).

In order to further facilitates tasks such as personalized engagement analysis, 10 second grid_view zoom recordings are further cropped to become 1o second individual recordings.



