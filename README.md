# MOSE Project

This is the Multimodal Online Student Engagement Dataset. This dataset is a collaborative effort by Catherine (Jialin Li) and Alia (Alia Waleed), designed to support research on online student engagement. It includes a variety of multimedia components for in-depth analysis.

---

## Dataset Overview

### Quick Reference
For a concise introduction to the dataset and its intricacies, check out our [presentation slides](https://docs.google.com/presentation/d/1oICvGvWpDMS1Ro6-yWFDrBTs-GKh_TB4LxYbBjpdD5Y/edit?usp=sharing).

### Raw Videos

Access the raw video recordings directly from Zoom in the [Raw Videos](https://drive.google.com/drive/folders/12e2aJ3oW91NYt9XyptG9BrYOB44ag_Xr?usp=drive_link) directory. Here's a snapshot:
- **Content**: Nine raw videos in total:
  - Seven on "Intro to AI" (avg. 32 mins each)
  - Two on "Mathematics" (avg. 77 mins each)
- **Naming**: Videos follow the "date_Instructor Name" format, e.g., "23092021_Pierre." Subsequent videos from the same day/instructor are appended with a sequence, like "23092021_Pierre_2."
- **Subfolders**: Each of the nine primary folders consistently houses:
  1. `audio_file.m4a`
  2. `share_screen.mp4`
  3. `speaker_view.mp4`
  4. `students_gallery_view.mp4`
  5. `chat_box.mp4`



### Preprocessed Data
Due to student's disconnect drop-off and reconnect join in, the window's arrangement in the recorded view may change back and forth. To solve this, we convert the raw grid_view video data into several unchanged grid_view Zoom recordings. Here's the sequence:

| # | Name | Content | Processing Step | Notes |
|---|------|---------|-----------------|-------|
| 0 | [**Raw Video**](https://drive.google.com/drive/folders/12e2aJ3oW91NYt9XyptG9BrYOB44ag_Xr?usp=drive_link) | - | The original raw video data. | - |
| 1.1 | **Unchanged grid_view Zoom recordings** | Student, lecturer | Splitted from 0 (students_gallery_view.mp4) using [Time Stamp Spreadsheet](https://docs.google.com/spreadsheets/d/1pYKqmghlGIbarUW7rUkTX_hiaAkYlV_0R-ExDdXn0_c/edit#gid=0) | Inside the `Cropped_videos` folder, find the `lecture` folder. Each lecture contains subfolders representing unchanged chunks of the original lecture. |
| 1.2 | [**Unchanged Individual Zoom recordings**](https://drive.google.com/drive/folders/1QVx7_Nm5LzYlcQAmjdksaA283VB_LBP-?usp=share_link) | Student, lecturer | Cropped from 1.1 using [Python Script for Cropping](https://drive.google.com/file/d/1je9xFKXrH3lmTsdaFkkWXOuW9xnjE0tp/view?usp=share_link) according to [Text to record People in Videos](https://docs.google.com/spreadsheets/d/1kwJogK-am3mgfxi7gFUr6KqTaWl5ET8fBsAqks86ZKQ/edit?usp=share_link) | Inside each subfolder, the "original" folder represents 1.2 in the corresponding subfolder. |
| 1.3 | **10-Second Individual recording** | Student, lecturer | Splitted from 1.2 using [Python Script for Splitting](https://drive.google.com/file/d/18RaKtyPWgcPoat-nhkxFzW_z0JOlKncx/view?usp=drive_link) | Sample 1.3 file name: 23092021_Pierre_10_Khalid_8.mp4 (date, professor, lecture segment, student name, 10-sec increment number) |
| 2.1 | [**Unchanged Shared Screen recording**](https://drive.google.com/drive/folders/1kZtNqy9UCAdt5JRcz0sCyDA0b9YTWylD?usp=share_link) | Share screen | Splitted from 0 (share_screen.mp4) using [Time Stamp Spreadsheet](https://docs.google.com/spreadsheets/d/1pYKqmghlGIbarUW7rUkTX_hiaAkYlV_0R-ExDdXn0_c/edit#gid=0) | - |
| 2.2 | **10-Second Shared Screen recording** | Share screen | Splitted from 2.1 using [Python Script for Splitting](https://drive.google.com/file/d/18RaKtyPWgcPoat-nhkxFzW_z0JOlKncx/view?usp=drive_link) | - |
| 3 | [**10-Second contextual recording**](https://drive.google.com/drive/folders/1OiT_cTSnfhF_PQ5bR3oGt0XUJs8D4-CF?usp=share_link) | Share screen, student, lecturer | Combined 1.3 with 2.2 | In "cropped video", find each lecture folder. Inside each lecture folder, find the "final" folder.  Outcome: 16,491 10-sec videos|
| 4 | [**Video uploads to Youtube for Annotations**](https://docs.google.com/spreadsheets/d/1kwJogK-am3mgfxi7gFUr6KqTaWl5ET8fBsAqks86ZKQ/edit?usp=share_link) | Share screen, student, lecturer | Upload 3 to YouTube | - |

---

### Annotation Results

The 10-second student clips were annotated by crowdsourcing workers on Appen. Each video received 10 engagement annotations on attributes such as bored, focused, and engaged.

#### 1. Questionnaire Creation
- Created a questionnaire with engagement attributes.
- Added context questions, e.g., "Is the professor explaining slides?"
- Distributed jobs and received back the annotated CSV file.
  - [Video URLs](#)
  - [Questionnaire Document](#)
  - [Annotation Account Detail](#)

#### 2. Annotation Cleaning & Statistical Validation

**Fundamental Pre-processing:**
- Encoding: Converted text to numerical data. [Code](#)
- Handled null values.

**Advanced Processing for Validation:**
- Inter-rater agreement with ICC.
  - Removed outliers.
  - [Slides](#)
  - [Code](#)
  - [Cleaned CSV](#)

#### 3. Annotation Distributions & Visualizations
- Examined correlations between attributes. [Slides Report](#)

#### 4. Manipulation (Aggregating / Averaging)
- Explored methods to create dataset labels. [Code](#)

---

### Machine Learning Models

#### Data Preparation:
- Preprocessed videos into image frames for visual analysis.
- Adapted annotations to the expected model format (CSV to PKL).
- Normalized annotation values from 0 to 1.
- Split data into train (60%), validation (20%), and test (20%) sets.

#### Baseline Model:
- Tested three models: HRNet, Swin Transformer, and VAT.
  - On full unsorted data.
  - On data filtered by ICC.

#### Personalized Models:
- Trained separate HRNet models for each professor.

