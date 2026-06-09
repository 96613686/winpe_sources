# _guard_dispatch_icall_nop

- ea: `0x1800031f0`
- end: `0x1800031f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001150`
- `0x1800013c4`
- `0x180003220`
- `0x180003250`

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
0x1800031f0  jmp     rax
```
