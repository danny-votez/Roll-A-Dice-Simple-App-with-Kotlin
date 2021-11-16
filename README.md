### Roll A Dice Simple App with Kotlin
#### Pre-requesites
- Android Studio installation
- Knowledge in using Android Studio, especially Layout Editor
- Some basics in Kotlin and programming principles
- Working emulator
#### Working Script
<pre>
<code>
/*

This illustration builds from Google's Developer lessons
GitHub link https://github.com/google-developer-training/android-basics-kotlin-create-dice-roller-with-button-app-solution

 */

package com.example.dicerollerapp

// Automatically added import button below for the button
import android.os.Bundle
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Android assigns ID numbers to resources automatically in the app
        // The syntax is R.<type>.<name>
        // For example, R.string.roll
        // For View IDs, the <type> is id, for example, R.id.button

        setContentView(R.layout.activity_main)

        val rollButton: Button = findViewById(R.id.button)
        // Now, adding an event listener, so that once the button is clicked
        // it executes, i.e., once tapped

        rollButton.setOnClickListener {
            rollDice()
            rollDice2()
            rollDice3()

            // val resultTextView: TextView = findViewById(R.id.textView)
            // This is just same as the standard variable declaration and assignment
            // For example, val name: String = "Kingsman West"
            // Another example, val Age: Int = 33
            // from above
            /*
            val says the variable cannot be changed
            resultTextView is the variable name
            TextView gives the data type
            = assigns
            findViewById(R.id.textView) is now the value

             */


            // val toast = Toast.makeText(this, "Dice Rolled!", Toast.LENGTH_SHORT)
            //  toast.show()
            // The above can also be written as
            // val toast = Toast.makeText(this, "Dice Rolled!", Toast.LENGTH_SHORT).show()
        }
    }

            // First role dice with 6 sides
    private fun rollDice() {
        val dice = Dice(6)
        val diceRoll = dice.roll()
        val resultTextView: TextView = findViewById(R.id.textView)
        resultTextView.text = diceRoll.toString()

    }

        // Second Roll Dice with 12 sides
    private fun rollDice2() {
        val dice1 = Dice(12)
        val diceRoll1 = dice1.roll()
        val resultTextView2: TextView = findViewById(R.id.textView2)
        resultTextView2.text = diceRoll1.toString()

    }

    // Third Roll Dice with 120 sides
    private fun rollDice3() {
        val dice2 = Dice(120)
        val diceRoll2 = dice2.roll()
        val resultView3: TextView = findViewById(R.id.textView7)
        resultView3.text = diceRoll2.toString()
    }
}
    // The Dice Class that also defines the random numbers
class Dice (val numSides: Int) {
    fun roll(): Int {
        return (1..numSides).random()
    }
}
</code>
</pre>
#### Sample Emulator Screens
##### Initial
<img src="https://user-images.githubusercontent.com/77758884/141791550-a4e1e5ed-fdfc-47da-86e0-58dc2037cb3c.png" width=200px />

##### Sample Screens: 1st, 2nd and 3rd Clicks
<div align=center>

<img src="https://user-images.githubusercontent.com/77758884/141791259-1e760833-b995-45c9-8b2c-b3b3d2556fd4.png" width=200px /> <img src="https://user-images.githubusercontent.com/77758884/141791094-eb5a35c2-16b4-4bdc-ad34-3f03795c0bf4.png" width=200px /> <img src="https://user-images.githubusercontent.com/77758884/141791901-c505aef1-0e5a-4321-b0be-bf7dadc553b6.png" width=200px>

</div>
#### Notes

-In the illustration, the displays are based on random value



