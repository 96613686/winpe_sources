# FReplaceTokenInLocation(char const *,char *,int,char *,int,int,ulong,char * *)

- ea: `0x1800132f8`
- end: `0x18001391b`
- name: `?FReplaceTokenInLocation@@YAHPEBDPEADH1HHKPEAPEAD@Z`
- size: `1571`
- prototype: `__int64 __fastcall(const char *, char *, int, char *, int, int, unsigned int, char **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180012760`
- `0x1800129b0`

## callees

- `0x1800132f8`
- `0x180018cc0`
- `0x180018e90`
- `0x18002735c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800133d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800133d4`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001333f`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001335d`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180013388`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001333f`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001335d`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180013388`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180013322`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180013322`

## pseudocode

```c
__int64 __fastcall FReplaceTokenInLocation(
        const char *a1,
        char *a2,
        int a3,
        char *a4,
        int a5,
        int a6,
        unsigned int a7,
        char **a8)
{
  unsigned __int64 v8; // r13
  const char *v9; // rdi
  const char *v10; // rsi
  int v11; // ebx
  char *v12; // r15
  char *v13; // rax
  __int64 v14; // r14
  char *v15; // rax
  int v16; // r12d
  size_t v17; // rcx
  unsigned __int64 v18; // rbx
  void *v19; // rax
  char *v20; // rcx
  bool v21; // zf
  void *v22; // r12
  int v23; // esi
  int v24; // r15d
  __int64 v25; // rax
  const char *v26; // rdx
  unsigned __int64 v27; // r8
  char *v28; // r9
  __int64 v29; // r11
  __int64 v30; // r10
  char *v31; // rax
  unsigned int v32; // edx
  __int64 v33; // rbx
  char *v34; // r9
  unsigned __int64 v35; // rax
  char *v36; // r11
  __int64 v37; // rdx
  __int64 v38; // rcx
  char *v39; // r8
  __int64 v40; // r10
  char *v41; // rax
  signed int v42; // edx
  int v43; // r14d
  __int64 v44; // rdx
  int v45; // r15d
  __int64 v46; // rax
  const char *v47; // rdx
  unsigned __int64 v48; // r8
  char *v49; // r9
  __int64 v50; // r10
  __int64 v51; // r11
  char *v52; // rax
  unsigned int v53; // edx
  __int64 v54; // rbx
  char *v55; // rsi
  __int64 v56; // rax
  const char *v57; // rcx
  __int64 v58; // rdx
  char *v59; // r8
  __int64 v60; // r9
  __int64 v61; // r10
  char *v62; // rax
  unsigned int v63; // ecx
  __int64 v64; // rbx
  char *v65; // r11
  __int64 v66; // rax
  const char *v67; // rcx
  __int64 v68; // rdx
  char *v69; // r8
  __int64 v70; // r9
  __int64 v71; // r10
  char *v72; // rax
  unsigned int v73; // ecx
  __int64 v74; // rbx
  char *v75; // r9
  const char *v76; // rsi
  int v77; // r14d
  __int64 v78; // rax
  const char *v79; // rcx
  __int64 v80; // rdx
  char *v81; // r8
  __int64 v82; // r11
  __int64 v83; // r10
  char *v84; // rax
  unsigned int v85; // ecx
  unsigned __int64 v86; // rbx
  unsigned int v88; // [rsp+28h] [rbp-38h]
  unsigned int v89; // [rsp+30h] [rbp-30h]
  unsigned int v90; // [rsp+30h] [rbp-30h]
  char *v91; // [rsp+40h] [rbp-20h] BYREF
  void *Block; // [rsp+48h] [rbp-18h]
  char *v93; // [rsp+50h] [rbp-10h]
  unsigned __int64 v94; // [rsp+A0h] [rbp+40h] BYREF
  char *v95; // [rsp+A8h] [rbp+48h]
  char *v96; // [rsp+B8h] [rbp+58h]

  v96 = a4;
  v95 = a2;
  v8 = a3;
  v9 = a1;
  v10 = a1;
  v11 = lstrlenA(a1);
  *a8 = 0;
  v12 = strstr(v10, "5479f6b6-71ac-44fc-9164-7e901a557f81");
  if ( v12 )
    v11 = v8 + v11 - 36;
  v13 = strstr(v9, "0bd2834d-d10e-46e9-84ba-34e538bea2d3");
  v93 = v13;
  if ( v13 )
    v11 += a5 + 15;
  v14 = a7;
  if ( a6 != 1 )
  {
LABEL_10:
    v16 = 0;
    if ( !v12 && !v13 )
      return 1;
    goto LABEL_12;
  }
  v15 = strstr(v9, "Host: 239.255.255.250:1900");
  LODWORD(v10) = (_DWORD)v15;
  if ( !v15 || (unsigned int)v14 >= 6 )
  {
    v13 = v93;
    goto LABEL_10;
  }
  v16 = 1;
  v11 += c_rgcchIPv6HostTagSizes[v14] - 26;
LABEL_12:
  v17 = (unsigned int)(v11 + 1);
  v18 = v17;
  v19 = malloc(v17);
  Block = v19;
  if ( !v19 )
    return 0;
  memset_0(v19, 0, (unsigned int)v18);
  v20 = (char *)Block;
  v21 = v16 == 0;
  v91 = (char *)Block;
  v22 = Block;
  v94 = v18;
  if ( !v21 )
  {
    v23 = (_DWORD)v10 - (_DWORD)v9;
    if ( (int)StringCbCopyNExA((char *)Block, (unsigned int)v18, v9, v23, &v91, &v94, v89) < 0
      || (int)StringCbCopyNExA(
                v91,
                v94,
                (const char *)c_rgszIPv6HostTags[v14],
                (unsigned int)c_rgcchIPv6HostTagSizes[v14],
                &v91,
                &v94,
                v90) < 0 )
    {
      goto LABEL_105;
    }
    v20 = v91;
    v18 = v94;
    v9 += v23 + 26;
  }
  if ( v12 )
  {
    if ( v18 - 1 > 0x7FFFFFFE )
    {
LABEL_105:
      free(v22);
      return 0;
    }
    v24 = (_DWORD)v12 - (_DWORD)v9;
    v25 = v24;
    if ( (unsigned __int64)v24 >= 0x7FFFFFFF )
    {
      *v20 = 0;
      goto LABEL_105;
    }
    v26 = v9;
    v27 = v18;
    v28 = v20;
    v29 = 0;
    do
    {
      if ( !v25 )
        break;
      if ( !*v26 )
        break;
      *v28++ = *v26++;
      --v25;
      ++v29;
      --v27;
    }
    while ( v27 );
    v30 = v29 - 1;
    if ( v27 )
      v30 = v29;
    v31 = v28 - 1;
    v32 = v27 != 0 ? 0 : 0x8007007A;
    if ( v27 )
      v31 = v28;
    *v31 = 0;
    if ( ((v32 + 0x80000000) & 0x80000000) == 0 && v32 != -2147024774 )
      goto LABEL_105;
    v33 = v18 - v30;
    v34 = &v20[v30];
    if ( (v27 != 0) - 1 < 0 || (unsigned __int64)(v33 - 1) > 0x7FFFFFFE )
      goto LABEL_105;
    v35 = v8;
    if ( v8 >= 0x7FFFFFFF )
    {
      *v34 = 0;
      goto LABEL_105;
    }
    v36 = v95;
    v37 = 0;
    v38 = v33;
    v39 = v34;
    do
    {
      if ( !v35 )
        break;
      if ( !*v36 )
        break;
      *v39++ = *v36++;
      --v35;
      ++v37;
      --v38;
    }
    while ( v38 );
    v40 = v37 - 1;
    if ( v38 )
      v40 = v37;
    v41 = v39 - 1;
    v42 = v38 != 0 ? 0 : 0x8007007A;
    if ( v38 )
      v41 = v39;
    *v41 = 0;
    if ( (int)(v42 + 0x80000000) >= 0 && v42 != -2147024774 )
      goto LABEL_105;
    v18 = v33 - v40;
    v20 = &v34[v40];
    if ( v42 < 0 )
      goto LABEL_105;
    v9 += v24 + 36;
  }
  v43 = (int)v93;
  if ( v93 )
  {
    v44 = -1;
    do
      ++v44;
    while ( aNls[v44] );
    if ( v18 - 1 > 0x7FFFFFFE )
      goto LABEL_105;
    v45 = (_DWORD)v93 - (_DWORD)v9 - v44 - 2;
    v46 = v45;
    if ( (unsigned __int64)v45 >= 0x7FFFFFFF )
    {
      *v20 = 0;
      goto LABEL_105;
    }
    v47 = v9;
    v48 = v18;
    v49 = v20;
    v50 = 0;
    do
    {
      if ( !v46 )
        break;
      if ( !*v47 )
        break;
      *v49++ = *v47++;
      --v46;
      ++v50;
      --v48;
    }
    while ( v48 );
    v51 = v50 - 1;
    if ( v48 )
      v51 = v50;
    v52 = v49 - 1;
    v53 = v48 != 0 ? 0 : 0x8007007A;
    if ( v48 )
      v52 = v49;
    *v52 = 0;
    if ( ((v53 + 0x80000000) & 0x80000000) == 0 && v53 != -2147024774 )
      goto LABEL_105;
    v54 = v18 - v51;
    v55 = &v20[v51];
    if ( (v48 != 0) - 1 < 0 || (unsigned __int64)(v54 - 1) > 0x7FFFFFFE )
      goto LABEL_105;
    v56 = 48;
    v57 = "OPT:\"http://schemas.upnp.org/upnp/1/0/\"; ns=01\r\n";
    v58 = v54;
    v59 = v55;
    v60 = 0;
    do
    {
      if ( !v56 )
        break;
      if ( !*v57 )
        break;
      *v59++ = *v57++;
      --v56;
      ++v60;
      --v58;
    }
    while ( v58 );
    v61 = v60 - 1;
    if ( v58 )
      v61 = v60;
    v62 = v59 - 1;
    v63 = v58 != 0 ? 0 : 0x8007007A;
    if ( v58 )
      v62 = v59;
    *v62 = 0;
    if ( ((v63 + 0x80000000) & 0x80000000) == 0 && v63 != -2147024774 )
      goto LABEL_105;
    v64 = v54 - v61;
    v65 = &v55[v61];
    if ( (v58 != 0) - 1 < 0 || (unsigned __int64)(v64 - 1) > 0x7FFFFFFE )
      goto LABEL_105;
    v66 = 3;
    v67 = "01-";
    v68 = v64;
    v69 = &v55[v61];
    v70 = 0;
    do
    {
      if ( !v66 )
        break;
      if ( !*v67 )
        break;
      *v69++ = *v67++;
      --v66;
      ++v70;
      --v68;
    }
    while ( v68 );
    v71 = v70 - 1;
    if ( v68 )
      v71 = v70;
    v72 = v69 - 1;
    v73 = v68 != 0 ? 0 : 0x8007007A;
    if ( v68 )
      v72 = v69;
    *v72 = 0;
    if ( ((v73 + 0x80000000) & 0x80000000) == 0 && v73 != -2147024774 )
      goto LABEL_105;
    v74 = v64 - v71;
    v75 = &v65[v71];
    if ( (v68 != 0) - 1 < 0 || (unsigned __int64)(v74 - 1) > 0x7FFFFFFE )
      goto LABEL_105;
    v76 = &v9[v45];
    v77 = v43 - (_DWORD)v76;
    if ( (unsigned __int64)v77 >= 0x7FFFFFFF )
    {
      *v75 = 0;
      goto LABEL_105;
    }
    v78 = v77;
    v79 = &v9[v45];
    v80 = v74;
    v81 = &v65[v71];
    v82 = 0;
    do
    {
      if ( !v78 )
        break;
      if ( !*v79 )
        break;
      *v81++ = *v79++;
      --v78;
      ++v82;
      --v80;
    }
    while ( v80 );
    v83 = v82 - 1;
    if ( v80 )
      v83 = v82;
    v84 = v81 - 1;
    v85 = v80 != 0 ? 0 : 0x8007007A;
    if ( v80 )
      v84 = v81;
    *v84 = 0;
    if ( ((v85 + 0x80000000) & 0x80000000) == 0 && v85 != -2147024774 )
      goto LABEL_105;
    v86 = v74 - v83;
    v91 = &v75[v83];
    v94 = v86;
    if ( (v80 != 0) - 1 < 0 || (int)StringCbCopyNExA(&v75[v83], v86, v96, a5, &v91, &v94, v89) < 0 )
      goto LABEL_105;
    v20 = v91;
    v18 = v94;
    v9 = &v76[v77 + 36];
  }
  if ( (int)StringCbCopyExA(v20, v18, v9, &v91, &v94, v88) < 0 )
    goto LABEL_105;
  *a8 = (char *)v22;
  return 1;
}

```

