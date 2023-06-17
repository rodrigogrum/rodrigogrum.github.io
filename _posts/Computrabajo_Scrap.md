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
      <th>region</th>
      <th>estado</th>
      <th>poblacion proyectada 2023</th>
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
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-94c045ba-7e98-4c3c-9665-071988e9c1eb')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-94c045ba-7e98-4c3c-9665-071988e9c1eb button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-94c045ba-7e98-4c3c-9665-071988e9c1eb');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




#### Web scraping

The scraped data is the number of job openings each states has for each category:
![scrapnum.png](data:image/png;base64,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)

Scraped data table:

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>estado</th>
      <th>categoria</th>
      <th>num_trabajos</th>
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


```python
# Replace None values
df_clean = df.fillna(0)

# Replace -
df_clean.replace('-',' ', regex=True, inplace=True)

# Convert data into INT
df_clean['num_trabajos'].replace(',','', regex=True, inplace=True)
df_clean = df_clean.astype({'num_trabajos': 'int'})
df_clean['estado'] = df_clean['estado'].str.capitalize()
df_clean['categoria'] = df_clean['categoria'].str.capitalize()
df_clean
```





  <div id="df-d897a90c-1292-472a-8959-f663785541e0">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>estado</th>
      <th>categoria</th>
      <th>num_trabajos</th>
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
<p>528 rows × 3 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d897a90c-1292-472a-8959-f663785541e0')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d897a90c-1292-472a-8959-f663785541e0 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d897a90c-1292-472a-8959-f663785541e0');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




#### Analysis

First, two new dataframes are created:

* To summarize the number of job openings per state.
* Another to summarize the number of job openings per category.


```python
res_estado = df_clean.groupby('estado').sum()
res_estado
```

    <ipython-input-6-4fc5d0341bb1>:1: FutureWarning: The default value of numeric_only in DataFrameGroupBy.sum is deprecated. In a future version, numeric_only will default to False. Either specify numeric_only or select only columns which should be valid for the function.
      res_estado = df_clean.groupby('estado').sum()






  <div id="df-1cfc671c-a0b2-4d9c-8313-6a45dc84645f">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>num_trabajos</th>
    </tr>
    <tr>
      <th>estado</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Amazonas</th>
      <td>762</td>
    </tr>
    <tr>
      <th>Anzoategui</th>
      <td>1529</td>
    </tr>
    <tr>
      <th>Apure</th>
      <td>775</td>
    </tr>
    <tr>
      <th>Aragua</th>
      <td>2754</td>
    </tr>
    <tr>
      <th>Barinas</th>
      <td>884</td>
    </tr>
    <tr>
      <th>Bolivar</th>
      <td>1080</td>
    </tr>
    <tr>
      <th>Carabobo</th>
      <td>3344</td>
    </tr>
    <tr>
      <th>Cojedes</th>
      <td>784</td>
    </tr>
    <tr>
      <th>Delta amacuro</th>
      <td>760</td>
    </tr>
    <tr>
      <th>Distrito capital</th>
      <td>7077</td>
    </tr>
    <tr>
      <th>Falcon</th>
      <td>882</td>
    </tr>
    <tr>
      <th>Guarico</th>
      <td>816</td>
    </tr>
    <tr>
      <th>Lara</th>
      <td>2458</td>
    </tr>
    <tr>
      <th>Merida</th>
      <td>917</td>
    </tr>
    <tr>
      <th>Miranda</th>
      <td>2660</td>
    </tr>
    <tr>
      <th>Monagas</th>
      <td>982</td>
    </tr>
    <tr>
      <th>Nueva esparta</th>
      <td>1019</td>
    </tr>
    <tr>
      <th>Portuguesa</th>
      <td>938</td>
    </tr>
    <tr>
      <th>Sucre</th>
      <td>807</td>
    </tr>
    <tr>
      <th>Tachira</th>
      <td>1281</td>
    </tr>
    <tr>
      <th>Trujillo</th>
      <td>809</td>
    </tr>
    <tr>
      <th>Vargas</th>
      <td>926</td>
    </tr>
    <tr>
      <th>Yaracuy</th>
      <td>818</td>
    </tr>
    <tr>
      <th>Zulia</th>
      <td>2759</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-1cfc671c-a0b2-4d9c-8313-6a45dc84645f')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-1cfc671c-a0b2-4d9c-8313-6a45dc84645f button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-1cfc671c-a0b2-4d9c-8313-6a45dc84645f');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
