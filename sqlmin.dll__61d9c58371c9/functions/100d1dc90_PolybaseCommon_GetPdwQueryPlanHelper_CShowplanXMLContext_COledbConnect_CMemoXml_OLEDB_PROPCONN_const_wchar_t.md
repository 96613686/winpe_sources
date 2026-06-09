# PolybaseCommon::GetPdwQueryPlanHelper(CShowplanXMLContext *,COledbConnect *,CMemoXml *,OLEDB_PROPCONN const *,wchar_t * *)

- ea: `0x100d1dc90`
- end: `0x100d2022d`
- name: `?GetPdwQueryPlanHelper@PolybaseCommon@@YAXPEAVCShowplanXMLContext@@PEAVCOledbConnect@@PEAVCMemoXml@@PEBUOLEDB_PROPCONN@@PEAPEA_W@Z`
- size: `9629`
- prototype: `void __fastcall(PolybaseCommon *__hidden this, struct CShowplanXMLContext *, struct COledbConnect *, struct CMemoXml *, const struct OLEDB_PROPCONN *, wchar_t **)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x100d1dac0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x10042d300`
- `0x10045e0a0`
- `0x100475060`
- `0x1004d88b0`
- `0x1005916f0`
- `0x100591e10`
- `0x1007cbc90`
- `0x100d1dc90`
- `0x1023a49c0`
- `0x1023a4ba0`
- `0x1023a4e00`
- `0x1023a4fc0`
- `0x1023a5b90`
- `0x1023a5d80`
- `0x1023a6cb0`
- `0x1023a6e50`
- `0x1023a7270`
- `0x1023a7480`
- `0x1023a76c0`
- `0x1023a7ab0`
- `0x1023a7d70`
- `0x1023a7f80`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x100d1eb9a`
- `OLEAUT32!__imp_SysFreeString` at `0x100d1eb9a`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e17a`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e2d5`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e445`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e17a`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e2d5`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100d1e445`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100d20100`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100d2017f`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100d20100`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100d2017f`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x100d1ef71`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x100d1ef71`
- `sqlTsEs!?CopyOut@CXVariant@@QEBAKPEAEPEBVCTypeInfo@@H@Z` at `0x100d1fcb4`
- `sqlTsEs!?CopyOut@CXVariant@@QEBAKPEAEPEBVCTypeInfo@@H@Z` at `0x100d1fcb4`
- `sqlTsEs!?GetCurCompatLevel@ContextAccessor@@YA?AVCCompatLevel@@VContextHandle@@@Z` at `0x100d1ed04`
- `sqlTsEs!?GetCurCompatLevel@ContextAccessor@@YA?AVCCompatLevel@@VContextHandle@@@Z` at `0x100d1ed04`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e0ee`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e22b`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e38a`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e0ee`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e22b`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100d1e38a`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100d1e679`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100d1e71a`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100d1e679`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100d1e71a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1e8b1`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1eded`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f194`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f430`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f6dc`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1fd58`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1ffea`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1e8b1`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1eded`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f194`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f430`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1f6dc`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1fd58`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100d1ffea`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e0b5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e1f1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e34d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f36e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f9e0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1fc90`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e0b5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e1f1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1e34d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f36e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f9e0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1fc90`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f81f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100d1f81f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ddeb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1de25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1df8d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1dfc7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1e5e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1e621`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1eb19`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ebfa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ecba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1f5f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1f630`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fb1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fb54`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fbfb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ff05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ff3f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ddeb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1de25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1df8d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1dfc7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1e5e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1e621`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1eb19`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ebfa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ecba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1f5f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1f630`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fb1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fb54`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1fbfb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ff05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100d1ff3f`
- `sqldk!SystemThread_TlsIndex` at `0x100d1e86d`
- `sqldk!SystemThread_TlsIndex` at `0x100d1e8c9`
- `sqldk!SystemThread_TlsIndex` at `0x100d1e94c`
- `sqldk!SystemThread_TlsIndex` at `0x100d1ece7`
- `sqldk!SystemThread_TlsIndex` at `0x100d1eda9`
- `sqldk!SystemThread_TlsIndex` at `0x100d1ee05`
- `sqldk!SystemThread_TlsIndex` at `0x100d1ef24`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f152`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f1ac`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f3ec`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f448`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f698`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f6f4`
- `sqldk!SystemThread_TlsIndex` at `0x100d1f98d`
- `sqldk!SystemThread_TlsIndex` at `0x100d1fd14`
- `sqldk!SystemThread_TlsIndex` at `0x100d1fd70`
- `sqldk!SystemThread_TlsIndex` at `0x100d1ffa6`
- `sqldk!SystemThread_TlsIndex` at `0x100d20002`
- `sqldk!SystemThread_TlsOffset` at `0x100d1e876`
- `sqldk!SystemThread_TlsOffset` at `0x100d1e8d2`
- `sqldk!SystemThread_TlsOffset` at `0x100d1e955`
- `sqldk!SystemThread_TlsOffset` at `0x100d1ecf0`
- `sqldk!SystemThread_TlsOffset` at `0x100d1edb2`
- `sqldk!SystemThread_TlsOffset` at `0x100d1ee0e`
- `sqldk!SystemThread_TlsOffset` at `0x100d1ef35`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f15b`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f1b5`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f3f5`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f451`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f6a1`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f6fd`
- `sqldk!SystemThread_TlsOffset` at `0x100d1f996`
- `sqldk!SystemThread_TlsOffset` at `0x100d1fd1d`
- `sqldk!SystemThread_TlsOffset` at `0x100d1fd79`
- `sqldk!SystemThread_TlsOffset` at `0x100d1ffaf`
- `sqldk!SystemThread_TlsOffset` at `0x100d2000b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100d20111`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100d20111`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1e891`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1e8ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1edcd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1ee29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f174`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f1d0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f410`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f46c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f6bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f718`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1fd38`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1fd94`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1ffca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d20026`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1e891`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1e8ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1edcd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1ee29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f174`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f1d0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f410`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f46c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f6bc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1f718`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1fd38`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1fd94`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d1ffca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100d20026`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1de33`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1dfd5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1e62f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1e807`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ec08`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ecc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f34e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f63e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f920`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1fb62`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1fc3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ff4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d200f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1de33`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1dfd5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1e62f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1e807`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ec08`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ecc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f34e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f63e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1f920`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1fb62`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1fc3a`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d1ff4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100d200f2`
- `sqllang!?PbhfDispenseBHF@IBHFDispenser@@QEAAPEAUIBlobHandleFactory@@XZ` at `0x100d1f9b4`
- `sqllang!?PbhfDispenseBHF@IBHFDispenser@@QEAAPEAUIBlobHandleFactory@@XZ` at `0x100d1f9b4`
- `sqllang!?ReleaseSession@CRemSess@@QEAAX_N0@Z` at `0x100d20204`
- `sqllang!?ReleaseSession@CRemSess@@QEAAX_N0@Z` at `0x100d20204`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1dd2a`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1de58`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1dea0`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1e030`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1e754`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1f0e5`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1dd2a`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1de58`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1dea0`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1e030`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1e754`
- `sqllang!?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z` at `0x100d1f0e5`
- `sqllang!?GetWStrLob@CTestHookXmlOutput@@QEAAPEAVCAutoClearXVariant@@XZ` at `0x100d1e647`
- `sqllang!?GetWStrLob@CTestHookXmlOutput@@QEAAPEAVCAutoClearXVariant@@XZ` at `0x100d1e647`
- `sqllang!?GetSession@COledbConnect@@QEBAPEAVCRemSess@@_N@Z` at `0x100d1dcfa`
- `sqllang!?GetSession@COledbConnect@@QEBAPEAVCRemSess@@_N@Z` at `0x100d1dcfa`

## string_xrefs

- `0x100d1f80c`: `sql\ntdbms\query\qecomp\kstr.cpp`
- `0x100d1f35f`: `sql\ntdbms\query\qeexec\qspbcommon.cpp`
- `0x100d1f9d0`: `sql\ntdbms\query\qeexec\qspbcommon.cpp`
- `0x100d1fc81`: `sql\ntdbms\query\qeexec\qspbcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=86
void __fastcall PolybaseCommon::GetPdwQueryPlanHelper(
        PolybaseCommon *this,
        struct CShowplanXMLContext *a2,
        struct COledbConnect *a3,
        struct CMemoXml *a4,
        const struct OLEDB_PROPCONN *a5)
{
  struct IMemObj *v6; // r13
  struct IUnknown *Interface; // rdi
  int v8; // r15d
  __int64 v9; // rbx
  __int64 v10; // rax
  struct IUnknown *v11; // r12
  struct IUnknown *v12; // r14
  const wchar_t *v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rax
  struct IMemObj *v16; // r15
  _QWORD *v17; // r12
  char v18; // al
  const struct CTypeInfo *v19; // rdx
  struct tagDBBINDING *v20; // rbx
  unsigned int *v21; // rdi
  struct tagDBPARAMBINDINFO *v22; // r14
  unsigned __int8 *v23; // rdi
  char v24; // al
  char v25; // al
  const struct CTypeInfo *v26; // rdx
  __int64 v27; // r13
  char v28; // al
  char v29; // al
  const struct CTypeInfo *v30; // rdx
  char v31; // al
  unsigned int v32; // ebx
  struct IUnknown *v33; // r15
  int v34; // r14d
  __int64 v35; // rbx
  __int64 v36; // rax
  struct CAutoClearXVariant *WStrLob; // rax
  struct IAccessor *v38; // rdi
  int v39; // r14d
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // r14
  char v48; // bl
  int v49; // r15d
  int v50; // ecx
  unsigned int v51; // edi
  __int64 v52; // rbx
  __int64 v53; // rax
  struct tagDBPROP *v54; // r14
  __int64 v55; // rdi
  BSTR *p_bstrVal; // rbx
  struct IUnknown *v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rbx
  __int64 v66; // rdx
  const wchar_t *v67; // rbx
  const wchar_t *v68; // rax
  char *ThreadLocalStoragePointer; // rdx
  __int64 v70; // r9
  int v71; // ebx
  unsigned int *DefaultCollationData; // rax
  unsigned int v73; // eax
  struct IMemObj *v74; // r14
  struct IUnknown *v75; // r13
  __int64 v76; // rbx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rbx
  __int64 v80; // rdx
  int v81; // edi
  __int64 v82; // rbx
  __int64 v83; // rax
  unsigned int *v84; // r12
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // rbx
  __int64 v89; // rdx
  int v90; // edi
  __int64 v91; // rbx
  __int64 v92; // rax
  __int64 v93; // rbx
  __int64 v94; // rax
  __int64 v95; // rcx
  __int64 v96; // rbx
  __int64 v97; // rdx
  int v98; // r14d
  unsigned int v99; // r15d
  struct IMemObj *v100; // rbx
  void *v101; // rax
  __int64 (__fastcall ***v102)(_QWORD, LPOLESTR, _QWORD); // rdi
  __int64 v103; // rbx
  __int64 v104; // rax
  const struct CQName *v105; // rax
  const struct CTypeInfo *v106; // r8
  struct IBlobHandleFactory *v107; // rbx
  void *v108; // rdi
  unsigned int v109; // r15d
  __int64 v110; // r12
  struct IUnknown *v111; // rbx
  int v112; // r14d
  __int64 v113; // rdi
  __int64 v114; // rax
  unsigned int v115; // eax
  __int64 v116; // rdi
  void *v117; // r12
  int *v118; // r13
  __int64 v119; // r14
  __int64 v120; // rbx
  int v121; // eax
  __int64 v122; // r15
  unsigned __int64 v123; // rax
  unsigned __int8 *v124; // rax
  const struct OLEDB_PROPCONN *v125; // rdi
  __int64 v126; // rbx
  __int64 v127; // rax
  __int64 v128; // rcx
  __int64 v129; // rbx
  __int64 v130; // rdx
  int v131; // edi
  __int64 v132; // rbx
  __int64 v133; // rax
  __int64 v134; // rbx
  __int64 v135; // rax
  __int64 v136; // rcx
  __int64 v137; // rbx
  __int64 v138; // rdx
  rsize_t SizeInWords; // [rsp+20h] [rbp-E0h]
  rsize_t SizeInWordsa; // [rsp+20h] [rbp-E0h]
  struct IUnknown *v141; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v142; // [rsp+48h] [rbp-B8h] BYREF
  struct tagDBPROP *v143; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v144; // [rsp+58h] [rbp-A8h] BYREF
  int *v145; // [rsp+60h] [rbp-A0h]
  struct IUnknown *v146; // [rsp+68h] [rbp-98h]
  struct IMemObj *v147; // [rsp+70h] [rbp-90h]
  struct IUnknown *v148; // [rsp+78h] [rbp-88h]
  int *v149; // [rsp+80h] [rbp-80h]
  unsigned int v150; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v151; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v152; // [rsp+90h] [rbp-70h] BYREF
  int v153; // [rsp+94h] [rbp-6Ch] BYREF
  int v154; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v155; // [rsp+A0h] [rbp-60h]
  int v156; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v157; // [rsp+B0h] [rbp-50h] BYREF
  struct tagDBCOLUMNINFO *v158; // [rsp+B8h] [rbp-48h] BYREF
  struct tagDBPROP *v159; // [rsp+C0h] [rbp-40h] BYREF
  struct IUnknown *v160; // [rsp+C8h] [rbp-38h] BYREF
  struct IUnknown *v161; // [rsp+D0h] [rbp-30h]
  struct IUnknown *v162; // [rsp+D8h] [rbp-28h]
  __int64 v163; // [rsp+E0h] [rbp-20h] BYREF
  CTestHookXmlOutput *v164; // [rsp+E8h] [rbp-18h]
  __int64 *v165; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *v166; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v167; // [rsp+100h] [rbp+0h]
  struct IAccessor *v168; // [rsp+108h] [rbp+8h]
  struct IMemObj *v169; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v170; // [rsp+118h] [rbp+18h]
  __int128 v171; // [rsp+120h] [rbp+20h]
  struct tagSSPARAMPROPS *v172; // [rsp+130h] [rbp+30h]
  struct tagDBBINDING *v173; // [rsp+138h] [rbp+38h]
  void *v174; // [rsp+140h] [rbp+40h]
  __int64 v175; // [rsp+148h] [rbp+48h]
  _QWORD *v176; // [rsp+150h] [rbp+50h]
  unsigned int v177; // [rsp+158h] [rbp+58h]
  int v178; // [rsp+15Ch] [rbp+5Ch]
  __int64 v179; // [rsp+160h] [rbp+60h]
  _QWORD v180[2]; // [rsp+170h] [rbp+70h] BYREF
  int v181; // [rsp+180h] [rbp+80h]
  __int64 v182; // [rsp+188h] [rbp+88h]
  __int64 v183; // [rsp+190h] [rbp+90h]
  void *v184; // [rsp+198h] [rbp+98h]
  __int64 v185; // [rsp+1A0h] [rbp+A0h]
  int v186; // [rsp+1A8h] [rbp+A8h]
  int v187; // [rsp+1ACh] [rbp+ACh]
  __int64 v188; // [rsp+1B0h] [rbp+B0h]
  int v189; // [rsp+1B8h] [rbp+B8h]
  char v190; // [rsp+1BCh] [rbp+BCh]
  unsigned __int64 v191; // [rsp+1C0h] [rbp+C0h] BYREF
  struct IUnknown *v192; // [rsp+1C8h] [rbp+C8h]
  __int64 v193; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v194; // [rsp+1D8h] [rbp+D8h]
  struct ILockBytesSS *v195; // [rsp+1E0h] [rbp+E0h]
  const struct OLEDB_PROPCONN *v196; // [rsp+1E8h] [rbp+E8h]
  struct IUnknown **Session; // [rsp+1F0h] [rbp+F0h]
  __int64 v198; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v199[2]; // [rsp+200h] [rbp+100h] BYREF
  int v200; // [rsp+210h] [rbp+110h]
  __int64 v201; // [rsp+218h] [rbp+118h]
  __int64 v202; // [rsp+220h] [rbp+120h]
  void *v203; // [rsp+228h] [rbp+128h]
  __int64 v204; // [rsp+230h] [rbp+130h]
  int v205; // [rsp+238h] [rbp+138h]
  int v206; // [rsp+23Ch] [rbp+13Ch]
  __int64 v207; // [rsp+240h] [rbp+140h]
  int v208; // [rsp+248h] [rbp+148h]
  char v209; // [rsp+24Ch] [rbp+14Ch]
  struct IUnknown *v210; // [rsp+250h] [rbp+150h]
  _QWORD v211[2]; // [rsp+260h] [rbp+160h] BYREF
  int v212; // [rsp+270h] [rbp+170h]
  __int64 v213; // [rsp+278h] [rbp+178h]
  __int64 v214; // [rsp+280h] [rbp+180h]
  void *v215; // [rsp+288h] [rbp+188h]
  __int64 v216; // [rsp+290h] [rbp+190h]
  int v217; // [rsp+298h] [rbp+198h]
  int v218; // [rsp+29Ch] [rbp+19Ch]
  __int64 v219; // [rsp+2A0h] [rbp+1A0h]
  int v220; // [rsp+2A8h] [rbp+1A8h]
  char v221; // [rsp+2ACh] [rbp+1ACh]
  _QWORD v222[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v223; // [rsp+2C0h] [rbp+1C0h]
  __int64 v224; // [rsp+2C8h] [rbp+1C8h]
  __int64 v225; // [rsp+2D0h] [rbp+1D0h]
  void *v226; // [rsp+2D8h] [rbp+1D8h]
  __int64 v227; // [rsp+2E0h] [rbp+1E0h]
  int v228; // [rsp+2E8h] [rbp+1E8h]
  int v229; // [rsp+2ECh] [rbp+1ECh]
  __int64 v230; // [rsp+2F0h] [rbp+1F0h]
  int v231; // [rsp+2F8h] [rbp+1F8h]
  char v232; // [rsp+2FCh] [rbp+1FCh]
  _QWORD v233[2]; // [rsp+300h] [rbp+200h] BYREF
  int v234; // [rsp+310h] [rbp+210h]
  __int64 v235; // [rsp+318h] [rbp+218h]
  __int64 v236; // [rsp+320h] [rbp+220h]
  void *v237; // [rsp+328h] [rbp+228h]
  __int64 v238; // [rsp+330h] [rbp+230h]
  int v239; // [rsp+338h] [rbp+238h]
  int v240; // [rsp+33Ch] [rbp+23Ch]
  __int64 v241; // [rsp+340h] [rbp+240h]
  int v242; // [rsp+348h] [rbp+248h]
  char v243; // [rsp+34Ch] [rbp+24Ch]
  _QWORD v244[2]; // [rsp+350h] [rbp+250h] BYREF
  int v245; // [rsp+360h] [rbp+260h]
  __int64 v246; // [rsp+368h] [rbp+268h]
  __int64 v247; // [rsp+370h] [rbp+270h]
  void *v248; // [rsp+378h] [rbp+278h]
  __int64 v249; // [rsp+380h] [rbp+280h]
  int v250; // [rsp+388h] [rbp+288h]
  int v251; // [rsp+38Ch] [rbp+28Ch]
  __int64 v252; // [rsp+390h] [rbp+290h]
  int v253; // [rsp+398h] [rbp+298h]
  char v254; // [rsp+39Ch] [rbp+29Ch]
  _QWORD v255[2]; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v256; // [rsp+3B0h] [rbp+2B0h]
  __int64 v257; // [rsp+3B8h] [rbp+2B8h]
  __int64 v258; // [rsp+3C0h] [rbp+2C0h]
  void *v259; // [rsp+3C8h] [rbp+2C8h]
  __int64 v260; // [rsp+3D0h] [rbp+2D0h]
  int v261; // [rsp+3D8h] [rbp+2D8h]
  int v262; // [rsp+3DCh] [rbp+2DCh]
  __int64 v263; // [rsp+3E0h] [rbp+2E0h]
  int v264; // [rsp+3E8h] [rbp+2E8h]
  char v265; // [rsp+3ECh] [rbp+2ECh]
  int v266; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v267; // [rsp+3F8h] [rbp+2F8h]
  int v268; // [rsp+400h] [rbp+300h] BYREF
  int v269; // [rsp+404h] [rbp+304h]
  __int64 v270; // [rsp+408h] [rbp+308h]
  int v271; // [rsp+410h] [rbp+310h] BYREF
  __int64 v272; // [rsp+418h] [rbp+318h]
  __int64 v273; // [rsp+420h] [rbp+320h]
  __int64 v274; // [rsp+428h] [rbp+328h]
  __int64 v275; // [rsp+430h] [rbp+330h]
  bool v276; // [rsp+440h] [rbp+340h]
  int v277; // [rsp+450h] [rbp+350h] BYREF
  __int64 v278; // [rsp+458h] [rbp+358h]
  int v279; // [rsp+460h] [rbp+360h] BYREF
  int v280; // [rsp+464h] [rbp+364h]
  __int64 v281; // [rsp+468h] [rbp+368h]
  int v282; // [rsp+470h] [rbp+370h] BYREF
  __int64 v283; // [rsp+478h] [rbp+378h]
  __int64 v284; // [rsp+480h] [rbp+380h]
  __int64 v285; // [rsp+488h] [rbp+388h]
  __int64 v286; // [rsp+490h] [rbp+390h]
  bool v287; // [rsp+4A0h] [rbp+3A0h]
  int v288; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v289; // [rsp+4B8h] [rbp+3B8h]
  int v290; // [rsp+4C0h] [rbp+3C0h] BYREF
  int v291; // [rsp+4C4h] [rbp+3C4h]
  __int64 v292; // [rsp+4C8h] [rbp+3C8h]
  int v293; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v294; // [rsp+4D8h] [rbp+3D8h]
  __int64 v295; // [rsp+4E0h] [rbp+3E0h]
  __int64 v296; // [rsp+4E8h] [rbp+3E8h]
  __int64 v297; // [rsp+4F0h] [rbp+3F0h]
  bool v298; // [rsp+500h] [rbp+400h]
  int v299; // [rsp+510h] [rbp+410h] BYREF
  __int64 v300; // [rsp+518h] [rbp+418h]
  int v301; // [rsp+520h] [rbp+420h] BYREF
  int v302; // [rsp+524h] [rbp+424h]
  __int64 v303; // [rsp+528h] [rbp+428h]
  int v304; // [rsp+530h] [rbp+430h] BYREF
  __int64 v305; // [rsp+538h] [rbp+438h]
  __int64 v306; // [rsp+540h] [rbp+440h]
  __int64 v307; // [rsp+548h] [rbp+448h]
  __int64 v308; // [rsp+550h] [rbp+450h]
  bool v309; // [rsp+560h] [rbp+460h]
  int v310; // [rsp+570h] [rbp+470h] BYREF
  __int64 v311; // [rsp+578h] [rbp+478h]
  int v312; // [rsp+580h] [rbp+480h] BYREF
  int v313; // [rsp+584h] [rbp+484h]
  __int64 v314; // [rsp+588h] [rbp+488h]
  int v315; // [rsp+590h] [rbp+490h] BYREF
  __int64 v316; // [rsp+598h] [rbp+498h]
  __int64 v317; // [rsp+5A0h] [rbp+4A0h]
  __int64 v318; // [rsp+5A8h] [rbp+4A8h]
  __int64 v319; // [rsp+5B0h] [rbp+4B0h]
  bool v320; // [rsp+5C0h] [rbp+4C0h]
  int v321; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v322; // [rsp+5D8h] [rbp+4D8h]
  int v323; // [rsp+5E0h] [rbp+4E0h] BYREF
  int v324; // [rsp+5E4h] [rbp+4E4h]
  __int64 v325; // [rsp+5E8h] [rbp+4E8h]
  int v326; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v327; // [rsp+5F8h] [rbp+4F8h]
  __int64 v328; // [rsp+600h] [rbp+500h]
  __int64 v329; // [rsp+608h] [rbp+508h]
  __int64 v330; // [rsp+610h] [rbp+510h]
  bool v331; // [rsp+620h] [rbp+520h]
  int v332; // [rsp+630h] [rbp+530h] BYREF
  __int64 v333; // [rsp+638h] [rbp+538h]
  int v334; // [rsp+640h] [rbp+540h] BYREF
  int v335; // [rsp+644h] [rbp+544h]
  __int64 v336; // [rsp+648h] [rbp+548h]
  int v337; // [rsp+650h] [rbp+550h] BYREF
  __int64 v338; // [rsp+658h] [rbp+558h]
  __int64 v339; // [rsp+660h] [rbp+560h]
  __int64 v340; // [rsp+668h] [rbp+568h]
  __int64 v341; // [rsp+670h] [rbp+570h]
  bool v342; // [rsp+680h] [rbp+580h]
  void **v343; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v344[2]; // [rsp+698h] [rbp+598h] BYREF
  __int16 v345; // [rsp+69Ah] [rbp+59Ah]
  __int128 v346; // [rsp+6A0h] [rbp+5A0h]
  int v347; // [rsp+6B0h] [rbp+5B0h]
  __int128 v348; // [rsp+6B8h] [rbp+5B8h]
  __int128 v349; // [rsp+6C8h] [rbp+5C8h]
  _QWORD v350[2]; // [rsp+6E0h] [rbp+5E0h] BYREF
  int v351; // [rsp+6F0h] [rbp+5F0h]
  __int64 v352; // [rsp+6F8h] [rbp+5F8h]
  __int64 v353; // [rsp+700h] [rbp+600h]
  void *v354; // [rsp+708h] [rbp+608h]
  __int64 v355; // [rsp+710h] [rbp+610h]
  int v356; // [rsp+718h] [rbp+618h]
  int v357; // [rsp+71Ch] [rbp+61Ch]
  __int64 v358; // [rsp+720h] [rbp+620h]
  int v359; // [rsp+728h] [rbp+628h]
  char v360; // [rsp+72Ch] [rbp+62Ch]
  _QWORD v361[2]; // [rsp+730h] [rbp+630h] BYREF
  int v362; // [rsp+740h] [rbp+640h]
  __int64 v363; // [rsp+748h] [rbp+648h]
  __int64 v364; // [rsp+750h] [rbp+650h]
  void *v365; // [rsp+758h] [rbp+658h]
  __int64 v366; // [rsp+760h] [rbp+660h]
  int v367; // [rsp+768h] [rbp+668h]
  int v368; // [rsp+76Ch] [rbp+66Ch]
  __int64 v369; // [rsp+770h] [rbp+670h]
  int v370; // [rsp+778h] [rbp+678h]
  char v371; // [rsp+77Ch] [rbp+67Ch]
  _QWORD v372[2]; // [rsp+780h] [rbp+680h] BYREF
  int v373; // [rsp+790h] [rbp+690h]
  __int64 v374; // [rsp+798h] [rbp+698h]
  __int64 v375; // [rsp+7A0h] [rbp+6A0h]
  void *v376; // [rsp+7A8h] [rbp+6A8h]
  __int64 v377; // [rsp+7B0h] [rbp+6B0h]
  int v378; // [rsp+7B8h] [rbp+6B8h]
  int v379; // [rsp+7BCh] [rbp+6BCh]
  __int64 v380; // [rsp+7C0h] [rbp+6C0h]
  int v381; // [rsp+7C8h] [rbp+6C8h]
  char v382; // [rsp+7CCh] [rbp+6CCh]
  void **v383; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v384; // [rsp+7D8h] [rbp+6D8h]
  __int64 v385; // [rsp+7E0h] [rbp+6E0h]
  void *v386; // [rsp+7F0h] [rbp+6F0h]
  unsigned int v387; // [rsp+7F8h] [rbp+6F8h]
  __int64 v388; // [rsp+800h] [rbp+700h]
  GUID *v389; // [rsp+808h] [rbp+708h]
  int v390; // [rsp+810h] [rbp+710h]
  __int64 v391; // [rsp+818h] [rbp+718h]
  __int64 v392; // [rsp+820h] [rbp+720h]
  __int64 v393; // [rsp+828h] [rbp+728h]
  __int64 v394; // [rsp+830h] [rbp+730h]
  int v395; // [rsp+838h] [rbp+738h]
  int v396; // [rsp+83Ch] [rbp+73Ch]
  __int64 v397; // [rsp+840h] [rbp+740h]
  int v398; // [rsp+848h] [rbp+748h]
  char v399; // [rsp+84Ch] [rbp+74Ch]
  _QWORD v400[2]; // [rsp+850h] [rbp+750h] BYREF
  __int128 v401; // [rsp+860h] [rbp+760h]
  __int64 v402; // [rsp+870h] [rbp+770h]
  __int16 v403; // [rsp+878h] [rbp+778h]
  __int64 v404; // [rsp+87Ch] [rbp+77Ch]
  __int64 v405; // [rsp+888h] [rbp+788h]
  char v406; // [rsp+890h] [rbp+790h]
  int v407; // [rsp+894h] [rbp+794h]
  __int64 v408; // [rsp+898h] [rbp+798h]
  _QWORD v409[8]; // [rsp+8A0h] [rbp+7A0h] BYREF
  int v410; // [rsp+8E0h] [rbp+7E0h]
  __int64 v411; // [rsp+8E8h] [rbp+7E8h]
  int v412; // [rsp+8F0h] [rbp+7F0h]
  int v413; // [rsp+8F4h] [rbp+7F4h]
  void **v414; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v415[2]; // [rsp+908h] [rbp+808h] BYREF
  __int16 v416; // [rsp+90Ah] [rbp+80Ah]
  __int128 v417; // [rsp+910h] [rbp+810h]
  int v418; // [rsp+920h] [rbp+820h]
  __int128 v419; // [rsp+928h] [rbp+828h]
  __int128 v420; // [rsp+938h] [rbp+838h]
  __int64 v421; // [rsp+950h] [rbp+850h]
  unsigned int *v422; // [rsp+958h] [rbp+858h]
  int v423; // [rsp+960h] [rbp+860h] BYREF
  __int64 v424; // [rsp+968h] [rbp+868h]
  _DWORD v425[2]; // [rsp+970h] [rbp+870h] BYREF
  __int64 v426; // [rsp+978h] [rbp+878h]
  char v427[64]; // [rsp+980h] [rbp+880h] BYREF
  struct tagDBPARAMS v428; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v429[48]; // [rsp+9D8h] [rbp+8D8h] BYREF
  _BYTE v430[56]; // [rsp+A08h] [rbp+908h] BYREF
  struct tagDBPROP *v431; // [rsp+A40h] [rbp+940h] BYREF
  int v432; // [rsp+A48h] [rbp+948h]
  GUID v433; // [rsp+A4Ch] [rbp+94Ch]
  struct tagDBCOLUMNINFO v434; // [rsp+A60h] [rbp+960h] BYREF
  int v435; // [rsp+AB0h] [rbp+9B0h] BYREF
  GUID v436; // [rsp+AB4h] [rbp+9B4h]
  _BYTE v437[8000]; // [rsp+AD0h] [rbp+9D0h] BYREF
  wchar_t v438[4008]; // [rsp+2A10h] [rbp+2910h] BYREF

  v421 = -2;
  v145 = (int *)a4;
  v164 = a3;
  v196 = a5;
  v6 = (struct IMemObj *)*((_QWORD *)this + 3);
  v147 = v6;
  v149 = (int *)v6;
  Session = (struct IUnknown **)COledbConnect::GetSession(a2, 0);
  v161 = 0;
  Interface = COledbConnect::GetInterface(a2, &IID_IDBCreateCommand, Session[5], &IID_IUnknown, 1);
  v161 = Interface;
  v160 = 0;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IUnknown **))Interface->lpVtbl[1].QueryInterface)(
         Interface,
         0,
         &IID_ICommandText,
         &v160);
  if ( v8 < 0 )
  {
    _mm_lfence();
    v9 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v10 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v199[0] = Interface;
    v199[1] = &IID_IDBCreateCommand;
    v200 = v8;
    v201 = v10;
    v202 = v9;
    v203 = 0;
    v204 = 0;
    v205 = 0;
    v206 = -1;
    v207 = 0;
    v208 = 0;
    v209 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v199) )
      ex_raise(73, 5, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v199);
    ex_raise(73, 5, 16, 2, v201, v202);
    operator delete[](v203);
  }
  v11 = COledbConnect::GetInterface(a2, &IID_ICommandText, v160, &IID_IUnknown, 1);
  v146 = v11;
  v148 = v11;
  ((void (__fastcall *)(struct IUnknown *, const GUID *, const wchar_t *))v11->lpVtbl[2].AddRef)(
    v11,
    &DBGUID_SQL,
    L"{? = call sp_execute_memo(?,?)}");
  v167 = 0;
  v12 = COledbConnect::GetInterface(a2, &IID_ICommandProperties, v11, &IID_IUnknown, 1);
  v167 = v12;
  v159 = 0;
  v151 = 137;
  v150 = 0;
  (*(void (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
  if ( !(unsigned int)FGetRowsetProperties(v12, v13, 1u, &v151, &v150, &v159, &DBPROPSET_ROWSET) )
  {
    v14 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v15 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v255[0] = Interface;
    v255[1] = &IID_ICommandProperties;
    v256 = v8;
    v257 = v15;
    v258 = v14;
    v259 = 0;
    v260 = 0;
    v261 = 0;
    v262 = -1;
    v263 = 0;
    v264 = 0;
    v265 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v255) )
      ex_raise(73, 5, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v255);
    ex_raise(73, 5, 16, 2, v257, v258);
    operator delete[](v259);
  }
  v431 = v159;
  v432 = 1;
  v433 = DBPROPSET_SQLSERVERSTREAM;
  ((void (__fastcall *)(struct IUnknown *, __int64, struct tagDBPROP **))v12->lpVtbl[1].AddRef)(v12, 1, &v431);
  v162 = 0;
  v155 = COledbConnect::GetInterface(a2, &IID_ICommandWithParameters, v11, &IID_IUnknown, 1);
  v162 = v155;
  v169 = v6;
  v170 = 0;
  v174 = 0;
  v173 = 0;
  v171 = 0;
  v172 = 0;
  v175 = 0;
  v176 = 0;
  v177 = 1;
  v178 = 1;
  v179 = 0;
  COleDbParams::Init((COleDbParams *)&v169, 3u);
  v16 = v169;
  v17 = v176;
  v18 = CTypeInfo::tiI4;
  if ( CTypeInfo::tiI4 == 98 )
  {
    if ( *v176 )
      goto LABEL_14;
    *v17 = operator new[](0x1F78u, v169, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v18 = CTypeInfo::tiI4;
  }
  if ( v18 == 31 || !v18 )
  {
    v19 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
    goto LABEL_16;
  }
LABEL_14:
  v19 = (const struct CTypeInfo *)&CTypeInfo::tiI4;
LABEL_16:
  v20 = v173;
  InitDbBind(v173, v19, 1, 1);
  if ( (_WORD)xmmword_1031D5690 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiI4)) )
  {
    v20->wType = 13;
    v20->cbMaxLen = 0x7FFFFFFF;
    v20->dwPart |= 2u;
    v20->obLength = 8;
    v20->pObject = &x_dbobjSequentialStream;
  }
  v20->dwMemOwner = 0;
  v20->iOrdinal = 1;
  v20->eParamIO |= 3u;
  v21 = (unsigned int *)v171;
  *(_QWORD *)v171 = 1;
  v22 = (struct tagDBPARAMBINDINFO *)*((_QWORD *)&v171 + 1);
  InitDbParamBindInfo(v16, *((struct tagDBPARAMBINDINFO **)&v171 + 1), (const struct CTypeInfo *)&CTypeInfo::tiI4);
  InitDbParamProperties(v16, v172, *v21, (const struct CTypeInfo *)&CTypeInfo::tiI4);
  v22->dwFlags |= 3u;
  v23 = (unsigned __int8 *)v174;
  *(_DWORD *)v174 = 3;
  v24 = CTypeInfo::tiI4;
  if ( CTypeInfo::tiI4 == 31 )
  {
    *(_DWORD *)v23 = 3;
    v24 = CTypeInfo::tiI4;
  }
  if ( !v24 )
    *(_DWORD *)v23 = 13;
  v25 = CTypeInfo::tiVarWstrUnlim;
  if ( CTypeInfo::tiVarWstrUnlim == 98 )
  {
    if ( v17[1] )
      goto LABEL_28;
    v17[1] = operator new[](0x1F78u, v16, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v25 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( v25 == 31 || !v25 )
  {
    v26 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
    goto LABEL_30;
  }
LABEL_28:
  v26 = (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim;
LABEL_30:
  InitDbBind(v20 + 1, v26, 1, 1);
  if ( (_WORD)xmmword_103369300 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiVarWstrUnlim)) )
  {
    v20[1].wType = 13;
    v20[1].cbMaxLen = 0x7FFFFFFF;
    v20[1].dwPart |= 2u;
    v20[1].obLength = 8;
    v20[1].pObject = &x_dbobjSequentialStream;
  }
  v20[1].dwMemOwner = 0;
  v20[1].iOrdinal = 2;
  v20[1].eParamIO |= 1u;
  v20[1].obStatus += 80LL;
  v20[1].obValue += 80LL;
  v20[1].obLength += 80LL;
  v27 = v171;
  *(_QWORD *)(v171 + 8) = 2;
  InitDbParamBindInfo(v16, v22 + 1, (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  InitDbParamProperties(
    v16,
    (struct tagSSPARAMPROPS *)((char *)v172 + 24),
    *(unsigned int *)(v27 + 8),
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  v22[1].dwFlags |= 1u;
  v28 = CTypeInfo::tiVarWstrUnlim;
  if ( CTypeInfo::tiVarWstrUnlim == 31 )
  {
    *((_DWORD *)v23 + 20) = 3;
    v28 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( !v28 )
    *((_DWORD *)v23 + 20) = 13;
  v29 = CTypeInfo::tiBoolNotNull;
  if ( CTypeInfo::tiBoolNotNull == 98 )
  {
    if ( v17[2] )
      goto LABEL_42;
    v17[2] = operator new[](0x1F78u, v16, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v29 = CTypeInfo::tiBoolNotNull;
  }
  if ( v29 == 31 || !v29 )
  {
    v30 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
    goto LABEL_44;
  }
LABEL_42:
  v30 = (const struct CTypeInfo *)&CTypeInfo::tiBoolNotNull;
LABEL_44:
  InitDbBind(v20 + 2, v30, 1, 1);
  if ( (_WORD)xmmword_1031F94F0 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiBoolNotNull)) )
  {
    v20[2].wType = 13;
    v20[2].cbMaxLen = 0x7FFFFFFF;
    v20[2].dwPart |= 2u;
    v20[2].obLength = 8;
    v20[2].pObject = &x_dbobjSequentialStream;
  }
  v20[2].dwMemOwner = 0;
  v20[2].iOrdinal = 3;
  v20[2].eParamIO |= 1u;
  v20[2].obStatus += 160LL;
  v20[2].obValue += 160LL;
  v20[2].obLength += 160LL;
  *(_QWORD *)(v27 + 16) = 3;
  InitDbParamBindInfo(v16, v22 + 2, (const struct CTypeInfo *)&CTypeInfo::tiBoolNotNull);
  InitDbParamProperties(
    v16,
    (struct tagSSPARAMPROPS *)((char *)v172 + 48),
    *(unsigned int *)(v27 + 16),
    (const struct CTypeInfo *)&CTypeInfo::tiBoolNotNull);
  v22[2].dwFlags |= 1u;
  v31 = CTypeInfo::tiBoolNotNull;
  if ( CTypeInfo::tiBoolNotNull == 31 )
  {
    *((_DWORD *)v23 + 40) = 3;
    v31 = CTypeInfo::tiBoolNotNull;
  }
  if ( !v31 )
    *((_DWORD *)v23 + 40) = 13;
  v32 = v170;
  memset_0(v23, 0, 80 * v170);
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v423, 536871443, v177);
  v33 = v155;
  v34 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, struct tagDBPARAMBINDINFO *))v155->lpVtbl[1].Release)(
          v155,
          v32,
          v27,
          v22);
  v155 = (struct IUnknown *)v425;
  if ( v425[0] )
  {
    if ( v425[1] )
      *(_DWORD *)(v426 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v426 + 608) + 16LL))(
        *(_QWORD *)(v426 + 608),
        v426,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v427);
  *(_DWORD *)(v424 + 616) &= ~v423;
  if ( v34 < 0 )
  {
    _mm_lfence();
    v35 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v36 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v211[0] = v33;
    v211[1] = &IID_ICommandText;
    v212 = v34;
    v213 = v36;
    v214 = v35;
    v215 = 0;
    v216 = 0;
    v217 = 0;
    v218 = -1;
    v219 = 0;
    v220 = 0;
    v221 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v211) )
      ex_raise(73, 22, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v211);
    ex_raise(73, 22, 16, 2, v213, v214);
    operator delete[](v215);
    v23 = (unsigned __int8 *)v174;
  }
  WStrLob = CTestHookXmlOutput::GetWStrLob(v164);
  CXVariant::ConvertToOleDbParam(
    (struct CAutoClearXVariant *)((char *)WStrLob + 8),
    v23 + 80,
    0x50u,
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim,
    0,
    0,
    0,
    1);
  v414 = &CAutoClearXVariant::`vftable';
  v419 = CTypeInfo::tiBoolNotNull;
  v420 = xmmword_1031F94F0;
  v416 = 0;
  LOBYTE(v419) = _mm_cvtsi128_si32(CTypeInfo::tiBoolNotNull);
  v415[1] = v419;
  v417 = 0;
  v418 = 0;
  LOBYTE(v417) = 1;
  v415[0] = 0;
  CXVariant::ConvertToOleDbParam(
    (CXVariant *)v415,
    v23 + 160,
    0x50u,
    (const struct CTypeInfo *)&CTypeInfo::tiBoolNotNull,
    0,
    0,
    0,
    1);
  *(_DWORD *)(v179 + 4) = 1;
  v178 = 1;
  v168 = 0;
  v38 = (struct IAccessor *)COledbConnect::GetInterface(a2, &IID_IAccessor, v146, &IID_IUnknown, 1);
  v168 = v38;
  v39 = COleDbParams::HrCreateDBPARAM((COleDbParams *)&v169, &v428, v38);
  if ( v39 < 0 )
  {
    _mm_lfence();
    v40 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v41 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v350[0] = v38;
    v350[1] = &IID_IAccessor;
    v351 = v39;
    v352 = v41;
    v353 = v40;
    v354 = 0;
    v355 = 0;
    v356 = 0;
    v357 = -1;
    v358 = 0;
    v359 = 0;
    v360 &= ~1u;
    COledbError::RaiseCreateParamAccError((COledbError *)v350);
    operator delete[](v354);
  }
  v141 = 0;
  v198 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v277, 1);
  v146 = (struct IUnknown *)&v279;
  v282 = 536871506;
  v283 = 0;
  v285 = 0;
  v284 = 0;
  v286 = 0;
  v287 = 0;
  v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v43 = *(_QWORD *)(v42 + 256);
  if ( !v43 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v43 = *(_QWORD *)(v42 + 256);
  }
  v44 = *(_QWORD *)(v43 + 600);
  if ( v44 )
    v287 = (unsigned int)SOS_Task::PushWait(v44, &v282) == 0;
  v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v46 = *(_QWORD *)(v45 + 256);
  if ( !v46 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v46 = *(_QWORD *)(v45 + 256);
  }
  v281 = v46;
  v280 = (*(_DWORD *)(v46 + 800) >> 11) & 1;
  if ( v280 || (*(_BYTE *)(v46 + 800) & 4) == 0 )
  {
    v279 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v46 + 608) + 8LL))(*(_QWORD *)(v46 + 608));
  }
  else
  {
    v279 = 0;
  }
  v178 = 0;
  v47 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 128LL);
  v408 = v47;
  v407 = 0x1000000;
  v406 = *(_BYTE *)(v47 + 79) & 1;
  v48 = v406;
  *(_DWORD *)(v47 + 76) |= 0x1000000u;
  v49 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct tagDBPARAMS *, __int64 *, struct IUnknown **))v148->lpVtbl[1].AddRef)(
          v148,
          0,
          &IID_IRowset,
          &v428,
          &v198,
          &v141);
  v50 = *(_DWORD *)(v47 + 76);
  if ( v48 )
    v51 = v50 | 0x1000000;
  else
    v51 = v50 & 0xFEFFFFFF;
  *(_DWORD *)(v47 + 76) = v51;
  v146 = (struct IUnknown *)&v279;
  if ( v279 )
  {
    if ( v280 )
      *(_DWORD *)(v281 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v281 + 608) + 16LL))(
        *(_QWORD *)(v281 + 608),
        v281,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v282);
  *(_DWORD *)(v278 + 616) &= ~v277;
  if ( v49 < 0 )
  {
    _mm_lfence();
    v52 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v53 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v180[0] = v148;
    v180[1] = &IID_ICommandText;
    v182 = v53;
    v183 = v52;
    v184 = 0;
    v185 = 0;
    v186 = 0;
    v187 = -1;
    v188 = 0;
    v189 = 0;
    v190 &= ~1u;
    v181 = v49;
    if ( COledbError::FPrintSQLServerError((COledbError *)v180) && v189 == 1 )
    {
      if ( v186 > 10 )
      {
        if ( (v190 & 1) != 0 )
          COledbError::SendOriginalErrorInStretchTelemetry(v180, 0);
        ex_raise(73, 20, 25, 1);
      }
    }
    else
    {
      COledbError::PrintMsgUsingHRESULT((COledbError *)v180);
      memset_0(v438, 0, 0x1F42u);
      if ( v181 == -2147217887 )
      {
        COledbError::GatherPropsInError((COledbError *)v180, &v152, &v143);
        LODWORD(SizeInWords) = 4001;
        v54 = v143;
        v55 = v152;
        COledbError::CwchFormatPropertyUser((COledbError *)v180, v152, v143, v438, SizeInWords);
        if ( (_DWORD)v55 )
        {
          p_bstrVal = &v54->vValue.bstrVal;
          do
          {
            if ( *((_WORD *)p_bstrVal - 4) == 8 )
              SysFreeString(*p_bstrVal);
            p_bstrVal += 9;
            --v55;
          }
          while ( v55 );
        }
        ((void (__fastcall *)(LPMALLOC, struct tagDBPROP *))ppMalloc->lpVtbl->Free)(ppMalloc, v54);
      }
      ex_raise(73, 20, 16, 2, L"sp_execute_memo", v182, v183, v438);
    }
    operator delete[](v184);
  }
  v57 = v141;
  if ( !v141 )
  {
    v58 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v59 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v388 = 0;
    v389 = &IID_IUnknown;
    v390 = 0;
    v391 = v59;
    v392 = v58;
    v393 = 0;
    v394 = 0;
    v395 = 0;
    v396 = -1;
    v397 = 0;
    v398 = 0;
    v399 &= ~1u;
    ex_raise(73, 57, 16, 1, L"sp_execute_memo call", v59, v58);
    operator delete[](0);
    v57 = v141;
  }
  v210 = v57;
  ContextAccessor::GetCurCompatLevel(
    &v156,
    *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset));
  v153 = v156;
  v60 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
  v61 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
  SOledbConnProp::SOledbConnProp(v430, v145, L"EXECUTE", &v153, v61, v60);
  v158 = 0;
  v166 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v266, 1);
  v145 = &v268;
  v271 = 536871506;
  v272 = 0;
  v274 = 0;
  v273 = 0;
  v275 = 0;
  v276 = 0;
  v62 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v63 = *(_QWORD *)(v62 + 256);
  if ( !v63 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v63 = *(_QWORD *)(v62 + 256);
  }
  v64 = *(_QWORD *)(v63 + 600);
  if ( v64 )
    v276 = (unsigned int)SOS_Task::PushWait(v64, &v271) == 0;
  v65 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v66 = *(_QWORD *)(v65 + 256);
  if ( !v66 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v66 = *(_QWORD *)(v65 + 256);
  }
  v270 = v66;
  v269 = (*(_DWORD *)(v66 + 800) >> 11) & 1;
  if ( v269 || (*(_BYTE *)(v66 + 800) & 4) == 0 )
  {
    v268 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v66 + 608) + 8LL))(*(_QWORD *)(v66 + 608));
  }
  else
  {
    v268 = 0;
  }
  v67 = (const wchar_t *)(*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
  v68 = (const wchar_t *)(*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
  GetColumnInfoFromPunk(v141, &v191, &v158, &v166, v68, v67);
  v145 = &v268;
  if ( v268 )
  {
    if ( v269 )
      *(_DWORD *)(v270 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v270 + 608) + 16LL))(
        *(_QWORD *)(v270 + 608),
        v270,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v271);
  *(_DWORD *)(v267 + 616) &= ~v266;
  ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v70 = 8LL * SystemThread_TlsIndex;
  v71 = *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&ThreadLocalStoragePointer[v70]) + 64LL)
                  + 44LL);
  DefaultCollationData = (unsigned int *)CDbAndSetOptsImplImport::GetDefaultCollationData(
                                           (CDbAndSetOptsImplImport *)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&ThreadLocalStoragePointer[v70] + SystemThread_TlsOffset) + 80LL)
                                                                                          + 8LL),
                                           (unsigned __int16)ThreadLocalStoragePointer);
  v73 = UICodePageFromCID(*DefaultCollationData);
  v400[0] = &CColMetaData::`vftable';
  v400[1] = 0;
  v401 = 0;
  v402 = 0;
  v403 = 0;
  v404 = 0;
  v405 = 0;
  v74 = v147;
  CColMetaData::Init((CColMetaData *)v400, v147, v191, v71, v73);
  v434 = *v158;
  CiFromDbCol(v429, &v434, 0, v430);
  v409[0] = 1;
  v409[1] = 0;
  v409[2] = 0;
  v409[3] = 8;
  v409[4] = 0;
  v409[5] = &v435;
  v409[6] = 0;
  v409[7] = 5;
  v410 = 0;
  v411 = 0;
  v412 = 0;
  v413 = 13;
  v435 = 0;
  v436 = IID_ISequentialStream;
  v192 = 0;
  v75 = COledbConnect::GetInterface(a2, &IID_IAccessor, v141, &IID_IUnknown, 1);
  v145 = (int *)v75;
  v192 = v75;
  v157 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v288, 1);
  v143 = (struct tagDBPROP *)&v290;
  v293 = 536871420;
  v294 = 0;
  v296 = 0;
  v295 = 0;
  v297 = 0;
  v298 = 0;
  v76 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v77 = *(_QWORD *)(v76 + 256);
  if ( !v77 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v77 = *(_QWORD *)(v76 + 256);
  }
  v78 = *(_QWORD *)(v77 + 600);
  if ( v78 )
    v298 = (unsigned int)SOS_Task::PushWait(v78, &v293) == 0;
  v79 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v80 = *(_QWORD *)(v79 + 256);
  if ( !v80 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v80 = *(_QWORD *)(v79 + 256);
  }
  v292 = v80;
  v291 = (*(_DWORD *)(v80 + 800) >> 11) & 1;
  if ( v291 || (*(_BYTE *)(v80 + 800) & 4) == 0 )
  {
    v290 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v80 + 608) + 8LL))(*(_QWORD *)(v80 + 608));
  }
  else
  {
    v290 = 0;
  }
  v81 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD *, __int64, __int64 *, _QWORD))v75->lpVtbl[1].AddRef)(
          v75,
          2,
          1,
          v409,
          12,
          &v157,
          0);
  v143 = (struct tagDBPROP *)&v290;
  if ( v290 )
  {
    if ( v291 )
      *(_DWORD *)(v292 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v292 + 608) + 16LL))(
        *(_QWORD *)(v292 + 608),
        v292,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v293);
  *(_DWORD *)(v289 + 616) &= ~v288;
  if ( v81 < 0 )
  {
    _mm_lfence();
    v82 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v83 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v361[0] = v75;
    v361[1] = &IID_IAccessor;
    v362 = v81;
    v363 = v83;
    v364 = v82;
    v365 = 0;
    v366 = 0;
    v367 = 0;
    v368 = -1;
    v369 = 0;
    v370 = 0;
    v371 &= ~1u;
    COledbError::RaiseMultipleGetAccessorError((COledbError *)v361);
    operator delete[](v365);
  }
  v84 = (unsigned int *)operator new[](0xCu, v74, "sql\\ntdbms\\query\\qeexec\\qspbcommon.cpp", 322, 1u);
  v146 = (struct IUnknown *)v84;
  v422 = v84;
  v163 = 0;
  v165 = &v163;
  v193 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v299, 1);
  v143 = (struct tagDBPROP *)&v301;
  v304 = 536871424;
  v305 = 0;
  v307 = 0;
  v306 = 0;
  v308 = 0;
  v309 = 0;
  v85 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v86 = *(_QWORD *)(v85 + 256);
  if ( !v86 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v86 = *(_QWORD *)(v85 + 256);
  }
  v87 = *(_QWORD *)(v86 + 600);
  if ( v87 )
    v309 = (unsigned int)SOS_Task::PushWait(v87, &v304) == 0;
  v88 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v89 = *(_QWORD *)(v88 + 256);
  if ( !v89 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v89 = *(_QWORD *)(v88 + 256);
  }
  v303 = v89;
  v302 = (*(_DWORD *)(v89 + 800) >> 11) & 1;
  if ( v302 || (*(_BYTE *)(v89 + 800) & 4) == 0 )
  {
    v301 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v89 + 608) + 8LL))(*(_QWORD *)(v89 + 608));
  }
  else
  {
    v301 = 0;
  }
  v90 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, __int64, __int64 *, __int64 **))v141->lpVtbl[1].Release)(
          v141,
          0,
          0,
          1,
          &v193,
          &v165);
  v143 = (struct tagDBPROP *)&v301;
  if ( v301 )
  {
    if ( v302 )
      *(_DWORD *)(v303 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v303 + 608) + 16LL))(
        *(_QWORD *)(v303 + 608),
        v303,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v304);
  *(_DWORD *)(v300 + 616) &= ~v299;
  if ( v90 < 0 )
  {
    v91 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v92 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v222[0] = v141;
    v222[1] = &IID_IRowset;
    v223 = v90;
    v224 = v92;
    v225 = v91;
    v226 = 0;
    v227 = 0;
    v228 = 0;
    v229 = -1;
    v230 = 0;
    v231 = 0;
    v232 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v222) )
      ex_raise(73, 30, 25, 1, 0);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v222);
    ex_raise(73, 30, 16, 2, v224, v225);
    operator delete[](v226);
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v310, 1);
  v143 = (struct tagDBPROP *)&v312;
  v315 = 536871423;
  v316 = 0;
  v318 = 0;
  v317 = 0;
  v319 = 0;
  v320 = 0;
  v93 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v94 = *(_QWORD *)(v93 + 256);
  if ( !v94 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v94 = *(_QWORD *)(v93 + 256);
  }
  v95 = *(_QWORD *)(v94 + 600);
  if ( v95 )
    v320 = (unsigned int)SOS_Task::PushWait(v95, &v315) == 0;
  v96 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v97 = *(_QWORD *)(v96 + 256);
  if ( !v97 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v97 = *(_QWORD *)(v96 + 256);
  }
  v314 = v97;
  v313 = (*(_DWORD *)(v97 + 800) >> 11) & 1;
  if ( v313 || (*(_BYTE *)(v97 + 800) & 4) == 0 )
  {
    v312 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v97 + 608) + 8LL))(*(_QWORD *)(v97 + 608));
  }
  else
  {
    v312 = 0;
  }
  v98 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, unsigned int *))v141->lpVtbl[1].AddRef)(
          v141,
          v163,
          v157,
          v84);
  v143 = (struct tagDBPROP *)&v312;
  if ( v312 )
  {
    if ( v313 )
      *(_DWORD *)(v314 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v314 + 608) + 16LL))(
        *(_QWORD *)(v314 + 608),
        v314,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v315);
  *(_DWORD *)(v311 + 616) &= ~v310;
  if ( v98 < 0 )
  {
    _mm_lfence();
    v99 = *v84;
    LODWORD(v155) = 259;
    v100 = v147;
    v101 = operator new(0xA0u, v147, "sql\\ntdbms\\query\\qecomp\\kstr.cpp", 259, 1u);
    v102 = (__int64 (__fastcall ***)(_QWORD, LPOLESTR, _QWORD))v101;
    v164 = (CTestHookXmlOutput *)v101;
    if ( v101 )
    {
      *(_QWORD *)v101 = &CQNameManagerImp::`vftable';
      *((_DWORD *)v101 + 2) = 0;
      *((_OWORD *)v101 + 1) = 0;
      *((_OWORD *)v101 + 2) = 0;
      *((_OWORD *)v101 + 3) = 0;
      *((_OWORD *)v101 + 4) = 0;
      *((_OWORD *)v101 + 5) = 0;
      *((_OWORD *)v101 + 6) = 0;
      *((_OWORD *)v101 + 7) = 0;
      *((_OWORD *)v101 + 8) = 0;
      *((_QWORD *)v101 + 18) = v100;
      *((_DWORD *)v101 + 38) = 1000;
    }
    else
    {
      v102 = 0;
    }
    v103 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v104 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v372[0] = v141;
    v372[1] = &IID_IRowset;
    v373 = v98;
    v374 = v104;
    v375 = v103;
    v376 = 0;
    v377 = 0;
    v378 = 0;
    v379 = -1;
    v380 = 0;
    v381 = 0;
    v382 &= ~1u;
    v105 = (const struct CQName *)(**v102)(v102, v434.pwszName, 0);
    COledbError::RaiseGetDataError((COledbError *)v372, v105, v106, v99);
    operator delete[](v376);
  }
  v343 = &CAutoClearXVariant::`vftable';
  v348 = CTypeInfo::tiVarWstrUnlim;
  v349 = xmmword_103369300;
  v345 = 0;
  v344[0] = 3;
  LOBYTE(v348) = _mm_cvtsi128_si32(CTypeInfo::tiVarWstrUnlim);
  v344[1] = v348;
  v346 = 0;
  v347 = 0;
  v107 = IBHFDispenser::PbhfDispenseBHF(*(IBHFDispenser **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                    + SystemThread_TlsIndex)
                                                                                  + SystemThread_TlsOffset)
                                                                      + 128LL)
                                                          + 264LL));
  v144 = 96;
  v108 = operator new[](0x60u, v147, "sql\\ntdbms\\query\\qeexec\\qspbcommon.cpp", 358, 1u);
  v194 = v108;
  (**(void (__fastcall ***)(struct IBlobHandleFactory *, void *, unsigned int *, _QWORD))v107)(v107, v108, &v144, 0);
  *(_QWORD *)&v346 = v108;
  *((_QWORD *)&v346 + 1) = v144;
  v194 = 0;
  v344[0] = 0;
  v345 |= 1u;
  v109 = 0;
  v195 = (struct ILockBytesSS *)(*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v108 + 8LL))(v108, 0);
  CWriterLockBytes::CWriterLockBytes((CWriterLockBytes *)&v383, v195);
  v142 = 0;
  v110 = *(_QWORD *)v84;
  v111 = v161;
  do
  {
    v112 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, unsigned int *))(*(_QWORD *)v110 + 24LL))(
             v110,
             v437,
             8000,
             &v142);
    if ( v112 < 0 )
    {
      v113 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
      v114 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v233[0] = v111;
      v233[1] = &IID_ISequentialStream;
      v234 = v112;
      v235 = v114;
      v236 = v113;
      v237 = 0;
      v238 = 0;
      v239 = 0;
      v240 = -1;
      v241 = 0;
      v242 = 0;
      v243 &= ~1u;
      if ( COledbError::FPrintSQLServerError((COledbError *)v233) )
        ex_raise(73, 5, 25, 1);
      COledbError::PrintMsgUsingHRESULT((COledbError *)v233);
      ex_raise(73, 5, 16, 2, v235, v236);
      operator delete[](v237);
    }
    v115 = v142;
    if ( v142 )
    {
      v109 += v142;
      CWriterLockBytes::WriteStream((CWriterLockBytes *)&v383, v437, v142);
      v115 = v142;
    }
  }
  while ( v115 >= 0x1F40 );
  v116 = v384;
  v117 = v386;
  v118 = v145;
  if ( v386 )
  {
    v119 = v387;
    if ( v387 )
    {
      v154 = 0;
      v120 = v385;
      v121 = (*(__int64 (__fastcall **)(__int64, __int64, void *, _QWORD, int *))(*(_QWORD *)v384 + 32LL))(
               v384,
               v385,
               v386,
               v387,
               &v154);
      if ( v121 )
      {
        LODWORD(SizeInWordsa) = v121;
        ex_raise(86, 30, 17, 40, SizeInWordsa);
      }
      v385 = v119 + v120;
      v387 = 0;
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 160LL))(v116);
  v383 = &CWriterLockBytes::`vftable';
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
  operator delete[](v117);
  v386 = 0;
  if ( v195 )
    (*(void (__fastcall **)(struct ILockBytesSS *))(*(_QWORD *)v195 + 16LL))(v195);
  v122 = v109 >> 1;
  v123 = 2 * (v122 + 2);
  if ( !is_mul_ok(v122 + 2, 2u) )
    v123 = -1;
  v124 = (unsigned __int8 *)operator new[](v123, v147, "sql\\ntdbms\\query\\qeexec\\qspbcommon.cpp", 417, 1u);
  v125 = v196;
  *(_QWORD *)v196 = v124;
  CXVariant::CopyOut((CXVariant *)v344, v124, (const struct CTypeInfo *)v429, 0);
  *(_WORD *)(*(_QWORD *)v125 + 2 * v122) = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v321, 1);
  v149 = &v323;
  v326 = 536871437;
  v327 = 0;
  v329 = 0;
  v328 = 0;
  v330 = 0;
  v331 = 0;
  v126 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v127 = *(_QWORD *)(v126 + 256);
  if ( !v127 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v127 = *(_QWORD *)(v126 + 256);
  }
  v128 = *(_QWORD *)(v127 + 600);
  if ( v128 )
    v331 = (unsigned int)SOS_Task::PushWait(v128, &v326) == 0;
  v129 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v130 = *(_QWORD *)(v129 + 256);
  if ( !v130 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v130 = *(_QWORD *)(v129 + 256);
  }
  v325 = v130;
  v324 = (*(_DWORD *)(v130 + 800) >> 11) & 1;
  if ( v324 || (*(_BYTE *)(v130 + 800) & 4) == 0 )
  {
    v323 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v130 + 608) + 8LL))(*(_QWORD *)(v130 + 608));
  }
  else
  {
    v323 = 0;
  }
  v131 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))v141->lpVtbl[2].QueryInterface)(v141, 1, v165);
  v149 = &v323;
  if ( v323 )
  {
    if ( v324 )
      *(_DWORD *)(v325 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v325 + 608) + 16LL))(
        *(_QWORD *)(v325 + 608),
        v325,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v326);
  *(_DWORD *)(v322 + 616) &= ~v321;
  if ( v131 < 0 )
  {
    v132 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v133 = (*(__int64 (__fastcall **)(struct CShowplanXMLContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v244[0] = v118;
    v244[1] = &IID_IAccessor;
    v245 = v131;
    v246 = v133;
    v247 = v132;
    v248 = 0;
    v249 = 0;
    v250 = 0;
    v251 = -1;
    v252 = 0;
    v253 = 0;
    v254 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v244) )
      ex_raise(73, 31, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v244);
    ex_raise(73, 31, 16, 2, v246, v247);
    operator delete[](v248);
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v332, 1);
  v149 = &v334;
  v337 = 536871436;
  v338 = 0;
  v340 = 0;
  v339 = 0;
  v341 = 0;
  v342 = 0;
  v134 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v135 = *(_QWORD *)(v134 + 256);
  if ( !v135 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v135 = *(_QWORD *)(v134 + 256);
  }
  v136 = *(_QWORD *)(v135 + 600);
  if ( v136 )
    v342 = (unsigned int)SOS_Task::PushWait(v136, &v337) == 0;
  v137 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v138 = *(_QWORD *)(v137 + 256);
  if ( !v138 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v138 = *(_QWORD *)(v137 + 256);
  }
  v336 = v138;
  v335 = (*(_DWORD *)(v138 + 800) >> 11) & 1;
  if ( v335 || (*(_BYTE *)(v138 + 800) & 4) == 0 )
  {
    v334 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v138 + 608) + 8LL))(*(_QWORD *)(v138 + 608));
  }
  else
  {
    v334 = 0;
  }
  (*(void (__fastcall **)(int *, __int64, _QWORD))(*(_QWORD *)v118 + 48LL))(v118, v157, 0);
  v149 = &v334;
  if ( v334 )
  {
    if ( v335 )
      *(_DWORD *)(v336 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v336 + 608) + 16LL))(
        *(_QWORD *)(v336 + 608),
        v336,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v337);
  *(_DWORD *)(v333 + 616) &= ~v332;
  operator delete[](0);
  CAutoClearXVariant::~CAutoClearXVariant(&v343);
  operator delete(v146, 1u);
  (*(void (__fastcall **)(int *))(*(_QWORD *)v118 + 16LL))(v118);
  CColMetaData::~CColMetaData((CColMetaData *)v400);
  ((void (__fastcall *)(LPMALLOC, wchar_t *))ppMalloc->lpVtbl->Free)(ppMalloc, v166);
  ((void (__fastcall *)(LPMALLOC, struct tagDBCOLUMNINFO *))ppMalloc->lpVtbl->Free)(ppMalloc, v158);
  if ( v210 )
    ((void (__fastcall *)(struct IUnknown *))v210->lpVtbl->Release)(v210);
  if ( v168 )
    ((void (__fastcall *)(struct IAccessor *))v168->lpVtbl->Release)(v168);
  CAutoClearXVariant::~CAutoClearXVariant(&v414);
  COleDbParams::~COleDbParams((COleDbParams *)&v169);
  if ( v162 )
    ((void (__fastcall *)(struct IUnknown *))v162->lpVtbl->Release)(v162);
  ((void (__fastcall *)(LPMALLOC, struct tagDBPROP *))ppMalloc->lpVtbl->Free)(ppMalloc, v159);
  if ( v167 )
    ((void (__fastcall *)(struct IUnknown *))v167->lpVtbl->Release)(v167);
  if ( v148 )
    ((void (__fastcall *)(struct IUnknown *))v148->lpVtbl->Release)(v148);
  if ( v160 )
    ((void (__fastcall *)(struct IUnknown *))v160->lpVtbl->Release)(v160);
  if ( v161 )
    ((void (__fastcall *)(struct IUnknown *))v161->lpVtbl->Release)(v161);
  if ( Session )
    CRemSess::ReleaseSession((CRemSess *)Session, 0, 0);
}

```

