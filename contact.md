---
title: Contact Us
permalink: /contact/
---
Theme includes integration for two popular contact form providers Formspree and Kwes, both have free plans with some limitations, see [Formspree](https://formspree.io/) and [Kwes](https://kwes.io/) for more details. Form name and subject fields can be disabled.

### Formspree Contact Form

{% include formspree.html email="my_name@gmail.com" redirect="/thanks/" name="true" subject="true" %}

<br>

### Kwes Contact Form

{% include kwes.html key="00000" redirect="/thanks/" name="true" subject="true" %}
