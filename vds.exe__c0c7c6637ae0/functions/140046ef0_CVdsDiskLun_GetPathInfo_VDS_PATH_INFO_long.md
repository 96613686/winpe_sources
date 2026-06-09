# CVdsDiskLun::GetPathInfo(_VDS_PATH_INFO * *,long *)

- ea: `0x140046ef0`
- end: `0x140048f93`
- name: `?GetPathInfo@CVdsDiskLun@@UEAAJPEAPEAU_VDS_PATH_INFO@@PEAJ@Z`
- size: `8355`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this, struct _VDS_PATH_INFO **, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140012c48`
- `0x14001f220`
- `0x14002a08c`
- `0x14002e123`
- `0x14003d60c`
- `0x14003d638`
- `0x140046ef0`
- `0x140052e52`
- `0x140052e80`
- `0x140052f40`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140047645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140047f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140047645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140047f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047bbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400488c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140047bbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400488c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140048e2d`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140046fb4`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140046fc2`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140046fb4`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140046fc2`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400472e1`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400472ef`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140048ee9`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140048ef7`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400472e1`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400472ef`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140048ee9`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140048ef7`
- `vdsutil!VdsWmiConnectToNamespace` at `0x1400474e1`
- `vdsutil!VdsWmiConnectToNamespace` at `0x1400474e1`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x1400477a8`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x140047c33`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x1400477a8`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x140047c33`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x1400477d9`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x140048036`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14004806b`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x1400477d9`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x140048036`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x14004806b`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x1400478c7`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x1400478e4`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x140047901`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14004791e`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x1400478c7`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x1400478e4`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x140047901`
- `vdsutil!VdsWmiGetByteFromInstance` at `0x14004791e`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140047d00`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140047f4d`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140047d00`
- `vdsutil!VdsWmiGetUlongFromInstance` at `0x140047f4d`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14004789d`
- `vdsutil!VdsWmiGetObjectFromInstance` at `0x14004789d`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140047be9`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140048d24`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140048d31`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140047be9`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140048d24`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x140048d31`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140047578`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140047578`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x14004759f`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047834`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047a47`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047c6c`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x14004759f`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047834`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047a47`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140047c6c`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x140047ee5`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x140048876`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x140047ee5`
- `vdsutil!VdsIscsiCheckEqualIpAddress` at `0x140048876`
- `vdsutil!VdsIscsiCacheSessionDevices` at `0x1400476af`
- `vdsutil!VdsIscsiCacheSessionDevices` at `0x1400476af`
- `vdsutil!VdsWmiGetObjectInVariantObjectArray` at `0x140047ca8`
- `vdsutil!VdsWmiGetObjectInVariantObjectArray` at `0x140047ca8`
- `vdsutil!VdsIscsiGetIpAddressFromInstance` at `0x140047cde`
- `vdsutil!VdsIscsiGetIpAddressFromInstance` at `0x140047f2b`
- `vdsutil!VdsIscsiGetIpAddressFromInstance` at `0x140047cde`
- `vdsutil!VdsIscsiGetIpAddressFromInstance` at `0x140047f2b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140047142`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140047142`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140047237`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140048e3f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140047237`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140048e3f`
- `vdsutil!VdsTraceW` at `0x140047229`
- `vdsutil!VdsTraceW` at `0x1400474f9`
- `vdsutil!VdsTraceW` at `0x14004765e`
- `vdsutil!VdsTraceW` at `0x1400479a5`
- `vdsutil!VdsTraceW` at `0x140047abe`
- `vdsutil!VdsTraceW` at `0x14004808d`
- `vdsutil!VdsTraceW` at `0x1400480df`
- `vdsutil!VdsTraceW` at `0x14004815e`
- `vdsutil!VdsTraceW` at `0x140048201`
- `vdsutil!VdsTraceW` at `0x14004821b`
- `vdsutil!VdsTraceW` at `0x140048264`
- `vdsutil!VdsTraceW` at `0x140048284`
- `vdsutil!VdsTraceW` at `0x1400483d0`
- `vdsutil!VdsTraceW` at `0x14004895c`
- `vdsutil!VdsTraceW` at `0x140048975`
- `vdsutil!VdsTraceW` at `0x14004898e`
- `vdsutil!VdsTraceW` at `0x140048be5`
- `vdsutil!VdsTraceW` at `0x140048c22`
- `vdsutil!VdsTraceW` at `0x140047229`
- `vdsutil!VdsTraceW` at `0x1400474f9`
- `vdsutil!VdsTraceW` at `0x14004765e`
- `vdsutil!VdsTraceW` at `0x1400479a5`
- `vdsutil!VdsTraceW` at `0x140047abe`
- `vdsutil!VdsTraceW` at `0x14004808d`
- `vdsutil!VdsTraceW` at `0x1400480df`
- `vdsutil!VdsTraceW` at `0x14004815e`
- `vdsutil!VdsTraceW` at `0x140048201`
- `vdsutil!VdsTraceW` at `0x14004821b`
- `vdsutil!VdsTraceW` at `0x140048264`
- `vdsutil!VdsTraceW` at `0x140048284`
- `vdsutil!VdsTraceW` at `0x1400483d0`
- `vdsutil!VdsTraceW` at `0x14004895c`
- `vdsutil!VdsTraceW` at `0x140048975`
- `vdsutil!VdsTraceW` at `0x14004898e`
- `vdsutil!VdsTraceW` at `0x140048be5`
- `vdsutil!VdsTraceW` at `0x140048c22`
- `OLEAUT32!__imp_SysAllocString` at `0x140047362`
- `OLEAUT32!__imp_SysAllocString` at `0x140047379`
- `OLEAUT32!__imp_SysAllocString` at `0x14004738a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004739b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473df`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473f0`
- `OLEAUT32!__imp_SysAllocString` at `0x140047401`
- `OLEAUT32!__imp_SysAllocString` at `0x140047412`
- `OLEAUT32!__imp_SysAllocString` at `0x140047426`
- `OLEAUT32!__imp_SysAllocString` at `0x14004743a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004744e`
- `OLEAUT32!__imp_SysAllocString` at `0x140047462`
- `OLEAUT32!__imp_SysAllocString` at `0x140047476`
- `OLEAUT32!__imp_SysAllocString` at `0x14004748a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004749e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400474b2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400474c6`
- `OLEAUT32!__imp_SysAllocString` at `0x140047362`
- `OLEAUT32!__imp_SysAllocString` at `0x140047379`
- `OLEAUT32!__imp_SysAllocString` at `0x14004738a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004739b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473df`
- `OLEAUT32!__imp_SysAllocString` at `0x1400473f0`
- `OLEAUT32!__imp_SysAllocString` at `0x140047401`
- `OLEAUT32!__imp_SysAllocString` at `0x140047412`
- `OLEAUT32!__imp_SysAllocString` at `0x140047426`
- `OLEAUT32!__imp_SysAllocString` at `0x14004743a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004744e`
- `OLEAUT32!__imp_SysAllocString` at `0x140047462`
- `OLEAUT32!__imp_SysAllocString` at `0x140047476`
- `OLEAUT32!__imp_SysAllocString` at `0x14004748a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004749e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400474b2`
- `OLEAUT32!__imp_SysAllocString` at `0x1400474c6`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c45`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c59`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c63`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c77`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c81`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c8b`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c95`
- `OLEAUT32!__imp_SysFreeString` at `0x140048ca2`
- `OLEAUT32!__imp_SysFreeString` at `0x140048caf`
- `OLEAUT32!__imp_SysFreeString` at `0x140048cbc`
- `OLEAUT32!__imp_SysFreeString` at `0x140048cc9`
- `OLEAUT32!__imp_SysFreeString` at `0x140048cd6`
- `OLEAUT32!__imp_SysFreeString` at `0x140048ce3`
- `OLEAUT32!__imp_SysFreeString` at `0x140048cf0`
- `OLEAUT32!__imp_SysFreeString` at `0x140048cfd`
- `OLEAUT32!__imp_SysFreeString` at `0x140048d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x140048d17`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c45`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c59`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c63`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c77`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c81`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c8b`
- `OLEAUT32!__imp_SysFreeString` at `0x140048c95`
- `OLEAUT32!__imp_SysFreeString` at `0x140048ca2`
- `OLEAUT32!__imp_SysFreeString` at `0x140048caf`

## string_xrefs

