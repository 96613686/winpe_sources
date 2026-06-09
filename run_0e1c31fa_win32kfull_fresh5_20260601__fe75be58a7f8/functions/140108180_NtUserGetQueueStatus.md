# NtUserGetQueueStatus

- ea: `0x140108180`
- end: `0x1401084af`
- name: `NtUserGetQueueStatus`
- size: `815`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140108180`
- `0x1401085e8`
- `0x140109814`

## import_xrefs

- `ntoskrnl!ZwSetIoCompletionEx` at `0x140108256`
- `ntoskrnl!ZwSetIoCompletionEx` at `0x140108256`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x14010828b`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x14010828b`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140108318`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140108318`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401081ad`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140108206`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401081ad`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140108206`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140108332`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140108332`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x140108340`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x140108340`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x1401083d6`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x1401083d6`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1401083c1`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x1401083c1`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14010849e`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14010849e`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14010844a`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14010844a`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x140108490`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x140108490`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x14010842f`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x14010842f`
- `win32kbase!EnterSharedCrit` at `0x1401081a1`
- `win32kbase!EnterSharedCrit` at `0x1401081a1`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140108456`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140108456`
- `WIN32K!W32GetUserSessionState` at `0x140108354`
- `WIN32K!W32GetUserSessionState` at `0x140108379`
- `WIN32K!W32GetUserSessionState` at `0x140108354`
- `WIN32K!W32GetUserSessionState` at `0x140108379`

## pseudocode

```c
__int64 __fastcall NtUserGetQueueStatus(__int16 a1)
{
  __int64 v2; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v4; // rbx
  __int64 i; // rcx
  const struct tagTHREADINFO **v6; // rax
  const struct tagTHREADINFO *v7; // rsi
  int v8; // r14d
  struct tagWND *v9; // rcx
  int v10; // edi
  unsigned int DLT; // eax
  __int64 v12; // rcx
  __int64 UserSessionState; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  PVOID KeyContext; // rcx
  unsigned int v19; // ebx
  int v21; // [rsp+30h] [rbp-21h]
  struct _FILE_IO_COMPLETION_INFORMATION v22; // [rsp+48h] [rbp-9h] BYREF
  __int128 v23; // [rsp+68h] [rbp+17h]
  char v24; // [rsp+78h] [rbp+27h]
  int v25; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v26; // [rsp+C0h] [rbp+6Fh] BYREF

  EnterSharedCrit(0, 1);
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v2);
  if ( CurrentThreadWin32Thread )
    v4 = *CurrentThreadWin32Thread;
  else
    v4 = 0;
  for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
  {
    if ( *(_QWORD *)(v4 + 8LL * (unsigned int)i + 1656) )
    {
      if ( (a1 & 8) != 0 )
      {
        v6 = (const struct tagTHREADINFO **)PsGetCurrentThreadWin32Thread(i);
        if ( v6 )
          v7 = *v6;
        else
          v7 = 0;
        v25 = 0;
        memset(&v22, 0, sizeof(v22));
        v26 = 0;
        v8 = 0;
        ZwSetIoCompletionEx(*((_QWORD *)v7 + 202), *((_QWORD *)v7 + 206), 0, -2147483647, 0, 0);
        while ( 1 )
        {
          LOBYTE(v21) = 0;
          if ( (unsigned int)ZwRemoveIoCompletionEx(*((_QWORD *)v7 + 202), &v22, 1, &v25, &v26, v21) )
            break;
          if ( ((__int64)v22.ApcContext & 0x80000000) != 0 )
          {
            if ( LODWORD(v22.ApcContext) != 0x80000000 )
              break;
            v8 = 1;
          }
          else
          {
            if ( v22.ApcContext >= (PVOID)2
              || (v9 = (struct tagWND *)*((_QWORD *)v7 + (__int64)v22.ApcContext + 207)) == 0 )
            {
              BroadcastCoreMessagingApcContextError(v7, (unsigned __int64)v22.ApcContext);
              break;
            }
            xxxHandleCoreMessagingQueueCompletion(v9, &v22, 0x80000000);
          }
        }
        if ( v8 )
          ZwAssociateWaitCompletionPacket(
            *((_QWORD *)v7 + 205),
            *((_QWORD *)v7 + 202),
            *((_QWORD *)v7 + 204),
            0,
            0xFFFFFFFF80000000uLL,
            0,
            0,
            0,
            v22.KeyContext,
            v22.ApcContext);
      }
      break;
    }
  }
  v10 = a1 & 0x5DFF;
  DLT = DLT_THREADINFO::getDLT();
  v22.KeyContext = (PVOID)GetDomainLockRef(DLT);
  LOBYTE(v22.ApcContext) = 0;
  UserSessionState = W32GetUserSessionState(v12);
  LOBYTE(v22.IoStatusBlock.Information) = 0;
  v24 = 0;
  v22.IoStatusBlock.Pointer = (PVOID)(UserSessionState + 42184);
  v23 = 0;
  v15 = W32GetUserSessionState(v14);
  v16 = 0;
  if ( v4 != v15 + 41856 )
    v16 = v4 + 424;
  *(_QWORD *)&v23 = v16;
  if ( !v24 )
  {
    if ( v22.KeyContext )
    {
      if ( LOBYTE(v22.ApcContext) )
        tagDomLock::LockExclusive((tagDomLock *)v22.KeyContext);
      else
        tagDomLock::LockShared((tagDomLock *)v22.KeyContext);
    }
    if ( (_QWORD)v23 )
      tagObjLock::LockExclusive((tagObjLock *)v23);
    v24 = 1;
  }
  v17 = *(unsigned int *)(*(_QWORD *)(v4 + 480) + 4LL);
  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v4 + 480) + 4LL), ~v10);
  KeyContext = (PVOID)*(unsigned int *)(*(_QWORD *)(v4 + 480) + 8LL);
  v19 = (unsigned __int16)(v10 & v17) | ((unsigned __int16)(v10 & (unsigned __int16)KeyContext) << 16);
  if ( v24 )
  {
    if ( (_QWORD)v23 )
      tagObjLock::UnLockExclusive((tagObjLock *)v23);
    KeyContext = v22.KeyContext;
    if ( v22.KeyContext )
    {
      if ( LOBYTE(v22.ApcContext) )
        tagDomLock::UnLockExclusive((tagDomLock *)v22.KeyContext);
      else
        tagDomLock::UnLockShared((tagDomLock *)v22.KeyContext);
    }
  }
  UserSessionSwitchLeaveCrit(KeyContext, v17);
  return v19;
}

