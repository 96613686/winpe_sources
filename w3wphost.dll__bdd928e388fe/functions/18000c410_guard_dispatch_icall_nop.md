# _guard_dispatch_icall_nop

- ea: `0x18000c410`
- end: `0x18000c412`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180002000`
- `0x180002274`
- `0x18000c440`
- `0x18000c470`

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
0x18000c410  jmp     rax
```
