# CCollationsSTVF::CopyRow(bool)

- ea: `0x100437b90`
- end: `0x100438134`
- name: `?CopyRow@CCollationsSTVF@@AEAAJ_N@Z`
- size: `1444`
- prototype: `__int64 __fastcall(CCollationsSTVF *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1004379d0`

## callees

- `0x100437b90`
- `0x100438380`
- `0x100439350`
- `0x100497450`
- `0x100497e90`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437d18`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437d64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437e14`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437e78`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437ee4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437f40`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437fb0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100438008`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100438087`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437d18`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437d64`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437e14`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437e78`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437ee4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437f40`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100437fb0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100438008`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100438087`

## string_xrefs

- `0x100437d7b`: `binary code point comparison sort`

## pseudocode

```c
__int64 __fastcall CCollationsSTVF::CopyRow(CCollationsSTVF *this, char a2)
{
  __int64 v2; // rdx
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // r9
  bool v7; // zf
  unsigned int v8; // r15d
  __int64 v9; // rcx
  __int64 v10; // rax
  char *v11; // rbp
  unsigned __int8 v12; // si
  _WORD *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  int i; // ecx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v20; // rax
  wchar_t *v21; // rdi
  struct __crt_locale_pointers *v22; // rax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rbx
  wchar_t *v27; // rdi
  struct __crt_locale_pointers *v28; // rax
  const wchar_t *v29; // rcx
  __int64 v30; // rax
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rbx
  wchar_t *v33; // rdi
  struct __crt_locale_pointers *v34; // rax
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rbx
  wchar_t *v39; // rdi
  struct __crt_locale_pointers *v40; // rax
  const wchar_t *v41; // rcx
  __int64 v42; // rcx
  unsigned int v43; // ecx
  unsigned int v44; // eax
  unsigned __int64 v45; // rbx
  struct __crt_locale_pointers *v46; // rax
  __int64 v47; // rax
  const wchar_t *v48; // rbx
  unsigned __int64 v49; // rdi
  struct __crt_locale_pointers *v50; // rax
  unsigned __int64 v51; // rbx
  struct __crt_locale_pointers *v52; // rax
  __int64 v53; // rax
  unsigned int v54; // r15d
  unsigned __int64 v55; // rsi
  __int64 v56; // rbx
  struct __crt_locale_pointers *v57; // rax
  __int64 v59; // [rsp+20h] [rbp-58h]
  __int64 v60; // [rsp+20h] [rbp-58h]
  __int64 v61; // [rsp+20h] [rbp-58h]
  __int64 v62; // [rsp+20h] [rbp-58h]
  __int64 v63; // [rsp+28h] [rbp-50h]
  int v64; // [rsp+88h] [rbp+10h] BYREF

  LOBYTE(v64) = a2;
  v2 = *((int *)this + 26);
  v4 = -1;
  if ( (int)v2 < 99 )
  {
    v9 = *((int *)this + 28);
    v10 = *((_QWORD *)this + 12);
    v64 = 256;
    v8 = (unsigned __int8)byte_10086AA21[2 * v2]
       | ((*((_BYTE *)this + 108) & 0x7F) << 17)
       | *(_DWORD *)(v10 + 4 * v9) & 0x1FF80;
    FGetCollationName(v8, (wchar_t *)this + 60, &v64);
    TTableBaseSimple<CCollationsSTVFInfo>::SetOutput(this, 0, (unsigned int)v64, (char *)this + 120);
  }
  else
  {
    v5 = -1;
    v6 = qword_10085C9C8[5 * *((unsigned __int8 *)&qword_1008935A0[14] + *((int *)this + 29))];
    do
      v7 = *(_WORD *)(v6 + 2 * v5++ + 2) == 0;
    while ( !v7 );
    TTableBaseSimple<CCollationsSTVFInfo>::SetOutput(this, 0, (unsigned int)(2 * v5), v6);
    v8 = dword_10085C9D8[10 * *((unsigned __int8 *)&qword_1008935A0[14] + *((int *)this + 29))];
  }
  v11 = (char *)this + 376;
  v12 = (v8 >> 17) & 0x7F;
  GetWindowsCollationShortName(v8 & 0x7F, v12, (wchar_t *)this + 188, 0x3E8u);
  v13 = (_WORD *)((char *)this + 376);
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&v11[2 * v14] );
  v15 = (unsigned __int64)(2 * (int)v14) >> 1;
  for ( i = v15; i > 0; ++v13 )
  {
    --i;
    if ( *v13 == 95 )
      *v13 = 45;
  }
  v17 = v15 + 188;
  v18 = 1000 - v15;
  if ( (v8 & 0x10000) != 0 )
  {
    DefaultLocale = GetDefaultLocale();
    StringCchPrintf_lW((wchar_t *)this + v17, v18, L"%c %s", DefaultLocale, 44, L"binary sort");
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v11[2 * v20] );
LABEL_45:
    v44 = 2 * v20;
    goto LABEL_46;
  }
  v21 = (wchar_t *)((char *)this + 2 * v17);
  v22 = GetDefaultLocale();
  if ( (v8 & 0x800) != 0 )
  {
    StringCchPrintf_lW(v21, v18, L"%c %s", v22, 44, L"binary code point comparison sort");
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v11[2 * v20] );
    goto LABEL_45;
  }
  v23 = L"case-insensitive";
  if ( (v8 & 0x1000) == 0 )
    v23 = L"case-sensitive";
  StringCchPrintf_lW(v21, v18, L"%c %s", v22, 44, v23);
  v24 = -1;
  do
    ++v24;
  while ( *(_WORD *)&v11[2 * v24] );
  v25 = (unsigned __int64)(2 * (int)v24) >> 1;
  v26 = 1000 - v25;
  v27 = (wchar_t *)((char *)this + 2 * v25 + 376);
  v28 = GetDefaultLocale();
  v29 = L"accent-insensitive";
  if ( (v8 & 0x2000) == 0 )
    v29 = L"accent-sensitive";
  LODWORD(v60) = 44;
  StringCchPrintf_lW(v27, v26, L"%c %s", v28, v60, v29);
  v30 = -1;
  do
    ++v30;
  while ( *(_WORD *)&v11[2 * v30] );
  v31 = (unsigned __int64)(2 * (int)v30) >> 1;
  v32 = 1000 - v31;
  v33 = (wchar_t *)((char *)this + 2 * v31 + 376);
  v34 = GetDefaultLocale();
  v35 = L"kanatype-insensitive";
  if ( (v8 & 0x4000) == 0 )
    v35 = L"kanatype-sensitive";
  LODWORD(v61) = 44;
  StringCchPrintf_lW(v33, v32, L"%c %s", v34, v61, v35);
  v36 = -1;
  do
    ++v36;
  while ( *(_WORD *)&v11[2 * v36] );
  v37 = (unsigned __int64)(2 * (int)v36) >> 1;
  v38 = 1000 - v37;
  v39 = (wchar_t *)((char *)this + 2 * v37 + 376);
  v40 = GetDefaultLocale();
  v41 = L"width-insensitive";
  if ( (v8 & 0x8000) == 0 )
    v41 = L"width-sensitive";
  LODWORD(v62) = 44;
  StringCchPrintf_lW(v39, v38, L"%c %s", v40, v62, v41);
  v42 = -1;
  do
    ++v42;
  while ( *(_WORD *)&v11[2 * v42] );
  v43 = 2 * v42;
  v44 = v43;
  if ( (v8 & 0x100) != 0 )
  {
    v45 = (unsigned __int64)(int)v43 >> 1;
    v46 = GetDefaultLocale();
    LODWORD(v59) = 44;
    StringCchPrintf_lW((wchar_t *)this + v45 + 188, 1000 - v45, L"%c %s", v46, v59, L"supplementary characters");
    v47 = -1;
    do
      ++v47;
    while ( *(_WORD *)&v11[2 * v47] );
    v44 = 2 * v47;
  }
  if ( v12 == 3 )
  {
    v48 = L"variation selector sensitive";
    v49 = (unsigned __int64)(int)v44 >> 1;
    if ( (v8 & 0x200) != 0 )
      v48 = L"variation selector insensitive";
    v50 = GetDefaultLocale();
    LODWORD(v59) = 44;
    StringCchPrintf_lW((wchar_t *)this + v49 + 188, 1000 - v49, L"%c %s", v50, v59, v48);
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)&v11[2 * v20] );
    goto LABEL_45;
  }
