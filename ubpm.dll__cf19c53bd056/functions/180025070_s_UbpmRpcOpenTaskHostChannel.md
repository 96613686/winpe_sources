# s_UbpmRpcOpenTaskHostChannel

- ea: `0x180025070`
- end: `0x180025420`
- name: `s_UbpmRpcOpenTaskHostChannel`
- size: `944`
- prototype: `__int64 __fastcall(__int64, int, void ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180025070`
- `0x180032e38`
- `0x18003c494`
- `0x18003c4e8`
- `0x18003cbc0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800251bd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800251bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002513c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002513c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025223`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800250f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800250f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025142`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025142`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800250d0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800250d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002510f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002510f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800253f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800251ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800251ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002525c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002526c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002525c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002526c`
- `RPCRT4!RpcImpersonateClient` at `0x1800250e3`
- `RPCRT4!RpcImpersonateClient` at `0x1800250e3`
- `RPCRT4!RpcRevertToSelf` at `0x18002511d`
- `RPCRT4!RpcRevertToSelf` at `0x18002511d`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcOpenTaskHostChannel(__int64 a1, int a2, void ***a3)
{
  DWORD v5; // eax
  DWORD v6; // ebx
  DWORD ProcessId; // r14d
  HANDLE CurrentThread; // rax
  __int64 v9; // r8
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  void *v12; // r12
  void **v13; // rbx
  PVOID *v14; // rcx
  signed __int32 v15; // eax
  void **v16; // rdi
  __int64 v17; // rdx
  __int64 v19; // rcx
  DWORD v20; // eax
  DWORD LastError; // eax
  signed __int32 v22[10]; // [rsp+0h] [rbp-78h] BYREF
  HANDLE Process[2]; // [rsp+30h] [rbp-48h] BYREF
  WINBOOL IsMember; // [rsp+90h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+20h] BYREF

  TokenHandle = 0;
  Process[0] = 0;
  if ( a3 )
    *a3 = 0;
  v5 = ((__int64 (__fastcall *)(_QWORD, __int64, HANDLE *))s_pfnI_RpcOpenClientProcess)(0, 4096, Process);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v5);
    goto LABEL_25;
  }
  ProcessId = GetProcessId(Process[0]);
  if ( !ProcessId )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    goto LABEL_25;
  }
  v6 = RpcImpersonateClient(0);
  if ( v6 )
    goto LABEL_25;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    v6 = GetLastError();
  RpcRevertToSelf();
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v9, ProcessId, v6);
    goto LABEL_25;
  }
  RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
  CurrentThreadId = GetCurrentThreadId();
  v12 = TokenHandle;
  v13 = (void **)g_leTaskHostContextListHead;
  dword_18004CF18 = CurrentThreadId;
  IsMember = 0;
LABEL_10:
  while ( 2 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    do
    {
      while ( 1 )
      {
        if ( v13 == (void **)&g_leTaskHostContextListHead )
        {
          v6 = 1168;
LABEL_39:
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
            WPP_SF_Ld(v14[2], 21, v11, ProcessId, 1168);
          goto LABEL_24;
        }
        v15 = *((unsigned __int8 *)v13 + 96);
        v16 = v13 - 1;
        v13 = (void **)*v13;
        if ( (v15 & 0x84) == 0 )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v22[8] = v15;
          WPP_SF_qd(v19, 89);
          goto LABEL_10;
        }
      }
    }
    while ( *((_DWORD *)v16 + 8) != ProcessId || a2 && (v15 & 9) != 1 );
    if ( !CheckTokenMembership(v12, v16[22], &IsMember) )
    {
      v6 = 1168;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_24;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v20);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_39;
    }
    if ( IsMember != 1 )
      continue;
    break;
  }
  _InterlockedIncrement64((volatile signed __int64 *)v16 + 12);
  if ( a2 )
  {
    *((_BYTE *)v16 + 104) |= 2u;
    _InterlockedOr(v22, 0);
    SetEvent(v16[6]);
  }
  if ( a3 )
    *a3 = v16;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Lqi(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v11, ProcessId, v16, v16[12]);
LABEL_24:
  dword_18004CF18 = 0;
  RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
LABEL_25:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Process[0] )
    CloseHandle(Process[0]);
  return v6;
}

```

## disassembly

