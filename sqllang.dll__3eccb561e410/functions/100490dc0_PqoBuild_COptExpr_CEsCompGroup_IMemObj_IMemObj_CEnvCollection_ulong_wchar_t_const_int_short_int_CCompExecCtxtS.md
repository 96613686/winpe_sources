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
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  __int64 v27; // rcx
  struct IMemObj *MemObject; // r14
  CMallocSpy *v29; // rax
  __int64 v30; // rdi
  struct QueryTraceAndRuleHints **v31; // r13
  struct CQOQueryHints *Hints; // rcx
  CExecLvlRepresentation **v33; // r9
  __int64 v34; // r8
  CExecLvlRepresentation *v35; // rbx
  __int64 v36; // rbx
  __int64 v37; // rcx
  struct CAutoSessionTraceFlagOrQORuleToggler *v38; // rax
  __int64 v39; // rcx
  struct IMemObj *v40; // r15
  CValRefTracker *v41; // rax
  struct IValRefTracker *v42; // rbx
  CVRTableComp *v43; // rax
  CVRTableComp *v44; // r13
  CVRTableOpt *v45; // rax
  CVRTableOpt *v46; // r12
  struct CQNameManager *CQNameManager; // rbx
  struct CQNameManager *v48; // rax
  unsigned __int16 v49; // cx
  unsigned __int16 v50; // r14
  struct IQueryCompile *IQueryCompile; // rbx
  struct IMemObj **v52; // rax
  __int64 v53; // rax
  struct QueryHints *v54; // r14
  int OptimizerCompatLevel; // eax
  __int64 v56; // r8
  struct CSessionTraceFlags **v57; // rax
  struct CSessionTraceFlags *v58; // rcx
  CExecLvlRepresentation *v59; // rcx
  unsigned __int8 v60; // al
  char v61; // al
  char v62; // al
  __int64 v63; // rbx
  struct IMemObj *v64; // rax
  struct CQOQueryHints *v65; // r13
  char v66; // r9
  struct DbccThreadContext *Context; // rax
  int v68; // r9d
  int v69; // r9d
  char v70; // al
  char v71; // dl
  __int64 v72; // rax
  struct CSessionTraceFlags **v73; // rax
  struct CSessionTraceFlags *v74; // rcx
  __int64 v75; // rax
  struct CSessionTraceFlags **v76; // rax
  struct CSessionTraceFlags *v77; // rcx
  char v78; // dl
  __int64 v79; // rax
  struct CSessionTraceFlags **v80; // rax
  struct CSessionTraceFlags *v81; // rcx
  __int64 v82; // r8
  COptContext *v83; // rcx
  __int64 v84; // rax
  struct CSessionTraceFlags **v85; // rax
  struct CSessionTraceFlags *v86; // rcx
  __int64 v87; // rax
  struct CSessionTraceFlags **v88; // rax
  struct CSessionTraceFlags *v89; // rcx
  char v90; // al
  char v91; // al
  __int64 v92; // r8
  struct CSessionTraceFlags **v93; // rax
  struct CSessionTraceFlags *v94; // rcx
  __int64 v95; // rax
  struct CSessionTraceFlags **v96; // rax
  struct CSessionTraceFlags *v97; // rcx
  __int64 v98; // r8
  struct CSessionTraceFlags **v99; // rax
  struct CSessionTraceFlags *v100; // rcx
  __int64 v101; // rax
  struct CSessionTraceFlags **v102; // rax
  struct CSessionTraceFlags *v103; // rcx
  CExecLvlRepresentation *v104; // rcx
  unsigned __int8 v105; // al
  __int64 v106; // rcx
  __int64 v107; // rdx
  struct IQueryCompile *v108; // rbx
  __int64 v109; // r8
  unsigned __int64 v110; // rcx
  struct CSessionTraceFlags *v111; // rax
  unsigned __int64 v112; // rcx
  struct CSessionTraceFlags *v113; // rax
  __int64 v114; // r8
  CExecLvlRepresentation *v115; // rax
  __int64 v116; // r8
  char v117; // cl
  int v118; // eax
  bool v119; // zf
  int v120; // ecx
  char v121; // dl
  char v122; // cl
  bool v123; // dl
  bool v124; // al
  __int64 v125; // rcx
  unsigned int v126; // r15d
  __int64 v127; // rbx
  unsigned __int16 v128; // ax
  __int64 v129; // rbx
  struct COptInterfaces *v130; // r13
  struct COptExpr *v131; // r14
  char v132; // al
  struct IMemObj *v133; // rbx
  CMATGen *v134; // r15
  char v135; // ecx^2
  CExecLvlRepresentation *v136; // r13
  __int64 v137; // rbx
  __int64 v138; // rbx
  __int64 v139; // rbx
  bool v140; // r15
  bool v141; // r12
  char v142; // r9
  __int64 v143; // rcx
  char v144; // r11
  char v145; // r11
  bool v146; // al
  bool v147; // al
  QueryHints *v148; // r13
  bool v149; // bl
  __int64 v150; // rax
  struct CSessionTraceFlags *v151; // rcx
  bool v152; // dl
  bool v153; // r15
  char v154; // al
  char v155; // r10
  bool v156; // bl
  __int64 *v157; // rcx
  __int64 v158; // rdx
  struct CSessionTraceFlags *v159; // rcx
  int v160; // eax
  __int64 v161; // rbx
  QueryHints *v162; // rcx
  __int64 v163; // rbx
  struct IMemObj *v164; // r12
  struct COptExpr *v165; // r15
  __int64 v166; // rdx
  struct CSessionTraceFlags *v167; // rcx
  int v168; // eax
  __int64 v169; // rbx
  __int64 v170; // rcx
  bool v171; // bl
  CInterestingPredicateExplorer *v172; // r13
  unsigned int *v173; // r14
  __int64 v174; // r8
  char v175; // al
  __int64 v176; // rbx
  __int64 v177; // rax
  double v178; // xmm6_8
  CInterestingPredicateExplorer *v179; // rax
  int v180; // eax
  __int64 v181; // rax
  struct CQte *v182; // rax
  struct CTelemetryPackageContainer *v183; // rdx
  _QWORD *v184; // r8
  __int64 v185; // r9
  char v186; // al
  char v187; // r9
  CExecLvlRepresentation *v188; // r13
  __int64 v189; // rbx
  CExecLvlRepresentation **v190; // r15
  _QWORD *v191; // rbx
  DataVirtualizationResource *v192; // rcx
  __int64 v193; // rbx
  struct IQueryObj *v194; // r15
  __int64 v195; // rdx
  int *v196; // rax
  bool v197; // cl
  CMultiPlanFeedback *v198; // rbx
  __int64 v199; // rbx
  __int64 v200; // r8
  const struct CCompExecCtxtStmt *v201; // r15
  __int64 v202; // rdx
  struct CSessionTraceFlags *v203; // rcx
  int v204; // eax
  double v205; // xmm6_8
  __int64 v206; // rax
  struct CQNameManager *v207; // rcx
  __int64 v208; // rdx
  __int64 v209; // r8
  __int64 v210; // rax
  __int64 v211; // rdx
  __int64 v212; // rax
  __int64 v213; // r9
  __int64 v214; // r8
  struct IMemObj *v215; // rbx
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rdx
  struct CSessionTraceFlags *v220; // rcx
  int v221; // eax
  struct IQueryObj *v222; // rbx
  BatchModeHeuristics *v223; // r14
  char v224; // al
  void *v225; // rbx
  struct Worker *v226; // rcx
  __int64 v227; // rbx
  struct IMemObj *v228; // rdi
  struct IMemObj *v229; // r14
  __int64 v230; // rbx
  struct Worker *v231; // rcx
  __int64 *v232; // rbx
  __int64 v233; // rbx
  __int64 v235; // r8
  struct CSessionTraceFlags **v236; // rax
  struct CSessionTraceFlags *v237; // rcx
  __int64 v238; // r8
  struct CSessionTraceFlags **v239; // rax
  struct CSessionTraceFlags *v240; // rcx
  struct CDataExportParameters *v241; // rax
  CDataExportParameters *v242; // rcx
  __int64 v243; // rax
  __int64 v244; // rcx
  bool v245; // r15
  __int64 v246; // rbx
  __int64 v247; // rax
  __int64 v248; // rax
  __int64 v249; // rax
  unsigned int k; // ebx
  __int64 v251; // rax
  unsigned int v252; // ecx
  __int64 v253; // r15
  bool v254; // di
  struct IMemObj *v255; // rbx
  CCompTimeTrace *v256; // rcx
  __int64 v257; // rbx
  _QWORD *v258; // r8
  __int64 v259; // rax
  unsigned __int64 v260; // rcx
  unsigned __int64 v261; // rax
  __int64 v262; // rcx
  struct CEsCompGroup *v263; // rbx
  __int64 v264; // rdi
  _QWORD *v265; // r8
  __int64 v266; // rax
  unsigned __int64 v267; // rcx
  unsigned __int64 v268; // rax
  __int64 v269; // rcx
  int v270; // edx
  DataVirtualizationResource *v271; // rcx
  __int64 v272; // rdx
  struct CSessionTraceFlags *v273; // rcx
  int v274; // eax
  struct SOS_TraceStream *v275; // rbx
  int v276; // ebx
  void ***v277; // rdi
  __int64 v278; // rdx
  struct CSessionTraceFlags *v279; // rcx
  int v280; // eax
  int v281; // ecx
  int v282; // edx
  int v283; // edx
  int v284; // edx
  CCompTimeTrace *v285; // rcx
  __int64 v286; // rbx
  _QWORD *v287; // r8
  __int64 v288; // rax
  unsigned __int64 v289; // rcx
  unsigned __int64 v290; // rax
  __int64 v291; // rcx
  struct CQNameManager *v292; // rbx
  __int64 v293; // rdi
  _QWORD *v294; // r8
  __int64 v295; // rax
  unsigned __int64 v296; // rcx
  unsigned __int64 v297; // rax
  __int64 v298; // rcx
  __int64 v299; // rbx
  __int64 v300; // rax
  __int64 v301; // rax
  char v302; // r9
  char v303; // r10
  __int64 v304; // rbx
  _QWORD *v305; // rax
  _QWORD *v306; // r8
  __int64 v307; // rax
  _QWORD *v308; // rcx
  unsigned __int64 v309; // rcx
  unsigned __int64 v310; // rax
  __int64 v311; // rcx
  int v312; // r9d
  _DWORD *v313; // rax
  int v314; // r9d
  char *v315; // rax
  char *v316; // rax
  CExecLvlRepresentation *v317; // rcx
  unsigned __int8 v318; // al
  char v319; // al
  __int64 v320; // rax
  struct CSessionTraceFlags **v321; // rax
  struct CSessionTraceFlags *v322; // rcx
  CQoTelemetryAgg *v323; // rax
  CQoTelemetryAgg *v324; // rax
  int *v325; // rax
  int v326; // eax
  char v327; // al
  unsigned int v328; // ecx
  __int64 v329; // rcx
  _QWORD *v330; // rax
  __int64 v331; // rbx
  __int64 v332; // rcx
  __int64 v333; // rcx
  DBTABLE *v334; // rcx
  __int64 v335; // rax
  unsigned __int8 v336; // cl
  char v337; // al
  char v338; // cl
  __int64 v339; // rax
  struct CSessionTraceFlags *v340; // rcx
  DBTABLE *v341; // rcx
  __int64 v342; // r14
  _QWORD *v343; // r8
  __int64 v344; // rax
  unsigned __int64 v345; // rcx
  unsigned __int64 v346; // rax
  __int64 v347; // rcx
  _DWORD *v348; // rax
  unsigned __int64 v349; // rbx
  char v350; // al
  _QWORD *v351; // rbx
  _QWORD *i; // rax
  struct IMemObj *v353; // r15
  char *v354; // rax
  struct DRgCId *v355; // rbx
  char *v356; // rax
  struct DRgCId *v357; // rdx
  struct IXteBuilder *v358; // rbx
  struct CQte *XteDummyConstScanWithOutput; // rax
  __int64 v360; // rcx
  __int64 v361; // rdx
  __int64 v362; // r14
  _QWORD *v363; // r8
  __int64 v364; // rax
  __int64 v365; // rcx
  unsigned __int64 v366; // rax
  unsigned __int64 v367; // rcx
  unsigned __int64 v368; // rax
  __int64 v369; // rcx
  int v370; // eax
  _QWORD *v371; // rcx
  __int64 v372; // rdx
  _QWORD *v373; // r14
  unsigned int v374; // r15d
  unsigned int j; // ebx
  char v376; // al
  __int64 v377; // rax
  CTableMetadata *v378; // rbx
  __int64 v379; // r11
  struct SOS_TraceStream *Stream; // rbx
  struct SOS_TraceStream *v381; // rbx
  struct SOS_TraceStream *v382; // rbx
  __int64 v383; // r14
  _QWORD *v384; // r8
  __int64 v385; // rax
  unsigned __int64 v386; // rcx
  unsigned __int64 v387; // rax
  __int64 v388; // rcx
  bool v389; // al
  __int64 v390; // rcx
  int v391; // eax
  int ii; // ebx
  unsigned int v393; // r15d
  unsigned int *v394; // rax
  unsigned int *v395; // rbx
  unsigned int v396; // r12d
  unsigned int v397; // eax
  _QWORD *v398; // rbx
  _OWORD *v399; // r15
  unsigned int v400; // ebx
  unsigned int v401; // eax
  __int64 v402; // rdx
  unsigned int v403; // ecx
  int v404; // edx
  unsigned int m; // r8d
  void *v406; // rcx
  unsigned int v407; // eax
  _QWORD *v408; // rax
  int v409; // ecx
  double v410; // xmm0_8
  unsigned __int64 v411; // rax
  CETelemetryPackage *v412; // rbx
  __int64 v413; // r14
  __int64 v414; // rax
  __int64 v415; // rcx
  unsigned __int64 v416; // rax
  unsigned __int64 v417; // rcx
  unsigned __int64 v418; // rax
  __int64 v419; // rcx
  __int64 v420; // r8
  __int64 v421; // r9
  _DWORD *v422; // rdx
  int v423; // eax
  int v424; // ecx
  int v425; // eax
  __int64 v426; // rbx
  void *v427; // rax
  struct CMemoXml *v428; // rax
  bool v429; // cl
  int v430; // eax
  __int64 v431; // rbx
  __int64 v432; // rax
  struct CRowsetFilesInfo *v433; // rax
  __int64 v434; // r14
  _QWORD *v435; // r8
  __int64 v436; // rax
  unsigned __int64 v437; // rcx
  unsigned __int64 v438; // rax
  __int64 v439; // rcx
  int *v440; // rcx
  __int64 v441; // rax
  int v442; // edx
  unsigned int n; // ebx
  struct CTelemetryPackage *v444; // r14
  CEncodeJsonUtil *v445; // rcx
  unsigned __int64 v446; // r14
  void *v447; // rcx
  int v448; // eax
  __int64 v449; // r14
  _QWORD *v450; // r8
  __int64 v451; // rax
  __int64 v452; // rcx
  unsigned __int64 v453; // rax
  unsigned __int64 v454; // rcx
  unsigned __int64 v455; // rax
  __int64 v456; // rcx
  struct CMemoXml *v457; // rdx
  struct SOS_TraceStream *v458; // rbx
  struct SOS_TraceStream *v459; // rbx
  struct SOS_TraceStream *v460; // rbx
  struct SOS_TraceStream *v461; // rbx
  struct SOS_TraceStream *v462; // rbx
  int v463; // ebx
  void ***v464; // r14
  __int64 v465; // rbx
  __int64 v466; // rax
  __int64 v467; // r9
  __int64 v468; // rdi
  _QWORD *v469; // r8
  __int64 v470; // rax
  unsigned __int64 v471; // rax
  unsigned __int64 v472; // rcx
  unsigned __int64 v473; // rax
  __int64 v474; // rcx
  __int64 v475; // rdi
  _QWORD *v476; // r8
  __int64 v477; // rax
  __int64 v478; // rdi
  _QWORD *v479; // r8
  unsigned __int64 v480; // rcx
  unsigned __int64 v481; // rax
  __int64 v482; // rcx
  unsigned __int64 v483; // rcx
  unsigned __int64 v484; // rax
  __int64 v485; // rcx
  _locale_t Locale; // [rsp+20h] [rbp-19A8h]
  int v487; // [rsp+28h] [rbp-19A0h]
  int v488; // [rsp+28h] [rbp-19A0h]
  int v489; // [rsp+30h] [rbp-1998h]
  char v490; // [rsp+90h] [rbp-1938h]
  bool v491; // [rsp+91h] [rbp-1937h]
  struct IMemObj *v492; // [rsp+A0h] [rbp-1928h]
  struct COptExpr *v493; // [rsp+A8h] [rbp-1920h]
  unsigned int CurrentDb; // [rsp+B0h] [rbp-1918h]
  CExecLvlRepresentation *v495; // [rsp+B8h] [rbp-1910h]
  bool v496; // [rsp+C0h] [rbp-1908h]
  char v497; // [rsp+C1h] [rbp-1907h]
  char v498; // [rsp+C3h] [rbp-1905h]
  bool v499; // [rsp+C4h] [rbp-1904h]
  char v500; // [rsp+C7h] [rbp-1901h] BYREF
  bool v501; // [rsp+C8h] [rbp-1900h]
  char v502; // [rsp+C9h] [rbp-18FFh]
  _BYTE v503[2]; // [rsp+CCh] [rbp-18FCh] BYREF
  char v504; // [rsp+CEh] [rbp-18FAh]
  char v505; // [rsp+CFh] [rbp-18F9h]
  char v506; // [rsp+D0h] [rbp-18F8h]
  int v507; // [rsp+D4h] [rbp-18F4h]
  struct IMemObj *v508; // [rsp+D8h] [rbp-18F0h]
  struct IQueryCompile *v509; // [rsp+E0h] [rbp-18E8h]
  int v510; // [rsp+E8h] [rbp-18E0h] BYREF
  unsigned __int64 v511; // [rsp+F0h] [rbp-18D8h]
  CEnvCollection *v512; // [rsp+F8h] [rbp-18D0h]
  char v513; // [rsp+100h] [rbp-18C8h]
  char v514; // [rsp+101h] [rbp-18C7h]
  char v515; // [rsp+102h] [rbp-18C6h]
  char v518; // [rsp+105h] [rbp-18C3h] BYREF
  char v519; // [rsp+106h] [rbp-18C2h]
  char v520; // [rsp+107h] [rbp-18C1h]
  char v522; // [rsp+109h] [rbp-18BFh]
  int v523; // [rsp+10Ch] [rbp-18BCh]
  char v524; // [rsp+110h] [rbp-18B8h] BYREF
  char v525; // [rsp+111h] [rbp-18B7h]
  char v526; // [rsp+112h] [rbp-18B6h]
  char v527; // [rsp+113h] [rbp-18B5h]
  char v528; // [rsp+114h] [rbp-18B4h]
  char v529; // [rsp+115h] [rbp-18B3h]
  char v530; // [rsp+116h] [rbp-18B2h]
  char v531; // [rsp+117h] [rbp-18B1h]
  char v532; // [rsp+118h] [rbp-18B0h]
  struct COptExpr *v533; // [rsp+120h] [rbp-18A8h]
  struct IQueryObj *v534; // [rsp+128h] [rbp-18A0h]
  CInterestingPredicateExplorer *v535; // [rsp+130h] [rbp-1898h]
  char v536[8]; // [rsp+138h] [rbp-1890h] BYREF
  struct CMemoXml *v537; // [rsp+140h] [rbp-1888h]
  __int64 v538; // [rsp+148h] [rbp-1880h]
  struct CSessionTraceFlags *v539; // [rsp+150h] [rbp-1878h]
  __int64 v540; // [rsp+158h] [rbp-1870h]
  struct CEsCompGroup *v541; // [rsp+160h] [rbp-1868h]
  char v542[8]; // [rsp+168h] [rbp-1860h] BYREF
  CMultiPlanFeedback *v543; // [rsp+170h] [rbp-1858h]
  unsigned __int64 v544; // [rsp+178h] [rbp-1850h]
  struct IMemObj **v545; // [rsp+180h] [rbp-1848h]
  CExecLvlRepresentation **v546; // [rsp+188h] [rbp-1840h]
  struct CQNameManager *v547; // [rsp+190h] [rbp-1838h]
  struct CQNameManager *v548; // [rsp+198h] [rbp-1830h]
  _QWORD *v549; // [rsp+1A0h] [rbp-1828h] BYREF
  unsigned int v550; // [rsp+1A8h] [rbp-1820h]
  int v551; // [rsp+1ACh] [rbp-181Ch]
  int v552; // [rsp+1B0h] [rbp-1818h]
  int v553; // [rsp+1B8h] [rbp-1810h]
  unsigned int v554; // [rsp+1C0h] [rbp-1808h] BYREF
  unsigned int v555; // [rsp+1C4h] [rbp-1804h]
  int v556; // [rsp+1C8h] [rbp-1800h]
  int v557; // [rsp+1CCh] [rbp-17FCh]
  unsigned int v558; // [rsp+1D0h] [rbp-17F8h]
  unsigned int v559; // [rsp+1D4h] [rbp-17F4h]
  int v560; // [rsp+1D8h] [rbp-17F0h]
  unsigned int v561; // [rsp+1E0h] [rbp-17E8h]
  int v562; // [rsp+1E8h] [rbp-17E0h]
  int v563; // [rsp+1F0h] [rbp-17D8h]
  int v564; // [rsp+1F8h] [rbp-17D0h]
  unsigned int v565; // [rsp+200h] [rbp-17C8h]
  int v566; // [rsp+208h] [rbp-17C0h]
  int v567; // [rsp+210h] [rbp-17B8h]
  struct COptInterfaces *v568; // [rsp+218h] [rbp-17B0h]
  __int64 v569; // [rsp+220h] [rbp-17A8h]
  struct IXteBuilder *XteBuilderObject; // [rsp+228h] [rbp-17A0h]
  struct IMemObj *v571; // [rsp+230h] [rbp-1798h]
  unsigned __int64 v572; // [rsp+238h] [rbp-1790h]
  struct CQOQueryHints *v573; // [rsp+240h] [rbp-1788h]
  int v574; // [rsp+248h] [rbp-1780h]
  int v575; // [rsp+24Ch] [rbp-177Ch]
  int v576; // [rsp+250h] [rbp-1778h]
  __int64 v577; // [rsp+258h] [rbp-1770h]
  unsigned int v578; // [rsp+260h] [rbp-1768h] BYREF
  double v579; // [rsp+268h] [rbp-1760h] BYREF
  __int64 v580; // [rsp+270h] [rbp-1758h]
  int v581; // [rsp+278h] [rbp-1750h]
  CExecLvlRepresentation **v582; // [rsp+280h] [rbp-1748h]
  _DWORD v583[4]; // [rsp+288h] [rbp-1740h] BYREF
  int v584; // [rsp+298h] [rbp-1730h]
  unsigned __int64 v585; // [rsp+2A0h] [rbp-1728h]
  int v586; // [rsp+2ACh] [rbp-171Ch]
  int v587; // [rsp+2B0h] [rbp-1718h]
  void *v588; // [rsp+2B8h] [rbp-1710h]
  unsigned __int64 v589; // [rsp+2C0h] [rbp-1708h] BYREF
  int v590; // [rsp+2CCh] [rbp-16FCh]
  int v591; // [rsp+2D0h] [rbp-16F8h]
  __int64 v592; // [rsp+2D8h] [rbp-16F0h]
  char v593[8]; // [rsp+2E0h] [rbp-16E8h] BYREF
  __int64 v594; // [rsp+2E8h] [rbp-16E0h] BYREF
  QueryHints *v595; // [rsp+2F0h] [rbp-16D8h]
  __int64 v596; // [rsp+2F8h] [rbp-16D0h]
  struct IMemObj *v597; // [rsp+300h] [rbp-16C8h]
  struct IMemObj *v598; // [rsp+308h] [rbp-16C0h]
  const struct CStatementDescription *v599; // [rsp+310h] [rbp-16B8h]
  __int64 v600; // [rsp+318h] [rbp-16B0h] BYREF
  struct CQte *v601; // [rsp+320h] [rbp-16A8h]
  double v602; // [rsp+328h] [rbp-16A0h] BYREF
  CExecLvlRepresentation **v603; // [rsp+330h] [rbp-1698h]
  struct CQODBSetOptions *v604; // [rsp+338h] [rbp-1690h]
  CExecLvlRepresentation **v605; // [rsp+340h] [rbp-1688h]
  CExecLvlRepresentation **v606; // [rsp+348h] [rbp-1680h]
  void ***v607; // [rsp+350h] [rbp-1678h] BYREF
  int v608; // [rsp+358h] [rbp-1670h]
  void ***v609; // [rsp+360h] [rbp-1668h] BYREF
  int v610; // [rsp+368h] [rbp-1660h]
  _QWORD *v611; // [rsp+370h] [rbp-1658h]
  __int64 v612; // [rsp+378h] [rbp-1650h]
  int *v613; // [rsp+380h] [rbp-1648h]
  int v614; // [rsp+388h] [rbp-1640h] BYREF
  unsigned int v615; // [rsp+38Ch] [rbp-163Ch]
  unsigned __int64 v616; // [rsp+390h] [rbp-1638h]
  __int64 v617; // [rsp+398h] [rbp-1630h]
  void **v618; // [rsp+3A0h] [rbp-1628h] BYREF
  int v619; // [rsp+3A8h] [rbp-1620h]
  int v620; // [rsp+3B0h] [rbp-1618h]
  __int64 v621; // [rsp+3B8h] [rbp-1610h]
  _QWORD v622[4]; // [rsp+3C0h] [rbp-1608h] BYREF
  unsigned __int64 v623; // [rsp+3E0h] [rbp-15E8h] BYREF
  unsigned __int64 v624; // [rsp+3E8h] [rbp-15E0h]
  int v625; // [rsp+3F0h] [rbp-15D8h]
  int v626; // [rsp+3F8h] [rbp-15D0h]
  int v627; // [rsp+400h] [rbp-15C8h]
  int v628; // [rsp+408h] [rbp-15C0h]
  int v629; // [rsp+410h] [rbp-15B8h]
  int v630; // [rsp+418h] [rbp-15B0h]
  int v631; // [rsp+420h] [rbp-15A8h]
  int v632; // [rsp+428h] [rbp-15A0h]
  int v633; // [rsp+430h] [rbp-1598h]
  int v634; // [rsp+438h] [rbp-1590h]
  int v635; // [rsp+440h] [rbp-1588h]
  int v636; // [rsp+448h] [rbp-1580h]
  int v637; // [rsp+44Ch] [rbp-157Ch]
  int v638; // [rsp+450h] [rbp-1578h]
  int v639; // [rsp+454h] [rbp-1574h]
  int v640; // [rsp+458h] [rbp-1570h]
  int v641; // [rsp+45Ch] [rbp-156Ch]
  int v642; // [rsp+460h] [rbp-1568h]
  int v643; // [rsp+464h] [rbp-1564h]
  int v644; // [rsp+468h] [rbp-1560h]
  _QWORD *v645; // [rsp+470h] [rbp-1558h]
  struct CSessionTraceFlags *v646; // [rsp+478h] [rbp-1550h]
  struct IValRefTracker *v647; // [rsp+480h] [rbp-1548h]
  __int64 v648; // [rsp+488h] [rbp-1540h]
  struct CQOFeatureSwitches *v649; // [rsp+490h] [rbp-1538h]
  struct CQOEEState *v650; // [rsp+498h] [rbp-1530h]
  struct CQOServerConfig *v651; // [rsp+4A0h] [rbp-1528h]
  struct CSessionTraceFlags *v652; // [rsp+4A8h] [rbp-1520h]
  struct CSessionTraceFlags *v653; // [rsp+4B0h] [rbp-1518h]
  struct CSessionTraceFlags *v654; // [rsp+4B8h] [rbp-1510h]
  struct CSessionTraceFlags *v655; // [rsp+4C0h] [rbp-1508h]
  struct CSessionTraceFlags *v656; // [rsp+4C8h] [rbp-1500h]
  struct CSessionTraceFlags *v657; // [rsp+4D0h] [rbp-14F8h]
  struct CSessionTraceFlags *v658; // [rsp+4D8h] [rbp-14F0h]
  struct CSessionTraceFlags *v659; // [rsp+4E0h] [rbp-14E8h]
  struct CSessionTraceFlags *v660; // [rsp+4E8h] [rbp-14E0h]
  struct CSessionTraceFlags *v661; // [rsp+4F0h] [rbp-14D8h]
  struct CSessionTraceFlags *v662; // [rsp+4F8h] [rbp-14D0h]
  int v663; // [rsp+500h] [rbp-14C8h]
  struct CSessionTraceFlags *v664; // [rsp+508h] [rbp-14C0h] BYREF
  struct CSessionTraceFlags *v665; // [rsp+510h] [rbp-14B8h] BYREF
  int *v666; // [rsp+518h] [rbp-14B0h] BYREF
  __int64 v667; // [rsp+520h] [rbp-14A8h]
  __int64 v668; // [rsp+528h] [rbp-14A0h]
  __int64 v669; // [rsp+530h] [rbp-1498h]
  char v670[8]; // [rsp+538h] [rbp-1490h] BYREF
  char v671[8]; // [rsp+540h] [rbp-1488h] BYREF
  char v672[8]; // [rsp+548h] [rbp-1480h] BYREF
  int v673; // [rsp+550h] [rbp-1478h]
  int v674; // [rsp+554h] [rbp-1474h]
  __int64 v675; // [rsp+558h] [rbp-1470h]
  int v676; // [rsp+560h] [rbp-1468h]
  int v677; // [rsp+568h] [rbp-1460h]
  int v678; // [rsp+570h] [rbp-1458h]
  __int64 v679; // [rsp+578h] [rbp-1450h]
  char v680[8]; // [rsp+580h] [rbp-1448h] BYREF
  char v681[8]; // [rsp+588h] [rbp-1440h] BYREF
  double v682; // [rsp+590h] [rbp-1438h] BYREF
  char v683[8]; // [rsp+598h] [rbp-1430h] BYREF
  char v684[8]; // [rsp+5A0h] [rbp-1428h] BYREF
  double v685; // [rsp+5A8h] [rbp-1420h] BYREF
  char v686[8]; // [rsp+5B0h] [rbp-1418h] BYREF
  char v687[8]; // [rsp+5B8h] [rbp-1410h] BYREF
  char v688[8]; // [rsp+5C0h] [rbp-1408h] BYREF
  char v689[8]; // [rsp+5C8h] [rbp-1400h] BYREF
  double v690; // [rsp+5D0h] [rbp-13F8h] BYREF
  char v691[8]; // [rsp+5D8h] [rbp-13F0h] BYREF
  char v692[8]; // [rsp+5E0h] [rbp-13E8h] BYREF
  char v693[8]; // [rsp+5E8h] [rbp-13E0h] BYREF
  int v694; // [rsp+5F0h] [rbp-13D8h]
  __int64 v695; // [rsp+5F8h] [rbp-13D0h]
  __int64 v696; // [rsp+600h] [rbp-13C8h]
  __int64 v697; // [rsp+608h] [rbp-13C0h] BYREF
  __int64 v698; // [rsp+610h] [rbp-13B8h] BYREF
  __int64 v699; // [rsp+618h] [rbp-13B0h] BYREF
  __int64 v700; // [rsp+620h] [rbp-13A8h] BYREF
  char v701[8]; // [rsp+628h] [rbp-13A0h] BYREF
  char v702[8]; // [rsp+630h] [rbp-1398h] BYREF
  char v703[8]; // [rsp+638h] [rbp-1390h] BYREF
  __int64 v704; // [rsp+640h] [rbp-1388h] BYREF
  __int64 v705; // [rsp+648h] [rbp-1380h] BYREF
  __int64 v706; // [rsp+650h] [rbp-1378h] BYREF
  __int64 v707; // [rsp+658h] [rbp-1370h]
  struct Worker *v708; // [rsp+660h] [rbp-1368h]
  int **v709; // [rsp+668h] [rbp-1360h] BYREF
  struct CAutoSessionTraceFlagOrQORuleToggler *v710; // [rsp+670h] [rbp-1358h] BYREF
  int v711; // [rsp+678h] [rbp-1350h]
  CExecLvlRepresentation **v712; // [rsp+680h] [rbp-1348h]
  int v713; // [rsp+688h] [rbp-1340h]
  int v714; // [rsp+690h] [rbp-1338h]
  CExecLvlRepresentation **v715; // [rsp+698h] [rbp-1330h]
  int v716; // [rsp+6A0h] [rbp-1328h]
  __int64 v717; // [rsp+6A8h] [rbp-1320h]
  int v718; // [rsp+6B0h] [rbp-1318h]
  int v719; // [rsp+6B8h] [rbp-1310h]
  int v720; // [rsp+6C0h] [rbp-1308h]
  int v721; // [rsp+6C8h] [rbp-1300h]
  int v722; // [rsp+6D0h] [rbp-12F8h]
  int v723; // [rsp+6D8h] [rbp-12F0h]
  int v724; // [rsp+6DCh] [rbp-12ECh]
  int v725; // [rsp+6E0h] [rbp-12E8h]
  void **v726; // [rsp+6E8h] [rbp-12E0h] BYREF
  int v727; // [rsp+6F0h] [rbp-12D8h]
  int v728; // [rsp+6F8h] [rbp-12D0h]
  __int64 v729; // [rsp+700h] [rbp-12C8h]
  int v730; // [rsp+708h] [rbp-12C0h]
  _DWORD v731[6]; // [rsp+710h] [rbp-12B8h] BYREF
  unsigned int v732; // [rsp+728h] [rbp-12A0h] BYREF
  struct IMemObj *v733; // [rsp+730h] [rbp-1298h]
  unsigned __int64 v734; // [rsp+738h] [rbp-1290h]
  unsigned int v735; // [rsp+740h] [rbp-1288h] BYREF
  struct IMemObj *v736; // [rsp+748h] [rbp-1280h]
  char v737; // [rsp+750h] [rbp-1278h]
  unsigned __int64 v738; // [rsp+758h] [rbp-1270h]
  __int64 v739; // [rsp+760h] [rbp-1268h]
  __int64 v740; // [rsp+768h] [rbp-1260h]
  _DWORD *v741; // [rsp+770h] [rbp-1258h]
  struct IMemObj *v742; // [rsp+778h] [rbp-1250h]
  struct IMemObj *v743; // [rsp+780h] [rbp-1248h]
  struct IMemObj *v744; // [rsp+788h] [rbp-1240h]
  char *v745; // [rsp+790h] [rbp-1238h]
  struct IMemObj *v746; // [rsp+798h] [rbp-1230h]
  struct IMemObj *v747; // [rsp+7A0h] [rbp-1228h]
  char *v748; // [rsp+7A8h] [rbp-1220h]
  struct IMemObj *v749; // [rsp+7B0h] [rbp-1218h]
  CInterestingPredicateExplorer *v750; // [rsp+7B8h] [rbp-1210h]
  unsigned int *v751; // [rsp+7C0h] [rbp-1208h]
  struct IMemObj *v752; // [rsp+7C8h] [rbp-1200h]
  struct IMemObj *v753; // [rsp+7D0h] [rbp-11F8h]
  struct IMemObj *v754; // [rsp+7D8h] [rbp-11F0h]
  unsigned int *v755; // [rsp+7E0h] [rbp-11E8h]
  _OWORD *v756; // [rsp+7E8h] [rbp-11E0h]
  double v757; // [rsp+7F0h] [rbp-11D8h] BYREF
  double v758; // [rsp+7F8h] [rbp-11D0h] BYREF
  double v759; // [rsp+800h] [rbp-11C8h] BYREF
  unsigned __int64 v760[12]; // [rsp+808h] [rbp-11C0h] BYREF
  unsigned __int64 v761[5]; // [rsp+868h] [rbp-1160h] BYREF
  __int128 v762; // [rsp+890h] [rbp-1138h] BYREF
  __int128 v763; // [rsp+8A0h] [rbp-1128h] BYREF
  _BYTE v764[16]; // [rsp+8B0h] [rbp-1118h] BYREF
  _QWORD v765[6]; // [rsp+8C0h] [rbp-1108h] BYREF
  struct IMemObj *v766; // [rsp+8F0h] [rbp-10D8h]
  CVRTableOpt *v767; // [rsp+8F8h] [rbp-10D0h]
  __int64 v768; // [rsp+900h] [rbp-10C8h]
  __int64 v769; // [rsp+908h] [rbp-10C0h]
  __int64 v770; // [rsp+910h] [rbp-10B8h]
  _QWORD *v771; // [rsp+918h] [rbp-10B0h]
  unsigned __int64 *v772; // [rsp+920h] [rbp-10A8h]
  _BYTE v773[40]; // [rsp+928h] [rbp-10A0h] BYREF
  char v774[8]; // [rsp+950h] [rbp-1078h] BYREF
  __int16 v775; // [rsp+958h] [rbp-1070h]
  __int16 v776; // [rsp+95Ah] [rbp-106Eh]
  int v777; // [rsp+960h] [rbp-1068h]
  char **v778; // [rsp+968h] [rbp-1060h]
  char *v779; // [rsp+970h] [rbp-1058h]
  __int64 v780; // [rsp+978h] [rbp-1050h]
  char *v781; // [rsp+980h] [rbp-1048h] BYREF
  int v782; // [rsp+988h] [rbp-1040h]
  __int16 v783; // [rsp+98Ch] [rbp-103Ch]
  __int16 v784; // [rsp+98Eh] [rbp-103Ah]
  char v785; // [rsp+990h] [rbp-1038h] BYREF
  int v786; // [rsp+BA0h] [rbp-E28h]
  int v787; // [rsp+BA4h] [rbp-E24h]
  __int64 v788; // [rsp+BA8h] [rbp-E20h]
  char v789; // [rsp+BB0h] [rbp-E18h] BYREF
  unsigned int v790; // [rsp+BB1h] [rbp-E17h]
  int v791; // [rsp+BB5h] [rbp-E13h]
  __int64 v792; // [rsp+BB9h] [rbp-E0Fh]
  char v793[8]; // [rsp+BD0h] [rbp-DF8h] BYREF
  __int16 v794; // [rsp+BD8h] [rbp-DF0h]
  __int16 v795; // [rsp+BDAh] [rbp-DEEh]
  int v796; // [rsp+BE0h] [rbp-DE8h]
  char **v797; // [rsp+BE8h] [rbp-DE0h]
  char *v798; // [rsp+BF0h] [rbp-DD8h]
  __int64 v799; // [rsp+BF8h] [rbp-DD0h]
  char *v800; // [rsp+C00h] [rbp-DC8h] BYREF
  int v801; // [rsp+C08h] [rbp-DC0h]
  __int16 v802; // [rsp+C0Ch] [rbp-DBCh]
  __int16 v803; // [rsp+C0Eh] [rbp-DBAh]
  char v804; // [rsp+C10h] [rbp-DB8h] BYREF
  int v805; // [rsp+E20h] [rbp-BA8h]
  int v806; // [rsp+E24h] [rbp-BA4h]
  __int64 v807; // [rsp+E28h] [rbp-BA0h]
  char v808; // [rsp+E30h] [rbp-B98h] BYREF
  int v809; // [rsp+E31h] [rbp-B97h]
  int v810; // [rsp+E35h] [rbp-B93h]
  __int64 v811; // [rsp+E39h] [rbp-B8Fh]
  char v812[8]; // [rsp+E50h] [rbp-B78h] BYREF
  __int16 v813; // [rsp+E58h] [rbp-B70h]
  __int16 v814; // [rsp+E5Ah] [rbp-B6Eh]
  int v815; // [rsp+E60h] [rbp-B68h]
  int **v816; // [rsp+E68h] [rbp-B60h]
  char *v817; // [rsp+E70h] [rbp-B58h]
  __int64 v818; // [rsp+E78h] [rbp-B50h]
  int *v819; // [rsp+E80h] [rbp-B48h] BYREF
  int v820; // [rsp+E88h] [rbp-B40h]
  __int16 v821; // [rsp+E8Ch] [rbp-B3Ch]
  __int16 v822; // [rsp+E8Eh] [rbp-B3Ah]
  char v823; // [rsp+E90h] [rbp-B38h] BYREF
  int v824; // [rsp+10A0h] [rbp-928h]
  int v825; // [rsp+10A4h] [rbp-924h]
  __int64 v826; // [rsp+10A8h] [rbp-920h]
  int v827; // [rsp+10B0h] [rbp-918h] BYREF
  char v828[8]; // [rsp+10C0h] [rbp-908h] BYREF
  __int16 v829; // [rsp+10C8h] [rbp-900h]
  __int16 v830; // [rsp+10CAh] [rbp-8FEh]
  int v831; // [rsp+10D0h] [rbp-8F8h]
  int **v832; // [rsp+10D8h] [rbp-8F0h]
  char *v833; // [rsp+10E0h] [rbp-8E8h]
  __int64 v834; // [rsp+10E8h] [rbp-8E0h]
  int *v835; // [rsp+10F0h] [rbp-8D8h] BYREF
  int v836; // [rsp+10F8h] [rbp-8D0h]
  __int16 v837; // [rsp+10FCh] [rbp-8CCh]
  __int16 v838; // [rsp+10FEh] [rbp-8CAh]
  char v839; // [rsp+1100h] [rbp-8C8h] BYREF
  int v840; // [rsp+1310h] [rbp-6B8h]
  int v841; // [rsp+1314h] [rbp-6B4h]
  __int64 v842; // [rsp+1318h] [rbp-6B0h]
  int v843; // [rsp+1320h] [rbp-6A8h] BYREF
  _BYTE v844[176]; // [rsp+1330h] [rbp-698h] BYREF
  CExecLvlRepresentation *v845; // [rsp+13E0h] [rbp-5E8h]
  int v846[4]; // [rsp+13F0h] [rbp-5D8h] BYREF
  __int64 v847; // [rsp+1400h] [rbp-5C8h]
  struct IMemObj *v848; // [rsp+1410h] [rbp-5B8h]
  __int64 v849; // [rsp+1418h] [rbp-5B0h]
  __int64 v850; // [rsp+1420h] [rbp-5A8h]
  __int64 v851; // [rsp+1438h] [rbp-590h]
  __int64 v852; // [rsp+1440h] [rbp-588h]
  __int16 v853; // [rsp+144Ch] [rbp-57Ch]
  char v854; // [rsp+144Eh] [rbp-57Ah]
  int v855; // [rsp+1450h] [rbp-578h]
  unsigned int v856; // [rsp+1454h] [rbp-574h]
  unsigned __int8 v857; // [rsp+1458h] [rbp-570h]
  char v858; // [rsp+1459h] [rbp-56Fh]
  char v859; // [rsp+145Ah] [rbp-56Eh]
  char v860; // [rsp+145Bh] [rbp-56Dh]
  char v861; // [rsp+145Ch] [rbp-56Ch]
  int v862; // [rsp+1460h] [rbp-568h]
  int v863; // [rsp+1464h] [rbp-564h]
  char v864; // [rsp+14A0h] [rbp-528h]
  char v865; // [rsp+14A1h] [rbp-527h]
  char v866; // [rsp+14A2h] [rbp-526h]
  char v867; // [rsp+14A3h] [rbp-525h]
  char v868; // [rsp+14A4h] [rbp-524h]
  char v869; // [rsp+14A5h] [rbp-523h]
  char v870; // [rsp+14A6h] [rbp-522h]
  char v871; // [rsp+14A7h] [rbp-521h]
  struct CQNameManager *v872; // [rsp+14B8h] [rbp-510h]
  CMemo *v873; // [rsp+1520h] [rbp-4A8h]
  __int64 v874; // [rsp+1580h] [rbp-448h]
  struct DRgPDispatcherPredicateHint *v875; // [rsp+1590h] [rbp-438h]
  COptAntiPatterns *v876; // [rsp+15F0h] [rbp-3D8h]
  __int64 v877; // [rsp+1610h] [rbp-3B8h]
  __int64 v878; // [rsp+1618h] [rbp-3B0h]
  int v879; // [rsp+1624h] [rbp-3A4h]
  __int64 v880; // [rsp+1630h] [rbp-398h]
  __int64 v881; // [rsp+1638h] [rbp-390h]
  __int64 v882; // [rsp+1660h] [rbp-368h]
  int v883; // [rsp+1668h] [rbp-360h]
  __int64 v884; // [rsp+1670h] [rbp-358h]
  unsigned int v885; // [rsp+16A0h] [rbp-328h]
  __int64 v886; // [rsp+16A8h] [rbp-320h]
  BatchModeHeuristics *v887; // [rsp+16C8h] [rbp-300h]
  __int64 v888; // [rsp+1710h] [rbp-2B8h]
  __int64 v889; // [rsp+1718h] [rbp-2B0h]
  CInterestingPredicateExplorer *v890; // [rsp+1720h] [rbp-2A8h]
  struct COptExpr *v891; // [rsp+1758h] [rbp-270h] BYREF
  __int64 v892; // [rsp+1778h] [rbp-250h]
  CQoTelemetryAgg *v893; // [rsp+1790h] [rbp-238h]
  CETelemetryPackage *v894; // [rsp+1798h] [rbp-230h]
  struct CDataExportParameters *v895; // [rsp+17C8h] [rbp-200h]
  int v896; // [rsp+1810h] [rbp-1B8h]
  __int64 v897; // [rsp+1818h] [rbp-1B0h]
  int v898; // [rsp+1820h] [rbp-1A8h]
  unsigned __int64 v899; // [rsp+1830h] [rbp-198h] BYREF
  unsigned __int64 v900; // [rsp+1838h] [rbp-190h]
  unsigned __int64 v901; // [rsp+1840h] [rbp-188h] BYREF
  unsigned __int64 v902; // [rsp+1848h] [rbp-180h]
  char Buffer[256]; // [rsp+1870h] [rbp-158h] BYREF

  v739 = -2;
  v508 = a3;
  v541 = a2;
  v533 = a1;
  v597 = a3;
  v512 = a5;
  v523 = a6;
  v546 = a11;
  v599 = a13;
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
  v534 = 0;
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
  v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v24 = *(_QWORD *)(v23 + 256);
  if ( !v24 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v24 = *(_QWORD *)(v23 + 256);
  }
  v25 = *(_QWORD *)(v24 + 992);
  ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, *(_WORD *)(v25 + 160));
  SOS_OS::GetClientProcessGlobals();
  MemObject = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(107);
  v492 = MemObject;
  if ( !MemObject )
  {
    LOBYTE(v27) = 65;
    ex_raise_oom(v27);
  }
  v29 = (CMallocSpy *)(*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemObject + 176LL))(MemObject);
  if ( v29 )
    CMallocSpy::SetDescriptiveName(v29, Buffer);
  (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)MemObject + 240LL))(MemObject);
  v571 = MemObject;
  v30 = *((_QWORD *)a1 + 2);
  v707 = v30;
  v31 = *(struct QueryTraceAndRuleHints ***)(v30 + 56);
  v595 = (QueryHints *)v31;
  Hints = CaptureQueryHints(MemObject, (const struct QueryHints *)v31);
  v573 = Hints;
  v33 = a11;
  if ( *(_BYTE *)a11 )
  {
    v34 = *((unsigned int *)a11 + 26);
  }
  else
  {
    CExecLvlIntCtxt::GetCurCompatLevel(a11[16], &v578, a11);
    v34 = v578;
    Hints = v573;
    v33 = a11;
  }
  v507 = v34;
  if ( a12 )
    return (struct IQueryObj *)(**(__int64 (__fastcall ***)(struct IQueryWithFeedback *, struct IMemObj *, __int64, _QWORD, struct CQOQueryHints *, CEnvCollection *, CExecLvlRepresentation **, struct COptExpr *))a12)(
                                 a12,
                                 v508,
                                 v34,
                                 0,
                                 Hints,
                                 v512,
                                 v33,
                                 v533);
  v509 = 0;
  v569 = 0;
  v491 = 0;
  memset(v622, 0, sizeof(v622));
  v623 = 0;
  v624 = 0;
  v35 = v33[20];
  v495 = v35;
  if ( v31 )
  {
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(_QWORD *)(v36 + 256);
    }
    v38 = CAutoSessionTraceFlagOrQORuleToggler::CreateAndActivate(*(struct IMemObj **)(v37 + 1000), v31[6], 1, 1);
    v35 = v495;
  }
  else
  {
    v38 = 0;
  }
  v710 = v38;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v773, 0x1Du, 6u, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
    *((_BYTE *)v35 + 44) |= 8u;
    GetMemoryClerk(8, 1);
    v40 = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(95);
    if ( !v40 )
    {
      LOBYTE(v39) = 65;
      ex_raise_oom(v39);
    }
    v598 = v40;
    v663 = 2219;
    v41 = (CValRefTracker *)operator new(0x20u, MemObject, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2219, 1u);
    v761[3] = (unsigned __int64)v41;
    if ( v41 )
      v42 = CValRefTracker::CValRefTracker(v41, MemObject);
    else
      v42 = 0;
    v647 = v42;
    v765[2] = v42;
    v673 = 2220;
    v43 = (CVRTableComp *)operator new(0x30u, v508, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2220, 1u);
    v765[4] = v43;
    if ( v43 )
      v44 = CVRTableComp::CVRTableComp(v43, v508, v42);
    else
      v44 = 0;
    v765[5] = v44;
    v674 = 2221;
    v45 = (CVRTableOpt *)operator new(0x30u, MemObject, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2221, 1u);
    v767 = v45;
    if ( v45 )
      v46 = CVRTableOpt::CVRTableOpt(v45, MemObject, v42);
    else
      v46 = 0;
    v603 = (CExecLvlRepresentation **)v46;
    CQNameManager = CreateCQNameManager(v40);
    v548 = CQNameManager;
    v48 = CreateCQNameManager(v508);
    v547 = v48;
    v49 = a9;
    v50 = 195;
    if ( a9 == 194 )
      v49 = 195;
    v603 = a11;
    IQueryCompile = (struct IQueryCompile *)CreateIQueryCompile(
                                              v508,
                                              v40,
                                              v49,
                                              (unsigned int)a10,
                                              a11,
                                              v512,
                                              v44,
                                              v46,
                                              CQNameManager,
                                              v48,
                                              v541);
    v509 = IQueryCompile;
    v603 = a11;
    CurrentDb = (unsigned __int16)ContextAccessor::GetCurrentDb();
    if ( FSystemDBId(CurrentDb) || CExecLvlRepresentation::FInternal(v495) )
    {
      v490 = 0;
      (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 360LL))(IQueryCompile);
    }
    else
    {
      v490 = 1;
      (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 352LL))(IQueryCompile);
      v569 = (*(__int64 (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)IQueryCompile + 384LL))(IQueryCompile);
    }
    XteBuilderObject = CreateXteBuilderObject(IQueryCompile);
    v676 = 2262;
    v52 = (struct IMemObj **)operator new(0x70u, v40, "sql\\ntdbms\\query\\qoin\\pqobuild.cpp", 2262, 1u);
    v761[2] = (unsigned __int64)v52;
    if ( v52 )
    {
      if ( a9 == 194 )
      {
        v581 = 195;
      }
      else
      {
        v50 = a9;
        v581 = (__int16)a9;
      }
      *v52 = v492;
      v52[1] = v508;
      v52[2] = v40;
      v52[3] = v512;
      v52[4] = (struct IMemObj *)a11;
      v52[5] = v548;
      v52[6] = v547;
      v52[7] = v46;
      v52[8] = v44;
      v52[9] = 0;
      v52[10] = IQueryCompile;
      v52[11] = XteBuilderObject;
      v52[12] = (struct IMemObj *)v30;
      *((_WORD *)v52 + 52) = v50;
    }
    else
    {
      v52 = 0;
    }
    v568 = (struct COptInterfaces *)v52;
    v545 = v52;
    v600 = *(_QWORD *)(v30 + 712);
    if ( !v600 )
      utgettime((struct SQLDATEBASE *)&v600, 1, 0);
    (*(void (__fastcall **)(struct IQueryCompile *, __int64 *))(*(_QWORD *)IQueryCompile + 176LL))(IQueryCompile, &v600);
    v53 = *((_QWORD *)v495 + 8);
    if ( v53 )
    {
      v645 = (_QWORD *)*((_QWORD *)v495 + 8);
      if ( *(_QWORD *)v53 || *(_QWORD *)(v53 + 120) )
        *(_BYTE *)(v53 + 704) = 0;
      v304 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v305 = *(_QWORD **)(v304 + 256);
      v306 = v305;
      if ( !v305 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v305 = *(_QWORD **)(v304 + 256);
        v306 = v305;
      }
      v712 = (CExecLvlRepresentation **)v305;
      if ( v306[107] )
      {
        v309 = __rdtsc();
        v310 = v306[108];
        if ( v309 <= v310 )
          v311 = 0;
        else
          v311 = v309 - v310;
        v307 = v311 + v306[109];
      }
      else
      {
        v307 = 0;
      }
      v308 = v645;
      *v645 = v307;
      v308[15] = __rdtsc();
    }
    v604 = CaptureDBAndSetOptions(v492);
    v651 = CaptureServerConfig(v492);
    v54 = v595;
    if ( v595 )
    {
      OptimizerCompatLevel = QueryHints::IGetQueryOptimizerCompatLevel(v595);
      if ( OptimizerCompatLevel != -1 )
      {
        if ( byte_102EDCE31 )
        {
          v677 = 11041;
          v520 = *((_BYTE *)qword_102ECFB10 + 1380) >> 1;
          if ( (v520 & 1) == 0 )
          {
            if ( OptimizerCompatLevel == 160 )
            {
              if ( byte_102EDCB6F )
                v507 = 160;
            }
            else
            {
              v507 = OptimizerCompatLevel;
            }
          }
        }
      }
      if ( (unsigned __int8)QueryHints::FHintSet(v54, 3) )
        goto LABEL_585;
    }
    v678 = 4199;
    if ( *((_BYTE *)qword_102ECFB10 + 524) >> 7 )
      goto LABEL_585;
    v694 = 0;
    v56 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v56 && (v57 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v56 + 56LL), (v58 = *v57) != 0) )
    {
      v646 = *v57;
      if ( CSessionTraceFlags::CheckSessionTraceInternal(v58, 0x1067u) )
        goto LABEL_585;
    }
    else
    {
      v646 = 0;
    }
    v712 = a11;
    v582 = a11;
    v582 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset);
    v59 = v582[10];
    v60 = *((_BYTE *)v59 + 60);
    if ( (*((_BYTE *)v59 + 68) & 8) != 0 )
      v61 = v60 >> 5;
    else
      v61 = v60 >> 4;
    if ( (v61 & 1) == 0 )
    {
      v62 = 0;
LABEL_55:
      v497 = v62;
      v648 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset)
                       + 120LL)
           + 120LL;
      v649 = CaptureFeatureSwitches(v492, v604);
      v550 = CaptureStatementType(a9);
      v650 = CaptureXLvlRepSettings(v492);
      v496 = FPDWFeaturesExposed();
      v63 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      FSetOptionsOkForIccIv(0, 13014);
      v64 = CExecLvlRepresentation::PmoPph(*(CExecLvlRepresentation **)(v63 + 160));
      v65 = v573;
      LOBYTE(v487) = v497;
      COptContext::COptContext(
        v846,
        v492,
        v64,
        v550,
        v507,
        v487,
        v651,
        v650,
        v649,
        v648,
        v568,
        v604,
        v647,
        v66,
        v523,
        v573,
        v496);
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 12)
        && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 84)
        && (v863 >= 160 || (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 121)) )
      {
        v858 |= 1u;
      }
      Context = UtilDbccGetContext();
      if ( Context )
      {
        v523 = (*((_DWORD *)Context + 3) >> 6) & 1;
        if ( v523 )
          v856 |= 0x20000u;
      }
      else
      {
        v523 = 0;
      }
      if ( FUtilNcciAreFlushBufferSyntaxAllowed() )
        v856 = v68 | 0x40000;
      if ( UtilDbccGetContext() )
      {
        if ( UtilDbccGetContext() )
          v313 = (_DWORD *)((char *)UtilDbccGetContext() + 12);
        else
          v313 = 0;
        v551 = (*v313 >> 15) & 1;
        if ( v551 )
          v856 = v312 | 0x80000;
      }
      else
      {
        v551 = 0;
      }
      if ( UtilDbccGetContext() )
      {
        v315 = UtilDbccGetContext() ? (char *)UtilDbccGetContext() + 12 : 0LL;
        if ( (*(_DWORD *)v315 & 0x4000) != 0 )
          v856 = v314 | 0x100000;
      }
      if ( UtilDbccGetContext() )
        v856 = v69 | 0x200000;
      if ( UtilDbccIsCheckRunning() )
      {
        if ( UtilDbccGetContext() )
          v316 = (char *)UtilDbccGetContext() + 12;
        else
          v316 = 0;
        v552 = v316[2] & 1;
        if ( v552 )
          v856 |= 0x400000u;
      }
      else
      {
        v552 = 0;
      }
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 53) )
        v858 |= 0x40u;
      v70 = CQOFeatureSwitches::FIsSet(v852, 54);
      v71 = v858;
      if ( v70 )
      {
        v71 = v858 | 0x20;
        v858 |= 0x20u;
      }
      if ( (*(_DWORD *)(*((_QWORD *)v495 + 1) + 580LL) & 2) != 0 )
        v858 = v71 | 4;
      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 55) )
      {
        v858 |= 0x10u;
        if ( (v858 & 4) != 0 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v495 + 1) + 1136LL) )
            COptContext::CreatePDWExpressionArrayForIV((COptContext *)v846);
        }
      }
      if ( FPDWUQOFeaturesExposed() )
        v859 |= 2u;
      v711 = 9307;
      v522 = *((_BYTE *)qword_102ECFB10 + 1163) >> 3;
      if ( (v522 & 1) != 0 )
        goto LABEL_607;
      v713 = 0;
      v72 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      if ( v72 && (v73 = *(struct CSessionTraceFlags ***)(v72 + 56), (v74 = *v73) != 0) )
      {
        v652 = *v73;
        if ( CSessionTraceFlags::CheckSessionTraceInternal(v74, 0x245Bu) )
          goto LABEL_607;
      }
      else
      {
        v652 = 0;
      }
      if ( !FUtilNcciAreFlushBufferSyntaxAllowed() )
      {
LABEL_85:
        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 56) )
        {
          if ( v54 && (unsigned __int8)QueryHints::FHintSet(v54, 10)
            || ((v582 = a11,
                 v605 = a11,
                 v605 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                      + SystemThread_TlsIndex)
                                                    + SystemThread_TlsOffset),
                 v317 = v605[10],
                 v318 = *((_BYTE *)v317 + 60),
                 (*((_BYTE *)v317 + 68) & 8) == 0)
              ? (v319 = (v318 & 0x40) != 0)
              : (v319 = v318 >> 7),
                v319) )
          {
            v864 |= 8u;
          }
        }
        v714 = 9390;
        v525 = *((_BYTE *)qword_102ECFB10 + 1173) >> 6;
        if ( (v525 & 1) == 0 )
        {
          v716 = 0;
          v75 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          if ( !v75 || (v76 = *(struct CSessionTraceFlags ***)(v75 + 56), (v77 = *v76) == 0) )
          {
            v653 = 0;
LABEL_90:
            if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 57) && v863 >= 130 )
              goto LABEL_92;
            v78 = v859;
            if ( (v859 & 2) == 0 || (v718 = 10068, v526 = *((_BYTE *)qword_102ECFB10 + 1258) >> 4, (v526 & 1) != 0) )
            {
LABEL_93:
              if ( (v78 & 8) != 0 || (v858 & 8) != 0 && v863 >= 130 )
                v859 = v78 | 4;
              if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 58)
                || v863 >= 140 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 59) )
              {
                v860 |= 1u;
              }
              if ( !UtilDbccIsCheckRunning() )
              {
                v722 = 9307;
                v528 = *((_BYTE *)qword_102ECFB10 + 1163) >> 3;
                if ( (v528 & 1) == 0 )
                {
                  v723 = 0;
                  v79 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( !v79 || (v80 = *(struct CSessionTraceFlags ***)(v79 + 56), (v81 = *v80) == 0) )
                  {
                    v656 = 0;
LABEL_104:
                    if ( !FUtilNcciAreFlushBufferSyntaxAllowed() )
                    {
                      v82 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                    + SystemThread_TlsIndex)
                                                  + SystemThread_TlsOffset
                                                  + 8LL)
                                      + 72LL);
                      v83 = (COptContext *)(v82 - 8);
                      if ( !v82 )
                        v83 = 0;
                      if ( COptContext::FTraceFlagIsOn(v83, 0x24EDu) )
                        goto LABEL_109;
                    }
                    goto LABEL_108;
                  }
                  v656 = *v80;
                  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v81, 0x245Bu) )
                    goto LABEL_104;
                }
              }
