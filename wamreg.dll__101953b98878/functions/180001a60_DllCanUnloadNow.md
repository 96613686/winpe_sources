# DllCanUnloadNow

- ea: `0x180001a60`
- end: `0x180001a6c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return g_dwRefCount != 0;
}

```

## disassembly

```asm
0x180001a60  xor     eax, eax
0x180001a62  cmp     cs:?g_dwRefCount@@3KA, eax; ulong g_dwRefCount
0x180001a68  setnz   al
0x180001a6b  retn
```
