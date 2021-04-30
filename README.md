# COMP3278 Face Recognition Project

*******
### Members

Chen Huijun	3035533367
He Yifu	3035533836
Lee Yu-Ting	3035555743
Yunxiang Fu	3035719026
Yihua Chen	3035661346

### Functions

1. Student can login with his/her face. When login is successful, a welcome message is displayed.
2. If student has tutorial/lecture within one hour, the Course Name, Course Information, Teacher, Zoom URL, Classroom, Starting Time, Lecture/tutorial notes will be displayed.
3. The student can click on buttons next to "Zoom URL" and "Lecture/tutorial notes" to direct them to relevant websites.
4. The student can choose to send this information to his/her email by clicking the "SendMail" button.
5. If student does not have classes at the moment, the GUI will display two timetables: one for lectures and one for tutorials.
6. The login time and the period of stay is stored in the login_history table
7. We have a friendly reminder to lower the confidence level during login if the student cannot login at first.
8. The background color of our GUI depends on the student's UID.


## Run

### 1. Face Recognition

#### 1.1 Collect Face Data
```
python face_capture.py
```
The program with then ask you to enter your name. (Please enter one of the following names: )
The camera will be activated and the captured images will be stored in `data/Jack` folder.      
**Note:** Only one person’s images can be captured at a time.

#### 1.2 Train a Face Recognition Model
```
python train.py
```
`train.yml` and `labels.pickle` will be created at the current folder.


### 2. Login Interface
```
python faces_gui.py
```

### 3. Testing lecture/tutorial
To test the function that informs the student if he/she has lecture/tutorial in one hour, please edit the date and time in line 166 and 171 of facerecognition.sql respectively. We assume that tutorials and lecture last at least one hour and there is no overlap.
```
line 166: insert into lecture values ("Lecture 1", "COMP3278", "2021-1", "2021-04-29", "22:30:00", "https://hku.zoom.us", "Zoom", "https://moodle.hku.hk/course/view.php?id=80047", "Dr. Luo", "Today's topic is Indexing");

line 171: insert into tutorial values ("Tutorial 1", "COMP3278", "2021-1", "2021-04-29", "22:30:00", "https://hku.zoom.us", "CPD-2.42", "https://moodle.hku.hk/", "tutor_name", "tutor_msg");

```
### 4. Testing email function
To test the email function, please change the original email address to your own email on line 131 of facerecognition.sql.
```
line 131: INSERT INTO student VALUES (3, "JACK", "2390778522@qq.com", NOW(), NOW());
```
