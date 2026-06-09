# _guard_dispatch_icall

- ea: `0x1800339c0`
- end: `0x1800339c6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007338`
- `0x18001b550`
- `0x180022a80`
- `0x180023390`
- `0x180023e94`
- `0x180024be8`
- `0x180025888`
- `0x180026024`
- `0x180026108`
- `0x180027604`
- `0x180027c78`
- `0x180028e98`
- `0x180029120`
- `0x180029420`
- `0x18002aee8`
- `0x180034010`

## callees

- `0x1800339f0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1800339c0  jmp     cs:__guard_dispatch_icall_fptr
```
