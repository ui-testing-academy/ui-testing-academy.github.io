---
width: expand
header:
  # image: header.jpg
  # background: "rgba(0, 0, 0, 0.5)"
  # color: light
  title: Here you learn more about UI testing
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

{% include cta.html 
  title="Didn't find an answer?" 
  button_text="Contact Us" 
  button_url="/contact/" 
  subtitle="Get in touch with us for more information about UI Testing" 
  section="muted"
%}
