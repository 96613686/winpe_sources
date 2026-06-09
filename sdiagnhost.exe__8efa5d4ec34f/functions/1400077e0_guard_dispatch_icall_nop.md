# _guard_dispatch_icall_nop

- ea: `0x1400077e0`
- end: `0x1400077e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001530`
- `0x14000180c`
- `0x1400077b0`
- `0x140007810`

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
0x1400077e0  jmp     rax
```
