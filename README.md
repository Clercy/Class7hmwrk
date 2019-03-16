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

******* Fixed the docker issue as requested.
******* generate_charts_hw7.py was updated with the sort from class

Docker update process

lcler@LAPTOP-D2T6EOO0 MINGW64 ~/desktop/class7hmwrk (master)

$ docker build -t class7-image .

Sending build context to Docker daemon  423.3MB

Step 1/11 : FROM ubuntu:16.04

 ---> 7e87e2b3bf7a

Step 2/11 : MAINTAINER Luigi Clerici <Clercy.github.io>


lcler@LAPTOP-D2T6EOO0 MINGW64 ~/desktop/class7hmwrk (master)

$ docker images

REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE

class7-image          latest              8fa0fe1fb7a0        5 days ago          782MB


lcler@LAPTOP-D2T6EOO0 MINGW64 ~/desktop/class7hmwrk (master)

Ran the following:

$ docker run -t -v /${PWD}:/${PWD} -w/${PWD} class7-image housing.data.txt

Namespace(csvfile='housing.data.txt')

housing.data.txt

./generate_charts_hw7.py:40: ParserWarning:

Falling back to the 'python' engine because the 'c' engine does not support regex separators (separators > 1 char and different from '\s+' are interpreted as regex); you can avoid this warning by specifying engine='python'.

      CRIM  ...  MEDV
0     0.01  ...  24.0
1     0.03  ...  21.6
2     0.03  ...  34.7
3     0.03  ...  33.4
.
.
.
.