LABEL_108:
              v864 |= 0x10u;
LABEL_109:
              if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 60) )
                v864 |= 0x20u;
              if ( v569 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 61) && !v847 )
              {
                v724 = 8537;
                v323 = (CQoTelemetryAgg *)operator new(
                                            0x278u,
                                            v848,
                                            "sql\\ntdbms\\query\\qeoptim\\engine\\qeoptim.cpp",
                                            8537,
                                            1u);
                v715 = (CExecLvlRepresentation **)v323;
                if ( v323 )
                  v324 = CQoTelemetryAgg::CQoTelemetryAgg(v323, v848);
                else
                  v324 = 0;
                v893 = v324;
              }
              if ( v54 && (unsigned __int8)QueryHints::FHintSet(v54, 7) )
                goto LABEL_633;
              v725 = 4139;
              v529 = *((_BYTE *)qword_102ECFB10 + 517) >> 3;
              if ( (v529 & 1) != 0 )
                goto LABEL_633;
              v730 = 0;
              v84 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset);
              if ( !v84 || (v85 = *(struct CSessionTraceFlags ***)(v84 + 56), (v86 = *v85) == 0) )
              {
                v657 = 0;
                goto LABEL_118;
              }
              v657 = *v85;
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v86, 0x102Bu) )
LABEL_633:
                v864 |= 0x40u;
