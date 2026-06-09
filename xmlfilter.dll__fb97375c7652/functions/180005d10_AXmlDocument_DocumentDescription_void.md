# AXmlDocument::DocumentDescription(void)

- ea: `0x180005d10`
- end: `0x180005d15`
- name: `?DocumentDescription@AXmlDocument@@UEAAPEB_WXZ`
- size: `5`
- prototype: `const wchar_t *__fastcall(AXmlDocument *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
const wchar_t *__fastcall AXmlDocument::DocumentDescription(AXmlDocument *this)
{
  return (const wchar_t *)*((_QWORD *)this + 8);
}

```

## disassembly

```asm
0x180005d10  mov     rax, [rcx+40h]
0x180005d14  retn
```