LABEL_46:
  if ( (v8 & 0x80u) != 0 )
  {
    v51 = (unsigned __int64)(int)v44 >> 1;
    v52 = GetDefaultLocale();
    LODWORD(v59) = 44;
    StringCchPrintf_lW((wchar_t *)this + v51 + 188, 1000 - v51, L"%c %s", v52, v59, L"UTF8");
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)&v11[2 * v53] );
    v44 = 2 * v53;
  }
  v54 = HIBYTE(v8);
  if ( (_BYTE)v54 )
  {
    v55 = (unsigned __int64)(int)v44 >> 1;
    v56 = (unsigned __int8)byte_10085C9DC[40 * (unsigned __int8)v54];
    v57 = GetDefaultLocale();
    LODWORD(v63) = v54;
    StringCchPrintf_lW(
      (wchar_t *)this + v55 + 188,
      1000 - v55,
      L"%s%d%s%d%s",
      v57,
      L" for Unicode Data, SQL Server Sort Order ",
      v63,
      L" on Code Page ",
      *((_DWORD *)&x_uiCodePage + v56),
      L" for non-Unicode Data");
    do
      v7 = *(_WORD *)&v11[2 * v4++ + 2] == 0;
    while ( !v7 );
    v44 = 2 * v4;
  }
  TTableBaseSimple<CCollationsSTVFInfo>::SetOutput(this, 1, v44, (char *)this + 376);
  return 0;
}

