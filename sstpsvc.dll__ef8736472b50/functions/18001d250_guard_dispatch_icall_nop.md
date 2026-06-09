# _guard_dispatch_icall_nop

- ea: `0x18001d250`
- end: `0x18001d252`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180009110`
- `0x180009384`
- `0x180009a4c`
- `0x18001d280`
- `0x18001d310`

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
0x18001d250  jmp     rax
```
