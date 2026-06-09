# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180004a7c`
- end: `0x180004a8d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(DWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002248`
- `0x180002f58`
- `0x180003394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004a86`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180004a7c  xor     r9d, r9d
0x180004a7f  xor     r8d, r8d
0x180004a82  lea     edx, [r9+1]
0x180004a86  jmp     cs:__imp_RaiseException
```
