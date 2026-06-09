# InitializeStateServiceGlobalState(void)

- ea: `0x1800eeb88`
- end: `0x1800eeda2`
- name: `?InitializeStateServiceGlobalState@@YAJXZ`
- size: `538`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180069bac`

## callees

- `0x180034540`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800ec7f8`
- `0x1800eeb88`
- `0x1800f9178`
- `0x1800fd480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eebdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eecbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eed12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eebdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eec6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eecbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eed12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eed59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eed59`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800eed08`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800eed08`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800eecaa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800eecaa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800eebcd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800eebcd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800eec65`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800eec65`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800eec5a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800eec5a`

## string_xrefs

- `0x1800eec20`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800eec19`: `InitializeStateServiceGlobalState`

## pseudocode

```c
__int64 InitializeStateServiceGlobalState(void)
{
  SC_HANDLE v0; // rdi
  int LastError; // ebx
  int v2; // r8d
  BOOL ServiceStatus; // ebx
  HANDLE v4; // rax
  __int64 pcbBytesNeeded; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  BYTE Buffer[16]; // [rsp+40h] [rbp-30h] BYREF
  DWORD dwProcessId[4]; // [rsp+50h] [rbp-20h]
  int v10; // [rsp+60h] [rbp-10h]

  *(_OWORD *)Buffer = 0;
  v10 = 0;
  *(_OWORD *)dwProcessId = 0;
  LODWORD(pcbBytesNeeded) = 0;
  v0 = OpenServiceW(g_hServiceController, L"RpcSS", 4u);
  if ( !v0 )
  {
    LastError = GetLastError();
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v2 = 2499;
LABEL_6:
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launchk.cxx",
        (unsigned int)"InitializeStateServiceGlobalState",
        v2,
        0,
        (__int64)L"%!WINERROR!",
        LastError,
        pcbBytesNeeded);
      goto LABEL_7;
    }
    goto LABEL_7;
  }
  ServiceStatus = QueryServiceStatusEx(v0, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, (LPDWORD)&pcbBytesNeeded);
  CloseServiceHandle(v0);
  if ( !ServiceStatus )
  {
    LastError = GetLastError();
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v2 = 2512;
      goto LABEL_6;
    }
LABEL_7:
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  v4 = OpenProcess(0x1FFFFFu, 0, dwProcessId[3]);
  g_hStateServiceProcess = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v2 = 2523;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  TokenHandle = 0;
  if ( !OpenProcessToken(v4, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v2 = 2534;
      goto LABEL_6;
    }
    goto LABEL_7;
  }
  LastError = InitializeStateServiceLogonSid(TokenHandle);
  CloseHandle(TokenHandle);
  if ( LastError >= 0 )
  {
    LastError = InitKernelRot();
    if ( LastError >= 0 )
    {
      LastError = CreatePartitionCacheAndLock();
      if ( LastError >= 0 )
        g_dwStateServicePID = dwProcessId[3];
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800eeb88  mov     [rsp-8+arg_0], rbx
0x1800eeb8d  mov     [rsp-8+arg_8], rdi
0x1800eeb92  push    rbp
0x1800eeb93  mov     rbp, rsp
0x1800eeb96  sub     rsp, 70h
0x1800eeb9a  mov     rax, cs:__security_cookie
0x1800eeba1  xor     rax, rsp
0x1800eeba4  mov     [rbp+var_8], rax
0x1800eeba8  mov     rcx, cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA; hSCManager
0x1800eebaf  lea     rdx, ServiceName; "RpcSS"
0x1800eebb6  xor     eax, eax
0x1800eebb8  xorps   xmm0, xmm0
0x1800eebbb  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800eebbf  mov     [rbp+var_10], eax
0x1800eebc2  movups  xmmword ptr [rbp+dwProcessId], xmm0
0x1800eebc6  lea     r8d, [rax+4]; dwDesiredAccess
0x1800eebca  mov     dword ptr [rbp+var_40], eax
0x1800eebcd  call    cs:__imp_OpenServiceW
0x1800eebd3  mov     rdi, rax
0x1800eebd6  test    rax, rax
0x1800eebd9  jnz     short loc_1800EEC42
0x1800eebdb  call    cs:__imp_GetLastError
0x1800eebe1  mov     ebx, eax
0x1800eebe3  mov     eax, cs:dword_18014E4B8
0x1800eebe9  test    eax, eax
0x1800eebeb  jnz     short loc_1800EEC00
0x1800eebed  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800eebf3  jz      short loc_1800EEC2C
0x1800eebf5  xor     ecx, ecx
0x1800eebf7  call    IsWppLevelEnabled
0x1800eebfc  test    al, al
0x1800eebfe  jz      short loc_1800EEC2C
0x1800eec00  mov     r8d, 9C3h
0x1800eec06  lea     rax, aWinerror; "%!WINERROR!"
0x1800eec0d  mov     [rsp+70h+var_48], ebx
0x1800eec11  xor     r9d, r9d
0x1800eec14  mov     [rsp+70h+pcbBytesNeeded], rax
0x1800eec19  lea     rdx, aInitializestat_0; "InitializeStateServiceGlobalState"
0x1800eec20  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800eec27  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800eec2c  test    ebx, ebx
0x1800eec2e  jle     loc_1800EED82
0x1800eec34  movzx   ebx, bx
0x1800eec37  or      ebx, 80070000h
0x1800eec3d  jmp     loc_1800EED82
0x1800eec42  lea     rax, [rbp+var_40]
0x1800eec46  mov     r9d, 24h ; '$'; cbBufSize
0x1800eec4c  lea     r8, [rbp+Buffer]; lpBuffer
0x1800eec50  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800eec55  xor     edx, edx; InfoLevel
0x1800eec57  mov     rcx, rdi; hService
0x1800eec5a  call    cs:__imp_QueryServiceStatusEx
0x1800eec60  mov     rcx, rdi; hSCObject
0x1800eec63  mov     ebx, eax
0x1800eec65  call    cs:__imp_CloseServiceHandle
0x1800eec6b  test    ebx, ebx
0x1800eec6d  jnz     short loc_1800EEC9F
0x1800eec6f  call    cs:__imp_GetLastError
0x1800eec75  mov     ebx, eax
0x1800eec77  mov     eax, cs:dword_18014E4B8
0x1800eec7d  test    eax, eax
0x1800eec7f  jnz     short loc_1800EEC94
0x1800eec81  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800eec87  jz      short loc_1800EEC2C
0x1800eec89  xor     ecx, ecx
0x1800eec8b  call    IsWppLevelEnabled
0x1800eec90  test    al, al
0x1800eec92  jz      short loc_1800EEC2C
0x1800eec94  mov     r8d, 9D0h
0x1800eec9a  jmp     loc_1800EEC06
0x1800eec9f  mov     r8d, [rbp+dwProcessId+0Ch]; dwProcessId
0x1800eeca3  xor     edx, edx; bInheritHandle
0x1800eeca5  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800eecaa  call    cs:__imp_OpenProcess
0x1800eecb0  mov     cs:?g_hStateServiceProcess@@3PEAXEA, rax; void * g_hStateServiceProcess
0x1800eecb7  test    rax, rax
0x1800eecba  jnz     short loc_1800EECF4
0x1800eecbc  call    cs:__imp_GetLastError
0x1800eecc2  mov     ebx, eax
0x1800eecc4  mov     eax, cs:dword_18014E4B8
0x1800eecca  test    eax, eax
0x1800eeccc  jnz     short loc_1800EECE9
0x1800eecce  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800eecd4  jz      loc_1800EEC2C
0x1800eecda  xor     ecx, ecx
0x1800eecdc  call    IsWppLevelEnabled
0x1800eece1  test    al, al
0x1800eece3  jz      loc_1800EEC2C
0x1800eece9  mov     r8d, 9DBh
0x1800eecef  jmp     loc_1800EEC06
0x1800eecf4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800eecf8  mov     [rbp+TokenHandle], 0
0x1800eed00  mov     edx, 20008h; DesiredAccess
0x1800eed05  mov     rcx, rax; ProcessHandle
0x1800eed08  call    cs:__imp_OpenProcessToken
0x1800eed0e  test    eax, eax
0x1800eed10  jnz     short loc_1800EED4A
0x1800eed12  call    cs:__imp_GetLastError
0x1800eed18  mov     ebx, eax
0x1800eed1a  mov     eax, cs:dword_18014E4B8
0x1800eed20  test    eax, eax
0x1800eed22  jnz     short loc_1800EED3F
0x1800eed24  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800eed2a  jz      loc_1800EEC2C
0x1800eed30  xor     ecx, ecx
0x1800eed32  call    IsWppLevelEnabled
0x1800eed37  test    al, al
0x1800eed39  jz      loc_1800EEC2C
0x1800eed3f  mov     r8d, 9E6h
0x1800eed45  jmp     loc_1800EEC06
0x1800eed4a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800eed4e  call    ?InitializeStateServiceLogonSid@@YAJPEAX@Z; InitializeStateServiceLogonSid(void *)
0x1800eed53  mov     rcx, [rbp+TokenHandle]; hObject
0x1800eed57  mov     ebx, eax
0x1800eed59  call    cs:__imp_CloseHandle
0x1800eed5f  test    ebx, ebx
0x1800eed61  js      short loc_1800EED82
0x1800eed63  call    InitKernelRot
0x1800eed68  mov     ebx, eax
0x1800eed6a  test    eax, eax
0x1800eed6c  js      short loc_1800EED82
0x1800eed6e  call    CreatePartitionCacheAndLock
0x1800eed73  mov     ebx, eax
0x1800eed75  test    eax, eax
0x1800eed77  js      short loc_1800EED82
0x1800eed79  mov     eax, [rbp+dwProcessId+0Ch]
0x1800eed7c  mov     cs:?g_dwStateServicePID@@3KA, eax; ulong g_dwStateServicePID
0x1800eed82  mov     eax, ebx
0x1800eed84  mov     rcx, [rbp+var_8]
0x1800eed88  xor     rcx, rsp; StackCookie
0x1800eed8b  call    __security_check_cookie
0x1800eed90  lea     r11, [rsp+70h+var_s0]
0x1800eed95  mov     rbx, [r11+10h]
0x1800eed99  mov     rdi, [r11+18h]
0x1800eed9d  mov     rsp, r11
0x1800eeda0  pop     rbp
0x1800eeda1  retn
```
