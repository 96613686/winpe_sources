# _guard_dispatch_icall

- ea: `0x140009c90`
- end: `0x140009c96`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `127`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400011c0`
- `0x140001620`
- `0x140001a38`
- `0x140001d00`
- `0x140001ef0`
- `0x140002358`
- `0x1400026d0`
- `0x140002830`
- `0x140002d60`
- `0x140002f80`
- `0x1400030b0`
- `0x140003240`
- `0x140003370`
- `0x1400034b0`
- `0x140003b70`
- `0x1400046b0`
- `0x140004a00`
- `0x140005140`
- `0x140005220`
- `0x1400053c0`
- `0x140005500`
- `0x1400059c0`
- `0x140005f40`
- `0x140006000`
- `0x140006b50`
- `0x140006e60`
- `0x140006f00`
- `0x140007010`
- `0x140007160`
- `0x140007480`
- `0x140007550`
- `0x140007660`
- `0x14000786c`
- `0x1400078dc`
- `0x140007980`
- `0x140007ad8`
- `0x140007bec`
- `0x140007cc4`
- `0x140007e40`
- `0x1400080c0`
- `0x140008270`
- `0x140008310`
- `0x140008420`
- `0x140008610`
- `0x140008750`
- `0x1400087f0`
- `0x1400088c0`
- `0x140008970`
- `0x140008a80`
- `0x140008ef0`

## callees

- `0x140009cc0`

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
0x140009c90  jmp     cs:__guard_dispatch_icall_fptr
```
