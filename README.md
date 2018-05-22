<!DOCTYPE html>
<html>
<head>
	<title>Javascript calculator</title>
</head>
<body>
	<form name="forms">
		<input type="text" READONLY name="form" id="demo"><br><br>
		<input type="button" name=" 9 " value=" 9 " onclick="forms.form.value  += '9'">
		<input type="button" name=" 8 " value=" 8 " onclick="forms.form.value  += '8'">
		<input type="button" name=" 7 " value=" 7 " onclick="forms.form.value  += '7'">
		<br>
		<input type="button" name=" 6 " value=" 6 " onclick="forms.form.value  += '6'">
		<input type="button" name=" 5 " value=" 5 " onclick="forms.form.value  += '5'">
		<input type="button" name=" 4 " value=" 4 " onclick="forms.form.value  += '4'">
        <br>
		<input type="button" name=" 3 " value=" 3 " onclick="forms.form.value  += '3'">
		<input type="button" name=" 2 " value=" 2 " onclick="forms.form.value  += '2'">
		<input type="button" name=" 1 " value=" 1 " onclick="forms.form.value  += '1'">
        <br>
		<input type="button" name=" * " value=" * " onclick="forms.form.value  += '*'">
		<input type="button" name=" 0 " value=" 0 " onclick="forms.form.value  += '0'">
		<input type="button" name=" / " value=" / " onclick="forms.form.value  += '/'">
		<br>
		<input type="button" name=" + " value=" + " onclick="forms.form.value  += '+'">
		<input type="button" name=" - " value=" - " onclick="forms.form.value  += '-'">
		<input type="button" name=" = " value=" = " onclick="calculate()">
		<br>
		<input type="button" name=" . " value=" . " onclick="forms.form.value  += '.'">
		<input type="button" name=" c " value=" C " onclick="myFunction()">
		<input type="button" name=" / " value=" / " onclick="forms.form.value  += '/'">
		<script type="text/javascript">
			function myFunction() {
				str = document.getElementById("demo").value;				
				forms.form.value = str.substring(0, str.length - 1);
			}
             function getAllIndexes(arr, val)  {
                var indexes = [];
                for(i = 0; i < arr.length; i++){
                if (arr[i] === '/')
                indexes.push(i);
                
            }return indexes;
            }
            function getAllIndexes1(arr, val)  {
                var indexes1 = [];
                for(i = 0; i < arr.length; i++){
                if (arr[i] === '*')
                indexes1.push(i);
                
            }return indexes1;
            }
            function getAllIndexes2(arr, val)  {
                var indexes2 = [];
                for(i = 0; i < arr.length; i++){
                if (arr[i] === '+')
                indexes2.push(i);
                
            }return indexes2;
            }
            function getAllIndexes3(arr, val)  {
                var indexes3 = [];
                for(i = 0; i < arr.length; i++){
                if (arr[i] === '-')
                indexes3.push(i);
                
            }return indexes3;
            }
            function divide(arr1, arr2) {

                var arr3 = [];
                for (i = 0; i < arr2.length; i++) {
                    arr3.push(parseFloat(arr1[arr2[i]-1]) / parseFloat(arr1[arr2[i]+1]));
                }
                 return arr3;
                
            }
            function multiply(arr1, arr2) {

                var arr3 = [];
                for (i = 0; i < arr2.length; i++) {
                    arr3.push(parseFloat(arr1[arr2[i]-1]) * parseFloat(arr1[arr2[i]+1]));
                }
                 return arr3;
                
            }
            function add(arr1, arr2) {

                var arr3 = [];
                for (i = 0; i < arr2.length; i++) {
                    arr3.push(parseFloat(arr1[arr2[i]-1]) + parseFloat(arr1[arr2[i]+1]));
                }
                 return arr3;
                
            }
            function subtract(arr1, arr2) {

                var arr3 = [];
                for (i = 0; i < arr2.length; i++) {
                    arr3.push(parseFloat(arr1[arr2[i]-1]) - parseFloat(arr1[arr2[i]+1]));
                }
                 return arr3;
                
            }
			function calculate() {
				var x = document.getElementById("demo").value;
				var inputarr = x.split(/(\d+\.?\d*)/);               
                var indexes = getAllIndexes(inputarr, "/");
                console.log(inputarr);
                console.log(indexes);
                function replace_divide_elements(n1, n2, n3)
                 {for (var i = 0; i < n2.length; i++) {
                    n1.splice(n1.indexOf('/')-1, 3, n3[i]);
                }
                
            }
                var q = divide(inputarr, indexes);
                var e = replace_divide_elements(inputarr, indexes, q);
                console.log(e);
                console.log(q);
                console.log(inputarr);
                var indexes1 = getAllIndexes1(inputarr, "*");
                function replace_multiply_elements(n1, n2, n3)
                 {for (var i = 0; i < n2.length; i++) {
                    n1.splice(n1.indexOf('*')-1, 3, n3[i]);
                }
                
            }
                var q1 = multiply(inputarr, indexes1);
                var e1 = replace_multiply_elements(inputarr, indexes1, q1);
                console.log(q1);
                console.log(e1);
                var indexes2 = getAllIndexes2(inputarr, "+");
                function replace_addition_elements(n1, n2, n3)
                 {for (var i = 0; i < n2.length; i++) {
                    n1.splice(n1.indexOf('+')-1, 3, n3[i]);
                }
                
            }
                var q2 = add(inputarr, indexes2);
                var e2 = replace_addition_elements(inputarr, indexes2, q2);
                console.log(q2);
                console.log(e2);
                var indexes3 =getAllIndexes3(inputarr, "-");
                function replace_sub_elements(n1, n2, n3)
                 {for (var i = 0; i < n2.length; i++) {
                    n1.splice(n1.indexOf('-')-1, 3, n3[i]);
                }
                
            }     
                var q3 = subtract(inputarr, indexes3);
                var e3 = replace_sub_elements(inputarr, indexes3, q3);
                console.log(q3);
                console.log(e3);  
                forms.form.value = inputarr[1];
                
                }

		</script>	

	</form>
</body>
</html>



