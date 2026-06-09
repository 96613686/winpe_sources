# TmpNamespaceExpire

- ea: `0x14001d630`
- end: `0x14001d683`
- name: `TmpNamespaceExpire`
- size: `83`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001860`
- `0x14000c7e8`
- `0x14001d610`
- `0x140020b50`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d652`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d652`
- `ntoskrnl!KeReleaseMutex` at `0x14001d66b`
- `ntoskrnl!KeReleaseMutex` at `0x14001d66b`

## pseudocode

```c
LONG __fastcall TmpNamespaceExpire(__int64 a1)
{
  KeWaitForSingleObject((PVOID)(a1 + 104), Executive, 0, 0, 0);
  *(_BYTE *)(a1 + 164) = 1;
  return KeReleaseMutex((PRKMUTEX)(a1 + 104), 0);
}

```

## disassembly

```asm
0x14001d630  mov     [rsp+arg_0], rbx
0x14001d635  push    rdi
0x14001d636  sub     rsp, 30h
0x14001d63a  mov     rbx, rcx
0x14001d63d  mov     [rsp+38h+Timeout], 0; Timeout
0x14001d646  add     rcx, 68h ; 'h'; Object
0x14001d64a  xor     r9d, r9d; Alertable
0x14001d64d  xor     r8d, r8d; WaitMode
0x14001d650  xor     edx, edx; WaitReason
0x14001d652  call    cs:__imp_KeWaitForSingleObject
0x14001d659  nop     dword ptr [rax+rax+00h]
0x14001d65e  xor     edx, edx; Wait
0x14001d660  mov     byte ptr [rbx+0A4h], 1
0x14001d667  lea     rcx, [rbx+68h]; Mutex
0x14001d66b  call    cs:__imp_KeReleaseMutex
0x14001d672  nop     dword ptr [rax+rax+00h]
0x14001d677  mov     rbx, [rsp+38h+arg_0]
0x14001d67c  add     rsp, 30h
0x14001d680  pop     rdi
0x14001d681  retn
```
