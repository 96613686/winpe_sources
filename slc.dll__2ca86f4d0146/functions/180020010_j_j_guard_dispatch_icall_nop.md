# j_j__guard_dispatch_icall_nop

- ea: `0x180020010`
- end: `0x180020015`
- name: `j_j__guard_dispatch_icall_nop`
- size: `5`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800010f0`
- `0x1800062f0`
- `0x180010df4`
- `0x180010e30`
- `0x1800167ac`
- `0x18001d9e8`
- `0x18001dd60`
- `0x18001e090`
- `0x18001e540`
- `0x18001e6c0`
- `0x18001e730`
- `0x18001e8d8`
- `0x18001e950`
- `0x18001f4d0`
- `0x18001f5b0`

## callees

- `0x18001fa10`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_j__guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180020010  jmp     j__guard_dispatch_icall_nop
```
