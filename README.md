# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step1:Create a new Android Studio project.

Step2:Open the layout file "activity_main.xml".

Step3:Add a container layout to hold the gallery images (e.g., GridLayout, RecyclerView, or ViewPager).

Step4:Within the container layout, add ImageView elements to display the images. You can set the image source using the android:src attribute or programmatically in the code.

Step5:If using a GridLayout, specify the number of columns using the android:columnCount attribute.

Step6:Customize the layout and appearance of the ImageView elements as desired.

Step7:Add any necessary attributes or listeners to handle user interactions, such as clicks on the images.

Step8:Optionally, create a data source to store the images (e.g., a list or an array of image references).

Step9:Bind the data source to the gallery control to populate the images dynamically.

Step10:Implement any additional functionality, such as zooming, sliding, or image transitions, if desired.

Step11:Build and run the application to see the gallery control displaying the images.


## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by:Kausalya G
Registeration Number :212221040076
*/
```
## activity_main.xml:
```
activity_main.xml:
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity" android:orientation="vertical">
 <ImageView
           android:id="@+id/imageView"
           android:layout_width="fill_parent"
           android:layout_height="200dp"
           android:scaleType="fitXY" />
 <!-- By using android:spacing we can give spacing between images
 android:animationDuration="3000" -> for animation running -->
 <Gallery
           android:id="@+id/languagesGallery"
           android:layout_width="match_parent"
           android:layout_height="wrap_content"
           android:layout_marginTop="100dp"
           android:animationDuration="2000"
           android:padding="10dp"
           android:spacing="5dp"
           android:unselectedAlpha="50" />
</LinearLayout>
```
## MainActivity.java:
```
MainActivity.java:
package com.example.ga;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Gallery;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Gallery;
import android.widget.ImageView;
import android.widget.SpinnerAdapter;
public class MainActivity extends AppCompatActivity {
     Gallery simpleGallery;
     // CustomizedGalleryAdapter is a java/kotlin
      // class which extends BaseAdapter
      // and implement the override methods.
      CustomizedGalleryAdapter customGalleryAdapter;
      ImageView selectedImageView;
      // To show the selected language, we need this
      // array of images, here taken 10 different kind of
      // most popular programming languages
      int[] images = {
                  R.drawable.s1,
                 R.drawable.s2,
                 R.drawable.s3,
                  R.drawable.s4,
                 R.drawable.s5,
                 R.drawable.s6,
 };
 @Override
 protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // Our layout is activity_main
        // get the reference of Gallery. As we are showing
        // languages it is named as languagesGallery
        // meaningful names will be good for easier understanding
        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
        // get the reference of ImageView
        selectedImageView = (ImageView) findViewById(R.id.imageView);
        // initialize the adapter
        customGalleryAdapter = new
CustomizedGalleryAdapter(getApplicationContext(), images);
        // set the adapter for gallery
        simpleGallery.setAdapter(customGalleryAdapter);
 
        // Let us do item click of gallery and image can be identified by its
position
        simpleGallery.setOnItemClickListener((parent, view, position, id) ->
{
        // Whichever image is clicked, that is set in the
selectedImageView
        // position will indicate the location of image
        selectedImageView.setImageResource(images[position]);
 });
 }
}

```

## OUTPUT
![WhatsApp Image 2023-06-04 at 12 18 52](https://github.com/gkausalya232/Gallery_control/assets/133086820/97e85852-31cf-4a6a-af37-6d0565db8a46)
![WhatsApp Image 2023-06-04 at 12 18 59](https://github.com/gkausalya232/Gallery_control/assets/133086820/2c90b7cf-3fd4-49d5-a930-2797a9e18e8d)




## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

