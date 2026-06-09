# _guard_dispatch_icall

- ea: `0x140002c90`
- end: `0x140002c96`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001c54`
- `0x140001ef0`
- `0x140001fe4`
- `0x140002950`
- `0x140004050`
- `0x1400090e0`
- `0x140009aa0`
- `0x14000a230`
- `0x14000a670`
- `0x14000b8b0`
- `0x14000c078`
- `0x14000c2d0`
- `0x14000c4d0`

## callees

- `0x140002c30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140002c90  jmp     cs:__guard_dispatch_icall_fptr
```
