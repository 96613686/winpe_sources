# McTemplateU0qzzzzzzzszshqxxxhssszshz_EventWriteTransfer

- ea: `0x1800067a4`
- end: `0x180006c31`
- name: `McTemplateU0qzzzzzzzszshqxxxhssszshz_EventWriteTransfer`
- size: `1165`
- prototype: `ULONG __fastcall(__int64, __int64, int, const char *, const char *, const char *, const char *, const char *, const char *, const char *, const char *, const char *, const char *, char, char, char, char, char, char, const char *, const char *, const char *, const char *, const char *, char, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800063bc`

## callees

- `0x180006744`
- `0x1800067a4`
- `0x18000e9a0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzzzzzzzszshqxxxhssszshz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const char *a4,
        const char *a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        const char *a10,
        const char *a11,
        const char *a12,
        const char *a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        const char *a20,
        const char *a21,
        const char *a22,
        const char *a23,
        const char *a24,
        char a25,
        const char *a26)
{
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  const char *v30; // rcx
  __int64 v31; // r8
  int v32; // r8d
  const char *v33; // rcx
  __int64 v34; // r8
  int v35; // r8d
  const char *v36; // rcx
  __int64 v37; // r8
  int v38; // r8d
  const char *v39; // rcx
  __int64 v40; // r8
  int v41; // r8d
  const char *v42; // rcx
  __int64 v43; // r8
  int v44; // r8d
  const char *v45; // rcx
  __int64 v46; // r8
  int v47; // r8d
  __int64 v48; // r9
  const char *v49; // rcx
  __int64 v50; // r8
  int v51; // r8d
  const char *v52; // rcx
  __int64 v53; // r8
  int v54; // r8d
  const char *v55; // r8
  __int64 v56; // rcx
  int v57; // ecx
  const char *v58; // r8
  __int64 v59; // rcx
  int v60; // ecx
  const char *v61; // rcx
  __int64 v62; // r8
  int v63; // r8d
  const char *v64; // rcx
  __int64 v65; // r8
  int v66; // r8d
  const char *v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r8
  const char *v70; // rcx
  bool v71; // zf
  const char *v72; // rcx
  bool v73; // zf
  struct _EVENT_DATA_DESCRIPTOR v75; // [rsp+30h] [rbp-D0h] BYREF
  int *v76; // [rsp+40h] [rbp-C0h]
  __int64 v77; // [rsp+48h] [rbp-B8h]
  const char *v78; // [rsp+50h] [rbp-B0h]
  int v79; // [rsp+58h] [rbp-A8h]
  int v80; // [rsp+5Ch] [rbp-A4h]
  const char *v81; // [rsp+60h] [rbp-A0h]
  int v82; // [rsp+68h] [rbp-98h]
  int v83; // [rsp+6Ch] [rbp-94h]
  const char *v84; // [rsp+70h] [rbp-90h]
  int v85; // [rsp+78h] [rbp-88h]
  int v86; // [rsp+7Ch] [rbp-84h]
  const char *v87; // [rsp+80h] [rbp-80h]
  int v88; // [rsp+88h] [rbp-78h]
  int v89; // [rsp+8Ch] [rbp-74h]
  const char *v90; // [rsp+90h] [rbp-70h]
  int v91; // [rsp+98h] [rbp-68h]
  int v92; // [rsp+9Ch] [rbp-64h]
  const char *v93; // [rsp+A0h] [rbp-60h]
  int v94; // [rsp+A8h] [rbp-58h]
  int v95; // [rsp+ACh] [rbp-54h]
  const char *v96; // [rsp+B0h] [rbp-50h]
  int v97; // [rsp+B8h] [rbp-48h]
  int v98; // [rsp+BCh] [rbp-44h]
  const char *v99; // [rsp+C0h] [rbp-40h]
  int v100; // [rsp+C8h] [rbp-38h]
  int v101; // [rsp+CCh] [rbp-34h]
  const char *v102; // [rsp+D0h] [rbp-30h]
  int v103; // [rsp+D8h] [rbp-28h]
  int v104; // [rsp+DCh] [rbp-24h]
  const char *v105; // [rsp+E0h] [rbp-20h]
  int v106; // [rsp+E8h] [rbp-18h]
  int v107; // [rsp+ECh] [rbp-14h]
  char *v108; // [rsp+F0h] [rbp-10h]
  __int64 v109; // [rsp+F8h] [rbp-8h]
  char *v110; // [rsp+100h] [rbp+0h]
  __int64 v111; // [rsp+108h] [rbp+8h]
  char *v112; // [rsp+110h] [rbp+10h]
  __int64 v113; // [rsp+118h] [rbp+18h]
  char *v114; // [rsp+120h] [rbp+20h]
  __int64 v115; // [rsp+128h] [rbp+28h]
  char *v116; // [rsp+130h] [rbp+30h]
  __int64 v117; // [rsp+138h] [rbp+38h]
  char *v118; // [rsp+140h] [rbp+40h]
  __int64 v119; // [rsp+148h] [rbp+48h]
  const char *v120; // [rsp+150h] [rbp+50h]
  int v121; // [rsp+158h] [rbp+58h]
  int v122; // [rsp+15Ch] [rbp+5Ch]
  const char *v123; // [rsp+160h] [rbp+60h]
  int v124; // [rsp+168h] [rbp+68h]
  int v125; // [rsp+16Ch] [rbp+6Ch]
  const char *v126; // [rsp+170h] [rbp+70h]
  int v127; // [rsp+178h] [rbp+78h]
  int v128; // [rsp+17Ch] [rbp+7Ch]
  const char *v129; // [rsp+180h] [rbp+80h]
  int v130; // [rsp+188h] [rbp+88h]
  int v131; // [rsp+18Ch] [rbp+8Ch]
  const char *v132; // [rsp+190h] [rbp+90h]
  int v133; // [rsp+198h] [rbp+98h]
  int v134; // [rsp+19Ch] [rbp+9Ch]
  char *v135; // [rsp+1A0h] [rbp+A0h]
  __int64 v136; // [rsp+1A8h] [rbp+A8h]
  const char *v137; // [rsp+1B0h] [rbp+B0h]
  int v138; // [rsp+1B8h] [rbp+B8h]
  int v139; // [rsp+1BCh] [rbp+BCh]
  int v140; // [rsp+1F0h] [rbp+F0h] BYREF

  v140 = a3;
  v77 = 4;
  v76 = &v140;
  v26 = -1;
  v27 = 10;
  if ( a4 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)&a4[2 * v28] );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v29 = 10;
  }
  v79 = v29;
  v30 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v80 = 0;
  v78 = a4;
  if ( a5 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_WORD *)&a5[2 * v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v32 = 10;
  }
  v82 = v32;
  v83 = 0;
  if ( !a5 )
    v30 = L"NULL";
  v81 = v30;
  v33 = a6;
  if ( a6 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)&a6[2 * v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v35 = 10;
  }
  v85 = v35;
  v86 = 0;
  if ( !a6 )
    v33 = L"NULL";
  v84 = v33;
  v36 = a7;
  if ( a7 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)&a7[2 * v37] );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v38 = 10;
  }
  v88 = v38;
  v89 = 0;
  if ( !a7 )
    v36 = L"NULL";
  v87 = v36;
  v39 = a8;
  if ( a8 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)&a8[2 * v40] );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v41 = 10;
  }
  v91 = v41;
  v92 = 0;
  if ( !a8 )
    v39 = L"NULL";
  v90 = v39;
  v42 = a9;
  if ( a9 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)&a9[2 * v43] );
    v44 = 2 * v43 + 2;
  }
  else
  {
    v44 = 10;
  }
  v94 = v44;
  v95 = 0;
  if ( !a9 )
    v42 = L"NULL";
  v93 = v42;
  v45 = a10;
  if ( a10 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *(_WORD *)&a10[2 * v46] );
    v47 = 2 * v46 + 2;
  }
  else
  {
    v47 = 10;
  }
  v97 = v47;
  v98 = 0;
  v48 = 5;
  if ( !a10 )
    v45 = L"NULL";
  v96 = v45;
  v49 = a11;
  if ( a11 )
  {
    v50 = -1;
    do
      ++v50;
    while ( a11[v50] );
    v51 = v50 + 1;
  }
  else
  {
    v51 = 5;
  }
  v100 = v51;
  v101 = 0;
  if ( !a11 )
    v49 = "NULL";
  v99 = v49;
  v52 = a12;
  if ( a12 )
  {
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)&a12[2 * v53] );
    v54 = 2 * v53 + 2;
  }
  else
  {
    v54 = 10;
  }
  v103 = v54;
  v55 = a13;
  if ( !a12 )
    v52 = L"NULL";
  v104 = 0;
  v102 = v52;
  if ( a13 )
  {
    v56 = -1;
    do
      ++v56;
    while ( a13[v56] );
    v57 = v56 + 1;
  }
  else
  {
    v57 = 5;
  }
  v106 = v57;
  v107 = 0;
  v108 = &a14;
  if ( !a13 )
    v55 = "NULL";
  v105 = v55;
  v58 = a20;
  v110 = &a15;
  v112 = &a16;
  v114 = &a17;
  v116 = &a18;
  v118 = &a19;
  v109 = 2;
  v111 = 4;
  v113 = 8;
  v115 = 8;
  v117 = 8;
  v119 = 2;
  if ( a20 )
  {
    v59 = -1;
    do
      ++v59;
    while ( a20[v59] );
    v60 = v59 + 1;
  }
  else
  {
    v60 = 5;
  }
  v121 = v60;
  v61 = a21;
  if ( !a20 )
    v58 = "NULL";
  v122 = 0;
  v120 = v58;
  if ( a21 )
  {
    v62 = -1;
    do
      ++v62;
    while ( a21[v62] );
    v63 = v62 + 1;
  }
  else
  {
    v63 = 5;
  }
  v124 = v63;
  v125 = 0;
  if ( !a21 )
    v61 = "NULL";
  v123 = v61;
  v64 = a22;
  if ( a22 )
  {
    v65 = -1;
    do
      ++v65;
    while ( a22[v65] );
    v66 = v65 + 1;
  }
  else
  {
    v66 = 5;
  }
  v127 = v66;
  v128 = 0;
  if ( !a22 )
    v64 = "NULL";
  v126 = v64;
  v67 = a23;
  if ( a23 )
  {
    v68 = -1;
    do
      ++v68;
    while ( *(_WORD *)&a23[2 * v68] );
    v69 = (unsigned int)(2 * v68 + 2);
  }
  else
  {
    v69 = 10;
  }
  v130 = v69;
  v131 = 0;
  if ( !a23 )
    v67 = L"NULL";
  v129 = v67;
  v70 = a24;
  v71 = a24 == 0;
  if ( a24 )
  {
    v69 = -1;
    do
      ++v69;
    while ( a24[v69] );
    v48 = (unsigned int)(v69 + 1);
    v71 = a24 == 0;
  }
  if ( v71 )
    v70 = "NULL";
  v133 = v48;
  v132 = v70;
  v135 = &a25;
  v72 = a26;
  v134 = 0;
  v136 = 2;
  v73 = a26 == 0;
  if ( a26 )
  {
    do
      ++v26;
    while ( *(_WORD *)&a26[2 * v26] );
    v27 = (unsigned int)(2 * v26 + 2);
    v73 = a26 == 0;
  }
  if ( v73 )
    v72 = L"NULL";
  v138 = v27;
  v137 = v72;
  v139 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v72, v27, v69, v48, &v75);
}

```

