---
layout: post
title: "Perl Literals and data structures: a guide to arrays, hashes, and references ((), [], {})"
description155: "Avoid the common mistakes with perl data structures, understand a more subtle behaviour, and safely nest { 'all' => { 'your' => 'data' } }."
search_title70: "Literals (), [], {} and data structures in Perl"
tags:
    - tutorials
    - perl
    - programming
type: post
published: true
main_square_image_url: /static/images/posts/perl-snippet.png
main_square_image_alt: Random perl code
---

Perl is not an easy language to get your head around sometimes. It's simple on the surface, with only a few data types to learn, but subtle behaviours abound, and learning them up-front can save painful hours.

One troublesome point is how Perl handles nested arrays and hashes. Perl, in contrast to languages like Python and JavaScript, likes to squish data structures together and treat them as a single continuous unit:

{% highlight perl %}
my @cats = ('meow', 'purr', 'pounce');
my @dogs = ('bark', 'drool');

# You want an array of arrays now, eh? (a nested arrangement)
my @animal_sounds = (@cats, @dogs);

# Sorry; @animal_sounds has been Perlsquished:
('meow', 'purr', 'pounce', 'bark', 'drool')
{% endhighlight %}

This combined array discards all separation between the two halves, and even the original type of those halves. If they had been hashes, the `@animal_sounds` array would be *identical*. Following that train of smooth-if-occasionally-unwanted conversions, the full `@animal_sounds` array is also completely interchangeable with a hash. Perl won't complain at all when you make a hash version of it.

{% highlight perl %}
my %unsound_mappings = @animal_sounds;

# %unsound_mappings is now:
('meow' => 'purr', 'pounce' => 'bark', 'drool' => undef)
{% endhighlight %}

Alternating elements are combined into key-value pairs. Notice how the odd number of elements results in that last `'run' => undef` mapping? Yay!

This array-hash shape-shifting feature is occasionally useful, but I find it tends to result in slightly confusing code. I like dumb code. Regardless, I also enjoy nesting...


## Achieving Nesting in Perl ##

Nesting is accomplished through the use of references, and for this reason alone (though there are others, I assure you), I recommend the use of references for arrays and hashes *whenever possible*. Here is a handy... *ahem*...  reference for Perl ref data types, all in one table!

{% include perl_referencing_table.html %}

As you can see, references look and behave very similarly, but you won't have to remember to keep your sigils straight with them (the little $, @, or %); they all use a dollar-sign! More importantly, you can also freely nest away:

{% highlight perl %}
my $cats = ['meow', 'purr', 'pounce'];
my $dogs = ['bark', 'drool'];

# You want an array of arrays now, eh? Go ahead!
my $animal_sounds = [$cats, $dogs];

# Perfect. This is the resulting $animal_sounds:
[['meow', 'purr', 'pounce'], ['bark', 'drool']]
{% endhighlight %}

To access an element of this data structure, just use the syntax from the syntax table above. For example, to print "pounce":

{% highlight perl %}
my $cat_sub_array = $animal_sounds->[0];
print($cat_sub_array->[2]); # This prints "pounce"

print($animal_sounds->[0]->[2]); # Also prints "pounce"!
{% endhighlight %}

There are syntactically shorter ways to write this ("[Now it really looks like two-dimensional arrays!](http://perldoc.perl.org/perlreftut.html#Arrow-Rule)"), but consistency of meaning wins for me over short cuts in syntax.

## Moving on then... ##

Raw, non-referenced data structures in Perl are not very intuitive for even moderately complex data structures, especially if you're used to many other high-level languages (e.g. Python). Non-referenced data types also introduce the need for sigils, and make passing data in and out of functions a pain (array and hash arguments get squashed into one big argument array).

So my advice is: save yourself from frustration, and just stick to references!
