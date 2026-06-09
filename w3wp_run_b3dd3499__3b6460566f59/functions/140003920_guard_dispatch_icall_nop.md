# _guard_dispatch_icall_nop

- ea: `0x140003920`
- end: `0x140003922`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001140`
- `0x140003950`
- `0x140003980`

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
0x140003920  jmp     rax
```
