# Android_ToolBar_Custom
Making Custom ToolBar in Android

This topic is a part of [My Complete Andorid Course](https://github.com/ananddasani/Android_Apps)

# Code

**1. Make toolbar_layout File**
### toolbar_layout.xml
```

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    android:orientation="vertical">

    <androidx.appcompat.widget.Toolbar
        android:id="@+id/toolbar"
        android:minHeight="?attr/actionBarSize"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:titleTextColor="@android:color/white"
        android:background="?attr/colorPrimary"
        android:theme="@style/ThemeOverlay.AppCompat.Dark"
        app:popupTheme="@style/ThemeOverlay.AppCompat.Light"
        >
    </androidx.appcompat.widget.Toolbar>

    <!-- Layout for content is here. This can be a RelativeLayout  -->

</LinearLayout>
```

**2. Add Menu and all oter stuffs in Toolbar in menu/....**
### menu/toolbar_menu.xml
```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item android:title="New Group"
        android:id="@+id/newGroup"
        />

    <item android:title="Web WhatsApp"
        android:id="@+id/webWhatsApp"
        />

</menu>
```

**3. Include all above work in activity_main.xml file**
### activity_main.xml
```
    <include
        android:id="@+id/toolbar_layout"
        layout="@layout/toolbar_layout" />
```

**4. Remove the Actionbar from styles **

**5. Do Backend by Inflating the toolbar and ....**
#### MainActivity.java
```
Toolbar toolbar;

toolbar = findViewById(R.id.toolbar);
setSupportActionBar(toolbar);
    
    @Override
    public boolean onCreateOptionsMenu(Menu menu) {

        //inflate menu
        getMenuInflater().inflate(R.menu.toolbar_menu, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {

        switch (item.getItemId()){
            case R.id.newGroup:
                Toast.makeText(this, "New Group Selected", Toast.LENGTH_SHORT).show();
                break;

            case R.id.webWhatsApp:
                Toast.makeText(this, "Web WhatsApp Selected", Toast.LENGTH_SHORT).show();
                break;
        }

        return true;
    }
```

# App Highlight

![Toolbar App1](https://user-images.githubusercontent.com/74413402/192095494-bdd7be4e-f9f8-4cbb-9bec-50d9cffee32a.png)
![Toolbar App2](https://user-images.githubusercontent.com/74413402/192095498-d9d91892-349c-4ab9-87b3-238139de0275.png)
![Toolbar Code](https://user-images.githubusercontent.com/74413402/192095499-19f8663f-924d-406c-a09e-e5706c279186.png)

