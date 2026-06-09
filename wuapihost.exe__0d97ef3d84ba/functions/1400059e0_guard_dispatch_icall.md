# _guard_dispatch_icall

- ea: `0x1400059e0`
- end: `0x1400059e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001008`
- `0x140001140`
- `0x140001200`
- `0x140001340`
- `0x140001620`
- `0x14000200c`
- `0x140002050`
- `0x140002348`
- `0x140002bc0`
- `0x14000327c`
- `0x1400040e0`
- `0x140005504`

## callees

- `0x140005a00`

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
0x1400059e0  jmp     cs:__guard_dispatch_icall_fptr
```
