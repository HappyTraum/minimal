---
layout: default
title: Mag. Richard Wolf - Psychotherapie
permalink: /
---

<h2><a href="/psychotherapie.html">Psychotherapie</a></h2>

<h2><a href="/lebenslauf.html">Lebenslauf</a></h2>

<h2><a href="/arbeitsschwerpunkte.html">Arbeitsschwerpunkte</a></h2>

<p>Ich biete personzentrierte Psychotherapie in Wien an.</p>
<!--<p>I offer therapy in English.</p>-->

<h2>Kontakt</h2>

<form id="contact-form" action="https://formspree.io/f/mvzwokkz" method="POST" style="max-width: 520px;">
  <p>
    <label for="name">Name</label><br>
    <input type="text" id="name" name="name" required style="width: 100%; padding: 8px;">
  </p>

  <p>
    <label for="email">E-Mail</label><br>
    <input type="email" id="email" name="email" required style="width: 100%; padding: 8px;">
  </p>

  <p>
    <label for="message">Nachricht</label><br>
    <textarea id="message" name="message" rows="8" required style="width: 100%; padding: 8px;"></textarea>
  </p>

  <input type="hidden" name="_subject" value="Kontaktanfrage über richardwolf.co.at">
  <input type="text" name="_gotcha" style="display:none">

  <p>
    <button type="submit">Nachricht senden</button>
  </p>
</form>

<p id="form-status" style="display:none; margin-top: 1em;"></p>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const form = document.getElementById("contact-form");
  const status = document.getElementById("form-status");

  form.addEventListener("submit", async function (e) {
    e.preventDefault();

    const data = new FormData(form);

    try {
      const response = await fetch(form.action, {
        method: "POST",
        body: data,
        headers: {
          "Accept": "application/json"
        }
      });

      if (response.ok) {
        form.reset();
        status.style.display = "block";
        status.textContent = "Vielen Dank. Ihre Nachricht wurde erfolgreich gesendet.";
      } else {
        status.style.display = "block";
        status.textContent = "Leider ist beim Senden ein Fehler aufgetreten. Bitte versuchen Sie es später erneut oder schreiben Sie mir direkt per E-Mail.";
      }
    } catch (error) {
      status.style.display = "block";
      status.textContent = "Leider ist beim Senden ein Fehler aufgetreten. Bitte versuchen Sie es später erneut oder schreiben Sie mir direkt per E-Mail.";
    }
  });
});
</script>

