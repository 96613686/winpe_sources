# CImpImportProvider::GetRowsetPtr(tagIMPORT_INFO,CBulkImp *,unsigned __int64,tagIMPORT_COLINFO * const,unsigned __int64,tagIMPORT_KEYINFO * const,unsigned __int64,wchar_t * const,unsigned __int64,wchar_t * const,unsigned __int64,uchar * const,unsigned __int64,uchar * const,ushort,unsigned __int64,unsigned __int64,CBcpImport *,bool,IGrantPageAllocator *,IUnknown * *)

- ea: `0x102097910`
- end: `0x102099a63`
- name: `?GetRowsetPtr@CImpImportProvider@@QEAAJUtagIMPORT_INFO@@PEAVCBulkImp@@_KQEAUtagIMPORT_COLINFO@@2QEAUtagIMPORT_KEYINFO@@2QEA_W252QEAE26G22PEAVCBcpImport@@_NPEAVIGrantPageAllocator@@PEAPEAUIUnknown@@@Z`
- size: `8531`
- prototype: `__int64 __fastcall(__int64, struct tagIMPORT_INFO *, __int64, unsigned __int64, struct IMemObj *, unsigned __int64, struct tagIMPORT_KEYINFO *, __int64, wchar_t *, __int64, wchar_t *, unsigned __int64 cchWideChar, const WCHAR *, rsize_t DestinationSize, const WCHAR *, __int64, unsigned __int64, unsigned __int64, struct CBcpImport *, unsigned __int8, struct IGrantPageAllocator *, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x100401490`
- `0x100402000`
- `0x1004025c0`
- `0x100415e90`
- `0x10042d300`
- `0x10042d820`
- `0x10042d8d4`
- `0x10045e0a0`
- `0x10045e1b8`
- `0x100882d10`
- `0x101217580`
- `0x102070d70`
- `0x102071450`
- `0x102071c00`
- `0x102077e30`
- `0x102082950`
- `0x102082bf0`
- `0x102083b40`
- `0x102086750`
- `0x102087310`
- `0x102087800`
- `0x102096fc0`
- `0x102097120`
- `0x1020975c0`
- `0x1020977e0`
- `0x102097910`
- `0x102099a90`
- `0x102099f10`
- `0x102099f80`
- `0x10209ff20`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x102098326`
- `KERNEL32!MapViewOfFile` at `0x102098326`
- `KERNEL32!GetACP` at `0x102097e36`
- `KERNEL32!GetACP` at `0x102097e66`
- `KERNEL32!GetACP` at `0x102097e36`
- `KERNEL32!GetACP` at `0x102097e66`
- `KERNEL32!GetOEMCP` at `0x102097e2e`
- `KERNEL32!GetOEMCP` at `0x102097e5e`
- `KERNEL32!GetOEMCP` at `0x102097e2e`
- `KERNEL32!GetOEMCP` at `0x102097e5e`
- `KERNEL32!OpenFileMappingA` at `0x10209826c`
- `KERNEL32!OpenFileMappingA` at `0x10209826c`
- `KERNEL32!OpenEventA` at `0x10209840c`
- `KERNEL32!OpenEventA` at `0x1020984f2`
- `KERNEL32!OpenEventA` at `0x10209840c`
- `KERNEL32!OpenEventA` at `0x1020984f2`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x1020991e7`
- `sqlTsEs!?DbtFromXvt@@YAGE@Z` at `0x1020991e7`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102097e9c`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102099235`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102097e9c`
- `sqlTsEs!?CIDFromTDSCollation@@YAKPEFBUTDSCOLLATION@@@Z` at `0x102099235`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102097ea4`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x10209923d`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x102097ea4`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x10209923d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10209822b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020983cb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020984b1`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10209822b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020983cb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1020984b1`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x102098958`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x102098958`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102098077`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x102098077`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102097e08`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020986ee`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102098e38`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102099440`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020995a7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102097e08`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020986ee`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102098e38`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102099440`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020995a7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020981d0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020989fe`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102098ac9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020996ef`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020981d0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020989fe`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102098ac9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1020996ef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1020994c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102099629`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1020994c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x102099629`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102098978`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020994e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10209964a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x102098978`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020994e6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10209964a`
- `sqldk!SystemThread_TlsIndex` at `0x102097dba`
- `sqldk!SystemThread_TlsIndex` at `0x102098033`
- `sqldk!SystemThread_TlsIndex` at `0x10209808f`
- `sqldk!SystemThread_TlsIndex` at `0x10209810e`
- `sqldk!SystemThread_TlsIndex` at `0x10209817a`
- `sqldk!SystemThread_TlsIndex` at `0x1020985c3`
- `sqldk!SystemThread_TlsIndex` at `0x10209867e`
- `sqldk!SystemThread_TlsIndex` at `0x1020989a8`
- `sqldk!SystemThread_TlsIndex` at `0x102098a73`
- `sqldk!SystemThread_TlsIndex` at `0x102098dd4`
- `sqldk!SystemThread_TlsIndex` at `0x1020993f3`
- `sqldk!SystemThread_TlsIndex` at `0x10209955a`
- `sqldk!SystemThread_TlsIndex` at `0x102099699`
- `sqldk!SystemThread_TlsOffset` at `0x102097dc3`
- `sqldk!SystemThread_TlsOffset` at `0x10209803c`
- `sqldk!SystemThread_TlsOffset` at `0x102098098`
- `sqldk!SystemThread_TlsOffset` at `0x102098117`
- `sqldk!SystemThread_TlsOffset` at `0x102098183`
- `sqldk!SystemThread_TlsOffset` at `0x1020985cc`
- `sqldk!SystemThread_TlsOffset` at `0x102098687`
- `sqldk!SystemThread_TlsOffset` at `0x1020989b1`
- `sqldk!SystemThread_TlsOffset` at `0x102098a7c`
- `sqldk!SystemThread_TlsOffset` at `0x102098ddd`
- `sqldk!SystemThread_TlsOffset` at `0x1020993fc`
- `sqldk!SystemThread_TlsOffset` at `0x102099563`
- `sqldk!SystemThread_TlsOffset` at `0x1020996a2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10209998e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x102099a30`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10209998e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x102099a30`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102097dde`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098057`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020980b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10209819e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020986a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020989cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098a97`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098df8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102099417`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10209957e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020996bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102097dde`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098057`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020980b3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10209819e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020986a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020989cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098a97`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102098df8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102099417`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10209957e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020996bd`
- `sqldk!??_V@YAXPEAX@Z` at `0x102098b73`
- `sqldk!??_V@YAXPEAX@Z` at `0x102098e48`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099018`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099450`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020995b7`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099968`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099972`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099a0d`
- `sqldk!??_V@YAXPEAX@Z` at `0x102098b73`
- `sqldk!??_V@YAXPEAX@Z` at `0x102098e48`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099018`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099450`
- `sqldk!??_V@YAXPEAX@Z` at `0x1020995b7`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099968`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099972`
- `sqldk!??_V@YAXPEAX@Z` at `0x102099a0d`
- `sqllang!?GetErrorFileByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097b04`
- `sqllang!?GetErrorFileByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097b04`
- `sqllang!?IsBatchExtractorFramework@CRemoteFileRowsetMetadata@@QEBA_NXZ` at `0x102097bed`
- `sqllang!?IsBatchExtractorFramework@CRemoteFileRowsetMetadata@@QEBA_NXZ` at `0x102097bed`
- `sqllang!?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ` at `0x102097c09`
- `sqllang!?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ` at `0x102097c1b`
- `sqllang!?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ` at `0x102097c09`
- `sqllang!?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ` at `0x102097c1b`
- `sqllang!?GetRowsetColDefHead@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetColDef@@XZ` at `0x102097a79`
- `sqllang!?GetRowsetColDefHead@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetColDef@@XZ` at `0x102097a79`
- `sqllang!?UnfilteredResolvedFiles@CRemoteFileRowsetMetadata@@QEBAPEBV?$CTDynArray@PEAVIDirectoryContentList@@V?$CFnI_Default@PEAVIDirectoryContentList@@@@V?$CFnD_Ptr@VIDirectoryContentList@@@@V?$CMemObjAlloc@$0A@@@@@XZ` at `0x102097a94`
- `sqllang!?UnfilteredResolvedFiles@CRemoteFileRowsetMetadata@@QEBAPEBV?$CTDynArray@PEAVIDirectoryContentList@@V?$CFnI_Default@PEAVIDirectoryContentList@@@@V?$CFnD_Ptr@VIDirectoryContentList@@@@V?$CMemObjAlloc@$0A@@@@@XZ` at `0x102097a94`
- `sqllang!?GetErrorFile@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097af4`
- `sqllang!?GetErrorFile@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097af4`
- `sqllang!?GetErrorFileSecret@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097b9c`
- `sqllang!?GetErrorFileSecret@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097b9c`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x10209814c`
- `sqllang!?intnl_impersonate_client@@YAHPEAVCSession@@@Z` at `0x10209814c`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x1020985e5`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x1020985e5`
- `sqllang!?FIncreaseBufferCount@CBulkImp@@QEBA_NXZ` at `0x102097a00`
- `sqllang!?FIncreaseBufferCount@CBulkImp@@QEBA_NXZ` at `0x102097a00`
- `sqllang!?GetFileReadLength@CRemoteFileRowsetMetadata@@QEBA_KXZ` at `0x102097a69`
- `sqllang!?GetFileReadLength@CRemoteFileRowsetMetadata@@QEBA_KXZ` at `0x102097a69`
- `sqllang!?GetExternalDataSourceName@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097aa7`
- `sqllang!?GetExternalDataSourceName@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097aa7`
- `sqllang!?GetExternalDataSourceNameLength@CRemoteFileRowsetMetadata@@QEAAHXZ` at `0x102097ab7`
- `sqllang!?GetExternalDataSourceNameLength@CRemoteFileRowsetMetadata@@QEAAHXZ` at `0x102097ab7`
- `sqllang!?GetSecretValue@CBulkImp@@QEBAPEA_WXZ` at `0x102097acc`
- `sqllang!?GetSecretValue@CBulkImp@@QEBAPEA_WXZ` at `0x102097acc`
- `sqllang!?GetSecretValueByteCount@CBulkImp@@QEBAHXZ` at `0x102097adf`
- `sqllang!?GetSecretValueByteCount@CBulkImp@@QEBAHXZ` at `0x102097adf`
- `sqllang!?GetErrorFileDataSource@CBulkImp@@QEBAPEA_WXZ` at `0x102097b19`
- `sqllang!?GetErrorFileDataSource@CBulkImp@@QEBAPEA_WXZ` at `0x102097b19`
- `sqllang!?GetErrorFileDataSourceByteCount@CBulkImp@@QEBAHXZ` at `0x102097b29`
- `sqllang!?GetErrorFileDataSourceByteCount@CBulkImp@@QEBAHXZ` at `0x102097b29`
- `sqllang!?GetFormatFile@CBulkImp@@QEBAPEA_WXZ` at `0x102097b3e`
- `sqllang!?GetFormatFile@CBulkImp@@QEBAPEA_WXZ` at `0x102097b3e`
- `sqllang!?GetFormatFileByteCount@CBulkImp@@QEBAHXZ` at `0x102097b4e`
- `sqllang!?GetFormatFileByteCount@CBulkImp@@QEBAHXZ` at `0x102097b4e`
- `sqllang!?GetFormatFileDataSource@CBulkImp@@QEBAPEA_WXZ` at `0x102097b63`
- `sqllang!?GetFormatFileDataSource@CBulkImp@@QEBAPEA_WXZ` at `0x102097b63`
- `sqllang!?GetFormatFileDataSourceByteCount@CBulkImp@@QEBAHXZ` at `0x102097b73`
- `sqllang!?GetFormatFileDataSourceByteCount@CBulkImp@@QEBAHXZ` at `0x102097b73`
- `sqllang!?GetErrorFileSecretByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097bac`
- `sqllang!?GetErrorFileSecretByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097bac`
- `sqllang!?GetCompression@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097bc1`
- `sqllang!?GetCompression@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ` at `0x102097bc1`
- `sqllang!?GetCompressionByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097bd1`
- `sqllang!?GetCompressionByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ` at `0x102097bd1`
- `sqllang!?GetRowsetFilesInfo@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetFilesInfo@@XZ` at `0x102097bf9`
- `sqllang!?GetRowsetFilesInfo@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetFilesInfo@@XZ` at `0x102097bf9`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c26`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c34`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c42`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c26`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c34`
- `sqllang!?GetBulkImpTableSampleData@CRemoteFileRowsetMetadata@@QEBAPEAUBulkImp_TableSampleData@@XZ` at `0x102098c42`
- `sqllang!?NormalizeTerminator@@YAXI_NPEA_WKPEAEAEAK30@Z` at `0x10209949a`
- `sqllang!?NormalizeTerminator@@YAXI_NPEA_WKPEAEAEAK30@Z` at `0x102099601`
- `sqllang!?NormalizeTerminator@@YAXI_NPEA_WKPEAEAEAK30@Z` at `0x10209949a`
- `sqllang!?NormalizeTerminator@@YAXI_NPEA_WKPEAEAEAK30@Z` at `0x102099601`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CImpImportProvider::GetRowsetPtr(
        __int64 a1,
        struct tagIMPORT_INFO *a2,
        __int64 a3,
        unsigned __int64 a4,
        struct IMemObj *a5,
        unsigned __int64 a6,
        struct tagIMPORT_KEYINFO *a7,
        __int64 a8,
        wchar_t *a9,
        __int64 a10,
        wchar_t *a11,
        unsigned __int64 cchWideChar,
        const WCHAR *a13,
        rsize_t DestinationSize,
        const WCHAR *a15,
        __int64 a16,
        unsigned __int64 a17,
        unsigned __int64 a18,
        struct CBcpImport *a19,
        unsigned __int8 a20,
        struct IGrantPageAllocator *a21,
        __int64 a22)
{
  __int64 v23; // r13
  struct tagIMPORT_COLINFO *v24; // r12
  int v25; // r15d
  int v26; // ecx
  __int64 v27; // xmm6_8
  __int64 v28; // rsi
  __int64 v29; // rdi
  wchar_t *SecretValue; // r14
  struct CRowsetFilesInfo *RowsetFilesInfo; // rbx
  bool v32; // zf
  struct IGrantPageAllocator *v33; // rax
  int v34; // eax
  __int64 v35; // rbx
  unsigned int v36; // r14d
  bool v37; // cl
  unsigned int v38; // ebx
  __int64 v39; // rcx
  struct tagIMPORT_INFO *v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rdx
  int v43; // ecx
  UINT OEMCP; // eax
  int v45; // ecx
  UINT ACP; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned __int64 v49; // rbx
  const void *v50; // rdx
  size_t v51; // r8
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rdx
  _BYTE *v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdx
  HANDLE *v60; // rax
  HANDLE *v61; // rbx
  __crt_locale_pointers *DefaultLocale; // rax
  HANDLE v63; // rax
  LPVOID v64; // rax
  __crt_locale_pointers *v65; // rax
  HANDLE v66; // rax
  __crt_locale_pointers *v67; // rax
  HANDLE v68; // rax
  int v69; // r15d
  __int64 v70; // rbx
  __int64 v71; // rcx
  struct IMemObj *v72; // rcx
  __int64 v73; // rax
  bool v74; // cf
  unsigned __int64 v75; // rax
  _QWORD *v76; // rax
  void *v77; // rsi
  struct IMemObj *v78; // rsi
  unsigned int v79; // r8d
  char v80; // cl
  _QWORD *v81; // rbx
  unsigned int v82; // eax
  _QWORD *v83; // rdx
  __int64 v84; // r12
  void *v85; // r15
  unsigned int v86; // r14d
  _QWORD *v87; // rdi
  __int64 v88; // rcx
  _QWORD *v89; // rax
  __int64 v90; // rax
  unsigned int v91; // ecx
  unsigned int v92; // eax
  wchar_t *OSErrString; // rax
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v95; // rbx
  __int64 v96; // rdx
  void *v97; // rax
  __int64 v98; // rbx
  __int64 v99; // rbx
  __int64 v100; // rdx
  struct IMemObj *v101; // rax
  __int64 *v102; // rsi
  __int64 v103; // rcx
  __int64 v104; // rsi
  unsigned __int64 v105; // rdi
  CRemoteFileRowsetMetadata *v106; // r14
  CImportStream *v107; // rbx
  char v108; // cl
  __int64 v109; // r9
  struct tagIMPORT_INFO *v110; // r14
  int v111; // r15d
  unsigned int v112; // esi
  rsize_t v113; // rdi
  rsize_t v114; // rdx
  unsigned __int64 v115; // rax
  void *v116; // rsp
  WCHAR *v117; // rdi
  __int64 v118; // r15
  __int64 v119; // rbx
  __int64 v120; // r10
  unsigned __int64 v121; // rax
  unsigned __int64 v122; // rsi
  unsigned int v123; // r10d
  unsigned __int64 v124; // r8
  __int64 v125; // r9
  unsigned __int64 v126; // rcx
  _QWORD *v127; // rdx
  unsigned __int64 v128; // rcx
  _QWORD *v129; // rax
  char v130; // cl
  unsigned int v131; // edx
  unsigned __int64 v132; // rdi
  unsigned int v133; // r10d
  __int64 v134; // r8
  unsigned __int64 v135; // rcx
  _QWORD *v136; // rax
  char v137; // cl
  unsigned __int64 v138; // r14
  __int64 v139; // rdi
  struct tagIMPORT_INFO *v140; // r15
  __int64 v141; // rbx
  const struct TDSCOLLATION *v142; // rcx
  char v143; // al
  unsigned int v144; // eax
  unsigned int v145; // eax
  __int64 v146; // rax
  __int16 v147; // cx
  int v148; // eax
  bool v149; // r15
  unsigned int v150; // r14d
  double v151; // xmm6_8
  double v152; // xmm0_8
  unsigned int v153; // esi
  __int64 v154; // rdi
  __int64 v155; // rdx
  double v156; // xmm0_8
  unsigned int v157; // r13d
  __int64 v158; // rdi
  __int64 v159; // rdx
  WCHAR *v160; // rsi
  struct tagIMPORT_INFO *v161; // r15
  char v162; // di
  __int64 v163; // rbx
  __int64 v164; // rdx
  char *v165; // rax
  CImportRowset *v166; // r14
  struct DELIMITER_INFO *v167; // r8
  struct CImportStream *v168; // r10
  _QWORD *v169; // rbx
  _QWORD *v170; // rbx
  HANDLE *v171; // rbx
  int Locale; // [rsp+20h] [rbp-B0h]
  CBulkImp *v174; // [rsp+B0h] [rbp-20h]
  bool v175; // [rsp+B0h] [rbp-20h]
  char Destination; // [rsp+D0h] [rbp+0h] BYREF
  __int16 v177; // [rsp+D1h] [rbp+1h]
  char v178; // [rsp+D3h] [rbp+3h]
  char v179; // [rsp+D4h] [rbp+4h]
  unsigned __int8 v180; // [rsp+D5h] [rbp+5h]
  char v181; // [rsp+D6h] [rbp+6h]
  bool v182; // [rsp+D7h] [rbp+7h] BYREF
  int v183; // [rsp+D8h] [rbp+8h]
  char v184; // [rsp+DCh] [rbp+Ch]
  bool IsBatchExtractorFramework; // [rsp+DDh] [rbp+Dh]
  int v186; // [rsp+E0h] [rbp+10h]
  unsigned int v187; // [rsp+E4h] [rbp+14h] BYREF
  unsigned int v188; // [rsp+E8h] [rbp+18h] BYREF
  int v189[2]; // [rsp+F0h] [rbp+20h] BYREF
  int v190[2]; // [rsp+F8h] [rbp+28h] BYREF
  unsigned __int64 v191; // [rsp+100h] [rbp+30h]
  int v192; // [rsp+108h] [rbp+38h] BYREF
  struct tagIMPORT_INFO *v193; // [rsp+110h] [rbp+40h]
  int v194; // [rsp+118h] [rbp+48h]
  int v195; // [rsp+11Ch] [rbp+4Ch]
  unsigned int BufferCount; // [rsp+120h] [rbp+50h]
  unsigned int v197; // [rsp+124h] [rbp+54h]
  unsigned int v198; // [rsp+128h] [rbp+58h]
  int v199; // [rsp+12Ch] [rbp+5Ch] BYREF
  int v200; // [rsp+130h] [rbp+60h]
  struct CImportStream *v201; // [rsp+138h] [rbp+68h] BYREF
  struct DELIMITER_INFO *v202; // [rsp+140h] [rbp+70h] BYREF
  __int64 *v203; // [rsp+148h] [rbp+78h]
  HANDLE *v204; // [rsp+150h] [rbp+80h]
  BOOL v205; // [rsp+158h] [rbp+88h]
  unsigned int v206; // [rsp+15Ch] [rbp+8Ch] BYREF
  int v207; // [rsp+160h] [rbp+90h]
  unsigned int v208; // [rsp+164h] [rbp+94h] BYREF
  unsigned int v209; // [rsp+168h] [rbp+98h] BYREF
  wchar_t *v210; // [rsp+170h] [rbp+A0h]
  struct IMemObj *v211; // [rsp+178h] [rbp+A8h]
  unsigned __int64 v212; // [rsp+180h] [rbp+B0h]
  wchar_t *Compression; // [rsp+188h] [rbp+B8h]
  unsigned __int64 v214; // [rsp+190h] [rbp+C0h]
  struct IGrantPageAllocator *v215; // [rsp+198h] [rbp+C8h]
  int v216; // [rsp+1A0h] [rbp+D0h]
  unsigned __int64 v217; // [rsp+1A8h] [rbp+D8h]
  wchar_t *ExternalDataSourceName; // [rsp+1B0h] [rbp+E0h]
  void *v219; // [rsp+1B8h] [rbp+E8h] BYREF
  _QWORD *v220; // [rsp+1C0h] [rbp+F0h]
  __int64 v221; // [rsp+1C8h] [rbp+F8h]
  WCHAR *v222; // [rsp+1D0h] [rbp+100h]
  void *v223; // [rsp+1D8h] [rbp+108h]
  _QWORD *v224; // [rsp+1E0h] [rbp+110h]
  struct IMemObj *v225; // [rsp+1E8h] [rbp+118h]
  LPCWCH v226; // [rsp+1F0h] [rbp+120h]
  wchar_t *v227; // [rsp+1F8h] [rbp+128h]
  unsigned __int64 Length; // [rsp+200h] [rbp+130h]
  __int64 v229; // [rsp+208h] [rbp+138h]
  _QWORD *v230; // [rsp+210h] [rbp+140h]
  wchar_t *v231; // [rsp+218h] [rbp+148h]
  LPCWCH v232; // [rsp+220h] [rbp+150h]
  CImportRowset *v233; // [rsp+228h] [rbp+158h]
  int v234; // [rsp+230h] [rbp+160h]
  __int64 v235; // [rsp+238h] [rbp+168h]
  wchar_t *ErrorFileSecret; // [rsp+240h] [rbp+170h]
  unsigned __int64 v237; // [rsp+248h] [rbp+178h]
  wchar_t *ErrorFileDataSource; // [rsp+250h] [rbp+180h]
  unsigned __int64 v239; // [rsp+258h] [rbp+188h]
  wchar_t *ErrorFile; // [rsp+260h] [rbp+190h]
  unsigned __int64 v241; // [rsp+268h] [rbp+198h]
  void *Source; // [rsp+270h] [rbp+1A0h]
  __int64 v243; // [rsp+278h] [rbp+1A8h]
  void *FormatFileDataSource; // [rsp+280h] [rbp+1B0h]
  struct CRowsetColDef *RowsetColDefHead; // [rsp+288h] [rbp+1B8h]
  __int64 v246; // [rsp+290h] [rbp+1C0h]
  struct CBcpImport *v247; // [rsp+298h] [rbp+1C8h]
  LPCWCH v248; // [rsp+2A0h] [rbp+1D0h]
  LPCWCH lpWideCharStr; // [rsp+2A8h] [rbp+1D8h]
  struct tagIMPORT_KEYINFO *v250; // [rsp+2B0h] [rbp+1E0h]
  __int64 v251; // [rsp+2B8h] [rbp+1E8h]
  struct IMemObj *v252; // [rsp+2C0h] [rbp+1F0h]
  struct IMemObj *v253; // [rsp+2C8h] [rbp+1F8h]
  int v254; // [rsp+2D0h] [rbp+200h] BYREF
  __int64 v255; // [rsp+2D8h] [rbp+208h]
  int v256; // [rsp+2E0h] [rbp+210h] BYREF
  int v257; // [rsp+2E4h] [rbp+214h]
  __int64 v258; // [rsp+2E8h] [rbp+218h]
  int v259; // [rsp+2F0h] [rbp+220h] BYREF
  __int64 v260; // [rsp+2F8h] [rbp+228h]
  __int64 v261; // [rsp+300h] [rbp+230h]
  __int64 v262; // [rsp+308h] [rbp+238h]
  __int64 v263; // [rsp+310h] [rbp+240h]
  bool v264; // [rsp+320h] [rbp+250h]
  __int128 v265; // [rsp+330h] [rbp+260h]
  __int128 v266; // [rsp+340h] [rbp+270h]
  void *v267; // [rsp+350h] [rbp+280h]
  __int64 v268; // [rsp+358h] [rbp+288h]
  struct IMemObj *v269; // [rsp+360h] [rbp+290h]
  __int128 v270; // [rsp+368h] [rbp+298h]
  _OWORD v271[8]; // [rsp+380h] [rbp+2B0h] BYREF
  __int16 v272; // [rsp+400h] [rbp+330h]
  _OWORD v273[8]; // [rsp+410h] [rbp+340h] BYREF
  __int16 v274; // [rsp+490h] [rbp+3C0h]
  _OWORD v275[8]; // [rsp+4A0h] [rbp+3D0h] BYREF
  __int16 v276; // [rsp+520h] [rbp+450h]
  _OWORD v277[8]; // [rsp+530h] [rbp+460h] BYREF
  __int16 v278; // [rsp+5B0h] [rbp+4E0h]
  _OWORD v279[10]; // [rsp+5C0h] [rbp+4F0h] BYREF
  char v280[32]; // [rsp+660h] [rbp+590h] BYREF
  __int128 v281; // [rsp+680h] [rbp+5B0h] BYREF
  __int128 v282; // [rsp+690h] [rbp+5C0h]
  __int128 v283; // [rsp+6A0h] [rbp+5D0h]
  __int128 v284; // [rsp+6B0h] [rbp+5E0h]
  __int128 v285; // [rsp+6C0h] [rbp+5F0h]
  __int128 v286; // [rsp+6D0h] [rbp+600h]
  __int128 v287; // [rsp+6E0h] [rbp+610h]
  __int128 v288; // [rsp+6F0h] [rbp+620h]
  __int16 v289; // [rsp+700h] [rbp+630h]
  char v290[4096]; // [rsp+710h] [rbp+640h] BYREF
  char Buffer[16]; // [rsp+1710h] [rbp+1640h] BYREF
  __int128 v292; // [rsp+1720h] [rbp+1650h]
  __int128 v293; // [rsp+1730h] [rbp+1660h]
  __int128 v294; // [rsp+1740h] [rbp+1670h]
  __int16 v295; // [rsp+1750h] [rbp+1680h]

  v268 = -2;
  v191 = a4;
  v221 = a3;
  v193 = a2;
  v23 = a1;
  v246 = a1;
  v24 = a5;
  v211 = a5;
  v250 = a7;
  v227 = a9;
  v231 = a11;
  lpWideCharStr = a13;
  v248 = a15;
  v247 = a19;
  v215 = a21;
  v251 = a22;
  v200 = 0;
  v194 = 0;
  v186 = 0;
  v192 = 0;
  v180 = CBulkImp::FIncreaseBufferCount((CBulkImp *)a3);
  BufferCount = CImpImportProvider::GetBufferCount((struct CBulkImp *)a3);
  v25 = 0x80000;
  v183 = 0x80000;
  v26 = *(_DWORD *)(a3 + 352);
  if ( v26 )
  {
    v25 = v26 << 10;
    v183 = v26 << 10;
  }
  v207 = v25;
  v27 = 0;
  v204 = 0;
  v233 = 0;
  *(_QWORD *)v189 = 0;
  *(_QWORD *)v190 = 0;
  v202 = 0;
  v182 = 0;
  *(_DWORD *)(v23 + 48) = 0;
  v223 = 0;
  Length = CRemoteFileRowsetMetadata::GetFileReadLength((CRemoteFileRowsetMetadata *)a3);
  RowsetColDefHead = CRemoteFileRowsetMetadata::GetRowsetColDefHead((CRemoteFileRowsetMetadata *)a3);
  v28 = *(_QWORD *)(a3 + 8);
  v235 = v28;
  v29 = CRemoteFileRowsetMetadata::UnfilteredResolvedFiles(a3);
  v230 = (_QWORD *)v29;
  ExternalDataSourceName = CRemoteFileRowsetMetadata::GetExternalDataSourceName((CRemoteFileRowsetMetadata *)a3);
  v217 = (unsigned __int64)(int)CRemoteFileRowsetMetadata::GetExternalDataSourceNameLength((CRemoteFileRowsetMetadata *)a3) >> 1;
  SecretValue = CBulkImp::GetSecretValue((CBulkImp *)a3);
  v210 = SecretValue;
  v214 = (unsigned __int64)(int)CBulkImp::GetSecretValueByteCount((CBulkImp *)a3) >> 1;
  ErrorFile = CRemoteFileRowsetMetadata::GetErrorFile((CRemoteFileRowsetMetadata *)a3);
  v241 = (unsigned __int64)(int)CRemoteFileRowsetMetadata::GetErrorFileByteCount((CRemoteFileRowsetMetadata *)a3) >> 1;
  ErrorFileDataSource = CBulkImp::GetErrorFileDataSource((CBulkImp *)a3);
  v239 = (unsigned __int64)(int)CBulkImp::GetErrorFileDataSourceByteCount((CBulkImp *)a3) >> 1;
  Source = CBulkImp::GetFormatFile((CBulkImp *)a3);
  v229 = (unsigned __int64)(int)CBulkImp::GetFormatFileByteCount((CBulkImp *)a3) >> 1;
  FormatFileDataSource = CBulkImp::GetFormatFileDataSource((CBulkImp *)a3);
  v243 = (unsigned __int64)(int)CBulkImp::GetFormatFileDataSourceByteCount((CBulkImp *)a3) >> 1;
  v177 = *(_WORD *)(a3 + 276);
  ErrorFileSecret = CRemoteFileRowsetMetadata::GetErrorFileSecret((CRemoteFileRowsetMetadata *)a3);
  v237 = (unsigned __int64)(int)CRemoteFileRowsetMetadata::GetErrorFileSecretByteCount((CRemoteFileRowsetMetadata *)a3) >> 1;
  Compression = CRemoteFileRowsetMetadata::GetCompression((CRemoteFileRowsetMetadata *)a3);
  v212 = (unsigned __int64)(int)CRemoteFileRowsetMetadata::GetCompressionByteCount((CRemoteFileRowsetMetadata *)a3) >> 1;
  v184 = *(_BYTE *)(a3 + 24);
  IsBatchExtractorFramework = CRemoteFileRowsetMetadata::IsBatchExtractorFramework((CRemoteFileRowsetMetadata *)a3);
  RowsetFilesInfo = CRemoteFileRowsetMetadata::GetRowsetFilesInfo((CRemoteFileRowsetMetadata *)a3);
  if ( !CRemoteFileRowsetMetadata::GetRowsetOptions((CRemoteFileRowsetMetadata *)v221)
    || (v32 = *((_BYTE *)CRemoteFileRowsetMetadata::GetRowsetOptions((CRemoteFileRowsetMetadata *)v221) + 16) == 0,
        v178 = 1,
        v32) )
  {
    v178 = 0;
  }
  v33 = v215;
  if ( byte_10316E9CB )
    v33 = 0;
  v215 = v33;
  if ( !SecretValue )
  {
    if ( RowsetFilesInfo )
    {
      if ( *((_DWORD *)RowsetFilesInfo + 13) == 3 )
      {
        if ( v29 )
        {
          v34 = *(_DWORD *)(v29 + 12);
          if ( v34 )
          {
            v35 = *(_QWORD *)(*(_QWORD *)(v29 + 24) + 8LL * (unsigned int)(v34 - 1));
            v210 = (wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 184LL))(v35);
            v214 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 192LL))(v35);
          }
        }
      }
    }
  }
  v36 = 0;
  v197 = 0;
  v37 = 1;
  if ( v28 )
  {
    v36 = *(_DWORD *)(v28 + 12);
    v197 = v36;
    v37 = *(_DWORD *)(*(_QWORD *)(v28 + 24) + 8LL) < 2u;
  }
  else if ( v29 )
  {
    v38 = 0;
    if ( *(_DWORD *)(v29 + 12) )
    {
      do
      {
        v39 = *(_QWORD *)(*(_QWORD *)(v29 + 24) + 8LL * v38);
        v36 += (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
        ++v38;
      }
      while ( v38 < *(_DWORD *)(v29 + 12) );
      v197 = v36;
    }
    v37 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(v29 + 24) + 168LL))(**(_QWORD **)(v29 + 24)) == 0;
  }
  v40 = v193;
  v279[0] = *(_OWORD *)v193;
  v279[1] = *((_OWORD *)v193 + 1);
  v279[2] = *((_OWORD *)v193 + 2);
  v279[3] = *((_OWORD *)v193 + 3);
  v279[4] = *((_OWORD *)v193 + 4);
  v279[5] = *((_OWORD *)v193 + 5);
  v279[6] = *((_OWORD *)v193 + 6);
  v279[7] = *((_OWORD *)v193 + 7);
  v279[8] = *((_OWORD *)v193 + 8);
  Destination = CImpImportProvider::FShouldOpenFileInGetRowset(v23, v279, a20, v180, v37, &v182);
  if ( *(_DWORD *)(v23 + 24) != 1 )
    goto LABEL_306;
  *(_DWORD *)(v23 + 24) = 4;
  v41 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v42 = *(_QWORD *)(v41 + 256);
  if ( !v42 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v42 = *(_QWORD *)(v41 + 256);
  }
  *(_QWORD *)(v23 + 40) = operator new[](
                            v191,
                            *(struct IMemObj **)(v42 + 1000),
                            "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp",
                            650,
                            5u);
  v43 = *((_DWORD *)v40 + 11);
  if ( v43 )
  {
    if ( v43 != 1 )
      goto LABEL_31;
    if ( (unsigned int)IsVDWBackendInstance() )
    {
      v43 = 65001;
      goto LABEL_31;
    }
    OEMCP = GetOEMCP();
  }
  else
  {
    OEMCP = GetACP();
  }
  v43 = OEMCP;
