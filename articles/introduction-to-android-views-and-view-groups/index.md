### Introduction
All user’s interaction with an Android application is via the user interface (UI). Therefore, knowing the fundamentals of the android application’s user interface is very essential. In android, The user interface of an android application is made up of a collection of views and view groups. This article goes through commonly used views, view groups, and the attributes associated with them.

#### Prerequisites
To follow through this article, you’ll need:
- [Android Studio](https://developer.android.com/studio) installed.
- Basic knowledge of building Android applications.

#### Views
A view is a rectangular block on the screen used to create UI components. It refers to the `android.view.View ` class, which is the base class for all GUI components. 

The attributes `android:layout_width` and `android:layout_height` is mandatory for every view and view group. They can take two forms that are `wrap_content`(adjusts height and width to the content) and `match_parent`(adjusts height and width to the full size of the parent container). They can also take specific density pixel values(dp/dip)

Some of the commonly used views in android are:

- TextView
- EditText
- Buttons
- ImageView

**TextView**
This view is for displaying text. We can also use it with other views. For example, when creating forms, it can be used alongside the EditText view to mention information required to enter by the user.

Example of TextView in XML:
```xml
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:text="hello world"
        android:textColor="#df3e4c"
        android:textSize="20sp"/>
```

![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-text-view.png)

First,  we open the tag with `<`and type TextView, indicating we are creating a TextView that will get displayed in the app. The same format will be used in the other views and viewgroups we'll discuss.

Now, let's see what the attributes stated above do:

- `android:gravity=”center”` – it is used to define the direction of the contents of a view. in this, our content “Hello world” will be aligned at the center.
- `android:text=” hello world”` – This attribute specifies the text to display. "hello world" will be the text displayed.
- `android:textColor=”#df3e4c”` – This attribute is used to set the color of the text. `"#df3e4c"`   is a color code that can be accessed from material design websites.
- `android:textSize=”20sp”` – This attribute is used to set the text size. Scale pixel(sp) is for text size scaled by the user's font performance. density pixel(dp) is used for everything else.

**NOTE:** Android provides many different attributes that can be applied to manage various properties thus, the user is not limited to the above only.

**EditText**
It is a widget that allows the user to enter text. The android:inputType attribute is not really a must since it has a default value of text.

Example of EditText in XML:
```xml
    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Enter your Name"
        android:textColorHint="#df3e4c"
        android:textColor="#df3e4c"
        android:inputType="text"
        android:maxLength="10"/>
```
![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-edit-text.png)

The attributes we have stated above will be broken down as follows:

- `android:hint=” Enter your Name”` - it is used to display the hint when the text is empty. The user will see the hint as “Enter your Name”.
- `android:textColor=”#de4f3e” ` - it is used to set the color of the text.
- `android:textColorHint=”#de4f3e” ` - It is used to set the color of the text.
- `android:inputType=”text” `-It is used to specify the type of input that the view should accept.
- `android:maxLength=”10”` - Specifies the maximum number of characters that the view should accept. in this case, it only accepts 10 characters.

**Button**
it is a user interface feature that contains a text or an icon that the user can tap or click to act.

Example of Button in XML:

```xml  
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="click me"
        android:backgroundTint="#df3e4c"/>
```

![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-button.png)

The attributes are defined as follows:

- `android:backgroundTint=”#de4f3e”` - It sets the background color of the button.
- `android:text=”click me”` - is the text that will be displayed on the button.

**ImageView**
it is a widget used to display images and bitmaps in android applications. Image files supported by android are in three formats:

`.png` -preferred
`.jpg` -acceptable
` .gif` -discouraged

Example of ImageView in XML:

```xml
    <ImageView
        android:layout_width="160dp"
        android:layout_height="140dp"
        android:src="@drawable/ic_campaign"/>
```
![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-image-view.png)

The attributes are defined as follows:

`android:src=”@drawable/ic_campaign” />` - sets a drawable as the content of this ImageView.
A drawable resource is a general term for a graph that can be drawn on the screen and can be retrieved by adding attributes such as `android:drawable` and `android:icon` to another XML resource.

Android also provides more views such as Spinners, CheckBox and RadioButtons for more user input
Output screen

#### ViewGroups
A ViewGroup is a view that holds other views. The View group is the base class for containers, templates and views. Views use `LayoutParams` that serves to inform the parent class how to lay them out. For an easier understanding of viewgroups, we'll use the views we discussed to illustrate how we can align each of them in the same viewgroup. Some of the layout parameters take a boolean value, such as "true" or "false".

Some of the commonly used Viewgroups are:
- RelativeLayout
- LinearLayout
- ConstraintLayout
- FrameLayout

**RelativeLayout**
RelativeLayout displays views relatively to one another. The view position has some relation to the sibling. RelativeLayout substitutes many nested LinearLayout groups while keeping the hierarchy of the layout flat, improving performance.

Example of RelativeLayout in XML:

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="hello world"
        android:textColor="#df3e4c"
        android:textSize="20sp"/>

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:hint="Enter your Name"
        android:textColorHint="#df3e4c"
        android:textColor="#df3e4c"
        android:inputType="text"
        android:maxLength="10"/>
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:text="click me"
        android:backgroundTint="#df3e4c"/>
    <ImageView
        android:layout_width="160dp"
        android:layout_height="140dp"
        android:layout_alignParentBottom="true"
        android:src="@drawable/ic_campaign"/>

</RelativeLayout>
```

![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-relative-layout.png)

The attributes are defined as follows:

- `android:layout_alignParentEnd="true"` - It makes the end edge of this view match the end edge of the parent when the boolean value is true. In this case, the EditText view will align to the end edge of the parent.
- `android:layout_alignParentEnd="true"` - True, makes the end edge of the button view  match the end edge of the parent.
- `android:layout_alignParentBottom="true"` - 	True, makes the bottom edge of the button view match the bottom edge of the parent.
- `android:layout_alignParentBottom="true"` - True, makes the bottom edge of the ImageView match the bottom edge of the parent.

**LinearLayout**
Views are arranged in a linear format either vertically or horizontally. LinearLayout children are stacked one by one, so no matter how large they are, a vertical list will only have one child per row and a horizontal list will only be one row long.

Example of LinearLayout in XML:

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="hello world"
        android:textColor="#df3e4c"
        android:textSize="20sp"/>

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Enter your Name"
        android:textColorHint="#df3e4c"
        android:textColor="#df3e4c"
        android:inputType="text"
        android:maxLength="10"/>
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="click me"
        android:backgroundTint="#df3e4c"/>
    <ImageView
        android:layout_width="160dp"
        android:layout_height="140dp"
        android:src="@drawable/ic_campaign"/>

</LinearLayout>
```

![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-linear-layout.png)

The attributes above can be defined as follows:
-`android:gravity="center"`-  This controls how linear layout aligns all the views it contains.  In this case, the views will align at the center.
-`android:orientation="vertical"` - This determines the arrangement direction. We use "vertical" for a column" and "horizontal" for a row. In this case, the views are arranged in a column.

**ConstraintLayout**
It allows developers to position and size widgets in a flexible way. One of the fundamental building blocks of layout formation in ConstraintLayout is relative positioning. This allows you to position a given view relative to another one. A view will restrict to the horizontal and vertical axes. The general idea is to constrain a specific side of a widget to another side of some other widget.

Example of ConstraintLayout in XML:

```xml
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:text="hello world"
        android:textColor="#df3e4c"
        android:textSize="20sp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_marginEnd="20dp"
        android:layout_marginRight="20dp"
        android:hint="Enter your Name"
        android:inputType="text"
        android:maxLength="10"
        android:textColor="#df3e4c"
        android:textColorHint="#df3e4c"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="20dp"
        android:layout_marginLeft="20dp"
        android:backgroundTint="#df3e4c"
        android:text="click me"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <ImageView
        android:layout_width="160dp"
        android:layout_height="140dp"
        android:layout_alignParentBottom="true"
        android:layout_marginBottom="20dp"
        android:src="@drawable/ic_campaign"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-constraint-layout.png)

The attributes are defined as follows:

- `android:id="@id/textView"` -  The `android:id` attribute lets you specify a unique id—a resource identifier for every view. in this case the resource identified is TextView.
- `android:layout_marginTop="20dp"` - sets the distance from top between the constraints to 20dp
- `app:layout_constraintEnd_toEndof="parent"` - This attribute constrains the end of the Textview to an end of another view which in this case is the parent.
- `app:layout_constraintStart_toStartof="parent"` -  This attribute constrains the start of the TextView to the start of another view which in this case is the parent.
- `app:layout_constraintTop_toTopof="parent"` - This attribute constrains the top of the view to the top of another view which in this case is the parent.
- `app:layout_constraintEnd_toEndof="parent"` - This attribute constrains the end of the TextView to the end of another view which in this case is the parent.
- `android:id="@id/editText"` - The resource identified is EditText.
- `android:layout_marginEnd="20dp"` -  sets the distance from end between the constraints to 20dp.
- `android:layout_marginRight="20dp"` - sets the distance from right between the constraints to 20dp.
- `app:layout_constraintBottom_toBottomof="parent"` - This attribute constrains the bottom of the EditText to the end of another view which in this case is the parent.
- `app:layout_constraintEnd_toEndof="parent"` - This attribute constrains the end of the EditText to the end of another view which in this case is the parent.
- `app:layout_constraintTop_toTopof="parent"` - This attribute constrains the top of the EditText to the top of another view which in this case is the parent.
- `android:layout_marginStart="20dp"` - sets the distance from start between the constrains to 20dp.
- `android:layout_marginLeft="20dp"` - sets the distance from left between the constrains to 20dp
- `android:layout_marginTop="20dp"` - sets distance from top between the constraints to 20dp
- `app:layout_constraintStart_toStartof="parent"` - This attribute constrains the start of the button to the start of another view which in this case is the parent.
- `app:layout_constraintTop_toTopof="+@id/editText"` - This attribute constrains the top of the button to the top of another view which in this case is the EditText.
- `android:layout_marginBottom="20dp"` - sets the bottom distance between the constrains to 20dp.
- `app:layout_constraintBottom_toBottomof="parent"` - This attribute constrains the bottom of the ImageView to the bottom of another view which in this case is the parent.
- `app:layout_constraintEnd_toEndof="parent"` - This attribute constrains the end of the ImageView to the end of another view which in this case is the parent.
- `app:layout_constraintStart_toStartof="parent"` - This attribute constrains the start of the ImageView to the start of another view which in this case is the parent.


**FrameLayout**
FrameLayout holds a single child view. it is designed to block out a region on the screen to view a single item.

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_marginTop="20dp"
        android:text="hello world"
        android:textColor="#df3e4c"
        android:textSize="20sp" />


</FrameLayout>
```
![Output screen](/engineering-education/android-views-and-viewgroups/screenshot-frame-layout.png)

The attributes above can be defined as follows:
- `android:layout_marginTop="20dp` - Specifies extra space on the top side of this view. Hence, the extra space is set to "20dp"
- `android:layout_gravity="center"` - controls how frame layout aligns the view it contains. The value you set affects both horizontal and vertical alignment of all child views within the single row or column. In this case, the views are aligned at the center.

Android also provides more viewgroups such as GridLayout and TableLayout for more user input
Output screen.

#### Conclusion
In this article, we've gone through creating views and viewgroups. We have also seen some of the attributes associated with our views and viewgroups, where they are used and what they are used for. This helps developers build applications with a better user experience.