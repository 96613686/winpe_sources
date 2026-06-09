# _guard_dispatch_icall_nop

- ea: `0x180003430`
- end: `0x180003432`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001dac`
- `0x180003460`
- `0x180003490`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180003430  jmp     rax
```
