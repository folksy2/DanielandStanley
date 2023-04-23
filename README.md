# DanielandStanley
ourworkspace
/* eslint-disable jsx-a11y/anchor-is-valid */
import React from "react";
import {useState, useEffect} from "react";


const App = () => {
  const [isOn, setIsOn] = useState(false);//i createdd this const

  function handleClick() {  //created this handle function
    setIsOn("true")

    } 
   


  return (
    <>
      <div className={ "block" ? "true"  : "block night"}>
        <h1>The Light Bulb</h1>
        Your goal: switch the lightbulb on

        <br />
        <ul>
          <li>
            In this component (turn it into a class, or leave it as a function),
            create a state that will keep track of whether the lightbulb is
            turned on or not
          </li>
          <li>
            Put an onClick handler on the <strong>turn me on</strong> button
            that will change the lightbulb's state from on to off
          </li>
          <li>
            Using the state as a toggler, conditionaly change the className of
            the lightbulb's holding div from <em>"block"</em> to{" "}
            <em>"block night"</em>
          </li>
          <li>
            Let's think about the planet and not be wasteful. Make sure that the
            lightbulb turns itself off after 5 seconds :)
          </li>
          <li>
            Using another state, keep track of how many times the light bulb has
            been turned on. After 10 times, tell the user he used his daily
            electricity limit and should light a candle instead.
          </li>
        </ul>
    
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://reactjs.org/docs/state-and-lifecycle.html"
        >
          Help
        </a>
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://www.pluralsight.com/guides/applying-classes-conditionally-react"
        >
          Help
        </a>
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://en.reactjs.org/docs/hooks-state.html"
        >
          Help
        </a>
      </div>

      <div className={"block"}>
        <a><button onClick={handleClick}>turn me on!</button></a>
        <div className="container">
          <div className="bulb-light">
            <div id="light" />

            <div id="bulb">
              <div className="bulb-top">
                <div className="reflection" />
              </div>
              <div className="bulb-middle-1" />
              <div className="bulb-middle-2" />
              <div className="bulb-middle-3" />
              <div className="bulb-bottom" />
            </div>

            <div id="base">
              <div className="screw-top" />
              <div className="screw-a" />
              <div className="screw-b" />
              <div className="screw-a" />
              <div className="screw-b" />
              <div className="screw-a" />
              <div className="screw-b" />
              <div className="screw-c" />
              <div className="screw-d" />
            </div>
          </div>
        </div>
      </div>
    </>
  );
};

export default App;

=========================================================================================================================================================

import { useState } from 'react'

const BulbLight = ({ on_off, toggle, img, }) => {

  const label = on_off ? "turnoff" : "turnon"

  return (<div>
    <img src={img} />
    <img src={img} />
    <img src={img} />
    <img src={img} />
    <div>
      <img src={img} />
      <img src={img} />
      <img src={img} />
      <img src={img} />
    </div>
    <div>
      <button type="button" onClick={toggle}>{label}</button>

    </div>
  </div>)

}

function App() {
  const [isOn, setIsOn] = useState(false)
  const [bulbImage, setBulbImage] = useState("off.gif")
  const [count, setCount] = useState(0)

  function switchImage() {
    if (isOn) {
      setIsOn(false)
      setBulbImage("off.gif");

    } else {
      setIsOn(true)
      setBulbImage("on.gif");
      setCount(count + 1)
    }

    setTimeout(() => {
      setBulbImage("off.gif")
      setIsOn(false)
    }, 5000);

  }

  return (
    <div>
      <BulbLight toggle={switchImage} on_off={isOn} img={bulbImage} />
      <>
        The bulbs have been turned on {count} times
      </>
    </div>
  );
}

export default App;
=========================================================================================

/*
Simple react app to toggle light bulb images.
The two images are located in my vscode's public folder.
Not possible to place the folders here.
The app can be run as is if the two bulb images are named exactly as in this app
and placed in the public folder of your vscode.
Notice the use of ternary operator to toggle the text on the button.
Two states were used. One for on/off position. The other for the bulb images.
Function component—always recommended so as to use hooks—is used instead of class component.
*/

import { useState } from 'react'

const BulbLight = ({ on_off, toggle, img }) => {

  const label = on_off ? "turnoff" : "turnon"

  return (<div>
    <img src={img} />
    <div>
      <button type="button" onClick={toggle}>{label}</button>
    </div>

  </div>)

}

function App() {
  const [isOn, setIsOn] = useState(false)
  const [bulbImage, setBulbImage] = useState("off.gif")

  function switchImage() {
    
    if (isOn) {
      setIsOn(false)
      setBulbImage("off.gif");

    } else {
      setIsOn(true)
      setBulbImage("on.gif");

    }
  }



  return (
    <div>
      <BulbLight toggle={switchImage} on_off={isOn} img={bulbImage} />
    </div>
  );
}

export default App;

==================================================================
/* The switchImage function was tweaked to automatically toggle the bulb image*/

function switchImage() {
    if (isOn) {
      setIsOn(false)
      setBulbImage("off.gif");

    } else {
      setIsOn(true)
      setBulbImage("on.gif");
    }

    setTimeout(() => {
      setBulbImage("off.gif")
      setIsOn(false)
    }, 5000);

  }
  
  =================================================================================================
  
  
