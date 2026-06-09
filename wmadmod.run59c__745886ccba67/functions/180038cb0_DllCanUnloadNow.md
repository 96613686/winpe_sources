# DllCanUnloadNow

- ea: `0x180038cb0`
- end: `0x180038cce`
- name: `DllCanUnloadNow`
- size: `30`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180038cb0`

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
0x180038cb0  cmp     cs:dword_1800E1F84, 0
0x180038cb7  jg      short loc_180038CC8
0x180038cb9  mov     ecx, cs:dword_1800E1F80
0x180038cbf  xor     eax, eax
0x180038cc1  test    ecx, ecx
0x180038cc3  setnz   al
0x180038cc6  retn
0x180038cc8  mov     eax, 1
0x180038ccd  retn
```
