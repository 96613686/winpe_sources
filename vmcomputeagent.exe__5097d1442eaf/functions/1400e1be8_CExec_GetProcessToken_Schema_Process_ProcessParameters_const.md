# CExec::GetProcessToken(Schema::Process::ProcessParameters const &)

- ea: `0x1400e1be8`
- end: `0x1400e2173`
- name: `?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z`
- size: `1419`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x140005010`
- `0x140005360`
- `0x14000664c`
- `0x140008760`
- `0x14000ddac`
- `0x14001e4f4`
- `0x14002dd18`
- `0x1400341ac`
- `0x14003bc60`
- `0x1400e0654`
- `0x1400e1be8`
- `0x1400e22d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1d8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1e23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1e45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1f43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1f5b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1d8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1e23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1e45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1f43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e1f5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1e8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1f22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1f86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1fd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e203c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1e8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1f22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1f86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e1fd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e203c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1f0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e2029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1f0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e1fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e2029`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400e1eeb`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400e1eeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e1f90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e1f90`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400e1fa2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400e1fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1f7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e2034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1f1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1f7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e1fca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e2034`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400e2004`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400e2075`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400e2004`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400e2075`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1400e1db0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1400e1db0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400e1d2f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400e1d2f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400e1de3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400e1de3`

## string_xrefs

- `0x1400e20ca`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e20e6`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e20f7`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e2109`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e211b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e2137`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e2149`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e2161`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
void **__fastcall CExec::GetProcessToken(void **a1, __int64 a2)
{
  __int64 v2; // r13
  const WCHAR *v4; // rdi
  const WCHAR *v5; // r15
  __int64 v6; // rax
  const WCHAR *v7; // r12
  const WCHAR *v8; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // r8
  const WCHAR *v12; // rdx
  const unsigned __int16 *v13; // r8
  const char *v14; // r9
  PWTS_SESSION_INFO_1W v15; // rbx
  struct _WTS_SESSION_INFO_1W *v16; // rdi
  CExec *pDomainName; // rcx
  const unsigned __int16 *v18; // rdx
  const char *v19; // r9
  __int64 v20; // rdx
  HANDLE *ContainerVirtualAccountToken; // rdi
  HANDLE v22; // rsi
  HANDLE v23; // r15
  DWORD v24; // ebx
  const char *v25; // r9
  void *v26; // rbx
  HANDLE v27; // rsi
  DWORD v28; // edi
  LPCWSTR *v29; // rcx
  int v30; // eax
  HANDLE v31; // rdi
  bool v32; // zf
  char *v33; // rax
  DWORD v34; // ebx
  HANDLE CurrentProcess; // rax
  const char *v36; // r9
  DWORD v37; // ebx
  const WCHAR *v38; // rdx
  const char *v39; // r9
  HANDLE v40; // rsi
  DWORD LastError; // ebx
  const char *v42; // r9
  unsigned int pCount; // [rsp+20h] [rbp-89h]
  unsigned int pCounta; // [rsp+20h] [rbp-89h]
  __int128 v46; // [rsp+58h] [rbp-51h] BYREF
  __int128 v47; // [rsp+68h] [rbp-41h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+78h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-29h] BYREF
  void *phToken; // [rsp+88h] [rbp-21h] BYREF
  DWORD NumberOfEntries; // [rsp+90h] [rbp-19h] BYREF
  LPCWSTR lpszDomain[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-1h]
  unsigned __int64 v54; // [rsp+B0h] [rbp+7h]
  DWORD pLevel; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = a2;
  phToken = a1;
  *(_OWORD *)lpszDomain = 0;
  v53 = 0;
  v54 = 7;
  LOWORD(lpszDomain[0]) = 0;
  v4 = (const WCHAR *)(a2 + 88);
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v5 = (const WCHAR *)(a2 + 88);
  else
    v5 = *(const WCHAR **)v4;
  v6 = *(_QWORD *)(a2 + 104);
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v7 = (const WCHAR *)(a2 + 88);
  else
    v7 = *(const WCHAR **)v4;
  if ( v6 )
  {
    v8 = &v7[v6];
    trivial_2 = _std_find_trivial_2(v7, v8, 92);
    if ( (const WCHAR *)trivial_2 != v8 )
    {
      v10 = (trivial_2 - (__int64)v7) >> 1;
      if ( v10 != -1 )
      {
        v46 = 0;
        v47 = 0;
        v11 = (trivial_2 - (__int64)v7) >> 1;
        if ( *((_QWORD *)v4 + 2) < v10 )
          v11 = *((_QWORD *)v4 + 2);
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v12 = v4;
        else
          v12 = *(const WCHAR **)v4;
        std::wstring::_Construct<1,unsigned short const *>(&v46, v12, v11);
        std::wstring::operator=(lpszDomain, &v46);
        std::wstring::~wstring(&v46);
        v5 += v10 + 1;
      }
    }
  }
  if ( *(_BYTE *)(v2 + 179) )
  {
    if ( !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4E1,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)0x32,
        pCount);
    ppSessionInfo = 0;
    NumberOfEntries = 0;
    *(_QWORD *)&v46 = &ppSessionInfo;
    *((_QWORD *)&v46 + 1) = &NumberOfEntries;
    LOBYTE(v47) = 1;
    pLevel = 1;
    if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4EF,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v14);
    v15 = ppSessionInfo;
    if ( !ppSessionInfo && NumberOfEntries )
      gsl::details::terminate(retaddr);
    v16 = &ppSessionInfo[NumberOfEntries];
    while ( 1 )
    {
      if ( v15 == v16 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x4FD,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          (const char *)0x520,
          pCounta);
      pDomainName = (CExec *)v15->pDomainName;
      if ( pDomainName && v15->pUserName )
      {
        v18 = (const unsigned __int16 *)lpszDomain;
        if ( v54 > 7 )
          v18 = lpszDomain[0];
        if ( CExec::DomainMatchesSession(pDomainName, v18, v13) && !(unsigned int)_o__wcsicmp(v15->pUserName, v5) )
          break;
      }
      ++v15;
    }
    phToken = 0;
    if ( !WTSQueryUserToken(v15->SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4F8,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v19);
    *a1 = phToken;
    phToken = 0;
    if ( ppSessionInfo )
      WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries);
    goto LABEL_75;
  }
  if ( !*(_QWORD *)(v2 + 104) )
  {
    LOBYTE(a2) = *(_BYTE *)(v2 + 168) == 0;
    CExec::MakeContainerVirtualAccountToken(a1, a2);
    goto LABEL_75;
  }
  hObject = 0;
  if ( v53 )
    goto LABEL_53;
  if ( (unsigned int)_o__wcsicmp(v5, L"ContainerAdministrator") )
  {
    if ( !v53 && !(unsigned int)_o__wcsicmp(v5, L"ContainerUser") )
    {
      v20 = 0;
      goto LABEL_42;
    }
LABEL_53:
    v29 = lpszDomain;
    if ( v54 > 7 )
      v29 = (LPCWSTR *)lpszDomain[0];
    if ( (unsigned int)_o__wcsicmp(v29, L"NT AUTHORITY") )
    {
      v40 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v40);
        SetLastError(LastError);
      }
      hObject = 0;
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const WCHAR **)v4;
      if ( !LogonUserW(v4, L".", &szPassword, 2u, 0, &hObject) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x52B,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v42);
    }
    else
    {
      v30 = _o__wcsicmp(v5, L"SYSTEM");
      v31 = hObject;
      v32 = v30 == 0;
      v33 = (char *)hObject - 1;
      if ( v32 )
      {
        if ( (unsigned __int64)v33 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v34 = GetLastError();
          CloseHandle(v31);
          SetLastError(v34);
        }
        hObject = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, &hObject) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x515,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
            v36);
      }
      else
      {
        if ( (unsigned __int64)v33 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v37 = GetLastError();
          CloseHandle(v31);
          SetLastError(v37);
        }
        hObject = 0;
        v38 = (const WCHAR *)lpszDomain;
        if ( v54 > 7 )
          v38 = lpszDomain[0];
        if ( !LogonUserW(v5, v38, 0, 5u, 0, &hObject) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x51F,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
            v39);
      }
    }
    goto LABEL_48;
  }
  LOBYTE(v20) = 1;
LABEL_42:
  ContainerVirtualAccountToken = (HANDLE *)CExec::MakeContainerVirtualAccountToken(&phToken, v20);
  if ( &hObject != ContainerVirtualAccountToken )
  {
    v22 = hObject;
    v23 = *ContainerVirtualAccountToken;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v24 = GetLastError();
      CloseHandle(v22);
      SetLastError(v24);
    }
    hObject = v23;
    *ContainerVirtualAccountToken = 0;
  }
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
LABEL_48:
  if ( *(_BYTE *)(v2 + 168) )
  {
    phToken = 0;
    if ( !CreateRestrictedToken(hObject, 4u, 0, 0, 0, 0, 0, 0, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v25);
    v26 = phToken;
    v27 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v28 = GetLastError();
      CloseHandle(v27);
      SetLastError(v28);
    }
  }
  else
  {
    v26 = hObject;
  }
  *a1 = v26;
  hObject = 0;
LABEL_75:
  std::wstring::~wstring(lpszDomain);
  return a1;
}

```

