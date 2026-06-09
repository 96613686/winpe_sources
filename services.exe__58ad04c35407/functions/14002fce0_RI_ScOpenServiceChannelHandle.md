# RI_ScOpenServiceChannelHandle

- ea: `0x14002fce0`
- end: `0x140030162`
- name: `RI_ScOpenServiceChannelHandle`
- size: `1154`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004c58`
- `0x140013b0c`
- `0x140029228`
- `0x14002f288`
- `0x14002fce0`
- `0x140041bc4`
- `0x14004401c`
- `0x14006c8c0`
- `0x14006da24`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003007a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003007a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fe55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002feb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400300b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002fe55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002feb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400300b7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002fdde`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14002fdde`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x14002fe2f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x14002fe2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002feaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002feaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002fe94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002fe94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003013f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140030130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003013f`
- `RPCRT4!I_RpcOpenClientThread` at `0x14002fe25`
- `RPCRT4!I_RpcOpenClientThread` at `0x14002fe25`
- `RPCRT4!RpcImpersonateClient` at `0x14002fe7c`
- `RPCRT4!RpcImpersonateClient` at `0x14002fe7c`
- `RPCRT4!RpcRevertToSelf` at `0x14002fed5`
- `RPCRT4!RpcRevertToSelf` at `0x14002fedd`
- `RPCRT4!RpcRevertToSelf` at `0x14002fed5`
- `RPCRT4!RpcRevertToSelf` at `0x14002fedd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140030001`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140030001`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140030112`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140030112`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14002ffc3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14002ffc3`
- `ntdll!NtQueryInformationProcess` at `0x14002ff86`
- `ntdll!NtQueryInformationProcess` at `0x14002ff86`

## pseudocode

