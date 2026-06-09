# CheckServiceAutoStarted

- ea: `0x180086c40`
- end: `0x180086e9e`
- name: `CheckServiceAutoStarted`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180086ea4`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x18001fed0`
- `0x180081a38`
- `0x180086820`
- `0x1800868ac`
- `0x180086988`
- `0x180086c40`
- `0x180090bc8`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e07`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180086dae`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180086dae`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180086d8b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180086d8b`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180086d31`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180086d31`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180086e6d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180086e6d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180086dfd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180086dfd`

## string_xrefs

- `0x180086dbc`: `C:\__w\1\s\src\Client\lib\util\ServiceUtil.cpp`
- `0x180086e1d`: `C:\__w\1\s\src\Client\lib\util\ServiceUtil.cpp`
- `0x180086e47`: `C:\__w\1\s\src\Client\lib\util\ServiceUtil.cpp`

## pseudocode

```c
__int64 CheckServiceAutoStarted()
{
  void *v0; // rdi
  int v1; // eax
  SC_HANDLE v2; // rbx
  unsigned int LastError; // esi
  __int64 v4; // rdx
  int ServiceConfig; // eax
  unsigned __int64 v6; // r9
  const char *v7; // r9
  __int64 v8; // rdx
  const char *v9; // r9
  unsigned int v10; // edx
  int v11; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-60h]
  SC_HANDLE hService; // [rsp+60h] [rbp-20h] BYREF
  DWORD pcbBytesNeeded[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_QWORD *)pcbBytesNeeded = 0;
  hService = 0;
  v0 = 0;
  v1 = OpenNamedService(L"BITS", 0x17u, &hService);
  v2 = hService;
  LastError = v1;
  if ( v1 < 0 )
  {
    v4 = 463;
LABEL_5:
    v6 = LastError;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\ServiceUtil.cpp",
      (const char *)v6,
      lpBinaryPathName);
    goto LABEL_25;
  }
  ServiceConfig = GetServiceConfig(hService, (struct _QUERY_SERVICE_CONFIGW **)pcbBytesNeeded);
  v0 = *(void **)pcbBytesNeeded;
  LastError = ServiceConfig;
  if ( ServiceConfig < 0 )
  {
    v4 = 466;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(*(_QWORD *)pcbBytesNeeded + 4LL) != 2 )
  {
    if ( *(_DWORD *)(*(_QWORD *)pcbBytesNeeded + 4LL) == 4 )
      WUTrace(0, 0, 32, 4, 0, L"%ws is disabled", L"BITS");
    if ( !ChangeServiceConfigW(v2, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v8 = 488;
LABEL_20:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v8,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\ServiceUtil.cpp",
                    v7);
      goto LABEL_25;
    }
    WUTrace(0, 0, 32, 4, 0, L"Changed %ws to auto-start", L"BITS");
  }
  LODWORD(hService) = 0;
  pcbBytesNeeded[0] = 0;
  if ( QueryServiceConfig2W(v2, 3u, (LPBYTE)&hService, 4u, pcbBytesNeeded) && !(_DWORD)hService )
  {
    LODWORD(hService) = 1;
    if ( ChangeServiceConfig2W(v2, 3u, &hService) )
      WUTrace(0, 0, 32, 4, 0, L"Changed %ws to delayed auto-start");
    else
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x200,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\ServiceUtil.cpp",
        v9);
  }
  if ( !StartServiceW(v2, 0, 0) && GetLastError() != 1056 )
  {
    v8 = 527;
    goto LABEL_20;
  }
  v11 = WaitForServiceState(v2, v10);
  LastError = v11;
  if ( v11 < 0 )
  {
    v6 = (unsigned int)v11;
    v4 = 531;
    goto LABEL_23;
  }
  LastError = 0;
LABEL_25:
  if ( v0 )
    SusFree(v0);
  if ( v2 )
    CloseServiceHandle(v2);
  return LastError;
}

