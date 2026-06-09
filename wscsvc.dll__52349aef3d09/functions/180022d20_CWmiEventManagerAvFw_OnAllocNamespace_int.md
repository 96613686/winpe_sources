# CWmiEventManagerAvFw::OnAllocNamespace(int)

- ea: `0x180022d20`
- end: `0x180022d39`
- name: `?OnAllocNamespace@CWmiEventManagerAvFw@@MEAAPEAGH@Z`
- size: `25`
- prototype: `BSTR __fastcall(CWmiEventManagerAvFw *this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022d20`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022d32`

## string_xrefs

- `0x180022d20`: `ROOT\SecurityCenter2`
- `0x180022d2b`: `ROOT\SecurityCenter`

## pseudocode

```c
BSTR __fastcall CWmiEventManagerAvFw::OnAllocNamespace(CWmiEventManagerAvFw *this, int a2)
{
  const OLECHAR *v2; // rcx

  v2 = L"ROOT\\SecurityCenter2";
  if ( !a2 )
    v2 = L"ROOT\\SecurityCenter";
  return SysAllocString(v2);
}

```

## disassembly

```asm
0x180022d20  lea     rcx, aRootSecurityce; "ROOT\\SecurityCenter2"
0x180022d27  test    edx, edx
0x180022d29  jnz     short loc_180022D32
0x180022d2b  lea     rcx, aRootSecurityce_0; "ROOT\\SecurityCenter"
0x180022d32  jmp     cs:__imp_SysAllocString
```