```c
__int64 __fastcall RI_ScOpenServiceChannelHandle(__int64 a1, char a2, _QWORD *a3)
{
  int (*v3)(void *, unsigned int, void **); // rax
  DWORD v5; // ebx
  int LastError; // eax
  PRPC_ASYNC_STATE v7; // rcx
  __int64 v8; // rdx
  DWORD ProcessId; // r14d
  DWORD v10; // eax
  RPC_STATUS v11; // eax
  HANDLE CurrentThread; // rax
  unsigned int v13; // eax
  DWORD v14; // esi
  void *StubInfo; // rcx
  int v16; // r15d
  int v17; // r12d
  _UNKNOWN **v18; // rbx
  _UNKNOWN **v19; // rsi
  char v20; // al
  bool v21; // zf
  unsigned int v22; // ecx
  DWORD v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  DWORD v26; // eax
  PRPC_ASYNC_STATE v27; // rcx
  __int64 v28; // rdx
  void *v29; // rcx
  signed __int32 v31[8]; // [rsp+0h] [rbp-80h] BYREF
  PULONG ReturnLength; // [rsp+20h] [rbp-60h]
  DWORD ThreadId; // [rsp+30h] [rbp-50h]
  void *TokenHandle; // [rsp+38h] [rbp-48h] BYREF
  HANDLE Process; // [rsp+40h] [rbp-40h] BYREF
  HANDLE Thread; // [rsp+48h] [rbp-38h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v38[4]; // [rsp+70h] [rbp-10h]
  WINBOOL IsMember; // [rsp+D8h] [rbp+58h] BYREF

  v3 = s_pfnI_RpcOpenClientProcess;
  IsMember = 0;
  TokenHandle = 0;
  Process = 0;
  Thread = 0;
  *a3 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)v38 = 0;
  if ( !v3 )
  {
    v5 = 50;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 79, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, 50);
      goto LABEL_65;
    }
    return v5;
  }
  LastError = ((__int64 (__fastcall *)(_QWORD, __int64, HANDLE *))v3)(0, 4096, &Process);
  v5 = LastError;
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_65;
    v8 = 80;
    goto LABEL_9;
  }
  ProcessId = GetProcessId(Process);
  if ( !ProcessId )
  {
    LastError = GetLastError();
    v5 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_65;
    v8 = ProcessId + 81;
    goto LABEL_9;
  }
  I_RpcOpenClientThread(0, 0x800u, &Thread);
  ThreadId = GetThreadId(Thread);
  if ( !ThreadId
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v10 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 82, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v10);
  }
  v11 = RpcImpersonateClient(0);
  v5 = v11;
  if ( v11 )
  {
    ScLogImpersonateFailureEvent(v11);
    goto LABEL_65;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    v5 = GetLastError();
  if ( a2 && !v5 && !(unsigned int)ScIsCallerLocalSystem(TokenHandle) )
  {
    v5 = 5;
    RpcRevertToSelf();
LABEL_27:
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      StubInfo = WPP_GLOBAL_Control->StubInfo;
      LODWORD(ReturnLength) = v5;
      WPP_SF_Dd(StubInfo, 84, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
    }
    goto LABEL_65;
  }
  v13 = RpcRevertToSelf();
  v14 = v13;
  if ( v5 )
    goto LABEL_27;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 85, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v13);
    ScLogEvent(5u, L"RpcRevertToSelf", v14);
    v5 = v14;
    goto LABEL_65;
  }
  LastError = NtQueryInformationProcess(Process, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  v5 = LastError;
  if ( LastError < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_65;
    v8 = 86;
LABEL_9:
    WPP_SF_d(v7->StubInfo, v8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, (unsigned int)LastError);
    goto LABEL_65;
  }
  v16 = 0;
  v17 = 0;
  RtlAcquireSRWLockExclusive(&g_ScServiceChannelLock);
  v18 = (_UNKNOWN **)g_ScServiceChannelContextListHead;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v18 == &g_ScServiceChannelContextListHead )
      {
        v26 = 50;
        v5 = 50;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_64;
        }
        v28 = 88;
LABEL_63:
        v29 = v27->StubInfo;
        LODWORD(ReturnLength) = v26;
        WPP_SF_Dd(v29, v28, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
        goto LABEL_64;
      }
      v19 = v18 - 1;
      v18 = (_UNKNOWN **)*v18;
      v20 = *((_BYTE *)v19 + 141);
      if ( (v20 & 1) != 0 && (v20 & 2) == 0 )
      {
        if ( !CheckTokenMembership(TokenHandle, v19[11], &IsMember) )
        {
          v26 = GetLastError();
          v5 = v26;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
          {
            goto LABEL_64;
          }
          v28 = 87;
          goto LABEL_63;
        }
        if ( IsMember )
          break;
        if ( !v16 )
        {
          v16 = 1;
          v17 = ScCheckForUserServiceClaim(TokenHandle);
        }
        if ( v17 )
          break;
      }
    }
    if ( !a2 )
      break;
    v21 = (*((_BYTE *)v19 + 141) & 0x10) == 0;
LABEL_53:
    if ( !v21 )
      goto LABEL_54;
  }
  v22 = *((_DWORD *)v19 + 25);
  if ( ProcessId != v22 && v38[2] != v22 )
  {
    v21 = (unsigned int)ScIsProcessSCMStarted(v22, v38[2]) == 0;
    goto LABEL_53;
  }
LABEL_54:
  *((_BYTE *)v19 + 141) |= 2u;
  v23 = ThreadId;
  v19[14] = (_UNKNOWN *)((char *)v19[14] + 1);
  *((_DWORD *)v19 + 24) = ProcessId;
  *((_DWORD *)v19 + 26) = v23;
  _InterlockedOr(v31, 0);
  SetEvent(v19[10]);
  v5 = 0;
  *a3 = v19;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_Dqi(WPP_GLOBAL_Control->StubInfo, v24, v25, ProcessId, v19, v19[14]);
LABEL_64:
  RtlReleaseSRWLockExclusive(&g_ScServiceChannelLock);
LABEL_65:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Process )
    CloseHandle(Process);
  if ( Thread )
    CloseHandle(Thread);
  return v5;
}

```

## disassembly

