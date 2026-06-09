# PqoBuild(COptExpr *,CEsCompGroup *,IMemObj *,IMemObj *,CEnvCollection *,ulong,wchar_t const *,int,short,int,CCompExecCtxtStmt const &,IQueryWithFeedback *,CStatementDescription const &,bool,bool)

- ea: `0x100490dc0`
- end: `0x100490e05`
- name: `?PqoBuild@@YAPEAVIQueryObj@@PEAVCOptExpr@@PEAVCEsCompGroup@@PEAVIMemObj@@2PEAVCEnvCollection@@KPEB_WHFHAEBVCCompExecCtxtStmt@@PEAVIQueryWithFeedback@@AEBVCStatementDescription@@_N8@Z`
- size: `69`
- prototype: `struct IQueryObj *__fastcall(struct COptExpr *, struct CEsCompGroup *, struct IMemObj *, struct IMemObj *, struct CEnvCollection *, unsigned int, const wchar_t *, __int64, __int16, __int64, const struct CCompExecCtxtStmt *, struct IQueryWithFeedback *, const struct CStatementDescription *, bool, bool)`
- caller_count: `2`
- callee_count: `128`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x10046e680`
- `0x100ea88e0`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x1004022e0`
- `0x100409010`
- `0x100409b70`
- `0x10040b790`
- `0x10040be50`
- `0x10040bf50`
- `0x10040bfa0`
- `0x10040bff0`
- `0x10040c070`
- `0x1004112c0`
- `0x100439ca0`
- `0x10045a980`
- `0x10045c260`
- `0x10045f4f0`
- `0x10046cee0`
- `0x10046d1f0`
- `0x10046d8a0`
- `0x10046ee60`
- `0x100471a70`
- `0x100473380`
- `0x100473420`
- `0x100473ae0`
- `0x100474280`
- `0x1004747c0`
- `0x1004748a0`
- `0x100474930`
- `0x1004749b0`
- `0x100474b00`
- `0x100474b30`
- `0x100474b70`
- `0x100474c30`
- `0x100475550`
- `0x10047dfe0`
- `0x10047e0c0`
- `0x100480060`
- `0x100480400`
- `0x100481150`
- `0x100487900`
- `0x100487b60`
- `0x100487e30`
- `0x10048b8d0`
- `0x10048b940`
- `0x10048b9d0`
- `0x10048c6f0`
- `0x10048c710`
- `0x10048c740`

## import_xrefs

- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100470893`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1018df58b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10047047e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100470c6e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1007156ae`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e01ae`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e0229`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e0276`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e16e8`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e172a`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e1805`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e190c`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e1a0d`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e01ae`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e0229`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e0276`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e16e8`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e172a`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e1805`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e190c`
- `sqldk!?GetStream@TraceStreamHolder@@QEAAAEAVSOS_TraceStream@@XZ` at `0x1018e1a0d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e01c2`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e023d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e028a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e16fc`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e173e`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e176f`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e17a3`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e17d4`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1819`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e184a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1881`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e18b2`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e18e6`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1920`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a21`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a4a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a7b`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e01c2`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e023d`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e028a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e16fc`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e173e`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e176f`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e17a3`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e17d4`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1819`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e184a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1881`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e18b2`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e18e6`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1920`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a21`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a4a`
- `sqldk!??0TraceStreamProtector@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e1a7b`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e01e2`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e0268`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e02a4`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e171c`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e175e`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1792`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e17c3`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e17f7`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1839`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1870`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18a1`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18d5`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18fe`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e193a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a39`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a6a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a93`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e01e2`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e0268`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e02a4`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e171c`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e175e`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1792`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e17c3`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e17f7`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1839`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1870`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18a1`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18d5`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e18fe`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e193a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a39`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a6a`
- `sqldk!??1TraceStreamProtector@@QEAA@XZ` at `0x1018e1a93`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e02b3`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e1949`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e1aa7`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e02b3`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e1949`
- `sqldk!??1TraceStreamHolder@@QEAA@XZ` at `0x1018e1aa7`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e019f`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e16d3`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e19fe`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e019f`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e16d3`
- `sqldk!??0TraceStreamHolder@@QEAA@AEAVSOS_TraceStream@@@Z` at `0x1018e19fe`
- `sqldk!?SetDescriptiveName@CMallocSpy@@QEAAXPEBD@Z` at `0x1018debb3`
- `sqldk!?SetDescriptiveName@CMallocSpy@@QEAAXPEBD@Z` at `0x1018debb3`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x10046f2e3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10046f0a9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10046f0a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018df8e4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e070f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018df8e4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e070f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f374`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f3d9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f432`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f5b6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004710f4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018df13c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018df456`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018dfa27`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018dfbaa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0567`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0635`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0d2d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0ed7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f374`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f3d9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f432`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10046f5b6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004710f4`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018df13c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018df456`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018dfa27`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018dfbaa`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0567`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0635`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0d2d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1018e0ed7`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018e1b71`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018e1bca`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018e1b71`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1018e1bca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df96f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0103`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0167`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e08fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0ab8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1212`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1c27`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df96f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0103`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0167`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e08fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0ab8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1212`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1c27`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046f11b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046f134`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046f11b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046f134`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10046f15e`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10046f336`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10046f15e`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10046f336`
- `sqldk!SystemThread_TlsIndex` at `0x10046f0ee`
- `sqldk!SystemThread_TlsIndex` at `0x10046f289`
- `sqldk!SystemThread_TlsIndex` at `0x10046f747`
- `sqldk!SystemThread_TlsIndex` at `0x10046f7a7`
- `sqldk!SystemThread_TlsIndex` at `0x10046f7fa`
- `sqldk!SystemThread_TlsIndex` at `0x10046f879`
- `sqldk!SystemThread_TlsIndex` at `0x10046fb0c`
- `sqldk!SystemThread_TlsIndex` at `0x10046fba5`
- `sqldk!SystemThread_TlsIndex` at `0x10046fcbd`
- `sqldk!SystemThread_TlsIndex` at `0x10046fd06`
- `sqldk!SystemThread_TlsIndex` at `0x10046fdc8`
- `sqldk!SystemThread_TlsIndex` at `0x10046fe58`
- `sqldk!SystemThread_TlsIndex` at `0x10046ff4a`
- `sqldk!SystemThread_TlsIndex` at `0x10046ffde`
- `sqldk!SystemThread_TlsIndex` at `0x1004700d4`
- `sqldk!SystemThread_TlsIndex` at `0x100470149`
- `sqldk!SystemThread_TlsIndex` at `0x100470222`
- `sqldk!SystemThread_TlsIndex` at `0x10047036a`
- `sqldk!SystemThread_TlsIndex` at `0x100470781`
- `sqldk!SystemThread_TlsIndex` at `0x100470c18`
- `sqldk!SystemThread_TlsIndex` at `0x100470e19`
- `sqldk!SystemThread_TlsIndex` at `0x100470fdb`
- `sqldk!SystemThread_TlsIndex` at `0x10047151f`
- `sqldk!SystemThread_TlsIndex` at `0x100471686`
- `sqldk!SystemThread_TlsIndex` at `0x100471786`
- `sqldk!SystemThread_TlsIndex` at `0x10047181f`
- `sqldk!SystemThread_TlsIndex` at `0x100471913`
- `sqldk!SystemThread_TlsIndex` at `0x10047199a`
- `sqldk!SystemThread_TlsIndex` at `0x1005c1aab`
- `sqldk!SystemThread_TlsIndex` at `0x1005c1b86`
- `sqldk!SystemThread_TlsIndex` at `0x100629d38`
- `sqldk!SystemThread_TlsIndex` at `0x1018dec9a`
- `sqldk!SystemThread_TlsIndex` at `0x1018def9d`
- `sqldk!SystemThread_TlsIndex` at `0x1018df07e`
- `sqldk!SystemThread_TlsIndex` at `0x1018df6f2`
- `sqldk!SystemThread_TlsIndex` at `0x1018df810`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfd18`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfdab`

## string_xrefs

- `0x1018e1707`: `End of query plan compilation,`
- `0x1018e1a55`: `Query Compilation completed`
- `0x1018e06fc`: `Sql\Ntdbms\include\common\stdarray.inl`
- `0x1018df8d8`: `IsVdwFrontendExtDistrComputationEnabled()`

## pseudocode

```c
// Hidden C++ exception states: #wind=76
struct IQueryObj *__fastcall PqoBuild(
        struct COptExpr *a1,
        struct CEsCompGroup *a2,
        struct IMemObj *a3,
        struct IMemObj *a4,
        struct CEnvCollection *a5,
        unsigned int a6,
        const wchar_t *a7,
        __int64 a8,
        unsigned __int16 a9,
        __int64 a10,
        CExecLvlRepresentation **a11,
        struct IQueryWithFeedback *a12,
        const struct CStatementDescription *a13,
        bool a14,
        bool a15)
{
  int v15; // eax
  char v17; // al
  char v18; // bl
  __int64 v19; // rsi
  unsigned __int64 v20; // rdi
  const wchar_t *v21; // rbx
  __crt_locale_pointers *DefaultLocale; // rax
  __int64 v23; // r8
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  struct MemoryClerk *v34; // rax
  char *v35; // r8
  __int64 v36; // rcx
  struct IMemObj *MemObject; // r14
  CMallocSpy *v38; // rax
  __int64 v39; // rdi
  struct QueryTraceAndRuleHints **v40; // r13
  struct CQOQueryHints *Hints; // rcx
  CExecLvlRepresentation **v42; // r9
  __int64 v43; // r8
  CExecLvlRepresentation *v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rcx
  struct CAutoSessionTraceFlagOrQORuleToggler *v47; // rax
  __int64 MemoryClerk; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  struct IMemObj *v51; // r15
  CValRefTracker *v52; // rax
  struct IValRefTracker *v53; // rbx
  CVRTableComp *v54; // rax
  CVRTableComp *v55; // r13
  CVRTableOpt *v56; // rax
  CVRTableOpt *v57; // r12
  struct CQNameManager *CQNameManager; // rbx
  struct CQNameManager *v59; // rax
  unsigned __int16 v60; // cx
  unsigned __int16 v61; // r14
  struct IQueryCompile *IQueryCompile; // rbx
  struct IMemObj **v63; // rax
  __int64 v64; // rax
  struct QueryHints *v65; // r14
  int OptimizerCompatLevel; // eax
  __int64 v67; // r8
  struct CSessionTraceFlags **v68; // rax
  struct CSessionTraceFlags *v69; // rcx
  CExecLvlRepresentation *v70; // rcx
  unsigned __int8 v71; // al
  char v72; // al
  char v73; // al
  __int64 v74; // rbx
  struct IMemObj *v75; // rax
  struct CQOQueryHints *v76; // r13
  char v77; // r9
  struct DbccThreadContext *Context; // rax
  int v79; // r9d
  int v80; // r9d
  char v81; // al
  char v82; // dl
  __int64 v83; // rax
  struct CSessionTraceFlags **v84; // rax
  struct CSessionTraceFlags *v85; // rcx
  __int64 v86; // rax
  struct CSessionTraceFlags **v87; // rax
  struct CSessionTraceFlags *v88; // rcx
  char v89; // dl
  __int64 v90; // rax
  struct CSessionTraceFlags **v91; // rax
  struct CSessionTraceFlags *v92; // rcx
  __int64 v93; // r8
  COptContext *v94; // rcx
  __int64 v95; // rax
  struct CSessionTraceFlags **v96; // rax
  struct CSessionTraceFlags *v97; // rcx
  __int64 v98; // rax
  struct CSessionTraceFlags **v99; // rax
  struct CSessionTraceFlags *v100; // rcx
  char v101; // al
  char v102; // al
  __int64 v103; // r8
  struct CSessionTraceFlags **v104; // rax
  struct CSessionTraceFlags *v105; // rcx
  __int64 v106; // rax
  struct CSessionTraceFlags **v107; // rax
  struct CSessionTraceFlags *v108; // rcx
  __int64 v109; // r8
  struct CSessionTraceFlags **v110; // rax
  struct CSessionTraceFlags *v111; // rcx
  __int64 v112; // rax
  struct CSessionTraceFlags **v113; // rax
  struct CSessionTraceFlags *v114; // rcx
  CExecLvlRepresentation *v115; // rcx
  unsigned __int8 v116; // al
  __int64 v117; // rcx
  __int64 v118; // rdx
  struct IQueryCompile *v119; // rbx
  __int64 v120; // r8
  unsigned __int64 v121; // rcx
  struct CSessionTraceFlags *v122; // rax
  unsigned __int64 v123; // rcx
  struct CSessionTraceFlags *v124; // rax
  __int64 v125; // r8
  CExecLvlRepresentation *v126; // rax
  __int64 v127; // r8
  char v128; // cl
  int v129; // eax
  bool v130; // zf
  int v131; // ecx
  char v132; // dl
  char v133; // cl
  bool v134; // dl
  bool v135; // al
  __int64 v136; // rdx
  __int64 v137; // rcx
  unsigned int v138; // r15d
  __int64 v139; // rbx
  unsigned __int16 v140; // ax
  __int64 v141; // rbx
  struct COptInterfaces *v142; // r13
  struct COptExpr *v143; // r14
  char v144; // al
  struct IMemObj *v145; // rbx
  CMATGen *v146; // r15
  char v147; // ecx^2
  CExecLvlRepresentation *v148; // r13
  __int64 v149; // rbx
  __int64 v150; // rbx
  __int64 v151; // rbx
  bool v152; // r15
  bool v153; // r12
  char v154; // r9
  __int64 v155; // rcx
  char v156; // r11
  char v157; // r11
  bool v158; // al
  bool v159; // al
  QueryHints *v160; // r13
  bool v161; // bl
  __int64 v162; // rax
  struct CSessionTraceFlags *v163; // rcx
  bool v164; // dl
  bool v165; // r15
  char v166; // al
  char v167; // r10
  bool v168; // bl
  __int64 *v169; // rcx
  __int64 v170; // rdx
  struct CSessionTraceFlags *v171; // rcx
  int v172; // eax
  __int64 v173; // rbx
  QueryHints *v174; // rcx
  __int64 v175; // rbx
  struct IMemObj *v176; // r12
  struct COptExpr *v177; // r15
  __int64 v178; // rdx
  struct CSessionTraceFlags *v179; // rcx
  int v180; // eax
  __int64 v181; // rbx
  __int64 v182; // rcx
  bool v183; // bl
  CInterestingPredicateExplorer *v184; // r13
  unsigned int *v185; // r14
  __int64 v186; // r8
  char v187; // al
  __int64 v188; // rbx
  __int64 v189; // rax
  double v190; // xmm6_8
  CInterestingPredicateExplorer *v191; // rax
  int v192; // eax
  __int64 v193; // rax
  struct CQte *v194; // rax
  struct CTelemetryPackageContainer *v195; // rdx
  _QWORD *v196; // r8
  __int64 v197; // r9
  char v198; // al
  char v199; // r9
  CExecLvlRepresentation *v200; // r13
  __int64 v201; // rbx
  CExecLvlRepresentation **v202; // r15
  _QWORD *v203; // rbx
  DataVirtualizationResource *v204; // rcx
  __int64 v205; // rbx
  struct IQueryObj *v206; // r15
  __int64 v207; // rdx
  int *v208; // rax
  bool v209; // cl
  CMultiPlanFeedback *v210; // rbx
  __int64 v211; // rbx
  __int64 v212; // r8
  const struct CCompExecCtxtStmt *v213; // r15
  __int64 v214; // rdx
  struct CSessionTraceFlags *v215; // rcx
  int v216; // eax
  double v217; // xmm6_8
  __int64 v218; // rax
  struct CQNameManager *v219; // rcx
  __int64 v220; // rdx
  __int64 v221; // r8
  __int64 v222; // rax
  __int64 v223; // rdx
  __int64 v224; // rax
  __int64 v225; // r9
  __int64 v226; // r8
  struct IMemObj *v227; // rbx
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // rdx
  struct CSessionTraceFlags *v232; // rcx
  int v233; // eax
  struct IQueryObj *v234; // rbx
  BatchModeHeuristics *v235; // r14
  char v236; // al
  void *v237; // rbx
  struct Worker *v238; // rcx
  __int64 v239; // rbx
  struct IMemObj *v240; // rdi
  struct IMemObj *v241; // r14
  __int64 v242; // rbx
  struct Worker *v243; // rcx
  __int64 *v244; // rbx
  __int64 v245; // rbx
  __int64 v247; // r8
  struct CSessionTraceFlags **v248; // rax
  struct CSessionTraceFlags *v249; // rcx
  __int64 v250; // r8
  struct CSessionTraceFlags **v251; // rax
  struct CSessionTraceFlags *v252; // rcx
  struct CDataExportParameters *v253; // rax
  CDataExportParameters *v254; // rcx
  __int64 v255; // rax
  __int64 v256; // rcx
  bool v257; // r15
  __int64 v258; // rbx
  __int64 v259; // rax
  __int64 v260; // rax
  __int64 v261; // rax
  unsigned int k; // ebx
  __int64 v263; // rax
  unsigned int v264; // ecx
  __int64 v265; // r15
  bool v266; // di
  struct IMemObj *v267; // rbx
  CCompTimeTrace *v268; // rcx
  __int64 v269; // rbx
  _QWORD *v270; // r8
  __int64 v271; // rax
  unsigned __int64 v272; // rcx
  unsigned __int64 v273; // rax
  __int64 v274; // rcx
  struct CEsCompGroup *v275; // rbx
  __int64 v276; // rdi
  _QWORD *v277; // r8
  __int64 v278; // rax
  unsigned __int64 v279; // rcx
  unsigned __int64 v280; // rax
  __int64 v281; // rcx
  int v282; // edx
  DataVirtualizationResource *v283; // rcx
  __int64 v284; // rdx
  struct CSessionTraceFlags *v285; // rcx
  int v286; // eax
  struct SOS_TraceStream *v287; // rbx
  int v288; // ebx
  void ***v289; // rdi
  __int64 v290; // rdx
  struct CSessionTraceFlags *v291; // rcx
  int v292; // eax
  int v293; // ecx
  int v294; // edx
  int v295; // edx
  int v296; // edx
  CCompTimeTrace *v297; // rcx
  __int64 v298; // rbx
  _QWORD *v299; // r8
  __int64 v300; // rax
  unsigned __int64 v301; // rcx
  unsigned __int64 v302; // rax
  __int64 v303; // rcx
  struct CQNameManager *v304; // rbx
  __int64 v305; // rdi
  _QWORD *v306; // r8
  __int64 v307; // rax
  unsigned __int64 v308; // rcx
  unsigned __int64 v309; // rax
  __int64 v310; // rcx
  __int64 v311; // rbx
  __int64 v312; // rax
  __int64 v313; // rax
  char v314; // r9
  char v315; // r10
  __int64 v316; // rbx
  _QWORD *v317; // rax
  _QWORD *v318; // r8
  __int64 v319; // rax
  _QWORD *v320; // rcx
  unsigned __int64 v321; // rcx
  unsigned __int64 v322; // rax
  __int64 v323; // rcx
  int v324; // r9d
  _DWORD *v325; // rax
  int v326; // r9d
  char *v327; // rax
  char *v328; // rax
  CExecLvlRepresentation *v329; // rcx
  unsigned __int8 v330; // al
  char v331; // al
  __int64 v332; // rax
  struct CSessionTraceFlags **v333; // rax
  struct CSessionTraceFlags *v334; // rcx
  CQoTelemetryAgg *v335; // rax
  CQoTelemetryAgg *v336; // rax
  int *v337; // rax
  int v338; // eax
  char v339; // al
  unsigned int v340; // ecx
  __int64 v341; // rcx
  _QWORD *v342; // rax
  __int64 v343; // rbx
  __int64 v344; // rdx
  __int64 v345; // rcx
  __int64 v346; // rcx
  DBTABLE *v347; // rcx
  __int64 v348; // rax
  unsigned __int8 v349; // cl
  char v350; // al
  char v351; // cl
  __int64 v352; // rax
  struct CSessionTraceFlags *v353; // rcx
  DBTABLE *v354; // rcx
  __int64 v355; // r14
  _QWORD *v356; // r8
  __int64 v357; // rax
  unsigned __int64 v358; // rcx
  unsigned __int64 v359; // rax
  __int64 v360; // rcx
  _DWORD *v361; // rax
  unsigned __int64 v362; // rbx
  char v363; // al
  _QWORD *v364; // rbx
  _QWORD *i; // rax
  struct IMemObj *v366; // r15
  char *v367; // rax
  struct DRgCId *v368; // rbx
  char *v369; // rax
  struct DRgCId *v370; // rdx
  struct IXteBuilder *v371; // rbx
  struct CQte *XteDummyConstScanWithOutput; // rax
  __int64 v373; // rcx
  __int64 v374; // rdx
  __int64 v375; // r14
  _QWORD *v376; // r8
  __int64 v377; // rax
  __int64 v378; // rcx
  unsigned __int64 v379; // rax
  unsigned __int64 v380; // rcx
  unsigned __int64 v381; // rax
  __int64 v382; // rcx
  int v383; // eax
  _QWORD *v384; // rcx
  __int64 v385; // rdx
  _QWORD *v386; // r14
  unsigned int v387; // r15d
  unsigned int j; // ebx
  char v389; // al
  __int64 v390; // rax
  CTableMetadata *v391; // rbx
  __int64 v392; // r11
  struct SOS_TraceStream *Stream; // rbx
  struct SOS_TraceStream *v394; // rbx
  struct SOS_TraceStream *v395; // rbx
  __int64 v396; // r14
  _QWORD *v397; // r8
  __int64 v398; // rax
  unsigned __int64 v399; // rcx
  unsigned __int64 v400; // rax
  __int64 v401; // rcx
  bool v402; // al
  __int64 v403; // rcx
  int v404; // eax
  int ii; // ebx
  unsigned int v406; // r15d
  unsigned int *v407; // rax
  unsigned int *v408; // rbx
  unsigned int v409; // r12d
  unsigned int v410; // eax
  _QWORD *v411; // rbx
  _OWORD *v412; // r15
  unsigned int v413; // ebx
  unsigned int v414; // eax
  __int64 v415; // rdx
  unsigned int v416; // ecx
  int v417; // edx
  unsigned int m; // r8d
  void *v419; // rcx
  unsigned int v420; // eax
  _QWORD *v421; // rax
  int v422; // ecx
  double v423; // xmm0_8
  unsigned __int64 v424; // rax
  CETelemetryPackage *v425; // rbx
  __int64 v426; // r14
  __int64 v427; // rax
  __int64 v428; // rcx
  unsigned __int64 v429; // rax
  unsigned __int64 v430; // rcx
  unsigned __int64 v431; // rax
  __int64 v432; // rcx
  __int64 v433; // r8
  __int64 v434; // r9
  _DWORD *v435; // rdx
  int v436; // eax
  int v437; // ecx
  int v438; // eax
  __int64 v439; // rbx
  void *v440; // rax
  struct CMemoXml *v441; // rax
  bool v442; // cl
  int v443; // eax
  __int64 v444; // rbx
  __int64 v445; // rax
  struct CRowsetFilesInfo *v446; // rax
  __int64 v447; // r14
  _QWORD *v448; // r8
  __int64 v449; // rax
  unsigned __int64 v450; // rcx
  unsigned __int64 v451; // rax
  __int64 v452; // rcx
  int *v453; // rcx
  __int64 v454; // rax
  int v455; // edx
  unsigned int n; // ebx
  struct CTelemetryPackage *v457; // r14
  CEncodeJsonUtil *v458; // rcx
  unsigned __int64 v459; // r14
  void *v460; // rcx
  int v461; // eax
  __int64 v462; // r14
  _QWORD *v463; // r8
  __int64 v464; // rax
  __int64 v465; // rcx
  unsigned __int64 v466; // rax
  unsigned __int64 v467; // rcx
  unsigned __int64 v468; // rax
  __int64 v469; // rcx
  struct CMemoXml *v470; // rdx
  struct SOS_TraceStream *v471; // rbx
  struct SOS_TraceStream *v472; // rbx
  struct SOS_TraceStream *v473; // rbx
  struct SOS_TraceStream *v474; // rbx
  struct SOS_TraceStream *v475; // rbx
  int v476; // ebx
  void ***v477; // r14
  __int64 v478; // rbx
  __int64 v479; // rax
  __int64 v480; // r9
  __int64 v481; // rdi
  _QWORD *v482; // r8
  __int64 v483; // rax
  unsigned __int64 v484; // rax
  unsigned __int64 v485; // rcx
  unsigned __int64 v486; // rax
  __int64 v487; // rcx
  __int64 v488; // rdi
  _QWORD *v489; // r8
  __int64 v490; // rax
  __int64 v491; // rdi
  _QWORD *v492; // r8
  unsigned __int64 v493; // rcx
  unsigned __int64 v494; // rax
  __int64 v495; // rcx
  unsigned __int64 v496; // rcx
  unsigned __int64 v497; // rax
  __int64 v498; // rcx
  int Locale; // [rsp+20h] [rbp-19A8h]
  int Localea; // [rsp+20h] [rbp-19A8h]
  _locale_t Localeb; // [rsp+20h] [rbp-19A8h]
  int v502; // [rsp+28h] [rbp-19A0h]
  int v503; // [rsp+28h] [rbp-19A0h]
  int v504; // [rsp+30h] [rbp-1998h]
  char v505; // [rsp+90h] [rbp-1938h]
  bool v506; // [rsp+91h] [rbp-1937h]
  struct IMemObj *v507; // [rsp+A0h] [rbp-1928h]
  struct COptExpr *v508; // [rsp+A8h] [rbp-1920h]
  unsigned int CurrentDb; // [rsp+B0h] [rbp-1918h]
  CExecLvlRepresentation *v510; // [rsp+B8h] [rbp-1910h]
  bool v511; // [rsp+C0h] [rbp-1908h]
  char v512; // [rsp+C1h] [rbp-1907h]
  char v513; // [rsp+C3h] [rbp-1905h]
  bool v514; // [rsp+C4h] [rbp-1904h]
  char v515; // [rsp+C7h] [rbp-1901h] BYREF
  bool v516; // [rsp+C8h] [rbp-1900h]
  char v517; // [rsp+C9h] [rbp-18FFh]
  _BYTE v518[2]; // [rsp+CCh] [rbp-18FCh] BYREF
  char v519; // [rsp+CEh] [rbp-18FAh]
  char v520; // [rsp+CFh] [rbp-18F9h]
  char v521; // [rsp+D0h] [rbp-18F8h]
  int v522; // [rsp+D4h] [rbp-18F4h]
  struct IMemObj *v523; // [rsp+D8h] [rbp-18F0h]
  struct IQueryCompile *v524; // [rsp+E0h] [rbp-18E8h]
  int v525; // [rsp+E8h] [rbp-18E0h] BYREF
  unsigned __int64 v526; // [rsp+F0h] [rbp-18D8h]
  CEnvCollection *v527; // [rsp+F8h] [rbp-18D0h]
  char v528; // [rsp+100h] [rbp-18C8h]
  char v529; // [rsp+101h] [rbp-18C7h]
  char v530; // [rsp+102h] [rbp-18C6h]
  char v533; // [rsp+105h] [rbp-18C3h] BYREF
  char v534; // [rsp+106h] [rbp-18C2h]
  char v535; // [rsp+107h] [rbp-18C1h]
  char v537; // [rsp+109h] [rbp-18BFh]
  int v538; // [rsp+10Ch] [rbp-18BCh]
  char v539; // [rsp+110h] [rbp-18B8h] BYREF
  char v540; // [rsp+111h] [rbp-18B7h]
  char v541; // [rsp+112h] [rbp-18B6h]
  char v542; // [rsp+113h] [rbp-18B5h]
  char v543; // [rsp+114h] [rbp-18B4h]
  char v544; // [rsp+115h] [rbp-18B3h]
  char v545; // [rsp+116h] [rbp-18B2h]
  char v546; // [rsp+117h] [rbp-18B1h]
  char v547; // [rsp+118h] [rbp-18B0h]
  struct COptExpr *v548; // [rsp+120h] [rbp-18A8h]
  struct IQueryObj *v549; // [rsp+128h] [rbp-18A0h]
  CInterestingPredicateExplorer *v550; // [rsp+130h] [rbp-1898h]
  char v551[8]; // [rsp+138h] [rbp-1890h] BYREF
  struct CMemoXml *v552; // [rsp+140h] [rbp-1888h]
  __int64 v553; // [rsp+148h] [rbp-1880h]
  struct CSessionTraceFlags *v554; // [rsp+150h] [rbp-1878h]
  __int64 v555; // [rsp+158h] [rbp-1870h]
  struct CEsCompGroup *v556; // [rsp+160h] [rbp-1868h]
  char v557[8]; // [rsp+168h] [rbp-1860h] BYREF
  CMultiPlanFeedback *v558; // [rsp+170h] [rbp-1858h]
  unsigned __int64 v559; // [rsp+178h] [rbp-1850h]
  struct IMemObj **v560; // [rsp+180h] [rbp-1848h]
  CExecLvlRepresentation **v561; // [rsp+188h] [rbp-1840h]
  struct CQNameManager *v562; // [rsp+190h] [rbp-1838h]
  struct CQNameManager *v563; // [rsp+198h] [rbp-1830h]
  _QWORD *v564; // [rsp+1A0h] [rbp-1828h] BYREF
  unsigned int v565; // [rsp+1A8h] [rbp-1820h]
  int v566; // [rsp+1ACh] [rbp-181Ch]
  int v567; // [rsp+1B0h] [rbp-1818h]
  int v568; // [rsp+1B8h] [rbp-1810h]
  unsigned int v569; // [rsp+1C0h] [rbp-1808h] BYREF
  unsigned int v570; // [rsp+1C4h] [rbp-1804h]
  int v571; // [rsp+1C8h] [rbp-1800h]
  int v572; // [rsp+1CCh] [rbp-17FCh]
  unsigned int v573; // [rsp+1D0h] [rbp-17F8h]
  unsigned int v574; // [rsp+1D4h] [rbp-17F4h]
  int v575; // [rsp+1D8h] [rbp-17F0h]
  unsigned int v576; // [rsp+1E0h] [rbp-17E8h]
  int v577; // [rsp+1E8h] [rbp-17E0h]
  int v578; // [rsp+1F0h] [rbp-17D8h]
  int v579; // [rsp+1F8h] [rbp-17D0h]
  unsigned int v580; // [rsp+200h] [rbp-17C8h]
  int v581; // [rsp+208h] [rbp-17C0h]
  int v582; // [rsp+210h] [rbp-17B8h]
  struct COptInterfaces *v583; // [rsp+218h] [rbp-17B0h]
  __int64 v584; // [rsp+220h] [rbp-17A8h]
  struct IXteBuilder *XteBuilderObject; // [rsp+228h] [rbp-17A0h]
  struct IMemObj *v586; // [rsp+230h] [rbp-1798h]
  unsigned __int64 v587; // [rsp+238h] [rbp-1790h]
  struct CQOQueryHints *v588; // [rsp+240h] [rbp-1788h]
  int v589; // [rsp+248h] [rbp-1780h]
  int v590; // [rsp+24Ch] [rbp-177Ch]
  int v591; // [rsp+250h] [rbp-1778h]
  __int64 v592; // [rsp+258h] [rbp-1770h]
  unsigned int v593; // [rsp+260h] [rbp-1768h] BYREF
  double v594; // [rsp+268h] [rbp-1760h] BYREF
  __int64 v595; // [rsp+270h] [rbp-1758h]
  int v596; // [rsp+278h] [rbp-1750h]
  CExecLvlRepresentation **v597; // [rsp+280h] [rbp-1748h]
  _DWORD v598[4]; // [rsp+288h] [rbp-1740h] BYREF
  int v599; // [rsp+298h] [rbp-1730h]
  unsigned __int64 v600; // [rsp+2A0h] [rbp-1728h]
  int v601; // [rsp+2ACh] [rbp-171Ch]
  int v602; // [rsp+2B0h] [rbp-1718h]
  void *v603; // [rsp+2B8h] [rbp-1710h]
  unsigned __int64 v604; // [rsp+2C0h] [rbp-1708h] BYREF
  int v605; // [rsp+2CCh] [rbp-16FCh]
  int v606; // [rsp+2D0h] [rbp-16F8h]
  __int64 v607; // [rsp+2D8h] [rbp-16F0h]
  char v608[8]; // [rsp+2E0h] [rbp-16E8h] BYREF
  __int64 v609; // [rsp+2E8h] [rbp-16E0h] BYREF
  QueryHints *v610; // [rsp+2F0h] [rbp-16D8h]
  __int64 v611; // [rsp+2F8h] [rbp-16D0h]
  struct IMemObj *v612; // [rsp+300h] [rbp-16C8h]
  struct IMemObj *v613; // [rsp+308h] [rbp-16C0h]
  const struct CStatementDescription *v614; // [rsp+310h] [rbp-16B8h]
  __int64 v615; // [rsp+318h] [rbp-16B0h] BYREF
  struct CQte *v616; // [rsp+320h] [rbp-16A8h]
  double v617; // [rsp+328h] [rbp-16A0h] BYREF
  CExecLvlRepresentation **v618; // [rsp+330h] [rbp-1698h]
  struct CQODBSetOptions *v619; // [rsp+338h] [rbp-1690h]
  CExecLvlRepresentation **v620; // [rsp+340h] [rbp-1688h]
  CExecLvlRepresentation **v621; // [rsp+348h] [rbp-1680h]
  void ***v622; // [rsp+350h] [rbp-1678h] BYREF
  int v623; // [rsp+358h] [rbp-1670h]
  void ***v624; // [rsp+360h] [rbp-1668h] BYREF
  int v625; // [rsp+368h] [rbp-1660h]
  _QWORD *v626; // [rsp+370h] [rbp-1658h]
  __int64 v627; // [rsp+378h] [rbp-1650h]
  int *v628; // [rsp+380h] [rbp-1648h]
  int v629; // [rsp+388h] [rbp-1640h] BYREF
  unsigned int v630; // [rsp+38Ch] [rbp-163Ch]
  unsigned __int64 v631; // [rsp+390h] [rbp-1638h]
  __int64 v632; // [rsp+398h] [rbp-1630h]
  void **v633; // [rsp+3A0h] [rbp-1628h] BYREF
  int v634; // [rsp+3A8h] [rbp-1620h]
  int v635; // [rsp+3B0h] [rbp-1618h]
  __int64 v636; // [rsp+3B8h] [rbp-1610h]
  _QWORD v637[4]; // [rsp+3C0h] [rbp-1608h] BYREF
  unsigned __int64 v638; // [rsp+3E0h] [rbp-15E8h] BYREF
  unsigned __int64 v639; // [rsp+3E8h] [rbp-15E0h]
  int v640; // [rsp+3F0h] [rbp-15D8h]
  int v641; // [rsp+3F8h] [rbp-15D0h]
  int v642; // [rsp+400h] [rbp-15C8h]
  int v643; // [rsp+408h] [rbp-15C0h]
  int v644; // [rsp+410h] [rbp-15B8h]
  int v645; // [rsp+418h] [rbp-15B0h]
  int v646; // [rsp+420h] [rbp-15A8h]
  int v647; // [rsp+428h] [rbp-15A0h]
  int v648; // [rsp+430h] [rbp-1598h]
  int v649; // [rsp+438h] [rbp-1590h]
  int v650; // [rsp+440h] [rbp-1588h]
  int v651; // [rsp+448h] [rbp-1580h]
  int v652; // [rsp+44Ch] [rbp-157Ch]
  int v653; // [rsp+450h] [rbp-1578h]
  int v654; // [rsp+454h] [rbp-1574h]
  int v655; // [rsp+458h] [rbp-1570h]
  int v656; // [rsp+45Ch] [rbp-156Ch]
  int v657; // [rsp+460h] [rbp-1568h]
  int v658; // [rsp+464h] [rbp-1564h]
  int v659; // [rsp+468h] [rbp-1560h]
  _QWORD *v660; // [rsp+470h] [rbp-1558h]
  struct CSessionTraceFlags *v661; // [rsp+478h] [rbp-1550h]
  struct IValRefTracker *v662; // [rsp+480h] [rbp-1548h]
  __int64 v663; // [rsp+488h] [rbp-1540h]
  struct CQOFeatureSwitches *v664; // [rsp+490h] [rbp-1538h]
  struct CQOEEState *v665; // [rsp+498h] [rbp-1530h]
  struct CQOServerConfig *v666; // [rsp+4A0h] [rbp-1528h]
  struct CSessionTraceFlags *v667; // [rsp+4A8h] [rbp-1520h]
  struct CSessionTraceFlags *v668; // [rsp+4B0h] [rbp-1518h]
  struct CSessionTraceFlags *v669; // [rsp+4B8h] [rbp-1510h]
  struct CSessionTraceFlags *v670; // [rsp+4C0h] [rbp-1508h]
  struct CSessionTraceFlags *v671; // [rsp+4C8h] [rbp-1500h]
  struct CSessionTraceFlags *v672; // [rsp+4D0h] [rbp-14F8h]
  struct CSessionTraceFlags *v673; // [rsp+4D8h] [rbp-14F0h]
  struct CSessionTraceFlags *v674; // [rsp+4E0h] [rbp-14E8h]
  struct CSessionTraceFlags *v675; // [rsp+4E8h] [rbp-14E0h]
  struct CSessionTraceFlags *v676; // [rsp+4F0h] [rbp-14D8h]
  struct CSessionTraceFlags *v677; // [rsp+4F8h] [rbp-14D0h]
  int v678; // [rsp+500h] [rbp-14C8h]
  struct CSessionTraceFlags *v679; // [rsp+508h] [rbp-14C0h] BYREF
  struct CSessionTraceFlags *v680; // [rsp+510h] [rbp-14B8h] BYREF
  int *v681; // [rsp+518h] [rbp-14B0h] BYREF
  __int64 v682; // [rsp+520h] [rbp-14A8h]
  __int64 v683; // [rsp+528h] [rbp-14A0h]
  __int64 v684; // [rsp+530h] [rbp-1498h]
  char v685[8]; // [rsp+538h] [rbp-1490h] BYREF
  char v686[8]; // [rsp+540h] [rbp-1488h] BYREF
  char v687[8]; // [rsp+548h] [rbp-1480h] BYREF
  int v688; // [rsp+550h] [rbp-1478h]
  int v689; // [rsp+554h] [rbp-1474h]
  __int64 v690; // [rsp+558h] [rbp-1470h]
  int v691; // [rsp+560h] [rbp-1468h]
  int v692; // [rsp+568h] [rbp-1460h]
  int v693; // [rsp+570h] [rbp-1458h]
  __int64 v694; // [rsp+578h] [rbp-1450h]
  char v695[8]; // [rsp+580h] [rbp-1448h] BYREF
  char v696[8]; // [rsp+588h] [rbp-1440h] BYREF
  double v697; // [rsp+590h] [rbp-1438h] BYREF
  char v698[8]; // [rsp+598h] [rbp-1430h] BYREF
  char v699[8]; // [rsp+5A0h] [rbp-1428h] BYREF
  double v700; // [rsp+5A8h] [rbp-1420h] BYREF
  char v701[8]; // [rsp+5B0h] [rbp-1418h] BYREF
  char v702[8]; // [rsp+5B8h] [rbp-1410h] BYREF
  char v703[8]; // [rsp+5C0h] [rbp-1408h] BYREF
  char v704[8]; // [rsp+5C8h] [rbp-1400h] BYREF
  double v705; // [rsp+5D0h] [rbp-13F8h] BYREF
  char v706[8]; // [rsp+5D8h] [rbp-13F0h] BYREF
  char v707[8]; // [rsp+5E0h] [rbp-13E8h] BYREF
  char v708[8]; // [rsp+5E8h] [rbp-13E0h] BYREF
  int v709; // [rsp+5F0h] [rbp-13D8h]
  __int64 v710; // [rsp+5F8h] [rbp-13D0h]
  __int64 v711; // [rsp+600h] [rbp-13C8h]
  __int64 v712; // [rsp+608h] [rbp-13C0h] BYREF
  __int64 v713; // [rsp+610h] [rbp-13B8h] BYREF
  __int64 v714; // [rsp+618h] [rbp-13B0h] BYREF
  __int64 v715; // [rsp+620h] [rbp-13A8h] BYREF
  char v716[8]; // [rsp+628h] [rbp-13A0h] BYREF
  char v717[8]; // [rsp+630h] [rbp-1398h] BYREF
  char v718[8]; // [rsp+638h] [rbp-1390h] BYREF
  __int64 v719; // [rsp+640h] [rbp-1388h] BYREF
  __int64 v720; // [rsp+648h] [rbp-1380h] BYREF
  __int64 v721; // [rsp+650h] [rbp-1378h] BYREF
  __int64 v722; // [rsp+658h] [rbp-1370h]
  struct Worker *v723; // [rsp+660h] [rbp-1368h]
  int **v724; // [rsp+668h] [rbp-1360h] BYREF
  struct CAutoSessionTraceFlagOrQORuleToggler *v725; // [rsp+670h] [rbp-1358h] BYREF
  int v726; // [rsp+678h] [rbp-1350h]
  CExecLvlRepresentation **v727; // [rsp+680h] [rbp-1348h]
  int v728; // [rsp+688h] [rbp-1340h]
  int v729; // [rsp+690h] [rbp-1338h]
  CExecLvlRepresentation **v730; // [rsp+698h] [rbp-1330h]
  int v731; // [rsp+6A0h] [rbp-1328h]
  __int64 v732; // [rsp+6A8h] [rbp-1320h]
  int v733; // [rsp+6B0h] [rbp-1318h]
  int v734; // [rsp+6B8h] [rbp-1310h]
  int v735; // [rsp+6C0h] [rbp-1308h]
  int v736; // [rsp+6C8h] [rbp-1300h]
  int v737; // [rsp+6D0h] [rbp-12F8h]
  int v738; // [rsp+6D8h] [rbp-12F0h]
  int v739; // [rsp+6DCh] [rbp-12ECh]
  int v740; // [rsp+6E0h] [rbp-12E8h]
  void **v741; // [rsp+6E8h] [rbp-12E0h] BYREF
  int v742; // [rsp+6F0h] [rbp-12D8h]
  int v743; // [rsp+6F8h] [rbp-12D0h]
  __int64 v744; // [rsp+700h] [rbp-12C8h]
  int v745; // [rsp+708h] [rbp-12C0h]
  _DWORD v746[6]; // [rsp+710h] [rbp-12B8h] BYREF
  unsigned int v747; // [rsp+728h] [rbp-12A0h] BYREF
  struct IMemObj *v748; // [rsp+730h] [rbp-1298h]
  unsigned __int64 v749; // [rsp+738h] [rbp-1290h]
  unsigned int v750; // [rsp+740h] [rbp-1288h] BYREF
  struct IMemObj *v751; // [rsp+748h] [rbp-1280h]
  char v752; // [rsp+750h] [rbp-1278h]
  unsigned __int64 v753; // [rsp+758h] [rbp-1270h]
  __int64 v754; // [rsp+760h] [rbp-1268h]
  __int64 v755; // [rsp+768h] [rbp-1260h]
  _DWORD *v756; // [rsp+770h] [rbp-1258h]
  struct IMemObj *v757; // [rsp+778h] [rbp-1250h]
  struct IMemObj *v758; // [rsp+780h] [rbp-1248h]
  struct IMemObj *v759; // [rsp+788h] [rbp-1240h]
  char *v760; // [rsp+790h] [rbp-1238h]
  struct IMemObj *v761; // [rsp+798h] [rbp-1230h]
  struct IMemObj *v762; // [rsp+7A0h] [rbp-1228h]
  char *v763; // [rsp+7A8h] [rbp-1220h]
  struct IMemObj *v764; // [rsp+7B0h] [rbp-1218h]
  CInterestingPredicateExplorer *v765; // [rsp+7B8h] [rbp-1210h]
  unsigned int *v766; // [rsp+7C0h] [rbp-1208h]
  struct IMemObj *v767; // [rsp+7C8h] [rbp-1200h]
  struct IMemObj *v768; // [rsp+7D0h] [rbp-11F8h]
  struct IMemObj *v769; // [rsp+7D8h] [rbp-11F0h]
  unsigned int *v770; // [rsp+7E0h] [rbp-11E8h]
  _OWORD *v771; // [rsp+7E8h] [rbp-11E0h]
  double v772; // [rsp+7F0h] [rbp-11D8h] BYREF
  double v773; // [rsp+7F8h] [rbp-11D0h] BYREF
  double v774; // [rsp+800h] [rbp-11C8h] BYREF
  unsigned __int64 v775[12]; // [rsp+808h] [rbp-11C0h] BYREF
  unsigned __int64 v776[5]; // [rsp+868h] [rbp-1160h] BYREF
  __int128 v777; // [rsp+890h] [rbp-1138h] BYREF
  __int128 v778; // [rsp+8A0h] [rbp-1128h] BYREF
  _BYTE v779[16]; // [rsp+8B0h] [rbp-1118h] BYREF
  _QWORD v780[6]; // [rsp+8C0h] [rbp-1108h] BYREF
  struct IMemObj *v781; // [rsp+8F0h] [rbp-10D8h]
  CVRTableOpt *v782; // [rsp+8F8h] [rbp-10D0h]
  __int64 v783; // [rsp+900h] [rbp-10C8h]
  __int64 v784; // [rsp+908h] [rbp-10C0h]
  __int64 v785; // [rsp+910h] [rbp-10B8h]
  _QWORD *v786; // [rsp+918h] [rbp-10B0h]
  unsigned __int64 *v787; // [rsp+920h] [rbp-10A8h]
  _BYTE v788[40]; // [rsp+928h] [rbp-10A0h] BYREF
  char v789[8]; // [rsp+950h] [rbp-1078h] BYREF
  __int16 v790; // [rsp+958h] [rbp-1070h]
  __int16 v791; // [rsp+95Ah] [rbp-106Eh]
  int v792; // [rsp+960h] [rbp-1068h]
  char **v793; // [rsp+968h] [rbp-1060h]
  char *v794; // [rsp+970h] [rbp-1058h]
  __int64 v795; // [rsp+978h] [rbp-1050h]
  char *v796; // [rsp+980h] [rbp-1048h] BYREF
  int v797; // [rsp+988h] [rbp-1040h]
  __int16 v798; // [rsp+98Ch] [rbp-103Ch]
  __int16 v799; // [rsp+98Eh] [rbp-103Ah]
  char v800; // [rsp+990h] [rbp-1038h] BYREF
  int v801; // [rsp+BA0h] [rbp-E28h]
  int v802; // [rsp+BA4h] [rbp-E24h]
  __int64 v803; // [rsp+BA8h] [rbp-E20h]
  char v804; // [rsp+BB0h] [rbp-E18h] BYREF
  unsigned int v805; // [rsp+BB1h] [rbp-E17h]
  int v806; // [rsp+BB5h] [rbp-E13h]
  __int64 v807; // [rsp+BB9h] [rbp-E0Fh]
  char v808[8]; // [rsp+BD0h] [rbp-DF8h] BYREF
  __int16 v809; // [rsp+BD8h] [rbp-DF0h]
  __int16 v810; // [rsp+BDAh] [rbp-DEEh]
  int v811; // [rsp+BE0h] [rbp-DE8h]
  char **v812; // [rsp+BE8h] [rbp-DE0h]
  char *v813; // [rsp+BF0h] [rbp-DD8h]
  __int64 v814; // [rsp+BF8h] [rbp-DD0h]
  char *v815; // [rsp+C00h] [rbp-DC8h] BYREF
  int v816; // [rsp+C08h] [rbp-DC0h]
  __int16 v817; // [rsp+C0Ch] [rbp-DBCh]
  __int16 v818; // [rsp+C0Eh] [rbp-DBAh]
  char v819; // [rsp+C10h] [rbp-DB8h] BYREF
  int v820; // [rsp+E20h] [rbp-BA8h]
  int v821; // [rsp+E24h] [rbp-BA4h]
  __int64 v822; // [rsp+E28h] [rbp-BA0h]
  char v823; // [rsp+E30h] [rbp-B98h] BYREF
  int v824; // [rsp+E31h] [rbp-B97h]
  int v825; // [rsp+E35h] [rbp-B93h]
  __int64 v826; // [rsp+E39h] [rbp-B8Fh]
  char v827[8]; // [rsp+E50h] [rbp-B78h] BYREF
  __int16 v828; // [rsp+E58h] [rbp-B70h]
  __int16 v829; // [rsp+E5Ah] [rbp-B6Eh]
  int v830; // [rsp+E60h] [rbp-B68h]
  int **v831; // [rsp+E68h] [rbp-B60h]
  char *v832; // [rsp+E70h] [rbp-B58h]
  __int64 v833; // [rsp+E78h] [rbp-B50h]
  int *v834; // [rsp+E80h] [rbp-B48h] BYREF
  int v835; // [rsp+E88h] [rbp-B40h]
  __int16 v836; // [rsp+E8Ch] [rbp-B3Ch]
  __int16 v837; // [rsp+E8Eh] [rbp-B3Ah]
  char v838; // [rsp+E90h] [rbp-B38h] BYREF
  int v839; // [rsp+10A0h] [rbp-928h]
  int v840; // [rsp+10A4h] [rbp-924h]
  __int64 v841; // [rsp+10A8h] [rbp-920h]
  int v842; // [rsp+10B0h] [rbp-918h] BYREF
  char v843[8]; // [rsp+10C0h] [rbp-908h] BYREF
  __int16 v844; // [rsp+10C8h] [rbp-900h]
  __int16 v845; // [rsp+10CAh] [rbp-8FEh]
  int v846; // [rsp+10D0h] [rbp-8F8h]
  int **v847; // [rsp+10D8h] [rbp-8F0h]
  char *v848; // [rsp+10E0h] [rbp-8E8h]
  __int64 v849; // [rsp+10E8h] [rbp-8E0h]
  int *v850; // [rsp+10F0h] [rbp-8D8h] BYREF
  int v851; // [rsp+10F8h] [rbp-8D0h]
  __int16 v852; // [rsp+10FCh] [rbp-8CCh]
  __int16 v853; // [rsp+10FEh] [rbp-8CAh]
  char v854; // [rsp+1100h] [rbp-8C8h] BYREF
  int v855; // [rsp+1310h] [rbp-6B8h]
  int v856; // [rsp+1314h] [rbp-6B4h]
  __int64 v857; // [rsp+1318h] [rbp-6B0h]
  int v858; // [rsp+1320h] [rbp-6A8h] BYREF
  _BYTE v859[176]; // [rsp+1330h] [rbp-698h] BYREF
  CExecLvlRepresentation *v860; // [rsp+13E0h] [rbp-5E8h]
  int v861[4]; // [rsp+13F0h] [rbp-5D8h] BYREF
  __int64 v862; // [rsp+1400h] [rbp-5C8h]
  struct IMemObj *v863; // [rsp+1410h] [rbp-5B8h]
  __int64 v864; // [rsp+1418h] [rbp-5B0h]
  __int64 v865; // [rsp+1420h] [rbp-5A8h]
  __int64 v866; // [rsp+1438h] [rbp-590h]
  __int64 v867; // [rsp+1440h] [rbp-588h]
  __int16 v868; // [rsp+144Ch] [rbp-57Ch]
  char v869; // [rsp+144Eh] [rbp-57Ah]
  int v870; // [rsp+1450h] [rbp-578h]
  unsigned int v871; // [rsp+1454h] [rbp-574h]
  unsigned __int8 v872; // [rsp+1458h] [rbp-570h]
  char v873; // [rsp+1459h] [rbp-56Fh]
  char v874; // [rsp+145Ah] [rbp-56Eh]
  char v875; // [rsp+145Bh] [rbp-56Dh]
  char v876; // [rsp+145Ch] [rbp-56Ch]
  int v877; // [rsp+1460h] [rbp-568h]
  int v878; // [rsp+1464h] [rbp-564h]
  char v879; // [rsp+14A0h] [rbp-528h]
  char v880; // [rsp+14A1h] [rbp-527h]
  char v881; // [rsp+14A2h] [rbp-526h]
  char v882; // [rsp+14A3h] [rbp-525h]
  char v883; // [rsp+14A4h] [rbp-524h]
  char v884; // [rsp+14A5h] [rbp-523h]
  char v885; // [rsp+14A6h] [rbp-522h]
  char v886; // [rsp+14A7h] [rbp-521h]
  struct CQNameManager *v887; // [rsp+14B8h] [rbp-510h]
  CMemo *v888; // [rsp+1520h] [rbp-4A8h]
  __int64 v889; // [rsp+1580h] [rbp-448h]
  struct DRgPDispatcherPredicateHint *v890; // [rsp+1590h] [rbp-438h]
  COptAntiPatterns *v891; // [rsp+15F0h] [rbp-3D8h]
  __int64 v892; // [rsp+1610h] [rbp-3B8h]
  __int64 v893; // [rsp+1618h] [rbp-3B0h]
  int v894; // [rsp+1624h] [rbp-3A4h]
  __int64 v895; // [rsp+1630h] [rbp-398h]
  __int64 v896; // [rsp+1638h] [rbp-390h]
  __int64 v897; // [rsp+1660h] [rbp-368h]
  int v898; // [rsp+1668h] [rbp-360h]
  __int64 v899; // [rsp+1670h] [rbp-358h]
  unsigned int v900; // [rsp+16A0h] [rbp-328h]
  __int64 v901; // [rsp+16A8h] [rbp-320h]
  BatchModeHeuristics *v902; // [rsp+16C8h] [rbp-300h]
  __int64 v903; // [rsp+1710h] [rbp-2B8h]
  __int64 v904; // [rsp+1718h] [rbp-2B0h]
  CInterestingPredicateExplorer *v905; // [rsp+1720h] [rbp-2A8h]
  struct COptExpr *v906; // [rsp+1758h] [rbp-270h] BYREF
  __int64 v907; // [rsp+1778h] [rbp-250h]
  CQoTelemetryAgg *v908; // [rsp+1790h] [rbp-238h]
  CETelemetryPackage *v909; // [rsp+1798h] [rbp-230h]
  struct CDataExportParameters *v910; // [rsp+17C8h] [rbp-200h]
  int v911; // [rsp+1810h] [rbp-1B8h]
  __int64 v912; // [rsp+1818h] [rbp-1B0h]
  int v913; // [rsp+1820h] [rbp-1A8h]
  unsigned __int64 v914; // [rsp+1830h] [rbp-198h] BYREF
  unsigned __int64 v915; // [rsp+1838h] [rbp-190h]
  unsigned __int64 v916; // [rsp+1840h] [rbp-188h] BYREF
  unsigned __int64 v917; // [rsp+1848h] [rbp-180h]
  char Buffer[256]; // [rsp+1870h] [rbp-158h] BYREF

  v754 = -2;
  v523 = a3;
  v556 = a2;
  v548 = a1;
  v612 = a3;
  v527 = a5;
  v538 = a6;
  v561 = a11;
  v614 = a13;
  v17 = _statusfp();
  v18 = v17;
  if ( (v17 & 0x1C) != 0 )
  {
    _clearfp();
    if ( (v18 & 0x10) != 0 )
      _fpreset();
  }
  _controlfp(0x9001Fu, 0x8031Fu);
  v19 = 0;
  v549 = 0;
  if ( (_DWORD)a8 )
    v20 = (unsigned __int64)(int)a8 >> 1;
  else
    LODWORD(v20) = 5;
  v21 = L"Adhoc";
  if ( (_DWORD)a8 )
    v21 = a7;
  DefaultLocale = GetDefaultLocale();
  snprintf_s_l(Buffer, 0xFFu, 0xFFFFFFFFFFFFFFFFuLL, "QueryOptimizer_%.*ls", DefaultLocale, v20, v21);
  Buffer[255] = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v25 = SystemThread_TlsIndex;
  v26 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
  v27 = *(_QWORD *)(v26 + 256);
  if ( !v27 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v27 = *(_QWORD *)(v26 + 256);
  }
  v28 = *(_QWORD *)(v27 + 992);
  ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals(v25, ThreadLocalStoragePointer, v23);
  DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                 ClientProcessGlobals,
                                 *(_WORD *)(v28 + 160));
  SOS_OS::GetClientProcessGlobals(v32, v31, v33);
  v34 = DefaultMemoryClerksForNode[8];
  v35 = (char *)v34 + 64;
  if ( !v34 )
    v35 = 0;
  LOWORD(Locale) = 352;
  MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(107, 0, v35, 8, Locale);
  v507 = MemObject;
  if ( !MemObject )
  {
    LOBYTE(v36) = 65;
    ex_raise_oom(v36);
  }
  v38 = (CMallocSpy *)(*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemObject + 176LL))(MemObject);
  if ( v38 )
    CMallocSpy::SetDescriptiveName(v38, Buffer);
  (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemObject + 240LL))(MemObject);
  v586 = MemObject;
  v39 = *((_QWORD *)a1 + 2);
  v722 = v39;
  v40 = *(struct QueryTraceAndRuleHints ***)(v39 + 56);
  v610 = (QueryHints *)v40;
  Hints = CaptureQueryHints(MemObject, (const struct QueryHints *)v40);
  v588 = Hints;
  v42 = a11;
  if ( *(_BYTE *)a11 )
  {
    v43 = *((unsigned int *)a11 + 26);
  }
  else
  {
    CExecLvlIntCtxt::GetCurCompatLevel(a11[16], &v593, a11);
    v43 = v593;
    Hints = v588;
    v42 = a11;
  }
  v522 = v43;
  if ( a12 )
    return (struct IQueryObj *)(**(__int64 (__fastcall ***)(struct IQueryWithFeedback *, struct IMemObj *, __int64, _QWORD, struct CQOQueryHints *, CEnvCollection *, CExecLvlRepresentation **, struct COptExpr *))a12)(
                                 a12,
                                 v523,
                                 v43,
                                 0,
                                 Hints,
                                 v527,
                                 v42,
                                 v548);
  v524 = 0;
  v584 = 0;
  v506 = 0;
  memset(v637, 0, sizeof(v637));
  v638 = 0;
  v639 = 0;
  v44 = v42[20];
  v510 = v44;
  if ( v40 )
  {
    v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v46 = *(_QWORD *)(v45 + 256);
    if ( !v46 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v46 = *(_QWORD *)(v45 + 256);
    }
    v47 = CAutoSessionTraceFlagOrQORuleToggler::CreateAndActivate(*(struct IMemObj **)(v46 + 1000), v40[6], 1, 1);
    v44 = v510;
  }
  else
  {
    v47 = 0;
  }
  v725 = v47;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v788, 0x1Du, 6u, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
    *((_BYTE *)v44 + 44) |= 8u;
    MemoryClerk = GetMemoryClerk(8, 1);
    v49 = MemoryClerk + 64;
    if ( !MemoryClerk )
      v49 = 0;
    LOWORD(Localea) = 128;
    v51 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(95, 1, v49, 8, Localea);
    if ( !v51 )
    {
      LOBYTE(v50) = 65;
      ex_raise_oom(v50);
    }
    v613 = v51;
    v678 = 2219;
    v52 = (CValRefTracker *)operator new(0x20u, MemObject, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2219, 1u);
    v776[3] = (unsigned __int64)v52;
    if ( v52 )
      v53 = CValRefTracker::CValRefTracker(v52, MemObject);
    else
      v53 = 0;
    v662 = v53;
    v780[2] = v53;
    v688 = 2220;
    v54 = (CVRTableComp *)operator new(0x30u, v523, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2220, 1u);
    v780[4] = v54;
    if ( v54 )
      v55 = CVRTableComp::CVRTableComp(v54, v523, v53);
    else
      v55 = 0;
    v780[5] = v55;
    v689 = 2221;
    v56 = (CVRTableOpt *)operator new(0x30u, MemObject, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2221, 1u);
    v782 = v56;
    if ( v56 )
      v57 = CVRTableOpt::CVRTableOpt(v56, MemObject, v53);
    else
      v57 = 0;
    v618 = (CExecLvlRepresentation **)v57;
    CQNameManager = CreateCQNameManager(v51);
    v563 = CQNameManager;
    v59 = CreateCQNameManager(v523);
    v562 = v59;
    v60 = a9;
    v61 = 195;
    if ( a9 == 194 )
      v60 = 195;
    v618 = a11;
    IQueryCompile = (struct IQueryCompile *)CreateIQueryCompile(
                                              v523,
                                              v51,
                                              v60,
                                              (unsigned int)a10,
                                              a11,
                                              v527,
                                              v55,
                                              v57,
                                              CQNameManager,
                                              v59,
                                              v556);
    v524 = IQueryCompile;
    v618 = a11;
    CurrentDb = (unsigned __int16)ContextAccessor::GetCurrentDb();
    if ( FSystemDBId(CurrentDb) || CExecLvlRepresentation::FInternal(v510) )
    {
      v505 = 0;
      (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 360LL))(IQueryCompile);
    }
    else
    {
      v505 = 1;
      (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 352LL))(IQueryCompile);
      v584 = (*(__int64 (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 384LL))(IQueryCompile);
    }
    XteBuilderObject = CreateXteBuilderObject(IQueryCompile);
    v691 = 2262;
    v63 = (struct IMemObj **)operator new(0x70u, v51, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2262, 1u);
    v776[2] = (unsigned __int64)v63;
    if ( v63 )
    {
      if ( a9 == 194 )
      {
        v596 = 195;
      }
      else
      {
        v61 = a9;
        v596 = (__int16)a9;
      }
      *v63 = v507;
      v63[1] = v523;
      v63[2] = v51;
      v63[3] = v527;
      v63[4] = (struct IMemObj *)a11;
      v63[5] = v563;
      v63[6] = v562;
      v63[7] = v57;
      v63[8] = v55;
      v63[9] = 0;
      v63[10] = IQueryCompile;
      v63[11] = XteBuilderObject;
      v63[12] = (struct IMemObj *)v39;
      *((_WORD *)v63 + 52) = v61;
    }
    else
    {
      v63 = 0;
    }
    v583 = (struct COptInterfaces *)v63;
    v560 = v63;
    v615 = *(_QWORD *)(v39 + 712);
    if ( !v615 )
      utgettime((struct SQLDATEBASE *)&v615, 1, 0);
    (*(void (__fastcall **)(struct IQueryCompile *, __int64 *))(*(_QWORD *)IQueryCompile + 176LL))(IQueryCompile, &v615);
    v64 = *((_QWORD *)v510 + 8);
    if ( v64 )
    {
      v660 = (_QWORD *)*((_QWORD *)v510 + 8);
      if ( *(_QWORD *)v64 || *(_QWORD *)(v64 + 120) )
        *(_BYTE *)(v64 + 704) = 0;
      v316 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v317 = *(_QWORD **)(v316 + 256);
      v318 = v317;
      if ( !v317 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v317 = *(_QWORD **)(v316 + 256);
        v318 = v317;
      }
      v727 = (CExecLvlRepresentation **)v317;
      if ( v318[107] )
      {
        v321 = __rdtsc();
        v322 = v318[108];
        if ( v321 <= v322 )
          v323 = 0;
        else
          v323 = v321 - v322;
        v319 = v323 + v318[109];
      }
      else
      {
        v319 = 0;
      }
      v320 = v660;
      *v660 = v319;
      v320[15] = __rdtsc();
    }
    v619 = CaptureDBAndSetOptions(v507);
    v666 = CaptureServerConfig(v507);
    v65 = v610;
    if ( v610 )
    {
      OptimizerCompatLevel = QueryHints::IGetQueryOptimizerCompatLevel(v610);
      if ( OptimizerCompatLevel != -1 )
      {
        if ( byte_102EDCE31 )
        {
          v692 = 11041;
          v535 = *((_BYTE *)qword_102ECFB10 + 1380) >> 1;
          if ( (v535 & 1) == 0 )
          {
            if ( OptimizerCompatLevel == 160 )
            {
              if ( byte_102EDCB6F )
                v522 = 160;
            }
            else
            {
              v522 = OptimizerCompatLevel;
            }
          }
        }
      }
      if ( (unsigned __int8)QueryHints::FHintSet(v65, 3) )
        goto LABEL_589;
    }
    v693 = 4199;
    if ( *((_BYTE *)qword_102ECFB10 + 524) >> 7 )
      goto LABEL_589;
    v709 = 0;
    v67 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v67 && (v68 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v67 + 56LL), (v69 = *v68) != 0) )
    {
      v661 = *v68;
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v69, 0x1067u) )
        goto LABEL_589;
    }
    else
    {
      v661 = 0;
    }
    v727 = a11;
    v597 = a11;
    v597 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset);
    v70 = v597[10];
    v71 = *((_BYTE *)v70 + 60);
    if ( (*((_BYTE *)v70 + 68) & 8) != 0 )
      v72 = v71 >> 5;
    else
      v72 = v71 >> 4;
    if ( (v72 & 1) == 0 )
    {
      v73 = 0;
LABEL_59:
      v512 = v73;
      v663 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)
                       + 120LL)
           + 120LL;
      v664 = CaptureFeatureSwitches(v507, v619);
      v565 = CaptureStatementType(a9);
      v665 = CaptureXLvlRepSettings(v507);
      v511 = FPDWFeaturesExposed();
      v74 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      FSetOptionsOkForIccIv(0, 13014);
      v75 = CExecLvlRepresentation::PmoPph(*(CExecLvlRepresentation **)(v74 + 160));
      v76 = v588;
      LOBYTE(v502) = v512;
      COptContext::COptContext(
        v861,
        v507,
        v75,
        v565,
        v522,
        v502,
        v666,
        v665,
        v664,
        v663,
        v583,
        v619,
        v662,
        v77,
        v538,
        v588,
        v511);
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 12)
        && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 84)
        && (v878 >= 160 || (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 121)) )
      {
        v873 |= 1u;
      }
      Context = UtilDbccGetContext();
      if ( Context )
      {
        v538 = (*((_DWORD *)Context + 3) >> 6) & 1;
        if ( v538 )
          v871 |= 0x20000u;
      }
      else
      {
        v538 = 0;
      }
      if ( FUtilNcciAreFlushBufferSyntaxAllowed() )
        v871 = v79 | 0x40000;
      if ( UtilDbccGetContext() )
      {
        if ( UtilDbccGetContext() )
          v325 = (_DWORD *)((char *)UtilDbccGetContext() + 12);
        else
          v325 = 0;
        v566 = (*v325 >> 15) & 1;
        if ( v566 )
          v871 = v324 | 0x80000;
      }
      else
      {
        v566 = 0;
      }
      if ( UtilDbccGetContext() )
      {
        v327 = UtilDbccGetContext() ? (char *)UtilDbccGetContext() + 12 : 0LL;
        if ( (*(_DWORD *)v327 & 0x4000) != 0 )
          v871 = v326 | 0x100000;
      }
      if ( UtilDbccGetContext() )
        v871 = v80 | 0x200000;
      if ( UtilDbccIsCheckRunning() )
      {
        if ( UtilDbccGetContext() )
          v328 = (char *)UtilDbccGetContext() + 12;
        else
          v328 = 0;
        v567 = v328[2] & 1;
        if ( v567 )
          v871 |= 0x400000u;
      }
      else
      {
        v567 = 0;
      }
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 53) )
        v873 |= 0x40u;
      v81 = CQOFeatureSwitches::FIsSet(v867, 54);
      v82 = v873;
      if ( v81 )
      {
        v82 = v873 | 0x20;
        v873 |= 0x20u;
      }
      if ( (*(_DWORD *)(*((_QWORD *)v510 + 1) + 580LL) & 2) != 0 )
        v873 = v82 | 4;
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 55) )
      {
        v873 |= 0x10u;
        if ( (v873 & 4) != 0 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v510 + 1) + 1136LL) )
            COptContext::CreatePDWExpressionArrayForIV((COptContext *)v861);
        }
      }
      if ( FPDWUQOFeaturesExposed() )
        v874 |= 2u;
      v726 = 9307;
      v537 = *((_BYTE *)qword_102ECFB10 + 1163) >> 3;
      if ( (v537 & 1) != 0 )
        goto LABEL_611;
      v728 = 0;
      v83 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      if ( v83 && (v84 = *(struct CSessionTraceFlags ***)(v83 + 56), (v85 = *v84) != 0) )
      {
        v667 = *v84;
        if ( CSessionTraceFlags::CheckSessionTraceInternal(v85, 0x245Bu) )
          goto LABEL_611;
      }
      else
      {
        v667 = 0;
      }
      if ( !FUtilNcciAreFlushBufferSyntaxAllowed() )
      {
LABEL_89:
        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 56) )
        {
          if ( v65 && (unsigned __int8)QueryHints::FHintSet(v65, 10)
            || ((v597 = a11,
                 v620 = a11,
                 v620 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset),
                 v329 = v620[10],
                 v330 = *((_BYTE *)v329 + 60),
                 (*((_BYTE *)v329 + 68) & 8) == 0)
              ? (v331 = (v330 & 0x40) != 0)
              : (v331 = v330 >> 7),
                v331) )
          {
            v879 |= 8u;
          }
        }
        v729 = 9390;
        v540 = *((_BYTE *)qword_102ECFB10 + 1173) >> 6;
        if ( (v540 & 1) == 0 )
        {
          v731 = 0;
          v86 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          if ( !v86 || (v87 = *(struct CSessionTraceFlags ***)(v86 + 56), (v88 = *v87) == 0) )
          {
            v668 = 0;
LABEL_94:
            if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 57) && v878 >= 130 )
              goto LABEL_96;
            v89 = v874;
            if ( (v874 & 2) == 0 || (v733 = 10068, v541 = *((_BYTE *)qword_102ECFB10 + 1258) >> 4, (v541 & 1) != 0) )
            {
LABEL_97:
              if ( (v89 & 8) != 0 || (v873 & 8) != 0 && v878 >= 130 )
                v874 = v89 | 4;
              if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 58)
                || v878 >= 140 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 59) )
              {
                v875 |= 1u;
              }
              if ( !UtilDbccIsCheckRunning() )
              {
                v737 = 9307;
                v543 = *((_BYTE *)qword_102ECFB10 + 1163) >> 3;
                if ( (v543 & 1) == 0 )
                {
                  v738 = 0;
                  v90 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( !v90 || (v91 = *(struct CSessionTraceFlags ***)(v90 + 56), (v92 = *v91) == 0) )
                  {
                    v671 = 0;
LABEL_108:
                    if ( !FUtilNcciAreFlushBufferSyntaxAllowed() )
                    {
                      v93 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset
                                                  + 8LL)
                                      + 72LL);
                      v94 = (COptContext *)(v93 - 8);
                      if ( !v93 )
                        v94 = 0;
                      if ( COptContext::FTraceFlagIsOn(v94, 0x24EDu) )
                        goto LABEL_113;
                    }
                    goto LABEL_112;
                  }
                  v671 = *v91;
                  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v92, 0x245Bu) )
                    goto LABEL_108;
                }
              }
