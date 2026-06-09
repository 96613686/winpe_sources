# CUserConfig::UpdateConfig(IUserName *,_GUID *)

- ea: `0x18006c290`
- end: `0x18006c801`
- name: `?UpdateConfig@CUserConfig@@UEAAJPEAUIUserName@@PEAU_GUID@@@Z`
- size: `1393`
- prototype: `int(CUserConfig *__hidden this, struct IUserName *, struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800127b0`
- `0x1800148d0`
- `0x180024d80`
- `0x180027a94`
- `0x18002869c`
- `0x1800321f0`
- `0x18006bed8`
- `0x18006c290`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c46d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c42b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c42b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c5ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c3aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c3aa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c3d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c5e3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c3d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c5e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c554`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c66c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c785`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c554`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c66c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c785`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c6be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c702`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c6be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c702`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18006c421`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18006c421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c7be`
- `logoncli!DsGetDcNameW` at `0x18006c49a`
- `logoncli!DsGetDcNameW` at `0x18006c4d3`
- `logoncli!DsGetDcNameW` at `0x18006c49a`
- `logoncli!DsGetDcNameW` at `0x18006c4d3`
- `netutils!NetApiBufferFree` at `0x18006c79e`
- `netutils!NetApiBufferFree` at `0x18006c79e`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006c6d7`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006c77a`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006c6d7`
- `REGAPI!RegDefaultUserConfigQueryW` at `0x18006c77a`

## string_xrefs

- `0x18006c544`: `StringCchCopy failed: 0x%x in %s`
- `0x18006c3fe`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006c615`: `ImpersonateLoggedOnUser failed: 0x%x in %s`
- `0x18006c2e3`: `CUserConfig::UpdateConfig`
- `0x18006c4ec`: `CUserConfig::UpdateConfig`
- `0x18006c53a`: `CUserConfig::UpdateConfig`
- `0x18006c565`: `CUserConfig::UpdateConfig`
- `0x18006c60b`: `CUserConfig::UpdateConfig`
- `0x18006c67d`: `CUserConfig::UpdateConfig`
- `0x18006c2ed`: `UpdateConfig for user`
- `0x18006c392`: `Loading user config for user %ws\%ws, ignore user config error is %s`
- `0x18006c3c7`: `pUserName->DuplicateTokenInPid failed: 0x%x in %s`
- `0x18006c443`: `GetComputerNameW failed: 0x%x in %s`
- `0x18006c5cf`: `LoadConfigFromDC 1 failed with 0x%08x - will retry`
- `0x18006c65b`: `LoadConfigFromDC 2 failed with 0x%08x`
- `0x18006c6b0`: `LoadConfig failed, load default User Configuration from server %ws registry`
- `0x18006c6e8`: `RegDefaultUserConfigQuery failed with 0x%08x`
- `0x18006c710`: `RegDefaultUserConfigQuery returned with 0x%08x, took %d ms`
- `0x18006c753`: `LoadConfig failed, use default User Configuration from local registry`

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
  const char *v40[7]; // [rsp+70h] [rbp-69h] BYREF
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
  CGenericTrace::CGenericTrace((CGenericTrace *)v40, 4, "UpdateConfig for user", "CUserConfig::UpdateConfig");
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
  CGenericTrace::~CGenericTrace(v40);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hToken);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006c290  mov     [rsp-8+arg_10], rbx
