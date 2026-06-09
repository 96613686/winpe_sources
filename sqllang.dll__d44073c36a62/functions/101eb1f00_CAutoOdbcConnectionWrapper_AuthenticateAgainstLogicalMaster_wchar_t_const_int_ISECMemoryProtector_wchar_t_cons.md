# CAutoOdbcConnectionWrapper::AuthenticateAgainstLogicalMaster(wchar_t const *,int,ISECMemoryProtector *,wchar_t const *,int,wchar_t const *,int,wchar_t const *,wchar_t const *,int,bool,bool,bool,_GUID &,_GUID &,bool &,bool,CConnectionChecker &,uchar *,int *,bool &,int &,ELoginFailedState &,bool &,int &,int &,bool &,wchar_t *,CVNetAuditingLoginContainer *,bool,bool &,wchar_t const *,int,bool,bool,ESECExternalDataActionState)

- ea: `0x101eb1f00`
- end: `0x101eb4094`
- name: `?AuthenticateAgainstLogicalMaster@CAutoOdbcConnectionWrapper@@QEAAKPEB_WHPEAVISECMemoryProtector@@0H0H00H_N2_NAEAU_GUID@@4AEA_N2AEAVCConnectionChecker@@PEAEPEAH5AEAHAEAW4ELoginFailedState@@5995PEA_WPEAVCVNetAuditingLoginContainer@@250H33W4ESECExternalDataActionState@@@Z`
- size: `8596`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x101eb1a10`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x1004076a0`
- `0x10040bfa0`
- `0x100430d60`
- `0x100754290`
- `0x100860500`
- `0x100a51c00`
- `0x100a522c0`
- `0x1012b2c30`
- `0x1012b2e00`
- `0x1014b5380`
- `0x101e88ed0`
- `0x101ea90f0`
- `0x101eafb80`
- `0x101eafc40`
- `0x101eb1f00`
- `0x101ebee80`

## import_xrefs

- `ODBC32!__imp_SQLExecute` at `0x101eb3e01`
- `ODBC32!__imp_SQLExecute` at `0x101eb3e01`
- `ODBC32!__imp_SQLAllocHandle` at `0x101eb287d`
- `ODBC32!__imp_SQLAllocHandle` at `0x101eb287d`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2a33`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2ace`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2c57`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2cf2`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2d88`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2e23`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2e9c`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2f16`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2f83`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3040`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb30ca`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3149`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb31be`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3234`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb32a9`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb332f`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb33ac`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb342b`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb34a8`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3525`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb35b0`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb366f`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3700`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3791`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3822`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb38b3`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3944`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb39b6`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3a47`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3ad7`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3b50`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3c89`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3d10`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3dbf`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2a33`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2ace`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2c57`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2cf2`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2d88`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2e23`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2e9c`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2f16`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb2f83`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3040`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb30ca`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3149`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb31be`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3234`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb32a9`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb332f`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb33ac`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb342b`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb34a8`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3525`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb35b0`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb366f`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3700`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3791`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3822`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb38b3`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3944`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb39b6`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3a47`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3ad7`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3b50`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3c89`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3d10`
- `ODBC32!__imp_SQLBindParameter` at `0x101eb3dbf`
- `ODBC32!__imp_SQLPrepareW` at `0x101eb29a3`
- `ODBC32!__imp_SQLPrepareW` at `0x101eb29a3`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb240c`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb265c`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb26eb`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb405e`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb240c`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb265c`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb26eb`
- `sqldk!?ReleaseSemaphore@SOS_Semaphore@@QEAA?AW4SOS_RESULT@@JPEAJ@Z` at `0x101eb405e`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x101eb283f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x101eb217c`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x101eb217c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101eb3f99`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101eb3f99`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101eb27a7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101eb27a7`
- `sqldk!SystemThread_TlsIndex` at `0x101eb2762`
- `sqldk!SystemThread_TlsIndex` at `0x101eb27c0`
- `sqldk!SystemThread_TlsIndex` at `0x101eb3f61`
- `sqldk!SystemThread_TlsOffset` at `0x101eb276b`
- `sqldk!SystemThread_TlsOffset` at `0x101eb27c9`
- `sqldk!SystemThread_TlsOffset` at `0x101eb3f6a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb2786`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb27e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb3f83`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb2786`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb27e4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101eb3f83`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesFido@@SAPEBV1@XZ` at `0x101eb20c9`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesFido@@SAPEBV1@XZ` at `0x101eb20c9`
- `sqlmin!GetXdbServerGlobals` at `0x101eb20ab`
- `sqlmin!GetXdbServerGlobals` at `0x101eb20ba`
- `sqlmin!GetXdbServerGlobals` at `0x101eb20ab`
- `sqlmin!GetXdbServerGlobals` at `0x101eb20ba`

## string_xrefs

- `0x101eb25e9`: `Unexpected XOdbc Connection Open Failure occurred during sp_cloud_extensions_authenticate_login.`
- `0x101eb2935`: `{? = call sp_cloud_extensions_authenticate_login (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?,%ls ?%ls)}`
- `0x101eb2957`: `{? = call sp_cloud_extensions_authenticate_login (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?%ls%ls)}`

## pseudocode

```c

```
