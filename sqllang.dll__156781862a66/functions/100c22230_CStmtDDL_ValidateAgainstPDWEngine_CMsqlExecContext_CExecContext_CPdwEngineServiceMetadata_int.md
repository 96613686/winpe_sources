# CStmtDDL::ValidateAgainstPDWEngine(CMsqlExecContext *,CExecContext *,CPdwEngineServiceMetadata *,int)

- ea: `0x100c22230`
- end: `0x100c24945`
- name: `?ValidateAgainstPDWEngine@CStmtDDL@@SAXPEAVCMsqlExecContext@@PEAVCExecContext@@PEAVCPdwEngineServiceMetadata@@H@Z`
- size: `10005`
- prototype: `void __fastcall(struct CMsqlExecContext *, struct CExecContext *, struct CPdwEngineServiceMetadata *, int)`
- caller_count: `5`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x100676e60`
- `0x100b5ed90`
- `0x100b61100`
- `0x100c1e340`
- `0x10127ba20`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x1004076a0`
- `0x10040b790`
- `0x100430d60`
- `0x100430e10`
- `0x10049e920`
- `0x1005509c0`
- `0x1007043b0`
- `0x100c22230`
- `0x101175bd0`
- `0x1011e41a0`
- `0x1011e4790`
- `0x1016d7290`
- `0x1016d8890`
- `0x1016dc000`
- `0x101701080`
- `0x1017023f0`
- `0x101c2a180`
- `0x101e58cd0`
- `0x101e58f30`
- `0x101e5a1c0`
- `0x101e5a330`
- `0x101e5a890`
- `0x101e5a920`
- `0x101e5ab80`
- `0x101e5ad30`
- `0x101e5b830`
- `0x101e5c800`
- `0x101e5ce60`
- `0x101e5d070`
- `0x101e5d2b0`
- `0x101e5d6a0`
- `0x101e5dea0`
- `0x101e5edc0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x100c2313a`
- `OLEAUT32!__imp_SysFreeString` at `0x100c2313a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c242bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c24315`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c24342`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c242bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c24315`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100c24342`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c222b2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c222b2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c2240e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22448`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22a7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22ab8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22d20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22d90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c230b2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23193`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23256`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23c28`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23c62`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23f58`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23fe8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c241be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c241f8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c245c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c24601`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c2240e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22448`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22a7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22ab8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22d20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c22d90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c230b2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23193`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23256`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23c28`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23c62`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23f58`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c23fe8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c241be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c241f8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c245c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100c24601`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c22558`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c22697`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c227ea`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c239a1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c2407f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c22558`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c22697`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c227ea`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c239a1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100c2407f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c22e47`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c2340a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c237c7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c23a62`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c23d0e`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c24412`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c246ac`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c22e47`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c2340a`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c237c7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c23a62`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c23d0e`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c24412`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100c246ac`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100c22d32`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100c22d32`
- `sqldk!SystemThread_TlsIndex` at `0x100c22b43`
- `sqldk!SystemThread_TlsIndex` at `0x100c22e03`
- `sqldk!SystemThread_TlsIndex` at `0x100c22e5f`
- `sqldk!SystemThread_TlsIndex` at `0x100c22ee5`
- `sqldk!SystemThread_TlsIndex` at `0x100c23280`
- `sqldk!SystemThread_TlsIndex` at `0x100c2332a`
- `sqldk!SystemThread_TlsIndex` at `0x100c233c6`
- `sqldk!SystemThread_TlsIndex` at `0x100c23422`
- `sqldk!SystemThread_TlsIndex` at `0x100c23541`
- `sqldk!SystemThread_TlsIndex` at `0x100c23785`
- `sqldk!SystemThread_TlsIndex` at `0x100c237df`
- `sqldk!SystemThread_TlsIndex` at `0x100c23a1e`
- `sqldk!SystemThread_TlsIndex` at `0x100c23a7a`
- `sqldk!SystemThread_TlsIndex` at `0x100c23cca`
- `sqldk!SystemThread_TlsIndex` at `0x100c23d26`
- `sqldk!SystemThread_TlsIndex` at `0x100c243ce`
- `sqldk!SystemThread_TlsIndex` at `0x100c2442a`
- `sqldk!SystemThread_TlsIndex` at `0x100c24668`
- `sqldk!SystemThread_TlsIndex` at `0x100c246c4`
- `sqldk!SystemThread_TlsOffset` at `0x100c22b4c`
- `sqldk!SystemThread_TlsOffset` at `0x100c22e0c`
- `sqldk!SystemThread_TlsOffset` at `0x100c22e68`
- `sqldk!SystemThread_TlsOffset` at `0x100c22eee`
- `sqldk!SystemThread_TlsOffset` at `0x100c23289`
- `sqldk!SystemThread_TlsOffset` at `0x100c23333`
- `sqldk!SystemThread_TlsOffset` at `0x100c233cf`
- `sqldk!SystemThread_TlsOffset` at `0x100c2342b`
- `sqldk!SystemThread_TlsOffset` at `0x100c23552`
- `sqldk!SystemThread_TlsOffset` at `0x100c2378e`
- `sqldk!SystemThread_TlsOffset` at `0x100c237e8`
- `sqldk!SystemThread_TlsOffset` at `0x100c23a27`
- `sqldk!SystemThread_TlsOffset` at `0x100c23a83`
- `sqldk!SystemThread_TlsOffset` at `0x100c23cd3`
- `sqldk!SystemThread_TlsOffset` at `0x100c23d2f`
- `sqldk!SystemThread_TlsOffset` at `0x100c243d7`
- `sqldk!SystemThread_TlsOffset` at `0x100c24433`
- `sqldk!SystemThread_TlsOffset` at `0x100c24671`
- `sqldk!SystemThread_TlsOffset` at `0x100c246cd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100c24804`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100c24804`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c22e27`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c22e83`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c233ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23446`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c237a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23803`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23a42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23a9e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23cee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23d4a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c243f2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c2444e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c2468c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c246e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c22e27`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c22e83`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c233ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23446`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c237a7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23803`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23a42`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23a9e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23cee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c23d4a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c243f2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c2444e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c2468c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100c246e8`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22456`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22ac6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22d9e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c231a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c2325f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23981`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23c70`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23ff6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c24206`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c2460f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c247ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c247e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22456`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22ac6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c22d9e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c231a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c2325f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23981`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23c70`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c23ff6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c24206`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c2460f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c247ca`
- `sqldk!??_V@YAXPEAX@Z` at `0x100c247e6`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c2261a`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c22773`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c228e1`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c2261a`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c22773`
- `sqlTsEs!?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z` at `0x100c228e1`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c22591`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c226ce`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c22827`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c22591`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c226ce`
- `sqlTsEs!?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z` at `0x100c22827`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100c247f4`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100c24860`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100c247f4`
- `sqlTsEs!??1CAutoClearXVariant@@UEAA@XZ` at `0x100c24860`
- `sqlTsEs!?GetDefaultCollationData@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x100c23587`
- `sqlTsEs!?GetDefaultCollationData@CDbAndSetOptsImplImport@@YAQEBVCDefaultCollation@@G@Z` at `0x100c23587`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x100c2358f`
- `sqlTsEs!?UICodePageFromCID@@YAIK@Z` at `0x100c2358f`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100c22bd8`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100c22c11`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100c22bd8`
- `sqlTsEs!?ConvertToOleDbParam@CXVariant@@QEBAXPEAEKPEBVCTypeInfo@@0KHH@Z` at `0x100c22c11`
- `sqlmin!?CreateCQNameManager@@YAPEAVCQNameManager@@PEAVIMemObj@@@Z` at `0x100c23e2f`
- `sqlmin!?CreateCQNameManager@@YAPEAVCQNameManager@@PEAVIMemObj@@@Z` at `0x100c23e2f`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c2314d`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c24827`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c24832`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c2314d`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c24827`
- `sqlmin!?TaskFree@@YAXPEAX@Z` at `0x100c24832`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c225e4`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c22728`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c22884`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c225e4`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c22728`
- `sqlmin!?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ` at `0x100c22884`

## string_xrefs

- `0x100c242a9`: `showplanWrite.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=85
void __fastcall CStmtDDL::ValidateAgainstPDWEngine(
        struct CSQLSource **a1,
        struct CExecContext *a2,
        struct CPdwEngineServiceMetadata *a3,
        int a4)
{
  struct IMemObj *v5; // r15
  struct IUnknown *v6; // rax
  __int64 v7; // rbx
  COledbConnect *v8; // r14
  struct IUnknown *Interface; // rdi
  int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // rax
  struct IMemObj *v13; // r15
  _QWORD *v14; // r12
  char v15; // al
  const struct CTypeInfo *v16; // rdx
  struct tagDBBINDING *v17; // rbx
  unsigned int *v18; // r13
  struct tagDBPARAMBINDINFO *v19; // rsi
  unsigned __int8 *v20; // rdi
  char v21; // al
  char v22; // al
  const struct CTypeInfo *v23; // rdx
  char v24; // al
  const struct CTypeInfo *v25; // rdx
  char v26; // al
  unsigned int v27; // ebx
  struct IUnknown *v28; // r15
  int v29; // esi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rbx
  struct IBlobHandleFactory *v33; // rcx
  __int64 v34; // rax
  struct IAccessor *v35; // rdi
  int v36; // esi
  __int64 v37; // rbx
  __int64 v38; // rax
  IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rsi
  char v48; // bl
  int v49; // r15d
  int v50; // ecx
  unsigned int v51; // ecx
  __int64 v52; // rbx
  __int64 v53; // rax
  struct tagDBPROP *v54; // rsi
  __int64 v55; // rdi
  BSTR *p_bstrVal; // rbx
  struct IUnknown *v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // r8
  int v61; // ebx
  __int64 v62; // rsi
  __int64 v63; // rdi
  __int64 v64; // rax
  __int64 v65; // r8
  int v66; // eax
  __int64 v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rbx
  __int64 v71; // rdx
  const wchar_t *v72; // rbx
  const wchar_t *v73; // rax
  char *ThreadLocalStoragePointer; // rdx
  __int64 v75; // r9
  int v76; // ebx
  unsigned int *DefaultCollationData; // rax
  unsigned int v78; // eax
  struct IMemObj *v79; // rsi
  struct IUnknown *v80; // r13
  __int64 v81; // rbx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rbx
  __int64 v85; // rdx
  int v86; // edi
  __int64 v87; // rbx
  __int64 v88; // rax
  struct CSQLSource **v89; // r12
  __int64 v90; // rbx
  __int64 v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rbx
  __int64 v94; // rdx
  int v95; // edi
  __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rbx
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rbx
  __int64 v102; // rdx
  int v103; // r15d
  unsigned int v104; // edi
  struct CQNameManager *CQNameManager; // rsi
  __int64 v106; // rbx
  __int64 v107; // rax
  __int64 v108; // rbx
  const wchar_t *v109; // rdi
  __int64 v110; // rbx
  int ErrorColFromStatus; // eax
  void *v112; // rbx
  struct CSQLSource *v113; // r12
  unsigned int v114; // edi
  char *v115; // rsi
  int v116; // r15d
  __int64 v117; // rbx
  __int64 v118; // rax
  size_t v119; // rbx
  struct IUnknown *v120; // r13
  unsigned int v121; // r15d
  __int64 v122; // rbx
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 v125; // rbx
  __int64 v126; // rdx
  int v127; // edi
  __int64 v128; // rbx
  __int64 v129; // rax
  __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rcx
  __int64 v133; // rbx
  __int64 v134; // rdx
  rsize_t SizeInWords; // [rsp+20h] [rbp-E0h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v137; // [rsp+58h] [rbp-A8h] BYREF
  struct tagDBPROP *v138; // [rsp+60h] [rbp-A0h] BYREF
  int v139; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v140[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v141; // [rsp+78h] [rbp-88h] BYREF
  int v142; // [rsp+7Ch] [rbp-84h] BYREF
  struct IUnknown *v143; // [rsp+80h] [rbp-80h]
  struct IUnknown *v144; // [rsp+88h] [rbp-78h]
  int *v145; // [rsp+90h] [rbp-70h]
  struct IUnknown *v146; // [rsp+98h] [rbp-68h]
  int v147; // [rsp+A0h] [rbp-60h]
  unsigned int v148; // [rsp+A4h] [rbp-5Ch] BYREF
  struct IMemObj *v149; // [rsp+A8h] [rbp-58h]
  __int64 v150; // [rsp+B0h] [rbp-50h] BYREF
  struct tagDBCOLUMNINFO *v151; // [rsp+B8h] [rbp-48h] BYREF
  struct IUnknown *v152; // [rsp+C0h] [rbp-40h] BYREF
  struct IUnknown *v153; // [rsp+C8h] [rbp-38h]
  struct ILockBytesSS *v154; // [rsp+D0h] [rbp-30h]
  struct CSQLSource **v155; // [rsp+D8h] [rbp-28h]
  void **v156; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v157; // [rsp+E8h] [rbp-18h]
  unsigned int v158; // [rsp+F8h] [rbp-8h]
  void *v159; // [rsp+100h] [rbp+0h]
  unsigned int v160; // [rsp+108h] [rbp+8h]
  __int64 v161; // [rsp+110h] [rbp+10h]
  wchar_t *v162; // [rsp+118h] [rbp+18h] BYREF
  __int64 v163; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v164; // [rsp+128h] [rbp+28h] BYREF
  struct IAccessor *v165; // [rsp+130h] [rbp+30h]
  struct IUnknown *v166; // [rsp+138h] [rbp+38h]
  CRemSess *Session; // [rsp+140h] [rbp+40h]
  struct IUnknown *v168; // [rsp+148h] [rbp+48h]
  struct IMemObj *v169; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v170; // [rsp+158h] [rbp+58h]
  __int128 v171; // [rsp+160h] [rbp+60h]
  struct tagSSPARAMPROPS *v172; // [rsp+170h] [rbp+70h]
  struct tagDBBINDING *v173; // [rsp+178h] [rbp+78h]
  void *v174; // [rsp+180h] [rbp+80h]
  __int64 v175; // [rsp+188h] [rbp+88h]
  _QWORD *v176; // [rsp+190h] [rbp+90h]
  unsigned int v177; // [rsp+198h] [rbp+98h]
  int v178; // [rsp+19Ch] [rbp+9Ch]
  __int64 v179; // [rsp+1A0h] [rbp+A0h]
  _QWORD v180[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v181; // [rsp+1C0h] [rbp+C0h]
  __int64 v182; // [rsp+1C8h] [rbp+C8h]
  __int64 v183; // [rsp+1D0h] [rbp+D0h]
  void *v184; // [rsp+1D8h] [rbp+D8h]
  __int64 v185; // [rsp+1E0h] [rbp+E0h]
  int v186; // [rsp+1E8h] [rbp+E8h]
  int v187; // [rsp+1ECh] [rbp+ECh]
  __int64 v188; // [rsp+1F0h] [rbp+F0h]
  int v189; // [rsp+1F8h] [rbp+F8h]
  char v190; // [rsp+1FCh] [rbp+FCh]
  _QWORD v191[2]; // [rsp+200h] [rbp+100h] BYREF
  int v192; // [rsp+210h] [rbp+110h]
  __int64 v193; // [rsp+218h] [rbp+118h]
  __int64 v194; // [rsp+220h] [rbp+120h]
  void *v195; // [rsp+228h] [rbp+128h]
  __int64 v196; // [rsp+230h] [rbp+130h]
  int v197; // [rsp+238h] [rbp+138h]
  int v198; // [rsp+23Ch] [rbp+13Ch]
  __int64 v199; // [rsp+240h] [rbp+140h]
  int v200; // [rsp+248h] [rbp+148h]
  char v201; // [rsp+24Ch] [rbp+14Ch]
  void *v202; // [rsp+250h] [rbp+150h]
  __int64 v203; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int64 v204; // [rsp+260h] [rbp+160h] BYREF
  struct IUnknown *v205; // [rsp+268h] [rbp+168h]
  void **v206; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v207[2]; // [rsp+278h] [rbp+178h] BYREF
  __int16 v208; // [rsp+27Ah] [rbp+17Ah]
  __int128 v209; // [rsp+280h] [rbp+180h]
  int v210; // [rsp+290h] [rbp+190h]
  __int128 v211; // [rsp+298h] [rbp+198h]
  __int128 v212; // [rsp+2A8h] [rbp+1A8h]
  __int64 v213; // [rsp+2C0h] [rbp+1C0h] BYREF
  _QWORD v214[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v215; // [rsp+2E0h] [rbp+1E0h]
  __int64 v216; // [rsp+2E8h] [rbp+1E8h]
  __int64 v217; // [rsp+2F0h] [rbp+1F0h]
  void *v218; // [rsp+2F8h] [rbp+1F8h]
  __int64 v219; // [rsp+300h] [rbp+200h]
  int v220; // [rsp+308h] [rbp+208h]
  int v221; // [rsp+30Ch] [rbp+20Ch]
  __int64 v222; // [rsp+310h] [rbp+210h]
  int v223; // [rsp+318h] [rbp+218h]
  char v224; // [rsp+31Ch] [rbp+21Ch]
  _QWORD v225[2]; // [rsp+320h] [rbp+220h] BYREF
  int v226; // [rsp+330h] [rbp+230h]
  __int64 v227; // [rsp+338h] [rbp+238h]
  __int64 v228; // [rsp+340h] [rbp+240h]
  void *v229; // [rsp+348h] [rbp+248h]
  __int64 v230; // [rsp+350h] [rbp+250h]
  int v231; // [rsp+358h] [rbp+258h]
  int v232; // [rsp+35Ch] [rbp+25Ch]
  __int64 v233; // [rsp+360h] [rbp+260h]
  int v234; // [rsp+368h] [rbp+268h]
  char v235; // [rsp+36Ch] [rbp+26Ch]
  _QWORD v236[2]; // [rsp+370h] [rbp+270h] BYREF
  int v237; // [rsp+380h] [rbp+280h]
  __int64 v238; // [rsp+388h] [rbp+288h]
  __int64 v239; // [rsp+390h] [rbp+290h]
  void *v240; // [rsp+398h] [rbp+298h]
  __int64 v241; // [rsp+3A0h] [rbp+2A0h]
  int v242; // [rsp+3A8h] [rbp+2A8h]
  int v243; // [rsp+3ACh] [rbp+2ACh]
  __int64 v244; // [rsp+3B0h] [rbp+2B0h]
  int v245; // [rsp+3B8h] [rbp+2B8h]
  char v246; // [rsp+3BCh] [rbp+2BCh]
  _QWORD v247[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v248; // [rsp+3D0h] [rbp+2D0h]
  __int64 v249; // [rsp+3D8h] [rbp+2D8h]
  __int64 v250; // [rsp+3E0h] [rbp+2E0h]
  void *v251; // [rsp+3E8h] [rbp+2E8h]
  __int64 v252; // [rsp+3F0h] [rbp+2F0h]
  int v253; // [rsp+3F8h] [rbp+2F8h]
  int v254; // [rsp+3FCh] [rbp+2FCh]
  __int64 v255; // [rsp+400h] [rbp+300h]
  int v256; // [rsp+408h] [rbp+308h]
  char v257; // [rsp+40Ch] [rbp+30Ch]
  _QWORD v258[2]; // [rsp+410h] [rbp+310h] BYREF
  int v259; // [rsp+420h] [rbp+320h]
  __int64 v260; // [rsp+428h] [rbp+328h]
  __int64 v261; // [rsp+430h] [rbp+330h]
  void *v262; // [rsp+438h] [rbp+338h]
  __int64 v263; // [rsp+440h] [rbp+340h]
  int v264; // [rsp+448h] [rbp+348h]
  int v265; // [rsp+44Ch] [rbp+34Ch]
  __int64 v266; // [rsp+450h] [rbp+350h]
  int v267; // [rsp+458h] [rbp+358h]
  char v268; // [rsp+45Ch] [rbp+35Ch]
  _QWORD v269[2]; // [rsp+460h] [rbp+360h] BYREF
  int v270; // [rsp+470h] [rbp+370h]
  __int64 v271; // [rsp+478h] [rbp+378h]
  __int64 v272; // [rsp+480h] [rbp+380h]
  void *v273; // [rsp+488h] [rbp+388h]
  __int64 v274; // [rsp+490h] [rbp+390h]
  int v275; // [rsp+498h] [rbp+398h]
  int v276; // [rsp+49Ch] [rbp+39Ch]
  __int64 v277; // [rsp+4A0h] [rbp+3A0h]
  int v278; // [rsp+4A8h] [rbp+3A8h]
  char v279; // [rsp+4ACh] [rbp+3ACh]
  int v280; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v281; // [rsp+4B8h] [rbp+3B8h]
  int v282; // [rsp+4C0h] [rbp+3C0h] BYREF
  int v283; // [rsp+4C4h] [rbp+3C4h]
  __int64 v284; // [rsp+4C8h] [rbp+3C8h]
  int v285; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v286; // [rsp+4D8h] [rbp+3D8h]
  __int64 v287; // [rsp+4E0h] [rbp+3E0h]
  __int64 v288; // [rsp+4E8h] [rbp+3E8h]
  __int64 v289; // [rsp+4F0h] [rbp+3F0h]
  bool v290; // [rsp+500h] [rbp+400h]
  int v291; // [rsp+510h] [rbp+410h] BYREF
  __int64 v292; // [rsp+518h] [rbp+418h]
  int v293; // [rsp+520h] [rbp+420h] BYREF
  int v294; // [rsp+524h] [rbp+424h]
  __int64 v295; // [rsp+528h] [rbp+428h]
  int v296; // [rsp+530h] [rbp+430h] BYREF
  __int64 v297; // [rsp+538h] [rbp+438h]
  __int64 v298; // [rsp+540h] [rbp+440h]
  __int64 v299; // [rsp+548h] [rbp+448h]
  __int64 v300; // [rsp+550h] [rbp+450h]
  bool v301; // [rsp+560h] [rbp+460h]
  int v302; // [rsp+570h] [rbp+470h] BYREF
  __int64 v303; // [rsp+578h] [rbp+478h]
  int v304; // [rsp+580h] [rbp+480h] BYREF
  int v305; // [rsp+584h] [rbp+484h]
  __int64 v306; // [rsp+588h] [rbp+488h]
  int v307; // [rsp+590h] [rbp+490h] BYREF
  __int64 v308; // [rsp+598h] [rbp+498h]
  __int64 v309; // [rsp+5A0h] [rbp+4A0h]
  __int64 v310; // [rsp+5A8h] [rbp+4A8h]
  __int64 v311; // [rsp+5B0h] [rbp+4B0h]
  bool v312; // [rsp+5C0h] [rbp+4C0h]
  int v313; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v314; // [rsp+5D8h] [rbp+4D8h]
  int v315; // [rsp+5E0h] [rbp+4E0h] BYREF
  int v316; // [rsp+5E4h] [rbp+4E4h]
  __int64 v317; // [rsp+5E8h] [rbp+4E8h]
  int v318; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v319; // [rsp+5F8h] [rbp+4F8h]
  __int64 v320; // [rsp+600h] [rbp+500h]
  __int64 v321; // [rsp+608h] [rbp+508h]
  __int64 v322; // [rsp+610h] [rbp+510h]
  bool v323; // [rsp+620h] [rbp+520h]
  int v324; // [rsp+630h] [rbp+530h] BYREF
  __int64 v325; // [rsp+638h] [rbp+538h]
  int v326; // [rsp+640h] [rbp+540h] BYREF
  int v327; // [rsp+644h] [rbp+544h]
  __int64 v328; // [rsp+648h] [rbp+548h]
  int v329; // [rsp+650h] [rbp+550h] BYREF
  __int64 v330; // [rsp+658h] [rbp+558h]
  __int64 v331; // [rsp+660h] [rbp+560h]
  __int64 v332; // [rsp+668h] [rbp+568h]
  __int64 v333; // [rsp+670h] [rbp+570h]
  bool v334; // [rsp+680h] [rbp+580h]
  int v335; // [rsp+690h] [rbp+590h] BYREF
  __int64 v336; // [rsp+698h] [rbp+598h]
  int v337; // [rsp+6A0h] [rbp+5A0h] BYREF
  int v338; // [rsp+6A4h] [rbp+5A4h]
  __int64 v339; // [rsp+6A8h] [rbp+5A8h]
  int v340; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v341; // [rsp+6B8h] [rbp+5B8h]
  __int64 v342; // [rsp+6C0h] [rbp+5C0h]
  __int64 v343; // [rsp+6C8h] [rbp+5C8h]
  __int64 v344; // [rsp+6D0h] [rbp+5D0h]
  bool v345; // [rsp+6E0h] [rbp+5E0h]
  int v346; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v347; // [rsp+6F8h] [rbp+5F8h]
  int v348; // [rsp+700h] [rbp+600h] BYREF
  int v349; // [rsp+704h] [rbp+604h]
  __int64 v350; // [rsp+708h] [rbp+608h]
  int v351; // [rsp+710h] [rbp+610h] BYREF
  __int64 v352; // [rsp+718h] [rbp+618h]
  __int64 v353; // [rsp+720h] [rbp+620h]
  __int64 v354; // [rsp+728h] [rbp+628h]
  __int64 v355; // [rsp+730h] [rbp+630h]
  bool v356; // [rsp+740h] [rbp+640h]
  _QWORD v357[2]; // [rsp+750h] [rbp+650h] BYREF
  int v358; // [rsp+760h] [rbp+660h]
  __int64 v359; // [rsp+768h] [rbp+668h]
  __int64 v360; // [rsp+770h] [rbp+670h]
  void *v361; // [rsp+778h] [rbp+678h]
  __int64 v362; // [rsp+780h] [rbp+680h]
  int v363; // [rsp+788h] [rbp+688h]
  int v364; // [rsp+78Ch] [rbp+68Ch]
  __int64 v365; // [rsp+790h] [rbp+690h]
  int v366; // [rsp+798h] [rbp+698h]
  char v367; // [rsp+79Ch] [rbp+69Ch]
  _QWORD v368[4]; // [rsp+7A0h] [rbp+6A0h] BYREF
  __int16 v369; // [rsp+7C0h] [rbp+6C0h]
  char v370; // [rsp+7C2h] [rbp+6C2h]
  __int64 v371; // [rsp+7C8h] [rbp+6C8h]
  int v372; // [rsp+7D0h] [rbp+6D0h]
  __int64 v373; // [rsp+7E0h] [rbp+6E0h]
  GUID *v374; // [rsp+7E8h] [rbp+6E8h]
  int v375; // [rsp+7F0h] [rbp+6F0h]
  __int64 v376; // [rsp+7F8h] [rbp+6F8h]
  __int64 v377; // [rsp+800h] [rbp+700h]
  __int64 v378; // [rsp+808h] [rbp+708h]
  __int64 v379; // [rsp+810h] [rbp+710h]
  int v380; // [rsp+818h] [rbp+718h]
  int v381; // [rsp+81Ch] [rbp+71Ch]
  __int64 v382; // [rsp+820h] [rbp+720h]
  int v383; // [rsp+828h] [rbp+728h]
  char v384; // [rsp+82Ch] [rbp+72Ch]
  _QWORD v385[2]; // [rsp+830h] [rbp+730h] BYREF
  __int128 v386; // [rsp+840h] [rbp+740h]
  __int64 v387; // [rsp+850h] [rbp+750h]
  __int16 v388; // [rsp+858h] [rbp+758h]
  __int64 v389; // [rsp+85Ch] [rbp+75Ch]
  __int64 v390; // [rsp+868h] [rbp+768h]
  char v391; // [rsp+870h] [rbp+770h]
  int v392; // [rsp+874h] [rbp+774h]
  __int64 v393; // [rsp+878h] [rbp+778h]
  _QWORD v394[8]; // [rsp+880h] [rbp+780h] BYREF
  int v395; // [rsp+8C0h] [rbp+7C0h]
  __int64 v396; // [rsp+8C8h] [rbp+7C8h]
  int v397; // [rsp+8D0h] [rbp+7D0h]
  int v398; // [rsp+8D4h] [rbp+7D4h]
  void **v399; // [rsp+8E0h] [rbp+7E0h] BYREF
  _BYTE v400[2]; // [rsp+8E8h] [rbp+7E8h] BYREF
  __int16 v401; // [rsp+8EAh] [rbp+7EAh]
  __int128 v402; // [rsp+8F0h] [rbp+7F0h]
  int v403; // [rsp+900h] [rbp+800h]
  __int128 v404; // [rsp+908h] [rbp+808h]
  __int128 v405; // [rsp+918h] [rbp+818h]
  __int64 v406; // [rsp+958h] [rbp+858h]
  struct ILockBytesSS *v407; // [rsp+960h] [rbp+860h]
  struct CSQLSource **v408; // [rsp+968h] [rbp+868h]
  __int64 v409; // [rsp+970h] [rbp+870h]
  char v410; // [rsp+978h] [rbp+878h] BYREF
  _OWORD v411[2]; // [rsp+998h] [rbp+898h] BYREF
  int v412; // [rsp+9C0h] [rbp+8C0h] BYREF
  __int64 v413; // [rsp+9C8h] [rbp+8C8h]
  _DWORD v414[2]; // [rsp+9D0h] [rbp+8D0h] BYREF
  __int64 v415; // [rsp+9D8h] [rbp+8D8h]
  char v416[64]; // [rsp+9E0h] [rbp+8E0h] BYREF
  tagDBPARAMS v417; // [rsp+A20h] [rbp+920h] BYREF
  struct tagDBCOLUMNINFO v418; // [rsp+A40h] [rbp+940h] BYREF
  struct _GUID v419; // [rsp+A90h] [rbp+990h] BYREF
  __int128 v420; // [rsp+AA0h] [rbp+9A0h]
  int v421; // [rsp+AB0h] [rbp+9B0h] BYREF
  GUID v422; // [rsp+AB4h] [rbp+9B4h]
  _BYTE Src[8000]; // [rsp+AD0h] [rbp+9D0h] BYREF
  wchar_t v424[4008]; // [rsp+2A10h] [rbp+2910h] BYREF
  wchar_t v425[4008]; // [rsp+4960h] [rbp+4860h] BYREF
  wchar_t v426[4008]; // [rsp+68B0h] [rbp+67B0h] BYREF

  v409 = -2;
  v147 = a4;
  v145 = (int *)a3;
  v155 = a1;
  v5 = a1[15];
  v149 = v5;
  Session = v5;
  v142 = 24279;
  v6 = (struct IUnknown *)operator new(0x710u, v5, "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp", 24279, 3u);
  v166 = v6;
  if ( v6 )
    v7 = COledbRangeExternalComputation::COledbRangeExternalComputation(v6, v5, 0xFFFFFFFFLL);
  else
    v7 = 0;
  v161 = v7;
  CAutoPolyBaseRequest::CAutoPolyBaseRequest((CAutoPolyBaseRequest *)&v419, (const struct _GUID *)(v7 + 1788));
  v8 = (COledbConnect *)(**(__int64 (__fastcall ***)(__int64))v7)(v7);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 1) + 16LL))(*((_QWORD *)a3 + 1));
  CTestHookXmlOutput::PrepareWStrLog(*((CTestHookXmlOutput **)a3 + 1));
  v154 = *(struct ILockBytesSS **)(*((_QWORD *)a3 + 1) + 1088LL);
  Session = COledbConnect::GetSession(v8, 0);
  v153 = 0;
  Interface = COledbConnect::GetInterface(
                v8,
                &IID_IDBCreateCommand,
                *((struct IUnknown **)Session + 5),
                &IID_IUnknown,
                1);
  v153 = Interface;
  v152 = 0;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, struct IUnknown **))Interface->lpVtbl[1].QueryInterface)(
          Interface,
          0,
          &IID_ICommandText,
          &v152);
  if ( v10 < 0 )
  {
    _mm_lfence();
    v11 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v12 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v214[0] = Interface;
    v214[1] = &IID_IDBCreateCommand;
    v215 = v10;
    v216 = v12;
    v217 = v11;
    v218 = 0;
    v219 = 0;
    v220 = 0;
    v221 = -1;
    v222 = 0;
    v223 = 0;
    v224 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v214) )
      ex_raise(73, 5, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v214);
    ex_raise(73, 5, 16, 2, v216, v217);
    operator delete[](v218);
  }
  v144 = COledbConnect::GetInterface(v8, &IID_ICommandText, v152, &IID_IUnknown, 1);
  v146 = v144;
  ((void (__fastcall *)(struct IUnknown *, const GUID *, const wchar_t *))v144->lpVtbl[2].AddRef)(
    v144,
    &DBGUID_SQL,
    L"{? = call sp_validate_ddl(?,?)}");
  v168 = 0;
  v143 = COledbConnect::GetInterface(v8, &IID_ICommandWithParameters, v144, &IID_IUnknown, 1);
  v168 = v143;
  v169 = v5;
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
  v13 = v169;
  v14 = v176;
  v15 = CTypeInfo::tiI4;
  if ( CTypeInfo::tiI4 == 98 )
  {
    if ( *v176 )
      goto LABEL_13;
    *v14 = operator new[](0x1F78u, v169, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v15 = CTypeInfo::tiI4;
  }
  if ( v15 == 31 || !v15 )
  {
    v16 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
    goto LABEL_15;
  }
LABEL_13:
  v16 = (const struct CTypeInfo *)&CTypeInfo::tiI4;
LABEL_15:
  v17 = v173;
  InitDbBind(v173, v16, 1, 1);
  if ( (_WORD)xmmword_102EF7C30 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiI4)) )
  {
    v17->wType = 13;
    v17->cbMaxLen = 0x7FFFFFFF;
    v17->dwPart |= 2u;
    v17->obLength = 8;
    v17->pObject = DbObjSequentialStream();
  }
  v17->dwMemOwner = 0;
  v17->iOrdinal = 1;
  v17->eParamIO |= 3u;
  v18 = (unsigned int *)v171;
  *(_QWORD *)v171 = 1;
  v19 = (struct tagDBPARAMBINDINFO *)*((_QWORD *)&v171 + 1);
  InitDbParamBindInfo(v13, *((struct tagDBPARAMBINDINFO **)&v171 + 1), (const struct CTypeInfo *)&CTypeInfo::tiI4);
  InitDbParamProperties(v13, v172, *v18, (const struct CTypeInfo *)&CTypeInfo::tiI4);
  v19->dwFlags |= 3u;
  v20 = (unsigned __int8 *)v174;
  *(_DWORD *)v174 = 3;
  v21 = CTypeInfo::tiI4;
  if ( CTypeInfo::tiI4 == 31 )
  {
    *(_DWORD *)v20 = 3;
    v21 = CTypeInfo::tiI4;
  }
  if ( !v21 )
    *(_DWORD *)v20 = 13;
  v22 = CTypeInfo::tiVarWstrUnlim;
  if ( CTypeInfo::tiVarWstrUnlim == 98 )
  {
    if ( v14[1] )
      goto LABEL_27;
    v14[1] = operator new[](0x1F78u, v13, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v22 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( v22 == 31 || !v22 )
  {
    v23 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
    goto LABEL_29;
  }
LABEL_27:
  v23 = (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim;
LABEL_29:
  InitDbBind(v17 + 1, v23, 1, 1);
  if ( (_WORD)xmmword_102F39930 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiVarWstrUnlim)) )
  {
    v17[1].wType = 13;
    v17[1].cbMaxLen = 0x7FFFFFFF;
    v17[1].dwPart |= 2u;
    v17[1].obLength = 8;
    v17[1].pObject = DbObjSequentialStream();
  }
  v17[1].dwMemOwner = 0;
  v17[1].iOrdinal = 2;
  v17[1].eParamIO |= 1u;
  v17[1].obStatus += 80LL;
  v17[1].obValue += 80LL;
  v17[1].obLength += 80LL;
  *((_QWORD *)v18 + 1) = 2;
  InitDbParamBindInfo(v13, v19 + 1, (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  InitDbParamProperties(
    v13,
    (struct tagSSPARAMPROPS *)((char *)v172 + 24),
    v18[2],
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  v19[1].dwFlags |= 1u;
  v24 = CTypeInfo::tiVarWstrUnlim;
  if ( CTypeInfo::tiVarWstrUnlim == 31 )
  {
    *((_DWORD *)v20 + 20) = 3;
    v24 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( !v24 )
  {
    *((_DWORD *)v20 + 20) = 13;
    v24 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( v24 == 98 )
  {
    if ( v14[2] )
    {
LABEL_41:
      v25 = (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim;
      goto LABEL_43;
    }
    v14[2] = operator new[](0x1F78u, v13, "sql\\ntdbms\\query\\qpshared\\oledbutl.cpp", 511, 1u);
    v24 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( v24 != 31 && v24 )
    goto LABEL_41;
  v25 = (const struct CTypeInfo *)&CTypeInfo::tiEmpty;
LABEL_43:
  InitDbBind(v17 + 2, v25, 1, 1);
  if ( (_WORD)xmmword_102F39930 == 0xFFFF
    || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + CTypeInfo::tiVarWstrUnlim)) )
  {
    v17[2].wType = 13;
    v17[2].cbMaxLen = 0x7FFFFFFF;
    v17[2].dwPart |= 2u;
    v17[2].obLength = 8;
    v17[2].pObject = DbObjSequentialStream();
  }
  v17[2].dwMemOwner = 0;
  v17[2].iOrdinal = 3;
  v17[2].eParamIO |= 1u;
  v17[2].obStatus += 160LL;
  v17[2].obValue += 160LL;
  v17[2].obLength += 160LL;
  *((_QWORD *)v18 + 2) = 3;
  InitDbParamBindInfo(v13, v19 + 2, (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  InitDbParamProperties(
    v13,
    (struct tagSSPARAMPROPS *)((char *)v172 + 48),
    v18[4],
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim);
  v19[2].dwFlags |= 1u;
  v26 = CTypeInfo::tiVarWstrUnlim;
  if ( CTypeInfo::tiVarWstrUnlim == 31 )
  {
    *((_DWORD *)v20 + 40) = 3;
    v26 = CTypeInfo::tiVarWstrUnlim;
  }
  if ( !v26 )
    *((_DWORD *)v20 + 40) = 13;
  v27 = v170;
  memset_0(v20, 0, 80 * v170);
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v412, 536871443, v177);
  v28 = v143;
  v29 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, unsigned int *, struct tagDBPARAMBINDINFO *))v143->lpVtbl[1].Release)(
          v143,
          v27,
          v18,
          v19);
  v143 = (struct IUnknown *)v414;
  if ( v414[0] )
  {
    if ( v414[1] )
      *(_DWORD *)(v415 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v415 + 608) + 16LL))(
        *(_QWORD *)(v415 + 608),
        v415,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v416);
  *(_DWORD *)(v413 + 616) &= ~v412;
  if ( v29 < 0 )
  {
    _mm_lfence();
    v30 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v31 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v269[0] = v28;
    v269[1] = &IID_ICommandText;
    v270 = v29;
    v271 = v31;
    v272 = v30;
    v273 = 0;
    v274 = 0;
    v275 = 0;
    v276 = -1;
    v277 = 0;
    v278 = 0;
    v279 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v269) )
      ex_raise(73, 22, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v269);
    ex_raise(73, 22, 16, 2, v271, v272);
    operator delete[](v273);
    v20 = (unsigned __int8 *)v174;
  }
  v399 = &CAutoClearXVariant::`vftable';
  v404 = CTypeInfo::tiVarWstrUnlim;
  v405 = xmmword_102F39930;
  v401 = 0;
  v400[0] = 3;
  LOBYTE(v404) = _mm_cvtsi128_si32(CTypeInfo::tiVarWstrUnlim);
  v400[1] = v404;
  v402 = 0;
  v403 = 0;
  v32 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 128LL)
                  + 264LL);
  v33 = *(struct IBlobHandleFactory **)(v32 + 16);
  v143 = (struct IUnknown *)v33;
  if ( !v33 )
  {
    (**(void (__fastcall ***)(__int64))v32)(v32);
    v33 = *(struct IBlobHandleFactory **)(v32 + 16);
    v143 = (struct IUnknown *)v33;
  }
  CStatement::GetStatementSqlText(v155[12], (struct CAutoClearXVariant *)&v399, v33, v149, v147);
  CXVariant::ConvertToOleDbParam(
    (CXVariant *)v400,
    v20 + 80,
    0x50u,
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim,
    0,
    0,
    0,
    1);
  CXVariant::ConvertToOleDbParam(
    (struct ILockBytesSS *)((char *)v154 + 8),
    v20 + 160,
    0x50u,
    (const struct CTypeInfo *)&CTypeInfo::tiVarWstrUnlim,
    0,
    0,
    0,
    1);
  v34 = v179;
  *(_DWORD *)(v179 + 4) = 1;
  *(_DWORD *)(v34 + 8) = 1;
  v178 = 1;
  v165 = 0;
  v35 = (struct IAccessor *)COledbConnect::GetInterface(v8, &IID_IAccessor, v144, &IID_IUnknown, 1);
  v165 = v35;
  v36 = COleDbParams::HrCreateDBPARAM((COleDbParams *)&v169, &v417, v35);
  if ( v36 < 0 )
  {
    _mm_lfence();
    v37 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v38 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v225[0] = v35;
    v225[1] = &IID_IAccessor;
    v226 = v36;
    v227 = v38;
    v228 = v37;
    v229 = 0;
    v230 = 0;
    v231 = 0;
    v232 = -1;
    v233 = 0;
    v234 = 0;
    v235 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v225) )
      ex_raise(73, 40, 25, 7);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v225);
    ErrorReportingManager = GetErrorReportingManager();
    v40 = v228;
    v41 = v227;
    IErrorReportingManager::CwchCallFormatToBuffer(ErrorReportingManager, 7340, v426, 4001, v227, v228);
    SendErrorEventToTrace(v426);
    ex_raise(73, 40, 16, 8, v41, v40);
    operator delete[](v229);
  }
  v137 = 0;
  v203 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v291, 1);
  v144 = (struct IUnknown *)&v293;
  v296 = 536871506;
  v297 = 0;
  v299 = 0;
  v298 = 0;
  v300 = 0;
  v301 = 0;
  v42 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v43 = *(_QWORD *)(v42 + 256);
  if ( !v43 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v43 = *(_QWORD *)(v42 + 256);
  }
  v44 = *(_QWORD *)(v43 + 600);
  if ( v44 )
    v301 = (unsigned int)SOS_Task::PushWait(v44, &v296) == 0;
  v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v46 = *(_QWORD *)(v45 + 256);
  if ( !v46 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v46 = *(_QWORD *)(v45 + 256);
  }
  v295 = v46;
  v294 = (*(_DWORD *)(v46 + 800) >> 11) & 1;
  if ( v294 || (*(_BYTE *)(v46 + 800) & 4) == 0 )
  {
    v293 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v46 + 608) + 8LL))(*(_QWORD *)(v46 + 608));
  }
  else
  {
    v293 = 0;
  }
  v178 = 0;
  v47 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 128LL);
  v393 = v47;
  v392 = 0x1000000;
  v391 = *(_BYTE *)(v47 + 79) & 1;
  v48 = v391;
  *(_DWORD *)(v47 + 76) |= 0x1000000u;
  v49 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, tagDBPARAMS *, __int64 *, struct IUnknown **))v146->lpVtbl[1].AddRef)(
          v146,
          0,
          &IID_IRowset,
          &v417,
          &v203,
          &v137);
  v50 = *(_DWORD *)(v47 + 76);
  if ( v48 )
    v51 = v50 | 0x1000000;
  else
    v51 = v50 & 0xFEFFFFFF;
  *(_DWORD *)(v47 + 76) = v51;
  v144 = (struct IUnknown *)&v293;
  if ( v293 )
  {
    if ( v294 )
      *(_DWORD *)(v295 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v295 + 608) + 16LL))(
        *(_QWORD *)(v295 + 608),
        v295,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v296);
  *(_DWORD *)(v292 + 616) &= ~v291;
  if ( v49 < 0 )
  {
    _mm_lfence();
    v52 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v53 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v180[0] = v146;
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
      memset_0(v424, 0, 0x1F42u);
      if ( v181 == -2147217887 )
      {
        COledbError::GatherPropsInError((COledbError *)v180, &v148, &v138);
        LODWORD(SizeInWords) = 4001;
        v54 = v138;
        v55 = v148;
        COledbError::CwchFormatPropertyUser((COledbError *)v180, v148, v138, v424, SizeInWords);
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
        TaskFree(v54);
      }
      ex_raise(73, 20, 16, 2, L"sp_validate_ddl", v182, v183, v424);
    }
    operator delete[](v184);
  }
  v57 = v137;
  if ( !v137 )
  {
    v58 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v59 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v373 = 0;
    v374 = &IID_IUnknown;
    v375 = 0;
    v376 = v59;
    v377 = v58;
    v378 = 0;
    v379 = 0;
    v380 = 0;
    v381 = -1;
    v382 = 0;
    v383 = 0;
    v384 &= ~1u;
    ex_raise(73, 57, 16, 1, L"sp_validate_ddl call", v59, v58);
    operator delete[](0);
    v57 = v137;
  }
  v166 = v57;
  v60 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset);
  if ( *(_BYTE *)v60 )
  {
    v61 = *(_DWORD *)(v60 + 104);
  }
  else
  {
    CExecLvlIntCtxt::GetCurCompatLevel(*(_QWORD *)(v60 + 128), &v142, v60);
    v61 = v142;
  }
  v62 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v161 + 64LL))(v161);
  v63 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
  v64 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
  v368[0] = v62;
  v368[1] = v64;
  v368[2] = v63;
  v368[3] = L"EXECUTE";
  v369 = 257;
  v370 = 1;
  v371 = 0;
  v372 = v61;
  if ( !v61 )
  {
    v65 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset);
    if ( *(_BYTE *)v65 )
    {
      v66 = *(_DWORD *)(v65 + 104);
    }
    else
    {
      CExecLvlIntCtxt::GetCurCompatLevel(*(_QWORD *)(v65 + 128), &v139, v65);
      v66 = v139;
    }
    v372 = v66;
  }
  v151 = 0;
  v162 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v302, 1);
  v138 = (struct tagDBPROP *)&v304;
  v307 = 536871506;
  v308 = 0;
  v310 = 0;
  v309 = 0;
  v311 = 0;
  v312 = 0;
  v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v68 = *(_QWORD *)(v67 + 256);
  if ( !v68 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v68 = *(_QWORD *)(v67 + 256);
  }
  v69 = *(_QWORD *)(v68 + 600);
  if ( v69 )
    v312 = (unsigned int)SOS_Task::PushWait(v69, &v307) == 0;
  v70 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v71 = *(_QWORD *)(v70 + 256);
  if ( !v71 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v71 = *(_QWORD *)(v70 + 256);
  }
  v306 = v71;
  v305 = (*(_DWORD *)(v71 + 800) >> 11) & 1;
  if ( v305 || (*(_BYTE *)(v71 + 800) & 4) == 0 )
  {
    v304 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v71 + 608) + 8LL))(*(_QWORD *)(v71 + 608));
  }
  else
  {
    v304 = 0;
  }
  v72 = (const wchar_t *)(*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
  v73 = (const wchar_t *)(*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
  GetColumnInfoFromPunk(v137, &v204, &v151, &v162, v73, v72);
  v138 = (struct tagDBPROP *)&v304;
  if ( v304 )
  {
    if ( v305 )
      *(_DWORD *)(v306 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v306 + 608) + 16LL))(
        *(_QWORD *)(v306 + 608),
        v306,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v307);
  *(_DWORD *)(v303 + 616) &= ~v302;
  ThreadLocalStoragePointer = (char *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v75 = 8LL * SystemThread_TlsIndex;
  v76 = *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)&ThreadLocalStoragePointer[v75]) + 64LL)
                  + 44LL);
  DefaultCollationData = (unsigned int *)CDbAndSetOptsImplImport::GetDefaultCollationData(
                                           (CDbAndSetOptsImplImport *)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&ThreadLocalStoragePointer[v75] + SystemThread_TlsOffset) + 80LL)
                                                                                          + 8LL),
                                           (unsigned __int16)ThreadLocalStoragePointer);
  v78 = UICodePageFromCID(*DefaultCollationData);
  v385[0] = &CColMetaData::`vftable';
  v385[1] = 0;
  v386 = 0;
  v387 = 0;
  v388 = 0;
  v389 = 0;
  v390 = 0;
  v79 = v149;
  CColMetaData::Init((CColMetaData *)v385, v149, v204, v76, v78);
  v418 = *v151;
  anonymous_namespace_::TiFromDbColOrDbParamWithErrors_1_(
    (unsigned int)&v410,
    (unsigned int)&v418,
    0,
    0,
    v418.ulColumnSize,
    (__int64)v368);
  v406 = 0;
  v394[0] = 1;
  v394[1] = 0;
  v394[2] = 0;
  v394[3] = 8;
  v394[4] = 0;
  v394[5] = &v421;
  v394[6] = 0;
  v394[7] = 5;
  v395 = 0;
  v396 = 0;
  v397 = 0;
  v398 = 13;
  v421 = 0;
  v422 = IID_ISequentialStream;
  v205 = 0;
  v80 = COledbConnect::GetInterface(v8, &IID_IAccessor, v137, &IID_IUnknown, 1);
  v144 = v80;
  v205 = v80;
  v150 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v313, 1);
  v138 = (struct tagDBPROP *)&v315;
  v318 = 536871420;
  v319 = 0;
  v321 = 0;
  v320 = 0;
  v322 = 0;
  v323 = 0;
  v81 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v82 = *(_QWORD *)(v81 + 256);
  if ( !v82 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v82 = *(_QWORD *)(v81 + 256);
  }
  v83 = *(_QWORD *)(v82 + 600);
  if ( v83 )
    v323 = (unsigned int)SOS_Task::PushWait(v83, &v318) == 0;
  v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v85 = *(_QWORD *)(v84 + 256);
  if ( !v85 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v85 = *(_QWORD *)(v84 + 256);
  }
  v317 = v85;
  v316 = (*(_DWORD *)(v85 + 800) >> 11) & 1;
  if ( v316 || (*(_BYTE *)(v85 + 800) & 4) == 0 )
  {
    v315 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v85 + 608) + 8LL))(*(_QWORD *)(v85 + 608));
  }
  else
  {
    v315 = 0;
  }
  v86 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD *, __int64, __int64 *, _QWORD))v80->lpVtbl[1].AddRef)(
          v80,
          2,
          1,
          v394,
          12,
          &v150,
          0);
  v138 = (struct tagDBPROP *)&v315;
  if ( v315 )
  {
    if ( v316 )
      *(_DWORD *)(v317 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v317 + 608) + 16LL))(
        *(_QWORD *)(v317 + 608),
        v317,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v318);
  *(_DWORD *)(v314 + 616) &= ~v313;
  if ( v86 < 0 )
  {
    _mm_lfence();
    v87 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v88 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v357[0] = v80;
    v357[1] = &IID_IAccessor;
    v358 = v86;
    v359 = v88;
    v360 = v87;
    v361 = 0;
    v362 = 0;
    v363 = 0;
    v364 = -1;
    v365 = 0;
    v366 = 0;
    v367 &= ~1u;
    COledbError::RaiseMultipleGetAccessorError((COledbError *)v357);
    operator delete[](v361);
  }
  v89 = (struct CSQLSource **)operator new[](0xCu, v79, "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp", 24491, 3u);
  v155 = v89;
  v408 = v89;
  v163 = 0;
  v164 = &v163;
  v213 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v280, 1);
  v138 = (struct tagDBPROP *)&v282;
  v285 = 536871424;
  v286 = 0;
  v288 = 0;
  v287 = 0;
  v289 = 0;
  v290 = 0;
  v90 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v91 = *(_QWORD *)(v90 + 256);
  if ( !v91 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v91 = *(_QWORD *)(v90 + 256);
  }
  v92 = *(_QWORD *)(v91 + 600);
  if ( v92 )
    v290 = (unsigned int)SOS_Task::PushWait(v92, &v285) == 0;
  v93 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v94 = *(_QWORD *)(v93 + 256);
  if ( !v94 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v94 = *(_QWORD *)(v93 + 256);
  }
  v284 = v94;
  v283 = (*(_DWORD *)(v94 + 800) >> 11) & 1;
  if ( v283 || (*(_BYTE *)(v94 + 800) & 4) == 0 )
  {
    v282 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v94 + 608) + 8LL))(*(_QWORD *)(v94 + 608));
  }
  else
  {
    v282 = 0;
  }
  v95 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, __int64, __int64 *, __int64 **))v137->lpVtbl[1].Release)(
          v137,
          0,
          0,
          1,
          &v213,
          &v164);
  v138 = (struct tagDBPROP *)&v282;
  if ( v282 )
  {
    if ( v283 )
      *(_DWORD *)(v284 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v284 + 608) + 16LL))(
        *(_QWORD *)(v284 + 608),
        v284,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v285);
  *(_DWORD *)(v281 + 616) &= ~v280;
  if ( v95 < 0 )
  {
    v96 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v97 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v236[0] = v137;
    v236[1] = &IID_IRowset;
    v237 = v95;
    v238 = v97;
    v239 = v96;
    v240 = 0;
    v241 = 0;
    v242 = 0;
    v243 = -1;
    v244 = 0;
    v245 = 0;
    v246 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v236) )
      ex_raise(73, 30, 25, 1, 0);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v236);
    ex_raise(73, 30, 16, 2, v238, v239);
    operator delete[](v240);
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v324, 1);
  v138 = (struct tagDBPROP *)&v326;
  v329 = 536871423;
  v330 = 0;
  v332 = 0;
  v331 = 0;
  v333 = 0;
  v334 = 0;
  v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v99 = *(_QWORD *)(v98 + 256);
  if ( !v99 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v99 = *(_QWORD *)(v98 + 256);
  }
  v100 = *(_QWORD *)(v99 + 600);
  if ( v100 )
    v334 = (unsigned int)SOS_Task::PushWait(v100, &v329) == 0;
  v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v102 = *(_QWORD *)(v101 + 256);
  if ( !v102 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v102 = *(_QWORD *)(v101 + 256);
  }
  v328 = v102;
  v327 = (*(_DWORD *)(v102 + 800) >> 11) & 1;
  if ( v327 || (*(_BYTE *)(v102 + 800) & 4) == 0 )
  {
    v326 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v102 + 608) + 8LL))(*(_QWORD *)(v102 + 608));
  }
  else
  {
    v326 = 0;
  }
  v103 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, struct CSQLSource **))v137->lpVtbl[1].AddRef)(
           v137,
           v163,
           v150,
           v89);
  v138 = (struct tagDBPROP *)&v326;
  if ( v326 )
  {
    if ( v327 )
      *(_DWORD *)(v328 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v328 + 608) + 16LL))(
        *(_QWORD *)(v328 + 608),
        v328,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v329);
  *(_DWORD *)(v325 + 616) &= ~v324;
  if ( v103 < 0 )
  {
    _mm_lfence();
    v104 = *(_DWORD *)v89;
    CQNameManager = CreateCQNameManager(v79);
    v106 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v107 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v191[0] = v137;
    v191[1] = &IID_IRowset;
    v192 = v103;
    v193 = v107;
    v194 = v106;
    v195 = 0;
    v196 = 0;
    v197 = 0;
    v198 = -1;
    v199 = 0;
    v200 = 0;
    v201 &= ~1u;
    v140[0] = v104;
    v108 = (**(__int64 (__fastcall ***)(struct CQNameManager *, LPOLESTR, _QWORD))CQNameManager)(
             CQNameManager,
             v418.pwszName,
             0);
    memset_0(v425, 0, 0x1F42u);
    if ( (**(unsigned int (__fastcall ***)(__int64))v108)(v108) )
      v109 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v108 + 8LL))(v108);
    else
      v109 = L"(user generated expression)";
    v110 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
    if ( COledbError::FPrintSQLServerError((COledbError *)v191) )
      ex_raise(73, 41, 25, 1, v109, v110, v193, v194, &szPassword);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v191);
    if ( v192 == -2147217887 || v192 == 265946 )
    {
      ErrorColFromStatus = FindErrorColFromStatus(v140, 1);
      if ( ErrorColFromStatus != -1 )
        CwchDBStatusDesc(v140[ErrorColFromStatus], v425, 0xFA1u);
    }
    ex_raise(73, 41, 16, 2, v109, v110, v193, v194, v425);
    operator delete[](v195);
    v79 = v149;
  }
  v206 = &CAutoClearXVariant::`vftable';
  v211 = CTypeInfo::tiVarWstrUnlim;
  v212 = xmmword_102F39930;
  v208 = 0;
  v207[0] = 3;
  LOBYTE(v211) = _mm_cvtsi128_si32(CTypeInfo::tiVarWstrUnlim);
  v207[1] = v211;
  v209 = 0;
  v210 = 0;
  v141 = 96;
  v112 = operator new[](0x60u, v79, "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp", 24525, 3u);
  v202 = v112;
  ((void (__fastcall *)(struct IUnknown *, void *, unsigned int *, _QWORD))v143->lpVtbl->QueryInterface)(
    v143,
    v112,
    &v141,
    0);
  *(_QWORD *)&v209 = v112;
  *((_QWORD *)&v209 + 1) = v141;
  v202 = 0;
  v207[0] = 0;
  v208 |= 1u;
  v154 = (struct ILockBytesSS *)(*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v112 + 8LL))(v112, 0);
  v407 = v154;
  CWriterLockBytes::CWriterLockBytes((CWriterLockBytes *)&v156, v154);
  LODWORD(Size) = 0;
  v113 = *v89;
  v114 = v160;
  v115 = (char *)v159;
  do
  {
    v116 = (*(__int64 (__fastcall **)(struct CSQLSource *, _BYTE *, __int64, size_t *))(*(_QWORD *)v113 + 24LL))(
             v113,
             Src,
             8000,
             &Size);
    if ( v116 < 0 )
    {
      v117 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
      v118 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
      v247[0] = v153;
      v247[1] = &IID_ISequentialStream;
      v248 = v116;
      v249 = v118;
      v250 = v117;
      v251 = 0;
      v252 = 0;
      v253 = 0;
      v254 = -1;
      v255 = 0;
      v256 = 0;
      v257 &= ~1u;
      if ( COledbError::FPrintSQLServerError((COledbError *)v247) )
        ex_raise(73, 5, 25, 1);
      COledbError::PrintMsgUsingHRESULT((COledbError *)v247);
      ex_raise(73, 5, 16, 2, v249, v250);
      operator delete[](v251);
    }
    v119 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      if ( v115 )
      {
        if ( (unsigned int)Size + v114 <= v158 )
          goto LABEL_198;
        if ( v114 )
        {
          CWriterLockBytes::WriteStreamInternal((CWriterLockBytes *)&v156, v115, v114);
          v114 = 0;
          v160 = 0;
          v115 = (char *)v159;
        }
        if ( (unsigned int)v119 <= v158 )
        {
LABEL_198:
          v121 = v114 + v119;
          if ( v114 + (unsigned int)v119 > v158 )
            utassert_fail(1u, "cbSize + m_cbBuffer <= x_cbBuffer", "showplanWrite.cpp", 138, 0);
          memmove(&v115[v114], Src, v119);
          v114 += v119;
          v160 = v121;
          goto LABEL_193;
        }
        _mm_lfence();
      }
      CWriterLockBytes::WriteStreamInternal((CWriterLockBytes *)&v156, Src, v119);
      v115 = (char *)v159;
      v114 = v160;
LABEL_193:
      LODWORD(v119) = Size;
    }
  }
  while ( (unsigned int)v119 >= 0x1F40 );
  v120 = v144;
  if ( v115 && v114 )
  {
    CWriterLockBytes::WriteStreamInternal((CWriterLockBytes *)&v156, v115, v114);
    v160 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 160LL))(v157);
  if ( v207[0] )
    utassert_fail(1u, "DBSTATUS_S_OK == a_xvarResult.DbStatus()", "tabcreat.cpp", 24573, 0);
  if ( (v208 & 1) == 0 )
    utassert_fail(1u, "a_xvarResult.FGetOwnerFlag()", "tabcreat.cpp", 24574, 0);
  v411[0] = CTypeInfo::tiVarWstrUnlim;
  v411[1] = xmmword_102F39930;
  (**(void (__fastcall ***)(int *, _BYTE *, _OWORD *))v145)(v145, v207, v411);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v335, 1);
  v145 = &v337;
  v340 = 536871437;
  v341 = 0;
  v343 = 0;
  v342 = 0;
  v344 = 0;
  v345 = 0;
  v122 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v123 = *(_QWORD *)(v122 + 256);
  if ( !v123 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v123 = *(_QWORD *)(v122 + 256);
  }
  v124 = *(_QWORD *)(v123 + 600);
  if ( v124 )
    v345 = (unsigned int)SOS_Task::PushWait(v124, &v340) == 0;
  v125 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v126 = *(_QWORD *)(v125 + 256);
  if ( !v126 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v126 = *(_QWORD *)(v125 + 256);
  }
  v339 = v126;
  v338 = (*(_DWORD *)(v126 + 800) >> 11) & 1;
  if ( v338 || (*(_BYTE *)(v126 + 800) & 4) == 0 )
  {
    v337 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v126 + 608) + 8LL))(*(_QWORD *)(v126 + 608));
  }
  else
  {
    v337 = 0;
  }
  v127 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))v137->lpVtbl[2].QueryInterface)(v137, 1, v164);
  v145 = &v337;
  if ( v337 )
  {
    if ( v338 )
      *(_DWORD *)(v339 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v339 + 608) + 16LL))(
        *(_QWORD *)(v339 + 608),
        v339,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v340);
  *(_DWORD *)(v336 + 616) &= ~v335;
  if ( v127 < 0 )
  {
    v128 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 40LL))(v8);
    v129 = (*(__int64 (__fastcall **)(COledbConnect *))(*(_QWORD *)v8 + 24LL))(v8);
    v258[0] = v120;
    v258[1] = &IID_IAccessor;
    v259 = v127;
    v260 = v129;
    v261 = v128;
    v262 = 0;
    v263 = 0;
    v264 = 0;
    v265 = -1;
    v266 = 0;
    v267 = 0;
    v268 &= ~1u;
    if ( COledbError::FPrintSQLServerError((COledbError *)v258) )
      ex_raise(73, 31, 25, 1);
    COledbError::PrintMsgUsingHRESULT((COledbError *)v258);
    ex_raise(73, 31, 16, 2, v260, v261);
    operator delete[](v262);
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v346, 1);
  v145 = &v348;
  v351 = 536871436;
  v352 = 0;
  v354 = 0;
  v353 = 0;
  v355 = 0;
  v356 = 0;
  v130 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v131 = *(_QWORD *)(v130 + 256);
  if ( !v131 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v131 = *(_QWORD *)(v130 + 256);
  }
  v132 = *(_QWORD *)(v131 + 600);
  if ( v132 )
    v356 = (unsigned int)SOS_Task::PushWait(v132, &v351) == 0;
  v133 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v134 = *(_QWORD *)(v133 + 256);
  if ( !v134 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v134 = *(_QWORD *)(v133 + 256);
  }
  v350 = v134;
  v349 = (*(_DWORD *)(v134 + 800) >> 11) & 1;
  if ( v349 || (*(_BYTE *)(v134 + 800) & 4) == 0 )
  {
    v348 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v134 + 608) + 8LL))(*(_QWORD *)(v134 + 608));
  }
  else
  {
    v348 = 0;
  }
  ((void (__fastcall *)(struct IUnknown *, __int64, _QWORD))v120->lpVtbl[2].QueryInterface)(v120, v150, 0);
  v145 = &v348;
  if ( v348 )
  {
    if ( v349 )
      *(_DWORD *)(v350 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v350 + 608) + 16LL))(
        *(_QWORD *)(v350 + 608),
        v350,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v351);
  *(_DWORD *)(v347 + 616) &= ~v346;
  v156 = &CWriterLockBytes::`vftable';
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v157 + 16LL))(v157);
  operator delete[](v159);
  v159 = 0;
  if ( v154 )
    (*(void (__fastcall **)(struct ILockBytesSS *))(*(_QWORD *)v154 + 16LL))(v154);
  operator delete[](0);
  CAutoClearXVariant::~CAutoClearXVariant(&v206);
  operator delete(v155, 1u);
  ((void (__fastcall *)(struct IUnknown *))v120->lpVtbl->Release)(v120);
  CColMetaData::~CColMetaData((CColMetaData *)v385);
  TaskFree(v162);
  TaskFree(v151);
  if ( v166 )
    ((void (__fastcall *)(struct IUnknown *))v166->lpVtbl->Release)(v166);
  if ( v165 )
    ((void (__fastcall *)(struct IAccessor *))v165->lpVtbl->Release)(v165);
  CAutoClearXVariant::~CAutoClearXVariant(&v399);
  COleDbParams::~COleDbParams((COleDbParams *)&v169);
  if ( v168 )
    ((void (__fastcall *)(struct IUnknown *))v168->lpVtbl->Release)(v168);
  if ( v146 )
    ((void (__fastcall *)(struct IUnknown *))v146->lpVtbl->Release)(v146);
  if ( v152 )
    ((void (__fastcall *)(struct IUnknown *))v152->lpVtbl->Release)(v152);
  if ( v153 )
    ((void (__fastcall *)(struct IUnknown *))v153->lpVtbl->Release)(v153);
  if ( Session )
    CRemSess::ReleaseSession(Session, 0, 0);
  v420 = 0;
  if ( byte_1030905C0 && *(_OWORD *)&v419 != v420 )
    PolyBaseAuthorizationTable::RemovePolyBaseRequest((PolyBaseAuthorizationTable *)g_PolyBaseAuthorizationTable, &v419);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v161 + 72LL))(v161, 1);
}

