# _guard_dispatch_icall_nop

- ea: `0x180006890`
- end: `0x180006892`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010d0`
- `0x180001344`
- `0x180001748`
- `0x1800068c0`
- `0x1800068f0`

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
0x180006890  jmp     rax
```
