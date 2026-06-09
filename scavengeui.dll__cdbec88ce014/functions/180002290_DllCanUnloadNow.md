# DllCanUnloadNow

- ea: `0x180002290`
- end: `0x18000229e`
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
  return dword_18000A8D4 != 0;
}

```

## disassembly

```asm
0x180002290  mov     ecx, cs:dword_18000A8D4
0x180002296  xor     eax, eax
0x180002298  test    ecx, ecx
0x18000229a  setnz   al
0x18000229d  retn
```