LABEL_118:
              if ( !v54 || !(unsigned __int8)QueryHints::FHintSet(v54, 8) )
              {
                v625 = 4138;
                v530 = *((_BYTE *)qword_102ECFB10 + 517) >> 2;
                if ( (v530 & 1) == 0 )
                {
                  v626 = 0;
                  v87 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                  + SystemThread_TlsOffset);
                  if ( !v87 || (v88 = *(struct CSessionTraceFlags ***)(v87 + 56), (v89 = *v88) == 0) )
                  {
                    v658 = 0;
LABEL_124:
                    if ( v863 >= 140 && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 62) )
                    {
                      v90 = 1;
                    }
                    else
                    {
                      v865 &= ~1u;
                      v90 = 0;
                    }
                    v531 = v90;
                    if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 63) )
                      goto LABEL_489;
                    if ( v863 < 140 && (v861 & 0x10) == 0 )
                    {
                      v627 = 9939;
                      v532 = *((_BYTE *)qword_102ECFB10 + 1242) >> 3;
                      if ( (v532 & 1) == 0 )
                      {
                        v628 = 0;
                        v238 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset;
                        if ( !*(_QWORD *)v238
                          || (v239 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v238 + 56LL), (v240 = *v239) == 0) )
                        {
                          v659 = 0;
LABEL_489:
                          v865 &= ~2u;
                          v91 = 0;
LABEL_130:
                          v513 = v91;
                          if ( v490 )
                            v865 |= 8u;
                          v629 = 9358;
                          v519 = *((_BYTE *)qword_102ECFB10 + 1169) >> 6;
                          if ( (v519 & 1) != 0 )
                            goto LABEL_139;
                          v630 = 0;
                          v92 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset;
                          if ( *(_QWORD *)v92
                            && (v93 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v92 + 56LL), (v94 = *v93) != 0) )
                          {
                            v660 = *v93;
                            if ( CSessionTraceFlags::CheckSessionTraceInternal(v94, 0x248Eu) )
                              goto LABEL_139;
                          }
                          else
                          {
                            v660 = 0;
                          }
                          if ( (v863 < 130 || (v861 & 0x10) == 0) && v863 < 140 )
                          {
LABEL_140:
                            v631 = 176;
                            v514 = *((_BYTE *)qword_102ECFB10 + 22);
                            if ( (v514 & 1) == 0 )
                            {
                              v632 = 0;
                              v95 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset);
                              if ( v95 && (v96 = *(struct CSessionTraceFlags ***)(v95 + 56), (v97 = *v96) != 0) )
                              {
                                v661 = *v96;
                                if ( CSessionTraceFlags::CheckSessionTraceInternal(v97, 0xB0u) )
                                  goto LABEL_529;
                              }
                              else
                              {
                                v661 = 0;
                              }
                              if ( v863 < 150 && (v861 & 0x10) == 0 )
                              {
LABEL_146:
                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 64) )
                                {
                                  if ( v54 && (unsigned __int8)QueryHints::FHintSet(v54, 20) )
                                    goto LABEL_152;
                                  if ( v863 >= 150 || (v861 & 0x10) != 0 )
                                    v859 |= 0x10u;
                                }
                                if ( !v54 )
                                {
LABEL_153:
                                  v633 = 8649;
                                  v515 = *((_BYTE *)qword_102ECFB10 + 1081) >> 1;
                                  if ( (v515 & 1) == 0 )
                                  {
                                    v634 = 0;
                                    v98 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset;
                                    if ( !*(_QWORD *)v98
                                      || (v99 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v98 + 56LL),
                                          (v100 = *v99) == 0) )
                                    {
                                      v662 = 0;
                                      goto LABEL_157;
                                    }
                                    v662 = *v99;
                                    if ( !CSessionTraceFlags::CheckSessionTraceInternal(v100, 0x21C9u) )
                                    {
LABEL_157:
                                      v635 = 9423;
                                      if ( !(*((_BYTE *)qword_102ECFB10 + 1177) >> 7) )
                                      {
                                        v636 = 0;
                                        v101 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset);
                                        if ( v101
                                          && (v102 = *(struct CSessionTraceFlags ***)(v101 + 56), (v103 = *v102) != 0) )
                                        {
                                          v539 = *v102;
                                          if ( CSessionTraceFlags::CheckSessionTraceInternal(v103, 0x24CFu) )
                                            goto LABEL_531;
                                        }
                                        else
                                        {
                                          v539 = 0;
                                        }
                                        if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 65) || v863 < 150 )
                                        {
LABEL_163:
                                          if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 66)
                                            && (v863 >= 140 || (v861 & 0x10) != 0) )
                                          {
                                            v861 |= 2u;
                                          }
                                          v715 = a11;
                                          v606 = a11;
                                          if ( !v54 || !(unsigned __int8)QueryHints::FHintSet(v54, 16) )
                                          {
                                            v606 = *(CExecLvlRepresentation ***)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset);
                                            v104 = v606[10];
                                            v105 = *((_BYTE *)v104 + 64);
                                            if ( (*((_BYTE *)v104 + 68) & 8) != 0 )
                                              v105 >>= 1;
                                            if ( (v105 & 1) == 0
                                              && ((unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 67) && v863 >= 150
                                               || (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 68)) )
                                            {
                                              v867 |= 0x10u;
                                            }
                                          }
                                          if ( !v894 )
                                            COptContext::StartCECalculatorContainer((COptContext *)v846);
                                          if ( ((unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 69)
                                             || (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 70) && v863 >= 150)
                                            && *((_DWORD *)s_pServerConf + 2) == 2
                                            && !CExecLvlRepresentation::FInternal(v495) )
                                          {
                                            if ( v54 && (unsigned __int8)QueryHints::FHintSet(v54, 17) )
                                            {
LABEL_180:
                                              if ( (unsigned __int8)QueryHints::FHintSet(v54, 13) )
                                              {
LABEL_644:
                                                v866 |= 0x10u;
LABEL_182:
                                                if ( (!v54 || !(unsigned __int8)QueryHints::FHintSet(v54, 42))
                                                  && !*(_BYTE *)(v850 + 37) )
                                                {
                                                  v870 |= 4u;
                                                }
                                                if ( !*(_BYTE *)(v850 + 38) )
                                                  v870 |= 8u;
                                                v106 = v857;
                                                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                          + SystemThread_TlsIndex)
                                                                                        + SystemThread_TlsOffset)
                                                                            + 128LL)
                                                                + 76LL)
                                                    & 0x8000000) != 0 )
                                                {
                                                  LOBYTE(v106) = v857 | 2;
                                                  v857 |= 2u;
                                                }
                                                v107 = *(_QWORD *)(*((_QWORD *)v495 + 1) + 40LL);
                                                if ( v107
                                                  && *(_QWORD *)v107
                                                  && (*(_BYTE *)(*(_QWORD *)v107 + 144LL) & 1) != 0 )
                                                {
                                                  LOBYTE(v106) = v106 | 4;
                                                  v857 = v106;
                                                }
                                                if ( *(_DWORD *)(qword_102ECFB00 + 14504)
                                                  && !*(_BYTE *)(GetXdbServerGlobals(v106) + 16289) )
                                                {
                                                  v861 &= ~1u;
                                                }
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 71)
                                                  && v863 >= 140 )
                                                {
                                                  v866 |= 0x80u;
                                                }
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 73) )
                                                  v868 |= 8u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 75) )
                                                  v868 |= 4u;
                                                if ( *(_QWORD *)(GetSqlServerGlobals() + 40) )
                                                  v889 = *(_QWORD *)(GetSqlServerGlobals() + 40);
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 76) )
                                                  v866 |= 1u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 77)
                                                  && v863 >= 140
                                                  && *((_DWORD *)s_pServerConf + 2) == 2
                                                  && !CExecLvlRepresentation::FInternal(v495)
                                                  && (*((_BYTE *)v495 + 128) & 4) == 0
                                                  && (!v54 || !(unsigned __int8)QueryHints::FHintSet(v54, 14))
                                                  && !*(_BYTE *)(v850 + 32) )
                                                {
                                                  v866 |= 8u;
                                                }
                                                if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30) == 251 )
                                                {
                                                  v768 = v30;
                                                  v241 = 0;
                                                  v242 = *(CDataExportParameters **)(v30 + 784);
                                                  if ( v242 )
                                                    v241 = CDataExportParameters::DeepCopy(v242, v492);
                                                  v895 = v241;
                                                }
                                                v108 = v509;
                                                (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v509 + 96LL))(v509);
                                                v769 = 0;
                                                v770 = 0;
                                                if ( *(_QWORD *)(v30 + 688) )
                                                {
                                                  v772 = &v899;
                                                  v110 = *(_QWORD *)(v30 + 688);
                                                  if ( v899 < v110 )
                                                    v111 = 0;
                                                  else
                                                    v111 = (struct CSessionTraceFlags *)(v899 - v110);
                                                  v539 = v111;
                                                  v664 = v111;
                                                  v765[3] = &v901;
                                                  v112 = *(_QWORD *)(v30 + 696);
                                                  if ( v901 < v112 )
                                                    v113 = 0;
                                                  else
                                                    v113 = (struct CSessionTraceFlags *)(v901 - v112);
                                                  v539 = v113;
                                                  v665 = v113;
                                                  LOBYTE(v109) = 1;
                                                  COptRsrcInfoHelper::SetCompTime(v622, &v664, v109, 0);
                                                  COptRsrcInfoHelper::SetCompTime(
                                                    v622,
                                                    &v665,
                                                    v114,
                                                    (unsigned __int8)v114);
                                                }
                                                v115 = a11[20];
                                                if ( *((_QWORD *)v115 + 17) )
                                                {
                                                  v869 |= 0x80u;
                                                  v325 = (int *)*((_QWORD *)v115 + 17);
                                                  if ( v325 )
                                                    v326 = *v325;
                                                  else
                                                    v326 = 0;
                                                  v898 = v326;
                                                }
                                                COptContext::SetHints((COptContext *)v846, v54);
                                                OptimizerUtil::ProcessHintsTelemetry(
                                                  (const struct COptContext *)v846,
                                                  v492,
                                                  v54,
                                                  v533);
                                                COptContext::ComputeHardwareDependentProperties(
                                                  (COptContext *)v846,
                                                  v54);
                                                if ( *((_QWORD *)a11[16] + 63) )
                                                {
                                                  v327 = (*(__int64 (__fastcall **)(__int64, CExecLvlRepresentation **))(*(_QWORD *)v30 + 1056LL))(
                                                           v30,
                                                           a11);
                                                  v328 = IQNManager::x_qntStmtInvalid;
                                                  if ( v327 )
                                                    v328 = 0;
                                                  v885 = v328;
                                                }
                                                if ( *(_QWORD *)(v30 + 600) )
                                                {
                                                  v882 = *(_QWORD *)(v30 + 600);
                                                  v329 = *(_QWORD *)(v30 + 600);
                                                  if ( v329 )
                                                  {
                                                    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v329 + 24LL))(v329) == 1 )
                                                      v883 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v30 + 600) + 16LL)
                                                                                               + 8LL))(*(_QWORD *)(*(_QWORD *)(v30 + 600) + 16LL));
                                                  }
                                                }
                                                v117 = *(_BYTE *)(v30 + 568);
                                                v118 = v855;
                                                if ( (v117 & 0x20) != 0 )
                                                {
                                                  v118 = v855 | 0x40000;
                                                  v855 |= 0x40000u;
                                                  v117 = *(_BYTE *)(v30 + 568);
                                                }
                                                v119 = (v117 & 8) == 0;
                                                v120 = v856;
                                                if ( !v119 )
                                                {
                                                  v120 = v856 | 0x2000;
                                                  v856 |= 0x2000u;
                                                }
                                                if ( (*(_BYTE *)(v30 + 570) & 8) != 0 )
                                                {
                                                  v118 |= 0x80000u;
                                                  v855 = v118;
                                                }
                                                if ( (*(_BYTE *)(v30 + 571) & 0x10) != 0 )
                                                {
                                                  v118 |= 0x100000u;
                                                  v855 = v118;
                                                }
                                                if ( *(char *)(v30 + 569) < 0 )
                                                {
                                                  v856 = v120 | 0x4000;
                                                  LOBYTE(v116) = 1;
                                                  CExecLvlRepresentation::SetNotCacheable(v495, 41, v116);
                                                  v120 = v856;
                                                  v118 = v855;
                                                }
                                                v121 = *(_BYTE *)(v30 + 570);
                                                if ( (v121 & 1) != 0 )
                                                {
                                                  v120 |= 0x8000u;
                                                  v856 = v120;
                                                  v121 = *(_BYTE *)(v30 + 570);
                                                }
                                                if ( (v121 & 2) != 0 )
                                                  v856 = v120 | 0x10000;
                                                v122 = *(_BYTE *)(v30 + 569);
                                                if ( (v122 & 4) != 0 )
                                                {
                                                  v762 = xmmword_1026A3440;
                                                  (*(void (__fastcall **)(struct IQueryCompile *, __int128 *))(*(_QWORD *)v509 + 8LL))(
                                                    v509,
                                                    &v762);
                                                  v637 = 2924;
                                                  v766 = (struct IMemObj *)*((_QWORD *)v512 + 48);
                                                  v330 = operator new(
                                                           0x18u,
                                                           v766,
                                                           "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                           2924,
                                                           3u);
                                                  v771 = v330;
                                                  if ( v330 )
                                                  {
                                                    *v330 = &CEnvElem::`vftable';
                                                    v330[1] = 0;
                                                    v330[2] = 0;
                                                    *v330 = &CNeedStrictSetOpts::`vftable';
                                                  }
                                                  else
                                                  {
                                                    v330 = 0;
                                                  }
                                                  CEnvCollection::AddEnvElem(v512, (struct CEnvElem *)v330);
                                                  v122 = *(_BYTE *)(v30 + 569);
                                                  v118 = v855;
                                                }
                                                if ( (v122 & 8) != 0 )
                                                  v855 = v118 | 0x10000;
                                                if ( (*(_BYTE *)(v30 + 571) & 0x10) != 0 )
                                                {
                                                  v763 = xmmword_10255BFE0;
                                                  (*(void (__fastcall **)(struct IQueryCompile *, __int128 *))(*(_QWORD *)v108 + 8LL))(
                                                    v108,
                                                    &v763);
                                                }
                                                if ( *(char *)(v30 + 720) < 0 )
                                                  v857 |= 0x40u;
                                                if ( v863 >= 150 || (v861 & 0x10) != 0 )
                                                  (*(void (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v108
                                                                                                 + 408LL))(v108);
                                                if ( (*(_BYTE *)(v30 + 720) & 0x20) != 0 )
                                                  v870 |= 0x80u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 78)
                                                  && (v863 >= 150
                                                   && *(_BYTE *)(qword_102ECFB00 + 48768)
                                                   && *(_BYTE *)(qword_102ECFB00 + 48772)
                                                   || v863 >= 160
                                                   || (v861 & 0x10) != 0) )
                                                {
                                                  v868 |= 0x20u;
                                                }
                                                v666 = v846;
                                                v709 = &v666;
                                                v596 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                           + SystemThread_TlsIndex)
                                                                                         + SystemThread_TlsOffset)
                                                                             + 176LL)
                                                                 + 32LL);
                                                v123 = ((*(_DWORD *)(*((_QWORD *)v495 + 1) + 32LL) & 4) != 0
                                                     || CExecLvlRepresentation::FStoredProc(v495))
                                                    && *(_DWORD *)(v596 + 72) == 193
                                                    && *(_WORD *)(v596 + 226) != 4;
                                                v124 = COptContext::InitializeInterleavedExec((COptContext *)v846, v123);
                                                CExecLvlRepresentation::InitializeForInterleavedExec(v495, v124, v492);
                                                if ( *((_BYTE *)v495 + 88) )
                                                  v866 |= 2u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 201) )
                                                  v871 |= 4u;
                                                if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 215) )
                                                  v871 |= 8u;
                                                if ( *(_BYTE *)(GetXdbServerGlobals(v125) + 12004) )
                                                {
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 119) )
                                                    v868 |= 0x40u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 79) )
                                                    v868 |= 0x80u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 85) )
                                                    v869 |= 1u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 86) )
                                                    v869 |= 2u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 87) )
                                                    v869 |= 4u;
                                                  v126 = CurrentDb;
                                                  v331 = g_dbtableFactory[4](CurrentDb);
                                                  v502 = *(_BYTE *)(GetXdbServerGlobals(v332) + 12004);
                                                  if ( v502 && *(_QWORD *)(v331 + 5320) )
                                                    v869 |= 8u;
                                                }
                                                else
                                                {
                                                  v126 = CurrentDb;
                                                }
                                                if ( (unsigned int)IsVDWOrFidoInstance() )
                                                {
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 127) )
                                                    v869 |= 0x20u;
                                                  if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 126) )
                                                    v869 |= 0x10u;
                                                }
                                                if ( IsXDBDwPestoInstance() )
                                                {
                                                  LODWORD(v573) = *(_DWORD *)(v850 + 48);
                                                  v553 = (unsigned __int16)v573;
                                                  v717 = qword_102ECFB00;
                                                  v333 = *(_QWORD *)(qword_102ECFB00 + 32);
                                                  v667 = v333;
                                                  switch ( (unsigned __int16)v573 )
                                                  {
                                                    case 0x7FFCu:
                                                      v334 = *(DBTABLE **)(v333 + 104);
                                                      break;
                                                    case 0x7FFDu:
                                                      v334 = *(DBTABLE **)(v333 + 112);
                                                      break;
                                                    case 0x7FFFu:
                                                      v334 = *(DBTABLE **)(v333 + 88);
                                                      break;
                                                    default:
                                                      if ( (unsigned int)(unsigned __int16)v573 > *(_DWORD *)(v333 + 76)
                                                        || !(_WORD)v573 )
                                                      {
                                                        goto LABEL_266;
                                                      }
                                                      _mm_lfence();
                                                      v334 = *(DBTABLE **)(*(_QWORD *)(v667 + 40) + 8LL * (v553 - 1));
                                                      v126 = CurrentDb;
                                                      break;
                                                  }
                                                  if ( v334 && DBTABLE::IsDwPestoDistributionDb(v334) )
                                                    v870 |= 0x10u;
                                                }
