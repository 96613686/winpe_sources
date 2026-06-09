# _guard_dispatch_icall_nop

- ea: `0x18001f9b0`
- end: `0x18001f9b2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18001c350`
- `0x18001c5c4`
- `0x18001c7d8`
- `0x18001f9e0`
- `0x18001fa10`

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
0x18001f9b0  jmp     rax
```
