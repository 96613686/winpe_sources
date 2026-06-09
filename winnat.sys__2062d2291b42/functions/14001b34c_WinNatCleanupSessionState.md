# WinNatCleanupSessionState

- ea: `0x14001b34c`
- end: `0x14001b4a9`
- name: `WinNatCleanupSessionState`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018df8`

## callees

- `0x14000a638`
- `0x14000caa0`
- `0x14000d8e4`
- `0x14001b34c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b430`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b430`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b458`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b458`
- `ntoskrnl!KeCancelTimer` at `0x14001b380`
- `ntoskrnl!KeCancelTimer` at `0x14001b380`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b3aa`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b3df`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b414`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b3aa`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b3df`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001b414`
- `NETIO!RtlCleanupTimerWheel` at `0x14001b443`
- `NETIO!RtlCleanupTimerWheel` at `0x14001b443`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001b496`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001b496`

## pseudocode

```c
void __fastcall WinNatCleanupSessionState(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  void *v8; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  *(_BYTE *)(a1 + 628) |= 1u;
  KeCancelTimer((PKTIMER)(a1 + 488));
  v5 = *(_QWORD *)(a1 + 392);
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392));
    *(_QWORD *)(a1 + 392) = 0;
  }
  v6 = *(_QWORD *)(a1 + 384);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384));
    *(_QWORD *)(a1 + 384) = 0;
  }
  v7 = *(_QWORD *)(a1 + 400);
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 400));
    *(_QWORD *)(a1 + 400) = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  RtlCleanupTimerWheel(*(_QWORD *)(a1 + 472));
  ExFreePoolWithTag(*(PVOID *)(a1 + 472), 0);
  if ( *(_QWORD *)a1 )
    PplDestroyLookasideList(*(PVOID *)a1, 0x65734C57u);
  v8 = *(void **)(a1 + 8);
  if ( v8 )
    PplDestroyLookasideList(v8, 0x65734C57u);
  if ( *(_QWORD *)(a1 + 408) )
    RtlCleanupToeplitzHash();
}

```

## disassembly

```asm
0x14001b34c  push    rbx
0x14001b34e  sub     rsp, 40h
0x14001b352  mov     rbx, rcx
0x14001b355  lea     rdx, [rsp+48h+LockHandle]
0x14001b35a  xorps   xmm0, xmm0
0x14001b35d  xor     eax, eax
0x14001b35f  add     rcx, 40h ; '@'
0x14001b363  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14001b368  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14001b36d  call    RtlAcquireScalableWriteLock
0x14001b372  or      byte ptr [rbx+274h], 1
0x14001b379  lea     rcx, [rbx+1E8h]; PKTIMER
0x14001b380  call    cs:__imp_KeCancelTimer
0x14001b387  nop     dword ptr [rax+rax+00h]
0x14001b38c  mov     rax, [rbx+188h]
0x14001b393  test    rax, rax
0x14001b396  jz      short loc_14001B3C1
0x14001b398  cmp     dword ptr [rax+14h], 0
0x14001b39c  jz      short loc_14001B3A3
0x14001b39e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b3a3  mov     rcx, [rbx+188h]; HashTable
0x14001b3aa  call    cs:__imp_RtlDeleteHashTable
0x14001b3b1  nop     dword ptr [rax+rax+00h]
0x14001b3b6  mov     qword ptr [rbx+188h], 0
0x14001b3c1  mov     rax, [rbx+180h]
0x14001b3c8  test    rax, rax
0x14001b3cb  jz      short loc_14001B3F6
0x14001b3cd  cmp     dword ptr [rax+14h], 0
0x14001b3d1  jz      short loc_14001B3D8
0x14001b3d3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b3d8  mov     rcx, [rbx+180h]; HashTable
0x14001b3df  call    cs:__imp_RtlDeleteHashTable
0x14001b3e6  nop     dword ptr [rax+rax+00h]
0x14001b3eb  mov     qword ptr [rbx+180h], 0
0x14001b3f6  mov     rax, [rbx+190h]
0x14001b3fd  test    rax, rax
0x14001b400  jz      short loc_14001B42B
0x14001b402  cmp     dword ptr [rax+14h], 0
0x14001b406  jz      short loc_14001B40D
0x14001b408  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b40d  mov     rcx, [rbx+190h]; HashTable
0x14001b414  call    cs:__imp_RtlDeleteHashTable
0x14001b41b  nop     dword ptr [rax+rax+00h]
0x14001b420  mov     qword ptr [rbx+190h], 0
0x14001b42b  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14001b430  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b437  nop     dword ptr [rax+rax+00h]
0x14001b43c  mov     rcx, [rbx+1D8h]
0x14001b443  call    cs:__imp_RtlCleanupTimerWheel
0x14001b44a  nop     dword ptr [rax+rax+00h]
0x14001b44f  mov     rcx, [rbx+1D8h]; P
0x14001b456  xor     edx, edx; Tag
0x14001b458  call    cs:__imp_ExFreePoolWithTag
0x14001b45f  nop     dword ptr [rax+rax+00h]
0x14001b464  mov     rcx, [rbx]; P
0x14001b467  test    rcx, rcx
0x14001b46a  jz      short loc_14001B476
0x14001b46c  mov     edx, 65734C57h; Tag
0x14001b471  call    PplDestroyLookasideList
0x14001b476  mov     rcx, [rbx+8]; P
0x14001b47a  test    rcx, rcx
0x14001b47d  jz      short loc_14001B489
0x14001b47f  mov     edx, 65734C57h; Tag
0x14001b484  call    PplDestroyLookasideList
0x14001b489  lea     rcx, [rbx+198h]
0x14001b490  cmp     qword ptr [rcx], 0
0x14001b494  jz      short loc_14001B4A2
0x14001b496  call    cs:__imp_RtlCleanupToeplitzHash
0x14001b49d  nop     dword ptr [rax+rax+00h]
0x14001b4a2  add     rsp, 40h
0x14001b4a6  pop     rbx
0x14001b4a7  retn
```
