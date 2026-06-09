# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x140005b9c`
- end: `0x140005bad`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003298`
- `0x1400032c0`
- `0x140003f2c`
- `0x140005294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140005ba6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x140005b9c  xor     r9d, r9d
0x140005b9f  xor     r8d, r8d
0x140005ba2  lea     edx, [r9+1]
0x140005ba6  jmp     cs:__imp_RaiseException
```
