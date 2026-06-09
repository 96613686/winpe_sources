# _guard_dispatch_icall_nop

- ea: `0x1800031a0`
- end: `0x1800031a2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001870`
- `0x180001ae4`
- `0x1800031d0`
- `0x180003200`

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
0x1800031a0  jmp     rax
```
