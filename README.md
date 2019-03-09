Class 7 Homework

Chart Generation

I reset my chart generator to create 3 column charts as the 4 column run took very long to execute.  After an hour I had only generated 1/4 of the files.  The 3 column generation takes approx. 20 minutes and generates over 1000 files.


Chart Analysis

My analysis was based on finding the ideal scenario to raise a family using the following 3 factors: affordability (MEDV), teaching ratios (PTRATIO) and peace of mind (CRIM).  That is why I targeted the following 3 attributes to help make my decision.


CRIM per capita crime rate by town

PTRATIO pupil-teacher ratio by town

MEDV Median value of owner-occupied homes in $1000’s


I worked with plot charts for generating my visual representations for analysis purposes.  I attempted to produce other types of charts but came back to the plot and each time the chart would evolve giving me the one I preferred the most PLT_MEDV_PTRATIO_CRIM_20193719145.png.  Two others that were generated similarly were PLT_CRIM_PTRATIO_ZN_MEDV_201936174728.png and PLT_CRIM_RAD_MEDV_PTRATIO_201936213828.png.  The last 2 I did not like as much because as a 4 column chart we were adding unnecessary noise to the analysis.  By the end my preferred choice looked better and easier to analyze as it included the 3 attributes I mentioned previously suiting my needs.


Adding a chart legend also helped me greatly as it gave me a reference point to facilitate my task.  Based on chart PLT_MEDV_PTRATIO_CRIM_20193719145.png I think the ideal area of focus would be between respondents 100 to 130 and 310 to 340.  In this area we have a lower than average PTRATIO along with a below average crime rate and the value of homes are hovering around the average.




REACH: DOCKER

I tried making this work but was not able to get further than this portion.

I built my container:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)
$ docker build -t class7-image .
Sending build context to Docker daemon  17.02MB
Step 1/10 : FROM ubuntu:16.04
 ---> 7e87e2b3bf7a
Step 2/10 : MAINTAINER Luigi Clerici <Clercy.github.io>
 ---> Using cache
 ---> 5a4d6caa160f
 .
 .
Successfully built c99f429ba774
Successfully tagged class7-image:latest

I checked for the available containers:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)
$ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
class7-image          latest              c99f429ba774        16 seconds ago      624MB
class7-charts-image   latest              e43bbfccfc05        23 hours ago        624MB
class4-python-image   latest              0106975cd944        3 weeks ago         572MB


Then I tried running it to see the outcome:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)
$ docker run -i class7-image

usage: generate_charts_hw7.py [-h] csvfile
generate_charts_hw7.py: error: the following arguments are required: csvfile


Then I proceeded to create a volume:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)

$ docker volume create myvol7
myvol7

Then I checked the availability:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)

$ docker volume ls
DRIVER              VOLUME NAME
local               myvol7

Then I tried referencing it getting the same error:

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/Desktop/class7hmwrk (master)

$ docker run -v myvol7:/app class7-image
usage: generate_charts_hw7.py [-h] csvfile
generate_charts_hw7.py: error: the following arguments are required: csvfile
