# CXmlContentFilter::SaveCompleted(wchar_t const *)

- ea: `0x180011a30`
- end: `0x180011a36`
- name: `?SaveCompleted@CXmlContentFilter@@UEAAJPEB_W@Z`
- size: `6`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a40`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::SaveCompleted(CXmlContentFilter *this, const wchar_t *a2)
{
  return 2147751697LL;
}

```

## disassembly

```asm
0x180011a30  mov     eax, 80041711h
0x180011a35  retn
```
