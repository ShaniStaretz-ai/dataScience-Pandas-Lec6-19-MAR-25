# dataScience-Pandas-Lec6-19-MAR-25
Pandas functions 3
* if return result, the action was done on new copy and return the copy with the change.
* if DON'T return result, the action was done on the origin
* filter data with conditions: between
* set_index(index name,inplace)
* loc[[rowindex1,rowindex2]]/loc[index1:index2][[colvalue]]
* concat(...).tail() add to the end of the df
* filter return Series of True/False
* to change values to str: df_tip['CC Number'].astype(str)
* dtype of string is object
* function apply(callback) in df: sends 1 column value for each row
  * using functions: define in the cell the function and the call it for each value:
    * df_tip['CC Number'].apply(last4)
  * using lambda:  df_copy['CC Number'].apply(lambda cc:str(cc)[-4:])
  * can send to apply the entire row: 
    * type of row is Series 
    * df_tip.apply(calc_on_row)
    * axis= 1 - to send the row's values (and not the column's values)
* vectorize(callback)(parameter1,parameter2) in df: like apply on list of columns: 
  * function of numpy: np.vectorize(measure_tip)(df_copy['total_bill'],df_copy['tip'])
  * receive callback function and sends the required the callback's parameters
  * works with lambda function
* to change display title you can edit it with Markdown in custom function:
```
from IPython.display import Markdown,display
def printmd(message,data):
    text="**<u>"+message+"</u>**"
    display(Markdown(text),data)
printmd("5 first:",df_hw_mobile.head()) # will print the title: '5 first:' in bold and underline
```