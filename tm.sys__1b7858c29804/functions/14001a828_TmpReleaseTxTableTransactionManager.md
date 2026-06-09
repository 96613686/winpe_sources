# TmpReleaseTxTableTransactionManager

- ea: `0x14001a828`
- end: `0x14001a85f`
- name: `TmpReleaseTxTableTransactionManager`
- size: `55`
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

- `ntoskrnl!KeReleaseMutex` at `0x14001a83a`
- `ntoskrnl!KeReleaseMutex` at `0x14001a84c`
- `ntoskrnl!KeReleaseMutex` at `0x14001a83a`
- `ntoskrnl!KeReleaseMutex` at `0x14001a84c`

## pseudocode

```c
LONG __fastcall TmpReleaseTxTableTransactionManager(__int64 a1)
{
  KeReleaseMutex((PRKMUTEX)(a1 + 280), 0);
  return KeReleaseMutex((PRKMUTEX)(a1 + 8), 0);
}

```

## disassembly

```asm
0x14001a828  push    rbx
0x14001a82a  sub     rsp, 20h
0x14001a82e  mov     rbx, rcx
0x14001a831  xor     edx, edx; Wait
0x14001a833  add     rcx, 118h; Mutex
0x14001a83a  call    cs:__imp_KeReleaseMutex
0x14001a841  nop     dword ptr [rax+rax+00h]
0x14001a846  lea     rcx, [rbx+8]; Mutex
0x14001a84a  xor     edx, edx; Wait
0x14001a84c  call    cs:__imp_KeReleaseMutex
0x14001a853  nop     dword ptr [rax+rax+00h]
0x14001a858  add     rsp, 20h
0x14001a85c  pop     rbx
0x14001a85d  retn
```
