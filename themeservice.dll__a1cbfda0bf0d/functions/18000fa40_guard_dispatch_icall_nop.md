# _guard_dispatch_icall_nop

- ea: `0x18000fa40`
- end: `0x18000fa42`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800074c0`
- `0x180007734`
- `0x180007948`
- `0x18000fa70`
- `0x18000fb00`

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
0x18000fa40  jmp     rax
```