0x18006c295  push    rbp
0x18006c296  push    rsi
0x18006c297  push    rdi
0x18006c298  push    r12
0x18006c29a  push    r13
0x18006c29c  push    r14
0x18006c29e  push    r15
0x18006c2a0  lea     rbp, [rsp-27h]
0x18006c2a5  sub     rsp, 100h
0x18006c2ac  mov     rax, cs:__security_cookie
0x18006c2b3  xor     rax, rsp
0x18006c2b6  mov     [rbp+57h+var_40], rax
0x18006c2ba  mov     rbx, r8
0x18006c2bd  mov     rdi, rdx
0x18006c2c0  mov     r15, rcx
0x18006c2c3  mov     [rbp+57h+var_C8], rcx
0x18006c2c7  xor     esi, esi
0x18006c2c9  mov     [rsp+130h+nSize], esi
0x18006c2cd  mov     [rsp+130h+var_D8], rsi
0x18006c2d2  mov     [rsp+130h+pv], rsi
0x18006c2d7  mov     [rsp+130h+DomainName], rsi
0x18006c2dc  mov     [rbp+57h+hToken], rsi
0x18006c2e0  mov     r14d, esi
0x18006c2e3  lea     r12, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c2ea  mov     r9, r12; char *
0x18006c2ed  lea     r8, aUpdateconfigFo_0; "UpdateConfig for user"
0x18006c2f4  lea     edx, [rsi+4]; unsigned int
0x18006c2f7  lea     rcx, [rbp+57h+var_C0]; this
0x18006c2fb  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18006c300  nop
0x18006c301  mov     rcx, rbx; struct _GUID *
0x18006c304  call    ?IsIgnoreRegUserConfigError@CUserConfig@@CAHPEAU_GUID@@@Z; CUserConfig::IsIgnoreRegUserConfigError(_GUID *)
0x18006c309  mov     r13d, eax
0x18006c30c  mov     rcx, [rdi]
0x18006c30f  mov     rax, [rcx+28h]
0x18006c313  lea     rdx, [rsp+130h+pv]
0x18006c318  mov     rcx, rdi
0x18006c31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c320  mov     ebx, eax
0x18006c322  test    eax, eax
0x18006c324  jns     short loc_18006C342
0x18006c326  lea     rdx, aGetuserstrFail; "GetUserStr failed: 0x%x in %s"
0x18006c32d  mov     r8d, eax
0x18006c330  mov     r9, r12
0x18006c333  mov     ecx, 8; int
0x18006c338  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c33d  jmp     loc_18006C740
0x18006c342  mov     rax, [rdi]
0x18006c345  lea     rdx, [rsp+130h+DomainName]
0x18006c34a  mov     rcx, rdi
0x18006c34d  mov     rax, [rax+30h]
0x18006c351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c356  mov     ebx, eax
0x18006c358  test    eax, eax
0x18006c35a  jns     short loc_18006C365
0x18006c35c  lea     rdx, aGetdomainstrFa; "GetDomainStr failed: 0x%x in %s"
0x18006c363  jmp     short loc_18006C32D
0x18006c365  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006c36c  jz      short loc_18006C3A3
0x18006c36e  lea     rcx, aFalse; "FALSE"
0x18006c375  lea     rax, aTrue; "TRUE"
0x18006c37c  test    r13d, r13d
0x18006c37f  cmovz   rax, rcx
0x18006c383  mov     qword ptr [rsp+130h+Flags], rax
0x18006c388  mov     r9, [rsp+130h+pv]
0x18006c38d  mov     r8, [rsp+130h+DomainName]
0x18006c392  lea     rdx, aLoadingUserCon; "Loading user config for user %ws\\%ws, "...
0x18006c399  mov     ecx, 2; int
0x18006c39e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c3a3  mov     rax, [rdi]
0x18006c3a6  mov     rbx, [rax+50h]
0x18006c3aa  call    cs:__imp_GetCurrentProcessId
0x18006c3b0  lea     r8, [rbp+57h+hToken]
0x18006c3b4  mov     edx, eax
0x18006c3b6  mov     rcx, rdi
0x18006c3b9  mov     rax, rbx
0x18006c3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c3c1  mov     ebx, eax
0x18006c3c3  test    eax, eax
0x18006c3c5  jns     short loc_18006C3D3
0x18006c3c7  lea     rdx, aPusernameDupli; "pUserName->DuplicateTokenInPid failed: "...
0x18006c3ce  jmp     loc_18006C32D
0x18006c3d3  mov     rcx, [rbp+57h+hToken]; hToken
0x18006c3d7  call    cs:__imp_ImpersonateLoggedOnUser
0x18006c3dd  mov     edi, 80070000h
0x18006c3e2  test    eax, eax
0x18006c3e4  jnz     short loc_18006C40A
0x18006c3e6  call    cs:__imp_GetLastError
0x18006c3ec  mov     ebx, eax
0x18006c3ee  test    eax, eax
0x18006c3f0  jle     short loc_18006C3F7
0x18006c3f2  movzx   ebx, ax
0x18006c3f5  or      ebx, edi
0x18006c3f7  test    ebx, ebx
0x18006c3f9  jns     short loc_18006C40A
0x18006c3fb  mov     r8d, ebx
0x18006c3fe  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006c405  jmp     loc_18006C330
0x18006c40a  mov     r14d, 1
0x18006c410  mov     [rsp+130h+nSize], 10h
0x18006c418  lea     rdx, [rsp+130h+nSize]; nSize
0x18006c41d  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18006c421  call    cs:__imp_GetComputerNameW
0x18006c427  test    eax, eax
0x18006c429  jnz     short loc_18006C44F
0x18006c42b  call    cs:__imp_GetLastError
0x18006c431  mov     ebx, eax
0x18006c433  test    eax, eax
0x18006c435  jle     short loc_18006C43C
0x18006c437  movzx   ebx, ax
0x18006c43a  or      ebx, edi
0x18006c43c  test    ebx, ebx
0x18006c43e  jns     short loc_18006C44F
0x18006c440  mov     r8d, ebx
0x18006c443  lea     rdx, aGetcomputernam_0; "GetComputerNameW failed: 0x%x in %s"
0x18006c44a  jmp     loc_18006C330
0x18006c44f  mov     r12d, esi
0x18006c452  mov     rdx, [rsp+130h+DomainName]
0x18006c457  test    rdx, rdx
0x18006c45a  jz      loc_18006C51B
0x18006c460  cmp     [rdx], si
0x18006c463  jz      loc_18006C51B
0x18006c469  lea     rcx, [rbp+57h+Buffer]
0x18006c46d  call    cs:__imp__o__wcsicmp
0x18006c473  test    eax, eax
0x18006c475  jz      loc_18006C51B
0x18006c47b  lea     rax, [rsp+130h+var_D8]
0x18006c480  mov     [rsp+130h+DomainControllerInfo], rax; DomainControllerInfo
0x18006c485  mov     [rsp+130h+Flags], 40000000h; Flags
0x18006c48d  xor     r9d, r9d; SiteName
0x18006c490  xor     r8d, r8d; DomainGuid
0x18006c493  mov     rdx, [rsp+130h+DomainName]; DomainName
0x18006c498  xor     ecx, ecx; ComputerName
0x18006c49a  call    cs:__imp_DsGetDcNameW
0x18006c4a0  test    eax, eax
0x18006c4a2  jz      short loc_18006C50E
0x18006c4a4  mov     r8d, eax
0x18006c4a7  lea     rdx, aDsgetdcnameFai; "DsGetDcName failed with 0x%08x for DS_R"...
0x18006c4ae  mov     ecx, 4; int
0x18006c4b3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c4b8  lea     rax, [rsp+130h+var_D8]
0x18006c4bd  mov     [rsp+130h+DomainControllerInfo], rax; DomainControllerInfo
0x18006c4c2  mov     [rsp+130h+Flags], esi; Flags
0x18006c4c6  xor     r9d, r9d; SiteName
0x18006c4c9  xor     r8d, r8d; DomainGuid
0x18006c4cc  mov     rdx, [rsp+130h+DomainName]; DomainName
0x18006c4d1  xor     ecx, ecx; ComputerName
0x18006c4d3  call    cs:__imp_DsGetDcNameW
0x18006c4d9  test    eax, eax
0x18006c4db  jz      short loc_18006C50E
0x18006c4dd  jg      short loc_18006C4E3
0x18006c4df  mov     ebx, eax
0x18006c4e1  jmp     short loc_18006C4E8
0x18006c4e3  movzx   ebx, ax
0x18006c4e6  or      ebx, edi
0x18006c4e8  test    ebx, ebx
0x18006c4ea  jns     short loc_18006C554
0x18006c4ec  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c4f3  mov     r8d, ebx
0x18006c4f6  lea     rdx, aDsgetdcname1Fa; "DsGetDcName 1 failed: 0x%x in %s"
0x18006c4fd  mov     ecx, 8; int
0x18006c502  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c507  xor     esi, esi
0x18006c509  jmp     loc_18006C740
0x18006c50e  mov     rax, [rsp+130h+var_D8]
0x18006c513  mov     rsi, [rax]
0x18006c516  mov     r12d, r14d
0x18006c519  jmp     short loc_18006C554
0x18006c51b  mov     [rbp+57h+var_88], 5C005Ch
0x18006c522  lea     r8, [rbp+57h+Buffer]; unsigned __int16 *
0x18006c526  mov     edx, 10h; unsigned __int64
0x18006c52b  lea     rcx, [rbp+57h+var_84]; unsigned __int16 *
0x18006c52f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006c534  mov     ebx, eax
0x18006c536  test    eax, eax
0x18006c538  jns     short loc_18006C550
0x18006c53a  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c541  mov     r8d, eax
0x18006c544  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18006c54b  jmp     loc_18006C333
0x18006c550  lea     rsi, [rbp+57h+var_88]
0x18006c554  call    cs:__imp_RevertToSelf
0x18006c55a  test    eax, eax
0x18006c55c  jnz     short loc_18006C585
0x18006c55e  mov     edi, 80070005h
0x18006c563  mov     ebx, edi
0x18006c565  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c56c  mov     r8d, edi
0x18006c56f  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x18006c576  lea     ecx, [rax+8]; int
0x18006c579  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c57e  xor     esi, esi
0x18006c580  jmp     loc_18006C745
0x18006c585  add     r15, 640h
0x18006c58c  lea     rax, [rsp+130h+nSize]
0x18006c591  mov     [rsp+130h+var_F8], rax; unsigned int *
0x18006c596  mov     [rsp+130h+DomainControllerInfo], r15; struct _USERCONFIGW *
0x18006c59b  mov     rax, [rsp+130h+pv]
0x18006c5a0  mov     qword ptr [rsp+130h+Flags], rax; unsigned __int16 *
0x18006c5a5  mov     r9, rsi; unsigned __int16 *
0x18006c5a8  mov     r8, [rsp+130h+DomainName]; unsigned __int16 *
0x18006c5ad  mov     edx, r12d; int
0x18006c5b0  call    ?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z; CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)
0x18006c5b5  mov     edi, eax
0x18006c5b7  mov     r8d, 5
0x18006c5bd  cmp     eax, r8d
0x18006c5c0  jnz     loc_18006C69F
0x18006c5c6  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006c5cd  jz      short loc_18006C5DF
0x18006c5cf  lea     rdx, aLoadconfigfrom_0; "LoadConfigFromDC 1 failed with 0x%08x -"...
0x18006c5d6  lea     ecx, [r8-3]; int
0x18006c5da  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c5df  mov     rcx, [rbp+57h+hToken]; hToken
0x18006c5e3  call    cs:__imp_ImpersonateLoggedOnUser
0x18006c5e9  test    eax, eax
0x18006c5eb  jnz     short loc_18006C602
0x18006c5ed  call    cs:__imp_GetLastError
0x18006c5f3  mov     ebx, eax
0x18006c5f5  test    eax, eax
0x18006c5f7  jle     short loc_18006C602
0x18006c5f9  movzx   ebx, ax
0x18006c5fc  or      ebx, 80070000h
0x18006c602  test    ebx, ebx
0x18006c604  jns     short loc_18006C629
0x18006c606  xor     esi, esi
0x18006c608  mov     r14d, esi
0x18006c60b  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c612  mov     r8d, ebx
0x18006c615  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser failed: 0x%x in"...
0x18006c61c  lea     ecx, [rsi+8]; int
0x18006c61f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c624  jmp     loc_18006C73C
0x18006c629  lea     rax, [rsp+130h+nSize]
0x18006c62e  mov     [rsp+130h+var_F8], rax; unsigned int *
0x18006c633  mov     [rsp+130h+DomainControllerInfo], r15; struct _USERCONFIGW *
0x18006c638  mov     rax, [rsp+130h+pv]
0x18006c63d  mov     qword ptr [rsp+130h+Flags], rax; unsigned __int16 *
0x18006c642  mov     r9, rsi; unsigned __int16 *
0x18006c645  mov     r8, [rsp+130h+DomainName]; unsigned __int16 *
0x18006c64a  mov     edx, r12d; int
0x18006c64d  call    ?LoadConfigFromDC@CUserConfig@@AEAAKHPEAG00PEAU_USERCONFIGW@@KPEAK@Z; CUserConfig::LoadConfigFromDC(int,ushort *,ushort *,ushort *,_USERCONFIGW *,ulong,ulong *)
0x18006c652  mov     edi, eax
0x18006c654  test    eax, eax
0x18006c656  jz      short loc_18006C66C
0x18006c658  mov     r8d, ebx
0x18006c65b  lea     rdx, aLoadconfigfrom; "LoadConfigFromDC 2 failed with 0x%08x"
0x18006c662  mov     ecx, 4; int
0x18006c667  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c66c  call    cs:__imp_RevertToSelf
0x18006c672  test    eax, eax
0x18006c674  jnz     short loc_18006C69F
0x18006c676  mov     edi, 80070005h
0x18006c67b  mov     ebx, edi
0x18006c67d  lea     r9, aCuserconfigUpd; "CUserConfig::UpdateConfig"
0x18006c684  mov     r8d, edi
0x18006c687  lea     rdx, aReverttoselfFa; "RevertToSelf failed: 0x%x in %s"
0x18006c68e  lea     ecx, [rax+8]; int
0x18006c691  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c696  mov     r15, [rbp+57h+var_C8]
0x18006c69a  jmp     loc_18006C57E
0x18006c69f  cmp     edi, 2
0x18006c6a2  jnz     short loc_18006C722
0x18006c6a4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006c6ab  jz      short loc_18006C6BE
0x18006c6ad  mov     r8, rsi
0x18006c6b0  lea     rdx, aLoadconfigFail; "LoadConfig failed, load default User Co"...
0x18006c6b7  mov     ecx, edi; int
0x18006c6b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c6be  call    cs:__imp_GetTickCount
0x18006c6c4  mov     ebx, eax
0x18006c6c6  lea     r9, [rsp+130h+nSize]
0x18006c6cb  mov     r8d, 9E8h
0x18006c6d1  mov     rdx, r15
0x18006c6d4  mov     rcx, rsi
0x18006c6d7  call    cs:__imp_RegDefaultUserConfigQueryW
0x18006c6dd  mov     edi, eax
0x18006c6df  xor     esi, esi
0x18006c6e1  test    eax, eax
0x18006c6e3  jz      short loc_18006C6F9
0x18006c6e5  mov     r8d, eax
0x18006c6e8  lea     rdx, aRegdefaultuser_1; "RegDefaultUserConfigQuery failed with 0"...
0x18006c6ef  lea     ecx, [rsi+8]; int
0x18006c6f2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c6f7  jmp     short loc_18006C724
0x18006c6f9  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006c700  jz      short loc_18006C728
0x18006c702  call    cs:__imp_GetTickCount
0x18006c708  sub     eax, ebx
0x18006c70a  mov     r9d, eax
0x18006c70d  xor     r8d, r8d
0x18006c710  lea     rdx, aRegdefaultuser_0; "RegDefaultUserConfigQuery returned with"...
0x18006c717  lea     ecx, [r8+2]; int
0x18006c71b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006c720  jmp     short loc_18006C724
0x18006c722  xor     esi, esi
0x18006c724  test    edi, edi
0x18006c726  jg      short loc_18006C72C
0x18006c728  mov     ebx, edi
0x18006c72a  jmp     short loc_18006C735
  ... truncated ...
```
