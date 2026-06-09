# WaitForCryptService

- ea: `0x180005920`
- end: `0x180005cf7`
- name: `WaitForCryptService`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180004ea0`

## callees

- `0x180005920`
- `0x180005d00`
- `0x180023e3c`
- `0x18002ef20`
- `0x18004da6c`
- `0x18004dc24`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005cc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ce6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005cc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c95`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005a35`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180005a35`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005972`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005972`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180005c8b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180005c8b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005a88`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005af3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005cae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005a88`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005af3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005cae`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800059a9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005b20`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005c5e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800059a9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005b20`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005c5e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800059e5`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800059e5`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180005c7e`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180005c7e`

## pseudocode

```c
__int64 WaitForCryptService()
{
  SC_HANDLE v1; // rax
  unsigned __int16 *v2; // rcx
  SC_HANDLE v3; // rdi
  int v4; // esi
  unsigned __int16 *v5; // rcx
  SC_HANDLE v6; // rbx
  DWORD v7; // r14d
  unsigned __int16 *v8; // rcx
  unsigned int v9; // ebp
  unsigned __int16 *v10; // rcx
  int v11; // esi
  unsigned int v12; // r8d
  DWORD LastError; // esi
  unsigned __int16 *v14; // rcx
  int CryptSvcForceStartPolicy; // eax
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rcx
  DWORD v19; // r8d
  SC_HANDLE v20; // rax
  SC_HANDLE v21; // r15
  BOOL started; // eax
  DWORD v23; // esi
  int v24; // [rsp+20h] [rbp-468h]
  int v25; // [rsp+28h] [rbp-460h]
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-458h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-450h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+60h] [rbp-428h] BYREF

  if ( dword_180069F2C )
    return (unsigned int)dword_180069F60;
  v1 = OpenSCManagerW(0, 0, 1u);
  v3 = v1;
  if ( v1 )
  {
    v4 = 1;
    v6 = OpenServiceW(v1, L"CryptSvc", 5u);
    if ( !v6 )
    {
      ErrLog_LogError(v5, 4u, 0x159u, 0, v24, v25);
      v4 = 0;
      v6 = OpenServiceW(v3, L"CryptSvc", 4u);
      if ( !v6 )
      {
        ErrLog_LogError(v14, 4u, 0x160u, 0, v24, v25);
        LastError = GetLastError();
LABEL_14:
        CloseServiceHandle(v3);
        SetLastError(LastError);
        return (unsigned int)dword_180069F60;
      }
    }
    v7 = 0;
    if ( !v4 )
      goto LABEL_8;
    pcbBytesNeeded = 1024;
    if ( !QueryServiceConfigW(v6, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
    {
      ErrLog_LogError(v8, 4u, 0x19Fu, 0, v24, v25);
      goto LABEL_12;
    }
    if ( ServiceConfig.dwStartType != 4 )
      goto LABEL_8;
    if ( !wcsicmp_0(L"CryptSvc", L"cryptsvc") )
    {
      CryptSvcForceStartPolicy = GetCryptSvcForceStartPolicy();
      if ( CryptSvcForceStartPolicy )
      {
        if ( !(unsigned int)ForceCryptServiceToStart(L"cryptsvc", (unsigned int)(CryptSvcForceStartPolicy != 2) + 2) )
        {
          ErrLog_LogError(v16, 4u, 0x181u, 0, v24, v25);
          goto LABEL_12;
        }
LABEL_28:
        v7 = 1;
LABEL_8:
        v9 = 1000 * GetServiceWaitTimeout();
        while ( 1 )
        {
          v11 = WaitServiceState(v6, 73, v9, 0);
          if ( !v11 )
          {
            v12 = 435;
LABEL_11:
            ErrLog_LogError(v10, 4u, v12, 0, v24, v25);
            goto LABEL_12;
          }
          if ( v11 == 4 )
            break;
          if ( v7 )
          {
            SetLastError(0x5B4u);
            v12 = 448;
            goto LABEL_11;
          }
          v19 = 64;
          *(_OWORD *)&ServiceStatus.dwServiceType = 0;
          if ( v11 != 7 )
            v19 = 16;
          *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
          v20 = OpenServiceW(v3, L"CryptSvc", v19);
          v21 = v20;
          if ( !v20 )
          {
            v12 = 472;
            goto LABEL_11;
          }
          if ( v11 == 7 )
            started = ControlService(v20, 3u, &ServiceStatus);
          else
            started = StartServiceW(v20, 0, 0);
          if ( !started )
            v7 = GetLastError();
          v23 = 0;
          if ( v7 != 1056 )
            v23 = v7;
          CloseServiceHandle(v21);
          if ( v23 )
          {
            SetLastError(v23);
            v12 = 492;
            goto LABEL_11;
          }
          v7 = 1;
        }
        dword_180069F60 = 1;
        dword_180069F2C = 1;
        goto LABEL_12;
      }
    }
    if ( wcsicmp_0(L"CryptSvc", L"ProtectedStorage") )
    {
      SetLastError(0x422u);
      ErrLog_LogError(v18, 4u, 0x198u, 0, v24, v25);
    }
    else
    {
      if ( (unsigned int)ForceCryptServiceToStart(L"ProtectedStorage", 3u) )
        goto LABEL_28;
      ErrLog_LogError(v17, 4u, 0x18Eu, 0, v24, v25);
    }
LABEL_12:
    LastError = GetLastError();
    CloseServiceHandle(v6);
    goto LABEL_14;
  }
  ErrLog_LogError(v2, 4u, 0x14Du, 0, v24, v25);
  return 0;
}

```

## disassembly

```asm
0x180005920  sub     rsp, 488h
0x180005927  mov     rax, cs:__security_cookie
0x18000592e  xor     rax, rsp
0x180005931  mov     [rsp+488h+var_28], rax
0x180005939  cmp     cs:dword_180069F2C, 0
0x180005940  jz      short loc_180005960
0x180005942  mov     eax, cs:dword_180069F60
0x180005948  mov     rcx, [rsp+488h+var_28]
0x180005950  xor     rcx, rsp; StackCookie
0x180005953  call    __security_check_cookie
0x180005958  add     rsp, 488h
0x18000595f  retn
0x180005960  xor     edx, edx; lpDatabaseName
0x180005962  mov     [rsp+488h+arg_18], rdi
0x18000596a  xor     ecx, ecx; lpMachineName
0x18000596c  mov     r8d, 1; dwDesiredAccess
0x180005972  call    cs:__imp_OpenSCManagerW
0x180005978  mov     rdi, rax
0x18000597b  test    rax, rax
0x18000597e  jz      loc_180005B52
0x180005984  mov     [rsp+488h+arg_0], rbx
0x18000598c  lea     rdx, aCryptsvc_0; "CryptSvc"
0x180005993  mov     [rsp+488h+arg_10], rsi
0x18000599b  mov     r8d, 5; dwDesiredAccess
0x1800059a1  mov     rcx, rax; hSCManager
0x1800059a4  mov     esi, 1
0x1800059a9  call    cs:__imp_OpenServiceW
0x1800059af  mov     rbx, rax
0x1800059b2  test    rax, rax
0x1800059b5  jz      loc_180005AFB
0x1800059bb  mov     [rsp+488h+var_10], r14
0x1800059c3  xor     r14d, r14d
0x1800059c6  test    esi, esi
0x1800059c8  jz      short loc_1800059FE
0x1800059ca  lea     r9, [rsp+488h+pcbBytesNeeded]; pcbBytesNeeded
0x1800059cf  mov     [rsp+488h+pcbBytesNeeded], 400h
0x1800059d7  mov     r8d, 400h; cbBufSize
0x1800059dd  lea     rdx, [rsp+488h+ServiceConfig]; lpServiceConfig
0x1800059e2  mov     rcx, rbx; hService
0x1800059e5  call    cs:__imp_QueryServiceConfigW
0x1800059eb  test    eax, eax
0x1800059ed  jz      loc_180005AB9
0x1800059f3  cmp     [rsp+488h+ServiceConfig.dwStartType], 4
0x1800059f8  jz      loc_180005B6C
0x1800059fe  mov     [rsp+488h+arg_8], rbp
0x180005a06  mov     [rsp+488h+var_8], r12
0x180005a0e  call    GetServiceWaitTimeout
0x180005a13  imul    ebp, eax, 3E8h
0x180005a19  mov     r12d, 10h
0x180005a1f  mov     [rsp+488h+var_18], r15
0x180005a27  xor     r9d, r9d
0x180005a2a  mov     r8d, ebp
0x180005a2d  mov     edx, 49h ; 'I'
0x180005a32  mov     rcx, rbx
0x180005a35  call    cs:__imp_WaitServiceState
0x180005a3b  mov     esi, eax
0x180005a3d  test    eax, eax
0x180005a3f  jnz     loc_180005ACE
0x180005a45  mov     r8d, 1B3h; unsigned int
0x180005a4b  xor     r9d, r9d; unsigned int
0x180005a4e  mov     edx, 4; unsigned int
0x180005a53  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005a58  mov     r15, [rsp+488h+var_18]
0x180005a60  mov     rbp, [rsp+488h+arg_8]
0x180005a68  mov     r12, [rsp+488h+var_8]
0x180005a70  call    cs:__imp_GetLastError
0x180005a76  mov     r14, [rsp+488h+var_10]
0x180005a7e  mov     esi, eax
0x180005a80  test    rbx, rbx
0x180005a83  jnz     short loc_180005AF0
0x180005a85  mov     rcx, rdi; hSCObject
0x180005a88  call    cs:__imp_CloseServiceHandle
0x180005a8e  mov     ecx, esi; dwErrCode
0x180005a90  call    cs:__imp_SetLastError
0x180005a96  mov     eax, cs:dword_180069F60
0x180005a9c  mov     rsi, [rsp+488h+arg_10]
0x180005aa4  mov     rbx, [rsp+488h+arg_0]
0x180005aac  mov     rdi, [rsp+488h+arg_18]
0x180005ab4  jmp     loc_180005948
0x180005ab9  xor     r9d, r9d; unsigned int
0x180005abc  mov     edx, 4; unsigned int
0x180005ac1  mov     r8d, 19Fh; unsigned int
0x180005ac7  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005acc  jmp     short loc_180005A70
0x180005ace  cmp     esi, 4
0x180005ad1  jnz     loc_180005C31
0x180005ad7  mov     cs:dword_180069F60, 1
0x180005ae1  mov     cs:dword_180069F2C, 1
0x180005aeb  jmp     loc_180005A58
0x180005af0  mov     rcx, rbx; hSCObject
0x180005af3  call    cs:__imp_CloseServiceHandle
0x180005af9  jmp     short loc_180005A85
0x180005afb  xor     r9d, r9d; unsigned int
0x180005afe  mov     edx, 4; unsigned int
0x180005b03  mov     r8d, 159h; unsigned int
0x180005b09  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005b0e  mov     r8d, 4; dwDesiredAccess
0x180005b14  lea     rdx, aCryptsvc_0; "CryptSvc"
0x180005b1b  mov     rcx, rdi; hSCManager
0x180005b1e  xor     esi, esi
0x180005b20  call    cs:__imp_OpenServiceW
0x180005b26  mov     rbx, rax
0x180005b29  test    rax, rax
0x180005b2c  jnz     loc_1800059BB
0x180005b32  xor     r9d, r9d; unsigned int
0x180005b35  mov     edx, 4; unsigned int
0x180005b3a  mov     r8d, 160h; unsigned int
0x180005b40  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005b45  call    cs:__imp_GetLastError
0x180005b4b  mov     esi, eax
0x180005b4d  jmp     loc_180005A85
0x180005b52  xor     r9d, r9d; unsigned int
0x180005b55  mov     edx, 4; unsigned int
0x180005b5a  mov     r8d, 14Dh; unsigned int
0x180005b60  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005b65  xor     eax, eax
0x180005b67  jmp     loc_180005AAC
0x180005b6c  lea     rdx, aCryptsvc; "cryptsvc"
0x180005b73  lea     rcx, aCryptsvc_0; "CryptSvc"
0x180005b7a  call    _wcsicmp_0
0x180005b7f  test    eax, eax
0x180005b81  jnz     short loc_180005BBF
0x180005b83  call    GetCryptSvcForceStartPolicy
0x180005b88  test    eax, eax
0x180005b8a  jz      short loc_180005BBF
0x180005b8c  xor     edx, edx
0x180005b8e  lea     rcx, aCryptsvc; "cryptsvc"
0x180005b95  cmp     eax, 2
0x180005b98  setnz   dl
0x180005b9b  add     edx, 2; dwStartType
0x180005b9e  call    ForceCryptServiceToStart
0x180005ba3  test    eax, eax
0x180005ba5  jnz     short loc_180005C03
0x180005ba7  xor     r9d, r9d; unsigned int
0x180005baa  mov     edx, 4; unsigned int
0x180005baf  mov     r8d, 181h; unsigned int
0x180005bb5  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005bba  jmp     loc_180005A70
0x180005bbf  lea     rdx, aProtectedstora; "ProtectedStorage"
0x180005bc6  lea     rcx, aCryptsvc_0; "CryptSvc"
0x180005bcd  call    _wcsicmp_0
0x180005bd2  test    eax, eax
0x180005bd4  jnz     short loc_180005C0E
0x180005bd6  mov     edx, 3; dwStartType
0x180005bdb  lea     rcx, aProtectedstora; "ProtectedStorage"
0x180005be2  call    ForceCryptServiceToStart
0x180005be7  test    eax, eax
0x180005be9  jnz     short loc_180005C03
0x180005beb  xor     r9d, r9d; unsigned int
0x180005bee  mov     edx, 4; unsigned int
0x180005bf3  mov     r8d, 18Eh; unsigned int
0x180005bf9  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005bfe  jmp     loc_180005A70
0x180005c03  mov     r14d, 1
0x180005c09  jmp     loc_1800059FE
0x180005c0e  mov     ecx, 422h; dwErrCode
0x180005c13  call    cs:__imp_SetLastError
0x180005c19  xor     r9d, r9d; unsigned int
0x180005c1c  mov     edx, 4; unsigned int
0x180005c21  mov     r8d, 198h; unsigned int
0x180005c27  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180005c2c  jmp     loc_180005A70
0x180005c31  test    r14d, r14d
0x180005c34  jnz     loc_180005CE1
0x180005c3a  xorps   xmm0, xmm0
0x180005c3d  lea     rdx, aCryptsvc_0; "CryptSvc"
0x180005c44  mov     r8d, 40h ; '@'
0x180005c4a  cmp     esi, 7
0x180005c4d  movups  xmmword ptr [rsp+488h+ServiceStatus.dwServiceType], xmm0
0x180005c52  cmovnz  r8d, r12d; dwDesiredAccess
0x180005c56  mov     rcx, rdi; hSCManager
0x180005c59  movups  xmmword ptr [rsp+488h+ServiceStatus.dwWin32ExitCode], xmm0
0x180005c5e  call    cs:__imp_OpenServiceW
0x180005c64  mov     r15, rax
0x180005c67  test    rax, rax
0x180005c6a  jz      short loc_180005CD6
0x180005c6c  mov     rcx, rax; hService
0x180005c6f  cmp     esi, 7
0x180005c72  jnz     short loc_180005C86
0x180005c74  lea     r8, [rsp+488h+ServiceStatus]; lpServiceStatus
0x180005c79  mov     edx, 3; dwControl
0x180005c7e  call    cs:__imp_ControlService
0x180005c84  jmp     short loc_180005C91
0x180005c86  xor     r8d, r8d; lpServiceArgVectors
0x180005c89  xor     edx, edx; dwNumServiceArgs
0x180005c8b  call    cs:__imp_StartServiceW
0x180005c91  test    eax, eax
0x180005c93  jnz     short loc_180005C9E
0x180005c95  call    cs:__imp_GetLastError
0x180005c9b  mov     r14d, eax
0x180005c9e  xor     esi, esi
0x180005ca0  mov     rcx, r15; hSCObject
0x180005ca3  cmp     r14d, 420h
0x180005caa  cmovnz  esi, r14d
0x180005cae  call    cs:__imp_CloseServiceHandle
0x180005cb4  test    esi, esi
0x180005cb6  jnz     short loc_180005CC3
0x180005cb8  mov     r14d, 1
0x180005cbe  jmp     loc_180005A27
0x180005cc3  mov     ecx, esi; dwErrCode
0x180005cc5  call    cs:__imp_SetLastError
0x180005ccb  mov     r8d, 1ECh
0x180005cd1  jmp     loc_180005A4B
0x180005cd6  mov     r8d, 1D8h
0x180005cdc  jmp     loc_180005A4B
0x180005ce1  mov     ecx, 5B4h; dwErrCode
0x180005ce6  call    cs:__imp_SetLastError
0x180005cec  mov     r8d, 1C0h
0x180005cf2  jmp     loc_180005A4B
```
