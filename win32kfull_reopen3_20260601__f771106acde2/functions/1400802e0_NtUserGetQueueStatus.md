# NtUserGetQueueStatus

- ea: `0x1400802e0`
- end: `0x14008060f`
- name: `NtUserGetQueueStatus`
- size: `815`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400802e0`
- `0x140080748`
- `0x140081974`

## import_xrefs

- `ntoskrnl!ZwSetIoCompletionEx` at `0x1400803b6`
- `ntoskrnl!ZwSetIoCompletionEx` at `0x1400803b6`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400803eb`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x1400803eb`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140080478`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140080478`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008030d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140080366`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14008030d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140080366`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140080492`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140080492`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400804a0`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x1400804a0`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x140080536`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x140080536`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x140080521`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x140080521`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400805fe`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x1400805fe`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400805aa`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x1400805aa`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400805f0`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x1400805f0`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x14008058f`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x14008058f`
- `win32kbase!EnterSharedCrit` at `0x140080301`
- `win32kbase!EnterSharedCrit` at `0x140080301`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400805b6`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400805b6`
- `WIN32K!W32GetUserSessionState` at `0x1400804b4`
- `WIN32K!W32GetUserSessionState` at `0x1400804d9`
- `WIN32K!W32GetUserSessionState` at `0x1400804b4`
- `WIN32K!W32GetUserSessionState` at `0x1400804d9`

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
0x1400802e0  mov     rax, rsp
0x1400802e3  push    rbp
0x1400802e4  push    rbx
0x1400802e5  lea     rbp, [rax-5Fh]
0x1400802e9  sub     rsp, 98h
0x1400802f0  mov     [rax+20h], rdi
0x1400802f4  mov     edx, 1
0x1400802f9  mov     edi, ecx
0x1400802fb  mov     [rax-28h], r15
0x1400802ff  xor     ecx, ecx
0x140080301  call    cs:__imp_EnterSharedCrit
0x140080308  nop     dword ptr [rax+rax+00h]
0x14008030d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140080314  nop     dword ptr [rax+rax+00h]
0x140080319  xor     r15d, r15d
0x14008031c  test    rax, rax
0x14008031f  jz      loc_1400805CF
0x140080325  mov     rbx, [rax]
0x140080328  mov     ecx, r15d
0x14008032b  cmp     ecx, 2
0x14008032e  jnb     loc_14008048C
0x140080334  mov     eax, ecx
0x140080336  cmp     [rbx+rax*8+678h], r15
0x14008033e  jnz     short loc_140080344
0x140080340  inc     ecx
0x140080342  jmp     short loc_14008032B
0x140080344  test    dil, 8
0x140080348  jz      loc_14008048C
0x14008034e  mov     [rsp+0A0h+arg_10], rsi
0x140080356  mov     [rsp+90h], r12
0x14008035e  mov     [rsp+0A0h+var_18], r14
0x140080366  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14008036d  nop     dword ptr [rax+rax+00h]
0x140080372  test    rax, rax
0x140080375  jz      loc_1400805D7
0x14008037b  mov     rsi, [rax]
0x14008037e  xorps   xmm0, xmm0
0x140080381  mov     [rbp+57h+arg_0], r15d
0x140080385  movups  xmmword ptr [rbp+57h+var_60.KeyContext], xmm0
0x140080389  mov     [rbp+57h+arg_8], r15
0x14008038d  mov     r9, 0FFFFFFFF80000001h
0x140080394  movups  xmmword ptr [rbp+57h+var_60.IoStatusBlock], xmm0
0x140080398  mov     rdx, [rsi+670h]
0x14008039f  xor     r8d, r8d
0x1400803a2  mov     rcx, [rsi+650h]
0x1400803a9  mov     r14d, r15d
0x1400803ac  mov     [rsp+0A0h+var_78], r15
0x1400803b1  mov     dword ptr [rsp+0A0h+var_80], r15d
0x1400803b6  call    cs:__imp_ZwSetIoCompletionEx
0x1400803bd  nop     dword ptr [rax+rax+00h]
0x1400803c2  mov     r12d, 80000000h
0x1400803c8  mov     rcx, [rsi+650h]
0x1400803cf  lea     rax, [rbp+57h+arg_8]
0x1400803d3  mov     byte ptr [rsp+0A0h+var_78], r15b
0x1400803d8  lea     r9, [rbp+57h+arg_0]
0x1400803dc  mov     r8d, 1
0x1400803e2  mov     [rsp+0A0h+var_80], rax
0x1400803e7  lea     rdx, [rbp+57h+var_60]
0x1400803eb  call    cs:__imp_ZwRemoveIoCompletionEx
0x1400803f2  nop     dword ptr [rax+rax+00h]
0x1400803f7  test    eax, eax
0x1400803f9  jnz     short loc_140080433
0x1400803fb  mov     rdx, [rbp+57h+var_60.ApcContext]; unsigned __int64
0x1400803ff  test    r12, rdx
0x140080402  jz      short loc_140080414
0x140080404  cmp     edx, 80000000h
0x14008040a  jnz     short loc_140080433
0x14008040c  mov     r14d, 1
0x140080412  jmp     short loc_1400803C8
0x140080414  cmp     rdx, 2
0x140080418  jnb     short loc_14008042B
0x14008041a  mov     rcx, [rsi+rdx*8+678h]; struct tagWND *
0x140080422  test    rcx, rcx
0x140080425  jnz     loc_1400805DF
0x14008042b  mov     rcx, rsi; struct tagTHREADINFO *
0x14008042e  call    ?BroadcastCoreMessagingApcContextError@@YAXPEBUtagTHREADINFO@@_K@Z; BroadcastCoreMessagingApcContextError(tagTHREADINFO const *,unsigned __int64)
0x140080433  mov     r12, [rsp+90h]
0x14008043b  test    r14d, r14d
0x14008043e  mov     r14, [rsp+0A0h+var_18]
0x140080446  jz      short loc_140080484
0x140080448  mov     r8, [rsi+660h]
0x14008044f  xor     r9d, r9d
0x140080452  mov     rdx, [rsi+650h]
0x140080459  mov     rcx, [rsi+668h]
0x140080460  mov     [rsp+38h], r15
0x140080465  mov     [rsp+0A0h+var_70], r15
0x14008046a  mov     dword ptr [rsp+0A0h+var_78], r15d
0x14008046f  mov     [rsp+0A0h+var_80], 0FFFFFFFF80000000h
0x140080478  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14008047f  nop     dword ptr [rax+rax+00h]
0x140080484  mov     rsi, [rsp+0A0h+arg_10]
0x14008048c  and     edi, 5DFFh
0x140080492  call    cs:__imp_?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ; DLT_THREADINFO::getDLT(void)
0x140080499  nop     dword ptr [rax+rax+00h]
0x14008049e  mov     ecx, eax
0x1400804a0  call    cs:__imp_?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z; GetDomainLockRef(DomainLockType)
0x1400804a7  nop     dword ptr [rax+rax+00h]
0x1400804ac  mov     [rbp+57h+var_60.KeyContext], rax
0x1400804b0  mov     byte ptr [rbp+57h+var_60.ApcContext], r15b
0x1400804b4  call    cs:__imp_W32GetUserSessionState
0x1400804bb  nop     dword ptr [rax+rax+00h]
0x1400804c0  xorps   xmm0, xmm0
0x1400804c3  mov     byte ptr [rbp+57h+var_60.IoStatusBlock.Information], r15b
0x1400804c7  add     rax, 0A4C8h
0x1400804cd  mov     [rbp+57h+var_30], r15b
0x1400804d1  mov     qword ptr [rbp+57h+var_60.IoStatusBlock], rax
0x1400804d5  movups  [rbp+57h+var_40], xmm0
0x1400804d9  call    cs:__imp_W32GetUserSessionState
0x1400804e0  nop     dword ptr [rax+rax+00h]
0x1400804e5  mov     rdx, r15
0x1400804e8  lea     rcx, [rbx+1A8h]
0x1400804ef  mov     r15, [rsp+0A0h+var_20]
0x1400804f7  add     rax, 0A380h
0x1400804fd  cmp     rbx, rax
0x140080500  cmovnz  rdx, rcx
0x140080504  cmp     [rbp+57h+var_30], 0
0x140080508  mov     qword ptr [rbp+57h+var_40], rdx
0x14008050c  jnz     short loc_140080546
0x14008050e  mov     rcx, [rbp+57h+var_60.KeyContext]
0x140080512  test    rcx, rcx
0x140080515  jz      short loc_14008052D
0x140080517  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x14008051b  jnz     loc_1400805FE
0x140080521  call    cs:__imp_?LockShared@tagDomLock@@QEBAXXZ; tagDomLock::LockShared(void)
0x140080528  nop     dword ptr [rax+rax+00h]
0x14008052d  mov     rcx, qword ptr [rbp+57h+var_40]
0x140080531  test    rcx, rcx
0x140080534  jz      short loc_140080542
0x140080536  call    cs:__imp_?LockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::LockExclusive(void)
0x14008053d  nop     dword ptr [rax+rax+00h]
0x140080542  mov     [rbp+57h+var_30], 1
0x140080546  mov     rax, [rbx+1E0h]
0x14008054d  mov     ecx, edi
0x14008054f  not     ecx
0x140080551  mov     edx, [rax+4]
0x140080554  mov     rax, [rbx+1E0h]
0x14008055b  lock and [rax+4], ecx
0x14008055f  mov     rax, [rbx+1E0h]
0x140080566  mov     ecx, [rax+8]
0x140080569  movzx   ebx, cx
0x14008056c  and     ebx, edi
0x14008056e  movzx   eax, dx
0x140080571  and     eax, edi
0x140080573  shl     ebx, 10h
0x140080576  mov     rdi, [rsp+0A0h+arg_18]
0x14008057e  or      ebx, eax
0x140080580  cmp     [rbp+57h+var_30], 0
0x140080584  jz      short loc_1400805B6
0x140080586  mov     rcx, qword ptr [rbp+57h+var_40]
0x14008058a  test    rcx, rcx
0x14008058d  jz      short loc_14008059B
0x14008058f  call    cs:__imp_?UnLockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::UnLockExclusive(void)
0x140080596  nop     dword ptr [rax+rax+00h]
0x14008059b  mov     rcx, [rbp+57h+var_60.KeyContext]
0x14008059f  test    rcx, rcx
0x1400805a2  jz      short loc_1400805B6
0x1400805a4  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x1400805a8  jnz     short loc_1400805F0
0x1400805aa  call    cs:__imp_?UnLockShared@tagDomLock@@QEBAXXZ; tagDomLock::UnLockShared(void)
0x1400805b1  nop     dword ptr [rax+rax+00h]
0x1400805b6  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400805bd  nop     dword ptr [rax+rax+00h]
0x1400805c2  mov     eax, ebx
0x1400805c4  add     rsp, 98h
0x1400805cb  pop     rbx
0x1400805cc  pop     rbp
0x1400805cd  retn
0x1400805cf  mov     rbx, r15
0x1400805d2  jmp     loc_140080328
0x1400805d7  mov     rsi, r15
0x1400805da  jmp     loc_14008037E
0x1400805df  mov     r8, r12; unsigned __int64
0x1400805e2  lea     rdx, [rbp+57h+var_60]; struct _FILE_IO_COMPLETION_INFORMATION *
0x1400805e6  call    ?xxxHandleCoreMessagingQueueCompletion@@YAXPEAUtagWND@@QEAU_FILE_IO_COMPLETION_INFORMATION@@_K@Z; xxxHandleCoreMessagingQueueCompletion(tagWND *,_FILE_IO_COMPLETION_INFORMATION * const,unsigned __int64)
0x1400805eb  jmp     loc_1400803C8
0x1400805f0  call    cs:__imp_?UnLockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::UnLockExclusive(void)
0x1400805f7  nop     dword ptr [rax+rax+00h]
0x1400805fc  jmp     short loc_1400805B6
0x1400805fe  call    cs:__imp_?LockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::LockExclusive(void)
0x140080605  nop     dword ptr [rax+rax+00h]
0x14008060a  jmp     loc_14008052D
```
