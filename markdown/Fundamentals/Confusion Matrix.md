# Confusion Matrix

## TL;DR

![Confusion_Matrix_and_ROC](https://raw.githubusercontent.com/EckoTan0804/upic-repo/master/uPic/Confusion_Matrix_and_ROC.png)



## Confuse matrix

A confusion matrix tells you what your ML algorithm did right and what it did wrong.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-cly1{text-align:left;vertical-align:middle}
.tg .tg-tab6{color:#77b300;text-align:left;vertical-align:top}
.tg .tg-viqs{color:#fe0000;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
.tg .tg-hjor{font-weight:bold;color:#9698ed;text-align:center;vertical-align:middle}
.tg .tg-dsu0{color:#9698ed;text-align:left;vertical-align:top}
.tg .tg-0sd6{font-weight:bold;color:#3399ff;text-align:center;vertical-align:top}
.tg .tg-12v1{color:#3399ff;text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-0lax" colspan="2" rowspan="2"></th>
    <th class="tg-hjor" colspan="2">Known Truth</th>
    <th class="tg-cly1" rowspan="2"></th>
  </tr>
  <tr>
    <td class="tg-dsu0">Positive</td>
    <td class="tg-dsu0">Negative</td>
  </tr>
  <tr>
    <td class="tg-0sd6" rowspan="2"><br>Prediction</td>
    <td class="tg-12v1">Positive</td>
    <td class="tg-tab6">True Positive (TP)</td>
    <td class="tg-viqs">False Positive (FP)</td>
    <td class="tg-0lax">Precision = TP / (TP+FP)</td>
  </tr>
  <tr>
    <td class="tg-12v1">Negative</td>
    <td class="tg-viqs">False Negative (FN)</td>
    <td class="tg-tab6">True Negative (TN)</td>
    <td class="tg-0lax" rowspan="2"></td>
  </tr>
  <tr>
    <td class="tg-0lax" colspan="2"></td>
    <td class="tg-0lax">Sensitivity (Recall) = TP / (TP + FN)</td>
    <td class="tg-0lax">Specificity = TN / (FP+TN)</td>
  </tr>
</table>

- Row: Prediction
- Column: Known truth 

Each cell:

- Positive/negative: refers to the prediction

- True/False: Whether this prediction matches to the truth

- The numbers along the diagonal (green) tell us how many times the samples were correctly classified
- The numbers not on the diagonal (red) are samples the algorithm messed up.



## 🎥 Explaination

- [Machine Learning Fundamentals: The Confusion Matrix](http://https://www.youtube.com/watch?v=Kdsp6soqA7o&list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF&index=3)
- [Machine Learning Fundamentals: Sensitivity and Specificity](http://https://www.youtube.com/watch?v=vP06aMoz4v8&list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF&index=4)
- [ROC and AUC, Clearly Explained!](http://https://www.youtube.com/watch?v=4jRBRDbJemM&list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF&index=6)

