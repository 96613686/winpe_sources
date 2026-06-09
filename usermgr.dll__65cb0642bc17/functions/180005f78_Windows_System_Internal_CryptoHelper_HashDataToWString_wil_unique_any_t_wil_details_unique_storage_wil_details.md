# Windows::System::Internal::CryptoHelper::HashDataToWString<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,Windows::System::Internal::CryptoHelper::FixedSizeBuffer<char>>(Windows::System::Internal::CryptoHelper::HashAlgorithm,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong,Windows::System::Internal::CryptoHelper::FixedSizeBuffer<char> const &)

- ea: `0x180005f78`
- end: `0x1800060b2`
- name: `??$HashDataToWString@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$FixedSizeBuffer@D@CryptoHelper@Internal@System@Windows@@@CryptoHelper@Internal@System@Windows@@SAJW4HashAlgorithm@0123@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@KAEBV?$FixedSizeBuffer@D@0123@@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64, ULONG, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006700`

## callees

- `0x180005f78`
- `0x1800060b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006082`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006082`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000603d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000603d`
- `bcrypt!BCryptCreateHash` at `0x180005fca`
- `bcrypt!BCryptCreateHash` at `0x180005fca`
- `bcrypt!BCryptDestroyHash` at `0x1800060aa`
- `bcrypt!BCryptDestroyHash` at `0x1800060aa`
- `bcrypt!BCryptFinishHash` at `0x180006059`
- `bcrypt!BCryptFinishHash` at `0x180006059`
- `bcrypt!BCryptGetProperty` at `0x18000602c`
- `bcrypt!BCryptGetProperty` at `0x18000602c`
- `bcrypt!BCryptHashData` at `0x180005fe8`
- `bcrypt!BCryptHashData` at `0x180005fe8`

## pseudocode

```c

```
