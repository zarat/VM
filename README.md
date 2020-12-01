# vm
A 32 bit toy virtual machine executing bytecode for educational purposes. It is not promising anything! Your data can get lost! Be careful! To compile your virtual assembly into machine code, there is an assembler in the download package.

<pre>
// compile and run a binary
as [assembly] [binary]
vm [binary]
</pre>

More information at [vm.lima-city.at](https://vm.lima-city.at).

<code><script>
function targetBlank() {
  // remove subdomain of current site's url and setup regex
  var internal = location.host.replace("www.", "");
      internal = new RegExp(internal, "i");
      
  var a = document.getElementsByTagName('a'); // then, grab every link on the page
  for (var i = 0; i < a.length; i++) {
    var href = a[i].host; // set the host of each link
    if( !internal.test(href) ) { // make sure the href doesn't contain current site's host
      a[i].setAttribute('target', '_blank'); // if it doesn't, set attributes
    }
  }
};
targetBlank();
</script></code>
