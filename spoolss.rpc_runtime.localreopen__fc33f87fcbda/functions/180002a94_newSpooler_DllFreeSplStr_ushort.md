# newSpooler::DllFreeSplStr(ushort *)

- ea: `0x180002a94`
- end: `0x180002aa2`
- name: `?DllFreeSplStr@newSpooler@@YAHPEAG@Z`
- size: `14`
- prototype: `__int64 __fastcall(newSpooler *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dbf0`

## callees

- `0x180002a94`
- `0x18000300c`

## pseudocode

```c
_BOOL8 __fastcall newSpooler::DllFreeSplStr(newSpooler *this, void *a2)
{
  return this && newSpooler::DllFreeSplMem(this, a2);
}

```

## disassembly

```asm
0x180002a94  test    rcx, rcx
0x180002a97  jnz     short loc_180002A9D
0x180002a99  xor     eax, eax
0x180002a9b  retn
0x180002a9d  jmp     ?DllFreeSplMem@newSpooler@@YAHPEAX@Z; newSpooler::DllFreeSplMem(void *)
```
