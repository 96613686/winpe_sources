# CUserConfig::UpdateConfig(IUserName *,_GUID *)

- ea: `0x18006f6a0`
- end: `0x18006fc8e`
- name: `?UpdateConfig@CUserConfig@@UEAAJPEAUIUserName@@PEAU_GUID@@@Z`
- size: `1518`
- prototype: `int(CUserConfig *__hidden this, struct IUserName *, struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009940`
- `0x180012d10`
- `0x180015020`
- `0x1800260ec`
- `0x180028ed8`
- `0x180029bc4`
- `0x180033f60`
- `0x18006f2ac`
- `0x18006f6a0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f89b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006f89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f7ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006f7ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006fa29`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006f7ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006fa29`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006f994`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fabe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fbf9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006f994`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fabe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006fbf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006fb1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006fb6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006fb1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006fb6a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18006f843`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18006f843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fc2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fc44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fc2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fc44`
- `logoncli!DsGetDcNameW` at `0x18006f8ce`
- `logoncli!DsGetDcNameW` at `0x18006f90d`
- `logoncli!DsGetDcNameW` at `0x18006f8ce`
- `logoncli!DsGetDcNameW` at `0x18006f90d`
- `netutils!NetApiBufferFree` at `0x18006fc18`
- `netutils!NetApiBufferFree` at `0x18006fc18`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006fb39`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006fbe8`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006fb39`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006fbe8`

## string_xrefs

- `0x18006f984`: `StringCchCopy failed: 0x%x in %s`
- `0x18006f820`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006fa67`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006f6f3`: `CUserConfig::UpdateConfig`
- `0x18006f92c`: `CUserConfig::UpdateConfig`
- `0x18006f97a`: `CUserConfig::UpdateConfig`
- `0x18006f9ab`: `CUserConfig::UpdateConfig`
- `0x18006fa5d`: `CUserConfig::UpdateConfig`
- `0x18006fad5`: `CUserConfig::UpdateConfig`
- `0x18006f6fd`: `UpdateConfig for user`
- `0x18006f7a2`: `Loading user config for user %ws\%ws, ignore user config error is %s`
- `0x18006f7dd`: `pUserName->DuplicateTokenInPid failed: 0x%x in %s`
- `0x18006f871`: `GetComputerNameW failed: 0x%x in %s`
- `0x18006fa15`: `LoadConfigFromDC 1 failed with 0x%08x - will retry`
- `0x18006faad`: `LoadConfigFromDC 2 failed with 0x%08x`
- `0x18006fb0c`: `LoadConfig failed, load default User Configuration from server %ws registry`
- `0x18006fb50`: `RegDefaultUserConfigQuery failed with 0x%08x`
- `0x18006fb7e`: `RegDefaultUserConfigQuery returned with 0x%08x, took %d ms`
- `0x18006fbc1`: `LoadConfig failed, use default User Configuration from local registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserConfig::UpdateConfig(CUserConfig *this, struct IUserName *a2, struct _GUID *a3)
{
  CUserConfig *v5; // r15
  int v6; // r14d
  int IsIgnoreRegUserConfigError; // r13d
  int v8; // eax
  signed int v9; // ebx
  const char *v10; // rdx
  __int64 v11; // r8
  const char *v12; // rax
  __int64 (__fastcall *v13)(struct IUserName *, _QWORD, HANDLE *); // rbx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  signed int v16; // eax
  int v17; // r12d
  DWORD DcNameW; // eax
  signed int v19; // eax
  unsigned __int16 *DomainControllerName; // rsi
  int v21; // eax
  CUserConfig *v22; // rcx
  struct _USERCONFIGW *v23; // r15
  int v24; // edi
  CUserConfig *v25; // rcx
  signed int v26; // eax
  DWORD TickCount; // ebx
  int v28; // eax
  DWORD v29; // eax
  BOOL v30; // eax
  unsigned int v32; // [rsp+30h] [rbp-A9h]
  unsigned int v33; // [rsp+30h] [rbp-A9h]
  DWORD nSize; // [rsp+40h] [rbp-99h] BYREF
  LPCWSTR DomainName; // [rsp+48h] [rbp-91h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-89h] BYREF
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+58h] [rbp-81h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp-79h] BYREF
  CUserConfig *v39; // [rsp+68h] [rbp-71h]
  _BYTE v40[56]; // [rsp+70h] [rbp-69h] BYREF
  int v41; // [rsp+A8h] [rbp-31h] BYREF
  unsigned __int16 v42[18]; // [rsp+ACh] [rbp-2Dh] BYREF
  WCHAR Buffer[16]; // [rsp+D0h] [rbp-9h] BYREF

  v5 = this;
  v39 = this;
  nSize = 0;
  DomainControllerInfo = 0;
  pv = 0;
  DomainName = 0;
  hToken = 0;
  v6 = 0;
  CGenericTrace::CGenericTrace((CGenericTrace *)v40, 4u, "UpdateConfig for user", "CUserConfig::UpdateConfig");
  IsIgnoreRegUserConfigError = CUserConfig::IsIgnoreRegUserConfigError(a3);
  v8 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IUserName *, LPCWSTR *))(*(_QWORD *)a2 + 48LL))(a2, &DomainName);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = "GetDomainStr failed: 0x%x in %s";
      goto LABEL_3;
    }
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      v12 = "TRUE";
      if ( !IsIgnoreRegUserConfigError )
        v12 = "FALSE";
      _DbgPrintMessage(2, "Loading user config for user %ws\\%ws, ignore user config error is %s", DomainName, pv, v12);
    }
    v13 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, HANDLE *))(*(_QWORD *)a2 + 80LL);
    CurrentProcessId = GetCurrentProcessId();
    v8 = v13(a2, CurrentProcessId, &hToken);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = "pUserName->DuplicateTokenInPid failed: 0x%x in %s";
      goto LABEL_3;
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 < 0 )
      {
        v11 = (unsigned int)v9;
        v10 = "ImpersonateLoggedOnUser failed: 0x%x in %s";
        goto LABEL_4;
      }
    }
    v6 = 1;
    nSize = 16;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      v16 = GetLastError();
      v9 = v16;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      if ( v9 < 0 )
      {
        v11 = (unsigned int)v9;
        v10 = "GetComputerNameW failed: 0x%x in %s";
        goto LABEL_4;
      }
    }
    v17 = 0;
    if ( DomainName && *DomainName && (unsigned int)_o__wcsicmp(Buffer, DomainName) )
    {
      DcNameW = DsGetDcNameW(0, DomainName, 0, 0, 0x40000000u, &DomainControllerInfo);
      if ( DcNameW )
      {
        _DbgPrintMessage(4, "DsGetDcName failed with 0x%08x for DS_RETURN_DNS_NAME - will retry", DcNameW);
        v19 = DsGetDcNameW(0, DomainName, 0, 0, 0, &DomainControllerInfo);
        if ( v19 )
        {
          if ( v19 > 0 )
            v9 = (unsigned __int16)v19 | 0x80070000;
          else
            v9 = v19;
          _DbgPrintMessage(8, "DsGetDcName 1 failed: 0x%x in %s", v9, "CUserConfig::UpdateConfig");
          goto LABEL_62;
        }
      }
      DomainControllerName = DomainControllerInfo->DomainControllerName;
      v17 = 1;
    }
    else
    {
      v41 = 6029404;
      v21 = StringCchCopyW(v42, 0x10u, Buffer);
      v9 = v21;
      if ( v21 < 0 )
      {
        _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", (unsigned int)v21, "CUserConfig::UpdateConfig");
        goto LABEL_62;
      }
      DomainControllerName = (unsigned __int16 *)&v41;
    }
    if ( !RevertToSelf() )
    {
      v9 = -2147024891;
      _DbgPrintMessage(8, "RevertToSelf failed: 0x%x in %s", -2147024891, "CUserConfig::UpdateConfig");
      goto LABEL_62;
    }
    v23 = (CUserConfig *)((char *)v5 + 1600);
    v24 = CUserConfig::LoadConfigFromDC(
            v22,
            v17,
            (unsigned __int16 *)DomainName,
            DomainControllerName,
            (unsigned __int16 *)pv,
            v23,
            v32,
            &nSize);
    if ( v24 == 5 )
    {
      if ( (g_DebugTraceComponent & 4) != 0 )
        _DbgPrintMessage(2, "LoadConfigFromDC 1 failed with 0x%08x - will retry", 5);
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        v26 = GetLastError();
        v9 = v26;
        if ( v26 > 0 )
          v9 = (unsigned __int16)v26 | 0x80070000;
      }
      if ( v9 < 0 )
      {
        v6 = 0;
        _DbgPrintMessage(8, "ImpersonateLoggedOnUser failed: 0x%x in %s", v9, "CUserConfig::UpdateConfig");
LABEL_61:
        v5 = v39;
        goto LABEL_62;
      }
      v24 = CUserConfig::LoadConfigFromDC(
              v25,
              v17,
              (unsigned __int16 *)DomainName,
              DomainControllerName,
              (unsigned __int16 *)pv,
              v23,
              v33,
              &nSize);
      if ( v24 )
        _DbgPrintMessage(4, "LoadConfigFromDC 2 failed with 0x%08x", v9);
      if ( !RevertToSelf() )
      {
        v9 = -2147024891;
        _DbgPrintMessage(8, "RevertToSelf failed: 0x%x in %s", -2147024891, "CUserConfig::UpdateConfig");
        v5 = v39;
        goto LABEL_62;
      }
    }
    if ( v24 == 2 )
    {
      if ( (g_DebugTraceComponent & 4) != 0 )
        _DbgPrintMessage(
          2,
          "LoadConfig failed, load default User Configuration from server %ws registry",
          DomainControllerName);
      TickCount = GetTickCount();
      v28 = RegDefaultUserConfigQueryW(DomainControllerName, v23, 2536, &nSize);
      v24 = v28;
      if ( v28 )
      {
        _DbgPrintMessage(8, "RegDefaultUserConfigQuery failed with 0x%08x", v28);
      }
      else
      {
        if ( (g_DebugTraceComponent & 4) == 0 )
          goto LABEL_58;
        v29 = GetTickCount();
        _DbgPrintMessage(2, "RegDefaultUserConfigQuery returned with 0x%08x, took %d ms", 0, v29 - TickCount);
      }
    }
    if ( v24 > 0 )
    {
      v9 = (unsigned __int16)v24 | 0x80070000;
LABEL_60:
      v6 = 0;
      if ( v9 >= 0 )
        goto LABEL_70;
      goto LABEL_61;
    }