- `0x14004741f`: `MSiSCSI_InitiatorSessionInfo`
- `0x1400473d8`: `ScsiPathId`
- `0x14004712f`: `CVdsDiskLun::GetPathInfo()`
- `0x14004827b`: `CVdsDiskLun::GetPathInfo: NULL input arguments`
- `0x140047220`: `CVdsDiskLun::GetPathInfo: Could not load iSCSI library.`
- `0x14004740b`: `PathIdentifier`
- `0x1400474ed`: `CVdsDiskLun::GetPathInfo: VdsWmiConnectToNamespace failed: %X`
- `0x14004823f`: `CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor NOT SUPPORTED: hr=%lX`
- `0x140048258`: `CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor failed, 1: %lX`
- `0x14004826f`: `CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor failed, 2: %lX`
- `0x14004755c`: `CVdsDiskLun::GetPathInfo: VdsWmiGetVariantStringFromInstance InstanceName failed: %X`
- `0x140048171`: `CVdsDiskLun::GetPathInfo: VdsWmiGetVariantStringFromInstance InstanceName failed: %X`
- `0x140047584`: `CVdsDiskLun::GetPathInfo: VdsWmiFindInstanceOfClass DSM_QueryUniqueId failed: %X`
- `0x1400475ab`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance DsmUniqueId failed: %X`
- `0x1400475d6`: `CVdsDiskLun::GetPathInfo: VdsWmiGetVariantObjectArrayFromInstance PdoInformation failed: %X`
- `0x1400475fe`: `CVdsDiskLun::GetPathInfo: SafeArrayGetLBound failed: %X`
- `0x140047626`: `CVdsDiskLun::GetPathInfo: SafeArrayGetUBound failed: %X`
- `0x140047655`: `CVdsDiskLun::GetPathInfo: pPaths Alloc: Out of memory.`
- `0x14004769b`: `CVdsDiskLun::GetPathInfo: VdsWmiCreateInstanceEnum MSiSCSI_InitiatorSessionInfo failed: %X`
- `0x1400476bb`: `CVdsDiskLun::GetPathInfo: VdsIscsiCacheSessionDevices failed: %X`
- `0x14004820f`: `CVdsDiskLun::GetPathInfo: m_pService->QueryInitiatorAdapters failed: %X`
- `0x14004770f`: `CVdsDiskLun::GetPathInfo: GetSubSystem failed: %X`
- `0x14004773b`: `CVdsDiskLun::GetPathInfo: spSubsystem->QueryInterface IID_IVdsSubSystemIscsi failed: %X`
- `0x140047761`: `CVdsDiskLun::GetPathInfo: spSubsystemIscsi->QueryPortals failed: %X`
- `0x14004778e`: `CVdsDiskLun::GetPathInfo: GetLoadBalancePolicy failed: %X`
- `0x1400477b4`: `CVdsDiskLun::GetPathInfo: vdsPdoInformationEnum.Attach failed: %X`
- `0x1400481f5`: `CVdsDiskLun::GetPathInfo: vdsPdoInformationEnum.Next failed: %X`
- `0x1400481ec`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance PathIdentifier failed: %X`
- `0x1400481e0`: `CVdsDiskLun::GetPathInfo: VdsWmiGetObjectFromInstance ScsiAddress failed: %X`
- `0x1400481d4`: `CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance PortNumber failed: %X`
- `0x1400481c8`: `CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance ScsiPathId failed: %X`
- `0x1400481bc`: `CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance TargetId failed: %X`
- `0x1400481b0`: `CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance Lun failed: %X`
- `0x14004799c`: `CVdsDiskLun::GetPathInfo: Could not find session cache entry corresponding to path.`
- `0x1400481a4`: `CVdsDiskLun::GetPathInfo: spInitiatorSessionInfoEnum->Reset failed: %X`
- `0x140048198`: `CVdsDiskLun::GetPathInfo: spInitiatorSessionInfoEnum->Next failed: %X`
- `0x140048180`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance UniqueAdapterId failed: %X`
- `0x140047ab2`: `CVdsDiskLun::GetPathInfo: spEnumInitAdap->Reset failed: %X`
- `0x140048947`: `CVdsDiskLun::GetPathInfo: spEnumInitAdap->Next failed: %X`
- `0x14004893b`: `CVdsDiskLun::GetPathInfo: spInitAdapUnk->QueryInterface failed: %X`
- `0x140048149`: `CVdsDiskLun::GetPathInfo: spInitAdap->GetProperties failed: %X`
- `0x140048155`: `CVdsDiskLun::GetPathInfo: Could not find initiator adapter endpoint for path.`
- `0x14004813a`: `CVdsDiskLun::GetPathInfo: VdsWmiGetVariantObjectArrayFromInstance SessionsList failed: %X`
- `0x140047c46`: `CVdsDiskLun::GetPathInfo: vdsSessionsListEnum.Attach failed: %X`
- `0x14004812b`: `CVdsDiskLun::GetPathInfo: vdsSessionsListEnum.Next failed: %X`
- `0x14004811f`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance UniqueSessionId failed: %X`
- `0x140048110`: `CVdsDiskLun::GetPathInfo: VdsWmiGetObjectInVariantObjectArray ConnectionsList[0] failed: %X`
- `0x140048101`: `CVdsDiskLun::GetPathInfo: VdsIscsiGetIpAddressFromInstance RemoteAddr failed: %X`
- `0x1400480f2`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlongFromInstance RemotePort failed: %X`
- `0x140047d2d`: `CVdsDiskLun::GetPathInfo: spEnumPortals->Reset failed: %X`
- `0x1400480ca`: `CVdsDiskLun::GetPathInfo: spPortalUnk->QueryInterface failed: %X`
- `0x1400480be`: `CVdsDiskLun::GetPathInfo: spPortal->GetProperties failed: %X`
- `0x1400480d6`: `CVdsDiskLun::GetPathInfo: Could not find target portal endpoint for path.`
- `0x1400480af`: `CVdsDiskLun::GetPathInfo: VdsIscsiGetIpAddressFromInstance LocalAddr failed: %X`
- `0x1400480a0`: `CVdsDiskLun::GetPathInfo: VdsWmiGetUlongFromInstance LocalPort failed: %X`
- `0x140048084`: `CVdsDiskLun::GetPathInfo: pPaths[lCurrentPdo].pInitiatorPortalIpAddr Alloc: Out of memory.`
- `0x140048189`: `CVdsDiskLun::GetPathInfo: Could not find session corresponding to cache entry.`
- `0x1400489c1`: `CVdsDiskLun::GetPathInfo: m_pLunMpio->GetPathInfo failed: %X`
- `0x1400488ec`: `CVdsDiskLun::GetPathInfo: m_pService->QueryHbaPorts failed: %X`
- `0x140048c19`: `CVdsDiskLun::GetPathInfo: m_pService->QueryHbaPorts failed: %X`
- `0x140048bdc`: `CVdsDiskLun::GetPathInfo: Invalid path FC\SAS HBA returned`
- `0x140048bc4`: `CVdsDiskLun::GetPathInfo: spEnumHbaPorts->Next failed: %X`
- `0x140048bb8`: `CVdsDiskLun::GetPathInfo: spHbaPortUnk->QueryInterface failed: %X`
- `0x140048bac`: `CVdsDiskLun::GetPathInfo: spHbaPort->GetProperties failed: %X`
- `0x140048bd0`: `CVdsDiskLun::GetPathInfo: spEnumHbaPorts->Reset failed: %X`
- `0x14004831a`: `CVdsDiskLun::GetPathInfo: spSubsystem->QueryInterface IID_IVdsSubSystemInterconnect failed: %X`
- `0x140048340`: `CVdsDiskLun::GetPathInfo: spSubsystemInterconnect->GetSupportedInterconnects failed: %X`
- `0x1400483c7`: `CVdsDiskLun::GetPathInfo: Invalid path returned`
- `0x14004896c`: `CVdsDiskLun::GetPathInfo: Invalid path returned`
- `0x140048953`: `CVdsDiskLun::GetPathInfo: Invalid path iSCSI returned`
- `0x14004892f`: `CVdsDiskLun::GetPathInfo: spInitAdap->QueryInitiatorPortals failed: %X`
- `0x140048923`: `CVdsDiskLun::GetPathInfo: spEnumInitPort->Next failed: %X`
- `0x140048917`: `CVdsDiskLun::GetPathInfo: spInitPortUnk->QueryInterface failed: %X`
- `0x14004890b`: `CVdsDiskLun::GetPathInfo: spInitPortal->GetProperties failed: %X`
- `0x140048985`: `CVdsDiskLun::GetPathInfo: Unsupported provider type`

## pseudocode

```c
// Hidden C++ exception states: #wind=53
__int64 __fastcall CVdsDiskLun::GetPathInfo(CVdsDiskLun *this, struct _VDS_PATH_INFO **a2, int *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  OLECHAR *v8; // rdi
  int v9; // eax
  int v10; // edi
  int Descriptor; // eax
  struct IWbemClassObject *v12; // rbx
  int VariantFromInstance; // eax
  int InstanceOfClass; // eax
  int UlonglongFromInstance; // eax
  int v16; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  void *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // r13d
  __int64 v28; // rsi
  int v29; // eax
  int v30; // ecx
  int ObjectFromInstance; // eax
  int ByteFromInstance; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r9
  _QWORD *v37; // r14
  __int64 v38; // r8
  __int64 v39; // rdx
  int v40; // eax
  wchar_t *v41; // rbx
  int v42; // r15d
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  size_t v48; // r8
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int ObjectInVariantObjectArray; // eax
  int IpAddressFromInstance; // eax
  int UlongFromInstance; // eax
  int v55; // eax
  __int64 v56; // rbx
  int v57; // eax
  _OWORD *v58; // rcx
  char *v59; // rax
  __int64 v60; // rdx
  _OWORD *v61; // rcx
  _OWORD *v62; // rax
  __int64 v63; // rdx
  int v64; // eax
  int v65; // eax
  void *v66; // rcx
  _OWORD *v67; // rcx
  _OWORD *v68; // rax
  __int64 v69; // rdx
  const wchar_t *v70; // rdx
  int v71; // eax
  int v72; // eax
  int v73; // eax
  char v74; // al
  int v75; // eax
  int k; // r14d
  __int64 v77; // rbx
  int v78; // ecx
  GUID *v79; // rax
  int v80; // eax
  int v81; // eax
  int m; // edx
  __int64 v83; // r8
  int v84; // eax
  int n; // r14d
  __int64 v86; // rsi
  int v87; // edx
  int v88; // eax
  int v89; // eax
  __int64 v90; // rbx
  int v91; // eax
  _OWORD *v92; // rcx
  char *v93; // rax
  __int64 v94; // rdx
  _OWORD *v95; // rax
  _OWORD *v96; // rcx
  __int64 v97; // rdx
  int v98; // eax
  int v99; // esi
  int i; // esi
  __int64 v101; // rbx
  GUID *v102; // rax
  int v103; // eax
  int j; // edx
  __int64 v105; // r8
  _QWORD *v106; // rax
  _QWORD *v107; // rbx
  void *v108; // rcx
  char *v109; // rcx
  int ii; // esi
  __int64 v111; // rbx
  LPVOID v113; // [rsp+30h] [rbp-D0h] BYREF
  int v114; // [rsp+38h] [rbp-C8h] BYREF
  int v115; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v116; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v117; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v118)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v119; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v120; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v121; // [rsp+68h] [rbp-98h] BYREF
  struct IWbemClassObject *v122; // [rsp+70h] [rbp-90h] BYREF
  __int64 v123; // [rsp+78h] [rbp-88h] BYREF
  __int64 v124; // [rsp+80h] [rbp-80h] BYREF
  struct IWbemClassObject *v125; // [rsp+88h] [rbp-78h] BYREF
  __int64 v126; // [rsp+90h] [rbp-70h] BYREF
  int v127; // [rsp+98h] [rbp-68h] BYREF
  struct IWbemClassObject *v128; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v130)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall ***v131)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v132)(_QWORD, GUID *, __int64 *); // [rsp+C0h] [rbp-40h] BYREF
  __int64 v133; // [rsp+C8h] [rbp-38h] BYREF
  struct IEnumWbemClassObject *v134; // [rsp+D0h] [rbp-30h] BYREF
  struct IWbemServices *v135; // [rsp+D8h] [rbp-28h] BYREF
  LONG plUbound; // [rsp+E0h] [rbp-20h] BYREF
  LONG plLbound; // [rsp+E4h] [rbp-1Ch] BYREF
  int v138; // [rsp+E8h] [rbp-18h] BYREF
  int v139; // [rsp+ECh] [rbp-14h] BYREF
  __int64 v140; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v141; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v142; // [rsp+100h] [rbp+0h] BYREF
  struct IWbemClassObject *v143; // [rsp+108h] [rbp+8h] BYREF
  BSTR v144; // [rsp+110h] [rbp+10h]
  LPVOID v145; // [rsp+118h] [rbp+18h] BYREF
  __int64 v146; // [rsp+120h] [rbp+20h] BYREF
  __int64 v147; // [rsp+128h] [rbp+28h] BYREF
  __int64 v148; // [rsp+130h] [rbp+30h] BYREF
  int v149; // [rsp+138h] [rbp+38h] BYREF
  BSTR v150; // [rsp+140h] [rbp+40h]
  BSTR v151; // [rsp+148h] [rbp+48h]
  BSTR v152; // [rsp+150h] [rbp+50h]
  BSTR v153; // [rsp+158h] [rbp+58h]
  BSTR v154; // [rsp+160h] [rbp+60h]
  BSTR v155; // [rsp+168h] [rbp+68h]
  BSTR v156; // [rsp+170h] [rbp+70h]
  BSTR v157; // [rsp+178h] [rbp+78h]
  BSTR v158; // [rsp+180h] [rbp+80h]
  BSTR v159; // [rsp+188h] [rbp+88h]
  BSTR v160; // [rsp+190h] [rbp+90h]
  BSTR v161; // [rsp+198h] [rbp+98h]
  BSTR v162; // [rsp+1A0h] [rbp+A0h]
  BSTR v163; // [rsp+1A8h] [rbp+A8h]
  BSTR v164; // [rsp+1B0h] [rbp+B0h]
  BSTR v165; // [rsp+1B8h] [rbp+B8h]
  BSTR v166; // [rsp+1C0h] [rbp+C0h]
  BSTR v167; // [rsp+1C8h] [rbp+C8h]
  VARIANTARG v168; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v169; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v170; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v171; // [rsp+1F8h] [rbp+F8h] BYREF
  BSTR bstrString; // [rsp+200h] [rbp+100h]
  __int64 v173; // [rsp+208h] [rbp+108h] BYREF
  VARIANTARG pvarg; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v175[24]; // [rsp+228h] [rbp+128h] BYREF
  VARIANTARG v176; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v177[24]; // [rsp+258h] [rbp+158h] BYREF
  struct _VDS_PATH_INFO **v178; // [rsp+270h] [rbp+170h]
  int *v179; // [rsp+278h] [rbp+178h]
  _BYTE v180[16]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v181[560]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v182[560]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int128 v183; // [rsp+6F0h] [rbp+5F0h] BYREF
  wchar_t *String1; // [rsp+700h] [rbp+600h]
  __int128 v185; // [rsp+708h] [rbp+608h] BYREF
  __int128 v186; // [rsp+718h] [rbp+618h]
  __int128 v187; // [rsp+728h] [rbp+628h]
  _DWORD v188[137]; // [rsp+740h] [rbp+640h] BYREF
  int v189[3]; // [rsp+964h] [rbp+864h] BYREF
  _BYTE v190[548]; // [rsp+970h] [rbp+870h] BYREF
  char v191[12]; // [rsp+B94h] [rbp+A94h] BYREF
  __int128 v192; // [rsp+BA0h] [rbp+AA0h] BYREF
  char v193; // [rsp+BB0h] [rbp+AB0h] BYREF
  _BYTE v194[16]; // [rsp+DE0h] [rbp+CE0h] BYREF
  char v195; // [rsp+DF0h] [rbp+CF0h] BYREF

  v179 = a3;
  v178 = a2;
  v114 = 0;
  v113 = 0;
  v115 = 0;
  v173 = 0;
  v135 = 0;
  v134 = 0;
  v143 = 0;
  v148 = 0;
  v122 = 0;
  v126 = 0;
  v128 = 0;
  v125 = 0;
  v124 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v176, 0, sizeof(v176));
  memset(&v168, 0, sizeof(v168));
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v177);
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v175);
  bstrString = 0;
  v144 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  v164 = 0;
  v165 = 0;
  v166 = 0;
  v167 = 0;
  v169 = 0;
  v139 = 0;
  plLbound = 0;
  plUbound = 0;
  v170 = 0;
  v171 = 0;
  pv = 0;
  v116 = 0;
  v133 = 0;
  v142 = 0;
  v121 = 0;
  v132 = 0;
  v131 = 0;
  v120 = 0;
  v141 = 0;
  v130 = 0;
  v147 = 0;
  v146 = 0;
  v140 = 0;
  v127 = 0;
  v149 = 0;
  v145 = 0;
  v138 = 0;
  v183 = 0;
  String1 = 0;
  memset_0(v194, 0, 0x23Cu);
  memset_0(v190, 0, 0x228u);
  memset_0(v188, 0, 0x228u);
  memset_0(&v192, 0, 0x23Cu);
  v119 = 0;
  v118 = 0;
  v123 = 0;
  v185 = 0;
  v186 = 0;
  v187 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v180, 0x5Eu, "CVdsDiskLun::GetPathInfo()");
  v183 = 0;
  String1 = 0;
  memset_0(v194, 0, 0x23Cu);
  v185 = 0;
  v186 = 0;
  v187 = 0;
  memset_0(v190, 0, 0x228u);
  memset_0(v188, 0, 0x228u);
  memset_0(&v192, 0, 0x23Cu);
  VariantInit(&pvarg);
  VariantInit(&v176);
  VariantInit(&v168);
  v117 = 8;
  v6 = *((_DWORD *)this + 60);
  if ( v6 != 3 )
  {
    if ( v6 == 2 || v6 == 4 )
    {
      v71 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, int *))(**((_QWORD **)this + 26) + 24LL))(
              *((_QWORD *)this + 26),
              &v113,
              &v115);
      v10 = v71;
      if ( v71 >= 0 )
      {
        v98 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 24LL))(
                *((_QWORD *)this + 13) + 8LL,
                &v119);
        v99 = v98;
        if ( v98 == -2147212288 )
          goto LABEL_10;
        if ( v98 >= 0 && v119 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v115 )
              goto LABEL_269;
            v101 = (__int64)i << 6;
            if ( ((*(_DWORD *)((char *)v113 + v101 + 16) - 2) & 0xFFFFFFFD) != 0 )
              break;
            v102 = *(GUID **)((char *)v113 + v101 + 56);
            if ( !v102 )
              break;
            *v102 = GUID_NULL;
            *(GUID *)((char *)v113 + v101 + 40) = GUID_NULL;
