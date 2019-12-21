<h1>Sharing using FB.ui() Dialogs</h1>

<p>Below are some simple examples of how to use UI dialogs in a web page.</p>

<h3>Sharing Links</h3>

<div id="shareBtn" class="btn btn-success clearfix">Share Dialog</div>

<p>The Share Dialog enables you to share links to a person's profile without them having to use Facebook Login. <a href="https://www.medlinepro.us">Read our Share Dialog guide</a> to learn more about how it works.</p>

<script>
document.getElementById('shareBtn').onclick = function() {
  FB.ui({
    display: 'popup',
    method: 'share',
    href: 'https://www.medlinepro.us',
  }, function(response){});
}
</script>

<h3>Publishing Open Graph Stories</h3>

<p>The Share Dialog can also be used to publish Open Graph stories without using Facebook Login or the Graph API. <a href="https://www.medlinepro.us">Read our Share Dialog guide</a> to learn more about how it works.</p>

<div id="ogBtn" class="btn btn-success clearfix">Simple OG Dialog</div>

<script>
document.getElementById('ogBtn').onclick = function() {
  FB.ui({
    display: 'popup',
    method: 'share_open_graph',
    action_type: 'og.likes',
    action_properties: JSON.stringify({
        object:'https://www.medlinepro.us',
    })
  }, function(response){});
}
</script>

<h3>Sending App Requests</h3>

<p><a href="https://developers.facebook.com/docs/games/requests/">Requests</a> can be sent by any Facebook Apps that are categorised as Games and have a Canvas, iOS, or Android implementation. The JavaScript SDK enables web Canvas games to send requests. <a href="https://developers.facebook.com/docs/games/requests/">Read our guide to Requests</a> to learn more and see more complex examples that you could use.</p>

<div id="requestsBtn" class="btn btn-success clearfix">Basic Request Dialog</div>

<script>
document.getElementById('requestsBtn').onclick = function() {
  FB.ui({method: 'apprequests',
      message: 'This is a test message for the requests dialog.'
  }, function(data) {
    Log.info('App Requests Response', data);
  });
}
</script>


