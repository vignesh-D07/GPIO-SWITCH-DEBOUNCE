# GPIO-SWITCH-DEBOUNCE
Configure an on-board switch pin as a GPIO input with an internal pull-up resistor and implement software debouncing. Compare the switch response before and after eliminating mechanical bounce. 
---

## Apparatus Required

| S. No. | Apparatus / Software | Specification |
|:---:|---|---|
| 1 | Microcontroller Development Board | **NXP S32K144 Development Board** |
| 2 | IDE | **S32 Design Studio** |
| 3 | Programming Language | **Embedded C** |
| 4 | SDK | **S32K144 SDK** |
| 5 | LED | On-board LED / External LED |# GPIO-SWITCH-DEBOUNCE
Configure an on-board switch pin as a GPIO input with an internal pull-up resistor and implement software debouncing. Compare the switch response before and after eliminating mechanical bounce. 
---

## Apparatus Required

| S. No. | Apparatus / Software | Specification |
|:---:|---|---|
| 1 | Microcontroller Development Board | **NXP S32K144 Development Board** |
| 2 | IDE | **S32 Design Studio** |
| 3 | Programming Language | **Embedded C** |
| 4 | SDK | **S32K144 SDK** |
| 5 | LED | On-board LED / External LED |
| 6 | Programmer / Debugger | On-board Debugger / OpenSDA |
| 7 | USB Cable | For programming and power supply |

---
## Procedure


1. Connect the **NXP S32K Evaluation Board** to the computer using the **USB Debug Cable**.

2. Open the **ANCIT GenX Tool** and create/open the project for the target S32K microcontroller.

3. Configure the **user switch GPIO pin as a Digital Input** with the required interrupt capability.

4. Configure the **on-board LED GPIO pin as a Digital Output**.

5. Configure the switch interrupt to detect the required **rising-edge or falling-edge transition**.

6. Configure a hardware **timer** using the ANCIT GenX Tool and set the required debounce delay, typically in the range of a few milliseconds.

7. Generate the required **ECUx and MCAL GPIO/timer configuration and initialization code** using the ANCIT GenX Tool.

8. Integrate the generated configuration and initialization files into the application project.

9. Build the project in the selected S32 development environment and verify that there are no compilation errors.

10. Program the application into the **S32K Evaluation Board** and start execution.

11. When the switch is pressed or released, allow the **GPIO interrupt** to detect the initial transition.

12. In the GPIO interrupt service routine, record the switch event and start the configured **timer-based debounce delay**.

13. Do not wait inside the GPIO interrupt or main loop. Allow the timer to run independently so that the **main loop remains free to execute other tasks**.

14. After the debounce timer expires, read the switch GPIO state again and verify whether the switch state is stable.

15. If the switch state is stable, accept it as a valid switch event and update the LED accordingly.

16. If the switch state has changed during the debounce period, treat the transition as a bounce and ignore the false event.

17. Repeat the switch press and release operation several times and observe the LED response.

18. Verify that multiple transitions caused by **mechanical switch bounce** do not result in multiple LED state changes.

19. Observe the main loop operation during the debounce period and verify that it continues executing other application tasks without being blocked by a delay function.

20. Compare the behaviour with a conventional blocking-delay debounce method and verify that the **GPIO interrupt + timer-based method eliminates false triggering while maintaining non-blocking main-loop operation**.


---
## OUTPUT



<img width="1917" height="1197" alt="image" src="https://github.com/user-attachments/assets/92793705-c551-4371-acce-1d1b95a66b1c" />














---
## Result
The experiment was done successfully.

The **GPIO interrupt and timer-based non-blocking debounce** technique was successfully implemented. The timer delay effectively filtered the unwanted switch-bounce transitions and eliminated **false triggering**. The main loop continued to execute during the debounce period without blocking, confirming efficient and reliable switch debouncing.



| 6 | Programmer / Debugger | On-board Debugger / OpenSDA |
| 7 | USB Cable | For programming and power supply |

---
## Procedure


1. Connect the **NXP S32K Evaluation Board** to the computer using the **USB Debug Cable**.

2. Open the **ANCIT GenX Tool** and create/open the project for the target S32K microcontroller.

3. Configure the **user switch GPIO pin as a Digital Input** with the required interrupt capability.

4. Configure the **on-board LED GPIO pin as a Digital Output**.

5. Configure the switch interrupt to detect the required **rising-edge or falling-edge transition**.

6. Configure a hardware **timer** using the ANCIT GenX Tool and set the required debounce delay, typically in the range of a few milliseconds.

7. Generate the required **ECUx and MCAL GPIO/timer configuration and initialization code** using the ANCIT GenX Tool.

8. Integrate the generated configuration and initialization files into the application project.

9. Build the project in the selected S32 development environment and verify that there are no compilation errors.

10. Program the application into the **S32K Evaluation Board** and start execution.

11. When the switch is pressed or released, allow the **GPIO interrupt** to detect the initial transition.

12. In the GPIO interrupt service routine, record the switch event and start the configured **timer-based debounce delay**.

13. Do not wait inside the GPIO interrupt or main loop. Allow the timer to run independently so that the **main loop remains free to execute other tasks**.

14. After the debounce timer expires, read the switch GPIO state again and verify whether the switch state is stable.

15. If the switch state is stable, accept it as a valid switch event and update the LED accordingly.

16. If the switch state has changed during the debounce period, treat the transition as a bounce and ignore the false event.

17. Repeat the switch press and release operation several times and observe the LED response.

18. Verify that multiple transitions caused by **mechanical switch bounce** do not result in multiple LED state changes.

19. Observe the main loop operation during the debounce period and verify that it continues executing other application tasks without being blocked by a delay function.

20. Compare the behaviour with a conventional blocking-delay debounce method and verify that the **GPIO interrupt + timer-based method eliminates false triggering while maintaining non-blocking main-loop operation**.


---
## OUTPUT

















---
## Result

The **GPIO interrupt and timer-based non-blocking debounce** technique was successfully implemented. The timer delay effectively filtered the unwanted switch-bounce transitions and eliminated **false triggering**. The main loop continued to execute during the debounce period without blocking, confirming efficient and reliable switch debouncing.


