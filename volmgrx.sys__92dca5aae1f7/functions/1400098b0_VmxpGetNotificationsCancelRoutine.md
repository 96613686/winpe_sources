# VmxpGetNotificationsCancelRoutine

- ea: `0x1400098b0`
- end: `0x140009903`
- name: `VmxpGetNotificationsCancelRoutine`
- size: `83`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400098f0`
- `ntoskrnl!IofCompleteRequest` at `0x1400098f0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400098d0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400098d0`

## pseudocode

```c
void __fastcall VmxpGetNotificationsCancelRoutine(__int64 a1, IRP *a2)
{
  struct _LIST_ENTRY *Flink; // rax

  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  Flink[2].Blink = 0;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x1400098b0  push    rbx
0x1400098b2  sub     rsp, 20h
0x1400098b6  mov     rax, [rdx+78h]
0x1400098ba  mov     rbx, rdx
0x1400098bd  mov     qword ptr [rdx+78h], 0
0x1400098c5  mov     qword ptr [rax+28h], 0
0x1400098cd  mov     cl, [rdx+45h]; Irql
0x1400098d0  call    cs:__imp_IoReleaseCancelSpinLock
0x1400098d7  nop     dword ptr [rax+rax+00h]
0x1400098dc  xor     edx, edx; PriorityBoost
0x1400098de  mov     dword ptr [rbx+30h], 0C0000120h
0x1400098e5  mov     rcx, rbx; Irp
0x1400098e8  mov     qword ptr [rbx+38h], 0
0x1400098f0  call    cs:__imp_IofCompleteRequest
0x1400098f7  nop     dword ptr [rax+rax+00h]
0x1400098fc  add     rsp, 20h
0x140009900  pop     rbx
0x140009901  retn
```
