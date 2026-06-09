# WinNatCleanupSessionState

- ea: `0x14001ae6c`
- end: `0x14001afc9`
- name: `WinNatCleanupSessionState`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018918`

## callees

- `0x14000a638`
- `0x14000caa0`
- `0x14000d914`
- `0x14001ae6c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001af50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001af50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001af78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001af78`
- `ntoskrnl!KeCancelTimer` at `0x14001aea0`
- `ntoskrnl!KeCancelTimer` at `0x14001aea0`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001aeca`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001aeff`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001af34`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001aeca`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001aeff`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001af34`
- `NETIO!RtlCleanupTimerWheel` at `0x14001af63`
- `NETIO!RtlCleanupTimerWheel` at `0x14001af63`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001afb6`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001afb6`

## pseudocode

```c
void __fastcall WinNatCleanupSessionState(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  void *v9; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  *(_BYTE *)(a1 + 628) |= 1u;
  KeCancelTimer((PKTIMER)(a1 + 488));
  v6 = *(_QWORD *)(a1 + 392);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4, v5);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392));
    *(_QWORD *)(a1 + 392) = 0;
  }
  v7 = *(_QWORD *)(a1 + 384);
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4, v5);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384));
    *(_QWORD *)(a1 + 384) = 0;
  }
  v8 = *(_QWORD *)(a1 + 400);
  if ( v8 )
  {
    if ( *(_DWORD *)(v8 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4, v5);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 400));
    *(_QWORD *)(a1 + 400) = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  RtlCleanupTimerWheel(*(_QWORD *)(a1 + 472));
  ExFreePoolWithTag(*(PVOID *)(a1 + 472), 0);
  if ( *(_QWORD *)a1 )
    PplDestroyLookasideList(*(PVOID *)a1, 0x65734C57u);
  v9 = *(void **)(a1 + 8);
  if ( v9 )
    PplDestroyLookasideList(v9, 0x65734C57u);
  if ( *(_QWORD *)(a1 + 408) )
    RtlCleanupToeplitzHash();
}

```

## disassembly

```asm
0x14001ae6c  push    rbx
0x14001ae6e  sub     rsp, 40h
0x14001ae72  mov     rbx, rcx
0x14001ae75  lea     rdx, [rsp+48h+LockHandle]
0x14001ae7a  xorps   xmm0, xmm0
0x14001ae7d  xor     eax, eax
0x14001ae7f  add     rcx, 40h ; '@'
0x14001ae83  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14001ae88  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14001ae8d  call    RtlAcquireScalableWriteLock
0x14001ae92  or      byte ptr [rbx+274h], 1
0x14001ae99  lea     rcx, [rbx+1E8h]; PKTIMER
0x14001aea0  call    cs:__imp_KeCancelTimer
0x14001aea7  nop     dword ptr [rax+rax+00h]
0x14001aeac  mov     rax, [rbx+188h]
0x14001aeb3  test    rax, rax
0x14001aeb6  jz      short loc_14001AEE1
0x14001aeb8  cmp     dword ptr [rax+14h], 0
0x14001aebc  jz      short loc_14001AEC3
0x14001aebe  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001aec3  mov     rcx, [rbx+188h]; HashTable
0x14001aeca  call    cs:__imp_RtlDeleteHashTable
0x14001aed1  nop     dword ptr [rax+rax+00h]
0x14001aed6  mov     qword ptr [rbx+188h], 0
0x14001aee1  mov     rax, [rbx+180h]
0x14001aee8  test    rax, rax
0x14001aeeb  jz      short loc_14001AF16
0x14001aeed  cmp     dword ptr [rax+14h], 0
0x14001aef1  jz      short loc_14001AEF8
0x14001aef3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001aef8  mov     rcx, [rbx+180h]; HashTable
0x14001aeff  call    cs:__imp_RtlDeleteHashTable
0x14001af06  nop     dword ptr [rax+rax+00h]
0x14001af0b  mov     qword ptr [rbx+180h], 0
0x14001af16  mov     rax, [rbx+190h]
0x14001af1d  test    rax, rax
0x14001af20  jz      short loc_14001AF4B
0x14001af22  cmp     dword ptr [rax+14h], 0
0x14001af26  jz      short loc_14001AF2D
0x14001af28  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001af2d  mov     rcx, [rbx+190h]; HashTable
0x14001af34  call    cs:__imp_RtlDeleteHashTable
0x14001af3b  nop     dword ptr [rax+rax+00h]
0x14001af40  mov     qword ptr [rbx+190h], 0
0x14001af4b  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14001af50  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001af57  nop     dword ptr [rax+rax+00h]
0x14001af5c  mov     rcx, [rbx+1D8h]
0x14001af63  call    cs:__imp_RtlCleanupTimerWheel
0x14001af6a  nop     dword ptr [rax+rax+00h]
0x14001af6f  mov     rcx, [rbx+1D8h]; P
0x14001af76  xor     edx, edx; Tag
0x14001af78  call    cs:__imp_ExFreePoolWithTag
0x14001af7f  nop     dword ptr [rax+rax+00h]
0x14001af84  mov     rcx, [rbx]; P
0x14001af87  test    rcx, rcx
0x14001af8a  jz      short loc_14001AF96
0x14001af8c  mov     edx, 65734C57h; Tag
0x14001af91  call    PplDestroyLookasideList
0x14001af96  mov     rcx, [rbx+8]; P
0x14001af9a  test    rcx, rcx
0x14001af9d  jz      short loc_14001AFA9
0x14001af9f  mov     edx, 65734C57h; Tag
0x14001afa4  call    PplDestroyLookasideList
0x14001afa9  lea     rcx, [rbx+198h]
0x14001afb0  cmp     qword ptr [rcx], 0
0x14001afb4  jz      short loc_14001AFC2
0x14001afb6  call    cs:__imp_RtlCleanupToeplitzHash
0x14001afbd  nop     dword ptr [rax+rax+00h]
0x14001afc2  add     rsp, 40h
0x14001afc6  pop     rbx
0x14001afc7  retn
```
