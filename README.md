# Denise Sophy | Cybersecurity Portfolio

**Live Version:**  
[https://denise-sophy.github.io](https://denise-sophy.github.io)

---

### About This Portfolio

A clean, dark-themed, single-page portfolio built to showcase my hands-on experience in **cybersecurity**, **SOC operations**, **threat detection**, and **blue team skills**.

It highlights my real-world experience from internships at ICT Authority, Kenya Broadcasting Corporation, Future Interns, and CyberShujaa, along with my ongoing #100DaysOfCybersecurity journey, lab work with Wireshark, Nmap, Microsoft Sentinel, and MITRE ATT&CK mapping.

---

### Features

- Modern dark cyber aesthetic
- Fully responsive (looks great on mobile and desktop)
- Smooth scrolling navigation
- Interactive project cards with modal details
- Image gallery support for lab screenshots
- Easy-to-update configuration (all main content is in one JavaScript object)
- Downloadable résumé button
- Professional and recruiter-friendly layout

---

### How to Customize (for anyone forking this)

All the important content is controlled in the `<script>` section at the bottom of `index.html`.

Look for this block and update it with your own information:

```javascript
const portfolioConfig = {
  name: "Denise Sophy",
  title: "Cybersecurity Analyst | SOC | Threat Detection",
  skills: [ ... ],
  projects: [ ... ]
};