LABEL_266:
                                                v127 = g_dbtableFactory[4](v126);
                                                v128 = RecoveryUnit::GetOnDiskVersion(*(RecoveryUnit **)(v127 + 4624));
                                                if ( (byte_102EDCD04 || (*((_BYTE *)qword_102ECFB10 + 1625) & 0x10) != 0)
                                                  && v128 >= 0x3ABu )
                                                {
                                                  v870 |= 1u;
                                                  v717 = *(_QWORD *)(SystemThread_TlsOffset
                                                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + SystemThread_TlsIndex));
                                                  v335 = *(_QWORD *)(v717 + 80);
                                                  v336 = *(_BYTE *)(v335 + 66);
                                                  if ( (*(_BYTE *)(v335 + 68) & 8) != 0 )
                                                    v336 >>= 1;
                                                  if ( (v336 & 1) != 0 || (v337 = *((_BYTE *)v65 + 17), (v337 & 8) != 0) )
                                                  {
                                                    v338 = 0;
                                                    v337 = *((_BYTE *)v65 + 17);
                                                  }
                                                  else
                                                  {
                                                    v338 = 1;
                                                  }
                                                  v498 = v338;
                                                  v499 = (v337 & 4) != 0;
                                                  if ( (*((_BYTE *)qword_102ECFB10 + 1626) & 4) == 0 )
                                                  {
                                                    v339 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + SystemThread_TlsIndex)
                                                                     + SystemThread_TlsOffset);
                                                    if ( !v339
                                                      || (v340 = **(struct CSessionTraceFlags ***)(v339 + 56)) == 0
                                                      || !CSessionTraceFlags::CheckSessionTraceInternal(v340, 0x32D2u) )
                                                    {
                                                      v341 = *(DBTABLE **)(*(_QWORD *)(v127 + 4624) + 1712LL);
                                                      if ( (*((_BYTE *)v341 + 60) & 1) != 0
                                                        && !DBTABLE::IsCOWReplicaDatabase(v341)
                                                        && (v498 || v499) )
                                                      {
                                                        v870 |= 2u;
                                                      }
                                                    }
                                                  }
                                                  v126 = CurrentDb;
                                                }
                                                v129 = *((_QWORD *)v495 + 8);
                                                if ( v129 )
                                                {
                                                  v668 = *((_QWORD *)v495 + 8);
                                                  if ( *(_QWORD *)(v129 + 8) || *(_QWORD *)(v129 + 128) )
                                                    *(_BYTE *)(v129 + 704) = 0;
                                                  v342 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset;
                                                  v343 = *(_QWORD **)(v342 + 256);
                                                  if ( !v343 )
                                                  {
                                                    SystemThread::MakeMiniSOSThread(0);
                                                    v343 = *(_QWORD **)(v342 + 256);
                                                  }
                                                  if ( v343[107] )
                                                  {
                                                    v345 = __rdtsc();
                                                    v346 = v343[108];
                                                    if ( v345 <= v346 )
                                                      v347 = 0;
                                                    else
                                                      v347 = v345 - v346;
                                                    v344 = v347 + v343[109];
                                                  }
                                                  else
                                                  {
                                                    v344 = 0;
                                                  }
                                                  *(_QWORD *)(v129 + 8) = v344;
                                                  *(_QWORD *)(v668 + 128) = __rdtsc();
                                                  v126 = CurrentDb;
                                                }
                                                v544 = 0;
                                                v740 = v30;
                                                *(_QWORD *)(v30 + 384) = a11;
                                                v130 = v568;
                                                v131 = CRelOp_Query::PrepareQueryForQP((CRelOp_Query *)v30, v533, v568);
                                                v493 = v131;
                                                if ( *(_BYTE *)(v30 + 581) )
                                                  v855 |= 1u;
                                                if ( (v856 & 8) != 0 )
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
                                                  v132 = v858 | 4;
                                                  v858 |= 4u;
                                                }
                                                else
                                                {
                                                  v132 = v858;
                                                }
                                                if ( (v132 & 4) != 0
                                                  && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 74) )
                                                {
                                                  v868 |= 1u;
                                                }
                                                if ( (!*(_BYTE *)(qword_102ECFB00 + 48768)
                                                   || !*(_BYTE *)(qword_102ECFB00 + 48772))
                                                  && v862 > -1
                                                  && (v861 & 0x20) == 0 )
                                                {
                                                  ex_raise(1, 2, 16, 31, 34, L"SCALEOUTEXECUTION");
                                                }
                                                if ( (*(_BYTE *)(v30 + 720) & 0x40) != 0 )
                                                {
                                                  v133 = v492;
                                                  if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 80) )
                                                  {
                                                    v131 = PexprGraphOptimization(v131, v492, v126);
                                                    v493 = v131;
                                                  }
                                                }
                                                else
                                                {
                                                  v133 = v492;
                                                }
                                                if ( v490 )
                                                {
                                                  if ( (*(_BYTE *)(v30 + 721) & 1) != 0
                                                    && (*(unsigned __int8 (__fastcall **)(struct IQueryCompile *))(*(_QWORD *)v509 + 368LL))(v509) )
                                                  {
                                                    v554 = v126;
                                                    OptimizerUtil::FindNode<CFireApproxQueryProcessingCompileXEvents>(
                                                      v131,
                                                      &v554);
                                                  }
                                                  if ( v569 && (*(_BYTE *)(v30 + 721) & 0xC) != 0 )
                                                  {
                                                    v638 = 3208;
                                                    v348 = operator new(
                                                             0x20u,
                                                             v133,
                                                             "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                             3208,
                                                             1u);
                                                    v349 = (unsigned __int64)v348;
                                                    v741 = v348;
                                                    if ( v348 )
                                                    {
                                                      v742 = v492;
                                                      v743 = v492;
                                                      v744 = v492;
                                                      *(_QWORD *)v348 = v492;
                                                      v348[3] = 0;
                                                      v348[4] = 6;
                                                      *((_QWORD *)v348 + 3) = 0;
                                                    }
                                                    else
                                                    {
                                                      v349 = 0;
                                                    }
                                                    v544 = v349;
                                                    v350 = *(_BYTE *)(v30 + 721);
                                                    if ( (v350 & 4) != 0 )
                                                    {
                                                      v735 = v126;
                                                      v736 = v492;
                                                      v738 = v349;
                                                      v737 = 0;
                                                      OptimizerUtil::FindNode<CAddPercentileCompileXEvents>(v131, &v735);
                                                      v350 = *(_BYTE *)(v30 + 721);
                                                    }
                                                    if ( (v350 & 8) != 0 )
                                                    {
                                                      v732 = v126;
                                                      v733 = v492;
                                                      v734 = v349;
                                                      OptimizerUtil::FindNode<CAddApproxPercentileCompileXEvents>(
                                                        v131,
                                                        &v732);
                                                    }
                                                  }
                                                }
                                                if ( !(unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 1)
                                                  && a9 != 194
                                                  && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v30 + 192LL))(v30) )
                                                {
                                                  v857 |= 0x20u;
                                                }
                                                v134 = *(CMATGen **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v130 + 4)
                                                                                           + 160LL)
                                                                               + 8LL)
                                                                   + 1088LL);
                                                if ( v134 )
                                                {
                                                  v351 = *(_QWORD **)(*(_QWORD *)(v30 + 368) + 8LL);
                                                  for ( i = v351; i; i = v351 )
                                                  {
                                                    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD *))(*v351 + 96LL))(
                                                      v351,
                                                      *((_QWORD *)v134 + 99),
                                                      (_QWORD *)v134 + 103);
                                                    v351 = (_QWORD *)v351[1];
                                                  }
                                                  CMATGen::AppendColumnEncryptionKeys(v134, (struct CRelOp_Query *)v30);
                                                }
                                                *(_QWORD *)(v30 + 384) = 0;
                                                if ( (v865 & 4) != 0 )
                                                {
                                                  v639 = 3259;
                                                  v353 = v598;
                                                  v354 = (char *)operator new(
                                                                   0x30u,
                                                                   v598,
                                                                   "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                   3259,
                                                                   1u);
                                                  v355 = (struct DRgCId *)v354;
                                                  v745 = v354;
                                                  if ( v354 )
                                                  {
                                                    v502 = 0;
                                                    v746 = v353;
                                                    v747 = v353;
                                                    v356 = v354 + 16;
                                                    v748 = v356;
                                                    v749 = v353;
                                                    *(_QWORD *)v356 = v353;
                                                    v356[8] = 0;
                                                    *((_DWORD *)v356 + 3) = 0;
                                                    *((_DWORD *)v356 + 4) = 1;
                                                    *((_QWORD *)v356 + 3) = 0;
                                                    *(_QWORD *)v355 = &CRefCount::`vftable';
                                                    *((_DWORD *)v355 + 2) = 1;
                                                    *(_QWORD *)v355 = &DRgCId::`vftable';
                                                  }
                                                  else
                                                  {
                                                    v355 = 0;
                                                  }
                                                  COptExpr::ExtractOutputColumns(v131, v353, v355);
                                                  v357 = v355;
                                                  v358 = XteBuilderObject;
                                                  XteDummyConstScanWithOutput = CreateXteDummyConstScanWithOutput(
                                                                                  XteBuilderObject,
                                                                                  v357,
                                                                                  v508);
                                                  v534 = (struct IQueryObj *)(*(__int64 (__fastcall **)(struct IXteBuilder *, struct CQte *))(*(_QWORD *)v358 + 568LL))(
                                                                               v358,
                                                                               XteDummyConstScanWithOutput);
                                                  (*(void (__fastcall **)(struct IQueryObj *, const struct CStatementDescription *, bool))(*(_QWORD *)v534 + 600LL))(
                                                    v534,
                                                    v599,
                                                    a14);
                                                  (*(void (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v534 + 560LL))(v534);
                                                  (*(void (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v534 + 624LL))(v534);
                                                  v119 = (*((_DWORD *)v131 + 2))-- == 1;
                                                  if ( v119 )
                                                    (**(void (__fastcall ***)(struct COptExpr *, __int64))v131)(v131, 1);
                                                  v188 = v495;
                                                  *((_BYTE *)v495 + 44) &= ~8u;
                                                  v886 = 0;
                                                  *(_QWORD *)(*(_QWORD *)(v849 + 56) + 40LL) = 0;
                                                  *(_QWORD *)(*(_QWORD *)(v849 + 64) + 40LL) = 0;
                                                  v545[7] = 0;
                                                  v201 = (const struct CCompExecCtxtStmt *)a11;
LABEL_460:
                                                  if ( v870 < 0 )
                                                    *(_BYTE *)(v30 + 720) |= 0x20u;
                                                  SOS_AutoOutOfScope__lambda_4a84f5ffa16570040bfa82ea971820d2___::_SOS_AutoOutOfScope__lambda_4a84f5ffa16570040bfa82ea971820d2___(&v709);
                                                  COptContext::~COptContext((COptContext *)v846);
                                                  ExcHandler::~ExcHandler((ExcHandler *)v773);
                                                  goto LABEL_1154;
                                                }
                                                v135 = v854;
                                                if ( (v853 & 0x1000) != 0 )
                                                {
                                                  v360 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset
                                                                               + 8LL)
                                                                   + 72LL);
                                                  v361 = v360 - 8;
                                                  if ( !v360 )
                                                    v361 = 0;
                                                  if ( (*(_DWORD *)(v361 + 92) & 0x1000) != 0
                                                    && *(_DWORD *)(*(_QWORD *)(v361 + 640) + 52LL) )
                                                  {
                                                    v864 |= 0x10u;
                                                    v131 = v493;
                                                    goto LABEL_289;
                                                  }
                                                  v135 = v854;
                                                  v131 = v493;
                                                }
                                                if ( (v864 & 1) != 0
                                                  || (v856 & 0x2000) != 0
                                                  || (v135 & 1) != 0
                                                  || (v861 & 1) == 0 )
                                                {
                                                  v864 &= ~0x10u;
                                                }
