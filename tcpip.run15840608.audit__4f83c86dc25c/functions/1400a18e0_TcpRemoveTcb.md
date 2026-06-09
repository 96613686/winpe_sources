# TcpRemoveTcb

- ea: `0x1400a18e0`
- end: `0x1400a1bcd`
- name: `TcpRemoveTcb`
- size: `749`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004171c`
- `0x140058428`
- `0x14005881c`

## callees

- `0x140009410`
- `0x1400162f0`
- `0x1400a0540`
- `0x1400a18e0`
- `0x1400a1bd4`
- `0x1400a2910`
- `0x14014ff64`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400a192e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400a1adb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400a192e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400a1adb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400a1aa1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400a1b4f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400a1aa1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400a1b4f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a19d3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a19d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400a194c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400a1b25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400a194c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400a1b25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a1a2a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a1a2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a1a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a1a51`

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
0x1400a18e0  push    rbx
0x1400a18e2  push    rbp
0x1400a18e3  push    rsi
0x1400a18e4  push    rdi
0x1400a18e5  sub     rsp, 58h
0x1400a18e9  and     dword ptr [rcx+78h], 0FFFFFFFDh
0x1400a18ed  xor     eax, eax
0x1400a18ef  mov     [rsp+78h+arg_10], r14
0x1400a18f7  xorps   xmm0, xmm0
0x1400a18fa  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400a18ff  movzx   ebp, r8b
0x1400a1903  mov     rsi, rdx
0x1400a1906  mov     rdi, rcx
0x1400a1909  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400a190e  test    rdx, rdx
0x1400a1911  jz      loc_1400A1A62
0x1400a1917  mov     r14, rdx
0x1400a191a  xor     r8d, r8d; Context
0x1400a191d  test    bpl, bpl
0x1400a1920  jz      loc_1400A1AD3
0x1400a1926  mov     rcx, [r14+10h]; HashTable
0x1400a192a  lea     rdx, [rdi+48h]; Entry
0x1400a192e  call    cs:__imp_RtlRemoveEntryHashTable
0x1400a1935  nop     dword ptr [rax+rax+00h]
0x1400a193a  mov     r14, [rsp+78h+arg_10]
0x1400a1942  test    rsi, rsi
0x1400a1945  jnz     short loc_1400A1958
0x1400a1947  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400a194c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400a1953  nop     dword ptr [rax+rax+00h]
0x1400a1958  test    bpl, bpl
0x1400a195b  jz      short loc_1400A1967
0x1400a195d  add     rsp, 58h
0x1400a1961  pop     rdi
0x1400a1962  pop     rsi
0x1400a1963  pop     rbp
0x1400a1964  pop     rbx
0x1400a1965  retn
0x1400a1967  mov     rbx, [rdi+388h]
0x1400a196e  test    rbx, rbx
0x1400a1971  jz      short loc_1400A195D
0x1400a1973  xor     eax, eax
0x1400a1975  xorps   xmm0, xmm0
0x1400a1978  mov     qword ptr [rsp+78h+var_40.OldIrql], rax
0x1400a197d  mov     eax, [rbx+30h]
0x1400a1980  movups  xmmword ptr [rsp+78h+var_40.LockQueue.Next], xmm0
0x1400a1985  test    al, 4
0x1400a1987  jz      short loc_1400A1998
0x1400a1989  mov     rax, [rbx+160h]
0x1400a1990  mov     rcx, [rax+20h]
0x1400a1994  lock dec dword ptr [rcx+24h]
0x1400a1998  mov     r8d, 3
0x1400a199e  mov     rdx, rdi
0x1400a19a1  mov     rcx, rbx
0x1400a19a4  call    AleNotifyEndpointDeactivate
0x1400a19a9  cmp     eax, 103h
0x1400a19ae  jz      short loc_1400A195D
0x1400a19b0  xor     ebp, ebp
0x1400a19b2  mov     esi, ebp
0x1400a19b4  mov     [rsp+78h+arg_0], rbp
0x1400a19bc  cmp     cs:gAleDebugEnabled, sil
0x1400a19c3  mov     edi, ebp
0x1400a19c5  jnz     loc_1400A1B77
0x1400a19cb  lea     rdx, [rsp+78h+var_40]; LockHandle
0x1400a19d0  mov     rcx, rbx; SpinLock
0x1400a19d3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400a19da  nop     dword ptr [rax+rax+00h]
0x1400a19df  nop
0x1400a19e0  mov     eax, [rbx+8]
0x1400a19e3  test    eax, eax
0x1400a19e5  jnz     short loc_1400A19E0
0x1400a19e7  mov     rax, gs:188h
0x1400a19f0  cmp     cs:gAleDebugEnabled, 1
0x1400a19f7  mov     [rbx+10h], rax
0x1400a19fb  jz      loc_1400A1BBB
0x1400a1a01  lea     rcx, [rbx+80h]
0x1400a1a08  call    WfpAleDisableWaitRef
0x1400a1a0d  cmp     cs:gAleDebugEnabled, 1
0x1400a1a14  mov     rdi, rbp
0x1400a1a17  mov     [rbx+10h], rbp
0x1400a1a1b  jnz     short loc_1400A1A25
0x1400a1a1d  mov     rdi, [rbx+18h]
0x1400a1a21  mov     [rbx+18h], rbp
0x1400a1a25  lea     rcx, [rsp+78h+var_40]; LockHandle
0x1400a1a2a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400a1a31  nop     dword ptr [rax+rax+00h]
0x1400a1a36  cmp     cs:gAleDebugEnabled, 1
0x1400a1a3d  jnz     loc_1400A195D
0x1400a1a43  test    rdi, rdi
0x1400a1a46  jz      loc_1400A195D
0x1400a1a4c  xor     edx, edx; Tag
0x1400a1a4e  mov     rcx, rdi; P
0x1400a1a51  call    cs:__imp_ExFreePoolWithTag
0x1400a1a58  nop     dword ptr [rax+rax+00h]
0x1400a1a5d  jmp     loc_1400A195D
0x1400a1a62  mov     ecx, 40h ; '@'
0x1400a1a67  mov     [rsp+78h+arg_8], r12
0x1400a1a6f  mov     [rsp+78h+var_28], r15
0x1400a1a74  test    bpl, bpl
0x1400a1a77  movzx   r15d, cs:PartitionCount
0x1400a1a7f  mov     eax, 58h ; 'X'
0x1400a1a84  cmovz   eax, ecx
0x1400a1a87  mov     r12, [rax+rdi]
0x1400a1a8b  mov     rcx, r12
0x1400a1a8e  call    TcpGetPartitionFromKey
0x1400a1a93  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400a1a98  mov     r14, rax
0x1400a1a9b  mov     rbx, [rax]
0x1400a1a9e  mov     rcx, rbx; SpinLock
0x1400a1aa1  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400a1aa8  nop     dword ptr [rax+rax+00h]
0x1400a1aad  nop     dword ptr [rax]
0x1400a1ab0  mov     eax, [rbx+8]
0x1400a1ab3  test    eax, eax
0x1400a1ab5  jnz     short loc_1400A1AB0
0x1400a1ab7  cmp     r15w, cs:PartitionCount
0x1400a1abf  jnz     short loc_1400A1B20
0x1400a1ac1  mov     r15, [rsp+78h+var_28]
0x1400a1ac6  mov     r12, [rsp+78h+arg_8]
0x1400a1ace  jmp     loc_1400A191A
0x1400a1ad3  mov     rcx, [r14+8]; HashTable
0x1400a1ad7  lea     rdx, [rdi+30h]; Entry
0x1400a1adb  call    cs:__imp_RtlRemoveEntryHashTable
0x1400a1ae2  nop     dword ptr [rax+rax+00h]
0x1400a1ae7  mov     edx, [rdi+328h]
0x1400a1aed  test    dl, 8
0x1400a1af0  jz      loc_1400A193A
0x1400a1af6  movzx   r8d, word ptr [rdi+80h]
0x1400a1afe  mov     rcx, r14
0x1400a1b01  shr     r8w, 0Ch
0x1400a1b06  shr     edx, 4
0x1400a1b09  and     r8b, 1
0x1400a1b0d  and     dl, 1
0x1400a1b10  call    TcpDropSynRcvdFromPartition
0x1400a1b15  jmp     loc_1400A193A
0x1400a1b20  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400a1b25  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400a1b2c  nop     dword ptr [rax+rax+00h]
0x1400a1b31  movzx   r15d, cs:PartitionCount
0x1400a1b39  mov     rcx, r12
0x1400a1b3c  call    TcpGetPartitionFromKey
0x1400a1b41  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400a1b46  mov     r14, rax
0x1400a1b49  mov     rbx, [rax]
0x1400a1b4c  mov     rcx, rbx; SpinLock
0x1400a1b4f  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400a1b56  nop     dword ptr [rax+rax+00h]
0x1400a1b5b  nop     dword ptr [rax+rax+00h]
0x1400a1b60  mov     eax, [rbx+8]
0x1400a1b63  test    eax, eax
0x1400a1b65  jnz     short loc_1400A1B60
0x1400a1b67  cmp     r15w, cs:PartitionCount
0x1400a1b6f  jz      loc_1400A1AC1
0x1400a1b75  jmp     short loc_1400A1B20
0x1400a1b77  lea     r8, [rsp+78h+arg_0]
0x1400a1b7f  mov     edx, 4C656C41h
0x1400a1b84  mov     ecx, 22h ; '"'
0x1400a1b89  call    WfpPoolAllocNonPaged
0x1400a1b8e  mov     rdi, [rsp+78h+arg_0]
0x1400a1b96  mov     rsi, rax
0x1400a1b99  test    rax, rax
0x1400a1b9c  jnz     loc_1400A19CB
0x1400a1ba2  mov     r8, rdi
0x1400a1ba5  lea     rcx, aWfpaleendpoint_1; "WfpAleEndpointDeactivationHandler"
0x1400a1bac  mov     edx, 22h ; '"'
0x1400a1bb1  call    WfpStringCchCopyA
0x1400a1bb6  jmp     loc_1400A19CB
0x1400a1bbb  test    rsi, rsi
0x1400a1bbe  jnz     loc_1400A1A01
0x1400a1bc4  mov     [rbx+18h], rdi
0x1400a1bc8  jmp     loc_1400A1A01
```
