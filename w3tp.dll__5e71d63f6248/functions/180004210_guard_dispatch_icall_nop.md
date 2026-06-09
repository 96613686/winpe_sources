# _guard_dispatch_icall_nop

- ea: `0x180004210`
- end: `0x180004212`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001fe0`
- `0x180002254`
- `0x180004240`
- `0x180004270`

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
0x180004210  jmp     rax
```