LABEL_289:
                                                v136 = v495;
                                                v137 = *((_QWORD *)v495 + 8);
                                                if ( v137 )
                                                {
                                                  v669 = *((_QWORD *)v495 + 8);
                                                  if ( !*(_QWORD *)(v137 + 8) || !*(_QWORD *)(v137 + 128) )
                                                    *(_BYTE *)(v137 + 704) = 0;
                                                  v362 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                         + SystemThread_TlsIndex)
                                                       + SystemThread_TlsOffset;
                                                  v363 = *(_QWORD **)(v362 + 256);
                                                  if ( !v363 )
                                                  {
                                                    SystemThread::MakeMiniSOSThread(0);
                                                    v363 = *(_QWORD **)(v362 + 256);
                                                  }
                                                  if ( v363[107] )
                                                  {
                                                    v367 = __rdtsc();
                                                    v368 = v363[108];
                                                    if ( v367 <= v368 )
                                                      v369 = 0;
                                                    else
                                                      v369 = v367 - v368;
                                                    v364 = v369 + v363[109];
                                                  }
                                                  else
                                                  {
                                                    v364 = 0;
                                                  }
                                                  v365 = v669;
                                                  *(_QWORD *)(v669 + 248) += v364 - *(_QWORD *)(v137 + 8);
                                                  v366 = __rdtsc();
                                                  *(_QWORD *)(v365 + 368) += (((unsigned __int64)HIDWORD(v366) << 32)
                                                                            | (unsigned int)v366)
                                                                           - *(_QWORD *)(v365 + 128);
                                                  *(_QWORD *)(v137 + 8) = 0;
                                                  *(_QWORD *)(v365 + 128) = 0;
                                                  ++*(_DWORD *)(v365 + 484);
                                                  v131 = v493;
                                                }
                                                CTabRefIDUtil::AssignTabRefID(v492, v131);
                                                v138 = *(_QWORD *)(v30 + 648);
                                                if ( v138 )
                                                {
                                                  v370 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v138 + 16)
                                                                                           + 24LL))(*(_QWORD *)(v138 + 16));
                                                  v371 = *(_QWORD **)(v138 + 16);
                                                  if ( v370 == 99 )
                                                  {
                                                    v877 = v371[8];
                                                  }
                                                  else if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v371 + 24LL))(v371) == 98 )
                                                  {
                                                    v878 = *(_QWORD *)(v138 + 16) + 64LL;
                                                  }
                                                }
                                                v139 = *(_QWORD *)(v30 + 120);
                                                v140 = 0;
                                                if ( v139 )
                                                {
                                                  v243 = *(_QWORD *)(v139 + 208);
                                                  if ( v243 )
                                                    v244 = *(_QWORD *)(v243 + 8);
                                                  else
                                                    LODWORD(v244) = 0;
                                                  if ( (v244 & 0x8000000) != 0 )
                                                    v140 = 1;
                                                }
                                                v141 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v30
                                                                                                  + 1104LL))(v30)
                                                    && (*(_BYTE *)(v30 + 573) & 2) == 0;
                                                v142 = 0;
                                                if ( v139
                                                  && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 178)
                                                  && *(char *)(v139 + 537) < v142 )
                                                {
                                                  v142 = CAlgTableMetadata::FBulkContainJsonCol(
                                                           (CAlgTableMetadata *)v139,
                                                           (struct CRelOp_Query *)v30);
                                                }
                                                if ( v140 || (*(_BYTE *)(v30 + 569) & 0x10) != 0 )
                                                {
                                                  v143 = v856;
                                                  LODWORD(v143) = v856 | 0x2000000;
                                                  v856 |= 0x2000000u;
                                                }
                                                else
                                                {
                                                  v143 = v856;
                                                }
                                                if ( !v142 && (v140 || v141) )
                                                {
                                                  LODWORD(v143) = v143 | 0x4000000;
                                                  v856 = v143;
                                                }
                                                if ( (v853 & 0x1000) != 0 )
                                                {
                                                  v143 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                 + SystemThread_TlsIndex)
                                                                               + SystemThread_TlsOffset
                                                                               + 8LL)
                                                                   + 72LL);
                                                  v372 = v143 - 8;
                                                  if ( !v143 )
                                                    v372 = 0;
                                                  if ( (*(_DWORD *)(v372 + 92) & 0x1000) != 0
                                                    && *(_DWORD *)(*(_QWORD *)(v372 + 640) + 52LL) )
                                                  {
                                                    v373 = (_QWORD *)v884;
                                                    v374 = *(_DWORD *)(v884 + 8);
                                                    v555 = 0;
                                                    for ( j = 0; j < v374; v555 = j )
                                                    {
                                                      if ( SMD::FNonClusteredColumnStoreIndex(*(struct IMEDIndex **)(*v373 + 8LL * j)) )
                                                        v859 |= 0x80u;
                                                      ++j;
                                                    }
                                                  }
                                                  v131 = v493;
                                                }
                                                if ( *(_BYTE *)(*(_QWORD *)(v30 + 184) + 56LL) )
                                                {
                                                  if ( v863 < 160 && (v144 = v861, (v861 & 0x10) == 0)
                                                    || (v376 = CTrustedMachineHost::FConfigured(v143), v144 = v861, v376) )
                                                  {
                                                    v857 |= 0x80u;
                                                  }
                                                }
                                                else
                                                {
                                                  v144 = v861;
                                                }
                                                if ( (*(_DWORD *)(*((_QWORD *)v495 + 1) + 576LL) & 0x800) != 0 )
                                                  v861 = v144 | 0x40;
                                                if ( !COptBatchUtil::FQuerySupportsBatch((const struct COptContext *)v846) )
                                                {
LABEL_340:
                                                  if ( (v853 & 0x1000) != 0
                                                    && FindNode__PqoBuild_::_415_::CInvolvesColumnstoreIndexBuild_(
                                                         &v524,
                                                         v131) )
                                                  {
                                                    v859 |= 0x40u;
                                                  }
                                                  v157 = *(__int64 **)(*((_QWORD *)v136 + 1) + 40LL);
                                                  if ( (*(_BYTE *)(v851 + 16) & 2) != 0 )
                                                  {
                                                    v157 = (__int64 *)*v157;
                                                    if ( !*((_BYTE *)v157 + 145) )
                                                    {
                                                      v245 = (v157[24] & 6) == 6;
                                                      v246 = **((_QWORD **)v131 + 4);
                                                      if ( (v157[18] & 8) != 0
                                                        && (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v246 + 16)
                                                                                                  + 24LL))(*(_QWORD *)(v246 + 16)) == 29 )
                                                      {
                                                        v246 = **(_QWORD **)(v246 + 32);
                                                      }
                                                      v247 = **(_QWORD **)(**(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v246 + 32) + 8LL)
                                                                                       + 32LL)
                                                                         + 32LL);
                                                      v248 = *(_QWORD *)(*(_QWORD *)(v247 + 32)
                                                                       + 8LL * *(int *)(v247 + 24)
                                                                       - 8);
                                                      if ( v245 )
                                                        v249 = *(_QWORD *)(**(_QWORD **)(v248 + 32) + 16LL);
                                                      else
                                                        v249 = *(_QWORD *)(v248 + 16);
                                                      COptContext::InclForStats(
                                                        (COptContext *)v846,
                                                        *(const struct CValRef **)(v249 + 64));
                                                    }
                                                  }
                                                  LOBYTE(v157) = 124;
                                                  YieldAndCheckForAbort(v157);
                                                  v708 = 0;
                                                  try
                                                  {
                                                    COptContext::PinExpr((COptContext *)v846, &v891, v131);
                                                    if ( (*((_BYTE *)qword_102ECFB10 + 296) & 0x40) == 0 )
                                                    {
                                                      v556 = 0;
                                                      v158 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      if ( *(_QWORD *)v158
                                                        && (v159 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v158 + 56LL)) != 0 )
                                                      {
                                                        v160 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                 v159,
                                                                 0x946u);
                                                      }
                                                      else
                                                      {
                                                        v160 = v556;
                                                      }
                                                      if ( v160 )
                                                      {
                                                        v131 = v493;
                                                      }
                                                      else
                                                      {
                                                        v619 = 1;
                                                        v620 = 0;
                                                        v621 = 0;
                                                        v618 = &CFingerprintUtilEx::`vftable';
                                                        v161 = *((_QWORD *)a11[20] + 17);
                                                        if ( v161 )
                                                        {
                                                          v163 = *(_QWORD *)(v161 + 16);
                                                          v131 = v493;
                                                        }
                                                        else
                                                        {
                                                          v162 = *(QueryHints **)(v30 + 56);
                                                          if ( v162 && *((_DWORD *)v162 + 40) )
                                                            v162 = *(QueryHints **)(v30 + 64);
                                                          v620 = 0;
                                                          v621 = 0;
                                                          if ( v162 )
                                                            QueryHints::ComputeHashsum(
                                                              v162,
                                                              (struct CFingerprintUtil *)&v618);
                                                          v131 = v493;
                                                          CFingerprintUtilEx::GenFingerprintForQueryTree(
                                                            (CFingerprintUtilEx *)&v618,
                                                            v493,
                                                            0);
                                                          v163 = v621;
                                                        }
                                                        (*(void (__fastcall **)(struct IQueryCompile *, __int64))(*(_QWORD *)v509 + 224LL))(
                                                          v509,
                                                          v163);
                                                        v888 = v163;
                                                        v618 = &CRefCount::`vftable';
                                                      }
                                                    }
                                                    v164 = v492;
                                                    COptExpr::DeriveGroupProperties(v131, v492, 1u, 0);
                                                    if ( CTableGroupProperties::FUnBoundParams(*((CTableGroupProperties **)v131
                                                                                               + 10)) )
                                                      ex_raise(86, 24, 16, 17);
                                                    if ( (v861 & 1) != 0 )
                                                      JUMPOUT(0x100470F76LL);
                                                    v500 = 0;
                                                    v377 = FindNode__PqoBuild_::_444_::CReferencesTableWithClusteredColumnstoreIndex_(
                                                             &v500,
                                                             v131);
                                                    if ( v377 )
                                                    {
                                                      v378 = *(CTableMetadata **)(*(_QWORD *)(v377 + 16) + 24LL);
                                                      CTableMetadata::WsDisplayName(v378);
                                                      LODWORD(Locale) = CTableMetadata::CbDisplayName(v378);
                                                      ex_raise(353, 21, 16, 1, Locale, v379);
                                                    }
                                                    g_CRV_QOptconsidermed = 0;
                                                    v165 = COptExpr::PexprFold(v492, v131);
                                                    COptExpr::DeriveGroupProperties(v165, v492, 1u, 0);
                                                    if ( v165 )
                                                    {
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 1075) & 0x20) != 0
                                                        || ((v576 = 0,
                                                             v166 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v166)
                                                         && (v167 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v166 + 56LL)) != 0
                                                          ? (v168 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v167,
                                                                      0x219Du))
                                                          : (v168 = v576),
                                                            v168) )
                                                      {
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v542,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        Stream = TraceStreamHolder::GetStream((TraceStreamHolder *)v542);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v670,
                                                          Stream);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)Stream + 16,
                                                          "*** Converted Tree: ***\n");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v670);
                                                        LOBYTE(v489) = 0;
                                                        LOBYTE(v488) = 1;
                                                        (*(void (__fastcall **)(struct COptExpr *, const char *, const char *, __int64, int, int, int, _QWORD, _QWORD))(*(_QWORD *)v165 + 32LL))(
                                                          v165,
                                                          String2,
                                                          String2,
                                                          4,
                                                          4,
                                                          v488,
                                                          v489,
                                                          0,
                                                          0);
                                                        v381 = TraceStreamHolder::GetStream((TraceStreamHolder *)v542);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v671,
                                                          v381);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v381 + 16,
                                                          "*******************\n");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v671);
                                                        v382 = TraceStreamHolder::GetStream((TraceStreamHolder *)v542);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v672,
                                                          v382);
                                                        std::ostream::flush((char *)v382 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v672);
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v542);
                                                      }
                                                    }
                                                    v169 = *((_QWORD *)v136 + 8);
                                                    if ( v169 )
                                                    {
                                                      v577 = *((_QWORD *)v136 + 8);
                                                      if ( *(_QWORD *)(v169 + 16) || *(_QWORD *)(v169 + 136) )
                                                        *(_BYTE *)(v169 + 704) = 0;
                                                      v383 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      v384 = *(_QWORD **)(v383 + 256);
                                                      if ( !v384 )
                                                      {
                                                        SystemThread::MakeMiniSOSThread(0);
                                                        v384 = *(_QWORD **)(v383 + 256);
                                                      }
                                                      if ( v384[107] )
                                                      {
                                                        v386 = __rdtsc();
                                                        v387 = v384[108];
                                                        if ( v386 <= v387 )
                                                          v388 = 0;
                                                        else
                                                          v388 = v386 - v387;
                                                        v385 = v388 + v384[109];
                                                      }
                                                      else
                                                      {
                                                        v385 = 0;
                                                      }
                                                      *(_QWORD *)(v169 + 16) = v385;
                                                      *(_QWORD *)(v577 + 136) = __rdtsc();
                                                    }
                                                    v540 = *((_QWORD *)v533 + 2);
                                                    v170 = *(_QWORD *)(v540 + 680);
                                                    if ( v170 )
                                                      v15 = *(_DWORD *)(v170 + 28);
                                                    else
                                                      v15 = 0;
                                                    v171 = v15 != 0;
                                                    v172 = 0;
                                                    v535 = 0;
                                                    v543 = 0;
                                                    v173 = 0;
                                                    v511 = 0;
                                                    if ( !CExecLvlRepresentation::FAutoParam(a11[20])
                                                      || (v175 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v174 + 8) + 328LL))(*(_QWORD *)(v174 + 8))) != 0 )
                                                    {
                                                      v175 = 1;
                                                    }
                                                    if ( v171 && v175 )
                                                    {
                                                      v176 = v596;
                                                      v177 = *(_QWORD *)(v596 + 128);
                                                      if ( v177 )
                                                        v178 = *(double *)(v177 + 80);
                                                      else
                                                        v178 = DOUBLE_0_9;
                                                      v640 = 3790;
                                                      v179 = (CInterestingPredicateExplorer *)operator new(
                                                                                                0x38u,
                                                                                                v492,
                                                                                                "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                                                3790,
                                                                                                1u);
                                                      v750 = v179;
                                                      if ( v179 )
                                                        v172 = CInterestingPredicateExplorer::CInterestingPredicateExplorer(
                                                                 v179,
                                                                 v492,
                                                                 v178,
                                                                 v875);
                                                      else
                                                        v172 = 0;
                                                      v535 = v172;
                                                      v180 = COptContext::CheckParameterSensitivePlanEligibility(v846);
                                                      if ( !*((_DWORD *)v172 + 12) )
                                                        *((_DWORD *)v172 + 12) = v180;
                                                      v181 = *(_QWORD *)(v176 + 128);
                                                      if ( v181 )
                                                      {
                                                        *(_DWORD *)v172 = *(_DWORD *)(v181 + 40);
                                                        *((_QWORD *)v172 + 1) = *(_QWORD *)(*(_QWORD *)(v176 + 128)
                                                                                          + 72LL);
                                                      }
                                                      v890 = v172;
                                                    }
                                                    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v30 + 1160LL))(v30) )
                                                    {
                                                      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v165 + 2)
                                                                                                  + 24LL))(*((_QWORD *)v165 + 2)) != 39 )
                                                        goto LABEL_384;
                                                      if ( !IsFidoDWFrontEndSession() )
                                                      {
                                                        v172 = v535;
                                                        v173 = (unsigned int *)v511;
                                                        goto LABEL_384;
                                                      }
                                                      v389 = IsFidoDWFrontEndSession();
                                                      if ( v389 )
                                                      {
                                                        if ( *(_DWORD *)(qword_102ECFB00 + 14504) )
                                                          v389 = *((_BYTE *)qword_102EF3550 + 1651) != 0;
                                                        else
                                                          v389 = 0;
                                                      }
                                                      if ( v389
                                                        && *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v165 + 2) + 24LL) + 772LL) == 1 )
                                                      {
                                                        v172 = v535;
                                                        v173 = (unsigned int *)v511;
                                                        goto LABEL_384;
                                                      }
                                                      v390 = *(_QWORD *)(*(_QWORD *)(**((_QWORD **)v165 + 4) + 80LL)
                                                                       + 208LL);
                                                      if ( v390 )
                                                        v391 = *(_DWORD *)(v390 + 28);
                                                      else
                                                        v391 = 0;
                                                      if ( v391 )
                                                      {
                                                        v172 = v535;
                                                        v173 = (unsigned int *)v511;
                                                        goto LABEL_384;
                                                      }
                                                      v172 = v535;
                                                      v173 = (unsigned int *)v511;
                                                    }
                                                    v868 |= 0x10u;
