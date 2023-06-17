---
layout: post
title: Jobs availables in Venezuela (Computrabajo)
tags: [Project]
author: Rodrigo Guevara
comments : False
---

# Jobs availables in Venezuela

The project was made mainly with the intention to learn two things:

1. Web scraping
2. Simple data analysis and visualization with pandas and matplotlib

As this is a pretty basic and simple project, due to my inexperience with the tools and techniques, so there may be optimizations and improvements to be made.

There are three goals to achieve:

1. Know what states in Venezuela has the most job openings.
2. Know what job categories has the most job openings.
3. Know if there is a relationship between the number of jobs offerings in a state and their population.

The data for the project was gathered via web scraping from the web site Computrabajo, and the population data from Instituto Nacional de Estadistica de Venezuela (Venezuelan National Statistics Institute).

Population data:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Region</th>
      <th>State</th>
      <th>2023 population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Centro</td>
      <td>Distrito capital</td>
      <td>2095180</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Guayana</td>
      <td>Amazonas</td>
      <td>218438</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Oriente</td>
      <td>Anzoategui</td>
      <td>1847222</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Llanos</td>
      <td>Apure</td>
      <td>667147</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Occidente</td>
      <td>Aragua</td>
      <td>1929193</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Llanos</td>
      <td>Barinas</td>
      <td>1007338</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Guayana</td>
      <td>Bolivar</td>
      <td>1974310</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Centro</td>
      <td>Carabobo</td>
      <td>2631056</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Occidente</td>
      <td>Cojedes</td>
      <td>394123</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Oriente</td>
      <td>Delta amacuro</td>
      <td>224606</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Occidente</td>
      <td>Falcon</td>
      <td>1138128</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Llanos</td>
      <td>Guarico</td>
      <td>1012246</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Occidente</td>
      <td>Lara</td>
      <td>2123678</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Andes</td>
      <td>Merida</td>
      <td>1109960</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Centro</td>
      <td>Miranda</td>
      <td>3407812</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Oriente</td>
      <td>Monagas</td>
      <td>1064116</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Oriente</td>
      <td>Nueva esparta</td>
      <td>682671</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Occidente</td>
      <td>Portuguesa</td>
      <td>1115993</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Oriente</td>
      <td>Sucre</td>
      <td>1153495</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Andes</td>
      <td>Tachira</td>
      <td>1303637</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Andes</td>
      <td>Trujillo</td>
      <td>918973</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Centro</td>
      <td>Vargas</td>
      <td>391549</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Occidente</td>
      <td>Yaracuy</td>
      <td>788933</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Zulia</td>
      <td>Zulia</td>
      <td>4526397</td>
    </tr>
  </tbody>
</table>

#### Web scraping

The scraped data is the number of job openings each states has for each category:

![img]({{ site.baseurl }}/assets/img/jobs ct/scrapnum.png)


Scraped data table:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Category</th>
      <th>Number of jobs</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>aragua</td>
      <td>ventas</td>
      <td>1,030</td>
    </tr>
    <tr>
      <th>1</th>
      <td>aragua</td>
      <td>atencion-a-clientes</td>
      <td>189</td>
    </tr>
    <tr>
      <th>2</th>
      <td>aragua</td>
      <td>administracion-y-oficina</td>
      <td>238</td>
    </tr>
    <tr>
      <th>3</th>
      <td>aragua</td>
      <td>almacen-logistica</td>
      <td>159</td>
    </tr>
    <tr>
      <th>4</th>
      <td>aragua</td>
      <td>otros</td>
      <td>115</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>523</th>
      <td>amazonas</td>
      <td>educacion-y-universidad</td>
      <td>32</td>
    </tr>
    <tr>
      <th>524</th>
      <td>amazonas</td>
      <td>construccion-y-obra</td>
      <td>3</td>
    </tr>
    <tr>
      <th>525</th>
      <td>amazonas</td>
      <td>direccion-y-gerencia</td>
      <td>12</td>
    </tr>
    <tr>
      <th>526</th>
      <td>amazonas</td>
      <td>cientifico-y-investigacion</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>527</th>
      <td>amazonas</td>
      <td>legal-y-asesoria</td>
      <td>1</td>
    </tr>
  </tbody>
</table>

Most of the data is pretty simple, the cleaning is just:
* Replace all the None values to zero (0).
* Replacing all the '-' to blank spaces for better readability.
* Convert the 'num_trabajos' columns from string to int.
* Capitalize the data

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>State</th>
      <th>Category</th>
      <th>Number of jobs</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aragua</td>
      <td>Ventas</td>
      <td>1030</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Aragua</td>
      <td>Atencion a clientes</td>
      <td>189</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Aragua</td>
      <td>Administracion y oficina</td>
      <td>238</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Aragua</td>
      <td>Almacen logistica</td>
      <td>159</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Aragua</td>
      <td>Otros</td>
      <td>115</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>523</th>
      <td>Amazonas</td>
      <td>Educacion y universidad</td>
      <td>32</td>
    </tr>
    <tr>
      <th>524</th>
      <td>Amazonas</td>
      <td>Construccion y obra</td>
      <td>3</td>
    </tr>
    <tr>
      <th>525</th>
      <td>Amazonas</td>
      <td>Direccion y gerencia</td>
      <td>12</td>
    </tr>
    <tr>
      <th>526</th>
      <td>Amazonas</td>
      <td>Cientifico y investigacion</td>
      <td>0</td>
    </tr>
    <tr>
      <th>527</th>
      <td>Amazonas</td>
      <td>Legal y asesoria</td>
      <td>1</td>
    </tr>
  </tbody>
</table>

#### Analysis

![img]({{ site.baseurl }}/assets/img/jobs ct/per region.png)

Most of the job openings are concentrated in the center region (centro) and western region (occidente), which are the regions where most of the companies are concentrated in the country, specially in the industrial and manufacturing industry. 

    
![img]({{ site.baseurl }}/assets/img/jobs ct/Per state.png)
    
When we analyze by states, most of the jobs come from Distrito capital and Carabobo from the center region, followed by Zulia which is the state with the biggest population in the country.

![img]({{ site.baseurl }}/assets/img/jobs ct/per category.png)
    


The bar chart above clearly shows that the vast majority of job openings in Computrabajo are sales related (ventas), being a 39.29% percentage of the total job openings.

##### Correlation between number of job openings and population

  
![img]({{ site.baseurl }}/assets/img/jobs ct/full corr.png)    


We can see above that there is a slight correlation between the states population and the number of jobs openings, specially in the states with lower population. 
As Distrito capital is where most of the companies exists in the country, it makes sense that this state has a big number of job openings despite its population. 
Now, if we exclude those extreme values (from distrito capital) the results are like:

 
![img]({{ site.baseurl }}/assets/img/jobs ct/better corr.png)    

Without the values from distrito capital, it clearly shows that there is a high correlation between the states population and the number of job openings (0.83).
