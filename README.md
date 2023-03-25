# Google-Data-Analytics-Capstone-Project-Case-Study-1-Cyclistic-Bike-Share

1.INTRODUCTION:

1.1IN 2016, CYCLISTIC LAUNCHED A SUCCESSFUL BIKE-SHARE OFFERING. SINCE THEN, THE PROGRAM HAS GROWN TO A FLEET OF 5,824 BICYCLES THAT ARE GEOTRACKED AND LOCKED INTO A NETWORK OF 692 STATIONS ACROSS CHICAGO. THE BIKES CAN BE UNLOCKED FROM ONE STATION AND RETURNED TO ANY OTHER STATION IN THE SYSTEM ANYTIME. 

1.2UNTIL NOW, CYCLISTIC’S MARKETING STRATEGY RELIED ON BUILDING GENERAL AWARENESS AND APPEALING TO BROAD CONSUMER SEGMENTS. ONE APPROACH THAT HELPED MAKE THESE THINGS POSSIBLE WAS THE FLEXIBILITY OF ITS PRICING PLANS: SINGLE-RIDE PASSES, FULL-DAY PASSES, AND ANNUAL MEMBERSHIPS. CUSTOMERS WHO PURCHASE SINGLE-RIDE OR FULL-DAY PASSES ARE REFERRED TO AS CASUAL RIDERS. CUSTOMERS WHO PURCHASE ANNUAL MEMBERSHIPS ARE CYCLISTIC MEMBERS. 

1.3CYCLISTIC’S FINANCE ANALYSTS HAVE CONCLUDED THAT ANNUAL MEMBERS ARE MUCH MORE PROFITABLE THAN CASUAL RIDERS. ALTHOUGH THE PRICING FLEXIBILITY HELPS CYCLISTIC ATTRACT MORE CUSTOMERS, MORENO BELIEVES THAT MAXIMIZING THE NUMBER OF ANNUAL MEMBERS WILL BE KEY TO FUTURE GROWTH. RATHER THAN CREATING A MARKETING CAMPAIGN THAT TARGETS ALL-NEW CUSTOMERS, MORENO BELIEVES THERE IS A VERY GOOD CHANCE TO CONVERT CASUAL RIDERS INTO MEMBERS. SHE NOTES THAT CASUAL RIDERS ARE ALREADY AWARE OF THE CYCLISTIC PROGRAM AND HAVE CHOSEN CYCLISTIC FOR THEIR MOBILITY NEEDS.



2.OBJECTIVE:

2.1PROBLEM : DESIGN MARKETING STRATEGIES AIMED AT CONVERTING CASUAL MEMBERS TO CYCLISTIC MEMBERS

2.2BUSINESS OBJECTIVE :  TO UNDERSTAND HOW CASUAL MEMBERS AND CYCLISTIC MEMBERS USE CYCLISTIC BIKES DIFFERENTLY BY ANALYZING THE CYCLISTIC TRIP DATA FOR THE YEAR 2022.



3.DATA INTEGRITY:

3.1 DATA SOURCE : 12 MONTHS OF CYCLISTIC TRIP DATA BY MOTIVATE INTERNATIONAL INC. 

    THERE ARE 12 DATA SETS FOR THE RESPECTIVE 12 MONTHS.

3.2 THE DATA FOLLOWS A ROCCC APPROACH.

RELIABILITY : THE DATA FOR THE 12 MONTHS OF THE YEAR 2022 WAS MADE AVAILABLE BY MOTIVATE INTERNATIONAL INC. UNDER A PROPER LICENSE.

ORIGINAL : THE DATA IS ORIGINAL AS IT IS FROM A VERIFIED SOURCE MOTIVATE INTERNATIONAL INC.

COMPRHENSIVE : THE DATA IS COMPREHENSIVE IN TERMS OF BEING MEANINGFUL, EASY TO UNDERSTAND AND READABLE.

CURRENT : THE GIVEN DATA IS FOR THE PREVIOUS YEAR (2022) , SO IT IS VERY RECENT.

CITED : UNKNOWN      



4.DATA PREPROCESSING:

4.1 DATA CLEANING :

    AFTER HAVING EXPLORED THE 12 DATASETS THERE WERE SOME DATA QUALITY ISSUES THAT HAD TO BE ADDRESED.

    SOME OF THE DATA QUALITY ISSUES WERE : 

    INCOMPLETE DATA : THERE WERE A LOT OF BLANKS IN A FEW FIELDS.

    INCORRECT DATATYPE : A LOT OF DATA FIELDS WERE NOT PRESENT IN THE RIGHT DATA TYPE.

    INCORRECT VALUES : A FEW DATA FIELDS HAD NEGATIVE VALUES AND SOME ABSURD VALUES THAT WERE QUITE IRRELEVANT.

    SO THESE ISSUES WERE SOLVED BY DELETING THE ROWS IN THE RESPECTIVE FIELDS THAT HAD BLANK VALUES AND VALUES WHICH WERE IRRELEVANT. MANY DATA FIELDS WERE CONVERTED       TO THE APPROPRIATE DATA TYPE .

