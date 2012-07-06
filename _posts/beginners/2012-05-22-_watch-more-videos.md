---
layout: beginners
title: Sign Up to watch more video tutorials
category: beginners
sidebar: 'off'
comments: 'off'
---

Enter following details to recieve tutorials weekly right into your email box.

<form onsubmit='return validate();' action='http://kodeincloud.com/private/tuts_ci_beginners.php' method='post'>
<b>Your Name: </b>
<br/>
<input type='text' id='name' name='name' style='width: 300px; border: 1px solid #bbb; padding: 3px;'/>
<p></p>
<b>Your Email: </b>
<br/>
<input type='text' id='email' name='email' style='width: 300px; border: 1px solid #bbb; padding: 3px;'/>
<p></p>
<input type='submit' value='Sign Up'/>
</form>

<script type="text/javascript">
	
	$('#name').focus();

	function validate() {
		var email = $('#email').val();
		var name = $('#name').val();

		if(!name) {

			alert("Please enter your name!");
			$('#name').focus();
			return false;
		} else if(!email) {

			alert("Please enter your email!");
			$('#email').focus();
			return false;

		} else if(!validEmail(email)) {

			alert("Please enter a valid email!");
			$('#email').focus();
			return false;

		} else {

			return true;
		}
	}

	function validEmail(e) {
		var filter = /^\s*[\w\-\+_]+(\.[\w\-\+_]+)*\@[\w\-\+_]+\.[\w\-\+_]+(\.[\w\-\+_]+)*\s*$/;
		return String(e).search (filter) != -1;
	}
</script>

