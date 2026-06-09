# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x14000539c`
- end: `0x1400053ad`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003004`
- `0x14000302c`
- `0x140003924`
- `0x140004c18`
- `0x140006140`
- `0x1400061fc`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400053a6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x14000539c  xor     r9d, r9d
0x14000539f  xor     r8d, r8d
0x1400053a2  lea     edx, [r9+1]
0x1400053a6  jmp     cs:__imp_RaiseException
```
