# DllCanUnloadNow

- ea: `0x180038cf0`
- end: `0x180038d0e`
- name: `DllCanUnloadNow`
- size: `30`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180038cf0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( dword_1800E1F84 > 0 )
    LODWORD(v0) = 1;
  else
    return dword_1800E1F80 != 0;
  return v0;
}

```

## disassembly

```asm
0x180038cf0  cmp     cs:dword_1800E1F84, 0
0x180038cf7  jg      short loc_180038D08
0x180038cf9  mov     ecx, cs:dword_1800E1F80
0x180038cff  xor     eax, eax
0x180038d01  test    ecx, ecx
0x180038d03  setnz   al
0x180038d06  retn
0x180038d08  mov     eax, 1
0x180038d0d  retn
```
