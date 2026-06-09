# _guard_dispatch_icall_nop

- ea: `0x1800189b0`
- end: `0x1800189b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180010b10`
- `0x180010d84`
- `0x1800189e0`
- `0x180018a70`

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
0x1800189b0  jmp     rax
```
