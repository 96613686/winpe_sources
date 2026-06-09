# _guard_dispatch_icall_nop

- ea: `0x180015600`
- end: `0x180015602`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180006780`
- `0x1800069f4`
- `0x180006d24`
- `0x180015630`
- `0x1800156c0`

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
0x180015600  jmp     rax
```