LABEL_58:
    v9 = v24;
    goto LABEL_60;
  }
  v10 = "GetUserStr failed: 0x%x in %s";
LABEL_3:
  v11 = (unsigned int)v8;
LABEL_4:
  _DbgPrintMessage(8, v10, v11, "CUserConfig::UpdateConfig");
LABEL_62:
  if ( IsIgnoreRegUserConfigError )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "LoadConfig failed, use default User Configuration from local registry");
    v9 = 0;
    RegDefaultUserConfigQueryW(0, (char *)v5 + 1600, 2536, &nSize);
  }
  if ( v6 )
  {
    v30 = RevertToSelf();
    if ( v9 >= 0 && !v30 )
      v9 = -2147024891;
  }
LABEL_70:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( pv )
    CoTaskMemFree(pv);
  if ( DomainName )
    CoTaskMemFree((LPVOID)DomainName);
  CGenericTrace::~CGenericTrace((CGenericTrace *)v40);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hToken);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006f6a0  mov     [rsp-8+arg_10], rbx
0x18006f6a5  push    rbp
0x18006f6a6  push    rsi
0x18006f6a7  push    rdi
0x18006f6a8  push    r12
0x18006f6aa  push    r13
0x18006f6ac  push    r14
0x18006f6ae  push    r15
0x18006f6b0  lea     rbp, [rsp-27h]
0x18006f6b5  sub     rsp, 100h
0x18006f6bc  mov     rax, cs:__security_cookie
0x18006f6c3  xor     rax, rsp
0x18006f6c6  mov     [rbp+57h+var_40], rax
0x18006f6ca  mov     rbx, r8
0x18006f6cd  mov     rdi, rdx
0x18006f6d0  mov     r15, rcx
0x18006f6d3  mov     [rbp+57h+var_C8], rcx
0x18006f6d7  xor     esi, esi
0x18006f6d9  mov     [rsp+130h+nSize], esi
0x18006f6dd  mov     [rsp+130h+var_D8], rsi
0x18006f6e2  mov     [rsp+130h+pv], rsi
0x18006f6e7  mov     [rsp+130h+DomainName], rsi
0x18006f6ec  mov     [rbp+57h+hToken], rsi
0x18006f6f0  mov     r14d, esi
0x18006f6f3  lea     r12, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006f6fa  mov     r9, r12; char *
0x18006f6fd  lea     r8, aUpdateconfigFo_0; "UpdateConfig for user"
0x18006f704  lea     edx, [rsi+4]; unsigned int
0x18006f707  lea     rcx, [rbp+57h+var_C0]; this
0x18006f70b  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18006f710  nop
0x18006f711  mov     rcx, rbx; struct _GUID *
0x18006f714  call    ?IsIgnoreRegUserConfigError@CUserConfig@@CAHPEAU_GUID@@@Z; CUserConfig::IsIgnoreRegUserConfigError(_GUID *)
0x18006f719  mov     r13d, eax
0x18006f71c  mov     rcx, [rdi]
0x18006f71f  mov     rax, [rcx+28h]
0x18006f723  lea     rdx, [rsp+130h+pv]
0x18006f728  mov     rcx, rdi
0x18006f72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f730  mov     ebx, eax
0x18006f732  test    eax, eax
0x18006f734  jns     short loc_18006F752
0x18006f736  lea     rdx, aGetuserstrFail; "GetUserStr failed: 0x%x in %s"
0x18006f73d  mov     r8d, eax
0x18006f740  mov     r9, r12
0x18006f743  mov     ecx, 8; int
0x18006f748  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f74d  jmp     loc_18006FBAE
0x18006f752  mov     rax, [rdi]
0x18006f755  lea     rdx, [rsp+130h+DomainName]
0x18006f75a  mov     rcx, rdi
0x18006f75d  mov     rax, [rax+30h]
0x18006f761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f766  mov     ebx, eax
0x18006f768  test    eax, eax
0x18006f76a  jns     short loc_18006F775
0x18006f76c  lea     rdx, aGetdomainstrFa; "GetDomainStr failed: 0x%x in %s"
0x18006f773  jmp     short loc_18006F73D
0x18006f775  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006f77c  jz      short loc_18006F7B3
0x18006f77e  lea     rcx, aFalse; "FALSE"
0x18006f785  lea     rax, aTrue; "TRUE"
0x18006f78c  test    r13d, r13d
0x18006f78f  cmovz   rax, rcx
0x18006f793  mov     qword ptr [rsp+130h+Flags], rax
0x18006f798  mov     r9, [rsp+130h+pv]
0x18006f79d  mov     r8, [rsp+130h+DomainName]
0x18006f7a2  lea     rdx, aLoadingUserCon; "Loading user config for user %ws\\%ws, "...
0x18006f7a9  mov     ecx, 2; int
0x18006f7ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f7b3  mov     rax, [rdi]
0x18006f7b6  mov     rbx, [rax+50h]
0x18006f7ba  call    cs:__imp_GetCurrentProcessId
0x18006f7c1  nop     dword ptr [rax+rax+00h]
0x18006f7c6  lea     r8, [rbp+57h+hToken]
0x18006f7ca  mov     edx, eax
0x18006f7cc  mov     rcx, rdi
0x18006f7cf  mov     rax, rbx
0x18006f7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7d7  mov     ebx, eax
0x18006f7d9  test    eax, eax
0x18006f7db  jns     short loc_18006F7E9
0x18006f7dd  lea     rdx, aPusernameDupli; "pUserName->DuplicateTokenInPid failed: "...
0x18006f7e4  jmp     loc_18006F73D
0x18006f7e9  mov     rcx, [rbp+57h+hToken]; hToken
0x18006f7ed  call    cs:__imp_ImpersonateLoggedOnUser
0x18006f7f4  nop     dword ptr [rax+rax+00h]
0x18006f7f9  mov     edi, 80070000h
0x18006f7fe  test    eax, eax
0x18006f800  jnz     short loc_18006F82C
0x18006f802  call    cs:__imp_GetLastError
0x18006f809  nop     dword ptr [rax+rax+00h]
0x18006f80e  mov     ebx, eax
0x18006f810  test    eax, eax
0x18006f812  jle     short loc_18006F819
0x18006f814  movzx   ebx, ax
0x18006f817  or      ebx, edi
0x18006f819  test    ebx, ebx
0x18006f81b  jns     short loc_18006F82C
0x18006f81d  mov     r8d, ebx
0x18006f820  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006f827  jmp     loc_18006F740
0x18006f82c  mov     r14d, 1
0x18006f832  mov     [rsp+130h+nSize], 10h
0x18006f83a  lea     rdx, [rsp+130h+nSize]; nSize
0x18006f83f  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18006f843  call    cs:__imp_GetComputerNameW
0x18006f84a  nop     dword ptr [rax+rax+00h]
0x18006f84f  test    eax, eax
0x18006f851  jnz     short loc_18006F87D
0x18006f853  call    cs:__imp_GetLastError
0x18006f85a  nop     dword ptr [rax+rax+00h]
0x18006f85f  mov     ebx, eax
0x18006f861  test    eax, eax
0x18006f863  jle     short loc_18006F86A
0x18006f865  movzx   ebx, ax
0x18006f868  or      ebx, edi
0x18006f86a  test    ebx, ebx
0x18006f86c  jns     short loc_18006F87D
0x18006f86e  mov     r8d, ebx
0x18006f871  lea     rdx, aGetcomputernam_0; "GetComputerNameW failed: 0x%x in %s"
0x18006f878  jmp     loc_18006F740
0x18006f87d  mov     r12d, esi
0x18006f880  mov     rdx, [rsp+130h+DomainName]
0x18006f885  test    rdx, rdx
0x18006f888  jz      loc_18006F95B
0x18006f88e  cmp     [rdx], si
0x18006f891  jz      loc_18006F95B
0x18006f897  lea     rcx, [rbp+57h+Buffer]
0x18006f89b  call    cs:__imp__o__wcsicmp
0x18006f8a2  nop     dword ptr [rax+rax+00h]
0x18006f8a7  test    eax, eax
0x18006f8a9  jz      loc_18006F95B
0x18006f8af  lea     rax, [rsp+130h+var_D8]
0x18006f8b4  mov     [rsp+130h+DomainControllerInfo], rax; DomainControllerInfo
0x18006f8b9  mov     [rsp+130h+Flags], 40000000h; Flags
0x18006f8c1  xor     r9d, r9d; SiteName
0x18006f8c4  xor     r8d, r8d; DomainGuid
0x18006f8c7  mov     rdx, [rsp+130h+DomainName]; DomainName
0x18006f8cc  xor     ecx, ecx; ComputerName
0x18006f8ce  call    cs:__imp_DsGetDcNameW
0x18006f8d5  nop     dword ptr [rax+rax+00h]
0x18006f8da  test    eax, eax
0x18006f8dc  jz      short loc_18006F94E
0x18006f8de  mov     r8d, eax
0x18006f8e1  lea     rdx, aDsgetdcnameFai; "DsGetDcName failed with 0x%08x for DS_R"...
0x18006f8e8  mov     ecx, 4; int
0x18006f8ed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f8f2  lea     rax, [rsp+130h+var_D8]
0x18006f8f7  mov     [rsp+130h+DomainControllerInfo], rax; DomainControllerInfo
0x18006f8fc  mov     [rsp+130h+Flags], esi; Flags
0x18006f900  xor     r9d, r9d; SiteName
0x18006f903  xor     r8d, r8d; DomainGuid
0x18006f906  mov     rdx, [rsp+130h+DomainName]; DomainName
0x18006f90b  xor     ecx, ecx; ComputerName
0x18006f90d  call    cs:__imp_DsGetDcNameW
0x18006f914  nop     dword ptr [rax+rax+00h]
0x18006f919  test    eax, eax
0x18006f91b  jz      short loc_18006F94E
0x18006f91d  jg      short loc_18006F923
0x18006f91f  mov     ebx, eax
0x18006f921  jmp     short loc_18006F928
0x18006f923  movzx   ebx, ax
0x18006f926  or      ebx, edi
0x18006f928  test    ebx, ebx
0x18006f92a  jns     short loc_18006F994
0x18006f92c  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006f933  mov     r8d, ebx
0x18006f936  lea     rdx, aDsgetdcname1Fa; "DsGetDcName 1 failed: 0x%x in %s"
0x18006f93d  mov     ecx, 8; int
0x18006f942  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f947  xor     esi, esi
0x18006f949  jmp     loc_18006FBAE
0x18006f94e  mov     rax, [rsp+130h+var_D8]
0x18006f953  mov     rsi, [rax]
0x18006f956  mov     r12d, r14d
0x18006f959  jmp     short loc_18006F994
0x18006f95b  mov     [rbp+57h+var_88], 5C005Ch
0x18006f962  lea     r8, [rbp+57h+Buffer]; unsigned __int16 *
0x18006f966  mov     edx, 10h; unsigned __int64
0x18006f96b  lea     rcx, [rbp+57h+var_84]; unsigned __int16 *
0x18006f96f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f974  mov     ebx, eax
0x18006f976  test    eax, eax
0x18006f978  jns     short loc_18006F990
0x18006f97a  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006f981  mov     r8d, eax
0x18006f984  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18006f98b  jmp     loc_18006F743
0x18006f990  lea     rsi, [rbp+57h+var_88]
0x18006f994  call    cs:__imp_RevertToSelf
0x18006f99b  nop     dword ptr [rax+rax+00h]
0x18006f9a0  test    eax, eax
0x18006f9a2  jnz     short loc_18006F9CB
0x18006f9a4  mov     edi, 80070005h
0x18006f9a9  mov     ebx, edi
0x18006f9ab  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006f9b2  mov     r8d, edi
0x18006f9b5  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x18006f9bc  lea     ecx, [rax+8]; int
0x18006f9bf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f9c4  xor     esi, esi
0x18006f9c6  jmp     loc_18006FBB3
0x18006f9cb  add     r15, 640h
0x18006f9d2  lea     rax, [rsp+130h+nSize]
0x18006f9d7  mov     [rsp+130h+var_F8], rax; unsigned int *
0x18006f9dc  mov     [rsp+130h+DomainControllerInfo], r15; struct _USERCONFIGW *
0x18006f9e1  mov     rax, [rsp+130h+pv]
0x18006f9e6  mov     qword ptr [rsp+130h+Flags], rax; unsigned __int16 *
0x18006f9eb  mov     r9, rsi; unsigned __int16 *
0x18006f9ee  mov     r8, [rsp+130h+DomainName]; unsigned __int16 *
0x18006f9f3  mov     edx, r12d; int
0x18006f9f6  call    ?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z; CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)
0x18006f9fb  mov     edi, eax
0x18006f9fd  mov     r8d, 5
0x18006fa03  cmp     eax, r8d
0x18006fa06  jnz     loc_18006FAF7
0x18006fa0c  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006fa13  jz      short loc_18006FA25
0x18006fa15  lea     rdx, aLoadconfigfrom_0; "LoadConfigFromDC 1 failed with 0x%08x -"...
0x18006fa1c  lea     ecx, [r8-3]; int
0x18006fa20  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fa25  mov     rcx, [rbp+57h+hToken]; hToken
0x18006fa29  call    cs:__imp_ImpersonateLoggedOnUser
0x18006fa30  nop     dword ptr [rax+rax+00h]
0x18006fa35  test    eax, eax
0x18006fa37  jnz     short loc_18006FA54
0x18006fa39  call    cs:__imp_GetLastError
0x18006fa40  nop     dword ptr [rax+rax+00h]
0x18006fa45  mov     ebx, eax
0x18006fa47  test    eax, eax
0x18006fa49  jle     short loc_18006FA54
0x18006fa4b  movzx   ebx, ax
0x18006fa4e  or      ebx, 80070000h
0x18006fa54  test    ebx, ebx
0x18006fa56  jns     short loc_18006FA7B
0x18006fa58  xor     esi, esi
0x18006fa5a  mov     r14d, esi
0x18006fa5d  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006fa64  mov     r8d, ebx
0x18006fa67  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006fa6e  lea     ecx, [rsi+8]; int
0x18006fa71  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fa76  jmp     loc_18006FBAA
0x18006fa7b  lea     rax, [rsp+130h+nSize]
0x18006fa80  mov     [rsp+130h+var_F8], rax; unsigned int *
0x18006fa85  mov     [rsp+130h+DomainControllerInfo], r15; struct _USERCONFIGW *
0x18006fa8a  mov     rax, [rsp+130h+pv]
0x18006fa8f  mov     qword ptr [rsp+130h+Flags], rax; unsigned __int16 *
0x18006fa94  mov     r9, rsi; unsigned __int16 *
0x18006fa97  mov     r8, [rsp+130h+DomainName]; unsigned __int16 *
0x18006fa9c  mov     edx, r12d; int
0x18006fa9f  call    ?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z; CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)
0x18006faa4  mov     edi, eax
0x18006faa6  test    eax, eax
0x18006faa8  jz      short loc_18006FABE
0x18006faaa  mov     r8d, ebx
0x18006faad  lea     rdx, aLoadconfigfrom; "LoadConfigFromDC 2 failed with 0x%08x"
0x18006fab4  mov     ecx, 4; int
0x18006fab9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fabe  call    cs:__imp_RevertToSelf
0x18006fac5  nop     dword ptr [rax+rax+00h]
0x18006faca  test    eax, eax
0x18006facc  jnz     short loc_18006FAF7
0x18006face  mov     edi, 80070005h
0x18006fad3  mov     ebx, edi
0x18006fad5  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006fadc  mov     r8d, edi
0x18006fadf  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x18006fae6  lea     ecx, [rax+8]; int
0x18006fae9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006faee  mov     r15, [rbp+57h+var_C8]
0x18006faf2  jmp     loc_18006F9C4
0x18006faf7  cmp     edi, 2
0x18006fafa  jnz     loc_18006FB90
0x18006fb00  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006fb07  jz      short loc_18006FB1A
0x18006fb09  mov     r8, rsi
0x18006fb0c  lea     rdx, aLoadconfigFail; "LoadConfig failed, load default User Co"...
0x18006fb13  mov     ecx, edi; int
0x18006fb15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fb1a  call    cs:__imp_GetTickCount
0x18006fb21  nop     dword ptr [rax+rax+00h]
0x18006fb26  mov     ebx, eax
0x18006fb28  lea     r9, [rsp+130h+nSize]
0x18006fb2d  mov     r8d, 9E8h
0x18006fb33  mov     rdx, r15
0x18006fb36  mov     rcx, rsi
0x18006fb39  call    cs:__imp_RegDefaultUserConfigQueryW
0x18006fb40  nop     dword ptr [rax+rax+00h]
0x18006fb45  mov     edi, eax
0x18006fb47  xor     esi, esi
0x18006fb49  test    eax, eax
0x18006fb4b  jz      short loc_18006FB61
0x18006fb4d  mov     r8d, eax
0x18006fb50  lea     rdx, aRegdefaultuser_1; "RegDefaultUserConfigQuery failed with 0"...
0x18006fb57  lea     ecx, [rsi+8]; int
0x18006fb5a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fb5f  jmp     short loc_18006FB92
0x18006fb61  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
  ... truncated ...
```
