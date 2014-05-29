Linux-Shadow-style-passwd-script
================================

Creates a Linux /etc/shadow compatible salted hash of a string

From http://serverfault.com/questions/330069/how-to-create-an-sha-512-hashed-password-for-shadow:

Here's a one liner:

python -c 'import crypt; print crypt.crypt("test", "$6$random_salt")'
6 is the type of hash for SHA-512

1 -> MD5
2a -> Blowfish (not in mainline glibc; added in some Linux distributions)
5 -> SHA-256 (since glibc 2.7)
6 -> SHA-512 (since glibc 2.7)
I'd recommend you look up what salts are and such and as per smallclamgers comment the difference between encryption and hashing.

Update: The string produced is suitable for shadow and kickstart scripts.

answered Nov 11 '11 at 11:29
davey
