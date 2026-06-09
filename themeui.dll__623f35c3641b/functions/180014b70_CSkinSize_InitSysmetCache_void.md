# CSkinSize::_InitSysmetCache(void)

- ea: `0x180014b70`
- end: `0x180014e30`
- name: `?_InitSysmetCache@CSkinSize@@AEAAXXZ`
- size: `704`
- prototype: `void __fastcall(CSkinSize *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800146e0`
- `0x180014960`
- `0x180014a50`

## callees

- `0x180014b70`
- `0x1800358c0`
- `0x18003633c`

## import_xrefs

- `USER32!GetSysColor` at `0x180014beb`
- `USER32!GetSysColor` at `0x180014beb`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014c29`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014df0`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014e03`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014c29`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014df0`
- `UxTheme!__imp_ClassicSystemParametersInfoW` at `0x180014e03`

## pseudocode

```c
void __fastcall CSkinSize::_InitSysmetCache(CSkinSize *this)
{
  int v2; // edi
  DWORD SysColor; // eax
  __int64 v4; // rcx
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  int v7; // eax
  __int128 v8; // xmm0
  int v9; // eax
  __int128 v10; // xmm1
  int v11; // eax
  __int128 v12; // xmm0
  int v13; // eax
  __int128 v14; // xmm1
  int v15; // eax
  __int128 v16; // xmm0
  int v17; // eax
  __int128 v18; // xmm1
  int v19; // eax
  __int128 v20; // xmm0
  int v21; // eax
  __int128 v22; // xmm1
  int v23; // eax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  int v42; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v43[5]; // [rsp+24h] [rbp-DCh] BYREF
  __int128 v44; // [rsp+38h] [rbp-C8h]
  __int128 v45; // [rsp+48h] [rbp-B8h]
  __int128 v46; // [rsp+58h] [rbp-A8h]
  __int128 v47; // [rsp+68h] [rbp-98h]
  _BYTE v48[28]; // [rsp+78h] [rbp-88h]
  int v49; // [rsp+94h] [rbp-6Ch]
  int v50; // [rsp+98h] [rbp-68h]
  __int128 v51; // [rsp+9Ch] [rbp-64h]
  __int128 v52; // [rsp+ACh] [rbp-54h]
  __int128 v53; // [rsp+BCh] [rbp-44h]
  __int128 v54; // [rsp+CCh] [rbp-34h]
  _BYTE v55[28]; // [rsp+DCh] [rbp-24h]
  int v56; // [rsp+F8h] [rbp-8h]
  int v57; // [rsp+FCh] [rbp-4h]
  __int128 v58; // [rsp+100h] [rbp+0h]
  __int128 v59; // [rsp+110h] [rbp+10h]
  __int128 v60; // [rsp+120h] [rbp+20h]
  __int128 v61; // [rsp+130h] [rbp+30h]
  _DWORD v62[23]; // [rsp+140h] [rbp+40h]
  _DWORD v63[23]; // [rsp+19Ch] [rbp+9Ch]
  _BYTE v64[28]; // [rsp+1F8h] [rbp+F8h]
  int v65; // [rsp+214h] [rbp+114h]

  memset_0((char *)this + 96, 0, 0x228u);
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  memset_0((char *)this + 648, 0, 0x7Cu);
  *((_WORD *)this + 386) = 0;
  v2 = 0;
  *((_DWORD *)this + 323) = 0;
  do
  {
    SysColor = GetSysColor(v2);
    v4 = v2++;
    *((_DWORD *)this + v4 + 162) = SysColor;
  }
  while ( (unsigned int)v2 < 0x1F );
  memset_0(v43, 0, 0x1F4u);
  v42 = 504;
  if ( (unsigned int)ClassicSystemParametersInfoW(41, 504, &v42, 0) )
  {
    v5 = v44;
    v6 = v45;
    *((_DWORD *)this + 14) = v43[0];
    v7 = v43[1];
    *((_OWORD *)this + 6) = v5;
    *((_DWORD *)this + 15) = v7;
    v8 = v46;
    v9 = v43[2];
    *((_OWORD *)this + 7) = v6;
    *((_DWORD *)this + 16) = v9;
    v10 = v47;
    v11 = v43[3];
    *((_OWORD *)this + 8) = v8;
    *((_DWORD *)this + 17) = v11;
    v12 = *(_OWORD *)v48;
    v13 = v43[4];
    *((_OWORD *)this + 9) = v10;
    *((_DWORD *)this + 18) = v13;
    v14 = *(_OWORD *)&v48[12];
    v15 = v49;
    *((_OWORD *)this + 10) = v12;
    *((_DWORD *)this + 19) = v15;
    v16 = v51;
    v17 = v50;
    *(_OWORD *)((char *)this + 172) = v14;
    *((_DWORD *)this + 20) = v17;
    v18 = v52;
    v19 = v56;
    *(_OWORD *)((char *)this + 188) = v16;
    *((_DWORD *)this + 21) = v19;
    v20 = v53;
    v21 = v57;
    *(_OWORD *)((char *)this + 204) = v18;
    *((_DWORD *)this + 22) = v21;
    v22 = v54;
    v23 = v65;
    *(_OWORD *)((char *)this + 220) = v20;
    *((_DWORD *)this + 23) = v23;
    v24 = *(_OWORD *)v55;
    *(_OWORD *)((char *)this + 236) = v22;
    v25 = *(_OWORD *)&v55[12];
    *(_OWORD *)((char *)this + 252) = v24;
    *(_OWORD *)((char *)this + 280) = v58;
    v26 = v60;
    *(_OWORD *)((char *)this + 264) = v25;
    *(_OWORD *)((char *)this + 296) = v59;
    v27 = v61;
    *(_OWORD *)((char *)this + 312) = v26;
    v28 = *(_OWORD *)v62;
    *(_OWORD *)((char *)this + 328) = v27;
    v29 = *(_OWORD *)&v62[3];
    *(_OWORD *)((char *)this + 344) = v28;
    v30 = *(_OWORD *)&v62[7];
    *(_OWORD *)((char *)this + 356) = v29;
    v31 = *(_OWORD *)&v62[11];
    *(_OWORD *)((char *)this + 372) = v30;
    v32 = *(_OWORD *)&v62[15];
    *(_OWORD *)((char *)this + 388) = v31;
    v33 = *(_OWORD *)&v62[19];
    *(_OWORD *)((char *)this + 404) = v32;
    v34 = *(_OWORD *)v63;
    *(_OWORD *)((char *)this + 420) = v33;
    v35 = *(_OWORD *)&v63[3];
    *(_OWORD *)((char *)this + 436) = v34;
    v36 = *(_OWORD *)&v63[7];
    *((_OWORD *)this + 28) = v35;
    v37 = *(_OWORD *)&v63[11];
    *((_OWORD *)this + 29) = v36;
    v38 = *(_OWORD *)&v63[15];
    *((_OWORD *)this + 30) = v37;
    v39 = *(_OWORD *)&v63[19];
    *((_OWORD *)this + 31) = v38;
    v40 = *(_OWORD *)v64;
    *((_OWORD *)this + 32) = v39;
    v41 = *(_OWORD *)&v64[12];
    *((_OWORD *)this + 33) = v40;
    *(_OWORD *)((char *)this + 540) = v41;
  }
  ClassicSystemParametersInfoW(31, 92, (char *)this + 556, 0);
  ClassicSystemParametersInfoW(4130, 0, (char *)this + 1292, 0);
}

