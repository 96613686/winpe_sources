# _guard_dispatch_icall

- ea: `0x1400206e0`
- end: `0x1400206e6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `125`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001670`
- `0x140001b38`
- `0x140001efc`
- `0x1400021b8`
- `0x1400024c4`
- `0x1400024f0`
- `0x1400025a0`
- `0x140002ea8`
- `0x1400031c0`
- `0x140003a98`
- `0x140003ab8`
- `0x140003c60`
- `0x140004710`
- `0x1400049a0`
- `0x140004a10`
- `0x140004c68`
- `0x140004cc4`
- `0x140004eb8`
- `0x140005090`
- `0x1400051f0`
- `0x1400052cc`
- `0x140005934`
- `0x140005e60`
- `0x140005f84`
- `0x14000648c`
- `0x1400064b0`
- `0x140006550`
- `0x1400066b0`
- `0x140007320`
- `0x140007460`
- `0x1400074c8`
- `0x140007e10`
- `0x140007eb0`
- `0x140007fe0`
- `0x1400080bc`
- `0x140008afc`
- `0x140008bbc`
- `0x14000951c`
- `0x14000997c`
- `0x140009df4`
- `0x140009f10`
- `0x14000a02c`
- `0x14000a788`
- `0x14000a99c`
- `0x14000ae14`
- `0x14000ae78`
- `0x14000b344`
- `0x14000b7c0`
- `0x14000bb94`
- `0x14000bda4`

## callees

- `0x140020700`

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
0x1400206e0  jmp     cs:__guard_dispatch_icall_fptr
```