LABEL_112:
              v879 |= 0x10u;
LABEL_113:
              if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 60) )
                v879 |= 0x20u;
              if ( v584 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 61) && !v862 )
              {
                v739 = 8537;
                v335 = (CQoTelemetryAgg *)operator new(
                                            0x278u,
                                            v863,
                                            "sql\\ntdbms\\query\\qeoptim\\engine\\qeoptim.cpp",
                                            8537,
                                            1u);
                v730 = (CExecLvlRepresentation **)v335;
                if ( v335 )
                  v336 = CQoTelemetryAgg::CQoTelemetryAgg(v335, v863);
                else
                  v336 = 0;
                v908 = v336;
              }
              if ( v65 && (unsigned __int8)QueryHints::FHintSet(v65, 7) )
                goto LABEL_637;
              v740 = 4139;
              v544 = *((_BYTE *)qword_102ECFB10 + 517) >> 3;
              if ( (v544 & 1) != 0 )
                goto LABEL_637;
              v745 = 0;
              v95 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset);
              if ( !v95 || (v96 = *(struct CSessionTraceFlags ***)(v95 + 56), (v97 = *v96) == 0) )
              {
                v672 = 0;
                goto LABEL_122;
              }
              v672 = *v96;
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v97, 0x102Bu) )
LABEL_637:
                v879 |= 0x40u;
