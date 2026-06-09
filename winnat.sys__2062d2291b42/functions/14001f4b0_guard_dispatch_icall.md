# _guard_dispatch_icall

- ea: `0x14001f4b0`
- end: `0x14001f4b6`
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
- `0x14000dd70`
- `0x140011fc0`
- `0x140012048`
- `0x140012128`
- `0x140014048`
- `0x140014224`
- `0x14001526c`
- `0x140015ad8`
- `0x140015d7c`
- `0x140015ecc`
- `0x14001b994`
- `0x14001d930`
- `0x140020010`
- `0x140034b50`
- `0x140035860`
- `0x140035988`
- `0x140035a00`

## callees

- `0x14001f4e0`

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
0x14001f4b0  jmp     cs:__guard_dispatch_icall_fptr
```
