# CXmlContentFilter::GetSizeMax(_ULARGE_INTEGER *)

- ea: `0x180011ae0`
- end: `0x180011ae6`
- name: `?GetSizeMax@CXmlContentFilter@@UEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::GetSizeMax(CXmlContentFilter *this, union _ULARGE_INTEGER *a2)
{
  return 2147500037LL;
}

```

## disassembly

```asm
0x180011ae0  mov     eax, 80004005h
0x180011ae5  retn
```
