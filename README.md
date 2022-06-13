# ExpandableListView
In Android, ExpandableListView is a View that shows items in a vertically scrolling two level list.

Syntax:

      <ExpandableListView      
        android:id="@+id/simpleExpandableListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" 
      />


![ExpListView](https://user-images.githubusercontent.com/101108540/173298249-622a9c4b-5702-43b7-86dc-b2a33ab8f9a0.jpg)


# Attributes of ExpandableListView In Android :

1. id: id is an attribute used to uniquely identify a Expandable List View.




            <ExpandableListView  
             android:id="@+id/simpleExpandableListView" <!-- id of an attribute used to uniquely identify a expandable list view -->
             android:layout_width="match_parent"
             android:layout_height="match_parent"/> 



2. divider: This is a drawable or color to draw between different group list items.



            <ExpandableListView
             android:id="@+id/simpleExpandableListView"
             android:layout_width="match_parent"
             android:layout_height="match_parent"
             android:divider="#f00"   <!-- red color divider -->
             android:dividerHeight="1dp" /> <!-- red color divider with 1dp height between the groups items of expandable list view -->
        
        
        
        
![divider](https://user-images.githubusercontent.com/101108540/173300280-f7c85410-252e-4b55-871b-054622b7fa02.jpg)
        
        
        


3. dividerHeight: This specify the height of the divider between group list items. This could be in dp ( density pixel ), sp(scale independent pixel) or px ( pixel ).
      
      
      
            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:dividerHeight="1dp" /> <!-- red color divider with 1dp height between the groups items -->





4. listSelector: This property is used to set the selector of the expandable list View.
   You can also define your own custom color or an image as a list selector as per your design.
   
   
   
   

            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="1dp"
              android:listSelector="#0f0" /> <!-- green color for the list selector item -->
        
        
        
        
        
5. childDivider: This is a drawable or color to draw between different child list items of a expandable list view.





            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="1dp"
              android:childDivider="#0f0" /> <!-- green color divider between the child items of expandable list view -->
        
        
        
        

6. padding: padding attribute is used to set the padding from left, right, top or bottom.



paddingRight: set the padding from the right side of the expandable list view.
paddingLeft: set the padding from the left side of the Progress bar.
paddingTop: set the padding from the top side of the expandable list view.
paddingBottom: set the padding from the bottom side of the expandable list view.
Padding: set the padding from the all side’s of the expandable list view.




            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="2dp"
              android:childDivider="#0f0"
              android:padding="50dp" /> <!-- 50 dp padding from all the sides of a expandable list view -->



