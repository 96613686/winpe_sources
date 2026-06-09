# _guard_dispatch_icall

- ea: `0x1400050f0`
- end: `0x1400050f6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001010`
- `0x140002000`
- `0x140002d70`
- `0x140002fc0`
- `0x140004bd0`
- `0x140004d48`
- `0x140006010`
- `0x14000d3e4`
- `0x14000e310`
- `0x14000e530`
- `0x14000fdc4`
- `0x140012e3c`
- `0x140015db0`
- `0x140018024`
- `0x140018b14`

## callees

- `0x140005120`

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
0x1400050f0  jmp     cs:__guard_dispatch_icall_fptr
```
