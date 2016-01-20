# TabLayoutDemo
[Android support design](https://developer.android.com/reference/android/support/design/widget/TabLayout.html) -- TabLayout Demo

Start:

Layout:
```XML
...
 <android.support.v4.view.ViewPager
        android:id="@+id/container"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:layout_behavior="@string/appbar_scrolling_view_behavior"/>

    <android.support.design.widget.TabLayout
        android:id="@+id/tl"
        android:layout_marginTop="80dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:tabGravity="center"
        app:tabIndicatorColor="#FF00FF00"
        app:tabMode="scrollable"
        app:tabSelectedTextColor="#FF00FF00"
        app:tabTextColor="#FF000000"></android.support.design.widget.TabLayout>
...
```

Activity:
```JAVA
// Create the adapter that will return a fragment for each of the three
        // primary sections of the activity.
        mSectionsPagerAdapter = new SectionsPagerAdapter(getSupportFragmentManager());

        // Set up the ViewPager with the sections adapter.
        mViewPager = (ViewPager) findViewById(R.id.container);
        mViewPager.setAdapter(mSectionsPagerAdapter);

        // Set up the TabLayout
        mTabLayout = (TabLayout)findViewById(R.id.tl);
        mTabLayout.setTabsFromPagerAdapter(mSectionsPagerAdapter);
        mTabLayout.setupWithViewPager(mViewPager);

```

