# _guard_dispatch_icall_nop

- ea: `0x140014950`
- end: `0x140014952`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400013e0`
- `0x140001678`
- `0x140014980`
- `0x140014a10`

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
0x140014950  jmp     rax
```
