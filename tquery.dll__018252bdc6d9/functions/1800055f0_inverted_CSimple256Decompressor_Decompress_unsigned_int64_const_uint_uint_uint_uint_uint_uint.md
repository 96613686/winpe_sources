# inverted::CSimple256Decompressor::Decompress(unsigned __int64 const *,uint,uint,uint *,uint *,uint,uint *)

- ea: `0x1800055f0`
- end: `0x180024310`
- name: `?Decompress@CSimple256Decompressor@inverted@@UEAA_NPEB_KIIPEAI1I1@Z`
- size: `126240`
- prototype: `bool __fastcall(inverted::CSimple256Decompressor *__hidden this, const unsigned __int64 *, unsigned int, unsigned int, unsigned int *, unsigned int *Src, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800055f0`
- `0x180038f08`
- `0x180038f28`
- `0x18015708c`
- `0x18018e8cb`
- `0x1802c0010`

## string_xrefs

- `0x18001b724`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x18001b740`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022d53`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022d69`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022d8c`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022da2`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022dc5`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022ddb`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022dfe`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022e14`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022e37`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022e4d`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022e70`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022e86`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022ea9`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022ebf`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022ee2`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`
- `0x180022ef8`: `onecoreuap\base\appmodel\search\tquery\inverted\simple256decompressor.cpp`

## pseudocode

```c

