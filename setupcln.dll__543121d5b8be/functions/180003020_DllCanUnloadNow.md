# DllCanUnloadNow

- ea: `0x180003020`
- end: `0x18000302e`
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
  return dword_18001FBD4 != 0;
}

```

## disassembly

```asm
0x180003020  mov     ecx, cs:dword_18001FBD4
0x180003026  xor     eax, eax
0x180003028  test    ecx, ecx
0x18000302a  setnz   al
0x18000302d  retn
```
