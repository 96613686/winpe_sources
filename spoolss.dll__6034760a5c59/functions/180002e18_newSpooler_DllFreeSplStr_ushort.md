# newSpooler::DllFreeSplStr(ushort *)

- ea: `0x180002e18`
- end: `0x180002e25`
- name: `?DllFreeSplStr@newSpooler@@YAHPEAG@Z`
- size: `13`
- prototype: `__int64 __fastcall(newSpooler *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cfe0`

## callees

- `0x180002e18`
- `0x180002e2c`

## pseudocode

```c
_BOOL8 __fastcall newSpooler::DllFreeSplStr(newSpooler *this, void *a2)
{
  return this && newSpooler::DllFreeSplMem(this, a2);
}

```

## disassembly

```asm
0x180002e18  test    rcx, rcx
0x180002e1b  jnz     short loc_180002E20
0x180002e1d  xor     eax, eax
0x180002e1f  retn
0x180002e20  jmp     ?DllFreeSplMem@newSpooler@@YAHPEAX@Z; newSpooler::DllFreeSplMem(void *)
```
