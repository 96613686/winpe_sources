# _guard_dispatch_icall

- ea: `0x140010700`
- end: `0x140010706`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `120`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001020`
- `0x1400010e0`
- `0x1400011c8`
- `0x1400012b4`
- `0x1400013d0`
- `0x1400014bc`
- `0x1400015d8`
- `0x14000174c`
- `0x140001840`
- `0x14000193c`
- `0x140001a4c`
- `0x140001b4c`
- `0x140001c30`
- `0x140001d24`
- `0x140001e04`
- `0x1400024d0`
- `0x14000264c`
- `0x1400026d0`
- `0x14000334c`
- `0x1400034cc`
- `0x140003990`
- `0x140003a20`
- `0x140003e7c`
- `0x140004130`
- `0x1400043cc`
- `0x140004740`
- `0x140004908`
- `0x140004ea4`
- `0x14000529c`
- `0x1400053d4`
- `0x1400055fc`
- `0x140005838`
- `0x140005fe8`
- `0x1400062f4`
- `0x140006408`
- `0x140006504`
- `0x1400065e0`
- `0x140006acc`
- `0x140006cb0`
- `0x140006dec`
- `0x140007694`
- `0x1400079c8`
- `0x140007b3c`
- `0x140007fdc`
- `0x140008388`
- `0x14000866c`
- `0x1400087a0`
- `0x1400088a0`
- `0x140008aa4`
- `0x140008d10`

## callees

- `0x140010730`

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
0x140010700  jmp     cs:__guard_dispatch_icall_fptr
```
