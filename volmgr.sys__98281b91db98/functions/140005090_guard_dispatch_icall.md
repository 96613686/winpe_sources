# _guard_dispatch_icall

- ea: `0x140005090`
- end: `0x140005096`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `64`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400015a0`
- `0x1400018e0`
- `0x140001ae0`
- `0x140002b30`
- `0x140002c90`
- `0x140003000`
- `0x140003c50`
- `0x140003cf0`
- `0x1400044c0`
- `0x140004b40`
- `0x140006010`
- `0x14000e010`
- `0x14000e150`
- `0x14000e270`
- `0x14000e400`
- `0x14000e54c`
- `0x14000e888`
- `0x14000eba0`
- `0x14000f19c`
- `0x14000f3b0`
- `0x14000f950`
- `0x14000fbf8`
- `0x140010898`
- `0x14001171c`
- `0x140011920`
- `0x140012128`
- `0x14001218c`
- `0x140012524`
- `0x14001256c`
- `0x140012710`
- `0x140012964`
- `0x140012cf4`
- `0x140012d60`
- `0x140012db4`
- `0x140012f18`
- `0x140013138`
- `0x1400132f8`
- `0x1400134c8`
- `0x140013594`
- `0x1400136b8`
- `0x1400139b4`
- `0x140013ba0`
- `0x140013e00`
- `0x14001462c`
- `0x1400147dc`
- `0x140014838`
- `0x1400149e8`
- `0x140014b30`
- `0x140014b80`
- `0x1400151a0`

## callees

- `0x1400050c0`

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
0x140005090  jmp     cs:__guard_dispatch_icall_fptr
```
