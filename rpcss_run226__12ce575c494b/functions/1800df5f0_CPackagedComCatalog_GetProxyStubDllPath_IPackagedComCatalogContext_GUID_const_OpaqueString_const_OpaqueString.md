# CPackagedComCatalog::GetProxyStubDllPath(IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,OpaqueString &)

- ea: `0x1800df5f0`
- end: `0x1800dfa29`
- name: `?GetProxyStubDllPath@CPackagedComCatalog@@QEAAJPEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@AEAV4@@Z`
- size: `1081`
- prototype: `int(CPackagedComCatalog *__hidden this, struct IPackagedComCatalogContext *, const struct _GUID *, const struct OpaqueString *, struct OpaqueString *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d9528`
- `0x1800d9744`
- `0x1800dea00`

## callees

- `0x18000ae40`
- `0x18000f270`
- `0x180016160`
- `0x18002ba28`
- `0x180034540`
- `0x1800414d0`
- `0x18008e98c`
- `0x18009ffc0`
- `0x1800a16f4`
- `0x1800b27e0`
- `0x1800d8e48`
- `0x1800dec28`
- `0x1800df5f0`
- `0x1800dfd00`
- `0x1800e1d00`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df89e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df7f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df89e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df8ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df8fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800df9f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df91e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df97f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df91e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800df97f`

## string_xrefs

- `0x1800df724`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df757`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df877`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df8da`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df996`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800df718`: `CPackagedComCatalog::GetProxyStubDllPath`
- `0x1800df86b`: `CPackagedComCatalog::GetProxyStubDllPath`
- `0x1800df98a`: `CPackagedComCatalog::GetProxyStubDllPath`
- `0x1800df87e`: `Proxy-stub not present for the current process architecture (PackageId=%ws, ProxyStubCLSID=%ws): proxy-stub entry is missing DllPath_<arch> for the current process architecture and DllPath.`
- `0x1800df99d`: `Proxy-stub not present for the current process architecture (PackageId=%ws, ProxyStubCLSID=%ws): proxy-stub entry is missing DllPath_<arch> for the current process architecture and DllPath.`
- `0x1800df736`: `Failed to lookup packaged PSCLSID. PSCLSID=%ws PackageName=%ws hr=%!HRESULT!`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetProxyStubDllPath(
        CPackagedComCatalog *this,
        struct IPackagedComCatalogContext *a2,
        const struct _GUID *a3,
        HSTRING *a4,
        struct OpaqueString *a5)
{
  __int64 v5; // rax
  __int64 (__fastcall *v8)(struct IPackagedComCatalogContext *, HSTRING, const struct _GUID *, _BYTE *, int *, __int64 *); // rax
  HSTRING v9; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  Com::PackagedCom *v13; // rcx
  CGuidStr *v14; // rax
  int v15; // r9d
  __int64 v16; // r11
  unsigned int SupportedSyntaxVersion; // eax
  __int64 v18; // rcx
  HSTRING *ValueOrDefault; // rdi
  HSTRING v20; // rbx
  HSTRING *v21; // rdi
  HSTRING v22; // rbx
  char v23; // di
  CGuidStr *v24; // rdi
  PCWSTR StringRawBuffer; // rax
  HSTRING v26; // rcx
  int PackagedSystemMetadataFilePath; // eax
  __int64 v28; // rdx
  const WCHAR *v29; // rax
  CGuidStr *v30; // rbx
  PCWSTR v31; // rax
  int v33; // [rsp+20h] [rbp-E0h]
  HSTRING v34; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v36; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v40[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  _BYTE v42[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  char v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  _BYTE v46[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h]
  char v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  char v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  __int16 v52; // [rsp+D0h] [rbp-30h]
  char v53; // [rsp+D4h] [rbp-2Ch]
  unsigned int v54; // [rsp+D8h] [rbp-28h]
  char v55; // [rsp+DCh] [rbp-24h]
  int v56; // [rsp+E0h] [rbp-20h]
  _BYTE v57[80]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = *(_QWORD *)a2;
  v40[0] = 0;
  v8 = *(__int64 (__fastcall **)(struct IPackagedComCatalogContext *, HSTRING, const struct _GUID *, _BYTE *, int *, __int64 *))(v5 + 88);
  v9 = *a4;
  v41 = 0;
  v42[0] = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46[0] = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  *(_QWORD *)v39 = 0;
  v38 = 0;
  v11 = v8(a2, v9, a3, v40, v39, &v38);
  v33 = v39[0];
  CPackagedComCatalog::LogReadEntryResult(v11, v12, a4, a3);
  if ( v11 != -2147024894 )
  {
    if ( (v11 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B5,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v11,
        v33);
      goto LABEL_33;
    }
    if ( v53 )
    {
      SupportedSyntaxVersion = Com::PackagedCom::GetSupportedSyntaxVersion(v13);
      if ( v54 > SupportedSyntaxVersion )
        MicrosoftTelemetryAssertTriggeredNoArgs(v18);
    }
    v37 = 0;
    ValueOrDefault = (HSTRING *)Optional<OpaqueString>::GetValueOrDefault(v46, &string, &v37);
    WindowsDeleteString(0);
    v20 = *ValueOrDefault;
    *ValueOrDefault = 0;
    v36 = v20;
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v37);
    if ( v20 )
    {
      v23 = 0;
    }
    else
    {
      string = 0;
      v21 = (HSTRING *)Optional<OpaqueString>::GetValueOrDefault(v42, &v37, &string);
      WindowsDeleteString(0);
      v22 = *v21;
      *v21 = 0;
      v36 = v22;
      WindowsDeleteString(v37);
      v37 = 0;
      WindowsDeleteString(string);
      v23 = 1;
      if ( !v22 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
        {
          v24 = CGuidStr::CGuidStr((CGuidStr *)v57, a3);
          StringRawBuffer = WindowsGetStringRawBuffer(*a4, 0);
          ComTraceMessageT<unsigned short const *,unsigned short *>(
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (unsigned int)"CPackagedComCatalog::GetProxyStubDllPath",
            2510,
            1,
            (__int64)L"Proxy-stub not present for the current process architecture (PackageId=%ws, ProxyStubCLSID=%ws): pr"
                      "oxy-stub entry is missing DllPath_<arch> for the current process architecture and DllPath.",
            StringRawBuffer,
            v24);
        }
        v26 = 0;
LABEL_18:
        WindowsDeleteString(v26);
        v11 = -2147221164;
        goto LABEL_33;
      }
    }
    v34 = 0;
    PackagedSystemMetadataFilePath = CPackagedComCatalog::GetPackagedSystemMetadataFilePath(
                                       (const struct OpaqueString *)a4,
                                       (const struct OpaqueString *)&v36,
                                       (struct OpaqueString *)&v34);
    v11 = PackagedSystemMetadataFilePath;
    if ( PackagedSystemMetadataFilePath < 0 )
    {
      v28 = 2517;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)PackagedSystemMetadataFilePath,
        v33);
      WindowsDeleteString(v34);
      v34 = 0;
      WindowsDeleteString(v36);
      goto LABEL_33;
    }
    if ( v23 )
    {
      LODWORD(string) = 0;
      v29 = WindowsGetStringRawBuffer(v34, 0);
      PackagedSystemMetadataFilePath = CoGetModuleArchitecture(v29, &string);
      v11 = PackagedSystemMetadataFilePath;
      if ( PackagedSystemMetadataFilePath < 0 )
      {
        v28 = 2522;
        goto LABEL_22;
      }
      if ( (_DWORD)string != 34404 )
      {
        if ( dword_18014E4B8
          || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
        {
          v30 = CGuidStr::CGuidStr((CGuidStr *)v57, a3);
          v31 = WindowsGetStringRawBuffer(*a4, 0);
          ComTraceMessageT<unsigned short const *,unsigned short *>(
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (unsigned int)"CPackagedComCatalog::GetProxyStubDllPath",
            2528,
            1,
            (__int64)L"Proxy-stub not present for the current process architecture (PackageId=%ws, ProxyStubCLSID=%ws): pr"
                      "oxy-stub entry is missing DllPath_<arch> for the current process architecture and DllPath.",
            v31,
            v30);
        }
        WindowsDeleteString(v34);
        v26 = v36;
        v34 = 0;
        goto LABEL_18;
      }
    }
    OpaqueString::operator=(a5, &v34);
    WindowsDeleteString(v34);
    v34 = 0;
    WindowsDeleteString(v36);
    v11 = 0;
    goto LABEL_33;
  }
  v11 = -2147221164;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    WindowsGetStringRawBuffer(*a4, 0);
    v14 = CGuidStr::CGuidStr((CGuidStr *)v57, a3);
    ComTraceMessageT<unsigned short *,unsigned short const *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (unsigned int)"CPackagedComCatalog::GetProxyStubDllPath",
      2481,
      v15,
      (__int64)L"Failed to lookup packaged PSCLSID. PSCLSID=%ws PackageName=%ws hr=%!HRESULT!",
      v14,
      v16,
      -2147221164);
  }
