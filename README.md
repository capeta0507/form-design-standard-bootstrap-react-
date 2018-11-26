# Form 注意事項
###### tags: `form` `input`
1.若要阻止表單送出的話需在onsubmit(或是onclick)內加上return false
```htmlmixed=
<form name="myform" id="myform" method="GET" onsubmit="handleSubmit();return false"></form>
```
2. 若表單內有使用fieldset包覆的話，需注意button按鈕不能寫在fieldset裡面。
```htmlmixed=
<form action="" id="myform" > 
        <fieldset >
            <legend>表單</legend>
            <br>
            <div class="formDiv">
                <label for="myname">名字：</label>
                <input id="myname" type="text" name="myname" class="inputText" placeholder="Name">
            </div>
            <br>
        </fieldset>
        <div class="formDiv">
            <input type="submit" value="送出"> &nbsp;&nbsp;
            <input type="reset" value="重填">
        </div>
    </form>
```
3.判斷是否勾選
```
var marry = document.getElementById("marry"); 
if(marry.checked){
    merryCheck = true;
}else{
    merryCheck = false;
}

```
4.確認勾選項目(判斷勾選的項目)
```
var education = document.getElementsByName("education");
for(var x = 0;x<education.length;x++){
    if(education[x].checked){
        educateNum = x+1;
        break;
    }
}
```
5. select內容套上陣列(使用state)
```
this.state={
            jobs : ["請選擇...","前端","後端","全端","美編","UI/UX"],
            edus : ["高中","專科/大學","碩士","博士"]
        }

const myJob = this.state.jobs.map((job,index) =>{
            return(<option value={index}>{job}</option>)
        })
```
```
<div className="formDiv">
    <label for="">專長：</label>
    <select name="myJob" id="myJob" className="inputText">
        {myJob}
    </select>
</div>
```