# WinNatCleanupBindingState

- ea: `0x140019fdc`
- end: `0x14001a0c2`
- name: `WinNatCleanupBindingState`
- size: `230`
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
- `0x140019fdc`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a071`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001a071`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001a020`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001a055`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001a020`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001a055`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001a0af`
- `NETIO!RtlCleanupToeplitzHash` at `0x14001a0af`

## pseudocode

```c
void __fastcall WinNatCleanupBindingState(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  void *v7; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  v5 = *(_QWORD *)(a1 + 384);
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384));
    *(_QWORD *)(a1 + 384) = 0;
  }
  v6 = *(_QWORD *)(a1 + 392);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392));
    *(_QWORD *)(a1 + 392) = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( *(_QWORD *)a1 )
    PplDestroyLookasideList(*(PVOID *)a1, 0x65624C57u);
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    PplDestroyLookasideList(v7, 0x65624C57u);
  if ( *(_QWORD *)(a1 + 400) )
    RtlCleanupToeplitzHash();
}

```

## disassembly

```asm
0x140019fdc  push    rbx
0x140019fde  sub     rsp, 40h
0x140019fe2  mov     rbx, rcx
0x140019fe5  lea     rdx, [rsp+48h+LockHandle]
0x140019fea  xorps   xmm0, xmm0
0x140019fed  xor     eax, eax
0x140019fef  add     rcx, 40h ; '@'
0x140019ff3  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140019ff8  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140019ffd  call    RtlAcquireScalableWriteLock
0x14001a002  mov     rax, [rbx+180h]
0x14001a009  test    rax, rax
0x14001a00c  jz      short loc_14001A037
0x14001a00e  cmp     dword ptr [rax+14h], 0
0x14001a012  jz      short loc_14001A019
0x14001a014  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a019  mov     rcx, [rbx+180h]; HashTable
0x14001a020  call    cs:__imp_RtlDeleteHashTable
0x14001a027  nop     dword ptr [rax+rax+00h]
0x14001a02c  mov     qword ptr [rbx+180h], 0
0x14001a037  mov     rax, [rbx+188h]
0x14001a03e  test    rax, rax
0x14001a041  jz      short loc_14001A06C
0x14001a043  cmp     dword ptr [rax+14h], 0
0x14001a047  jz      short loc_14001A04E
0x14001a049  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001a04e  mov     rcx, [rbx+188h]; HashTable
0x14001a055  call    cs:__imp_RtlDeleteHashTable
0x14001a05c  nop     dword ptr [rax+rax+00h]
0x14001a061  mov     qword ptr [rbx+188h], 0
0x14001a06c  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14001a071  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001a078  nop     dword ptr [rax+rax+00h]
0x14001a07d  mov     rcx, [rbx]; P
0x14001a080  test    rcx, rcx
0x14001a083  jz      short loc_14001A08F
0x14001a085  mov     edx, 65624C57h; Tag
0x14001a08a  call    PplDestroyLookasideList
0x14001a08f  mov     rcx, [rbx+8]; P
0x14001a093  test    rcx, rcx
0x14001a096  jz      short loc_14001A0A2
0x14001a098  mov     edx, 65624C57h; Tag
0x14001a09d  call    PplDestroyLookasideList
0x14001a0a2  lea     rcx, [rbx+190h]
0x14001a0a9  cmp     qword ptr [rcx], 0
0x14001a0ad  jz      short loc_14001A0BB
0x14001a0af  call    cs:__imp_RtlCleanupToeplitzHash
0x14001a0b6  nop     dword ptr [rax+rax+00h]
0x14001a0bb  add     rsp, 40h
0x14001a0bf  pop     rbx
0x14001a0c0  retn
```
