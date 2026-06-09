# SenderWorkerThread

- ea: `0x14001ae10`
- end: `0x14001ae88`
- name: `SenderWorkerThread`
- size: `120`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001a334`
- `0x14001ae10`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001ae39`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ae39`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ae70`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ae70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ae5b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ae5b`

## pseudocode

```c
void __fastcall SenderWorkerThread(_QWORD *StartContext)
{
  KIRQL v2; // al

  do
    KeWaitForSingleObject((PVOID)(StartContext[5] + 704LL), Executive, 0, 0, 0);
  while ( !SendNextPacket((__int64)StartContext) );
  v2 = KeAcquireSpinLockRaiseToDpc(StartContext + 45);
  *((_DWORD *)StartContext + 8) |= 1u;
  KeReleaseSpinLock(StartContext + 45, v2);
}

```

## disassembly

```asm
0x14001ae10  mov     [rsp+arg_0], rbx
0x14001ae15  push    rdi
0x14001ae16  sub     rsp, 30h
0x14001ae1a  mov     rdi, rcx
0x14001ae1d  mov     rcx, [rdi+28h]
0x14001ae21  xor     r9d, r9d; Alertable
0x14001ae24  add     rcx, 2C0h; Object
0x14001ae2b  mov     [rsp+38h+Timeout], 0; Timeout
0x14001ae34  xor     r8d, r8d; WaitMode
0x14001ae37  xor     edx, edx; WaitReason
0x14001ae39  call    cs:__imp_KeWaitForSingleObject
0x14001ae40  nop     dword ptr [rax+rax+00h]
0x14001ae45  mov     rcx, rdi
0x14001ae48  call    SendNextPacket
0x14001ae4d  test    al, al
0x14001ae4f  jz      short loc_14001AE1D
0x14001ae51  lea     rbx, [rdi+168h]
0x14001ae58  mov     rcx, rbx; SpinLock
0x14001ae5b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ae62  nop     dword ptr [rax+rax+00h]
0x14001ae67  or      dword ptr [rdi+20h], 1
0x14001ae6b  mov     rcx, rbx; SpinLock
0x14001ae6e  mov     dl, al; NewIrql
0x14001ae70  call    cs:__imp_KeReleaseSpinLock
0x14001ae77  nop     dword ptr [rax+rax+00h]
0x14001ae7c  mov     rbx, [rsp+38h+arg_0]
0x14001ae81  add     rsp, 30h
0x14001ae85  pop     rdi
0x14001ae86  retn
```