res_categoria = df_clean.groupby('categoria').sum()
res_categoria
```

    <ipython-input-7-63f907244608>:1: FutureWarning: The default value of numeric_only in DataFrameGroupBy.sum is deprecated. In a future version, numeric_only will default to False. Either specify numeric_only or select only columns which should be valid for the function.
      res_categoria = df_clean.groupby('categoria').sum()






  <div id="df-908261c8-482b-46a0-b70f-d63dc40aac25">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>num_trabajos</th>
    </tr>
    <tr>
      <th>categoria</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Administracion y oficina</th>
      <td>2456</td>
    </tr>
    <tr>
      <th>Almacen logistica</th>
      <td>1264</td>
    </tr>
    <tr>
      <th>Arte y diseno y medios</th>
      <td>1103</td>
    </tr>
    <tr>
      <th>Atencion a clientes</th>
      <td>4654</td>
    </tr>
    <tr>
      <th>Callcenter telemercadeo</th>
      <td>2296</td>
    </tr>
    <tr>
      <th>Cientifico y investigacion</th>
      <td>72</td>
    </tr>
    <tr>
      <th>Compras comercio exterior</th>
      <td>241</td>
    </tr>
    <tr>
      <th>Construccion y obra</th>
      <td>215</td>
    </tr>
    <tr>
      <th>Direccion y gerencia</th>
      <td>386</td>
    </tr>
    <tr>
      <th>Economia y contabilidad</th>
      <td>857</td>
    </tr>
    <tr>
      <th>Educacion y universidad</th>
      <td>891</td>
    </tr>
    <tr>
      <th>Hosteleria y turismo</th>
      <td>479</td>
    </tr>
    <tr>
      <th>Ingenieria y tecnico</th>
      <td>925</td>
    </tr>
    <tr>
      <th>Legal y asesoria</th>
      <td>96</td>
    </tr>
    <tr>
      <th>Mantenimiento y reparaciones tecnicas</th>
      <td>569</td>
    </tr>
    <tr>
      <th>Medicina y salud</th>
      <td>903</td>
    </tr>
    <tr>
      <th>Mercadeo publicidad comunicacion</th>
      <td>2319</td>
    </tr>
    <tr>
      <th>Otros</th>
      <td>1241</td>
    </tr>
    <tr>
      <th>Produccion operaciones</th>
      <td>545</td>
    </tr>
    <tr>
      <th>Recursos humanos</th>
      <td>630</td>
    </tr>
    <tr>
      <th>Servicios generales aseo y seguridad</th>
      <td>820</td>
    </tr>
    <tr>
      <th>Ventas</th>
      <td>14859</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-908261c8-482b-46a0-b70f-d63dc40aac25')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-908261c8-482b-46a0-b70f-d63dc40aac25 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-908261c8-482b-46a0-b70f-d63dc40aac25');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




For the relationship analysis, a new data frame is created by merging the job openings per state and the population per state data frames.


```python
merged = poblacion.merge(res_estado, left_on='estado', right_on='estado')
merged
```





  <div id="df-05e2f5a8-cca1-44e5-9ee6-67bd504ac247">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>region</th>
      <th>estado</th>
      <th>poblacion proyectada 2023</th>
      <th>num_trabajos</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Centro</td>
      <td>Distrito capital</td>
      <td>2095180</td>
      <td>7077</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Guayana</td>
      <td>Amazonas</td>
      <td>218438</td>
      <td>762</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Oriente</td>
      <td>Anzoategui</td>
      <td>1847222</td>
      <td>1529</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Llanos</td>
      <td>Apure</td>
      <td>667147</td>
      <td>775</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Occidente</td>
      <td>Aragua</td>
      <td>1929193</td>
      <td>2754</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Llanos</td>
      <td>Barinas</td>
      <td>1007338</td>
      <td>884</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Guayana</td>
      <td>Bolivar</td>
      <td>1974310</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Centro</td>
      <td>Carabobo</td>
      <td>2631056</td>
      <td>3344</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Occidente</td>
      <td>Cojedes</td>
      <td>394123</td>
      <td>784</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Oriente</td>
      <td>Delta amacuro</td>
      <td>224606</td>
      <td>760</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Occidente</td>
      <td>Falcon</td>
      <td>1138128</td>
      <td>882</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Llanos</td>
      <td>Guarico</td>
      <td>1012246</td>
      <td>816</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Occidente</td>
      <td>Lara</td>
      <td>2123678</td>
      <td>2458</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Andes</td>
      <td>Merida</td>
      <td>1109960</td>
      <td>917</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Centro</td>
      <td>Miranda</td>
      <td>3407812</td>
      <td>2660</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Oriente</td>
      <td>Monagas</td>
      <td>1064116</td>
      <td>982</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Oriente</td>
      <td>Nueva esparta</td>
      <td>682671</td>
      <td>1019</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Occidente</td>
      <td>Portuguesa</td>
      <td>1115993</td>
      <td>938</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Oriente</td>
      <td>Sucre</td>
      <td>1153495</td>
      <td>807</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Andes</td>
      <td>Tachira</td>
      <td>1303637</td>
      <td>1281</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Andes</td>
      <td>Trujillo</td>
      <td>918973</td>
      <td>809</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Centro</td>
      <td>Vargas</td>
      <td>391549</td>
      <td>926</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Occidente</td>
      <td>Yaracuy</td>
      <td>788933</td>
      <td>818</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Zulia</td>
      <td>Zulia</td>
      <td>4526397</td>
      <td>2759</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-05e2f5a8-cca1-44e5-9ee6-67bd504ac247')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-05e2f5a8-cca1-44e5-9ee6-67bd504ac247 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-05e2f5a8-cca1-44e5-9ee6-67bd504ac247');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>




##### Charts


```python
res_region = merged[['region', 'num_trabajos']].groupby('region').sum()
res_region.sort_values('num_trabajos').plot.barh(
    title='Number of jobs per region',
    ylabel='Region',
    xlabel='Number of jobs',
    legend=False
)
plt.show()
```


    
![png](Computrabajo_Scrap%20%281%29_files/Computrabajo_Scrap%20%281%29_18_0.png)
    



```python

