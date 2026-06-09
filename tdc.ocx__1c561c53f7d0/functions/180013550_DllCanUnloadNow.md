# DllCanUnloadNow

- ea: `0x180013550`
- end: `0x18001355c`
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
  return dword_18001BD7C != 0;
}

```

## disassembly

```asm
0x180013550  xor     eax, eax
0x180013552  cmp     cs:dword_18001BD7C, eax
0x180013558  setnz   al
0x18001355b  retn
```
