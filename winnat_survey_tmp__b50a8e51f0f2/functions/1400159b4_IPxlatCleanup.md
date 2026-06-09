# IPxlatCleanup

- ea: `0x1400159b4`
- end: `0x140015b21`
- name: `IPxlatCleanup`
- size: `365`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000db20`

## callees

- `0x1400159b4`
- `0x140016368`
- `0x14002d008`
- `0x14002d4b0`
- `0x14003363c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015a94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015ace`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015a94`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015ace`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015a56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015ab4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015a56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015ab4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015ae8`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015ae8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400159fb`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400159fb`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400159e2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400159e2`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140015a13`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140015a13`

## pseudocode

```c
NTSTATUS IPxlatCleanup()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  PVOID v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r9
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  result = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( IPxlatGlobalState )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400268F0);
    IPxlatGlobalState = 0;
    ExReleaseResourceAndLeaveCriticalRegion(&stru_1400268F0);
    if ( changeHandle )
    {
      v1 = FwpmBfeStateUnsubscribeChanges0(changeHandle);
      if ( v1 < 0 && (xmmword_1400262D0 & 2) != 0 )
        WPP_SF_d(513, 13, WPP_24083f43286932c6336729c882afb6f6_Traceguids, (unsigned int)v1);
      changeHandle = 0;
    }
    KeAcquireInStackQueuedSpinLock(&qword_140026958, &LockHandle);
    while ( 1 )
    {
      v2 = qword_1400268E0;
      if ( qword_1400268E0 == &qword_1400268E0 )
        break;
      if ( *((PVOID **)qword_1400268E0 + 1) != &qword_1400268E0
        || (v3 = *(_QWORD *)qword_1400268E0, *(PVOID *)(*(_QWORD *)qword_1400268E0 + 8LL) != qword_1400268E0) )
      {
        __fastfail(3u);
      }
      qword_1400268E0 = *(PVOID *)qword_1400268E0;
      *(_QWORD *)(v3 + 8) = &qword_1400268E0;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      IPxlatDeleteInstance(v2);
      KeAcquireInStackQueuedSpinLock(&qword_140026958, &LockHandle);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IPxlatConfigureCallouts(0);
    result = ExDeleteResourceLite(&stru_1400268F0);
    if ( (xmmword_1400262E0 & 2) != 0 )
    {
      LOBYTE(v5) = IPxlatGlobalState;
      return WPP_SF_c(
               v4,
               14,
               WPP_24083f43286932c6336729c882afb6f6_Traceguids,
               v5,
               LockHandle.LockQueue.Next,
               LockHandle.LockQueue.Lock,
               *(_QWORD *)&LockHandle.OldIrql);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400159b4  mov     [rsp+arg_0], rbx
0x1400159b9  push    rdi
0x1400159ba  sub     rsp, 40h
0x1400159be  xor     eax, eax
0x1400159c0  xor     ebx, ebx
0x1400159c2  cmp     cs:IPxlatGlobalState, bl
0x1400159c8  xorps   xmm0, xmm0
0x1400159cb  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x1400159d0  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x1400159d5  jz      loc_140015B15
0x1400159db  lea     rcx, stru_1400268F0; Resource
0x1400159e2  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400159e9  nop     dword ptr [rax+rax+00h]
0x1400159ee  lea     rcx, stru_1400268F0; Resource
0x1400159f5  mov     cs:IPxlatGlobalState, bl
0x1400159fb  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140015a02  nop     dword ptr [rax+rax+00h]
0x140015a07  mov     rcx, cs:changeHandle; changeHandle
0x140015a0e  test    rcx, rcx
0x140015a11  jz      short loc_140015A4A
0x140015a13  call    cs:__imp_FwpmBfeStateUnsubscribeChanges0
0x140015a1a  nop     dword ptr [rax+rax+00h]
0x140015a1f  test    eax, eax
0x140015a21  jns     short loc_140015A43
0x140015a23  test    byte ptr cs:xmmword_1400262D0, 2
0x140015a2a  jz      short loc_140015A43
0x140015a2c  lea     edx, [rbx+0Dh]
0x140015a2f  mov     ecx, 201h
0x140015a34  mov     r9d, eax
0x140015a37  lea     r8, WPP_24083f43286932c6336729c882afb6f6_Traceguids
0x140015a3e  call    WPP_SF_d
0x140015a43  mov     cs:changeHandle, rbx
0x140015a4a  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140015a4f  lea     rcx, qword_140026958; SpinLock
0x140015a56  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140015a5d  nop     dword ptr [rax+rax+00h]
0x140015a62  lea     rdi, qword_1400268E0
0x140015a69  mov     rbx, cs:qword_1400268E0
0x140015a70  cmp     rbx, rdi
0x140015a73  jz      short loc_140015AC9
0x140015a75  cmp     [rbx+8], rdi
0x140015a79  jnz     short loc_140015AC2
0x140015a7b  mov     rax, [rbx]
0x140015a7e  cmp     [rax+8], rbx
0x140015a82  jnz     short loc_140015AC2
0x140015a84  mov     cs:qword_1400268E0, rax
0x140015a8b  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140015a90  mov     [rax+8], rdi
0x140015a94  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140015a9b  nop     dword ptr [rax+rax+00h]
0x140015aa0  mov     rcx, rbx; P
0x140015aa3  call    IPxlatDeleteInstance
0x140015aa8  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x140015aad  lea     rcx, qword_140026958; SpinLock
0x140015ab4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140015abb  nop     dword ptr [rax+rax+00h]
0x140015ac0  jmp     short loc_140015A69
0x140015ac2  mov     ecx, 3
0x140015ac7  int     29h; Win8: RtlFailFast(ecx)
0x140015ac9  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140015ace  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140015ad5  nop     dword ptr [rax+rax+00h]
0x140015ada  xor     ecx, ecx
0x140015adc  call    IPxlatConfigureCallouts
0x140015ae1  lea     rcx, stru_1400268F0; Resource
0x140015ae8  call    cs:__imp_ExDeleteResourceLite
0x140015aef  nop     dword ptr [rax+rax+00h]
0x140015af4  test    byte ptr cs:xmmword_1400262E0, 2
0x140015afb  jz      short loc_140015B15
0x140015afd  mov     r9b, cs:IPxlatGlobalState
0x140015b04  lea     r8, WPP_24083f43286932c6336729c882afb6f6_Traceguids
0x140015b0b  mov     edx, 0Eh
0x140015b10  call    WPP_SF_c
0x140015b15  mov     rbx, [rsp+48h+arg_0]
0x140015b1a  add     rsp, 40h
0x140015b1e  pop     rdi
0x140015b1f  retn
```
