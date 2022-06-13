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


![divider](https://user-images.githubusercontent.com/101108540/173300280-f7c85410-252e-4b55-871b-054622b7fa02.jpg)


            <ExpandableListView
             android:id="@+id/simpleExpandableListView"
             android:layout_width="match_parent"
             android:layout_height="match_parent"
             android:divider="#f00"   <!-- red color divider -->
             android:dividerHeight="1dp" /> <!-- red color divider with 1dp height between the groups items of expandableListView -->
        


3. dividerHeight: This specify the height of the divider between group list items. This could be in dp ( density pixel ), sp(scale independent pixel) or px ( pixel ).
      
      
      
            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:dividerHeight="1dp" /> <!-- red color divider with 1dp height between the groups items -->





4. listSelector: This property is used to set the selector of the expandable list View.
   You can also define your own custom color or an image as a list selector as per your design.
   
   
   
  ![Screenshot 2022-06-13 131259](https://user-images.githubusercontent.com/101108540/173304368-a99e993e-d36f-43a0-9b23-49cc576514f3.jpg)
 
   
   

            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="1dp"
              android:listSelector="#0f0" /> <!-- green color for the list selector item -->
        
        
        
        
        
5. childDivider: This is a drawable or color to draw between different child list items of a expandable list view.


![ExpandableListView](https://user-images.githubusercontent.com/101108540/173306114-900e27e8-539f-4035-ba6f-46d2210c6f89.jpg)





            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="1dp"
              android:childDivider="#0f0" /> <!-- green color divider between the child items of expandable list view -->
        
        
        
        

6. padding: padding attribute is used to set the padding from left, right, top or bottom.



  • paddingRight: set the padding from the right side of the expandable list view.

  • paddingLeft: set the padding from the left side of the Progress bar.
 
  • paddingTop: set the padding from the top side of the expandable list view.

  • paddingBottom: set the padding from the bottom side of the expandable list view.

  • Padding: set the padding from the all side’s of the expandable list view.




            <ExpandableListView
              android:id="@+id/simpleExpandableListView"
              android:layout_width="match_parent"
              android:layout_height="fill_parent"
              android:divider="#f00"
              android:dividerHeight="2dp"
              android:childDivider="#0f0"
              android:padding="50dp" /> <!-- 50 dp padding from all the sides of a expandable list view -->
              
              
# In Android for supplying data in an ExpandableListView following adapters are used.

            1. ExpandableListAdapter
            2. BaseExpandableListAdapter
            3. SimpleExpandableListAdapter
 


# Project Source Code :

Step 1: Create a new project

Step 2: Open res -> layout -> activity_main.xml (or) main.xml and add following code.


            <?xml version="1.0" encoding="UTF-8"?>
            <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
               android:layout_width="match_parent"
               android:layout_height="match_parent"
               android:orientation="vertical">

            <ExpandableListView
                android:id="@+id/simpleExpandableListView"
                android:layout_width="match_parent"
                android:layout_height="fill_parent"
                android:divider="#f00"
                android:dividerHeight="1dp" />

             </RelativeLayout>
             
             
Step 3: Create a new XML file for group items Open res -> layout -> group_items.xml and add following code:     


            <?xml version="1.0" encoding="utf-8"?>
            <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
              android:layout_width="fill_parent"
              android:layout_height="55dip"
              android:orientation="vertical" >

            <TextView
               android:id="@+id/heading"
               android:layout_width="wrap_content"
               android:layout_height="wrap_content"
               android:paddingLeft="35sp"
               android:gravity="center"
               android:textAppearance="?android:attr/textAppearanceLarge"
               android:textStyle="bold" />

            </LinearLayout>
            
            
            
Step 4: Create a new xml file for child items Open res -> layout -> child_items.xml and add following code:         



            <?xml version="1.0" encoding="utf-8"?>
            <RelativeLayout android:layout_width="match_parent" android:layout_height="match_parent"
               android:orientation="vertical" xmlns:android="http://schemas.android.com/apk/res/android">

            <TextView
               android:id="@+id/childItem"
               android:layout_width="wrap_content"
               android:layout_height="wrap_content"
               android:layout_alignParentTop="true"
               android:layout_marginLeft="5dp"
               android:textAppearance="?android:attr/textAppearanceMedium" />

            </RelativeLayout

Step 5: Open src -> package -> MainActivity.Java






        import android.os.Bundle;
        import android.view.View;
        import android.widget.ExpandableListView;
        import android.widget.SimpleExpandableListAdapter;
        import android.widget.Toast;

        import androidx.appcompat.app.AppCompatActivity;

        import java.util.ArrayList;
        import java.util.HashMap;
        import java.util.List;
        import java.util.Map;

        public class MainActivity extends AppCompatActivity {

        private static final String NAME = "NAME";

        private SimpleExpandableListAdapter mAdapter;
        ExpandableListView simpleExpandableListView;
        // string arrays for group and child items
        private String groupItems[] = {"Animals", "Birds"};
        private String[][] childItems = {{"Dog", "Cat", "Tiger"}, {"Crow", "Sparrow"}};

        @Override
        public void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            
        //  initiate the expandable list view
        simpleExpandableListView = (ExpandableListView) findViewById(R.id.simpleExpandableListView);
        
        // create lists for group and child items
        List<Map<String, String>> groupData = new ArrayList<Map<String, String>>();
        List<List<Map<String, String>>> childData = new ArrayList<List<Map<String, String>>>();
        // add data in group and child list
        for (int i = 0; i < groupItems.length; i++) {
            Map<String, String> curGroupMap = new HashMap<String, String>();
            groupData.add(curGroupMap);
            curGroupMap.put(NAME, groupItems[i]);

            List<Map<String, String>> children = new ArrayList<Map<String, String>>();
            for (int j = 0; j < childItems[i].length; j++) {
                Map<String, String> curChildMap = new HashMap<String, String>();
                children.add(curChildMap);
                curChildMap.put(NAME, childItems[i][j]);
            }
            childData.add(children);
        }
        // define arrays for displaying data in Expandable list view
        String groupFrom[] = {NAME};
        int groupTo[] = {R.id.heading};
        String childFrom[] = {NAME};
        int childTo[] = {R.id.childItem};


        // Set up the adapter
        mAdapter = new SimpleExpandableListAdapter(this, groupData,
                R.layout.group_items,
                groupFrom, groupTo,
                childData, R.layout.child_items,
                childFrom, childTo);
        simpleExpandableListView.setAdapter(mAdapter);

        // perform set on group click listener event
        simpleExpandableListView.setOnGroupClickListener(new ExpandableListView.OnGroupClickListener() {
            @Override
            public boolean onGroupClick(ExpandableListView parent, View v, int groupPosition, long id) {

                // display a toast with group name whenever a user clicks on a group item
                Toast.makeText(getApplicationContext(), "Group Name Is :" + groupItems[groupPosition], Toast.LENGTH_LONG).show();

                return false;
            }
        });
        // perform set on child click listener event
        simpleExpandableListView.setOnChildClickListener(new ExpandableListView.OnChildClickListener() {
          @Override
          public boolean onChildClick(ExpandableListView parent, View v, int groupPosition, int childPosition, long id) {

          // display a toast with child name whenever a user clicks on a child item
          Toast.makeText(getApplicationContext(),"Child Name Is :" +childItems[groupPosition][childPosition],Toast.LENGTH_LONG).show();
          return false;
          }
        });
       }
      }
      
      
      
      
      
Output :



https://user-images.githubusercontent.com/101108540/173310098-a5d0a781-4753-40b1-a441-048f06011555.mp4




