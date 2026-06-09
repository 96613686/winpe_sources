# DllCanUnloadNow

- ea: `0x180002a10`
- end: `0x180002a1c`
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
0x180002a10  xor     eax, eax
0x180002a12  cmp     cs:?g_Count@@3JA, eax; long g_Count
0x180002a18  setnz   al
0x180002a1b  retn
```
