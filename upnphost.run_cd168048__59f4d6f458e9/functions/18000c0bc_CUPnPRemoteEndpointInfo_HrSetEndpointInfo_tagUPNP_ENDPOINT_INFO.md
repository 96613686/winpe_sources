# CUPnPRemoteEndpointInfo::HrSetEndpointInfo(tagUPNP_ENDPOINT_INFO *)

- ea: `0x18000c0bc`
- end: `0x18000c785`
- name: `?HrSetEndpointInfo@CUPnPRemoteEndpointInfo@@QEAAJPEAUtagUPNP_ENDPOINT_INFO@@@Z`
- size: `1737`
- prototype: `__int64 __fastcall(CUPnPRemoteEndpointInfo *__hidden this, struct tagUPNP_ENDPOINT_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x18002f240`

## callees

- `0x18000aff0`
- `0x18000c0bc`
- `0x18000c78c`
- `0x18000c8e0`
- `0x18000d478`
- `0x18000f8a0`
- `0x18002a030`
- `0x18002c7d0`
- `0x18002cba0`
- `0x18003a798`
- `0x18003a9e8`
- `0x18003b1cc`
- `0x18003c048`
- `0x180045b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c18f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c211`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c266`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c2f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c35e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c40b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c49d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c52d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c53d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c54c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c721`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c75b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c18f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c211`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c266`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c2f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c35e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c3fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c40b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c49d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c52d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c53d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c54c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c5c4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c721`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c75b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c154`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c2bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c311`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c456`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c154`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c2bb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c311`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c456`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c13f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c181`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c2a6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c2e7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c13f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c181`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c2a6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c2e7`

## string_xrefs

- `0x18000c342`: `HttpUserAgent`

## pseudocode

