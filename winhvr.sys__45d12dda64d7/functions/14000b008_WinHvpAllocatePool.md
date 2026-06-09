# WinHvpAllocatePool

- ea: `0x14000b008`
- end: `0x14000b01e`
- name: `WinHvpAllocatePool`
- size: `22`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1400055d4`
- `0x140005720`
- `0x140005cf0`
- `0x14001b1c0`
- `0x14001c140`
- `0x14001d31c`
- `0x14001d65c`
- `0x14001e11c`
- `0x14001e2a0`
- `0x14001f2d0`
- `0x140020130`
- `0x1400204a4`
- `0x140021680`
- `0x140021a10`
- `0x1400226bc`
- `0x140023350`
- `0x140023d88`
- `0x140024330`
- `0x1400254e0`
- `0x140026268`
- `0x14002a40c`
- `0x14002a4fc`
- `0x14002a794`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b00c`
- `ntoskrnl!ExAllocatePool2` at `0x14000b00c`

## pseudocode

```c
__int64 __fastcall WinHvpAllocatePool(__int64 a1, __int64 a2, __int64 a3)
{
  return ExAllocatePool2(a1, a2, a3);
}

```

## disassembly

```asm
0x14000b008  sub     rsp, 28h
0x14000b00c  call    cs:__imp_ExAllocatePool2
0x14000b013  nop     dword ptr [rax+rax+00h]
0x14000b018  add     rsp, 28h
0x14000b01c  retn
```
