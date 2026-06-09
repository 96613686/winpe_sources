# FReplaceTokenInLocation(char const *,char *,int,char *,int,int,ulong,char * *)

- ea: `0x180015f20`
- end: `0x180016568`
- name: `?FReplaceTokenInLocation@@YAHPEBDPEADH1HHKPEAPEAD@Z`
- size: `1608`
- prototype: `__int64 __usercall@<rax>(const char *@<rcx>, char *@<rdx>, int@<r8d>, char *@<r9>, int, int, unsigned int, char **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800152c0`
- `0x180015530`

## callees

- `0x180015f20`
- `0x180019cd0`
- `0x180019ed0`
- `0x18002911c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016533`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016533`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016014`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016014`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015f6d`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015f91`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015fc2`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015f6d`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015f91`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180015fc2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180015f4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180015f4a`

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
0x180015f20  mov     [rsp-38h+arg_10], rbx
0x180015f25  mov     [rsp-38h+arg_18], r9
0x180015f2a  mov     [rsp-38h+arg_8], rdx
0x180015f2f  push    rbp
0x180015f30  push    rsi
0x180015f31  push    rdi
0x180015f32  push    r12
0x180015f34  push    r13
0x180015f36  push    r14
0x180015f38  push    r15
0x180015f3a  mov     rbp, rsp
0x180015f3d  sub     rsp, 60h
0x180015f41  movsxd  r13, r8d
0x180015f44  mov     rdi, rcx
0x180015f47  mov     rsi, rcx
0x180015f4a  call    cs:__imp_lstrlenA
0x180015f51  nop     dword ptr [rax+rax+00h]
0x180015f56  lea     rdx, a5479f6b671ac44; "5479f6b6-71ac-44fc-9164-7e901a557f81"
0x180015f5d  mov     rcx, rsi; Str
0x180015f60  mov     ebx, eax
0x180015f62  mov     rax, [rbp+arg_38]
0x180015f66  mov     qword ptr [rax], 0
0x180015f6d  call    cs:__imp_strstr
0x180015f74  nop     dword ptr [rax+rax+00h]
0x180015f79  mov     r15, rax
0x180015f7c  test    rax, rax
0x180015f7f  jz      short loc_180015F87
0x180015f81  add     ebx, 0FFFFFFDCh
0x180015f84  add     ebx, r13d
0x180015f87  lea     rdx, a0bd2834dD10e46; "0bd2834d-d10e-46e9-84ba-34e538bea2d3"
0x180015f8e  mov     rcx, rdi; Str
0x180015f91  call    cs:__imp_strstr
0x180015f98  nop     dword ptr [rax+rax+00h]
0x180015f9d  mov     [rbp+var_10], rax
0x180015fa1  test    rax, rax
0x180015fa4  jz      short loc_180015FAE
0x180015fa6  mov     ecx, [rbp+arg_20]
0x180015fa9  add     ecx, 0Fh
0x180015fac  add     ebx, ecx
0x180015fae  cmp     [rbp+arg_28], 1
0x180015fb2  mov     r14d, [rbp+arg_30]
0x180015fb6  jnz     short loc_180015FFC
0x180015fb8  lea     rdx, c_szIPv4HostTag; "Host: 239.255.255.250:1900"
0x180015fbf  mov     rcx, rdi; Str
0x180015fc2  call    cs:__imp_strstr
0x180015fc9  nop     dword ptr [rax+rax+00h]
0x180015fce  mov     rsi, rax
0x180015fd1  test    rax, rax
0x180015fd4  jz      short loc_180015FF8
0x180015fd6  cmp     r14d, 6
0x180015fda  jnb     short loc_180015FF8
0x180015fdc  lea     rax, __ImageBase
0x180015fe3  mov     r12d, 1
0x180015fe9  mov     ecx, ds:rva c_rgcchIPv6HostTagSizes[rax+r14*4]
0x180015ff1  add     ecx, 0FFFFFFE6h
0x180015ff4  add     ebx, ecx
0x180015ff6  jmp     short loc_18001600D
0x180015ff8  mov     rax, [rbp+var_10]
0x180015ffc  xor     r12d, r12d
0x180015fff  test    r15, r15
0x180016002  jnz     short loc_18001600D
0x180016004  test    rax, rax
0x180016007  jz      loc_180016561
0x18001600d  lea     eax, [rbx+1]
0x180016010  mov     ecx, eax; Size
0x180016012  mov     ebx, eax
0x180016014  call    cs:__imp_malloc
0x18001601b  nop     dword ptr [rax+rax+00h]
0x180016020  mov     [rbp+Block], rax
0x180016024  test    rax, rax
0x180016027  jz      loc_18001653F
0x18001602d  mov     r8d, ebx; Size
0x180016030  xor     edx, edx; Val
0x180016032  mov     rcx, rax; void *
0x180016035  call    memset_0
0x18001603a  mov     rcx, [rbp+Block]; char *
0x18001603e  test    r12d, r12d
0x180016041  mov     [rbp+var_20], rcx
0x180016045  mov     r12, rcx
0x180016048  mov     [rbp+arg_0], rbx
0x18001604c  jz      short loc_1800160C7
0x18001604e  lea     rax, [rbp+arg_0]
0x180016052  sub     esi, edi
0x180016054  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x180016059  mov     r8, rdi; char *
0x18001605c  lea     rax, [rbp+var_20]
0x180016060  movsxd  rsi, esi
0x180016063  mov     r9, rsi; unsigned __int64
0x180016066  mov     [rsp+60h+var_40], rax; char **
0x18001606b  mov     edx, ebx; unsigned __int64
0x18001606d  call    ?StringCbCopyNExA@@YAJPEAD_KPEBD1PEAPEADPEA_KK@Z; StringCbCopyNExA(char *,unsigned __int64,char const *,unsigned __int64,char * *,unsigned __int64 *,ulong)
0x180016072  test    eax, eax
0x180016074  js      loc_180016530
0x18001607a  mov     rdx, [rbp+arg_0]; unsigned __int64
0x18001607e  lea     rcx, __ImageBase
0x180016085  mov     r9d, ds:rva c_rgcchIPv6HostTagSizes[rcx+r14*4]; unsigned __int64
0x18001608d  lea     rax, [rbp+arg_0]
0x180016091  mov     r8, ds:rva c_rgszIPv6HostTags[rcx+r14*8]; char *
0x180016099  mov     rcx, [rbp+var_20]; char *
0x18001609d  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x1800160a2  lea     rax, [rbp+var_20]
0x1800160a6  mov     [rsp+60h+var_40], rax; char **
0x1800160ab  call    ?StringCbCopyNExA@@YAJPEAD_KPEBD1PEAPEADPEA_KK@Z; StringCbCopyNExA(char *,unsigned __int64,char const *,unsigned __int64,char * *,unsigned __int64 *,ulong)
0x1800160b0  test    eax, eax
0x1800160b2  js      loc_180016530
0x1800160b8  mov     rcx, [rbp+var_20]
0x1800160bc  add     rdi, 1Ah
0x1800160c0  mov     rbx, [rbp+arg_0]
0x1800160c4  add     rdi, rsi
0x1800160c7  xor     esi, esi
0x1800160c9  test    r15, r15
0x1800160cc  jz      loc_18001622F
0x1800160d2  lea     rax, [rbx-1]
0x1800160d6  cmp     rax, 7FFFFFFEh
0x1800160dc  ja      loc_180016530
0x1800160e2  sub     r15d, edi
0x1800160e5  movsxd  rax, r15d
0x1800160e8  cmp     rax, 7FFFFFFFh
0x1800160ee  jb      short loc_1800160F8
0x1800160f0  mov     [rcx], sil
0x1800160f3  jmp     loc_180016530
0x1800160f8  mov     rdx, rdi
0x1800160fb  mov     r8, rbx
0x1800160fe  mov     r9, rcx
0x180016101  mov     r11, rsi
0x180016104  mov     r14d, 1
0x18001610a  test    rax, rax
0x18001610d  jz      short loc_18001612B
0x18001610f  mov     r10b, [rdx]
0x180016112  test    r10b, r10b
0x180016115  jz      short loc_18001612B
0x180016117  mov     [r9], r10b
0x18001611a  add     rdx, r14
0x18001611d  add     r9, r14
0x180016120  sub     rax, r14
0x180016123  add     r11, r14
0x180016126  sub     r8, r14
0x180016129  jnz     short loc_18001610A
0x18001612b  test    r8, r8
0x18001612e  lea     r10, [r11-1]
0x180016132  mov     rax, r8
0x180016135  cmovnz  r10, r11
0x180016139  neg     rax
0x18001613c  mov     r11d, 8007007Ah
0x180016142  lea     rax, [r9-1]
0x180016146  sbb     edx, edx
0x180016148  not     edx
0x18001614a  and     edx, r11d
0x18001614d  test    r8, r8
0x180016150  mov     r8d, 80000000h
0x180016156  cmovnz  rax, r9
0x18001615a  mov     [rax], sil
0x18001615d  lea     eax, [rdx+r8]
0x180016161  test    r8d, eax
0x180016164  jnz     short loc_18001616F
0x180016166  cmp     edx, r11d
0x180016169  jnz     loc_180016530
0x18001616f  sub     rbx, r10
0x180016172  lea     r9, [r10+rcx]
0x180016176  test    edx, edx
0x180016178  js      loc_180016530
0x18001617e  lea     rax, [rbx-1]
0x180016182  cmp     rax, 7FFFFFFEh
0x180016188  ja      loc_180016530
0x18001618e  mov     rax, r13
0x180016191  cmp     r13, 7FFFFFFFh
0x180016198  jb      short loc_1800161A2
0x18001619a  mov     [r9], sil
0x18001619d  jmp     loc_180016530
0x1800161a2  mov     r11, [rbp+arg_8]
0x1800161a6  xor     r13d, r13d
0x1800161a9  mov     edx, r13d
0x1800161ac  mov     rcx, rbx
0x1800161af  mov     r8, r9
0x1800161b2  test    rax, rax
0x1800161b5  jz      short loc_1800161D3
0x1800161b7  mov     r10b, [r11]
0x1800161ba  test    r10b, r10b
0x1800161bd  jz      short loc_1800161D3
0x1800161bf  mov     [r8], r10b
0x1800161c2  add     r11, r14
0x1800161c5  add     r8, r14
0x1800161c8  sub     rax, r14
0x1800161cb  add     rdx, r14
0x1800161ce  sub     rcx, r14
0x1800161d1  jnz     short loc_1800161B2
0x1800161d3  test    rcx, rcx
0x1800161d6  lea     r10, [rdx-1]
0x1800161da  mov     rax, rcx
0x1800161dd  mov     esi, 8007007Ah
0x1800161e2  cmovnz  r10, rdx
0x1800161e6  neg     rax
0x1800161e9  lea     rax, [r8-1]
0x1800161ed  sbb     edx, edx
0x1800161ef  not     edx
0x1800161f1  and     edx, esi
0x1800161f3  test    rcx, rcx
0x1800161f6  cmovnz  rax, r8
0x1800161fa  mov     r8d, 80000000h
0x180016200  mov     [rax], r13b
0x180016203  lea     eax, [rdx+r8]
0x180016207  test    r8d, eax
0x18001620a  jnz     short loc_180016214
0x18001620c  cmp     edx, esi
0x18001620e  jnz     loc_180016530
0x180016214  sub     rbx, r10
0x180016217  lea     rcx, [r10+r9]
0x18001621b  test    edx, edx
0x18001621d  js      loc_180016530
0x180016223  movsxd  rax, r15d
0x180016226  add     rax, 24h ; '$'
0x18001622a  add     rdi, rax
0x18001622d  jmp     short loc_180016237
0x18001622f  xor     r13d, r13d
0x180016232  mov     esi, 8007007Ah
0x180016237  mov     r14, [rbp+var_10]
0x18001623b  test    r14, r14
0x18001623e  jz      loc_180016514
0x180016244  mov     rax, cs:off_18003B328; "NLS"
0x18001624b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001624f  inc     rdx
0x180016252  cmp     [rax+rdx], r13b
0x180016256  jnz     short loc_18001624F
0x180016258  lea     rax, [rbx-1]
0x18001625c  cmp     rax, 7FFFFFFEh
0x180016262  ja      loc_180016530
0x180016268  mov     r15d, r14d
0x18001626b  sub     r15d, edi
0x18001626e  sub     r15d, edx
0x180016271  add     r15d, 0FFFFFFFEh
0x180016275  movsxd  rax, r15d
0x180016278  cmp     rax, 7FFFFFFFh
0x18001627e  jb      short loc_180016288
0x180016280  mov     [rcx], r13b
0x180016283  jmp     loc_180016530
0x180016288  mov     rdx, rdi
0x18001628b  mov     r8, rbx
0x18001628e  mov     r9, rcx
0x180016291  mov     r10, r13
0x180016294  test    rax, rax
0x180016297  jz      short loc_1800162B6
0x180016299  mov     r11b, [rdx]
0x18001629c  test    r11b, r11b
0x18001629f  jz      short loc_1800162B6
0x1800162a1  mov     [r9], r11b
0x1800162a4  inc     rdx
0x1800162a7  inc     r9
0x1800162aa  dec     rax
0x1800162ad  inc     r10
0x1800162b0  sub     r8, 1
0x1800162b4  jnz     short loc_180016294
0x1800162b6  test    r8, r8
0x1800162b9  lea     r11, [r10-1]
0x1800162bd  mov     rax, r8
0x1800162c0  cmovnz  r11, r10
0x1800162c4  neg     rax
0x1800162c7  lea     rax, [r9-1]
0x1800162cb  sbb     edx, edx
0x1800162cd  not     edx
0x1800162cf  and     edx, esi
0x1800162d1  test    r8, r8
0x1800162d4  mov     r8d, 80000000h
0x1800162da  cmovnz  rax, r9
0x1800162de  mov     [rax], r13b
0x1800162e1  lea     eax, [rdx+r8]
0x1800162e5  test    r8d, eax
0x1800162e8  jnz     short loc_1800162F2
0x1800162ea  cmp     edx, esi
0x1800162ec  jnz     loc_180016530
0x1800162f2  sub     rbx, r11
0x1800162f5  lea     rsi, [r11+rcx]
0x1800162f9  test    edx, edx
0x1800162fb  js      loc_180016530
0x180016301  lea     rax, [rbx-1]
0x180016305  cmp     rax, 7FFFFFFEh
0x18001630b  ja      loc_180016530
0x180016311  mov     eax, 30h ; '0'
0x180016316  lea     rcx, aOptHttpSchemas; "OPT:\"http://schemas.upnp.org/upnp/1/0/"...
0x18001631d  mov     rdx, rbx
0x180016320  mov     r8, rsi
0x180016323  mov     r9, r13
0x180016326  test    rax, rax
0x180016329  jz      short loc_180016348
0x18001632b  mov     r10b, [rcx]
0x18001632e  test    r10b, r10b
0x180016331  jz      short loc_180016348
0x180016333  mov     [r8], r10b
0x180016336  inc     rcx
0x180016339  inc     r8
0x18001633c  dec     rax
0x18001633f  inc     r9
0x180016342  sub     rdx, 1
0x180016346  jnz     short loc_180016326
0x180016348  test    rdx, rdx
0x18001634b  lea     r10, [r9-1]
0x18001634f  mov     rax, rdx
0x180016352  mov     r11d, 8007007Ah
0x180016358  cmovnz  r10, r9
0x18001635c  neg     rax
0x18001635f  lea     rax, [r8-1]
  ... truncated ...
```