LABEL_33:
  ComProxyStubRegistrationEntryProperties::~ComProxyStubRegistrationEntryProperties((ComProxyStubRegistrationEntryProperties *)v40);
  return v11;
}

```

## disassembly

```asm
0x1800df5f0  push    rbp
0x1800df5f2  push    rbx
0x1800df5f3  push    rsi
0x1800df5f4  push    rdi
0x1800df5f5  push    r12
0x1800df5f7  push    r14
0x1800df5f9  push    r15
0x1800df5fb  lea     rbp, [rsp-50h]
0x1800df600  sub     rsp, 150h
0x1800df607  mov     rax, cs:__security_cookie
0x1800df60e  xor     rax, rsp
0x1800df611  mov     [rbp+80h+var_40], rax
0x1800df615  mov     rax, [rdx]
0x1800df618  lea     rcx, [rsp+180h+var_120]
0x1800df61d  mov     r15, [rbp+80h+arg_20]
0x1800df624  xor     r12d, r12d
0x1800df627  mov     [rsp+180h+var_158], rcx
0x1800df62c  mov     rsi, r9
0x1800df62f  mov     r10, rdx
0x1800df632  mov     [rsp+180h+var_110], r12b
0x1800df637  mov     rax, [rax+58h]
0x1800df63b  lea     rcx, [rsp+180h+var_118]
0x1800df640  mov     qword ptr [rsp+180h+var_160], rcx
0x1800df645  lea     r9, [rsp+180h+var_110]
0x1800df64a  mov     rdx, [rsi]
0x1800df64d  mov     rcx, r10
0x1800df650  mov     r14, r8
0x1800df653  mov     [rsp+180h+var_108], r12
0x1800df658  mov     [rbp+80h+var_100], r12b
0x1800df65c  mov     [rbp+80h+var_F8], r12
0x1800df660  mov     [rbp+80h+var_F0], r12b
0x1800df664  mov     [rbp+80h+var_E8], r12
0x1800df668  mov     [rbp+80h+var_E0], r12b
0x1800df66c  mov     [rbp+80h+var_D8], r12
0x1800df670  mov     [rbp+80h+var_D0], r12b
0x1800df674  mov     [rbp+80h+var_C8], r12
0x1800df678  mov     [rbp+80h+var_C0], r12b
0x1800df67c  mov     [rbp+80h+var_B8], r12
0x1800df680  mov     [rbp+80h+var_B0], r12w
0x1800df685  mov     [rbp+80h+var_AC], r12b
0x1800df689  mov     [rbp+80h+var_A8], r12d
0x1800df68d  mov     [rbp+80h+var_A4], r12b
0x1800df691  mov     [rbp+80h+var_A0], r12d
0x1800df695  mov     qword ptr [rsp+180h+var_118], r12
0x1800df69a  mov     [rsp+180h+var_120], r12
0x1800df69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6a4  mov     rcx, [rsp+180h+var_120]
0x1800df6a9  mov     r9, r14
0x1800df6ac  mov     [rsp+180h+var_158], rcx
0x1800df6b1  mov     r8, rsi
0x1800df6b4  mov     rcx, qword ptr [rsp+180h+var_118]
0x1800df6b9  mov     ebx, eax
0x1800df6bb  mov     qword ptr [rsp+180h+var_160], rcx; int
0x1800df6c0  mov     ecx, eax
0x1800df6c2  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComProxyStubRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComProxyStubRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComProxyStubRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComProxyStubRegistrationEntryPropertyFlags,ComProxyStubRegistrationEntryPropertyFlags)
0x1800df6c7  cmp     ebx, 80070002h
0x1800df6cd  jnz     short loc_1800DF74C
0x1800df6cf  mov     eax, cs:dword_18014E4B8
0x1800df6d5  mov     ebx, 80040154h
0x1800df6da  test    eax, eax
0x1800df6dc  jnz     short loc_1800DF6FA
0x1800df6de  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800df6e5  jz      loc_1800DF9FF
0x1800df6eb  xor     ecx, ecx
0x1800df6ed  call    IsWppLevelEnabled
0x1800df6f2  test    al, al
0x1800df6f4  jz      loc_1800DF9FF
0x1800df6fa  mov     rcx, [rsi]; string
0x1800df6fd  xor     edx, edx; length
0x1800df6ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800df705  mov     rdx, r14; struct _GUID *
0x1800df708  lea     rcx, [rbp+80h+var_90]; this
0x1800df70c  mov     r11, rax
0x1800df70f  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800df714  mov     [rsp+180h+var_148], ebx
0x1800df718  lea     rdx, aCpackagedcomca_6; "CPackagedComCatalog::GetProxyStubDllPat"...
0x1800df71f  mov     [rsp+180h+var_150], r11
0x1800df724  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df72b  mov     [rsp+180h+var_158], rax
0x1800df730  mov     r8d, 9B1h
0x1800df736  lea     rax, aFailedToLookup; "Failed to lookup packaged PSCLSID. PSCL"...
0x1800df73d  mov     qword ptr [rsp+180h+var_160], rax
0x1800df742  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800df747  jmp     loc_1800DF9FF
0x1800df74c  test    ebx, ebx
0x1800df74e  jns     short loc_1800DF770
0x1800df750  mov     rcx, [rbp+88h]; this
0x1800df757  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df75e  mov     r9d, ebx; char *
0x1800df761  mov     edx, 9B5h; void *
0x1800df766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df76b  jmp     loc_1800DF9FF
0x1800df770  cmp     [rbp+80h+var_AC], r12b
0x1800df774  jz      short loc_1800DF785
0x1800df776  call    ?GetSupportedSyntaxVersion@PackagedCom@Com@@YAIXZ; Com::PackagedCom::GetSupportedSyntaxVersion(void)
0x1800df77b  cmp     [rbp+80h+var_A8], eax
0x1800df77e  jbe     short loc_1800DF785
0x1800df780  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800df785  lea     r8, [rsp+180h+var_128]
0x1800df78a  mov     [rsp+180h+var_128], r12
0x1800df78f  lea     rdx, [rsp+180h+string]
0x1800df794  lea     rcx, [rbp+80h+var_E0]
0x1800df798  call    ?GetValueOrDefault@?$Optional@VOpaqueString@@@@QEBA?AVOpaqueString@@AEBV2@@Z; Optional<OpaqueString>::GetValueOrDefault(OpaqueString const &)
0x1800df79d  xor     ecx, ecx; string
0x1800df79f  mov     rdi, rax
0x1800df7a2  call    cs:__imp_WindowsDeleteString
0x1800df7a8  mov     rbx, [rdi]
0x1800df7ab  mov     [rdi], r12
0x1800df7ae  mov     rcx, [rsp+180h+string]; string
0x1800df7b3  mov     [rsp+180h+var_130], rbx
0x1800df7b8  call    cs:__imp_WindowsDeleteString
0x1800df7be  mov     rcx, [rsp+180h+var_128]; string
0x1800df7c3  mov     [rsp+180h+string], r12
0x1800df7c8  call    cs:__imp_WindowsDeleteString
0x1800df7ce  test    rbx, rbx
0x1800df7d1  jnz     loc_1800DF8AE
0x1800df7d7  lea     r8, [rsp+180h+string]
0x1800df7dc  mov     [rsp+180h+string], r12
0x1800df7e1  lea     rdx, [rsp+180h+var_128]
0x1800df7e6  lea     rcx, [rbp+80h+var_100]
0x1800df7ea  call    ?GetValueOrDefault@?$Optional@VOpaqueString@@@@QEBA?AVOpaqueString@@AEBV2@@Z; Optional<OpaqueString>::GetValueOrDefault(OpaqueString const &)
0x1800df7ef  mov     rcx, rbx; string
0x1800df7f2  mov     rdi, rax
0x1800df7f5  call    cs:__imp_WindowsDeleteString
0x1800df7fb  mov     rbx, [rdi]
0x1800df7fe  mov     [rdi], r12
0x1800df801  mov     rcx, [rsp+180h+var_128]; string
0x1800df806  mov     [rsp+180h+var_130], rbx
0x1800df80b  call    cs:__imp_WindowsDeleteString
0x1800df811  mov     rcx, [rsp+180h+string]; string
0x1800df816  mov     [rsp+180h+var_128], r12
0x1800df81b  call    cs:__imp_WindowsDeleteString
0x1800df821  mov     dil, 1
0x1800df824  test    rbx, rbx
0x1800df827  jnz     loc_1800DF8B1
0x1800df82d  mov     eax, cs:dword_18014E4B8
0x1800df833  test    eax, eax
0x1800df835  jnz     short loc_1800DF84C
0x1800df837  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800df83e  jz      short loc_1800DF89B
0x1800df840  lea     ecx, [rbx+1]
0x1800df843  call    IsWppLevelEnabled
0x1800df848  test    al, al
0x1800df84a  jz      short loc_1800DF89B
0x1800df84c  mov     rdx, r14; struct _GUID *
0x1800df84f  lea     rcx, [rbp+80h+var_90]; this
0x1800df853  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800df858  mov     rcx, [rsi]; string
0x1800df85b  xor     edx, edx; length
0x1800df85d  mov     rdi, rax
0x1800df860  call    cs:__imp_WindowsGetStringRawBuffer
0x1800df866  mov     [rsp+180h+var_150], rdi
0x1800df86b  lea     rdx, aCpackagedcomca_6; "CPackagedComCatalog::GetProxyStubDllPat"...
0x1800df872  mov     [rsp+180h+var_158], rax
0x1800df877  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df87e  lea     rax, aProxyStubNotPr; "Proxy-stub not present for the current "...
0x1800df885  mov     r9d, 1
0x1800df88b  mov     r8d, 9CEh
0x1800df891  mov     qword ptr [rsp+180h+var_160], rax
0x1800df896  call    ??$ComTraceMessageT@PEBGPEAG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG@Z; ComTraceMessageT<ushort const *,ushort *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *)
0x1800df89b  mov     rcx, rbx; string
0x1800df89e  call    cs:__imp_WindowsDeleteString
0x1800df8a4  mov     ebx, 80040154h
0x1800df8a9  jmp     loc_1800DF9FF
0x1800df8ae  mov     dil, r12b
0x1800df8b1  lea     r8, [rsp+180h+var_140]; struct OpaqueString *
0x1800df8b6  mov     [rsp+180h+var_140], r12
0x1800df8bb  lea     rdx, [rsp+180h+var_130]; struct OpaqueString *
0x1800df8c0  mov     rcx, rsi; struct OpaqueString *
0x1800df8c3  call    ?GetPackagedSystemMetadataFilePath@CPackagedComCatalog@@CAJAEBVOpaqueString@@0AEAV2@@Z; CPackagedComCatalog::GetPackagedSystemMetadataFilePath(OpaqueString const &,OpaqueString const &,OpaqueString &)
0x1800df8c8  mov     ebx, eax
0x1800df8ca  test    eax, eax
0x1800df8cc  jns     short loc_1800DF909
0x1800df8ce  mov     edx, 9D5h; void *
0x1800df8d3  mov     rcx, [rbp+88h]; this
0x1800df8da  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df8e1  mov     r9d, eax; char *
0x1800df8e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800df8e9  mov     rcx, [rsp+180h+var_140]; string
0x1800df8ee  call    cs:__imp_WindowsDeleteString
0x1800df8f4  mov     rcx, [rsp+180h+var_130]; string
0x1800df8f9  mov     [rsp+180h+var_140], r12
0x1800df8fe  call    cs:__imp_WindowsDeleteString
0x1800df904  jmp     loc_1800DF9FF
0x1800df909  test    dil, dil
0x1800df90c  jz      loc_1800DF9D4
0x1800df912  mov     rcx, [rsp+180h+var_140]; string
0x1800df917  xor     edx, edx; length
0x1800df919  mov     dword ptr [rsp+180h+string], r12d
0x1800df91e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800df924  mov     rcx, rax; lpFileName
0x1800df927  lea     rdx, [rsp+180h+string]
0x1800df92c  call    CoGetModuleArchitecture
0x1800df931  mov     ebx, eax
0x1800df933  test    eax, eax
0x1800df935  jns     short loc_1800DF93E
0x1800df937  mov     edx, 9DAh
0x1800df93c  jmp     short loc_1800DF8D3
0x1800df93e  cmp     dword ptr [rsp+180h+string], 8664h
0x1800df946  jz      loc_1800DF9D4
0x1800df94c  mov     eax, cs:dword_18014E4B8
0x1800df952  test    eax, eax
0x1800df954  jnz     short loc_1800DF96B
0x1800df956  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800df95d  jz      short loc_1800DF9BA
0x1800df95f  lea     ecx, [rax+1]
0x1800df962  call    IsWppLevelEnabled
0x1800df967  test    al, al
0x1800df969  jz      short loc_1800DF9BA
0x1800df96b  mov     rdx, r14; struct _GUID *
0x1800df96e  lea     rcx, [rbp+80h+var_90]; this
0x1800df972  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800df977  mov     rcx, [rsi]; string
0x1800df97a  xor     edx, edx; length
0x1800df97c  mov     rbx, rax
0x1800df97f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800df985  mov     [rsp+180h+var_150], rbx
0x1800df98a  lea     rdx, aCpackagedcomca_6; "CPackagedComCatalog::GetProxyStubDllPat"...
0x1800df991  mov     [rsp+180h+var_158], rax
0x1800df996  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800df99d  lea     rax, aProxyStubNotPr; "Proxy-stub not present for the current "...
0x1800df9a4  mov     r9d, 1
0x1800df9aa  mov     r8d, 9E0h
0x1800df9b0  mov     qword ptr [rsp+180h+var_160], rax
0x1800df9b5  call    ??$ComTraceMessageT@PEBGPEAG@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG@Z; ComTraceMessageT<ushort const *,ushort *>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *)
0x1800df9ba  mov     rcx, [rsp+180h+var_140]; string
0x1800df9bf  call    cs:__imp_WindowsDeleteString
0x1800df9c5  mov     rcx, [rsp+180h+var_130]
0x1800df9ca  mov     [rsp+180h+var_140], r12
0x1800df9cf  jmp     loc_1800DF89E
0x1800df9d4  lea     rdx, [rsp+180h+var_140]
0x1800df9d9  mov     rcx, r15
0x1800df9dc  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800df9e1  mov     rcx, [rsp+180h+var_140]; string
0x1800df9e6  call    cs:__imp_WindowsDeleteString
0x1800df9ec  mov     rcx, [rsp+180h+var_130]; string
0x1800df9f1  mov     [rsp+180h+var_140], r12
0x1800df9f6  call    cs:__imp_WindowsDeleteString
0x1800df9fc  mov     ebx, r12d
0x1800df9ff  lea     rcx, [rsp+180h+var_110]; this
0x1800dfa04  call    ??1ComProxyStubRegistrationEntryProperties@@QEAA@XZ; ComProxyStubRegistrationEntryProperties::~ComProxyStubRegistrationEntryProperties(void)
0x1800dfa09  mov     eax, ebx
0x1800dfa0b  mov     rcx, [rbp+80h+var_40]
0x1800dfa0f  xor     rcx, rsp; StackCookie
0x1800dfa12  call    __security_check_cookie
0x1800dfa17  add     rsp, 150h
0x1800dfa1e  pop     r15
0x1800dfa20  pop     r14
0x1800dfa22  pop     r12
0x1800dfa24  pop     rdi
0x1800dfa25  pop     rsi
0x1800dfa26  pop     rbx
0x1800dfa27  pop     rbp
0x1800dfa28  retn
```
