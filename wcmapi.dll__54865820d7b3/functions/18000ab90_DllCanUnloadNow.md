# DllCanUnloadNow

- ea: `0x18000ab90`
- end: `0x18000ab9c`
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
  return g_moduleRefs != 0;
}

```

## disassembly

```asm
0x18000ab90  xor     eax, eax
0x18000ab92  cmp     cs:?g_moduleRefs@@3JA, eax; long g_moduleRefs
0x18000ab98  setnz   al
0x18000ab9b  retn
```
