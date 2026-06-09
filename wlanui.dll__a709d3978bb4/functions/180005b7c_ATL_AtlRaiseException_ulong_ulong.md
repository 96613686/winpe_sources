# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005b7c`
- end: `0x180005b8d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003870`
- `0x180003898`
- `0x18000418c`
- `0x180005418`
- `0x1800146bc`
- `0x18001477c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180005b86`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005b7c  xor     r9d, r9d
0x180005b7f  xor     r8d, r8d
0x180005b82  lea     edx, [r9+1]
0x180005b86  jmp     cs:__imp_RaiseException
```
