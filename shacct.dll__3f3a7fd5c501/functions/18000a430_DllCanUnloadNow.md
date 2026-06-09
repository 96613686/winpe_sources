# DllCanUnloadNow

- ea: `0x18000a430`
- end: `0x18000a43c`
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
0x18000a430  xor     eax, eax
0x18000a432  cmp     cs:?g_cRefCount@@3JA, eax; long g_cRefCount
0x18000a438  setnz   al
0x18000a43b  retn
```
