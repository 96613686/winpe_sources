# Utf8CharacterSource::XmlDecl(uint *)

- ea: `0x100419190`
- end: `0x10041919e`
- name: `?XmlDecl@Utf8CharacterSource@@UEAAPEBEPEAI@Z`
- size: `14`
- prototype: `const unsigned __int8 *__fastcall(Utf8CharacterSource *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x100419196`: `<?xml version="1.0"?>`

## pseudocode

```c
const char *__fastcall Utf8CharacterSource::XmlDecl(Utf8CharacterSource *this, unsigned int *a2)
{
  *a2 = 21;
  return "<?xml version=\"1.0\"?>";
}

```

## disassembly

```asm
0x100419190  mov     dword ptr [rdx], 15h
0x100419196  lea     rax, aXmlVersion10; "<?xml version=\"1.0\"?>"
0x10041919d  retn
```
