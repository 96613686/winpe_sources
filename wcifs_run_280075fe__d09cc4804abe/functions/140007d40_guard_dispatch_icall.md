# _guard_dispatch_icall

- ea: `0x140007d40`
- end: `0x140007d46`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001c44`
- `0x140001dec`
- `0x1400020c4`
- `0x140002294`
- `0x140002ab4`
- `0x140002e48`
- `0x140004198`
- `0x140004310`
- `0x140004448`
- `0x14000465c`
- `0x1400048a4`
- `0x140004b0c`
- `0x140004d7c`
- `0x140004f40`
- `0x140005050`
- `0x1400051b0`
- `0x1400053f8`
- `0x1400055c4`
- `0x1400057a0`
- `0x1400059b4`
- `0x140005c0c`
- `0x140005ef8`
- `0x14000601c`
- `0x140006814`
- `0x140009080`
- `0x14001b794`
- `0x14001b83c`
- `0x14001b904`
- `0x14001ba50`
- `0x14002e9e0`
- `0x140034de0`

## callees

- `0x140007ce0`

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
0x140007d40  jmp     cs:__guard_dispatch_icall_fptr
```
