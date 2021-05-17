+++
fragment = "config"

[[config]]
  type = "css" # Acceptable values are icon, meta, link, css, js. Default is empty. Would not add anything on empty.
  block = true # If set to true, would inject the code to the <head> tag. Default is false
  resource = "css/style.css" # Path to file, can be on page or in static/ directory. Default is empty.
    
[[config]]
  type = "js"
  # block = true # Default is false
  html = """
  <script>
var nav = document.querySelector('.my-nav');
nav.addEventListener('toggle', function (event) {

	// Only run if the dropie is open
	if (!event.target.open) return;

	// Get all other open dropies and close them
	var dropies = nav.querySelectorAll('.dropie[open]');
	Array.prototype.forEach.call(dropies, function (dropie) {
		if (dropie === event.target) return;
		dropie.removeAttribute('open');
	});

}, true);
</script>
  """   
  
[[config]]
  type = "js"
  # block = true # Default is false
  html = """
  <script>
var all_links = document.querySelectorAll('a');
for (var i = 0; i < all_links.length; i++){
       var a = all_links[i];
       if(a.hostname != location.hostname) {
               a.rel = 'noopener';
               a.target = '_blank';
       }
}
</script>
  """    
    
+++
