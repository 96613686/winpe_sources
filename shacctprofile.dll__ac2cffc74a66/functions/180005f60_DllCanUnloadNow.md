# DllCanUnloadNow

- ea: `0x180005f60`
- end: `0x180005f6c`
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
  return g_cRefCount != 0;
}

```

## disassembly

```asm
0x180005f60  xor     eax, eax
0x180005f62  cmp     cs:?g_cRefCount@@3JA, eax; long g_cRefCount
0x180005f68  setnz   al
0x180005f6b  retn
```
