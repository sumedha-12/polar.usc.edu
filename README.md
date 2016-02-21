#D3 Visualizations

####Main HTML Files
Currently, we have a D3 tab on our home page that leads to a separate HTML page -- this is the page that we will be posting examples on for now. The HTML file for this page is located in data/HTML/D3.html. 

We are not planning to use this format in the future as we are going to integrate a couple of these examples within the home page, particularly under the 'Features' section. Nevertheless, linking to separate HTML pages for now will be a good start.

####Where To Place Files
Files such as json, txt, and csv files belong in the data directory. Javascript files belong in the js/D3 directory. HTML files (which we will be eliminating later) should be placed in data/HTML directory.

When adding a new team's HTML file to the page, navigate to data/HTML/D3.html. Scroll down to the D3 section and simply add another link.

####How To Start Finding Projects
We will be mainly looking at D3, so focus on the HW3 project submissions found in the Dropbox link that Dr. Mattmann provided us.

Every team has a different structure for their project. To add to this confusion, half of the teams' submissions are incomplete and cannot be used. Additionally, some projects, such as Mohammad's (Team 40), request data from Solr to generate data for D3 to consume and cannot be used (as of yet). However, there are still quite a few projects that may be useful for us at this time -- we just need to find them. Below I elaborate on how to extract some D3 examples from a team. 

####Example: Extracting D3 stuff from Team 29
-------------------
I took three widgets from Team 29's project. One of them Lorraine had demonstrated on the main Wicket page, worldmap-template.html. The other two that I extracted were timeSeriesChart.html and widget3.html. I will just focus on timeSeriesChart.html. Explicit steps can be found at the bottom of this example. The following information is a description of the overall process.

#####Javascript/CSS File Dependencies
A majority of these projects will have Javascript and CSS dependencies that we need to extract in order to run them. For example, in timeSeriesChart.html, you will see a ton of scripts and links that this HTML file is dependent on. However, a majority of these links are actually not needed and can be removed. If you compare this to the file to the file I altered, which can be found in the Github page's data/HTML/Team29SiteC.html, you can see links that I removed. You will have to experiment by removing links and testing to see if the HTML file still works.

Additionally, a lot of these files already exist in our Github page repo. Files such as bootstrap.min.js, jquery-1.7.1.min.js, etc. are located in the js directory and can be linked accordingly. However, a couple of files may have been created by the team, such as timeSeriesChart.js and clickPanel.js, and need to be transferred over to our repo. As stated above, these javascript files can be placed in the js/D3 directory. 

#####Javascript Function Extraction
After all the js and css dependencies are sorted out, we can move on to separating the javascript functions from the HTML files. Many teams combine javascript functions with their HTML files and we want to split them up into separate files. However, some teams may have already done this so this step can be stepped. In this example, the team combined their HTML and javascript functions into a single file. As you can see in timeSeriesChart.html near the bottom of the file, there is a function drawTimeSeries() javascript function. I simply just cut and paste it into another file and named it Team29c.js. It can be found in js/D3/Team29c.js if you want to reference it. 

#####Data dependencies
The D3 example should now be displaying. However, it needs data to plot the necessary points. If you go back and look at timeSeriesChart.html and scroll down to the "facet-view-simple" class divison, you can see it calls the function drawTimeSeries which we extracted out above. It passes in data files as an argument so we need to take these files and place them in the appropriate folder. A majority of teams have offline data stored in the form of csv, json, or txt. For the main GitHub repo, these files would go in the data directory.

######Explicit Steps
1. Create a folder on your Desktop. This will be our test folder and I will reference it as TEST.
2. Navigate to Team 29's HW3 Submission folder. 
3. Follow this path: TOTAL_PRERNAN_CSCI572_HW_DATAVIS/src
4. Extract hw3.zip and open the hw3 folder
5. Copy timeSeriesChart.html over to the TEST folder. Open the copied version of the file.
6. Remove unnecessary links/scripts in timeSeriesChart.html
7. For this example, you can simply put all the css and js dependencies in the TEST folder so that linking it will be easier. For example, I can just place bootstrap.min.js in TEST, and then in timeSeriesChart.html I can change the src to src="bootstramp.min.js". However, when placing it in the main Github page, put all necessary js and css files into the appropriate folders. You will have to change the src (for scripts) or href (for links) links in timeSeriesChart.html so that they navigate to the correct folder. 
8. Remove any javascript functions, typically found near the bottom of the HTML file, and place it in a separate file. Place this file in the js/D3 directory. Once again in this test example, put the js file in the TEST folder. 
9. Locate any file dependencies within the javascript function file. In this example, you can see that it needs wheatNotes.csv. Take wheatNotes.csv and place it in the TEST folder and change the link within the js file.
10. Locate any data dependencies within the main HTML page and place them in the appropriate folder. In this example, we will need warming_times.csv, oceancirculation_times.csv, and co2_times.csv. Take these files and place them in the TEST folder.
11. Open timeSeriesChart.html with Firefox if you are doing it locally. Browsers such as Chrome and Safari do not allow loading files through a local directory unless you change around some settings. If you upload these files to a local server or the GitHub IO website, you can use Chrome or Safari.
12. The D3 example should now be displaying.
 




 




