# Radius-Circle



function calc(form)
{
  
  var radius = parseFloat(form.radius.value);

   var volume = (4/3) * Math.PI * Math.pow(radius,3);
  document.getElementById("volume").innerHTML = chopTo4(volume);

  var c = document.getElementById("mycanvas");
    var ctx = c.getContext("2d");
    ctx.beginPath();
    ctx.arc(200,200,radius,0,2*Math.PI);
    ctx.stroke();
}

function chopTo4(raw)
{
  strRaw = raw.toString();
  if(strRaw.length - strRaw.indexOf(".") > 4)
    strRaw = strRaw.substring(0,strRaw.indexOf(".") + 5);
  return strRaw;
}
// openclass //
function surligne(champ, erreur)
{
   if(erreur)
      champ.style.backgroundColor = "#FF0000";
      
   else
      champ.style.backgroundColor = "#00FF00";
}

function verifPseudo(champ)
{
   if(champ.value < 0 || champ.value > 200 || champ.value*0 !=0 || champ.value == "" )
   {
      surligne(champ, true);
      alerty();    
        return false;
   }
   else
   {
      surligne(champ, false);
      return true;
   }
}
    

function alerty ()
{
    alert('Error,print a number between 0 and 200 !')
}




function cleary (context,canvas)
{
    canvas = document.getElementById("mycanvas");
ctx = canvas.getContext("2d");
ctx.clearRect(0, 0, canvas.width, canvas.height);
}
    