LABEL_384:
                                                    if ( !(unsigned int)IsVDWFrontendInstance() )
                                                    {
LABEL_385:
                                                      if ( COptContext::FUseOpTreeXML((COptContext *)v846) )
                                                        v182 = COptContext::PqteOptimizeQueryForTreeXml(
                                                                 (COptContext *)v846,
                                                                 v165);
                                                      else
                                                        v182 = COptContext::PqteOptimizeWrapper(
                                                                 (COptContext *)v846,
                                                                 v165);
                                                      v601 = v182;
                                                      LOBYTE(v185) = v863 >= 160
                                                                  || (byte_102EDCD59
                                                                   || (*((_BYTE *)qword_102ECFB10 + 1693) & 0x40) != 0
                                                                    ? (v186 = 1)
                                                                    : (v186 = 0),
                                                                      v186);
                                                      if ( v172 )
                                                      {
                                                        if ( !(_BYTE)v185 && !*((_DWORD *)v172 + 12) )
                                                          *((_DWORD *)v172 + 12) = 31;
                                                        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 37)
                                                          && (*(_BYTE *)(v540 + 580) & 1) != 0
                                                          && (v869 & 0x40) != 0
                                                          && v187 )
                                                        {
                                                          CInterestingPredicateExplorer::PopulateSensitivePredicates(
                                                            v172,
                                                            v492);
                                                          v558 = 0;
                                                          for ( k = 0; ; v558 = k )
                                                          {
                                                            v251 = *((_QWORD *)v172 + 4);
                                                            v252 = v251 ? *(_DWORD *)(v251 + 12) : 0;
                                                            if ( k >= v252 )
                                                              break;
                                                            v253 = *(_QWORD *)(*(_QWORD *)(v251 + 24) + 8LL * k);
                                                            *(_QWORD *)(v253 + 40) = FindStatsInfoForMultiPlan(
                                                                                       v492,
                                                                                       *(struct CValRef **)(*(_QWORD *)(*(_QWORD *)v253 + 16LL) + 64LL),
                                                                                       *(struct CStatsStream **)(v253 + 16),
                                                                                       *((double *)v172 + 2),
                                                                                       (struct CQODouble *)(v253 + 24));
                                                            ++k;
                                                          }
                                                          v540 = *((_QWORD *)v172 + 4);
                                                          if ( v251 )
                                                          {
                                                            v393 = *(_DWORD *)(v251 + 12);
                                                            v507 = v393;
                                                          }
                                                          else
                                                          {
                                                            v393 = 0;
                                                            v507 = 0;
                                                          }
                                                          v543 = *(CMultiPlanFeedback **)(*((_QWORD *)a11[22] + 4)
                                                                                        + 128LL);
                                                          if ( v393 )
                                                          {
                                                            v641 = 3864;
                                                            v394 = (unsigned int *)operator new(
                                                                                     0x20u,
                                                                                     v492,
                                                                                     "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                                     3864,
                                                                                     1u);
                                                            v395 = v394;
                                                            v751 = v394;
                                                            if ( v394 )
                                                            {
                                                              v752 = v492;
                                                              v753 = v492;
                                                              v754 = v492;
                                                              *(_QWORD *)v394 = v492;
                                                              v394[3] = 0;
                                                              v394[4] = 3;
                                                              *((_QWORD *)v394 + 3) = 0;
                                                            }
                                                            else
                                                            {
                                                              v395 = 0;
                                                            }
                                                            if ( v173 != v395 )
                                                            {
                                                              v755 = v173;
                                                              if ( v173 )
                                                              {
                                                                CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>::~CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>(v173);
                                                                operator delete(v173, 0x20u);
                                                              }
                                                            }
                                                            v173 = v395;
                                                            v511 = (unsigned __int64)v395;
                                                            v396 = 0;
                                                            v563 = 0;
                                                            v397 = 0;
                                                            while ( v397 < v393 )
                                                            {
                                                              v398 = *(_QWORD **)(*(_QWORD *)(v540 + 24) + 8LL * v397);
                                                              v642 = 3869;
                                                              v399 = operator new(
                                                                       0x48u,
                                                                       v492,
                                                                       "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                       3869,
                                                                       1u);
                                                              v756 = v399;
                                                              if ( v399 )
                                                              {
                                                                *v399 = 0;
                                                                v399[1] = 0;
                                                                v399[2] = 0;
                                                                v399[3] = 0;
                                                                *((_QWORD *)v399 + 8) = 0;
                                                                *((_QWORD *)v399 + 4) = 0;
                                                              }
                                                              else
                                                              {
                                                                v399 = 0;
                                                              }
                                                              *((_QWORD *)v399 + 4) = v398[3];
                                                              *(_QWORD *)v399 = *v398;
                                                              *((_QWORD *)v399 + 1) = v398[1];
                                                              *((_QWORD *)v399 + 2) = v398[4];
                                                              *((_QWORD *)v399 + 3) = v398[2];
                                                              *((_QWORD *)v399 + 5) = v398[5];
                                                              *((_QWORD *)v399 + 6) = 0xBFF0000000000000uLL;
                                                              *((_QWORD *)v399 + 7) = 0xBFF0000000000000uLL;
                                                              *((_DWORD *)v399 + 16) = -1;
                                                              *((_BYTE *)v399 + 68) = 0;
                                                              if ( !*((_QWORD *)v173 + 3) )
                                                              {
                                                                v400 = v173[4];
                                                                *((_QWORD *)v173 + 3) = StdAlloc<CRawMemObjAlloc<0>>::AllocArray<CReqdPlanProperties *>(
                                                                                          v173,
                                                                                          v400);
                                                                v173[4] = v400;
                                                              }
                                                              v401 = v173[3];
                                                              v402 = v173[4];
                                                              if ( v401 >= (unsigned int)v402 )
                                                              {
                                                                if ( v401 == -1 )
                                                                {
                                                                  utassert_fail(
                                                                    1u,
                                                                    "m_cElems < ULONG_MAX",
                                                                    "Sql\\Ntdbms\\include\\common\\stdarray.inl",
                                                                    217,
                                                                    0);
                                                                  v401 = v173[3];
                                                                  v402 = v173[4];
                                                                }
                                                                v510 = v402;
                                                                v403 = v402;
                                                                while ( v401 + 1 > v403 )
                                                                {
                                                                  v404 = v403;
                                                                  if ( v403 > 0x100 )
                                                                    v404 = 256;
                                                                  if ( v403 > ~v404 )
                                                                  {
                                                                    v402 = 0xFFFFFFFFLL;
                                                                    v510 = -1;
                                                                    v403 = -1;
                                                                  }
                                                                  else
                                                                  {
                                                                    v402 = v403 + v404;
                                                                    v403 = v402;
                                                                    v510 = v402;
                                                                  }
                                                                }
                                                                v675 = *(_QWORD *)v173;
                                                                v611 = (_QWORD *)StdAlloc<CRawMemObjAlloc<0>>::AllocArray<CReqdPlanProperties *>(
                                                                                   v173,
                                                                                   v402);
                                                                v612 = v675;
                                                                v613 = &v510;
                                                                v559 = 0;
                                                                for ( m = 0; m < v173[3]; v559 = m )
                                                                {
                                                                  v611[m] = *(_QWORD *)(*((_QWORD *)v173 + 3) + 8LL * m);
                                                                  ++m;
                                                                }
                                                                v406 = (void *)*((_QWORD *)v173 + 3);
                                                                if ( v406 )
                                                                {
                                                                  v407 = v173[4];
                                                                  v561 = v407;
                                                                  while ( v407 )
                                                                    v561 = --v407;
                                                                  operator delete[](v406);
                                                                  *((_QWORD *)v173 + 3) = 0;
                                                                }
                                                                v173[4] = 0;
                                                                v408 = v611;
                                                                v611 = 0;
                                                                *((_QWORD *)v173 + 3) = v408;
                                                                v173[4] = v510;
                                                                v409 = *v613;
                                                                v562 = *v613;
                                                                if ( v611 )
                                                                {
                                                                  while ( v409 )
                                                                    v562 = --v409;
                                                                  operator delete[](v611);
                                                                }
                                                                v611 = 0;
                                                              }
                                                              *(_QWORD *)(*((_QWORD *)v173 + 3) + 8LL * v173[3]++) = v399;
                                                              v563 = ++v396;
                                                              v397 = v396;
                                                              v393 = v507;
                                                            }
                                                            if ( v875 )
                                                            {
                                                              CInterestingPredicateExplorer::VerifyUsePlanAndSortPredicateInfoWrapperList(
                                                                v172,
                                                                v173);
                                                              if ( !(unsigned __int8)CMultiPlanFeedback::CompilePredicates(
                                                                                       v543,
                                                                                       v508) )
                                                                ex_raise(86, 98, 16, 5);
                                                              v164 = v492;
                                                            }
                                                            else
                                                            {
                                                              COptContext::TrackOptTime(
                                                                (COptContext *)v846,
                                                                v760,
                                                                &v759,
                                                                &v758,
                                                                &v579,
                                                                &v757,
                                                                0);
                                                              v410 = v579 * 1000.0;
                                                              v411 = 0;
                                                              if ( v579 * 1000.0 >= 9.223372036854776e18 )
                                                              {
                                                                v410 = v410 - 9.223372036854776e18;
                                                                if ( v410 < 9.223372036854776e18 )
                                                                  v411 = 0x8000000000000000uLL;
                                                              }
                                                              if ( v411 + (unsigned int)(int)v410 <= *((int *)v543 + 22) )
                                                              {
                                                                CMultiPlanFeedback::CompilePredicates(v543, v508);
                                                                v164 = v492;
                                                              }
                                                              else
                                                              {
                                                                v579 = 2.000000000000004;
                                                                if ( (qword_102EDCA04 & 0x4000000000000000LL) != 0 )
                                                                {
                                                                  v813 = 0;
                                                                  v814 = 1;
                                                                  v815 = 0;
                                                                  v816 = &v819;
                                                                  v817 = &v823;
                                                                  v824 = 0;
                                                                  v825 = 0;
                                                                  v818 = 0;
                                                                  v826 = 0;
                                                                  v819 = &v827;
                                                                  v820 = 4;
                                                                  v821 = 0;
                                                                  v822 = 0;
                                                                  v827 = 36;
                                                                  XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason::Publish((XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason *)v812);
                                                                }
                                                                v164 = v492;
                                                              }
                                                            }
                                                          }
                                                          else if ( v875 )
                                                          {
                                                            ex_raise(86, 98, 16, 6);
                                                          }
                                                        }
                                                        if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 36) )
                                                          CInterestingPredicateExplorer::FirePredicateSelectionXevent(
                                                            v172,
                                                            v164,
                                                            *((_WORD *)v545 + 52),
                                                            *(_BYTE *)(v30 + 580) & 1);
                                                        if ( *((_DWORD *)v172 + 12) )
                                                        {
                                                          v540 = 0x400000000000000ALL;
                                                          if ( (qword_102EDCA04 & 0x4000000000000000LL) != 0 )
                                                          {
                                                            v829 = 0;
                                                            v830 = 1;
                                                            v831 = 0;
                                                            v832 = &v835;
                                                            v833 = &v839;
                                                            v840 = 0;
                                                            v841 = 0;
                                                            v834 = 0;
                                                            v842 = 0;
                                                            v835 = &v843;
                                                            v836 = 4;
                                                            v837 = 0;
                                                            v838 = 0;
                                                            v843 = *((_DWORD *)v172 + 12);
                                                            XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason::Publish((XeSqlPkg::parameter_sensitive_plan_optimization_skipped_reason *)v828);
                                                          }
                                                        }
                                                      }
                                                      if ( v894 )
                                                      {
                                                        CETelemetryPackage::PublishCEPackage(v894, v183);
                                                        v412 = v894;
                                                        v760[1] = (unsigned __int64)v894;
                                                        if ( v894 )
                                                        {
                                                          v760[2] = (unsigned __int64)v894;
                                                          CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>::~CTHashTableBase<Pair<COptExpr *,unsigned __int64>,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryHashFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryCmpFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryInvalidFn,CTMap<COptExpr *,unsigned __int64,CFnH_Pointer,CFnC_Default<COptExpr *>,CFnI_Default<unsigned __int64>,CFnD_Noop<COptExpr *>,CFnD_Noop<unsigned __int64>,CMemObjAlloc<0>>::CEntryDestroyFn,CMemObjAlloc<0>>(v894);
                                                          operator delete(v412, 0x30u);
                                                        }
                                                        v894 = 0;
                                                      }
                                                      v188 = v495;
                                                      v189 = *((_QWORD *)v495 + 8);
                                                      if ( v189 )
                                                      {
                                                        v580 = *((_QWORD *)v495 + 8);
                                                        if ( !*(_QWORD *)(v189 + 16) || !*(_QWORD *)(v189 + 136) )
                                                          *(_BYTE *)(v189 + 704) = 0;
                                                        v413 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v184 = *(_QWORD **)(v413 + 256);
                                                        if ( !v184 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v184 = *(_QWORD **)(v413 + 256);
                                                        }
                                                        if ( v184[107] )
                                                        {
                                                          v417 = __rdtsc();
                                                          v418 = v184[108];
                                                          if ( v417 <= v418 )
                                                            v419 = 0;
                                                          else
                                                            v419 = v417 - v418;
                                                          v414 = v419 + v184[109];
                                                        }
                                                        else
                                                        {
                                                          v414 = 0;
                                                        }
                                                        v415 = v580;
                                                        *(_QWORD *)(v580 + 256) += v414 - *(_QWORD *)(v189 + 16);
                                                        v416 = __rdtsc();
                                                        *(_QWORD *)(v415 + 376) += (((unsigned __int64)HIDWORD(v416) << 32)
                                                                                  | (unsigned int)v416)
                                                                                 - *(_QWORD *)(v415 + 136);
                                                        *(_QWORD *)(v189 + 16) = 0;
                                                        *(_QWORD *)(v415 + 136) = 0;
                                                        ++*(_DWORD *)(v415 + 488);
                                                        v173 = (unsigned int *)v511;
                                                      }
                                                      v501 = (*(_DWORD *)(*((_QWORD *)v495 + 1) + 580LL) & 2) != 0;
                                                      v537 = 0;
                                                      if ( v501 )
                                                      {
                                                        if ( !COptContext::IsDwGen3FrontendInstanceWithDwUqoCompile((COptContext *)v846) )
                                                        {
                                                          if ( a15 )
                                                            v426 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v512 + 43) + 64LL))(*((_QWORD *)v512 + 43));
                                                          else
                                                            v426 = 0;
                                                          v643 = 3976;
                                                          v427 = operator new(
                                                                   0x4F8u,
                                                                   v508,
                                                                   "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                   3976,
                                                                   1u);
                                                          v760[3] = (unsigned __int64)v427;
                                                          if ( v427 )
                                                            v428 = (struct CMemoXml *)CMemoXml::CMemoXml(
                                                                                        v427,
                                                                                        1,
                                                                                        *(unsigned int *)(*((_QWORD *)v495 + 1) + 1128LL),
                                                                                        *(unsigned int *)(*((_QWORD *)v495 + 1) + 1132LL),
                                                                                        0,
                                                                                        v426);
                                                          else
                                                            v428 = 0;
                                                          v537 = v428;
                                                          v429 = (v859 & 2) != 0 && (v858 & 4) != 0;
                                                          v190 = a11;
                                                          if ( v429 )
                                                            CMemo::PrintXmlForPdwUqo(
                                                              v873,
                                                              (struct CRelOp_Query *)v30,
                                                              v533,
                                                              v512,
                                                              (const struct CCompExecCtxtStmt *)a11,
                                                              v428,
                                                              0,
                                                              0,
                                                              1);
                                                          else
                                                            CMemo::PrintXmlForPdw(
                                                              v873,
                                                              *((_DWORD *)v873 + 55),
                                                              0,
                                                              1,
                                                              (struct CRelOp_Query *)v30,
                                                              v533,
                                                              v512,
                                                              (const struct CCompExecCtxtStmt *)a11,
                                                              v428,
                                                              0,
                                                              0);
                                                          goto LABEL_408;
                                                        }
                                                        v537 = PMemoXml(**((const struct CQte ***)v601 + 3));
                                                      }
                                                      v190 = a11;
