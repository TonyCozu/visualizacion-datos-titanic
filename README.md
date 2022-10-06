# visualizacion-datos-titanic
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "cb472bfd",
   "metadata": {},
   "source": [
    "# Visualización de datos del titanic"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "fc9c2f24",
   "metadata": {},
   "source": [
    "### Acerca del titanic"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "3afc9d42",
   "metadata": {},
   "source": [
    "Fue un barco de pasajeros británico que sarpó en abril 10 de 1912, el cuál nunca arrivó con éxito su destino, para mayor información visitar este [link](https://en.wikipedia.org/wiki/Titanic)\n",
    "\n",
    "Una imagen del barco es:\n",
    "\n",
    "![imagen](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fd/RMS_Titanic_3.jpg/1280px-RMS_Titanic_3.jpg)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "95bae8bf",
   "metadata": {},
   "source": [
    "### Análisis de datos"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "93d324d4",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C85</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>C123</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Cabin Embarked  \n",
       "0      0         A/5 21171   7.2500   NaN        S  \n",
       "1      0          PC 17599  71.2833   C85        C  \n",
       "2      0  STON/O2. 3101282   7.9250   NaN        S  \n",
       "3      0            113803  53.1000  C123        S  \n",
       "4      0            373450   8.0500   NaN        S  "
      ]
     },
     "execution_count": 1,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "\n",
    "# Carga de los datos de entrenamiento en un data frame de pandas\n",
    "\n",
    "datos_entrenamiento = pd.read_csv(\"https://raw.githubusercontent.com/gf0657-programacionsig/2022-ii/main/contenido/3/datos/kaggle/titanic/pasajeros-titanic-entrenamiento.csv\")\n",
    "\n",
    "# Despliegue de las primeras filas\n",
    "\n",
    "datos_entrenamiento.head()\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "270513f2",
   "metadata": {},
   "source": [
    "### También podemos hacer la carga de los datos conociendo la ruta relativa de los datos"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "8b44c161",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>PassengerId</th>\n",
       "      <th>Survived</th>\n",
       "      <th>Pclass</th>\n",
       "      <th>Name</th>\n",
       "      <th>Sex</th>\n",
       "      <th>Age</th>\n",
       "      <th>SibSp</th>\n",
       "      <th>Parch</th>\n",
       "      <th>Ticket</th>\n",
       "      <th>Fare</th>\n",
       "      <th>Cabin</th>\n",
       "      <th>Embarked</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Braund, Mr. Owen Harris</td>\n",
       "      <td>male</td>\n",
       "      <td>22.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>A/5 21171</td>\n",
       "      <td>7.2500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Cumings, Mrs. John Bradley (Florence Briggs Th...</td>\n",
       "      <td>female</td>\n",
       "      <td>38.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>PC 17599</td>\n",
       "      <td>71.2833</td>\n",
       "      <td>C85</td>\n",
       "      <td>C</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>1</td>\n",
       "      <td>3</td>\n",
       "      <td>Heikkinen, Miss. Laina</td>\n",
       "      <td>female</td>\n",
       "      <td>26.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>STON/O2. 3101282</td>\n",
       "      <td>7.9250</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>1</td>\n",
       "      <td>1</td>\n",
       "      <td>Futrelle, Mrs. Jacques Heath (Lily May Peel)</td>\n",
       "      <td>female</td>\n",
       "      <td>35.0</td>\n",
       "      <td>1</td>\n",
       "      <td>0</td>\n",
       "      <td>113803</td>\n",
       "      <td>53.1000</td>\n",
       "      <td>C123</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>0</td>\n",
       "      <td>3</td>\n",
       "      <td>Allen, Mr. William Henry</td>\n",
       "      <td>male</td>\n",
       "      <td>35.0</td>\n",
       "      <td>0</td>\n",
       "      <td>0</td>\n",
       "      <td>373450</td>\n",
       "      <td>8.0500</td>\n",
       "      <td>NaN</td>\n",
       "      <td>S</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   PassengerId  Survived  Pclass  \\\n",
       "0            1         0       3   \n",
       "1            2         1       1   \n",
       "2            3         1       3   \n",
       "3            4         1       1   \n",
       "4            5         0       3   \n",
       "\n",
       "                                                Name     Sex   Age  SibSp  \\\n",
       "0                            Braund, Mr. Owen Harris    male  22.0      1   \n",
       "1  Cumings, Mrs. John Bradley (Florence Briggs Th...  female  38.0      1   \n",
       "2                             Heikkinen, Miss. Laina  female  26.0      0   \n",
       "3       Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1   \n",
       "4                           Allen, Mr. William Henry    male  35.0      0   \n",
       "\n",
       "   Parch            Ticket     Fare Cabin Embarked  \n",
       "0      0         A/5 21171   7.2500   NaN        S  \n",
       "1      0          PC 17599  71.2833   C85        C  \n",
       "2      0  STON/O2. 3101282   7.9250   NaN        S  \n",
       "3      0            113803  53.1000  C123        S  \n",
       "4      0            373450   8.0500   NaN        S  "
      ]
     },
     "execution_count": 3,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "\n",
    "# Carga de los datos de entrenamiento en un data frame de pandas\n",
    "\n",
    "datos_entrenamiento = pd.read_csv(\"pasajeros-titanic-entrenamiento.csv\")\n",
    "\n",
    "datos_entrenamiento.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4e75bc1c",
   "metadata": {},
   "source": [
    "### Distribución de pasajeros por sexo"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "990c785c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:>"
      ]
     },
     "execution_count": 10,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": "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AACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWlPH0AG5UUWM/l5ezrKeHAZQ6+/x6enoIN6b4TE+PALgucMQKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsIKAADAEsKqGObPn68FCxZ4ehgAAKCUKPGwio+PV0xMTEm/rSRp1qxZCg0NveLtV61aJYfDoZMnT+Zbl5ycrGeeeUYtWrSwN0AAAHBNK3RYZWRk6KmnnlL16tXldDoVFham9u3ba926dVdjfFZ169ZNO3fuvOLtW7ZsqcOHDyskJMRt+fHjx/XUU0/pP//5j6pWrWp7mAAA4BpVprAveOihh3Tu3DnNnj1bNWvW1NGjR7V8+XKdOHHiaoxPkpSbmytfX99i78ff31/+/v5XvL2vr6/CwsLyLa9YsaK2bdtW7PEAAIDrS6GOWJ08eVLJycmaMGGC2rZtq5tvvlm33367Ro0apfvvv1+SlJ6erk6dOikwMFDBwcHq2rWrjh49mm9f06ZNU0REhMqWLatHHnnE7XRbnz591LlzZyUkJCg8PFx169aVJH3//ffq1q2bypUrpwoVKqhTp07at2+fJOnzzz+Xn59fvtN2Q4YMUVxcnCT3U4E7duyQw+HQ//73P7ftJ02apBo1asgYU+CpwAULFujWW2+V0+lUjRo1NHHixMJMIQAAuI4VKqwCAwMVGBiohQsXKicnJ996Y4w6d+6sEydOKCkpScuWLVNaWpq6devmtt3u3bs1b948ffLJJ1qyZIlSUlI0cOBAt22WL1+u7du3a9myZfr000915swZtW3bVoGBgVq9erWSk5MVGBioe++9V7m5uWrXrp1CQ0PdLia/cOGC5s2bp169euUba7169dS0aVPNmTPHbfncuXPVs2dPORyOfK/ZuHGjunbtqu7du2vr1q2Kj4/XmDFjNGvWrEvOWU5OjrKystweAADg+lSosCpTpoxmzZql2bNnKzQ0VK1atdLo0aO1ZcsWSdIXX3yhLVu2aO7cuWratKmaN2+u999/X0lJSdqwYYNrP9nZ2Zo9e7ZiYmLUunVrvf7660pMTNSRI0dc2wQEBGjGjBm69dZbFRUVpcTERHl5eWnGjBmKjo5W/fr1NXPmTKWnp2vVqlXy9vZWt27dNHfuXNc+li9frh9//FGPPPJIgZ+nV69ebtvv3LlTGzdu1KOPPlrg9pMmTdJdd92lMWPGqG7duurTp48GDRqkV1555ZJzlpCQoJCQENcjIiLiyiYbAABccwp98fpDDz2kQ4cOadGiRWrfvr1WrVqlJk2aaNasWdq+fbsiIiLc4qFBgwYKDQ3V9u3bXcuqV6+uatWquZ7HxsYqLy9PO3bscC2Ljo52u65q48aN2r17t4KCglxHzsqXL6/s7GylpaVJ+jmUVq1apUOHDkmS5syZow4dOqhcuXIFfpbu3btr//79+uqrr1zbx8TEqEGDBgVuv337drVq1cptWatWrbRr1y5duHChwNeMGjVKmZmZrseBAwcK3A4AAFz7inS7BT8/P9199916/vnntXbtWvXp00djx46VMabAU2iXWn7RxXW/3CYgIMBtm7y8PDVt2lQpKSluj507d6pnz56SpNtvv121atVSYmKizp49q48//viSR58kqUqVKmrbtq3rqNW///3vy25f0Ocwxlxye0lyOp0KDg52ewAAgOuTlftYNWjQQKdPn1aDBg2Unp7udlQmNTVVmZmZql+/vmtZenq666iSJK1bt05eXl6ui9QL0qRJE+3atUuVKlVS7dq13R6/vB1Cz549NWfOHH3yySfy8vJyXVR/Kb169dIHH3ygdevWKS0tTd27d7/s50xOTnZbtnbtWtWtW1fe3t6XfR8AAHD9K1RY/fDDD7rzzjv1r3/9S1u2bNHevXv14Ycf6uWXX1anTp3Url07NWzYUL169dKmTZu0fv16/eEPf1BcXJyaNWvm2o+fn5969+6tb7/9VmvWrNGQIUPUtWvXAm9tcFGvXr1UsWJFderUSWvWrNHevXuVlJSkoUOH6uDBg27bbdq0SX//+9/18MMPy8/P77KfqUuXLsrKylL//v3Vtm3by96XasSIEVq+fLnGjRunnTt3avbs2ZoyZYpGjhxZiFkEAADXq0J/K7B58+b65z//qdatWysqKkpjxozRk08+qSlTpsjhcGjhwoUqV66cWrdurXbt2qlmzZr64IMP3PZTu3ZtdenSRR06dNA999yjqKgovfnmm5d977Jly2r16tWqXr26unTpovr16+vxxx/X2bNn3U6v1alTR7fddpu2bNlS4LcBfy04OFgdO3bUt99++5vbN2nSRPPmzVNiYqKioqL0/PPP64UXXlCfPn1+830AAMD1z2F+6yIhWJWVlfXztwOfnicvZ1lPDwcodfb59fT0EG5M8ZmeHgFQql38+Z2ZmXnZ66X5JcwAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWEFYAAACWlPH0AAAAwM/y8vKUm5vr6WHckHx8fOTt7V3s/RBWAACUArm5udq7d6/y8vI8PZQbVmhoqMLCwuRwOIq8D8IKAAAPM8bo8OHD8vb2VkREhLy8uFKnJBljdObMGWVkZEiSqlSpUuR9EVYAAHjY+fPndebMGYWHh6ts2bKeHs4Nyd/fX5KUkZGhSpUqFfm0IEkMAICHXbhwQZLk6+vr4ZHc2C5G7blz54q8D8IKAIBSojjX9qD4bMw/YQUAAGAJYQUAAIrEGKM//elPKl++vBwOh1JSUjwyjn379nn0/X+Ji9c95Lu/tVdwcLCnhwGUQpmeHgBQatT4y+ISfb994+8v1PZLlizRrFmztGrVKtWsWVMVK1a8SiO7dhBWAACgSNLS0lSlShW1bNnS00MpNTgVCAAACq1Pnz4aPHiw0tPT5XA4VKNGDRlj9PLLL6tmzZry9/dXo0aNNH/+fNdrVq1aJYfDoc8//1yNGzeWv7+/7rzzTmVkZOizzz5T/fr1FRwcrB49eujMmTOu1y1ZskR33HGHQkNDVaFCBT3wwANKS0u77PhSU1PVoUMHBQYGqnLlynrsscd0/PjxqzYfFxFWAACg0CZPnqwXXnhB1apV0+HDh7VhwwY999xzmjlzpqZOnapt27Zp2LBhevTRR5WUlOT22vj4eE2ZMkVr167VgQMH1LVrV7366quaO3euFi9erGXLlun11193bX/69GkNHz5cGzZs0PLly+Xl5aXf//73l7xL/eHDhxUXF6eYmBh98803WrJkiY4ePaquXbte1TmROBUIAACKICQkREFBQfL29lZYWJhOnz6tSZMmacWKFYqNjZUk1axZU8nJyZo2bZri4uJcr33xxRfVqlUrSVLfvn01atQopaWlqWbNmpKkhx9+WCtXrtSzzz4rSXrooYfc3vudd95RpUqVlJqaqqioqHxjmzp1qpo0aaKXXnrJtezdd99VRESEdu7cqbp169qdjF8grAAAQLGlpqYqOztbd999t9vy3NxcNW7c2G1Zw4YNXX+uXLmyypYt64qqi8vWr1/vep6WlqYxY8boq6++0vHjx11HqtLT0wsMq40bN2rlypUKDAzMty4tLY2wAgAApdvF2Fm8eLGqVq3qts7pdLo99/Hxcf3Z4XC4Pb+47Jen+Tp27KiIiAhNnz5d4eHhysvLU1RUlHJzcy85lo4dO2rChAn51hXn9wBeCcIKAAAUW4MGDeR0OpWenu522q+4fvjhB23fvl3Tpk3T7373O0lScnLyZV/TpEkTLViwQDVq1FCZMiWbOly8DgAAii0oKEgjR47UsGHDNHv2bKWlpWnz5s164403NHv27CLvt1y5cqpQoYLefvtt7d69WytWrNDw4cMv+5qBAwfqxIkT6tGjh9avX689e/Zo6dKlevzxx12/l/Fq4YgVAACwYty4capUqZISEhK0Z88ehYaGqkmTJho9enSR9+nl5aXExEQNGTJEUVFRqlevnl577TW1adPmkq8JDw/Xl19+qWeffVbt27dXTk6Obr75Zt17773y8rq6x5QcxhhzVd8BbrKyshQSEqLMzEzuvA4AkCRlZ2dr7969ioyMlJ+fn6eHc8O63N/Dlf785lQgAACAJYQVAACAJYQVAACAJYQVAACAJYQVAACAJYQVAACAJYQVAACAJYQVAACAJYQVAACAJYQVAAAoNfr06aPOnTt7ehhFxu8KBACgtIoPKeH3yyzZ97sOccQKAADAEsIKAAAUSZs2bTR48GA9/fTTKleunCpXrqy3335bp0+f1h//+EcFBQWpVq1a+uyzzyRJFy5cUN++fRUZGSl/f3/Vq1dPkydPvux7GGP08ssvq2bNmvL391ejRo00f/78kvh4RUJYAQCAIps9e7YqVqyo9evXa/Dgwerfv78eeeQRtWzZUps2bVL79u312GOP6cyZM8rLy1O1atU0b948paam6vnnn9fo0aM1b968S+7/ueee08yZMzV16lRt27ZNw4YN06OPPqqkpKQS/JRXzmGMMZ4exI0kKytLISEhyszMVHBwsKeHAwAoBbKzs7V3715FRkbKz8/v/1aU8mus2rRpowsXLmjNmjWSfj4iFRISoi5duui9996TJB05ckRVqlTRunXr1KJFi3z7GDhwoI4ePeo6CtWnTx+dPHlSCxcu1OnTp1WxYkWtWLFCsbGxrtc88cQTOnPmjObOnVvUT1qgS/496Mp/fnPxOgAAKLKGDRu6/uzt7a0KFSooOjrataxy5cqSpIyMDEnSW2+9pRkzZmj//v06e/ascnNzFRMTU+C+U1NTlZ2drbvvvttteW5urho3bmz5k9hBWAEAgCLz8fFxe+5wONyWORwOSVJeXp7mzZunYcOGaeLEiYqNjVVQUJBeeeUVff311wXuOy8vT5K0ePFiVa1a1W2d0+m0+TGsIawAAECJWLNmjVq2bKkBAwa4lqWlpV1y+wYNGsjpdCo9PV1xcXElMcRiI6wAAECJqF27tt577z19/vnnioyM1Pvvv68NGzYoMjKywO2DgoI0cuRIDRs2THl5ebrjjjuUlZWltWvXKjAwUL179y7hT/DbCCsAAFAi+vXrp5SUFHXr1k0Oh0M9evTQgAEDXLdjKMi4ceNUqVIlJSQkaM+ePQoNDVWTJk00evToEhz5leNbgSWMbwUCAH7tct9GQ8mx8a1A7mMFAABgCWEFAABgCWEFAABgCWEFAABgCWEFAABgCWEFAEApwRf1Pevind6Lg/tYAQDgYT4+PnI4HDp27Jhuuukm16+BQckwxig3N1fHjh2Tl5eXfH19i7wvwgoAAA/z9vZWtWrVdPDgQe3bt8/Tw7lhlS1bVtWrV5eXV9FP6BFWAACUAoGBgapTp47OnTvn6aHckLy9vVWmTJliHy0krAAAKCW8vb3l7e3t6WGgGLh4HQAAwBLCCgAAwBLCCgAAwBKusSphF+9RkpWV5eGRAACAK3Xx5/Zv3WuMsCphP/zwgyQpIiLCwyMBAACFderUKYWEhFxyPWFVwsqXLy9JSk9Pv+xfDAonKytLEREROnDggIKDgz09nOsG83p1MK9XB/N6dTCvPzPG6NSpUwoPD7/sdoRVCbt407GQkJAb+h/o1RIcHMy8XgXM69XBvF4dzOvVwbzqig6IcPE6AACAJYQVAACAJYRVCXM6nRo7dqycTqenh3JdYV6vDub16mBerw7m9epgXgvHYX7re4MAAAC4IhyxAgAAsISwAgAAsISwAgAAsISwAgAAsISwKkFvvvmmIiMj5efnp6ZNm2rNmjWeHlKptnr1anXs2FHh4eFyOBxauHCh23pjjOLj4xUeHi5/f3+1adNG27Ztc9smJydHgwcPVsWKFRUQEKAHH3xQBw8eLMFPUbokJCTotttuU1BQkCpVqqTOnTtrx44dbtswr4U3depUNWzY0HUDxdjYWH322Weu9cypHQkJCXI4HHr66addy5jboomPj5fD4XB7hIWFudYzr8VgUCISExONj4+PmT59uklNTTVDhw41AQEBZv/+/Z4eWqn13//+1/z1r381CxYsMJLMxx9/7LZ+/PjxJigoyCxYsMBs3brVdOvWzVSpUsVkZWW5tunXr5+pWrWqWbZsmdm0aZNp27atadSokTl//nwJf5rSoX379mbmzJnmu+++MykpKeb+++831atXNz/99JNrG+a18BYtWmQWL15sduzYYXbs2GFGjx5tfHx8zHfffWeMYU5tWL9+valRo4Zp2LChGTp0qGs5c1s0Y8eONbfeeqs5fPiw65GRkeFaz7wWHWFVQm6//XbTr18/t2W33HKL+ctf/uKhEV1bfh1WeXl5JiwszIwfP961LDs724SEhJi33nrLGGPMyZMnjY+Pj0lMTHRt8/333xsvLy+zZMmSEht7aZaRkWEkmaSkJGMM82pTuXLlzIwZM5hTC06dOmXq1Kljli1bZuLi4lxhxdwW3dixY02jRo0KXMe8Fg+nAktAbm6uNm7cqHvuucdt+T333KO1a9d6aFTXtr179+rIkSNuc+p0OhUXF+ea040bN+rcuXNu24SHhysqKop5//8yMzMl/d8vB2dei+/ChQtKTEzU6dOnFRsby5xaMHDgQN1///1q166d23Lmtnh27dql8PBwRUZGqnv37tqzZ48k5rW4+CXMJeD48eO6cOGCKleu7La8cuXKOnLkiIdGdW27OG8Fzen+/ftd2/j6+qpcuXL5tmHef76GYvjw4brjjjsUFRUliXktjq1btyo2NlbZ2dkKDAzUxx9/rAYNGrh+yDCnRZOYmKhNmzZpw4YN+dbx77Xomjdvrvfee09169bV0aNH9eKLL6ply5batm0b81pMhFUJcjgcbs+NMfmWoXCKMqfM+88GDRqkLVu2KDk5Od865rXw6tWrp5SUFJ08eVILFixQ7969lZSU5FrPnBbegQMHNHToUC1dulR+fn6X3I65Lbz77rvP9efo6GjFxsaqVq1amj17tlq0aCGJeS0qTgWWgIoVK8rb2ztfxWdkZOT7PwJcmYvfXrncnIaFhSk3N1c//vjjJbe5UQ0ePFiLFi3SypUrVa1aNddy5rXofH19Vbt2bTVr1kwJCQlq1KiRJk+ezJwWw8aNG5WRkaGmTZuqTJkyKlOmjJKSkvTaa6+pTJkyrrlhbosvICBA0dHR2rVrF/9mi4mwKgG+vr5q2rSpli1b5rZ82bJlatmypYdGdW2LjIxUWFiY25zm5uYqKSnJNadNmzaVj4+P2zaHDx/Wd999d8POuzFGgwYN0kcffaQVK1YoMjLSbT3zao8xRjk5OcxpMdx1113aunWrUlJSXI9mzZqpV69eSklJUc2aNZlbS3JycrR9+3ZVqVKFf7PF5Ykr5m9EF2+38M4775jU1FTz9NNPm4CAALNv3z5PD63UOnXqlNm8ebPZvHmzkWQmTZpkNm/e7LpFxfjx401ISIj56KOPzNatW02PHj0K/DpwtWrVzBdffGE2bdpk7rzzzhv668D9+/c3ISEhZtWqVW5fsz5z5oxrG+a18EaNGmVWr15t9u7da7Zs2WJGjx5tvLy8zNKlS40xzKlNv/xWoDHMbVGNGDHCrFq1yuzZs8d89dVX5oEHHjBBQUGun0nMa9ERViXojTfeMDfffLPx9fU1TZo0cX3FHQVbuXKlkZTv0bt3b2PMz18JHjt2rAkLCzNOp9O0bt3abN261W0fZ8+eNYMGDTLly5c3/v7+5oEHHjDp6eke+DSlQ0HzKcnMnDnTtQ3zWniPP/6467/tm266ydx1112uqDKGObXp12HF3BbNxftS+fj4mPDwcNOlSxezbds213rmtegcxhjjmWNlAAAA1xeusQIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALCEsAIAALDk/wHqa0c3/+FBUwAAAABJRU5ErkJggg==",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Gráfico de barras de cantidades de sobrevivientes y fallecidos por sexo\n",
    "\n",
    "sobrevivientes = datos_entrenamiento[datos_entrenamiento['Survived']==1]['Sex'].value_counts()\n",
    "fallecidos = datos_entrenamiento[datos_entrenamiento['Survived']==0]['Sex'].value_counts()\n",
    "\n",
    "df = pd.DataFrame([sobrevivientes, fallecidos])\n",
    "df.index = ['Sobrevivió', 'Falleció']\n",
    "df.plot(kind='barh', stacked='True')"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "81257f8d",
   "metadata": {},
   "source": [
    "### Distribución de pasajeros por clase"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "id": "2eefaf21",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:>"
      ]
     },
     "execution_count": 11,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": "iVBORw0KGgoAAAANSUhEUgAAAlYAAAGdCAYAAADQYj31AAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/NK7nSAAAACXBIWXMAAA9hAAAPYQGoP6dpAAAfVklEQVR4nO3dfZBV9X348c8usAss7AJRXJAloojhYRGFqEgGRI0GjYEhjRBpC5PUiUbUDCZttKOQ2ARsKq2JkTiaAm2h+IAYkrREQgUkSiMPKysQfELBAGKisIgCAuf3hz9us+FBF767F9bXa+bOeM8595zv/YLu23POvVuQZVkWAAAcs8J8DwAAoLEQVgAAiQgrAIBEhBUAQCLCCgAgEWEFAJCIsAIASERYAQAk0jTfA/i42b9/f2zatClat24dBQUF+R4OAPARZFkWO3bsiI4dO0Zh4eHPSwmrBrZp06aoqKjI9zAAgKOwcePG6NSp02HXC6sG1rp164j44A+mtLQ0z6MBAD6KmpqaqKioyP0cPxxh1cAOXP4rLS0VVgBwgvmw23jcvA4AkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACTSNN8D+LjqNf5XUVjcMt/DOC682vyafA8BIG8qu3TO9xAajerR1fkegjNWAACpCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirI5SlmUxefLkWL58eb6HAgAcJ07osJo2bVq0adMm93zChAnRp0+f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sAIASERYAQAkIqwAABIRVgAAiQgrAIBEhBUAQCLCCgAgkab5HsDHVa/xv4rC4pb5HgaJvNr8mnwPgUOo7NI530M4YVSPrs73EKBRcMYKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESE1TF49NFHY/bs2fkeBgBwnGjwsJowYUL06dOnoQ8bERHTpk2LNm3afOTtFy5cGAUFBbFt27aD1i1ZsiS+9a1vxQUXXJBugADACa3OYbV169b42te+Fp07d47i4uIoLy+Pyy+/PJ555pn6GF9SI0aMiBdeeOEjb3/hhRfG5s2bo6ysrNbyP/zhD/G1r30tfvazn8Wpp56aepgAwAmqaV1f8MUvfjHef//9mD59epx++unxxhtvxIIFC+Ktt96qj/FFRMSePXuiqKjomPfTokWLaNGixUfevqioKMrLyw9aftJJJ8Xq1auPeTwAQONSpzNW27ZtiyVLlsRdd90VgwcPjk9+8pNx3nnnxa233hpXXnllRERs2LAhhg4dGq1atYrS0tK4+uqr44033jhoX/fff39UVFREy5Yt40tf+lKty21jxoyJYcOGxcSJE6Njx47RrVu3iIj4/e9/HyNGjIi2bdvGJz7xiRg6dGi8+uqrERHxq1/9Kpo3b37QZbubbropBg0aFBG1LwWuW7cuCgoK4ne/+12t7SdPnhynnXZaZFl2yEuBs2fPjp49e0ZxcXGcdtppcffdd9dlCgGARqxOYdWqVato1apVPP7447F79+6D1mdZFsOGDYu33norFi1aFPPnz4+XX345RowYUWu7l156KR5++OH4+c9/HvPmzYuqqqq44YYbam2zYMGCWLt2bcyfPz9+8YtfxLvvvhuDBw+OVq1axeLFi2PJkiXRqlWr+NznPhd79uyJSy+9NNq0aVPrZvJ9+/bFww8/HKNGjTporGeddVb07ds3ZsyYUWv5zJkz45prromCgoKDXrN8+fK4+uqrY+TIkVFdXR0TJkyI22+/PaZNm3bYOdu9e3fU1NTUegAAjVOdwqpp06Yxbdq0mD59erRp0yYGDBgQt912W6xatSoiIn7961/HqlWrYubMmdG3b984//zz49///d9j0aJF8eyzz+b2s2vXrpg+fXr06dMnBg4cGD/60Y9i1qxZsWXLltw2JSUl8eCDD0bPnj2jV69eMWvWrCgsLIwHH3wwKisro3v37jF16tTYsGFDLFy4MJo0aRIjRoyImTNn5vaxYMGCePvtt+NLX/rSId/PqFGjam3/wgsvxPLly+Mv//IvD7n95MmT45JLLonbb789unXrFmPGjImxY8fGD37wg8PO2cSJE6OsrCz3qKio+GiTDQCccOp88/oXv/jF2LRpU8ydOzcuv/zyWLhwYZx77rkxbdq0WLt2bVRUVNSKhx49ekSbNm1i7dq1uWWdO3eOTp065Z73798/9u/fH+vWrcstq6ysrHVf1fLly+Oll16K1q1b586ctWvXLnbt2hUvv/xyRHwQSgsXLoxNmzZFRMSMGTPiiiuuiLZt2x7yvYwcOTJee+21WLp0aW77Pn36RI8ePQ65/dq1a2PAgAG1lg0YMCBefPHF2Ldv3yFfc+utt8b27dtzj40bNx5yOwDgxHdUX7fQvHnz+OxnPxt33HFHPP300zFmzJgYP358ZFl2yEtoh1t+wIF1f7pNSUlJrW32798fffv2jaqqqlqPF154Ia655pqIiDjvvPPijDPOiFmzZsV7770Xc+bMOezZp4iIDh06xODBg3Nnrf7zP//ziNsf6n1kWXbY7SMiiouLo7S0tNYDAGicknyPVY8ePWLnzp3Ro0eP2LBhQ62zMmvWrInt27dH9+7dc8s2bNiQO6sUEfHMM89EYWFh7ib1Qzn33HPjxRdfjPbt20fXrl1rPf706xCuueaamDFjRvz85z+PwsLC3E31hzNq1Kh46KGH4plnnomXX345Ro4cecT3uWTJklrLnn766ejWrVs0adLkiMcBABq/OoXVH//4x7j44ovjP/7jP2LVqlWxfv36eOSRR+If//EfY+jQoXHppZdG7969Y9SoUbFixYr47W9/G3/9138dgwYNin79+uX207x58xg9enQ899xz8dRTT8VNN90UV1999SG/2uCAUaNGxUknnRRDhw6Np556KtavXx+LFi2Km2++OV5//fVa261YsSK+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bcz7B/dQjBs3Lj7zmc9Er169IsK8Hovq6uro379/7Nq1K1q1ahVz5syJHj165H7ImNOjM2vWrFixYkU8++yzB63z9/XonX/++fFv//Zv0a1bt3jjjTfiH/7hH+LCCy+M1atXm9djJKwaUEFBQa3nWZYdtIy6OZo5Ne8fGDt2bKxatSqWLFly0DrzWndnnXVWVFVVxbZt22L27NkxevToWLRoUW69Oa27jRs3xs033xxPPPFENG/e/LDbmdu6GzJkSO6fKysro3///nHGGWfE9OnT44ILLogI83q0XApsACeddFI0adLkoIrfunXrQf9HwEdz4NMrR5rT8vLy2LNnT7z99tuH3ebj6sYbb4y5c+fGk08+GZ06dcotN69Hr6ioKLp27Rr9+vWLiRMnxtlnnx333HOPOT0Gy5cvj61bt0bfvn2jadOm0bRp01i0aFH88Ic/jKZNm+bmxtweu5KSkqisrIwXX3zR39ljJKwaQFFRUfTt2zfmz59fa/n8+fPjwgsvzNOoTmxdunSJ8vLyWnO6Z8+eWLRoUW5O+/btG82aNau1zebNm+P555//2M57lmUxduzYeOyxx+J//ud/okuXLrXWm9d0siyL3bt3m9NjcMkll0R1dXVUVVXlHv369YtRo0ZFVVVVnH766eY2kd27d8fatWujQ4cO/s4eq3zcMf9xdODrFn76059ma9asyb7xjW9kJSUl2auvvprvoR23duzYka1cuTJbuXJlFhHZ5MmTs5UrV+a+omLSpElZWVlZ9thjj2XV1dXZl7/85UN+HLhTp07Zr3/962zFihXZxRdf/LH+OPD111+flZWVZQsXLqz1Met33303t415rbtbb701W7x4cbZ+/fps1apV2W233ZYVFhZmTzzxRJZl5jSlP/1UYJaZ26N1yy23ZAsXLsxeeeWVbOnSpdnnP//5rHXr1rmfSeb16AmrBvTjH/84++QnP5kVFRVl5557bu4j7hzak08+mUXEQY/Ro0dnWfbBR4LHjx+flZeXZ8XFxdnAgQOz6urqWvt47733srFjx2bt2rXLWrRokX3+85/PNmzYkId3c3w41HxGRDZ16tTcNua17r7yla/k/t0++eSTs0suuSQXVVlmTlP687Ayt0fnwPdSNWvWLOvYsWM2fPjwbPXq1bn15vXoFWRZluXnXBkAQOPiHisAgESEFQBAIsIKACARYQUAkIiwAgBIRFgBACQirAAAEhFWAACJCCsAgESEFQBAIsIKACARYQUAkMj/Aywy0At3h1+mAAAAAElFTkSuQmCC",
      "text/plain": [
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Gráfico de barras de cantidades de sobrevivientes y fallecidos por sexo\n",
    "\n",
    "sobrevivientes = datos_entrenamiento[datos_entrenamiento['Survived']==1]['Pclass'].value_counts()\n",
    "fallecidos = datos_entrenamiento[datos_entrenamiento['Survived']==0]['Pclass'].value_counts()\n",
    "\n",
    "df = pd.DataFrame([sobrevivientes, fallecidos])\n",
    "df.index = ['Sobrevivió', 'Falleció']\n",
    "df.plot(kind='barh', stacked='True')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "43b4219f",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.6"
  },
  "vscode": {
   "interpreter": {
    "hash": "5a32a79650db291454053c8e37efe40e0141c4ec3fedfb47b850ea730bbb1701"
   }
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
