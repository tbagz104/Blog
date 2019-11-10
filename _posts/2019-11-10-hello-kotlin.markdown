---
layout: post
title: "Hello Kotlin"
date: 2019-11-10
categories:
  - Android
description: Build your first android app
image: https://i.imgur.com/QjTpTeo.jpg
image-sm: https://i.imgur.com/QjTpTeo.jpg
---
Ever wondered about making your own Android app?Here's your chance to do  so. In this article,you will learn how to create a Hello World app using Kotlin.<br>

<h3> Why Kotlin?</h3>
Kotlin is a new programming language developed by JetBrains that runs on Java Virtual Machine (JVM). Google announced Kotlin as its official programming language for Android app development.<br>

<figure>
  <img src="https://miro.medium.com/max/1260/1*_JIynJkYTmtADwj-RARpAQ.png">

</figure>

<h3>Advantages of Kotlin</h3>

<ul>
  <li>It is highly compatible so that apps that are built with Kotlin, will run on all Android devices (older devices as well).</li>
  <li>Apps developed in Kotlin are faster than the apps developed in Java. Also, Kotlin supports lambda expressions, this makes apps faster.</li>
  <li>It supports all the Android libraries, like Volley API, Retrofit, etc.</li>
  <li>It is easy to learn for Java developers. Also, the existing Java code can be easily converted into Kotlin.</li>
  <li>Compilation time is very fast as compared to Java.</li>
</ul>
<blockquote><strong>Before we start, you need to make sure that you have the necessary requirements to build your first app. </strong></blockquote>


<h3>Prerequisites</h3>
<ol>
  <li>In order to use Kotlin properly, we should use <strong><a href="#">Android Studio 3</a></strong>. It works with lower versions but you need to add a plugin.</li>
  <li><strong><a href="#">Kotlin</a></strong> Installed in your device.</li>

  

</ol>
<blockquote><strong>Once you're done with the prerequisites,you're good to get going.</strong></blockquote>

<h3>Hello Kotlin!</h3>
So let’s create our new project. As usual, open Android Studio and pick the ‘<em>Start a new Android Studio project</em>’ from the welcome screen or just go to ‘<em>File -> New -> New Project…</em>’<br>

<br>Choose an empty activity and click ' <em>Next</em> '

<figure>
  <img src="https://i.imgur.com/RksxchZ.png" align="middle">
</figure>

Then fill in all these details and don’t forget to change your Language to '<em>Kotlin</em>' in the bottom.This will create a base project with Kotlin instead of Java.

<figure>
  <img src="https://i.imgur.com/QfrhkUy.png" align="middle">
</figure>

And we’re good to go, we just created a basic Hello World app with Kotlin. Let’s check some files and see what’s different. If we look at both the Project and app module build.gradle files we can see that Android Studio automatically added the Kotlin dependencies we need.



<figure>
  <img src="https://i.imgur.com/H8pOhWk.png" align="middle">
</figure>

<pre><code>buildscript {
    ext.kotlin_version = '1.3.50'
    repositories {
        google()
        jcenter()
        
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.1'
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

...
</code></pre>
<br>

<figure>
    <img src="https://i.imgur.com/HRqPiFL.png" align="middle">
</figure>

<pre><code>
apply plugin: 'com.android.application'
apply plugin: 'kotlin-android'
apply plugin: 'kotlin-android-extensions'

...

dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation"org.jetbrains.kotlin:kotlin-stdlib-jre7:$kotlin_version"
    ...
}

</code></pre>





So with the Kotlin dependencies sorted for us by Android Studio we can look at some code. Let’s see how our basic MainActivity looks like in Kotlin.<br>

<pre><code>class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
</code></pre>
<br>


<figure>
    <img src="https://i.imgur.com/0lwxlk0.png" align="middle">
</figure>





<br>
Pretty much the same as in Java with just some specific Kotlin syntax in the class and method declaration. This doesn’t give us much so let’s add a few things and actually see some Kotlin in action.


Let’s add a button to our layout that will change the welcome text view from ‘<em>Hello World</em>’ to something more relevant to our context. We also need to add an id to the existing text view. The activity_main.xml should now look like this:

<br>

<figure>
    <img src="https://i.imgur.com/V5zdz8M.png" align="middle">
</figure>


<br>

Now we need to access those views in our MainActivity so we can actually update the text when the button is clicked.

You need to add a listener to the button and change the welcome message on click. Don’t believe me? Run the app and see for yourself. 

<pre><code>
updateTextButton.setOnClickListener { welcomeTextView.text = "Hello Kotlin World!" }
</code></pre>

<br>
Your MainActivity.kt should now look something like this:

<br>
<figure>
  <img src="https://i.imgur.com/1cXlKv2.png" align="middle">

</figure>

<h3>Test Your App</h3>

<figure>
  <img src="https://i.imgur.com/0C9ZwH3.gif" align="middle">
  <figcaption>"Click on the button to change the text to Hello Android"</figcaption>
</figure>

If you've done everything right then your app should work fine.This is a very simple example of how Kotlin can make your life much easier when building Android apps.This is much cleaner with much less boilerplate code.

We created a really basic Hello World app with Kotlin and then made some small changes to demonstrate the power of Kotlin for binding our layout views.