LABEL_250:
            v114 = 0;
            ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v118);
            v103 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v119 + 24LL))(
                     v119,
                     1,
                     &v118,
                     &v114);
            v10 = v103;
            if ( v103 != 1 )
            {
              if ( v103 < 0 || !v118 )
              {
LABEL_266:
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spEnumHbaPorts->Next failed: %X", (unsigned int)v10);
                goto LABEL_153;
              }
              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v123);
              v10 = (**v118)(v118, &IID_IVdsHbaPort, &v123);
              if ( v10 < 0 || !v123 )
              {
LABEL_265:
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spHbaPortUnk->QueryInterface failed: %X", (unsigned int)v10);
                goto LABEL_153;
              }
              v185 = 0;
              v186 = 0;
              v187 = 0;
              v81 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v123 + 24LL))(v123, &v185);
              v10 = v81;
              if ( v81 < 0 )
              {
LABEL_264:
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spHbaPort->GetProperties failed: %X", (unsigned int)v81);
                goto LABEL_273;
              }
              for ( j = 0; j < 8; ++j )
              {
                v105 = *(_QWORD *)((char *)v113 + v101 + 56);
                if ( *((_BYTE *)&v186 + j) != *(_BYTE *)(v105 + j + 16)
                  || *((_BYTE *)&v186 + j + 8) != *(_BYTE *)(v105 + j + 24) )
                {
                  goto LABEL_250;
                }
              }
              *(_OWORD *)*(_QWORD *)((char *)v113 + v101 + 56) = v185;
              *(_OWORD *)((char *)v113 + v101 + 40) = v185;
            }
            v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 40LL))(v119);
            v10 = v84;
            if ( v84 < 0 )
            {
LABEL_267:
              VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spEnumHbaPorts->Reset failed: %X", (unsigned int)v84);
              goto LABEL_273;
            }
          }
