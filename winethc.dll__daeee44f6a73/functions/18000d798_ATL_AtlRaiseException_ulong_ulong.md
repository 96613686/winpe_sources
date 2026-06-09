# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000d798`
- end: `0x18000d7a9`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800041f8`
- `0x180004220`
- `0x18000ab0c`
- `0x18001098c`
- `0x1800119fc`
- `0x180011ae0`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000d7a2`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000d798  xor     r9d, r9d
0x18000d79b  xor     r8d, r8d
0x18000d79e  lea     edx, [r9+1]
0x18000d7a2  jmp     cs:__imp_RaiseException
```