```

## disassembly

```asm
0x1800055f0  mov     rax, rsp
0x1800055f3  sub     rsp, 78h
0x1800055f7  test    r8d, r8d
0x1800055fa  jz      loc_18001B710
0x180005600  mov     ecx, [rsp+78h+arg_30]
0x180005607  lea     r11, [rdx+8]
0x18000560b  mov     [rax+8], rbx
0x18000560f  mov     rbx, [rsp+78h+Src]
0x180005617  mov     [rax+10h], rbp
0x18000561b  mov     [rax+20h], rsi
0x18000561f  mov     [rax-8], rdi
0x180005623  mov     [rax-10h], r12
0x180005627  lea     r10, [rbx+rcx*4]
0x18000562b  mov     [rax-18h], r13
0x18000562f  lea     r12, qword_1802DCBA0
0x180005636  mov     [rax-20h], r14
0x18000563a  mov     [rax-28h], r15
0x18000563e  lea     eax, [r8-1]
0x180005642  lea     rbp, [r11+rax*8]
0x180005646  mov     [rsp+78h+var_38], r11
0x18000564b  mov     eax, r9d
0x18000564e  lea     r15, __ImageBase
0x180005655  mov     [rsp+78h+var_30], rbx
0x18000565a  mov     [rsp+78h+var_48], r10
0x18000565f  lea     rdi, [r11+rax*8]
0x180005663  mov     eax, 86186187h
0x180005668  lea     r13, qword_1802DCAA0
0x18000566f  mul     ecx
0x180005671  mov     r9, 800000000000h
0x18000567b  sub     ecx, edx
0x18000567d  shr     ecx, 1
0x18000567f  add     ecx, edx
0x180005681  shr     ecx, 7
0x180005684  test    ecx, ecx
0x180005686  jz      loc_180007418
0x18000568c  cmp     rdi, rbp
0x18000568f  jnb     loc_180007418
0x180005695  lea     r14, [rdi+rcx*8]
0x180005699  cmp     rbp, r14
0x18000569c  cmovb   r14, rbp
0x1800056a0  mov     rsi, [rdi]
0x1800056a3  mov     r8, rdi
0x1800056a6  mov     rax, rsi
0x1800056a9  add     rdi, 8
0x1800056ad  shr     rax, 38h
0x1800056b1  mov     edx, eax
0x1800056b3  sub     edx, 0FEh
0x1800056b9  jz      loc_180006E12
0x1800056bf  cmp     edx, 1
0x1800056c2  jz      loc_180005780
0x1800056c8  cmp     eax, 0F5h
0x1800056cd  jz      short loc_180005739
0x1800056cf  movsxd  rcx, eax
0x1800056d2  mov     eax, ds:(jpt_1800056DD - 180000000h)[r15+rcx*4]; switch 256 cases
0x1800056da  add     rax, r15
0x1800056dd  jmp     rax; switch jump
0x1800056df  mov     rax, rsi; jumptable 00000001800056DD case 74
0x1800056e2  shr     rax, 30h
0x1800056e6  movzx   eax, al
0x1800056e9  mov     [rbx], eax
0x1800056eb  mov     rax, rsi
0x1800056ee  shr     rax, 28h
0x1800056f2  movzx   eax, al
0x1800056f5  mov     [rbx+4], eax
0x1800056f8  mov     rax, rsi
0x1800056fb  shr     rax, 20h
0x1800056ff  movzx   eax, al
0x180005702  mov     [rbx+8], eax
0x180005705  mov     rax, rsi
0x180005708  shr     rax, 18h
0x18000570c  movzx   eax, al
0x18000570f  mov     [rbx+0Ch], eax
0x180005712  mov     rax, rsi
0x180005715  shr     rax, 10h
0x180005719  movzx   eax, al
0x18000571c  mov     [rbx+10h], eax
0x18000571f  mov     rax, rsi
0x180005722  shr     rax, 8
0x180005726  movzx   eax, al
0x180005729  mov     [rbx+14h], eax
0x18000572c  movzx   eax, sil
0x180005730  mov     [rbx+18h], eax
0x180005733  add     rbx, 1Ch
0x180005737  jmp     short loc_180005763; jumptable 00000001800056DD case 245
0x180005739  mov     rax, rsi
0x18000573c  shr     rax, 25h
0x180005740  and     eax, 7FFFFh
0x180005745  mov     [rbx], eax
0x180005747  mov     rax, rsi
0x18000574a  shr     rax, 12h
0x18000574e  and     eax, 7FFFFh
0x180005753  and     esi, 3FFFFh
0x180005759  mov     [rbx+4], eax
0x18000575c  mov     [rbx+8], esi
0x18000575f  add     rbx, 0Ch
0x180005763  cmp     rdi, r14; jumptable 00000001800056DD case 245
0x180005766  jb      loc_1800056A0
0x18000576c  mov     r11, [rsp+78h+var_38]
0x180005771  mov     rcx, r10
0x180005774  sub     rcx, rbx
0x180005777  sar     rcx, 2
0x18000577b  jmp     loc_180005663
0x180005780  mov     rax, rsi
0x180005783  mov     r9, rdi
0x180005786  shr     rax, 2Eh
0x18000578a  and     eax, 3FFh
0x18000578f  lea     rax, ds:10h[rax*8]
0x180005797  sub     r9, rax
0x18000579a  cmp     r9, r11
0x18000579d  jb      loc_180022DF3
0x1800057a3  mov     r9, [r9]
0x1800057a6  mov     rax, r9
0x1800057a9  shr     rax, 38h
0x1800057ad  cmp     eax, 0F5h
0x1800057b2  jz      short loc_180005823
0x1800057b4  cdqe
0x1800057b6  mov     rdx, rbx
0x1800057b9  mov     ecx, ds:(jpt_1800057C4 - 180000000h)[r15+rax*4]; switch 256 cases
0x1800057c1  add     rcx, r15
0x1800057c4  jmp     rcx; switch jump
0x1800057c6  lea     rdx, [rbx+8]; jumptable 00000001800057C4 case 74
0x1800057ca  mov     rax, r9
0x1800057cd  shr     rax, 30h
0x1800057d1  movzx   eax, al
0x1800057d4  mov     [rbx], eax
0x1800057d6  mov     rax, r9
0x1800057d9  shr     rax, 28h
0x1800057dd  movzx   eax, al
0x1800057e0  mov     [rbx+4], eax
0x1800057e3  mov     rax, r9
0x1800057e6  shr     rax, 20h
0x1800057ea  movzx   eax, al
0x1800057ed  mov     [rdx], eax
0x1800057ef  mov     rax, r9
0x1800057f2  shr     rax, 18h
0x1800057f6  movzx   eax, al
0x1800057f9  mov     [rdx+4], eax
0x1800057fc  mov     rax, r9
0x1800057ff  shr     rax, 10h
0x180005803  movzx   eax, al
0x180005806  mov     [rdx+8], eax
0x180005809  mov     rax, r9
0x18000580c  shr     rax, 8
0x180005810  movzx   eax, al
0x180005813  mov     [rdx+0Ch], eax
0x180005816  movzx   eax, r9b
0x18000581a  mov     [rdx+10h], eax
0x18000581d  add     rdx, 14h
0x180005821  jmp     short loc_180005852; jumptable 00000001800057C4 case 245
0x180005823  mov     rax, r9
0x180005826  shr     rax, 25h
0x18000582a  and     eax, 7FFFFh
0x18000582f  mov     [rbx], eax
0x180005831  mov     rax, r9
0x180005834  shr     rax, 12h
0x180005838  and     eax, 7FFFFh
0x18000583d  and     r9d, 3FFFFh
0x180005844  lea     rdx, [rbx+8]
0x180005848  mov     [rbx+4], eax
0x18000584b  mov     [rdx], r9d
0x18000584e  add     rdx, 4
0x180005852  shl     rsi, 12h; jumptable 00000001800057C4 case 245
0x180005856  lea     rax, [rdx+2A0h]
0x18000585d  cmp     rax, r10
0x180005860  ja      loc_180022D38
0x180005866  mov     r8, rsi
0x180005869  shr     r8, 38h
0x18000586d  cmp     r8d, 0F5h
0x180005874  jz      short loc_1800058E6
0x180005876  movsxd  rax, r8d
0x180005879  mov     rbx, rdx
0x18000587c  mov     ecx, ds:(jpt_180005887 - 180000000h)[r15+rax*4]; switch 256 cases
0x180005884  add     rcx, r15
0x180005887  jmp     rcx; switch jump
0x180005889  lea     rbx, [rdx+8]; jumptable 0000000180005887 case 74
0x18000588d  mov     rax, rsi
0x180005890  shr     rax, 30h
0x180005894  movzx   eax, al
0x180005897  mov     [rdx], eax
0x180005899  mov     rax, rsi
0x18000589c  shr     rax, 28h
0x1800058a0  movzx   eax, al
0x1800058a3  mov     [rdx+4], eax
0x1800058a6  mov     rax, rsi
0x1800058a9  shr     rax, 20h
0x1800058ad  movzx   eax, al
0x1800058b0  mov     [rbx], eax
0x1800058b2  mov     rax, rsi
0x1800058b5  shr     rax, 18h
0x1800058b9  movzx   eax, al
0x1800058bc  mov     [rbx+4], eax
0x1800058bf  mov     rax, rsi
0x1800058c2  shr     rax, 10h
0x1800058c6  movzx   eax, al
0x1800058c9  mov     [rbx+8], eax
0x1800058cc  mov     rax, rsi
0x1800058cf  shr     rax, 8
0x1800058d3  movzx   eax, al
0x1800058d6  mov     [rbx+0Ch], eax
0x1800058d9  movzx   eax, sil
0x1800058dd  mov     [rbx+10h], eax
0x1800058e0  add     rbx, 14h
0x1800058e4  jmp     short loc_180005913; jumptable 0000000180005887 case 245
0x1800058e6  mov     rax, rsi
0x1800058e9  shr     rax, 25h
0x1800058ed  and     eax, 7FFFFh
0x1800058f2  mov     [rdx], eax
0x1800058f4  mov     rax, rsi
0x1800058f7  shr     rax, 12h
0x1800058fb  and     eax, 7FFFFh
0x180005900  and     esi, 3FFFFh
0x180005906  lea     rbx, [rdx+8]
0x18000590a  mov     [rdx+4], eax
0x18000590d  mov     [rbx], esi
0x18000590f  add     rbx, 4
0x180005913  mov     eax, r8d; jumptable 0000000180005887 case 245
0x180005916  sub     r14, 8
0x18000591a  movzx   ecx, byte ptr [rax+r15+3189E0h]
0x180005923  shl     rcx, 2
0x180005927  mov     r9, 800000000000h
0x180005931  sub     rbx, rcx
0x180005934  jmp     loc_180005763; jumptable 00000001800056DD case 245
0x180005939  mov     rax, rsi; jumptable 00000001800056DD case 174
0x18000593c  shr     rax, 2Eh
0x180005940  and     eax, 3FFh
0x180005945  mov     [rbx], eax
0x180005947  mov     rax, rsi
0x18000594a  shr     rax, 24h
0x18000594e  and     eax, 3FFh
0x180005953  mov     [rbx+4], eax
0x180005956  mov     rax, rsi
0x180005959  shr     rax, 1Ah
0x18000595d  and     eax, 3FFh
0x180005962  mov     [rbx+8], eax
0x180005965  mov     rax, rsi
0x180005968  shr     rax, 10h
0x18000596c  and     eax, 3FFh
0x180005971  mov     [rbx+0Ch], eax
0x180005974  movzx   eax, si
0x180005977  mov     [rbx+10h], eax
0x18000597a  add     rbx, 14h
0x18000597e  jmp     loc_180005763; jumptable 00000001800056DD case 245
0x180005983  mov     rax, rsi; jumptable 00000001800056DD case 153
0x180005986  shr     rax, 30h
0x18000598a  movzx   eax, al
0x18000598d  mov     [rbx], eax
0x18000598f  mov     rax, rsi
0x180005992  shr     rax, 28h
0x180005996  movzx   eax, al
0x180005999  mov     [rbx+4], eax
0x18000599c  mov     rax, rsi
0x18000599f  shr     rax, 22h
0x1800059a3  and     eax, 3Fh
0x1800059a6  mov     [rbx+8], eax
0x1800059a9  mov     rax, rsi
0x1800059ac  shr     rax, 11h
0x1800059b0  and     eax, 1FFFFh
0x1800059b5  and     esi, 1FFFFh
0x1800059bb  mov     [rbx+0Ch], eax
0x1800059be  mov     [rbx+10h], esi
0x1800059c1  add     rbx, 14h
0x1800059c5  jmp     loc_180005763; jumptable 00000001800056DD case 245
0x1800059ca  mov     rax, rsi; jumptable 00000001800056DD case 108
0x1800059cd  shr     rax, 29h
0x1800059d1  and     eax, 7FFFh
0x1800059d6  mov     [rbx], eax
0x1800059d8  mov     rax, rsi
0x1800059db  shr     rax, 21h
0x1800059df  movzx   eax, al
0x1800059e2  mov     [rbx+4], eax
0x1800059e5  mov     rax, rsi
0x1800059e8  shr     rax, 19h
0x1800059ec  movzx   eax, al
0x1800059ef  mov     [rbx+8], eax
0x1800059f2  mov     rax, rsi
0x1800059f5  shr     rax, 11h
0x1800059f9  movzx   eax, al
0x1800059fc  mov     [rbx+0Ch], eax
0x1800059ff  mov     rax, rsi
0x180005a02  shr     rax, 9
0x180005a06  movzx   eax, al
0x180005a09  and     esi, 1FFh
0x180005a0f  mov     [rbx+10h], eax
0x180005a12  mov     [rbx+14h], esi
0x180005a15  add     rbx, 18h
0x180005a19  jmp     loc_180005763; jumptable 00000001800056DD case 245
0x180005a1e  mov     rax, rsi; jumptable 00000001800056DD case 179
0x180005a21  shr     rax, 29h
0x180005a25  and     eax, 7FFFh
0x180005a2a  mov     [rbx], eax
0x180005a2c  mov     rax, rsi
0x180005a2f  shr     rax, 1Ah
0x180005a33  and     eax, 7FFFh
0x180005a38  mov     [rbx+4], eax
0x180005a3b  mov     rax, rsi
0x180005a3e  shr     rax, 12h
0x180005a42  movzx   eax, al
0x180005a45  mov     [rbx+8], eax
0x180005a48  mov     rax, rsi
0x180005a4b  shr     rax, 0Ah
  ... truncated ...
```
