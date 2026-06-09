# InpWaitForQueueStopEvent

- ea: `0x140008d78`
- end: `0x140008e12`
- name: `InpWaitForQueueStopEvent`
- size: `154`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140007e30`
- `0x14000840c`
- `0x14000d9b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140008da2`
- `ntoskrnl!KeInitializeEvent` at `0x140008da2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008de5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008de5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008df8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008df8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dc3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dc3`

## pseudocode

```c
KIRQL __fastcall InpWaitForQueueStopEvent(__int64 a1, KIRQL *a2)
{
  KIRQL v4; // dl
  KIRQL result; // al
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v4 = *a2;
  *(_QWORD *)(a1 + 1216) = &Event;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1088), v4);
  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  result = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1088));
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x140008d78  mov     [rsp+arg_0], rbx
0x140008d7d  push    rdi
0x140008d7e  sub     rsp, 50h
0x140008d82  xor     eax, eax
0x140008d84  mov     rdi, rdx
0x140008d87  mov     rbx, rcx
0x140008d8a  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x140008d8f  xorps   xmm0, xmm0
0x140008d92  lea     rcx, [rsp+58h+Event]; Event
0x140008d97  xor     r8d, r8d; State
0x140008d9a  lea     edx, [rax+1]; Type
0x140008d9d  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x140008da2  call    cs:__imp_KeInitializeEvent
0x140008da9  nop     dword ptr [rax+rax+00h]
0x140008dae  mov     dl, [rdi]; NewIrql
0x140008db0  lea     rax, [rsp+58h+Event]
0x140008db5  lea     rcx, [rbx+440h]; SpinLock
0x140008dbc  mov     [rbx+4C0h], rax
0x140008dc3  call    cs:__imp_KeReleaseSpinLock
0x140008dca  nop     dword ptr [rax+rax+00h]
0x140008dcf  xor     r9d, r9d; Alertable
0x140008dd2  mov     [rsp+58h+Timeout], 0; Timeout
0x140008ddb  xor     r8d, r8d; WaitMode
0x140008dde  lea     rcx, [rsp+58h+Event]; Object
0x140008de3  xor     edx, edx; WaitReason
0x140008de5  call    cs:__imp_KeWaitForSingleObject
0x140008dec  nop     dword ptr [rax+rax+00h]
0x140008df1  lea     rcx, [rbx+440h]; SpinLock
0x140008df8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008dff  nop     dword ptr [rax+rax+00h]
0x140008e04  mov     rbx, [rsp+58h+arg_0]
0x140008e09  mov     [rdi], al
0x140008e0b  add     rsp, 50h
0x140008e0f  pop     rdi
0x140008e10  retn
```
