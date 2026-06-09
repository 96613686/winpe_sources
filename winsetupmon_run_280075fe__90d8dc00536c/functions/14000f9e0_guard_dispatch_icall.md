# _guard_dispatch_icall

- ea: `0x14000f9e0`
- end: `0x14000f9e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `47`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001404`
- `0x140001674`
- `0x140001748`
- `0x1400018a8`
- `0x140001a10`
- `0x140001a94`
- `0x1400022f0`
- `0x140005164`
- `0x140007fec`
- `0x14000816c`
- `0x1400099e0`
- `0x140009ee0`
- `0x14000a300`
- `0x14000a4b0`
- `0x14000a598`
- `0x14000a7a4`
- `0x14000aa00`
- `0x14000aa40`
- `0x14000aa90`
- `0x14000aad0`
- `0x14000ab20`
- `0x14000ab4c`
- `0x14000adb8`
- `0x14000b064`
- `0x14000b1b4`
- `0x14000b550`
- `0x14000b970`
- `0x14000baf0`
- `0x14000bc00`
- `0x14000bc70`
- `0x14000bcdc`
- `0x14000bdf0`
- `0x14000bf50`
- `0x14000c590`
- `0x14000c6f0`
- `0x14000c9b0`
- `0x14000cad0`
- `0x14000d300`
- `0x14000d380`
- `0x14000d440`
- `0x14000d4b0`
- `0x140011030`
- `0x140020130`
- `0x1400201b0`
- `0x140020d14`
- `0x140021b30`
- `0x140022078`

## callees

- `0x14000f980`

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
0x14000f9e0  jmp     cs:__guard_dispatch_icall_fptr
```