```asm
0x14002fce0  mov     [rsp-38h+arg_0], rbx
0x14002fce5  mov     [rsp-38h+arg_10], r8
0x14002fcea  push    rbp
0x14002fceb  push    rsi
0x14002fcec  push    rdi
0x14002fced  push    r12
0x14002fcef  push    r13
0x14002fcf1  push    r14
0x14002fcf3  push    r15
0x14002fcf5  mov     rbp, rsp
0x14002fcf8  sub     rsp, 80h
0x14002fcff  mov     rax, cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x14002fd06  xorps   xmm0, xmm0
0x14002fd09  mov     [rbp+IsMember], 0
0x14002fd10  mov     r13b, dl
0x14002fd13  mov     [rbp+TokenHandle], 0
0x14002fd1b  mov     [rbp+Process], 0
0x14002fd23  mov     [rbp+Thread], 0
0x14002fd2b  mov     qword ptr [r8], 0
0x14002fd32  movups  [rbp+ProcessInformation], xmm0
0x14002fd36  movups  [rbp+var_20], xmm0
0x14002fd3a  movups  xmmword ptr [rbp+var_10], xmm0
0x14002fd3e  test    rax, rax
0x14002fd41  jnz     short loc_14002FD86
0x14002fd43  mov     eax, 32h ; '2'
0x14002fd48  mov     ebx, eax
0x14002fd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd51  lea     rdi, WPP_GLOBAL_Control
0x14002fd58  cmp     rcx, rdi
0x14002fd5b  jz      loc_140030145
0x14002fd61  test    byte ptr [rcx+1Ch], 1
0x14002fd65  jz      loc_140030145
0x14002fd6b  mov     rcx, [rcx+10h]
0x14002fd6f  lea     edx, [rax+1Dh]
0x14002fd72  mov     r9d, eax
0x14002fd75  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002fd7c  call    WPP_SF_d
0x14002fd81  jmp     loc_140030118
0x14002fd86  lea     r8, [rbp+Process]
0x14002fd8a  mov     edx, 1000h
0x14002fd8f  xor     ecx, ecx
0x14002fd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fd96  mov     ebx, eax
0x14002fd98  test    eax, eax
0x14002fd9a  jz      short loc_14002FDDA
0x14002fd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fda3  lea     rdi, WPP_GLOBAL_Control
0x14002fdaa  cmp     rcx, rdi
0x14002fdad  jz      loc_140030118
0x14002fdb3  test    byte ptr [rcx+1Ch], 1
0x14002fdb7  jz      loc_140030118
0x14002fdbd  mov     edx, 50h ; 'P'
0x14002fdc2  mov     rcx, [rcx+10h]
0x14002fdc6  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002fdcd  mov     r9d, eax
0x14002fdd0  call    WPP_SF_d
0x14002fdd5  jmp     loc_140030118
0x14002fdda  mov     rcx, [rbp+Process]; Process
0x14002fdde  call    cs:__imp_GetProcessId
0x14002fde4  mov     r14d, eax
0x14002fde7  test    eax, eax
0x14002fde9  jnz     short loc_14002FE1A
0x14002fdeb  call    cs:__imp_GetLastError
0x14002fdf1  mov     ebx, eax
0x14002fdf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdfa  lea     rdi, WPP_GLOBAL_Control
0x14002fe01  cmp     rcx, rdi
0x14002fe04  jz      loc_140030118
0x14002fe0a  test    byte ptr [rcx+1Ch], 1
0x14002fe0e  jz      loc_140030118
0x14002fe14  lea     edx, [r14+51h]
0x14002fe18  jmp     short loc_14002FDC2
0x14002fe1a  lea     r8, [rbp+Thread]
0x14002fe1e  mov     edx, 800h
0x14002fe23  xor     ecx, ecx
0x14002fe25  call    cs:__imp_?I_RpcOpenClientThread@@YAJPEAXKPEAPEAX@Z; I_RpcOpenClientThread(void *,ulong,void * *)
0x14002fe2b  mov     rcx, [rbp+Thread]; Thread
0x14002fe2f  call    cs:__imp_GetThreadId
0x14002fe35  mov     [rbp+var_50], eax
0x14002fe38  lea     rdi, WPP_GLOBAL_Control
0x14002fe3f  test    eax, eax
0x14002fe41  jnz     short loc_14002FE7A
0x14002fe43  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe4a  cmp     rcx, rdi
0x14002fe4d  jz      short loc_14002FE7A
0x14002fe4f  test    byte ptr [rcx+1Ch], 1
0x14002fe53  jz      short loc_14002FE7A
0x14002fe55  call    cs:__imp_GetLastError
0x14002fe5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe62  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002fe69  mov     edx, 52h ; 'R'
0x14002fe6e  mov     r9d, eax
0x14002fe71  mov     rcx, [rcx+10h]
0x14002fe75  call    WPP_SF_d
0x14002fe7a  xor     ecx, ecx; BindingHandle
0x14002fe7c  call    cs:__imp_RpcImpersonateClient
0x14002fe82  mov     ebx, eax
0x14002fe84  test    eax, eax
0x14002fe86  jz      short loc_14002FE94
0x14002fe88  mov     ecx, eax; int
0x14002fe8a  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x14002fe8f  jmp     loc_140030118
0x14002fe94  call    cs:__imp_GetCurrentThread
0x14002fe9a  mov     edx, 8; DesiredAccess
0x14002fe9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14002fea3  mov     rcx, rax; ThreadHandle
0x14002fea6  lea     r8d, [rdx-7]; OpenAsSelf
0x14002feaa  call    cs:__imp_OpenThreadToken
0x14002feb0  test    eax, eax
0x14002feb2  jnz     short loc_14002FEBC
0x14002feb4  call    cs:__imp_GetLastError
0x14002feba  mov     ebx, eax
0x14002febc  test    r13b, r13b
0x14002febf  jz      short loc_14002FEDD
0x14002fec1  test    ebx, ebx
0x14002fec3  jnz     short loc_14002FEDD
0x14002fec5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14002fec9  call    ?ScIsCallerLocalSystem@@YAHPEAX@Z; ScIsCallerLocalSystem(void *)
0x14002fece  test    eax, eax
0x14002fed0  jnz     short loc_14002FEDD
0x14002fed2  lea     ebx, [rax+5]
0x14002fed5  call    cs:__imp_RpcRevertToSelf
0x14002fedb  jmp     short loc_14002FEE9
0x14002fedd  call    cs:__imp_RpcRevertToSelf
0x14002fee3  mov     esi, eax
0x14002fee5  test    ebx, ebx
0x14002fee7  jz      short loc_14002FF24
0x14002fee9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fef0  cmp     rcx, rdi
0x14002fef3  jz      loc_140030118
0x14002fef9  test    byte ptr [rcx+1Ch], 1
0x14002fefd  jz      loc_140030118
0x14002ff03  mov     rcx, [rcx+10h]
0x14002ff07  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002ff0e  mov     edx, 54h ; 'T'
0x14002ff13  mov     dword ptr [rsp+80h+ReturnLength], ebx
0x14002ff17  mov     r9d, r14d
0x14002ff1a  call    WPP_SF_Dd
0x14002ff1f  jmp     loc_140030118
0x14002ff24  test    esi, esi
0x14002ff26  jz      short loc_14002FF6D
0x14002ff28  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff2f  cmp     rcx, rdi
0x14002ff32  jz      short loc_14002FF52
0x14002ff34  test    byte ptr [rcx+1Ch], 1
0x14002ff38  jz      short loc_14002FF52
0x14002ff3a  mov     rcx, [rcx+10h]
0x14002ff3e  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14002ff45  mov     edx, 55h ; 'U'
0x14002ff4a  mov     r9d, esi
0x14002ff4d  call    WPP_SF_d
0x14002ff52  mov     r8d, esi
0x14002ff55  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14002ff5c  mov     ecx, 5; unsigned int
0x14002ff61  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14002ff66  mov     ebx, esi
0x14002ff68  jmp     loc_140030118
0x14002ff6d  mov     rcx, [rbp+Process]; ProcessHandle
0x14002ff71  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x14002ff75  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14002ff7b  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x14002ff84  xor     edx, edx; ProcessInformationClass
0x14002ff86  call    cs:__imp_NtQueryInformationProcess
0x14002ff8c  mov     ebx, eax
0x14002ff8e  test    eax, eax
0x14002ff90  jns     short loc_14002FFB6
0x14002ff92  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ff99  cmp     rcx, rdi
0x14002ff9c  jz      loc_140030118
0x14002ffa2  test    byte ptr [rcx+1Ch], 1
0x14002ffa6  jz      loc_140030118
0x14002ffac  mov     edx, 56h ; 'V'
0x14002ffb1  jmp     loc_14002FDC2
0x14002ffb6  xor     r15d, r15d
0x14002ffb9  lea     rcx, g_ScServiceChannelLock
0x14002ffc0  xor     r12d, r12d
0x14002ffc3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14002ffc9  mov     rbx, cs:g_ScServiceChannelContextListHead
0x14002ffd0  lea     rax, g_ScServiceChannelContextListHead
0x14002ffd7  cmp     rbx, rax
0x14002ffda  jz      loc_1400300D8
0x14002ffe0  lea     rsi, [rbx-8]
0x14002ffe4  mov     rbx, [rbx]
0x14002ffe7  mov     al, [rsi+8Dh]
0x14002ffed  test    al, 1
0x14002ffef  jz      short loc_14002FFD0
0x14002fff1  test    al, 2
0x14002fff3  jnz     short loc_14002FFD0
0x14002fff5  mov     rdx, [rsi+58h]; SidToCheck
0x14002fff9  lea     r8, [rbp+IsMember]; IsMember
0x14002fffd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140030001  call    cs:__imp_CheckTokenMembership
0x140030007  test    eax, eax
0x140030009  jz      loc_1400300B7
0x14003000f  cmp     [rbp+IsMember], 0
0x140030013  jnz     short loc_140030031
0x140030015  test    r15d, r15d
0x140030018  jnz     short loc_14003002C
0x14003001a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003001e  mov     r15d, 1
0x140030024  call    ?ScCheckForUserServiceClaim@@YAHPEAX@Z; ScCheckForUserServiceClaim(void *)
0x140030029  mov     r12d, eax
0x14003002c  test    r12d, r12d
0x14003002f  jz      short loc_14002FFD0
0x140030031  test    r13b, r13b
0x140030034  jz      short loc_14003003F
0x140030036  test    byte ptr [rsi+8Dh], 10h
0x14003003d  jmp     short loc_140030056
0x14003003f  mov     ecx, [rsi+64h]; unsigned int
0x140030042  cmp     r14d, ecx
0x140030045  jz      short loc_14003005C
0x140030047  mov     rdx, qword ptr [rbp+var_10+8]; unsigned int
0x14003004b  cmp     edx, ecx
0x14003004d  jz      short loc_14003005C
0x14003004f  call    ?ScIsProcessSCMStarted@@YAHKK@Z; ScIsProcessSCMStarted(ulong,ulong)
0x140030054  test    eax, eax
0x140030056  jz      loc_14002FFD0
0x14003005c  or      byte ptr [rsi+8Dh], 2
0x140030063  mov     eax, [rbp+var_50]
0x140030066  inc     qword ptr [rsi+70h]
0x14003006a  mov     [rsi+60h], r14d
0x14003006e  mov     [rsi+68h], eax
0x140030071  lock or [rsp+80h+var_80], 0
0x140030076  mov     rcx, [rsi+50h]; hEvent
0x14003007a  call    cs:__imp_SetEvent
0x140030080  mov     rax, [rbp+arg_10]
0x140030084  xor     ebx, ebx
0x140030086  mov     [rax], rsi
0x140030089  mov     rcx, cs:WPP_GLOBAL_Control
0x140030090  cmp     rcx, rdi
0x140030093  jz      short loc_14003010B
0x140030095  test    byte ptr [rcx+1Ch], 4
0x140030099  jz      short loc_14003010B
0x14003009b  mov     rax, [rsi+70h]
0x14003009f  mov     r9d, r14d
0x1400300a2  mov     rcx, [rcx+10h]
0x1400300a6  mov     [rsp+80h+var_58], rax
0x1400300ab  mov     [rsp+80h+ReturnLength], rsi
0x1400300b0  call    WPP_SF_Dqi
0x1400300b5  jmp     short loc_14003010B
0x1400300b7  call    cs:__imp_GetLastError
0x1400300bd  mov     ebx, eax
0x1400300bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300c6  cmp     rcx, rdi
0x1400300c9  jz      short loc_14003010B
0x1400300cb  test    byte ptr [rcx+1Ch], 1
0x1400300cf  jz      short loc_14003010B
0x1400300d1  mov     edx, 57h ; 'W'
0x1400300d6  jmp     short loc_1400300F4
0x1400300d8  mov     eax, 32h ; '2'
0x1400300dd  mov     ebx, eax
0x1400300df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300e6  cmp     rcx, rdi
0x1400300e9  jz      short loc_14003010B
0x1400300eb  test    byte ptr [rcx+1Ch], 1
0x1400300ef  jz      short loc_14003010B
0x1400300f1  lea     edx, [rax+26h]
0x1400300f4  mov     rcx, [rcx+10h]
0x1400300f8  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x1400300ff  mov     r9d, r14d
0x140030102  mov     dword ptr [rsp+80h+ReturnLength], eax
0x140030106  call    WPP_SF_Dd
0x14003010b  lea     rcx, g_ScServiceChannelLock
0x140030112  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140030118  mov     rcx, [rbp+TokenHandle]; hObject
0x14003011c  test    rcx, rcx
0x14003011f  jz      short loc_140030127
0x140030121  call    cs:__imp_CloseHandle
0x140030127  mov     rcx, [rbp+Process]; hObject
0x14003012b  test    rcx, rcx
0x14003012e  jz      short loc_140030136
0x140030130  call    cs:__imp_CloseHandle
0x140030136  mov     rcx, [rbp+Thread]; hObject
0x14003013a  test    rcx, rcx
0x14003013d  jz      short loc_140030145
0x14003013f  call    cs:__imp_CloseHandle
0x140030145  mov     eax, ebx
0x140030147  mov     rbx, [rsp+80h+arg_0]
0x14003014f  add     rsp, 80h
0x140030156  pop     r15
0x140030158  pop     r14
0x14003015a  pop     r13
0x14003015c  pop     r12
0x14003015e  pop     rdi
0x14003015f  pop     rsi
0x140030160  pop     rbp
0x140030161  retn
```
