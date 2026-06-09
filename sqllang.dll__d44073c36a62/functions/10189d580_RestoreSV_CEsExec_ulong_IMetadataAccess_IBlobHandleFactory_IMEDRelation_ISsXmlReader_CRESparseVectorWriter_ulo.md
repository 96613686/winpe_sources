# RestoreSV(CEsExec *,ulong,IMetadataAccess *,IBlobHandleFactory *,IMEDRelation *,ISsXmlReader *,CRESparseVectorWriter *,ulong *)

- ea: `0x10189d580`
- end: `0x10189f3c9`
- name: `?RestoreSV@@YAXPEAVCEsExec@@KPEAVIMetadataAccess@@PEAUIBlobHandleFactory@@PEAVIMEDRelation@@PEAVISsXmlReader@@PEAVCRESparseVectorWriter@@PEAK@Z`
- size: `7753`
- prototype: `void __fastcall(struct CEsExec *, unsigned int, struct IMetadataAccess *, struct IBlobHandleFactory *, struct IMEDRelation *, struct ISsXmlReader *, struct CRESparseVectorWriter *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10189b950`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x100454360`
- `0x10045ab00`
- `0x10046cb10`
- `0x10046d010`
- `0x10053e0f0`
- `0x100794d60`
- `0x100860500`
- `0x1017a08c0`
- `0x1017ab8a0`
- `0x10189cbb0`
- `0x10189d580`
- `0x10189fde0`
- `0x10189fe50`
- `0x10189fec0`
- `0x101d5b700`

## import_xrefs

- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189d814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189dc31`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189dd51`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189eb5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ecae`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ed0d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ed75`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ee7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189efa6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189d814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189dc31`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189dd51`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189eb5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ecae`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ed0d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ed75`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189ee7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10189efa6`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10189f0ec`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10189f105`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10189f0ec`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10189f105`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10189f135`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10189f135`
- `sqldk!SystemThread_TlsIndex` at `0x10189d8ca`
- `sqldk!SystemThread_TlsIndex` at `0x10189f0b4`
- `sqldk!SystemThread_TlsOffset` at `0x10189d8d3`
- `sqldk!SystemThread_TlsOffset` at `0x10189f0bd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10189f342`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10189f38d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10189f342`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10189f38d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10189f0d8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10189f0d8`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10189f0fc`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10189f0fc`
- `sqlTsEs!?Write@CRESparseVectorWriter@@QEAAXXZ` at `0x10189f2f3`
- `sqlTsEs!?Write@CRESparseVectorWriter@@QEAAXXZ` at `0x10189f2f3`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e024`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e151`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e284`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e4e9`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e024`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e151`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e284`
- `sqlTsEs!?WstrConvertToUI1@CXVariant@@SAJPEB_WKPEAE@Z` at `0x10189e4e9`
- `sqlTsEs!?WstrConvertToI2@CXVariant@@SAJPEB_WKPEAF@Z` at `0x10189def6`
- `sqlTsEs!?WstrConvertToI2@CXVariant@@SAJPEB_WKPEAF@Z` at `0x10189def6`
- `sqlTsEs!?ResetAndSetType@CBufferedBlobXVarBase@@UEAAXPEBVCTypeInfo@@@Z` at `0x10189f09c`
- `sqlTsEs!?ResetAndSetType@CBufferedBlobXVarBase@@UEAAXPEBVCTypeInfo@@@Z` at `0x10189f09c`
- `sqlTsEs!?GetDefaultCollationData@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x10189d8eb`
- `sqlTsEs!?GetDefaultCollationData@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x10189d8eb`
- `sqlTsEs!?LWstrToI4@@YAJPEFB_WHPEFAJ@Z` at `0x10189e3b7`
- `sqlTsEs!?LWstrToI4@@YAJPEFB_WHPEFAJ@Z` at `0x10189e3b7`
- `sqlTsEs!??0CBufferedBlobXVarTmp@@QEAA@PEAVCTypeInfo@@PEAUIBlobHandleFactory@@@Z` at `0x10189d639`
- `sqlTsEs!??0CBufferedBlobXVarTmp@@QEAA@PEAVCTypeInfo@@PEAUIBlobHandleFactory@@@Z` at `0x10189d639`
- `sqlTsEs!??1CBufferedBlobXVarTmpBase@@UEAA@XZ` at `0x10189f3a0`
- `sqlTsEs!??1CBufferedBlobXVarTmpBase@@UEAA@XZ` at `0x10189f3a0`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dad9`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dafe`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dc6a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dda7`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189deb8`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dedd`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dfe6`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e00b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e113`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e138`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e246`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e26b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e379`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e39e`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e4ab`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e4d0`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e5e2`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e607`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e633`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e662`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e6c2`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e7eb`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e810`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e830`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e85a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e94e`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e973`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e999`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e9c5`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dad9`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dafe`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dc6a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dda7`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189deb8`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dedd`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189dfe6`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e00b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e113`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e138`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e246`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e26b`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e379`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e39e`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e4ab`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e4d0`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e5e2`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e607`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e633`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e662`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e6c2`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e7eb`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e810`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e830`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e85a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e94e`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e973`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e999`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10189e9c5`

## string_xrefs

- `0x10189e5d8`: `sqlCompareOptions`
- `0x10189e7a8`: `sqlCompareOptions`
- `0x10189daf4`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x10189db0c`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189ded3`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e001`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e12e`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e261`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e394`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e4c6`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e5fd`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e806`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`
- `0x10189e969`: `http://schemas.microsoft.com/sqlserver/2004/sqltypes`

## pseudocode

```c

```