res_estado.sort_values(by=['num_trabajos']).plot.barh(
    title='Number of jobs per state',
    ylabel='State',
    xlabel='Number of jobs',
    legend=False)
plt.show()

```


    
![png](Computrabajo_Scrap%20%281%29_files/Computrabajo_Scrap%20%281%29_19_0.png)
    



```python
res_categoria.sort_values(by=['num_trabajos']).plot.barh(
    title='Number of jobs per category',
    ylabel='Category',
    xlabel='Number of jobs',
    legend=False)
plt.show()
```


    
![png](Computrabajo_Scrap%20%281%29_files/Computrabajo_Scrap%20%281%29_20_0.png)
    


The bar chart above clearly shows that the vast majority of job openings in Computrabajo are sales related (ventas), being a percentage of the total:


```python
num_sales_jobs = res_categoria.at['Ventas', 'num_trabajos']
num_total_jobs = res_categoria['num_trabajos'].sum()
print(f"Percentage of sales jobs: {round((num_sales_jobs/num_total_jobs)*100, 2)}%")

```

    Percentage of sales jobs: 39.29%



```python
merged.plot.scatter(x='poblacion proyectada 2023',
                    y='num_trabajos',
                    xlabel='2023 estimated population (millions)',
                    ylabel='Number of jobs',
                    title='Relationship population - number of jobs',
                    xticks=range(0,5000000,500000)
                  )
# Regression line
m,b = np.polyfit(merged['poblacion proyectada 2023'], merged['num_trabajos'], 1)

# Correlation
r = np.corrcoef(merged['poblacion proyectada 2023'], merged['num_trabajos'])[0,1]
plt.annotate('r = {:.2f}'.format(r), xy=(0.7, 0.9), xycoords='axes fraction')

plt.plot(merged['poblacion proyectada 2023'], m*merged['poblacion proyectada 2023']+b, color='yellow')
plt.show()
```


    
![png](Computrabajo_Scrap%20%281%29_files/Computrabajo_Scrap%20%281%29_23_0.png)
    


We can see above that there is a slight correlation between the states population and the number of jobs openings, specially in the states with lower population

Now, if we exclude those extreme values (from distrito capital) the results are like:


```python
without_extremes = merged[merged['estado'] != 'Distrito capital']

without_extremes.plot.scatter(x='poblacion proyectada 2023',
                    y='num_trabajos',
                    xlabel='2023 estimated population (millions)',
                    ylabel='Number of jobs',
                    title='Relationship population - number of jobs',
                    xticks=range(0,5000000,500000)
                  )
# Regression line
m,b = np.polyfit(without_extremes['poblacion proyectada 2023'],
                 without_extremes['num_trabajos'], 1)

# Correlation
r = np.corrcoef(without_extremes['poblacion proyectada 2023'],
                without_extremes['num_trabajos'])[0,1]

plt.annotate('r = {:.2f}'.format(r), xy=(0.7, 0.9), xycoords='axes fraction')

plt.plot(without_extremes['poblacion proyectada 2023'],
         m*without_extremes['poblacion proyectada 2023']+b,
         color='yellow')
plt.show()
```


    
![png](Computrabajo_Scrap%20%281%29_files/Computrabajo_Scrap%20%281%29_26_0.png)
    