```

## disassembly

```asm
0x180014b70  mov     [rsp-8+arg_8], rbx
0x180014b75  mov     [rsp-8+arg_10], rsi
0x180014b7a  push    rbp
0x180014b7b  push    rdi
0x180014b7c  push    r14
0x180014b7e  lea     rbp, [rsp-130h]
0x180014b86  sub     rsp, 230h
0x180014b8d  mov     rax, cs:__security_cookie
0x180014b94  xor     rax, rsp
0x180014b97  mov     [rbp+140h+var_20], rax
0x180014b9e  mov     rbx, rcx
0x180014ba1  xor     edx, edx; Val
0x180014ba3  add     rcx, 60h ; '`'; void *
0x180014ba7  mov     r8d, 228h; Size
0x180014bad  call    memset_0
0x180014bb2  xor     eax, eax
0x180014bb4  lea     rcx, [rbx+288h]; void *
0x180014bbb  xorps   xmm0, xmm0
0x180014bbe  xor     edx, edx; Val
0x180014bc0  movups  xmmword ptr [rbx+38h], xmm0
0x180014bc4  movups  xmmword ptr [rbx+48h], xmm0
0x180014bc8  lea     r8d, [rax+7Ch]; Size
0x180014bcc  mov     [rbx+58h], rax
0x180014bd0  call    memset_0
0x180014bd5  xor     eax, eax
0x180014bd7  lea     rsi, [rbx+50Ch]
0x180014bde  mov     [rbx+304h], ax
0x180014be5  xor     edi, edi
0x180014be7  mov     [rsi], eax
0x180014be9  mov     ecx, edi; nIndex
0x180014beb  call    cs:__imp_GetSysColor
0x180014bf1  movsxd  rcx, edi
0x180014bf4  inc     edi
0x180014bf6  mov     [rbx+rcx*4+288h], eax
0x180014bfd  cmp     edi, 1Fh
0x180014c00  jb      short loc_180014BE9
0x180014c02  xor     edx, edx; Val
0x180014c04  lea     rcx, [rsp+240h+var_21C]; void *
0x180014c09  mov     r8d, 1F4h; Size
0x180014c0f  call    memset_0
0x180014c14  xor     r9d, r9d
0x180014c17  lea     r8, [rsp+240h+var_220]
0x180014c1c  mov     edx, 1F8h
0x180014c21  mov     [rsp+240h+var_220], edx
0x180014c25  lea     ecx, [r9+29h]
0x180014c29  call    cs:__imp_ClassicSystemParametersInfoW
0x180014c2f  test    eax, eax
0x180014c31  jz      loc_180014DDF
0x180014c37  movups  xmm0, [rsp+240h+var_208]
0x180014c3c  mov     eax, [rsp+240h+var_21C]
0x180014c40  movups  xmm1, [rsp+240h+var_1F8]
0x180014c45  mov     [rbx+38h], eax
0x180014c48  mov     eax, [rsp+240h+var_218]
0x180014c4c  movups  xmmword ptr [rbx+60h], xmm0
0x180014c50  mov     [rbx+3Ch], eax
0x180014c53  movups  xmm0, [rsp+240h+var_1E8]
0x180014c58  mov     eax, [rsp+240h+var_214]
0x180014c5c  movups  xmmword ptr [rbx+70h], xmm1
0x180014c60  mov     [rbx+40h], eax
0x180014c63  movups  xmm1, [rsp+240h+var_1D8]
0x180014c68  mov     eax, [rsp+240h+var_210]
0x180014c6c  movups  xmmword ptr [rbx+80h], xmm0
0x180014c73  mov     [rbx+44h], eax
0x180014c76  movups  xmm0, xmmword ptr [rsp+240h+var_1C8]
0x180014c7b  mov     eax, [rsp+240h+var_20C]
0x180014c7f  movups  xmmword ptr [rbx+90h], xmm1
0x180014c86  mov     [rbx+48h], eax
0x180014c89  movups  xmm1, xmmword ptr [rbp+140h+var_1C8+0Ch]
0x180014c8d  mov     eax, [rbp+140h+var_1AC]
0x180014c90  movups  xmmword ptr [rbx+0A0h], xmm0
0x180014c97  mov     [rbx+4Ch], eax
0x180014c9a  movups  xmm0, [rbp+140h+var_1A4]
0x180014c9e  mov     eax, [rbp+140h+var_1A8]
0x180014ca1  movups  xmmword ptr [rbx+0ACh], xmm1
0x180014ca8  mov     [rbx+50h], eax
0x180014cab  movups  xmm1, [rbp+140h+var_194]
0x180014caf  mov     eax, [rbp+140h+var_148]
0x180014cb2  movups  xmmword ptr [rbx+0BCh], xmm0
0x180014cb9  mov     [rbx+54h], eax
0x180014cbc  movups  xmm0, [rbp+140h+var_184]
0x180014cc0  mov     eax, [rbp+140h+var_144]
0x180014cc3  movups  xmmword ptr [rbx+0CCh], xmm1
0x180014cca  mov     [rbx+58h], eax
0x180014ccd  movups  xmm1, [rbp+140h+var_174]
0x180014cd1  mov     eax, [rbp+140h+var_2C]
0x180014cd7  movups  xmmword ptr [rbx+0DCh], xmm0
0x180014cde  mov     [rbx+5Ch], eax
0x180014ce1  movups  xmm0, xmmword ptr [rbp+140h+var_164]
0x180014ce5  movups  xmmword ptr [rbx+0ECh], xmm1
0x180014cec  movups  xmm1, xmmword ptr [rbp+140h+var_164+0Ch]
0x180014cf0  movups  xmmword ptr [rbx+0FCh], xmm0
0x180014cf7  movaps  xmm0, [rbp+140h+var_140]
0x180014cfb  movups  xmmword ptr [rbx+118h], xmm0
0x180014d02  movaps  xmm0, [rbp+140h+var_120]
0x180014d06  movups  xmmword ptr [rbx+108h], xmm1
0x180014d0d  movaps  xmm1, [rbp+140h+var_130]
0x180014d11  movups  xmmword ptr [rbx+128h], xmm1
0x180014d18  movaps  xmm1, [rbp+140h+var_110]
0x180014d1c  movups  xmmword ptr [rbx+138h], xmm0
0x180014d23  movaps  xmm0, xmmword ptr [rbp+140h+var_100]
0x180014d27  movups  xmmword ptr [rbx+148h], xmm1
0x180014d2e  movups  xmm1, xmmword ptr [rbp+140h+var_100+0Ch]
0x180014d32  movups  xmmword ptr [rbx+158h], xmm0
0x180014d39  movups  xmm0, [rbp+140h+var_E4]
0x180014d3d  movups  xmmword ptr [rbx+164h], xmm1
0x180014d44  movups  xmm1, [rbp+140h+var_D4]
0x180014d48  movups  xmmword ptr [rbx+174h], xmm0
0x180014d4f  movups  xmm0, [rbp+140h+var_C4]
0x180014d53  movups  xmmword ptr [rbx+184h], xmm1
0x180014d5a  movups  xmm1, [rbp+140h+var_B4]
0x180014d61  movups  xmmword ptr [rbx+194h], xmm0
0x180014d68  movups  xmm0, xmmword ptr [rbp+140h+var_A4]
0x180014d6f  movups  xmmword ptr [rbx+1A4h], xmm1
0x180014d76  movups  xmm1, xmmword ptr [rbp+140h+var_A4+0Ch]
0x180014d7d  movups  xmmword ptr [rbx+1B4h], xmm0
0x180014d84  movups  xmm0, [rbp+140h+var_88]
0x180014d8b  movups  xmmword ptr [rbx+1C0h], xmm1
0x180014d92  movups  xmm1, [rbp+140h+var_78]
0x180014d99  movups  xmmword ptr [rbx+1D0h], xmm0
0x180014da0  movups  xmm0, [rbp+140h+var_68]
0x180014da7  movups  xmmword ptr [rbx+1E0h], xmm1
0x180014dae  movups  xmm1, [rbp+140h+var_58]
0x180014db5  movups  xmmword ptr [rbx+1F0h], xmm0
0x180014dbc  movups  xmm0, xmmword ptr [rbp+140h+var_48]
0x180014dc3  movups  xmmword ptr [rbx+200h], xmm1
0x180014dca  movups  xmm1, xmmword ptr [rbp+140h+var_48+0Ch]
0x180014dd1  movups  xmmword ptr [rbx+210h], xmm0
0x180014dd8  movups  xmmword ptr [rbx+21Ch], xmm1
0x180014ddf  xor     r9d, r9d
0x180014de2  lea     r8, [rbx+22Ch]
0x180014de9  lea     edx, [r9+5Ch]
0x180014ded  lea     ecx, [rdx-3Dh]
0x180014df0  call    cs:__imp_ClassicSystemParametersInfoW
0x180014df6  xor     r9d, r9d
0x180014df9  mov     r8, rsi
0x180014dfc  xor     edx, edx
0x180014dfe  mov     ecx, 1022h
0x180014e03  call    cs:__imp_ClassicSystemParametersInfoW
0x180014e09  mov     rcx, [rbp+140h+var_20]
0x180014e10  xor     rcx, rsp; StackCookie
0x180014e13  call    __security_check_cookie
0x180014e18  lea     r11, [rsp+240h+var_10]
0x180014e20  mov     rbx, [r11+28h]
0x180014e24  mov     rsi, [r11+30h]
0x180014e28  mov     rsp, r11
0x180014e2b  pop     r14
0x180014e2d  pop     rdi
0x180014e2e  pop     rbp
0x180014e2f  retn
```
