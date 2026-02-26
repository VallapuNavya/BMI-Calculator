# Effect Hook - Part-2

- Persisting Application data
 - Local Storage
- Storing values in Local Storage 
 - Using Effect Hook
- Tips for using Effect Hook
 - Multiple Effects
 - Dependency Array
###
React starts
   ↓
Calls BmiCalculator component function
   ↓
Creates state variables
   height = 170
   weight = 60
   ↓
Calls getBmi(170, 60)
   ↓
BMI = 20.76
   ↓
Generates JSX (UI)
   ↓
Displays UI on screen
   ↓
Runs useEffect
   ↓
document.title = "Your BMI: 20.76"
###
Execution Flow:

User clicks + button
   ↓
onIncrementWeight() called
   ↓
setWeight(prevWeight => prevWeight + 1)
   ↓
React updates state
   ↓
weight becomes 61
   ↓
React triggers RE-RENDER
   ↓
BmiCalculator() runs again
   ↓
getBmi(170, 61)
   ↓
BMI = 21.11
   ↓
New JSX created
   ↓
UI updated with new values
   ↓
useEffect runs
   ↓
document.title = "Your BMI: 21.11"
###
Internal React Working Diagram (Core Concept):

             USER ACTION
                 ↓
            Event Handler
                 ↓
            setState()
                 ↓
         React updates state
                 ↓
         React calls component again
                 ↓
            Recalculate BMI
                 ↓
           Generate new JSX
                 ↓
      Compare with old JSX (Virtual DOM)
                 ↓
      Update only changed parts in Real DOM
                 ↓
             UI Updated
                 ↓
            useEffect runs