```

## disassembly

```asm
0x100437b90  mov     [rsp+arg_0], rbx
0x100437b95  mov     [rsp+arg_10], rbp
0x100437b9a  mov     [rsp+arg_18], rsi
0x100437b9f  mov     byte ptr [rsp+arg_8], dl
0x100437ba3  push    rdi
0x100437ba4  push    r12
0x100437ba6  push    r13
0x100437ba8  push    r14
0x100437baa  push    r15
0x100437bac  sub     rsp, 50h
0x100437bb0  movsxd  rdx, dword ptr [rcx+68h]
0x100437bb4  mov     r12, rcx
0x100437bb7  mov     r14, 0FFFFFFFFFFFFFFFFh
0x100437bbe  cmp     edx, 63h ; 'c'
0x100437bc1  jl      short loc_100437C26
0x100437bc3  movsxd  rax, dword ptr [rcx+74h]
0x100437bc7  lea     rdi, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100437bce  movzx   eax, byte ptr [rax+rdi+493610h]
0x100437bd6  lea     rcx, [rax+rax*4]
0x100437bda  mov     rax, r14
0x100437bdd  mov     r9, ds:rva qword_10085C9C8[rdi+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100437be5  nop     word ptr [rax+rax+00000000h]
0x100437bf0  cmp     word ptr [r9+rax*2+2], 0
0x100437bf7  lea     rax, [rax+1]
0x100437bfb  jnz     short loc_100437BF0
0x100437bfd  lea     r8d, [rax+rax]
0x100437c01  xor     edx, edx
0x100437c03  mov     rcx, r12
0x100437c06  call    ?SetOutput@?$TTableBaseSimple@VCCollationsSTVFInfo@@@@IEAAXHIPEB_W@Z; TTableBaseSimple<CCollationsSTVFInfo>::SetOutput(int,uint,wchar_t const *)
0x100437c0b  movsxd  rax, dword ptr [r12+74h]
0x100437c10  movzx   eax, byte ptr [rax+rdi+493610h]
0x100437c18  lea     rcx, [rax+rax*4]
0x100437c1c  mov     r15d, ds:rva dword_10085C9D8[rdi+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100437c24  jmp     short loc_100437C92
0x100437c26  movsxd  rcx, dword ptr [rcx+70h]
0x100437c2a  lea     r8, [rsp+78h+arg_8]; int *
0x100437c32  mov     rax, [r12+60h]
0x100437c37  mov     [rsp+78h+arg_8], 100h
0x100437c42  mov     r15d, [rax+rcx*4]
0x100437c46  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100437c4d  movzx   eax, byte ptr [r12+6Ch]
0x100437c53  and     r15d, 1FF80h
0x100437c5a  and     eax, 7Fh
0x100437c5d  shl     eax, 11h
0x100437c60  or      r15d, eax
0x100437c63  movzx   eax, ds:rva byte_10086AA21[rcx+rdx*2]; CTypeInfo const CTypeInfo::tiBit ...
0x100437c6b  or      r15d, eax
0x100437c6e  lea     rdx, [r12+78h]; wchar_t *
0x100437c73  mov     ecx, r15d; unsigned int
0x100437c76  call    ?FGetCollationName@@YA_NKPEA_WPEAH@Z; FGetCollationName(ulong,wchar_t *,int *)
0x100437c7b  mov     r8d, [rsp+78h+arg_8]
0x100437c83  lea     r9, [r12+78h]
0x100437c88  xor     edx, edx
0x100437c8a  mov     rcx, r12
0x100437c8d  call    ?SetOutput@?$TTableBaseSimple@VCCollationsSTVFInfo@@@@IEAAXHIPEB_W@Z; TTableBaseSimple<CCollationsSTVFInfo>::SetOutput(int,uint,wchar_t const *)
0x100437c92  movzx   ecx, r15b
0x100437c96  lea     rbp, [r12+178h]
0x100437c9e  mov     esi, r15d
0x100437ca1  mov     r13d, 3E8h
0x100437ca7  shr     esi, 11h
0x100437caa  and     cl, 7Fh; unsigned __int8
0x100437cad  and     sil, 7Fh
0x100437cb1  mov     r9d, r13d; unsigned int
0x100437cb4  movzx   edx, sil; unsigned __int8
0x100437cb8  mov     r8, rbp; wchar_t *
0x100437cbb  call    ?GetWindowsCollationShortName@@YAJEEPEA_WK@Z; GetWindowsCollationShortName(uchar,uchar,wchar_t *,ulong)
0x100437cc0  mov     rax, rbp
0x100437cc3  mov     rcx, r14
0x100437cc6  nop     word ptr [rax+rax+00000000h]
0x100437cd0  inc     rcx
0x100437cd3  cmp     word ptr [rbp+rcx*2+0], 0
0x100437cd9  jnz     short loc_100437CD0
0x100437cdb  add     ecx, ecx
0x100437cdd  movsxd  rdx, ecx
0x100437ce0  shr     rdx, 1
0x100437ce3  mov     ecx, edx
0x100437ce5  test    edx, edx
0x100437ce7  jle     short loc_100437D04
0x100437ce9  mov     r8d, 2Dh ; '-'
0x100437cef  nop
0x100437cf0  dec     ecx
0x100437cf2  cmp     word ptr [rax], 5Fh ; '_'
0x100437cf6  jnz     short loc_100437CFC
0x100437cf8  mov     [rax], r8w
0x100437cfc  add     rax, 2
0x100437d00  test    ecx, ecx
0x100437d02  jg      short loc_100437CF0
0x100437d04  mov     rbx, r13
0x100437d07  lea     rdi, [rdx+0BCh]
0x100437d0e  sub     rbx, rdx
0x100437d11  bt      r15d, 10h
0x100437d16  jnb     short loc_100437D60
0x100437d18  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437d1e  lea     rcx, [r12+rdi*2]; wchar_t *
0x100437d22  mov     rdx, rbx; unsigned __int64
0x100437d25  mov     r9, rax; struct __crt_locale_pointers *
0x100437d28  lea     r8, aCS; "%c %s"
0x100437d2f  lea     rax, aBinarySort; "binary sort"
0x100437d36  mov     [rsp+78h+var_50], rax
0x100437d3b  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437d43  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437d48  mov     rax, r14
0x100437d4b  nop     dword ptr [rax+rax+00h]
0x100437d50  inc     rax
0x100437d53  cmp     word ptr [rbp+rax*2+0], 0
0x100437d59  jnz     short loc_100437D50
0x100437d5b  jmp     loc_100437FFB
0x100437d60  lea     rdi, [r12+rdi*2]
0x100437d64  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437d6a  bt      r15d, 0Bh
0x100437d6f  jnb     short loc_100437DB0
0x100437d71  mov     r9, rax; struct __crt_locale_pointers *
0x100437d74  lea     r8, aCS; "%c %s"
0x100437d7b  lea     rax, aBinaryCodePoin; "binary code point comparison sort"
0x100437d82  mov     rdx, rbx; unsigned __int64
0x100437d85  mov     [rsp+78h+var_50], rax
0x100437d8a  mov     rcx, rdi; wchar_t *
0x100437d8d  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437d95  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437d9a  mov     rax, r14
0x100437d9d  nop     dword ptr [rax]
0x100437da0  inc     rax
0x100437da3  cmp     word ptr [rbp+rax*2+0], 0
0x100437da9  jnz     short loc_100437DA0
0x100437dab  jmp     loc_100437FFB
0x100437db0  lea     rcx, aCaseInsensitiv_10; "case-insensitive"
0x100437db7  bt      r15d, 0Ch
0x100437dbc  jb      short loc_100437DC5
0x100437dbe  lea     rcx, aCaseSensitive; "case-sensitive"
0x100437dc5  mov     [rsp+78h+var_50], rcx
0x100437dca  lea     r8, aCS; "%c %s"
0x100437dd1  mov     rcx, rdi; wchar_t *
0x100437dd4  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437ddc  mov     r9, rax; struct __crt_locale_pointers *
0x100437ddf  mov     rdx, rbx; unsigned __int64
0x100437de2  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437de7  mov     rax, r14
0x100437dea  nop     word ptr [rax+rax+00h]
0x100437df0  inc     rax
0x100437df3  cmp     word ptr [rbp+rax*2+0], 0
0x100437df9  jnz     short loc_100437DF0
0x100437dfb  add     eax, eax
0x100437dfd  lea     rdi, [r12+178h]
0x100437e05  cdqe
0x100437e07  mov     rbx, r13
0x100437e0a  shr     rax, 1
0x100437e0d  sub     rbx, rax
0x100437e10  lea     rdi, [rdi+rax*2]
0x100437e14  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437e1a  lea     rcx, aAccentInsensit; "accent-insensitive"
0x100437e21  bt      r15d, 0Dh
0x100437e26  jb      short loc_100437E2F
0x100437e28  lea     rcx, aAccentSensitiv; "accent-sensitive"
0x100437e2f  mov     [rsp+78h+var_50], rcx
0x100437e34  lea     r8, aCS; "%c %s"
0x100437e3b  mov     rcx, rdi; wchar_t *
0x100437e3e  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437e46  mov     r9, rax; struct __crt_locale_pointers *
0x100437e49  mov     rdx, rbx; unsigned __int64
0x100437e4c  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437e51  mov     rax, r14
0x100437e54  inc     rax
0x100437e57  cmp     word ptr [rbp+rax*2+0], 0
0x100437e5d  jnz     short loc_100437E54
0x100437e5f  add     eax, eax
0x100437e61  lea     rdi, [r12+178h]
0x100437e69  cdqe
0x100437e6b  mov     rbx, r13
0x100437e6e  shr     rax, 1
0x100437e71  sub     rbx, rax
0x100437e74  lea     rdi, [rdi+rax*2]
0x100437e78  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437e7e  lea     rcx, aKanatypeInsens; "kanatype-insensitive"
0x100437e85  bt      r15d, 0Eh
0x100437e8a  jb      short loc_100437E93
0x100437e8c  lea     rcx, aKanatypeSensit; "kanatype-sensitive"
0x100437e93  mov     [rsp+78h+var_50], rcx
0x100437e98  lea     r8, aCS; "%c %s"
0x100437e9f  mov     rcx, rdi; wchar_t *
0x100437ea2  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437eaa  mov     r9, rax; struct __crt_locale_pointers *
0x100437ead  mov     rdx, rbx; unsigned __int64
0x100437eb0  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437eb5  mov     rax, r14
0x100437eb8  nop     dword ptr [rax+rax+00000000h]
0x100437ec0  inc     rax
0x100437ec3  cmp     word ptr [rbp+rax*2+0], 0
0x100437ec9  jnz     short loc_100437EC0
0x100437ecb  add     eax, eax
0x100437ecd  lea     rdi, [r12+178h]
0x100437ed5  cdqe
0x100437ed7  mov     rbx, r13
0x100437eda  shr     rax, 1
0x100437edd  sub     rbx, rax
0x100437ee0  lea     rdi, [rdi+rax*2]
0x100437ee4  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437eea  lea     rcx, aWidthInsensiti; "width-insensitive"
0x100437ef1  bt      r15d, 0Fh
0x100437ef6  jb      short loc_100437EFF
0x100437ef8  lea     rcx, aWidthSensitive; "width-sensitive"
0x100437eff  mov     [rsp+78h+var_50], rcx
0x100437f04  lea     r8, aCS; "%c %s"
0x100437f0b  mov     rcx, rdi; wchar_t *
0x100437f0e  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437f16  mov     r9, rax; struct __crt_locale_pointers *
0x100437f19  mov     rdx, rbx; unsigned __int64
0x100437f1c  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437f21  mov     rcx, r14
0x100437f24  inc     rcx
0x100437f27  cmp     word ptr [rbp+rcx*2+0], 0
0x100437f2d  jnz     short loc_100437F24
0x100437f2f  add     ecx, ecx
0x100437f31  mov     eax, ecx
0x100437f33  bt      r15d, 8
0x100437f38  jnb     short loc_100437F8D
0x100437f3a  movsxd  rbx, ecx
0x100437f3d  shr     rbx, 1
0x100437f40  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437f46  mov     rdx, r13
0x100437f49  lea     rcx, [r12+178h]
0x100437f51  mov     r9, rax; struct __crt_locale_pointers *
0x100437f54  lea     rcx, [rcx+rbx*2]; wchar_t *
0x100437f58  lea     rax, aSupplementaryC; "supplementary characters"
0x100437f5f  sub     rdx, rbx; unsigned __int64
0x100437f62  mov     [rsp+78h+var_50], rax
0x100437f67  lea     r8, aCS; "%c %s"
0x100437f6e  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437f76  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437f7b  mov     rax, r14
0x100437f7e  xchg    ax, ax
0x100437f80  inc     rax
0x100437f83  cmp     word ptr [rbp+rax*2+0], 0
0x100437f89  jnz     short loc_100437F80
0x100437f8b  add     eax, eax
0x100437f8d  cmp     sil, 3
0x100437f91  jnz     short loc_100437FFD
0x100437f93  movsxd  rdi, eax
0x100437f96  lea     rbx, aVariationSelec; "variation selector sensitive"
0x100437f9d  lea     rax, aVariationSelec_0; "variation selector insensitive"
0x100437fa4  shr     rdi, 1
0x100437fa7  bt      r15d, 9
0x100437fac  cmovb   rbx, rax
0x100437fb0  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100437fb6  mov     rdx, r13
0x100437fb9  mov     [rsp+78h+var_50], rbx
0x100437fbe  lea     rcx, [r12+178h]
0x100437fc6  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x100437fce  sub     rdx, rdi; unsigned __int64
0x100437fd1  lea     rcx, [rcx+rdi*2]; wchar_t *
0x100437fd5  mov     r9, rax; struct __crt_locale_pointers *
0x100437fd8  lea     r8, aCS; "%c %s"
0x100437fdf  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100437fe4  mov     rax, r14
0x100437fe7  nop     word ptr [rax+rax+00000000h]
0x100437ff0  inc     rax
0x100437ff3  cmp     word ptr [rbp+rax*2+0], 0
0x100437ff9  jnz     short loc_100437FF0
0x100437ffb  add     eax, eax
0x100437ffd  test    r15b, r15b
0x100438000  jns     short loc_10043805D
0x100438002  movsxd  rbx, eax
0x100438005  shr     rbx, 1
0x100438008  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10043800e  mov     rdx, r13
0x100438011  lea     rcx, [r12+178h]
0x100438019  mov     r9, rax; struct __crt_locale_pointers *
0x10043801c  lea     rcx, [rcx+rbx*2]; wchar_t *
0x100438020  lea     rax, aUtf8; "UTF8"
0x100438027  sub     rdx, rbx; unsigned __int64
0x10043802a  mov     [rsp+78h+var_50], rax
0x10043802f  lea     r8, aCS; "%c %s"
0x100438036  mov     dword ptr [rsp+78h+var_58], 2Ch ; ','
0x10043803e  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100438043  mov     rax, r14
0x100438046  nop     word ptr [rax+rax+00000000h]
0x100438050  inc     rax
0x100438053  cmp     word ptr [rbp+rax*2+0], 0
0x100438059  jnz     short loc_100438050
0x10043805b  add     eax, eax
0x10043805d  shr     r15d, 18h
0x100438061  test    r15b, r15b
0x100438064  jz      loc_100438101
0x10043806a  movsxd  rsi, eax
0x10043806d  movzx   eax, r15b
0x100438071  shr     rsi, 1
0x100438074  lea     rcx, [rax+rax*4]
0x100438078  lea     rax, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10043807f  movzx   ebx, ds:rva byte_10085C9DC[rax+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100438087  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10043808d  sub     r13, rsi
0x100438090  lea     rcx, [r12+178h]
0x100438098  mov     r9, rax; struct __crt_locale_pointers *
0x10043809b  lea     rcx, [rcx+rsi*2]; wchar_t *
0x10043809f  lea     rax, aForNonUnicodeD; " for non-Unicode Data"
0x1004380a6  mov     rdx, r13; unsigned __int64
0x1004380a9  mov     [rsp+78h+var_38], rax
0x1004380ae  lea     r8, aSDSDS; "%s%d%s%d%s"
0x1004380b5  lea     rax, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004380bc  mov     eax, ds:rva ?x_uiCodePage@@3QBIB[rax+rbx*4]; CTypeInfo const CTypeInfo::tiBit
0x1004380c3  mov     [rsp+78h+var_40], eax
  ... truncated ...
```
