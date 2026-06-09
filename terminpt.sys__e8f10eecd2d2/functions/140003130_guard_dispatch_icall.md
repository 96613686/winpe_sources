# _guard_dispatch_icall

- ea: `0x140003130`
- end: `0x140003136`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000173c`
- `0x1400017e8`
- `0x1400018c0`
- `0x1400019a8`
- `0x140001a80`
- `0x1400024e8`
- `0x1400026a0`
- `0x140002858`
- `0x14000293c`
- `0x140002e78`
- `0x140004010`
- `0x14000a654`
- `0x14000a708`
- `0x14000a7d0`
- `0x14000a920`

## callees

- `0x140003160`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140003130  jmp     cs:__guard_dispatch_icall_fptr
```
