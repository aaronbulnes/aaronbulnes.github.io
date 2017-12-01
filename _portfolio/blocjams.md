---
layout: post
title: BlocJams
feature-img: 
thumbnail-path: "https://d13yacurqjgara.cloudfront.net/users/3217/screenshots/2030966/blocjams_1x.png"
short-description: BlocJams is a music streaming application.

---
{:.center}
![]({{ site.baseurl }}/img/bloc_jams_web_player.png)


{% highlight javascript %}

(function() {
    function timecode() {
        return function(seconds) {
            var seconds = Number.parseFloat(seconds);
            if (Number.isNaN(seconds)) {
                return '-:--';
            }
            var wholeSeconds = Math.floor(seconds);
            var minutes = Math.floor(wholeSeconds/60);
            var remainingSeconds = wholeSeconds % 60;
            var output = minutes + ':';
            if (remainingSeconds < 10) {
                output += '0';
            }
            output += remainingSeconds;
            return output;
        };
    }
    angular
        .module('blocJams')
        .filter('timecode', timecode);
})();

{% endhighlight %}

--

Above is a snippt from the code of my Bloc Jams web music player. The entire project was quite departure for me. Working with Angualr JavaScript was a challenge for me. I thought I knew what I was doing before, but Angular was curveball for me. Eventually, I was able to get the hang of it and get the app working.

This piece of code in particular was a challenge. Math is exactly my forte, so getting the math in the loop was quite tough for me.

Essentially, this code grabs all the seconds in the song and loops through the time duration to display the proper time.