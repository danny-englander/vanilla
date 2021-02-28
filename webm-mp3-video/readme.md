# Webm / MP3 Video custom code

This code below queries the state of an HTML5 video. The video has pause and play buttons that have click events. We swap the buttons depending on the state of play.

* Event listener for playing state
* Event listener for paused state
* Event listener for button click event

```javascript
      // MP4 uploaded video play and pause functions.
      // Define the video.
      const video = document.getElementById('mp4-video');
      // Pause trigger.
      const pause_trigger = document.querySelector("#mp4-trigger-pause-play .pause-icon");
      // Play trigger.
      const play_trigger = document.querySelector("#mp4-trigger-pause-play .play-icon");
      // Pause wrap.
      const pause_wrap = document.querySelector("#mp4-trigger-pause-play .pause-wrap");
      // Play wrap.
      const play_wrap = document.querySelector("#mp4-trigger-pause-play .play-wrap");

      // Pause event
      if (video) {
        video.addEventListener("pause", function () {
          // console.log('paused');
          pause_wrap.style.display = "none";
          play_wrap.style.display = "block";
        });

        // Playing event
        video.addEventListener("playing", function () {
          // console.log('playing');
          pause_wrap.style.display = "block";
          play_wrap.style.display = "none";
        });

        // Pause action.
        pause_trigger.addEventListener("click", function (e) {
          // Pause function.
          video.pause();
        }, false);

        // Play action.
        play_trigger.addEventListener("click", function (e) {
          // Play function.
          video.play();
        }, false);
      }
```


