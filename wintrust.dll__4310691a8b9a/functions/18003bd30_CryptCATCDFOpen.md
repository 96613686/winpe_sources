# CryptCATCDFOpen

- ea: `0x18003bd30`
- end: `0x18003c2bd`
- name: `CryptCATCDFOpen`
- size: `1421`
- prototype: `CRYPTCATCDF *__stdcall(LPWSTR pwszFilePath, PFN_CDF_PARSE_ERROR_CALLBACK pfnParseError)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1800077b0`
- `0x1800079c0`
- `0x18000bdb0`
- `0x18000d1c0`
- `0x18001dcc0`
- `0x18003a838`
- `0x18003b10c`
- `0x18003b3d0`
- `0x18003ba40`
- `0x18003bd30`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003c0b6`
- `msvcrt!_wcsicmp` at `0x18003c1e9`
- `msvcrt!_wcsicmp` at `0x18003c0b6`
- `msvcrt!_wcsicmp` at `0x18003c1e9`
- `msvcrt!wcsrchr` at `0x18003bdfc`
- `msvcrt!wcsrchr` at `0x18003bf7d`
- `msvcrt!wcsrchr` at `0x18003bdfc`
- `msvcrt!wcsrchr` at `0x18003bf7d`
- `msvcrt!wcstol` at `0x18003bff9`
- `msvcrt!wcstol` at `0x18003c056`
- `msvcrt!wcstol` at `0x18003bff9`
- `msvcrt!wcstol` at `0x18003c056`
- `msvcrt!_stricmp` at `0x18003c163`
- `msvcrt!_stricmp` at `0x18003c163`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bdab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bdab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c18e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c22e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c18e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c0cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c179`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c25a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c0cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c179`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c25a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c248`

## pseudocode

