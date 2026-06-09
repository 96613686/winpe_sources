# _guard_dispatch_icall_nop

- ea: `0x180002990`
- end: `0x180002992`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001330`
- `0x1800015a4`
- `0x1800029c0`
- `0x1800029f0`

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
0x180002990  jmp     rax
```
