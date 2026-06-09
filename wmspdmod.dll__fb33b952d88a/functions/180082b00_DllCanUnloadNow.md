# DllCanUnloadNow

- ea: `0x180082b00`
- end: `0x180082b1e`
- name: `DllCanUnloadNow`
- size: `30`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180082b00`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_18011B84C > 0 )
    LODWORD(v0) = 1;
  else
    return dword_18011B848 != 0;
  return v0;
}

```

## disassembly

```asm
0x180082b00  cmp     cs:dword_18011B84C, 0
0x180082b07  jg      short loc_180082B18
0x180082b09  mov     ecx, cs:dword_18011B848
0x180082b0f  xor     eax, eax
0x180082b11  test    ecx, ecx
0x180082b13  setnz   al
0x180082b16  retn
0x180082b18  mov     eax, 1
0x180082b1d  retn
```
