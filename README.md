# i3-video (is-it-instructional-video) annotations

This repo provides i3-video annotations from xxx paper.

We sample videos with English ASR from the validation set of the [YouTube-8M dataset](http://research.google.com/youtube8m/download.html), subject to YouTube policies.  Each video is shown to three paid annotators, who each provide a Yes/No answer to the question: 

“Is this an instructional video in a broad sense?  That is, does this video focus on *real-world* human actions accompanied by procedural language that explains what’s happening on screen in reasonable details?”  

More specifically, the raters were instructed to answer ***yes*** for videos that are
- a tutorial / how-to video intended to teach a user how to do something themselves.  For instance, a cooking demonstration, a video explaining how to bleed brakes, how to stretch your foot, or how to style the hair.   
- not intended to teach viewers how to do it themselves, but whose main focus is real-world human actions accompanied by procedural language.  e.g.,
  - an educational video intended to inform how it's done by professionals, for example, a video with a physician explaining a procedure to potential patients.
  - unboxing video where the narration explains what’s happening on-screen
- Note the emphasis on real-world human actions
  - we want to exclude videos where the visual information is dominated by screenshots
- Note also that the judgment should be made based on the main focus of the video.
  - we want to exclude, for instance, a conditioner review where visually it is mainly displaying the product, with little procedural language; but a video mainly focused on teaching people how to do a particular hair-do should be annotated as yes, even if it has a few product placement at the end

We release the resulting i3-video dataset (is-it-instructional annotations) for 6.8K videos in a csv file with two fields:
```
Video id, human annotation
```

[Video id](http://research.google.com/youtube8m/video_id_conversion.html) is the id for the video from YouTube-8M release, which was a randomly-generated ID to protect the privacy of uploaders.  The external YouTube ID can be looked up following the instructions on [this page](http://research.google.com/youtube8m/video_id_conversion.html), as long as the video remains public on YouTube. 

Human annotation field is simply a string with all ratings received by the video concatenated by `-`.  A rating can be either `Yes`, `No`, or, in a small number of cases, `Can’t Judge`.  In the vast majority of cases (99.8%), a video receives exactly three ratings; in a small number of cases, it receives 1,2, or 4 ratings. 96% of the time, all raters agreed on the same rating.  According to a majority vote, 73.6% of annotated videos are ***not*** instructional. 

