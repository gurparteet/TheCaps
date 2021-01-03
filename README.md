# TheCaps
As I have officially passed my EECS 1022 course in Fall 2020 semester , I would like to share an app that I made as a Lab on Android Studio using the book
"@Introduction to Computer Science with Andriod Studio- by Hamza Roumani"

App Name : The Caps
---

## About KryptoNote 
It is a fun capital or Country guessing game. It generates random question from a database of countries and their capitals. It asks 50% country guessing 
and 50% capital question. 

## Rules 
- There are maximum 10 questions.
- You get one point for every correct answer.
- No point for skipped question.
- No negative mark for wrong answer(so do give it a shot)
- Game over after 10 Question.

## Algorithm 
It involves using keys and maps for captials and countries. A database is constructed with countries and their keys stored to ref. their capital.
It is an easy implementation using jave 

> Code below:
```
package com.example.thecapsapp;
import java.util.List;
import java.util.Map;

import ca.roumani.i2c.Country;
import ca.roumani.i2c.CountryDB;

public class Game {
    private CountryDB db;
    private String result;


    public Game(){
        this.db= new CountryDB();

    }
    public String qa(){
        List<String> capitals=db.getCapitals();
        int numberOfCapitals= capitals.size();
        int index = (int)(numberOfCapitals  * Math.random()) ;
        String c =capitals.get(index);

        Map<String, Country> data=db.getData() ;
        Country ref =data.get(c) ;

        String countryName , capitalName ;
        countryName=ref.getName();
        capitalName=ref.getCapital();


        if (Math.random() < 0.5){
            String question= "What is the capital of  " + countryName+ " ?" ;
             this.result = question + "\n" + capitalName ;
        }
        else {
            String question= ref.getCapital() + " is capital of?" ;
            this.result = capitalName +" is the capital of? \n"+ countryName ;

        }
        return result;
    }




}
```

> **First Look**
![First Look](/Assests/1.png)


