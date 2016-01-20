# TabLayoutDemo
[Android support design](https://developer.android.com/reference/android/support/design/widget/TabLayout.html) -- TabLayout Demo
![image](https://github.com/Mr7Cat/TabLayoutDemo/blob/master/TabLayout/device-2016-01-20-110202.png)

##Doc
TabLayout provides a horizontal layout to display tabs.

Population of the tabs to display is done through TabLayout.Tab instances. You create tabs via newTab(). From there you can change the tab's label or icon via setText(int) and setIcon(int) respectively. To display the tab, you need to add it to the layout via one of the addTab(Tab) methods. For example:
```
 TabLayout tabLayout = ...;
 tabLayout.addTab(tabLayout.newTab().setText("Tab 1"));
 tabLayout.addTab(tabLayout.newTab().setText("Tab 2"));
 tabLayout.addTab(tabLayout.newTab().setText("Tab 3"));
``` 
You should set a listener via setOnTabSelectedListener(OnTabSelectedListener) to be notified when any tab's selection state has been changed.
If you're using a ViewPager together with this layout, you can use setTabsFromPagerAdapter(PagerAdapter) which will populate the tabs using the given PagerAdapter's page titles. You should also use a TabLayout.TabLayoutOnPageChangeListener to forward the scroll and selection changes to this layout like so:
```
 ViewPager viewPager = ...;
 TabLayout tabLayout = ...;
 viewPager.addOnPageChangeListener(new TabLayoutOnPageChangeListener(tabLayout));
 ```
See Also
[Tabs](http://www.google.com/design/spec/components/tabs.html)





##Step by Step:

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

