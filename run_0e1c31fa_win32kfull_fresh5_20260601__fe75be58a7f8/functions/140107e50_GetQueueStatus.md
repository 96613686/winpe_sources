# _GetQueueStatus

- ea: `0x140107e50`
- end: `0x14010816b`
- name: `_GetQueueStatus`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1401f7e60`

## callees

- `0x140107e50`
- `0x1401085e8`
- `0x140109814`

## import_xrefs

- `ntoskrnl!ZwSetIoCompletionEx` at `0x140107f13`
- `ntoskrnl!ZwSetIoCompletionEx` at `0x140107f13`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x140107f48`
- `ntoskrnl!ZwRemoveIoCompletionEx` at `0x140107f48`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140107fd5`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140107fd5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140107e6a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140107ec3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140107e6a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140107ec3`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140107fef`
- `win32kbase!?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ` at `0x140107fef`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x140107ffd`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x140107ffd`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x140108093`
- `win32kbase!?LockExclusive@tagObjLock@@QEBAXXZ` at `0x140108093`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14010807e`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14010807e`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14010815a`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14010815a`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x140108107`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x140108107`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x140108141`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x140108141`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x1401080ec`
- `win32kbase!?UnLockExclusive@tagObjLock@@QEBAXXZ` at `0x1401080ec`
- `WIN32K!W32GetUserSessionState` at `0x140108011`
- `WIN32K!W32GetUserSessionState` at `0x140108036`
- `WIN32K!W32GetUserSessionState` at `0x140108011`
- `WIN32K!W32GetUserSessionState` at `0x140108036`

## pseudocode

```c
__int64 __fastcall GetQueueStatus(__int64 a1)
{
  __int16 v1; // di
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v3; // rbx
  __int64 i; // rcx
  const struct tagTHREADINFO **v5; // rax
  const struct tagTHREADINFO *v6; // rsi
  int v7; // r14d
  struct tagWND *v8; // rcx
  int v9; // edi
  unsigned int DLT; // eax
  __int64 v11; // rcx
  __int64 UserSessionState; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // edx
  unsigned int v17; // ebx
  int v19; // [rsp+30h] [rbp-21h]
  struct _FILE_IO_COMPLETION_INFORMATION v20; // [rsp+48h] [rbp-9h] BYREF
  __int128 v21; // [rsp+68h] [rbp+17h]
  char v22; // [rsp+78h] [rbp+27h]
  int v23; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v24; // [rsp+C0h] [rbp+6Fh] BYREF

  v1 = a1;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(a1);
  if ( CurrentThreadWin32Thread )
    v3 = *CurrentThreadWin32Thread;
  else
    v3 = 0;
  for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
  {
    if ( *(_QWORD *)(v3 + 8LL * (unsigned int)i + 1656) )
    {
      if ( (v1 & 8) != 0 )
      {
        v5 = (const struct tagTHREADINFO **)PsGetCurrentThreadWin32Thread(i);
        if ( v5 )
          v6 = *v5;
        else
          v6 = 0;
        v23 = 0;
        memset(&v20, 0, sizeof(v20));
        v24 = 0;
        v7 = 0;
        ZwSetIoCompletionEx(*((_QWORD *)v6 + 202), *((_QWORD *)v6 + 206), 0, -2147483647, 0, 0);
        while ( 1 )
        {
          LOBYTE(v19) = 0;
          if ( (unsigned int)ZwRemoveIoCompletionEx(*((_QWORD *)v6 + 202), &v20, 1, &v23, &v24, v19) )
            break;
          if ( ((__int64)v20.ApcContext & 0x80000000) != 0 )
          {
            if ( LODWORD(v20.ApcContext) != 0x80000000 )
              break;
            v7 = 1;
          }
          else
          {
            if ( v20.ApcContext >= (PVOID)2
              || (v8 = (struct tagWND *)*((_QWORD *)v6 + (__int64)v20.ApcContext + 207)) == 0 )
            {
              BroadcastCoreMessagingApcContextError(v6, (unsigned __int64)v20.ApcContext);
              break;
            }
            xxxHandleCoreMessagingQueueCompletion(v8, &v20, 0x80000000);
          }
        }
        if ( v7 )
          ZwAssociateWaitCompletionPacket(
            *((_QWORD *)v6 + 205),
            *((_QWORD *)v6 + 202),
            *((_QWORD *)v6 + 204),
            0,
            0xFFFFFFFF80000000uLL,
            0,
            0,
            0,
            v20.KeyContext,
            v20.ApcContext);
      }
      break;
    }
  }
  v9 = v1 & 0x5DFF;
  DLT = DLT_THREADINFO::getDLT();
  v20.KeyContext = (PVOID)GetDomainLockRef(DLT);
  LOBYTE(v20.ApcContext) = 0;
  UserSessionState = W32GetUserSessionState(v11);
  LOBYTE(v20.IoStatusBlock.Information) = 0;
  v22 = 0;
  v20.IoStatusBlock.Pointer = (PVOID)(UserSessionState + 42184);
  v21 = 0;
  v14 = W32GetUserSessionState(v13);
  v15 = 0;
  if ( v3 != v14 + 41856 )
    v15 = v3 + 424;
  *(_QWORD *)&v21 = v15;
  if ( !v22 )
  {
    if ( v20.KeyContext )
    {
      if ( LOBYTE(v20.ApcContext) )
        tagDomLock::LockExclusive((tagDomLock *)v20.KeyContext);
      else
        tagDomLock::LockShared((tagDomLock *)v20.KeyContext);
    }
    if ( (_QWORD)v21 )
      tagObjLock::LockExclusive((tagObjLock *)v21);
    v22 = 1;
  }
  v16 = *(_DWORD *)(*(_QWORD *)(v3 + 480) + 4LL);
  _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v3 + 480) + 4LL), ~v9);
  v17 = (unsigned __int16)(v9 & v16) | ((unsigned __int16)(v9 & *(_DWORD *)(*(_QWORD *)(v3 + 480) + 8LL)) << 16);
  if ( !v22 )
    return v17;
  if ( (_QWORD)v21 )
    tagObjLock::UnLockExclusive((tagObjLock *)v21);
  if ( !v20.KeyContext )
    return v17;
  if ( !LOBYTE(v20.ApcContext) )
  {
    tagDomLock::UnLockShared((tagDomLock *)v20.KeyContext);
    return v17;
  }
  tagDomLock::UnLockExclusive((tagDomLock *)v20.KeyContext);
  return v17;
}

