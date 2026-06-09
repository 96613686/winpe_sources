# DllCanUnloadNow

- ea: `0x180005970`
- end: `0x18000597e`
- name: `DllCanUnloadNow`
- size: `14`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return g_Count != 0;
}

```

## disassembly

```asm
0x180005970  mov     eax, cs:?g_Count@@3JA; long g_Count
0x180005976  neg     eax
0x180005978  sbb     eax, eax
0x18000597a  and     eax, 1
0x18000597d  retn
```