```asm
0x180025070  mov     rax, rsp
0x180025073  push    rbx
0x180025074  sub     rsp, 70h
0x180025078  mov     [rax-10h], rsi
0x18002507c  mov     rsi, r8
0x18002507f  mov     [rax-18h], rdi
0x180025083  xor     edi, edi
0x180025085  mov     [rax-38h], r15
0x180025089  mov     r15d, edx
0x18002508c  mov     [rax+20h], rdi
0x180025090  mov     [rax-48h], rdi
0x180025094  test    r8, r8
0x180025097  jz      short loc_18002509C
0x180025099  mov     [r8], rdi
0x18002509c  mov     rax, cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x1800250a3  lea     r8, [rsp+78h+Process]
0x1800250a8  mov     edx, 1000h
0x1800250ad  mov     [rsp+78h+arg_0], rbp
0x1800250b5  xor     ecx, ecx
0x1800250b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250bc  mov     ebx, eax
0x1800250be  test    eax, eax
0x1800250c0  jnz     loc_180025370
0x1800250c6  mov     rcx, [rsp+78h+Process]; Process
0x1800250cb  mov     [rsp+78h+var_30], r14
0x1800250d0  call    cs:__imp_GetProcessId
0x1800250d6  mov     r14d, eax
0x1800250d9  test    eax, eax
0x1800250db  jz      loc_1800253AE
0x1800250e1  xor     ecx, ecx; BindingHandle
0x1800250e3  call    cs:__imp_RpcImpersonateClient
0x1800250e9  mov     ebx, eax
0x1800250eb  test    eax, eax
0x1800250ed  jnz     loc_180025233
0x1800250f3  call    cs:__imp_GetCurrentThread
0x1800250f9  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180025101  mov     edx, 8; DesiredAccess
0x180025106  mov     rcx, rax; ThreadHandle
0x180025109  mov     r8d, 1; OpenAsSelf
0x18002510f  call    cs:__imp_OpenThreadToken
0x180025115  test    eax, eax
0x180025117  jz      loc_1800253F4
0x18002511d  call    cs:__imp_RpcRevertToSelf
0x180025123  test    ebx, ebx
0x180025125  jnz     loc_180025335
0x18002512b  mov     [rsp+78h+var_20], r12
0x180025130  lea     rcx, g_TaskHostContextListLock
0x180025137  mov     [rsp+78h+var_28], r13
0x18002513c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180025142  call    cs:__imp_GetCurrentThreadId
0x180025148  mov     r12, [rsp+78h+TokenHandle]
0x180025150  lea     rbp, WPP_GLOBAL_Control
0x180025157  mov     rbx, cs:g_leTaskHostContextListHead
0x18002515e  lea     r13, g_leTaskHostContextListHead
0x180025165  mov     cs:dword_18004CF18, eax
0x18002516b  mov     [rsp+78h+IsMember], edi
0x180025172  mov     rcx, cs:WPP_GLOBAL_Control
0x180025179  nop     dword ptr [rax+00000000h]
0x180025180  cmp     rbx, r13
0x180025183  jz      loc_1800252A7
0x180025189  movzx   eax, byte ptr [rbx+60h]
0x18002518d  lea     rdi, [rbx-8]
0x180025191  mov     rbx, [rbx]
0x180025194  test    al, 84h
0x180025196  jnz     loc_18002527A
0x18002519c  cmp     [rdi+20h], r14d
0x1800251a0  jnz     short loc_180025180
0x1800251a2  test    r15d, r15d
0x1800251a5  jnz     loc_1800252B0
0x1800251ab  mov     rdx, [rdi+0B0h]; SidToCheck
0x1800251b2  lea     r8, [rsp+78h+IsMember]; IsMember
0x1800251ba  mov     rcx, r12; TokenHandle
0x1800251bd  call    cs:__imp_CheckTokenMembership
0x1800251c3  test    eax, eax
0x1800251c5  jz      loc_1800252BF
0x1800251cb  cmp     [rsp+78h+IsMember], 1
0x1800251d3  jnz     short loc_180025172
0x1800251d5  lock inc qword ptr [rdi+60h]
0x1800251da  test    r15d, r15d
0x1800251dd  jz      short loc_1800251F2
0x1800251df  or      byte ptr [rdi+68h], 2
0x1800251e3  lock or [rsp+78h+var_78], 0
0x1800251e8  mov     rcx, [rdi+30h]; hEvent
0x1800251ec  call    cs:__imp_SetEvent
0x1800251f2  test    rsi, rsi
0x1800251f5  jz      short loc_1800251FA
0x1800251f7  mov     [rsi], rdi
0x1800251fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180025201  xor     ebx, ebx
0x180025203  cmp     rcx, rbp
0x180025206  jz      short loc_180025212
0x180025208  test    byte ptr [rcx+1Ch], 80h
0x18002520c  jnz     loc_180025401
0x180025212  lea     rcx, g_TaskHostContextListLock
0x180025219  mov     cs:dword_18004CF18, 0
0x180025223  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180025229  mov     r13, [rsp+78h+var_28]
0x18002522e  mov     r12, [rsp+78h+var_20]
0x180025233  mov     r14, [rsp+78h+var_30]
0x180025238  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180025240  mov     r15, [rsp+78h+var_38]
0x180025245  mov     rdi, [rsp+78h+var_18]
0x18002524a  mov     rsi, [rsp+78h+var_10]
0x18002524f  mov     rbp, [rsp+78h+arg_0]
0x180025257  test    rcx, rcx
0x18002525a  jz      short loc_180025262
0x18002525c  call    cs:__imp_CloseHandle
0x180025262  mov     rcx, [rsp+78h+Process]; hObject
0x180025267  test    rcx, rcx
0x18002526a  jz      short loc_180025272
0x18002526c  call    cs:__imp_CloseHandle
0x180025272  mov     eax, ebx
0x180025274  add     rsp, 70h
0x180025278  pop     rbx
0x180025279  retn
0x18002527a  cmp     rcx, rbp
0x18002527d  jz      loc_180025180
0x180025283  test    byte ptr [rcx+1Ch], 2
0x180025287  jz      loc_180025180
0x18002528d  mov     rcx, [rcx+10h]
0x180025291  mov     edx, 59h ; 'Y'
0x180025296  mov     r9, rdi
0x180025299  mov     dword ptr [rsp+78h+var_58], eax
0x18002529d  call    WPP_SF_qd
0x1800252a2  jmp     loc_180025172
0x1800252a7  mov     ebx, 490h
0x1800252ac  mov     edi, ebx
0x1800252ae  jmp     short loc_180025308
0x1800252b0  and     al, 9
0x1800252b2  cmp     al, 1
0x1800252b4  jnz     loc_180025180
0x1800252ba  jmp     loc_1800251AB
0x1800252bf  mov     ebx, 490h
0x1800252c4  mov     edi, ebx
0x1800252c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252cd  cmp     rcx, rbp
0x1800252d0  jz      loc_180025212
0x1800252d6  test    byte ptr [rcx+1Ch], 1
0x1800252da  jz      short loc_180025308
0x1800252dc  call    cs:__imp_GetLastError
0x1800252e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252e9  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800252f0  mov     edx, 5Ah ; 'Z'
0x1800252f5  mov     r9d, eax
0x1800252f8  mov     rcx, [rcx+10h]
0x1800252fc  call    WPP_SF_d
0x180025301  mov     rcx, cs:WPP_GLOBAL_Control
0x180025308  cmp     rcx, rbp
0x18002530b  jz      loc_180025212
0x180025311  test    byte ptr [rcx+1Ch], 1
0x180025315  jz      loc_180025212
0x18002531b  mov     rcx, [rcx+10h]
0x18002531f  mov     edx, 15h
0x180025324  mov     r9d, r14d
0x180025327  mov     dword ptr [rsp+78h+var_58], edi
0x18002532b  call    WPP_SF_Ld
0x180025330  jmp     loc_180025212
0x180025335  mov     rcx, cs:WPP_GLOBAL_Control
0x18002533c  lea     rbp, WPP_GLOBAL_Control
0x180025343  cmp     rcx, rbp
0x180025346  jz      loc_180025233
0x18002534c  test    byte ptr [rcx+1Ch], 1
0x180025350  jz      loc_180025233
0x180025356  mov     rcx, [rcx+10h]
0x18002535a  mov     edx, 14h
0x18002535f  mov     r9d, r14d
0x180025362  mov     dword ptr [rsp+78h+var_58], ebx
0x180025366  call    WPP_SF_Ld
0x18002536b  jmp     loc_180025233
0x180025370  mov     rcx, cs:WPP_GLOBAL_Control
0x180025377  lea     rbp, WPP_GLOBAL_Control
0x18002537e  cmp     rcx, rbp
0x180025381  jz      loc_180025238
0x180025387  test    byte ptr [rcx+1Ch], 1
0x18002538b  jz      loc_180025238
0x180025391  mov     rcx, [rcx+10h]
0x180025395  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18002539c  mov     edx, 12h
0x1800253a1  mov     r9d, eax
0x1800253a4  call    WPP_SF_d
0x1800253a9  jmp     loc_180025238
0x1800253ae  call    cs:__imp_GetLastError
0x1800253b4  mov     ebx, eax
0x1800253b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253bd  lea     rbp, WPP_GLOBAL_Control
0x1800253c4  cmp     rcx, rbp
0x1800253c7  jz      loc_180025233
0x1800253cd  test    byte ptr [rcx+1Ch], 1
0x1800253d1  jz      loc_180025233
0x1800253d7  mov     rcx, [rcx+10h]
0x1800253db  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800253e2  mov     edx, 13h
0x1800253e7  mov     r9d, eax
0x1800253ea  call    WPP_SF_d
0x1800253ef  jmp     loc_180025233
0x1800253f4  call    cs:__imp_GetLastError
0x1800253fa  mov     ebx, eax
0x1800253fc  jmp     loc_18002511D
0x180025401  mov     rax, [rdi+60h]
0x180025405  mov     r9d, r14d
0x180025408  mov     rcx, [rcx+10h]
0x18002540c  mov     [rsp+78h+var_50], rax
0x180025411  mov     [rsp+78h+var_58], rdi
0x180025416  call    WPP_SF_Lqi
0x18002541b  jmp     loc_180025212
```
