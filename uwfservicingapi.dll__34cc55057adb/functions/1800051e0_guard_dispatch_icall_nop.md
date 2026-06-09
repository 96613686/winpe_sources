# _guard_dispatch_icall_nop

- ea: `0x1800051e0`
- end: `0x1800051e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010b0`
- `0x180001324`
- `0x18000175c`
- `0x180005210`
- `0x180005240`

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
0x1800051e0  jmp     rax
```
