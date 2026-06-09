# FileMgr::GetNewFileFromManagementService(IMemObj *,wchar_t const *,wchar_t const *,ushort,ushort,ulong,bool,wchar_t (&)[261])

- ea: `0x1017f2160`
- end: `0x1017f30d5`
- name: `?GetNewFileFromManagementService@FileMgr@@SAXPEAVIMemObj@@PEB_W1GGK_NAEAY0BAF@_W@Z`
- size: `3957`
- prototype: `void __usercall(struct IMemObj *@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, unsigned __int16@<r9w>, unsigned __int16, unsigned int, bool, wchar_t (*)[261])`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1017ec870`
- `0x1017f9390`

## callees

- `0x100401010`
- `0x1005d36b0`
- `0x100626050`
- `0x100652e80`
- `0x100653030`
- `0x10078c410`
- `0x10078c4f0`
- `0x10078c7c0`
- `0x1017f2160`
- `0x1023aee60`

## import_xrefs

- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1017f21c4`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1017f2205`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1017f21c4`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x1017f2205`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f2242`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f22f9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f280b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f2242`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f22f9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1017f280b`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f24a3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f29f6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f2cde`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f2d5a`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f24a3`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f29f6`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f2cde`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1017f2d5a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2291`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f234d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2862`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2faa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2291`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f234d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2862`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1017f2faa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f25e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2791`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2ec1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2f31`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f3026`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f25e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2791`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2ec1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f2f31`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1017f3026`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f260e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2645`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f295c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2968`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f298f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2ecb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2ed5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2edf`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2eeb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2f3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2f46`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fcd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fe1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3030`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f304c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3056`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3060`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f306a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3078`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3082`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3090`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f309c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f30a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f260e`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2645`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f295c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2968`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f298f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2ecb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2ed5`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2edf`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2eeb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2f3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2f46`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fcd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fd7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fe1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f2fed`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3030`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f304c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3056`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3060`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f306a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3078`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3082`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f3090`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f309c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1017f30a8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b48`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b60`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b78`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b90`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2ba8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b48`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b60`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b78`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2b90`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1017f2ba8`
- `sqllang!?SendGlobalClusterInternalServerActionRequest@@YAKPEB_W00PEAKPEAPEAE1HPEAU_HTTP_TIMEOUTS@@@Z` at `0x1017f2495`
- `sqllang!?SendGlobalClusterInternalServerActionRequest@@YAKPEB_W00PEAKPEAPEAE1HPEAU_HTTP_TIMEOUTS@@@Z` at `0x1017f28ca`
- `sqllang!?SendGlobalClusterInternalServerActionRequest@@YAKPEB_W00PEAKPEAPEAE1HPEAU_HTTP_TIMEOUTS@@@Z` at `0x1017f2495`
- `sqllang!?SendGlobalClusterInternalServerActionRequest@@YAKPEB_W00PEAKPEAPEAE1HPEAU_HTTP_TIMEOUTS@@@Z` at `0x1017f28ca`

## string_xrefs

- `0x1017f2629`: `xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'`
- `0x1017f29b2`: `xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'`
- `0x1017f266e`: `GetNewFileFromManagementService: Unknown message from Management Service %s.`
- `0x1017f2bb9`: `GetNewFileFromManagementService: Unknown message from Management Service %s.`
- `0x1017f25a2`: `Could not send Add new file request to Management Service.`
- `0x1017f24bd`: `GetNewFileFromManagementService: Could not send Add new file request to Management Service`
- `0x1017f2653`: `GetNewFileFromManagementService: Request ID recieved From Management Service %s.`
- `0x1017f274c`: `Unknown message from ManagementService.`
- `0x1017f299f`: `GetNewFileFromManagementService: Response from Management Service %s.`
- `0x1017f28f7`: `GetNewFileFromManagementService: Error occurred at Management Service. Http error code: %d. Retrying.`
- `0x1017f2f00`: `GetNewFileFromManagementService: Error occurred at Management Service. Http error code: %d.`
- `0x1017f290e`: `GetNewFileFromManagementService: Management Service %s call for database %s failed. WinHttp error: %d.`
- `0x1017f2b18`: `Message from Management Service does have have State`
- `0x1017f2a11`: `GetNewFileFromManagementService: Message from Management Service does have have State.`
- `0x1017f2d75`: `GetNewFileFromManagementService: Failed returned by Management Service`
- `0x1017f2fb3`: `GetNewFileFromManagementService: Got New File From Management Service %s.`
- `0x1017f2f51`: `//DataFileOperationStatus/DataFileBlobUri`
- `0x1017f2cb8`: `Unknown message from Management Service`
- `0x1017f2cf9`: `GetNewFileFromManagementService: InProgress returned by Management Service`
- `0x1017f2e78`: `Management Service Operation Failed`
- `0x1017f235d`: `GetNewFileFromManagementService: Posting to Management Service with action: '%s', and payload: '%s'.`

## pseudocode

```c

```
