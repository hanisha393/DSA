# DSA
Nandigam Hanisha Chowdary CS21M507 hanisha393@gmail.com Open code in devc++ and execute, 
Input: Give Message to be signed as input.
Output: Signature accepted / rejected
Code takes both numerical and character inputs 
p,q,g are generated randomly
x is generated randomly and y is calculated
Used SHA3-256 hashing algorithm.
Implemented below DSA algo:
1.Key generation:
a.choode p and q such that q|(p-1)
b.Find generator g such g^q modp =1
c.Chooxe random x
d.Calculate y = g^x mod p
e.Publickey(p,q,g,y) privatekey:x
2.Signing
a.Choose random k
b.r = g^k mod p mod q
c.s = ((k_inv(H(m) + xr)modq)
d.send (r,s) pair
3.Verification:
a.w = s_inv mod q
b.u1 = w*H(m) mod q
c.u2 = w*r mod q
d.v = ((g^u1)*(y^u2) mod p)mod q
e. if r==v accept else reject
