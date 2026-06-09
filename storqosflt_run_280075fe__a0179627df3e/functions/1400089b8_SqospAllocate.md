# SqospAllocate

- ea: `0x1400089b8`
- end: `0x1400089dc`
- name: `SqospAllocate`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140012094`
- `0x14001223c`
- `0x1400122e0`
- `0x140012c78`
- `0x140013cf8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400089ca`
- `ntoskrnl!ExAllocatePool2` at `0x1400089ca`

## pseudocode

```c
__int64 __fastcall SqospAllocate(__int64 a1)
{
  return ExAllocatePool2(64, a1, 1179865427);
}

```

## disassembly

```asm
0x1400089b8  sub     rsp, 28h
0x1400089bc  mov     rdx, rcx
0x1400089bf  mov     r8d, 46535153h
0x1400089c5  mov     ecx, 40h ; '@'
0x1400089ca  call    cs:__imp_ExAllocatePool2
0x1400089d1  nop     dword ptr [rax+rax+00h]
0x1400089d6  add     rsp, 28h
0x1400089da  retn
```
