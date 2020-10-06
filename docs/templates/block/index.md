# Block Templates

### Hero Image
![HeroImage](/images/Hero_Image.png)
![HeroImageCMS](/images/HeroImage_CMS.png)
This block relates to your HERO content. You should specifiy the following information, as needed:
- **Author:** The name of the person or persons who wrote this article. This will show up on the card's hover on the landing grid
- **Card Image:** This is the image that shows up on the landing grid.
- **Date:** This is the date the article was published. You will need to list two dates here. The date that appears on the article should be in this format: 1 January 2020. The date that will not show up on the card but helps sort the cards should be listed as [YYYY-MM-DD] (see image)
- **Title:** This is the article title
- **Image:** This is the image that will show up on the header.
- **Image Caption:** This is the caption under the photo.

### Hero Text
![HeroText](/images/HeroText.png)
![HeroTextCMS](/images/HeroText_CMS.png)
This is the block you choose if you do not wish to have a hero image. Typically this block is chosen if you want the user to quickly get to a visualization. For the card, which will only show up on the landing grid, you will just need to take a screenshot of the visualization and add it to the card image.

### Body
![Body_InsightSidebar](/images/Body_InsightSidebar.png)
![Body_CMS](/images/Body_CMS.png)
This block contains one body text field. Please look up Markdown syntax for styling. 

### Insight Sidebar
![Body_InsightSideBar](/images/Body_InsightSidebar.png)
![InsightSidebar_CMS](/images/InsightSidebar_CMS.png)
This block contains information for sharing the page and insights portal as well as a tag cloud. You do not have to do anything other than add this block to a page to make it populate the cloud and sharing information.

### Body + Stat
![BodyStatInsight](/images/BodyStat_Insight.png)
![BodyStat_CMS](/images/BodyStat_CMS.png)
This block includes editorial body text as well as a stat. The stat should include a big number that you'd like to point out to users. The body text should follow the normal markdown styling.

### Body + Insight
![BodyStatInsight](/images/BodyStat_Insight.png)
![BodyInsight_CMS](/images/BodyInsight_CMS.png)
This block includes editorial body text as well as a connection to an insight. You can connect a relevent insight to the body text by selecting the insight in the connections drop down.

### Body + external link
![BodyExternal_CMS](/images/bodyexternal_CMS.png)
This block includes editorial body text as well as a connection to an external link. You can connect a relevent link to the body text by selecting the insight in the connections drop down.

### Pull Quote
![pullquote](/images/pullquote.png)
This block allows you to pull out a quote from an article and credit it to its author.

### Table
![Table](/images/Table.png)
![Table_CMS](/images/Table_CMS.png)
![Table_CMS_Preview](/images/Table_CMS_Prevew.png)
This block allows you to have a table in an insight. The table is a markdown element and should follow normal markdown styling.

### Image two-collumn
![image_two](/images/image_two.png)
This block is for two collumn-image.

### Image inline
![image_inline](/images/image_inline.png)
This block is for smaller image.

### Image Full-Width
![ImageFull](/images/ImageFull.png)
![ImageFull_CMS](/images/ImageFull_CMS.png)
This block is for images that take up the entire screen.

## Observable

### Single View
![SingleView](/images/SingleView.png)
![SingleView_CMS](/images/Singleview_CMS.png)
The Single view block consists of a single Observable Element. An Observable Element has 4 input fields:
- **ObservableHQ User:** observable username, or d if it’s an unpublished notebook (with link sharing. If it’s ever a question, this value is taken from the URL: https://www.observable.com/<username>/…..
- **ObservableHQ Notebook name:** name or id of chosen notebook, taken from last part of the URL: https://www.observable.com/d/<notebook id>
- **ObservableHQ Cells:** Comma-separated list of key:value pairs that link frontend visual components to specific cells (or variables) from the notebook. 
The pattern is: <frontend visual component>: <notebook cell/variable>
The Trase Yearbook frontend is expecting up to 3 visual components on each visualization: chart, chartTitleCard, and chartLegend. The names are case-sensitive. 
You can choose any cell or variable from the notebook to link to each of these components. Note that cells must be named cells: (chart = {....} ) 
- **ObservableHQ Params:** [optional] This field accepts a comma-separated list of key:value pairs that represent notebook variables that you want to assign new values to. 
For instance, by default, the reference notebook has the variable context = ‘BRAZIL - SOY’
You can tell the frontend to override that variable with a new value when rendering by entering  context: ‘ARGENTINA - SOY’ in this field

### Slideshow
![Slideshow](/images/Slideshow.png)
![Slideshow_CMS](/images/Slideshow_CMS.png)
![Slideshow_CMS_expanded](/images/Slideshow_CMS_expanded.png)
The [data] Slideshow block is very similar to the [data] Single view block, only you can add 2 or more Observable Elements. 
You can add more Observable Elements by clicking the ‘+’ button under this block. Each Observable element can be expanded to see the same input fields (with the same behavior) as with the [data] Single view block. 
You can put different notebooks in each element, or the same notebook with different variable overrides. 
When you click Save, the front end will render each of these Observable Elements into a slideshow carousel.

### Multistate
![Multistate](/images/Multistate.png)
![Multistate_CMS](/images/multistate_cms.png)
The [data] Multistate is designed for observable visualizations that have multiple different states. Let’s use this one for reference: https://observablehq.com/d/dee964b806395dd9. When the frontend renders the notebook, it will also include an interactive element for toggling among the notebook states. This adds a couple of additional requirements to the notebook and the CMS specifications. 

**On the notebook:**
- The notebook should have a named cell with an array representing the different states. The state names can take on any values you wish. 

![Multistate_1](/images/Multistate_1.png)

- For purposes of testing the different states in the notebook itself, it may be helpful to include a selection input, but this will not be passed along to the front end:

![Multistate_2](/images/Multistate_2.png)

- The main chart svg should follow this general update pattern, and respond to changes in the state 

![Multistate_3](/images/Multistate_3.png)

- Finally, the notebook must also have a named cell in which the update function is called once. Without this, the chart won’t render. 

![Multistate_4](/images/Multistate_4.png)

**In Schema CMS:**

![Multistate_5](/images/Multistate_5.png)

The [data] Multistate block consists of a single Multistate Observable Element, which has the same 4 input fields as the Observable Element before, but with slightly different requirements on the ObservableHQ Cells field:
- ObservableHQ User: observable username, or d if it’s an unpublished notebook (with link sharing. If it’s ever a question, this value is taken from the URL: https://www.observable.com/<username>/…..
- ObservableHQ Notebook name: name or id of chosen notebook, taken from last part of the URL: https://www.observable.com/d/<notebook id>
- ObservableHQ Cells: Comma-separated list of key:value pairs that link frontend visual components to specific cells (or variables) from the notebook. 
- The pattern is: <frontend visual component>: <notebook cell/variable>
The Trase Yearbook frontend is expecting up to 3 visual components on each visualization: chart, chartTitleCard, and chartLegend. The names are case-sensitive.
You can choose any cell or variable from the notebook to link to each of these components. In this case, only named cells ( chart = {....} ) are allowed
In addition to the visual component, you need to tell the CMS which notebook cells correspond to the states and initDraw cells
 
 ![Multistate_6](/images/Multistate_6.png)