```

## disassembly

```asm
0x100c22230  push    rbp
0x100c22232  push    rsi
0x100c22233  push    rdi
0x100c22234  push    r12
0x100c22236  push    r13
0x100c22238  push    r14
0x100c2223a  push    r15
0x100c2223c  lea     rbp, [rsp-8710h]
0x100c22244  mov     eax, 8810h
0x100c22249  call    _alloca_probe
0x100c2224e  sub     rsp, rax
0x100c22251  mov     [rbp+8740h+var_7ED0], 0FFFFFFFFFFFFFFFEh
0x100c2225c  mov     [rsp+8840h+arg_8], rbx
0x100c22264  mov     rax, cs:__security_cookie
0x100c2226b  xor     rax, rsp
0x100c2226e  mov     [rbp+8740h+var_40], rax
0x100c22275  mov     [rbp+8740h+var_87A0], r9d
0x100c22279  mov     rdi, r8
0x100c2227c  mov     [rbp+8740h+var_87B0], r8
0x100c22280  mov     [rbp+8740h+var_8768], rcx
0x100c22284  mov     r15, [rcx+78h]
0x100c22288  mov     [rbp+8740h+var_8798], r15
0x100c2228c  mov     [rbp+8740h+var_8700], r15
0x100c22290  mov     [rsp+8840h+var_87C4], 5ED7h
0x100c22298  mov     byte ptr [rsp+8840h+SizeInWords], 3
0x100c2229d  mov     r9d, 5ED7h
0x100c222a3  lea     r8, aSqlNtdbmsMsqlD_28; "Sql\\Ntdbms\\msql\\ddl\\tabcreat.cpp"
0x100c222aa  mov     rdx, r15
0x100c222ad  mov     ecx, 710h
0x100c222b2  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x100c222b8  mov     [rbp+8740h+var_8708], rax
0x100c222bc  xor     r13d, r13d
0x100c222bf  test    rax, rax
0x100c222c2  jz      short loc_100C222D8
0x100c222c4  lea     r8d, [r13-1]
0x100c222c8  mov     rdx, r15
0x100c222cb  mov     rcx, rax
0x100c222ce  call    ??0COledbRangeExternalComputation@@QEAA@PEAVIMemObj@@W4EScaleOutHintTypes@@@Z; COledbRangeExternalComputation::COledbRangeExternalComputation(IMemObj *,EScaleOutHintTypes)
0x100c222d3  mov     rbx, rax
0x100c222d6  jmp     short loc_100C222DB
0x100c222d8  mov     rbx, r13
0x100c222db  mov     [rbp+8740h+var_8730], rbx
0x100c222df  lea     rdx, [rbx+6FCh]; struct _GUID *
0x100c222e6  lea     rcx, [rbp+8740h+var_7DB0]; this
0x100c222ed  call    ??0CAutoPolyBaseRequest@@QEAA@AEBU_GUID@@@Z; CAutoPolyBaseRequest::CAutoPolyBaseRequest(_GUID const &)
0x100c222f2  nop
0x100c222f3  mov     rax, [rbx]
0x100c222f6  mov     rcx, rbx
0x100c222f9  call    qword ptr [rax]
0x100c222fb  mov     r14, rax
0x100c222fe  mov     rcx, [rdi+8]
0x100c22302  mov     rdx, [rcx]
0x100c22305  call    qword ptr [rdx+10h]
0x100c22308  mov     rcx, [rdi+8]; this
0x100c2230c  call    ?PrepareWStrLog@CTestHookXmlOutput@@QEAAXXZ; CTestHookXmlOutput::PrepareWStrLog(void)
0x100c22311  mov     rcx, [rdi+8]
0x100c22315  mov     rax, [rcx+440h]
0x100c2231c  mov     [rbp+8740h+var_8770], rax
0x100c22320  xor     edx, edx; bool
0x100c22322  mov     rcx, r14; this
0x100c22325  call    ?GetSession@COledbConnect@@QEBAPEAVCRemSess@@_N@Z; COledbConnect::GetSession(bool)
0x100c2232a  mov     [rbp+8740h+var_8700], rax
0x100c2232e  mov     [rbp+8740h+var_8778], r13
0x100c22332  mov     byte ptr [rsp+8840h+SizeInWords], 1; bool
0x100c22337  lea     r9, IID_IUnknown; struct _GUID *
0x100c2233e  mov     r8, [rax+28h]; struct IUnknown *
0x100c22342  lea     r12, IID_IDBCreateCommand
0x100c22349  mov     rdx, r12; struct _GUID *
0x100c2234c  mov     rcx, r14; this
0x100c2234f  call    ?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100c22354  mov     rdi, rax
0x100c22357  mov     [rbp+8740h+var_8778], rax
0x100c2235b  mov     [rbp+8740h+var_8780], r13
0x100c2235f  mov     r10, [rax]
0x100c22362  lea     r9, [rbp+8740h+var_8780]
0x100c22366  lea     r8, IID_ICommandText
0x100c2236d  xor     edx, edx
0x100c2236f  mov     rcx, rax
0x100c22372  call    qword ptr [r10+18h]
0x100c22376  mov     esi, eax
0x100c22378  test    eax, eax
0x100c2237a  jns     loc_100C2245C
0x100c22380  lfence
0x100c22383  mov     rdx, [r14]
0x100c22386  mov     rcx, r14
0x100c22389  call    qword ptr [rdx+28h]
0x100c2238c  mov     rbx, rax
0x100c2238f  mov     rdx, [r14]
0x100c22392  mov     rcx, r14
0x100c22395  call    qword ptr [rdx+18h]
0x100c22398  mov     [rbp+8740h+var_8570], rdi
0x100c2239f  mov     [rbp+8740h+var_8568], r12
0x100c223a6  mov     [rbp+8740h+var_8560], esi
0x100c223ac  mov     [rbp+8740h+var_8558], rax
0x100c223b3  mov     [rbp+8740h+var_8550], rbx
0x100c223ba  mov     [rbp+8740h+var_8548], r13
0x100c223c1  mov     [rbp+8740h+var_8540], r13
0x100c223c8  mov     [rbp+8740h+var_8538], r13d
0x100c223cf  mov     [rbp+8740h+var_8534], 0FFFFFFFFh
0x100c223d9  mov     [rbp+8740h+var_8530], r13
0x100c223e0  mov     [rbp+8740h+var_8528], r13d
0x100c223e7  and     [rbp+8740h+var_8524], 0FEh
0x100c223ee  lea     rcx, [rbp+8740h+var_8570]; this
0x100c223f5  call    ?FPrintSQLServerError@COledbError@@AEAA_NXZ; COledbError::FPrintSQLServerError(void)
0x100c223fa  test    al, al
0x100c223fc  jz      short loc_100C22414
0x100c223fe  mov     edx, 5
0x100c22403  lea     ecx, [rdx+44h]
0x100c22406  lea     r9d, [rdx-4]
0x100c2240a  lea     r8d, [rdx+14h]
0x100c2240e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100c22414  lea     rcx, [rbp+8740h+var_8570]; this
0x100c2241b  call    ?PrintMsgUsingHRESULT@COledbError@@AEAAXXZ; COledbError::PrintMsgUsingHRESULT(void)
0x100c22420  mov     rax, [rbp+8740h+var_8550]
0x100c22427  mov     [rsp+8840h+var_8818], rax
0x100c2242c  mov     rax, [rbp+8740h+var_8558]
0x100c22433  mov     [rsp+8840h+SizeInWords], rax
0x100c22438  mov     edx, 5
0x100c2243d  lea     ecx, [rdx+44h]
0x100c22440  lea     r9d, [rdx-3]
0x100c22444  lea     r8d, [rdx+0Bh]
0x100c22448  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100c2244e  nop
0x100c2244f  mov     rcx, [rbp+8740h+var_8548]
0x100c22456  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100c2245c  mov     [rbp+8740h+var_87A8], r13
0x100c22460  mov     byte ptr [rsp+8840h+SizeInWords], 1; bool
0x100c22465  lea     rdi, IID_IUnknown
0x100c2246c  mov     r9, rdi; struct _GUID *
0x100c2246f  mov     r8, [rbp+8740h+var_8780]; struct IUnknown *
0x100c22473  lea     rdx, IID_ICommandText; struct _GUID *
0x100c2247a  mov     rcx, r14; this
0x100c2247d  call    ?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100c22482  mov     rbx, rax
0x100c22485  mov     [rbp+8740h+var_87B8], rax
0x100c22489  mov     [rbp+8740h+var_87A8], rax
0x100c2248d  mov     r9, [rax]
0x100c22490  lea     r8, aCallSpValidate; "{? = call sp_validate_ddl(?,?)}"
0x100c22497  lea     rdx, DBGUID_SQL
0x100c2249e  mov     rcx, rax
0x100c224a1  call    qword ptr [r9+38h]
0x100c224a5  mov     [rbp+8740h+var_86F8], r13
0x100c224a9  mov     byte ptr [rsp+8840h+SizeInWords], 1; bool
0x100c224ae  mov     r9, rdi; struct _GUID *
0x100c224b1  mov     r8, rbx; struct IUnknown *
0x100c224b4  lea     rdx, IID_ICommandWithParameters; struct _GUID *
0x100c224bb  mov     rcx, r14; this
0x100c224be  call    ?GetInterface@COledbConnect@@QEBAPEAUIUnknown@@AEBU_GUID@@PEAU2@0_N@Z; COledbConnect::GetInterface(_GUID const &,IUnknown *,_GUID const &,bool)
0x100c224c3  mov     [rbp+8740h+var_87C0], rax
0x100c224c7  mov     [rbp+8740h+var_86F8], rax
0x100c224cb  mov     [rbp+8740h+var_86F0], r15
0x100c224cf  mov     [rbp+8740h+var_86E8], r13d
0x100c224d3  mov     [rbp+8740h+var_86C0], r13
0x100c224da  mov     [rbp+8740h+var_86C8], r13
0x100c224de  xorps   xmm0, xmm0
0x100c224e1  movdqa  [rbp+8740h+var_86E0], xmm0
0x100c224e6  mov     [rbp+8740h+var_86D0], r13
0x100c224ea  mov     [rbp+8740h+var_86B8], r13
0x100c224f1  mov     [rbp+8740h+var_86B0], r13
0x100c224f8  mov     [rbp+8740h+var_86A8], 1
0x100c22502  mov     [rbp+8740h+var_86A4], 1
0x100c2250c  mov     [rbp+8740h+var_86A0], r13
0x100c22513  mov     edx, 3; unsigned int
0x100c22518  lea     rcx, [rbp+8740h+var_86F0]; this
0x100c2251c  call    ?Init@COleDbParams@@QEAAXK@Z; COleDbParams::Init(ulong)
0x100c22521  mov     r15, [rbp+8740h+var_86F0]
0x100c22525  mov     r12, [rbp+8740h+var_86B0]
0x100c2252c  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c22533  cmp     al, 62h ; 'b'
0x100c22535  jnz     short loc_100C22569
0x100c22537  cmp     qword ptr [r12], 0
0x100c2253c  jnz     short loc_100C22571
0x100c2253e  mov     byte ptr [rsp+8840h+SizeInWords], 1
0x100c22543  mov     r9d, 1FFh
0x100c22549  lea     r8, aSqlNtdbmsQuery_159; "sql\\ntdbms\\query\\qpshared\\oledbutl."...
0x100c22550  mov     rdx, r15
0x100c22553  mov     ecx, 1F78h
0x100c22558  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100c2255e  mov     [r12], rax
0x100c22562  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c22569  cmp     al, 1Fh
0x100c2256b  jz      short loc_100C2257A
0x100c2256d  test    al, al
0x100c2256f  jz      short loc_100C2257A
0x100c22571  lea     rdx, ?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c22578  jmp     short loc_100C22581
0x100c2257a  lea     rdx, ?tiEmpty@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiEmpty
0x100c22581  mov     r9d, 1
0x100c22587  mov     rbx, [rbp+8740h+var_86C8]
0x100c2258b  mov     r8d, r9d
0x100c2258e  mov     rcx, rbx
0x100c22591  call    cs:__imp_?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z; InitDbBind(tagDBBINDING *,CTypeInfo const &,int,int)
0x100c22597  mov     eax, 0FFFFh
0x100c2259c  mov     r8d, 0Dh
0x100c225a2  lea     rdx, ?m_szName@CXplOp_ParameterSensitivePredicate@@0QEBDEB; char const * const CXplOp_ParameterSensitivePredicate::m_szName
0x100c225a9  cmp     word ptr cs:xmmword_102EF7C30, ax
0x100c225b0  jz      short loc_100C225CB
0x100c225b2  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c225b9  movzx   ecx, byte ptr [rax+rdx+201B6B0h]
0x100c225c1  cmp     byte ptr [rcx+rdx+2AF7BF8h], 0
0x100c225c9  jz      short loc_100C225EE
0x100c225cb  mov     [rbx+54h], r8w
0x100c225d0  mov     qword ptr [rbx+48h], 7FFFFFFFh
0x100c225d8  or      dword ptr [rbx+38h], 2
0x100c225dc  mov     qword ptr [rbx+10h], 8
0x100c225e4  call    cs:__imp_?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ; DbObjSequentialStream(void)
0x100c225ea  mov     [rbx+28h], rax
0x100c225ee  mov     [rbx+3Ch], r13d
0x100c225f2  mov     qword ptr [rbx], 1
0x100c225f9  or      dword ptr [rbx+40h], 3
0x100c225fd  mov     r13, qword ptr [rbp+8740h+var_86E0]
0x100c22601  mov     qword ptr [r13+0], 1
0x100c22609  lea     r8, ?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c22610  mov     rsi, qword ptr [rbp+8740h+var_86E0+8]
0x100c22614  mov     rdx, rsi
0x100c22617  mov     rcx, r15
0x100c2261a  call    cs:__imp_?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z; InitDbParamBindInfo(IMemObj *,tagDBPARAMBINDINFO *,CTypeInfo const &)
0x100c22620  mov     r8d, [r13+0]; unsigned __int64
0x100c22624  lea     r9, ?tiI4@CTypeInfo@@2V1@B; struct CTypeInfo *
0x100c2262b  mov     rdx, [rbp+8740h+var_86D0]; struct tagSSPARAMPROPS *
0x100c2262f  mov     rcx, r15; struct IMemObj *
0x100c22632  call    ?InitDbParamProperties@@YAXPEAVIMemObj@@PEAUtagSSPARAMPROPS@@_KAEBVCTypeInfo@@@Z; InitDbParamProperties(IMemObj *,tagSSPARAMPROPS *,unsigned __int64,CTypeInfo const &)
0x100c22637  or      dword ptr [rsi+18h], 3
0x100c2263b  mov     rdi, [rbp+8740h+var_86C0]
0x100c22642  mov     dword ptr [rdi], 3
0x100c22648  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c2264f  cmp     al, 1Fh
0x100c22651  jnz     short loc_100C22660
0x100c22653  mov     dword ptr [rdi], 3
0x100c22659  movzx   eax, byte ptr cs:?tiI4@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiI4
0x100c22660  test    al, al
0x100c22662  jnz     short loc_100C2266A
0x100c22664  mov     dword ptr [rdi], 0Dh
0x100c2266a  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c22671  cmp     al, 62h ; 'b'
0x100c22673  jnz     short loc_100C226A9
0x100c22675  cmp     qword ptr [r12+8], 0
0x100c2267b  jnz     short loc_100C226B1
0x100c2267d  mov     byte ptr [rsp+8840h+SizeInWords], 1
0x100c22682  mov     r9d, 1FFh
0x100c22688  lea     r8, aSqlNtdbmsQuery_159; "sql\\ntdbms\\query\\qpshared\\oledbutl."...
0x100c2268f  mov     rdx, r15
0x100c22692  mov     ecx, 1F78h
0x100c22697  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100c2269d  mov     [r12+8], rax
0x100c226a2  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c226a9  cmp     al, 1Fh
0x100c226ab  jz      short loc_100C226BA
0x100c226ad  test    al, al
0x100c226af  jz      short loc_100C226BA
0x100c226b1  lea     rdx, ?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c226b8  jmp     short loc_100C226C1
0x100c226ba  lea     rdx, ?tiEmpty@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiEmpty
0x100c226c1  mov     r9d, 1
0x100c226c7  mov     r8d, r9d
0x100c226ca  lea     rcx, [rbx+58h]
0x100c226ce  call    cs:__imp_?InitDbBind@@YAXPEAUtagDBBINDING@@AEBVCTypeInfo@@HH@Z; InitDbBind(tagDBBINDING *,CTypeInfo const &,int,int)
0x100c226d4  mov     eax, 0FFFFh
0x100c226d9  cmp     word ptr cs:xmmword_102F39930, ax
0x100c226e0  jz      short loc_100C22702
0x100c226e2  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c226e9  lea     rdx, ?m_szName@CXplOp_ParameterSensitivePredicate@@0QEBDEB; char const * const CXplOp_ParameterSensitivePredicate::m_szName
0x100c226f0  movzx   ecx, byte ptr [rax+rdx+201B6B0h]
0x100c226f8  cmp     byte ptr [rcx+rdx+2AF7BF8h], 0
0x100c22700  jz      short loc_100C22735
0x100c22702  mov     eax, 0Dh
0x100c22707  mov     [rbx+0ACh], ax
0x100c2270e  mov     qword ptr [rbx+0A0h], 7FFFFFFFh
0x100c22719  or      dword ptr [rbx+90h], 2
0x100c22720  mov     qword ptr [rbx+68h], 8
0x100c22728  call    cs:__imp_?DbObjSequentialStream@@YAPEAUtagDBOBJECT@@XZ; DbObjSequentialStream(void)
0x100c2272e  mov     [rbx+80h], rax
0x100c22735  mov     dword ptr [rbx+94h], 0
0x100c2273f  mov     qword ptr [rbx+58h], 2
0x100c22747  or      dword ptr [rbx+98h], 1
0x100c2274e  add     qword ptr [rbx+70h], 50h ; 'P'
0x100c22753  add     qword ptr [rbx+60h], 50h ; 'P'
0x100c22758  add     qword ptr [rbx+68h], 50h ; 'P'
0x100c2275d  mov     qword ptr [r13+8], 2
0x100c22765  lea     rdx, [rsi+20h]
0x100c22769  lea     r8, ?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c22770  mov     rcx, r15
0x100c22773  call    cs:__imp_?InitDbParamBindInfo@@YAXPEAVIMemObj@@PEAUtagDBPARAMBINDINFO@@AEBVCTypeInfo@@@Z; InitDbParamBindInfo(IMemObj *,tagDBPARAMBINDINFO *,CTypeInfo const &)
0x100c22779  mov     r8d, [r13+8]; unsigned __int64
0x100c2277d  mov     rdx, [rbp+8740h+var_86D0]
0x100c22781  add     rdx, 18h; struct tagSSPARAMPROPS *
0x100c22785  lea     r9, ?tiVarWstrUnlim@CTypeInfo@@2V1@B; struct CTypeInfo *
0x100c2278c  mov     rcx, r15; struct IMemObj *
0x100c2278f  call    ?InitDbParamProperties@@YAXPEAVIMemObj@@PEAUtagSSPARAMPROPS@@_KAEBVCTypeInfo@@@Z; InitDbParamProperties(IMemObj *,tagSSPARAMPROPS *,unsigned __int64,CTypeInfo const &)
0x100c22794  or      dword ptr [rsi+38h], 1
0x100c22798  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c2279f  cmp     al, 1Fh
0x100c227a1  jnz     short loc_100C227B1
0x100c227a3  mov     dword ptr [rdi+50h], 3
0x100c227aa  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
0x100c227b1  test    al, al
0x100c227b3  jnz     short loc_100C227C4
0x100c227b5  mov     eax, 0Dh
0x100c227ba  mov     [rdi+50h], eax
0x100c227bd  movzx   eax, byte ptr cs:?tiVarWstrUnlim@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiVarWstrUnlim
  ... truncated ...
```
