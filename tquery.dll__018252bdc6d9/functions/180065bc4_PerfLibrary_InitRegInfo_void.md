# PerfLibrary::InitRegInfo(void)

- ea: `0x180065bc4`
- end: `0x180065e74`
- name: `?InitRegInfo@PerfLibrary@@AEAAHXZ`
- size: `688`
- prototype: `__int64 __fastcall(PerfLibrary *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180065834`

## callees

- `0x18002f914`
- `0x180065bc4`
- `0x1801480fc`
- `0x180160468`
- `0x18016a4ec`
- `0x180188d90`
- `0x1801b9afc`
- `0x1801b9c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065e02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065dba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065dba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065e49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065df8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065d45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065df8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180065c37`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180065c37`

## string_xrefs

- `0x180065c09`: `SYSTEM\CurrentControlSet\Services\%s\Performance`
- `0x180065cf3`: `[PerfCounter] MSFTESQL: Cannot open Reg Key "%ls".  Error 0x%08x in RegOpenKeyEx.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PerfLibrary::InitRegInfo(BYTE *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  const wchar_t *v5; // rcx
  bool v6; // al
  wchar_t *p_SubKey; // rdx
  int LastError; // eax
  int v9; // r8d
  unsigned __int16 v10; // r9
  signed int v11; // eax
  int v13; // eax
  int v14; // r8d
  unsigned __int16 v15; // r9
  signed int v16; // eax
  int v17; // eax
  int v18; // r8d
  unsigned __int16 v19; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  struct CSearchRegistryRedirectHelper *v25; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v27; // [rsp+58h] [rbp-A8h]
  wchar_t v28[256]; // [rsp+870h] [rbp+770h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( (int)StringCchPrintfW(v28, 0x100u, L"SYSTEM\\CurrentControlSet\\Services\\%s\\Performance", this) < 0 )
    v28[0] = 0;
  v25 = 0;
  v6 = (unsigned __int8)RtlIsStateSeparationEnabled(v3, v2, v4)
    && GetSearchRegistryRedirect(v5, &v25)
    && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath((const wchar_t *)v25, v28, &SubKey) >= 0;
  p_SubKey = v28;
  if ( v6 )
    p_SubKey = &SubKey;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, p_SubKey, 0, 0x20019u, &hKey) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CErrorString::CErrorString((CErrorString *)&SubKey, LastError, v9);
    PerfLibrary::Report((PerfLibrary *)this, 0x80002725, v27, v10);
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    LODWORD(phkResult) = v11;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x101,
      (unsigned int)L"[PerfCounter] MSFTESQL: Cannot open Reg Key \"%ls\".  Error 0x%08x in RegOpenKeyEx.",
      v28,
      phkResult);
    return 0;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"First Counter", 0, &Type, this + 268, &cbData) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    CErrorString::CErrorString((CErrorString *)&SubKey, v13, v14);
    PerfLibrary::Report((PerfLibrary *)this, 0x80002725, v27, v15);
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    LODWORD(phkResulta) = v16;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x116,
      (unsigned int)L"[PerfCounter] MSFTESQL: Cannot query value First Counter in reg key \"%ls\".  Error 0x%08x in RegQueryValueEx.",
      v28,
      phkResulta);
    RegCloseKey(hKey);
    return 0;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"First Help", 0, &Type, this + 264, &cbData) )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    CErrorString::CErrorString((CErrorString *)&SubKey, v17, v18);
    PerfLibrary::Report((PerfLibrary *)this, 0x80002725, v27, v19);
    RegCloseKey(hKey);
    return 0;
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180065bc4  mov     [rsp-8+arg_8], rdi
0x180065bc9  push    rbp
0x180065bca  lea     rbp, [rsp-980h]
0x180065bd2  sub     rsp, 0A80h
0x180065bd9  mov     rax, cs:__security_cookie
0x180065be0  xor     rax, rsp
0x180065be3  mov     [rbp+980h+var_10], rax
0x180065bea  mov     rdi, rcx
0x180065bed  mov     [rsp+0A80h+hKey], 0
0x180065bf6  mov     [rsp+0A80h+cbData], 0
0x180065bfe  mov     [rsp+0A80h+Type], 0
0x180065c06  mov     r9, rcx
0x180065c09  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\%s"...
0x180065c10  mov     edx, 100h; unsigned __int64
0x180065c15  lea     rcx, [rbp+980h+var_210]; wchar_t *
0x180065c1c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180065c21  test    eax, eax
0x180065c23  jns     short loc_180065C2E
0x180065c25  xor     eax, eax
0x180065c27  mov     [rbp+980h+var_210], ax
0x180065c2e  mov     [rsp+0A80h+var_A38], 0
0x180065c37  call    cs:__imp_RtlIsStateSeparationEnabled
0x180065c3d  test    al, al
0x180065c3f  jz      short loc_180065C6D
0x180065c41  lea     rdx, [rsp+0A80h+var_A38]; struct CSearchRegistryRedirectHelper **
0x180065c46  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x180065c4b  test    al, al
0x180065c4d  jz      short loc_180065C6D
0x180065c4f  lea     r8, [rsp+0A80h+SubKey]; wchar_t *
0x180065c54  lea     rdx, [rbp+980h+var_210]; wchar_t *
0x180065c5b  mov     rcx, [rsp+0A80h+var_A38]; this
0x180065c60  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180065c65  test    eax, eax
0x180065c67  js      short loc_180065C6D
0x180065c69  mov     al, 1
0x180065c6b  jmp     short loc_180065C6F
0x180065c6d  xor     al, al
0x180065c6f  lea     rdx, [rbp+980h+var_210]
0x180065c76  lea     rcx, [rsp+0A80h+SubKey]
0x180065c7b  test    al, al
0x180065c7d  cmovnz  rdx, rcx; lpSubKey
0x180065c81  lea     rax, [rsp+0A80h+hKey]
0x180065c86  mov     [rsp+0A80h+phkResult], rax; phkResult
0x180065c8b  mov     r9d, 20019h; samDesired
0x180065c91  xor     r8d, r8d; ulOptions
0x180065c94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065c9b  call    cs:__imp_RegOpenKeyExW
0x180065ca1  test    eax, eax
0x180065ca3  jz      short loc_180065D13
0x180065ca5  call    cs:__imp_GetLastError
0x180065cab  test    eax, eax
0x180065cad  jle     short loc_180065CB7
0x180065caf  movzx   eax, ax
0x180065cb2  or      eax, 80070000h
0x180065cb7  mov     edx, eax; dwMessageId
0x180065cb9  lea     rcx, [rsp+0A80h+SubKey]; this
0x180065cbe  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x180065cc3  nop
0x180065cc4  mov     r8, [rsp+0A80h+var_A28]; wchar_t *
0x180065cc9  mov     edx, 80002725h; unsigned int
0x180065cce  mov     rcx, rdi; this
0x180065cd1  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065cd6  call    cs:__imp_GetLastError
0x180065cdc  test    eax, eax
0x180065cde  jle     short loc_180065CE8
0x180065ce0  movzx   eax, ax
0x180065ce3  or      eax, 80070000h
0x180065ce8  mov     dword ptr [rsp+0A80h+phkResult], eax
0x180065cec  lea     r9, [rbp+980h+var_210]; wchar_t *
0x180065cf3  lea     r8, aPerfcounterMsf_20; "[PerfCounter] MSFTESQL: Cannot open Reg"...
0x180065cfa  mov     edx, 101h; wchar_t *
0x180065cff  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180065d06  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065d0b  nop
0x180065d0c  xor     eax, eax
0x180065d0e  jmp     loc_180065E54
0x180065d13  mov     [rsp+0A80h+cbData], 4
0x180065d1b  lea     rax, [rdi+10Ch]
0x180065d22  lea     rcx, [rsp+0A80h+cbData]
0x180065d27  mov     [rsp+0A80h+lpcbData], rcx; lpcbData
0x180065d2c  mov     [rsp+0A80h+phkResult], rax; lpData
0x180065d31  lea     r9, [rsp+0A80h+Type]; lpType
0x180065d36  xor     r8d, r8d; lpReserved
0x180065d39  lea     rdx, aFirstCounter; "First Counter"
0x180065d40  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180065d45  call    cs:__imp_RegQueryValueExW
0x180065d4b  test    eax, eax
0x180065d4d  jz      short loc_180065DC6
0x180065d4f  call    cs:__imp_GetLastError
0x180065d55  test    eax, eax
0x180065d57  jle     short loc_180065D61
0x180065d59  movzx   eax, ax
0x180065d5c  or      eax, 80070000h
0x180065d61  mov     edx, eax; dwMessageId
0x180065d63  lea     rcx, [rsp+0A80h+SubKey]; this
0x180065d68  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x180065d6d  nop
0x180065d6e  mov     r8, [rsp+0A80h+var_A28]; wchar_t *
0x180065d73  mov     edx, 80002725h; unsigned int
0x180065d78  mov     rcx, rdi; this
0x180065d7b  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065d80  call    cs:__imp_GetLastError
0x180065d86  test    eax, eax
0x180065d88  jle     short loc_180065D92
0x180065d8a  movzx   eax, ax
0x180065d8d  or      eax, 80070000h
0x180065d92  mov     dword ptr [rsp+0A80h+phkResult], eax
0x180065d96  lea     r9, [rbp+980h+var_210]; wchar_t *
0x180065d9d  lea     r8, aPerfcounterMsf_24; "[PerfCounter] MSFTESQL: Cannot query va"...
0x180065da4  mov     edx, 116h; wchar_t *
0x180065da9  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180065db0  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065db5  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180065dba  call    cs:__imp_RegCloseKey
0x180065dc0  nop
0x180065dc1  jmp     loc_180065D0C
0x180065dc6  mov     [rsp+0A80h+cbData], 4
0x180065dce  lea     rax, [rdi+108h]
0x180065dd5  lea     rcx, [rsp+0A80h+cbData]
0x180065dda  mov     [rsp+0A80h+lpcbData], rcx; lpcbData
0x180065ddf  mov     [rsp+0A80h+phkResult], rax; lpData
0x180065de4  lea     r9, [rsp+0A80h+Type]; lpType
0x180065de9  xor     r8d, r8d; lpReserved
0x180065dec  lea     rdx, aFirstHelp; "First Help"
0x180065df3  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180065df8  call    cs:__imp_RegQueryValueExW
0x180065dfe  test    eax, eax
0x180065e00  jz      short loc_180065E44
0x180065e02  call    cs:__imp_GetLastError
0x180065e08  test    eax, eax
0x180065e0a  jle     short loc_180065E14
0x180065e0c  movzx   eax, ax
0x180065e0f  or      eax, 80070000h
0x180065e14  mov     edx, eax; dwMessageId
0x180065e16  lea     rcx, [rsp+0A80h+SubKey]; this
0x180065e1b  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x180065e20  nop
0x180065e21  mov     r8, [rsp+0A80h+var_A28]; wchar_t *
0x180065e26  mov     edx, 80002725h; unsigned int
0x180065e2b  mov     rcx, rdi; this
0x180065e2e  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065e33  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180065e38  call    cs:__imp_RegCloseKey
0x180065e3e  nop
0x180065e3f  jmp     loc_180065D0C
0x180065e44  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180065e49  call    cs:__imp_RegCloseKey
0x180065e4f  mov     eax, 1
0x180065e54  mov     rcx, [rbp+980h+var_10]
0x180065e5b  xor     rcx, rsp; StackCookie
0x180065e5e  call    __security_check_cookie
0x180065e63  mov     rdi, [rsp+0A80h+arg_8]
0x180065e6b  add     rsp, 0A80h
0x180065e72  pop     rbp
0x180065e73  retn
```
