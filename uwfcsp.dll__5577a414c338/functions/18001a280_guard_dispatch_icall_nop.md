# _guard_dispatch_icall_nop

- ea: `0x18001a280`
- end: `0x18001a282`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180003600`
- `0x180003874`
- `0x180003a98`
- `0x18001a250`
- `0x18001a2b0`

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
0x18001a280  jmp     rax
```
