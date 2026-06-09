# _guard_dispatch_icall_nop

- ea: `0x1800160e0`
- end: `0x1800160e2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180013620`
- `0x180013894`
- `0x180016110`
- `0x1800161a0`

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
0x1800160e0  jmp     rax
```
