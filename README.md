
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Metro Directions</title>

<style>
body {
  margin: 0;
  padding: 20px;
  background: transparent;
  font-family: "Proxima Nova Condensed", "Arial Narrow", Arial, sans-serif;
}

.cvent-accordion {
  max-width: 800px;
  margin: 0 auto;
}

.acc-item {
  border: 1px solid #e3e3e3;
  border-radius: 6px;
  margin-bottom: 14px;
  overflow: hidden;
  box-shadow: 0 3px 8px rgba(0,0,0,.06);
}

.acc-header {
  width: 100%;
  background: #0f2a44;
  color: #ffffff;
  padding: 16px 20px;
  font-size: 18px;
  font-weight: 700;
  letter-spacing: .4px;
  border: none;
  cursor: pointer;
  text-align: left;
  position: relative;
}

.acc-header:hover {
  background: #183c5f;
}

.acc-header::after {
  content: "+";
  position: absolute;
  right: 20px;
  font-size: 22px;
}

.acc-header.active::after {
  content: "–";
}

.acc-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease;
  background: #ffffff;
  padding: 0 20px;
  font-size: 15px;
  line-height: 1.6;
}

.acc-content ol {
  padding-left: 20px;
  margin: 20px 0;
}

.walktime {
  font-weight: 600;
  margin-bottom: 20px;
  color: #0f2a44;
}
</style>
</head>

<body>

<div class="cvent-accordion">

  <div class="acc-item">
    <button class="acc-header">By Metro’s Red Line – Judiciary Square</button>
    <div class="acc-content">
      <ol>
        <li>Take Metro’s Red Line to the Judiciary Square station</li>
        <li>Exit using the National Building Museum / F Street exit</li>
        <li>Turn RIGHT and walk EAST on F Street N.W.</li>
        <li>Walk through the Georgetown University Law Center campus plaza toward New Jersey Avenue N.W.</li>
        <li>Exit onto New Jersey Avenue N.W. and cross the street</li>
        <li>Turn LEFT and walk about half a block</li>
        <li>The office building at 601 New Jersey Ave NW will be on your right</li>
      </ol>
      <p class="walktime">Approximate walk time: 6–8 minutes</p>
    </div>
  </div>

  <div class="acc-item">
    <button class="acc-header">By Metro’s Red Line – Union Station</button>
    <div class="acc-content">
      <ol>
        <li>Take Metro’s Red Line to the Union Station stop</li>
        <li>Exit following signs for Massachusetts Avenue / Columbus Circle</li>
        <li>Face Columbus Circle and turn RIGHT toward the U.S. Capitol</li>
        <li>Walk SOUTH along First Street N.E.</li>
        <li>Continue across Massachusetts Avenue N.E.; it becomes First Street N.W.</li>
        <li>Turn RIGHT onto D Street N.W.</li>
        <li>Turn LEFT onto New Jersey Avenue N.W.</li>
        <li>Continue SOUTH about half a block</li>
        <li>The office building at 601 New Jersey Ave NW will be on your right</li>
      </ol>
      <p class="walktime">Approximate walk time: 8–10 minutes</p>
    </div>
  </div>

  <div class="acc-item">
    <button class="acc-header">By Metro’s Green or Yellow Line – Gallery Place–Chinatown</button>
    <div class="acc-content">
      <ol>
        <li>Take Metro’s Green or Yellow Line to the Gallery Place–Chinatown station</li>
        <li>Exit using the F Street / Capital One Arena exit</li>
        <li>Walk EAST on F Street N.W.</li>
        <li>Walk through the Georgetown University Law Center campus plaza toward New Jersey Avenue N.W.</li>
        <li>Exit onto New Jersey Avenue N.W. and cross</li>
        <li>Turn LEFT and walk half a block</li>
        <li>The office building at 601 New Jersey Ave NW will be on your right</li>
      </ol>
      <p class="walktime">Approximate walk time: 12–14 minutes</p>
    </div>
  </div>

</div>

<script>
const headers = document.querySelectorAll(".acc-header");

headers.forEach(header => {
  header.addEventListener("click", function() {

    headers.forEach(h => {
      if (h !== header) {
        h.classList.remove("active");
        h.nextElementSibling.style.maxHeight = null;
      }
    });

    header.classList.toggle("active");
    const content = header.nextElementSibling;

    if (content.style.maxHeight) {
      content.style.maxHeight = null;
    } else {
      content.style.maxHeight = content.scrollHeight + "px";
    }

  });
});
</script>

</body>
</html>
