---
author: "YUEPENG"
title: "IPython Notebook Intro"
date: 2015-09-06T19:52:01+05:45
comments: false
---

{% highlight python %}
%pylab inline

def return_on_investment(principal, interest_rate, number_of_years):
	return principal * e ** (interest_rate * number_of_years)
{% endhighlight %}