# Microsoft::Diagnostics::HttpRequest::HttpRequest(std::shared_ptr<Microsoft::Diagnostics::HttpConnection>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,Microsoft::Diagnostics::HttpMethod,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::vector<gsl::byte,std::allocator<gsl::byte>> const &,ISequentialStream *,bool,std::shared_ptr<Microsoft::Diagnostics::CertPinCache> const &,std::shared_ptr<std::function<void (ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)>>,bool (*)(_CERT_CONTEXT const *))

- ea: `0x18006c1b4`
- end: `0x18006c61e`
- name: `??0HttpRequest@Diagnostics@Microsoft@@AEAA@V?$shared_ptr@VHttpConnection@Diagnostics@Microsoft@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@4@_NVHttpMethod@12@1AEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@4@PEAUISequentialStream@@2AEBV?$shared_ptr@VCertPinCache@Diagnostics@Microsoft@@@4@V?$shared_ptr@V?$function@$$A6AXKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@std@@@4@P6A_NPEBU_CERT_CONTEXT@@@Z@Z`
- size: `1130`
- prototype: `__int64 __fastcall(int, int, int, int, int Buffer, __int64, __int64, __int64, char, __int64, void *, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033814`
- `0x1800340f8`

## callees

- `0x180024ee0`
- `0x1800326cc`
- `0x1800340c0`
- `0x180034d94`
- `0x180035698`
- `0x18005828c`
- `0x18005c218`
- `0x18006c1b4`
- `0x18006c624`
- `0x18006c984`
- `0x18006cb84`
- `0x18006cc3c`
- `0x18006ccd0`
- `0x18006cf4c`
- `0x1800a0d08`
- `0x1800a1e24`
- `0x18012de64`
- `0x18012eb08`
- `0x18015f810`
- `0x180178864`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c5a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c5a5`
- `WINHTTP!WinHttpSetOption` at `0x18006c4a4`
- `WINHTTP!WinHttpSetOption` at `0x18006c4ed`
- `WINHTTP!WinHttpSetOption` at `0x18006c4a4`
- `WINHTTP!WinHttpSetOption` at `0x18006c4ed`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18006c45d`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18006c45d`
- `WINHTTP!WinHttpOpenRequest` at `0x18006c40b`
- `WINHTTP!WinHttpOpenRequest` at `0x18006c40b`

## string_xrefs

- `0x18006c5b9`: `onecore\base\telemetry\utc\include\ImpersonationScope.h`

## pseudocode

```c

```
