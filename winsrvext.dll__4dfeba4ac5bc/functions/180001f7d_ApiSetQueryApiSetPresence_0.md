# ApiSetQueryApiSetPresence_0

- ea: `0x180001f7d`
- end: `0x180001f83`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d88`
- `0x180001e68`
- `0x180001f8c`
- `0x180001fe0`
- `0x180002034`
- `0x180002088`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x180001f7d`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ApiSetQueryApiSetPresence_0(__int64 a1, __int64 a2)
{
  return ApiSetQueryApiSetPresence(a1, a2);
}

```

## disassembly

```asm
0x180001f7d  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
