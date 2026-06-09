# DllCanUnloadNow

- ea: `0x180006680`
- end: `0x18000668c`
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
  return dword_18001E36C != 0;
}

```

## disassembly

```asm
0x180006680  xor     eax, eax
0x180006682  cmp     cs:dword_18001E36C, eax
0x180006688  setnz   al
0x18000668b  retn
```
