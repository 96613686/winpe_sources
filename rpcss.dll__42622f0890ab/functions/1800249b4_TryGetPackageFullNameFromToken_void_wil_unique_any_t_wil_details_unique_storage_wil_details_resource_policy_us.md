# TryGetPackageFullNameFromToken(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800249b4`
- end: `0x180024bce`
- name: `?TryGetPackageFullNameFromToken@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?PrivMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `538`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024510`
- `0x1800247a8`
- `0x180024834`
- `0x18002f9ac`
- `0x180071294`
- `0x18009d270`

## callees

- `0x1800249b4`
- `0x18002ba28`
- `0x18008cd90`
- `0x1800b27e0`
- `0x1800b30d2`
- `0x1800b3128`
- `0x18010a084`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024bb8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024bb8`
- `ntdll!RtlQueryPackageIdentity` at `0x180024a24`
- `ntdll!RtlQueryPackageIdentity` at `0x180024a24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024af0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024af0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024afb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024a75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024a75`

## string_xrefs

- `0x180024b2e`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180024b91`: `onecore\com\combase\processtoken\processtoken.cxx`

## pseudocode

```c

```
