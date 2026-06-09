# TcpRemoveTcb

- ea: `0x14001b5f0`
- end: `0x14001b8dd`
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

- `0x14001a630`
- `0x14001b5f0`
- `0x14001b8e4`
- `0x14001c170`
- `0x140055a20`
- `0x1400b03d0`
- `0x14014e364`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b63e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b7eb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b63e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001b7eb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b7b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b85f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b7b1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b85f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b6e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b6e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b65c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b835`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b65c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b835`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b73a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b73a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b761`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b761`

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
0x14001b5f0  push    rbx
0x14001b5f2  push    rbp
0x14001b5f3  push    rsi
0x14001b5f4  push    rdi
0x14001b5f5  sub     rsp, 58h
0x14001b5f9  and     dword ptr [rcx+78h], 0FFFFFFFDh
0x14001b5fd  xor     eax, eax
0x14001b5ff  mov     [rsp+78h+arg_10], r14
0x14001b607  xorps   xmm0, xmm0
0x14001b60a  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14001b60f  movzx   ebp, r8b
0x14001b613  mov     rsi, rdx
0x14001b616  mov     rdi, rcx
0x14001b619  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14001b61e  test    rdx, rdx
0x14001b621  jz      loc_14001B772
0x14001b627  mov     r14, rdx
0x14001b62a  xor     r8d, r8d; Context
0x14001b62d  test    bpl, bpl
0x14001b630  jz      loc_14001B7E3
0x14001b636  mov     rcx, [r14+10h]; HashTable
0x14001b63a  lea     rdx, [rdi+48h]; Entry
0x14001b63e  call    cs:__imp_RtlRemoveEntryHashTable
0x14001b645  nop     dword ptr [rax+rax+00h]
0x14001b64a  mov     r14, [rsp+78h+arg_10]
0x14001b652  test    rsi, rsi
0x14001b655  jnz     short loc_14001B668
0x14001b657  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14001b65c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001b663  nop     dword ptr [rax+rax+00h]
0x14001b668  test    bpl, bpl
0x14001b66b  jz      short loc_14001B677
0x14001b66d  add     rsp, 58h
0x14001b671  pop     rdi
0x14001b672  pop     rsi
0x14001b673  pop     rbp
0x14001b674  pop     rbx
0x14001b675  retn
0x14001b677  mov     rbx, [rdi+388h]
0x14001b67e  test    rbx, rbx
0x14001b681  jz      short loc_14001B66D
0x14001b683  xor     eax, eax
0x14001b685  xorps   xmm0, xmm0
0x14001b688  mov     qword ptr [rsp+78h+var_40.OldIrql], rax
0x14001b68d  mov     eax, [rbx+30h]
0x14001b690  movups  xmmword ptr [rsp+78h+var_40.LockQueue.Next], xmm0
0x14001b695  test    al, 4
0x14001b697  jz      short loc_14001B6A8
0x14001b699  mov     rax, [rbx+160h]
0x14001b6a0  mov     rcx, [rax+20h]
0x14001b6a4  lock dec dword ptr [rcx+24h]
0x14001b6a8  mov     r8d, 3
0x14001b6ae  mov     rdx, rdi
0x14001b6b1  mov     rcx, rbx
0x14001b6b4  call    AleNotifyEndpointDeactivate
0x14001b6b9  cmp     eax, 103h
0x14001b6be  jz      short loc_14001B66D
0x14001b6c0  xor     ebp, ebp
0x14001b6c2  mov     esi, ebp
0x14001b6c4  mov     [rsp+78h+arg_0], rbp
0x14001b6cc  cmp     cs:gAleDebugEnabled, sil
0x14001b6d3  mov     edi, ebp
0x14001b6d5  jnz     loc_14001B887
0x14001b6db  lea     rdx, [rsp+78h+var_40]; LockHandle
0x14001b6e0  mov     rcx, rbx; SpinLock
0x14001b6e3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001b6ea  nop     dword ptr [rax+rax+00h]
0x14001b6ef  nop
0x14001b6f0  mov     eax, [rbx+8]
0x14001b6f3  test    eax, eax
0x14001b6f5  jnz     short loc_14001B6F0
0x14001b6f7  mov     rax, gs:188h
0x14001b700  cmp     cs:gAleDebugEnabled, 1
0x14001b707  mov     [rbx+10h], rax
0x14001b70b  jz      loc_14001B8CB
0x14001b711  lea     rcx, [rbx+80h]
0x14001b718  call    WfpAleDisableWaitRef
0x14001b71d  cmp     cs:gAleDebugEnabled, 1
0x14001b724  mov     rdi, rbp
0x14001b727  mov     [rbx+10h], rbp
0x14001b72b  jnz     short loc_14001B735
0x14001b72d  mov     rdi, [rbx+18h]
0x14001b731  mov     [rbx+18h], rbp
0x14001b735  lea     rcx, [rsp+78h+var_40]; LockHandle
0x14001b73a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b741  nop     dword ptr [rax+rax+00h]
0x14001b746  cmp     cs:gAleDebugEnabled, 1
0x14001b74d  jnz     loc_14001B66D
0x14001b753  test    rdi, rdi
0x14001b756  jz      loc_14001B66D
0x14001b75c  xor     edx, edx; Tag
0x14001b75e  mov     rcx, rdi; P
0x14001b761  call    cs:__imp_ExFreePoolWithTag
0x14001b768  nop     dword ptr [rax+rax+00h]
0x14001b76d  jmp     loc_14001B66D
0x14001b772  mov     ecx, 40h ; '@'
0x14001b777  mov     [rsp+78h+arg_8], r12
0x14001b77f  mov     [rsp+78h+var_28], r15
0x14001b784  test    bpl, bpl
0x14001b787  movzx   r15d, cs:PartitionCount
0x14001b78f  mov     eax, 58h ; 'X'
0x14001b794  cmovz   eax, ecx
0x14001b797  mov     r12, [rax+rdi]
0x14001b79b  mov     rcx, r12
0x14001b79e  call    TcpGetPartitionFromKey
0x14001b7a3  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14001b7a8  mov     r14, rax
0x14001b7ab  mov     rbx, [rax]
0x14001b7ae  mov     rcx, rbx; SpinLock
0x14001b7b1  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001b7b8  nop     dword ptr [rax+rax+00h]
0x14001b7bd  nop     dword ptr [rax]
0x14001b7c0  mov     eax, [rbx+8]
0x14001b7c3  test    eax, eax
0x14001b7c5  jnz     short loc_14001B7C0
0x14001b7c7  cmp     r15w, cs:PartitionCount
0x14001b7cf  jnz     short loc_14001B830
0x14001b7d1  mov     r15, [rsp+78h+var_28]
0x14001b7d6  mov     r12, [rsp+78h+arg_8]
0x14001b7de  jmp     loc_14001B62A
0x14001b7e3  mov     rcx, [r14+8]; HashTable
0x14001b7e7  lea     rdx, [rdi+30h]; Entry
0x14001b7eb  call    cs:__imp_RtlRemoveEntryHashTable
0x14001b7f2  nop     dword ptr [rax+rax+00h]
0x14001b7f7  mov     edx, [rdi+328h]
0x14001b7fd  test    dl, 8
0x14001b800  jz      loc_14001B64A
0x14001b806  movzx   r8d, word ptr [rdi+80h]
0x14001b80e  mov     rcx, r14
0x14001b811  shr     r8w, 0Ch
0x14001b816  shr     edx, 4
0x14001b819  and     r8b, 1
0x14001b81d  and     dl, 1
0x14001b820  call    TcpDropSynRcvdFromPartition
0x14001b825  jmp     loc_14001B64A
0x14001b830  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14001b835  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14001b83c  nop     dword ptr [rax+rax+00h]
0x14001b841  movzx   r15d, cs:PartitionCount
0x14001b849  mov     rcx, r12
0x14001b84c  call    TcpGetPartitionFromKey
0x14001b851  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14001b856  mov     r14, rax
0x14001b859  mov     rbx, [rax]
0x14001b85c  mov     rcx, rbx; SpinLock
0x14001b85f  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14001b866  nop     dword ptr [rax+rax+00h]
0x14001b86b  nop     dword ptr [rax+rax+00h]
0x14001b870  mov     eax, [rbx+8]
0x14001b873  test    eax, eax
0x14001b875  jnz     short loc_14001B870
0x14001b877  cmp     r15w, cs:PartitionCount
0x14001b87f  jz      loc_14001B7D1
0x14001b885  jmp     short loc_14001B830
0x14001b887  lea     r8, [rsp+78h+arg_0]
0x14001b88f  mov     edx, 4C656C41h
0x14001b894  mov     ecx, 22h ; '"'
0x14001b899  call    WfpPoolAllocNonPaged
0x14001b89e  mov     rdi, [rsp+78h+arg_0]
0x14001b8a6  mov     rsi, rax
0x14001b8a9  test    rax, rax
0x14001b8ac  jnz     loc_14001B6DB
0x14001b8b2  mov     r8, rdi
0x14001b8b5  lea     rcx, aWfpaleendpoint_1; "WfpAleEndpointDeactivationHandler"
0x14001b8bc  mov     edx, 22h ; '"'
0x14001b8c1  call    WfpStringCchCopyA
0x14001b8c6  jmp     loc_14001B6DB
0x14001b8cb  test    rsi, rsi
0x14001b8ce  jnz     loc_14001B711
0x14001b8d4  mov     [rbx+18h], rdi
0x14001b8d8  jmp     loc_14001B711
```
