# DllRegisterServer

- ea: `0x18000ac80`
- end: `0x18000ac83`
- name: `DllRegisterServer`
- size: `3`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return 0;
}

```

## disassembly

```asm
0x18000ac80  xor     eax, eax; DllRegisterServer
0x18000ac82  retn
```
