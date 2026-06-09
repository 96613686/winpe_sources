# _guard_dispatch_icall_nop

- ea: `0x180002220`
- end: `0x180002222`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001560`
- `0x180001654`
- `0x1800018d0`
- `0x180001b50`

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
0x180002220  jmp     rax
```
