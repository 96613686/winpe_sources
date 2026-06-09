# TrkRaiseException(long)

- ea: `0x18000d39c`
- end: `0x18000d3ab`
- name: `?TrkRaiseException@@YAXJ@Z`
- size: `15`
- prototype: `void __fastcall(DWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003798`
- `0x180006a80`
- `0x18000756c`
- `0x1800090c8`
- `0x18000a65c`
- `0x18000f22c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d3a4`

## pseudocode

```c
void __fastcall TrkRaiseException(DWORD a1)
{
  RaiseException(a1, 0, 0, 0);
}

```

## disassembly

```asm
0x18000d39c  xor     r9d, r9d
0x18000d39f  xor     r8d, r8d
0x18000d3a2  xor     edx, edx
0x18000d3a4  jmp     cs:__imp_RaiseException
```
