# DllUnregisterServer

- ea: `0x1800012a0`
- end: `0x1800012a3`
- name: `DllUnregisterServer`
- size: `3`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  return 0;
}

```

## disassembly

```asm
0x1800012a0  xor     eax, eax; DllCanUnloadNow
0x1800012a2  retn
```