LABEL_268:
          VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Invalid path FC\\SAS HBA returned");
          v10 = -2147211006;
        }
        else
        {
          VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: m_pService->QueryHbaPorts failed: %X", (unsigned int)v98);
          if ( v99 >= 0 )
            v99 = -2147467259;
          v10 = v99;
        }
        goto LABEL_273;
      }
    }
    else
    {
      if ( v6 != 5 )
      {
        VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Unsupported provider type");
        v10 = -2147211927;
        goto LABEL_273;
      }
      v71 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, int *))(**((_QWORD **)this + 26) + 24LL))(
              *((_QWORD *)this + 26),
              &v113,
              &v115);
      v10 = v71;
      if ( v71 >= 0 )
      {
        v22 = (*(__int64 (__fastcall **)(char *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*((_QWORD *)this - 3) + 32LL))(
                (char *)this - 24,
                &v130);
        v10 = v22;
        if ( v22 < 0 )
          goto LABEL_32;
        v72 = (**v130)(v130, &IID_IVdsSubSystemInterconnect, &v146);
        v10 = v72;
        if ( v72 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetPathInfo: spSubsystem->QueryInterface IID_IVdsSubSystemInterconnect failed: %X",
            (unsigned int)v72);
          goto LABEL_273;
        }
        v73 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v146 + 24LL))(v146, &v127);
        v10 = v73;
        if ( v73 < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetPathInfo: spSubsystemInterconnect->GetSupportedInterconnects failed: %X",
            (unsigned int)v73);
          goto LABEL_273;
        }
        v74 = v127;
        if ( (v127 & 0xA) != 0 )
        {
          v75 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 24LL))(
                  *((_QWORD *)this + 13) + 8LL,
                  &v119);
          v10 = v75;
          if ( v75 == -2147212288 )
            goto LABEL_10;
          if ( v75 < 0 || !v119 )
          {
            VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: m_pService->QueryHbaPorts failed: %X", (unsigned int)v75);
            goto LABEL_153;
          }
          for ( k = 0; k < v115; ++k )
          {
            v77 = (__int64)k << 6;
            v78 = *(_DWORD *)((char *)v113 + v77 + 16);
            if ( ((v78 - 2) & 0xFFFFFFFD) != 0 )
            {
              if ( v78 != 3 )
              {
LABEL_178:
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Invalid path returned");
                v10 = -2147210981;
                goto LABEL_273;
              }
            }
            else
            {
              v79 = *(GUID **)((char *)v113 + v77 + 56);
              if ( !v79 )
                goto LABEL_268;
              *v79 = GUID_NULL;
              *(GUID *)((char *)v113 + v77 + 40) = GUID_NULL;
LABEL_181:
              v114 = 0;
              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v118);
              v80 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v119 + 24LL))(
                      v119,
                      1,
                      &v118,
                      &v114);
              v10 = v80;
              if ( v80 != 1 )
              {
                if ( v80 < 0 || !v118 )
                  goto LABEL_266;
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v123);
                v10 = (**v118)(v118, &IID_IVdsHbaPort, &v123);
                if ( v10 < 0 || !v123 )
                  goto LABEL_265;
                v185 = 0;
                v186 = 0;
                v187 = 0;
                v81 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v123 + 24LL))(v123, &v185);
                v10 = v81;
                if ( v81 < 0 )
                  goto LABEL_264;
                for ( m = 0; m < 8; ++m )
                {
                  v83 = *(_QWORD *)((char *)v113 + v77 + 56);
                  if ( *((_BYTE *)&v186 + m) != *(_BYTE *)(v83 + m + 16)
                    || *((_BYTE *)&v186 + m + 8) != *(_BYTE *)(v83 + m + 24) )
                  {
                    goto LABEL_181;
                  }
                }
                *(_OWORD *)*(_QWORD *)((char *)v113 + v77 + 56) = v185;
                *(_OWORD *)((char *)v113 + v77 + 40) = v185;
              }
            }
            v84 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v119 + 40LL))(v119);
            v10 = v84;
            if ( v84 < 0 )
              goto LABEL_267;
          }
          v74 = v127;
        }
        if ( (v74 & 4) == 0 )
          goto LABEL_269;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 32LL))(
                *((_QWORD *)this + 13) + 16LL,
                &v116);
        if ( v10 >= 0 && v116 )
        {
          for ( n = 0; ; ++n )
          {
LABEL_200:
            if ( n >= v115 )
              goto LABEL_269;
            v86 = (__int64)n << 6;
            v87 = *(_DWORD *)((char *)v113 + v86 + 16);
            if ( ((v87 - 2) & 0xFFFFFFFD) != 0 )
            {
              if ( v87 != 3 )
                goto LABEL_178;
              if ( !*(_QWORD *)((char *)v113 + v86 + 56) )
              {
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Invalid path iSCSI returned");
                v10 = -2147210980;
                goto LABEL_273;
              }
              *(GUID *)((char *)v113 + v86 + 40) = GUID_NULL;
              v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v116 + 40LL))(v116);
              if ( v10 < 0 || !v116 )
                goto LABEL_76;
              while ( 1 )
              {
                v114 = 0;
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v121);
                v88 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *))(*(_QWORD *)v116 + 24LL))(
                        v116,
                        1,
                        &v121,
                        &v114);
                v10 = v88;
                if ( v88 == 1 )
                  break;
                if ( v88 < 0 || !v121 )
                {
LABEL_236:
                  VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spEnumInitAdap->Next failed: %X", (unsigned int)v10);
                  goto LABEL_153;
                }
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v120);
                v10 = (**(__int64 (__fastcall ***)(wchar_t *, GUID *, __int64 *))v121)(
                        v121,
                        &IID_IVdsIscsiInitiatorAdapter,
                        &v120);
                if ( v10 < 0 || !v120 )
                {
LABEL_235:
                  VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spInitAdapUnk->QueryInterface failed: %X", (unsigned int)v10);
                  goto LABEL_153;
                }
                ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v133);
                v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v120 + 32LL))(v120, &v133);
                if ( v10 < 0 || !v133 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsDiskLun::GetPathInfo: spInitAdap->QueryInitiatorPortals failed: %X",
                    (unsigned int)v10);
                  goto LABEL_153;
                }
                while ( 1 )
                {
                  v114 = 0;
                  ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v132);
                  v89 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v133 + 24LL))(
                          v133,
                          1,
                          &v132,
                          &v114);
                  v10 = v89;
                  if ( v89 == 1 )
                    break;
                  if ( v89 < 0 || !v132 )
                  {
                    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spEnumInitPort->Next failed: %X", (unsigned int)v89);
                    goto LABEL_153;
                  }
                  ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v141);
                  v10 = (**v132)(v132, &IID_IVdsIscsiInitiatorPortal, &v141);
                  if ( v10 < 0 || (v90 = v141) == 0 )
                  {
                    VdsTraceW(
                      0,
                      L"CVdsDiskLun::GetPathInfo: spInitPortUnk->QueryInterface failed: %X",
                      (unsigned int)v10);
                    goto LABEL_153;
                  }
                  memset_0(v194, 0, 0x23Cu);
                  v91 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v90 + 24LL))(v90, v194);
                  v10 = v91;
                  if ( v91 < 0 )
                  {
                    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spInitPortal->GetProperties failed: %X", (unsigned int)v91);
                    goto LABEL_273;
                  }
                  v92 = v182;
                  v93 = &v195;
                  v94 = 4;
                  do
                  {
                    *v92 = *(_OWORD *)v93;
                    v92[1] = *((_OWORD *)v93 + 1);
                    v92[2] = *((_OWORD *)v93 + 2);
                    v92[3] = *((_OWORD *)v93 + 3);
                    v92[4] = *((_OWORD *)v93 + 4);
                    v92[5] = *((_OWORD *)v93 + 5);
                    v92[6] = *((_OWORD *)v93 + 6);
                    v92[7] = *((_OWORD *)v93 + 7);
                    v92 += 8;
                    v93 += 128;
                    --v94;
                  }
                  while ( v94 );
                  *v92 = *(_OWORD *)v93;
                  v92[1] = *((_OWORD *)v93 + 1);
                  *((_QWORD *)v92 + 4) = *((_QWORD *)v93 + 4);
                  v95 = *(_OWORD **)((char *)v113 + v86 + 56);
                  v96 = v181;
                  v97 = 4;
                  do
                  {
                    *v96 = *v95;
                    v96[1] = v95[1];
                    v96[2] = v95[2];
                    v96[3] = v95[3];
                    v96[4] = v95[4];
                    v96[5] = v95[5];
                    v96[6] = v95[6];
                    v96[7] = v95[7];
                    v96 += 8;
                    v95 += 8;
                    --v97;
                  }
                  while ( v97 );
                  *v96 = *v95;
                  v96[1] = v95[1];
                  *((_QWORD *)v96 + 4) = *((_QWORD *)v95 + 4);
                  if ( (unsigned int)VdsIscsiCheckEqualIpAddress(v181, v182) )
                  {
                    v183 = 0;
                    String1 = 0;
                    v47 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v120 + 24LL))(v120, &v183);
                    v10 = v47;
                    if ( v47 < 0 )
                    {
LABEL_137:
                      VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spInitAdap->GetProperties failed: %X", (unsigned int)v47);
                      goto LABEL_273;
                    }
                    if ( String1 )
                    {
                      CoTaskMemFree(String1);
                      String1 = 0;
                    }
                    *(_OWORD *)((char *)v113 + v86 + 40) = v183;
                    ++n;
                    goto LABEL_200;
                  }
                }
              }
            }
            if ( v10 < 0 )
              goto LABEL_269;
          }
        }
        goto LABEL_152;
      }
    }
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: m_pLunMpio->GetPathInfo failed: %X", (unsigned int)v71);
    goto LABEL_273;
  }
  if ( !a2 || !a3 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: NULL input arguments");
    v10 = -2147024809;
    goto LABEL_273;
  }
  *a3 = 0;
  *a2 = 0;
  if ( !CVdsService::m_hIscsidscModule )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Could not load iSCSI library.");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v180);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v118);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v140);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v146);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v147);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v130);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v141);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v120);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v131);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v132);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v121);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v142);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v133);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v116);
    CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v175);
    CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v177);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v124);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v125);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v128);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v126);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v122);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v148);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v143);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v134);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v135);
    v7 = -2147212288;
    goto LABEL_294;
  }
  v8 = SysAllocString(L"root\\wmi");
  bstrString = v8;
  v144 = SysAllocString(L"InstanceName");
  v150 = SysAllocString(L"DSM_QueryUniqueId");
  v151 = SysAllocString(L"DsmUniqueId");
  v152 = SysAllocString(L"PdoInformation");
  v153 = SysAllocString(L"ScsiAddress");
  v154 = SysAllocString(L"PortNumber");
  v155 = SysAllocString(L"ScsiPathId");
  v156 = SysAllocString(L"TargetId");
  v157 = SysAllocString(L"Lun");
  v158 = SysAllocString(L"PathIdentifier");
  v159 = SysAllocString(L"MSiSCSI_InitiatorSessionInfo");
  v160 = SysAllocString(L"UniqueAdapterId");
  v161 = SysAllocString(L"SessionsList");
  v162 = SysAllocString(L"UniqueSessionId");
  v163 = SysAllocString(L"ConnectionsList");
  v164 = SysAllocString(L"RemoteAddr");
  v165 = SysAllocString(L"RemotePort");
  v166 = SysAllocString(L"LocalAddr");
  v167 = SysAllocString(L"LocalPort");
  v9 = VdsWmiConnectToNamespace(v8, &v173, &v135);
  v10 = v9;
  if ( v9 < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: VdsWmiConnectToNamespace failed: %X", (unsigned int)v9);
    goto LABEL_273;
  }
  Descriptor = CVdsDiskLun::FindMpioGetDescriptor((CVdsDiskLun *)((char *)this - 112), v135, &v143);
  v10 = Descriptor;
  if ( Descriptor < 0 )
  {
    if ( Descriptor == -2147212288 )
    {
      VdsTraceW(2, L"CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor NOT SUPPORTED: hr=%lX", 2147755008LL);
    }
    else if ( Descriptor == -2147212277 )
    {
      VdsTraceW(1, L"CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor failed, 1: %lX", 2147755019LL);
    }
    else
    {
      VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: FindMpioGetDescriptor failed, 2: %lX", (unsigned int)Descriptor);
    }
    goto LABEL_273;
  }
  v12 = v143;
  if ( !v143 )
    goto LABEL_10;
  VariantClear(&v168);
  VariantFromInstance = VdsWmiGetVariantFromInstance(v12, v144, 8u, &v168);
  v10 = VariantFromInstance;
  if ( VariantFromInstance < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: VdsWmiGetVariantStringFromInstance InstanceName failed: %X",
      (unsigned int)VariantFromInstance);
    goto LABEL_273;
  }
  InstanceOfClass = VdsWmiFindInstanceOfClass(v135, v150, v168.llVal, &v148);
  v10 = InstanceOfClass;
  if ( InstanceOfClass < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: VdsWmiFindInstanceOfClass DSM_QueryUniqueId failed: %X",
      (unsigned int)InstanceOfClass);
    goto LABEL_273;
  }
  UlonglongFromInstance = VdsWmiGetUlonglongFromInstance(v148, v151, &v169);
  v10 = UlonglongFromInstance;
  if ( UlonglongFromInstance < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance DsmUniqueId failed: %X",
      (unsigned int)UlonglongFromInstance);
    goto LABEL_273;
  }
  v16 = VdsWmiGetVariantFromInstance(v12, v152, 0x200Du, &pvarg);
  v10 = v16;
  if ( v16 < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: VdsWmiGetVariantObjectArrayFromInstance PdoInformation failed: %X",
      (unsigned int)v16);
    goto LABEL_273;
  }
  LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
  v10 = LBound;
  if ( LBound < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: SafeArrayGetLBound failed: %X", (unsigned int)LBound);
    goto LABEL_273;
  }
  UBound = SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
  v10 = UBound;
  if ( UBound < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: SafeArrayGetUBound failed: %X", (unsigned int)UBound);
    goto LABEL_273;
  }
  v115 = plUbound - plLbound + 1;
  v19 = CoTaskMemAlloc((__int64)v115 << 6);
  v113 = v19;
  if ( !v19 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: pPaths Alloc: Out of memory.");
    v10 = -2147024882;
    goto LABEL_273;
  }
  memset_0(v19, 0, (__int64)v115 << 6);
  v20 = VdsWmiCreateInstanceEnum(v135, v159, &v134);
  v10 = v20;
  if ( v20 < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: VdsWmiCreateInstanceEnum MSiSCSI_InitiatorSessionInfo failed: %X",
      (unsigned int)v20);
    goto LABEL_273;
  }
  v21 = VdsIscsiCacheSessionDevices(v134, &pv);
  v10 = v21;
  if ( v21 < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: VdsIscsiCacheSessionDevices failed: %X", (unsigned int)v21);
    goto LABEL_273;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 32LL))(
          *((_QWORD *)this + 13) + 16LL,
          &v116);
  if ( v10 < 0 || !v116 )
  {
LABEL_152:
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: m_pService->QueryInitiatorAdapters failed: %X", (unsigned int)v10);
    goto LABEL_153;
  }
  v22 = (*(__int64 (__fastcall **)(char *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*((_QWORD *)this - 3)
                                                                                                + 32LL))(
          (char *)this - 24,
          &v130);
  v10 = v22;
  if ( v22 < 0 )
  {
LABEL_32:
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: GetSubSystem failed: %X", (unsigned int)v22);
    goto LABEL_273;
  }
  v23 = (**v130)(v130, &IID_IVdsSubSystemIscsi, &v147);
  v10 = v23;
  if ( v23 < 0 )
  {
    VdsTraceW(
      0,
      L"CVdsDiskLun::GetPathInfo: spSubsystem->QueryInterface IID_IVdsSubSystemIscsi failed: %X",
      (unsigned int)v23);
    goto LABEL_273;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v147 + 32LL))(v147, &v142);
  v10 = v24;
  if ( v24 < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spSubsystemIscsi->QueryPortals failed: %X", (unsigned int)v24);
    goto LABEL_273;
  }
  v25 = (*(__int64 (__fastcall **)(CVdsDiskLun *, int *, LPVOID *, int *))(*(_QWORD *)this + 32LL))(
          this,
          &v149,
          &v145,
          &v138);
  v10 = v25;
  if ( v25 < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: GetLoadBalancePolicy failed: %X", (unsigned int)v25);
    goto LABEL_273;
  }
  v26 = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v177, &pvarg);
  v10 = v26;
  if ( v26 < 0 )
  {
    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: vdsPdoInformationEnum.Attach failed: %X", (unsigned int)v26);
    goto LABEL_273;
  }
  v27 = 0;
  ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v122);
  v10 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v177, &v122);
  if ( v10 == 1 )
    goto LABEL_269;
