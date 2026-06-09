# _bstr_t::length(void)

- ea: `0x180007294`
- end: `0x1800072ae`
- name: `?length@_bstr_t@@QEBAIXZ`
- size: `26`
- prototype: `UINT __fastcall(OLECHAR ***this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b1c`
- `0x1800090d4`
- `0x180009c50`
- `0x180009d50`
- `0x18000b96c`
- `0x18000bfa0`

## callees

- `0x180007294`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800072a4`

## pseudocode

```c
UINT __fastcall _bstr_t::length(OLECHAR ***this)
{
  OLECHAR **v1; // rcx
  OLECHAR *v2; // rcx

  v1 = *this;
  if ( v1 && (v2 = *v1) != 0 )
    return SysStringLen(v2);
  else
    return 0;
}

```

## disassembly

```asm
0x180007294  mov     rcx, [rcx]
0x180007297  test    rcx, rcx
0x18000729a  jz      short loc_1800072AB
0x18000729c  mov     rcx, [rcx]
0x18000729f  test    rcx, rcx
0x1800072a2  jz      short loc_1800072AB
0x1800072a4  jmp     cs:__imp_SysStringLen
0x1800072ab  xor     eax, eax
0x1800072ad  retn
```