LABEL_31:
  *(_DWORD *)(v23 + 52) = v43;
  v45 = *((_DWORD *)v40 + 12);
  if ( !v45 )
  {
    ACP = GetACP();
    goto LABEL_37;
  }
  if ( v45 == 1 )
  {
    if ( (unsigned int)IsVDWBackendInstance() )
    {
      v45 = 65001;
      goto LABEL_38;
    }
    ACP = GetOEMCP();
LABEL_37:
    v45 = ACP;
  }
LABEL_38:
  *(_DWORD *)(v23 + 60) = v45;
  *(_DWORD *)(v23 + 64) = *((_DWORD *)v40 + 13);
  *(_BYTE *)(v23 + 68) = *((_BYTE *)v40 + 56);
  *(_BYTE *)(v23 + 69) = *((_BYTE *)v40 + 40);
  if ( *(_DWORD *)(v23 + 64) || *(_BYTE *)(v23 + 68) )
  {
    v48 = CIDFromTDSCollation((const struct TDSCOLLATION *)(v23 + 64));
    v47 = UICodePageFromCID(v48);
  }
  else
  {
    v47 = 99999;
  }
  *(_DWORD *)(v23 + 56) = v47;
  *(_WORD *)(v23 + 74) = *((_WORD *)v40 + 44);
  *(_WORD *)(v23 + 70) = *((_WORD *)v40 + 45);
  *(_WORD *)(v23 + 72) = *((_WORD *)v40 + 46);
  *(_WORD *)(v23 + 76) = *((_WORD *)v40 + 47);
  if ( *((_DWORD *)v40 + 24) )
  {
    *(_WORD *)(v23 + 78) = 128;
  }
  else if ( *((_DWORD *)v40 + 25) )
  {
    *(_WORD *)(v23 + 78) = 129;
  }
  else if ( *((_DWORD *)v40 + 26) )
  {
    *(_WORD *)(v23 + 78) = 130;
  }
  v49 = a17;
  if ( !a17 || (v181 = 1, !Length) )
    v181 = 0;
  if ( *((_DWORD *)v40 + 16) != 6 )
  {
    if ( Destination )
    {
      v195 = 719;
      v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v71 = *(_QWORD *)(v70 + 256);
      if ( !v71 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v71 = *(_QWORD *)(v70 + 256);
      }
      v72 = *(struct IMemObj **)(v71 + 1000);
      v225 = v72;
      v73 = 8LL * v36;
      if ( !is_mul_ok(v36, 8u) )
        v73 = -1;
      v74 = __CFADD__(v73, 8);
      v75 = v73 + 8;
      if ( v74 )
        v75 = -1;
      v76 = operator new[](v75, v72, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp", 719, 5u);
      v224 = v76;
      if ( v76 )
      {
        *v76 = v36;
        v77 = v76 + 1;
        v203 = v76 + 1;
        `eh vector constructor iterator'(
          v76 + 1,
          8u,
          v36,
          CAutoRefc<ToadFuture>::CAutoRefc<ToadFuture>,
          CAutoRefc<FidoUnionSchema>::~CAutoRefc<FidoUnionSchema>);
      }
      else
      {
        v77 = 0;
        v203 = 0;
      }
      v223 = v77;
      v78 = 0;
      v225 = 0;
      v79 = 0;
      v198 = 0;
      v80 = 0;
      v179 = 0;
      v81 = 0;
      v220 = 0;
      v82 = 0;
      v195 = 0;
      if ( v36 )
      {
        _mm_lfence();
        v83 = 0;
        v224 = 0;
        v84 = 0;
        while ( 1 )
        {
          v85 = 0;
          v86 = 0;
          v87 = 0;
          if ( v235 )
          {
            if ( v82 >= *(_DWORD *)(v235 + 12) )
            {
              v270 = 0;
              v266 = 0;
              v88 = 0;
            }
            else
            {
              v270 = *(_OWORD *)((char *)v83 + *(_QWORD *)(v235 + 24));
              v85 = (void *)v270;
              v266 = v270;
              v88 = v270;
            }
            v86 = DWORD2(v266) >> 1;
            CImpImportProvider::GetCodecType(v88, DWORD2(v266) >> 1, Compression, v212);
            goto LABEL_123;
          }
          if ( v78 )
          {
            if ( !v80 )
            {
              v89 = v81;
LABEL_116:
              if ( v89 )
                goto LABEL_118;
              goto LABEL_117;
            }
            if ( v84 )
            {
              v89 = *(_QWORD **)(v84 + 16);
              goto LABEL_116;
            }
          }
LABEL_117:
          v225 = *(struct IMemObj **)(v230[3] + 8LL * v79);
          v90 = (*(__int64 (__fastcall **)(struct IMemObj *, char *))(*(_QWORD *)v225 + 16LL))(v225, v280);
          v80 = *(_BYTE *)v90;
          v179 = *(_BYTE *)v90;
          v84 = *(_QWORD *)(v90 + 8);
          v81 = *(_QWORD **)(v90 + 16);
          v220 = v81;
          ++v198;
LABEL_118:
          if ( v80 )
          {
            if ( v84 )
            {
              v87 = *(_QWORD **)(v84 + 16);
              CImpImportProvider::GetCodecType(v87[2], v87[3], Compression, v212);
              v84 = *(_QWORD *)(v84 + 8);
            }
            else
            {
              v87 = 0;
              CImpImportProvider::GetCodecType(MEMORY[0x10], MEMORY[0x18], Compression, v212);
              v84 = MEMORY[8];
            }
          }
          else
          {
            v87 = v81;
            CImpImportProvider::GetCodecType(v81[2], v81[3], Compression, v212);
            v220 = (_QWORD *)v81[1];
          }
LABEL_123:
          v219 = 0;
          if ( IsBdcStoragePoolCacheEnabled() )
          {
            v206 = v91;
            v92 = BDCCachePathUtil::TransformBulkPathToBdcSbsCacheUrl(
                    *(unsigned __int16 *)(v23 + 76),
                    (_DWORD)v85,
                    v86,
                    (_DWORD)ExternalDataSourceName,
                    v217,
                    (__int64)v210,
                    v214,
                    (__int64)&v219,
                    (__int64)&v206);
            if ( v92 )
            {
              OSErrString = GetOSErrString(v92, (struct ErrorStringHolder *)v290, 0, 0);
              ex_raise(48, 61, 16, 6, v85, OSErrString);
            }
            v85 = v219;
            v86 = v206;
          }
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          if ( v87 )
          {
            v234 = 795;
            v95 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v96 = *(_QWORD *)(v95 + 256);
            if ( !v96 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v96 = *(_QWORD *)(v95 + 256);
            }
            v269 = *(struct IMemObj **)(v96 + 1000);
            v97 = operator new(0x60u, v269, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp", 795, 5u);
            v267 = v97;
            if ( v97 )
            {
              Locale = (int)v210;
              v98 = CDiskDev::CDiskDev(v97, v87, ExternalDataSourceName, (unsigned int)v217);
            }
            else
            {
              v98 = 0;
            }
          }
          else
          {
            v216 = 808;
            v99 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
            v100 = *(_QWORD *)(v99 + 256);
            if ( !v100 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v100 = *(_QWORD *)(v99 + 256);
            }
            v252 = *(struct IMemObj **)(v100 + 1000);
            v101 = (struct IMemObj *)operator new(
                                       0x60u,
                                       v252,
                                       "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp",
                                       808,
                                       5u);
            v253 = v101;
            if ( v101 )
            {
              Locale = v217;
              v98 = CDiskDev::CDiskDev(v101, v85, v86, ExternalDataSourceName);
            }
            else
            {
              v98 = 0;
            }
          }
          v102 = v203;
          v103 = *v203;
          if ( *v203 && _InterlockedExchangeAdd((volatile signed __int32 *)(v103 + 8), 0xFFFFFFFF) == 1 && v103 != -8 )
            (**(void (__fastcall ***)(__int64, __int64))v103)(v103, 1);
          *v102 = v98;
          ++*(_DWORD *)(v23 + 48);
          operator delete[](v219);
          v82 = v195 + 1;
          v195 = v82;
          v83 = v224 + 2;
          v224 += 2;
          v203 = v102 + 1;
          v81 = v220;
          v80 = v179;
          v78 = v225;
          v79 = v198;
          if ( v82 >= v197 )
          {
            v24 = v211;
            break;
          }
        }
      }
      v204 = 0;
      v49 = a17;
    }
    v69 = BufferCount;
    goto LABEL_146;
  }
  v183 = v25;
  if ( *(_DWORD *)(v28 + 12) )
  {
    v265 = *(_OWORD *)*(_QWORD *)(v28 + 24);
    v50 = (const void *)v265;
  }
  else
  {
    v265 = 0;
    v50 = 0;
  }
  if ( DWORD2(v265) < 2uLL || !v50 )
  {
LABEL_306:
    v111 = -2147467259;
    goto LABEL_307;
  }
  v281 = 0;
  v282 = 0;
  v283 = 0;
  v284 = 0;
  v285 = 0;
  v286 = 0;
  v287 = 0;
  v288 = 0;
  v289 = 0;
  v51 = DWORD2(v265) & 0xFFFFFFFE;
  if ( v51 > 0x82 )
  {
    v51 = 130;
LABEL_60:
    memmove(&v281, v50, v51);
    goto LABEL_61;
  }
  if ( (DWORD2(v265) & 0xFFFFFFFE) != 0 )
    goto LABEL_60;
LABEL_61:
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v254, 1);
  v211 = (struct IMemObj *)&v256;
  v259 = 536871408;
  v260 = 0;
  v262 = 0;
  v261 = 0;
  v263 = 0;
  v264 = 0;
  v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v53 = *(_QWORD *)(v52 + 256);
  if ( !v53 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v53 = *(_QWORD *)(v52 + 256);
  }
  v54 = *(_QWORD *)(v53 + 600);
  if ( v54 )
    v264 = (unsigned int)SOS_Task::PushWait(v54, &v259) == 0;
  v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v56 = *(_QWORD *)(v55 + 256);
  if ( !v56 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v56 = *(_QWORD *)(v55 + 256);
  }
  v258 = v56;
  v257 = (*(_DWORD *)(v56 + 800) >> 11) & 1;
  if ( v257 || (*(_BYTE *)(v56 + 800) & 4) == 0 )
  {
    v256 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v56 + 608) + 8LL))(*(_QWORD *)(v56 + 608));
  }
  else
  {
    v256 = 0;
  }
  v57 = *(_BYTE **)(SystemThread_TlsOffset
                  + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
  v205 = !dword_103172554
      && !*v57
      && intnl_impersonate_client(*(struct CSession **)(*(_QWORD *)(SystemThread_TlsOffset
                                                                  + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex))
                                                      + 72LL)) == 1;
  BufferCount = 707;
  v58 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v59 = *(_QWORD *)(v58 + 256);
  if ( !v59 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v59 = *(_QWORD *)(v58 + 256);
  }
  v211 = *(struct IMemObj **)(v59 + 1000);
  v60 = (HANDLE *)operator new(0x28u, v211, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp", 707, 5u);
  v61 = v60;
  v230 = v60;
  if ( v60 )
  {
    *v60 = (HANDLE)-1LL;
    v60[1] = (HANDLE)-1LL;
    v60[2] = (HANDLE)-1LL;
    v60[3] = 0;
    *((_DWORD *)v60 + 8) = 0;
    *(_OWORD *)Buffer = 0;
    v292 = 0;
    v293 = 0;
    v294 = 0;
    v295 = 0;
    DefaultLocale = GetDefaultLocale();
    snprintf_s_l(Buffer, 0x42u, 0x41u, "%-64.64S", DefaultLocale, &v281);
    v63 = OpenFileMappingA(0xF001Fu, 0, Buffer);
    *v61 = v63;
    if ( !v63 )
    {
      CDTSqlT<1048576>::Release(v61);
      v271[0] = v281;
      v271[1] = v282;
      v271[2] = v283;
      v271[3] = v284;
      v271[4] = v285;
      v271[5] = v286;
      v271[6] = v287;
      v271[7] = v288;
      v272 = v289;
      FATAL(v271);
    }
    v64 = MapViewOfFile(*v61, 2u, 0, 0, 0x100000u);
    v61[3] = v64;
    if ( !v64 )
    {
      CDTSqlT<1048576>::Release(v61);
      v273[0] = v281;
      v273[1] = v282;
      v273[2] = v283;
      v273[3] = v284;
      v273[4] = v285;
      v273[5] = v286;
      v273[6] = v287;
      v273[7] = v288;
      v274 = v289;
      FATAL(v273);
    }
    v65 = GetDefaultLocale();
    snprintf_s_l(Buffer, 0x42u, 0x41u, "%-64.64SG", v65, &v281);
    v66 = OpenEventA(0x1F0003u, 0, Buffer);
    v61[2] = v66;
    if ( !v66 )
    {
      CDTSqlT<1048576>::Release(v61);
      v275[0] = v281;
      v275[1] = v282;
      v275[2] = v283;
      v275[3] = v284;
      v275[4] = v285;
      v275[5] = v286;
      v275[6] = v287;
      v275[7] = v288;
      v276 = v289;
      FATAL(v275);
    }
    v67 = GetDefaultLocale();
    snprintf_s_l(Buffer, 0x42u, 0x41u, "%-64.64SP", v67);
    v68 = OpenEventA(0x1F0003u, 0, Buffer);
    v61[1] = v68;
    if ( !v68 )
    {
      CDTSqlT<1048576>::Release(v61);
      v277[0] = v281;
      v277[1] = v282;
      v277[2] = v283;
      v277[3] = v284;
      v277[4] = v285;
      v277[5] = v286;
      v277[6] = v287;
      v277[7] = v288;
      v278 = v289;
      FATAL(v277);
    }
  }
  else
  {
    v61 = 0;
  }
  v204 = v61;
  *((_DWORD *)v61[3] + 6) = 1;
  v69 = 0;
  if ( v205 )
    intnl_revert_to_self(
      *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset)
                          + 72LL),
      1);
  v211 = (struct IMemObj *)&v256;
  if ( v256 )
  {
    if ( v257 )
      *(_DWORD *)(v258 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v258 + 608) + 16LL))(
        *(_QWORD *)(v258 + 608),
        v258,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v259);
  *(_DWORD *)(v255 + 616) &= ~v254;
  v49 = a17;
LABEL_146:
  CAutoImportStream::CAutoImportStream((CAutoImportStream *)&v201, (struct CImpImportProvider *)v23);
  v104 = 0;
  if ( Destination && Length )
  {
    v104 = v49 + Length;
    v105 = v49 - DestinationSize;
    if ( v49 < DestinationSize )
      v105 = 0;
  }
  else
  {
    v105 = v49;
  }
  v106 = (CRemoteFileRowsetMetadata *)v221;
  if ( CRemoteFileRowsetMetadata::GetBulkImpTableSampleData((CRemoteFileRowsetMetadata *)v221)
    && *(_DWORD *)CRemoteFileRowsetMetadata::GetBulkImpTableSampleData(v106) == 1 )
  {
    v27 = *((_QWORD *)CRemoteFileRowsetMetadata::GetBulkImpTableSampleData(v106) + 3);
  }
  v107 = v201;
  v108 = Destination;
  if ( Destination )
  {
    v109 = (__int64)v204;
    v204 = 0;
    v174 = v106;
    v110 = v193;
    v111 = CImportStream::Init(
             v201,
             (__int64 *)v223,
             *(_DWORD *)(v23 + 48),
             v109,
             v69,
             v183,
             v207,
             a17,
             v105,
             v104,
             v27,
             *((_DWORD *)v193 + 21),
             v184,
             v180,
             v241,
             ErrorFile,
             v239,
             ErrorFileDataSource,
             v237,
             ErrorFileSecret,
             *((_DWORD *)v193 + 17),
             v215,
             v174);
    v186 = v111;
    if ( v111 < 0 )
      goto LABEL_304;
    v108 = Destination;
  }
  else
  {
    v110 = v193;
  }
  v112 = 0;
  v199 = 0;
  if ( !v229 )
  {
    if ( v177 )
    {
      v186 = OpenrowsetColDefLst_readfmt(
               (unsigned int)v190,
               (unsigned int)v189,
               (_DWORD)v24,
               v191,
               Locale,
               (__int64)RowsetColDefHead,
               *((_DWORD *)v110 + 16),
               *((_DWORD *)v110 + 12),
               a20);
      v191 = *(_QWORD *)v189;
      if ( Destination && (unsigned int)CImportStream::SwitchBuffer((__int64)v107, *((_DWORD *)v110 + 16), &v192) )
      {
        v111 = -2147467259;
        goto LABEL_304;
      }
      goto LABEL_255;
    }
    if ( v108 && (unsigned int)CImportStream::SwitchBuffer((__int64)v107, *((_DWORD *)v110 + 16), &v192) )
    {
      v111 = -2147467259;
      goto LABEL_304;
    }
    if ( *((_DWORD *)v110 + 16) == 6 )
    {
      v132 = v191;
      v111 = DTS_readfmt(v191, (_DWORD)v24, (unsigned int)v189, (unsigned int)v190, (__int64)&v202, (__int64)v107, v23);
      v186 = v111;
      if ( v111 < 0 )
        goto LABEL_304;
      _mm_lfence();
      v133 = 0;
      if ( v132 )
      {
        v134 = 0;
        do
        {
          if ( !*((_BYTE *)v24 + 384 * v134 + 83) || v132 == 1 )
          {
            v135 = 0;
            if ( *(_QWORD *)v189 )
            {
              v136 = (_QWORD *)(*(_QWORD *)v190 + 8LL);
              while ( v133 + 1 != *v136 )
              {
                ++v135;
                v136 += 48;
                if ( v135 >= *(_QWORD *)v189 )
                  goto LABEL_215;
              }
              v137 = 1;
            }
            else
            {
LABEL_215:
              v137 = 0;
            }
            *(_BYTE *)(v134 + *(_QWORD *)(v23 + 40)) = v137;
          }
          else
          {
            *(_BYTE *)(v134 + *(_QWORD *)(v23 + 40)) = 0;
          }
          v134 = ++v133;
        }
        while ( v133 < v132 );
      }
      v191 = *(_QWORD *)v189;
      v200 = 1;
      goto LABEL_255;
    }
    if ( *(_WORD *)(v23 + 78) != 1 )
    {
      v111 = SingleCol_readfmt(v190, &v202, v23);
      v186 = v111;
      if ( v111 < 0 )
        goto LABEL_304;
      v191 = 1;
      v194 = 1;
      goto LABEL_255;
    }
    v138 = v191;
    if ( !v191 )
    {
      v110 = v193;
      goto LABEL_255;
    }
    v139 = 0;
    v140 = v193;
    while ( 1 )
    {
      if ( (v141 = 384 * v139,
            *((_QWORD *)v24 + 48 * v139 + 2) = *((_QWORD *)v24 + 48 * v139 + 1),
            *((_BYTE *)v24 + 384 * v139 + 83))
        && v138 != 1
        || *(_WORD *)((char *)v24 + v141 + 70) )
      {
        *(_BYTE *)(*(_QWORD *)(v23 + 40) + v139) = 0;
        *(_QWORD *)((char *)v24 + v141 + 8) = 0;
      }
      else
      {
        *(_BYTE *)(v139 + *(_QWORD *)(v23 + 40)) = 1;
      }
      *(_DWORD *)((char *)v24 + v141 + 112) = *(_DWORD *)(v23 + 60);
      if ( (unsigned __int16)(*(_WORD *)((char *)v24 + v141 + 68) - 129) <= 1u
        || *(_DWORD *)((char *)v24 + v141 + 76) == 1 )
      {
        break;
      }
      if ( *(_WORD *)((char *)v24 + v141 + 68) == DbtFromXvt(0x62u) )
      {
        v142 = (struct tagIMPORT_COLINFO *)((char *)v24 + v141 + 104);
        *(_DWORD *)v142 = *(_DWORD *)(v23 + 64);
        v143 = *(_BYTE *)(v23 + 68);
        *((_BYTE *)v142 + 4) = v143;
        if ( !*(_DWORD *)v142 && !v143 )
        {
          v144 = 99999;
LABEL_240:
          *(_DWORD *)((char *)v24 + v141 + 116) = v144;
          goto LABEL_241;
        }
        goto LABEL_239;
      }
LABEL_241:
      switch ( *((_DWORD *)v140 + 16) )
      {
        case 0:
          v146 = 384 * v139;
          v147 = 129;
          goto LABEL_246;
        case 1:
        case 4:
        case 7:
        case 8:
          v146 = 384 * v139;
          v147 = 130;
          goto LABEL_246;
        case 2:
          v146 = 384 * v139;
          goto LABEL_245;
        case 3:
          v146 = 384 * v139;
          if ( *((_WORD *)v24 + 192 * v139 + 34) == 129 )
            v147 = 130;
          else
LABEL_245:
            v147 = 128;
LABEL_246:
          *(_WORD *)((char *)v24 + v146 + 70) = v147;
          break;
        default:
          break;
      }
      v139 = ++v112;
      if ( v112 >= v138 )
      {
        v110 = v140;
        goto LABEL_255;
      }
    }
    v142 = (struct tagIMPORT_COLINFO *)((char *)v24 + v141 + 104);
    if ( !*(_DWORD *)v142 && !*((_BYTE *)v142 + 4) )
    {
      v144 = 99999;
      goto LABEL_240;
    }
LABEL_239:
    v145 = CIDFromTDSCollation(v142);
    v144 = UICodePageFromCID(v145);
    goto LABEL_240;
  }
  v113 = 2 * v229;
  v114 = 2 * v229 + 2;
  v115 = 2 * v229 + 17;
  if ( v115 <= v114 )
    v115 = 0xFFFFFFFFFFFFFF0LL;
  v116 = alloca(v115 & 0xFFFFFFFFFFFFFFF0uLL);
  memcpy_s(&Destination, v114, Source, v113);
  *(_WORD *)(&Destination + v113) = 0;
  v117 = 0;
  v222 = 0;
  v118 = v243;
  if ( v243 )
  {
    v119 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v120 = *(_QWORD *)(v119 + 256);
    if ( !v120 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v120 = *(_QWORD *)(v119 + 256);
    }
    v121 = 2 * (v118 + 1);
    if ( !is_mul_ok(v118 + 1, 2u) )
      v121 = -1;
    v117 = (WCHAR *)operator new[](
                      v121,
                      *(struct IMemObj **)(v120 + 1000),
                      "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp",
                      910,
                      5u);
    if ( v117 )
      operator delete[](0);
    v222 = v117;
    memcpy_s(v117, 2 * v118 + 2, FormatFileDataSource, 2 * v118);
    v117[v118] = 0;
    v107 = v201;
  }
  v122 = v191;
  v111 = BCP_readfmt(
           v191,
           (int)v24,
           (int)v189,
           (int)v190,
           (__int64)&v202,
           (__int64)&v199,
           (__int64)v110,
           (wchar_t *)&Destination,
           v229,
           v117,
           v118,
           v23);
  v186 = v111;
  if ( v111 < 0 )
    goto LABEL_303;
  _mm_lfence();
  v123 = 0;
  v124 = *(_QWORD *)v189;
  if ( v122 )
  {
    v125 = 0;
    while ( *((_BYTE *)v24 + 384 * v125 + 83) && v122 != 1 )
    {
      *(_BYTE *)(v125 + *(_QWORD *)(v23 + 40)) = 0;
      *((_QWORD *)v24 + 48 * v125 + 1) = 0;
      v126 = 0;
      v124 = *(_QWORD *)v189;
      if ( *(_QWORD *)v189 )
      {
        v127 = (_QWORD *)(*(_QWORD *)v190 + 8LL);
        while ( v125 != *v127 - 1LL )
        {
          ++v126;
          v127 += 48;
          if ( v126 >= *(_QWORD *)v189 )
            goto LABEL_188;
        }
        *(_QWORD *)(*(_QWORD *)v190 + 384 * v126 + 8) = 0;
LABEL_187:
        v124 = *(_QWORD *)v189;
      }
LABEL_188:
      v125 = ++v123;
      if ( v123 >= v122 )
        goto LABEL_189;
    }
    v128 = 0;
    if ( v124 )
    {
      v129 = (_QWORD *)(*(_QWORD *)v190 + 8LL);
      while ( v123 + 1 != *v129 )
      {
        ++v128;
        v129 += 48;
        if ( v128 >= v124 )
          goto LABEL_185;
      }
      v130 = 1;
    }
    else
    {
LABEL_185:
      v130 = 0;
    }
    *(_BYTE *)(*(_QWORD *)(v23 + 40) + v125) = v130;
    goto LABEL_187;
  }
LABEL_189:
  v191 = v124;
  v200 = 1;
  if ( Destination )
  {
    if ( v199 )
    {
      v131 = 1;
    }
    else if ( *(_DWORD *)(v23 + 60) == 65001 )
    {
      v131 = 0;
    }
    else
    {
      _mm_lfence();
      v131 = *((_DWORD *)v110 + 16);
    }
    v107 = v201;
    if ( (unsigned int)CImportStream::SwitchBuffer((__int64)v201, v131, &v192) )
    {
      v111 = -2147467259;
      v117 = v222;
      goto LABEL_303;
    }
  }
  _mm_lfence();
  operator delete[](v222);
LABEL_255:
  v148 = *((_DWORD *)v110 + 16);
  if ( v148 && (v148 != 5 || v199) )
  {
    v149 = 0;
    v150 = *((_DWORD *)v110 + 11);
  }
  else
  {
    if ( *((_DWORD *)v110 + 12) == 65001 )
    {
      v150 = 65001;
      v151 = DOUBLE_1_5;
      v149 = 1;
      goto LABEL_260;
    }
    v150 = *((_DWORD *)v110 + 11);
    v149 = 1;
    if ( v150 == 65001 )
    {
      v151 = DOUBLE_1_5;
      goto LABEL_260;
    }
  }
  v151 = DOUBLE_1_0;
LABEL_260:
  v188 = 0;
  v226 = 0;
  if ( !v227 )
    goto LABEL_276;
  if ( a8 < 0 )
    v152 = (double)(int)(a8 & 1 | ((unsigned __int64)a8 >> 1)) + (double)(int)(a8 & 1 | ((unsigned __int64)a8 >> 1));
  else
    v152 = (double)(int)a8;
  v153 = (int)(v152 * v151);
  v188 = v153 + 2;
  v154 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v155 = *(_QWORD *)(v154 + 256);
  if ( !v155 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v155 = *(_QWORD *)(v154 + 256);
  }
  v117 = (WCHAR *)operator new[](
                    v188,
                    *(struct IMemObj **)(v155 + 1000),
                    "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp",
                    1151,
                    5u);
  if ( v117 )
    operator delete[](0);
  v226 = v117;
  v208 = 0;
  NormalizeTerminator(v150, v149, v227, (unsigned int)a8 >> 1, (unsigned __int8 *)v117, &v188, &v208, v177);
  if ( v188 > v153 )
    utassert_fail(1u, "cbNormFieldQuote <= (DWORD)(cbFieldQuote * sizeAdjustment)", "ImpImpl.cpp", 1165, 0);
  if ( v208 <= 1 )
  {
LABEL_276:
    v187 = 0;
    v232 = 0;
    if ( v231 )
    {
      if ( a10 < 0 )
        v156 = (double)(int)(a10 & 1 | ((unsigned __int64)a10 >> 1))
             + (double)(int)(a10 & 1 | ((unsigned __int64)a10 >> 1));
      else
        v156 = (double)(int)a10;
      v157 = (int)(v156 * v151);
      v187 = v157 + 2;
      v158 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v159 = *(_QWORD *)(v158 + 256);
      if ( !v159 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v159 = *(_QWORD *)(v158 + 256);
      }
      v160 = (WCHAR *)operator new[](
                        v187,
                        *(struct IMemObj **)(v159 + 1000),
                        "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp",
                        1182,
                        5u);
      if ( v160 )
        operator delete[](0);
      v232 = v160;
      v209 = 0;
      NormalizeTerminator(v150, v149, v231, (unsigned int)a10 >> 1, (unsigned __int8 *)v160, &v187, &v209, v177);
      if ( v187 > v157 )
        utassert_fail(1u, "cbNormEscapeChar <= (DWORD)(cbEscapeChar * sizeAdjustment)", "ImpImpl.cpp", 1196, 0);
      if ( v209 > 1 )
      {
        ex_raise(138, 4, 16, 1);
        v111 = 13;
        v107 = v201;
        v117 = (WCHAR *)v226;
LABEL_302:
        operator delete[](v160);
        goto LABEL_303;
      }
      v23 = v246;
    }
    v161 = v193;
    if ( Destination )
    {
      v162 = v181;
    }
    else
    {
      *((_QWORD *)v193 + 2) = 0;
      v162 = 0;
    }
    v216 = 1217;
    v163 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v164 = *(_QWORD *)(v163 + 256);
    if ( !v164 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v164 = *(_QWORD *)(v163 + 256);
    }
    v253 = *(struct IMemObj **)(v164 + 1000);
    v165 = (char *)operator new(0xF8u, v253, "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\impimpl.cpp", 1217, 5u);
    v166 = (CImportRowset *)v165;
    v252 = (struct IMemObj *)v165;
    if ( v165 )
    {
      *(_QWORD *)v165 = &CImportRowset::`vftable';
      *((_QWORD *)v165 + 1) = 0;
      *((_DWORD *)v165 + 4) = 0;
      *((_QWORD *)v165 + 3) = 0;
      *((_QWORD *)v165 + 4) = 0;
      *((_QWORD *)v165 + 5) = 0;
      *((_QWORD *)v165 + 6) = 0;
      *((_QWORD *)v165 + 7) = 0;
      *((_QWORD *)v165 + 8) = 0;
      *((_QWORD *)v165 + 9) = 0;
      *((_QWORD *)v165 + 10) = 0;
      *((_QWORD *)v165 + 12) = v23;
      *((_QWORD *)v165 + 13) = 0;
      *((_QWORD *)v165 + 14) = 0;
      *((_QWORD *)v165 + 15) = 0;
      *((_QWORD *)v165 + 16) = 0;
      *((_DWORD *)v165 + 34) = 0;
      v165[141] = 0;
      *((_DWORD *)v165 + 36) = *(_DWORD *)(v23 + 24) != 4;
      *(_QWORD *)(v165 + 148) = 0;
      *((_DWORD *)v165 + 39) = 99999;
      *((_QWORD *)v165 + 21) = 0;
      *((_QWORD *)v165 + 22) = 0;
      *((_QWORD *)v165 + 23) = 0;
      *((_DWORD *)v165 + 48) = 0;
      *((_WORD *)v165 + 98) = 0;
      *((_QWORD *)v165 + 25) = 0;
      *((_QWORD *)v165 + 26) = 0;
      *((_QWORD *)v165 + 28) = 0;
      *((_QWORD *)v165 + 29) = 0;
      *((_QWORD *)v165 + 30) = 0;
      *((_QWORD *)v165 + 4) = 0;
      *((_QWORD *)v165 + 5) = 0;
      *((_QWORD *)v165 + 6) = 0;
      *((_QWORD *)v165 + 7) = 0;
      *((_QWORD *)v165 + 8) = 0;
      *((_QWORD *)v165 + 9) = 0;
      *((_QWORD *)v165 + 10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    }
    else
    {
      v166 = 0;
    }
    v233 = v166;
    if ( v200 || v194 || v177 )
    {
      v24 = *(struct tagIMPORT_COLINFO **)v190;
      *(_QWORD *)v190 = 0;
    }
    v167 = v202;
    v202 = 0;
    v168 = v201;
    v107 = 0;
    v201 = 0;
    v175 = v162;
    v160 = (WCHAR *)v232;
    v117 = (WCHAR *)v226;
    CImportRowset::Init(
      v166,
      v168,
      v161,
      v191,
      v24,
      a6,
      v250,
      cchWideChar,
      lpWideCharStr,
      DestinationSize,
      v248,
      v188,
      v226,
      v187,
      v232,
      v247,
      v167,
      v200,
      a18,
      v192,
      v194,
      (unsigned __int8)v177,
      v175,
      v182,
      SHIBYTE(v177),
      IsBatchExtractorFramework);
    (**(void (__fastcall ***)(CImportRowset *, GUID *, __int64))v166)(v166, &IID_IRowset, v251);
    v233 = 0;
    v111 = v186;
    goto LABEL_302;
  }
  ex_raise(48, 78, 16, 1);
  v111 = 13;
  v107 = v201;
LABEL_303:
  operator delete[](v117);
LABEL_304:
  if ( v107 )
  {
    CImportStream::~CImportStream(v107);
    operator delete(v107, 0xFC0u);
  }
LABEL_307:
  if ( v223 )
  {
    v169 = (char *)v223 - 8;
    `eh vector destructor iterator'(
      v223,
      8u,
      *((_QWORD *)v223 - 1),
      CAutoRefc<FidoUnionSchema>::~CAutoRefc<FidoUnionSchema>);
    operator delete[](v169, 8LL * *v169 + 8);
  }
  if ( v202 )
  {
    v170 = (_QWORD *)((char *)v202 - 8);
    `eh vector destructor iterator'(
      v202,
      0x10u,
      *((_QWORD *)v202 - 1),
      (void (*)(void *))DELIMITER_INFO::~DELIMITER_INFO);
    operator delete[](v170, 16LL * *v170 + 8);
  }
  operator delete[](*(void **)v190);
  v171 = v204;
  if ( v204 )
  {
    CDTSqlT<1048576>::Release(v204);
    operator delete(v171, 0x28u);
  }
  return (unsigned int)v111;
}

```

## disassembly

```asm
0x102097910  push    rbp
0x102097912  push    rbx
0x102097913  push    rsi
0x102097914  push    rdi
0x102097915  push    r12
0x102097917  push    r13
0x102097919  push    r14
0x10209791b  push    r15
0x10209791d  mov     eax, 1788h
0x102097922  call    _alloca_probe
0x102097927  sub     rsp, rax
0x10209792a  lea     rbp, [rsp+0D0h]
0x102097932  mov     [rbp+16F0h+var_1468], 0FFFFFFFFFFFFFFFEh
0x10209793d  movaps  [rbp+16F0h+var_50], xmm6
0x102097944  mov     rax, cs:__security_cookie
0x10209794b  xor     rax, rbp
0x10209794e  mov     [rbp+16F0h+var_60], rax
0x102097955  mov     [rbp+16F0h+var_16C0], r9
0x102097959  mov     rbx, r8
0x10209795c  mov     [rbp+16F0h+var_15F8], rbx
0x102097963  mov     [rbp+16F0h+var_16B0], rdx
0x102097967  mov     r13, rcx
0x10209796a  mov     [rbp+16F0h+var_1530], rcx
0x102097971  mov     r12, [rbp+16F0h+arg_20]
0x102097978  mov     [rbp+16F0h+var_1648], r12
0x10209797f  mov     rax, [rbp+16F0h+arg_30]
0x102097986  mov     [rbp+16F0h+var_1510], rax
0x10209798d  mov     rax, [rbp+16F0h+arg_40]
0x102097994  mov     [rbp+16F0h+var_15C8], rax
0x10209799b  mov     rax, [rbp+16F0h+arg_50]
0x1020979a2  mov     [rbp+16F0h+var_15A8], rax
0x1020979a9  mov     rax, [rbp+16F0h+arg_60]
0x1020979b0  mov     [rbp+16F0h+var_1518], rax
0x1020979b7  mov     rax, [rbp+16F0h+arg_70]
0x1020979be  mov     [rbp+16F0h+var_1520], rax
0x1020979c5  mov     rax, [rbp+16F0h+arg_90]
0x1020979cc  mov     [rbp+16F0h+var_1528], rax
0x1020979d3  mov     rax, [rbp+16F0h+arg_A0]
0x1020979da  mov     [rbp+16F0h+var_1628], rax
0x1020979e1  mov     rax, [rbp+16F0h+arg_A8]
0x1020979e8  mov     [rbp+16F0h+var_1508], rax
0x1020979ef  xor     edi, edi
0x1020979f1  mov     dword ptr [rbp+16F0h+var_1694+4], edi
0x1020979f4  mov     [rbp+16F0h+var_16A8], edi
0x1020979f7  mov     [rbp+16F0h+var_16E0], edi
0x1020979fa  mov     [rbp+16F0h+var_16B8], edi
0x1020979fd  mov     rcx, r8
0x102097a00  call    cs:__imp_?FIncreaseBufferCount@CBulkImp@@QEBA_NXZ; CBulkImp::FIncreaseBufferCount(void)
0x102097a06  mov     [rbp+16F0h+var_16EB], al
0x102097a09  mov     rcx, rbx; struct CBulkImp *
0x102097a0c  call    ?GetBufferCount@CImpImportProvider@@SAIPEAVCBulkImp@@@Z; CImpImportProvider::GetBufferCount(CBulkImp *)
0x102097a11  mov     [rbp+16F0h+var_16A0], eax
0x102097a14  mov     r15d, 80000h
0x102097a1a  mov     [rbp+16F0h+var_16E8], r15d
0x102097a1e  mov     ecx, [rbx+160h]
0x102097a24  test    ecx, ecx
0x102097a26  jz      short loc_102097A33
0x102097a28  mov     r15d, ecx
0x102097a2b  shl     r15d, 0Ah
0x102097a2f  mov     [rbp+16F0h+var_16E8], r15d
0x102097a33  mov     [rbp+16F0h+var_1660], r15d
0x102097a3a  xorps   xmm6, xmm6
0x102097a3d  mov     [rbp+16F0h+var_1670], rdi
0x102097a44  mov     [rbp+16F0h+var_1598], rdi
0x102097a4b  mov     qword ptr [rbp+16F0h+var_16D0], rdi
0x102097a4f  mov     qword ptr [rbp+16F0h+var_16C8], rdi
0x102097a53  mov     [rbp+16F0h+var_1680], rdi
0x102097a57  mov     [rbp+16F0h+var_16E9], 0
0x102097a5b  mov     [r13+30h], edi
0x102097a5f  mov     [rbp+16F0h+var_15E8], rdi
0x102097a66  mov     rcx, rbx
0x102097a69  call    cs:__imp_?GetFileReadLength@CRemoteFileRowsetMetadata@@QEBA_KXZ; CRemoteFileRowsetMetadata::GetFileReadLength(void)
0x102097a6f  mov     [rbp+16F0h+var_15C0], rax
0x102097a76  mov     rcx, rbx
0x102097a79  call    cs:__imp_?GetRowsetColDefHead@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetColDef@@XZ; CRemoteFileRowsetMetadata::GetRowsetColDefHead(void)
0x102097a7f  mov     [rbp+16F0h+var_1538], rax
0x102097a86  mov     rsi, [rbx+8]
0x102097a8a  mov     [rbp+16F0h+var_1588], rsi
0x102097a91  mov     rcx, rbx
0x102097a94  call    cs:__imp_?UnfilteredResolvedFiles@CRemoteFileRowsetMetadata@@QEBAPEBV?$CTDynArray@PEAVIDirectoryContentList@@V?$CFnI_Default@PEAVIDirectoryContentList@@@@V?$CFnD_Ptr@VIDirectoryContentList@@@@V?$CMemObjAlloc@$0A@@@@@XZ; CRemoteFileRowsetMetadata::UnfilteredResolvedFiles(void)
0x102097a9a  mov     rdi, rax
0x102097a9d  mov     [rbp+16F0h+var_15B0], rax
0x102097aa4  mov     rcx, rbx
0x102097aa7  call    cs:__imp_?GetExternalDataSourceName@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ; CRemoteFileRowsetMetadata::GetExternalDataSourceName(void)
0x102097aad  mov     [rbp+16F0h+var_1610], rax
0x102097ab4  mov     rcx, rbx
0x102097ab7  call    cs:__imp_?GetExternalDataSourceNameLength@CRemoteFileRowsetMetadata@@QEAAHXZ; CRemoteFileRowsetMetadata::GetExternalDataSourceNameLength(void)
0x102097abd  cdqe
0x102097abf  shr     rax, 1
0x102097ac2  mov     [rbp+16F0h+var_1618], rax
0x102097ac9  mov     rcx, rbx
0x102097acc  call    cs:__imp_?GetSecretValue@CBulkImp@@QEBAPEA_WXZ; CBulkImp::GetSecretValue(void)
0x102097ad2  mov     r14, rax
0x102097ad5  mov     [rbp+16F0h+var_1650], rax
0x102097adc  mov     rcx, rbx
0x102097adf  call    cs:__imp_?GetSecretValueByteCount@CBulkImp@@QEBAHXZ; CBulkImp::GetSecretValueByteCount(void)
0x102097ae5  cdqe
0x102097ae7  shr     rax, 1
0x102097aea  mov     [rbp+16F0h+var_1630], rax
0x102097af1  mov     rcx, rbx
0x102097af4  call    cs:__imp_?GetErrorFile@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ; CRemoteFileRowsetMetadata::GetErrorFile(void)
0x102097afa  mov     [rbp+16F0h+var_1560], rax
0x102097b01  mov     rcx, rbx
0x102097b04  call    cs:__imp_?GetErrorFileByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ; CRemoteFileRowsetMetadata::GetErrorFileByteCount(void)
0x102097b0a  cdqe
0x102097b0c  shr     rax, 1
0x102097b0f  mov     [rbp+16F0h+var_1558], rax
0x102097b16  mov     rcx, rbx
0x102097b19  call    cs:__imp_?GetErrorFileDataSource@CBulkImp@@QEBAPEA_WXZ; CBulkImp::GetErrorFileDataSource(void)
0x102097b1f  mov     [rbp+16F0h+var_1570], rax
0x102097b26  mov     rcx, rbx
0x102097b29  call    cs:__imp_?GetErrorFileDataSourceByteCount@CBulkImp@@QEBAHXZ; CBulkImp::GetErrorFileDataSourceByteCount(void)
0x102097b2f  cdqe
0x102097b31  shr     rax, 1
0x102097b34  mov     [rbp+16F0h+var_1568], rax
0x102097b3b  mov     rcx, rbx
0x102097b3e  call    cs:__imp_?GetFormatFile@CBulkImp@@QEBAPEA_WXZ; CBulkImp::GetFormatFile(void)
0x102097b44  mov     [rbp+16F0h+Source], rax
0x102097b4b  mov     rcx, rbx
0x102097b4e  call    cs:__imp_?GetFormatFileByteCount@CBulkImp@@QEBAHXZ; CBulkImp::GetFormatFileByteCount(void)
0x102097b54  cdqe
0x102097b56  shr     rax, 1
0x102097b59  mov     [rbp+16F0h+var_15B8], rax
0x102097b60  mov     rcx, rbx
0x102097b63  call    cs:__imp_?GetFormatFileDataSource@CBulkImp@@QEBAPEA_WXZ; CBulkImp::GetFormatFileDataSource(void)
0x102097b69  mov     [rbp+16F0h+var_1540], rax
0x102097b70  mov     rcx, rbx
0x102097b73  call    cs:__imp_?GetFormatFileDataSourceByteCount@CBulkImp@@QEBAHXZ; CBulkImp::GetFormatFileDataSourceByteCount(void)
0x102097b79  cdqe
0x102097b7b  shr     rax, 1
0x102097b7e  mov     [rbp+16F0h+var_1548], rax
0x102097b85  movzx   eax, byte ptr [rbx+114h]
0x102097b8c  mov     [rbp+16F0h+var_16EF], al
0x102097b8f  movzx   eax, byte ptr [rbx+115h]
0x102097b96  mov     [rbp+16F0h+var_16EE], al
0x102097b99  mov     rcx, rbx
0x102097b9c  call    cs:__imp_?GetErrorFileSecret@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ; CRemoteFileRowsetMetadata::GetErrorFileSecret(void)
0x102097ba2  mov     [rbp+16F0h+var_1580], rax
0x102097ba9  mov     rcx, rbx
0x102097bac  call    cs:__imp_?GetErrorFileSecretByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ; CRemoteFileRowsetMetadata::GetErrorFileSecretByteCount(void)
0x102097bb2  cdqe
0x102097bb4  shr     rax, 1
0x102097bb7  mov     [rbp+16F0h+var_1578], rax
0x102097bbe  mov     rcx, rbx
0x102097bc1  call    cs:__imp_?GetCompression@CRemoteFileRowsetMetadata@@QEBAPEA_WXZ; CRemoteFileRowsetMetadata::GetCompression(void)
0x102097bc7  mov     [rbp+16F0h+var_1638], rax
0x102097bce  mov     rcx, rbx
0x102097bd1  call    cs:__imp_?GetCompressionByteCount@CRemoteFileRowsetMetadata@@QEBAHXZ; CRemoteFileRowsetMetadata::GetCompressionByteCount(void)
0x102097bd7  cdqe
0x102097bd9  shr     rax, 1
0x102097bdc  mov     [rbp+16F0h+var_1640], rax
0x102097be3  movzx   eax, byte ptr [rbx+18h]
0x102097be7  mov     [rbp+16F0h+var_16E4], al
0x102097bea  mov     rcx, rbx
0x102097bed  call    cs:__imp_?IsBatchExtractorFramework@CRemoteFileRowsetMetadata@@QEBA_NXZ; CRemoteFileRowsetMetadata::IsBatchExtractorFramework(void)
0x102097bf3  mov     [rbp+16F0h+var_16E3], al
0x102097bf6  mov     rcx, rbx
0x102097bf9  call    cs:__imp_?GetRowsetFilesInfo@CRemoteFileRowsetMetadata@@QEBAPEAVCRowsetFilesInfo@@XZ; CRemoteFileRowsetMetadata::GetRowsetFilesInfo(void)
0x102097bff  mov     rbx, rax
0x102097c02  mov     rcx, [rbp+16F0h+var_15F8]
0x102097c09  call    cs:__imp_?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ; CRemoteFileRowsetMetadata::GetRowsetOptions(void)
0x102097c0f  test    rax, rax
0x102097c12  jz      short loc_102097C2B
0x102097c14  mov     rcx, [rbp+16F0h+var_15F8]
0x102097c1b  call    cs:__imp_?GetRowsetOptions@CRemoteFileRowsetMetadata@@QEBAPEBVCRowsetOptions@@XZ; CRemoteFileRowsetMetadata::GetRowsetOptions(void)
0x102097c21  cmp     byte ptr [rax+10h], 0
0x102097c25  mov     [rbp+16F0h+var_16ED], 1
0x102097c29  jnz     short loc_102097C2F
0x102097c2b  mov     [rbp+16F0h+var_16ED], 0
0x102097c2f  cmp     cs:byte_10316E9CB, 0
0x102097c36  setnz   al
0x102097c39  test    al, al
0x102097c3b  mov     rax, [rbp+16F0h+var_1628]
0x102097c42  mov     edx, 0
0x102097c47  cmovnz  rax, rdx
0x102097c4b  mov     [rbp+16F0h+var_1628], rax
0x102097c52  test    r14, r14
0x102097c55  jnz     short loc_102097C9F
0x102097c57  test    rbx, rbx
0x102097c5a  jz      short loc_102097C9F
0x102097c5c  cmp     dword ptr [rbx+34h], 3
0x102097c60  jnz     short loc_102097C9F
0x102097c62  test    rdi, rdi
0x102097c65  jz      short loc_102097C9F
0x102097c67  mov     eax, [rdi+0Ch]
0x102097c6a  test    eax, eax
0x102097c6c  jz      short loc_102097C9F
0x102097c6e  lea     ecx, [rax-1]
0x102097c71  mov     rax, [rdi+18h]
0x102097c75  mov     rbx, [rax+rcx*8]
0x102097c79  mov     rax, [rbx]
0x102097c7c  mov     rcx, rbx
0x102097c7f  call    qword ptr [rax+0B8h]
0x102097c85  mov     [rbp+16F0h+var_1650], rax
0x102097c8c  mov     rax, [rbx]
0x102097c8f  mov     rcx, rbx
0x102097c92  call    qword ptr [rax+0C0h]
0x102097c98  mov     [rbp+16F0h+var_1630], rax
0x102097c9f  xor     eax, eax
0x102097ca1  mov     r14d, eax
0x102097ca4  mov     [rbp+16F0h+var_169C], eax
0x102097ca7  mov     cl, 1
0x102097ca9  test    rsi, rsi
0x102097cac  jnz     short loc_102097CF6
0x102097cae  test    rdi, rdi
0x102097cb1  jz      short loc_102097D09
0x102097cb3  mov     ebx, eax
0x102097cb5  cmp     [rdi+0Ch], eax
0x102097cb8  jbe     short loc_102097CDE
0x102097cba  nop     word ptr [rax+rax]
0x102097cbf  nop
0x102097cc0  mov     ecx, ebx
0x102097cc2  mov     rax, [rdi+18h]
0x102097cc6  mov     rcx, [rax+rcx*8]
0x102097cca  mov     rax, [rcx]
0x102097ccd  call    qword ptr [rax+20h]
0x102097cd0  add     r14d, eax
0x102097cd3  inc     ebx
0x102097cd5  cmp     ebx, [rdi+0Ch]
0x102097cd8  jb      short loc_102097CC0
0x102097cda  mov     [rbp+16F0h+var_169C], r14d
0x102097cde  mov     rax, [rdi+18h]
0x102097ce2  mov     rcx, [rax]
0x102097ce5  mov     rax, [rcx]
0x102097ce8  call    qword ptr [rax+0A8h]
0x102097cee  test    rax, rax
0x102097cf1  setz    cl
0x102097cf4  jmp     short loc_102097D09
0x102097cf6  mov     r14d, [rsi+0Ch]
0x102097cfa  mov     [rbp+16F0h+var_169C], r14d
0x102097cfe  mov     rax, [rsi+18h]
0x102097d02  cmp     dword ptr [rax+8], 2
0x102097d06  setb    cl
0x102097d09  mov     rdi, [rbp+16F0h+var_16B0]
0x102097d0d  movups  xmm0, xmmword ptr [rdi]
0x102097d10  movaps  [rbp+16F0h+var_1200], xmm0
0x102097d17  movups  xmm1, xmmword ptr [rdi+10h]
0x102097d1b  movaps  [rbp+16F0h+var_11F0], xmm1
0x102097d22  movups  xmm0, xmmword ptr [rdi+20h]
0x102097d26  movaps  [rbp+16F0h+var_11E0], xmm0
0x102097d2d  movups  xmm1, xmmword ptr [rdi+30h]
0x102097d31  movaps  [rbp+16F0h+var_11D0], xmm1
0x102097d38  movups  xmm0, xmmword ptr [rdi+40h]
0x102097d3c  movaps  [rbp+16F0h+var_11C0], xmm0
0x102097d43  movups  xmm1, xmmword ptr [rdi+50h]
0x102097d47  movaps  [rbp+16F0h+var_11B0], xmm1
0x102097d4e  movups  xmm0, xmmword ptr [rdi+60h]
0x102097d52  movaps  [rbp+16F0h+var_11A0], xmm0
0x102097d59  movups  xmm1, xmmword ptr [rdi+70h]
0x102097d5d  movaps  [rbp+16F0h+var_1190], xmm1
0x102097d64  movups  xmm0, xmmword ptr [rdi+80h]
0x102097d6b  movaps  [rbp+16F0h+var_1180], xmm0
0x102097d72  lea     rax, [rbp+16F0h+var_16E9]
0x102097d76  mov     [rsp+17C0h+var_1798], rax
0x102097d7b  mov     byte ptr [rsp+17C0h+Locale], cl
0x102097d7f  movzx   r9d, [rbp+16F0h+var_16EB]
0x102097d84  movzx   r8d, [rbp+16F0h+arg_98]
0x102097d8c  lea     rdx, [rbp+16F0h+var_1200]
0x102097d93  mov     rcx, r13
0x102097d96  call    ?FShouldOpenFileInGetRowset@CImpImportProvider@@AEAA_NUtagIMPORT_INFO@@_N11PEA_N@Z; CImpImportProvider::FShouldOpenFileInGetRowset(tagIMPORT_INFO,bool,bool,bool,bool *)
0x102097d9b  mov     [rbp+16F0h+Destination], al
0x102097d9e  cmp     dword ptr [r13+18h], 1
0x102097da3  jnz     loc_102099996
0x102097da9  mov     dword ptr [r13+18h], 4
0x102097db1  mov     r8, gs:58h
0x102097dba  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x102097dc1  mov     edx, [rcx]
0x102097dc3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102097dca  mov     ebx, [rax]
0x102097dcc  add     rbx, [r8+rdx*8]
0x102097dd0  mov     rdx, [rbx+100h]
0x102097dd7  test    rdx, rdx
0x102097dda  jnz     short loc_102097DEB
0x102097ddc  xor     ecx, ecx
0x102097dde  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x102097de4  mov     rdx, [rbx+100h]
0x102097deb  mov     byte ptr [rsp+17C0h+Locale], 5
0x102097df0  mov     r9d, 28Ah
0x102097df6  lea     r8, aSqlNtdbmsStore_698; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x102097dfd  mov     rdx, [rdx+3E8h]
0x102097e04  mov     rcx, [rbp+16F0h+var_16C0]
0x102097e08  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x102097e0e  mov     [r13+28h], rax
0x102097e12  mov     ecx, [rdi+2Ch]
0x102097e15  test    ecx, ecx
0x102097e17  jz      short loc_102097E36
0x102097e19  cmp     ecx, 1
0x102097e1c  jnz     short loc_102097E3E
0x102097e1e  call    ?IsVDWBackendInstance@@YAHXZ; IsVDWBackendInstance(void)
0x102097e23  test    eax, eax
0x102097e25  jz      short loc_102097E2E
0x102097e27  mov     ecx, 0FDE9h
0x102097e2c  jmp     short loc_102097E3E
0x102097e2e  call    cs:__imp_GetOEMCP
0x102097e34  jmp     short loc_102097E3C
0x102097e36  call    cs:__imp_GetACP
0x102097e3c  mov     ecx, eax
0x102097e3e  mov     [r13+34h], ecx
0x102097e42  mov     ecx, [rdi+30h]
0x102097e45  test    ecx, ecx
  ... truncated ...
```
