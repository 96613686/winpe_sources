# CSqlUcsSecurityMgr::LoadCertificateContext(ulong &,ulong,wchar_t *,ulong &,CSbCryptoContext &,CSbCertificate &,CSbPrivateKey &,CUcsErrorMessage &)

- ea: `0x100962c50`
- end: `0x100963c22`
- name: `?LoadCertificateContext@CSqlUcsSecurityMgr@@UEAA_NAEAKKPEA_W0AEAVCSbCryptoContext@@AEAVCSbCertificate@@AEAVCSbPrivateKey@@AEAVCUcsErrorMessage@@@Z`
- size: `4050`
- prototype: `bool __fastcall(CSqlUcsSecurityMgr *__hidden this, unsigned int *, unsigned int, wchar_t *, unsigned int *, struct CSbCryptoContext *, struct CSbCertificate *, struct CSbPrivateKey *, struct CUcsErrorMessage *Destination)`
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100403080`
- `0x1004076a0`
- `0x100430960`
- `0x100430d60`
- `0x100536250`
- `0x1006d99f0`
- `0x1008496f0`
- `0x100849900`
- `0x10085c5d0`
- `0x10085f800`
- `0x10085f8d0`
- `0x1008bc030`
- `0x10090dc80`
- `0x10090f7f0`
- `0x100962c50`
- `0x1009651e0`
- `0x101e899b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100962eea`
- `KERNEL32!GetLastError` at `0x1009636a5`
- `KERNEL32!GetLastError` at `0x100963866`
- `KERNEL32!GetLastError` at `0x10096397a`
- `KERNEL32!GetLastError` at `0x100962eea`
- `KERNEL32!GetLastError` at `0x1009636a5`
- `KERNEL32!GetLastError` at `0x100963866`
- `KERNEL32!GetLastError` at `0x10096397a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100962fa7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963073`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1009631b0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963325`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963920`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963a39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963ba7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100962fa7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963073`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1009631b0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963325`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963920`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963a39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100963ba7`
- `ole32!CoCreateGuid` at `0x1009630e8`
- `ole32!CoCreateGuid` at `0x1009630e8`
- `ole32!StringFromGUID2` at `0x100963226`
- `ole32!StringFromGUID2` at `0x100963226`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10096323b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10096323b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009637fe`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1009637fe`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100962f02`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10096310b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963280`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1009636bd`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10096387f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963992`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963b03`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100962f02`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10096310b`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963280`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1009636bd`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10096387f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963992`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x100963b03`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100963481`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100963481`
- `sqldk!SystemThread_TlsIndex` at `0x100962d0f`
- `sqldk!SystemThread_TlsIndex` at `0x100962dc7`
- `sqldk!SystemThread_TlsIndex` at `0x10096343c`
- `sqldk!SystemThread_TlsIndex` at `0x10096349a`
- `sqldk!SystemThread_TlsIndex` at `0x100963616`
- `sqldk!SystemThread_TlsIndex` at `0x1009637c6`
- `sqldk!SystemThread_TlsOffset` at `0x100962d18`
- `sqldk!SystemThread_TlsOffset` at `0x100962dd0`
- `sqldk!SystemThread_TlsOffset` at `0x100963445`
- `sqldk!SystemThread_TlsOffset` at `0x1009634a3`
- `sqldk!SystemThread_TlsOffset` at `0x10096361f`
- `sqldk!SystemThread_TlsOffset` at `0x1009637cf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100962d33`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100962deb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100963460`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009634be`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009637e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100962d33`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100962deb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100963460`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009634be`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1009637e8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100963645`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100963645`
- `sqldk!??_V@YAXPEAX@Z` at `0x100962e89`
- `sqldk!??_V@YAXPEAX@Z` at `0x100962fb3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096309c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009631bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963331`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096373d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963766`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096380a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096392c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963aac`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963bb3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100962e89`
- `sqldk!??_V@YAXPEAX@Z` at `0x100962fb3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096309c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1009631bc`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963331`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096373d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963766`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096380a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10096392c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963aac`
- `sqldk!??_V@YAXPEAX@Z` at `0x100963bb3`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x100962cdd`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x100962cdd`
- `sqlmin!?GetReplicatedMasterDbId@@YAGXZ` at `0x100963654`
- `sqlmin!?GetReplicatedMasterDbId@@YAGXZ` at `0x100963654`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100962ecd`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963754`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963849`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963bf7`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100962ecd`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963754`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963849`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x100963bf7`

## string_xrefs

- `0x10096312b`: `SSB_SSPI: OS Error: %X '%ls' calling CoCreateGuid\n`

## pseudocode

```c

```
