# _guard_dispatch_icall_nop

- ea: `0x1800932f0`
- end: `0x1800932f2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `200`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001ca0`
- `0x180002320`
- `0x180003da0`
- `0x1800063f0`
- `0x180006500`
- `0x180007270`
- `0x1800074c0`
- `0x180007a30`
- `0x180007c00`
- `0x1800087d0`
- `0x180009030`
- `0x18000a800`
- `0x18000a990`
- `0x18000aa90`
- `0x18000ad10`
- `0x18000aec0`
- `0x18000af90`
- `0x18000b110`
- `0x18000b420`
- `0x18000b4a0`
- `0x18000b740`
- `0x18000c2c4`
- `0x18000c5c0`
- `0x18000ca70`
- `0x18000dbc0`
- `0x18000dcb0`
- `0x18000df24`
- `0x18000e0e0`
- `0x18000e160`
- `0x18000e1f8`
- `0x18000e380`
- `0x18000e43c`
- `0x18000eca0`
- `0x18000f170`
- `0x18000fe48`
- `0x1800197bc`
- `0x180019960`
- `0x180019d00`
- `0x180019e78`
- `0x18001a1c0`
- `0x18001abe0`
- `0x18001ae0c`
- `0x18001af70`
- `0x18001b070`
- `0x18001b170`
- `0x18001b1a0`
- `0x18001b260`
- `0x18001b360`
- `0x18001b470`
- `0x18001b4a0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x1800932f0  jmp     rax
```
