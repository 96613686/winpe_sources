# WinNatCleanupBindingState

- ea: `0x140019afc`
- end: `0x140019be2`
- name: `WinNatCleanupBindingState`
- size: `230`
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
- `0x140019afc`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019b91`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019b91`
- `ntoskrnl!RtlDeleteHashTable` at `0x140019b40`
- `ntoskrnl!RtlDeleteHashTable` at `0x140019b75`
- `ntoskrnl!RtlDeleteHashTable` at `0x140019b40`
- `ntoskrnl!RtlDeleteHashTable` at `0x140019b75`
- `NETIO!RtlCleanupToeplitzHash` at `0x140019bcf`
- `NETIO!RtlCleanupToeplitzHash` at `0x140019bcf`

## pseudocode

```c
void __fastcall WinNatCleanupBindingState(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  void *v6; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  v4 = *(_QWORD *)(a1 + 384);
  if ( v4 )
  {
    if ( *(_DWORD *)(v4 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384));
    *(_QWORD *)(a1 + 384) = 0;
  }
  v5 = *(_QWORD *)(a1 + 392);
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 20) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 392));
    *(_QWORD *)(a1 + 392) = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( *(_QWORD *)a1 )
    PplDestroyLookasideList(*(PVOID *)a1, 0x65624C57u);
  v6 = *(void **)(a1 + 8);
  if ( v6 )
    PplDestroyLookasideList(v6, 0x65624C57u);
  if ( *(_QWORD *)(a1 + 400) )
    RtlCleanupToeplitzHash();
}

```

## disassembly

```asm
0x140019afc  push    rbx
0x140019afe  sub     rsp, 40h
0x140019b02  mov     rbx, rcx
0x140019b05  lea     rdx, [rsp+48h+LockHandle]
0x140019b0a  xorps   xmm0, xmm0
0x140019b0d  xor     eax, eax
0x140019b0f  add     rcx, 40h ; '@'
0x140019b13  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140019b18  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140019b1d  call    RtlAcquireScalableWriteLock
0x140019b22  mov     rax, [rbx+180h]
0x140019b29  test    rax, rax
0x140019b2c  jz      short loc_140019B57
0x140019b2e  cmp     dword ptr [rax+14h], 0
0x140019b32  jz      short loc_140019B39
0x140019b34  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019b39  mov     rcx, [rbx+180h]; HashTable
0x140019b40  call    cs:__imp_RtlDeleteHashTable
0x140019b47  nop     dword ptr [rax+rax+00h]
0x140019b4c  mov     qword ptr [rbx+180h], 0
0x140019b57  mov     rax, [rbx+188h]
0x140019b5e  test    rax, rax
0x140019b61  jz      short loc_140019B8C
0x140019b63  cmp     dword ptr [rax+14h], 0
0x140019b67  jz      short loc_140019B6E
0x140019b69  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140019b6e  mov     rcx, [rbx+188h]; HashTable
0x140019b75  call    cs:__imp_RtlDeleteHashTable
0x140019b7c  nop     dword ptr [rax+rax+00h]
0x140019b81  mov     qword ptr [rbx+188h], 0
0x140019b8c  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140019b91  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019b98  nop     dword ptr [rax+rax+00h]
0x140019b9d  mov     rcx, [rbx]; P
0x140019ba0  test    rcx, rcx
0x140019ba3  jz      short loc_140019BAF
0x140019ba5  mov     edx, 65624C57h; Tag
0x140019baa  call    PplDestroyLookasideList
0x140019baf  mov     rcx, [rbx+8]; P
0x140019bb3  test    rcx, rcx
0x140019bb6  jz      short loc_140019BC2
0x140019bb8  mov     edx, 65624C57h; Tag
0x140019bbd  call    PplDestroyLookasideList
0x140019bc2  lea     rcx, [rbx+190h]
0x140019bc9  cmp     qword ptr [rcx], 0
0x140019bcd  jz      short loc_140019BDB
0x140019bcf  call    cs:__imp_RtlCleanupToeplitzHash
0x140019bd6  nop     dword ptr [rax+rax+00h]
0x140019bdb  add     rsp, 40h
0x140019bdf  pop     rbx
0x140019be0  retn
```