## disassembly

```asm
0x100d1dc90  push    rbp
0x100d1dc92  push    rbx
0x100d1dc93  push    rsi
0x100d1dc94  push    rdi
0x100d1dc95  push    r12
0x100d1dc97  push    r13
0x100d1dc99  push    r14
0x100d1dc9b  push    r15
0x100d1dc9d  lea     rbp, [rsp-4878h]
0x100d1dca5  mov     eax, 4978h
0x100d1dcaa  call    _alloca_probe
0x100d1dcaf  sub     rsp, rax
0x100d1dcb2  mov     [rbp+48B0h+var_4060], 0FFFFFFFFFFFFFFFEh
0x100d1dcbd  mov     rax, cs:__security_cookie
0x100d1dcc4  xor     rax, rsp
0x100d1dcc7  mov     [rbp+48B0h+var_50], rax
0x100d1dcce  mov     [rsp+49B0h+var_4950], r9
0x100d1dcd3  mov     [rbp+48B0h+var_48C8], r8
0x100d1dcd7  mov     rsi, rdx
0x100d1dcda  mov     rax, [rbp+48B0h+arg_20]
0x100d1dce1  mov     [rbp+48B0h+var_47C8], rax
0x100d1dce8  mov     r13, [rcx+18h]
0x100d1dcec  mov     [rsp+49B0h+var_4940], r13
0x100d1dcf1  mov     [rbp+48B0h+var_4930], r13
0x100d1dcf5  xor     edx, edx
0x100d1dcf7  mov     rcx, rsi
0x100d1dcfa  call    cs:__imp_?GetSession@COledbConnect@@QEBAPEAVCRemSess@@_N@Z; COledbConnect::GetSession(bool)
0x100d1dd00  mov     [rbp+48B0h+var_47C0], rax
0x100d1dd07  xor     ebx, ebx
0x100d1dd09  mov     [rbp+48B0h+var_48E0], rbx
0x100d1dd0d  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1dd12  lea     r9, IID_IUnknown
0x100d1dd19  mov     r8, [rax+28h]
0x100d1dd1d  lea     r12, IID_IDBCreateCommand
0x100d1dd24  mov     rdx, r12
0x100d1dd27  mov     rcx, rsi
0x100d1dd2a  call    cs:__imp_?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100d1dd30  mov     rdi, rax
0x100d1dd33  mov     [rbp+48B0h+var_48E0], rax
0x100d1dd37  mov     [rbp+48B0h+var_48E8], rbx
0x100d1dd3b  mov     r10, [rax]
0x100d1dd3e  lea     r9, [rbp+48B0h+var_48E8]
0x100d1dd42  lea     r8, IID_ICommandText
0x100d1dd49  xor     edx, edx
0x100d1dd4b  mov     rcx, rax
0x100d1dd4e  call    qword ptr [r10+18h]
0x100d1dd52  mov     r15d, eax
0x100d1dd55  lea     r14, [rbx-1]
0x100d1dd59  test    eax, eax
0x100d1dd5b  jns     loc_100D1DE39
0x100d1dd61  lfence
0x100d1dd64  mov     rdx, [rsi]
0x100d1dd67  mov     rcx, rsi
0x100d1dd6a  call    qword ptr [rdx+28h]
0x100d1dd6d  mov     rbx, rax
0x100d1dd70  mov     rdx, [rsi]
0x100d1dd73  mov     rcx, rsi
0x100d1dd76  call    qword ptr [rdx+18h]
0x100d1dd79  mov     [rbp+48B0h+var_47B0], rdi
0x100d1dd80  mov     [rbp+48B0h+var_47A8], r12
0x100d1dd87  mov     [rbp+48B0h+var_47A0], r15d
0x100d1dd8e  mov     [rbp+48B0h+var_4798], rax
0x100d1dd95  mov     [rbp+48B0h+var_4790], rbx
0x100d1dd9c  xor     ebx, ebx
0x100d1dd9e  mov     [rbp+48B0h+var_4788], rbx
0x100d1dda5  mov     [rbp+48B0h+var_4780], rbx
0x100d1ddac  mov     [rbp+48B0h+var_4778], ebx
0x100d1ddb2  mov     [rbp+48B0h+var_4774], r14d
0x100d1ddb9  mov     [rbp+48B0h+var_4770], rbx
0x100d1ddc0  mov     [rbp+48B0h+var_4768], ebx
0x100d1ddc6  and     [rbp+48B0h+var_4764], 0FEh
0x100d1ddcd  lea     rcx, [rbp+48B0h+var_47B0]; this
0x100d1ddd4  call    ?FPrintSQLServerError@COledbError@@AEAA_NXZ; COledbError::FPrintSQLServerError(void)
0x100d1ddd9  test    al, al
0x100d1dddb  jz      short loc_100D1DDF1
0x100d1dddd  lea     edx, [rbx+5]
0x100d1dde0  lea     ecx, [rbx+49h]
0x100d1dde3  lea     r9d, [r14+2]
0x100d1dde7  lea     r8d, [r14+1Ah]
0x100d1ddeb  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100d1ddf1  lea     rcx, [rbp+48B0h+var_47B0]; this
0x100d1ddf8  call    ?PrintMsgUsingHRESULT@COledbError@@AEAAXXZ; COledbError::PrintMsgUsingHRESULT(void)
0x100d1ddfd  mov     rax, [rbp+48B0h+var_4790]
0x100d1de04  mov     [rsp+49B0h+var_4988], rax
0x100d1de09  mov     rax, [rbp+48B0h+var_4798]
0x100d1de10  mov     [rsp+49B0h+SizeInWords], rax
0x100d1de15  mov     edx, 5
0x100d1de1a  lea     ecx, [rdx+44h]
0x100d1de1d  lea     r9d, [rdx-3]
0x100d1de21  lea     r8d, [rdx+0Bh]
0x100d1de25  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100d1de2b  nop
0x100d1de2c  mov     rcx, [rbp+48B0h+var_4788]
0x100d1de33  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100d1de39  mov     [rsp+49B0h+var_4938], rbx
0x100d1de3e  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1de43  lea     r9, IID_IUnknown
0x100d1de4a  mov     r8, [rbp+48B0h+var_48E8]
0x100d1de4e  lea     rdx, IID_ICommandText
0x100d1de55  mov     rcx, rsi
0x100d1de58  call    cs:__imp_?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100d1de5e  mov     r12, rax
0x100d1de61  mov     [rsp+49B0h+var_4948], rax
0x100d1de66  mov     [rsp+49B0h+var_4938], rax
0x100d1de6b  mov     r9, [rax]
0x100d1de6e  lea     r8, aCallSpExecuteM_0; "{? = call sp_execute_memo(?,?)}"
0x100d1de75  lea     rdx, DBGUID_SQL
0x100d1de7c  mov     rcx, rax
0x100d1de7f  call    qword ptr [r9+38h]
0x100d1de83  mov     [rbp+48B0h+var_48B0], rbx
0x100d1de87  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1de8c  lea     r9, IID_IUnknown
0x100d1de93  mov     r8, r12
0x100d1de96  lea     rdx, IID_ICommandProperties
0x100d1de9d  mov     rcx, rsi
0x100d1dea0  call    cs:__imp_?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100d1dea6  mov     r14, rax
0x100d1dea9  mov     [rbp+48B0h+var_48B0], rax
0x100d1dead  mov     [rbp+48B0h+var_48F0], rbx
0x100d1deb1  mov     [rbp+48B0h+var_4924], 89h
0x100d1deb8  mov     [rbp+48B0h+var_4928], ebx
0x100d1debb  mov     rdx, [rsi]
0x100d1debe  mov     rcx, rsi
0x100d1dec1  call    qword ptr [rdx+18h]
0x100d1dec4  lea     rax, DBPROPSET_ROWSET
0x100d1decb  mov     [rsp+49B0h+var_4980], rax; struct _GUID *
0x100d1ded0  lea     rax, [rbp+48B0h+var_48F0]
0x100d1ded4  mov     [rsp+49B0h+var_4988], rax; struct tagDBPROP **
0x100d1ded9  lea     rax, [rbp+48B0h+var_4928]
0x100d1dedd  mov     [rsp+49B0h+SizeInWords], rax; unsigned int *
0x100d1dee2  lea     r9, [rbp+48B0h+var_4924]; unsigned int *
0x100d1dee6  mov     r8d, 1; unsigned int
0x100d1deec  mov     rcx, r14; struct IUnknown *
0x100d1deef  call    ?FGetRowsetProperties@@YAHPEAUIUnknown@@PEB_WKPEAK2PEAPEAUtagDBPROP@@AEBU_GUID@@@Z; FGetRowsetProperties(IUnknown *,wchar_t const *,ulong,ulong *,ulong *,tagDBPROP * *,_GUID const &)
0x100d1def4  test    eax, eax
0x100d1def6  jnz     loc_100D1DFDB
0x100d1defc  mov     rax, [rsi]
0x100d1deff  mov     rcx, rsi
0x100d1df02  call    qword ptr [rax+28h]
0x100d1df05  mov     rbx, rax
0x100d1df08  mov     rdx, [rsi]
0x100d1df0b  mov     rcx, rsi
0x100d1df0e  call    qword ptr [rdx+18h]
0x100d1df11  mov     [rbp+48B0h+var_4610], rdi
0x100d1df18  lea     rcx, IID_ICommandProperties
0x100d1df1f  mov     [rbp+48B0h+var_4608], rcx
0x100d1df26  mov     [rbp+48B0h+var_4600], r15d
0x100d1df2d  mov     [rbp+48B0h+var_45F8], rax
0x100d1df34  mov     [rbp+48B0h+var_45F0], rbx
0x100d1df3b  xor     ebx, ebx
0x100d1df3d  mov     [rbp+48B0h+var_45E8], rbx
0x100d1df44  mov     [rbp+48B0h+var_45E0], rbx
0x100d1df4b  mov     [rbp+48B0h+var_45D8], ebx
0x100d1df51  mov     [rbp+48B0h+var_45D4], 0FFFFFFFFh
0x100d1df5b  mov     [rbp+48B0h+var_45D0], rbx
0x100d1df62  mov     [rbp+48B0h+var_45C8], ebx
0x100d1df68  and     [rbp+48B0h+var_45C4], 0FEh
0x100d1df6f  lea     rcx, [rbp+48B0h+var_4610]; this
0x100d1df76  call    ?FPrintSQLServerError@COledbError@@AEAA_NXZ; COledbError::FPrintSQLServerError(void)
0x100d1df7b  test    al, al
0x100d1df7d  jz      short loc_100D1DF93
0x100d1df7f  lea     edx, [rbx+5]
0x100d1df82  lea     ecx, [rbx+49h]
0x100d1df85  lea     r9d, [rbx+1]
0x100d1df89  lea     r8d, [rbx+19h]
0x100d1df8d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100d1df93  lea     rcx, [rbp+48B0h+var_4610]; this
0x100d1df9a  call    ?PrintMsgUsingHRESULT@COledbError@@AEAAXXZ; COledbError::PrintMsgUsingHRESULT(void)
0x100d1df9f  mov     rax, [rbp+48B0h+var_45F0]
0x100d1dfa6  mov     [rsp+49B0h+var_4988], rax
0x100d1dfab  mov     rax, [rbp+48B0h+var_45F8]
0x100d1dfb2  mov     [rsp+49B0h+SizeInWords], rax
0x100d1dfb7  mov     edx, 5
0x100d1dfbc  lea     ecx, [rdx+44h]
0x100d1dfbf  lea     r9d, [rdx-3]
0x100d1dfc3  lea     r8d, [rdx+0Bh]
0x100d1dfc7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100d1dfcd  nop
0x100d1dfce  mov     rcx, [rbp+48B0h+var_45E8]
0x100d1dfd5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100d1dfdb  mov     rax, [rbp+48B0h+var_48F0]
0x100d1dfdf  mov     [rbp+48B0h+var_3F70], rax
0x100d1dfe6  mov     [rbp+48B0h+var_3F68], 1
0x100d1dff0  movups  xmm0, xmmword ptr cs:DBPROPSET_SQLSERVERSTREAM.Data1
0x100d1dff7  movups  [rbp+48B0h+var_3F64], xmm0
0x100d1dffe  mov     rax, [r14]
0x100d1e001  lea     r8, [rbp+48B0h+var_3F70]
0x100d1e008  mov     edx, 1
0x100d1e00d  mov     rcx, r14
0x100d1e010  call    qword ptr [rax+20h]
0x100d1e013  mov     [rbp+48B0h+var_48D8], rbx
0x100d1e017  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1e01c  lea     r9, IID_IUnknown
0x100d1e023  mov     r8, r12
0x100d1e026  lea     rdx, IID_ICommandWithParameters
0x100d1e02d  mov     rcx, rsi
0x100d1e030  call    cs:__imp_?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100d1e036  mov     [rbp+48B0h+var_4910], rax
0x100d1e03a  mov     [rbp+48B0h+var_48D8], rax
0x100d1e03e  mov     [rbp+48B0h+var_48A0], r13
0x100d1e042  mov     [rbp+48B0h+var_4898], ebx
0x100d1e045  mov     [rbp+48B0h+var_4870], rbx
0x100d1e049  mov     [rbp+48B0h+var_4878], rbx
0x100d1e04d  xorps   xmm0, xmm0
0x100d1e050  movdqa  [rbp+48B0h+var_4890], xmm0
0x100d1e055  mov     [rbp+48B0h+var_4880], rbx
0x100d1e059  mov     [rbp+48B0h+var_4868], rbx
0x100d1e05d  mov     [rbp+48B0h+var_4860], rbx
0x100d1e061  mov     [rbp+48B0h+var_4858], 1
0x100d1e068  mov     [rbp+48B0h+var_4854], 1
0x100d1e06f  mov     [rbp+48B0h+var_4850], rbx
0x100d1e073  mov     edx, 3; unsigned int
0x100d1e078  lea     rcx, [rbp+48B0h+var_48A0]; this
0x100d1e07c  call    ?Init@COleDbParams@@QEAAXK@Z; COleDbParams::Init(ulong)
0x100d1e081  mov     r15, [rbp+48B0h+var_48A0]
0x100d1e085  mov     r12, [rbp+48B0h+var_4860]
0x100d1e089  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e090  cmp     al, 62h ; 'b'
0x100d1e092  jnz     short loc_100D1E0C6
0x100d1e094  cmp     qword ptr [r12], 0
0x100d1e099  jnz     short loc_100D1E0CE
0x100d1e09b  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1e0a0  mov     r9d, 1FFh
0x100d1e0a6  lea     r8, aSqlNtdbmsQuery_214; "sql\\ntdbms\\query\\qpshared\\oledbutl."...
0x100d1e0ad  mov     rdx, r15
0x100d1e0b0  mov     ecx, 1F78h
0x100d1e0b5  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100d1e0bb  mov     [r12], rax
0x100d1e0bf  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e0c6  cmp     al, 1Fh
0x100d1e0c8  jz      short loc_100D1E0D7
0x100d1e0ca  test    al, al
0x100d1e0cc  jz      short loc_100D1E0D7
0x100d1e0ce  lea     rdx, ?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e0d5  jmp     short loc_100D1E0DE
0x100d1e0d7  lea     rdx, ?tiEmpty@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiEmpty
0x100d1e0de  mov     r9d, 1
0x100d1e0e4  mov     rbx, [rbp+48B0h+var_4878]
0x100d1e0e8  mov     r8d, r9d
0x100d1e0eb  mov     rcx, rbx
0x100d1e0ee  call    cs:__imp_?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z; InitDbBind(tagDBBINDING *,CTypeInfo const &,int,int)
0x100d1e0f4  mov     eax, 0FFFFh
0x100d1e0f9  mov     r13d, 0Dh
0x100d1e0ff  lea     r8, ?x_dbobjSequentialStream@@3UtagDBOBJECT@@A; tagDBOBJECT x_dbobjSequentialStream
0x100d1e106  lea     rdx, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x100d1e10d  cmp     word ptr cs:xmmword_1031D5690, ax
0x100d1e114  jz      short loc_100D1E12F
0x100d1e116  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e11d  movzx   ecx, byte ptr [rax+rdx+240BEE0h]
0x100d1e125  cmp     byte ptr [rcx+rdx+2D99708h], 0
0x100d1e12d  jz      short loc_100D1E14C
0x100d1e12f  mov     [rbx+54h], r13w
0x100d1e134  mov     qword ptr [rbx+48h], 7FFFFFFFh
0x100d1e13c  or      dword ptr [rbx+38h], 2
0x100d1e140  mov     qword ptr [rbx+10h], 8
0x100d1e148  mov     [rbx+28h], r8
0x100d1e14c  mov     dword ptr [rbx+3Ch], 0
0x100d1e153  mov     qword ptr [rbx], 1
0x100d1e15a  or      dword ptr [rbx+40h], 3
0x100d1e15e  mov     rdi, qword ptr [rbp+48B0h+var_4890]
0x100d1e162  mov     qword ptr [rdi], 1
0x100d1e169  lea     r8, ?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e170  mov     r14, qword ptr [rbp+48B0h+var_4890+8]
0x100d1e174  mov     rdx, r14
0x100d1e177  mov     rcx, r15
0x100d1e17a  call    cs:__imp_?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z; InitDbParamBindInfo(IMemObj *,tagDBPARAMBINDINFO *,CTypeInfo const &)
0x100d1e180  mov     r8d, [rdi]; unsigned __int64
0x100d1e183  lea     r9, ?tiI4@CTypeInfo@@2V1@B; struct CTypeInfo *
0x100d1e18a  mov     rdx, [rbp+48B0h+var_4880]; struct tagSSPARAMPROPS *
0x100d1e18e  mov     rcx, r15; struct IMemObj *
0x100d1e191  call    ?InitDbParamProperties@@YAXPEAVIMemObj@@PEAUtagSSPARAMPROPS@@_KAEBVCTypeInfo@@@Z; InitDbParamProperties(IMemObj *,tagSSPARAMPROPS *,unsigned __int64,CTypeInfo const &)
0x100d1e196  or      dword ptr [r14+18h], 3
0x100d1e19b  mov     rdi, [rbp+48B0h+var_4870]
0x100d1e19f  mov     dword ptr [rdi], 3
0x100d1e1a5  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e1ac  cmp     al, 1Fh
0x100d1e1ae  jnz     short loc_100D1E1BD
0x100d1e1b0  mov     dword ptr [rdi], 3
0x100d1e1b6  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100d1e1bd  test    al, al
0x100d1e1bf  jnz     short loc_100D1E1C4
0x100d1e1c1  mov     [rdi], r13d
0x100d1e1c4  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100d1e1cb  cmp     al, 62h ; 'b'
0x100d1e1cd  jnz     short loc_100D1E203
0x100d1e1cf  cmp     qword ptr [r12+8], 0
0x100d1e1d5  jnz     short loc_100D1E20B
0x100d1e1d7  mov     byte ptr [rsp+49B0h+SizeInWords], 1
0x100d1e1dc  mov     r9d, 1FFh
0x100d1e1e2  lea     r8, aSqlNtdbmsQuery_214; "sql\\ntdbms\\query\\qpshared\\oledbutl."...
0x100d1e1e9  mov     rdx, r15
0x100d1e1ec  mov     ecx, 1F78h
0x100d1e1f1  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100d1e1f7  mov     [r12+8], rax
0x100d1e1fc  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100d1e203  cmp     al, 1Fh
0x100d1e205  jz      short loc_100D1E214
0x100d1e207  test    al, al
0x100d1e209  jz      short loc_100D1E214
0x100d1e20b  lea     rdx, ?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
  ... truncated ...
```
