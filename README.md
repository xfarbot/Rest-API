<h1>Rest-API</h1>
<p>rest api ini gratis buat anda, tolong jangan di perjual belikan</p>


<h3>Thanks to:</h3>
<p>- Tobz API<br>- Zahirr<br>- Itskhyaa<br>- Jojo API<br>- Zeks API</p>

<h1>GEMPA TERKINI</h1>
<p>
   Kedalaman: <span id="data-kedalam"></span><br>
   Wilayah: <span id="data-lokasi"></span><br>
   Kekuatan: <span id="data-magnu"></span>&nbsp;&nbsp;Magnutido<br>
   Waktu: <span id="data-wktu"></span><br>
</p>
<script>
function getgempa() {
    fetch('https://viko-api.herokuapp.com/api/info/gempa?apikey=rxking')
    .then(response => response.json())
    .then(data => {
        console.log(data)

        let lokasi = data.result.Wilayah
        let magnu = `kekuatan ${data.result.Magnitudo} SR`
		let kedalam = `dengan kedalaman ${data.result.Kedalaman}`
		let wktu = data.result.Waktu
        document.getElementById("data-lokasi").innerHTML = lokasi
		document.getElementById("data-magnu").innerHTML = magnu
		document.getElementById("data-kedalam").innerHTML = kedalam
		document.getElementById("data-wktu").innerHTML = wktu
    })
    .catch(err => {
        console.log(err)
    });
} 
</script>
