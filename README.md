Download Link: https://assignmentchef.com/product/solved-cs5704-project4-design-patterns
<br>
<strong>Deliverables: A <em>.zip file of the ducksim folder containing all of your </em>.java files</strong>

<strong>In addition to the requirements given below, please implement the following two requirements.</strong>

<ol>

 <li><strong><em>When you select a duck (left click on it), the background of the square should turn to the duck’s color </em></strong><strong><em>(instead of black)</em></strong></li>

 <li><strong><em>When a duck joins the welcoming committee, a little “w” should appear in the bottom left corner of the duck’s square.</em></strong></li>

</ol>

<strong>Here is a sample run of a completed application:</strong>

<strong>Download the</strong><strong><u> ducksim-starter-src</u></strong><strong> archive, create a project from it, and make the following </strong><strong>modifications.</strong>

<strong>Strategy Pattern</strong>

<strong>Use the Strategy Pattern to encapsulate flying behavior and quacking behavior. Create FlyBehavior and </strong><strong>QuackBehavior interfaces. FlyBehavior should have 2 implementations: FlyNoWay and FlyWithWings. </strong><strong>QuackBehavior should have 3 implementations: QuackNoWay, QuackNormal, and QuackSqueek.</strong>

<strong>Implement the following capture and release behavior for ducks. When a duck is captured, it will neither </strong><strong>fly nor quack. However, when a duck is released, it will exhibit the flying and quacking behavior that it did </strong><strong>originally.</strong>

<strong>Decoy Duck</strong>

<strong>Implement a decoy duck that can neither fly nor quack. The color of the decoy duck should be orange.</strong>

<strong>Decorator Pattern</strong>

<strong>Add an abstract decorator class Bling to ducks. You should have 3 types of bling represented by the </strong><strong>following classes: StarBling, MoonBling, and CrossBling. Each item of bling will be added to the display </strong><strong>method by adding a colon and a     </strong><strong>for star, a for moon, or a for cross. For example, the display</strong><strong>method of a mallard duck with two stars and a moon will return the string</strong><strong> :Mallard:*:*:)</strong><strong> . </strong><strong>The </strong><strong>DuckSimView component is already configured to handle the bling.</strong>

