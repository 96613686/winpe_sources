# _guard_dispatch_icall_nop

- ea: `0x180018130`
- end: `0x180018132`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001100`
- `0x180001374`
- `0x180018160`
- `0x180018190`

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
0x180018130  jmp     rax
```
