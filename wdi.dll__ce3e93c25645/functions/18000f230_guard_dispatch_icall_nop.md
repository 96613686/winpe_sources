# _guard_dispatch_icall_nop

- ea: `0x18000f230`
- end: `0x18000f232`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180007fe0`
- `0x180008254`
- `0x18000f260`
- `0x18000f290`

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
0x18000f230  jmp     rax
```
