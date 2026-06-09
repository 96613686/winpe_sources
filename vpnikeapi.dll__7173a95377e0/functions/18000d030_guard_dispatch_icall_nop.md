# _guard_dispatch_icall_nop

- ea: `0x18000d030`
- end: `0x18000d032`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001770`
- `0x1800019e4`
- `0x180001df8`
- `0x18000d060`
- `0x18000d0f0`

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
0x18000d030  jmp     rax
```
