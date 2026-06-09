# McTemplateU0ddllddlzczzttdzzzzzzzzzuuuu_EventWriteTransfer

- ea: `0x18000ad80`
- end: `0x18000b1f1`
- name: `McTemplateU0ddllddlzczzttdzzzzzzzzzuuuu_EventWriteTransfer`
- size: `1137`
- prototype: `ULONG __fastcall(__int64, __int64, int, int, char, char, char, char, char, const wchar_t *, char, const wchar_t *, const wchar_t *, char, char, char, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009e60`

## callees

- `0x18000247c`
- `0x18000ad80`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0ddllddlzczzttdzzzzzzzzzuuuu_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        const wchar_t *a10,
        char a11,
        const wchar_t *a12,
        const wchar_t *a13,
        char a14,
        char a15,
        char a16,
        const wchar_t *a17,
        const wchar_t *a18,
        const wchar_t *a19,
        const wchar_t *a20,
        const wchar_t *a21,
        const wchar_t *a22,
        const wchar_t *a23,
        const wchar_t *a24,
        const wchar_t *a25,
        char a26,
        char a27,
        char a28,
        char a29)
{
  const wchar_t *v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  int v33; // edx
  const wchar_t *v34; // rdx
  __int64 v35; // r8
  int v36; // r8d
  const wchar_t *v37; // r8
  __int64 v38; // rdx
  int v39; // edx
  const wchar_t *v40; // rdx
  __int64 v41; // r8
  int v42; // r8d
  const wchar_t *v43; // rdx
  __int64 v44; // r8
  int v45; // r8d
  const wchar_t *v46; // rdx
  __int64 v47; // r8
  int v48; // r8d
  const wchar_t *v49; // rdx
  __int64 v50; // r8
  int v51; // r8d
  const wchar_t *v52; // rdx
  __int64 v53; // r8
  int v54; // r8d
  const wchar_t *v55; // rdx
  __int64 v56; // r8
  int v57; // r8d
  const wchar_t *v58; // rdx
  __int64 v59; // r8
  int v60; // r8d
  const wchar_t *v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r8
  const wchar_t *v64; // rdx
  bool v65; // zf
  struct _EVENT_DATA_DESCRIPTOR v67; // [rsp+38h] [rbp-D0h] BYREF
  int *v68; // [rsp+48h] [rbp-C0h]
  __int64 v69; // [rsp+50h] [rbp-B8h]
  int *v70; // [rsp+58h] [rbp-B0h]
  __int64 v71; // [rsp+60h] [rbp-A8h]
  char *v72; // [rsp+68h] [rbp-A0h]
  __int64 v73; // [rsp+70h] [rbp-98h]
  char *v74; // [rsp+78h] [rbp-90h]
  __int64 v75; // [rsp+80h] [rbp-88h]
  char *v76; // [rsp+88h] [rbp-80h]
  __int64 v77; // [rsp+90h] [rbp-78h]
  char *v78; // [rsp+98h] [rbp-70h]
  __int64 v79; // [rsp+A0h] [rbp-68h]
  char *v80; // [rsp+A8h] [rbp-60h]
  __int64 v81; // [rsp+B0h] [rbp-58h]
  const wchar_t *v82; // [rsp+B8h] [rbp-50h]
  int v83; // [rsp+C0h] [rbp-48h]
  int v84; // [rsp+C4h] [rbp-44h]
  char *v85; // [rsp+C8h] [rbp-40h]
  __int64 v86; // [rsp+D0h] [rbp-38h]
  const wchar_t *v87; // [rsp+D8h] [rbp-30h]
  int v88; // [rsp+E0h] [rbp-28h]
  int v89; // [rsp+E4h] [rbp-24h]
  const wchar_t *v90; // [rsp+E8h] [rbp-20h]
  int v91; // [rsp+F0h] [rbp-18h]
  int v92; // [rsp+F4h] [rbp-14h]
  char *v93; // [rsp+F8h] [rbp-10h]
  __int64 v94; // [rsp+100h] [rbp-8h]
  char *v95; // [rsp+108h] [rbp+0h]
  __int64 v96; // [rsp+110h] [rbp+8h]
  char *v97; // [rsp+118h] [rbp+10h]
  __int64 v98; // [rsp+120h] [rbp+18h]
  const wchar_t *v99; // [rsp+128h] [rbp+20h]
  int v100; // [rsp+130h] [rbp+28h]
  int v101; // [rsp+134h] [rbp+2Ch]
  const wchar_t *v102; // [rsp+138h] [rbp+30h]
  int v103; // [rsp+140h] [rbp+38h]
  int v104; // [rsp+144h] [rbp+3Ch]
  const wchar_t *v105; // [rsp+148h] [rbp+40h]
  int v106; // [rsp+150h] [rbp+48h]
  int v107; // [rsp+154h] [rbp+4Ch]
  const wchar_t *v108; // [rsp+158h] [rbp+50h]
  int v109; // [rsp+160h] [rbp+58h]
  int v110; // [rsp+164h] [rbp+5Ch]
  const wchar_t *v111; // [rsp+168h] [rbp+60h]
  int v112; // [rsp+170h] [rbp+68h]
  int v113; // [rsp+174h] [rbp+6Ch]
  const wchar_t *v114; // [rsp+178h] [rbp+70h]
  int v115; // [rsp+180h] [rbp+78h]
  int v116; // [rsp+184h] [rbp+7Ch]
  const wchar_t *v117; // [rsp+188h] [rbp+80h]
  int v118; // [rsp+190h] [rbp+88h]
  int v119; // [rsp+194h] [rbp+8Ch]
  const wchar_t *v120; // [rsp+198h] [rbp+90h]
  int v121; // [rsp+1A0h] [rbp+98h]
  int v122; // [rsp+1A4h] [rbp+9Ch]
  const wchar_t *v123; // [rsp+1A8h] [rbp+A0h]
  int v124; // [rsp+1B0h] [rbp+A8h]
  int v125; // [rsp+1B4h] [rbp+ACh]
  char *v126; // [rsp+1B8h] [rbp+B0h]
  __int64 v127; // [rsp+1C0h] [rbp+B8h]
  char *v128; // [rsp+1C8h] [rbp+C0h]
  __int64 v129; // [rsp+1D0h] [rbp+C8h]
  char *v130; // [rsp+1D8h] [rbp+D0h]
  __int64 v131; // [rsp+1E0h] [rbp+D8h]
  char *v132; // [rsp+1E8h] [rbp+E0h]
  __int64 v133; // [rsp+1F0h] [rbp+E8h]
  int v134; // [rsp+228h] [rbp+120h] BYREF
  int v135; // [rsp+230h] [rbp+128h] BYREF

  v135 = a4;
  v134 = a3;
  v29 = a10;
  v68 = &v134;
  v69 = 4;
  v70 = &v135;
  v72 = &a5;
  v74 = &a6;
  v30 = 10;
  v71 = 4;
  v76 = &a7;
  v78 = &a8;
  v80 = &a9;
  v31 = -1;
  v73 = 2;
  v75 = 2;
  v77 = 4;
  v79 = 4;
  v81 = 2;
  if ( a10 )
  {
    v32 = -1;
    do
      ++v32;
    while ( a10[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v33 = 10;
  }
  v83 = v33;
  v84 = 0;
  v85 = &a11;
  v34 = a12;
  if ( !a10 )
    v29 = L"NULL";
  v86 = 1;
  v82 = v29;
  if ( a12 )
  {
    v35 = -1;
    do
      ++v35;
    while ( a12[v35] );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v36 = 10;
  }
  v88 = v36;
  v37 = a13;
  if ( !a12 )
    v34 = L"NULL";
  v89 = 0;
  v87 = v34;
  if ( a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( a13[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v39 = 10;
  }
  v91 = v39;
  v92 = 0;
  v93 = &a14;
  if ( !a13 )
    v37 = L"NULL";
  v90 = v37;
  v95 = &a15;
  v97 = &a16;
  v40 = a17;
  v94 = 4;
  v96 = 4;
  v98 = 4;
  if ( a17 )
  {
    v41 = -1;
    do
      ++v41;
    while ( a17[v41] );
    v42 = 2 * v41 + 2;
  }
  else
  {
    v42 = 10;
  }
  v100 = v42;
  v101 = 0;
  if ( !a17 )
    v40 = L"NULL";
  v99 = v40;
  v43 = a18;
  if ( a18 )
  {
    v44 = -1;
    do
      ++v44;
    while ( a18[v44] );
    v45 = 2 * v44 + 2;
  }
  else
  {
    v45 = 10;
  }
  v103 = v45;
  v104 = 0;
  if ( !a18 )
    v43 = L"NULL";
  v102 = v43;
  v46 = a19;
  if ( a19 )
  {
    v47 = -1;
    do
      ++v47;
    while ( a19[v47] );
    v48 = 2 * v47 + 2;
  }
  else
  {
    v48 = 10;
  }
  v106 = v48;
  v107 = 0;
  if ( !a19 )
    v46 = L"NULL";
  v105 = v46;
  v49 = a20;
  if ( a20 )
  {
    v50 = -1;
    do
      ++v50;
    while ( a20[v50] );
    v51 = 2 * v50 + 2;
  }
  else
  {
    v51 = 10;
  }
  v109 = v51;
  v110 = 0;
  if ( !a20 )
    v49 = L"NULL";
  v108 = v49;
  v52 = a21;
  if ( a21 )
  {
    v53 = -1;
    do
      ++v53;
    while ( a21[v53] );
    v54 = 2 * v53 + 2;
  }
  else
  {
    v54 = 10;
  }
  v112 = v54;
  v113 = 0;
  if ( !a21 )
    v52 = L"NULL";
  v111 = v52;
  v55 = a22;
  if ( a22 )
  {
    v56 = -1;
    do
      ++v56;
    while ( a22[v56] );
    v57 = 2 * v56 + 2;
  }
  else
  {
    v57 = 10;
  }
  v115 = v57;
  v116 = 0;
  if ( !a22 )
    v55 = L"NULL";
  v114 = v55;
  v58 = a23;
  if ( a23 )
  {
    v59 = -1;
    do
      ++v59;
    while ( a23[v59] );
    v60 = 2 * v59 + 2;
  }
  else
  {
    v60 = 10;
  }
  v118 = v60;
  v119 = 0;
  if ( !a23 )
    v58 = L"NULL";
  v117 = v58;
  v61 = a24;
  if ( a24 )
  {
    v62 = -1;
    do
      ++v62;
    while ( a24[v62] );
    v63 = (unsigned int)(2 * v62 + 2);
  }
  else
  {
    v63 = 10;
  }
  v121 = v63;
  v122 = 0;
  if ( !a24 )
    v61 = L"NULL";
  v120 = v61;
  v64 = a25;
  v65 = a25 == 0;
  if ( a25 )
  {
    do
      ++v31;
    while ( a25[v31] );
    v30 = (unsigned int)(2 * v31 + 2);
    v65 = a25 == 0;
  }
  if ( v65 )
    v64 = L"NULL";
  v125 = 0;
  v123 = v64;
  v126 = &a26;
  v124 = v30;
  v128 = &a27;
  v127 = 1;
  v130 = &a28;
  v132 = &a29;
  v129 = 1;
  v131 = 1;
  v133 = 1;
  return McGenEventWrite_EventWriteTransfer(
           v30,
           (const EVENT_DESCRIPTOR *)SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_SYSTEM_CONFIGURATION,
           v63,
           0x1Cu,
           &v67);
}

```

## disassembly

```asm
0x18000ad80  mov     rax, rsp
0x18000ad83  mov     [rax+8], rbx
0x18000ad87  mov     [rax+20h], r9d
0x18000ad8b  mov     [rax+18h], r8d
0x18000ad8f  push    rbp
0x18000ad90  lea     rbp, [rax-108h]
0x18000ad97  sub     rsp, 200h
0x18000ad9e  mov     rax, cs:__security_cookie
0x18000ada5  xor     rax, rsp
0x18000ada8  mov     [rbp+100h+var_10], rax
0x18000adaf  mov     r8, [rbp+100h+arg_48]
0x18000adb6  lea     rax, [rbp+100h+arg_10]
0x18000adbd  mov     [rsp+200h+var_1C0], rax
0x18000adc2  xor     r9d, r9d
0x18000adc5  lea     rax, [rbp+100h+arg_18]
0x18000adcc  mov     [rsp+200h+var_1B8], 4
0x18000add5  mov     [rsp+200h+var_1B0], rax
0x18000adda  lea     rax, [rbp+100h+arg_20]
0x18000ade1  mov     [rsp+200h+var_1A0], rax
0x18000ade6  lea     rax, [rbp+100h+arg_28]
0x18000aded  mov     [rsp+200h+var_190], rax
0x18000adf2  lea     ecx, [r9+0Ah]
0x18000adf6  lea     rax, [rbp+100h+arg_30]
0x18000adfd  mov     [rsp+200h+var_1A8], 4
0x18000ae06  mov     [rbp+100h+var_180], rax
0x18000ae0a  lea     rax, [rbp+100h+arg_38]
0x18000ae11  mov     [rbp+100h+var_170], rax
0x18000ae15  lea     rax, [rbp+100h+arg_40]
0x18000ae1c  mov     [rbp+100h+var_160], rax
0x18000ae20  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae24  mov     [rsp+200h+var_198], 2
0x18000ae2d  mov     [rsp+200h+var_188], 2
0x18000ae36  mov     [rbp+100h+var_178], 4
0x18000ae3e  mov     [rbp+100h+var_168], 4
0x18000ae46  mov     [rbp+100h+var_158], 2
0x18000ae4e  test    r8, r8
0x18000ae51  jz      short loc_18000AE69
0x18000ae53  mov     rdx, rax
0x18000ae56  inc     rdx
0x18000ae59  cmp     [r8+rdx*2], r9w
0x18000ae5e  jnz     short loc_18000AE56
0x18000ae60  lea     edx, ds:2[rdx*2]
0x18000ae67  jmp     short loc_18000AE6B
0x18000ae69  mov     edx, ecx
0x18000ae6b  mov     [rbp+100h+var_148], edx
0x18000ae6e  lea     r10, aNull_0; "NULL"
0x18000ae75  lea     rdx, [rbp+100h+arg_50]
0x18000ae7c  mov     [rbp+100h+var_144], r9d
0x18000ae80  test    r8, r8
0x18000ae83  mov     [rbp+100h+var_140], rdx
0x18000ae87  mov     rdx, [rbp+100h+arg_58]
0x18000ae8e  cmovz   r8, r10
0x18000ae92  mov     [rbp+100h+var_138], 1
0x18000ae9a  mov     [rbp+100h+var_150], r8
0x18000ae9e  test    rdx, rdx
0x18000aea1  jz      short loc_18000AEBA
0x18000aea3  mov     r8, rax
0x18000aea6  inc     r8
0x18000aea9  cmp     [rdx+r8*2], r9w
0x18000aeae  jnz     short loc_18000AEA6
0x18000aeb0  lea     r8d, ds:2[r8*2]
0x18000aeb8  jmp     short loc_18000AEBD
0x18000aeba  mov     r8d, ecx
0x18000aebd  test    rdx, rdx
0x18000aec0  mov     [rbp+100h+var_128], r8d
0x18000aec4  mov     r8, [rbp+100h+arg_60]
0x18000aecb  cmovz   rdx, r10
0x18000aecf  mov     [rbp+100h+var_124], r9d
0x18000aed3  mov     [rbp+100h+var_130], rdx
0x18000aed7  test    r8, r8
0x18000aeda  jz      short loc_18000AEF2
0x18000aedc  mov     rdx, rax
0x18000aedf  inc     rdx
0x18000aee2  cmp     [r8+rdx*2], r9w
0x18000aee7  jnz     short loc_18000AEDF
0x18000aee9  lea     edx, ds:2[rdx*2]
0x18000aef0  jmp     short loc_18000AEF4
0x18000aef2  mov     edx, ecx
0x18000aef4  mov     [rbp+100h+var_118], edx
0x18000aef7  test    r8, r8
0x18000aefa  lea     rdx, [rbp+100h+arg_68]
0x18000af01  mov     [rbp+100h+var_114], r9d
0x18000af05  mov     [rbp+100h+var_110], rdx
0x18000af09  cmovz   r8, r10
0x18000af0d  lea     rdx, [rbp+100h+arg_70]
0x18000af14  mov     [rbp+100h+var_120], r8
0x18000af18  mov     [rbp+100h+var_100], rdx
0x18000af1c  lea     rdx, [rbp+100h+arg_78]
0x18000af23  mov     [rbp+100h+var_F0], rdx
0x18000af27  mov     rdx, [rbp+100h+arg_80]
0x18000af2e  mov     [rbp+100h+var_108], 4
0x18000af36  mov     [rbp+100h+var_F8], 4
0x18000af3e  mov     [rbp+100h+var_E8], 4
0x18000af46  test    rdx, rdx
0x18000af49  jz      short loc_18000AF62
0x18000af4b  mov     r8, rax
0x18000af4e  inc     r8
0x18000af51  cmp     [rdx+r8*2], r9w
0x18000af56  jnz     short loc_18000AF4E
0x18000af58  lea     r8d, ds:2[r8*2]
0x18000af60  jmp     short loc_18000AF65
0x18000af62  mov     r8d, ecx
0x18000af65  test    rdx, rdx
0x18000af68  mov     [rbp+100h+var_D8], r8d
0x18000af6c  mov     [rbp+100h+var_D4], r9d
0x18000af70  cmovz   rdx, r10
0x18000af74  mov     [rbp+100h+var_E0], rdx
0x18000af78  mov     rdx, [rbp+100h+arg_88]
0x18000af7f  test    rdx, rdx
0x18000af82  jz      short loc_18000AF9B
0x18000af84  mov     r8, rax
0x18000af87  inc     r8
0x18000af8a  cmp     [rdx+r8*2], r9w
0x18000af8f  jnz     short loc_18000AF87
0x18000af91  lea     r8d, ds:2[r8*2]
0x18000af99  jmp     short loc_18000AF9E
0x18000af9b  mov     r8d, ecx
0x18000af9e  test    rdx, rdx
0x18000afa1  mov     [rbp+100h+var_C8], r8d
0x18000afa5  mov     [rbp+100h+var_C4], r9d
0x18000afa9  cmovz   rdx, r10
0x18000afad  mov     [rbp+100h+var_D0], rdx
0x18000afb1  mov     rdx, [rbp+100h+arg_90]
0x18000afb8  test    rdx, rdx
0x18000afbb  jz      short loc_18000AFD4
0x18000afbd  mov     r8, rax
0x18000afc0  inc     r8
0x18000afc3  cmp     [rdx+r8*2], r9w
0x18000afc8  jnz     short loc_18000AFC0
0x18000afca  lea     r8d, ds:2[r8*2]
0x18000afd2  jmp     short loc_18000AFD7
0x18000afd4  mov     r8d, ecx
0x18000afd7  test    rdx, rdx
0x18000afda  mov     [rbp+100h+var_B8], r8d
0x18000afde  mov     [rbp+100h+var_B4], r9d
0x18000afe2  cmovz   rdx, r10
0x18000afe6  mov     [rbp+100h+var_C0], rdx
0x18000afea  mov     rdx, [rbp+100h+arg_98]
0x18000aff1  test    rdx, rdx
0x18000aff4  jz      short loc_18000B00D
0x18000aff6  mov     r8, rax
0x18000aff9  inc     r8
0x18000affc  cmp     [rdx+r8*2], r9w
0x18000b001  jnz     short loc_18000AFF9
0x18000b003  lea     r8d, ds:2[r8*2]
0x18000b00b  jmp     short loc_18000B010
0x18000b00d  mov     r8d, ecx
0x18000b010  test    rdx, rdx
0x18000b013  mov     [rbp+100h+var_A8], r8d
0x18000b017  mov     [rbp+100h+var_A4], r9d
0x18000b01b  cmovz   rdx, r10
0x18000b01f  mov     [rbp+100h+var_B0], rdx
0x18000b023  mov     rdx, [rbp+100h+arg_A0]
0x18000b02a  test    rdx, rdx
0x18000b02d  jz      short loc_18000B046
0x18000b02f  mov     r8, rax
0x18000b032  inc     r8
0x18000b035  cmp     [rdx+r8*2], r9w
0x18000b03a  jnz     short loc_18000B032
0x18000b03c  lea     r8d, ds:2[r8*2]
0x18000b044  jmp     short loc_18000B049
0x18000b046  mov     r8d, ecx
0x18000b049  test    rdx, rdx
0x18000b04c  mov     [rbp+100h+var_98], r8d
0x18000b050  mov     [rbp+100h+var_94], r9d
0x18000b054  cmovz   rdx, r10
0x18000b058  mov     [rbp+100h+var_A0], rdx
0x18000b05c  mov     rdx, [rbp+100h+arg_A8]
0x18000b063  test    rdx, rdx
0x18000b066  jz      short loc_18000B07F
0x18000b068  mov     r8, rax
0x18000b06b  inc     r8
0x18000b06e  cmp     [rdx+r8*2], r9w
0x18000b073  jnz     short loc_18000B06B
0x18000b075  lea     r8d, ds:2[r8*2]
0x18000b07d  jmp     short loc_18000B082
0x18000b07f  mov     r8d, ecx
0x18000b082  test    rdx, rdx
0x18000b085  mov     [rbp+100h+var_88], r8d
0x18000b089  mov     [rbp+100h+var_84], r9d
0x18000b08d  cmovz   rdx, r10
0x18000b091  mov     [rbp+100h+var_90], rdx
0x18000b095  mov     rdx, [rbp+100h+arg_B0]
0x18000b09c  test    rdx, rdx
0x18000b09f  jz      short loc_18000B0B8
0x18000b0a1  mov     r8, rax
0x18000b0a4  inc     r8
0x18000b0a7  cmp     [rdx+r8*2], r9w
0x18000b0ac  jnz     short loc_18000B0A4
0x18000b0ae  lea     r8d, ds:2[r8*2]
0x18000b0b6  jmp     short loc_18000B0BB
0x18000b0b8  mov     r8d, ecx
0x18000b0bb  test    rdx, rdx
0x18000b0be  mov     [rbp+100h+var_78], r8d
0x18000b0c5  mov     [rbp+100h+var_74], r9d
0x18000b0cc  cmovz   rdx, r10
0x18000b0d0  mov     [rbp+100h+var_80], rdx
0x18000b0d7  mov     rdx, [rbp+100h+arg_B8]
0x18000b0de  test    rdx, rdx
0x18000b0e1  jz      short loc_18000B0FA
0x18000b0e3  mov     r8, rax
0x18000b0e6  inc     r8
0x18000b0e9  cmp     [rdx+r8*2], r9w
0x18000b0ee  jnz     short loc_18000B0E6
0x18000b0f0  lea     r8d, ds:2[r8*2]
0x18000b0f8  jmp     short loc_18000B0FD
0x18000b0fa  mov     r8d, ecx
0x18000b0fd  test    rdx, rdx
0x18000b100  mov     [rbp+100h+var_68], r8d
0x18000b107  mov     [rbp+100h+var_64], r9d
0x18000b10e  cmovz   rdx, r10
0x18000b112  mov     [rbp+100h+var_70], rdx
0x18000b119  mov     rdx, [rbp+100h+arg_C0]
0x18000b120  test    rdx, rdx
0x18000b123  jz      short loc_18000B139
0x18000b125  inc     rax
0x18000b128  cmp     [rdx+rax*2], r9w
0x18000b12d  jnz     short loc_18000B125
0x18000b12f  lea     ecx, ds:2[rax*2]
0x18000b136  test    rdx, rdx
0x18000b139  cmovz   rdx, r10
0x18000b13d  mov     [rbp+100h+var_54], r9d
0x18000b144  lea     rax, [rbp+100h+arg_C8]
0x18000b14b  mov     [rbp+100h+var_60], rdx
0x18000b152  mov     [rbp+100h+var_50], rax
0x18000b159  lea     rdx, SDIAGPRV_EVENT_BWC_CONTENT_DIAGNOSTIC_PROVIDER_SYSTEM_CONFIGURATION
0x18000b160  lea     rax, [rbp+100h+arg_D0]
0x18000b167  mov     [rbp+100h+var_58], ecx
0x18000b16d  mov     [rbp+100h+var_40], rax
0x18000b174  mov     r9d, 1Ch
0x18000b17a  lea     rax, [rbp+100h+arg_D8]
0x18000b181  mov     [rbp+100h+var_48], 1
0x18000b18c  mov     [rbp+100h+var_30], rax
0x18000b193  lea     rax, [rbp+100h+arg_E0]
0x18000b19a  mov     [rbp+100h+var_20], rax
0x18000b1a1  lea     rax, [rsp+30h]
0x18000b1a6  mov     [rsp+20h], rax
0x18000b1ab  mov     [rbp+100h+var_38], 1
0x18000b1b6  mov     [rbp+100h+var_28], 1
0x18000b1c1  mov     [rbp+100h+var_18], 1
0x18000b1cc  call    McGenEventWrite_EventWriteTransfer
0x18000b1d1  mov     rcx, [rbp+100h+var_10]
0x18000b1d8  xor     rcx, rsp; StackCookie
0x18000b1db  call    __security_check_cookie
0x18000b1e0  mov     rbx, [rsp+200h+arg_0]
0x18000b1e8  add     rsp, 200h
0x18000b1ef  pop     rbp
0x18000b1f0  retn
```
