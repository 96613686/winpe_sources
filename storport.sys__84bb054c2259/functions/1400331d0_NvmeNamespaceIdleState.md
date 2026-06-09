# NvmeNamespaceIdleState

- ea: `0x1400331d0`
- end: `0x1400333ff`
- name: `NvmeNamespaceIdleState`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007d9a0`

## callees

- `0x1400331d0`
- `0x140033410`
- `0x140033454`
- `0x14003348c`
- `0x140067e24`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033336`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033336`
- `ntoskrnl!PoFxIdleComponent` at `0x140033398`
- `ntoskrnl!PoFxIdleComponent` at `0x140033398`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400332f1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400332f1`
- `ntoskrnl!PoFxActivateComponent` at `0x1400332c7`
- `ntoskrnl!PoFxActivateComponent` at `0x1400332c7`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400333dd`
- `ntoskrnl!PoFxCompleteIdleState` at `0x1400333dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033347`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400333ab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140033347`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400333ab`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceIdleState(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v4; // rax
  __int64 v7; // rdi
  __int64 result; // rax
  unsigned int v9; // ebp
  _DWORD *StorPoFxComponent; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // r10d
  int v15; // eax
  __int64 v16; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v7 = *(_QWORD *)(v4 + 128);
  result = NvmeNamespaceCheckAndAcquirePoFx(a1);
  if ( (_BYTE)result )
  {
    v9 = 1;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) + 16LL) = a3;
    if ( *(_DWORD *)(a1 + 276) && a3 )
      NvmeUpdateCrashDumpPowerReady(v7);
    StorPoFxComponent = (_DWORD *)RaidGetStorPoFxComponent(
                                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 8LL) + 8LL),
                                    a2,
                                    *(_QWORD *)(a1 + 128));
    if ( StorPoFxComponent && *StorPoFxComponent == 2 )
      v9 = StorPoFxComponent[8];
    v13 = *(_QWORD *)(v7 + 168);
    v14 = *(_DWORD *)(v13 + 176);
    if ( (v14 & 1) != 0 )
      v9 = 1;
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 408) + 184LL) & 0x40000000) == 0 )
      goto LABEL_27;
    v15 = *(_DWORD *)(v12 + 32);
    if ( (v15 & 2) != 0 )
    {
      if ( a3 <= v9 )
      {
        if ( *(_BYTE *)v13 != 1 )
          goto LABEL_27;
        goto LABEL_14;
      }
      if ( *(_BYTE *)v13 != 1 )
        goto LABEL_27;
    }
    else
    {
      if ( (v14 & 0x20) == 0 || (v15 & 0x200) == 0 || *(_BYTE *)v13 != 1 )
        goto LABEL_27;
      if ( !a3 )
      {
LABEL_14:
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v11 + 96), 1, 0) )
        {
          PoFxActivateComponent(**(_QWORD **)(*(_QWORD *)(v7 + 168) + 8LL), 0, 0);
          v16 = *(_QWORD *)(v7 + 168);
          if ( *(_BYTE *)(*(_QWORD *)(v16 + 8) + 64LL) != 1 )
          {
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v16 + 120), &LockHandle);
            if ( *(int *)(*(_QWORD *)(v7 + 168) + 68LL) > 1 )
            {
              *(_BYTE *)(*(_QWORD *)(a1 + 128) + 50LL) |= 1u;
              *(_WORD *)(*(_QWORD *)(a1 + 128) + 48LL) = a3;
              ExpInterlockedPushEntrySList((PSLIST_HEADER)(*(_QWORD *)(v7 + 168) + 96LL), (PSLIST_ENTRY)(a1 + 144));
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              return NvmeNamespaceReleasePoFx(a1);
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
          }
        }
LABEL_27:
        if ( *(_DWORD *)(a1 + 276) )
        {
          if ( !a3 )
            NvmeUpdateCrashDumpPowerReady(v7);
        }
        PoFxCompleteIdleState(**(_QWORD **)(*(_QWORD *)(a1 + 128) + 8LL), a2);
        return NvmeNamespaceReleasePoFx(a1);
      }
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 96), 0, 1) == 1 )
      PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v7 + 168) + 8LL), 0, 0);
    goto LABEL_27;
  }
  return result;
}

```

## disassembly