## disassembly

```asm
0x1400e1be8  mov     [rsp-8+arg_10], rbx
0x1400e1bed  push    rbp
0x1400e1bee  push    rsi
0x1400e1bef  push    rdi
0x1400e1bf0  push    r12
0x1400e1bf2  push    r13
0x1400e1bf4  push    r14
0x1400e1bf6  push    r15
0x1400e1bf8  lea     rbp, [rsp-27h]
0x1400e1bfd  sub     rsp, 0D0h
0x1400e1c04  mov     rax, cs:__security_cookie
0x1400e1c0b  xor     rax, rsp
0x1400e1c0e  mov     [rbp+57h+var_40], rax
0x1400e1c12  mov     r13, rdx
0x1400e1c15  mov     r14, rcx
0x1400e1c18  mov     [rbp+57h+phToken], rcx
0x1400e1c1c  xorps   xmm0, xmm0
0x1400e1c1f  movups  xmmword ptr [rbp+57h+lpszDomain], xmm0
0x1400e1c23  mov     [rbp+57h+var_58], 0
0x1400e1c2b  mov     [rbp+57h+var_50], 7
0x1400e1c33  xor     eax, eax
0x1400e1c35  mov     word ptr [rbp+57h+lpszDomain], ax
0x1400e1c39  lea     rdi, [rdx+58h]
0x1400e1c3d  cmp     qword ptr [rdi+18h], 7
0x1400e1c42  jbe     short loc_1400E1C49
0x1400e1c44  mov     r15, [rdi]
0x1400e1c47  jmp     short loc_1400E1C4C
0x1400e1c49  mov     r15, rdi
0x1400e1c4c  mov     rax, [rdi+10h]
0x1400e1c50  jbe     short loc_1400E1C57
0x1400e1c52  mov     r12, [rdi]
0x1400e1c55  jmp     short loc_1400E1C5A
0x1400e1c57  mov     r12, rdi
0x1400e1c5a  test    rax, rax
0x1400e1c5d  jz      short loc_1400E1CD9
0x1400e1c5f  lea     rbx, [r12+rax*2]
0x1400e1c63  mov     r8d, 5Ch ; '\'
0x1400e1c69  mov     rdx, rbx
0x1400e1c6c  mov     rcx, r12
0x1400e1c6f  call    __std_find_trivial_2
0x1400e1c74  mov     rsi, rax
0x1400e1c77  cmp     rax, rbx
0x1400e1c7a  jz      short loc_1400E1CD9
0x1400e1c7c  sub     rsi, r12
0x1400e1c7f  sar     rsi, 1
0x1400e1c82  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400e1c86  jz      short loc_1400E1CD9
0x1400e1c88  xorps   xmm0, xmm0
0x1400e1c8b  movups  [rbp+57h+var_A8], xmm0
0x1400e1c8f  xorps   xmm1, xmm1
0x1400e1c92  movdqu  [rbp+57h+var_98], xmm1
0x1400e1c97  mov     r8, rsi
0x1400e1c9a  cmp     [rdi+10h], rsi
0x1400e1c9e  cmovb   r8, [rdi+10h]
0x1400e1ca3  cmp     qword ptr [rdi+18h], 7
0x1400e1ca8  jbe     short loc_1400E1CAF
0x1400e1caa  mov     rdx, [rdi]
0x1400e1cad  jmp     short loc_1400E1CB2
0x1400e1caf  mov     rdx, rdi
0x1400e1cb2  lea     rcx, [rbp+57h+var_A8]
0x1400e1cb6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400e1cbb  lea     rdx, [rbp+57h+var_A8]
0x1400e1cbf  lea     rcx, [rbp+57h+lpszDomain]
0x1400e1cc3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400e1cc8  lea     rcx, [rbp+57h+var_A8]; void *
0x1400e1ccc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400e1cd1  lea     r15, [r15+rsi*2]
0x1400e1cd5  add     r15, 2
0x1400e1cd9  xor     r12d, r12d
0x1400e1cdc  cmp     [r13+0B3h], r12b
0x1400e1ce3  jz      loc_1400E1DEE
0x1400e1ce9  call    IsWTSEnumerateSessionsExWPresent
0x1400e1cee  test    al, al
0x1400e1cf0  jz      loc_1400E212D
0x1400e1cf6  mov     [rbp+57h+ppSessionInfo], r12
0x1400e1cfa  mov     [rbp+57h+NumberOfEntries], r12d
0x1400e1cfe  lea     rax, [rbp+57h+ppSessionInfo]
0x1400e1d02  mov     qword ptr [rbp+57h+var_A8], rax
0x1400e1d06  lea     rax, [rbp+57h+NumberOfEntries]
0x1400e1d0a  mov     qword ptr [rbp+57h+var_A8+8], rax
0x1400e1d0e  mov     byte ptr [rbp+57h+var_98], 1
0x1400e1d12  mov     [rbp+57h+pLevel], 1
0x1400e1d19  lea     rax, [rbp+57h+NumberOfEntries]
0x1400e1d1d  mov     [rsp+100h+pCount], rax; pCount
0x1400e1d22  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x1400e1d26  xor     r8d, r8d; Filter
0x1400e1d29  lea     rdx, [rbp+57h+pLevel]; pLevel
0x1400e1d2d  xor     ecx, ecx; hServer
0x1400e1d2f  call    cs:__imp_WTSEnumerateSessionsExW
0x1400e1d35  mov     rcx, [rbp+5Fh]; this
0x1400e1d39  test    eax, eax
0x1400e1d3b  jz      loc_1400E2149
0x1400e1d41  mov     eax, [rbp+57h+NumberOfEntries]
0x1400e1d44  mov     rbx, [rbp+57h+ppSessionInfo]
0x1400e1d48  test    rbx, rbx
0x1400e1d4b  jnz     short loc_1400E1D56
0x1400e1d4d  test    rax, rax
0x1400e1d50  jnz     loc_1400E215B
0x1400e1d56  imul    rdi, rax, 38h ; '8'
0x1400e1d5a  add     rdi, rbx
0x1400e1d5d  jmp     short loc_1400E1D9A
0x1400e1d5f  mov     rcx, [rbx+28h]; this
0x1400e1d63  test    rcx, rcx
0x1400e1d66  jz      short loc_1400E1D96
0x1400e1d68  cmp     [rbx+20h], r12
0x1400e1d6c  jz      short loc_1400E1D96
0x1400e1d6e  lea     rdx, [rbp+57h+lpszDomain]
0x1400e1d72  cmp     [rbp+57h+var_50], 7
0x1400e1d77  cmova   rdx, [rbp+57h+lpszDomain]; unsigned __int16 *
0x1400e1d7c  call    ?DomainMatchesSession@CExec@@YA_NPEBG0@Z; CExec::DomainMatchesSession(ushort const *,ushort const *)
0x1400e1d81  test    al, al
0x1400e1d83  jz      short loc_1400E1D96
0x1400e1d85  mov     rdx, r15
0x1400e1d88  mov     rcx, [rbx+20h]
0x1400e1d8c  call    cs:__imp__o__wcsicmp
0x1400e1d92  test    eax, eax
0x1400e1d94  jz      short loc_1400E1DA5
0x1400e1d96  add     rbx, 38h ; '8'
0x1400e1d9a  cmp     rbx, rdi
0x1400e1d9d  jz      loc_1400E20DC
0x1400e1da3  jmp     short loc_1400E1D5F
0x1400e1da5  mov     [rbp+57h+phToken], r12
0x1400e1da9  lea     rdx, [rbp+57h+phToken]; phToken
0x1400e1dad  mov     ecx, [rbx+8]; SessionId
0x1400e1db0  call    cs:__imp_WTSQueryUserToken
0x1400e1db6  mov     rcx, [rbp+5Fh]; this
0x1400e1dba  test    eax, eax
0x1400e1dbc  jz      loc_1400E2161
0x1400e1dc2  mov     rax, [rbp+57h+phToken]
0x1400e1dc6  mov     [r14], rax
0x1400e1dc9  mov     [rbp+57h+phToken], r12
0x1400e1dcd  mov     rdx, [rbp+57h+ppSessionInfo]; pMemory
0x1400e1dd1  test    rdx, rdx
0x1400e1dd4  jz      loc_1400E2097
0x1400e1dda  mov     r8d, [rbp+57h+NumberOfEntries]; NumberOfEntries
0x1400e1dde  mov     ecx, 2; WTSTypeClass
0x1400e1de3  call    cs:__imp_WTSFreeMemoryExW
0x1400e1de9  jmp     loc_1400E2097
0x1400e1dee  cmp     [r13+68h], r12
0x1400e1df2  jnz     short loc_1400E1E0B
0x1400e1df4  cmp     [r13+0A8h], r12b
0x1400e1dfb  setz    dl
0x1400e1dfe  mov     rcx, r14
0x1400e1e01  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x1400e1e06  jmp     loc_1400E2097
0x1400e1e0b  mov     [rbp+57h+hObject], r12
0x1400e1e0f  cmp     [rbp+57h+var_58], r12
0x1400e1e13  jnz     loc_1400E1F2E
0x1400e1e19  lea     rdx, aContaineradmin; "ContainerAdministrator"
0x1400e1e20  mov     rcx, r15
0x1400e1e23  call    cs:__imp__o__wcsicmp
0x1400e1e29  test    eax, eax
0x1400e1e2b  jnz     short loc_1400E1E31
0x1400e1e2d  mov     dl, 1
0x1400e1e2f  jmp     short loc_1400E1E55
0x1400e1e31  cmp     [rbp+57h+var_58], r12
0x1400e1e35  jnz     loc_1400E1F2E
0x1400e1e3b  lea     rdx, aContaineruser; "ContainerUser"
0x1400e1e42  mov     rcx, r15
0x1400e1e45  call    cs:__imp__o__wcsicmp
0x1400e1e4b  test    eax, eax
0x1400e1e4d  jnz     loc_1400E1F2E
0x1400e1e53  xor     edx, edx
0x1400e1e55  lea     rcx, [rbp+57h+phToken]
0x1400e1e59  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x1400e1e5e  mov     rdi, rax
0x1400e1e61  lea     rax, [rbp+57h+hObject]
0x1400e1e65  cmp     rax, rdi
0x1400e1e68  jz      short loc_1400E1E9B
0x1400e1e6a  mov     rsi, [rbp+57h+hObject]
0x1400e1e6e  lea     rcx, [rsi-1]
0x1400e1e72  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400e1e76  mov     r15, [rdi]
0x1400e1e79  ja      short loc_1400E1E94
0x1400e1e7b  call    cs:__imp_GetLastError
0x1400e1e81  mov     ebx, eax
0x1400e1e83  mov     rcx, rsi; hObject
0x1400e1e86  call    cs:__imp_CloseHandle
0x1400e1e8c  mov     ecx, ebx; dwErrCode
0x1400e1e8e  call    cs:__imp_SetLastError
0x1400e1e94  mov     [rbp+57h+hObject], r15
0x1400e1e98  mov     [rdi], r12
0x1400e1e9b  mov     rcx, [rbp+57h+phToken]; hObject
0x1400e1e9f  lea     rax, [rcx-1]
0x1400e1ea3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e1ea7  ja      short loc_1400E1EAF
0x1400e1ea9  call    cs:__imp_CloseHandle
0x1400e1eaf  cmp     [r13+0A8h], r12b
0x1400e1eb6  jz      loc_1400E208C
0x1400e1ebc  mov     [rbp+57h+phToken], r12
0x1400e1ec0  lea     rax, [rbp+57h+phToken]
0x1400e1ec4  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x1400e1ec9  mov     [rsp+100h+SidsToRestrict], r12; SidsToRestrict
0x1400e1ece  mov     [rsp+100h+RestrictedSidCount], r12d; RestrictedSidCount
0x1400e1ed3  mov     [rsp+100h+PrivilegesToDelete], r12; PrivilegesToDelete
0x1400e1ed8  mov     dword ptr [rsp+100h+pCount], r12d; DeletePrivilegeCount
0x1400e1edd  xor     r9d, r9d; SidsToDisable
0x1400e1ee0  xor     r8d, r8d; DisableSidCount
0x1400e1ee3  lea     edx, [r9+4]; Flags
0x1400e1ee7  mov     rcx, [rbp+57h+hObject]; ExistingTokenHandle
0x1400e1eeb  call    cs:__imp_CreateRestrictedToken
0x1400e1ef1  mov     rcx, [rbp+5Fh]; this
0x1400e1ef5  test    eax, eax
0x1400e1ef7  jz      loc_1400E20CA
0x1400e1efd  mov     rbx, [rbp+57h+phToken]
0x1400e1f01  mov     rsi, [rbp+57h+hObject]
0x1400e1f05  lea     rax, [rsi-1]
0x1400e1f09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e1f0d  ja      short loc_1400E1F29
0x1400e1f0f  call    cs:__imp_GetLastError
0x1400e1f15  mov     edi, eax
0x1400e1f17  mov     rcx, rsi; hObject
0x1400e1f1a  call    cs:__imp_CloseHandle
0x1400e1f20  mov     ecx, edi; dwErrCode
0x1400e1f22  call    cs:__imp_SetLastError
0x1400e1f28  nop
0x1400e1f29  jmp     loc_1400E2090
0x1400e1f2e  lea     rcx, [rbp+57h+lpszDomain]
0x1400e1f32  cmp     [rbp+57h+var_50], 7
0x1400e1f37  cmova   rcx, [rbp+57h+lpszDomain]
0x1400e1f3c  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x1400e1f43  call    cs:__imp__o__wcsicmp
0x1400e1f49  test    eax, eax
0x1400e1f4b  jnz     loc_1400E201B
0x1400e1f51  lea     rdx, aSystem_0; "SYSTEM"
0x1400e1f58  mov     rcx, r15
0x1400e1f5b  call    cs:__imp__o__wcsicmp
0x1400e1f61  mov     rdi, [rbp+57h+hObject]
0x1400e1f65  test    eax, eax
0x1400e1f67  lea     rax, [rdi-1]
0x1400e1f6b  jnz     short loc_1400E1FB9
0x1400e1f6d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e1f71  ja      short loc_1400E1F8C
0x1400e1f73  call    cs:__imp_GetLastError
0x1400e1f79  mov     ebx, eax
0x1400e1f7b  mov     rcx, rdi; hObject
0x1400e1f7e  call    cs:__imp_CloseHandle
0x1400e1f84  mov     ecx, ebx; dwErrCode
0x1400e1f86  call    cs:__imp_SetLastError
0x1400e1f8c  mov     [rbp+57h+hObject], r12
0x1400e1f90  call    cs:__imp_GetCurrentProcess
0x1400e1f96  lea     r8, [rbp+57h+hObject]; TokenHandle
0x1400e1f9a  mov     edx, 0F01FFh; DesiredAccess
0x1400e1f9f  mov     rcx, rax; ProcessHandle
0x1400e1fa2  call    cs:__imp_OpenProcessToken
0x1400e1fa8  mov     rcx, [rbp+5Fh]; this
0x1400e1fac  test    eax, eax
0x1400e1fae  jz      loc_1400E20F7
0x1400e1fb4  jmp     loc_1400E1EAF
0x1400e1fb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e1fbd  ja      short loc_1400E1FD8
0x1400e1fbf  call    cs:__imp_GetLastError
0x1400e1fc5  mov     ebx, eax
0x1400e1fc7  mov     rcx, rdi; hObject
0x1400e1fca  call    cs:__imp_CloseHandle
0x1400e1fd0  mov     ecx, ebx; dwErrCode
0x1400e1fd2  call    cs:__imp_SetLastError
0x1400e1fd8  mov     [rbp+57h+hObject], r12
0x1400e1fdc  lea     rdx, [rbp+57h+lpszDomain]
0x1400e1fe0  cmp     [rbp+57h+var_50], 7
0x1400e1fe5  cmova   rdx, [rbp+57h+lpszDomain]; lpszDomain
0x1400e1fea  lea     rax, [rbp+57h+hObject]
0x1400e1fee  mov     [rsp+100h+PrivilegesToDelete], rax; phToken
0x1400e1ff3  mov     dword ptr [rsp+100h+pCount], r12d; dwLogonProvider
0x1400e1ff8  mov     r9d, 5; dwLogonType
0x1400e1ffe  xor     r8d, r8d; lpszPassword
0x1400e2001  mov     rcx, r15; lpszUsername
0x1400e2004  call    cs:__imp_LogonUserW
0x1400e200a  mov     rcx, [rbp+5Fh]; this
0x1400e200e  test    eax, eax
0x1400e2010  jz      loc_1400E2109
0x1400e2016  jmp     loc_1400E1EAF
0x1400e201b  mov     rsi, [rbp+57h+hObject]
0x1400e201f  lea     rax, [rsi-1]
0x1400e2023  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e2027  ja      short loc_1400E2042
0x1400e2029  call    cs:__imp_GetLastError
0x1400e202f  mov     ebx, eax
0x1400e2031  mov     rcx, rsi; hObject
0x1400e2034  call    cs:__imp_CloseHandle
0x1400e203a  mov     ecx, ebx; dwErrCode
0x1400e203c  call    cs:__imp_SetLastError
0x1400e2042  mov     [rbp+57h+hObject], r12
0x1400e2046  cmp     qword ptr [rdi+18h], 7
0x1400e204b  jbe     short loc_1400E2050
0x1400e204d  mov     rdi, [rdi]
0x1400e2050  lea     rax, [rbp+57h+hObject]
0x1400e2054  mov     [rsp+100h+PrivilegesToDelete], rax; phToken
0x1400e2059  mov     dword ptr [rsp+100h+pCount], r12d; dwLogonProvider
0x1400e205e  mov     r9d, 2; dwLogonType
0x1400e2064  lea     r8, szPassword; lpszPassword
0x1400e206b  lea     rdx, szDomain; "."
0x1400e2072  mov     rcx, rdi; lpszUsername
0x1400e2075  call    cs:__imp_LogonUserW
0x1400e207b  mov     rcx, [rbp+5Fh]; this
0x1400e207f  test    eax, eax
0x1400e2081  jz      loc_1400E211B
0x1400e2087  jmp     loc_1400E1EAF
0x1400e208c  mov     rbx, [rbp+57h+hObject]
0x1400e2090  mov     [r14], rbx
  ... truncated ...
```
