# _guard_dispatch_icall_nop

- ea: `0x180001150`
- end: `0x180001152`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001180`

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
0x180001150  jmp     rax
```
