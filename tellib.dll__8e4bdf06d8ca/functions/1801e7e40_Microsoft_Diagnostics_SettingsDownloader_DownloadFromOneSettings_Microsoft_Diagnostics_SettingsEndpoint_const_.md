# Microsoft::Diagnostics::SettingsDownloader::DownloadFromOneSettings(Microsoft::Diagnostics::SettingsEndpoint const &,bool,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,AutoDeleteFile &,Microsoft::Diagnostics::WideStringStream &,OneSettingsDownloadSession *,std::optional<ulong>,void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,void *,std::shared_ptr<Microsoft::Diagnostics::HttpResponse> &,unsigned __int64 &,__int64 &)

- ea: `0x1801e7e40`
- end: `0x1801e8646`
- name: `?DownloadFromOneSettings@SettingsDownloader@Diagnostics@Microsoft@@CAJAEBVSettingsEndpoint@23@_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVAutoDeleteFile@@AEAVWideStringStream@23@PEAUOneSettingsDownloadSession@@V?$optional@K@6@PEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@7AEAV?$shared_ptr@UHttpResponse@Diagnostics@Microsoft@@@6@AEA_KAEA_J@Z`
- size: `2054`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801e970c`

## callees

- `0x180001d28`
- `0x180007c04`
- `0x18001d160`
- `0x180020fbc`
- `0x180027be0`
- `0x1800326cc`
- `0x180035698`
- `0x18004ab70`
- `0x18005d050`
- `0x18006c984`
- `0x18006cc00`
- `0x180080054`
- `0x180089c54`
- `0x18008bd1c`
- `0x18009c71c`
- `0x1800bc2e0`
- `0x1800d0d9c`
- `0x18012de40`
- `0x1801612b8`
- `0x1801e6f30`
- `0x1801e7044`
- `0x1801e7158`
- `0x1801e7260`
- `0x1801e7550`
- `0x1801e76ec`
- `0x1801e7ab8`
- `0x1801e7e40`
- `0x1801e8760`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e7ef6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e831e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e7ef6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801e831e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801e844b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801e844b`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x1801e83df`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x1801e83df`

## string_xrefs

- `0x1801e830d`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1801e8463`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`

## pseudocode

```c

```