<strong>Modify the MakeDuckDialog component so that it includes a bling panel in between the duck panel and </strong><strong>the button panel. The bling panel should have a grid layout consisting of 3 rows and four columns. The </strong><strong>first row will have a label with</strong><strong> ,Star,,</strong><strong> a label with , a button with    </strong><strong>and a button with . The second</strong><strong>row will be similar but its first label will be</strong><strong> (Moon</strong><strong> , </strong><strong>and the first label of the third row will be</strong><strong> Cross</strong><strong> . </strong><strong>The </strong><strong>buttons should have the following logic:</strong>

<strong>When a       </strong><strong>button is pressed the number in its row is incremented. When a       </strong><strong>button is pressed, the</strong>

<strong>number is decremented. The numbers will never go below 0, and the sum of all three numbers will never </strong><strong>go above 3.</strong>

<strong>Use lambda expressions for the action listeners on your buttons. See how I did the action listeners for </strong><strong>the other buttons. For example:</strong>

<strong>cancelButton.addActionListener(e -&gt; { </strong><strong>this. dispose();</strong>

});

<strong>The addActionListener is expecting something that implements the ActionListener functional interface, </strong><strong>which only declares one method (actionPerformed). As of Java 8, instead of writing a class that implements only one method, you can use lambda notation: just pass in a variable that represents the arguments to the method (in this case, e represent the ActionEvent argument to the function actionPerformed) and then pass in the method body. Done!</strong>

<strong>Factory Pattern</strong>

<strong>Add class DuckFactory to the simulator. The duck factory should handle the creation of all ducks. It will </strong><strong>have a method called createDuck with the following signature:</strong>




<strong>public Duck createDuck(String duckType, int starCount, int moonCount, int crossCount)</strong>

<strong>Make the duck factory a singleton class!</strong>

<strong>Adapter Pattern</strong>

<strong>Write an adapter called GooseDuck for the following Goose class:</strong>

<strong>class Goose {</strong>

<strong>String getHonk() { return “Honk!”; }</strong><strong>String getName() { return “Goose”; }</strong>

1

<strong>The adapted goose should use the normal fly and quack strategies. However, the result of getHonk should appear when a goose “quacks” and the result of getName should appear on the goose’s button.</strong>

<strong>Observer Pattern</strong>

<strong>NOTE: Do NOT use the </strong><strong><em>Java </em></strong><strong>Observable class and Observer interface to implement the observer </strong><strong>pattern!</strong>

<strong>Instead, create your own Subject and Observer interfaces, and use those to implement the observer </strong><strong>pattern as show in </strong><strong>HFDP. It is also fine to make Subject an abstract class, and implement methods </strong><strong>registerObserver, removeObserver, and notifyObservers directly in the Subject class. However, Observer must be an interface, and it should have the update method.</strong>

<strong>The duck factory will be the subject and the ducks will be the potential observers. When a duck joins the </strong><strong>DuckSim Welcoming Committee (DSWC) it registers with the duck factory so that when a new duck is </strong><strong>created a</strong><strong> Welcome</strong><strong> message appears above the DSWC member’s name.</strong>

<strong>Modify the simulator so that if a duck is captured, it says</strong><strong> Beware!</strong><strong> instead of</strong><strong> Welcome!</strong><strong> .</strong>

<strong>The Welcome/Beware message should stay over the duck’s name until the screen is repainted.</strong>

<strong>Composite Pattern</strong>

<strong>In this section, you will use the composite pattern to create a Flock class, which is the a composite for </strong><strong>the Duck class. The requirements for the composite class are:</strong>

<ul>

 <li><strong>The Flock must be a Duck</strong></li>

 <li><strong>The Flock will hold a collection of Ducks</strong></li>

 <li><strong>The Flock must display the word “Flock” followed by the first letter in the name of every Duck it holds </strong><strong>(where the Bling would normally be)</strong></li>

 <li><strong>A Flock cannot have Bling</strong></li>

 <li><strong>The fly method works as usual on a Flock (it uses the Duck default)</strong></li>

</ul>

<a href="https://canvas.vt.edu/courses/115592/assignments/963310"><strong>https://canvas.vt.edu/courses/115592/assignments/963310</strong></a><strong>                                                                                                                                           </strong><strong>3/5</strong>




<ul>

 <li><strong>The quack method works as usual on a Flock, but it should the string “Noise!” instead of “Quack!”</strong></li>

 <li><strong>The joinDSCW method works as usual on a Flock, and every Duck that a Flock holds will also join </strong><strong>the DSCW. Similarly with quitting the DSCW.</strong></li>

 <li><strong>The capture method works as usual on a Flock, and every Duck that a Flock holds will be captured. </strong><strong>Similarly with releasing the Flock.</strong></li>

</ul>

<strong>You will need to make some changes to the model and the controller in order to effectively use this </strong><strong>class. First add a getSelectedDucks method to DuckSimModel:</strong>

<strong>public List&lt;Duck&gt; getSelectedDucks() { </strong><strong>List&lt;Duck&gt; result = new ArrayList&lt;&gt;(); </strong><strong>for (Integer i : selected) {</strong>

<strong>result.add(ducks.get(i));</strong>

<strong>I</strong>

<strong>return result;</strong>

<strong>}</strong>

<strong>Next, change the code in DuckSimContoller that executes when the New-Duck button is pressed:</strong>

<strong>if (view.clickedNewDuckButton(e)) {</strong>

<strong>new NewDuckController(model, view).createNewDuck();</strong>

}

<strong>Finally, add a new class called NewDuckController that controls what happens when you click the “New </strong><strong>Duck” button. The class should have fields “model” and “view” to hold the model and the view, and a </strong><strong>single method called createNewDuck. The createNewDuck method should create a NewDuckDialog when no ducks are selected (as was done originally), but when one or more ducks are selected, it </strong><strong>should create a new Flock and add it to the model.</strong>

<strong>public void createNewDuck() {</strong>

<strong>if (model.noSelectedDucks()) {</strong>

<strong>MakeDuckDialog makeDuckDialog = new MakeDuckDialog(model, view); </strong><strong>makeDuckDialog.setSize(300, 200);</strong>

<strong>makeDuckDialog.setVisible(true);</strong>

<strong>1 else {</strong>

<strong>// get the selected ducks from the model</strong>

<strong>// filter the selected ducks by removing any flocks</strong>

<strong>// if there is more than one duck after removing flocks, // create a new flock with the selected ducks</strong>

<strong>Flock flock = new Flock(ducks); </strong><strong>model. addNewDuck(flock);</strong>

<strong>view. repaint();</strong>

}

}




<strong>Essentially, the New-Duck button is used to create both Ducks and Flocks (composites), depending on </strong><strong>whether any ducks are selected.</strong>