LABEL_42:
  if ( v10 < 0 )
  {
    v70 = L"CVdsDiskLun::GetPathInfo: vdsPdoInformationEnum.Next failed: %X";
LABEL_151:
    VdsTraceW(0, v70, (unsigned int)v10);
  }
  else
  {
    if ( v27 >= v115 )
      goto LABEL_269;
    v28 = (__int64)v27 << 6;
    *(_QWORD *)((char *)v113 + v28) = v169;
    v29 = VdsWmiGetUlonglongFromInstance(v122, v158, (char *)v113 + v28 + 8);
    v10 = v29;
    if ( v29 < 0 )
    {
      VdsTraceW(
        0,
        L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance PathIdentifier failed: %X",
        (unsigned int)v29);
    }
    else
    {
      *(_DWORD *)((char *)v113 + v28 + 16) = 3;
      if ( v138 <= 0 )
      {
LABEL_49:
        *(_DWORD *)((char *)v113 + v28 + 20) = 0;
      }
      else
      {
        v30 = 0;
        while ( *((_QWORD *)v145 + 3 * v30 + 1) != *(_QWORD *)((char *)v113 + v28 + 8) )
        {
          if ( ++v30 >= v138 )
            goto LABEL_49;
        }
        *(_DWORD *)((char *)v113 + v28 + 20) = *((_DWORD *)v145 + 6 * v30 + 4) != 0 ? 1 : 7;
      }
      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v126);
      ObjectFromInstance = VdsWmiGetObjectFromInstance(v122, v153, &v126);
      v10 = ObjectFromInstance;
      if ( ObjectFromInstance < 0 )
      {
        VdsTraceW(
          0,
          L"CVdsDiskLun::GetPathInfo: VdsWmiGetObjectFromInstance ScsiAddress failed: %X",
          (unsigned int)ObjectFromInstance);
      }
      else
      {
        v117 = 8;
        ByteFromInstance = VdsWmiGetByteFromInstance(v126, v154, (char *)&v117 + 4);
        v10 = ByteFromInstance;
        if ( ByteFromInstance < 0 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance PortNumber failed: %X",
            (unsigned int)ByteFromInstance);
        }
        else
        {
          v33 = VdsWmiGetByteFromInstance(v126, v155, (char *)&v117 + 5);
          v10 = v33;
          if ( v33 < 0 )
          {
            VdsTraceW(
              0,
              L"CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance ScsiPathId failed: %X",
              (unsigned int)v33);
          }
          else
          {
            v34 = VdsWmiGetByteFromInstance(v126, v156, (char *)&v117 + 6);
            v10 = v34;
            if ( v34 < 0 )
            {
              VdsTraceW(
                0,
                L"CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance TargetId failed: %X",
                (unsigned int)v34);
            }
            else
            {
              v35 = VdsWmiGetByteFromInstance(v126, v157, (char *)&v117 + 7);
              v10 = v35;
              if ( v35 < 0 )
              {
                VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: VdsWmiGetByteFromInstance Lun failed: %X", (unsigned int)v35);
              }
              else
              {
                v37 = pv;
                if ( !pv )
                {
LABEL_63:
                  VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Could not find session cache entry corresponding to path.");
                  goto LABEL_64;
                }
                LOBYTE(v36) = HIBYTE(v117);
                while ( !*((_DWORD *)v37 + 4) )
                {
LABEL_62:
                  v37 = (_QWORD *)v37[4];
                  if ( !v37 )
                    goto LABEL_63;
                }
                v38 = 0;
                v39 = v37[3];
                while ( *(_DWORD *)(2040LL * (unsigned int)v38 + v39 + 964) != HIDWORD(v117) )
                {
                  v38 = (unsigned int)(v38 + 1);
                  if ( (unsigned int)v38 >= *((_DWORD *)v37 + 4) )
                    goto LABEL_62;
                }
                v40 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, __int64))v134->lpVtbl->Reset)(
                        v134,
                        v39,
                        v38,
                        v36);
                v10 = v40;
                v41 = 0;
                if ( v40 < 0 )
                {
                  VdsTraceW(
                    0,
                    L"CVdsDiskLun::GetPathInfo: spInitiatorSessionInfoEnum->Reset failed: %X",
                    (unsigned int)v40);
                }
                else
                {
                  v42 = 0;
                  do
                  {
LABEL_68:
                    ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v128);
                    v43 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, struct IWbemClassObject **, int *))v134->lpVtbl->Next)(
                            v134,
                            0xFFFFFFFFLL,
                            1,
                            &v128,
                            &v139);
                    v10 = v43;
                    if ( v43 < 0 )
                    {
                      VdsTraceW(
                        0,
                        L"CVdsDiskLun::GetPathInfo: spInitiatorSessionInfoEnum->Next failed: %X",
                        (unsigned int)v43);
                      goto LABEL_273;
                    }
                    if ( v43 || v139 != 1 )
                    {
                      if ( v42 )
                      {
                        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v122);
                        v10 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v177, &v122);
                        if ( v10 != 1 )
                        {
                          ++v27;
                          goto LABEL_42;
                        }
