# _guard_dispatch_icall

- ea: `0x140008d60`
- end: `0x140008d66`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005aac`
- `0x14000666c`
- `0x140007e78`
- `0x140007ea8`
- `0x140007f00`
- `0x140007f48`
- `0x140007fe8`
- `0x140008250`
- `0x14000829c`
- `0x140008304`
- `0x140008368`
- `0x1400083b4`
- `0x140008410`
- `0x1400086c0`
- `0x140008880`
- `0x14000a010`
- `0x140011dd0`
- `0x140013408`
- `0x14001348c`
- `0x140013520`
- `0x140013670`

## callees

- `0x140008d90`

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
0x140008d60  jmp     cs:__guard_dispatch_icall_fptr
```