```

## disassembly

```asm
0x180086c40  mov     [rsp-18h+arg_0], rbx
0x180086c45  mov     [rsp-18h+arg_8], rsi
0x180086c4a  mov     [rsp-18h+arg_10], rdi
0x180086c4f  push    rbp
0x180086c50  push    r12
0x180086c52  push    r14
0x180086c54  mov     rbp, rsp
0x180086c57  sub     rsp, 80h
0x180086c5e  mov     rax, cs:__security_cookie
0x180086c65  xor     rax, rsp
0x180086c68  mov     [rbp+var_10], rax
0x180086c6c  xor     r14d, r14d
0x180086c6f  lea     r12, ?c_szBitsService@@3QB_WB; "BITS"
0x180086c76  lea     r8, [rbp+hService]; struct SC_HANDLE__ **
0x180086c7a  mov     qword ptr [rbp+pcbBytesNeeded], r14
0x180086c7e  mov     rcx, r12; lpServiceName
0x180086c81  mov     [rbp+hService], r14
0x180086c85  mov     edi, r14d
0x180086c88  lea     edx, [r14+17h]; dwDesiredAccess
0x180086c8c  call    ?OpenNamedService@@YAJPEB_WKPEAPEAUSC_HANDLE__@@@Z; OpenNamedService(wchar_t const *,ulong,SC_HANDLE__ * *)
0x180086c91  mov     rbx, [rbp+hService]
0x180086c95  mov     esi, eax
0x180086c97  test    eax, eax
0x180086c99  jns     short loc_180086CA2
0x180086c9b  mov     edx, 1CFh
0x180086ca0  jmp     short loc_180086CBD
0x180086ca2  lea     rdx, [rbp+pcbBytesNeeded]; struct _QUERY_SERVICE_CONFIGW **
0x180086ca6  mov     rcx, rbx; hService
0x180086ca9  call    ?GetServiceConfig@@YAJPEAUSC_HANDLE__@@PEAPEAU_QUERY_SERVICE_CONFIGW@@@Z; GetServiceConfig(SC_HANDLE__ *,_QUERY_SERVICE_CONFIGW * *)
0x180086cae  mov     rdi, qword ptr [rbp+pcbBytesNeeded]
0x180086cb2  mov     esi, eax
0x180086cb4  test    eax, eax
0x180086cb6  jns     short loc_180086CC5
0x180086cb8  mov     edx, 1D2h
0x180086cbd  mov     r9d, esi
0x180086cc0  jmp     loc_180086E43
0x180086cc5  cmp     dword ptr [rdi+4], 2
0x180086cc9  mov     esi, 4
0x180086cce  jz      loc_180086D6B
0x180086cd4  cmp     [rdi+4], esi
0x180086cd7  jnz     short loc_180086CFF
0x180086cd9  lea     rax, aWsIsDisabled; "%ws is disabled"
0x180086ce0  mov     [rsp+80h+lpdwTagId], r12
0x180086ce5  mov     [rsp+80h+lpLoadOrderGroup], rax
0x180086cea  lea     r8d, [rsi+1Ch]
0x180086cee  mov     r9d, esi
0x180086cf1  mov     [rsp+80h+lpBinaryPathName], r14
0x180086cf6  xor     edx, edx
0x180086cf8  xor     ecx, ecx
0x180086cfa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180086cff  mov     [rsp+80h+lpDisplayName], r14; lpDisplayName
0x180086d04  or      edx, 0FFFFFFFFh; dwServiceType
0x180086d07  mov     [rsp+80h+lpPassword], r14; lpPassword
0x180086d0c  mov     r9d, edx; dwErrorControl
0x180086d0f  mov     [rsp+80h+lpServiceStartName], r14; lpServiceStartName
0x180086d14  mov     r8d, 2; dwStartType
0x180086d1a  mov     [rsp+80h+lpDependencies], r14; lpDependencies
0x180086d1f  mov     rcx, rbx; hService
0x180086d22  mov     [rsp+80h+lpdwTagId], r14; lpdwTagId
0x180086d27  mov     [rsp+80h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x180086d2c  mov     [rsp+80h+lpBinaryPathName], r14; lpBinaryPathName
0x180086d31  call    cs:__imp_ChangeServiceConfigW
0x180086d37  test    eax, eax
0x180086d39  jnz     short loc_180086D45
0x180086d3b  mov     edx, 1E8h
0x180086d40  jmp     loc_180086E19
0x180086d45  xor     edx, edx
0x180086d47  mov     [rsp+80h+lpdwTagId], r12
0x180086d4c  lea     rax, aChangedWsToAut; "Changed %ws to auto-start"
0x180086d53  mov     r9d, esi
0x180086d56  mov     [rsp+80h+lpLoadOrderGroup], rax
0x180086d5b  xor     ecx, ecx
0x180086d5d  mov     [rsp+80h+lpBinaryPathName], r14
0x180086d62  lea     r8d, [rdx+20h]
0x180086d66  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180086d6b  lea     rax, [rbp+pcbBytesNeeded]
0x180086d6f  mov     dword ptr [rbp+hService], r14d
0x180086d73  mov     r9d, esi; cbBufSize
0x180086d76  mov     [rsp+80h+lpBinaryPathName], rax; pcbBytesNeeded
0x180086d7b  lea     r8, [rbp+hService]; lpBuffer
0x180086d7f  mov     [rbp+pcbBytesNeeded], r14d
0x180086d83  mov     edx, 3; dwInfoLevel
0x180086d88  mov     rcx, rbx; hService
0x180086d8b  call    cs:__imp_QueryServiceConfig2W
0x180086d91  test    eax, eax
0x180086d93  jz      short loc_180086DF5
0x180086d95  cmp     dword ptr [rbp+hService], r14d
0x180086d99  jnz     short loc_180086DF5
0x180086d9b  lea     r8, [rbp+hService]; lpInfo
0x180086d9f  mov     dword ptr [rbp+hService], 1
0x180086da6  mov     edx, 3; dwInfoLevel
0x180086dab  mov     rcx, rbx; hService
0x180086dae  call    cs:__imp_ChangeServiceConfig2W
0x180086db4  test    eax, eax
0x180086db6  jnz     short loc_180086DCF
0x180086db8  mov     rcx, [rbp+18h]; this
0x180086dbc  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180086dc3  mov     edx, 200h; void *
0x180086dc8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180086dcd  jmp     short loc_180086DF5
0x180086dcf  xor     edx, edx
0x180086dd1  mov     [rsp+80h+lpdwTagId], r12
0x180086dd6  lea     rax, aChangedWsToDel; "Changed %ws to delayed auto-start"
0x180086ddd  mov     r9d, esi
0x180086de0  mov     [rsp+80h+lpLoadOrderGroup], rax
0x180086de5  xor     ecx, ecx
0x180086de7  mov     [rsp+80h+lpBinaryPathName], r14; int
0x180086dec  lea     r8d, [rdx+20h]
0x180086df0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180086df5  xor     r8d, r8d; lpServiceArgVectors
0x180086df8  xor     edx, edx; dwNumServiceArgs
0x180086dfa  mov     rcx, rbx; hService
0x180086dfd  call    cs:__imp_StartServiceW
0x180086e03  test    eax, eax
0x180086e05  jnz     short loc_180086E2D
0x180086e07  call    cs:__imp_GetLastError
0x180086e0d  cmp     eax, 420h
0x180086e12  jz      short loc_180086E2D
0x180086e14  mov     edx, 20Fh; void *
0x180086e19  mov     rcx, [rbp+18h]; this
0x180086e1d  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180086e24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086e29  mov     esi, eax
0x180086e2b  jmp     short loc_180086E58
0x180086e2d  mov     rcx, rbx; hService
0x180086e30  call    ?WaitForServiceState@@YAJPEAUSC_HANDLE__@@K@Z; WaitForServiceState(SC_HANDLE__ *,ulong)
0x180086e35  mov     esi, eax
0x180086e37  test    eax, eax
0x180086e39  jns     short loc_180086E55
0x180086e3b  mov     r9d, eax; char *
0x180086e3e  mov     edx, 213h; void *
0x180086e43  mov     rcx, [rbp+18h]; this
0x180086e47  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180086e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086e53  jmp     short loc_180086E58
0x180086e55  mov     esi, r14d
0x180086e58  test    rdi, rdi
0x180086e5b  jz      short loc_180086E65
0x180086e5d  mov     rcx, rdi; lpMem
0x180086e60  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180086e65  test    rbx, rbx
0x180086e68  jz      short loc_180086E73
0x180086e6a  mov     rcx, rbx; hSCObject
0x180086e6d  call    cs:__imp_CloseServiceHandle
0x180086e73  mov     eax, esi
0x180086e75  mov     rcx, [rbp+var_10]
0x180086e79  xor     rcx, rsp; StackCookie
0x180086e7c  call    __security_check_cookie
0x180086e81  lea     r11, [rsp+80h+var_s0]
0x180086e89  mov     rbx, [r11+20h]
0x180086e8d  mov     rsi, [r11+28h]
0x180086e91  mov     rdi, [r11+30h]
0x180086e95  mov     rsp, r11
0x180086e98  pop     r14
0x180086e9a  pop     r12
0x180086e9c  pop     rbp
0x180086e9d  retn
```