4.2 DATA FORMATTING AND ADJUSTING :

    THE DATE AND TIME COLUMN WAS SPLIT INTO 2 COLUMNS DATE AND TIME AND THE TIME COLUMN WAS FURTHER SPLIT INTO HOURS MINUTES AND SECONDS.

    SORTING :

    THE DATASET WAS SORTED BY DATE COLUMN IN THE OLDEST TO THE NEWEST ORDER.
    
    

5.DATA PROCESSING:

DATA PROCESSING INVOLVES THE CONVERSION OF RAW DATA INTO USEFUL INFORMATION.

BY KEEPING THE BUSINESS TASK IN MIND IT WAS DECIDED TO IDENTIFY COLUMNS THAT CAN BE SIMPLIFIED AS WELL AS COLUMNS THAT CAN BE USED AS OPERANDS IN A FORMULAE IN ORDER TO CREATE NEW CALCULATED COLUMNS.

TWO CALCULATED COLUMNS NAMELY RIDE DURATION AND RIDE DISTANCE WERE CREATED BY APPLYING THE FOLLOWING FORMULAE :

RIDE DURATION ( IN MINS) : (((START_HOURS*3600) + (START_MINS*60) + START_SECONDS) – ((END_HOURS*3600) + (END_MINS*60) + END_SECONDS)) / 60. 

RIDE DISTANCE (IN KMS) :                                                                                                                                                                         ACOS( SIN(LAT1*PI()/180)*SIN(LAT2*PI()/180) + COS(LAT1*PI()/180)*COS(LAT2*PI()/180)*COS(LON2*PI()/180-LON1*PI()/180) ) * 6371. (LATITUDE AND LONGITUDE SHOULD BE IN DEGREES.)

BY USING PIVOT TABLES IT WAS DECIDED TO SUMMARIZE THE WHOLE DATASET BASED ON CERTAIN COLUMNS ACCORDING TO THE BUSINESS TASK.

THE BASIC IDEA WAS TO COUNT THE NUMBER OF RIDES BY CASUAL AND ANNUAL MEMBERS AS WELL AS  NUMBER OF RIDES BY EACH BIKE TYPE USED BY EACH MEMBER.

THE DATE COLUMN WAS USED TO COUNT THE NUMBER OF RIDES ON EACH DAY AND THIS WAS FURTHER SIMPLIFIED BY CALCULATING THE AVERAGE NUMBER OF RIDES ON WEEKDAYS AND WEEKENDS FOR EACH MONTH. 

THE TIME COLUMN WAS USED TO COUNT THE NUMBER OF RIDES ON EACH HOUR OF THE DAY AND THIS WAS FURTHER SIMPLIFIED INTO PHASES OF THE DAY SUCH AS MORNING, NOON, EVENING AND NIGHT IN WHICH THE AVERAGE NUMBER OF RIDES WERE CALCULATED BASED ON THE FOLLOWING ASSUMPTIONS :  

MORNING HOURS : 6:00 A.M. – 12:00 P.M.

NOON HOURS : 12:00 P.M. – 5:00 P.M. 

EVENING HOURS : 5:00 P.M. – 8:00 P.M.

NIGHT HOURS : 8:00 P.M. – 6:00 A.M. 

THUS THE DATA FIELDS IN THE DATA SETS WERE PROCESSED ACCORDING TO THE REQUIREMENTS OF THE BUSINESS TASK. 



6.MODEL DEVELOPMENT:

AFTER HAVING PROCESSED THE DATA IT WAS DECIDED TO CREATE A MODEL TO ACCOMMODATE THE NECCESARY INFORMATION FROM THE PROCESSED DATA INTO ROWS AND COLUMNS.
THE MODEL CONSISTED OF 14 COLUMNS AND 118 ROWS. 

THE COLUMN NAMES WERE : 1.S.NO. , 2.MEMBER TYPE, 3.BIKE TYPE, 4.MONTH AND YEAR , 5.MONTH, 6.WEEKDAYS AVERAGE, 7.WEEKENDS AVERAGE, 8.MORNING, 9.NOON, 10.EVENING, 11.NIGHT 12. RIDE DURATION, 13.RIDE DISTANCE, 14.TOTAL NUMBER OF RIDES.

