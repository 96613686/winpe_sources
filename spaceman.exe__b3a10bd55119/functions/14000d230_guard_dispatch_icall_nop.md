# _guard_dispatch_icall_nop

- ea: `0x14000d230`
- end: `0x14000d232`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001520`
- `0x140001a00`
- `0x14000d260`
- `0x14000d2f0`

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
0x14000d230  jmp     rax
```