LABEL_269:
                        *v178 = (struct _VDS_PATH_INFO *)v113;
                        *v179 = v115;
LABEL_10:
                        v10 = 0;
                        goto LABEL_273;
                      }
                      VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Could not find session corresponding to cache entry.");
LABEL_64:
                      v10 = -2147211510;
                      goto LABEL_273;
                    }
                    v44 = VdsWmiGetUlonglongFromInstance(v128, v160, &v170);
                    v10 = v44;
                    if ( v44 < 0 )
                    {
                      VdsTraceW(
                        0,
                        L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance UniqueAdapterId failed: %X",
                        (unsigned int)v44);
                      goto LABEL_273;
                    }
                  }
                  while ( v170 != *v37 );
                  VariantClear(&v168);
                  v45 = VdsWmiGetVariantFromInstance(v128, v144, 8u, &v168);
                  v10 = v45;
                  if ( v45 < 0 )
                  {
                    VdsTraceW(
                      0,
                      L"CVdsDiskLun::GetPathInfo: VdsWmiGetVariantStringFromInstance InstanceName failed: %X",
                      (unsigned int)v45);
                    goto LABEL_273;
                  }
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v116 + 40LL))(v116);
                  if ( v10 >= 0 && v116 )
                  {
                    while ( 1 )
                    {
                      v114 = (int)v41;
                      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v121);
                      v46 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *))(*(_QWORD *)v116 + 24LL))(
                              v116,
                              1,
                              &v121,
                              &v114);
                      v10 = v46;
                      if ( v46 == 1 )
                      {
                        VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: Could not find initiator adapter endpoint for path.");
                        v10 = -2147211008;
                        goto LABEL_273;
                      }
                      if ( v46 < 0 || v121 == v41 )
                        goto LABEL_236;
                      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v120);
                      v10 = (**(__int64 (__fastcall ***)(wchar_t *, GUID *, __int64 *))v121)(
                              v121,
                              &IID_IVdsIscsiInitiatorAdapter,
                              &v120);
                      if ( v10 < 0 || !v120 )
                        goto LABEL_235;
                      v183 = 0;
                      String1 = 0;
                      v47 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v120 + 24LL))(v120, &v183);
                      v10 = v47;
                      if ( v47 < 0 )
                        goto LABEL_137;
                      v41 = String1;
                      v48 = -1;
                      do
                        ++v48;
                      while ( String1[v48] );
                      if ( !wcsncmp_0(String1, v168.bstrVal, v48) )
                        break;
                      if ( v41 )
                      {
                        CoTaskMemFree(v41);
                        v41 = 0;
                        String1 = 0;
                      }
                    }
                    *(_OWORD *)((char *)v113 + v28 + 40) = v183;
                    CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v175);
                    VariantClear(&v176);
                    v49 = VdsWmiGetVariantFromInstance(v128, v161, 0x200Du, &v176);
                    v10 = v49;
                    v41 = 0;
                    if ( v49 < 0 )
                    {
                      VdsTraceW(
                        0,
                        L"CVdsDiskLun::GetPathInfo: VdsWmiGetVariantObjectArrayFromInstance SessionsList failed: %X",
                        (unsigned int)v49);
                    }
                    else
                    {
                      v50 = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v175, &v176);
                      v10 = v50;
                      if ( v50 < 0 )
                      {
                        VdsTraceW(
                          0,
                          L"CVdsDiskLun::GetPathInfo: vdsSessionsListEnum.Attach failed: %X",
                          (unsigned int)v50);
                        goto LABEL_273;
                      }
                      do
                      {
LABEL_120:
                        ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v125);
                        v10 = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v175, &v125);
                        if ( v10 == 1 )
                          goto LABEL_68;
                        if ( v10 < 0 )
                        {
                          v70 = L"CVdsDiskLun::GetPathInfo: vdsSessionsListEnum.Next failed: %X";
                          goto LABEL_151;
                        }
                        v51 = VdsWmiGetUlonglongFromInstance(v125, v162, &v171);
                        v10 = v51;
                        if ( v51 < 0 )
                        {
                          VdsTraceW(
                            0,
                            L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlonglongFromInstance UniqueSessionId failed: %X",
                            (unsigned int)v51);
                          goto LABEL_273;
                        }
                      }
                      while ( v171 != v37[1] );
                      ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v124);
                      ObjectInVariantObjectArray = VdsWmiGetObjectInVariantObjectArray(v125, v163, 0, &v124);
                      v10 = ObjectInVariantObjectArray;
                      if ( ObjectInVariantObjectArray < 0 )
                      {
                        VdsTraceW(
                          0,
                          L"CVdsDiskLun::GetPathInfo: VdsWmiGetObjectInVariantObjectArray ConnectionsList[0] failed: %X",
                          (unsigned int)ObjectInVariantObjectArray);
                      }
                      else
                      {
                        memset_0(v190, 0, 0x228u);
                        IpAddressFromInstance = VdsIscsiGetIpAddressFromInstance(v124, v164, v190);
                        v10 = IpAddressFromInstance;
                        if ( IpAddressFromInstance < 0 )
                        {
                          VdsTraceW(
                            0,
                            L"CVdsDiskLun::GetPathInfo: VdsIscsiGetIpAddressFromInstance RemoteAddr failed: %X",
                            (unsigned int)IpAddressFromInstance);
                        }
                        else
                        {
                          UlongFromInstance = VdsWmiGetUlongFromInstance(v124, v165, v191);
                          v10 = UlongFromInstance;
                          if ( UlongFromInstance < 0 )
                          {
                            VdsTraceW(
                              0,
                              L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlongFromInstance RemotePort failed: %X",
                              (unsigned int)UlongFromInstance);
                          }
                          else
                          {
                            v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v142 + 40LL))(v142);
                            if ( v10 < 0 || !v116 )
                            {
                              VdsTraceW(
                                0,
                                L"CVdsDiskLun::GetPathInfo: spEnumPortals->Reset failed: %X",
                                (unsigned int)v10);
                              goto LABEL_153;
                            }
                            do
                            {
                              v114 = 0;
                              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v131);
                              v55 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v142 + 24LL))(
                                      v142,
                                      1,
                                      &v131,
                                      &v114);
                              v10 = v55;
                              if ( v55 == 1 )
                              {
                                VdsTraceW(
                                  0,
                                  L"CVdsDiskLun::GetPathInfo: Could not find target portal endpoint for path.");
                                v10 = -2147211007;
                                goto LABEL_273;
                              }
                              if ( v55 < 0 || !v131 )
                                goto LABEL_236;
                              ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v140);
                              v10 = (**v131)(v131, &IID_IVdsIscsiPortal, &v140);
                              if ( v10 < 0 || (v56 = v140) == 0 )
                              {
                                VdsTraceW(
                                  0,
                                  L"CVdsDiskLun::GetPathInfo: spPortalUnk->QueryInterface failed: %X",
                                  (unsigned int)v10);
                                goto LABEL_153;
                              }
                              memset_0(&v192, 0, 0x23Cu);
                              v57 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v56 + 24LL))(v56, &v192);
                              v10 = v57;
                              if ( v57 < 0 )
                              {
                                VdsTraceW(
                                  0,
                                  L"CVdsDiskLun::GetPathInfo: spPortal->GetProperties failed: %X",
                                  (unsigned int)v57);
                                goto LABEL_273;
                              }
                              v58 = v181;
                              v59 = &v193;
                              v60 = 4;
                              do
                              {
                                *v58 = *(_OWORD *)v59;
                                v58[1] = *((_OWORD *)v59 + 1);
                                v58[2] = *((_OWORD *)v59 + 2);
                                v58[3] = *((_OWORD *)v59 + 3);
                                v58[4] = *((_OWORD *)v59 + 4);
                                v58[5] = *((_OWORD *)v59 + 5);
                                v58[6] = *((_OWORD *)v59 + 6);
                                v58[7] = *((_OWORD *)v59 + 7);
                                v58 += 8;
                                v59 += 128;
                                --v60;
                              }
                              while ( v60 );
                              *v58 = *(_OWORD *)v59;
                              v58[1] = *((_OWORD *)v59 + 1);
                              *((_QWORD *)v58 + 4) = *((_QWORD *)v59 + 4);
                              v61 = v182;
                              v62 = v190;
                              v63 = 4;
                              do
                              {
                                *v61 = *v62;
                                v61[1] = v62[1];
                                v61[2] = v62[2];
                                v61[3] = v62[3];
                                v61[4] = v62[4];
                                v61[5] = v62[5];
                                v61[6] = v62[6];
                                v61[7] = v62[7];
                                v61 += 8;
                                v62 += 8;
                                --v63;
                              }
                              while ( v63 );
                              *v61 = *v62;
                              v61[1] = v62[1];
                              *((_QWORD *)v61 + 4) = *((_QWORD *)v62 + 4);
                            }
                            while ( !(unsigned int)VdsIscsiCheckEqualIpAddress(v182, v181) );
                            *(_OWORD *)((char *)v113 + v28 + 24) = v192;
                            memset_0(v188, 0, 0x228u);
                            v64 = VdsIscsiGetIpAddressFromInstance(v124, v166, v188);
                            v10 = v64;
                            if ( v64 < 0 )
                            {
                              VdsTraceW(
                                0,
                                L"CVdsDiskLun::GetPathInfo: VdsIscsiGetIpAddressFromInstance LocalAddr failed: %X",
                                (unsigned int)v64);
                            }
                            else
                            {
                              v65 = VdsWmiGetUlongFromInstance(v124, v167, v189);
                              v10 = v65;
                              if ( v65 >= 0 )
                              {
                                v42 = 1;
                                if ( v189[0] || v188[0] != 3 )
                                {
                                  *(_QWORD *)((char *)v113 + v28 + 56) = CoTaskMemAlloc(0x228u);
                                  v66 = *(void **)((char *)v113 + v28 + 56);
                                  if ( !v66 )
                                  {
                                    VdsTraceW(
                                      0,
                                      L"CVdsDiskLun::GetPathInfo: pPaths[lCurrentPdo].pInitiatorPortalIpAddr Alloc: Out of memory.");
                                    v10 = -2147024882;
                                    goto LABEL_273;
                                  }
                                  memset_0(v66, 0, 0x228u);
                                  v67 = *(_OWORD **)((char *)v113 + v28 + 56);
                                  v68 = v188;
                                  v69 = 4;
                                  do
                                  {
                                    *v67 = *v68;
                                    v67[1] = v68[1];
                                    v67[2] = v68[2];
                                    v67[3] = v68[3];
                                    v67[4] = v68[4];
                                    v67[5] = v68[5];
                                    v67[6] = v68[6];
                                    v67[7] = v68[7];
                                    v67 += 8;
                                    v68 += 8;
                                    --v69;
                                  }
                                  while ( v69 );
                                  *v67 = *v68;
                                  v67[1] = v68[1];
                                  *((_QWORD *)v67 + 4) = *((_QWORD *)v68 + 4);
                                }
                                v41 = 0;
                                goto LABEL_120;
                              }
                              VdsTraceW(
                                0,
                                L"CVdsDiskLun::GetPathInfo: VdsWmiGetUlongFromInstance LocalPort failed: %X",
                                (unsigned int)v65);
                            }
                          }
                        }
                      }
                    }
                  }
                  else
                  {
LABEL_76:
                    VdsTraceW(0, L"CVdsDiskLun::GetPathInfo: spEnumInitAdap->Reset failed: %X", (unsigned int)v10);
LABEL_153:
                    if ( v10 >= 0 )
                      v10 = -2147467259;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_273:
  SysFreeString(bstrString);
  SysFreeString(v144);
  SysFreeString(v150);
  SysFreeString(v151);
  SysFreeString(v152);
  SysFreeString(v153);
  SysFreeString(v154);
  SysFreeString(v155);
  SysFreeString(v156);
  SysFreeString(v157);
  SysFreeString(v158);
  SysFreeString(v159);
  SysFreeString(v160);
  SysFreeString(v161);
  SysFreeString(v162);
  SysFreeString(v163);
  SysFreeString(v164);
  SysFreeString(v165);
  SysFreeString(v166);
  SysFreeString(v167);
  CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v177);
  CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v175);
  VariantClear(&pvarg);
  VariantClear(&v176);
  VariantClear(&v168);
  v106 = pv;
  if ( pv )
  {
    do
    {
      v107 = (_QWORD *)v106[4];
      v108 = (void *)v106[3];
      if ( v108 )
      {
        CoTaskMemFree(v108);
        *((_QWORD *)pv + 3) = 0;
        v106 = pv;
      }
      if ( v106 )
        CoTaskMemFree(v106);
      v106 = v107;
      pv = v107;
    }
    while ( v107 );
  }
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  if ( v145 )
  {
    CoTaskMemFree(v145);
    v145 = 0;
  }
  if ( v10 < 0 )
  {
    v109 = (char *)v113;
    if ( v113 )
    {
      for ( ii = 0; ii < v115; ++ii )
      {
        v111 = (__int64)ii << 6;
        if ( (*(_DWORD *)&v109[v111 + 16] == 2 || (unsigned int)(*(_DWORD *)&v109[v111 + 16] - 3) <= 1)
          && *(_QWORD *)&v109[v111 + 56] )
        {
          CoTaskMemFree(*(LPVOID *)&v109[v111 + 56]);
          *(_QWORD *)((char *)v113 + v111 + 56) = 0;
          v109 = (char *)v113;
        }
      }
      if ( v109 )
      {
        CoTaskMemFree(v109);
        v113 = 0;
      }
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v180);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v123);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v118);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v119);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v140);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v146);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v147);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v130);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v141);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v120);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v131);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v132);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v121);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v142);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v133);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v116);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v175);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v177);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v124);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v125);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v128);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v126);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v122);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v148);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v143);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v134);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v135);
  v7 = v10;
