# _guard_dispatch_icall_nop

- ea: `0x180003700`
- end: `0x180003702`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001050`
- `0x1800012c4`
- `0x180003730`
- `0x180003760`

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
0x180003700  jmp     rax
```
