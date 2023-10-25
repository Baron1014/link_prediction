# link_prediction
Link prediction is a fundamental task in network analysis, particularly in the fields of graph theory and social network analysis. It leverages the existing network structure and connection patterns to predict missing or potential edges (links) within a given network. Its purpose is to infer or estimate connections that may exist but have not been observed or explicitly defined. In this experiment, we utilized three datasets provided by Professor Cheng-Te Li of  Institute of Data Science at NCKU. We implemented link prediction using various common graph feature indicators to identify the best-performing features and model combinations.
<div align="center">
<img src="https://i.imgur.com/Q8PqRSe.png" width="50%" >
</div>

## Performance Table
- feature 1:
    - Common Neighbor
    - Preferential Attachment
    - Jaccard’s Coefficient
    - Adamic/Adar (AA)
- feature 2:
    - Salton index
    - Sφrensen index
    - Hub Promoted & Hub Depressed index
    - Leicht-Holme-Newman
    -  Resorce Allocation
- Random Walk with Restart (RWR)
### Dataset 1
<table>
  <tr>
    <th colspan="3"><CENTER>Attribute</th>
    <th colspan="2"><CENTER>Random Forest</th>
    <th colspan="2"><CENTER>DNN</th>
  </tr>
  <tr>
    <th>feature 1</th>
    <th>feature 2</th>
    <th>RWR</th>
    <th><CENTER>AUC</th><th><CENTER>AP</th>
    <th><CENTER>AUC</th> <th><CENTER>AP</th>
  </tr>
  <tr>
    <td><CENTER> V <td>  <td>  <td> .700 <td> .783 <td> .683 <td> .771
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td>  <td> .687 <td> .779 <td> .686 <td>  .781
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td><CENTER> V  <td> .700 <td> .782 <td> .684 <td>  .781
  </tr>
  
 </table>
  
### Dataset 2
<table>
  <tr>
    <th colspan="3"><CENTER>Attribute</th>
    <th colspan="2"><CENTER>Random Forest</th>
    <th colspan="2"><CENTER>DNN</th>
  </tr>
  <tr>
    <th>feature 1</th>
    <th>feature 2</th>
    <th>RWR</th>
    <th><CENTER>AUC</th><th><CENTER>AP</th>
    <th><CENTER>AUC</th> <th><CENTER>AP</th>
  </tr>
  <tr>
    <td><CENTER> V <td>  <td>  <td> .659 <td> .775 <td> .669<td> .774
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td>  <td> .654 <td> .772<td> .668 <td>  .773
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td><CENTER> V  <td> .655 <td> .773 <td> .656 <td>  .768
  </tr>
  
 </table>

### Dataset 3
<table>
  <tr>
    <th colspan="3"><CENTER>Attribute</th>
    <th colspan="2"><CENTER>Random Forest</th>
    <th colspan="2"><CENTER>DNN</th>
  </tr>
  <tr>
    <th>feature 1</th>
    <th>feature 2</th>
    <th>RWR</th>
    <th><CENTER>AUC</th><th><CENTER>AP</th>
    <th><CENTER>AUC</th> <th><CENTER>AP</th>
  </tr>
  <tr>
    <td><CENTER> V <td>  <td>  <td> .812 <td> .865 <td> .759 <td> .843
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td>  <td> .812 <td> .864 <td> .738 <td>  .834
  </tr>
  <tr>
    <td><CENTER> V <td><CENTER> V <td><CENTER> V  <td> .833<td> .871 <td> .772 <td>  .843
  </tr>
  
 </table>

 ### Result
 - only use feature 1
 <table>
  <tr>
    <td>
    <th colspan="2"><CENTER>Dataset 1</th>
    <th colspan="2"><CENTER>Dataset 2</th>
    <th colspan="2"><CENTER>Dataset 3</th>
  </tr>
  <tr>
    <th><CENTER>Model</th>
    <th><CENTER>AUC</th><th><CENTER>AP</th>
    <th><CENTER>AUC</th> <th><CENTER>AP</th>
    <th><CENTER>AUC</th> <th><CENTER>AP</th>
  </tr>
  <tr>
    <td> Random Forest (RF) <td> .700 <td> .783 <td> .659 <td> .775 <td> .812 <td> .865
  </tr>
  <tr>
    <td> DNN <td> .683 <td> .771 <td> .669 <td> .774 <td> .759 <td> .843
  </tr><tr>
    <td> GCN + Encoder <td> .816 <td> .831 <td> .885 <td> .881 <td> .600 <td> .580
  </tr><tr>
    <td> GCN + Encoder + RF <td> .852 <td> .878 <td> .898 <td> .915 <td> .833 <td> .889
  </tr><tr>
    <td> GCN + Encoder + DNN <td> <b>.864</b> <td> <b>.898  <td> <b>.910</b> <td> <b>.921 <td> <b>.861</b> <td> <b>.910</b>
  </tr>
  
 </table>