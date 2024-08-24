# FLSUN S1
XY Dimension Calibration Method

![Banner](https://github.com/user-attachments/assets/a2ebd6cd-e430-4d7b-a240-a8cac461b0c7)

This can be useful if the accuracy of your dimensions is not acceptable.

## CALIBRATION

- Download this calibration cube: <a href="https://www.printables.com/model/118657-calibration-cube">Printables</a>

- Slice it and print it.

- Once printed, measure the X and Y dimensions. The ideal values ​​of this model are: X=20mm / Y=20mm.

- If you notice a significant deviation in the measured dimensions, it will therefore be necessary to apply a correction.

- Go to your **Mainsail** Web interface then select the `CONSOLE` tab on the left side.

- If you notice a deviation in X, enter this command by replacing `zz`  by your measured value in X (Note: T is the expected value):

  ```
  M101 Xzz T20
  ```

- Wait for Klipper to restart.

- If you notice a deviation in Y, enter this command by replacing `zz`  by your measured value in Y (Note: T is the expected value):
 
  ```
  M101 Yzz T20
  ```

- Wait for Klipper to restart.

- Correction is now applied in your `printer.cfg` file. You can reprint your model to see if the accuracy of your dimensions is now acceptable.
