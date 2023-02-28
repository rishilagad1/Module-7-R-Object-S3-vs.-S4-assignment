# Module-7-R-Object-S3-vs.-S4-assignment
#Download  datasets package or create your own set. 
> # Downloading and importing the dataset from kaggle.
> #https://www.kaggle.com/datasets/jneelima/nobel-prize-winner-1901-to-2020?resource=download
> read <- ("nobel_prize_awarded_country_details_1901_2020_v3.csv")
> nobel_prize_awarded_country_details_1901_2020_v3 <- read.csv("C:/Users/rushi/Desktop/nobel_prize_awarded_country_details_1901_2020_v3.csv")
>   View(nobel_prize_awarded_country_details_1901_2020_v3)
> # Determine if generic functions can be used on the data .
> summary(nobel_prize_awarded_country_details_1901_2020_v3)
     Name                Year        Country           Countries        
 Length:1154        Min.   :1901   Length:1154        Length:1154       
 Class :character   1st Qu.:1950   Class :character   Class :character  
 Mode  :character   Median :1978   Mode  :character   Mode  :character  
                    Mean   :1973                                        
                    3rd Qu.:2001                                        
                    Max.   :2020                                        
   Category            Gender            Details         
 Length:1154        Length:1154        Length:1154       
 Class :character   Class :character   Class :character  
 Mode  :character   Mode  :character   Mode  :character  
                                                         
                                                         
                                                         
 Description       
 Length:1154       
 Class :character  
 Mode  :character  
                   
                   
                   
> head(nobel_prize_awarded_country_details_1901_2020_v3)
               Name Year       Country               Countries  Category
1   14th Dalai Lama 1989         Tibet                   Tibet     Peace
2 A. Michael Spence 2001 United States           United States Economics
3         Aage Bohr 1975       Denmark                 Denmark   Physics
4 Aaron Ciechanover 2004        Israel                  Israel Chemistry
5        Aaron Klug 1982     Lithuania               Lithuania Chemistry
6        Aaron Klug 1982  South Africa Lithuania, South Africa Chemistry
  Gender        Details Description
1    Man  born in Tibet            
2    Man                           
3    Man                           
4    Man                           
5    Man                           
6    Man                           
> class(nobel_prize_awarded_country_details_1901_2020_v3)
[1] "data.frame"
> # Explore if your dataset is S3 or S4.
> isS4(nobel_prize_awarded_country_details_1901_2020_v3)
[1] FALSE
> # How do you tell what OO system (S3 vs. S4) an object is associated with?
> # You can use the isS4() function to find out whether or not it's a S4 system. 
> # If it's FALSE, then that means it is a S3 sysyem. 
> # How do you determine the base type (like integer or list) of an object?
> # You can use the class() function and it will tell you if it's a data frame,
> # list, matrix, etc. 
> 
> #What is a generic function? 
> # A generic function is one that is used to find the class 
      of the function's arguments and get the right method.
> 
> # What are the main differences between S3 and S4?
> # S3 is informal, but interactive in it's capabilities. Meanwhile, 
> # S4 is much more formal, but can can be less interactive. The S4 system 
> # newer and more structured, while S3 is older and simpler. 
> # Example of S3 dataset
> s3 <- list(doctor = "Dr. Ram", patient = "Johnathan seagle", age = 23, 
+            weight.kg = 68.2, height.cm = 182.88)
> s3 # view the results
$doctor
[1] "Dr. Ram"

$patient
[1] "Johnathan seagle"

$age
[1] 23

$weight.kg
[1] 68.2

$height.cm
[1] 182.88

> # Example of S4 dataset
> # creating the class
> setClass("Patient", representation(physician = "character", 
+                                   name = "character", age = "numeric", 
+                                   weight.kg = "numeric", height.cm = "numeric"))
> 
> # creating the object
> 
> s4 <- new("Patient", physician = "Dr.robert", 
+           name = "jasica Garcia", age = 58, 
+           weight.kg = 64.3, height.cm = 155.8)
> s4 # view the results
An object of class "Patient"
Slot "physician":
[1] "Dr.robert"

Slot "name":
[1] "jasica Garcia"

Slot "age":
[1] 58

Slot "weight.kg":
[1] 64.3

Slot "height.cm":
[1] 155.8
 # Thank You. ...
