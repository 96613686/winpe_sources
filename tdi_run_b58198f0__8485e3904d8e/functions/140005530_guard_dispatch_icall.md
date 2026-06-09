# _guard_dispatch_icall

- ea: `0x140005530`
- end: `0x140005536`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001540`
- `0x140001df0`
- `0x1400032e0`
- `0x1400041b0`
- `0x140004820`
- `0x1400051f0`
- `0x140006010`

## callees

- `0x140005560`

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
0x140005530  jmp     cs:__guard_dispatch_icall_fptr
```