## disassembly

```asm
0x1800132f8  mov     [rsp-38h+arg_10], rbx
0x1800132fd  mov     [rsp-38h+arg_18], r9
0x180013302  mov     [rsp-38h+arg_8], rdx
0x180013307  push    rbp
0x180013308  push    rsi
0x180013309  push    rdi
0x18001330a  push    r12
0x18001330c  push    r13
0x18001330e  push    r14
0x180013310  push    r15
0x180013312  mov     rbp, rsp
0x180013315  sub     rsp, 60h
0x180013319  movsxd  r13, r8d
0x18001331c  mov     rdi, rcx
0x18001331f  mov     rsi, rcx
0x180013322  call    cs:__imp_lstrlenA
0x180013328  lea     rdx, a5479f6b671ac44; "5479f6b6-71ac-44fc-9164-7e901a557f81"
0x18001332f  mov     rcx, rsi; Str
0x180013332  mov     ebx, eax
0x180013334  mov     rax, [rbp+arg_38]
0x180013338  mov     qword ptr [rax], 0
0x18001333f  call    cs:__imp_strstr
0x180013345  mov     r15, rax
0x180013348  test    rax, rax
0x18001334b  jz      short loc_180013353
0x18001334d  add     ebx, 0FFFFFFDCh
0x180013350  add     ebx, r13d
0x180013353  lea     rdx, a0bd2834dD10e46; "0bd2834d-d10e-46e9-84ba-34e538bea2d3"
0x18001335a  mov     rcx, rdi; Str
0x18001335d  call    cs:__imp_strstr
0x180013363  mov     [rbp+var_10], rax
0x180013367  test    rax, rax
0x18001336a  jz      short loc_180013374
0x18001336c  mov     ecx, [rbp+arg_20]
0x18001336f  add     ecx, 0Fh
0x180013372  add     ebx, ecx
0x180013374  cmp     [rbp+arg_28], 1
0x180013378  mov     r14d, [rbp+arg_30]
0x18001337c  jnz     short loc_1800133BC
0x18001337e  lea     rdx, c_szIPv4HostTag; "Host: 239.255.255.250:1900"
0x180013385  mov     rcx, rdi; Str
0x180013388  call    cs:__imp_strstr
0x18001338e  mov     rsi, rax
0x180013391  test    rax, rax
0x180013394  jz      short loc_1800133B8
0x180013396  cmp     r14d, 6
0x18001339a  jnb     short loc_1800133B8
0x18001339c  lea     rax, __ImageBase
0x1800133a3  mov     r12d, 1
0x1800133a9  mov     ecx, ds:rva c_rgcchIPv6HostTagSizes[rax+r14*4]
0x1800133b1  add     ecx, 0FFFFFFE6h
0x1800133b4  add     ebx, ecx
0x1800133b6  jmp     short loc_1800133CD
0x1800133b8  mov     rax, [rbp+var_10]
0x1800133bc  xor     r12d, r12d
0x1800133bf  test    r15, r15
0x1800133c2  jnz     short loc_1800133CD
0x1800133c4  test    rax, rax
0x1800133c7  jz      loc_180013914
0x1800133cd  lea     eax, [rbx+1]
0x1800133d0  mov     ecx, eax; Size
0x1800133d2  mov     ebx, eax
0x1800133d4  call    cs:__imp_malloc
0x1800133da  mov     [rbp+Block], rax
0x1800133de  test    rax, rax
0x1800133e1  jz      loc_1800138F3
0x1800133e7  mov     r8d, ebx; Size
0x1800133ea  xor     edx, edx; Val
0x1800133ec  mov     rcx, rax; void *
0x1800133ef  call    memset_0
0x1800133f4  mov     rcx, [rbp+Block]; char *
0x1800133f8  test    r12d, r12d
0x1800133fb  mov     [rbp+var_20], rcx
0x1800133ff  mov     r12, rcx
0x180013402  mov     [rbp+arg_0], rbx
0x180013406  jz      short loc_180013481
0x180013408  lea     rax, [rbp+arg_0]
0x18001340c  sub     esi, edi
0x18001340e  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x180013413  mov     r8, rdi; char *
0x180013416  lea     rax, [rbp+var_20]
0x18001341a  movsxd  rsi, esi
0x18001341d  mov     r9, rsi; unsigned __int64
0x180013420  mov     [rsp+60h+var_40], rax; char **
0x180013425  mov     edx, ebx; unsigned __int64
0x180013427  call    ?StringCbCopyNExA@@YAJPEAD_KPEBD1PEAPEADPEA_KK@Z; StringCbCopyNExA(char *,unsigned __int64,char const *,unsigned __int64,char * *,unsigned __int64 *,ulong)
0x18001342c  test    eax, eax
0x18001342e  js      loc_1800138EA
0x180013434  mov     rdx, [rbp+arg_0]; unsigned __int64
0x180013438  lea     rcx, __ImageBase
0x18001343f  mov     r9d, ds:rva c_rgcchIPv6HostTagSizes[rcx+r14*4]; unsigned __int64
0x180013447  lea     rax, [rbp+arg_0]
0x18001344b  mov     r8, ds:rva c_rgszIPv6HostTags[rcx+r14*8]; char *
0x180013453  mov     rcx, [rbp+var_20]; char *
0x180013457  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x18001345c  lea     rax, [rbp+var_20]
0x180013460  mov     [rsp+60h+var_40], rax; char **
0x180013465  call    ?StringCbCopyNExA@@YAJPEAD_KPEBD1PEAPEADPEA_KK@Z; StringCbCopyNExA(char *,unsigned __int64,char const *,unsigned __int64,char * *,unsigned __int64 *,ulong)
0x18001346a  test    eax, eax
0x18001346c  js      loc_1800138EA
0x180013472  mov     rcx, [rbp+var_20]
0x180013476  add     rdi, 1Ah
0x18001347a  mov     rbx, [rbp+arg_0]
0x18001347e  add     rdi, rsi
0x180013481  xor     esi, esi
0x180013483  test    r15, r15
0x180013486  jz      loc_1800135E9
0x18001348c  lea     rax, [rbx-1]
0x180013490  cmp     rax, 7FFFFFFEh
0x180013496  ja      loc_1800138EA
0x18001349c  sub     r15d, edi
0x18001349f  movsxd  rax, r15d
0x1800134a2  cmp     rax, 7FFFFFFFh
0x1800134a8  jb      short loc_1800134B2
0x1800134aa  mov     [rcx], sil
0x1800134ad  jmp     loc_1800138EA
0x1800134b2  mov     rdx, rdi
0x1800134b5  mov     r8, rbx
0x1800134b8  mov     r9, rcx
0x1800134bb  mov     r11, rsi
0x1800134be  mov     r14d, 1
0x1800134c4  test    rax, rax
0x1800134c7  jz      short loc_1800134E5
0x1800134c9  mov     r10b, [rdx]
0x1800134cc  test    r10b, r10b
0x1800134cf  jz      short loc_1800134E5
0x1800134d1  mov     [r9], r10b
0x1800134d4  add     rdx, r14
0x1800134d7  add     r9, r14
0x1800134da  sub     rax, r14
0x1800134dd  add     r11, r14
0x1800134e0  sub     r8, r14
0x1800134e3  jnz     short loc_1800134C4
0x1800134e5  test    r8, r8
0x1800134e8  lea     r10, [r11-1]
0x1800134ec  mov     rax, r8
0x1800134ef  cmovnz  r10, r11
0x1800134f3  neg     rax
0x1800134f6  mov     r11d, 8007007Ah
0x1800134fc  lea     rax, [r9-1]
0x180013500  sbb     edx, edx
0x180013502  not     edx
0x180013504  and     edx, r11d
0x180013507  test    r8, r8
0x18001350a  mov     r8d, 80000000h
0x180013510  cmovnz  rax, r9
0x180013514  mov     [rax], sil
0x180013517  lea     eax, [rdx+r8]
0x18001351b  test    r8d, eax
0x18001351e  jnz     short loc_180013529
0x180013520  cmp     edx, r11d
0x180013523  jnz     loc_1800138EA
0x180013529  sub     rbx, r10
0x18001352c  lea     r9, [r10+rcx]
0x180013530  test    edx, edx
0x180013532  js      loc_1800138EA
0x180013538  lea     rax, [rbx-1]
0x18001353c  cmp     rax, 7FFFFFFEh
0x180013542  ja      loc_1800138EA
0x180013548  mov     rax, r13
0x18001354b  cmp     r13, 7FFFFFFFh
0x180013552  jb      short loc_18001355C
0x180013554  mov     [r9], sil
0x180013557  jmp     loc_1800138EA
0x18001355c  mov     r11, [rbp+arg_8]
0x180013560  xor     r13d, r13d
0x180013563  mov     edx, r13d
0x180013566  mov     rcx, rbx
0x180013569  mov     r8, r9
0x18001356c  test    rax, rax
0x18001356f  jz      short loc_18001358D
0x180013571  mov     r10b, [r11]
0x180013574  test    r10b, r10b
0x180013577  jz      short loc_18001358D
0x180013579  mov     [r8], r10b
0x18001357c  add     r11, r14
0x18001357f  add     r8, r14
0x180013582  sub     rax, r14
0x180013585  add     rdx, r14
0x180013588  sub     rcx, r14
0x18001358b  jnz     short loc_18001356C
0x18001358d  test    rcx, rcx
0x180013590  lea     r10, [rdx-1]
0x180013594  mov     rax, rcx
0x180013597  mov     esi, 8007007Ah
0x18001359c  cmovnz  r10, rdx
0x1800135a0  neg     rax
0x1800135a3  lea     rax, [r8-1]
0x1800135a7  sbb     edx, edx
0x1800135a9  not     edx
0x1800135ab  and     edx, esi
0x1800135ad  test    rcx, rcx
0x1800135b0  cmovnz  rax, r8
0x1800135b4  mov     r8d, 80000000h
0x1800135ba  mov     [rax], r13b
0x1800135bd  lea     eax, [rdx+r8]
0x1800135c1  test    r8d, eax
0x1800135c4  jnz     short loc_1800135CE
0x1800135c6  cmp     edx, esi
0x1800135c8  jnz     loc_1800138EA
0x1800135ce  sub     rbx, r10
0x1800135d1  lea     rcx, [r10+r9]
0x1800135d5  test    edx, edx
0x1800135d7  js      loc_1800138EA
0x1800135dd  movsxd  rax, r15d
0x1800135e0  add     rax, 24h ; '$'
0x1800135e4  add     rdi, rax
0x1800135e7  jmp     short loc_1800135F1
0x1800135e9  xor     r13d, r13d
0x1800135ec  mov     esi, 8007007Ah
0x1800135f1  mov     r14, [rbp+var_10]
0x1800135f5  test    r14, r14
0x1800135f8  jz      loc_1800138CE
0x1800135fe  mov     rax, cs:off_180038328; "NLS"
0x180013605  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180013609  inc     rdx
0x18001360c  cmp     [rax+rdx], r13b
0x180013610  jnz     short loc_180013609
0x180013612  lea     rax, [rbx-1]
0x180013616  cmp     rax, 7FFFFFFEh
0x18001361c  ja      loc_1800138EA
0x180013622  mov     r15d, r14d
0x180013625  sub     r15d, edi
0x180013628  sub     r15d, edx
0x18001362b  add     r15d, 0FFFFFFFEh
0x18001362f  movsxd  rax, r15d
0x180013632  cmp     rax, 7FFFFFFFh
0x180013638  jb      short loc_180013642
0x18001363a  mov     [rcx], r13b
0x18001363d  jmp     loc_1800138EA
0x180013642  mov     rdx, rdi
0x180013645  mov     r8, rbx
0x180013648  mov     r9, rcx
0x18001364b  mov     r10, r13
0x18001364e  test    rax, rax
0x180013651  jz      short loc_180013670
0x180013653  mov     r11b, [rdx]
0x180013656  test    r11b, r11b
0x180013659  jz      short loc_180013670
0x18001365b  mov     [r9], r11b
0x18001365e  inc     rdx
0x180013661  inc     r9
0x180013664  dec     rax
0x180013667  inc     r10
0x18001366a  sub     r8, 1
0x18001366e  jnz     short loc_18001364E
0x180013670  test    r8, r8
0x180013673  lea     r11, [r10-1]
0x180013677  mov     rax, r8
0x18001367a  cmovnz  r11, r10
0x18001367e  neg     rax
0x180013681  lea     rax, [r9-1]
0x180013685  sbb     edx, edx
0x180013687  not     edx
0x180013689  and     edx, esi
0x18001368b  test    r8, r8
0x18001368e  mov     r8d, 80000000h
0x180013694  cmovnz  rax, r9
0x180013698  mov     [rax], r13b
0x18001369b  lea     eax, [rdx+r8]
0x18001369f  test    r8d, eax
0x1800136a2  jnz     short loc_1800136AC
0x1800136a4  cmp     edx, esi
0x1800136a6  jnz     loc_1800138EA
0x1800136ac  sub     rbx, r11
0x1800136af  lea     rsi, [r11+rcx]
0x1800136b3  test    edx, edx
0x1800136b5  js      loc_1800138EA
0x1800136bb  lea     rax, [rbx-1]
0x1800136bf  cmp     rax, 7FFFFFFEh
0x1800136c5  ja      loc_1800138EA
0x1800136cb  mov     eax, 30h ; '0'
0x1800136d0  lea     rcx, aOptHttpSchemas; "OPT:\"http://schemas.upnp.org/upnp/1/0/"...
0x1800136d7  mov     rdx, rbx
0x1800136da  mov     r8, rsi
0x1800136dd  mov     r9, r13
0x1800136e0  test    rax, rax
0x1800136e3  jz      short loc_180013702
0x1800136e5  mov     r10b, [rcx]
0x1800136e8  test    r10b, r10b
0x1800136eb  jz      short loc_180013702
0x1800136ed  mov     [r8], r10b
0x1800136f0  inc     rcx
0x1800136f3  inc     r8
0x1800136f6  dec     rax
0x1800136f9  inc     r9
0x1800136fc  sub     rdx, 1
0x180013700  jnz     short loc_1800136E0
0x180013702  test    rdx, rdx
0x180013705  lea     r10, [r9-1]
0x180013709  mov     rax, rdx
0x18001370c  mov     r11d, 8007007Ah
0x180013712  cmovnz  r10, r9
0x180013716  neg     rax
0x180013719  lea     rax, [r8-1]
0x18001371d  sbb     ecx, ecx
0x18001371f  not     ecx
0x180013721  and     ecx, r11d
0x180013724  test    rdx, rdx
0x180013727  mov     edx, 80000000h
  ... truncated ...
```
