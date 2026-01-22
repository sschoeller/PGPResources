# PGPResources
Resources for Pretty Good Privacy
<br>
<h1>Intro</h1>
If you've landed on this repo, I've assumed you've done your research on PGP/GPG; otherwise, please read the starred sections in <a href="#resources">"Resources"</a>. I have some advice here, combined with links (and my global configuration files) to make your journey into it a bit easier.<br>
<h1>Recommended Keytypes</h1>
Based on information from respected researchers and raw information about PGP clients, here are the best public keytypes for most users:<br>
<b>RSA-3072 or RSA-4096</b>, <b>Ed25519</b> (about equivalent in security to RSA-3072), <b>Ed448</b> and <b>BrainpoolP512r1</b> (not for ProtonMail)<br>
<h2>Rationale for Keytypes</h2>
RSA is a longly-held standard to the point where it is supported by any modern PGP client. 3000+ is the <a href="https://www.keylength.com/en/8">current recommended keysize</a> for that. However, most systems use mutliples of 1024, so that really means 3072 or 4096 in practice.<br>
Regarding ECC, the Edwards curves -- Ed25519 and Ed448 -- are recommended for most users, if one has a choice of curves (vs a compliance reason). Ed25519 is similar in cryptanalytic strength (by classical computers) to RSA-3072, but with a smaller key size. Ed448 exceeds RSA-4096 by a large margin. Indeed, in modern versions of GNU Priavcy Guard, these are at the top of the list for ECC! The primary disadvantage of Edwards curves is that most PGP smartcards don't support them (Yubikey 5 currently supports Ed25519). The original PGP program, now called <a href="https://techdocs.broadcom.com/us/en/symantec-security-software/information-security/pgp-solutions/11-0-1.html">PGP Command Line</a>, supports less ECC algorithms than the others (namely GPG and ProtonMail). That program seems to be geared towards corporations vs individuals, though.<br> 
NIST and BSI (German Government) each have their own standard curves, so if you're using PGP in a situation like that, the type and perhaps size has already been made for you. There are some concerns raised by<br><a href="https://safecurves.cr.yp.to">Daniel J. Bernstein</a> about the NIST curves and the smaller Brainpool curves. The largest Brainpool curve, BrainpoolP512r1, is more for individuals who <i>actually</i> need a reliable 512-bit ECC curve which allows for a public key security margin equivalent to AES-256. However there are compatibility issues with ProtonMail (which a large population uses), which means you might not want to use it.<br>
Finally, if you're really concerned about quantum computing, then <a href="https://nap.nationalacademies.org/read/25196/chapter/6#98">RSA is a better hedge against it compared to ECC</a>. Then again, GPG just supported <a href="https://pq-crystals.org/kyber">Kyber</a>+ECC in its newest stable version, 2.5.16. My position is that I'm more concerned about ID theft than major governments potentially reading my emails via a quantum computer, so ECC is better for my use case (<a href="https://github.com/sschoeller/PGPResources/blob/main/sschoeller8080.asc">I use BrainpoolP512r1</a>.). 
<h1>Rationale for AES</h1>
Why is AES preferred? <a href="https://competitions.cr.yp.to/aes.html">AES was standardized via an open competiton</a> near the turn of the last century -- <a href="https://www.schneier.com/essays/archives/2022/08/nists-post-quantum-cryptography-standards-competition.html">just like Kyber in recent years</a> -- and most cryptographers prefer it to this day over other symmetric encryption schemes. In particular, AES-256 is the &quot;gold standard&quot; of encryption.
<h1>Rationale for SHA-2/3</h1>
<a href="https://www.nist.gov/news-events/news/2022/12/nist-retires-sha-1-cryptographic-algorithm">SHA-1 will be not be allowed by NIST</a> (for US Govenment use) as of 2030. RIPEMD-160 is the same size as SHA-1. The newer, safe generations of hash algorithms are SHA-2 (SHA-224, SHA-256, SHA-384, SHA-512) and SHA-3.
<h1>Resources</h1>
<h3>Basic*</h3>
<a href="https://emailselfdefense.fsf.org">Email Self-Defense webpage</a><br>
<a href="https://www.thunderbird.net">Thunderbird Mail Client</a> (PGP client built-in)<br>
<a href="https://proton.me">ProtonMail</a>
<h3>Intermediate*</h3>
<a href="https://www.gpg4win.org">GPG4Win</a><br>
<a href="https://gnupg.org/faq/gnupg-faq.html#glossary">Glossary of GPG FAQ</a>
<h3>Advanced</h3>
<a href="https://www.gnupg.org/documentation/manuals/gnupg/GPG-Options.html">GPG Options</a>
<h3>Guru</h3>
<a href="https://librepgp.org">LibrePGP</a><br>
<a href="https://openpgp.org">OpenPGP</a><br>
<h3>Scientist</h3>
<a href="https://facultyweb.kennesaw.edu/lli13/alg/6823/lm6/AReviewPaperonCryptography.pdf">A Review Paper on Cryptography</a><br>
<a href="https://eprint.iacr.org/2015/625.pdf">Ed448-Goldilocks, a new elliptic curve</a><br>
<a href="https://www.nist.gov/pqcrypto">NIST Post-Quantum Cryptography Standards</a>
