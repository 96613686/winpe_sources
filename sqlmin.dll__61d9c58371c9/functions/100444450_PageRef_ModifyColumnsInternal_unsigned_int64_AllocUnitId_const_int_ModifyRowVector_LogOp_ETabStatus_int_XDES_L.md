# PageRef::ModifyColumnsInternal(unsigned __int64,AllocUnitId const &,int,ModifyRowVector &,LogOp,ETabStatus,int,XDES *,LogLockCollection const *,bool,void const *,uint,ModifyRowVector const *,PageRef::CheckDiffMapCalled,RecordHolder const *,int,bool,RecVersioningInfo const *)

- ea: `0x100444450`
- end: `0x10044463f`
- name: `?ModifyColumnsInternal@PageRef@@IEAAX_KAEBVAllocUnitId@@HAEAVModifyRowVector@@W4LogOp@@W4ETabStatus@@HPEAVXDES@@PEBVLogLockCollection@@_NPEBXIPEBV3@W4CheckDiffMapCalled@1@PEBVRecordHolder@@H7PEBVRecVersioningInfo@@@Z`
- size: `495`
- prototype: ``
- caller_count: `5`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x1004437c0`
- `0x1005b1c20`
- `0x1013016b0`
- `0x101909fe0`
- `0x10190b2c0`

## callees

- `0x100401490`
- `0x10042d750`
- `0x100432c80`
- `0x100441e00`
- `0x1004443e0`
- `0x100444450`
- `0x100445640`
- `0x100445e80`
- `0x1004489c0`
- `0x10044bbb0`
- `0x10044bcb0`
- `0x10044c300`
- `0x100453ae0`
- `0x100455720`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x100480640`
- `0x1004807a0`
- `0x1004813c0`
- `0x100481c40`
- `0x1004a6ea0`
- `0x10058cca0`
- `0x1006059f0`
- `0x100605a70`
- `0x100605c50`
- `0x100606760`
- `0x10168b160`
- `0x1016c99f0`
- `0x101726350`
- `0x101912d90`
- `0x101d0fad0`
- `0x1021d8a90`
- `0x1021eab40`
- `0x102394d80`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1018e773d`
- `KERNEL32!HeapAlloc` at `0x1018e773d`
- `KERNEL32!GetProcessHeap` at `0x1018e772c`
- `KERNEL32!GetProcessHeap` at `0x1018e772c`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018e76fa`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018e76fa`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018e7810`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018e7810`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e78a9`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e78cb`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e78a9`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e78cb`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e794d`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e7974`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e794d`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e7974`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018e776f`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018e776f`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e78e6`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e7910`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e78e6`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e7910`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e77f4`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e7802`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e77f4`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e7802`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e7717`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e7725`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e7717`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e7725`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018e778a`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018e778a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6336`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e64d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6537`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e65f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e66ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6772`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6979`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6a36`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6fc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6ff4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e701f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e70fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7125`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e756f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7688`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e76d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e77e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e785c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7b8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7be0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7e1b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6336`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e64d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6537`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e65f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e66ad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6772`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6979`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6a36`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6fc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e6ff4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e701f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e70fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7125`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e756f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7688`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e76d1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e77e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e785c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7b8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7be0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e7e1b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e65b1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e666a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6727`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6936`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e69f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6b81`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6c33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6ce4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6eca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6f6a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e65b1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e666a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6727`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6936`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e69f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6b81`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6c33`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6ce4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6eca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e6f6a`
- `sqldk!SystemThread_TlsIndex` at `0x1018e655c`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6615`
- `sqldk!SystemThread_TlsIndex` at `0x1018e66d2`
- `sqldk!SystemThread_TlsIndex` at `0x1018e68e1`
- `sqldk!SystemThread_TlsIndex` at `0x1018e699e`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6b24`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6bd6`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6c87`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6e6d`
- `sqldk!SystemThread_TlsIndex` at `0x1018e6f0d`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6565`
- `sqldk!SystemThread_TlsOffset` at `0x1018e661e`
- `sqldk!SystemThread_TlsOffset` at `0x1018e66db`
- `sqldk!SystemThread_TlsOffset` at `0x1018e68ea`
- `sqldk!SystemThread_TlsOffset` at `0x1018e69a7`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6b2d`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6bdf`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6c90`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6e76`
- `sqldk!SystemThread_TlsOffset` at `0x1018e6f16`

## string_xrefs

- `0x1018e78fb`: `BUF in PageRef::ComputeLogMode:`
- `0x1018e78d1`: `DBTABLE in PageRef::ComputeLogMode:`
- `0x1018e767e`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018e77da`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018e76c5`: `!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)`

## pseudocode

```c

```