LABEL_122:
              if ( !v65 || !(unsigned __int8)QueryHints::FHintSet(v65, 8) )
              {
                v640 = 4138;
                v545 = *((_BYTE *)qword_102ECFB10 + 517) >> 2;
                if ( (v545 & 1) == 0 )
                {
                  v641 = 0;
                  v98 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( !v98 || (v99 = *(struct CSessionTraceFlags ***)(v98 + 56), (v100 = *v99) == 0) )
                  {
                    v673 = 0;
LABEL_128:
                    if ( v878 >= 140 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 62) )
                    {
                      v101 = 1;
                    }
                    else
                    {
                      v880 &= ~1u;
                      v101 = 0;
                    }
                    v546 = v101;
                    if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 63) )
                      goto LABEL_493;
                    if ( v878 < 140 && (v876 & 0x10) == 0 )
                    {
                      v642 = 9939;
                      v547 = *((_BYTE *)qword_102ECFB10 + 1242) >> 3;
                      if ( (v547 & 1) == 0 )
                      {
                        v643 = 0;
                        v250 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset;
                        if ( !*(_QWORD *)v250
                          || (v251 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v250 + 56LL), (v252 = *v251) == 0) )
                        {
                          v674 = 0;
LABEL_493:
                          v880 &= ~2u;
                          v102 = 0;
LABEL_134:
                          v528 = v102;
                          if ( v505 )
                            v880 |= 8u;
                          v644 = 9358;
                          v534 = *((_BYTE *)qword_102ECFB10 + 1169) >> 6;
                          if ( (v534 & 1) != 0 )
                            goto LABEL_143;
                          v645 = 0;
                          v103 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset;
                          if ( *(_QWORD *)v103
                            && (v104 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v103 + 56LL), (v105 = *v104) != 0) )
                          {
                            v675 = *v104;
                            if ( CSessionTraceFlags::CheckSessionTraceInternal(v105, 0x248Eu) )
                              goto LABEL_143;
                          }
                          else
                          {
                            v675 = 0;
                          }
                          if ( (v878 < 130 || (v876 & 0x10) == 0) && v878 < 140 )
                          {
LABEL_144:
                            v646 = 176;
                            v529 = *((_BYTE *)qword_102ECFB10 + 22);
                            if ( (v529 & 1) == 0 )
                            {
                              v647 = 0;
                              v106 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                 + SystemThread_TlsIndex)
                                               + SystemThread_TlsOffset);
                              if ( v106 && (v107 = *(struct CSessionTraceFlags ***)(v106 + 56), (v108 = *v107) != 0) )
                              {
                                v676 = *v107;
                                if ( CSessionTraceFlags::CheckSessionTraceInternal(v108, 0xB0u) )
                                  goto LABEL_533;
                              }
                              else
                              {
                                v676 = 0;
                              }
                              if ( v878 < 150 && (v876 & 0x10) == 0 )
                              {
LABEL_150:
                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 64) )
                                {
                                  if ( v65 && (unsigned __int8)QueryHints::FHintSet(v65, 20) )
                                    goto LABEL_156;
                                  if ( v878 >= 150 || (v876 & 0x10) != 0 )
                                    v874 |= 0x10u;
                                }
                                if ( !v65 )
                                {
LABEL_157:
                                  v648 = 8649;
                                  v530 = *((_BYTE *)qword_102ECFB10 + 1081) >> 1;
                                  if ( (v530 & 1) == 0 )
                                  {
                                    v649 = 0;
                                    v109 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                         + SystemThread_TlsOffset;
                                    if ( !*(_QWORD *)v109
                                      || (v110 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v109 + 56LL),
                                          (v111 = *v110) == 0) )
                                    {
                                      v677 = 0;
                                      goto LABEL_161;
                                    }
                                    v677 = *v110;
                                    if ( !CSessionTraceFlags::CheckSessionTraceInternal(v111, 0x21C9u) )
                                    {
LABEL_161:
                                      v650 = 9423;
                                      if ( !(*((_BYTE *)qword_102ECFB10 + 1177) >> 7) )
                                      {
                                        v651 = 0;
                                        v112 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset);
                                        if ( v112
                                          && (v113 = *(struct CSessionTraceFlags ***)(v112 + 56), (v114 = *v113) != 0) )
                                        {
                                          v554 = *v113;
                                          if ( CSessionTraceFlags::CheckSessionTraceInternal(v114, 0x24CFu) )
                                            goto LABEL_535;
                                        }
                                        else
                                        {
                                          v554 = 0;
                                        }
                                        if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 65) || v878 < 150 )
                                        {
LABEL_167:
                                          if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 66)
                                            && (v878 >= 140 || (v876 & 0x10) != 0) )
                                          {
                                            v876 |= 2u;
                                          }
                                          v730 = a11;
                                          v621 = a11;
                                          if ( !v65 || !(unsigned __int8)QueryHints::FHintSet(v65, 16) )
                                          {
                                            v621 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset);
                                            v115 = v621[10];
                                            v116 = *((_BYTE *)v115 + 64);
                                            if ( (*((_BYTE *)v115 + 68) & 8) != 0 )
                                              v116 >>= 1;
                                            if ( (v116 & 1) == 0
                                              && ((unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 67) && v878 >= 150
                                               || (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 68)) )
                                            {
                                              v882 |= 0x10u;
                                            }
                                          }
                                          if ( !v909 )
                                            COptContext::StartCECalculatorContainer((COptContext *)v861);
                                          if ( ((unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 69)
                                             || (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 70) && v878 >= 150)
                                            && *((_DWORD *)s_pServerConf + 2) == 2
                                            && !CExecLvlRepresentation::FInternal(v510) )
                                          {
                                            if ( v65 && (unsigned __int8)QueryHints::FHintSet(v65, 17) )
                                            {
LABEL_184:
                                              if ( (unsigned __int8)QueryHints::FHintSet(v65, 13) )
                                              {
LABEL_648:
                                                v881 |= 0x10u;
LABEL_186:
                                                if ( (!v65 || !(unsigned __int8)QueryHints::FHintSet(v65, 42))
                                                  && !*(_BYTE *)(v865 + 37) )
                                                {
                                                  v885 |= 4u;
                                                }
                                                if ( !*(_BYTE *)(v865 + 38) )
                                                  v885 |= 8u;
                                                v117 = v872;
                                                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                          + SystemThread_TlsIndex)
                                                                                        + SystemThread_TlsOffset)
                                                                            + 128LL)
                                                                + 76LL)
                                                    & 0x8000000) != 0 )
                                                {
                                                  LOBYTE(v117) = v872 | 2;
                                                  v872 |= 2u;
                                                }
                                                v118 = *(_QWORD *)(*((_QWORD *)v510 + 1) + 40LL);
                                                if ( v118
                                                  && *(_QWORD *)v118
                                                  && (*(_BYTE *)(*(_QWORD *)v118 + 144LL) & 1) != 0 )
                                                {
                                                  LOBYTE(v117) = v117 | 4;
                                                  v872 = v117;
                                                }
                                                if ( *(_DWORD *)(qword_102ECFB00 + 14504)
                                                  && !*(_BYTE *)(GetXdbServerGlobals(v117, v118) + 16289) )
                                                {
                                                  v876 &= ~1u;
                                                }
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 71)
                                                  && v878 >= 140 )
                                                {
                                                  v881 |= 0x80u;
                                                }
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 73) )
                                                  v883 |= 8u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 75) )
                                                  v883 |= 4u;
                                                if ( *(_QWORD *)(GetSqlServerGlobals() + 40) )
                                                  v904 = *(_QWORD *)(GetSqlServerGlobals() + 40);
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 76) )
                                                  v881 |= 1u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 77)
                                                  && v878 >= 140
                                                  && *((_DWORD *)s_pServerConf + 2) == 2
                                                  && !CExecLvlRepresentation::FInternal(v510)
                                                  && (*((_BYTE *)v510 + 128) & 4) == 0
                                                  && (!v65 || !(unsigned __int8)QueryHints::FHintSet(v65, 14))
                                                  && !*(_BYTE *)(v865 + 32) )
                                                {
                                                  v881 |= 8u;
                                                }
                                                if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39) == 251 )
                                                {
                                                  v783 = v39;
                                                  v253 = 0;
                                                  v254 = *(CDataExportParameters **)(v39 + 784);
                                                  if ( v254 )
                                                    v253 = CDataExportParameters::DeepCopy(v254, v507);
                                                  v910 = v253;
                                                }
                                                v119 = v524;
                                                (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v524 + 96LL))(v524);
                                                v784 = 0;
                                                v785 = 0;
                                                if ( *(_QWORD *)(v39 + 688) )
                                                {
                                                  v787 = &v914;
                                                  v121 = *(_QWORD *)(v39 + 688);
                                                  if ( v914 < v121 )
                                                    v122 = 0;
                                                  else
                                                    v122 = (struct CSessionTraceFlags *)(v914 - v121);
                                                  v554 = v122;
                                                  v679 = v122;
                                                  v780[3] = &v916;
                                                  v123 = *(_QWORD *)(v39 + 696);
                                                  if ( v916 < v123 )
                                                    v124 = 0;
                                                  else
                                                    v124 = (struct CSessionTraceFlags *)(v916 - v123);
                                                  v554 = v124;
                                                  v680 = v124;
                                                  LOBYTE(v120) = 1;
                                                  COptRsrcInfoHelper::SetCompTime(v637, &v679, v120, 0);
                                                  COptRsrcInfoHelper::SetCompTime(
                                                    v637,
                                                    &v680,
                                                    v125,
                                                    (unsigned __int8)v125);
                                                }
                                                v126 = a11[20];
                                                if ( *((_QWORD *)v126 + 17) )
                                                {
                                                  v884 |= 0x80u;
                                                  v337 = (int *)*((_QWORD *)v126 + 17);
                                                  if ( v337 )
                                                    v338 = *v337;
                                                  else
                                                    v338 = 0;
                                                  v913 = v338;
                                                }
                                                COptContext::SetHints((COptContext *)v861, v65);
                                                OptimizerUtil::ProcessHintsTelemetry(
                                                  (const struct COptContext *)v861,
                                                  v507,
                                                  v65,
                                                  v548);
                                                COptContext::ComputeHardwareDependentProperties(
                                                  (COptContext *)v861,
                                                  v65);
                                                if ( *((_QWORD *)a11[16] + 63) )
                                                {
                                                  v339 = (*(__int64 (__fastcall **)(__int64, CExecLvlRepresentation **))(*(_QWORD *)v39 + 1056LL))(
                                                           v39,
                                                           a11);
                                                  v340 = IQNManager::x_qntStmtInvalid;
                                                  if ( v339 )
                                                    v340 = 0;
                                                  v900 = v340;
                                                }
                                                if ( *(_QWORD *)(v39 + 600) )
                                                {
                                                  v897 = *(_QWORD *)(v39 + 600);
                                                  v341 = *(_QWORD *)(v39 + 600);
                                                  if ( v341 )
                                                  {
                                                    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v341 + 24LL))(v341) == 1 )
                                                      v898 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v39 + 600) + 16LL)
                                                                                               + 8LL))(*(_QWORD *)(*(_QWORD *)(v39 + 600) + 16LL));
                                                  }
                                                }
                                                v128 = *(_BYTE *)(v39 + 568);
                                                v129 = v870;
                                                if ( (v128 & 0x20) != 0 )
                                                {
                                                  v129 = v870 | 0x40000;
                                                  v870 |= 0x40000u;
                                                  v128 = *(_BYTE *)(v39 + 568);
                                                }
                                                v130 = (v128 & 8) == 0;
                                                v131 = v871;
                                                if ( !v130 )
                                                {
                                                  v131 = v871 | 0x2000;
                                                  v871 |= 0x2000u;
                                                }
                                                if ( (*(_BYTE *)(v39 + 570) & 8) != 0 )
                                                {
                                                  v129 |= 0x80000u;
                                                  v870 = v129;
                                                }
                                                if ( (*(_BYTE *)(v39 + 571) & 0x10) != 0 )
                                                {
                                                  v129 |= 0x100000u;
                                                  v870 = v129;
                                                }
                                                if ( *(char *)(v39 + 569) < 0 )
                                                {
                                                  v871 = v131 | 0x4000;
                                                  LOBYTE(v127) = 1;
                                                  CExecLvlRepresentation::SetNotCacheable(v510, 41, v127);
                                                  v131 = v871;
                                                  v129 = v870;
                                                }
                                                v132 = *(_BYTE *)(v39 + 570);
                                                if ( (v132 & 1) != 0 )
                                                {
                                                  v131 |= 0x8000u;
                                                  v871 = v131;
                                                  v132 = *(_BYTE *)(v39 + 570);
                                                }
                                                if ( (v132 & 2) != 0 )
                                                  v871 = v131 | 0x10000;
                                                v133 = *(_BYTE *)(v39 + 569);
                                                if ( (v133 & 4) != 0 )
                                                {
                                                  v777 = xmmword_1026A3440;
                                                  (*(void (__fastcall **)(struct IQueryCompile *, __int128 *))(*(_QWORD *)v524 + 8LL))(
                                                    v524,
                                                    &v777);
                                                  v652 = 2924;
                                                  v781 = (struct IMemObj *)*((_QWORD *)v527 + 48);
                                                  v342 = operator new(
                                                           0x18u,
                                                           v781,
                                                           "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                           2924,
                                                           3u);
                                                  v786 = v342;
                                                  if ( v342 )
                                                  {
                                                    *v342 = &CEnvElem::`vftable';
                                                    v342[1] = 0;
                                                    v342[2] = 0;
                                                    *v342 = &CNeedStrictSetOpts::`vftable';
                                                  }
                                                  else
                                                  {
                                                    v342 = 0;
                                                  }
                                                  CEnvCollection::AddEnvElem(v527, (struct CEnvElem *)v342);
                                                  v133 = *(_BYTE *)(v39 + 569);
                                                  v129 = v870;
                                                }
                                                if ( (v133 & 8) != 0 )
                                                  v870 = v129 | 0x10000;
                                                if ( (*(_BYTE *)(v39 + 571) & 0x10) != 0 )
                                                {
                                                  v778 = xmmword_10255BFE0;
                                                  (*(void (__fastcall **)(struct IQueryCompile *, __int128 *))(*(_QWORD *)v119 + 8LL))(
                                                    v119,
                                                    &v778);
                                                }
                                                if ( *(char *)(v39 + 720) < 0 )
                                                  v872 |= 0x40u;
                                                if ( v878 >= 150 || (v876 & 0x10) != 0 )
                                                  (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v119
                                                                                                 + 408LL))(v119);
                                                if ( (*(_BYTE *)(v39 + 720) & 0x20) != 0 )
                                                  v885 |= 0x80u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 78)
                                                  && (v878 >= 150
                                                   && *(_BYTE *)(qword_102ECFB00 + 48768)
                                                   && *(_BYTE *)(qword_102ECFB00 + 48772)
                                                   || v878 >= 160
                                                   || (v876 & 0x10) != 0) )
                                                {
                                                  v883 |= 0x20u;
                                                }
                                                v681 = v861;
                                                v724 = &v681;
                                                v611 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                           + SystemThread_TlsIndex)
                                                                                         + SystemThread_TlsOffset)
                                                                             + 176LL)
                                                                 + 32LL);
                                                v134 = ((*(_DWORD *)(*((_QWORD *)v510 + 1) + 32LL) & 4) != 0
                                                     || CExecLvlRepresentation::FStoredProc(v510))
                                                    && *(_DWORD *)(v611 + 72) == 193
                                                    && *(_WORD *)(v611 + 226) != 4;
                                                v135 = COptContext::InitializeInterleavedExec((COptContext *)v861, v134);
                                                CExecLvlRepresentation::InitializeForInterleavedExec(v510, v135, v507);
                                                if ( *((_BYTE *)v510 + 88) )
                                                  v881 |= 2u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 201) )
                                                  v886 |= 4u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 215) )
                                                  v886 |= 8u;
                                                if ( *(_BYTE *)(GetXdbServerGlobals(v137, v136) + 12004) )
                                                {
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 119) )
                                                    v883 |= 0x40u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 79) )
                                                    v883 |= 0x80u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 85) )
                                                    v884 |= 1u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 86) )
                                                    v884 |= 2u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 87) )
                                                    v884 |= 4u;
                                                  v138 = CurrentDb;
                                                  v343 = g_dbtableFactory[4](CurrentDb);
                                                  v517 = *(_BYTE *)(GetXdbServerGlobals(v345, v344) + 12004);
                                                  if ( v517 && *(_QWORD *)(v343 + 5320) )
                                                    v884 |= 8u;
                                                }
                                                else
                                                {
                                                  v138 = CurrentDb;
                                                }
                                                if ( (unsigned int)IsVDWOrFidoInstance() )
                                                {
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 127) )
                                                    v884 |= 0x20u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 126) )
                                                    v884 |= 0x10u;
                                                }
                                                if ( IsXDBDwPestoInstance() )
                                                {
                                                  LODWORD(v588) = *(_DWORD *)(v865 + 48);
                                                  v568 = (unsigned __int16)v588;
                                                  v732 = qword_102ECFB00;
                                                  v346 = *(_QWORD *)(qword_102ECFB00 + 32);
                                                  v682 = v346;
                                                  switch ( (unsigned __int16)v588 )
                                                  {
                                                    case 0x7FFCu:
                                                      v347 = *(DBTABLE **)(v346 + 104);
                                                      break;
                                                    case 0x7FFDu:
                                                      v347 = *(DBTABLE **)(v346 + 112);
                                                      break;
                                                    case 0x7FFFu:
                                                      v347 = *(DBTABLE **)(v346 + 88);
                                                      break;
                                                    default:
                                                      if ( (unsigned int)(unsigned __int16)v588 > *(_DWORD *)(v346 + 76)
                                                        || !(_WORD)v588 )
                                                      {
                                                        goto LABEL_270;
                                                      }
                                                      _mm_lfence();
                                                      v347 = *(DBTABLE **)(*(_QWORD *)(v682 + 40) + 8LL * (v568 - 1));
                                                      v138 = CurrentDb;
                                                      break;
                                                  }
                                                  if ( v347 && DBTABLE::IsDwPestoDistributionDb(v347) )
                                                    v885 |= 0x10u;
                                                }
LABEL_270:
                                                v139 = g_dbtableFactory[4](v138);
                                                v140 = RecoveryUnit::GetOnDiskVersion(*(RecoveryUnit **)(v139 + 4624));
                                                if ( (byte_102EDCD04 || (*((_BYTE *)qword_102ECFB10 + 1625) & 0x10) != 0)
                                                  && v140 >= 0x3ABu )
                                                {
                                                  v885 |= 1u;
                                                  v732 = *(_QWORD *)(SystemThread_TlsOffset
                                                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + SystemThread_TlsIndex));
                                                  v348 = *(_QWORD *)(v732 + 80);
                                                  v349 = *(_BYTE *)(v348 + 66);
                                                  if ( (*(_BYTE *)(v348 + 68) & 8) != 0 )
                                                    v349 >>= 1;
                                                  if ( (v349 & 1) != 0 || (v350 = *((_BYTE *)v76 + 17), (v350 & 8) != 0) )
                                                  {
                                                    v351 = 0;
                                                    v350 = *((_BYTE *)v76 + 17);
                                                  }
                                                  else
                                                  {
                                                    v351 = 1;
                                                  }
                                                  v513 = v351;
                                                  v514 = (v350 & 4) != 0;
                                                  if ( (*((_BYTE *)qword_102ECFB10 + 1626) & 4) == 0 )
                                                  {
                                                    v352 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + SystemThread_TlsIndex)
                                                                     + SystemThread_TlsOffset);
                                                    if ( !v352
                                                      || (v353 = **(struct CSessionTraceFlags ***)(v352 + 56)) == 0
                                                      || !CSessionTraceFlags::CheckSessionTraceInternal(v353, 0x32D2u) )
                                                    {
                                                      v354 = *(DBTABLE **)(*(_QWORD *)(v139 + 4624) + 1712LL);
                                                      if ( (*((_BYTE *)v354 + 60) & 1) != 0
                                                        && !DBTABLE::IsCOWReplicaDatabase(v354)
                                                        && (v513 || v514) )
                                                      {
                                                        v885 |= 2u;
                                                      }
                                                    }
                                                  }
                                                  v138 = CurrentDb;
                                                }
                                                v141 = *((_QWORD *)v510 + 8);
                                                if ( v141 )
                                                {
                                                  v683 = *((_QWORD *)v510 + 8);
                                                  if ( *(_QWORD *)(v141 + 8) || *(_QWORD *)(v141 + 128) )
                                                    *(_BYTE *)(v141 + 704) = 0;
                                                  v355 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset;
                                                  v356 = *(_QWORD **)(v355 + 256);
                                                  if ( !v356 )
                                                  {
                                                    SystemThread::MakeMiniSOSThread(0);
                                                    v356 = *(_QWORD **)(v355 + 256);
                                                  }
                                                  if ( v356[107] )
                                                  {
                                                    v358 = __rdtsc();
                                                    v359 = v356[108];
                                                    if ( v358 <= v359 )
                                                      v360 = 0;
                                                    else
                                                      v360 = v358 - v359;
                                                    v357 = v360 + v356[109];
                                                  }
                                                  else
                                                  {
                                                    v357 = 0;
                                                  }
                                                  *(_QWORD *)(v141 + 8) = v357;
                                                  *(_QWORD *)(v683 + 128) = __rdtsc();
                                                  v138 = CurrentDb;
                                                }
                                                v559 = 0;
                                                v755 = v39;
                                                *(_QWORD *)(v39 + 384) = a11;
                                                v142 = v583;
                                                v143 = CRelOp_Query::PrepareQueryForQP((CRelOp_Query *)v39, v548, v583);
                                                v508 = v143;
                                                if ( *(_BYTE *)(v39 + 581) )
                                                  v870 |= 1u;
                                                if ( (v871 & 8) != 0 )
                                                {
                                                  if ( !(unsigned int)IsVDWFrontendInstance()
                                                    || !*((_BYTE *)qword_102EF3550 + 1645) )
                                                  {
                                                    utassert_fail(
                                                      1u,
                                                      "IsVdwFrontendExtDistrComputationEnabled()",
                                                      "pqobuild.cpp",
                                                      3153,
                                                      0);
                                                  }
                                                  v144 = v873 | 4;
                                                  v873 |= 4u;
                                                }
                                                else
                                                {
                                                  v144 = v873;
                                                }
                                                if ( (v144 & 4) != 0
                                                  && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 74) )
                                                {
                                                  v883 |= 1u;
                                                }
                                                if ( (!*(_BYTE *)(qword_102ECFB00 + 48768)
                                                   || !*(_BYTE *)(qword_102ECFB00 + 48772))
                                                  && v877 > -1
                                                  && (v876 & 0x20) == 0 )
                                                {
                                                  ex_raise(1, 2, 16, 31, 34, L"SCALEOUTEXECUTION");
                                                }
                                                if ( (*(_BYTE *)(v39 + 720) & 0x40) != 0 )
                                                {
                                                  v145 = v507;
                                                  if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 80) )
                                                  {
                                                    v143 = PexprGraphOptimization(v143, v507, v138);
                                                    v508 = v143;
                                                  }
                                                }
                                                else
                                                {
                                                  v145 = v507;
                                                }
                                                if ( v505 )
                                                {
                                                  if ( (*(_BYTE *)(v39 + 721) & 1) != 0
                                                    && (*(unsigned __int8 (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v524 + 368LL))(v524) )
                                                  {
                                                    v569 = v138;
                                                    OptimizerUtil::FindNode<CFireApproxQueryProcessingCompileXEvents>(
                                                      v143,
                                                      &v569);
                                                  }
                                                  if ( v584 && (*(_BYTE *)(v39 + 721) & 0xC) != 0 )
                                                  {
                                                    v653 = 3208;
                                                    v361 = operator new(
                                                             0x20u,
                                                             v145,
                                                             "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                             3208,
                                                             1u);
                                                    v362 = (unsigned __int64)v361;
                                                    v756 = v361;
                                                    if ( v361 )
                                                    {
                                                      v757 = v507;
                                                      v758 = v507;
                                                      v759 = v507;
                                                      *(_QWORD *)v361 = v507;
                                                      v361[3] = 0;
                                                      v361[4] = 6;
                                                      *((_QWORD *)v361 + 3) = 0;
                                                    }
                                                    else
                                                    {
                                                      v362 = 0;
                                                    }
                                                    v559 = v362;
                                                    v363 = *(_BYTE *)(v39 + 721);
                                                    if ( (v363 & 4) != 0 )
                                                    {
                                                      v750 = v138;
                                                      v751 = v507;
                                                      v753 = v362;
                                                      v752 = 0;
                                                      OptimizerUtil::FindNode<CAddPercentileCompileXEvents>(v143, &v750);
                                                      v363 = *(_BYTE *)(v39 + 721);
                                                    }
                                                    if ( (v363 & 8) != 0 )
                                                    {
                                                      v747 = v138;
                                                      v748 = v507;
                                                      v749 = v362;
                                                      OptimizerUtil::FindNode<CAddApproxPercentileCompileXEvents>(
                                                        v143,
                                                        &v747);
                                                    }
                                                  }
                                                }
                                                if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 1)
                                                  && a9 != 194
                                                  && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v39 + 192LL))(v39) )
                                                {
                                                  v872 |= 0x20u;
                                                }
                                                v146 = *(CMATGen **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 4)
                                                                                           + 160LL)
                                                                               + 8LL)
                                                                   + 1088LL);
                                                if ( v146 )
                                                {
                                                  v364 = *(_QWORD **)(*(_QWORD *)(v39 + 368) + 8LL);
                                                  for ( i = v364; i; i = v364 )
                                                  {
                                                    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD *))(*v364 + 96LL))(
                                                      v364,
                                                      *((_QWORD *)v146 + 99),
                                                      (_QWORD *)v146 + 103);
                                                    v364 = (_QWORD *)v364[1];
                                                  }
                                                  CMATGen::AppendColumnEncryptionKeys(v146, (struct CRelOp_Query *)v39);
                                                }
                                                *(_QWORD *)(v39 + 384) = 0;
                                                if ( (v880 & 4) != 0 )
                                                {
                                                  v654 = 3259;
                                                  v366 = v613;
                                                  v367 = (char *)operator new(
                                                                   0x30u,
                                                                   v613,
                                                                   "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                   3259,
                                                                   1u);
                                                  v368 = (struct DRgCId *)v367;
                                                  v760 = v367;
                                                  if ( v367 )
                                                  {
                                                    v517 = 0;
                                                    v761 = v366;
                                                    v762 = v366;
                                                    v369 = v367 + 16;
                                                    v763 = v369;
                                                    v764 = v366;
                                                    *(_QWORD *)v369 = v366;
                                                    v369[8] = 0;
                                                    *((_DWORD *)v369 + 3) = 0;
                                                    *((_DWORD *)v369 + 4) = 1;
                                                    *((_QWORD *)v369 + 3) = 0;
                                                    *(_QWORD *)v368 = &CRefCount::`vftable';
                                                    *((_DWORD *)v368 + 2) = 1;
                                                    *(_QWORD *)v368 = &DRgCId::`vftable';
                                                  }
                                                  else
                                                  {
                                                    v368 = 0;
                                                  }
                                                  COptExpr::ExtractOutputColumns(v143, v366, v368);
                                                  v370 = v368;
                                                  v371 = XteBuilderObject;
                                                  XteDummyConstScanWithOutput = CreateXteDummyConstScanWithOutput(
                                                                                  XteBuilderObject,
                                                                                  v370,
                                                                                  v523);
                                                  v549 = (struct IQueryObj *)(*(__int64 (__fastcall **)(struct IXteBuilder *, struct CQte *))(*(_QWORD *)v371 + 568LL))(
                                                                               v371,
                                                                               XteDummyConstScanWithOutput);
                                                  (*(void (__fastcall **)(struct IQueryObj *, const struct CStatementDescription *, bool))(*(_QWORD *)v549 + 600LL))(
                                                    v549,
                                                    v614,
                                                    a14);
                                                  (*(void (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v549 + 560LL))(v549);
                                                  (*(void (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v549 + 624LL))(v549);
                                                  v130 = (*((_DWORD *)v143 + 2))-- == 1;
                                                  if ( v130 )
                                                    (**(void (__fastcall ***)(struct COptExpr *, __int64))v143)(v143, 1);
                                                  v200 = v510;
                                                  *((_BYTE *)v510 + 44) &= ~8u;
                                                  v901 = 0;
                                                  *(_QWORD *)(*(_QWORD *)(v864 + 56) + 40LL) = 0;
                                                  *(_QWORD *)(*(_QWORD *)(v864 + 64) + 40LL) = 0;
                                                  v560[7] = 0;
                                                  v213 = (const struct CCompExecCtxtStmt *)a11;
LABEL_464:
                                                  if ( v885 < 0 )
                                                    *(_BYTE *)(v39 + 720) |= 0x20u;
                                                  SOS_AutoOutOfScope__lambda_4a84f5ffa16570040bfa82ea971820d2___::_SOS_AutoOutOfScope__lambda_4a84f5ffa16570040bfa82ea971820d2___(&v724);
                                                  COptContext::~COptContext((COptContext *)v861);
                                                  ExcHandler::~ExcHandler((ExcHandler *)v788);
                                                  goto LABEL_1158;
                                                }
                                                v147 = v869;
                                                if ( (v868 & 0x1000) != 0 )
                                                {
                                                  v373 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset
                                                                               + 8LL)
                                                                   + 72LL);
                                                  v374 = v373 - 8;
                                                  if ( !v373 )
                                                    v374 = 0;
                                                  if ( (*(_DWORD *)(v374 + 92) & 0x1000) != 0
                                                    && *(_DWORD *)(*(_QWORD *)(v374 + 640) + 52LL) )
                                                  {
                                                    v879 |= 0x10u;
                                                    v143 = v508;
                                                    goto LABEL_293;
                                                  }
                                                  v147 = v869;
                                                  v143 = v508;
                                                }
                                                if ( (v879 & 1) != 0
                                                  || (v871 & 0x2000) != 0
                                                  || (v147 & 1) != 0
                                                  || (v876 & 1) == 0 )
                                                {
                                                  v879 &= ~0x10u;
                                                }
