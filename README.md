{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "498143e1",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<img src=\"https://static1.squarespace.com/static/5006453fe4b09ef2252ba068/5095eabce4b06cb305058603/5095eabce4b02d37bef4c24c/1352002236895/100_anniversary_titanic_sinking_by_esai8mellows-d4xbme8.jpg\"/>"
      ],
      "text/plain": [
       "<IPython.core.display.Image object>"
      ]
     },
     "execution_count": 3,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "from IPython.display import Image\n",
    "Image(url= \"https://static1.squarespace.com/static/5006453fe4b09ef2252ba068/5095eabce4b06cb305058603/5095eabce4b02d37bef4c24c/1352002236895/100_anniversary_titanic_sinking_by_esai8mellows-d4xbme8.jpg\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "e92708c7",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "b230faad",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train = pd.read_csv(\"input/train.csv\")\n",
    "test = pd.read_csv(\"input/test.csv\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "bb9aadb4",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train.isnull().sum()\n",
    "print(\"Train Shape:\",train.shape)\n",
    "test.isnull().sum()\n",
    "print(\"Test Shape:\",test.shape)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "5058ce9a",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "1c8b374e",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "test.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "9fc58a48",
   "metadata": {},
   "source": [
    "* Survived: 0 = No, 1 = Yes\n",
    "* pclass: Ticket class 1 = 1st, 2 = 2nd, 3 = 3rd\n",
    "* sibsp: # of siblings / spouses aboard the Titanic\n",
    "* parch: # of parents / children aboard the Titanic\n",
    "* ticket: Ticket number\n",
    "* cabin: Cabin number\n",
    "* embarked: Port of Embarkation C = Cherbourg, Q = Queenstown, S = Southampton\n",
    "\n",
    "**Total rows and columns**\n",
    "\n",
    "We can see that there are 891 rows and 12 columns in our training dataset.\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "5d6d11fc",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train.head(10)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "4ce0fdce",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train.describe()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "907d7b54",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "test.describe()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "0dfebbdf",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "train.isnull().sum()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "6d913f28",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "test.isnull().sum()\n",
    "test[\"Survived\"] = \"\"\n",
    "test.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "407f39f6",
   "metadata": {},
   "source": [
    "Data Visualization using Matplotlib and Seaborn packages"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "78332da7",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "import matplotlib.pyplot as plt # Plot the graphes\n",
    "%matplotlib inline\n",
    "import seaborn as sns\n",
    "sns.set() # setting seaborn default for plots"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0c63dddc",
   "metadata": {},
   "source": [
    "# Bar Chart for Categorical Features"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "92cc15b9",
   "metadata": {},
   "source": [
    "* Pclass\n",
    "* Sex\n",
    "* SibSp ( # of siblings and spouse)\n",
    "* Parch ( # of parents and children)\n",
    "* Embarked\n",
    "* Cabin\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "10f344a9",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "def bar_chart(feature):\n",
    "    survived = train[train['Survived']==1][feature].value_counts()\n",
    "    dead = train[train['Survived']==0][feature].value_counts()\n",
    "    df = pd.DataFrame([survived,dead])\n",
    "    df.index = ['Survived','Dead']\n",
    "    df.plot(kind='bar',stacked=True, figsize=(10,5))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "57d19bb2",
   "metadata": {},
   "outputs": [
    {
     "ename": "",
     "evalue": "",
     "output_type": "error",
     "traceback": [
      "\u001b[1;31mnotebook controller is DISPOSED. \n",
      "\u001b[1;31mView Jupyter <a href='command:jupyter.viewOutput'>log</a> for further details."
     ]
    }
   ],
   "source": [
    "bar_chart('Sex')\n",
    "print(\"Survived :\\n\",train[train['Survived']==1]['Sex'].value_counts())\n",
    "print(\"Dead:\\n\",train[train['Survived']==0]['Sex'].value_counts())"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "ee9a5c6f",
   "metadata": {},
   "outputs": [
    {
     "ename": "NameError",
     "evalue": "name 'bar_chart' is not defined",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mNameError\u001b[0m                                 Traceback (most recent call last)",
      "Cell \u001b[0;32mIn[4], line 1\u001b[0m\n\u001b[0;32m----> 1\u001b[0m \u001b[43mbar_chart\u001b[49m(\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mPclass\u001b[39m\u001b[38;5;124m'\u001b[39m)\n\u001b[1;32m      2\u001b[0m \u001b[38;5;28mprint\u001b[39m(\u001b[38;5;124m\"\u001b[39m\u001b[38;5;124mSurvived :\u001b[39m\u001b[38;5;130;01m\\n\u001b[39;00m\u001b[38;5;124m\"\u001b[39m,train[train[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mSurvived\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m==\u001b[39m\u001b[38;5;241m1\u001b[39m][\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mPclass\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m.\u001b[39mvalue_counts())\n\u001b[1;32m      3\u001b[0m \u001b[38;5;28mprint\u001b[39m(\u001b[38;5;124m\"\u001b[39m\u001b[38;5;124mDead:\u001b[39m\u001b[38;5;130;01m\\n\u001b[39;00m\u001b[38;5;124m\"\u001b[39m,train[train[\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mSurvived\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m==\u001b[39m\u001b[38;5;241m0\u001b[39m][\u001b[38;5;124m'\u001b[39m\u001b[38;5;124mPclass\u001b[39m\u001b[38;5;124m'\u001b[39m]\u001b[38;5;241m.\u001b[39mvalue_counts())\n",
      "\u001b[0;31mNameError\u001b[0m: name 'bar_chart' is not defined"
     ]
    }
   ],
   "source": [
    "bar_chart('Pclass')\n",
    "print(\"Survived :\\n\",train[train['Survived']==1]['Pclass'].value_counts())\n",
    "print(\"Dead:\\n\",train[train['Survived']==0]['Pclass'].value_counts())"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "41ea8e32",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Data_Processing",
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
   "version": "3.10.14"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
