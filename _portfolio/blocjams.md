---
layout: post
title: BlocJams
feature-img: "img/bloc_jams_bg.jpg"
thumbnail-path: "https://d13yacurqjgara.cloudfront.net/users/3217/screenshots/2030966/blocjams_1x.png"
short-description: BlocJams is a music streaming application.

---
{:.center}
![]({{ site.baseurl }}/img/bloc_jams_bg.jpg)


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