LABEL_293:
                                                v148 = v510;
                                                v149 = *((_QWORD *)v510 + 8);
                                                if ( v149 )
                                                {
                                                  v684 = *((_QWORD *)v510 + 8);
                                                  if ( !*(_QWORD *)(v149 + 8) || !*(_QWORD *)(v149 + 128) )
                                                    *(_BYTE *)(v149 + 704) = 0;
                                                  v375 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset;
                                                  v376 = *(_QWORD **)(v375 + 256);
                                                  if ( !v376 )
                                                  {
                                                    SystemThread::MakeMiniSOSThread(0);
                                                    v376 = *(_QWORD **)(v375 + 256);
                                                  }
                                                  if ( v376[107] )
                                                  {
                                                    v380 = __rdtsc();
                                                    v381 = v376[108];
                                                    if ( v380 <= v381 )
                                                      v382 = 0;
                                                    else
                                                      v382 = v380 - v381;
                                                    v377 = v382 + v376[109];
                                                  }
                                                  else
                                                  {
                                                    v377 = 0;
                                                  }
                                                  v378 = v684;
                                                  *(_QWORD *)(v684 + 248) += v377 - *(_QWORD *)(v149 + 8);
                                                  v379 = __rdtsc();
                                                  *(_QWORD *)(v378 + 368) += (((unsigned __int64)HIDWORD(v379) << 32)
                                                                            | (unsigned int)v379)
                                                                           - *(_QWORD *)(v378 + 128);
                                                  *(_QWORD *)(v149 + 8) = 0;
                                                  *(_QWORD *)(v378 + 128) = 0;
                                                  ++*(_DWORD *)(v378 + 484);
                                                  v143 = v508;
                                                }
                                                CTabRefIDUtil::AssignTabRefID(v507, v143);
                                                v150 = *(_QWORD *)(v39 + 648);
                                                if ( v150 )
                                                {
                                                  v383 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v150 + 16)
                                                                                           + 24LL))(*(_QWORD *)(v150 + 16));
                                                  v384 = *(_QWORD **)(v150 + 16);
                                                  if ( v383 == 99 )
                                                  {
                                                    v892 = v384[8];
                                                  }
                                                  else if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v384 + 24LL))(v384) == 98 )
                                                  {
                                                    v893 = *(_QWORD *)(v150 + 16) + 64LL;
                                                  }
                                                }
                                                v151 = *(_QWORD *)(v39 + 120);
                                                v152 = 0;
                                                if ( v151 )
                                                {
                                                  v255 = *(_QWORD *)(v151 + 208);
                                                  if ( v255 )
                                                    v256 = *(_QWORD *)(v255 + 8);
                                                  else
                                                    LODWORD(v256) = 0;
                                                  if ( (v256 & 0x8000000) != 0 )
                                                    v152 = 1;
                                                }
                                                v153 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v39
                                                                                                  + 1104LL))(v39)
                                                    && (*(_BYTE *)(v39 + 573) & 2) == 0;
                                                v154 = 0;
                                                if ( v151
                                                  && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 178)
                                                  && *(char *)(v151 + 537) < v154 )
                                                {
                                                  v154 = CAlgTableMetadata::FBulkContainJsonCol(
                                                           (CAlgTableMetadata *)v151,
                                                           (struct CRelOp_Query *)v39);
                                                }
                                                if ( v152 || (*(_BYTE *)(v39 + 569) & 0x10) != 0 )
                                                {
                                                  v155 = v871;
                                                  LODWORD(v155) = v871 | 0x2000000;
                                                  v871 |= 0x2000000u;
                                                }
                                                else
                                                {
                                                  v155 = v871;
                                                }
                                                if ( !v154 && (v152 || v153) )
                                                {
                                                  LODWORD(v155) = v155 | 0x4000000;
                                                  v871 = v155;
                                                }
                                                if ( (v868 & 0x1000) != 0 )
                                                {
                                                  v155 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset
                                                                               + 8LL)
                                                                   + 72LL);
                                                  v385 = v155 - 8;
                                                  if ( !v155 )
                                                    v385 = 0;
                                                  if ( (*(_DWORD *)(v385 + 92) & 0x1000) != 0
                                                    && *(_DWORD *)(*(_QWORD *)(v385 + 640) + 52LL) )
                                                  {
                                                    v386 = (_QWORD *)v899;
                                                    v387 = *(_DWORD *)(v899 + 8);
                                                    v570 = 0;
                                                    for ( j = 0; j < v387; v570 = j )
                                                    {
                                                      if ( SMD::FNonClusteredColumnStoreIndex(*(struct IMEDIndex **)(*v386 + 8LL * j)) )
                                                        v874 |= 0x80u;
                                                      ++j;
                                                    }
                                                  }
                                                  v143 = v508;
                                                }
                                                if ( *(_BYTE *)(*(_QWORD *)(v39 + 184) + 56LL) )
                                                {
                                                  if ( v878 < 160 && (v156 = v876, (v876 & 0x10) == 0)
                                                    || (v389 = CTrustedMachineHost::FConfigured(v155), v156 = v876, v389) )
                                                  {
                                                    v872 |= 0x80u;
                                                  }
                                                }
                                                else
                                                {
                                                  v156 = v876;
                                                }
                                                if ( (*(_DWORD *)(*((_QWORD *)v510 + 1) + 576LL) & 0x800) != 0 )
                                                  v876 = v156 | 0x40;
                                                if ( !COptBatchUtil::FQuerySupportsBatch((const struct COptContext *)v861) )
                                                {
LABEL_344:
                                                  if ( (v868 & 0x1000) != 0
                                                    && FindNode__PqoBuild_::_415_::CInvolvesColumnstoreIndexBuild_(
                                                         &v539,
                                                         v143) )
                                                  {
                                                    v874 |= 0x40u;
                                                  }
                                                  v169 = *(__int64 **)(*((_QWORD *)v148 + 1) + 40LL);
                                                  if ( (*(_BYTE *)(v866 + 16) & 2) != 0 )
                                                  {
                                                    v169 = (__int64 *)*v169;
                                                    if ( !*((_BYTE *)v169 + 145) )
                                                    {
                                                      v257 = (v169[24] & 6) == 6;
                                                      v258 = **((_QWORD **)v143 + 4);
                                                      if ( (v169[18] & 8) != 0
                                                        && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v258 + 16)
                                                                                                  + 24LL))(*(_QWORD *)(v258 + 16)) == 29 )
                                                      {
                                                        v258 = **(_QWORD **)(v258 + 32);
                                                      }
                                                      v259 = **(_QWORD **)(**(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v258 + 32) + 8LL)
                                                                                       + 32LL)
                                                                         + 32LL);
                                                      v260 = *(_QWORD *)(*(_QWORD *)(v259 + 32)
                                                                       + 8LL * *(int *)(v259 + 24)
                                                                       - 8);
                                                      if ( v257 )
                                                        v261 = *(_QWORD *)(**(_QWORD **)(v260 + 32) + 16LL);
                                                      else
                                                        v261 = *(_QWORD *)(v260 + 16);
                                                      COptContext::InclForStats(
                                                        (COptContext *)v861,
                                                        *(const struct CValRef **)(v261 + 64));
                                                    }
                                                  }
                                                  LOBYTE(v169) = 124;
                                                  YieldAndCheckForAbort(v169);
                                                  v723 = 0;
                                                  try
                                                  {
                                                    COptContext::PinExpr((COptContext *)v861, &v906, v143);
                                                    if ( (*((_BYTE *)qword_102ECFB10 + 296) & 0x40) == 0 )
                                                    {
                                                      v571 = 0;
                                                      v170 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      if ( *(_QWORD *)v170
                                                        && (v171 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v170 + 56LL)) != 0 )
                                                      {
                                                        v172 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                 v171,
                                                                 0x946u);
                                                      }
                                                      else
                                                      {
                                                        v172 = v571;
                                                      }
                                                      if ( v172 )
                                                      {
                                                        v143 = v508;
                                                      }
                                                      else
                                                      {
                                                        v634 = 1;
                                                        v635 = 0;
                                                        v636 = 0;
                                                        v633 = &CFingerprintUtilEx::`vftable';
                                                        v173 = *((_QWORD *)a11[20] + 17);
                                                        if ( v173 )
                                                        {
                                                          v175 = *(_QWORD *)(v173 + 16);
                                                          v143 = v508;
                                                        }
                                                        else
                                                        {
                                                          v174 = *(QueryHints **)(v39 + 56);
                                                          if ( v174 && *((_DWORD *)v174 + 40) )
                                                            v174 = *(QueryHints **)(v39 + 64);
                                                          v635 = 0;
                                                          v636 = 0;
                                                          if ( v174 )
                                                            QueryHints::ComputeHashsum(
                                                              v174,
                                                              (struct CFingerprintUtil *)&v633);
                                                          v143 = v508;
                                                          CFingerprintUtilEx::GenFingerprintForQueryTree(
                                                            (CFingerprintUtilEx *)&v633,
                                                            v508,
                                                            0);
                                                          v175 = v636;
                                                        }
                                                        (*(void (__fastcall **)(struct IQueryCompile *, __int64))(*(_QWORD *)v524 + 224LL))(
                                                          v524,
                                                          v175);
                                                        v903 = v175;
                                                        v633 = &CRefCount::`vftable';
                                                      }
                                                    }
                                                    v176 = v507;
                                                    COptExpr::DeriveGroupProperties(v143, v507, 1u, 0);
                                                    if ( CTableGroupProperties::FUnBoundParams(*((CTableGroupProperties **)v143
                                                                                               + 10)) )
                                                      ex_raise(86, 24, 16, 17);
                                                    if ( (v876 & 1) != 0 )
                                                      JUMPOUT(0x100470F76LL);
                                                    v515 = 0;
                                                    v390 = FindNode__PqoBuild_::_444_::CReferencesTableWithClusteredColumnstoreIndex_(
                                                             &v515,
                                                             v143);
                                                    if ( v390 )
                                                    {
                                                      v391 = *(CTableMetadata **)(*(_QWORD *)(v390 + 16) + 24LL);
                                                      CTableMetadata::WsDisplayName(v391);
                                                      LODWORD(Localeb) = CTableMetadata::CbDisplayName(v391);
                                                      ex_raise(353, 21, 16, 1, Localeb, v392);
                                                    }
                                                    g_CRV_QOptconsidermed = 0;
                                                    v177 = COptExpr::PexprFold(v507, v143);
                                                    COptExpr::DeriveGroupProperties(v177, v507, 1u, 0);
                                                    if ( v177 )
                                                    {
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 1075) & 0x20) != 0
                                                        || ((v591 = 0,
                                                             v178 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v178)
                                                         && (v179 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v178 + 56LL)) != 0
                                                          ? (v180 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v179,
                                                                      0x219Du))
                                                          : (v180 = v591),
                                                            v180) )
                                                      {
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v557,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        Stream = TraceStreamHolder::GetStream((TraceStreamHolder *)v557);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v685,
                                                          Stream);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)Stream + 16,
                                                          "*** Converted Tree: ***\n");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v685);
                                                        LOBYTE(v504) = 0;
                                                        LOBYTE(v503) = 1;
                                                        (*(void (__fastcall **)(struct COptExpr *, const char *, const char *, __int64, int, int, int, _QWORD, _QWORD))(*(_QWORD *)v177 + 32LL))(
                                                          v177,
                                                          String2,
                                                          String2,
                                                          4,
                                                          4,
                                                          v503,
                                                          v504,
                                                          0,
                                                          0);
                                                        v394 = TraceStreamHolder::GetStream((TraceStreamHolder *)v557);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v686,
                                                          v394);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v394 + 16,
                                                          "*******************\n");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v686);
                                                        v395 = TraceStreamHolder::GetStream((TraceStreamHolder *)v557);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v687,
                                                          v395);
                                                        std::ostream::flush((char *)v395 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v687);
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v557);
                                                      }
                                                    }
                                                    v181 = *((_QWORD *)v148 + 8);
                                                    if ( v181 )
                                                    {
                                                      v592 = *((_QWORD *)v148 + 8);
                                                      if ( *(_QWORD *)(v181 + 16) || *(_QWORD *)(v181 + 136) )
                                                        *(_BYTE *)(v181 + 704) = 0;
                                                      v396 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      v397 = *(_QWORD **)(v396 + 256);
                                                      if ( !v397 )
                                                      {
                                                        SystemThread::MakeMiniSOSThread(0);
                                                        v397 = *(_QWORD **)(v396 + 256);
                                                      }
                                                      if ( v397[107] )
                                                      {
                                                        v399 = __rdtsc();
                                                        v400 = v397[108];
                                                        if ( v399 <= v400 )
                                                          v401 = 0;
                                                        else
                                                          v401 = v399 - v400;
                                                        v398 = v401 + v397[109];
                                                      }
                                                      else
                                                      {
                                                        v398 = 0;
                                                      }
                                                      *(_QWORD *)(v181 + 16) = v398;
                                                      *(_QWORD *)(v592 + 136) = __rdtsc();
                                                    }
                                                    v555 = *((_QWORD *)v548 + 2);
                                                    v182 = *(_QWORD *)(v555 + 680);
                                                    if ( v182 )
                                                      v15 = *(_DWORD *)(v182 + 28);
                                                    else
                                                      v15 = 0;
                                                    v183 = v15 != 0;
                                                    v184 = 0;
                                                    v550 = 0;
                                                    v558 = 0;
                                                    v185 = 0;
                                                    v526 = 0;
                                                    if ( !CExecLvlRepresentation::FAutoParam(a11[20])
                                                      || (v187 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v186 + 8) + 328LL))(*(_QWORD *)(v186 + 8))) != 0 )
                                                    {
                                                      v187 = 1;
                                                    }
                                                    if ( v183 && v187 )
                                                    {
                                                      v188 = v611;
                                                      v189 = *(_QWORD *)(v611 + 128);
                                                      if ( v189 )
                                                        v190 = *(double *)(v189 + 80);
                                                      else
                                                        v190 = DOUBLE_0_9;
                                                      v655 = 3790;
                                                      v191 = (CInterestingPredicateExplorer *)operator new(
                                                                                                0x38u,
                                                                                                v507,
                                                                                                "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                                                3790,
                                                                                                1u);
                                                      v765 = v191;
                                                      if ( v191 )
                                                        v184 = CInterestingPredicateExplorer::CInterestingPredicateExplorer(
                                                                 v191,
                                                                 v507,
                                                                 v190,
                                                                 v890);
                                                      else
                                                        v184 = 0;
                                                      v550 = v184;
                                                      v192 = COptContext::CheckParameterSensitivePlanEligibility(v861);
                                                      if ( !*((_DWORD *)v184 + 12) )
                                                        *((_DWORD *)v184 + 12) = v192;
                                                      v193 = *(_QWORD *)(v188 + 128);
                                                      if ( v193 )
                                                      {
                                                        *(_DWORD *)v184 = *(_DWORD *)(v193 + 40);
                                                        *((_QWORD *)v184 + 1) = *(_QWORD *)(*(_QWORD *)(v188 + 128)
                                                                                          + 72LL);
                                                      }
                                                      v905 = v184;
                                                    }
                                                    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v39 + 1160LL))(v39) )
                                                    {
                                                      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v177 + 2)
                                                                                                  + 24LL))(*((_QWORD *)v177 + 2)) != 39 )
                                                        goto LABEL_388;
                                                      if ( !IsFidoDWFrontEndSession() )
                                                      {
                                                        v184 = v550;
                                                        v185 = (unsigned int *)v526;
                                                        goto LABEL_388;
                                                      }
                                                      v402 = IsFidoDWFrontEndSession();
                                                      if ( v402 )
                                                      {
                                                        if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
                                                          v402 = *((_BYTE *)qword_102EF3550 + 1651) != 0;
                                                        else
                                                          v402 = 0;
                                                      }
                                                      if ( v402
                                                        && *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v177 + 2) + 24LL) + 772LL) == 1 )
                                                      {
                                                        v184 = v550;
                                                        v185 = (unsigned int *)v526;
                                                        goto LABEL_388;
                                                      }
                                                      v403 = *(_QWORD *)(*(_QWORD *)(**((_QWORD **)v177 + 4) + 80LL)
                                                                       + 208LL);
                                                      if ( v403 )
                                                        v404 = *(_DWORD *)(v403 + 28);
                                                      else
                                                        v404 = 0;
                                                      if ( v404 )
                                                      {
                                                        v184 = v550;
                                                        v185 = (unsigned int *)v526;
                                                        goto LABEL_388;
                                                      }
                                                      v184 = v550;
                                                      v185 = (unsigned int *)v526;
                                                    }
                                                    v883 |= 0x10u;
