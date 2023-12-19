Create debugging_pipeline V.2
I did this project in 2 phases.
Phase 1: Do what Datacamp required, e.g. find mistakes in the data pipeline. I used proposed "Run->Isolate->Rectify" strategy.
1.1 I checked data shape(the amount of columns after loading had to correspond the amount of cloumns in the original .csv file).
1.2 Next step was to check data integrity, using statistical concepts, like normal distribution(mean and std neded for that matter). I added one more column, "Tax_calculated", so to make sure it is there and correct(original "Tax" column contained "0" values, and because of that there were mistakes in "Total" column.)
1.3. I was expected to add one more condition, and according to the Datacamp's instructions, if at least one of conditions hold, the data was ok.
1.4. I wasn't satisfied with this, and changed the code. In my version the code is modified, so that only if all 3 conditions met, the data is considered not to be corrupted.
Phase 2: Take this project to the real world, so that .csv file worked outside Datacamp's IDE, and the code code was interactive.
2.1 I located .csv file on my Google Drive. The initial idea was to create Postgre database , hosted on AWS's Amason RDS(and connected to EC2 instance). Postgre was installed on my MacAir 2017, x64(086) system(Monterey), database(with proxy ofc) was created and connected to EC2, using Free Tier plan. But due to problems with bash or smth else, Postgre's pgadmin4 didn't connect to both AWS and even localhost.
2.2 As this project revolves around debugging itself, rather that pipeline building, and there was just 1 .csv, I decided to go for Google Drive. In order to load data from .csv, I had to edit obtained csv-file's link. I had to add special  uc?id=...&export=download ending, as standard link wasn't loaded properly thtu .read_csv method.

Now the code works for any user, and it's interactive, so one can see the table, created from csv-file, and even conduct further cleaning, analysis and visualisations(please check google colab jupyter notebook https://colab.research.google.com/drive/1LEtSdkzMkI2Pr0vE9mBBF8lOoLtasJmx?usp=sharing).
