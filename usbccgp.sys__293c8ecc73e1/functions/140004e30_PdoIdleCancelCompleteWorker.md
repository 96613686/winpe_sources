# PdoIdleCancelCompleteWorker

- ea: `0x140004e30`
- end: `0x140004eca`
- name: `PdoIdleCancelCompleteWorker`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e86`
- `ntoskrnl!IofCompleteRequest` at `0x140004e72`
- `ntoskrnl!IofCompleteRequest` at `0x140004e72`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004ead`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004ead`

## pseudocode

```c
void __fastcall PdoIdleCancelCompleteWorker(__int64 a1, _QWORD *a2)
{
  IRP *v3; // rdi

  v3 = (IRP *)a2[2];
  WaitForSignal((PVOID)(*a2 + 200LL));
  v3->IoStatus.Status = -1073741536;
  IofCompleteRequest(v3, 0);
  ExFreePoolWithTag(a2, 0x43627355u);
  UsbcReleaseRemoveLock(a1, v3);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), v3, 0x20u);
}

```

## disassembly

```asm
0x140004e30  mov     [rsp+arg_0], rbx
0x140004e35  mov     [rsp+arg_8], rsi
0x140004e3a  push    rdi
0x140004e3b  sub     rsp, 20h
0x140004e3f  mov     r8, [rdx]
0x140004e42  mov     rsi, rcx
0x140004e45  mov     rdi, [rdx+10h]
0x140004e49  mov     rbx, rdx
0x140004e4c  lea     rdx, aIdlecallbackev; "idleCallbackEvent"
0x140004e53  lea     rcx, [r8+0C8h]; Object
0x140004e5a  mov     r8, [r8+188h]
0x140004e61  call    WaitForSignal
0x140004e66  xor     edx, edx; PriorityBoost
0x140004e68  mov     dword ptr [rdi+30h], 0C0000120h
0x140004e6f  mov     rcx, rdi; Irp
0x140004e72  call    cs:__imp_IofCompleteRequest
0x140004e79  nop     dword ptr [rax+rax+00h]
0x140004e7e  mov     edx, 43627355h; Tag
0x140004e83  mov     rcx, rbx; P
0x140004e86  call    cs:__imp_ExFreePoolWithTag
0x140004e8d  nop     dword ptr [rax+rax+00h]
0x140004e92  mov     rdx, rdi
0x140004e95  mov     rcx, rsi
0x140004e98  call    UsbcReleaseRemoveLock
0x140004e9d  lea     rcx, [rsi+0C8h]; RemoveLock
0x140004ea4  mov     r8d, 20h ; ' '; RemlockSize
0x140004eaa  mov     rdx, rdi; Tag
0x140004ead  call    cs:__imp_IoReleaseRemoveLockEx
0x140004eb4  nop     dword ptr [rax+rax+00h]
0x140004eb9  mov     rbx, [rsp+28h+arg_0]
0x140004ebe  mov     rsi, [rsp+28h+arg_8]
0x140004ec3  add     rsp, 20h
0x140004ec7  pop     rdi
0x140004ec8  retn
```
