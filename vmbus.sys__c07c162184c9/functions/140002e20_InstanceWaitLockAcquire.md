# InstanceWaitLockAcquire

- ea: `0x140002e20`
- end: `0x140002e5d`
- name: `InstanceWaitLockAcquire`
- size: `61`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140003c24`
- `0x1400041b4`
- `0x1400043c8`
- `0x1400044b8`
- `0x140004780`
- `0x1400047f0`
- `0x14000b4f0`
- `0x14000b800`
- `0x14000b980`
- `0x14000ba60`
- `0x140028354`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140002e29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002e29`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002e4a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002e4a`

## pseudocode

```c
NTSTATUS __fastcall InstanceWaitLockAcquire(__int64 a1)
{
  KeEnterCriticalRegion();
  return KeWaitForSingleObject((PVOID)(a1 + 32), Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x140002e20  push    rbx
0x140002e22  sub     rsp, 30h
0x140002e26  mov     rbx, rcx
0x140002e29  call    cs:__imp_KeEnterCriticalRegion
0x140002e30  nop     dword ptr [rax+rax+00h]
0x140002e35  lea     rcx, [rbx+20h]; Object
0x140002e39  mov     [rsp+38h+Timeout], 0; Timeout
0x140002e42  xor     r9d, r9d; Alertable
0x140002e45  xor     r8d, r8d; WaitMode
0x140002e48  xor     edx, edx; WaitReason
0x140002e4a  call    cs:__imp_KeWaitForSingleObject
0x140002e51  nop     dword ptr [rax+rax+00h]
0x140002e56  add     rsp, 30h
0x140002e5a  pop     rbx
0x140002e5b  retn
```
