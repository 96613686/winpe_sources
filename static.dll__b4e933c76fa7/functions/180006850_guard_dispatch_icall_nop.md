# _guard_dispatch_icall_nop

- ea: `0x180006850`
- end: `0x180006852`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800013f0`
- `0x180001664`
- `0x180006880`
- `0x1800068b0`

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
0x180006850  jmp     rax
```
