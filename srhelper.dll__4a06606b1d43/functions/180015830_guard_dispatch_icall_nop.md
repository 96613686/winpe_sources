# _guard_dispatch_icall_nop

- ea: `0x180015830`
- end: `0x180015832`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001380`
- `0x1800015f4`
- `0x180001ba4`
- `0x180015860`
- `0x1800158f0`

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
0x180015830  jmp     rax
```