## disassembly

```asm
0x1800067a4  mov     [rsp-8+arg_0], rbx
0x1800067a9  mov     [rsp-8+arg_10], r8d
0x1800067ae  push    rbp
0x1800067af  lea     rbp, [rsp-0D0h]
0x1800067b7  sub     rsp, 1D0h
0x1800067be  mov     rax, cs:__security_cookie
0x1800067c5  xor     rax, rsp
0x1800067c8  mov     [rbp+0D0h+var_10], rax
0x1800067cf  lea     rax, [rbp+0D0h+arg_10]
0x1800067d6  mov     [rsp+1D0h+var_188], 4
0x1800067df  xor     r10d, r10d
0x1800067e2  mov     [rsp+1D0h+var_190], rax
0x1800067e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800067eb  lea     edx, [r10+0Ah]
0x1800067ef  test    r9, r9
0x1800067f2  jz      short loc_18000680A
0x1800067f4  mov     rcx, rax
0x1800067f7  inc     rcx
0x1800067fa  cmp     [r9+rcx*2], r10w
0x1800067ff  jnz     short loc_1800067F7
0x180006801  lea     ecx, ds:2[rcx*2]
0x180006808  jmp     short loc_18000680C
0x18000680a  mov     ecx, edx
0x18000680c  test    r9, r9
0x18000680f  mov     [rsp+1D0h+var_178], ecx
0x180006813  mov     rcx, [rbp+0D0h+arg_20]
0x18000681a  lea     r11, aNull_0; "NULL"
0x180006821  cmovz   r9, r11
0x180006825  mov     [rsp+1D0h+var_174], r10d
0x18000682a  mov     [rsp+1D0h+var_180], r9
0x18000682f  test    rcx, rcx
0x180006832  jz      short loc_18000684B
0x180006834  mov     r8, rax
0x180006837  inc     r8
0x18000683a  cmp     [rcx+r8*2], r10w
0x18000683f  jnz     short loc_180006837
0x180006841  lea     r8d, ds:2[r8*2]
0x180006849  jmp     short loc_18000684E
0x18000684b  mov     r8d, edx
0x18000684e  test    rcx, rcx
0x180006851  mov     [rsp+1D0h+var_168], r8d
0x180006856  mov     [rsp+1D0h+var_164], r10d
0x18000685b  cmovz   rcx, r11
0x18000685f  mov     [rsp+1D0h+var_170], rcx
0x180006864  mov     rcx, [rbp+0D0h+arg_28]
0x18000686b  test    rcx, rcx
0x18000686e  jz      short loc_180006887
0x180006870  mov     r8, rax
0x180006873  inc     r8
0x180006876  cmp     [rcx+r8*2], r10w
0x18000687b  jnz     short loc_180006873
0x18000687d  lea     r8d, ds:2[r8*2]
0x180006885  jmp     short loc_18000688A
0x180006887  mov     r8d, edx
0x18000688a  test    rcx, rcx
0x18000688d  mov     [rsp+1D0h+var_158], r8d
0x180006892  mov     [rsp+1D0h+var_154], r10d
0x180006897  cmovz   rcx, r11
0x18000689b  mov     [rsp+1D0h+var_160], rcx
0x1800068a0  mov     rcx, [rbp+0D0h+arg_30]
0x1800068a7  test    rcx, rcx
0x1800068aa  jz      short loc_1800068C3
0x1800068ac  mov     r8, rax
0x1800068af  inc     r8
0x1800068b2  cmp     [rcx+r8*2], r10w
0x1800068b7  jnz     short loc_1800068AF
0x1800068b9  lea     r8d, ds:2[r8*2]
0x1800068c1  jmp     short loc_1800068C6
0x1800068c3  mov     r8d, edx
0x1800068c6  test    rcx, rcx
0x1800068c9  mov     [rbp+0D0h+var_148], r8d
0x1800068cd  mov     [rbp+0D0h+var_144], r10d
0x1800068d1  cmovz   rcx, r11
0x1800068d5  mov     [rbp+0D0h+var_150], rcx
0x1800068d9  mov     rcx, [rbp+0D0h+arg_38]
0x1800068e0  test    rcx, rcx
0x1800068e3  jz      short loc_1800068FC
0x1800068e5  mov     r8, rax
0x1800068e8  inc     r8
0x1800068eb  cmp     [rcx+r8*2], r10w
0x1800068f0  jnz     short loc_1800068E8
0x1800068f2  lea     r8d, ds:2[r8*2]
0x1800068fa  jmp     short loc_1800068FF
0x1800068fc  mov     r8d, edx
0x1800068ff  test    rcx, rcx
0x180006902  mov     [rbp+0D0h+var_138], r8d
0x180006906  mov     [rbp+0D0h+var_134], r10d
0x18000690a  cmovz   rcx, r11
0x18000690e  mov     [rbp+0D0h+var_140], rcx
0x180006912  mov     rcx, [rbp+0D0h+arg_40]
0x180006919  test    rcx, rcx
0x18000691c  jz      short loc_180006935
0x18000691e  mov     r8, rax
0x180006921  inc     r8
0x180006924  cmp     [rcx+r8*2], r10w
0x180006929  jnz     short loc_180006921
0x18000692b  lea     r8d, ds:2[r8*2]
0x180006933  jmp     short loc_180006938
0x180006935  mov     r8d, edx
0x180006938  test    rcx, rcx
0x18000693b  mov     [rbp+0D0h+var_128], r8d
0x18000693f  mov     [rbp+0D0h+var_124], r10d
0x180006943  cmovz   rcx, r11
0x180006947  mov     [rbp+0D0h+var_130], rcx
0x18000694b  mov     rcx, [rbp+0D0h+arg_48]
0x180006952  test    rcx, rcx
0x180006955  jz      short loc_18000696E
0x180006957  mov     r8, rax
0x18000695a  inc     r8
0x18000695d  cmp     [rcx+r8*2], r10w
0x180006962  jnz     short loc_18000695A
0x180006964  lea     r8d, ds:2[r8*2]
0x18000696c  jmp     short loc_180006971
0x18000696e  mov     r8d, edx
0x180006971  test    rcx, rcx
0x180006974  mov     [rbp+0D0h+var_118], r8d
0x180006978  mov     [rbp+0D0h+var_114], r10d
0x18000697c  mov     r9d, 5
0x180006982  cmovz   rcx, r11
0x180006986  mov     [rbp+0D0h+var_120], rcx
0x18000698a  mov     rcx, [rbp+0D0h+arg_50]
0x180006991  test    rcx, rcx
0x180006994  jz      short loc_1800069A7
0x180006996  mov     r8, rax
0x180006999  inc     r8
0x18000699c  cmp     [rcx+r8], r10b
0x1800069a0  jnz     short loc_180006999
0x1800069a2  inc     r8d
0x1800069a5  jmp     short loc_1800069AA
0x1800069a7  mov     r8d, r9d
0x1800069aa  test    rcx, rcx
0x1800069ad  mov     [rbp+0D0h+var_108], r8d
0x1800069b1  lea     rbx, aNull; "NULL"
0x1800069b8  mov     [rbp+0D0h+var_104], r10d
0x1800069bc  cmovz   rcx, rbx
0x1800069c0  mov     [rbp+0D0h+var_110], rcx
0x1800069c4  mov     rcx, [rbp+0D0h+arg_58]
0x1800069cb  test    rcx, rcx
0x1800069ce  jz      short loc_1800069E7
0x1800069d0  mov     r8, rax
0x1800069d3  inc     r8
0x1800069d6  cmp     [rcx+r8*2], r10w
0x1800069db  jnz     short loc_1800069D3
0x1800069dd  lea     r8d, ds:2[r8*2]
0x1800069e5  jmp     short loc_1800069EA
0x1800069e7  mov     r8d, edx
0x1800069ea  test    rcx, rcx
0x1800069ed  mov     [rbp+0D0h+var_F8], r8d
0x1800069f1  mov     r8, [rbp+0D0h+arg_60]
0x1800069f8  cmovz   rcx, r11
0x1800069fc  mov     [rbp+0D0h+var_F4], r10d
0x180006a00  mov     [rbp+0D0h+var_100], rcx
0x180006a04  test    r8, r8
0x180006a07  jz      short loc_180006A19
0x180006a09  mov     rcx, rax
0x180006a0c  inc     rcx
0x180006a0f  cmp     [r8+rcx], r10b
0x180006a13  jnz     short loc_180006A0C
0x180006a15  inc     ecx
0x180006a17  jmp     short loc_180006A1C
0x180006a19  mov     ecx, r9d
0x180006a1c  mov     [rbp+0D0h+var_E8], ecx
0x180006a1f  test    r8, r8
0x180006a22  lea     rcx, [rbp+0D0h+arg_68]
0x180006a29  mov     [rbp+0D0h+var_E4], r10d
0x180006a2d  mov     [rbp+0D0h+var_E0], rcx
0x180006a31  cmovz   r8, rbx
0x180006a35  lea     rcx, [rbp+0D0h+arg_70]
0x180006a3c  mov     [rbp+0D0h+var_F0], r8
0x180006a40  mov     r8, [rbp+0D0h+arg_98]
0x180006a47  mov     [rbp+0D0h+var_D0], rcx
0x180006a4b  lea     rcx, [rbp+0D0h+arg_78]
0x180006a52  mov     [rbp+0D0h+var_C0], rcx
0x180006a56  lea     rcx, [rbp+0D0h+arg_80]
0x180006a5d  mov     [rbp+0D0h+var_B0], rcx
0x180006a61  lea     rcx, [rbp+0D0h+arg_88]
0x180006a68  mov     [rbp+0D0h+var_A0], rcx
0x180006a6c  lea     rcx, [rbp+0D0h+arg_90]
0x180006a73  mov     [rbp+0D0h+var_90], rcx
0x180006a77  mov     [rbp+0D0h+var_D8], 2
0x180006a7f  mov     [rbp+0D0h+var_C8], 4
0x180006a87  mov     [rbp+0D0h+var_B8], 8
0x180006a8f  mov     [rbp+0D0h+var_A8], 8
0x180006a97  mov     [rbp+0D0h+var_98], 8
0x180006a9f  mov     [rbp+0D0h+var_88], 2
0x180006aa7  test    r8, r8
0x180006aaa  jz      short loc_180006ABC
0x180006aac  mov     rcx, rax
0x180006aaf  inc     rcx
0x180006ab2  cmp     [r8+rcx], r10b
0x180006ab6  jnz     short loc_180006AAF
0x180006ab8  inc     ecx
0x180006aba  jmp     short loc_180006ABF
0x180006abc  mov     ecx, r9d
0x180006abf  test    r8, r8
0x180006ac2  mov     [rbp+0D0h+var_78], ecx
0x180006ac5  mov     rcx, [rbp+0D0h+arg_A0]
0x180006acc  cmovz   r8, rbx
0x180006ad0  mov     [rbp+0D0h+var_74], r10d
0x180006ad4  mov     [rbp+0D0h+var_80], r8
0x180006ad8  test    rcx, rcx
0x180006adb  jz      short loc_180006AEE
0x180006add  mov     r8, rax
0x180006ae0  inc     r8
0x180006ae3  cmp     [rcx+r8], r10b
0x180006ae7  jnz     short loc_180006AE0
0x180006ae9  inc     r8d
0x180006aec  jmp     short loc_180006AF1
0x180006aee  mov     r8d, r9d
0x180006af1  test    rcx, rcx
0x180006af4  mov     [rbp+0D0h+var_68], r8d
0x180006af8  mov     [rbp+0D0h+var_64], r10d
0x180006afc  cmovz   rcx, rbx
0x180006b00  mov     [rbp+0D0h+var_70], rcx
0x180006b04  mov     rcx, [rbp+0D0h+arg_A8]
0x180006b0b  test    rcx, rcx
0x180006b0e  jz      short loc_180006B21
0x180006b10  mov     r8, rax
0x180006b13  inc     r8
0x180006b16  cmp     [rcx+r8], r10b
0x180006b1a  jnz     short loc_180006B13
0x180006b1c  inc     r8d
0x180006b1f  jmp     short loc_180006B24
0x180006b21  mov     r8d, r9d
0x180006b24  test    rcx, rcx
0x180006b27  mov     [rbp+0D0h+var_58], r8d
0x180006b2b  mov     [rbp+0D0h+var_54], r10d
0x180006b2f  cmovz   rcx, rbx
0x180006b33  mov     [rbp+0D0h+var_60], rcx
0x180006b37  mov     rcx, [rbp+0D0h+arg_B0]
0x180006b3e  test    rcx, rcx
0x180006b41  jz      short loc_180006B5A
0x180006b43  mov     r8, rax
0x180006b46  inc     r8
0x180006b49  cmp     [rcx+r8*2], r10w
0x180006b4e  jnz     short loc_180006B46
0x180006b50  lea     r8d, ds:2[r8*2]
0x180006b58  jmp     short loc_180006B5D
0x180006b5a  mov     r8d, edx
0x180006b5d  test    rcx, rcx
0x180006b60  mov     [rbp+0D0h+var_48], r8d
0x180006b67  mov     [rbp+0D0h+var_44], r10d
0x180006b6e  cmovz   rcx, r11
0x180006b72  mov     [rbp+0D0h+var_50], rcx
0x180006b79  mov     rcx, [rbp+0D0h+arg_B8]
0x180006b80  test    rcx, rcx
0x180006b83  jz      short loc_180006B98
0x180006b85  mov     r8, rax
0x180006b88  inc     r8; int
0x180006b8b  cmp     [rcx+r8], r10b
0x180006b8f  jnz     short loc_180006B88
0x180006b91  lea     r9d, [r8+1]; int
0x180006b95  test    rcx, rcx
0x180006b98  cmovz   rcx, rbx
0x180006b9c  mov     [rbp+0D0h+var_38], r9d
0x180006ba3  mov     [rbp+0D0h+var_40], rcx
0x180006baa  lea     rcx, [rbp+0D0h+arg_C0]
0x180006bb1  mov     [rbp+0D0h+var_30], rcx
0x180006bb8  mov     rcx, [rbp+0D0h+arg_C8]
0x180006bbf  mov     [rbp+0D0h+var_34], r10d
0x180006bc6  mov     [rbp+0D0h+var_28], 2
0x180006bd1  test    rcx, rcx
0x180006bd4  jz      short loc_180006BEA
0x180006bd6  inc     rax
0x180006bd9  cmp     [rcx+rax*2], r10w
0x180006bde  jnz     short loc_180006BD6
0x180006be0  lea     edx, ds:2[rax*2]; int
0x180006be7  test    rcx, rcx
0x180006bea  cmovz   rcx, r11; int
0x180006bee  mov     [rbp+0D0h+var_18], edx
0x180006bf4  lea     rax, [rsp+1D0h+var_1A0]
0x180006bf9  mov     [rbp+0D0h+var_20], rcx
0x180006c00  mov     [rsp+1D0h+var_1B0], rax; PEVENT_DATA_DESCRIPTOR
0x180006c05  mov     [rbp+0D0h+var_14], r10d
0x180006c0c  call    McGenEventWrite_EventWriteTransfer
0x180006c11  mov     rcx, [rbp+0D0h+var_10]
0x180006c18  xor     rcx, rsp; StackCookie
0x180006c1b  call    __security_check_cookie
0x180006c20  mov     rbx, [rsp+1D0h+arg_0]
0x180006c28  add     rsp, 1D0h
0x180006c2f  pop     rbp
0x180006c30  retn
```
