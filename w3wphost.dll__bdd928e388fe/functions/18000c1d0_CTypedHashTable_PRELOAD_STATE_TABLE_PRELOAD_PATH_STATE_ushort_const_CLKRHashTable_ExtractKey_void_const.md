# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_ExtractKey(void const *)

- ea: `0x18000c1d0`
- end: `0x18000c1e2`
- name: `?_ExtractKey@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
const unsigned __int16 *__fastcall CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_ExtractKey(
        __int64 a1)
{
  const unsigned __int16 *result; // rax

  result = &dword_18000EB74;
  if ( *(_QWORD *)(a1 + 8) )
    return *(const unsigned __int16 **)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x18000c1d0  cmp     qword ptr [rcx+8], 0
0x18000c1d5  lea     rax, dword_18000EB74
0x18000c1dc  cmovnz  rax, [rcx+8]
0x18000c1e1  retn
```
