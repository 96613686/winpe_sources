# [thunk]:CXmlContentFilter::GetClassID`adjustor{8}' (_GUID *)

- ea: `0x180011a40`
- end: `0x180011a49`
- name: `?GetClassID@CXmlContentFilter@@W7EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011a30`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::GetClassID(__int64 a1, const wchar_t *a2)
{
  return CXmlContentFilter::SaveCompleted((CXmlContentFilter *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180011a40  sub     rcx, 8; this
0x180011a44  jmp     ?SaveCompleted@CXmlContentFilter@@UEAAJPEB_W@Z; CXmlContentFilter::SaveCompleted(wchar_t const *)
```