```c
__int64 __fastcall CUPnPRemoteEndpointInfo::HrSetEndpointInfo(void **this, const CHAR **a2)
{
  _QWORD *v4; // r15
  const CHAR *v5; // rbx
  WCHAR *v6; // rsi
  int cchWideChar; // r14d
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  int v10; // eax
  void *v11; // rbx
  HRESULT v12; // r14d
  int i; // edx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  int v17; // r8d
  int v18; // r9d
  bool v19; // zf
  char *v20; // rdi
  CUString *v21; // rcx
  const CHAR *v22; // rbx
  WCHAR *v23; // rdi
  int v24; // r12d
  WCHAR *v25; // rax
  WCHAR *v26; // r14
  wchar_t *v27; // rbx
  const wchar_t *v28; // rcx
  size_t v29; // r8
  wchar_t *v30; // r12
  size_t v31; // rdx
  size_t *v32; // r8
  int v33; // edx
  __int64 v34; // rcx
  wchar_t *v35; // rax
  __int64 v36; // rcx
  int v37; // r8d
  int v38; // r9d
  bool v39; // zf
  char *v40; // r12
  CUString *v41; // rcx
  const char *v42; // rdx
  wchar_t *v43; // rbx
  const wchar_t *v44; // rcx
  wchar_t *v45; // rdi
  size_t v46; // r8
  size_t v47; // rdx
  size_t *v48; // r8
  int v49; // edx
  __int64 v50; // rcx
  wchar_t *v51; // rax
  __int64 v52; // rcx
  int v53; // r9d
  int v54; // r8d
  bool v55; // zf
  char *v56; // rdi
  CUString *v57; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-10h]
  void *Block; // [rsp+70h] [rbp+40h] BYREF
  void *v61; // [rsp+78h] [rbp+48h] BYREF
  wchar_t *v62; // [rsp+80h] [rbp+50h] BYREF

  v61 = a2;
  CUArray<CUString>::Clear(this + 8);
  operator delete(this[10]);
  v4 = this + 12;
  this[10] = 0;
  this[11] = 0;
  CTable<CUString,CUString>::Clear(this + 12);
  CTable<CUString,_GUID>::Clear(this + 16);
  v5 = *a2;
  v6 = 0;
  v62 = 0;
  if ( v5 )
  {
    cchWideChar = MultiByteToWideChar(0, 0, v5, -1, 0, 0);
    v8 = (WCHAR *)malloc(2LL * cchWideChar);
    v9 = v8;
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, 2147942414LL);
      v12 = -2147024882;
      goto LABEL_64;
    }
    MultiByteToWideChar(0, 0, v5, -1, v8, cchWideChar);
    free(0);
    v6 = v9;
    v62 = v9;
  }
  else
  {
    free(0);
  }
  Block = 0;
  v10 = CUString::HrAssign((CUString *)&Block, L"RemoteAddress");
  v11 = Block;
  v12 = v10;
  if ( v10 < 0 )
    goto LABEL_21;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 26) )
    {
      v20 = (char *)(this + 14);
      goto LABEL_18;
    }
    v14 = *(_QWORD *)(*v4 + 8LL * i);
    if ( Block )
    {
      if ( !v14 )
        continue;
      v15 = (unsigned __int16 *)Block;
      v16 = v14 - (_QWORD)Block;
      do
      {
        v17 = *(unsigned __int16 *)((char *)v15 + v16);
        v18 = *v15 - v17;
        if ( v18 )
          break;
        ++v15;
      }
      while ( v17 );
      v19 = v18 == 0;
    }
    else
    {
      v19 = v14 == 0;
    }
    if ( v19 )
      break;
  }
  v20 = (char *)(this + 14);
  v21 = (CUString *)((char *)this[14] + 8 * i);
  if ( v21 )
  {
    v12 = CUString::HrAssign(v21, (const struct CUString *)&v62);
    goto LABEL_19;
  }
LABEL_18:
  v12 = CUArray<CUString>::HrPushBack(this + 12, &Block);
  if ( v12 >= 0 )
  {
    v12 = CUArray<CUString>::HrPushBack(v20, &v62);
    if ( v12 < 0 )
      CUArray<CUString>::HrPopBack(this + 12);
  }
LABEL_19:
  if ( v12 >= 0 )
    v12 = CUPnPRemoteEndpointInfo::HrSetAddressFamily(
            (CUPnPRemoteEndpointInfo *)this,
            (struct tagUPNP_ENDPOINT_INFO *)a2);
LABEL_21:
  free(v11);
  if ( v12 < 0 )
    goto LABEL_64;
  v22 = a2[1];
  v23 = 0;
  Block = 0;
  if ( v22 )
  {
    v24 = MultiByteToWideChar(0, 0, v22, -1, 0, 0);
    v25 = (WCHAR *)malloc(2LL * v24);
    v26 = v25;
    if ( !v25 )
    {
      v12 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, 2147942414LL);
      goto LABEL_43;
    }
    MultiByteToWideChar(0, 0, v22, -1, v25, v24);
    free(0);
    v23 = v26;
    Block = v26;
  }
  else
  {
    free(0);
  }
  v27 = 0;
  v62 = 0;
  v30 = (wchar_t *)malloc(0x1Cu);
  if ( v30 )
  {
    v12 = StringValidateDestW(v28, 0xEu, v29);
    if ( v12 < 0 )
    {
      *v30 = 0;
    }
    else
    {
      v12 = StringCopyWorkerW(v30, v31, v32, L"HttpUserAgent", (size_t)lpWideCharStr);
      if ( v12 >= 0 )
      {
        free(0);
        v27 = v30;
        v62 = v30;
        if ( !v12 )
          goto LABEL_29;
        goto LABEL_73;
      }
    }
    free(v30);
  }
  else
  {
    v12 = -2147024882;
  }
LABEL_73:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
      (unsigned int)v12);
  if ( v12 < 0 )
    goto LABEL_42;
LABEL_29:
  v33 = 0;
  while ( 2 )
  {
    if ( v33 >= *((_DWORD *)this + 26) )
    {
      v40 = (char *)(this + 14);
      goto LABEL_41;
    }
    v34 = *(_QWORD *)(*v4 + 8LL * v33);
    if ( !v27 )
    {
      v39 = v34 == 0;
      goto LABEL_37;
    }
    if ( !v34 )
      goto LABEL_38;
    v35 = v27;
    v36 = v34 - (_QWORD)v27;
    do
    {
      v37 = *(wchar_t *)((char *)v35 + v36);
      v38 = *v35 - v37;
      if ( v38 )
        break;
      ++v35;
    }
    while ( v37 );
    v39 = v38 == 0;
LABEL_37:
    if ( !v39 )
    {
LABEL_38:
      ++v33;
      continue;
    }
    break;
  }
  v40 = (char *)(this + 14);
  v41 = (CUString *)((char *)this[14] + 8 * v33);
  if ( v41 )
  {
    v12 = CUString::HrAssign(v41, (const struct CUString *)&Block);
    goto LABEL_42;
  }
LABEL_41:
  v12 = CUArray<CUString>::HrPushBack(v4, &v62);
  if ( v12 >= 0 )
  {
    v12 = CUArray<CUString>::HrPushBack(v40, &Block);
    if ( v12 < 0 )
      CUArray<CUString>::HrPopBack(v4);
  }
LABEL_42:
  free(v27);
LABEL_43:
  free(v23);
  if ( v12 < 0 )
    goto LABEL_64;
  v42 = (const char *)*((_QWORD *)v61 + 2);
  if ( !v42 )
    goto LABEL_64;
  v61 = 0;
  v12 = CUString::HrAssign((CUString *)&v61, v42);
  if ( v12 < 0 )
    goto LABEL_63;
  v43 = 0;
  Block = 0;
  v45 = (wchar_t *)malloc(0x22u);
  if ( v45 )
  {
    v12 = StringValidateDestW(v44, 0x11u, v46);
    if ( v12 < 0 )
    {
      *v45 = 0;
    }
    else
    {
      v12 = StringCopyWorkerW(v45, v47, v48, L"DlnaFriendlyName", (size_t)lpWideCharStr);
      if ( v12 >= 0 )
      {
        free(0);
        v43 = v45;
        Block = v45;
        if ( !v12 )
          goto LABEL_50;
        goto LABEL_78;
      }
    }
    free(v45);
  }
  else
  {
    v12 = -2147024882;
  }
LABEL_78:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
      (unsigned int)v12);
  if ( v12 < 0 )
    goto LABEL_62;
LABEL_50:
  v49 = 0;
  while ( 2 )
  {
    if ( v49 >= *((_DWORD *)this + 26) )
    {
      v56 = (char *)(this + 14);
      goto LABEL_61;
    }
    v50 = *(_QWORD *)(*v4 + 8LL * v49);
    if ( !v43 )
    {
      v55 = v50 == 0;
      goto LABEL_58;
    }
    if ( !v50 )
      goto LABEL_59;
    v51 = v43;
    v52 = v50 - (_QWORD)v43;
    do
    {
      v53 = *(wchar_t *)((char *)v51 + v52);
      v54 = *v51 - v53;
      if ( v54 )
        break;
      ++v51;
    }
    while ( v53 );
    v55 = v54 == 0;
LABEL_58:
    if ( !v55 )
    {
LABEL_59:
      ++v49;
      continue;
    }
    break;
  }
  v56 = (char *)(this + 14);
  v57 = (CUString *)((char *)this[14] + 8 * v49);
  if ( v57 )
  {
    v12 = CUString::HrAssign(v57, (const struct CUString *)&v61);
    goto LABEL_62;
  }
LABEL_61:
  v12 = CUArray<CUString>::HrPushBack(v4, &Block);
  if ( v12 >= 0 )
  {
    v12 = CUArray<CUString>::HrPushBack(v56, &v61);
    if ( v12 < 0 )
      CUArray<CUString>::HrPopBack(v4);
  }
LABEL_62:
  free(v43);
LABEL_63:
  free(v61);
LABEL_64:
  free(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c0bc  mov     [rsp-38h+arg_18], rbx
0x18000c0c1  mov     [rsp-38h+arg_8], rdx
0x18000c0c6  push    rbp
0x18000c0c7  push    rsi
0x18000c0c8  push    rdi
0x18000c0c9  push    r12
0x18000c0cb  push    r13
0x18000c0cd  push    r14
0x18000c0cf  push    r15
0x18000c0d1  mov     rbp, rsp
0x18000c0d4  sub     rsp, 30h
0x18000c0d8  mov     r13, rcx
0x18000c0db  mov     r12, rdx
0x18000c0de  add     rcx, 40h ; '@'
0x18000c0e2  call    ?Clear@?$CUArray@VCUString@@@@QEAAXXZ; CUArray<CUString>::Clear(void)
0x18000c0e7  mov     rcx, [r13+50h]; void *
0x18000c0eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c0f0  lea     r15, [r13+60h]
0x18000c0f4  mov     qword ptr [r13+50h], 0
0x18000c0fc  mov     rcx, r15
0x18000c0ff  mov     qword ptr [r13+58h], 0
0x18000c107  call    ?Clear@?$CTable@VCUString@@V1@@@QEAAXXZ; CTable<CUString,CUString>::Clear(void)
0x18000c10c  lea     rcx, [r13+80h]
0x18000c113  call    ?Clear@?$CTable@VCUString@@U_GUID@@@@QEAAXXZ; CTable<CUString,_GUID>::Clear(void)
0x18000c118  mov     rbx, [r12]
0x18000c11c  xor     esi, esi
0x18000c11e  mov     [rbp+arg_10], rsi
0x18000c122  test    rbx, rbx
0x18000c125  jz      loc_18000C20F
0x18000c12b  mov     [rsp+30h+cchWideChar], esi; cchWideChar
0x18000c12f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000c133  mov     r8, rbx; lpMultiByteStr
0x18000c136  mov     [rsp+30h+lpWideCharStr], rsi; lpWideCharStr
0x18000c13b  xor     edx, edx; dwFlags
0x18000c13d  xor     ecx, ecx; CodePage
0x18000c13f  call    cs:__imp_MultiByteToWideChar
0x18000c146  nop     dword ptr [rax+rax+00h]
0x18000c14b  movsxd  r14, eax
0x18000c14e  mov     rcx, r14
0x18000c151  add     rcx, rcx; Size
0x18000c154  call    cs:__imp_malloc
0x18000c15b  nop     dword ptr [rax+rax+00h]
0x18000c160  mov     rdi, rax
0x18000c163  test    rax, rax
0x18000c166  jz      loc_18000C670
0x18000c16c  mov     [rsp+30h+cchWideChar], r14d; cchWideChar
0x18000c171  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000c175  mov     r8, rbx; lpMultiByteStr
0x18000c178  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x18000c17d  xor     edx, edx; dwFlags
0x18000c17f  xor     ecx, ecx; CodePage
0x18000c181  call    cs:__imp_MultiByteToWideChar
0x18000c188  nop     dword ptr [rax+rax+00h]
0x18000c18d  xor     ecx, ecx; Block
0x18000c18f  call    cs:__imp_free
0x18000c196  nop     dword ptr [rax+rax+00h]
0x18000c19b  mov     rsi, rdi
0x18000c19e  mov     [rbp+arg_10], rdi
0x18000c1a2  lea     rdx, aRemoteaddress; "RemoteAddress"
0x18000c1a9  mov     [rbp+Block], 0
0x18000c1b1  lea     rcx, [rbp+Block]; this
0x18000c1b5  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000c1ba  mov     rbx, [rbp+Block]
0x18000c1be  mov     r14d, eax
0x18000c1c1  test    eax, eax
0x18000c1c3  js      loc_18000C263
0x18000c1c9  xor     edx, edx
0x18000c1cb  cmp     edx, [r15+8]
0x18000c1cf  jge     short loc_18000C21F
0x18000c1d1  mov     rax, [r15]
0x18000c1d4  movsxd  r10, edx
0x18000c1d7  mov     rcx, [rax+r10*8]
0x18000c1db  test    rbx, rbx
0x18000c1de  jz      loc_18000C6AF
0x18000c1e4  test    rcx, rcx
0x18000c1e7  jz      short loc_18000C20B
0x18000c1e9  mov     rax, rbx
0x18000c1ec  sub     rcx, rbx
0x18000c1ef  movzx   r9d, word ptr [rax]
0x18000c1f3  movzx   r8d, word ptr [rax+rcx]
0x18000c1f8  sub     r9d, r8d
0x18000c1fb  jnz     short loc_18000C206
0x18000c1fd  add     rax, 2
0x18000c201  test    r8d, r8d
0x18000c204  jnz     short loc_18000C1EF
0x18000c206  test    r9d, r9d
0x18000c209  jz      short loc_18000C225
0x18000c20b  inc     edx
0x18000c20d  jmp     short loc_18000C1CB
0x18000c20f  xor     ecx, ecx; Block
0x18000c211  call    cs:__imp_free
0x18000c218  nop     dword ptr [rax+rax+00h]
0x18000c21d  jmp     short loc_18000C1A2
0x18000c21f  lea     rdi, [r15+10h]
0x18000c223  jmp     short loc_18000C239
0x18000c225  lea     rdi, [r15+10h]
0x18000c229  mov     rax, [rdi]
0x18000c22c  lea     rcx, [rax+r10*8]; this
0x18000c230  test    rcx, rcx
0x18000c233  jnz     loc_18000C6B7
0x18000c239  lea     rdx, [rbp+Block]
0x18000c23d  mov     rcx, r15
0x18000c240  call    ?HrPushBack@?$CUArray@VCUString@@@@QEAAJAEBVCUString@@@Z; CUArray<CUString>::HrPushBack(CUString const &)
0x18000c245  mov     r14d, eax
0x18000c248  test    eax, eax
0x18000c24a  jns     loc_18000C5D5
0x18000c250  test    r14d, r14d
0x18000c253  js      short loc_18000C263
0x18000c255  mov     rdx, r12; struct tagUPNP_ENDPOINT_INFO *
0x18000c258  mov     rcx, r13; this
0x18000c25b  call    ?HrSetAddressFamily@CUPnPRemoteEndpointInfo@@AEAAJPEAUtagUPNP_ENDPOINT_INFO@@@Z; CUPnPRemoteEndpointInfo::HrSetAddressFamily(tagUPNP_ENDPOINT_INFO *)
0x18000c260  mov     r14d, eax
0x18000c263  mov     rcx, rbx; Block
0x18000c266  call    cs:__imp_free
0x18000c26d  nop     dword ptr [rax+rax+00h]
0x18000c272  test    r14d, r14d
0x18000c275  js      loc_18000C549
0x18000c27b  mov     rbx, [r12+8]
0x18000c280  xor     edi, edi
0x18000c282  mov     [rbp+Block], rdi
0x18000c286  test    rbx, rbx
0x18000c289  jz      loc_18000C5C2
0x18000c28f  or      r13d, 0FFFFFFFFh
0x18000c293  mov     [rsp+30h+cchWideChar], edi; cchWideChar
0x18000c297  mov     r9d, r13d; cbMultiByte
0x18000c29a  mov     [rsp+30h+lpWideCharStr], rdi; lpWideCharStr
0x18000c29f  mov     r8, rbx; lpMultiByteStr
0x18000c2a2  xor     edx, edx; dwFlags
0x18000c2a4  xor     ecx, ecx; CodePage
0x18000c2a6  call    cs:__imp_MultiByteToWideChar
0x18000c2ad  nop     dword ptr [rax+rax+00h]
0x18000c2b2  movsxd  r12, eax
0x18000c2b5  mov     rcx, r12
0x18000c2b8  add     rcx, rcx; Size
0x18000c2bb  call    cs:__imp_malloc
0x18000c2c2  nop     dword ptr [rax+rax+00h]
0x18000c2c7  mov     r14, rax
0x18000c2ca  test    rax, rax
0x18000c2cd  jz      loc_18000C6C8
0x18000c2d3  mov     [rsp+30h+cchWideChar], r12d; cchWideChar
0x18000c2d8  mov     r9d, r13d; cbMultiByte
0x18000c2db  mov     r8, rbx; lpMultiByteStr
0x18000c2de  mov     [rsp+30h+lpWideCharStr], rax; cchToCopy
0x18000c2e3  xor     edx, edx; dwFlags
0x18000c2e5  xor     ecx, ecx; CodePage
0x18000c2e7  call    cs:__imp_MultiByteToWideChar
0x18000c2ee  nop     dword ptr [rax+rax+00h]
0x18000c2f3  xor     ecx, ecx; Block
0x18000c2f5  call    cs:__imp_free
0x18000c2fc  nop     dword ptr [rax+rax+00h]
0x18000c301  mov     rdi, r14
0x18000c304  mov     [rbp+Block], r14
0x18000c308  xor     ebx, ebx
0x18000c30a  mov     [rbp+arg_10], rbx
0x18000c30e  lea     ecx, [rbx+1Ch]; Size
0x18000c311  call    cs:__imp_malloc
0x18000c318  nop     dword ptr [rax+rax+00h]
0x18000c31d  mov     r12, rax
0x18000c320  mov     r13d, 8007000Eh
0x18000c326  test    rax, rax
0x18000c329  jz      loc_18000C70F
0x18000c32f  lea     edx, [rbx+0Eh]; cchDest
0x18000c332  call    StringValidateDestW
0x18000c337  mov     r14d, eax
0x18000c33a  test    eax, eax
0x18000c33c  js      loc_18000C717
0x18000c342  lea     r9, aHttpuseragent; "HttpUserAgent"
0x18000c349  mov     rcx, r12; pszDest
0x18000c34c  call    StringCopyWorkerW
0x18000c351  mov     r14d, eax
0x18000c354  test    eax, eax
0x18000c356  js      loc_18000C71E
0x18000c35c  xor     ecx, ecx; Block
0x18000c35e  call    cs:__imp_free
0x18000c365  nop     dword ptr [rax+rax+00h]
0x18000c36a  mov     rbx, r12
0x18000c36d  mov     [rbp+arg_10], rbx
0x18000c371  test    r14d, r14d
0x18000c374  jnz     loc_18000C5F9
0x18000c37a  xor     edx, edx
0x18000c37c  cmp     edx, [r15+8]
0x18000c380  jge     short loc_18000C3C0
0x18000c382  mov     rax, [r15]
0x18000c385  movsxd  r10, edx
0x18000c388  mov     rcx, [rax+r10*8]
0x18000c38c  test    rbx, rbx
0x18000c38f  jz      loc_18000C732
0x18000c395  test    rcx, rcx
0x18000c398  jz      short loc_18000C3BC
0x18000c39a  mov     rax, rbx
0x18000c39d  sub     rcx, rbx
0x18000c3a0  movzx   r9d, word ptr [rax]
0x18000c3a4  movzx   r8d, word ptr [rax+rcx]
0x18000c3a9  sub     r9d, r8d
0x18000c3ac  jnz     short loc_18000C3B7
0x18000c3ae  add     rax, 2
0x18000c3b2  test    r8d, r8d
0x18000c3b5  jnz     short loc_18000C3A0
0x18000c3b7  test    r9d, r9d
0x18000c3ba  jz      short loc_18000C3C6
0x18000c3bc  inc     edx
0x18000c3be  jmp     short loc_18000C37C
0x18000c3c0  lea     r12, [r15+10h]
0x18000c3c4  jmp     short loc_18000C3DB
0x18000c3c6  lea     r12, [r15+10h]
0x18000c3ca  mov     rax, [r12]
0x18000c3ce  lea     rcx, [rax+r10*8]; this
0x18000c3d2  test    rcx, rcx
0x18000c3d5  jnz     loc_18000C73A
0x18000c3db  lea     rdx, [rbp+arg_10]
0x18000c3df  mov     rcx, r15
0x18000c3e2  call    ?HrPushBack@?$CUArray@VCUString@@@@QEAAJAEBVCUString@@@Z; CUArray<CUString>::HrPushBack(CUString const &)
0x18000c3e7  mov     r14d, eax
0x18000c3ea  test    eax, eax
0x18000c3ec  jns     loc_18000C57A
0x18000c3f2  lea     r12, WPP_GLOBAL_Control
0x18000c3f9  mov     rcx, rbx; Block
0x18000c3fc  call    cs:__imp_free
0x18000c403  nop     dword ptr [rax+rax+00h]
0x18000c408  mov     rcx, rdi; Block
0x18000c40b  call    cs:__imp_free
0x18000c412  nop     dword ptr [rax+rax+00h]
0x18000c417  test    r14d, r14d
0x18000c41a  js      loc_18000C549
0x18000c420  mov     rdx, [rbp+arg_8]
0x18000c424  mov     rdx, [rdx+10h]; char *
0x18000c428  test    rdx, rdx
0x18000c42b  jz      loc_18000C549
0x18000c431  lea     rcx, [rbp+arg_8]; this
0x18000c435  mov     [rbp+arg_8], 0
0x18000c43d  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x18000c442  mov     r14d, eax
0x18000c445  test    eax, eax
0x18000c447  js      loc_18000C539
0x18000c44d  xor     ebx, ebx
0x18000c44f  mov     [rbp+Block], rbx
0x18000c453  lea     ecx, [rbx+22h]; Size
0x18000c456  call    cs:__imp_malloc
0x18000c45d  nop     dword ptr [rax+rax+00h]
0x18000c462  mov     rdi, rax
0x18000c465  test    rax, rax
0x18000c468  jz      loc_18000C74B
0x18000c46e  lea     edx, [rbx+11h]; cchDest
0x18000c471  call    StringValidateDestW
0x18000c476  mov     r14d, eax
0x18000c479  test    eax, eax
0x18000c47b  js      loc_18000C753
0x18000c481  lea     r9, aDlnafriendlyna; "DlnaFriendlyName"
0x18000c488  mov     rcx, rdi; pszDest
0x18000c48b  call    StringCopyWorkerW
0x18000c490  mov     r14d, eax
0x18000c493  test    eax, eax
0x18000c495  js      loc_18000C758
0x18000c49b  xor     ecx, ecx; Block
0x18000c49d  call    cs:__imp_free
0x18000c4a4  nop     dword ptr [rax+rax+00h]
0x18000c4a9  mov     rbx, rdi
0x18000c4ac  mov     [rbp+Block], rbx
0x18000c4b0  test    r14d, r14d
0x18000c4b3  jnz     loc_18000C638
0x18000c4b9  xor     edx, edx
0x18000c4bb  cmp     edx, [r15+8]
0x18000c4bf  jge     loc_18000C574
0x18000c4c5  mov     rax, [r15]
0x18000c4c8  movsxd  r10, edx
0x18000c4cb  mov     rcx, [rax+r10*8]
0x18000c4cf  test    rbx, rbx
0x18000c4d2  jz      loc_18000C76C
0x18000c4d8  test    rcx, rcx
0x18000c4db  jz      short loc_18000C4FF
0x18000c4dd  mov     rax, rbx
0x18000c4e0  sub     rcx, rbx
0x18000c4e3  movzx   r8d, word ptr [rax]
0x18000c4e7  movzx   r9d, word ptr [rax+rcx]
0x18000c4ec  sub     r8d, r9d
0x18000c4ef  jnz     short loc_18000C4FA
0x18000c4f1  add     rax, 2
0x18000c4f5  test    r9d, r9d
0x18000c4f8  jnz     short loc_18000C4E3
0x18000c4fa  test    r8d, r8d
0x18000c4fd  jz      short loc_18000C503
0x18000c4ff  inc     edx
0x18000c501  jmp     short loc_18000C4BB
0x18000c503  lea     rdi, [r15+10h]
0x18000c507  mov     rax, [rdi]
0x18000c50a  lea     rcx, [rax+r10*8]; this
0x18000c50e  test    rcx, rcx
0x18000c511  jnz     loc_18000C774
0x18000c517  lea     rdx, [rbp+Block]
0x18000c51b  mov     rcx, r15
0x18000c51e  call    ?HrPushBack@?$CUArray@VCUString@@@@QEAAJAEBVCUString@@@Z; CUArray<CUString>::HrPushBack(CUString const &)
0x18000c523  mov     r14d, eax
0x18000c526  test    eax, eax
0x18000c528  jns     short loc_18000C59E
0x18000c52a  mov     rcx, rbx; Block
0x18000c52d  call    cs:__imp_free
0x18000c534  nop     dword ptr [rax+rax+00h]
0x18000c539  mov     rcx, [rbp+arg_8]; Block
0x18000c53d  call    cs:__imp_free
0x18000c544  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
