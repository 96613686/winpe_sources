# DllCanUnloadNow

- ea: `0x180003c20`
- end: `0x180003c2e`
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
  return g_HandlerInstanceCount != 0;
}

```

## disassembly

```asm
0x180003c20  mov     ecx, cs:g_HandlerInstanceCount
0x180003c26  xor     eax, eax
0x180003c28  test    ecx, ecx
0x180003c2a  setnz   al
0x180003c2d  retn
```
