# DllCanUnloadNow

- ea: `0x180018ff0`
- end: `0x180019008`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018ff0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 0;
  if ( dword_180028594 || dword_180028590 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180018ff0  xor     eax, eax
0x180018ff2  cmp     cs:dword_180028594, eax
0x180018ff8  jnz     short loc_180019002
0x180018ffa  cmp     cs:dword_180028590, eax
0x180019000  jz      short locret_180019007
0x180019002  mov     eax, 1
0x180019007  retn
```
