// This function checks if the user is on an iOS device
function isIOS() {
  return /iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream;
}

// This function takes a YouTube URL and opens it in the YouTube app
function openInYouTubeApp(youtubeURL) {
  if (isIOS()) {
    // Extract the video ID from the YouTube URL
    var videoID = youtubeURL.split('v=')[1];
    var ampersandPosition = videoID.indexOf('&');
    if (ampersandPosition != -1) {
      videoID = videoID.substring(0, ampersandPosition);
    }

    // Construct the YouTube app URL and open it
    var appURL = 'youtube://' + videoID;
    window.open(appURL);
  }
}

// Add event listener to links with class 'youtube-video'
document.querySelectorAll('a.youtube-video').forEach(function(link) {
  link.addEventListener('click', function(e) {
    e.preventDefault();
    openInYouTubeApp(this.href);
  });
});