```c
CRYPTCATCDF *__stdcall CryptCATCDFOpen(LPWSTR pwszFilePath, PFN_CDF_PARSE_ERROR_CALLBACK pfnParseError)
{
  DWORD v2; // r13d
  struct CRYPTCATCDF_ *v5; // rbx
  unsigned __int16 *v6; // r12
  unsigned __int16 *v7; // r14
  __int64 FileW; // r15
  __int64 v9; // rax
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 **p_pwszResultDir; // rsi
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // r10
  __int64 v20; // rax
  unsigned int v21; // esi
  const unsigned __int16 *v22; // rdx
  wchar_t *v23; // rdi
  const unsigned __int16 *v24; // rdx
  wchar_t *v25; // rdi
  const unsigned __int16 *v26; // rdx
  wchar_t *v27; // rdi
  const unsigned __int16 *v28; // rdx
  DWORD v29; // ecx
  __int64 v30; // r15
  DWORD v31; // edi
  __int64 HashAlgorithm; // rax
  const unsigned __int16 *v33; // rdx
  wchar_t *v34; // rdi
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwEncodingType[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v39[1032]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  *(_QWORD *)dwEncodingType = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( !pwszFilePath )
  {
    SetLastError(0x57u);
    goto LABEL_54;
  }
  FileW = (__int64)CreateFileW(pwszFilePath, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  if ( FileW != -1 )
  {
    v9 = CatalogNew(0x30u);
    v5 = (struct CRYPTCATCDF_ *)v9;
    if ( !v9 )
    {
LABEL_53:
      CloseHandle((HANDLE)FileW);
      goto LABEL_54;
    }
    *(_OWORD *)v9 = 0;
    *(_OWORD *)(v9 + 16) = 0;
    *(_OWORD *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 8) = FileW;
    FileW = -1;
    *(_DWORD *)v9 = 48;
    v38 = -1;
    String = wcsrchr(pwszFilePath, 0x5Cu);
    v10 = String + 1;
    if ( !String )
      v10 = pwszFilePath;
    if ( (int)StringCchCopyW(v39, 0x404u, v10) < 0 )
    {
LABEL_52:
      CryptCATCDFClose(v5);
      v5 = 0;
      if ( FileW == -1 )
        goto LABEL_54;
      goto LABEL_53;
    }
    if ( !(unsigned int)CDFPositionAtGroupTag(v5, L"[CatalogHeader]") )
    {
      if ( pfnParseError )
        ((void (__fastcall *)(_QWORD, __int64, const unsigned __int16 *))pfnParseError)(0, 4, L"[CatalogHeader]");
      goto LABEL_52;
    }
    if ( !CDFGetParam(v5, v11, L"Name", v39, (unsigned __int16 **)dwEncodingType, 0) )
    {
      if ( pfnParseError )
        ((void (__fastcall *)(_QWORD, __int64, const unsigned __int16 *))pfnParseError)(0, 4, L"[CatalogHeader]");
      v6 = *(unsigned __int16 **)dwEncodingType;
      goto LABEL_52;
    }
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    p_pwszResultDir = (const unsigned __int16 **)&v5->pwszResultDir;
    CDFGetParam(v5, v13, L"ResultDir", 0, &v5->pwszResultDir, 0);
    v6 = *(unsigned __int16 **)dwEncodingType;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(*(_QWORD *)dwEncodingType + 2 * v15) );
    if ( *p_pwszResultDir )
    {
      do
        ++v14;
      while ( (*p_pwszResultDir)[v14] );
      LODWORD(v15) = v14 + v15;
    }
    v16 = (unsigned int)(v15 + 6);
    v17 = (unsigned int)v16;
    if ( (unsigned __int64)(2 * v16) > 0xFFFFFFFF )
    {
      v29 = 111;
      goto LABEL_51;
    }
    v18 = (unsigned __int16 *)CatalogNew(2 * v16);
    v7 = v18;
    if ( !v18 )
      goto LABEL_52;
    *v18 = 0;
    if ( *p_pwszResultDir )
    {
      StringCchCopyW(v18, (unsigned int)v17, *p_pwszResultDir);
      v19 = *p_pwszResultDir;
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( v19[v20 - 1] != 92 )
        StringCchCatW(v7, v17, L"\\");
    }
    StringCchCatW(v7, v17, v6);
    if ( !wcsrchr(v7, 0x2Eu) )
    {
      StringCchCatW(v7, v17, L".");
      StringCchCatW(v7, v17, L"CAT");
    }
    dwEncodingType[0] = 0;
    v21 = 1;
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    CDFGetParam(v5, v22, L"CatalogVersion", 0, &String, 0);
    v23 = String;
    if ( String )
    {
      v21 = wcstol(String, 0, 10);
      LocalFree(v23);
      String = 0;
    }
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    CDFGetParam(v5, v24, L"EncodingType", L"0x00010001", &String, 0);
    v25 = String;
    if ( String )
    {
      dwEncodingType[0] = wcstol(String, 0, 16);
      LocalFree(v25);
      String = 0;
    }
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    CDFGetParam(v5, v26, L"PageHashes", L"false", &String, 0);
    v27 = String;
    if ( String )
    {
      g_PageHashes = _wcsicmp(String, L"false") != 0;
      LocalFree(v27);
      String = 0;
    }
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    if ( !CDFGetParam(v5, v28, L"HashAlgorithms", L"SHA1", &String, 0) )
    {
      v29 = 8;
LABEL_51:
      SetLastError(v29);
      goto LABEL_52;
    }
    v30 = v21 - 1;
    v31 = 87;
    if ( (unsigned int)v30 <= 1 )
    {
      HashAlgorithm = CatalogFindHashAlgorithm(String);
      if ( HashAlgorithm )
      {
        if ( v21 >= *(_DWORD *)(HashAlgorithm + 24) && v21 <= *(_DWORD *)(HashAlgorithm + 28) )
        {
          off_180069238[0] = *(char **)(HashAlgorithm + 8);
          v2 = *((_DWORD *)&qword_180058358 + v30);
          v31 = 0;
          if ( !_stricmp(off_180069238[0], "1.3.14.3.2.26") )
            off_180069238[0] = "1.3.14.3.2.26";
        }
      }
    }
    LocalFree(String);
    String = 0;
    if ( v31 )
    {
      SetLastError(v31);
      FileW = v38;
      goto LABEL_52;
    }
    CDFPositionAtGroupTag(v5, L"[CatalogHeader]");
    CDFGetParam(v5, v33, L"NonConformantFilesFallbackFlat", 0, &String, 0);
    v34 = String;
    if ( String )
    {
      if ( !_wcsicmp(String, L"true") )
        g_FallbackFlat = 1;
      LocalFree(v34);
    }
    v5->hCATStore = CryptCATOpen(v7, 1u, 0, v2, dwEncodingType[0]);
  }
LABEL_54:
  LocalFree(v6);
  LocalFree(v7);
  if ( v5 )
  {
    if ( (((unsigned __int64)v5->hCATStore + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      CryptCATSetCreatePageHashesFlag(v5->hCATStore, g_PageHashes);
    }
    else
    {
      CryptCATCDFClose(v5);
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18003bd30  mov     [rsp-8+arg_10], rbx
0x18003bd35  push    rbp
0x18003bd36  push    rsi
0x18003bd37  push    rdi
0x18003bd38  push    r12
0x18003bd3a  push    r13
0x18003bd3c  push    r14
0x18003bd3e  push    r15
0x18003bd40  lea     rbp, [rsp-780h]
0x18003bd48  sub     rsp, 880h
0x18003bd4f  mov     rax, cs:__security_cookie
0x18003bd56  xor     rax, rsp
0x18003bd59  mov     [rbp+7B0h+var_40], rax
0x18003bd60  xor     r13d, r13d
0x18003bd63  mov     rsi, rdx
0x18003bd66  mov     qword ptr [rsp+8B0h+dwEncodingType], r13
0x18003bd6b  mov     rdi, rcx
0x18003bd6e  mov     ebx, r13d
0x18003bd71  mov     r12d, r13d
0x18003bd74  mov     r14d, r13d
0x18003bd77  test    rcx, rcx
0x18003bd7a  jnz     short loc_18003BD8A
0x18003bd7c  lea     ecx, [rdi+57h]; dwErrCode
0x18003bd7f  call    cs:__imp_SetLastError
0x18003bd85  jmp     loc_18003C24E
0x18003bd8a  xor     r9d, r9d; lpSecurityAttributes
0x18003bd8d  mov     [rsp+8B0h+hTemplateFile], r13; hTemplateFile
0x18003bd92  mov     [rsp+8B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003bd9a  mov     edx, 80000000h; dwDesiredAccess
0x18003bd9f  mov     [rsp+8B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003bda7  lea     r8d, [r9+5]; dwShareMode
0x18003bdab  call    cs:__imp_CreateFileW
0x18003bdb1  mov     r15, rax
0x18003bdb4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bdb8  jz      loc_18003C24E
0x18003bdbe  mov     ecx, 30h ; '0'; uBytes
0x18003bdc3  call    CatalogNew
0x18003bdc8  mov     rbx, rax
0x18003bdcb  test    rax, rax
0x18003bdce  jz      loc_18003C245
0x18003bdd4  xorps   xmm0, xmm0
0x18003bdd7  mov     rcx, rdi; Str
0x18003bdda  movups  xmmword ptr [rax], xmm0
0x18003bddd  movups  xmmword ptr [rax+10h], xmm0
0x18003bde1  movups  xmmword ptr [rax+20h], xmm0
0x18003bde5  mov     [rax+8], r15
0x18003bde9  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003bded  mov     dword ptr [rax], 30h ; '0'
0x18003bdf3  mov     [rsp+8B0h+var_860], r15
0x18003bdf8  lea     edx, [r15+5Dh]; Ch
0x18003bdfc  call    cs:__imp_wcsrchr
0x18003be02  mov     [rsp+8B0h+String], rax
0x18003be07  mov     edx, 404h; unsigned __int64
0x18003be0c  lea     rcx, [rsp+8B0h+var_850]; unsigned __int16 *
0x18003be11  lea     r8, [rax+2]
0x18003be15  test    rax, rax
0x18003be18  jnz     short loc_18003BE1D
0x18003be1a  mov     r8, rdi; unsigned __int16 *
0x18003be1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003be22  test    eax, eax
0x18003be24  js      loc_18003C234
0x18003be2a  lea     rdi, aCatalogheader; "[CatalogHeader]"
0x18003be31  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003be34  mov     rdx, rdi; Buf2
0x18003be37  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003be3c  test    eax, eax
0x18003be3e  jnz     short loc_18003BE5E
0x18003be40  test    rsi, rsi
0x18003be43  jz      loc_18003C234
0x18003be49  lea     edx, [rax+4]
0x18003be4c  mov     r8, rdi
0x18003be4f  mov     rax, rsi
0x18003be52  xor     ecx, ecx
0x18003be54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be59  jmp     loc_18003C234
0x18003be5e  lea     rax, [rsp+8B0h+dwEncodingType]
0x18003be63  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003be68  lea     r9, [rsp+8B0h+var_850]; unsigned __int16 *
0x18003be6d  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003be72  lea     r8, aName; "Name"
0x18003be79  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003be7c  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003be81  test    eax, eax
0x18003be83  jnz     short loc_18003BEA4
0x18003be85  test    rsi, rsi
0x18003be88  jz      short loc_18003BE9A
0x18003be8a  lea     edx, [rax+4]
0x18003be8d  mov     r8, rdi
0x18003be90  mov     rax, rsi
0x18003be93  xor     ecx, ecx
0x18003be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be9a  mov     r12, qword ptr [rsp+8B0h+dwEncodingType]
0x18003be9f  jmp     loc_18003C234
0x18003bea4  mov     rdx, rdi; Buf2
0x18003bea7  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003beaa  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003beaf  lea     rsi, [rbx+20h]
0x18003beb3  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003beb8  xor     r9d, r9d; unsigned __int16 *
0x18003bebb  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rsi; unsigned __int16 **
0x18003bec0  lea     r8, aResultdir; "ResultDir"
0x18003bec7  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003beca  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003becf  mov     r12, qword ptr [rsp+8B0h+dwEncodingType]
0x18003bed4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003bed8  mov     rax, rcx
0x18003bedb  inc     rax
0x18003bede  cmp     [r12+rax*2], r13w
0x18003bee3  jnz     short loc_18003BEDB
0x18003bee5  mov     rdx, [rsi]
0x18003bee8  test    rdx, rdx
0x18003beeb  jz      short loc_18003BEF9
0x18003beed  inc     rcx
0x18003bef0  cmp     [rdx+rcx*2], r13w
0x18003bef5  jnz     short loc_18003BEED
0x18003bef7  add     eax, ecx
0x18003bef9  add     eax, 6
0x18003befc  mov     edi, eax
0x18003befe  lea     rcx, [rax+rax]; uBytes
0x18003bf02  mov     eax, 0FFFFFFFFh
0x18003bf07  cmp     rcx, rax
0x18003bf0a  ja      loc_18003C229
0x18003bf10  call    CatalogNew
0x18003bf15  mov     r14, rax
0x18003bf18  test    rax, rax
0x18003bf1b  jz      loc_18003C234
0x18003bf21  mov     [rax], r13w
0x18003bf25  mov     r8, [rsi]; unsigned __int16 *
0x18003bf28  test    r8, r8
0x18003bf2b  jz      short loc_18003BF67
0x18003bf2d  mov     edx, edi; unsigned __int64
0x18003bf2f  mov     rcx, rax; unsigned __int16 *
0x18003bf32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bf37  mov     r10, [rsi]
0x18003bf3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003bf3e  inc     rax
0x18003bf41  cmp     [r10+rax*2], r13w
0x18003bf46  jnz     short loc_18003BF3E
0x18003bf48  mov     ecx, 5Ch ; '\'
0x18003bf4d  cmp     [r10+rax*2-2], cx
0x18003bf53  jz      short loc_18003BF67
0x18003bf55  lea     r8, asc_1800557E4; "\\"
0x18003bf5c  mov     rdx, rdi; unsigned __int64
0x18003bf5f  mov     rcx, r14; unsigned __int16 *
0x18003bf62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bf67  mov     r8, r12; unsigned __int16 *
0x18003bf6a  mov     rdx, rdi; unsigned __int64
0x18003bf6d  mov     rcx, r14; unsigned __int16 *
0x18003bf70  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bf75  mov     edx, 2Eh ; '.'; Ch
0x18003bf7a  mov     rcx, r14; Str
0x18003bf7d  call    cs:__imp_wcsrchr
0x18003bf83  test    rax, rax
0x18003bf86  jnz     short loc_18003BFAC
0x18003bf88  lea     r8, asc_1800581EC; "."
0x18003bf8f  mov     rdx, rdi; unsigned __int64
0x18003bf92  mov     rcx, r14; unsigned __int16 *
0x18003bf95  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bf9a  lea     r8, aCat; "CAT"
0x18003bfa1  mov     rdx, rdi; unsigned __int64
0x18003bfa4  mov     rcx, r14; unsigned __int16 *
0x18003bfa7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bfac  lea     rdx, aCatalogheader; "[CatalogHeader]"
0x18003bfb3  mov     [rsp+8B0h+dwEncodingType], r13d
0x18003bfb8  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003bfbb  mov     esi, 1
0x18003bfc0  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003bfc5  lea     rax, [rsp+8B0h+String]
0x18003bfca  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003bfcf  xor     r9d, r9d; unsigned __int16 *
0x18003bfd2  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003bfd7  lea     r8, aCatalogversion; "CatalogVersion"
0x18003bfde  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003bfe1  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003bfe6  mov     rdi, [rsp+8B0h+String]
0x18003bfeb  test    rdi, rdi
0x18003bfee  jz      short loc_18003C00F
0x18003bff0  xor     edx, edx; EndPtr
0x18003bff2  lea     r8d, [rsi+9]; Radix
0x18003bff6  mov     rcx, rdi; String
0x18003bff9  call    cs:__imp_wcstol
0x18003bfff  mov     rcx, rdi; hMem
0x18003c002  mov     esi, eax
0x18003c004  call    cs:__imp_LocalFree
0x18003c00a  mov     [rsp+8B0h+String], r13
0x18003c00f  lea     rdx, aCatalogheader; "[CatalogHeader]"
0x18003c016  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c019  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003c01e  lea     rax, [rsp+8B0h+String]
0x18003c023  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003c028  lea     r9, a0x00010001; "0x00010001"
0x18003c02f  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003c034  lea     r8, aEncodingtype; "EncodingType"
0x18003c03b  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c03e  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003c043  mov     rdi, [rsp+8B0h+String]
0x18003c048  test    rdi, rdi
0x18003c04b  jz      short loc_18003C06E
0x18003c04d  xor     edx, edx; EndPtr
0x18003c04f  mov     rcx, rdi; String
0x18003c052  lea     r8d, [rdx+10h]; Radix
0x18003c056  call    cs:__imp_wcstol
0x18003c05c  mov     rcx, rdi; hMem
0x18003c05f  mov     [rsp+8B0h+dwEncodingType], eax
0x18003c063  call    cs:__imp_LocalFree
0x18003c069  mov     [rsp+8B0h+String], r13
0x18003c06e  lea     rdx, aCatalogheader; "[CatalogHeader]"
0x18003c075  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c078  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003c07d  lea     rax, [rsp+8B0h+String]
0x18003c082  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003c087  lea     r9, aFalse; "false"
0x18003c08e  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003c093  lea     r8, aPagehashes; "PageHashes"
0x18003c09a  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c09d  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003c0a2  mov     rdi, [rsp+8B0h+String]
0x18003c0a7  test    rdi, rdi
0x18003c0aa  jz      short loc_18003C0D8
0x18003c0ac  lea     rdx, aFalse; "false"
0x18003c0b3  mov     rcx, rdi; String1
0x18003c0b6  call    cs:__imp__wcsicmp
0x18003c0bc  mov     ecx, r13d
0x18003c0bf  test    eax, eax
0x18003c0c1  setnz   cl
0x18003c0c4  mov     cs:?g_PageHashes@@3HA, ecx; int g_PageHashes
0x18003c0ca  mov     rcx, rdi; hMem
0x18003c0cd  call    cs:__imp_LocalFree
0x18003c0d3  mov     [rsp+8B0h+String], r13
0x18003c0d8  lea     rdx, aCatalogheader; "[CatalogHeader]"
0x18003c0df  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c0e2  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003c0e7  lea     rax, [rsp+8B0h+String]
0x18003c0ec  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x18003c0f1  lea     r9, aSha1; "SHA1"
0x18003c0f8  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003c0fd  lea     r8, aHashalgorithms; "HashAlgorithms"
0x18003c104  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c107  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003c10c  test    eax, eax
0x18003c10e  jnz     short loc_18003C118
0x18003c110  lea     ecx, [rax+8]
0x18003c113  jmp     loc_18003C22E
0x18003c118  lea     r15d, [rsi-1]
0x18003c11c  mov     edi, 57h ; 'W'
0x18003c121  cmp     r15d, 1
0x18003c125  ja      short loc_18003C174
0x18003c127  mov     rcx, [rsp+8B0h+String]; String2
0x18003c12c  call    CatalogFindHashAlgorithm
0x18003c131  test    rax, rax
0x18003c134  jz      short loc_18003C174
0x18003c136  cmp     esi, [rax+18h]
0x18003c139  jb      short loc_18003C174
0x18003c13b  cmp     esi, [rax+1Ch]
0x18003c13e  ja      short loc_18003C174
0x18003c140  mov     rcx, [rax+8]; String1
0x18003c144  lea     rsi, a13143226; "1.3.14.3.2.26"
0x18003c14b  lea     r13, qword_180058358
0x18003c152  mov     cs:off_180069238, rcx; "1.3.14.3.2.26"
0x18003c159  mov     r13d, [r13+r15*4+0]
0x18003c15e  mov     rdx, rsi; String2
0x18003c161  xor     edi, edi
0x18003c163  call    cs:__imp__stricmp
0x18003c169  test    eax, eax
0x18003c16b  jnz     short loc_18003C174
0x18003c16d  mov     cs:off_180069238, rsi; "1.3.14.3.2.26"
0x18003c174  mov     rcx, [rsp+8B0h+String]; hMem
0x18003c179  call    cs:__imp_LocalFree
0x18003c17f  mov     [rsp+8B0h+String], 0
0x18003c188  test    edi, edi
0x18003c18a  jz      short loc_18003C1A1
0x18003c18c  mov     ecx, edi; dwErrCode
0x18003c18e  call    cs:__imp_SetLastError
0x18003c194  mov     r15, [rsp+8B0h+var_860]
0x18003c199  xor     r13d, r13d
0x18003c19c  jmp     loc_18003C234
0x18003c1a1  lea     rdx, aCatalogheader; "[CatalogHeader]"
0x18003c1a8  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c1ab  call    ?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z; CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)
0x18003c1b0  lea     rax, [rsp+8B0h+String]
0x18003c1b5  mov     qword ptr [rsp+8B0h+dwFlagsAndAttributes], 0; unsigned __int16 *
0x18003c1be  xor     r9d, r9d; unsigned __int16 *
0x18003c1c1  mov     qword ptr [rsp+8B0h+dwCreationDisposition], rax; unsigned __int16 **
0x18003c1c6  lea     r8, aNonconformantf; "NonConformantFilesFallbackFlat"
0x18003c1cd  mov     rcx, rbx; struct CRYPTCATCDF_ *
0x18003c1d0  call    ?CDFGetParam@@YAHPEAUCRYPTCATCDF_@@PEBG11PEAPEAG1@Z; CDFGetParam(CRYPTCATCDF_ *,ushort const *,ushort const *,ushort const *,ushort * *,ushort const *)
0x18003c1d5  mov     rdi, [rsp+8B0h+String]
0x18003c1da  test    rdi, rdi
0x18003c1dd  jz      short loc_18003C206
0x18003c1df  lea     rdx, aTrue; "true"
0x18003c1e6  mov     rcx, rdi; String1
0x18003c1e9  call    cs:__imp__wcsicmp
0x18003c1ef  test    eax, eax
0x18003c1f1  jnz     short loc_18003C1FD
0x18003c1f3  mov     cs:?g_FallbackFlat@@3HA, 1; int g_FallbackFlat
0x18003c1fd  mov     rcx, rdi; hMem
0x18003c200  call    cs:__imp_LocalFree
0x18003c206  mov     eax, [rsp+8B0h+dwEncodingType]
0x18003c20a  xor     r8d, r8d; hProv
0x18003c20d  mov     r9d, r13d; dwPublicVersion
  ... truncated ...
```
