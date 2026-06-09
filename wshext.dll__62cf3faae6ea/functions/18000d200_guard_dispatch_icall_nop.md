# _guard_dispatch_icall_nop

- ea: `0x18000d200`
- end: `0x18000d202`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180003280`
- `0x1800034f4`
- `0x18000d230`
- `0x18000d2c0`

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
0x18000d200  jmp     rax
```
