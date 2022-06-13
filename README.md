# ExpandableListView
In Android, ExpandableListView is a View that shows items in a vertically scrolling two level list.

Syntax:

      <ExpandableListView
        android:id="@+id/simpleExpandableListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" 
      />


![ExpListView](https://user-images.githubusercontent.com/101108540/173298249-622a9c4b-5702-43b7-86dc-b2a33ab8f9a0.jpg)


Attributes of ExpandableListView In Android :
Now let’s we discuss about some important attributes that helps us to configure a
ExpandableListView in XML file(layout).
1. id: id is an attribute used to uniquely identify a Expandable List View.
2. divider: This is a drawable or color to draw between different group list items.
Below we draw red color divider between different group items.
© AbhiAndroid.com - Enrol in our MASTER ANDROID COURSE HERE 299
<ExpandableListView
android:id="@+id/simpleExpandableListView"
android:layout_width="fill_parent"
android:layout_height="fill_parent"/> <!-- id of an attribute used to uniquely identify a
expandable list view -->
<ExpandableListView
android:id="@+id/simpleExpandableListView"
android:layout_width="match_parent"
android:layout_height="fill_parent"
android:divider="#f00"
android:dividerHeight="1dp" /> "/> <!-- red color divider with 1dp height between the
