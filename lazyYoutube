function labnolIframe(div) {
  var videoId = div.dataset.id;
  if (!videoId) return; // Cek apakah videoId ada sebelum membuat iframe

  var iframe = document.createElement("iframe");
  iframe.setAttribute(
    "src",
    "https://www.youtube.com/embed/" + videoId + "?autoplay=1&rel=0"
  );
  iframe.setAttribute("frameborder", "0");
  iframe.setAttribute("allowfullscreen", "1");
  iframe.setAttribute(
    "allow",
    "accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
  );
  div.parentNode.replaceChild(iframe, div);
}

function initYouTubeVideos() {
  var playerElements = document.getElementsByClassName("Pixabin-youtube-player");
  if (!playerElements || playerElements.length === 0) return; // Cek apakah ada elemen video

  for (var n = 0; n < playerElements.length; n++) {
    var videoId = playerElements[n].dataset.id;
    if (!videoId) continue; // Lewatkan jika tidak ada videoId

    var div = document.createElement("div");
    div.setAttribute("data-id", videoId);

    var thumbNode = document.createElement("img");
    thumbNode.setAttribute("class", "lazyload");
    thumbNode.setAttribute("alt", "youtube");   
    thumbNode.setAttribute("src","data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=");
    thumbNode.src = "https://img.youtube.com/vi/" + videoId + "/maxresdefault.jpg";
    div.appendChild(thumbNode);

    var playButton = document.createElement("div");
    playButton.setAttribute("class", "play");
    div.appendChild(playButton);

    div.onclick = function () {
      labnolIframe(this);
    };

    playerElements[n].appendChild(div);
  }
}

document.addEventListener("DOMContentLoaded", initYouTubeVideos);	//]]>
