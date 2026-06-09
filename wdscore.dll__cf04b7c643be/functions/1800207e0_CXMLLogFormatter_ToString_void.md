# CXMLLogFormatter::ToString(void)

- ea: `0x1800207e0`
- end: `0x1800207e8`
- name: `?ToString@CXMLLogFormatter@@UEAAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(CXMLLogFormatter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x1800207e0`: `XMLLogFormatter`

## pseudocode

```c
const unsigned __int16 *__fastcall CXMLLogFormatter::ToString(CXMLLogFormatter *this)
{
  return L"XMLLogFormatter";
}

```

## disassembly

```asm
0x1800207e0  lea     rax, aXmllogformatte; "XMLLogFormatter"
0x1800207e7  retn
```
