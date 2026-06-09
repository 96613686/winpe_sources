# DllCanUnloadNow

- ea: `0x18000a0f0`
- end: `0x18000a0fc`
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
  return dword_18001D9DC != 0;
}

```

## disassembly

```asm
0x18000a0f0  xor     eax, eax
0x18000a0f2  cmp     cs:dword_18001D9DC, eax
0x18000a0f8  setnz   al
0x18000a0fb  retn
```
