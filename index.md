---
width: expand
header:
  # image: header.jpg
  # background: "rgba(0, 0, 0, 0.5)"
  # color: light
  title: How can we help you?
  subtitle:
  # search: true
---

{% include categories.html 
  columns="3" 
  section="muted" 
%}

{% include faqs.html 
  multiple="true" 
  title="Frequently asked questions" 
  category="faq" 
  subtitle="Find quicke answers to frequent pre-sale questions asked by customers" 
  section="muted" 
%}

{% include team.html 
  authors="alex_zhukovich, robert_konarskis, jonatas_josue_kirsch" 
  title="We are here to help" 
  subtitle="Our team is just an email away ready to answer your questions" 
  section="default" 
%}