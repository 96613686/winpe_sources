# _guard_dispatch_icall

- ea: `0x14001ef70`
- end: `0x14001ef76`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `29`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001c30`
- `0x1400020e0`
- `0x140006340`
- `0x140006558`
- `0x140006764`
- `0x140006b74`
- `0x140006f04`
- `0x140009620`
- `0x14000a680`
- `0x14000b5e0`
- `0x14000c230`
- `0x14000c618`
- `0x14000dda0`
- `0x140013708`
- `0x1400138e4`
- `0x14001492c`
- `0x14001515c`
- `0x140015400`
- `0x140015550`
- `0x140017b94`
- `0x140017c1c`
- `0x140017cfc`
- `0x14001b4b4`
- `0x14001d450`
- `0x140020010`
- `0x140033890`
- `0x140034550`
- `0x140034678`
- `0x1400346f0`

## callees

- `0x14001efa0`

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
0x14001ef70  jmp     cs:__guard_dispatch_icall_fptr
```
