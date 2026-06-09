# CatalogFillCTL(CRYPTCATSTORE_ *,_CTL_INFO *)

- ea: `0x18003c2c4`
- end: `0x18003c72b`
- name: `?CatalogFillCTL@@YAHPEAUCRYPTCATSTORE_@@PEAU_CTL_INFO@@@Z`
- size: `1127`
- prototype: `__int64 __fastcall(struct CRYPTCATSTORE_ *, struct _CTL_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18003c864`

## callees

- `0x1800077b0`
- `0x1800097b0`
- `0x180014df0`
- `0x18003c2c4`
- `0x18003cd08`
- `0x18003cf80`
- `0x18004de6a`
- `0x18004de76`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c37d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c37d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c3ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c3ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c302`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c302`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003c361`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003c361`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c3b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c3b8`

## string_xrefs

- `0x18003c352`: `OLE32.DLL`
- `0x18003c373`: `CoCreateGuid`

## pseudocode

```c
__int64 __fastcall CatalogFillCTL(struct CRYPTCATSTORE_ *a1, struct _CTL_INFO *a2)
{
  DWORD dwPublicVersion; // ecx
  struct _CTL_INFO *v4; // rsi
  DWORD v5; // ecx
  DWORD v6; // ecx
  void **v7; // rcx
  __int64 v8; // r12
  HMODULE LibraryA; // rax
  HMODULE v10; // rbx
  FARPROC ProcAddress; // rbp
  __int64 v12; // rax
  unsigned int *v13; // r8
  Stack_ *v14; // r14
  DWORD v15; // eax
  struct _CTL_ENTRY *v16; // rax
  unsigned int i; // r15d
  _QWORD *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r13
  bool v21; // bp
  int v22; // ecx
  unsigned int *v23; // r12
  void *v24; // rax
  unsigned int v25; // ebx
  _OWORD *v26; // rcx
  Stack_ *hAttrs; // r14
  DWORD v28; // ecx
  struct _CERT_EXTENSION *v29; // rax
  unsigned int *v31; // r8
  unsigned int j; // ebp
  PCERT_EXTENSION rgExtension; // rbx
  __int64 v34; // rcx
  __int128 v35; // [rsp+30h] [rbp-78h] BYREF
  CHAR *v36; // [rsp+40h] [rbp-68h]
  __int64 v37; // [rsp+48h] [rbp-60h]
  CRYPT_OBJID_BLOB *v38; // [rsp+50h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp+8h]
  __int64 v41; // [rsp+C0h] [rbp+18h]
  Stack_ *v42; // [rsp+C8h] [rbp+20h]

  dwPublicVersion = a1->dwPublicVersion;
  v4 = a2;
  if ( dwPublicVersion && (v5 = dwPublicVersion - 1) != 0 && (v6 = v5 - 255) != 0 )
  {
    if ( v6 != 256 )
    {
      SetLastError(0x32u);
      return 0;
    }
    v7 = g_CatalogParserV2;
  }
  else
  {
    v7 = &g_CatalogParserV1;
  }
  *((_QWORD *)a1->hReserved + 1) = v7;
  v8 = *((_QWORD *)a1->hReserved + 1);
  v41 = v8;
  memset_0(a2, 0, sizeof(struct _CTL_INFO));
  v4->SubjectUsage.rgpszUsageIdentifier = &off_180052F00;
  v4->SubjectUsage.cUsageIdentifier = 1;
  LibraryA = LoadLibraryA("OLE32.DLL");
  v10 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "CoCreateGuid");
    if ( ProcAddress )
    {
      v12 = CatalogNew(0x10u);
      v4->ListIdentifier.pbData = (BYTE *)v12;
      if ( v12 )
      {
        v4->ListIdentifier.cbData = 16;
        ((void (__fastcall *)(__int64))ProcAddress)(v12);
      }
    }
    FreeLibrary(v10);
  }
  GetSystemTimeAsFileTime(&v4->ThisUpdate);
  v4->SubjectAlgorithm.pszObjId = (LPSTR)(**(__int64 (__fastcall ***)(__int64))v8)(v8);
  v14 = *(Stack_ **)a1->hReserved;
  if ( v14 )
  {
    v15 = *((_DWORD *)v14 + 8);
    v4->cCTLEntry = v15;
    if ( v15 )
    {
      v16 = (struct _CTL_ENTRY *)CatalogNew((unsigned int)(32 * *((_DWORD *)v14 + 8)));
      v4->rgCTLEntry = v16;
      if ( !v16 )
        return 0;
      memset_0(v16, 0, 32LL * *((unsigned int *)v14 + 8));
    }
    for ( i = 0; i < *((_DWORD *)v14 + 8); ++i )
    {
      v18 = Stack_::Get(v14, i, v13);
      v19 = (__int64)v18;
      if ( !v18 )
        return 0;
      v20 = (__int64)&v4->rgCTLEntry[i];
      v21 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v8 + 8LL))(
              v8,
              v18[1],
              v20 + 8,
              v20)
        || !*(_DWORD *)(v19 + 24)
        && !*(_WORD *)(v19 + 28)
        && !*(_WORD *)(v19 + 30)
        && !(*(unsigned int (__fastcall **)(__int64, struct CRYPTCATSTORE_ *, __int64, __int64))(*(_QWORD *)v8 + 40LL))(
              v8,
              a1,
              v19,
              v19 + 88) )
      {
        return 0;
      }
      if ( !*(_QWORD *)(v19 + 48) && !(unsigned int)CatalogReallyDecodeIndirectData((__int64)a1, v19, v19 + 72) )
        return 0;
      if ( a1->dwPublicVersion >= 0x200 )
        v21 = strcmp_0(*(const char **)(*(_QWORD *)(v19 + 48) + 24LL), "1.3.14.3.2.26") == 0;
      v22 = !v21 + 1;
      *(_DWORD *)(v20 + 16) = v22;
      v42 = *(Stack_ **)(v19 + 64);
      v23 = (unsigned int *)((char *)v42 + 32);
      if ( v42 )
      {
        v22 += *v23;
        *(_DWORD *)(v20 + 16) = v22;
      }
      v24 = (void *)CatalogNew((unsigned int)(24 * v22));
      *(_QWORD *)(v20 + 24) = v24;
      if ( !v24 )
        return 0;
      memset_0(v24, 0, 24LL * *(unsigned int *)(v20 + 16));
      if ( !(*(unsigned int (__fastcall **)(__int64, struct CRYPTCATSTORE_ *, __int64, _QWORD))(*(_QWORD *)v41 + 24LL))(
              v41,
              a1,
              v19,
              *(_QWORD *)(v20 + 24))
        || !v21 && !(unsigned int)CatalogEncodeIndirectData(a1, v19, *(_QWORD *)(v20 + 24) + 24LL) )
      {
        return 0;
      }
      if ( v42 )
      {
        v25 = 0;
        if ( *v23 )
        {
          do
          {
            Stack_::Get(v42, v25, v13);
            v39 = *(_QWORD *)(v20 + 24) + 24LL * (!v21 + 1 + v25);
            v26 = (_OWORD *)CatalogNew(0x10u);
            *(_QWORD *)(v39 + 16) = v26;
            if ( v26 )
            {
              *(_DWORD *)(v39 + 8) = 1;
              *v26 = 0;
              CatalogEncodeNameValue(a1);
            }
            ++v25;
          }
          while ( v25 < *v23 );
          v4 = a2;
        }
      }
      v8 = v41;
    }
  }
  hAttrs = (Stack_ *)a1->hAttrs;
  if ( hAttrs )
  {
    v28 = *((_DWORD *)hAttrs + 8);
    v4->cExtension = v28;
    v29 = (struct _CERT_EXTENSION *)CatalogNew(32 * v28);
    v4->rgExtension = v29;
    if ( !v29 )
      return 0;
    memset_0(v29, 0, 32LL * v4->cExtension);
    for ( j = 0; j < *((_DWORD *)hAttrs + 8); ++j )
    {
      if ( Stack_::Get(hAttrs, j, v31) )
      {
        rgExtension = v4->rgExtension;
        v38 = (CRYPT_OBJID_BLOB *)&v35;
        v36 = 0;
        v37 = 1;
        v35 = 0;
        if ( (unsigned int)CatalogEncodeNameValue(a1) )
        {
          v34 = j;
          *(_QWORD *)(&rgExtension[v34].fCritical + 1) = 0;
          *(_QWORD *)(&rgExtension[v34].Value.cbData + 1) = 0;
          HIDWORD(rgExtension[v34].Value.pbData) = 0;
          rgExtension[v34].pszObjId = v36;
          rgExtension[v34].fCritical = 0;
          if ( (_DWORD)v37 )
          {
            if ( v38 )
              rgExtension[v34].Value = *v38;
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18003c2c4  mov     [rsp+arg_8], rdx
0x18003c2c9  push    rbx
0x18003c2ca  push    rbp
0x18003c2cb  push    rsi
0x18003c2cc  push    rdi
0x18003c2cd  push    r12
0x18003c2cf  push    r13
0x18003c2d1  push    r14
0x18003c2d3  push    r15
0x18003c2d5  sub     rsp, 68h
0x18003c2d9  mov     rdi, rcx
0x18003c2dc  xor     r13d, r13d
0x18003c2df  mov     ecx, [rcx+4]
0x18003c2e2  mov     rsi, rdx
0x18003c2e5  test    ecx, ecx
0x18003c2e7  jz      short loc_18003C316
0x18003c2e9  sub     ecx, 1
0x18003c2ec  jz      short loc_18003C316
0x18003c2ee  sub     ecx, 0FFh
0x18003c2f4  jz      short loc_18003C316
0x18003c2f6  cmp     ecx, 100h
0x18003c2fc  jz      short loc_18003C30D
0x18003c2fe  lea     ecx, [r13+32h]; dwErrCode
0x18003c302  call    cs:__imp_SetLastError
0x18003c308  jmp     loc_18003C660
0x18003c30d  lea     rcx, g_CatalogParserV2
0x18003c314  jmp     short loc_18003C31D
0x18003c316  lea     rcx, g_CatalogParserV1
0x18003c31d  mov     rax, [rdi+20h]
0x18003c321  xor     edx, edx; Val
0x18003c323  mov     r8d, 80h; Size
0x18003c329  mov     [rax+8], rcx
0x18003c32d  mov     rcx, rsi; void *
0x18003c330  mov     rax, [rdi+20h]
0x18003c334  mov     r12, [rax+8]
0x18003c338  mov     [rsp+0A8h+arg_10], r12
0x18003c340  call    memset_0
0x18003c345  lea     rax, off_180052F00; "1.3.6.1.4.1.311.12.1.1"
0x18003c34c  mov     r15d, 1
0x18003c352  lea     rcx, aOle32Dll; "OLE32.DLL"
0x18003c359  mov     [rsi+10h], rax
0x18003c35d  mov     [rsi+8], r15d
0x18003c361  call    cs:__imp_LoadLibraryA
0x18003c367  lea     r14d, [r15+0Fh]
0x18003c36b  mov     rbx, rax
0x18003c36e  test    rax, rax
0x18003c371  jz      short loc_18003C3B4
0x18003c373  lea     rdx, aCocreateguid; "CoCreateGuid"
0x18003c37a  mov     rcx, rax; hModule
0x18003c37d  call    cs:__imp_GetProcAddress
0x18003c383  mov     rbp, rax
0x18003c386  test    rax, rax
0x18003c389  jz      short loc_18003C3AB
0x18003c38b  mov     ecx, r14d; uBytes
0x18003c38e  call    CatalogNew
0x18003c393  mov     [rsi+20h], rax
0x18003c397  test    rax, rax
0x18003c39a  jz      short loc_18003C3AB
0x18003c39c  mov     rcx, rax
0x18003c39f  mov     [rsi+18h], r14d
0x18003c3a3  mov     rax, rbp
0x18003c3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3ab  mov     rcx, rbx; hLibModule
0x18003c3ae  call    cs:__imp_FreeLibrary
0x18003c3b4  lea     rcx, [rsi+38h]; lpSystemTimeAsFileTime
0x18003c3b8  call    cs:__imp_GetSystemTimeAsFileTime
0x18003c3be  mov     rax, [r12]
0x18003c3c2  mov     rcx, r12
0x18003c3c5  mov     rax, [rax]
0x18003c3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3cd  mov     [rsi+48h], rax
0x18003c3d1  mov     rax, [rdi+20h]
0x18003c3d5  mov     r14, [rax]
0x18003c3d8  test    r14, r14
0x18003c3db  jz      loc_18003C63B
0x18003c3e1  mov     eax, [r14+20h]
0x18003c3e5  mov     [rsi+60h], eax
0x18003c3e8  test    eax, eax
0x18003c3ea  jz      short loc_18003C417
0x18003c3ec  mov     ecx, [r14+20h]
0x18003c3f0  shl     ecx, 5; uBytes
0x18003c3f3  call    CatalogNew
0x18003c3f8  mov     [rsi+68h], rax
0x18003c3fc  test    rax, rax
0x18003c3ff  jz      loc_18003C660
0x18003c405  mov     r8d, [r14+20h]
0x18003c409  xor     edx, edx; Val
0x18003c40b  shl     r8, 5; Size
0x18003c40f  mov     rcx, rax; void *
0x18003c412  call    memset_0
0x18003c417  mov     r15d, r13d
0x18003c41a  cmp     r15d, [r14+20h]
0x18003c41e  jnb     loc_18003C635
0x18003c424  mov     edx, r15d; unsigned int
0x18003c427  mov     rcx, r14; this
0x18003c42a  call    ?Get@Stack_@@QEAAPEAXKPEAK@Z; Stack_::Get(ulong,ulong *)
0x18003c42f  mov     rbx, rax
0x18003c432  test    rax, rax
0x18003c435  jz      loc_18003C660
0x18003c43b  mov     rcx, [r12]
0x18003c43f  mov     rdx, [rbx+8]
0x18003c443  mov     r13d, r15d
0x18003c446  shl     r13, 5
0x18003c44a  add     r13, [rsi+68h]
0x18003c44e  mov     rax, [rcx+8]
0x18003c452  mov     r9, r13
0x18003c455  mov     rcx, r12
0x18003c458  lea     r8, [r13+8]
0x18003c45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c461  xor     ebp, ebp
0x18003c463  test    eax, eax
0x18003c465  jz      loc_18003C660
0x18003c46b  cmp     [rbx+18h], ebp
0x18003c46e  jnz     short loc_18003C49E
0x18003c470  cmp     [rbx+1Ch], bp
0x18003c474  jnz     short loc_18003C49E
0x18003c476  cmp     [rbx+1Eh], bp
0x18003c47a  jnz     short loc_18003C49E
0x18003c47c  mov     rax, [r12]
0x18003c480  lea     r9, [rbx+58h]
0x18003c484  mov     r8, rbx
0x18003c487  mov     rdx, rdi
0x18003c48a  mov     rcx, r12
0x18003c48d  mov     rax, [rax+28h]
0x18003c491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c496  test    eax, eax
0x18003c498  jz      loc_18003C660
0x18003c49e  cmp     [rbx+30h], rbp
0x18003c4a2  jnz     short loc_18003C4BB
0x18003c4a4  lea     r8, [rbx+48h]
0x18003c4a8  mov     rdx, rbx
0x18003c4ab  mov     rcx, rdi
0x18003c4ae  call    CatalogReallyDecodeIndirectData
0x18003c4b3  test    eax, eax
0x18003c4b5  jz      loc_18003C660
0x18003c4bb  cmp     dword ptr [rdi+4], 200h
0x18003c4c2  jb      short loc_18003C4E6
0x18003c4c4  mov     rcx, [rbx+30h]
0x18003c4c8  lea     rdx, a13143226; "1.3.14.3.2.26"
0x18003c4cf  mov     rcx, [rcx+18h]; Str1
0x18003c4d3  call    strcmp_0
0x18003c4d8  test    eax, eax
0x18003c4da  movzx   ebp, bpl
0x18003c4de  mov     eax, 1
0x18003c4e3  cmovz   ebp, eax
0x18003c4e6  movzx   ecx, bpl
0x18003c4ea  xor     ecx, 1
0x18003c4ed  inc     ecx
0x18003c4ef  mov     [r13+10h], ecx
0x18003c4f3  mov     rax, [rbx+40h]
0x18003c4f7  mov     dword ptr [rsp+0A8h+arg_0], ecx
0x18003c4fe  mov     [rsp+0A8h+arg_18], rax
0x18003c506  lea     r12, [rax+20h]
0x18003c50a  test    rax, rax
0x18003c50d  jz      short loc_18003C517
0x18003c50f  add     ecx, [r12]
0x18003c513  mov     [r13+10h], ecx
0x18003c517  lea     ecx, [rcx+rcx*2]
0x18003c51a  shl     ecx, 3; uBytes
0x18003c51d  call    CatalogNew
0x18003c522  mov     [r13+18h], rax
0x18003c526  test    rax, rax
0x18003c529  jz      loc_18003C660
0x18003c52f  mov     ecx, [r13+10h]
0x18003c533  xor     edx, edx; Val
0x18003c535  lea     r8, [rcx+rcx*2]
0x18003c539  mov     rcx, rax; void *
0x18003c53c  shl     r8, 3; Size
0x18003c540  call    memset_0
0x18003c545  mov     rcx, [rsp+0A8h+arg_10]
0x18003c54d  mov     r8, rbx
0x18003c550  mov     r9, [r13+18h]
0x18003c554  mov     rdx, rdi
0x18003c557  mov     rax, [rcx]
0x18003c55a  mov     rax, [rax+18h]
0x18003c55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c563  test    eax, eax
0x18003c565  jz      loc_18003C660
0x18003c56b  test    bpl, bpl
0x18003c56e  jnz     short loc_18003C58B
0x18003c570  mov     r8, [r13+18h]
0x18003c574  mov     rdx, rbx
0x18003c577  add     r8, 18h
0x18003c57b  mov     rcx, rdi
0x18003c57e  call    CatalogEncodeIndirectData
0x18003c583  test    eax, eax
0x18003c585  jz      loc_18003C660
0x18003c58b  mov     rbp, [rsp+0A8h+arg_18]
0x18003c593  test    rbp, rbp
0x18003c596  jz      loc_18003C622
0x18003c59c  xor     ebx, ebx
0x18003c59e  cmp     [r12], ebx
0x18003c5a2  jbe     short loc_18003C622
0x18003c5a4  mov     esi, dword ptr [rsp+0A8h+arg_0]
0x18003c5ab  mov     edx, ebx; unsigned int
0x18003c5ad  mov     rcx, rbp; this
0x18003c5b0  call    ?Get@Stack_@@QEAAPEAXKPEAK@Z; Stack_::Get(ulong,ulong *)
0x18003c5b5  lea     ecx, [rsi+rbx]
0x18003c5b8  mov     [rsp+0A8h+arg_18], rax
0x18003c5c0  lea     r8, [rcx+rcx*2]
0x18003c5c4  mov     rcx, [r13+18h]
0x18003c5c8  lea     rdx, [rcx+r8*8]
0x18003c5cc  mov     ecx, 10h; uBytes
0x18003c5d1  mov     [rsp+0A8h+arg_0], rdx
0x18003c5d9  call    CatalogNew
0x18003c5de  mov     rcx, rax
0x18003c5e1  mov     rax, [rsp+0A8h+arg_0]
0x18003c5e9  mov     [rax+10h], rcx
0x18003c5ed  test    rcx, rcx
0x18003c5f0  jz      short loc_18003C612
0x18003c5f2  mov     rdx, [rsp+0A8h+arg_18]
0x18003c5fa  xorps   xmm0, xmm0
0x18003c5fd  mov     dword ptr [rax+8], 1
0x18003c604  mov     r8, rax
0x18003c607  movups  xmmword ptr [rcx], xmm0
0x18003c60a  mov     rcx, rdi; struct CRYPTCATSTORE_ *
0x18003c60d  call    CatalogEncodeNameValue
0x18003c612  inc     ebx
0x18003c614  cmp     ebx, [r12]
0x18003c618  jb      short loc_18003C5AB
0x18003c61a  mov     rsi, [rsp+0A8h+arg_8]
0x18003c622  mov     r12, [rsp+0A8h+arg_10]
0x18003c62a  inc     r15d
0x18003c62d  xor     r13d, r13d
0x18003c630  jmp     loc_18003C41A
0x18003c635  mov     r15d, 1
0x18003c63b  mov     r14, [rdi+28h]
0x18003c63f  test    r14, r14
0x18003c642  jz      loc_18003C717
0x18003c648  mov     ecx, [r14+20h]
0x18003c64c  mov     [rsi+70h], ecx
0x18003c64f  shl     ecx, 5; uBytes
0x18003c652  call    CatalogNew
0x18003c657  mov     [rsi+78h], rax
0x18003c65b  test    rax, rax
0x18003c65e  jnz     short loc_18003C667
0x18003c660  xor     eax, eax
0x18003c662  jmp     loc_18003C71A
0x18003c667  mov     r8d, [rsi+70h]
0x18003c66b  xor     edx, edx; Val
0x18003c66d  shl     r8, 5; Size
0x18003c671  mov     rcx, rax; void *
0x18003c674  call    memset_0
0x18003c679  mov     ebp, r13d
0x18003c67c  cmp     [r14+20h], r13d
0x18003c680  jbe     loc_18003C717
0x18003c686  mov     edx, ebp; unsigned int
0x18003c688  mov     rcx, r14; this
0x18003c68b  call    ?Get@Stack_@@QEAAPEAXKPEAK@Z; Stack_::Get(ulong,ulong *)
0x18003c690  test    rax, rax
0x18003c693  jz      short loc_18003C70A
0x18003c695  mov     rbx, [rsi+78h]
0x18003c699  lea     rcx, [rsp+0A8h+var_78]
0x18003c69e  mov     [rsp+0A8h+var_58], rcx
0x18003c6a3  lea     r8, [rsp+0A8h+var_68]
0x18003c6a8  xorps   xmm0, xmm0
0x18003c6ab  mov     [rsp+0A8h+var_68], r13
0x18003c6b0  mov     rcx, rdi; struct CRYPTCATSTORE_ *
0x18003c6b3  mov     [rsp+0A8h+var_60], 1
0x18003c6bc  mov     rdx, rax
0x18003c6bf  movups  [rsp+0A8h+var_78], xmm0
0x18003c6c4  call    CatalogEncodeNameValue
0x18003c6c9  test    eax, eax
0x18003c6cb  jz      short loc_18003C70A
0x18003c6cd  mov     ecx, ebp
0x18003c6cf  shl     rcx, 5
0x18003c6d3  mov     [rcx+rbx+0Ch], r13
0x18003c6d8  mov     [rcx+rbx+14h], r13
0x18003c6dd  mov     [rcx+rbx+1Ch], r13d
0x18003c6e2  mov     rax, [rsp+0A8h+var_68]
0x18003c6e7  mov     [rcx+rbx], rax
0x18003c6eb  mov     [rcx+rbx+8], r13d
0x18003c6f0  cmp     dword ptr [rsp+0A8h+var_60], r13d
0x18003c6f5  jz      short loc_18003C70A
0x18003c6f7  mov     rdx, [rsp+0A8h+var_58]
0x18003c6fc  test    rdx, rdx
0x18003c6ff  jz      short loc_18003C70A
0x18003c701  movups  xmm0, xmmword ptr [rdx]
0x18003c704  movdqu  xmmword ptr [rcx+rbx+10h], xmm0
0x18003c70a  add     ebp, r15d
0x18003c70d  cmp     ebp, [r14+20h]
0x18003c711  jb      loc_18003C686
0x18003c717  mov     eax, r15d
0x18003c71a  add     rsp, 68h
0x18003c71e  pop     r15
0x18003c720  pop     r14
0x18003c722  pop     r13
0x18003c724  pop     r12
0x18003c726  pop     rdi
0x18003c727  pop     rsi
0x18003c728  pop     rbp
0x18003c729  pop     rbx
0x18003c72a  retn
```