THUS WHATEVER FIELDS THAT WERE PROCESSED WERE ADDED INTO THE MODEL AS COLUMNS SUCH AS WEEKDAYS,WEEKENDS,MORNING,NOON ETC. ON THE BASIS OF THE MEMBER TYPE,BIKE TYPE,AND MONTH AND YEAR.

THUS THE MODEL WAS DEVELOPED FOR FURTHER ANALYSIS.



7.INTERPRETATION:

THE DEVELOPED MODEL WAS EXPLORED IN WHICH A FEW INTERPRETATIONS WERE MADE ON THE BASIS OF WHICH IT WAS DECIDED TO ILLUSTRATE THE DIFFERENCES BETWEEN CASUAL AND CYCLISTIC MEMBERS IN TERMS OF :

TOTAL NUMBER OF RIDES FOR THE YEAR 2022.

THE NUMBER OF RIDES BY EACH BIKE TYPE FOR EACH MONTH IN 2022.

THE AVERAGE NUMBER OF RIDES DURING WEEKDAYS AND WEEKENDS IN 2022.

THE AVERAGE NUMBER OF RIDES DURING EACH PHASE OF THE DAY IN 2022.

THE AVERAGE RIDE DURATION FOR THE YEAR 2022.

![1](https://user-images.githubusercontent.com/128831771/227699124-bf03db1d-ca01-4734-8ebf-e78c144af8dd.png)

![2](https://user-images.githubusercontent.com/128831771/227699141-0bd7a3a8-13b5-4494-b9fc-b3e8f8773edc.png)

![3](https://user-images.githubusercontent.com/128831771/227699158-9d500212-f9de-42fb-bb04-f96752d692df.png)

![4](https://user-images.githubusercontent.com/128831771/227699168-36a25d4c-7fc4-44e5-b892-40294bbc1a5a.png)

![5](https://user-images.githubusercontent.com/128831771/227699177-9f6956c4-e5b0-4a03-bae0-7dabdfbf0256.png)

![Cyclistic Dashboard](https://user-images.githubusercontent.com/128831771/227696969-fba0f623-a5b5-42e5-94b6-83aa04eb88f7.png)



8.CONCLUSIONS:

THUS FROM THE ABOVE DIFFERENCES WE CAN CONCLUDE THAT :

ANNUAL MEMBERS PREDOMINANTLY USE BIKES FOR WORK RELATED PURPOSES LIKE GOING TO OFFICE AND FOR OTHER PROFESSIONAL PURPOSES.

CASUAL MEMBERS PREDOMINANTLY USE BIKES FOR RELAXING BY GOING TO BEACHES, PARKS ETC. WHICH IS NON PROFESSIONAL.

THE ABOVE 2 CONCLUSIONS ARE SUPPORTED BY THE BELOW FACTS:

CASUAL MEMBERS PREFER WEEKENDS FOR THEIR RIDES WHEREAS ANNUAL MEMBERS PREFER WEEKDAYS FOR THEIR RIDES. 

THE RIDE DURATION FOR THE CASUAL MEMBERS IS HIGH WHEN COMPARED TO ANNUAL MEMBERS.

THE FACT THAT ANNUAL MEMBERS PREDOMINANTLY USE THEIR BIKES DURING MORNING THAN COMPARED TO CASUAL MEMBERS WHO PREDOMINANTLY USE THEIR BIKES DURING AFTERNOON AND EVENING.



9.RECOMMENDATIONS:

CYCLISTIC CAN FOCUS ON PROVIDING ANY OFFERS OR DISCOUNTS FOR RIDES DURING WEEKENDS IN THEIR ANNUAL MEMBERSHIP PLAN.

IN THE MONTHS OF OCTOBER, NOVEMBER AND DECEMBER SOME OFFERS CAN BE PROVIDED RELATED TO THE USAGE OF ELECTRIC BIKES AS ELECTRIC BIKES ARE PREDOMINANTLY USED IN THESE MONTHS BY CASUAL RIDERS.

OFFERS CAN ALSO BE PROVIDED IN THE MONTH OF JULY IN WHICH THE NUMBER OF RIDES BY CASUAL MEMBERS ARE THE MAXIMUM BASED ON WHICH THEY CAN ALSO PLAN TO CONDUCT CAMPAIGNS AND PROMOTIONAL ACTIVITIES IN THE MONTH OF MAY SO THAT CHANCES OF MANY CASUAL MEMBERS TAKING MEMBERSHIPS FROM JULY ARE HIGH.

BASED ON THE ABOVE RECOMMENDATIONS CYCLISTIC CAN TWEAK THEIR ANNUAL MEMBERSHIP PLAN TO ATTRACT MORE CASUAL MEMBERS.




       


      