```

## disassembly

```asm
0x140107e50  mov     rax, rsp
0x140107e53  push    rbp
0x140107e54  push    rbx
0x140107e55  lea     rbp, [rax-5Fh]
0x140107e59  sub     rsp, 98h
0x140107e60  mov     [rax+20h], rdi
0x140107e64  mov     edi, ecx
0x140107e66  mov     [rax-28h], r15
0x140107e6a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140107e71  nop     dword ptr [rax+rax+00h]
0x140107e76  xor     r15d, r15d
0x140107e79  test    rax, rax
0x140107e7c  jz      loc_140108120
0x140107e82  mov     rbx, [rax]
0x140107e85  mov     ecx, r15d
0x140107e88  cmp     ecx, 2
0x140107e8b  jnb     loc_140107FE9
0x140107e91  mov     eax, ecx
0x140107e93  cmp     [rbx+rax*8+678h], r15
0x140107e9b  jnz     short loc_140107EA1
0x140107e9d  inc     ecx
0x140107e9f  jmp     short loc_140107E88
0x140107ea1  test    dil, 8
0x140107ea5  jz      loc_140107FE9
0x140107eab  mov     [rsp+0A0h+arg_10], rsi
0x140107eb3  mov     [rsp+90h], r12
0x140107ebb  mov     [rsp+0A0h+var_18], r14
0x140107ec3  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140107eca  nop     dword ptr [rax+rax+00h]
0x140107ecf  test    rax, rax
0x140107ed2  jz      loc_140108128
0x140107ed8  mov     rsi, [rax]
0x140107edb  xorps   xmm0, xmm0
0x140107ede  mov     [rbp+57h+arg_0], r15d
0x140107ee2  movups  xmmword ptr [rbp+57h+var_60.KeyContext], xmm0
0x140107ee6  mov     [rbp+57h+arg_8], r15
0x140107eea  mov     r9, 0FFFFFFFF80000001h
0x140107ef1  movups  xmmword ptr [rbp+57h+var_60.IoStatusBlock], xmm0
0x140107ef5  mov     rdx, [rsi+670h]
0x140107efc  xor     r8d, r8d
0x140107eff  mov     rcx, [rsi+650h]
0x140107f06  mov     r14d, r15d
0x140107f09  mov     [rsp+0A0h+var_78], r15
0x140107f0e  mov     dword ptr [rsp+0A0h+var_80], r15d
0x140107f13  call    cs:__imp_ZwSetIoCompletionEx
0x140107f1a  nop     dword ptr [rax+rax+00h]
0x140107f1f  mov     r12d, 80000000h
0x140107f25  mov     rcx, [rsi+650h]
0x140107f2c  lea     rax, [rbp+57h+arg_8]
0x140107f30  mov     byte ptr [rsp+0A0h+var_78], r15b
0x140107f35  lea     r9, [rbp+57h+arg_0]
0x140107f39  mov     r8d, 1
0x140107f3f  mov     [rsp+0A0h+var_80], rax
0x140107f44  lea     rdx, [rbp+57h+var_60]
0x140107f48  call    cs:__imp_ZwRemoveIoCompletionEx
0x140107f4f  nop     dword ptr [rax+rax+00h]
0x140107f54  test    eax, eax
0x140107f56  jnz     short loc_140107F90
0x140107f58  mov     rdx, [rbp+57h+var_60.ApcContext]; unsigned __int64
0x140107f5c  test    r12, rdx
0x140107f5f  jz      short loc_140107F71
0x140107f61  cmp     edx, 80000000h
0x140107f67  jnz     short loc_140107F90
0x140107f69  mov     r14d, 1
0x140107f6f  jmp     short loc_140107F25
0x140107f71  cmp     rdx, 2
0x140107f75  jnb     short loc_140107F88
0x140107f77  mov     rcx, [rsi+rdx*8+678h]; struct tagWND *
0x140107f7f  test    rcx, rcx
0x140107f82  jnz     loc_140108130
0x140107f88  mov     rcx, rsi; struct tagTHREADINFO *
0x140107f8b  call    ?BroadcastCoreMessagingApcContextError@@YAXPEBUtagTHREADINFO@@_K@Z; BroadcastCoreMessagingApcContextError(tagTHREADINFO const *,unsigned __int64)
0x140107f90  mov     r12, [rsp+90h]
0x140107f98  test    r14d, r14d
0x140107f9b  mov     r14, [rsp+0A0h+var_18]
0x140107fa3  jz      short loc_140107FE1
0x140107fa5  mov     r8, [rsi+660h]
0x140107fac  xor     r9d, r9d
0x140107faf  mov     rdx, [rsi+650h]
0x140107fb6  mov     rcx, [rsi+668h]
0x140107fbd  mov     [rsp+38h], r15
0x140107fc2  mov     [rsp+0A0h+var_70], r15
0x140107fc7  mov     dword ptr [rsp+0A0h+var_78], r15d
0x140107fcc  mov     [rsp+0A0h+var_80], 0FFFFFFFF80000000h
0x140107fd5  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x140107fdc  nop     dword ptr [rax+rax+00h]
0x140107fe1  mov     rsi, [rsp+0A0h+arg_10]
0x140107fe9  and     edi, 5DFFh
0x140107fef  call    cs:__imp_?getDLT@DLT_THREADINFO@@SA?AW4DomainLockType@@XZ; DLT_THREADINFO::getDLT(void)
0x140107ff6  nop     dword ptr [rax+rax+00h]
0x140107ffb  mov     ecx, eax
0x140107ffd  call    cs:__imp_?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z; GetDomainLockRef(DomainLockType)
0x140108004  nop     dword ptr [rax+rax+00h]
0x140108009  mov     [rbp+57h+var_60.KeyContext], rax
0x14010800d  mov     byte ptr [rbp+57h+var_60.ApcContext], r15b
0x140108011  call    cs:__imp_W32GetUserSessionState
0x140108018  nop     dword ptr [rax+rax+00h]
0x14010801d  xorps   xmm0, xmm0
0x140108020  mov     byte ptr [rbp+57h+var_60.IoStatusBlock.Information], r15b
0x140108024  add     rax, 0A4C8h
0x14010802a  mov     [rbp+57h+var_30], r15b
0x14010802e  mov     qword ptr [rbp+57h+var_60.IoStatusBlock], rax
0x140108032  movups  [rbp+57h+var_40], xmm0
0x140108036  call    cs:__imp_W32GetUserSessionState
0x14010803d  nop     dword ptr [rax+rax+00h]
0x140108042  mov     rdx, r15
0x140108045  lea     rcx, [rbx+1A8h]
0x14010804c  mov     r15, [rsp+0A0h+var_20]
0x140108054  add     rax, 0A380h
0x14010805a  cmp     rbx, rax
0x14010805d  cmovnz  rdx, rcx
0x140108061  cmp     [rbp+57h+var_30], 0
0x140108065  mov     qword ptr [rbp+57h+var_40], rdx
0x140108069  jnz     short loc_1401080A3
0x14010806b  mov     rcx, [rbp+57h+var_60.KeyContext]
0x14010806f  test    rcx, rcx
0x140108072  jz      short loc_14010808A
0x140108074  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x140108078  jnz     loc_14010815A
0x14010807e  call    cs:__imp_?LockShared@tagDomLock@@QEBAXXZ; tagDomLock::LockShared(void)
0x140108085  nop     dword ptr [rax+rax+00h]
0x14010808a  mov     rcx, qword ptr [rbp+57h+var_40]
0x14010808e  test    rcx, rcx
0x140108091  jz      short loc_14010809F
0x140108093  call    cs:__imp_?LockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::LockExclusive(void)
0x14010809a  nop     dword ptr [rax+rax+00h]
0x14010809f  mov     [rbp+57h+var_30], 1
0x1401080a3  mov     rax, [rbx+1E0h]
0x1401080aa  mov     ecx, edi
0x1401080ac  not     ecx
0x1401080ae  mov     edx, [rax+4]
0x1401080b1  mov     rax, [rbx+1E0h]
0x1401080b8  lock and [rax+4], ecx
0x1401080bc  mov     rax, [rbx+1E0h]
0x1401080c3  mov     ecx, [rax+8]
0x1401080c6  movzx   ebx, cx
0x1401080c9  and     ebx, edi
0x1401080cb  movzx   eax, dx
0x1401080ce  and     eax, edi
0x1401080d0  shl     ebx, 10h
0x1401080d3  mov     rdi, [rsp+0A0h+arg_18]
0x1401080db  or      ebx, eax
0x1401080dd  cmp     [rbp+57h+var_30], 0
0x1401080e1  jz      short loc_140108113
0x1401080e3  mov     rcx, qword ptr [rbp+57h+var_40]
0x1401080e7  test    rcx, rcx
0x1401080ea  jz      short loc_1401080F8
0x1401080ec  call    cs:__imp_?UnLockExclusive@tagObjLock@@QEBAXXZ; tagObjLock::UnLockExclusive(void)
0x1401080f3  nop     dword ptr [rax+rax+00h]
0x1401080f8  mov     rcx, [rbp+57h+var_60.KeyContext]
0x1401080fc  test    rcx, rcx
0x1401080ff  jz      short loc_140108113
0x140108101  cmp     byte ptr [rbp+57h+var_60.ApcContext], 0
0x140108105  jnz     short loc_140108141
0x140108107  call    cs:__imp_?UnLockShared@tagDomLock@@QEBAXXZ; tagDomLock::UnLockShared(void)
0x14010810e  nop     dword ptr [rax+rax+00h]
0x140108113  mov     eax, ebx
0x140108115  add     rsp, 98h
0x14010811c  pop     rbx
0x14010811d  pop     rbp
0x14010811e  retn
0x140108120  mov     rbx, r15
0x140108123  jmp     loc_140107E85
0x140108128  mov     rsi, r15
0x14010812b  jmp     loc_140107EDB
0x140108130  mov     r8, r12; unsigned __int64
0x140108133  lea     rdx, [rbp+57h+var_60]; struct _FILE_IO_COMPLETION_INFORMATION *
0x140108137  call    ?xxxHandleCoreMessagingQueueCompletion@@YAXPEAUtagWND@@QEAU_FILE_IO_COMPLETION_INFORMATION@@_K@Z; xxxHandleCoreMessagingQueueCompletion(tagWND *,_FILE_IO_COMPLETION_INFORMATION * const,unsigned __int64)
0x14010813c  jmp     loc_140107F25
0x140108141  call    cs:__imp_?UnLockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::UnLockExclusive(void)
0x140108148  nop     dword ptr [rax+rax+00h]
0x14010814d  mov     eax, ebx
0x14010814f  add     rsp, 98h
0x140108156  pop     rbx
0x140108157  pop     rbp
0x140108158  retn
0x14010815a  call    cs:__imp_?LockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::LockExclusive(void)
0x140108161  nop     dword ptr [rax+rax+00h]
0x140108166  jmp     loc_14010808A
```
