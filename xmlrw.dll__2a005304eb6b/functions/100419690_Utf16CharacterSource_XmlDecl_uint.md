# Utf16CharacterSource::XmlDecl(uint *)

- ea: `0x100419690`
- end: `0x10041969e`
- name: `?XmlDecl@Utf16CharacterSource@@UEAAPEBEPEAI@Z`
- size: `14`
- prototype: `const unsigned __int8 *__fastcall(Utf16CharacterSource *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x100419696`: `<?xml version="1.0"?>`

## pseudocode

```c
const wchar_t *__fastcall Utf16CharacterSource::XmlDecl(Utf16CharacterSource *this, unsigned int *a2)
{
  *a2 = 42;
  return L"<?xml version=\"1.0\"?>";
}

```

## disassembly

```asm
0x100419690  mov     dword ptr [rdx], 2Ah ; '*'
0x100419696  lea     rax, aXmlVersion10_0; "<?xml version=\"1.0\"?>"
0x10041969d  retn
```
