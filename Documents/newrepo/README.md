<!DOCTYPE html>
<html>
<head>
<title>Haro</title>
</head>

<body>
The content of the document......

<script>
var movie1 = {
	title: "Plan 9 from Outer Space",
	genre: "Cult Classic",
	rating: 5,
	showtimes: ["3:00pm", "7:00pm", "11:00pm"],

getNextShowing: function() {
	var now = new Date().getTime();

	for (var i = 0; i < this.showtimes.length; i++) {
		var showtime = getTimeFromString(this.showtimes[i]);
		if ((showtime - now) > 0) {
			return "Next showing of " + this.title + " is " + this.showtimes[i];
		}
	}
	return null;
}
};
function getTimeFromString(str) {
	var theTime = new Date();
	var time = str.match(/(\d+)(?::(\d\d))?\s*(p?)/);
	theTime.setHours( parseInt(time[1]) + (time[3] ? 12 : 0) );
	theTime.setMinutes( parseInt(time[2]) || 0 );
	return theTime.getTime();
}
</script>
</html>