LABEL_294:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v173);
  return v7;
}

```

## disassembly

```asm
0x140046ef0  mov     [rsp-8+arg_18], rbx
0x140046ef5  push    rbp
0x140046ef6  push    rsi
0x140046ef7  push    rdi
0x140046ef8  push    r12
0x140046efa  push    r13
0x140046efc  push    r14
0x140046efe  push    r15
0x140046f00  lea     rbp, [rsp-0F30h]
0x140046f08  mov     eax, 1030h
0x140046f0d  call    _alloca_probe
0x140046f12  sub     rsp, rax
0x140046f15  mov     rax, cs:__security_cookie
0x140046f1c  xor     rax, rsp
0x140046f1f  mov     [rbp+0F60h+var_40], rax
0x140046f26  mov     r14, r8
0x140046f29  mov     [rbp+0F60h+var_DE8], r8
0x140046f30  mov     rdi, rdx
0x140046f33  mov     [rbp+0F60h+var_DF0], rdx
0x140046f3a  mov     rsi, rcx
0x140046f3d  xor     r12d, r12d
0x140046f40  mov     [rsp+1060h+var_1028], r12d
0x140046f45  mov     [rsp+1060h+var_1030], r12
0x140046f4a  mov     [rsp+1060h+var_1024], r12d
0x140046f4f  mov     [rbp+0F60h+var_E58], r12
0x140046f56  mov     [rbp+0F60h+var_F88], r12
0x140046f5a  mov     [rbp+0F60h+var_F90], r12
0x140046f5e  mov     [rbp+0F60h+var_F58], r12
0x140046f62  mov     [rbp+0F60h+var_F30], r12
0x140046f66  mov     [rsp+1060h+var_FF0], r12
0x140046f6b  mov     [rbp+0F60h+var_FD0], r12
0x140046f6f  mov     [rbp+0F60h+var_FC0], r12
0x140046f73  mov     [rbp+0F60h+var_FD8], r12
0x140046f77  mov     [rbp+0F60h+var_FE0], r12
0x140046f7b  xorps   xmm0, xmm0
0x140046f7e  xor     eax, eax
0x140046f80  movups  xmmword ptr [rbp+0F60h+pvarg], xmm0
0x140046f87  mov     qword ptr [rbp+0F60h+pvarg+10h], rax
0x140046f8e  xorps   xmm1, xmm1
0x140046f91  movups  xmmword ptr [rbp+0F60h+var_E20], xmm1
0x140046f98  mov     qword ptr [rbp+0F60h+var_E20+10h], rax
0x140046f9f  movups  xmmword ptr [rbp+0F60h+var_E90], xmm0
0x140046fa6  mov     qword ptr [rbp+0F60h+var_E90+10h], rax
0x140046fad  lea     rcx, [rbp+0F60h+var_E08]
0x140046fb4  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x140046fba  nop
0x140046fbb  lea     rcx, [rbp+0F60h+var_E38]
0x140046fc2  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x140046fc8  nop
0x140046fc9  mov     [rbp+0F60h+bstrString], r12
0x140046fd0  mov     [rbp+0F60h+var_F50], r12
0x140046fd4  mov     [rbp+0F60h+var_F20], r12
0x140046fd8  mov     [rbp+0F60h+var_F18], r12
0x140046fdc  mov     [rbp+0F60h+var_F10], r12
0x140046fe0  mov     [rbp+0F60h+var_F08], r12
0x140046fe4  mov     [rbp+0F60h+var_F00], r12
0x140046fe8  mov     [rbp+0F60h+var_EF8], r12
0x140046fec  mov     [rbp+0F60h+var_EF0], r12
0x140046ff0  mov     [rbp+0F60h+var_EE8], r12
0x140046ff4  mov     [rbp+0F60h+var_EE0], r12
0x140046ffb  mov     [rbp+0F60h+var_ED8], r12
0x140047002  mov     [rbp+0F60h+var_ED0], r12
0x140047009  mov     [rbp+0F60h+var_EC8], r12
0x140047010  mov     [rbp+0F60h+var_EC0], r12
0x140047017  mov     [rbp+0F60h+var_EB8], r12
0x14004701e  mov     [rbp+0F60h+var_EB0], r12
0x140047025  mov     [rbp+0F60h+var_EA8], r12
0x14004702c  mov     [rbp+0F60h+var_EA0], r12
0x140047033  mov     [rbp+0F60h+var_E98], r12
0x14004703a  mov     [rbp+0F60h+var_E78], r12
0x140047041  mov     [rbp+0F60h+var_F74], r12d
0x140047045  mov     [rbp+0F60h+plLbound], r12d
0x140047049  mov     [rbp+0F60h+plUbound], r12d
0x14004704d  mov     [rbp+0F60h+var_E70], r12
0x140047054  mov     [rbp+0F60h+var_E68], r12
0x14004705b  mov     [rbp+0F60h+pv], r12
0x14004705f  mov     [rsp+1060h+var_1020], r12
0x140047064  mov     [rbp+0F60h+var_F98], r12
0x140047068  mov     [rbp+0F60h+var_F60], r12
0x14004706c  mov     [rsp+1060h+var_FF8], r12
0x140047071  mov     [rbp+0F60h+var_FA0], r12
0x140047075  mov     [rbp+0F60h+var_FA8], r12
0x140047079  mov     [rsp+1060h+var_1000], r12
0x14004707e  mov     [rbp+0F60h+var_F68], r12
0x140047082  mov     [rbp+0F60h+var_FB0], r12
0x140047086  mov     [rbp+0F60h+var_F38], r12
0x14004708a  mov     [rbp+0F60h+var_F40], r12
0x14004708e  mov     [rbp+0F60h+var_F70], r12
0x140047092  mov     [rbp+0F60h+var_FC8], r12d
0x140047096  mov     [rbp+0F60h+var_F28], r12d
0x14004709a  mov     [rbp+0F60h+var_F48], r12
0x14004709e  mov     [rbp+0F60h+var_F78], r12d
0x1400470a2  mov     [rsp+1060h+var_1018], r12
0x1400470a7  xorps   xmm0, xmm0
0x1400470aa  xor     eax, eax
0x1400470ac  movups  [rbp+0F60h+var_970], xmm0
0x1400470b3  mov     [rbp+0F60h+String1], rax
0x1400470ba  mov     r15d, 23Ch
0x1400470c0  mov     r8d, r15d; Size
0x1400470c3  xor     edx, edx; Val
0x1400470c5  lea     rcx, [rbp+0F60h+var_280]; void *
0x1400470cc  call    memset_0
0x1400470d1  lea     ebx, [r15-14h]
0x1400470d5  mov     r8d, ebx; Size
0x1400470d8  xor     edx, edx; Val
0x1400470da  lea     rcx, [rbp+0F60h+var_6F0]; void *
0x1400470e1  call    memset_0
0x1400470e6  mov     r8d, ebx; Size
0x1400470e9  xor     edx, edx; Val
0x1400470eb  lea     rcx, [rbp+0F60h+var_920]; void *
0x1400470f2  call    memset_0
0x1400470f7  mov     r8d, r15d; Size
0x1400470fa  xor     edx, edx; Val
0x1400470fc  lea     rcx, [rbp+0F60h+var_4C0]; void *
0x140047103  call    memset_0
0x140047108  mov     [rsp+1060h+var_1008], r12
0x14004710d  mov     [rsp+1060h+var_1010], r12
0x140047112  mov     [rsp+1060h+var_FE8], r12
0x140047117  xorps   xmm0, xmm0
0x14004711a  movups  [rbp+0F60h+var_958], xmm0
0x140047121  movups  [rbp+0F60h+var_948], xmm0
0x140047128  movups  [rbp+0F60h+var_938], xmm0
0x14004712f  lea     r8, aCvdsdisklunGet_48; "CVdsDiskLun::GetPathInfo()"
0x140047136  lea     edx, [r12+5Eh]
0x14004713b  lea     rcx, [rbp+0F60h+var_DE0]
0x140047142  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140047148  nop
0x140047149  mov     [rsp+1060h+var_1018], r12
0x14004714e  xorps   xmm0, xmm0
0x140047151  xor     eax, eax
0x140047153  movups  [rbp+0F60h+var_970], xmm0
0x14004715a  mov     [rbp+0F60h+String1], rax
0x140047161  mov     r8d, r15d; Size
0x140047164  xor     edx, edx; Val
0x140047166  lea     rcx, [rbp+0F60h+var_280]; void *
0x14004716d  call    memset_0
0x140047172  xorps   xmm0, xmm0
0x140047175  movups  [rbp+0F60h+var_958], xmm0
0x14004717c  movups  [rbp+0F60h+var_948], xmm0
0x140047183  movups  [rbp+0F60h+var_938], xmm0
0x14004718a  mov     r8d, ebx; Size
0x14004718d  xor     edx, edx; Val
0x14004718f  lea     rcx, [rbp+0F60h+var_6F0]; void *
0x140047196  call    memset_0
0x14004719b  mov     r8d, ebx; Size
0x14004719e  xor     edx, edx; Val
0x1400471a0  lea     rcx, [rbp+0F60h+var_920]; void *
0x1400471a7  call    memset_0
0x1400471ac  mov     r8d, r15d; Size
0x1400471af  xor     edx, edx; Val
0x1400471b1  lea     rcx, [rbp+0F60h+var_4C0]; void *
0x1400471b8  call    memset_0
0x1400471bd  lea     rcx, [rbp+0F60h+pvarg]; pvarg
0x1400471c4  call    cs:__imp_VariantInit
0x1400471ca  lea     rcx, [rbp+0F60h+var_E20]; pvarg
0x1400471d1  call    cs:__imp_VariantInit
0x1400471d7  lea     rcx, [rbp+0F60h+var_E90]; pvarg
0x1400471de  call    cs:__imp_VariantInit
0x1400471e4  mov     dword ptr [rsp+1060h+var_1018], 8
0x1400471ec  mov     eax, [rsi+0F0h]
0x1400471f2  cmp     eax, 3
0x1400471f5  jnz     loc_140048294
0x1400471fb  test    rdi, rdi
0x1400471fe  jz      loc_14004827B
0x140047204  test    r14, r14
0x140047207  jz      loc_14004827B
0x14004720d  mov     [r14], r12d
0x140047210  mov     [rdi], r12
0x140047213  cmp     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x14004721a  jnz     loc_14004735B
0x140047220  lea     rdx, aCvdsdisklunGet_128; "CVdsDiskLun::GetPathInfo: Could not loa"...
0x140047227  xor     ecx, ecx
0x140047229  call    cs:__imp_VdsTraceW
0x14004722f  nop
0x140047230  lea     rcx, [rbp+0F60h+var_DE0]
0x140047237  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004723d  nop
0x14004723e  lea     rcx, [rsp+1060h+var_FE8]
0x140047243  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047248  nop
0x140047249  lea     rcx, [rsp+1060h+var_1010]
0x14004724e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047253  nop
0x140047254  lea     rcx, [rsp+1060h+var_1008]
0x140047259  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004725e  nop
0x14004725f  lea     rcx, [rbp+0F60h+var_F70]
0x140047263  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047268  nop
0x140047269  lea     rcx, [rbp+0F60h+var_F40]
0x14004726d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047272  nop
0x140047273  lea     rcx, [rbp+0F60h+var_F38]
0x140047277  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004727c  nop
0x14004727d  lea     rcx, [rbp+0F60h+var_FB0]
0x140047281  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047286  nop
0x140047287  lea     rcx, [rbp+0F60h+var_F68]
0x14004728b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047290  nop
0x140047291  lea     rcx, [rsp+1060h+var_1000]
0x140047296  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004729b  nop
0x14004729c  lea     rcx, [rbp+0F60h+var_FA8]
0x1400472a0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472a5  nop
0x1400472a6  lea     rcx, [rbp+0F60h+var_FA0]
0x1400472aa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472af  nop
0x1400472b0  lea     rcx, [rsp+1060h+var_FF8]
0x1400472b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472ba  nop
0x1400472bb  lea     rcx, [rbp+0F60h+var_F60]
0x1400472bf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472c4  nop
0x1400472c5  lea     rcx, [rbp+0F60h+var_F98]
0x1400472c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472ce  nop
0x1400472cf  lea     rcx, [rsp+1060h+var_1020]
0x1400472d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472d9  nop
0x1400472da  lea     rcx, [rbp+0F60h+var_E38]
0x1400472e1  call    cs:__imp_??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum(void)
0x1400472e7  nop
0x1400472e8  lea     rcx, [rbp+0F60h+var_E08]
0x1400472ef  call    cs:__imp_??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum(void)
0x1400472f5  nop
0x1400472f6  lea     rcx, [rbp+0F60h+var_FE0]
0x1400472fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400472ff  nop
0x140047300  lea     rcx, [rbp+0F60h+var_FD8]
0x140047304  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047309  nop
0x14004730a  lea     rcx, [rbp+0F60h+var_FC0]
0x14004730e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047313  nop
0x140047314  lea     rcx, [rbp+0F60h+var_FD0]
0x140047318  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004731d  nop
0x14004731e  lea     rcx, [rsp+1060h+var_FF0]
0x140047323  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047328  nop
0x140047329  lea     rcx, [rbp+0F60h+var_F30]
0x14004732d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047332  nop
0x140047333  lea     rcx, [rbp+0F60h+var_F58]
0x140047337  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004733c  nop
0x14004733d  lea     rcx, [rbp+0F60h+var_F90]
0x140047341  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047346  nop
0x140047347  lea     rcx, [rbp+0F60h+var_F88]
0x14004734b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140047350  nop
0x140047351  mov     ebx, 80042400h
0x140047356  jmp     loc_140048F5B
0x14004735b  lea     rcx, Source; "root\\wmi"
0x140047362  call    cs:__imp_SysAllocString
0x140047368  mov     rdi, rax
0x14004736b  mov     [rbp+0F60h+bstrString], rax
0x140047372  lea     rcx, aInstancename; "InstanceName"
0x140047379  call    cs:__imp_SysAllocString
0x14004737f  mov     [rbp+0F60h+var_F50], rax
0x140047383  lea     rcx, aDsmQueryunique; "DSM_QueryUniqueId"
0x14004738a  call    cs:__imp_SysAllocString
0x140047390  mov     [rbp+0F60h+var_F20], rax
0x140047394  lea     rcx, aDsmuniqueid; "DsmUniqueId"
0x14004739b  call    cs:__imp_SysAllocString
0x1400473a1  mov     [rbp+0F60h+var_F18], rax
0x1400473a5  lea     rcx, aPdoinformation; "PdoInformation"
0x1400473ac  call    cs:__imp_SysAllocString
0x1400473b2  mov     [rbp+0F60h+var_F10], rax
0x1400473b6  lea     rcx, aScsiaddress; "ScsiAddress"
0x1400473bd  call    cs:__imp_SysAllocString
0x1400473c3  mov     [rbp+0F60h+var_F08], rax
0x1400473c7  lea     rcx, aPortnumber; "PortNumber"
0x1400473ce  call    cs:__imp_SysAllocString
0x1400473d4  mov     [rbp+0F60h+var_F00], rax
0x1400473d8  lea     rcx, aScsipathid; "ScsiPathId"
0x1400473df  call    cs:__imp_SysAllocString
0x1400473e5  mov     [rbp+0F60h+var_EF8], rax
0x1400473e9  lea     rcx, aTargetid; "TargetId"
0x1400473f0  call    cs:__imp_SysAllocString
0x1400473f6  mov     [rbp+0F60h+var_EF0], rax
0x1400473fa  lea     rcx, aLun; "Lun"
0x140047401  call    cs:__imp_SysAllocString
0x140047407  mov     [rbp+0F60h+var_EE8], rax
0x14004740b  lea     rcx, aPathidentifier; "PathIdentifier"
0x140047412  call    cs:__imp_SysAllocString
0x140047418  mov     [rbp+0F60h+var_EE0], rax
0x14004741f  lea     rcx, aMsiscsiInitiat; "MSiSCSI_InitiatorSessionInfo"
0x140047426  call    cs:__imp_SysAllocString
0x14004742c  mov     [rbp+0F60h+var_ED8], rax
0x140047433  lea     rcx, aUniqueadapteri; "UniqueAdapterId"
0x14004743a  call    cs:__imp_SysAllocString
0x140047440  mov     [rbp+0F60h+var_ED0], rax
0x140047447  lea     rcx, aSessionslist; "SessionsList"
0x14004744e  call    cs:__imp_SysAllocString
0x140047454  mov     [rbp+0F60h+var_EC8], rax
  ... truncated ...
```
