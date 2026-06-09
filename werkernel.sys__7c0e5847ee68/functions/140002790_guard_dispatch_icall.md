# _guard_dispatch_icall

- ea: `0x140002790`
- end: `0x140002796`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001e68`
- `0x140001f88`
- `0x140002078`
- `0x140004010`
- `0x140010710`

## callees

- `0x1400027c0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140002790  jmp     cs:__guard_dispatch_icall_fptr
```
