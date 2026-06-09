# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180005404`
- end: `0x180005415`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000335c`
- `0x180003384`
- `0x180003c7c`
- `0x1800079d4`
- `0x180008b98`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000540e`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180005404  xor     r9d, r9d
0x180005407  xor     r8d, r8d
0x18000540a  lea     edx, [r9+1]
0x18000540e  jmp     cs:__imp_RaiseException
```
