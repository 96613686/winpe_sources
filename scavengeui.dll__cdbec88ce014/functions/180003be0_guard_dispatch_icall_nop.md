# _guard_dispatch_icall_nop

- ea: `0x180003be0`
- end: `0x180003be2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001a00`
- `0x180001c74`
- `0x180001f14`
- `0x180003bb0`
- `0x180003c10`

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
0x180003be0  jmp     rax
```
