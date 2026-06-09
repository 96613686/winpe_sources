# _guard_dispatch_icall_nop

- ea: `0x1800152f0`
- end: `0x1800152f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001430`
- `0x180001760`
- `0x180001a90`
- `0x180001ec0`
- `0x1800021b0`
- `0x180002610`
- `0x1800028f0`
- `0x180002bf0`
- `0x180003030`
- `0x180003410`
- `0x1800037a0`
- `0x180003950`
- `0x180003bc4`
- `0x180003dd8`
- `0x180015320`

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
0x1800152f0  jmp     rax
```