LABEL_388:
                                                    if ( !(unsigned int)IsVDWFrontendInstance() )
                                                    {
LABEL_389:
                                                      if ( COptContext::FUseOpTreeXML((COptContext *)v861) )
                                                        v194 = COptContext::PqteOptimizeQueryForTreeXml(
                                                                 (COptContext *)v861,
                                                                 v177);
                                                      else
                                                        v194 = COptContext::PqteOptimizeWrapper(
                                                                 (COptContext *)v861,
                                                                 v177);
                                                      v616 = v194;
                                                      LOBYTE(v197) = v878 >= 160
                                                                  || (byte_102EDCD59
                                                                   || (*((_BYTE *)qword_102ECFB10 + 1693) & 0x40) != 0
                                                                    ? (v198 = 1)
                                                                    : (v198 = 0),
                                                                      v198);
                                                      if ( v184 )
                                                      {
                                                        if ( !(_BYTE)v197 && !*((_DWORD *)v184 + 12) )
                                                          *((_DWORD *)v184 + 12) = 31;
                                                        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 37)
                                                          && (*(_BYTE *)(v555 + 580) & 1) != 0
                                                          && (v884 & 0x40) != 0
                                                          && v199 )
                                                        {
                                                          CInterestingPredicateExplorer::PopulateSensitivePredicates(
                                                            v184,
                                                            v507);
                                                          v573 = 0;
                                                          for ( k = 0; ; v573 = k )
                                                          {
                                                            v263 = *((_QWORD *)v184 + 4);
                                                            v264 = v263 ? *(_DWORD *)(v263 + 12) : 0;
                                                            if ( k >= v264 )
                                                              break;
                                                            v265 = *(_QWORD *)(*(_QWORD *)(v263 + 24) + 8LL * k);
                                                            *(_QWORD *)(v265 + 40) = FindStatsInfoForMultiPlan(
                                                                                       v507,
                                                                                       *(struct CValRef **)(*(_QWORD *)(*(_QWORD *)v265 + 16LL) + 64LL),
                                                                                       *(struct CStatsStream **)(v265 + 16),
                                                                                       *((double *)v184 + 2),
                                                                                       (struct CQODouble *)(v265 + 24));
                                                            ++k;
                                                          }
                                                          v555 = *((_QWORD *)v184 + 4);
                                                          if ( v263 )
                                                          {
                                                            v406 = *(_DWORD *)(v263 + 12);
                                                            v522 = v406;
                                                          }
                                                          else
                                                          {
                                                            v406 = 0;
                                                            v522 = 0;
                                                          }
                                                          v558 = *(CMultiPlanFeedback **)(*((_QWORD *)a11[22] + 4)
                                                                                        + 128LL);
                                                          if ( v406 )
                                                          {
                                                            v656 = 3864;
                                                            v407 = (unsigned int *)operator new(
                                                                                     0x20u,
                                                                                     v507,
                                                                                     "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                                     3864,
                                                                                     1u);
                                                            v408 = v407;
                                                            v766 = v407;
                                                            if ( v407 )
                                                            {
                                                              v767 = v507;
                                                              v768 = v507;
                                                              v769 = v507;
                                                              *(_QWORD *)v407 = v507;
                                                              v407[3] = 0;
                                                              v407[4] = 3;
                                                              *((_QWORD *)v407 + 3) = 0;
                                                            }
                                                            else
                                                            {
                                                              v408 = 0;
                                                            }
                                                            if ( v185 != v408 )
                                                            {
                                                              v770 = v185;
                                                              if ( v185 )
                                                              {
                                                                CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>::~CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>(v185);
                                                                operator delete(v185, 0x20u);
                                                              }
                                                            }
                                                            v185 = v408;
                                                            v526 = (unsigned __int64)v408;
                                                            v409 = 0;
                                                            v578 = 0;
                                                            v410 = 0;
                                                            while ( v410 < v406 )
                                                            {
                                                              v411 = *(_QWORD **)(*(_QWORD *)(v555 + 24) + 8LL * v410);
                                                              v657 = 3869;
                                                              v412 = operator new(
                                                                       0x48u,
                                                                       v507,
                                                                       "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                       3869,
                                                                       1u);
                                                              v771 = v412;
                                                              if ( v412 )
                                                              {
                                                                *v412 = 0;
                                                                v412[1] = 0;
                                                                v412[2] = 0;
                                                                v412[3] = 0;
                                                                *((_QWORD *)v412 + 8) = 0;
                                                                *((_QWORD *)v412 + 4) = 0;
                                                              }
                                                              else
                                                              {
                                                                v412 = 0;
                                                              }
                                                              *((_QWORD *)v412 + 4) = v411[3];
                                                              *(_QWORD *)v412 = *v411;
                                                              *((_QWORD *)v412 + 1) = v411[1];
                                                              *((_QWORD *)v412 + 2) = v411[4];
                                                              *((_QWORD *)v412 + 3) = v411[2];
                                                              *((_QWORD *)v412 + 5) = v411[5];
                                                              *((_QWORD *)v412 + 6) = 0xBFF0000000000000uLL;
                                                              *((_QWORD *)v412 + 7) = 0xBFF0000000000000uLL;
                                                              *((_DWORD *)v412 + 16) = -1;
                                                              *((_BYTE *)v412 + 68) = 0;
                                                              if ( !*((_QWORD *)v185 + 3) )
                                                              {
                                                                v413 = v185[4];
                                                                *((_QWORD *)v185 + 3) = StdAlloc<CRawMemObjAlloc<0>>::AllocArray<CReqdPlanProperties *>(
                                                                                          v185,
                                                                                          v413);
                                                                v185[4] = v413;
                                                              }
                                                              v414 = v185[3];
                                                              v415 = v185[4];
                                                              if ( v414 >= (unsigned int)v415 )
                                                              {
                                                                if ( v414 == -1 )
                                                                {
                                                                  utassert_fail(
                                                                    1u,
                                                                    "m_cElems < ULONG_MAX",
                                                                    "Sql\\Ntdbms\\include\\common\\stdarray.inl",
                                                                    217,
                                                                    0);
                                                                  v414 = v185[3];
                                                                  v415 = v185[4];
                                                                }
                                                                v525 = v415;
                                                                v416 = v415;
                                                                while ( v414 + 1 > v416 )
                                                                {
                                                                  v417 = v416;
                                                                  if ( v416 > 0x100 )
                                                                    v417 = 256;
                                                                  if ( v416 > ~v417 )
                                                                  {
                                                                    v415 = 0xFFFFFFFFLL;
                                                                    v525 = -1;
                                                                    v416 = -1;
                                                                  }
                                                                  else
                                                                  {
                                                                    v415 = v416 + v417;
                                                                    v416 = v415;
                                                                    v525 = v415;
                                                                  }
                                                                }
                                                                v690 = *(_QWORD *)v185;
                                                                v626 = (_QWORD *)StdAlloc<CRawMemObjAlloc<0>>::AllocArray<CReqdPlanProperties *>(
                                                                                   v185,
                                                                                   v415);
                                                                v627 = v690;
                                                                v628 = &v525;
                                                                v574 = 0;
                                                                for ( m = 0; m < v185[3]; v574 = m )
                                                                {
                                                                  v626[m] = *(_QWORD *)(*((_QWORD *)v185 + 3) + 8LL * m);
                                                                  ++m;
                                                                }
                                                                v419 = (void *)*((_QWORD *)v185 + 3);
                                                                if ( v419 )
                                                                {
                                                                  v420 = v185[4];
                                                                  v576 = v420;
                                                                  while ( v420 )
                                                                    v576 = --v420;
                                                                  operator delete[](v419);
                                                                  *((_QWORD *)v185 + 3) = 0;
                                                                }
                                                                v185[4] = 0;
                                                                v421 = v626;
                                                                v626 = 0;
                                                                *((_QWORD *)v185 + 3) = v421;
                                                                v185[4] = v525;
                                                                v422 = *v628;
                                                                v577 = *v628;
                                                                if ( v626 )
                                                                {
                                                                  while ( v422 )
                                                                    v577 = --v422;
                                                                  operator delete[](v626);
                                                                }
                                                                v626 = 0;
                                                              }
                                                              *(_QWORD *)(*((_QWORD *)v185 + 3) + 8LL * v185[3]++) = v412;
                                                              v578 = ++v409;
                                                              v410 = v409;
                                                              v406 = v522;
                                                            }
                                                            if ( v890 )
                                                            {
                                                              CInterestingPredicateExplorer::VerifyUsePlanAndSortPredicateInfoWrapperList(
                                                                v184,
                                                                v185);
                                                              if ( !(unsigned __int8)CMultiPlanFeedback::CompilePredicates(
                                                                                       v558,
                                                                                       v523) )
                                                                ex_raise(86, 98, 16, 5);
                                                              v176 = v507;
                                                            }
                                                            else
                                                            {
                                                              COptContext::TrackOptTime(
                                                                (COptContext *)v861,
                                                                v775,
                                                                &v774,
                                                                &v773,
                                                                &v594,
                                                                &v772,
                                                                0);
                                                              v423 = v594 * 1000.0;
                                                              v424 = 0;
                                                              if ( v594 * 1000.0 >= 9.223372036854776e18 )
                                                              {
                                                                v423 = v423 - 9.223372036854776e18;
                                                                if ( v423 < 9.223372036854776e18 )
                                                                  v424 = 0x8000000000000000uLL;
                                                              }
                                                              if ( v424 + (unsigned int)(int)v423 <= *((int *)v558 + 22) )
                                                              {
                                                                CMultiPlanFeedback::CompilePredicates(v558, v523);
                                                                v176 = v507;
                                                              }
                                                              else
                                                              {
                                                                v594 = 2.000000000000004;
                                                                if ( (qword_102EDCA04 & 0x4000000000000000LL) != 0 )
                                                                {
                                                                  v828 = 0;
                                                                  v829 = 1;
                                                                  v830 = 0;
                                                                  v831 = &v834;
                                                                  v832 = &v838;
                                                                  v839 = 0;
                                                                  v840 = 0;
                                                                  v833 = 0;
                                                                  v841 = 0;
                                                                  v834 = &v842;
                                                                  v835 = 4;
                                                                  v836 = 0;
                                                                  v837 = 0;
                                                                  v842 = 36;
                                                                  XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason::Publish((XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason *)v827);
                                                                }
                                                                v176 = v507;
                                                              }
                                                            }
                                                          }
                                                          else if ( v890 )
                                                          {
                                                            ex_raise(86, 98, 16, 6);
                                                          }
                                                        }
                                                        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 36) )
                                                          CInterestingPredicateExplorer::FirePredicateSelectionXevent(
                                                            v184,
                                                            v176,
                                                            *((_WORD *)v560 + 52),
                                                            *(_BYTE *)(v39 + 580) & 1);
                                                        if ( *((_DWORD *)v184 + 12) )
                                                        {
                                                          v555 = 0x400000000000000ALL;
                                                          if ( (qword_102EDCA04 & 0x4000000000000000LL) != 0 )
                                                          {
                                                            v844 = 0;
                                                            v845 = 1;
                                                            v846 = 0;
                                                            v847 = &v850;
                                                            v848 = &v854;
                                                            v855 = 0;
                                                            v856 = 0;
                                                            v849 = 0;
                                                            v857 = 0;
                                                            v850 = &v858;
                                                            v851 = 4;
                                                            v852 = 0;
                                                            v853 = 0;
                                                            v858 = *((_DWORD *)v184 + 12);
                                                            XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason::Publish((XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason *)v843);
                                                          }
                                                        }
                                                      }
                                                      if ( v909 )
                                                      {
                                                        CETelemetryPackage::PublishCEPackage(v909, v195);
                                                        v425 = v909;
                                                        v775[1] = (unsigned __int64)v909;
                                                        if ( v909 )
                                                        {
                                                          v775[2] = (unsigned __int64)v909;
                                                          CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v909);
                                                          operator delete(v425, 0x30u);
                                                        }
                                                        v909 = 0;
                                                      }
                                                      v200 = v510;
                                                      v201 = *((_QWORD *)v510 + 8);
                                                      if ( v201 )
                                                      {
                                                        v595 = *((_QWORD *)v510 + 8);
                                                        if ( !*(_QWORD *)(v201 + 16) || !*(_QWORD *)(v201 + 136) )
                                                          *(_BYTE *)(v201 + 704) = 0;
                                                        v426 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v196 = *(_QWORD **)(v426 + 256);
                                                        if ( !v196 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v196 = *(_QWORD **)(v426 + 256);
                                                        }
                                                        if ( v196[107] )
                                                        {
                                                          v430 = __rdtsc();
                                                          v431 = v196[108];
                                                          if ( v430 <= v431 )
                                                            v432 = 0;
                                                          else
                                                            v432 = v430 - v431;
                                                          v427 = v432 + v196[109];
                                                        }
                                                        else
                                                        {
                                                          v427 = 0;
                                                        }
                                                        v428 = v595;
                                                        *(_QWORD *)(v595 + 256) += v427 - *(_QWORD *)(v201 + 16);
                                                        v429 = __rdtsc();
                                                        *(_QWORD *)(v428 + 376) += (((unsigned __int64)HIDWORD(v429) << 32)
                                                                                  | (unsigned int)v429)
                                                                                 - *(_QWORD *)(v428 + 136);
                                                        *(_QWORD *)(v201 + 16) = 0;
                                                        *(_QWORD *)(v428 + 136) = 0;
                                                        ++*(_DWORD *)(v428 + 488);
                                                        v185 = (unsigned int *)v526;
                                                      }
                                                      v516 = (*(_DWORD *)(*((_QWORD *)v510 + 1) + 580LL) & 2) != 0;
                                                      v552 = 0;
                                                      if ( v516 )
                                                      {
                                                        if ( !COptContext::IsDwGen3FrontendInstanceWithDwUqoCompile((COptContext *)v861) )
                                                        {
                                                          if ( a15 )
                                                            v439 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v527 + 43) + 64LL))(*((_QWORD *)v527 + 43));
                                                          else
                                                            v439 = 0;
                                                          v658 = 3976;
                                                          v440 = operator new(
                                                                   0x4F8u,
                                                                   v523,
                                                                   "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                   3976,
                                                                   1u);
                                                          v775[3] = (unsigned __int64)v440;
                                                          if ( v440 )
                                                            v441 = (struct CMemoXml *)CMemoXml::CMemoXml(
                                                                                        v440,
                                                                                        1,
                                                                                        *(unsigned int *)(*((_QWORD *)v510 + 1) + 1128LL),
                                                                                        *(unsigned int *)(*((_QWORD *)v510 + 1) + 1132LL),
                                                                                        0,
                                                                                        v439);
                                                          else
                                                            v441 = 0;
                                                          v552 = v441;
                                                          v442 = (v874 & 2) != 0 && (v873 & 4) != 0;
                                                          v202 = a11;
                                                          if ( v442 )
                                                            CMemo::PrintXmlForPdwUqo(
                                                              v888,
                                                              (struct CRelOp_Query *)v39,
                                                              v548,
                                                              v527,
                                                              (const struct CCompExecCtxtStmt *)a11,
                                                              v441,
                                                              0,
                                                              0,
                                                              1);
                                                          else
                                                            CMemo::PrintXmlForPdw(
                                                              v888,
                                                              *((_DWORD *)v888 + 55),
                                                              0,
                                                              1,
                                                              (struct CRelOp_Query *)v39,
                                                              v548,
                                                              v527,
                                                              (const struct CCompExecCtxtStmt *)a11,
                                                              v441,
                                                              0,
                                                              0);
                                                          goto LABEL_412;
                                                        }
                                                        v552 = PMemoXml(**((const struct CQte ***)v616 + 3));
                                                      }
                                                      v202 = a11;
