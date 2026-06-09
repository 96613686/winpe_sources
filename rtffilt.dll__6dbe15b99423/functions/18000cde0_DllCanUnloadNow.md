# DllCanUnloadNow

- ea: `0x18000cde0`
- end: `0x18000cdec`
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
  return g_cInstances != 0;
}

```

## disassembly

```asm
0x18000cde0  xor     eax, eax
0x18000cde2  cmp     cs:?g_cInstances@@3JA, eax; long g_cInstances
0x18000cde8  setnz   al
0x18000cdeb  retn
```
