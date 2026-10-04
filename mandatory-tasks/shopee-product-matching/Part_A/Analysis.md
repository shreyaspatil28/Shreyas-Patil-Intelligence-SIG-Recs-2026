The dataset contains `34250 listings` with each listing having a `listing id`, corresponding `image` uploaded, `title` and `label_group`. Items having same label
groups are same items. There are no null values in the dataset and it contains 11014 product groups i.e. almost every group has approx 3 listings on average 
without inspecting data.
After seeing the product group distribution graph, almost 7k products are listed twice, almost 2k are listed thrice, less than 1k four times and so on where
value keeps getting lower significantly.

Around 32k are unique images which means there are only about `2k duplicate images`, titles are also almost all unique with only 1k duplicate. However, 
there are about `18k highly similar titles` (which have cosine similarity greater than 0.8). Many of the titles of listings are in the range of `7-11 words`
(around 17k) and very few have 1 word or more than 20 words. When a random batch of 10000 images was selected it was found that `gray` and `white` were the 
predominant colors in most of them (almost 7k) so most images are gray and white.

Also I found most occurring words in titles with top of them to be `anak`, `wanita` (idk which lang they are gng) and `original`. After running a batch
of 10000 images to find distribution of number of colors present in an image, they mostly had `5-9 colors` with `9` being the highest.