LABEL_408:
                                                      v191 = 0;
                                                      v549 = 0;
                                                      if ( (unsigned __int8)COptContext::FFeatureSwitchOn(
                                                                              v846,
                                                                              213,
                                                                              v184,
                                                                              v185)
                                                        && (v856 & 0x80) != 0
                                                        && !DataVirtualizationResource::IsDataVirtualizationFeatureSetLockdownEnabled(v192)
                                                        && (unsigned __int8)COptContext::FFeatureSwitchOn(
                                                                              v846,
                                                                              141,
                                                                              v420,
                                                                              v421) )
                                                      {
                                                        v644 = 4006;
                                                        v422 = operator new(
                                                                 0x18u,
                                                                 v164,
                                                                 "sql\\ntdbms\\query\\qoin\\pqobuild.cpp",
                                                                 4006,
                                                                 1u);
                                                        v760[4] = (unsigned __int64)v422;
                                                        if ( v422 )
                                                        {
                                                          v423 = *(_DWORD *)(v30 + 80);
                                                          *(_QWORD *)v422 = 0;
                                                          v422[2] = v423 + 1;
                                                          *((_QWORD *)v422 + 2) = v164;
                                                        }
                                                        CAutoP<PartitionReducedSourceList>::operator=(&v549);
                                                        v760[5] = (unsigned __int64)v164;
                                                        v760[6] = (unsigned __int64)v164;
                                                        v424 = *(_DWORD *)(v30 + 80);
                                                        v760[7] = (unsigned __int64)v164;
                                                        v585 = (unsigned __int64)v164;
                                                        v586 = 0;
                                                        v425 = 1;
                                                        if ( v424 )
                                                          v425 = v424;
                                                        v587 = v425;
                                                        v588 = 0;
                                                        v760[8] = (unsigned __int64)&v589;
                                                        v760[9] = (unsigned __int64)v844;
                                                        v760[10] = v585;
                                                        v589 = v585;
                                                        v590 = 0;
                                                        v591 = v425;
                                                        v592 = 0;
                                                        CCompExecCtxt::CCompExecCtxt(
                                                          (CCompExecCtxt *)v844,
                                                          (const struct CCompExecCtxt *)v190);
                                                        v845 = v190[22];
                                                        v191 = v549;
                                                        DataVirtualizationQeoptimUtils::TryEliminatePartitions(
                                                          (unsigned int)v846,
                                                          (_DWORD)v164,
                                                          (_DWORD)v549,
                                                          (unsigned int)v844,
                                                          (__int64)&v589);
                                                        v586 = 0;
                                                        if ( v588 )
                                                        {
                                                          v430 = v587;
                                                          v564 = v587;
                                                          while ( v430 )
                                                            v564 = --v430;
                                                          operator delete[](v588);
                                                          v588 = 0;
                                                        }
                                                        v587 = 0;
                                                      }
                                                      if ( v509 && v191 && *v191 )
                                                      {
                                                        v431 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v432 = *(_QWORD *)(v431 + 256);
                                                        if ( !v432 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v432 = *(_QWORD *)(v431 + 256);
                                                        }
                                                        v433 = CRowsetFilesInfo::Copy(
                                                                 *(CRowsetFilesInfo **)(*v549 + 32LL),
                                                                 *(struct IMemObj **)(v432 + 1000));
                                                        *((_QWORD *)v509 + 113) = v433;
                                                        v173 = (unsigned int *)v511;
                                                      }
                                                      if ( (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 167) )
                                                        CSqlDwTelemetry::ProcessQueryAnnotations(
                                                          (struct COptContext *)v846,
                                                          (struct CRelOp_Query *)v30);
                                                      v886 = 0;
                                                      *(_QWORD *)(*(_QWORD *)(v849 + 56) + 40LL) = 0;
                                                      *(_QWORD *)(*(_QWORD *)(v849 + 64) + 40LL) = 0;
                                                      v193 = *((_QWORD *)v495 + 8);
                                                      if ( v193 )
                                                      {
                                                        v572 = *((_QWORD *)v495 + 8);
                                                        if ( *(_QWORD *)(v193 + 24) || *(_QWORD *)(v193 + 144) )
                                                          *(_BYTE *)(v193 + 704) = 0;
                                                        v434 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v435 = *(_QWORD **)(v434 + 256);
                                                        if ( !v435 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v435 = *(_QWORD **)(v434 + 256);
                                                        }
                                                        if ( v435[107] )
                                                        {
                                                          v437 = __rdtsc();
                                                          v438 = v435[108];
                                                          if ( v437 <= v438 )
                                                            v439 = 0;
                                                          else
                                                            v439 = v437 - v438;
                                                          v436 = v439 + v435[109];
                                                        }
                                                        else
                                                        {
                                                          v436 = 0;
                                                        }
                                                        *(_QWORD *)(v193 + 24) = v436;
                                                        *(_QWORD *)(v572 + 144) = __rdtsc();
                                                        v173 = (unsigned int *)v511;
                                                      }
                                                      v194 = (struct IQueryObj *)(*(__int64 (__fastcall **)(struct IXteBuilder *, struct CQte *))(*(_QWORD *)XteBuilderObject + 568LL))(
                                                                                   XteBuilderObject,
                                                                                   v601);
                                                      v534 = v194;
                                                      v195 = (*(__int64 (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v194 + 120LL))(v194);
                                                      v196 = *(int **)(v852 + 16);
                                                      v197 = v196[2] > 177
                                                          && (*(_DWORD *)(*(_QWORD *)v196 + 20LL) & 0x20000) != 0;
                                                      if ( v197 && v896 == 3 && v897 && v897 != v195 )
                                                        ex_raise(86, 75, 16, 5);
                                                      if ( v876 )
                                                      {
                                                        v572 = 0x8000000000000009uLL;
                                                        if ( (int)qword_102EDCA04 < 0 )
                                                          COptAntiPatterns::FireAllAntiPatternEvents(v876);
                                                      }
                                                      v198 = v543;
                                                      if ( v543 && *((_DWORD *)v543 + 1) != 1 && v173 && v173[3] )
                                                      {
                                                        v727 = 1;
                                                        v726 = &CFingerprintUtil::`vftable';
                                                        v728 = 0;
                                                        v729 = 0;
                                                        *((_QWORD *)v198 + 4) = COptContext::GenDispatcherShowplanXMLSerialized(
                                                                                  (int)v846,
                                                                                  (int)v508,
                                                                                  (int)v598,
                                                                                  (int)v173,
                                                                                  (__int64)v194,
                                                                                  (CFingerprintUtil *)&v726);
                                                        *((_QWORD *)v198 + 6) = v729;
                                                        v580 = 0x20000000BLL;
                                                        if ( (dword_102EDCA0C & 2) != 0 )
                                                        {
                                                          v775 = 0;
                                                          v776 = 1;
                                                          v777 = 0;
                                                          v778 = &v781;
                                                          v779 = &v785;
                                                          v786 = 0;
                                                          v787 = 0;
                                                          v780 = 0;
                                                          v788 = 0;
                                                          v781 = &v789;
                                                          v782 = 17;
                                                          v783 = 0;
                                                          v784 = 0;
                                                          v789 = 0;
                                                          v790 = v173[3];
                                                          v791 = 0;
                                                          v792 = 0;
                                                          XeSqlPkg::parameter_sensitive_plan_optimization::Publish((XeSqlPkg::parameter_sensitive_plan_optimization *)v774);
                                                        }
                                                        v726 = &CRefCount::`vftable';
                                                      }
                                                      if ( v869 < 0 )
                                                      {
                                                        v440 = (int *)*((_QWORD *)a11[20] + 17);
                                                        v441 = *((_QWORD *)v440 + 1);
                                                        v442 = *v440;
                                                        v577 = 0x20000000BLL;
                                                        if ( (dword_102EDCA0C & 2) != 0 )
                                                        {
                                                          v794 = 0;
                                                          v795 = 1;
                                                          v796 = 0;
                                                          v797 = &v800;
                                                          v798 = &v804;
                                                          v805 = 0;
                                                          v806 = 0;
                                                          v799 = 0;
                                                          v807 = 0;
                                                          v800 = &v808;
                                                          v801 = 17;
                                                          v802 = 0;
                                                          v803 = 0;
                                                          v808 = 1;
                                                          v809 = 0;
                                                          v810 = v442;
                                                          v811 = v441;
                                                          XeSqlPkg::parameter_sensitive_plan_optimization::Publish((XeSqlPkg::parameter_sensitive_plan_optimization *)v793);
                                                        }
                                                      }
                                                      if ( v544 )
                                                      {
                                                        v565 = 0;
                                                        for ( n = 0; n < *(_DWORD *)(v544 + 12); v565 = n )
                                                        {
                                                          v444 = *(struct CTelemetryPackage **)(*(_QWORD *)(v544 + 24)
                                                                                              + 8LL * n);
                                                          CTelemetryPackageContainer::PublishTelemetryPackage(
                                                            (CTelemetryPackageContainer *)n,
                                                            v444);
                                                          if ( v444 )
                                                          {
                                                            v445 = (CEncodeJsonUtil *)*((_QWORD *)v444 + 1);
                                                            if ( v445 )
                                                              CEncodeJsonUtil::`scalar deleting destructor'(v445, 1u);
                                                            operator delete(v444, 0x18u);
                                                          }
                                                          ++n;
                                                        }
                                                        v446 = v544;
                                                        v760[11] = v544;
                                                        *(_DWORD *)(v544 + 12) = 0;
                                                        v447 = *(void **)(v446 + 24);
                                                        if ( v447 )
                                                        {
                                                          v448 = *(_DWORD *)(v446 + 16);
                                                          v566 = v448;
                                                          while ( v448 )
                                                            v566 = --v448;
                                                          operator delete[](v447);
                                                          *(_QWORD *)(v446 + 24) = 0;
                                                        }
                                                        *(_DWORD *)(v446 + 16) = 0;
                                                        operator delete((void *)v446, 0x20u);
                                                      }
                                                      v199 = *((_QWORD *)v495 + 8);
                                                      if ( v199 )
                                                      {
                                                        v679 = *((_QWORD *)v495 + 8);
                                                        if ( !*(_QWORD *)(v199 + 24) || !*(_QWORD *)(v199 + 144) )
                                                          *(_BYTE *)(v199 + 704) = 0;
                                                        v449 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        v450 = *(_QWORD **)(v449 + 256);
                                                        if ( !v450 )
                                                        {
                                                          SystemThread::MakeMiniSOSThread(0);
                                                          v450 = *(_QWORD **)(v449 + 256);
                                                        }
                                                        if ( v450[107] )
                                                        {
                                                          v454 = __rdtsc();
                                                          v455 = v450[108];
                                                          if ( v454 <= v455 )
                                                            v456 = 0;
                                                          else
                                                            v456 = v454 - v455;
                                                          v451 = v456 + v450[109];
                                                        }
                                                        else
                                                        {
                                                          v451 = 0;
                                                        }
                                                        v452 = v679;
                                                        *(_QWORD *)(v679 + 264) += v451 - *(_QWORD *)(v199 + 24);
                                                        v453 = __rdtsc();
                                                        *(_QWORD *)(v452 + 384) += (((unsigned __int64)HIDWORD(v453) << 32)
                                                                                  | (unsigned int)v453)
                                                                                 - *(_QWORD *)(v452 + 144);
                                                        *(_QWORD *)(v199 + 24) = 0;
                                                        *(_QWORD *)(v452 + 144) = 0;
                                                        ++*(_DWORD *)(v452 + 492);
                                                        v194 = v534;
                                                      }
                                                      (*(void (__fastcall **)(struct IQueryObj *, const struct CStatementDescription *, bool))(*(_QWORD *)v194 + 600LL))(
                                                        v194,
                                                        v599,
                                                        a14);
                                                      v545[7] = 0;
                                                      if ( v501 )
                                                      {
                                                        v457 = v537;
                                                        v537 = 0;
                                                        (*(void (__fastcall **)(struct IQueryObj *, struct CMemoXml *))(*(_QWORD *)v194 + 248LL))(
                                                          v194,
                                                          v457);
                                                      }
                                                      v201 = (const struct CCompExecCtxtStmt *)a11;
                                                      if ( (v856 & 2) != 0 )
                                                      {
                                                        LOBYTE(v200) = 1;
                                                        CExecLvlRepresentation::SetNotCacheable(a11[20], 40, v200);
                                                      }
                                                      COptContext::TrackOptTime(
                                                        (COptContext *)v846,
                                                        v761,
                                                        &v602,
                                                        &v682,
                                                        &v690,
                                                        &v685,
                                                        1);
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 1084) & 8) != 0
                                                        || ((v567 = 0,
                                                             v202 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v202)
                                                         && (v203 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v202 + 56LL)) != 0
                                                          ? (v204 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v203,
                                                                      0x21E3u))
                                                          : (v204 = v567),
                                                            v204) )
                                                      {
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v536,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        v458 = TraceStreamHolder::GetStream((TraceStreamHolder *)v536);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v680,
                                                          v458);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v458 + 16,
                                                          "End of query plan compilation,");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v680);
                                                        v459 = TraceStreamHolder::GetStream((TraceStreamHolder *)v536);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v681,
                                                          v459);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v459 + 16,
                                                          " time: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v681);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v683,
                                                          v459);
                                                        std::ostream::operator<<((char *)v459 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v683);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v684,
                                                          v459);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v459 + 16,
                                                          " net: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v684);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v686,
                                                          v459);
                                                        std::ostream::operator<<((char *)v459 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v686);
                                                        v460 = TraceStreamHolder::GetStream((TraceStreamHolder *)v536);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v687,
                                                          v460);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v460 + 16,
                                                          " total: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v687);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v688,
                                                          v460);
                                                        v205 = v602;
                                                        std::ostream::operator<<((char *)v460 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v688);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v689,
                                                          v460);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v460 + 16,
                                                          " net: ");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v689);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v691,
                                                          v460);
                                                        std::ostream::operator<<((char *)v460 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v691);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v692,
                                                          v460);
                                                        endl(v460);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v692);
                                                        v461 = TraceStreamHolder::GetStream((TraceStreamHolder *)v536);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v693,
                                                          v461);
                                                        std::ostream::flush((char *)v461 + 16);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v693);
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v536);
                                                      }
                                                      else
                                                      {
                                                        v205 = v602;
                                                      }
                                                      v206 = v892;
                                                      ++*(_DWORD *)(v892 + 4);
                                                      *(double *)(v206 + 168) = v205 + *(double *)(v206 + 168);
                                                      v207 = 0;
                                                      v547 = 0;
                                                      v538 = 0;
                                                      v208 = 0;
                                                      if ( (v867 & 1) != 0 )
                                                      {
                                                        v547 = (struct CQNameManager *)*((_QWORD *)v495 + 12);
                                                        v208 = *((_QWORD *)v495 + 13);
                                                        v538 = v208;
                                                        v207 = v872;
                                                        v547 = v872;
                                                      }
                                                      v209 = v899 + v208;
                                                      v695 = v899 + v208;
                                                      if ( v900 < v899 + v208 )
                                                      {
                                                        v210 = 0;
                                                        v538 = 0;
                                                      }
                                                      else
                                                      {
                                                        v210 = v900 - v209;
                                                        v538 = v900 - v209;
                                                      }
                                                      v697 = v210;
                                                      v211 = (__int64)v207 + v901;
                                                      v696 = (__int64)v207 + v901;
                                                      if ( v902 < (unsigned __int64)v207 + v901 )
                                                      {
                                                        v212 = 0;
                                                        v538 = 0;
                                                      }
                                                      else
                                                      {
                                                        v212 = v902 - v211;
                                                        v538 = v902 - v211;
                                                      }
                                                      v698 = v212;
                                                      COptRsrcInfoHelper::SetCompTime(v622, &v697, 0, 0);
                                                      LOBYTE(v213) = 1;
                                                      COptRsrcInfoHelper::SetCompTime(v622, &v698, v214, v213);
                                                      (*(void (__fastcall **)(struct IQueryCompile *, _QWORD *))(*(_QWORD *)v509 + 64LL))(
                                                        v509,
                                                        v622);
                                                      v215 = CExecLvlRepresentation::PmoPph(*(CExecLvlRepresentation **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset) + 160LL));
                                                      v623 = (unsigned __int64)(*((_QWORD *)v215 + 2)
                                                                              * (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v215 + 120LL))(v215)) >> 10;
                                                      v624 = (unsigned __int64)(*((_QWORD *)v492 + 2)
                                                                              * (*(__int64 (__fastcall **)(struct IMemObj *))(*(_QWORD *)v492 + 120LL))(v492)) >> 10;
                                                      (*(void (__fastcall **)(struct IQueryCompile *, unsigned __int64 *))(*(_QWORD *)v509 + 72LL))(
                                                        v509,
                                                        &v623);
                                                      v615 = 0;
                                                      v616 = 0;
                                                      v617 = 0;
                                                      v614 = v879;
                                                      v699 = v880;
                                                      v615 = ToULong((const struct CQODouble *)&v699);
                                                      v700 = v881;
                                                      v616 = ToULongLong((const struct CQODouble *)&v700) >> 10;
                                                      v216 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + SystemThread_TlsIndex)
                                                                                   + SystemThread_TlsOffset
                                                                                   + 8LL)
                                                                       + 80LL);
                                                      if ( v216 && (v217 = *(_QWORD *)(v216 + 8)) != 0 )
                                                        v218 = *(_QWORD *)(v217 + 1344) << 13;
                                                      else
                                                        v218 = 0;
                                                      v617 = v218 / 1024;
                                                      (*(void (__fastcall **)(struct IQueryCompile *, int *))(*(_QWORD *)v509 + 80LL))(
                                                        v509,
                                                        &v614);
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 289) & 8) != 0
                                                        || ((v574 = 0,
                                                             v219 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset,
                                                             *(_QWORD *)v219)
                                                         && (v220 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v219 + 56LL)) != 0
                                                          ? (v221 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                      v220,
                                                                      0x90Bu))
                                                          : (v221 = v574),
                                                            v221) )
                                                      {
                                                        v607 = &g_mutexQOPrint;
                                                        v608 = 0;
                                                        TAutoMutex<SOS_Mutex,1>::GetAccess(&v607, 4194681);
                                                        TraceStreamHolder::TraceStreamHolder(
                                                          (TraceStreamHolder *)v593,
                                                          (struct SOS_TraceStream *)&g_traceout);
                                                        v462 = TraceStreamHolder::GetStream((TraceStreamHolder *)v593);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v701,
                                                          v462);
                                                        endl(v462);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v701);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v702,
                                                          v462);
                                                        std::operator<<<std::char_traits<char>>(
                                                          (char *)v462 + 16,
                                                          "Query Compilation completed");
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v702);
                                                        TraceStreamProtector::TraceStreamProtector(
                                                          (TraceStreamProtector *)v703,
                                                          v462);
                                                        endl(v462);
                                                        TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)v703);
                                                        OptimizerUtil::PrintQOMemoryUsageInfo();
                                                        TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)v593);
                                                        v463 = v608;
                                                        v464 = v607;
                                                        while ( v463 )
                                                        {
                                                          v464[6] = 0;
                                                          EventAutoInternal<SuspendQueueSLock>::Signal(v464, 0);
                                                          v608 = --v463;
                                                        }
                                                      }
                                                      *((_BYTE *)v495 + 44) &= ~8u;
                                                      CMemo::CollectTelemetry(v873);
                                                      v222 = v534;
                                                      if ( v893 )
                                                        CQoTelemetryAgg::FireCompilationEvent(v893, v534);
                                                      COptContext::TryFireLongCompilationTelemetry(
                                                        (COptContext *)v846,
                                                        1);
                                                      v223 = v887;
                                                      if ( v887 )
                                                      {
                                                        v224 = (*(__int64 (__fastcall **)(struct IQueryObj *))(*(_QWORD *)v222 + 136LL))(v222);
                                                        BatchModeHeuristics::FireHeuristicsXEvent(v223, v224);
                                                      }
                                                      CAutoP<PartitionReducedSourceList>::~CAutoP<PartitionReducedSourceList>(&v549);
                                                      if ( v537 )
                                                        (**(void (__fastcall ***)(struct CMemoXml *, __int64))v537)(
                                                          v537,
                                                          1);
                                                      v225 = (void *)v511;
                                                      v761[1] = v511;
                                                      if ( v511 )
                                                      {
                                                        CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>::~CTDynArrayBase<PredicateInfoWrapper *,CFnI_Default<PredicateInfoWrapper *>,CFnD_Ptr<PredicateInfoWrapper>,CMemObjAlloc<0>>(v511);
                                                        operator delete(v225, 0x20u);
                                                      }
                                                      goto LABEL_1159;
                                                    }
                                                    if ( IsTridentSqlFrontendSession() )
                                                    {
                                                      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v165 + 2)
                                                                                                  + 24LL))(*((_QWORD *)v165 + 2)) == 80 )
                                                      {
LABEL_846:
                                                        v859 &= ~2u;
                                                        goto LABEL_385;
                                                      }
                                                      v557 = 0;
                                                      for ( ii = 0; ii < *((_DWORD *)v165 + 6); v557 = ii )
                                                      {
                                                        if ( COptContext::FContainUqoUnsupportedOperator(*(const struct COptExpr **)(*((_QWORD *)v165 + 4) + 8LL * ii)) )
                                                          goto LABEL_846;
                                                        ++ii;
                                                      }
                                                    }
                                                    if ( (v868 & 0x10) == 0 )
                                                      goto LABEL_385;
                                                    goto LABEL_846;
                                                  }
                                                  catch ( SQLError v583 )
                                                  {
                                                    try
                                                    {
                                                      ExceptionBackout::ExceptionBackout(
                                                        (ExceptionBackout *)v764,
                                                        (const struct SQLError *)v583);
                                                      if ( v584 == 1 )
                                                        v270 = v583[0];
                                                      else
                                                        v270 = LOWORD(v583[0]);
                                                      COptContext::PublishFailedCompilationEvent(
                                                        (COptContext *)v846,
                                                        v270,
                                                        v583[3]);
                                                      CInterleavedExecUtil::CleanUpTvfTablesOnException((const struct CCompExecCtxtStmt *)v546);
                                                      v271 = qword_102ECFB10;
                                                      if ( (*((_BYTE *)qword_102ECFB10 + 289) & 8) == 0 )
                                                      {
                                                        v575 = 0;
                                                        v272 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        if ( *(_QWORD *)v272
                                                          && (v273 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v272 + 56LL)) != 0 )
                                                        {
                                                          v274 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                   v273,
                                                                   0x90Bu);
                                                        }
                                                        else
                                                        {
                                                          v274 = v575;
                                                        }
                                                        if ( !v274 )
                                                          goto LABEL_1064;
                                                        v271 = qword_102ECFB10;
                                                      }
                                                      if ( v583[0] / 100 != 7 || v583[0] != 701 )
                                                        goto LABEL_1065;
                                                      v609 = &g_mutexQOPrint;
                                                      v610 = 0;
                                                      TAutoMutex<SOS_Mutex,1>::GetAccess(&v609, 4194681);
                                                      TraceStreamHolder::TraceStreamHolder(
                                                        (TraceStreamHolder *)&v594,
                                                        (struct SOS_TraceStream *)&g_traceout);
                                                      v275 = TraceStreamHolder::GetStream((TraceStreamHolder *)&v594);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v704,
                                                        v275);
                                                      endl(v275);
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v704);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v705,
                                                        v275);
                                                      std::operator<<<std::char_traits<char>>(
                                                        (char *)v275 + 16,
                                                        "OOM thrown during Query Optimization");
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v705);
                                                      TraceStreamProtector::TraceStreamProtector(
                                                        (TraceStreamProtector *)&v706,
                                                        v275);
                                                      endl(v275);
                                                      TraceStreamProtector::~TraceStreamProtector((TraceStreamProtector *)&v706);
                                                      OptimizerUtil::PrintQOMemoryUsageInfo();
                                                      TraceStreamHolder::~TraceStreamHolder((TraceStreamHolder *)&v594);
                                                      v276 = v610;
                                                      v277 = v609;
                                                      while ( v276 )
                                                      {
                                                        v277[6] = 0;
                                                        EventAutoInternal<SuspendQueueSLock>::Signal(v277, 0);
                                                        v610 = --v276;
                                                      }
LABEL_1064:
                                                      v271 = qword_102ECFB10;
LABEL_1065:
                                                      if ( (*((_BYTE *)v271 + 324) & 1) != 0
                                                        && (*((_BYTE *)v271 + 1079) & 1) == 0 )
                                                      {
                                                        v560 = 0;
                                                        v278 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + SystemThread_TlsIndex)
                                                             + SystemThread_TlsOffset;
                                                        if ( *(_QWORD *)v278
                                                          && (v279 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v278 + 56LL)) != 0 )
                                                        {
                                                          v280 = CSessionTraceFlags::CheckSessionTraceInternal(
                                                                   v279,
                                                                   0x21B8u);
                                                        }
                                                        else
                                                        {
                                                          v280 = v560;
                                                        }
                                                        if ( !v280 && v545[7] )
                                                        {
                                                          v281 = v583[0];
                                                          v282 = v583[0] / 100;
                                                          if ( v583[0] / 100 == 29 && v583[0] != 2906 )
                                                            goto LABEL_1094;
                                                          if ( v282 == 36 && v583[0] == 3624 )
                                                            goto LABEL_1094;
                                                          if ( v282 == 36 && v583[0] == 3621 )
                                                            goto LABEL_1094;
                                                          if ( v282 == 86 && v583[0] == 8624 )
                                                            goto LABEL_1094;
                                                          if ( v282 == 7 && v583[0] == 701 )
                                                            goto LABEL_1094;
                                                          v283 = v584 == 1 ? v583[0] : LOWORD(v583[0]);
                                                          if ( v283 == 17065 )
                                                            goto LABEL_1094;
                                                          v284 = v584 == 1 ? v583[0] : LOWORD(v583[0]);
                                                          if ( v284 == 17066 )
                                                            goto LABEL_1094;
                                                          if ( v584 != 1 )
                                                            v281 = LOWORD(v583[0]);
                                                          if ( v281 == 17067 )
LABEL_1094:
                                                            COptContext::PrintExceptionInfo((COptContext *)v846, 1);
                                                        }
                                                      }
                                                      v285 = (CCompTimeTrace *)*((_QWORD *)v495 + 8);
                                                      if ( v285 )
                                                      {
                                                        CCompTimeTrace::HandlePqoBuildExceptionCase(v285);
                                                        v548 = (struct CQNameManager *)*((_QWORD *)v495 + 8);
                                                        if ( !*((_DWORD *)v548 + 175) )
                                                        {
                                                          v286 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset;
                                                          v287 = *(_QWORD **)(v286 + 256);
                                                          if ( !v287 )
                                                          {
                                                            SystemThread::MakeMiniSOSThread(0);
                                                            v287 = *(_QWORD **)(v286 + 256);
                                                          }
                                                          if ( v287[107] )
                                                          {
                                                            v289 = __rdtsc();
                                                            v290 = v287[108];
                                                            if ( v289 <= v290 )
                                                              v291 = 0;
                                                            else
                                                              v291 = v289 - v290;
                                                            v288 = v291 + v287[109];
                                                          }
                                                          else
                                                          {
                                                            v288 = 0;
                                                          }
                                                          v292 = v548;
                                                          *((_QWORD *)v548 + 44) = v288 - *((_QWORD *)v548 + 14);
                                                          *((_QWORD *)v292 + 59) = __rdtsc() - *((_QWORD *)v292 + 29);
                                                          v293 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + SystemThread_TlsIndex)
                                                               + SystemThread_TlsOffset;
                                                          v294 = *(_QWORD **)(v293 + 256);
                                                          if ( !v294 )
                                                          {
                                                            SystemThread::MakeMiniSOSThread(0);
                                                            v294 = *(_QWORD **)(v293 + 256);
                                                          }
                                                          if ( v294[107] )
                                                          {
                                                            v296 = __rdtsc();
                                                            v297 = v294[108];
                                                            if ( v296 <= v297 )
                                                              v298 = 0;
                                                            else
                                                              v298 = v296 - v297;
                                                            v295 = v298 + v294[109];
                                                          }
                                                          else
                                                          {
                                                            v295 = 0;
                                                          }
                                                          *((_QWORD *)v292 + 14) = v295;
                                                          *((_QWORD *)v292 + 29) = __rdtsc();
                                                          *((_DWORD *)v548 + 134) = 1;
                                                        }
                                                      }
                                                      v299 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + SystemThread_TlsIndex)
                                                           + SystemThread_TlsOffset;
                                                      v300 = *(_QWORD *)(v299 + 256);
                                                      if ( !v300 )
                                                      {
                                                        SystemThread::MakeMiniSOSThread(0);
                                                        v300 = *(_QWORD *)(v299 + 256);
                                                      }
                                                      if ( *(_DWORD *)(*(_QWORD *)(v300 + 600) + 192LL) == 0x100000 )
                                                      {
                                                        v301 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + SystemThread_TlsIndex)
                                                                                     + SystemThread_TlsOffset)
                                                                         + 128LL);
                                                        *(_BYTE *)(v301 + 296) = 0;
                                                        *(_DWORD *)(v301 + 76) &= ~0x2000000u;
                                                        ex_raise(109, 61, 16, 2);
                                                      }
                                                      ExceptionPassOn((const struct SQLError *)v583);
                                                      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v764);
                                                    }
                                                    catch ( ShortStackException )
                                                    {
                                                    }
                                                    v19 = 0;
                                                    v492 = v571;
                                                    v30 = v707;
                                                    v188 = v495;
                                                    v508 = v597;
                                                    v201 = (const struct CCompExecCtxtStmt *)v546;
                                                  }
LABEL_1159:
                                                  v226 = v708;
                                                  if ( !v708 )
                                                  {
                                                    v227 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                           + SystemThread_TlsIndex)
                                                         + SystemThread_TlsOffset;
                                                    v226 = *(struct Worker **)(v227 + 256);
                                                    if ( !v226 )
                                                    {
                                                      SystemThread::MakeMiniSOSThread(0);
                                                      v226 = *(struct Worker **)(v227 + 256);
                                                    }
                                                  }
                                                  if ( *((_DWORD *)v226 + 139) )
                                                    ExceptionPostCatchActions(v226);
                                                  goto LABEL_460;
                                                }
                                                v506 = 0;
                                                v146 = (v863 >= 130 || (v145 & 0x10) != 0) && (v864 & 1) != 0;
                                                v503[0] = v146;
                                                v147 = v863 >= 130 || (v145 & 0x10) != 0;
                                                v503[1] = v147;
                                                v504 = 0;
                                                v505 = 0;
                                                OptimizerUtil::FindNode<CDetermineBatchModeEligibility>(v131, v503);
                                                if ( v505 )
                                                  v860 |= 0x40u;
                                                v148 = v595;
                                                v149 = v595 && (unsigned __int8)QueryHints::FHintSet(v595, 21);
                                                if ( !v504 && (*((_BYTE *)qword_102ECFB10 + 1643) & 2) == 0 )
                                                {
                                                  v150 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + SystemThread_TlsIndex)
                                                                   + SystemThread_TlsOffset);
                                                  if ( !v150
                                                    || (v151 = **(struct CSessionTraceFlags ***)(v150 + 56)) == 0
                                                    || !CSessionTraceFlags::CheckSessionTraceInternal(v151, 0x3359u) )
                                                  {
                                                    v131 = v493;
LABEL_323:
                                                    CExecLvlRepresentation::FInternal(v495);
                                                    v152 = v863 >= 150
                                                        || (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 81);
                                                    if ( v152
                                                      && (unsigned __int8)CQOFeatureSwitches::FIsSet(v852, 82)
                                                      && v303
                                                      && v302 )
                                                    {
                                                      v866 |= 0x20u;
                                                    }
                                                    v153 = (v860 & 8) == 0 && (v866 & 0x20) != 0 && (v859 & 8) != 0;
                                                    v154 = CQOFeatureSwitches::FIsSet(v852, 83);
                                                    if ( (v153 || v154) && v155 )
                                                    {
                                                      v156 = v148 && (unsigned __int8)QueryHints::FHintSet(v148, 23);
                                                      if ( !v156 && v153 && v874 )
                                                        v156 = FindNode<CDetermineBatchModePlanHint>(&v518) != 0;
                                                      COptContext::ActivateBatchModeHeuristics(
                                                        (COptContext *)v846,
                                                        v153,
                                                        v156);
                                                    }
                                                    v136 = v495;
                                                    goto LABEL_340;
                                                  }
                                                  v131 = v493;
                                                }
                                                if ( !v149 )
                                                {
                                                  v860 |= 0x2Cu;
                                                  if ( !COptContext::FNoMinimumDistanceGuarantee((COptContext *)v846) )
                                                    *((_BYTE *)v873 + 75) = 1;
                                                }
                                                goto LABEL_323;
                                              }
LABEL_181:
                                              if ( !*(_BYTE *)(v850 + 31) )
                                                goto LABEL_182;
                                              goto LABEL_644;
                                            }
                                            if ( !*(_BYTE *)(v850 + 30) )
                                              v867 |= 0x20u;
                                          }
                                          if ( !v54 )
                                            goto LABEL_181;
                                          goto LABEL_180;
                                        }
                                      }
LABEL_531:
                                      v866 |= 0x40u;
                                      goto LABEL_163;
                                    }
                                  }
LABEL_641:
                                  v865 |= 0x40u;
                                  goto LABEL_157;
                                }
LABEL_152:
                                if ( (unsigned __int8)QueryHints::FHintSet(v54, 11) )
                                  goto LABEL_641;
                                goto LABEL_153;
                              }
                            }
LABEL_529:
                            v865 |= 0x20u;
                            goto LABEL_146;
                          }
LABEL_139:
                          v865 |= 0x10u;
                          goto LABEL_140;
                        }
                        v659 = *v239;
                        if ( !CSessionTraceFlags::CheckSessionTraceInternal(v240, 0x26D3u) )
                          goto LABEL_489;
                      }
                    }
                    v91 = 1;
                    goto LABEL_130;
                  }
                  v658 = *v88;
                  if ( !CSessionTraceFlags::CheckSessionTraceInternal(v89, 0x102Au) )
                    goto LABEL_124;
                }
              }
              v864 |= 0x80u;
              goto LABEL_124;
            }
            v719 = 0;
            v235 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                 + SystemThread_TlsOffset;
            if ( *(_QWORD *)v235
              && (v236 = *(struct CSessionTraceFlags ***)(*(_QWORD *)v235 + 56LL), (v237 = *v236) != 0) )
            {
              v654 = *v236;
              if ( CSessionTraceFlags::CheckSessionTraceInternal(v237, 0x2754u) )
                goto LABEL_479;
            }
            else
            {
              v654 = 0;
            }
            v720 = 2418;
            v527 = *((_BYTE *)qword_102ECFB10 + 302) >> 2;
            if ( (v527 & 1) == 0 )
            {
              v721 = 0;
              v320 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset);
              if ( !v320 || (v321 = *(struct CSessionTraceFlags ***)(v320 + 56), (v322 = *v321) == 0) )
              {
                v655 = 0;
LABEL_92:
                v78 = v859 | 8;
                v859 |= 8u;
                goto LABEL_93;
              }
              v655 = *v321;
              if ( !CSessionTraceFlags::CheckSessionTraceInternal(v322, 0x972u) )
              {
                v78 = v859 | 8;
                v859 |= 8u;
                goto LABEL_93;
              }
            }
LABEL_479:
            v78 = v859;
            goto LABEL_93;
          }
          v653 = *v76;
          if ( !CSessionTraceFlags::CheckSessionTraceInternal(v77, 0x24AEu) )
            goto LABEL_90;
        }
        v861 |= 8u;
        goto LABEL_90;
      }
LABEL_607:
      v864 |= 2u;
      goto LABEL_85;
    }
LABEL_585:
    v62 = 1;
    goto LABEL_55;
  }
  catch ( SQLError v731 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v765, (const struct SQLError *)v731);
      CInterleavedExecUtil::CleanUpTvfTablesOnException((const struct CCompExecCtxtStmt *)v546);
      v254 = v731[0] / 100 == 29 && v731[0] == 2906;
      v491 = v254;
      *((_BYTE *)v495 + 44) &= ~8u;
      if ( v731[0] / 100 != 29 && v509 )
        (**(void (__fastcall ***)(struct IQueryCompile *, __int64))v509)(v509, 1);
      v255 = v571;
      if ( v571 )
      {
        (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v571 + 240LL))(v571);
        (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v255 + 16LL))(v255);
      }
      v256 = (CCompTimeTrace *)*((_QWORD *)v495 + 8);
      if ( v256 )
      {
        CCompTimeTrace::HandlePqoBuildExceptionCase(v256);
        v541 = (struct CEsCompGroup *)*((_QWORD *)v495 + 8);
        if ( !*((_DWORD *)v541 + 175) )
        {
          v257 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v258 = *(_QWORD **)(v257 + 256);
          if ( !v258 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v258 = *(_QWORD **)(v257 + 256);
          }
          if ( v258[107] )
          {
            v260 = __rdtsc();
            v261 = v258[108];
            if ( v260 <= v261 )
              v262 = 0;
            else
              v262 = v260 - v261;
            v259 = v262 + v258[109];
          }
          else
          {
            v259 = 0;
          }
          v263 = v541;
          *((_QWORD *)v541 + 44) = v259 - *((_QWORD *)v541 + 14);
          *((_QWORD *)v263 + 59) = __rdtsc() - *((_QWORD *)v263 + 29);
          v264 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v265 = *(_QWORD **)(v264 + 256);
          if ( !v265 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v265 = *(_QWORD **)(v264 + 256);
          }
          if ( v265[107] )
          {
            v267 = __rdtsc();
            v268 = v265[108];
            if ( v267 <= v268 )
              v269 = 0;
            else
              v269 = v267 - v268;
            v266 = v269 + v265[109];
          }
          else
          {
            v266 = 0;
          }
          *((_QWORD *)v263 + 14) = v266;
          *((_QWORD *)v263 + 29) = __rdtsc();
          *((_DWORD *)v541 + 134) = 1;
          v254 = v491;
        }
      }
      if ( !v254 )
        ExceptionPassOn((const struct SQLError *)v731);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v765);
    }
    catch ( ShortStackException )
    {
    }
    v19 = 0;
    v228 = v571;
    v188 = v495;
    v229 = v597;
    v201 = (const struct CCompExecCtxtStmt *)v546;
    goto LABEL_464;
  }
LABEL_1154:
  v228 = v492;
  v229 = v508;
LABEL_464:
  v230 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v231 = *(struct Worker **)(v230 + 256);
  if ( !v231 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v231 = *(struct Worker **)(v230 + 256);
  }
  if ( *((_DWORD *)v231 + 139) )
    ExceptionPostCatchActions(v231);
  if ( v491 )
  {
    v465 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v466 = *(_QWORD *)(v465 + 256);
    if ( !v466 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v466 = *(_QWORD *)(v465 + 256);
    }
    *(_DWORD *)(v466 + 800) &= ~0x20u;
    ex_raise(86, 21, 17, 1);
  }
  (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)v228 + 16LL))(v228);
  g_CRV_QOptconsiderlow = 0;
  v232 = (__int64 *)*((_QWORD *)v188 + 8);
  if ( v232 )
  {
    v467 = *v232;
    if ( !*v232 || !v232[15] )
      *((_BYTE *)v232 + 704) = 0;
    v468 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v469 = *(_QWORD **)(v468 + 256);
    if ( !v469 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v469 = *(_QWORD **)(v468 + 256);
      v467 = *v232;
    }
    if ( v469[107] )
    {
      v472 = __rdtsc();
      v473 = v469[108];
      if ( v472 <= v473 )
        v474 = 0;
      else
        v474 = v472 - v473;
      v470 = v474 + v469[109];
    }
    else
    {
      v470 = 0;
    }
    v232[30] += v470 - v467;
    v471 = __rdtsc();
    v232[45] += (((unsigned __int64)HIDWORD(v471) << 32) | (unsigned int)v471) - v232[15];
    *v232 = 0;
    v232[15] = 0;
    ++*((_DWORD *)v232 + 120);
  }
  v233 = *((_QWORD *)v188 + 8);
  if ( v233 && !*(_DWORD *)(v233 + 700) )
  {
    v475 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v476 = *(_QWORD **)(v475 + 256);
    if ( !v476 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v476 = *(_QWORD **)(v475 + 256);
    }
    if ( v476[107] )
    {
      v483 = __rdtsc();
      v484 = v476[108];
      if ( v483 <= v484 )
        v485 = 0;
      else
        v485 = v483 - v484;
      v477 = v485 + v476[109];
    }
    else
    {
      v477 = 0;
    }
    *(_QWORD *)(v233 + 352) = v477 - *(_QWORD *)(v233 + 112);
    *(_QWORD *)(v233 + 472) = __rdtsc() - *(_QWORD *)(v233 + 232);
    v478 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v479 = *(_QWORD **)(v478 + 256);
    if ( !v479 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v479 = *(_QWORD **)(v478 + 256);
    }
    if ( v479[107] )
    {
      v480 = __rdtsc();
      v481 = v479[108];
      if ( v480 <= v481 )
        v482 = 0;
      else
        v482 = v480 - v481;
      v19 = v482 + v479[109];
    }
    *(_QWORD *)(v233 + 112) = v19;
    *(_QWORD *)(v233 + 232) = __rdtsc();
    *(_DWORD *)(v233 + 536) = 1;
  }
  PublishQPQualityTelemetryPackage(v229, v201, v509);
  CAutoP<CAutoSessionTraceFlagOrQORuleToggler>::~CAutoP<CAutoSessionTraceFlagOrQORuleToggler>(&v710);
  return v534;
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
