For an eCommerce website every millisecond counts, and page speed is a common sticking point for most solutions out there. In this article I’m going to describe 3 practical ways you can decrease your page load time.

"Remember that time is money.” - Benjamin Franklin

1. Image Optimisation

Images are by far the single largest group of resources a visitor to your site will download.

When creating image assets, both designers and developers are used to “Saving for Web” from Photoshop or running site assets through apps like TinyPNG or SmushIt, which all compress and optimise your images (hopefully) without loss of detail.

Another technique that has been around for a while, but will have a positive effect on your page load, is CSS sprites, although with a modern SVG twist. I won’t go do into detail on the implementation but for those wishing to read up Chris Colier has a great tutorial over on [CSS Tricks](https://css-tricks.com/svg-sprites-use-better-icon-fonts/).

These are great ways of saving bytes on images you create, but what about assets uploaded through a CMS or by a user? Thoughtbot maintain a great Ruby gem called [Paperclip](https://github.com/thoughtbot/paperclip) which leverages imagemagick to crop, resize, and optimise your uploaded assets. You could then take this one step further, by implementing the (picture element)[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture] and serving the correct image for the correct viewport.

2. Domain sharding
Out of the box web browsers limit the number of concurrent connections per domain - which is usually two - and any further requests get placed in one long queue, thus slowing down our page load.

However, we can side step this queue if we load different types of content from different subdomains, which creates more possible connections, allowing the requests to be processed faster, therefore decreasing the page load!

How can we achieve this in Rails? Firstly we leverage Amazon S3s ability to host (static websites)[http://docs.aws.amazon.com/AmazonS3/latest/dev/website-hosting-custom-domain-walkthrough.html] and then point our DNS toward the bucket - we use (CloudFlare for this)[https://support.cloudflare.com/hc/en-us/articles/200168926-How-do-I-use-CloudFlare-with-Amazon-s-S3-Service-] as we then get the added bonus that our assets get cached by their CDN.

We then use (Asset Sync)[https://github.com/AssetSync/asset_sync], which precompiles our static assets to one bucket, and Paperclip, which transfers all our uploaded content to a separate bucket.

3. Critical CSS

Second to images, the CSS for highly stylised eCommerce websites can be the biggest sink hole for page load times, so seperating your styling into (critical rendering path)[https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path] and non-critical styling is essential.

So what should go into your critical CSS? The short answer is anything that is required to make the (above the fold)[https://en.wikipedia.org/wiki/Above_the_fold#In_web_design] content look premium. After all it is the first thing a visitor sees on your website. A basis critical CSS file could just contain your grid structure, header, and hero image styles all of which would be above the fold.

The filament group have open sourced a great NodeJS package for extracting the critical CSS of a webpage into a single file cunningly called (criticalCSS)[https://github.com/filamentgroup/criticalCSS], which is worth checking out.

Rails bonus: Turbolinks

Turbolinks is not really a Rails bonus as it's just a JavaScript file you can include in any project, but you do get an awful lot more from it in a Rails app - especially a Rails 5 app.

Essentially it speeds up your site by AJAXing your internal site links, and only replacing the body, meaning your visitor (and their browser) only has to download your static assets (JavaScript and CSS) once. It does some other tricks too like changing the pushState, and page titles.

If you are working on a Ruby project installing Turbolinks is easy, just bundle install the Ruby gem and require turbolinks in your application. However if you aren’t coding in Ruby, Turbolinks has been ported over to many other languages/frameworks, and a quick search on (libraries.io)[https://libraries.io/keywords/turbolinks] will hopefully turn up the results you are after. Failing that you can grab the CoffeeScript from (GitHub)[https://github.com/rails/turbolinks/blob/master/lib/assets/javascripts/turbolinks.coffee] and include it in your project.

Once you have implemented some of these suggestions, you’ll see the positive effects in page load time, which can be measured from within Google Webmaster page speed tools, or using services like (webpagetest)[http://www.webpagetest.org/].