```

## disassembly

```asm
0x140108180  mov     rax, rsp
0x140108183  push    rbp
0x140108184  push    rbx
0x140108185  lea     rbp, [rax-5Fh]
0x140108189  sub     rsp, 98h
0x140108190  mov     [rax+20h], rdi
0x140108194  mov     edx, 1
0x140108199  mov     edi, ecx
0x14010819b  mov     [rax-28h], r15
0x14010819f  xor     ecx, ecx
0x1401081a1  call    cs:__imp_EnterSharedCrit
0x1401081a8  nop     dword ptr [rax+rax+00h]
0x1401081ad  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1401081b4  nop     dword ptr [rax+rax+00h]
0x1401081b9  xor     r15d, r15d
0x1401081bc  test    rax, rax
0x1401081bf  jz      loc_14010846F
0x1401081c5  mov     rbx, [rax]
0x1401081c8  mov     ecx, r15d
0x1401081cb  cmp     ecx, 2
0x1401081ce  jnb     loc_14010832C
0x1401081d4  mov     eax, ecx
0x1401081d6  cmp     [rbx+rax*8+678h], r15
0x1401081de  jnz     short loc_1401081E4
0x1401081e0  inc     ecx
0x1401081e2  jmp     short loc_1401081CB
0x1401081e4  test    dil, 8
0x1401081e8  jz      loc_14010832C
0x1401081ee  mov     [rsp+0A0h+arg_10], rsi
0x1401081f6  mov     [rsp+90h], r12
0x1401081fe  mov     [rsp+0A0h+var_18], r14
0x140108206  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14010820d  nop     dword ptr [rax+rax+00h]
0x140108212  test    rax, rax
0x140108215  jz      loc_140108477
0x14010821b  mov     rsi, [rax]
0x14010821e  xorps   xmm0, xmm0
0x140108221  mov     [rbp+57h+arg_0], r15d
0x140108225  movups  xmmword ptr [rbp+57h+var_60.KeyContext], xmm0
0x140108229  mov     [rbp+57h+arg_8], r15
0x14010822d  mov     r9, 0FFFFFFFF80000001h
0x140108234  movups  xmmword ptr [rbp+57h+var_60.IoStatusBlock], xmm0
0x140108238  mov     rdx, [rsi+670h]
0x14010823f  xor     r8d, r8d
0x140108242  mov     rcx, [rsi+650h]
0x140108249  mov     r14d, r15d
0x14010824c  mov     [rsp+0A0h+var_78], r15
0x140108251  mov     dword ptr [rsp+0A0h+var_80], r15d
0x140108256  call    cs:__imp_ZwSetIoCompletionEx
0x14010825d  nop     dword ptr [rax+rax+00h]
0x140108262  mov     r12d, 80000000h
0x140108268  mov     rcx, [rsi+650h]
0x14010826f  lea     rax, [rbp+57h+arg_8]
0x140108273  mov     byte ptr [rsp+0A0h+var_78], r15b
0x140108278  lea     r9, [rbp+57h+arg_0]
0x14010827c  mov     r8d, 1
0x140108282  mov     [rsp+0A0h+var_80], rax
0x140108287  lea     rdx, [rbp+57h+var_60]
0x14010828b  call    cs:__imp_ZwRemoveIoCompletionEx
0x140108292  nop     dword ptr [rax+rax+00h]
0x140108297  test    eax, eax
0x140108299  jnz     short loc_1401082D3
0x14010829b  mov     rdx, [rbp+57h+var_60.ApcContext]; unsigned __int64
0x14010829f  test    r12, rdx
0x1401082a2  jz      short loc_1401082B4
0x1401082a4  cmp     edx, 80000000h
0x1401082aa  jnz     short loc_1401082D3
0x1401082ac  mov     r14d, 1
0x1401082b2  jmp     short loc_140108268
0x1401082b4  cmp     rdx, 2
0x1401082b8  jnb     short loc_1401082CB
0x1401082ba  mov     rcx, [rsi+rdx*8+678h]; struct tagWND *
0x1401082c2  test    rcx, rcx
0x1401082c5  jnz     loc_14010847F
0x1401082cb  mov     rcx, rsi; struct tagTHREADINFO *
0x1401082ce  call    ?BroadcastCoreMessagingApcContextError@@YAXPEBUtagTHREADINFO@@_K@Z; BroadcastCoreMessagingApcContextError(tagTHREADINFO const *,unsigned __int64)
0x1401082d3  mov     r12, [rsp+90h]
0x1401082db  test    r14d, r14d
0x1401082de  mov     r14, [rsp+0A0h+var_18]
0x1401082e6  jz      short loc_140108324
0x1401082e8  mov     r8, [rsi+660h]
0x1401082ef  xor     r9d, r9d
0x1401082f2  mov     rdx, [rsi+650h]
0x1401082f9  mov     rcx, [rsi+668h]
0x140108300  mov     [rsp+38h], r15
0x140108305  mov     [rsp+0A0h+var_70], r15
0x14010830a  mov     dword ptr [rsp+0A0h+var_78], r15d
0x14010830f  mov     [rsp+0A0h+var_80], 0FFFFFFFF80000000h
0x140108318  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14010831f  nop     dword ptr [rax+rax+00h]
0x140108324  mov     rsi, [rsp+0A0h+arg_10]
0x14010832c  and     edi, 5DFFh
0x140108332  call    cs:__imp_?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ; DLT_THREADINFO::getDLT(void)
0x140108339  nop     dword ptr [rax+rax+00h]
0x14010833e  mov     ecx, eax
0x140108340  call    cs:__imp_?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z; GetDomainLockRef(DomainLockType)
0x140108347  nop     dword ptr [rax+rax+00h]
0x14010834c  mov     [rbp+57h+var_60.KeyContext], rax
0x140108350  mov     byte ptr [rbp+57h+var_60.ApcContext], r15b
0x140108354  call    cs:__imp_W32GetUserSessionState
0x14010835b  nop     dword ptr [rax+rax+00h]
0x140108360  xorps   xmm0, xmm0
0x140108363  mov     byte ptr [rbp+57h+var_60.IoStatusBlock.Information], r15b
0x140108367  add     rax, 0A4C8h
0x14010836d  mov     [rbp+57h+var_30], r15b
0x140108371  mov     qword ptr [rbp+57h+var_60.IoStatusBlock], rax
0x140108375  movups  [rbp+57h+var_40], xmm0
0x140108379  call    cs:__imp_W32GetUserSessionState
0x140108380  nop     dword ptr [rax+rax+00h]
0x140108385  mov     rdx, r15
0x140108388  lea     rcx, [rbx+1A8h]
0x14010838f  mov     r15, [rsp+0A0h+var_20]
0x140108397  add     rax, 0A380h
0x14010839d  cmp     rbx, rax
0x1401083a0  cmovnz  rdx, rcx
0x1401083a4  cmp     [rbp+57h+var_30], 0
0x1401083a8  mov     qword ptr [rbp+57h+var_40], rdx
0x1401083ac  jnz     short loc_1401083E6
0x1401083ae  mov     rcx, [rbp+57h+var_60.KeyContext]
0x1401083b2  test    rcx, rcx
0x1401083b5  jz      short loc_1401083CD
0x1401083b7  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x1401083bb  jnz     loc_14010849E
0x1401083c1  call    cs:__imp_?LockShared@tagDomLock@@QEBAXXZ; tagDomLock::LockShared(void)
0x1401083c8  nop     dword ptr [rax+rax+00h]
0x1401083cd  mov     rcx, qword ptr [rbp+57h+var_40]
0x1401083d1  test    rcx, rcx
0x1401083d4  jz      short loc_1401083E2
0x1401083d6  call    cs:__imp_?LockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::LockExclusive(void)
0x1401083dd  nop     dword ptr [rax+rax+00h]
0x1401083e2  mov     [rbp+57h+var_30], 1
0x1401083e6  mov     rax, [rbx+1E0h]
0x1401083ed  mov     ecx, edi
0x1401083ef  not     ecx
0x1401083f1  mov     edx, [rax+4]
0x1401083f4  mov     rax, [rbx+1E0h]
0x1401083fb  lock and [rax+4], ecx
0x1401083ff  mov     rax, [rbx+1E0h]
0x140108406  mov     ecx, [rax+8]
0x140108409  movzx   ebx, cx
0x14010840c  and     ebx, edi
0x14010840e  movzx   eax, dx
0x140108411  and     eax, edi
0x140108413  shl     ebx, 10h
0x140108416  mov     rdi, [rsp+0A0h+arg_18]
0x14010841e  or      ebx, eax
0x140108420  cmp     [rbp+57h+var_30], 0
0x140108424  jz      short loc_140108456
0x140108426  mov     rcx, qword ptr [rbp+57h+var_40]
0x14010842a  test    rcx, rcx
0x14010842d  jz      short loc_14010843B
0x14010842f  call    cs:__imp_?UnLockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::UnLockExclusive(void)
0x140108436  nop     dword ptr [rax+rax+00h]
0x14010843b  mov     rcx, [rbp+57h+var_60.KeyContext]
0x14010843f  test    rcx, rcx
0x140108442  jz      short loc_140108456
0x140108444  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x140108448  jnz     short loc_140108490
0x14010844a  call    cs:__imp_?UnLockShared@tagDomLock@@QEBAXXZ; tagDomLock::UnLockShared(void)
0x140108451  nop     dword ptr [rax+rax+00h]
0x140108456  call    cs:__imp_UserSessionSwitchLeaveCrit
0x14010845d  nop     dword ptr [rax+rax+00h]
0x140108462  mov     eax, ebx
0x140108464  add     rsp, 98h
0x14010846b  pop     rbx
0x14010846c  pop     rbp
0x14010846d  retn
0x14010846f  mov     rbx, r15
0x140108472  jmp     loc_1401081C8
0x140108477  mov     rsi, r15
0x14010847a  jmp     loc_14010821E
0x14010847f  mov     r8, r12; unsigned __int64
0x140108482  lea     rdx, [rbp+57h+var_60]; struct _FILE_IO_COMPLETION_INFORMATION *
0x140108486  call    ?xxxHandleCoreMessagingQueueCompletion@@YAXPEAUtagWND@@QEAU_FILE_IO_COMPLETION_INFORMATION@@_K@Z; xxxHandleCoreMessagingQueueCompletion(tagWND *,_FILE_IO_COMPLETION_INFORMATION * const,unsigned __int64)
0x14010848b  jmp     loc_140108268
0x140108490  call    cs:__imp_?UnLockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::UnLockExclusive(void)
0x140108497  nop     dword ptr [rax+rax+00h]
0x14010849c  jmp     short loc_140108456
0x14010849e  call    cs:__imp_?LockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::LockExclusive(void)
0x1401084a5  nop     dword ptr [rax+rax+00h]
0x1401084aa  jmp     loc_1401083CD
```
