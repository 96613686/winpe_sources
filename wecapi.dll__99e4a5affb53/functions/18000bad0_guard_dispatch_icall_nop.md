# _guard_dispatch_icall_nop

- ea: `0x18000bad0`
- end: `0x18000bad2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800014b0`
- `0x180001724`
- `0x180001948`
- `0x18000baa0`
- `0x18000bb00`

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
0x18000bad0  jmp     rax
```
