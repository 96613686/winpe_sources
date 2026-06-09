# InitializeStateServiceGlobalState(void)

- ea: `0x1800f6770`
- end: `0x1800f69c7`
- name: `?InitializeStateServiceGlobalState@@YAJXZ`
- size: `599`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006e8b8`

## callees

- `0x180034260`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x1800f4234`
- `0x1800f6770`
- `0x180101278`
- `0x180105b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f67c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f686f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f68c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f692a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f67c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f686f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f68c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f692a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f6977`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f6977`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f691a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f691a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f68b0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f68b0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800f67b5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800f67b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f685f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800f685f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f684e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800f684e`

## string_xrefs

- `0x1800f6814`: `onecore\com\combase\rpcss\olescm\launchk.cxx`
- `0x1800f680d`: `InitializeStateServiceGlobalState`

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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800f6770  mov     [rsp-8+arg_0], rbx
0x1800f6775  mov     [rsp-8+arg_8], rdi
0x1800f677a  push    rbp
0x1800f677b  mov     rbp, rsp
0x1800f677e  sub     rsp, 70h
0x1800f6782  mov     rax, cs:__security_cookie
0x1800f6789  xor     rax, rsp
0x1800f678c  mov     [rbp+var_8], rax
0x1800f6790  mov     rcx, cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA; hSCManager
0x1800f6797  lea     rdx, ServiceName; "RpcSS"
0x1800f679e  xor     eax, eax
0x1800f67a0  xorps   xmm0, xmm0
0x1800f67a3  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800f67a7  mov     [rbp+var_10], eax
0x1800f67aa  movups  xmmword ptr [rbp+dwProcessId], xmm0
0x1800f67ae  lea     r8d, [rax+4]; dwDesiredAccess
0x1800f67b2  mov     dword ptr [rbp+var_40], eax
0x1800f67b5  call    cs:__imp_OpenServiceW
0x1800f67bc  nop     dword ptr [rax+rax+00h]
0x1800f67c1  mov     rdi, rax
0x1800f67c4  test    rax, rax
0x1800f67c7  jnz     short loc_1800F6836
0x1800f67c9  call    cs:__imp_GetLastError
0x1800f67d0  nop     dword ptr [rax+rax+00h]
0x1800f67d5  mov     ebx, eax
0x1800f67d7  mov     eax, cs:dword_1801574B8
0x1800f67dd  test    eax, eax
0x1800f67df  jnz     short loc_1800F67F4
0x1800f67e1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f67e7  jz      short loc_1800F6820
0x1800f67e9  xor     ecx, ecx
0x1800f67eb  call    IsWppLevelEnabled
0x1800f67f0  test    al, al
0x1800f67f2  jz      short loc_1800F6820
0x1800f67f4  mov     r8d, 9C3h
0x1800f67fa  lea     rax, aWinerror; "%!WINERROR!"
0x1800f6801  mov     [rsp+70h+var_48], ebx
0x1800f6805  xor     r9d, r9d
0x1800f6808  mov     [rsp+70h+pcbBytesNeeded], rax
0x1800f680d  lea     rdx, aInitializestat_0; "InitializeStateServiceGlobalState"
0x1800f6814  lea     rcx, aOnecoreComComb_70; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800f681b  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800f6820  test    ebx, ebx
0x1800f6822  jle     loc_1800F69A6
0x1800f6828  movzx   ebx, bx
0x1800f682b  or      ebx, 80070000h
0x1800f6831  jmp     loc_1800F69A6
0x1800f6836  lea     rax, [rbp+var_40]
0x1800f683a  mov     r9d, 24h ; '$'; cbBufSize
0x1800f6840  lea     r8, [rbp+Buffer]; lpBuffer
0x1800f6844  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800f6849  xor     edx, edx; InfoLevel
0x1800f684b  mov     rcx, rdi; hService
0x1800f684e  call    cs:__imp_QueryServiceStatusEx
0x1800f6855  nop     dword ptr [rax+rax+00h]
0x1800f685a  mov     rcx, rdi; hSCObject
0x1800f685d  mov     ebx, eax
0x1800f685f  call    cs:__imp_CloseServiceHandle
0x1800f6866  nop     dword ptr [rax+rax+00h]
0x1800f686b  test    ebx, ebx
0x1800f686d  jnz     short loc_1800F68A5
0x1800f686f  call    cs:__imp_GetLastError
0x1800f6876  nop     dword ptr [rax+rax+00h]
0x1800f687b  mov     ebx, eax
0x1800f687d  mov     eax, cs:dword_1801574B8
0x1800f6883  test    eax, eax
0x1800f6885  jnz     short loc_1800F689A
0x1800f6887  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f688d  jz      short loc_1800F6820
0x1800f688f  xor     ecx, ecx
0x1800f6891  call    IsWppLevelEnabled
0x1800f6896  test    al, al
0x1800f6898  jz      short loc_1800F6820
0x1800f689a  mov     r8d, 9D0h
0x1800f68a0  jmp     loc_1800F67FA
0x1800f68a5  mov     r8d, [rbp+dwProcessId+0Ch]; dwProcessId
0x1800f68a9  xor     edx, edx; bInheritHandle
0x1800f68ab  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800f68b0  call    cs:__imp_OpenProcess
0x1800f68b7  nop     dword ptr [rax+rax+00h]
0x1800f68bc  mov     cs:?g_hStateServiceProcess@@3PEAXEA, rax; void * g_hStateServiceProcess
0x1800f68c3  test    rax, rax
0x1800f68c6  jnz     short loc_1800F6906
0x1800f68c8  call    cs:__imp_GetLastError
0x1800f68cf  nop     dword ptr [rax+rax+00h]
0x1800f68d4  mov     ebx, eax
0x1800f68d6  mov     eax, cs:dword_1801574B8
0x1800f68dc  test    eax, eax
0x1800f68de  jnz     short loc_1800F68FB
0x1800f68e0  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f68e6  jz      loc_1800F6820
0x1800f68ec  xor     ecx, ecx
0x1800f68ee  call    IsWppLevelEnabled
0x1800f68f3  test    al, al
0x1800f68f5  jz      loc_1800F6820
0x1800f68fb  mov     r8d, 9DBh
0x1800f6901  jmp     loc_1800F67FA
0x1800f6906  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800f690a  mov     [rbp+TokenHandle], 0
0x1800f6912  mov     edx, 20008h; DesiredAccess
0x1800f6917  mov     rcx, rax; ProcessHandle
0x1800f691a  call    cs:__imp_OpenProcessToken
0x1800f6921  nop     dword ptr [rax+rax+00h]
0x1800f6926  test    eax, eax
0x1800f6928  jnz     short loc_1800F6968
0x1800f692a  call    cs:__imp_GetLastError
0x1800f6931  nop     dword ptr [rax+rax+00h]
0x1800f6936  mov     ebx, eax
0x1800f6938  mov     eax, cs:dword_1801574B8
0x1800f693e  test    eax, eax
0x1800f6940  jnz     short loc_1800F695D
0x1800f6942  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f6948  jz      loc_1800F6820
0x1800f694e  xor     ecx, ecx
0x1800f6950  call    IsWppLevelEnabled
0x1800f6955  test    al, al
0x1800f6957  jz      loc_1800F6820
0x1800f695d  mov     r8d, 9E6h
0x1800f6963  jmp     loc_1800F67FA
0x1800f6968  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800f696c  call    ?InitializeStateServiceLogonSid@@YAJPEAX@Z; InitializeStateServiceLogonSid(void *)
0x1800f6971  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f6975  mov     ebx, eax
0x1800f6977  call    cs:__imp_CloseHandle
0x1800f697e  nop     dword ptr [rax+rax+00h]
0x1800f6983  test    ebx, ebx
0x1800f6985  js      short loc_1800F69A6
0x1800f6987  call    InitKernelRot
0x1800f698c  mov     ebx, eax
0x1800f698e  test    eax, eax
0x1800f6990  js      short loc_1800F69A6
0x1800f6992  call    CreatePartitionCacheAndLock
0x1800f6997  mov     ebx, eax
0x1800f6999  test    eax, eax
0x1800f699b  js      short loc_1800F69A6
0x1800f699d  mov     eax, [rbp+dwProcessId+0Ch]
0x1800f69a0  mov     cs:?g_dwStateServicePID@@3KA, eax; ulong g_dwStateServicePID
0x1800f69a6  mov     eax, ebx
0x1800f69a8  mov     rcx, [rbp+var_8]
0x1800f69ac  xor     rcx, rsp; StackCookie
0x1800f69af  call    __security_check_cookie
0x1800f69b4  lea     r11, [rsp+70h+var_s0]
0x1800f69b9  mov     rbx, [r11+10h]
0x1800f69bd  mov     rdi, [r11+18h]
0x1800f69c1  mov     rsp, r11
0x1800f69c4  pop     rbp
0x1800f69c5  retn
```
