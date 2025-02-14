# PGPResources
Resources for Pretty Good Privacy
<br>
<h1>Intro</h1>
The PGP protocols are easier to use than you think! I've assumed you've done your research on PGP/GPG; otherwise, skip down below to "Resources". I have some advice here, combined with links (and my global gpg.conf settings) to make your journey into it a bit easier.<br>
TL;DR, here are the best public keytypes for most users:<br>
<b>RSA-3072 or RSA-4096</b>, <b>Ed25519</b> (about equivalent in security to RSA-3072), <b>Ed448</b> and <b>BrainpoolP512r1</b> (not for Protonmail)<br>
<br>
Rationale: RSA is a longly-held standard to the point where it is supported by any modern PGP client. 3000+ is the <a href="https://www.keylength.com/en/8/">current recommended keysize</a> for that. However, most systems use mutliples of 1024, so that really means 3072 or 4906 in practice.<br>
Regarding ECC, the Edwards curves -- Ed25519 and Ed448 -- are recommended for most users, if one has a choice of curves (vs a compliance reason). Indeed, in modern versions of GNU Priavcy Guard, these are at the top of the list for ECC!<br> 
NIST and the German Government each have their own standard curves, so if you're using PGP in a situation like that, the type and perhaps size has already been made for you. There are some concerns raised by<br><a href="https://safecurves.cr.yp.to">Daniel J. Bernstein</a> about the NIST curves and the smaller Brainpool curves. The largest curve, BrainpoolP512r1, is more for individuals who <i>actually</i> need a reliable 512-bit ECC curve which allows for a public key security margin equivalent to AES-256. However there are compatibility issues with Protonmail (which a large population uses), which means you might not want to use it.<br>
Finally, if you're really concerned about quantum computing, then <a href="https://nap.nationalacademies.org/read/25196/chapter/6#98">RSA is a better hedge against it compared to ECC</a>. Then again, GPG will soon support Kyber+ECC in its stable version, 2.6. My position is that I'm more concerned about ID theft than major governments potentially reading my emails via a quantum computer, so ECC is better for my use case (I use BrainpoolP512r1.). 
<h2>Resources</h2>
<h3>Basic</h3>
<a href="https://emailselfdefense.fsf.org">Email Self-Defense webpage</a><br>
<a href="https://www.thunderbird.net">Thunderbird Mail Client</a> (PGP client built-in)<br>
<a href="https://proton.me">ProtonMail</a>
<h3>Intermediate</h3>
<a href="https://www.gpg4win.org/">GPG4Win</a>
<h3>Advanced</h3>
<a href="https://www.gnupg.org/">GNU Privacy Guard</a> (pre-installed on most Linux Systems)
<h3>Guru</h3>
<a href="https://librepgp.org">LibrePGP</a><br>
<a href="https://openpgp.org">OpenPGP</a><br>
<h3>Scientist</h3>
<a href="https://facultyweb.kennesaw.edu/lli13/alg/6823/lm6/AReviewPaperonCryptography.pdf">A Review Paper on Cryptography</a>
