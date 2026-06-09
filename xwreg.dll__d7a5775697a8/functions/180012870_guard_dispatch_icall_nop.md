# _guard_dispatch_icall_nop

- ea: `0x180012870`
- end: `0x180012872`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001b90`
- `0x180001e04`
- `0x1800023cc`
- `0x180012840`
- `0x1800128a0`

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
0x180012870  jmp     rax
```
