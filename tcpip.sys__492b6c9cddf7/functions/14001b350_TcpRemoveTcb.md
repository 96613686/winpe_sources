# TcpRemoveTcb

- ea: `0x14001b350`
- end: `0x14001b63d`
- name: `TcpRemoveTcb`
- size: `749`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400064f8`
- `0x1400074c8`
- `0x14000a9d4`

## callees

- `0x14001a390`
- `0x14001b350`
- `0x14001b644`
- `0x14001bed0`
- `0x140055780`
- `0x1400b07b0`
- `0x14014e224`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b39e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b54b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b39e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b54b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b511`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b5bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b511`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b5bf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b443`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b443`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b3bc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b595`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b3bc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b595`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b49a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b49a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4c1`

## pseudocode

```c
void __fastcall TcpRemoveTcb(__int64 a1, __int64 a2, char a3)
{
  __int64 PartitionFromKey; // r14
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rsi
  __int64 v10; // rdi
  bool v11; // zf
  void *v12; // rdi
  __int16 v13; // r15
  __int64 v14; // rax
  __int64 v15; // r12
  PKSPIN_LOCK v16; // rbx
  unsigned int v17; // edx
  __int64 v18; // rdx
  __int16 v19; // r15
  PKSPIN_LOCK v20; // rbx
  __int64 v21; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE v23; // [rsp+38h] [rbp-40h] BYREF
  __int64 v24; // [rsp+80h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 120) &= ~2u;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a2 )
  {
    PartitionFromKey = a2;
  }
  else
  {
    v13 = PartitionCount;
    v14 = 88;
    if ( !a3 )
      v14 = 64;
    v15 = *(_QWORD *)(v14 + a1);
    PartitionFromKey = TcpGetPartitionFromKey(v15);
    v16 = *(PKSPIN_LOCK *)PartitionFromKey;
    KeAcquireInStackQueuedSpinLockAtDpcLevel(*(PKSPIN_LOCK *)PartitionFromKey, &LockHandle);
    while ( *((_DWORD *)v16 + 2) )
      ;
    if ( v13 != PartitionCount )
    {
      do
      {
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        v19 = PartitionCount;
        PartitionFromKey = TcpGetPartitionFromKey(v15);
        v20 = *(PKSPIN_LOCK *)PartitionFromKey;
        KeAcquireInStackQueuedSpinLockAtDpcLevel(*(PKSPIN_LOCK *)PartitionFromKey, &LockHandle);
        while ( *((_DWORD *)v20 + 2) )
          ;
      }
      while ( v19 != PartitionCount );
    }
  }
  if ( a3 )
  {
    RtlRemoveEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(PartitionFromKey + 16),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 72),
      0);
  }
  else
  {
    RtlRemoveEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(PartitionFromKey + 8),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 48),
      0);
    v17 = *(_DWORD *)(a1 + 808);
    if ( (v17 & 8) != 0 )
    {
      v18 = v17 >> 4;
      LOBYTE(v18) = v18 & 1;
      TcpDropSynRcvdFromPartition(PartitionFromKey, v18, (*(_WORD *)(a1 + 128) & 0x1000) != 0);
    }
  }
  if ( !a2 )
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( !a3 )
  {
    v7 = *(_QWORD *)(a1 + 904);
    if ( v7 )
    {
      v8 = *(_DWORD *)(v7 + 48);
      memset(&v23, 0, sizeof(v23));
      if ( (v8 & 4) != 0 )
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v7 + 352) + 32LL) + 36LL));
      if ( (unsigned int)AleNotifyEndpointDeactivate(v7, a1, 3) != 259 )
      {
        v9 = 0;
        v24 = 0;
        v10 = 0;
        if ( gAleDebugEnabled )
        {
          v21 = WfpPoolAllocNonPaged(34, 1281715265, &v24);
          v10 = v24;
          v9 = v21;
          if ( !v21 )
            WfpStringCchCopyA("WfpAleEndpointDeactivationHandler", 34, v24);
        }
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v7, &v23);
        while ( *(_DWORD *)(v7 + 8) )
          ;
        v11 = gAleDebugEnabled == 1;
        *(_QWORD *)(v7 + 16) = KeGetCurrentThread();
        if ( v11 && !v9 )
          *(_QWORD *)(v7 + 24) = v10;
        WfpAleDisableWaitRef(v7 + 128);
        v11 = gAleDebugEnabled == 1;
        v12 = 0;
        *(_QWORD *)(v7 + 16) = 0;
        if ( v11 )
        {
          v12 = *(void **)(v7 + 24);
          *(_QWORD *)(v7 + 24) = 0;
        }
        KeReleaseInStackQueuedSpinLock(&v23);
        if ( gAleDebugEnabled == 1 )
        {
          if ( v12 )
            ExFreePoolWithTag(v12, 0);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14001b350  push    rbx
0x14001b352  push    rbp
0x14001b353  push    rsi
0x14001b354  push    rdi
0x14001b355  sub     rsp, 58h
0x14001b359  and     dword ptr [rcx+78h], 0FFFFFFFDh
0x14001b35d  xor     eax, eax
0x14001b35f  mov     [rsp+78h+arg_10], r14
0x14001b367  xorps   xmm0, xmm0
0x14001b36a  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14001b36f  movzx   ebp, r8b
0x14001b373  mov     rsi, rdx
0x14001b376  mov     rdi, rcx
0x14001b379  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14001b37e  test    rdx, rdx
0x14001b381  jz      loc_14001B4D2
0x14001b387  mov     r14, rdx
0x14001b38a  xor     r8d, r8d; Context
0x14001b38d  test    bpl, bpl
0x14001b390  jz      loc_14001B543
0x14001b396  mov     rcx, [r14+10h]; HashTable
0x14001b39a  lea     rdx, [rdi+48h]; Entry
0x14001b39e  call    cs:__imp_RtlRemoveEntryHashTable
0x14001b3a5  nop     dword ptr [rax+rax+00h]
0x14001b3aa  mov     r14, [rsp+78h+arg_10]
0x14001b3b2  test    rsi, rsi
0x14001b3b5  jnz     short loc_14001B3C8
0x14001b3b7  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14001b3bc  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001b3c3  nop     dword ptr [rax+rax+00h]
0x14001b3c8  test    bpl, bpl
0x14001b3cb  jz      short loc_14001B3D7
0x14001b3cd  add     rsp, 58h
0x14001b3d1  pop     rdi
0x14001b3d2  pop     rsi
0x14001b3d3  pop     rbp
0x14001b3d4  pop     rbx
0x14001b3d5  retn
0x14001b3d7  mov     rbx, [rdi+388h]
0x14001b3de  test    rbx, rbx
0x14001b3e1  jz      short loc_14001B3CD
0x14001b3e3  xor     eax, eax
0x14001b3e5  xorps   xmm0, xmm0
0x14001b3e8  mov     qword ptr [rsp+78h+var_40.OldIrql], rax
0x14001b3ed  mov     eax, [rbx+30h]
0x14001b3f0  movups  xmmword ptr [rsp+78h+var_40.LockQueue.Next], xmm0
0x14001b3f5  test    al, 4
0x14001b3f7  jz      short loc_14001B408
0x14001b3f9  mov     rax, [rbx+160h]
0x14001b400  mov     rcx, [rax+20h]
0x14001b404  lock dec dword ptr [rcx+24h]
0x14001b408  mov     r8d, 3
0x14001b40e  mov     rdx, rdi
0x14001b411  mov     rcx, rbx
0x14001b414  call    AleNotifyEndpointDeactivate
0x14001b419  cmp     eax, 103h
0x14001b41e  jz      short loc_14001B3CD
0x14001b420  xor     ebp, ebp
0x14001b422  mov     esi, ebp
0x14001b424  mov     [rsp+78h+arg_0], rbp
0x14001b42c  cmp     cs:gAleDebugEnabled, sil
0x14001b433  mov     edi, ebp
0x14001b435  jnz     loc_14001B5E7
0x14001b43b  lea     rdx, [rsp+78h+var_40]; LockHandle
0x14001b440  mov     rcx, rbx; SpinLock
0x14001b443  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001b44a  nop     dword ptr [rax+rax+00h]
0x14001b44f  nop
0x14001b450  mov     eax, [rbx+8]
0x14001b453  test    eax, eax
0x14001b455  jnz     short loc_14001B450
0x14001b457  mov     rax, gs:188h
0x14001b460  cmp     cs:gAleDebugEnabled, 1
0x14001b467  mov     [rbx+10h], rax
0x14001b46b  jz      loc_14001B62B
0x14001b471  lea     rcx, [rbx+80h]
0x14001b478  call    WfpAleDisableWaitRef
0x14001b47d  cmp     cs:gAleDebugEnabled, 1
0x14001b484  mov     rdi, rbp
0x14001b487  mov     [rbx+10h], rbp
0x14001b48b  jnz     short loc_14001B495
0x14001b48d  mov     rdi, [rbx+18h]
0x14001b491  mov     [rbx+18h], rbp
0x14001b495  lea     rcx, [rsp+78h+var_40]; LockHandle
0x14001b49a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b4a1  nop     dword ptr [rax+rax+00h]
0x14001b4a6  cmp     cs:gAleDebugEnabled, 1
0x14001b4ad  jnz     loc_14001B3CD
0x14001b4b3  test    rdi, rdi
0x14001b4b6  jz      loc_14001B3CD
0x14001b4bc  xor     edx, edx; Tag
0x14001b4be  mov     rcx, rdi; P
0x14001b4c1  call    cs:__imp_ExFreePoolWithTag
0x14001b4c8  nop     dword ptr [rax+rax+00h]
0x14001b4cd  jmp     loc_14001B3CD
0x14001b4d2  mov     ecx, 40h ; '@'
0x14001b4d7  mov     [rsp+78h+arg_8], r12
0x14001b4df  mov     [rsp+78h+var_28], r15
0x14001b4e4  test    bpl, bpl
0x14001b4e7  movzx   r15d, cs:PartitionCount
0x14001b4ef  mov     eax, 58h ; 'X'
0x14001b4f4  cmovz   eax, ecx
0x14001b4f7  mov     r12, [rax+rdi]
0x14001b4fb  mov     rcx, r12
0x14001b4fe  call    TcpGetPartitionFromKey
0x14001b503  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14001b508  mov     r14, rax
0x14001b50b  mov     rbx, [rax]
0x14001b50e  mov     rcx, rbx; SpinLock
0x14001b511  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001b518  nop     dword ptr [rax+rax+00h]
0x14001b51d  nop     dword ptr [rax]
0x14001b520  mov     eax, [rbx+8]
0x14001b523  test    eax, eax
0x14001b525  jnz     short loc_14001B520
0x14001b527  cmp     r15w, cs:PartitionCount
0x14001b52f  jnz     short loc_14001B590
0x14001b531  mov     r15, [rsp+78h+var_28]
0x14001b536  mov     r12, [rsp+78h+arg_8]
0x14001b53e  jmp     loc_14001B38A
0x14001b543  mov     rcx, [r14+8]; HashTable
0x14001b547  lea     rdx, [rdi+30h]; Entry
0x14001b54b  call    cs:__imp_RtlRemoveEntryHashTable
0x14001b552  nop     dword ptr [rax+rax+00h]
0x14001b557  mov     edx, [rdi+328h]
0x14001b55d  test    dl, 8
0x14001b560  jz      loc_14001B3AA
0x14001b566  movzx   r8d, word ptr [rdi+80h]
0x14001b56e  mov     rcx, r14
0x14001b571  shr     r8w, 0Ch
0x14001b576  shr     edx, 4
0x14001b579  and     r8b, 1
0x14001b57d  and     dl, 1
0x14001b580  call    TcpDropSynRcvdFromPartition
0x14001b585  jmp     loc_14001B3AA
0x14001b590  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14001b595  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001b59c  nop     dword ptr [rax+rax+00h]
0x14001b5a1  movzx   r15d, cs:PartitionCount
0x14001b5a9  mov     rcx, r12
0x14001b5ac  call    TcpGetPartitionFromKey
0x14001b5b1  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14001b5b6  mov     r14, rax
0x14001b5b9  mov     rbx, [rax]
0x14001b5bc  mov     rcx, rbx; SpinLock
0x14001b5bf  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001b5c6  nop     dword ptr [rax+rax+00h]
0x14001b5cb  nop     dword ptr [rax+rax+00h]
0x14001b5d0  mov     eax, [rbx+8]
0x14001b5d3  test    eax, eax
0x14001b5d5  jnz     short loc_14001B5D0
0x14001b5d7  cmp     r15w, cs:PartitionCount
0x14001b5df  jz      loc_14001B531
0x14001b5e5  jmp     short loc_14001B590
0x14001b5e7  lea     r8, [rsp+78h+arg_0]
0x14001b5ef  mov     edx, 4C656C41h
0x14001b5f4  mov     ecx, 22h ; '"'
0x14001b5f9  call    WfpPoolAllocNonPaged
0x14001b5fe  mov     rdi, [rsp+78h+arg_0]
0x14001b606  mov     rsi, rax
0x14001b609  test    rax, rax
0x14001b60c  jnz     loc_14001B43B
0x14001b612  mov     r8, rdi
0x14001b615  lea     rcx, aWfpaleendpoint_1; "WfpAleEndpointDeactivationHandler"
0x14001b61c  mov     edx, 22h ; '"'
0x14001b621  call    WfpStringCchCopyA
0x14001b626  jmp     loc_14001B43B
0x14001b62b  test    rsi, rsi
0x14001b62e  jnz     loc_14001B471
0x14001b634  mov     [rbx+18h], rdi
0x14001b638  jmp     loc_14001B471
```
