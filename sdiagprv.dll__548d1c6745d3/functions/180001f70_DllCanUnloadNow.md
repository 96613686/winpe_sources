# DllCanUnloadNow

- ea: `0x180001f70`
- end: `0x180001f7c`
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
  return g_Count != 0;
}

```

## disassembly

```asm
0x180001f70  xor     eax, eax
0x180001f72  cmp     cs:?g_Count@@3JA, eax; long g_Count
0x180001f78  setnz   al
0x180001f7b  retn
```