LABEL_412:
                                                      v203 = 0;
                                                      v564 = 0;
                                                      if ( (unsigned __int8)COptContext::FFeatureSwitchOn(
                                                                              v861,
                                                                              213,
                                                                              v196,
                                                                              v197)
                                                        && (v871 & 0x80) != 0
                                                        && !DataVirtualizationResource::IsDataVirtualizationFeatureSetLockdownEnabled(v204)
                                                        && (unsigned __int8)COptContext::FFeatureSwitchOn(
                                                                              v861,
                                                                              141,
                                                                              v433,
                                                                              v434) )
                                                      {
                                                        v659 = 4006;
                                                        v435 = operator new(
                                                                 0x18u,
                                                                 v176,
                                                                 "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                 4006,
                                                                 1u);
                                                        v775[4] = (unsigned __int64)v435;
                                                        if ( v435 )
                                                        {
                                                          v436 = *(_DWORD *)(v39 + 80);
                                                          *(_QWORD *)v435 = 0;
                                                          v435[2] = v436 + 1;
                                                          *((_QWORD *)v435 + 2) = v176;
                                                        }
                                                        CAutoP<PartitionReducedSourceList>::operator=(&v564);
                                                        v775[5] = (unsigned __int64)v176;
                                                        v775[6] = (unsigned __int64)v176;
                                                        v437 = *(_DWORD *)(v39 + 80);
                                                        v775[7] = (unsigned __int64)v176;
                                                        v600 = (unsigned __int64)v176;
                                                        v601 = 0;
                                                        v438 = 1;
                                                        if ( v437 )
                                                          v438 = v437;
                                                        v602 = v438;
                                                        v603 = 0;
                                                        v775[8] = (unsigned __int64)&v604;
                                                        v775[9] = (unsigned __int64)v859;
                                                        v775[10] = v600;
                                                        v604 = v600;
                                                        v605 = 0;
                                                        v606 = v438;
                                                        v607 = 0;
                                                        CCompExecCtxt::CCompExecCtxt(
                                                          (CCompExecCtxt *)v859,
                                                          (const struct CCompExecCtxt *)v202);
                                                        v860 = v202[22];
                                                        v203 = v564;
                                                        DataVirtualizationQeoptimUtils::TryEliminatePartitions(
                                                          (unsigned int)v861,
                                                          (_DWORD)v176,
                                                          (_DWORD)v564,
                                                          (unsigned int)v859,
                                                          (__int64)&v604);
                                                        v601 = 0;
                                                        if ( v603 )
                                                        {
                                                          v443 = v602;
                                                          v579 = v602;
                                                          while ( v443 )
                                                            v579 = --v443;
                                                          operator delete[](v603);
                                                          v603 = 0;
                                                        }
                                                        v602 = 0;
                                                      }
                                                      if ( v524 && v203 && *v203 )
                                                      {
                                                        v444 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v445 = *(_QWORD *)(v444 + 256);
                                                        if ( !v445 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v445 = *(_QWORD *)(v444 + 256);
                                                        }
                                                        v446 = CRowsetFilesInfo::Copy(
                                                                 *(CRowsetFilesInfo **)(*v564 + 32LL),
                                                                 *(struct IMemObj **)(v445 + 1000));
                                                        *((_QWORD *)v524 + 113) = v446;
                                                        v185 = (unsigned int *)v526;
                                                      }
                                                      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 167) )
                                                        CSqlDwTelemetry::ProcessQueryAnnotations(
                                                          (struct COptContext *)v861,
                                                          (struct CRelOp_Query *)v39);
                                                      v901 = 0;
                                                      *(_QWORD *)(*(_QWORD *)(v864 + 56) + 40LL) = 0;
                                                      *(_QWORD *)(*(_QWORD *)(v864 + 64) + 40LL) = 0;
                                                      v205 = *((_QWORD *)v510 + 8);
                                                      if ( v205 )
                                                      {
                                                        v587 = *((_QWORD *)v510 + 8);
                                                        if ( *(_QWORD *)(v205 + 24) || *(_QWORD *)(v205 + 144) )
                                                          *(_BYTE *)(v205 + 704) = 0;
                                                        v447 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v448 = *(_QWORD **)(v447 + 256);
                                                        if ( !v448 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v448 = *(_QWORD **)(v447 + 256);
                                                        }
                                                        if ( v448[107] )
                                                        {
                                                          v450 = __rdtsc();
                                                          v451 = v448[108];
                                                          if ( v450 <= v451 )
                                                            v452 = 0;
                                                          else
                                                            v452 = v450 - v451;
                                                          v449 = v452 + v448[109];
                                                        }
                                                        else
                                                        {
                                                          v449 = 0;
                                                        }
                                                        *(_QWORD *)(v205 + 24) = v449;
                                                        *(_QWORD *)(v587 + 144) = __rdtsc();
                                                        v185 = (unsigned int *)v526;
                                                      }
                                                      v206 = (struct IQueryObj *)(*(__int64 (__fastcall **)(struct IXteBuilder *, struct CQte *))(*(_QWORD *)XteBuilderObject + 568LL))(
                                                                                   XteBuilderObject,
                                                                                   v616);
                                                      v549 = v206;
                                                      v207 = (*(__int64 (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v206 + 120LL))(v206);
                                                      v208 = *(int **)(v867 + 16);
                                                      v209 = v208[2] > 177
                                                          && (*(_DWORD *)(*(_QWORD *)v208 + 20LL) & 0x20000) != 0;
                                                      if ( v209 && v911 == 3 && v912 && v912 != v207 )
                                                        ex_raise(86, 75, 16, 5);
                                                      if ( v891 )
                                                      {
                                                        v587 = 0x8000000000000009uLL;
                                                        if ( (int)qword_102EDCA04 < 0 )
                                                          COptAntiPatterns::FireAllAntiPatternEvents(v891);
                                                      }
                                                      v210 = v558;
                                                      if ( v558 && *((_DWORD *)v558 + 1) != 1 && v185 && v185[3] )
                                                      {
                                                        v742 = 1;
                                                        v741 = &CFingerprintUtil::`vftable';
                                                        v743 = 0;
                                                        v744 = 0;
                                                        *((_QWORD *)v210 + 4) = COptContext::GenDispatcherShowplanXMLSerialized(
                                                                                  (int)v861,
                                                                                  (int)v523,
                                                                                  (int)v613,
                                                                                  (int)v185,
                                                                                  (__int64)v206,
                                                                                  (CFingerprintUtil *)&v741);
                                                        *((_QWORD *)v210 + 6) = v744;
                                                        v595 = 0x20000000BLL;
                                                        if ( (dword_102EDCA0C & 2) != 0 )
                                                        {
                                                          v790 = 0;
                                                          v791 = 1;
                                                          v792 = 0;
                                                          v793 = &v796;
                                                          v794 = &v800;
                                                          v801 = 0;
                                                          v802 = 0;
                                                          v795 = 0;
                                                          v803 = 0;
                                                          v796 = &v804;
                                                          v797 = 17;
                                                          v798 = 0;
                                                          v799 = 0;
                                                          v804 = 0;
                                                          v805 = v185[3];
                                                          v806 = 0;
                                                          v807 = 0;
                                                          XeSqlPkg::parameter_sensitive_plan_optimization::Publish((XeSqlPkg::parameter_sensitive_plan_optimization *)v789);
                                                        }
                                                        v741 = &CRefCount::`vftable';
                                                      }
                                                      if ( v884 < 0 )
                                                      {
                                                        v453 = (int *)*((_QWORD *)a11[20] + 17);
                                                        v454 = *((_QWORD *)v453 + 1);
                                                        v455 = *v453;
                                                        v592 = 0x20000000BLL;
                                                        if ( (dword_102EDCA0C & 2) != 0 )
                                                        {
                                                          v809 = 0;
                                                          v810 = 1;
                                                          v811 = 0;
                                                          v812 = &v815;
                                                          v813 = &v819;
                                                          v820 = 0;
                                                          v821 = 0;
                                                          v814 = 0;
                                                          v822 = 0;
                                                          v815 = &v823;
                                                          v816 = 17;
                                                          v817 = 0;
                                                          v818 = 0;
                                                          v823 = 1;
                                                          v824 = 0;
                                                          v825 = v455;
                                                          v826 = v454;
                                                          XeSqlPkg::parameter_sensitive_plan_optimization::Publish((XeSqlPkg::parameter_sensitive_plan_optimization *)v808);
                                                        }
                                                      }
                                                      if ( v559 )
                                                      {
                                                        v580 = 0;
                                                        for ( n = 0; n < *(_DWORD *)(v559 + 12); v580 = n )
                                                        {
                                                          v457 = *(struct CTelemetryPackage **)(*(_QWORD *)(v559 + 24)
                                                                                              + 8LL * n);
                                                          CTelemetryPackageContainer::PublishTelemetryPackage(
                                                            (CTelemetryPackageContainer *)n,
                                                            v457);
                                                          if ( v457 )
                                                          {
                                                            v458 = (CEncodeJsonUtil *)*((_QWORD *)v457 + 1);
                                                            if ( v458 )
                                                              CEncodeJsonUtil::`scalar deleting destructor'(v458, 1u);
                                                            operator delete(v457, 0x18u);
                                                          }
                                                          ++n;
                                                        }
                                                        v459 = v559;
                                                        v775[11] = v559;
                                                        *(_DWORD *)(v559 + 12) = 0;
                                                        v460 = *(void **)(v459 + 24);
                                                        if ( v460 )
                                                        {
                                                          v461 = *(_DWORD *)(v459 + 16);
                                                          v581 = v461;
                                                          while ( v461 )
                                                            v581 = --v461;
                                                          operator delete[](v460);
                                                          *(_QWORD *)(v459 + 24) = 0;
                                                        }
                                                        *(_DWORD *)(v459 + 16) = 0;
                                                        operator delete((void *)v459, 0x20u);
                                                      }
                                                      v211 = *((_QWORD *)v510 + 8);
                                                      if ( v211 )
                                                      {
                                                        v694 = *((_QWORD *)v510 + 8);
                                                        if ( !*(_QWORD *)(v211 + 24) || !*(_QWORD *)(v211 + 144) )
                                                          *(_BYTE *)(v211 + 704) = 0;
                                                        v462 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v463 = *(_QWORD **)(v462 + 256);
                                                        if ( !v463 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v463 = *(_QWORD **)(v462 + 256);
                                                        }
                                                        if ( v463[107] )
                                                        {
                                                          v467 = __rdtsc();
                                                          v468 = v463[108];
                                                          if ( v467 <= v468 )
                                                            v469 = 0;
                                                          else
                                                            v469 = v467 - v468;
                                                          v464 = v469 + v463[109];
                                                        }
                                                        else
                                                        {
                                                          v464 = 0;
                                                        }
                                                        v465 = v694;
                                                        *(_QWORD *)(v694 + 264) += v464 - *(_QWORD *)(v211 + 24);
                                                        v466 = __rdtsc();
                                                        *(_QWORD *)(v465 + 384) += (((unsigned __int64)HIDWORD(v466) << 32)
                                                                                  | (unsigned int)v466)
                                                                                 - *(_QWORD *)(v465 + 144);
                                                        *(_QWORD *)(v211 + 24) = 0;
                                                        *(_QWORD *)(v465 + 144) = 0;
                                                        ++*(_DWORD *)(v465 + 492);
                                                        v206 = v549;
                                                      }
                                                      (*(void (__fastcall **)(struct IQueryObj *, const struct CStatementDescription *, bool))(*(_QWORD *)v206 + 600LL))(
                                                        v206,
                                                        v614,
                                                        a14);
                                                      v560[7] = 0;
                                                      if ( v516 )
                                                      {
                                                        v470 = v552;
                                                        v552 = 0;
                                                        (*(void (__fastcall **)(struct IQueryObj *, struct CMemoXml *))(*(_QWORD *)v206 + 248LL))(
                                                          v206,
                                                          v470);
                                                      }
                                                      v213 = (const struct CCompExecCtxtStmt *)a11;
                                                      if ( (v871 & 2) != 0 )
                                                      {
                                                        LOBYTE(v212) = 1;
                                                        CExecLvlRepresentation::SetNotCacheable(a11[20], 40, v212);
                                                      }
                                                      COptContext::TrackOptTime(
                                                        (COptContext *)v861,
                                                        v776,
                                                        &v617,
                                                        &v697,
                                                        &v705,
                                                        &v700,
                                                        1);
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 1084) & 8) != 0
                                                        || ((v582 = 0,
                                                             v214 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v214)
                                                         && (v215 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v214 + 56LL)) != 0
                                                          ? (v216 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v215,
                                                                      0x21E3u))
                                                          : (v216 = v582),
                                                            v216) )
                                                      {
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v551,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        v471 = TraceStreamHolder::GetStream((TraceStreamHolder *)v551);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v695,
                                                          v471);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v471 + 16,
                                                          "End of query plan compilation,");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v695);
                                                        v472 = TraceStreamHolder::GetStream((TraceStreamHolder *)v551);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v696,
                                                          v472);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v472 + 16,
                                                          " time: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v696);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v698,
                                                          v472);
                                                        std::ostream::operator<<((char *)v472 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v698);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v699,
                                                          v472);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v472 + 16,
                                                          " net: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v699);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v701,
                                                          v472);
                                                        std::ostream::operator<<((char *)v472 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v701);
                                                        v473 = TraceStreamHolder::GetStream((TraceStreamHolder *)v551);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v702,
                                                          v473);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v473 + 16,
                                                          " total: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v702);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v703,
                                                          v473);
                                                        v217 = v617;
                                                        std::ostream::operator<<((char *)v473 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v703);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v704,
                                                          v473);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v473 + 16,
                                                          " net: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v704);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v706,
                                                          v473);
                                                        std::ostream::operator<<((char *)v473 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v706);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v707,
                                                          v473);
                                                        endl(v473);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v707);
                                                        v474 = TraceStreamHolder::GetStream((TraceStreamHolder *)v551);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v708,
                                                          v474);
                                                        std::ostream::flush((char *)v474 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v708);
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v551);
                                                      }
                                                      else
                                                      {
                                                        v217 = v617;
                                                      }
                                                      v218 = v907;
                                                      ++*(_DWORD *)(v907 + 4);
                                                      *(double *)(v218 + 168) = v217 + *(double *)(v218 + 168);
                                                      v219 = 0;
                                                      v562 = 0;
                                                      v553 = 0;
                                                      v220 = 0;
                                                      if ( (v882 & 1) != 0 )
                                                      {
                                                        v562 = (struct CQNameManager *)*((_QWORD *)v510 + 12);
                                                        v220 = *((_QWORD *)v510 + 13);
                                                        v553 = v220;
                                                        v219 = v887;
                                                        v562 = v887;
                                                      }
                                                      v221 = v914 + v220;
                                                      v710 = v914 + v220;
                                                      if ( v915 < v914 + v220 )
                                                      {
                                                        v222 = 0;
                                                        v553 = 0;
                                                      }
                                                      else
                                                      {
                                                        v222 = v915 - v221;
                                                        v553 = v915 - v221;
                                                      }
                                                      v712 = v222;
                                                      v223 = (__int64)v219 + v916;
                                                      v711 = (__int64)v219 + v916;
                                                      if ( v917 < (unsigned __int64)v219 + v916 )
                                                      {
                                                        v224 = 0;
                                                        v553 = 0;
                                                      }
                                                      else
                                                      {
                                                        v224 = v917 - v223;
                                                        v553 = v917 - v223;
                                                      }
                                                      v713 = v224;
                                                      COptRsrcInfoHelper::SetCompTime(v637, &v712, 0, 0);
                                                      LOBYTE(v225) = 1;
                                                      COptRsrcInfoHelper::SetCompTime(v637, &v713, v226, v225);
                                                      (*(void (__fastcall **)(struct IQueryCompile *, _QWORD *))(*(_QWORD *)v524 + 64LL))(
                                                        v524,
                                                        v637);
                                                      v227 = CExecLvlRepresentation::PmoPph(*(CExecLvlRepresentation **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset) + 160LL));
                                                      v638 = (unsigned __int64)(*((_QWORD *)v227 + 2)
                                                                              * (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v227 + 120LL))(v227)) >> 10;
                                                      v639 = (unsigned __int64)(*((_QWORD *)v507 + 2)
                                                                              * (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v507 + 120LL))(v507)) >> 10;
                                                      (*(void (__fastcall **)(struct IQueryCompile *, unsigned __int64 *))(*(_QWORD *)v524 + 72LL))(
                                                        v524,
                                                        &v638);
                                                      v630 = 0;
                                                      v631 = 0;
                                                      v632 = 0;
                                                      v629 = v894;
                                                      v714 = v895;
                                                      v630 = ToULong((const struct CQODouble *)&v714);
                                                      v715 = v896;
                                                      v631 = ToULongLong((const struct CQODouble *)&v715) >> 10;
                                                      v228 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + SystemThread_TlsIndex)
                                                                                   + SystemThread_TlsOffset
                                                                                   + 8LL)
                                                                       + 80LL);
                                                      if ( v228 && (v229 = *(_QWORD *)(v228 + 8)) != 0 )
                                                        v230 = *(_QWORD *)(v229 + 1344) << 13;
                                                      else
                                                        v230 = 0;
                                                      v632 = v230 / 1024;
                                                      (*(void (__fastcall **)(struct IQueryCompile *, int *))(*(_QWORD *)v524 + 80LL))(
                                                        v524,
                                                        &v629);
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 289) & 8) != 0
                                                        || ((v589 = 0,
                                                             v231 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v231)
                                                         && (v232 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v231 + 56LL)) != 0
                                                          ? (v233 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v232,
                                                                      0x90Bu))
                                                          : (v233 = v589),
                                                            v233) )
                                                      {
                                                        v622 = &g_mutexQOPrint;
                                                        v623 = 0;
                                                        TAutoMutex<SOS_Mutex,1>::GetAccess(&v622, 4194681);
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v608,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        v475 = TraceStreamHolder::GetStream((TraceStreamHolder *)v608);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v716,
                                                          v475);
                                                        endl(v475);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v716);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v717,
                                                          v475);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v475 + 16,
                                                          "Query Compilation completed");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v717);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v718,
                                                          v475);
                                                        endl(v475);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v718);
                                                        OptimizerUtil::PrintQOMemoryUsageInfo();
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v608);
                                                        v476 = v623;
                                                        v477 = v622;
                                                        while ( v476 )
                                                        {
                                                          v477[6] = 0;
                                                          EventAutoInternal<SuspendQueueSLock>::Signal(v477, 0);
                                                          v623 = --v476;
                                                        }
                                                      }
                                                      *((_BYTE *)v510 + 44) &= ~8u;
                                                      CMemo::CollectTelemetry(v888);
                                                      v234 = v549;
                                                      if ( v908 )
                                                        CQoTelemetryAgg::FireCompilationEvent(v908, v549);
                                                      COptContext::TryFireLongCompilationTelemetry(
                                                        (COptContext *)v861,
                                                        1);
                                                      v235 = v902;
                                                      if ( v902 )
                                                      {
                                                        v236 = (*(__int64 (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v234 + 136LL))(v234);
                                                        BatchModeHeuristics::FireHeuristicsXEvent(v235, v236);
                                                      }
                                                      CAutoP<PartitionReducedSourceList>::~CAutoP<PartitionReducedSourceList>(&v564);
                                                      if ( v552 )
                                                        (**(void (__fastcall ***)(struct CMemoXml *, __int64))v552)(
                                                          v552,
                                                          1);
                                                      v237 = (void *)v526;
                                                      v776[1] = v526;
                                                      if ( v526 )
                                                      {
                                                        CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>::~CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>(v526);
                                                        operator delete(v237, 0x20u);
                                                      }
                                                      goto LABEL_1163;
                                                    }
                                                    if ( IsTridentSqlFrontendSession() )
                                                    {
                                                      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v177 + 2)
                                                                                                  + 24LL))(*((_QWORD *)v177 + 2)) == 80 )
                                                      {
LABEL_850:
                                                        v874 &= ~2u;
                                                        goto LABEL_389;
                                                      }
                                                      v572 = 0;
                                                      for ( ii = 0; ii < *((_DWORD *)v177 + 6); v572 = ii )
                                                      {
                                                        if ( COptContext::FContainUqoUnsupportedOperator(*(const struct COptExpr **)(*((_QWORD *)v177 + 4) + 8LL * ii)) )
                                                          goto LABEL_850;
                                                        ++ii;
                                                      }
                                                    }
                                                    if ( (v883 & 0x10) == 0 )
                                                      goto LABEL_389;
                                                    goto LABEL_850;
                                                  }
                                                  catch ( SQLError v598 )
                                                  {
                                                    try
                                                    {
                                                      ExceptionBackout::ExceptionBackout(
                                                        (ExceptionBackout *)v779,
                                                        (const struct SQLError *)v598);
                                                      if ( v599 == 1 )
                                                        v282 = v598[0];
                                                      else
                                                        v282 = LOWORD(v598[0]);
                                                      COptContext::PublishFailedCompilationEvent(
                                                        (COptContext *)v861,
                                                        v282,
                                                        v598[3]);
                                                      CInterleavedExecUtil::CleanUpTvfTablesOnException((const struct CCompExecCtxtStmt *)v561);
                                                      v283 = qword_102ECFB10;
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 289) & 8) == 0 )
                                                      {
                                                        v590 = 0;
                                                        v284 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        if ( *(_QWORD *)v284
                                                          && (v285 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v284 + 56LL)) != 0 )
                                                        {
                                                          v286 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                   v285,
                                                                   0x90Bu);
                                                        }
                                                        else
                                                        {
                                                          v286 = v590;
                                                        }
                                                        if ( !v286 )
                                                          goto LABEL_1068;
                                                        v283 = qword_102ECFB10;
                                                      }
                                                      if ( v598[0] / 100 != 7 || v598[0] != 701 )
                                                        goto LABEL_1069;
                                                      v624 = &g_mutexQOPrint;
                                                      v625 = 0;
                                                      TAutoMutex<SOS_Mutex,1>::GetAccess(&v624, 4194681);
                                                      TraceStreamHolder::TraceStreamHolder(
                                                        (TraceStreamHolder *)&v609,
                                                        (struct SOS_TraceStream *)&g_traceout);
                                                      v287 = TraceStreamHolder::GetStream((TraceStreamHolder *)&v609);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v719,
                                                        v287);
                                                      endl(v287);
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v719);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v720,
                                                        v287);
                                                      std::operator<<<std::char_traits<char>>(
                                                        (char *)v287 + 16,
                                                        "OOM thrown during Query Optimization");
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v720);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v721,
                                                        v287);
                                                      endl(v287);
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v721);
                                                      OptimizerUtil::PrintQOMemoryUsageInfo();
                                                      TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)&v609);
                                                      v288 = v625;
                                                      v289 = v624;
                                                      while ( v288 )
                                                      {
                                                        v289[6] = 0;
                                                        EventAutoInternal<SuspendQueueSLock>::Signal(v289, 0);
                                                        v625 = --v288;
                                                      }
LABEL_1068:
                                                      v283 = qword_102ECFB10;
LABEL_1069:
                                                      if ( (*((_BYTE *)v283 + 324) & 1) != 0
                                                        && (*((_BYTE *)v283 + 1079) & 1) == 0 )
                                                      {
                                                        v575 = 0;
                                                        v290 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        if ( *(_QWORD *)v290
                                                          && (v291 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v290 + 56LL)) != 0 )
                                                        {
                                                          v292 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                   v291,
                                                                   0x21B8u);
                                                        }
                                                        else
                                                        {
                                                          v292 = v575;
                                                        }
                                                        if ( !v292 && v560[7] )
                                                        {
                                                          v293 = v598[0];
                                                          v294 = v598[0] / 100;
                                                          if ( v598[0] / 100 == 29 && v598[0] != 2906 )
                                                            goto LABEL_1098;
                                                          if ( v294 == 36 && v598[0] == 3624 )
                                                            goto LABEL_1098;
                                                          if ( v294 == 36 && v598[0] == 3621 )
                                                            goto LABEL_1098;
                                                          if ( v294 == 86 && v598[0] == 8624 )
                                                            goto LABEL_1098;
                                                          if ( v294 == 7 && v598[0] == 701 )
                                                            goto LABEL_1098;
                                                          v295 = v599 == 1 ? v598[0] : LOWORD(v598[0]);
                                                          if ( v295 == 17065 )
                                                            goto LABEL_1098;
                                                          v296 = v599 == 1 ? v598[0] : LOWORD(v598[0]);
                                                          if ( v296 == 17066 )
                                                            goto LABEL_1098;
                                                          if ( v599 != 1 )
                                                            v293 = LOWORD(v598[0]);
                                                          if ( v293 == 17067 )
LABEL_1098:
                                                            COptContext::PrintExceptionInfo((COptContext *)v861, 1);
                                                        }
                                                      }
                                                      v297 = (CCompTimeTrace *)*((_QWORD *)v510 + 8);
                                                      if ( v297 )
                                                      {
                                                        CCompTimeTrace::HandlePqoBuildExceptionCase(v297);
                                                        v563 = (struct CQNameManager *)*((_QWORD *)v510 + 8);
                                                        if ( !*((_DWORD *)v563 + 175) )
                                                        {
                                                          v298 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset;
                                                          v299 = *(_QWORD **)(v298 + 256);
                                                          if ( !v299 )
                                                          {
                                                            SystemThread::MakeMiniSOSThread(0);
                                                            v299 = *(_QWORD **)(v298 + 256);
                                                          }
                                                          if ( v299[107] )
                                                          {
                                                            v301 = __rdtsc();
                                                            v302 = v299[108];
                                                            if ( v301 <= v302 )
                                                              v303 = 0;
                                                            else
                                                              v303 = v301 - v302;
                                                            v300 = v303 + v299[109];
                                                          }
                                                          else
                                                          {
                                                            v300 = 0;
                                                          }
                                                          v304 = v563;
                                                          *((_QWORD *)v563 + 44) = v300 - *((_QWORD *)v563 + 14);
                                                          *((_QWORD *)v304 + 59) = __rdtsc() - *((_QWORD *)v304 + 29);
                                                          v305 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset;
                                                          v306 = *(_QWORD **)(v305 + 256);
                                                          if ( !v306 )
                                                          {
                                                            SystemThread::MakeMiniSOSThread(0);
                                                            v306 = *(_QWORD **)(v305 + 256);
                                                          }
                                                          if ( v306[107] )
                                                          {
                                                            v308 = __rdtsc();
                                                            v309 = v306[108];
                                                            if ( v308 <= v309 )
                                                              v310 = 0;
                                                            else
                                                              v310 = v308 - v309;
                                                            v307 = v310 + v306[109];
                                                          }
                                                          else
                                                          {
                                                            v307 = 0;
                                                          }
                                                          *((_QWORD *)v304 + 14) = v307;
                                                          *((_QWORD *)v304 + 29) = __rdtsc();
                                                          *((_DWORD *)v563 + 134) = 1;
                                                        }
                                                      }
                                                      v311 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      v312 = *(_QWORD *)(v311 + 256);
                                                      if ( !v312 )
                                                      {
                                                        SystemThread::MakeMiniSOSThread(0);
                                                        v312 = *(_QWORD *)(v311 + 256);
                                                      }
                                                      if ( *(_DWORD *)(*(_QWORD *)(v312 + 600) + 192LL) == 0x100000 )
                                                      {
                                                        v313 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + SystemThread_TlsIndex)
                                                                                     + SystemThread_TlsOffset)
                                                                         + 128LL);
                                                        *(_BYTE *)(v313 + 296) = 0;
                                                        *(_DWORD *)(v313 + 76) &= ~0x2000000u;
                                                        ex_raise(109, 61, 16, 2);
                                                      }
                                                      ExceptionPassOn((const struct SQLError *)v598);
                                                      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v779);
                                                    }
                                                    catch ( ShortStackException )
                                                    {
                                                    }
                                                    v19 = 0;
                                                    v507 = v586;
                                                    v39 = v722;
                                                    v200 = v510;
                                                    v523 = v612;
                                                    v213 = (const struct CCompExecCtxtStmt *)v561;
                                                  }
LABEL_1163:
                                                  v238 = v723;
                                                  if ( !v723 )
                                                  {
                                                    v239 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset;
                                                    v238 = *(struct Worker **)(v239 + 256);
                                                    if ( !v238 )
                                                    {
                                                      SystemThread::MakeMiniSOSThread(0);
                                                      v238 = *(struct Worker **)(v239 + 256);
                                                    }
                                                  }
                                                  if ( *((_DWORD *)v238 + 139) )
                                                    ExceptionPostCatchActions(v238);
                                                  goto LABEL_464;
                                                }
                                                v521 = 0;
                                                v158 = (v878 >= 130 || (v157 & 0x10) != 0) && (v879 & 1) != 0;
                                                v518[0] = v158;
                                                v159 = v878 >= 130 || (v157 & 0x10) != 0;
                                                v518[1] = v159;
                                                v519 = 0;
                                                v520 = 0;
                                                OptimizerUtil::FindNode<CDetermineBatchModeEligibility>(v143, v518);
                                                if ( v520 )
                                                  v875 |= 0x40u;
                                                v160 = v610;
                                                v161 = v610 && (unsigned __int8)QueryHints::FHintSet(v610, 21);
                                                if ( !v519 && (*((_BYTE *)qword_102ECFB10 + 1643) & 2) == 0 )
                                                {
                                                  v162 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + SystemThread_TlsIndex)
                                                                   + SystemThread_TlsOffset);
                                                  if ( !v162
                                                    || (v163 = **(struct CSessionTraceFlags ***)(v162 + 56)) == 0
                                                    || !CSessionTraceFlags::CheckSessionTraceInternal(v163, 0x3359u) )
                                                  {
                                                    v143 = v508;
LABEL_327:
                                                    CExecLvlRepresentation::FInternal(v510);
                                                    v164 = v878 >= 150
                                                        || (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 81);
                                                    if ( v164
                                                      && (unsigned __int8)CQOFeatureSwitches::FIsSet(v867, 82)
                                                      && v315
                                                      && v314 )
                                                    {
                                                      v881 |= 0x20u;
                                                    }
                                                    v165 = (v875 & 8) == 0 && (v881 & 0x20) != 0 && (v874 & 8) != 0;
                                                    v166 = CQOFeatureSwitches::FIsSet(v867, 83);
                                                    if ( (v165 || v166) && v167 )
                                                    {
                                                      v168 = v160 && (unsigned __int8)QueryHints::FHintSet(v160, 23);
                                                      if ( !v168 && v165 && v889 )
                                                        v168 = FindNode<CDetermineBatchModePlanHint>(&v533) != 0;
                                                      COptContext::ActivateBatchModeHeuristics(
                                                        (COptContext *)v861,
                                                        v165,
                                                        v168);
                                                    }
                                                    v148 = v510;
                                                    goto LABEL_344;
                                                  }
                                                  v143 = v508;
                                                }
                                                if ( !v161 )
                                                {
                                                  v875 |= 0x2Cu;
                                                  if ( !COptContext::FNoMinimumDistanceGuarantee((COptContext *)v861) )
                                                    *((_BYTE *)v888 + 75) = 1;
                                                }
                                                goto LABEL_327;
                                              }
LABEL_185:
                                              if ( !*(_BYTE *)(v865 + 31) )
                                                goto LABEL_186;
                                              goto LABEL_648;
                                            }
                                            if ( !*(_BYTE *)(v865 + 30) )
                                              v882 |= 0x20u;
                                          }
                                          if ( !v65 )
                                            goto LABEL_185;
                                          goto LABEL_184;
                                        }
                                      }
LABEL_535:
                                      v881 |= 0x40u;
                                      goto LABEL_167;
                                    }
                                  }
LABEL_645:
                                  v880 |= 0x40u;
                                  goto LABEL_161;
                                }
LABEL_156:
                                if ( (unsigned __int8)QueryHints::FHintSet(v65, 11) )
                                  goto LABEL_645;
                                goto LABEL_157;
                              }
                            }
LABEL_533:
                            v880 |= 0x20u;
                            goto LABEL_150;
                          }
LABEL_143:
                          v880 |= 0x10u;
                          goto LABEL_144;
                        }
                        v674 = *v251;
                        if ( !CSessionTraceFlags::CheckSessionTraceInternal(v252, 0x26D3u) )
                          goto LABEL_493;
                      }
                    }
                    v102 = 1;
                    goto LABEL_134;
                  }
                  v673 = *v99;
                  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v100, 0x102Au) )
                    goto LABEL_128;
                }
              }
              v879 |= 0x80u;
              goto LABEL_128;
            }
            v734 = 0;
            v247 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( *(_QWORD *)v247
              && (v248 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v247 + 56LL), (v249 = *v248) != 0) )
            {
              v669 = *v248;
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v249, 0x2754u) )
                goto LABEL_483;
            }
            else
            {
              v669 = 0;
            }
            v735 = 2418;
            v542 = *((_BYTE *)qword_102ECFB10 + 302) >> 2;
            if ( (v542 & 1) == 0 )
            {
              v736 = 0;
              v332 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset);
              if ( !v332 || (v333 = *(struct CSessionTraceFlags ***)(v332 + 56), (v334 = *v333) == 0) )
              {
                v670 = 0;
LABEL_96:
                v89 = v874 | 8;
                v874 |= 8u;
                goto LABEL_97;
              }
              v670 = *v333;
              if ( !CSessionTraceFlags::CheckSessionTraceInternal(v334, 0x972u) )
              {
                v89 = v874 | 8;
                v874 |= 8u;
                goto LABEL_97;
              }
            }
LABEL_483:
            v89 = v874;
            goto LABEL_97;
          }
          v668 = *v87;
          if ( !CSessionTraceFlags::CheckSessionTraceInternal(v88, 0x24AEu) )
            goto LABEL_94;
        }
        v876 |= 8u;
        goto LABEL_94;
      }
LABEL_611:
      v879 |= 2u;
      goto LABEL_89;
    }
LABEL_589:
    v73 = 1;
    goto LABEL_59;
  }
  catch ( SQLError v746 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v780, (const struct SQLError *)v746);
      CInterleavedExecUtil::CleanUpTvfTablesOnException((const struct CCompExecCtxtStmt *)v561);
      v266 = v746[0] / 100 == 29 && v746[0] == 2906;
      v506 = v266;
      *((_BYTE *)v510 + 44) &= ~8u;
      if ( v746[0] / 100 != 29 && v524 )
        (**(void (__fastcall ***)(struct IQueryCompile *, __int64))v524)(v524, 1);
      v267 = v586;
      if ( v586 )
      {
        (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v586 + 240LL))(v586);
        (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v267 + 16LL))(v267);
      }
      v268 = (CCompTimeTrace *)*((_QWORD *)v510 + 8);
      if ( v268 )
      {
        CCompTimeTrace::HandlePqoBuildExceptionCase(v268);
        v556 = (struct CEsCompGroup *)*((_QWORD *)v510 + 8);
        if ( !*((_DWORD *)v556 + 175) )
        {
          v269 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v270 = *(_QWORD **)(v269 + 256);
          if ( !v270 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v270 = *(_QWORD **)(v269 + 256);
          }
          if ( v270[107] )
          {
            v272 = __rdtsc();
            v273 = v270[108];
            if ( v272 <= v273 )
              v274 = 0;
            else
              v274 = v272 - v273;
            v271 = v274 + v270[109];
          }
          else
          {
            v271 = 0;
          }
          v275 = v556;
          *((_QWORD *)v556 + 44) = v271 - *((_QWORD *)v556 + 14);
          *((_QWORD *)v275 + 59) = __rdtsc() - *((_QWORD *)v275 + 29);
          v276 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v277 = *(_QWORD **)(v276 + 256);
          if ( !v277 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v277 = *(_QWORD **)(v276 + 256);
          }
          if ( v277[107] )
          {
            v279 = __rdtsc();
            v280 = v277[108];
            if ( v279 <= v280 )
              v281 = 0;
            else
              v281 = v279 - v280;
            v278 = v281 + v277[109];
          }
          else
          {
            v278 = 0;
          }
          *((_QWORD *)v275 + 14) = v278;
          *((_QWORD *)v275 + 29) = __rdtsc();
          *((_DWORD *)v556 + 134) = 1;
          v266 = v506;
        }
      }
      if ( !v266 )
        ExceptionPassOn((const struct SQLError *)v746);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v780);
    }
    catch ( ShortStackException )
    {
    }
    v19 = 0;
    v240 = v586;
    v200 = v510;
    v241 = v612;
    v213 = (const struct CCompExecCtxtStmt *)v561;
    goto LABEL_468;
  }
LABEL_1158:
  v240 = v507;
  v241 = v523;
LABEL_468:
  v242 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v243 = *(struct Worker **)(v242 + 256);
  if ( !v243 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v243 = *(struct Worker **)(v242 + 256);
  }
  if ( *((_DWORD *)v243 + 139) )
    ExceptionPostCatchActions(v243);
  if ( v506 )
  {
    v478 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v479 = *(_QWORD *)(v478 + 256);
    if ( !v479 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v479 = *(_QWORD *)(v478 + 256);
    }
    *(_DWORD *)(v479 + 800) &= ~0x20u;
    ex_raise(86, 21, 17, 1);
  }
  (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v240 + 16LL))(v240);
  g_CRV_QOptconsiderlow = 0;
  v244 = (__int64 *)*((_QWORD *)v200 + 8);
  if ( v244 )
  {
    v480 = *v244;
    if ( !*v244 || !v244[15] )
      *((_BYTE *)v244 + 704) = 0;
    v481 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v482 = *(_QWORD **)(v481 + 256);
    if ( !v482 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v482 = *(_QWORD **)(v481 + 256);
      v480 = *v244;
    }
    if ( v482[107] )
    {
      v485 = __rdtsc();
      v486 = v482[108];
      if ( v485 <= v486 )
        v487 = 0;
      else
        v487 = v485 - v486;
      v483 = v487 + v482[109];
    }
    else
    {
      v483 = 0;
    }
    v244[30] += v483 - v480;
    v484 = __rdtsc();
    v244[45] += (((unsigned __int64)HIDWORD(v484) << 32) | (unsigned int)v484) - v244[15];
    *v244 = 0;
    v244[15] = 0;
    ++*((_DWORD *)v244 + 120);
  }
  v245 = *((_QWORD *)v200 + 8);
  if ( v245 && !*(_DWORD *)(v245 + 700) )
  {
    v488 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v489 = *(_QWORD **)(v488 + 256);
    if ( !v489 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v489 = *(_QWORD **)(v488 + 256);
    }
    if ( v489[107] )
    {
      v496 = __rdtsc();
      v497 = v489[108];
      if ( v496 <= v497 )
        v498 = 0;
      else
        v498 = v496 - v497;
      v490 = v498 + v489[109];
    }
    else
    {
      v490 = 0;
    }
    *(_QWORD *)(v245 + 352) = v490 - *(_QWORD *)(v245 + 112);
    *(_QWORD *)(v245 + 472) = __rdtsc() - *(_QWORD *)(v245 + 232);
    v491 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v492 = *(_QWORD **)(v491 + 256);
    if ( !v492 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v492 = *(_QWORD **)(v491 + 256);
    }
    if ( v492[107] )
    {
      v493 = __rdtsc();
      v494 = v492[108];
      if ( v493 <= v494 )
        v495 = 0;
      else
        v495 = v493 - v494;
      v19 = v495 + v492[109];
    }
    *(_QWORD *)(v245 + 112) = v19;
    *(_QWORD *)(v245 + 232) = __rdtsc();
    *(_DWORD *)(v245 + 536) = 1;
  }
  PublishQPQualityTelemetryPackage(v241, v213, v524);
  CAutoP<CAutoSessionTraceFlagOrQORuleToggler>::~CAutoP<CAutoSessionTraceFlagOrQORuleToggler>(&v725);
  return v549;
}

```

## disassembly

```asm
0x100490dc0  push    rbx
0x100490dc2  push    rsi
0x100490dc3  push    rdi
0x100490dc4  push    r12
0x100490dc6  push    r13
0x100490dc8  push    r14
0x100490dca  push    r15
0x100490dcc  mov     eax, 1990h
0x100490dd1  call    _alloca_probe
0x100490dd6  sub     rsp, rax
0x100490dd9  mov     [rsp+19C8h+var_1268], 0FFFFFFFFFFFFFFFEh
0x100490de5  movaps  [rsp+19C8h+var_48], xmm6
0x100490ded  mov     rax, cs:__security_cookie
0x100490df4  xor     rax, rsp
0x100490df7  mov     [rsp+19C8h+var_58], rax
0x100490dff  jmp     loc_10046EFC2
0x10046b767  mov     eax, esi
0x10046b769  jmp     loc_10047105B
0x10046efc2  mov     rax, r8
0x10046efc5  mov     [rsp+19C8h+var_18F0], rax
0x10046efcd  mov     [rsp+19C8h+var_1868], rdx
0x10046efd5  mov     r13, rcx
0x10046efd8  mov     [rsp+19C8h+var_18A8], rcx
0x10046efe0  mov     [rsp+19C8h+var_16C8], rax
0x10046efe8  mov     rax, [rsp+19C8h+arg_20]
0x10046eff0  mov     [rsp+19C8h+var_18D0], rax
0x10046eff8  mov     eax, [rsp+19C8h+arg_28]
0x10046efff  mov     [rsp+19C8h+var_18BC], eax
0x10046f006  mov     r12, [rsp+19C8h+arg_30]
0x10046f00e  movsxd  r14, dword ptr [rsp+19C8h+arg_38]
0x10046f016  mov     eax, dword ptr [rsp+19C8h+arg_48]
0x10046f01d  mov     [rsp+19C8h+var_1918], eax
0x10046f024  mov     rax, [rsp+19C8h+arg_50]
0x10046f02c  mov     [rsp+19C8h+var_1930], rax
0x10046f034  mov     [rsp+19C8h+var_1840], rax
0x10046f03c  mov     r15, [rsp+19C8h+arg_58]
0x10046f044  mov     rax, [rsp+19C8h+arg_60]
0x10046f04c  mov     [rsp+19C8h+var_16B8], rax
0x10046f054  call    cs:__imp__statusfp
0x10046f05a  mov     ebx, eax
0x10046f05c  test    al, 1Ch
0x10046f05e  jz      short loc_10046F06F
0x10046f060  call    cs:__imp__clearfp
0x10046f066  test    bl, 10h
0x10046f069  jnz     loc_1018DEB78
0x10046f06f  mov     edx, 8031Fh; Mask
0x10046f074  mov     ecx, 9001Fh; NewValue
0x10046f079  call    cs:__imp__controlfp
0x10046f07f  xor     esi, esi
0x10046f081  mov     [rsp+19C8h+var_18A0], rsi
0x10046f089  test    r14d, r14d
0x10046f08c  jz      loc_1004C0103
0x10046f092  mov     rdi, r14
0x10046f095  shr     rdi, 1
0x10046f098  jmp     short loc_10046F09B
0x10046f09b  lea     rbx, aAdhoc_0; "Adhoc"
0x10046f0a2  test    r14d, r14d
0x10046f0a5  cmovnz  rbx, r12
0x10046f0a9  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10046f0af  mov     [rsp+19C8h+var_1998], rbx
0x10046f0b4  mov     dword ptr [rsp+19C8h+var_19A0], edi
0x10046f0b8  mov     [rsp+19C8h+Locale], rax; Locale
0x10046f0bd  lea     r9, aQueryoptimizer; "QueryOptimizer_%.*ls"
0x10046f0c4  mov     edx, 0FFh; BufferCount
0x10046f0c9  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x10046f0d0  lea     rcx, [rsp+19C8h+Buffer]; Buffer
0x10046f0d8  call    _snprintf_s_l
0x10046f0dd  mov     [rsp+19C8h+var_59], sil
0x10046f0e5  mov     rdx, gs:58h
0x10046f0ee  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10046f0f5  mov     ecx, [rax]
0x10046f0f7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10046f0fe  mov     ebx, [rax]
0x10046f100  add     rbx, [rdx+rcx*8]
0x10046f104  mov     rax, [rbx+100h]
0x10046f10b  test    rax, rax
0x10046f10e  jz      loc_1018DEB85
0x10046f114  mov     rbx, [rax+3E0h]
0x10046f11b  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10046f121  mov     rcx, rax
0x10046f124  movzx   edx, word ptr [rbx+0A0h]
0x10046f12b  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10046f131  mov     rbx, rax
0x10046f134  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10046f13a  mov     rax, [rbx+40h]
0x10046f13e  mov     ecx, 160h
0x10046f143  mov     r9d, 8
0x10046f149  lea     r8, [rax+40h]
0x10046f14d  test    rax, rax
0x10046f150  cmovz   r8, rsi
0x10046f154  mov     word ptr [rsp+19C8h+Locale], cx
0x10046f159  xor     edx, edx
0x10046f15b  lea     ecx, [rdx+6Bh]
0x10046f15e  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x10046f164  mov     r14, rax
0x10046f167  mov     [rsp+19C8h+var_1928], rax
0x10046f16f  test    rax, rax
0x10046f172  jz      loc_1018DEB9A
0x10046f178  mov     rax, [r14]
0x10046f17b  mov     rcx, r14
0x10046f17e  call    qword ptr [rax+0B0h]
0x10046f184  test    rax, rax
0x10046f187  jnz     loc_1018DEBA8
0x10046f18d  mov     rax, [r14]
0x10046f190  mov     rcx, r14
0x10046f193  call    qword ptr [rax+0F0h]
0x10046f199  mov     [rsp+19C8h+var_1798], r14
0x10046f1a1  mov     rdi, [r13+10h]
0x10046f1a5  mov     [rsp+19C8h+var_1370], rdi
0x10046f1ad  mov     r13, [rdi+38h]
0x10046f1b1  mov     [rsp+19C8h+var_16D8], r13
0x10046f1b9  mov     rdx, r13; struct QueryHints *
0x10046f1bc  mov     rcx, r14; struct IMemObj *
0x10046f1bf  call    ?CaptureQueryHints@@YAPEAVCQOQueryHints@@PEAVIMemObj@@PEBUQueryHints@@@Z; CaptureQueryHints(IMemObj *,QueryHints const *)
0x10046f1c4  mov     rcx, rax
0x10046f1c7  mov     [rsp+19C8h+var_1788], rax
0x10046f1cf  mov     r9, [rsp+19C8h+var_1930]
0x10046f1d7  cmp     [r9], sil
0x10046f1da  jnz     loc_1018DEBC0
0x10046f1e0  mov     r8, r9
0x10046f1e3  lea     rdx, [rsp+19C8h+var_1768]
0x10046f1eb  mov     rcx, [r9+80h]
0x10046f1f2  call    ?GetCurCompatLevel@CExecLvlIntCtxt@@AEBA?AVCCompatLevel@@VContextHandle@@@Z; CExecLvlIntCtxt::GetCurCompatLevel(ContextHandle)
0x10046f1f7  mov     r8d, [rsp+19C8h+var_1768]
0x10046f1ff  mov     rcx, [rsp+19C8h+var_1788]
0x10046f207  mov     r9, [rsp+19C8h+var_1930]
0x10046f20f  mov     [rsp+19C8h+var_18F4], r8d
0x10046f217  test    r15, r15
0x10046f21a  jnz     loc_1018DEBCA
0x10046f220  mov     [rsp+19C8h+var_18E8], rsi
0x10046f228  mov     [rsp+19C8h+var_17A8], rsi
0x10046f230  mov     [rsp+19C8h+var_1937], sil
0x10046f238  mov     [rsp+19C8h+var_1608], rsi
0x10046f240  mov     [rsp+19C8h+var_1600], rsi
0x10046f248  mov     [rsp+19C8h+var_15F8], rsi
0x10046f250  mov     [rsp+19C8h+var_15F0], rsi
0x10046f258  mov     [rsp+19C8h+var_15E8], rsi
0x10046f260  mov     [rsp+19C8h+var_15E0], rsi
0x10046f268  mov     rbx, [r9+0A0h]
0x10046f26f  mov     [rsp+19C8h+var_1910], rbx
0x10046f277  test    r13, r13
0x10046f27a  jz      loc_1018DEC1A
0x10046f280  mov     rdx, gs:58h
0x10046f289  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10046f290  mov     ecx, [rax]
0x10046f292  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10046f299  mov     ebx, [rax]
0x10046f29b  add     rbx, [rdx+rcx*8]
0x10046f29f  mov     rcx, [rbx+100h]
0x10046f2a6  test    rcx, rcx
0x10046f2a9  jz      loc_1018DEC07
0x10046f2af  mov     r9b, 1; bool
0x10046f2b2  movzx   r8d, r9b; bool
0x10046f2b6  mov     rdx, [r13+30h]; struct QueryTraceAndRuleHints *
0x10046f2ba  mov     rcx, [rcx+3E8h]; struct IMemObj *
0x10046f2c1  call    ?CreateAndActivate@CAutoSessionTraceFlagOrQORuleToggler@@SAPEAV1@PEAVIMemObj@@PEAUQueryTraceAndRuleHints@@_N2@Z; CAutoSessionTraceFlagOrQORuleToggler::CreateAndActivate(IMemObj *,QueryTraceAndRuleHints *,bool,bool)
0x10046f2c6  mov     rbx, [rsp+19C8h+var_1910]
0x10046f2ce  jmp     short loc_10046F2D1
0x10046f2d1  mov     [rsp+19C8h+var_1358], rax
0x10046f2d9  mov     edx, 1Dh; unsigned __int16
0x10046f2de  mov     [rsp+19C8h+var_19A0], rsi; struct Worker *
0x10046f2e3  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x10046f2ea  mov     [rsp+19C8h+Locale], rax; int (*)(int, int, int, int, char *)
0x10046f2ef  xor     r9d, r9d; unsigned __int8
0x10046f2f2  mov     r8b, 6; unsigned __int8
0x10046f2f5  lea     rcx, [rsp+19C8h+var_10A0]; this
0x10046f2fd  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10046f302  nop
0x10046f303  or      byte ptr [rbx+2Ch], 8
0x10046f307  mov     ebx, 1
0x10046f30c  mov     edx, ebx
0x10046f30e  lea     ecx, [rbx+7]
0x10046f311  call    ?GetMemoryClerk@@YAPEAVMemoryClerk@@W4SOSHOST_MEMORYCLERK_TYPE@@W4SOS_CallerType@@@Z; GetMemoryClerk(SOSHOST_MEMORYCLERK_TYPE,SOS_CallerType)
0x10046f316  test    rax, rax
0x10046f319  lea     r8, [rax+40h]
0x10046f31d  jz      loc_1018DEC23
0x10046f323  mov     eax, 80h
0x10046f328  lea     r9d, [rax-78h]
0x10046f32c  mov     word ptr [rsp+19C8h+Locale], ax
0x10046f331  mov     edx, ebx
0x10046f333  lea     ecx, [rax-21h]
0x10046f336  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x10046f33c  mov     r15, rax
0x10046f33f  test    rax, rax
0x10046f342  jz      loc_1018DEC2C
0x10046f348  mov     [rsp+19C8h+var_16C0], r15
0x10046f350  mov     [rsp+19C8h+var_14C8], 8ABh
0x10046f35b  mov     byte ptr [rsp+19C8h+Locale], bl
0x10046f35f  mov     r9d, 8ABh
0x10046f365  lea     r8, aSqlNtdbmsQuery_17; "sql\\ntdbms\\query\\qoin\\pqobuild.cpp"
0x10046f36c  mov     rdx, r14
0x10046f36f  mov     ecx, 20h ; ' '
0x10046f374  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10046f37a  mov     [rsp+19C8h+var_1148], rax
0x10046f382  test    rax, rax
0x10046f385  jz      loc_1018DEC3A
0x10046f38b  mov     rdx, r14; struct IMemObj *
0x10046f38e  mov     rcx, rax; this
0x10046f391  call    ??0CValRefTracker@@QEAA@PEAVIMemObj@@@Z; CValRefTracker::CValRefTracker(IMemObj *)
0x10046f396  mov     rbx, rax
0x10046f399  jmp     short loc_10046F39C
0x10046f39c  mov     [rsp+19C8h+var_1548], rbx
0x10046f3a4  mov     [rsp+19C8h+var_10F8], rbx
0x10046f3ac  mov     [rsp+19C8h+var_1478], 8ACh
0x10046f3b7  mov     byte ptr [rsp+19C8h+Locale], 1
0x10046f3bc  mov     r9d, 8ACh
0x10046f3c2  lea     r8, aSqlNtdbmsQuery_17; "sql\\ntdbms\\query\\qoin\\pqobuild.cpp"
0x10046f3c9  mov     r12, [rsp+19C8h+var_18F0]
0x10046f3d1  mov     rdx, r12
0x10046f3d4  mov     ecx, 30h ; '0'
0x10046f3d9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10046f3df  mov     [rsp+19C8h+var_10E8], rax
0x10046f3e7  test    rax, rax
0x10046f3ea  jz      loc_1018DEC43
0x10046f3f0  mov     r8, rbx
0x10046f3f3  mov     rdx, r12
0x10046f3f6  mov     rcx, rax
0x10046f3f9  call    cs:__imp_??0CVRTableComp@@QEAA@PEAVIMemObj@@PEAVIValRefTracker@@@Z; CVRTableComp::CVRTableComp(IMemObj *,IValRefTracker *)
0x10046f3ff  mov     r13, rax
0x10046f402  jmp     short loc_10046F405
0x10046f405  mov     [rsp+19C8h+var_10E0], r13
0x10046f40d  mov     [rsp+19C8h+var_1474], 8ADh
0x10046f418  mov     byte ptr [rsp+19C8h+Locale], 1
0x10046f41d  mov     r9d, 8ADh
0x10046f423  lea     r8, aSqlNtdbmsQuery_17; "sql\\ntdbms\\query\\qoin\\pqobuild.cpp"
0x10046f42a  mov     rdx, r14
0x10046f42d  mov     ecx, 30h ; '0'
0x10046f432  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10046f438  mov     [rsp+19C8h+var_10D0], rax
0x10046f440  test    rax, rax
0x10046f443  jz      loc_1018DEC4C
0x10046f449  mov     r8, rbx; struct IValRefTracker *
0x10046f44c  mov     rdx, r14; struct IMemObj *
0x10046f44f  mov     rcx, rax; this
0x10046f452  call    ??0CVRTableOpt@@QEAA@PEAVIMemObj@@PEAVIValRefTracker@@@Z; CVRTableOpt::CVRTableOpt(IMemObj *,IValRefTracker *)
0x10046f457  mov     r12, rax
0x10046f45a  jmp     short loc_10046F45D
0x10046f45d  mov     [rsp+19C8h+var_1698], r12
0x10046f465  mov     rcx, r15
0x10046f468  call    cs:__imp_?CreateCQNameManager@@YAPEAVCQNameManager@@PEAVIMemObj@@@Z; CreateCQNameManager(IMemObj *)
0x10046f46e  mov     rbx, rax
0x10046f471  mov     [rsp+19C8h+var_1830], rax
0x10046f479  mov     rcx, [rsp+19C8h+var_18F0]
0x10046f481  call    cs:__imp_?CreateCQNameManager@@YAPEAVCQNameManager@@PEAVIMemObj@@@Z; CreateCQNameManager(IMemObj *)
0x10046f487  mov     [rsp+19C8h+var_1838], rax
0x10046f48f  mov     edx, 0C2h
0x10046f494  movsx   ecx, [rsp+19C8h+arg_40]
0x10046f49c  lea     r14d, [rdx+1]
0x10046f4a0  cmp     cx, dx
0x10046f4a3  jz      loc_1018DEC55
0x10046f4a9  mov     r8, [rsp+19C8h+var_1930]
0x10046f4b1  mov     [rsp+19C8h+var_1698], r8
0x10046f4b9  mov     rdx, [rsp+19C8h+var_1868]
0x10046f4c1  mov     [rsp+19C8h+var_1978], rdx
0x10046f4c6  mov     [rsp+19C8h+var_1980], rax
0x10046f4cb  mov     [rsp+19C8h+var_1988], rbx
0x10046f4d0  mov     [rsp+19C8h+var_1990], r12
0x10046f4d5  mov     [rsp+19C8h+var_1998], r13
0x10046f4da  mov     rax, [rsp+19C8h+var_18D0]
0x10046f4e2  mov     [rsp+19C8h+var_19A0], rax
0x10046f4e7  mov     [rsp+19C8h+Locale], r8
0x10046f4ec  mov     r9d, [rsp+19C8h+var_1918]
0x10046f4f4  movzx   r8d, cx
0x10046f4f8  mov     rdx, r15
0x10046f4fb  mov     rcx, [rsp+19C8h+var_18F0]
0x10046f503  call    cs:__imp_?CreateIQueryCompile@@YAPEAVIQueryCompile@@PEAVIMemObj@@0FHVContextHandle@@PEAVCEnvCollection@@PEAVCVRTable@@3PEAVCQNameManager@@4PEAVCEsCompGroup@@@Z; CreateIQueryCompile(IMemObj *,IMemObj *,short,int,ContextHandle,CEnvCollection *,CVRTable *,CVRTable *,CQNameManager *,CQNameManager *,CEsCompGroup *)
0x10046f509  mov     rbx, rax
0x10046f50c  mov     [rsp+19C8h+var_18E8], rax
0x10046f514  mov     rax, [rsp+19C8h+var_1930]
0x10046f51c  mov     [rsp+19C8h+var_1698], rax
0x10046f524  call    ?GetCurrentDb@ContextAccessor@@YAGVContextHandle@@@Z; ContextAccessor::GetCurrentDb(ContextHandle)
0x10046f529  movzx   ecx, ax; unsigned int
0x10046f52c  mov     [rsp+19C8h+var_1918], ecx
0x10046f533  call    ?FSystemDBId@@YA_NK@Z; FSystemDBId(ulong)
0x10046f538  test    al, al
0x10046f53a  jnz     loc_1005359D9
0x10046f540  mov     rcx, [rsp+19C8h+var_1910]; this
0x10046f548  call    ?FInternal@CExecLvlRepresentation@@QEBA_NXZ; CExecLvlRepresentation::FInternal(void)
0x10046f54d  test    al, al
0x10046f54f  jnz     loc_1005359D9
0x10046f555  mov     [rsp+19C8h+var_1938], 1
0x10046f55d  mov     rax, [rbx]
0x10046f560  mov     rcx, rbx
0x10046f563  call    qword ptr [rax+160h]
0x10046f569  mov     rax, [rbx]
0x10046f56c  mov     rcx, rbx
0x10046f56f  call    qword ptr [rax+180h]
0x10046f575  mov     [rsp+19C8h+var_17A8], rax
0x10046f57d  jmp     short loc_10046F580
0x10046f580  mov     rcx, rbx
0x10046f583  call    cs:__imp_?CreateXteBuilderObject@@YAPEAVIXteBuilder@@PEAVIQueryCompile@@@Z; CreateXteBuilderObject(IQueryCompile *)
0x10046f589  mov     [rsp+19C8h+var_17A0], rax
0x10046f591  mov     [rsp+19C8h+var_1468], 8D6h
0x10046f59c  mov     byte ptr [rsp+19C8h+Locale], 1
0x10046f5a1  mov     r9d, 8D6h
0x10046f5a7  lea     r8, aSqlNtdbmsQuery_17; "sql\\ntdbms\\query\\qoin\\pqobuild.cpp"
0x10046f5ae  mov     rdx, r15
0x10046f5b1  mov     ecx, 70h ; 'p'
0x10046f5b6  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10046f5bc  mov     [rsp+19C8h+var_1150], rax
  ... truncated ...
```
