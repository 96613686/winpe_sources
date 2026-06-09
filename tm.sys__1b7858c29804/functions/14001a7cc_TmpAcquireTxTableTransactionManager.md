# TmpAcquireTxTableTransactionManager

- ea: `0x14001a7cc`
- end: `0x14001a821`
- name: `TmpAcquireTxTableTransactionManager`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400109a4`
- `0x140016f40`
- `0x14001a630`
- `0x14001ab8c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001a7ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a80e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a7ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a80e`

## pseudocode

```c
NTSTATUS __fastcall TmpAcquireTxTableTransactionManager(__int64 a1)
{
  KeWaitForSingleObject((PVOID)(a1 + 8), Executive, 0, 0, 0);
  return KeWaitForSingleObject((PVOID)(a1 + 280), Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x14001a7cc  push    rbx
0x14001a7ce  sub     rsp, 30h
0x14001a7d2  mov     rbx, rcx
0x14001a7d5  mov     [rsp+38h+Timeout], 0; Timeout
0x14001a7de  add     rcx, 8; Object
0x14001a7e2  xor     r9d, r9d; Alertable
0x14001a7e5  xor     r8d, r8d; WaitMode
0x14001a7e8  xor     edx, edx; WaitReason
0x14001a7ea  call    cs:__imp_KeWaitForSingleObject
0x14001a7f1  nop     dword ptr [rax+rax+00h]
0x14001a7f6  lea     rcx, [rbx+118h]; Object
0x14001a7fd  mov     [rsp+38h+Timeout], 0; Timeout
0x14001a806  xor     r9d, r9d; Alertable
0x14001a809  xor     r8d, r8d; WaitMode
0x14001a80c  xor     edx, edx; WaitReason
0x14001a80e  call    cs:__imp_KeWaitForSingleObject
0x14001a815  nop     dword ptr [rax+rax+00h]
0x14001a81a  add     rsp, 30h
0x14001a81e  pop     rbx
0x14001a81f  retn
```
