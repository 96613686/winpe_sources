# _guard_dispatch_icall

- ea: `0x140007df0`
- end: `0x140007e22`
- name: `_guard_dispatch_icall`
- size: `50`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400024f0`
- `0x1400025e0`
- `0x140002df0`
- `0x140003220`
- `0x140003fcc`
- `0x1400061e0`
- `0x140006cd4`
- `0x140006f6c`
- `0x140007444`
- `0x1400075c0`
- `0x1400075f4`
- `0x140007754`
- `0x140007850`
- `0x140009010`
- `0x1400146e0`
- `0x140014760`
- `0x1400148cc`
- `0x1400154c4`
- `0x140016200`
- `0x1400166e0`
- `0x1400167a0`
- `0x140016db0`
- `0x140016ed8`
- `0x140017058`
- `0x1400172dc`
- `0x140017810`
- `0x140017dec`
- `0x1400192e0`
- `0x14001a090`
- `0x14001a160`
- `0x14001b0c0`
- `0x14001b5cc`
- `0x14001ba1c`

## callees

- `0x140007df0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140007df0  jmp     cs:__guard_dispatch_icall_fptr
0x140007e20  jmp     rax
```