```asm
0x1400331d0  push    rbx
0x1400331d2  push    rbp
0x1400331d3  push    rsi
0x1400331d4  push    rdi
0x1400331d5  push    r14
0x1400331d7  push    r15
0x1400331d9  sub     rsp, 48h
0x1400331dd  xor     eax, eax
0x1400331df  xorps   xmm0, xmm0
0x1400331e2  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400331e7  mov     esi, r8d
0x1400331ea  mov     rax, [rcx+10h]
0x1400331ee  mov     r14d, edx
0x1400331f1  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400331f6  mov     rbx, rcx
0x1400331f9  mov     rdi, [rax+80h]
0x140033200  call    NvmeNamespaceCheckAndAcquirePoFx
0x140033205  test    al, al
0x140033207  jz      loc_1400333F1
0x14003320d  mov     rax, [rbx+80h]
0x140033214  mov     r15d, 1
0x14003321a  mov     ebp, r15d
0x14003321d  mov     rcx, [rax+8]
0x140033221  mov     [rcx+10h], esi
0x140033224  cmp     dword ptr [rbx+114h], 0
0x14003322b  jbe     short loc_140033239
0x14003322d  test    esi, esi
0x14003322f  jz      short loc_140033239
0x140033231  mov     rcx, rdi
0x140033234  call    NvmeUpdateCrashDumpPowerReady
0x140033239  mov     r8, [rbx+80h]
0x140033240  mov     edx, r14d
0x140033243  mov     r9, [r8+8]
0x140033247  mov     rcx, [r9+8]
0x14003324b  call    RaidGetStorPoFxComponent
0x140033250  test    rax, rax
0x140033253  jz      short loc_14003325D
0x140033255  cmp     dword ptr [rax], 2
0x140033258  jnz     short loc_14003325D
0x14003325a  mov     ebp, [rax+20h]
0x14003325d  mov     rdx, [rdi+0A8h]
0x140033264  mov     rax, [rdi+198h]
0x14003326b  mov     r10d, [rdx+0B0h]
0x140033272  test    r15b, r10b
0x140033275  cmovnz  ebp, r15d
0x140033279  test    dword ptr [rax+0B8h], 40000000h
0x140033283  jz      loc_1400333B7
0x140033289  mov     eax, [r9+20h]
0x14003328d  test    al, 2
0x14003328f  jz      loc_14003335F
0x140033295  cmp     esi, ebp
0x140033297  ja      loc_140033358
0x14003329d  cmp     [rdx], r15b
0x1400332a0  jnz     loc_1400333B7
0x1400332a6  xor     eax, eax
0x1400332a8  lock cmpxchg [r8+60h], r15d
0x1400332ae  jnz     loc_1400333B7
0x1400332b4  mov     rax, [rdi+0A8h]
0x1400332bb  xor     r8d, r8d
0x1400332be  xor     edx, edx
0x1400332c0  mov     rcx, [rax+8]
0x1400332c4  mov     rcx, [rcx]
0x1400332c7  call    cs:__imp_PoFxActivateComponent
0x1400332ce  nop     dword ptr [rax+rax+00h]
0x1400332d3  mov     rcx, [rdi+0A8h]
0x1400332da  mov     rax, [rcx+8]
0x1400332de  cmp     [rax+40h], r15b
0x1400332e2  jz      loc_1400333B7
0x1400332e8  add     rcx, 78h ; 'x'; SpinLock
0x1400332ec  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400332f1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400332f8  nop     dword ptr [rax+rax+00h]
0x1400332fd  mov     rax, [rdi+0A8h]
0x140033304  cmp     [rax+44h], r15d
0x140033308  jle     loc_1400333A6
0x14003330e  mov     rax, [rbx+80h]
0x140033315  lea     rdx, [rbx+90h]; ListEntry
0x14003331c  or      [rax+32h], r15b
0x140033320  mov     rax, [rbx+80h]
0x140033327  mov     [rax+30h], si
0x14003332b  mov     rcx, [rdi+0A8h]
0x140033332  add     rcx, 60h ; '`'; ListHead
0x140033336  call    cs:__imp_ExpInterlockedPushEntrySList
0x14003333d  nop     dword ptr [rax+rax+00h]
0x140033342  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140033347  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003334e  nop     dword ptr [rax+rax+00h]
0x140033353  jmp     loc_1400333E9
0x140033358  cmp     [rdx], r15b
0x14003335b  jz      short loc_140033378
0x14003335d  jmp     short loc_1400333B7
0x14003335f  test    r10b, 20h
0x140033363  jz      short loc_1400333B7
0x140033365  bt      eax, 9
0x140033369  jnb     short loc_1400333B7
0x14003336b  cmp     [rdx], r15b
0x14003336e  jnz     short loc_1400333B7
0x140033370  test    esi, esi
0x140033372  jz      loc_1400332A6
0x140033378  xor     ecx, ecx
0x14003337a  mov     eax, r15d
0x14003337d  lock cmpxchg [r8+60h], ecx
0x140033383  jnz     short loc_1400333B7
0x140033385  mov     rax, [rdi+0A8h]
0x14003338c  xor     r8d, r8d
0x14003338f  xor     edx, edx
0x140033391  mov     rcx, [rax+8]
0x140033395  mov     rcx, [rcx]
0x140033398  call    cs:__imp_PoFxIdleComponent
0x14003339f  nop     dword ptr [rax+rax+00h]
0x1400333a4  jmp     short loc_1400333B7
0x1400333a6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400333ab  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400333b2  nop     dword ptr [rax+rax+00h]
0x1400333b7  cmp     dword ptr [rbx+114h], 0
0x1400333be  jbe     short loc_1400333CC
0x1400333c0  test    esi, esi
0x1400333c2  jnz     short loc_1400333CC
0x1400333c4  mov     rcx, rdi
0x1400333c7  call    NvmeUpdateCrashDumpPowerReady
0x1400333cc  mov     rax, [rbx+80h]
0x1400333d3  mov     edx, r14d
0x1400333d6  mov     rcx, [rax+8]
0x1400333da  mov     rcx, [rcx]
0x1400333dd  call    cs:__imp_PoFxCompleteIdleState
0x1400333e4  nop     dword ptr [rax+rax+00h]
0x1400333e9  mov     rcx, rbx
0x1400333ec  call    NvmeNamespaceReleasePoFx
0x1400333f1  add     rsp, 48h
0x1400333f5  pop     r15
0x1400333f7  pop     r14
0x1400333f9  pop     rdi
0x1400333fa  pop     rsi
0x1400333fb  pop     rbp
0x1400333fc  pop     rbx
0x1400333fd  retn
```
