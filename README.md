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

| # | Name | Content | Processing Step | Notes |
|---|------|---------|-----------------|-------|
| 1 | [**Raw Video**](https://drive.google.com/drive/folders/12e2aJ3oW91NYt9XyptG9BrYOB44ag_Xr?usp=drive_link) | - | The original raw video data. | - |
| 2 | **Unchanged grid_view Zoom recordings** | Student, lecturer | Splitted from 1 (students_gallery_view.mp4) using [Time Stamp Spreadsheet](https://docs.google.com/spreadsheets/d/1pYKqmghlGIbarUW7rUkTX_hiaAkYlV_0R-ExDdXn0_c/edit#gid=0) | Inside the `Cropped_videos` folder, find the `lecture` folder. Each lecture contains subfolders representing unchanged chunks of the original lecture. |
| 3 | [**Unchanged Individual Zoom recordings**](https://drive.google.com/drive/folders/1QVx7_Nm5LzYlcQAmjdksaA283VB_LBP-?usp=share_link) | Student, lecturer | Cropped from 2 using [Python Script for Cropping](https://drive.google.com/file/d/1je9xFKXrH3lmTsdaFkkWXOuW9xnjE0tp/view?usp=share_link) according to [Text to record People in Videos](https://docs.google.com/spreadsheets/d/1kwJogK-am3mgfxi7gFUr6KqTaWl5ET8fBsAqks86ZKQ/edit?usp=share_link) | Inside each subfolder, the "original" folder represents step 3 in the corresponding subfolder. |
| 4 | **10-Second Individual recording** | Student, lecturer | Splitted from 3 using [Python Script for Splitting](https://drive.google.com/file/d/18RaKtyPWgcPoat-nhkxFzW_z0JOlKncx/view?usp=drive_link) | - |
| 5 | [**Unchanged Shared Screen recording**](https://drive.google.com/drive/folders/1kZtNqy9UCAdt5JRcz0sCyDA0b9YTWylD?usp=share_link) | Share screen | Splitted from 1 (share_screen.mp4) using [Time Stamp Spreadsheet](https://docs.google.com/spreadsheets/d/1pYKqmghlGIbarUW7rUkTX_hiaAkYlV_0R-ExDdXn0_c/edit#gid=0) | - |
| 6 | **10-Second Shared Screen recording** | Share screen | Splitted from 5 using [Python Script for Splitting](https://drive.google.com/file/d/18RaKtyPWgcPoat-nhkxFzW_z0JOlKncx/view?usp=drive_link) | - |
| 7 | [**10-Second contextual recording**](https://drive.google.com/drive/folders/1OiT_cTSnfhF_PQ5bR3oGt0XUJs8D4-CF?usp=share_link) | Share screen, student, lecturer | Combined 4 with 6 | In "cropped video", find each lecture folder. Inside each lecture folder, find the "final" folder. |
| 8 | [**Video uploads to Youtube for Annotations**](https://docs.google.com/spreadsheets/d/1kwJogK-am3mgfxi7gFUr6KqTaWl5ET8fBsAqks86ZKQ/edit?usp=share_link) | Share screen, student, lecturer | Upload 6 to YouTube | - |
