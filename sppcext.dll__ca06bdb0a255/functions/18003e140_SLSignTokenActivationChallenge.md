# SLSignTokenActivationChallenge

- ea: `0x18003e140`
- end: `0x18003e555`
- name: `SLSignTokenActivationChallenge`
- size: `1045`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCert@<rcx>, char, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `29`
- tags: ``

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x18000760c`
- `0x180007638`
- `0x180034f88`
- `0x180035540`
- `0x180036618`
- `0x180037398`
- `0x1800390bc`
- `0x180039efc`
- `0x18003ac84`
- `0x18003b004`
- `0x18003b14c`
- `0x18003b530`
- `0x18003b63c`
- `0x18003c464`
- `0x18003cc9c`
- `0x18003e140`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`
- `0x18006ef3a`

## pseudocode

```c
__int64 __fastcall SLSignTokenActivationChallenge(
        PCCERT_CONTEXT pCert,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        _DWORD *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9)
{
  __int64 v13; // rcx
  int v14; // ebx
  int v15; // eax
  __int64 v16; // rdi
  unsigned int v17; // esi
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v23; // [rsp+30h] [rbp-C1h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-BDh] BYREF
  size_t Size; // [rsp+38h] [rbp-B9h] BYREF
  int v26; // [rsp+40h] [rbp-B1h]
  __int64 v27; // [rsp+48h] [rbp-A9h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v29; // [rsp+58h] [rbp-99h] BYREF
  void *Src; // [rsp+60h] [rbp-91h] BYREF
  __int64 v31; // [rsp+68h] [rbp-89h] BYREF
  __int64 v32; // [rsp+70h] [rbp-81h] BYREF
  __int64 v33; // [rsp+78h] [rbp-79h] BYREF
  __int128 v34; // [rsp+80h] [rbp-71h] BYREF
  __int64 v35; // [rsp+90h] [rbp-61h]
  _QWORD v36[18]; // [rsp+A0h] [rbp-51h] BYREF

  memset(v36, 0, 0x48u);
  v33 = 0;
  sub_180043088(qword_180080F58, qword_18008D938);
  v23 = 0;
  v32 = 0;
  v35 = 0;
  v31 = 0;
  v24 = 0;
  Src = 0;
  Size = 0;
  v29 = 0;
  v26 = 0;
  pChainContext = 0;
  v27 = 0;
  v34 = 0;
  if ( !pCert || !a2 )
    goto LABEL_2;
  if ( a3 )
  {
    if ( !a6 || !a7 || !a8 )
      goto LABEL_2;
    if ( !a9 )
    {
      v14 = -2147024809;
      sub_180004CA0(2147942487LL);
      sub_180043900(qword_180083CB8, qword_18008D3A8);
      goto LABEL_41;
    }
    LODWORD(v34) = 24;
    DWORD1(v34) = a5 & 1;
    if ( a4 )
    {
      if ( *(_DWORD *)a4 < 0x18u )
        goto LABEL_2;
      *((_QWORD *)&v34 + 1) = *(_QWORD *)(a4 + 8);
      v35 = *(_QWORD *)(a4 + 16);
    }
    v15 = sub_180039EFC(pCert);
    v14 = v15;
    if ( v15 >= 0 )
    {
      v15 = sub_180036618(pCert);
      v14 = v15;
      if ( v15 >= 0 )
      {
        v15 = sub_1800390BC(v36, a3, a2);
        v14 = v15;
        if ( v15 >= 0 )
        {
          v16 = v36[0];
          if ( v36[0] )
          {
            v14 = 0;
            sub_180043EAC(&dword_180082644, &dword_18008D15C);
            *(_BYTE *)(v16 + 8) = 0;
          }
          else
          {
            v14 = -2147418113;
            sub_180004CA0(2147549183LL);
          }
          sub_180006C10((unsigned int)v14);
          if ( v14 < 0 )
          {
            sub_180042514(qword_180084E50, byte_18008DA58);
LABEL_24:
            v13 = (unsigned int)v14;
            goto LABEL_3;
          }
          if ( v16 )
          {
            v16 = v36[4];
            v14 = 0;
            v17 = v36[5];
          }
          else
          {
            v17 = 0;
            v14 = -2147418113;
            sub_180004CA0(2147549183LL);
          }
          sub_180006C10((unsigned int)v14);
          if ( v14 < 0 )
          {
            sub_180042DB0(byte_180085360, byte_18008E120);
            goto LABEL_24;
          }
          v15 = sub_180037398(v18, v16, v17);
          v14 = v15;
          if ( v15 >= 0 )
          {
            v19 = sub_18003B004(v36, &v33, &v23);
            v14 = v19;
            if ( v19 < 0 )
            {
              sub_180004CA0((unsigned int)v19);
              sub_180043BD8(qword_180081678, qword_18008DEA8);
              goto LABEL_41;
            }
            v20 = sub_18003C464(v32, (unsigned int)&v34, v33, v23, (__int64)&v31, (__int64)&v24);
            v14 = v20;
            if ( v20 < 0 )
            {
              sub_180004CA0((unsigned int)v20);
              sub_18004362C(qword_180083888, qword_18008CC90);
              goto LABEL_41;
            }
            v15 = sub_18003AC84(v36, v31, v24, &Src, &Size);
            v14 = v15;
            if ( v15 >= 0 )
            {
              v15 = sub_18003B530(Src, (unsigned int)Size);
              v14 = v15;
              if ( v15 >= 0 )
              {
                v15 = sub_180035540(pCert);
                v14 = v15;
                if ( v15 >= 0 )
                {
                  v14 = sub_18003CC9C(pChainContext);
                  sub_1800427F4(byte_180082240, &dword_18008CECC);
                  if ( v14 >= 0 )
                  {
                    v14 = sub_18003B63C((__int64)pChainContext, &v27, (_DWORD *)&Size + 1);
                    sub_180042ACC(qword_1800851C8, qword_18008DF40);
                    if ( v14 >= 0 )
                    {
                      v21 = v27;
                      v27 = 0;
                      *a9 = v21;
                      *a8 = HIDWORD(Size);
                      *a7 = v29;
                      *a6 = v26;
                      v29 = 0;
                      goto LABEL_41;
                    }
                  }
                  goto LABEL_24;
                }
              }
            }
          }
        }
      }
    }
    v13 = (unsigned int)v15;
    goto LABEL_3;
  }
  sub_180043364(qword_1800818A0, qword_18008E038);
LABEL_2:
  v13 = 2147942487LL;
  v14 = -2147024809;
LABEL_3:
  sub_180004CA0(v13);
LABEL_41:
  sub_180006C10((unsigned int)v14);
  sub_180007638(&v27);
  sub_18003B14C(&pChainContext);
  sub_180007638(&v29);
  sub_180007638(&Src);
  sub_180007638(&v31);
  sub_180034F88(&v32);
  sub_18000760C(v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003e140  push    rbp
0x18003e142  push    rbx
0x18003e143  push    rsi
0x18003e144  push    rdi
0x18003e145  push    r12
0x18003e147  push    r13
0x18003e149  push    r14
0x18003e14b  push    r15
0x18003e14d  lea     rbp, [rsp-7]
0x18003e152  sub     rsp, 0F8h
0x18003e159  mov     esi, edx
0x18003e15b  mov     rdi, r8
0x18003e15e  xor     edx, edx; Val
0x18003e160  mov     r13, rcx
0x18003e163  lea     rcx, [rbp+3Fh+var_90]; void *
0x18003e167  mov     rbx, r9
0x18003e16a  lea     r8d, [rdx+48h]; Size
0x18003e16e  call    memset
0x18003e173  lea     rdx, qword_18008D938
0x18003e17a  mov     [rbp+3Fh+var_B8], 0
0x18003e182  lea     rcx, qword_180080F58
0x18003e189  call    sub_180043088
0x18003e18e  xor     ecx, ecx
0x18003e190  xor     eax, eax
0x18003e192  mov     [rsp+130h+var_100], ecx
0x18003e196  xorps   xmm0, xmm0
0x18003e199  mov     [rbp+3Fh+arg_0], ecx
0x18003e19c  mov     [rsp+130h+var_C0], rcx
0x18003e1a1  mov     [rbp+3Fh+var_A0], rax
0x18003e1a5  mov     [rsp+130h+var_C8], rcx
0x18003e1aa  mov     [rsp+130h+var_FC], ecx
0x18003e1ae  mov     [rsp+130h+Src], rcx
0x18003e1b3  mov     dword ptr [rsp+130h+Size], ecx
0x18003e1b7  mov     [rsp+130h+var_D8], rcx
0x18003e1bc  mov     [rsp+130h+var_F0], ecx
0x18003e1c0  mov     [rsp+130h+pChainContext], rcx
0x18003e1c5  mov     [rsp+130h+var_E8], rcx
0x18003e1ca  mov     dword ptr [rsp+130h+Size+4], ecx
0x18003e1ce  movups  [rbp+3Fh+var_B0], xmm0
0x18003e1d2  test    r13, r13
0x18003e1d5  jnz     short loc_18003E1E8
0x18003e1d7  mov     ecx, 80070057h
0x18003e1dc  mov     ebx, ecx
0x18003e1de  call    sub_180004CA0
0x18003e1e3  jmp     loc_18003E4F3
0x18003e1e8  test    esi, esi
0x18003e1ea  jz      short loc_18003E1D7
0x18003e1ec  test    rdi, rdi
0x18003e1ef  jnz     short loc_18003E206
0x18003e1f1  lea     rdx, qword_18008E038
0x18003e1f8  lea     rcx, qword_1800818A0
0x18003e1ff  call    sub_180043364
0x18003e204  jmp     short loc_18003E1D7
0x18003e206  mov     r14, [rbp+3Fh+arg_28]
0x18003e20a  test    r14, r14
0x18003e20d  jz      short loc_18003E1D7
0x18003e20f  mov     r15, [rbp+3Fh+arg_30]
0x18003e213  test    r15, r15
0x18003e216  jz      short loc_18003E1D7
0x18003e218  mov     r12, [rbp+3Fh+arg_38]
0x18003e21f  test    r12, r12
0x18003e222  jz      short loc_18003E1D7
0x18003e224  cmp     [rbp+3Fh+arg_40], rcx
0x18003e22b  jnz     short loc_18003E251
0x18003e22d  mov     ecx, 80070057h
0x18003e232  mov     ebx, ecx
0x18003e234  call    sub_180004CA0
0x18003e239  lea     rdx, qword_18008D3A8
0x18003e240  lea     rcx, qword_180083CB8
0x18003e247  call    sub_180043900
0x18003e24c  jmp     loc_18003E4F3
0x18003e251  movzx   eax, [rbp+3Fh+arg_20]
0x18003e255  and     eax, 1
0x18003e258  mov     dword ptr [rbp+3Fh+var_B0], 18h
0x18003e25f  mov     dword ptr [rbp+3Fh+var_B0+4], eax
0x18003e262  test    rbx, rbx
0x18003e265  jz      short loc_18003E280
0x18003e267  cmp     dword ptr [rbx], 18h
0x18003e26a  jb      loc_18003E1D7
0x18003e270  mov     rax, [rbx+8]
0x18003e274  mov     qword ptr [rbp+3Fh+var_B0+8], rax
0x18003e278  mov     rax, [rbx+10h]
0x18003e27c  mov     [rbp+3Fh+var_A0], rax
0x18003e280  lea     rdx, [rbp+3Fh+arg_0]
0x18003e284  mov     rcx, r13; pCert
0x18003e287  call    sub_180039EFC
0x18003e28c  mov     ebx, eax
0x18003e28e  test    eax, eax
0x18003e290  jns     short loc_18003E299
0x18003e292  mov     ecx, eax
0x18003e294  jmp     loc_18003E1DE
0x18003e299  lea     rdx, [rsp+130h+var_C0]
0x18003e29e  mov     rcx, r13; pCertContext
0x18003e2a1  call    sub_180036618
0x18003e2a6  mov     ebx, eax
0x18003e2a8  test    eax, eax
0x18003e2aa  js      short loc_18003E292
0x18003e2ac  mov     r8d, esi
0x18003e2af  lea     rcx, [rbp+3Fh+var_90]
0x18003e2b3  mov     rdx, rdi
0x18003e2b6  call    sub_1800390BC
0x18003e2bb  mov     ebx, eax
0x18003e2bd  test    eax, eax
0x18003e2bf  js      short loc_18003E292
0x18003e2c1  mov     rdi, [rbp+3Fh+var_90]
0x18003e2c5  mov     eax, 8000FFFFh
0x18003e2ca  test    rdi, rdi
0x18003e2cd  jnz     short loc_18003E2DA
0x18003e2cf  mov     ecx, eax
0x18003e2d1  mov     ebx, eax
0x18003e2d3  call    sub_180004CA0
0x18003e2d8  jmp     short loc_18003E2F8
0x18003e2da  lea     rdx, dword_18008D15C
0x18003e2e1  xor     ebx, ebx
0x18003e2e3  lea     rcx, dword_180082644
0x18003e2ea  call    sub_180043EAC
0x18003e2ef  cmp     [rbp+3Fh+arg_0], ebx
0x18003e2f2  setnz   al
0x18003e2f5  mov     [rdi+8], al
0x18003e2f8  mov     ecx, ebx
0x18003e2fa  call    sub_180006C10
0x18003e2ff  test    ebx, ebx
0x18003e301  jns     short loc_18003E31D
0x18003e303  lea     rdx, byte_18008DA58
0x18003e30a  lea     rcx, qword_180084E50
0x18003e311  call    sub_180042514
0x18003e316  mov     ecx, ebx
0x18003e318  jmp     loc_18003E1DE
0x18003e31d  test    rdi, rdi
0x18003e320  jnz     short loc_18003E332
0x18003e322  mov     ecx, 8000FFFFh
0x18003e327  xor     esi, esi
0x18003e329  mov     ebx, ecx
0x18003e32b  call    sub_180004CA0
0x18003e330  jmp     short loc_18003E33B
0x18003e332  mov     rdi, [rbp+3Fh+var_70]
0x18003e336  xor     ebx, ebx
0x18003e338  mov     esi, [rbp+3Fh+var_68]
0x18003e33b  mov     ecx, ebx
0x18003e33d  call    sub_180006C10
0x18003e342  test    ebx, ebx
0x18003e344  jns     short loc_18003E35B
0x18003e346  lea     rdx, byte_18008E120
0x18003e34d  lea     rcx, byte_180085360
0x18003e354  call    sub_180042DB0
0x18003e359  jmp     short loc_18003E316
0x18003e35b  mov     r8d, esi
0x18003e35e  mov     rdx, rdi
0x18003e361  call    sub_180037398
0x18003e366  mov     ebx, eax
0x18003e368  test    eax, eax
0x18003e36a  js      loc_18003E292
0x18003e370  lea     r8, [rsp+130h+var_100]
0x18003e375  lea     rdx, [rbp+3Fh+var_B8]
0x18003e379  lea     rcx, [rbp+3Fh+var_90]
0x18003e37d  call    sub_18003B004
0x18003e382  mov     ebx, eax
0x18003e384  test    eax, eax
0x18003e386  jns     short loc_18003E3A7
0x18003e388  mov     ecx, eax
0x18003e38a  call    sub_180004CA0
0x18003e38f  lea     rdx, qword_18008DEA8
0x18003e396  lea     rcx, qword_180081678
0x18003e39d  call    sub_180043BD8
0x18003e3a2  jmp     loc_18003E4F3
0x18003e3a7  mov     r9d, [rsp+130h+var_100]
0x18003e3ac  lea     rax, [rsp+130h+var_FC]
0x18003e3b1  mov     r8, [rbp+3Fh+var_B8]
0x18003e3b5  lea     rdx, [rbp+3Fh+var_B0]
0x18003e3b9  mov     rcx, [rsp+130h+var_C0]
0x18003e3be  mov     [rsp+130h+var_108], rax
0x18003e3c3  lea     rax, [rsp+130h+var_C8]
0x18003e3c8  mov     [rsp+130h+var_110], rax
0x18003e3cd  call    sub_18003C464
0x18003e3d2  mov     ebx, eax
0x18003e3d4  test    eax, eax
0x18003e3d6  jns     short loc_18003E3F7
0x18003e3d8  mov     ecx, eax
0x18003e3da  call    sub_180004CA0
0x18003e3df  lea     rdx, qword_18008CC90
0x18003e3e6  lea     rcx, qword_180083888
0x18003e3ed  call    sub_18004362C
0x18003e3f2  jmp     loc_18003E4F3
0x18003e3f7  mov     r8d, [rsp+130h+var_FC]
0x18003e3fc  lea     rax, [rsp+130h+Size]
0x18003e401  mov     rdx, [rsp+130h+var_C8]
0x18003e406  lea     r9, [rsp+130h+Src]
0x18003e40b  lea     rcx, [rbp+3Fh+var_90]
0x18003e40f  mov     [rsp+130h+var_110], rax
0x18003e414  call    sub_18003AC84
0x18003e419  mov     ebx, eax
0x18003e41b  test    eax, eax
0x18003e41d  js      loc_18003E292
0x18003e423  mov     edx, dword ptr [rsp+130h+Size]; Size
0x18003e427  lea     r9, [rsp+130h+var_F0]
0x18003e42c  mov     rcx, [rsp+130h+Src]; Src
0x18003e431  lea     r8, [rsp+130h+var_D8]
0x18003e436  call    sub_18003B530
0x18003e43b  mov     ebx, eax
0x18003e43d  test    eax, eax
0x18003e43f  js      loc_18003E292
0x18003e445  xor     r8d, r8d
0x18003e448  lea     r9, [rsp+130h+pChainContext]
0x18003e44d  mov     rcx, r13; pCertContext
0x18003e450  lea     edx, [r8+1]
0x18003e454  call    sub_180035540
0x18003e459  mov     ebx, eax
0x18003e45b  test    eax, eax
0x18003e45d  js      loc_18003E292
0x18003e463  mov     rcx, [rsp+130h+pChainContext]; pChainContext
0x18003e468  call    sub_18003CC9C
0x18003e46d  lea     rdx, dword_18008CECC
0x18003e474  mov     ebx, eax
0x18003e476  lea     rcx, byte_180082240
0x18003e47d  call    sub_1800427F4
0x18003e482  test    ebx, ebx
0x18003e484  js      loc_18003E316
0x18003e48a  mov     rcx, [rsp+130h+pChainContext]
0x18003e48f  lea     r8, [rsp+130h+Size+4]
0x18003e494  lea     rdx, [rsp+130h+var_E8]
0x18003e499  call    sub_18003B63C
0x18003e49e  lea     rdx, qword_18008DF40
0x18003e4a5  mov     ebx, eax
0x18003e4a7  lea     rcx, qword_1800851C8
0x18003e4ae  call    sub_180042ACC
0x18003e4b3  test    ebx, ebx
0x18003e4b5  js      loc_18003E316
0x18003e4bb  mov     rax, [rsp+130h+var_E8]
0x18003e4c0  mov     rcx, [rbp+3Fh+arg_40]
0x18003e4c7  mov     [rsp+130h+var_E8], 0
0x18003e4d0  mov     [rcx], rax
0x18003e4d3  mov     eax, dword ptr [rsp+130h+Size+4]
0x18003e4d7  mov     [r12], eax
0x18003e4db  mov     rax, [rsp+130h+var_D8]
0x18003e4e0  mov     [r15], rax
0x18003e4e3  mov     eax, [rsp+130h+var_F0]
0x18003e4e7  mov     [r14], eax
0x18003e4ea  mov     [rsp+130h+var_D8], 0
0x18003e4f3  mov     ecx, ebx
0x18003e4f5  call    sub_180006C10
0x18003e4fa  lea     rcx, [rsp+130h+var_E8]
0x18003e4ff  call    sub_180007638
0x18003e504  lea     rcx, [rsp+130h+pChainContext]
0x18003e509  call    sub_18003B14C
0x18003e50e  lea     rcx, [rsp+130h+var_D8]
0x18003e513  call    sub_180007638
0x18003e518  lea     rcx, [rsp+130h+Src]
0x18003e51d  call    sub_180007638
0x18003e522  lea     rcx, [rsp+130h+var_C8]
0x18003e527  call    sub_180007638
0x18003e52c  lea     rcx, [rsp+130h+var_C0]
0x18003e531  call    sub_180034F88
0x18003e536  lea     rcx, [rbp+3Fh+var_90]
0x18003e53a  call    sub_18000760C
0x18003e53f  mov     eax, ebx
0x18003e541  add     rsp, 0F8h
0x18003e548  pop     r15
0x18003e54a  pop     r14
0x18003e54c  pop     r13
0x18003e54e  pop     r12
0x18003e550  pop     rdi
0x18003e551  pop     rsi
0x18003e552  pop     rbx
0x18003e553  pop     rbp
0x18003e554  retn
```
