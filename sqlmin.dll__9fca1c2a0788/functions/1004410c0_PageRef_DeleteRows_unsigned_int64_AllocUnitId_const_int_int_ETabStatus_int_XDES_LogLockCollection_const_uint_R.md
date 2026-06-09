# PageRef::DeleteRows(unsigned __int64,AllocUnitId const &,int,int,ETabStatus,int,XDES *,LogLockCollection const *,uint,RecVersioningInfo const *,PageRef::CheckDiffMapCalled,RecordHolder *)

- ea: `0x1004410c0`
- end: `0x100441a94`
- name: `?DeleteRows@PageRef@@QEAAX_KAEBVAllocUnitId@@HHW4ETabStatus@@HPEAVXDES@@PEBVLogLockCollection@@IPEBVRecVersioningInfo@@W4CheckDiffMapCalled@1@PEAVRecordHolder@@@Z`
- size: `2516`
- prototype: `void __high(unsigned __int64, const struct AllocUnitId *, int, int, enum ETabStatus, int, struct XDES *, const struct LogLockCollection *, unsigned int, const struct RecVersioningInfo *, enum PageRef::CheckDiffMapCalled, struct RecordHolder *)`
- caller_count: `17`
- callee_count: `49`
- tags: `broker_com_uri`

## callers

- `0x100456940`
- `0x10045bcc0`
- `0x10048abf0`
- `0x100491f60`
- `0x1005b1c20`
- `0x1005bc080`
- `0x1005de550`
- `0x1012a6660`
- `0x1012ab8a0`
- `0x1012fa3b0`
- `0x101371880`
- `0x1016b5920`
- `0x10191e410`
- `0x101945bf0`
- `0x101e8ea00`
- `0x101e90a20`
- `0x101e9a4c0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100415e90`
- `0x10042d750`
- `0x100432c80`
- `0x10043dd90`
- `0x10043e110`
- `0x1004410c0`
- `0x100441e00`
- `0x100445e80`
- `0x100455720`
- `0x10046bf90`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x100480640`
- `0x1004807a0`
- `0x1004813c0`
- `0x100481c40`
- `0x10048b650`
- `0x10048c200`
- `0x10049dc80`
- `0x1004a6ea0`
- `0x1004b4190`
- `0x10058cca0`
- `0x100605a70`
- `0x100605c50`
- `0x100606760`
- `0x101200050`
- `0x1012c9010`
- `0x10168b160`
- `0x1016c99f0`
- `0x101726350`
- `0x1018af2f0`
- `0x1018b1210`
- `0x1018b2dd0`
- `0x1018bc9e0`
- `0x101912d90`
- `0x101d0fad0`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e8950`
- `0x1021e8ae0`
- `0x1021e8b50`
- `0x1021eab40`
- `0x1021ed230`
- `0x102394d80`
- `0x10249c620`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1018d82dd`
- `KERNEL32!HeapAlloc` at `0x1018d82dd`
- `KERNEL32!GetProcessHeap` at `0x1018d82cc`
- `KERNEL32!GetProcessHeap` at `0x1018d82cc`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018d829d`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018d829d`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018d83b7`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018d83b7`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d844a`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d846c`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d844a`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d846c`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d84ea`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d8510`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d84ea`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d8510`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018d8312`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018d8312`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d8487`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d84b1`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d8487`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d84b1`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d839a`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d83a8`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d839a`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d83a8`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d82b7`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d82c5`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d82b7`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d82c5`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018d832d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018d832d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d814f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8229`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8266`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d838c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d83ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8df5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8edf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8f0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8f40`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9542`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d956d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d95e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d960b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9636`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9924`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d994f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9e9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9f43`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da488`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da57d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da5a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da5de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dac3c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dac67`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dacd2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dacfd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dad33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db170`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db537`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db562`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db684`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db6ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db6d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db9a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db9cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dbf5e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc016`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc03c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc067`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc09d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc37c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc3a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc43a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc901`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc99e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcb8a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcbf4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcfbc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcfe7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd01d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd494`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd4bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd609`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd6c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd77b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd981`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dda37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018ddeba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018ddf5b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de169`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de1e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de2af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de37e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de44e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de629`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de6e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb08`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dee70`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dee9b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018defa2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018df245`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d814f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8229`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8266`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d838c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d83ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8df5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8edf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8f0a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d8f40`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9542`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d956d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d95e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d960b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9636`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9924`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d994f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9e9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d9f43`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da488`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da57d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da5a8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018da5de`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dac3c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dac67`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dacd2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dacfd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dad33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db170`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db537`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db562`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db684`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db6ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db6d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db9a0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018db9cb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dbf5e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc016`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc03c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc067`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc09d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc37c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc3a7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc43a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc901`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dc99e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcb8a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcbf4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcfbc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dcfe7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd01d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd494`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd4bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd609`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd6c4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd77b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dd981`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dda37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018ddeba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018ddf5b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de169`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de1e0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de2af`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de37e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de44e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de629`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018de6e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb08`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb33`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018deb69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dee70`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018dee9b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018defa2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018df245`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d8a09`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d8ac7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d8b8b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d9108`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d91b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d92e8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d9395`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d943f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d97dd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d987d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da0be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da174`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da22e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da7a1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da847`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018da984`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018daa3a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018daaf4`

## string_xrefs

- `0x1018d849c`: `BUF in PageRef::ComputeLogMode:`
- `0x1018d8472`: `DBTABLE in PageRef::ComputeLogMode:`
- `0x1018d821b`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018d8380`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018d825d`: `!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)`

## pseudocode

```c

```

## disassembly

```asm
0x1004410c0  push    rbp
0x1004410c2  push    rsi
0x1004410c3  push    rdi
0x1004410c4  push    r12
0x1004410c6  push    r13
0x1004410c8  push    r14
0x1004410ca  push    r15
0x1004410cc  mov     eax, 2B10h
0x1004410d1  call    _alloca_probe
0x1004410d6  sub     rsp, rax
0x1004410d9  lea     rbp, [rsp+40h]
0x1004410de  mov     [rbp+2B00h+var_2870], 0FFFFFFFFFFFFFFFEh
0x1004410e9  mov     [rbp+2B00h+arg_8], rbx
0x1004410f0  mov     rax, cs:__security_cookie
0x1004410f7  xor     rax, rbp
0x1004410fa  mov     [rbp+2B00h+var_40], rax
0x100441101  mov     [rbp+2B00h+var_2AF8], r9d
0x100441105  mov     rbx, r8
0x100441108  mov     [rbp+2B00h+var_2A10], rbx
0x10044110f  mov     [rbp+2B00h+var_2910], rdx
0x100441116  mov     r15, rcx
0x100441119  mov     [rbp+2B00h+var_29A8], rcx
0x100441120  mov     rax, [rbp+2B00h+arg_50]
0x100441127  mov     [rbp+2B00h+var_29B0], rax
0x10044112e  mov     eax, [rbp+2B00h+arg_20]
0x100441134  mov     [rbp+2B00h+var_2AF4], eax
0x100441137  mov     r14, [rbp+2B00h+arg_38]
0x10044113e  mov     [rbp+2B00h+var_29C8], r14
0x100441145  mov     rax, [rbp+2B00h+arg_60]
0x10044114c  mov     [rbp+2B00h+var_29A0], rax
0x100441153  mov     [rbp+2B00h+var_2AE8], 1
0x10044115a  xor     r12d, r12d
0x10044115d  mov     [rbp+2B00h+var_29F0], r12
0x100441164  mov     [rbp+2B00h+var_2A24], r12d
0x10044116b  mov     [rbp+2B00h+var_2A20], r12w
0x100441173  mov     r13d, r12d
0x100441176  mov     [rbp+2B00h+var_2B00], r12w
0x10044117b  mov     [rbp+2B00h+var_2918], r12
0x100441182  mov     eax, r12d
0x100441185  mov     [rbp+2B00h+var_2648], rax
0x10044118c  mov     [rbp+2B00h+var_2640], r12d
0x100441193  mov     [rbp+2B00h+var_263C], r12w
0x10044119b  mov     [rbp+2B00h+var_29D0], r12
0x1004411a2  mov     [rbp+2B00h+var_2A1C], r12d
0x1004411a9  mov     edi, [rbp+2B00h+arg_48]
0x1004411af  mov     [rbp+2B00h+var_2AE4], edi
0x1004411b2  test    r14, r14
0x1004411b5  jz      loc_1018D7E5E
0x1004411bb  mov     rax, [r14+30h]
0x1004411bf  mov     [rbp+2B00h+var_29D0], rax
0x1004411c6  mov     rax, [r14]
0x1004411c9  mov     rcx, r14
0x1004411cc  call    qword ptr [rax]
0x1004411ce  mov     ecx, edi
0x1004411d0  shr     ecx, 15h
0x1004411d3  and     ecx, 2
0x1004411d6  test    al, al
0x1004411d8  mov     edi, 1
0x1004411dd  cmovnz  ecx, edi
0x1004411e0  mov     [rbp+2B00h+var_2A1C], ecx
0x1004411e6  jmp     short loc_1004411E9
0x1004411e9  mov     esi, 0EDFFh
0x1004411ee  cmp     [rbp+2B00h+arg_58], r12d
0x1004411f5  jnz     loc_100441361
0x1004411fb  xor     r9d, r9d
0x1004411fe  mov     r8d, edi
0x100441201  mov     rdx, [r15]
0x100441204  mov     rcx, cs:qword_10317B628
0x10044120b  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x100441210  and     [rax+4], si
0x100441214  mov     [rax+40h], edi
0x100441217  mov     r11, [r15]
0x10044121a  mov     eax, 2
0x10044121f  cmp     ax, [r11+2Ch]
0x100441224  jz      loc_10044134B
0x10044122a  mov     rax, [r11+90h]
0x100441231  test    rax, rax
0x100441234  jz      loc_1018D7E69
0x10044123a  mov     rcx, [rax+6B0h]
0x100441241  test    byte ptr [rcx+3Ch], 1
0x100441245  jnz     loc_1018D7E81
0x10044124b  mov     r11, [r15]
0x10044124e  mov     rax, [r11+90h]
0x100441255  test    rax, rax
0x100441258  jz      loc_1018D7EBC
0x10044125e  test    byte ptr [rax+1CD0h], 20h
0x100441265  jnz     loc_10044134B
0x10044126b  mov     rax, [r15]
0x10044126e  mov     r11, [rax]
0x100441271  cmp     [r11+24h], r12w
0x100441276  jz      short loc_100441295
0x100441278  movzx   eax, byte ptr [r11+1]
0x10044127d  cmp     al, 0Bh
0x10044127f  jz      loc_1018D7ED1
0x100441285  cmp     al, 8
0x100441287  jz      loc_1018D7F1E
0x10044128d  cmp     al, 9
0x10044128f  jz      loc_1018D7F1E
0x100441295  movsd   xmm0, qword ptr [r11+28h]
0x10044129b  movsd   [rbp+2B00h+var_2980], xmm0
0x1004412a3  movzx   eax, word ptr [r11+30h]
0x1004412a8  mov     [rbp+2B00h+var_2978], ax
0x1004412af  mov     r11, [r15]
0x1004412b2  mov     rcx, [r11+90h]
0x1004412b9  test    rcx, rcx
0x1004412bc  jz      loc_1018D7F2B
0x1004412c2  movzx   edx, word ptr [r11+74h]
0x1004412c7  xor     r8d, r8d
0x1004412ca  mov     rcx, [rcx+6A0h]
0x1004412d1  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x1004412d6  mov     rdi, rax
0x1004412d9  mov     rbx, [r15]
0x1004412dc  mov     rax, [rbx+90h]
0x1004412e3  mov     r11, rbx
0x1004412e6  test    rax, rax
0x1004412e9  jz      loc_1018D7F40
0x1004412ef  mov     rax, [rax+7A8h]
0x1004412f6  cmp     [rax+58h], r12d
0x1004412fa  jnz     loc_1004B9999
0x100441300  mov     eax, [rdi+130h]
0x100441306  cmp     eax, dword ptr [rbp+2B00h+var_2980]
0x10044130c  ja      loc_1004B9999
0x100441312  jz      loc_1004B9971
0x100441318  mov     rax, [r11+90h]
0x10044131f  test    rax, rax
0x100441322  jz      loc_1018D7F86
0x100441328  mov     r8, [r11]
0x10044132b  mov     rax, [rax+7A8h]
0x100441332  cmp     [rax+110h], r12d
0x100441339  jnz     loc_1018D7F9E
0x10044133f  mov     edi, 1
0x100441344  mov     rbx, [rbp+2B00h+var_2A10]
0x10044134b  mov     rax, [r15]
0x10044134e  mov     r11, [rax]
0x100441351  mov     edx, 2000h
0x100441356  test    [r11+4], dx
0x10044135b  jnz     loc_1018D800C
0x100441361  xor     r9d, r9d
0x100441364  mov     r8d, edi
0x100441367  mov     rdx, [r15]
0x10044136a  mov     rcx, cs:qword_10317B628
0x100441371  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x100441376  and     [rax+4], si
0x10044137a  mov     [rax+40h], edi
0x10044137d  mov     r11, [r15]
0x100441380  mov     rsi, [r11]
0x100441383  mov     [rbp+2B00h+var_2AE0], rsi
0x100441387  mov     eax, [rbx]
0x100441389  mov     [rbp+2B00h+var_2998], eax
0x10044138f  movzx   eax, word ptr [rbx+4]
0x100441393  mov     [rbp+2B00h+var_2994], ax
0x10044139a  movzx   eax, word ptr [rbx+6]
0x10044139e  mov     [rbp+2B00h+var_2992], ax
0x1004413a5  mov     ebx, [rbp+2B00h+arg_28]
0x1004413ab  mov     [rbp+2B00h+var_2A18], ebx
0x1004413b1  mov     r8d, 0FFh
0x1004413b7  bt      ebx, 16h
0x1004413bb  jb      loc_100492AB0
0x1004413c1  mov     eax, [r11+64h]
0x1004413c5  bt      eax, 13h
0x1004413c9  jb      loc_1018D8120
0x1004413cf  mov     r15d, r12d
0x1004413d2  jmp     short loc_1004413D5
0x1004413d5  movzx   eax, byte ptr [rsi+1]
0x1004413d9  mov     [rbp+2B00h+var_2A08], 9
0x1004413e3  mov     edi, 0Fh
0x1004413e8  mov     [rbp+2B00h+var_2AF0], edi
0x1004413eb  mov     edx, 0FFFh
0x1004413f0  cmp     al, 3
0x1004413f2  jz      loc_1018D8544
0x1004413f8  cmp     al, 1
0x1004413fa  jnz     short loc_100441404
0x1004413fc  test    al, bl
0x1004413fe  jz      loc_1018D8520
0x100441404  mov     [rbp+2B00h+var_2A28], 2
0x10044140e  mov     eax, [rbp+2B00h+var_2AA0]
0x100441411  mov     [rbp+2B00h+var_29E8], eax
0x100441417  mov     eax, [rbp+2B00h+var_2AA0]
0x10044141a  mov     [rbp+2B00h+var_2A04], eax
0x100441420  mov     r13d, [rbp+2B00h+var_2AE4]
0x100441424  mov     ecx, r13d
0x100441427  mov     eax, 100h
0x10044142c  movzx   edx, [rbp+2B00h+var_2B00]
0x100441430  mov     r8d, 80h
0x100441436  or      dx, r8w
0x10044143a  and     ecx, eax
0x10044143c  cmovz   dx, [rbp+2B00h+var_2B00]
0x100441441  mov     eax, r13d
0x100441444  mov     r8d, 800h
0x10044144a  movzx   ecx, dx
0x10044144d  or      cx, r8w
0x100441451  and     eax, r8d
0x100441454  cmovz   cx, dx
0x100441458  mov     r14d, r13d
0x10044145b  mov     eax, 2000h
0x100441460  and     r14d, eax
0x100441463  mov     eax, 1000h
0x100441468  movzx   ebx, cx
0x10044146b  or      bx, ax
0x10044146e  test    r14d, r14d
0x100441471  cmovz   bx, cx
0x100441475  mov     rdi, [rbp+2B00h+var_29C8]
0x10044147c  mov     eax, [rdi+218h]
0x100441482  and     al, 5
0x100441484  mov     [rbp+2B00h+var_2AFC], bx
0x100441488  cmp     al, 1
0x10044148a  jnz     short loc_100441498
0x10044148c  test    [rdi+2D8h], al
0x100441492  jnz     loc_1018DC3E9
0x100441498  test    r15d, r15d
0x10044149b  jnz     loc_100492B13
0x1004414a1  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1004414a8  mov     [rbp+2B00h+var_2750], r9w
0x1004414b0  mov     [rbp+2B00h+var_2748], r12
0x1004414b7  mov     [rbp+2B00h+var_274C], r12d
0x1004414be  mov     [rbp+2B00h+var_2738+6], r12
0x1004414c5  mov     [rbp+2B00h+var_2728], r12
0x1004414cc  mov     [rbp+2B00h+var_2740], r12
0x1004414d3  mov     [rbp+2B00h+var_271C], r9d
0x1004414da  mov     [rbp+2B00h+var_26A0], r9w
0x1004414e2  mov     [rbp+2B00h+var_2698], r12
0x1004414e9  mov     [rbp+2B00h+var_269C], r12d
0x1004414f0  mov     [rbp+2B00h+var_2682], r12
0x1004414f7  mov     [rbp+2B00h+var_2678], r12
0x1004414fe  mov     [rbp+2B00h+var_2690], r12
0x100441505  mov     [rbp+2B00h+var_2668], r12
0x10044150c  mov     dword ptr [rbp+2B00h+DestinationSize], r12d
0x100441513  movzx   esi, r12w
0x100441517  mov     r15d, 1
0x10044151d  mov     [rbp+2B00h+var_2AA0], r15d
0x100441521  mov     ecx, [rbp+2B00h+var_2AF4]
0x100441524  cmp     ecx, r15d
0x100441527  jg      loc_100496204
0x10044152d  mov     rax, [rdi]
0x100441530  mov     rcx, rdi
0x100441533  call    qword ptr [rax+10h]
0x100441536  lea     r13, [rbp+2B00h+var_2500]
0x10044153d  mov     [rbp+2B00h+var_29C0], r13
0x100441544  test    al, al
0x100441546  jnz     loc_1018DC4B1
0x10044154c  lea     rax, [rbp+2B00h+var_2440]
0x100441553  mov     [rbp+2B00h+var_29F8], rax
0x10044155a  lea     rax, [rbp+2B00h+var_2428]
0x100441561  mov     [rbp+2B00h+var_2A00], rax
0x100441568  mov     [r13+10h], r12d
0x10044156c  mov     [r13+14h], r12w
0x100441571  mov     [r13+3Eh], r12w
0x100441576  mov     r8d, [rbp+2B00h+arg_30]
0x10044157d  mov     rax, [rbp+2B00h+var_2AE0]
0x100441581  cmp     byte ptr [rax+1], 1
0x100441585  jnz     short loc_100441593
0x100441587  mov     eax, r8d
0x10044158a  neg     eax
0x10044158c  sbb     si, si
0x10044158f  and     si, 4
0x100441593  mov     ebx, [rbp+2B00h+var_2AE4]
0x100441596  mov     eax, ebx
0x100441598  movzx   edi, si
0x10044159b  mov     ecx, 400h
0x1004415a0  or      di, cx
0x1004415a3  and     eax, 1000000h
0x1004415a8  cmovz   di, si
0x1004415ac  mov     rdx, [rbp+2B00h+var_29A8]
0x1004415b3  mov     rax, [rdx]
0x1004415b6  mov     rcx, [rax]
0x1004415b9  movzx   eax, byte ptr [rcx+1]
0x1004415bd  sub     al, 3
0x1004415bf  cmp     al, 1
0x1004415c1  jbe     loc_1018DC4CC
0x1004415c7  bt      ebx, 12h
0x1004415cb  jb      loc_1018DC4CC
0x1004415d1  mov     byte ptr [r13+16h], 3
0x1004415d6  mov     rax, [rdx]
0x1004415d9  movzx   ebx, word ptr [rax+62h]
0x1004415dd  mov     edx, [rbp+2B00h+var_2A18]
0x1004415e3  mov     rsi, [rbp+2B00h+var_2AE0]
0x1004415e7  mov     rcx, rsi
0x1004415ea  call    ?MapContext@PageLog@@SA?AW4LogContext@@AEBVPageHeader@@W4ETabStatus@@@Z; PageLog::MapContext(PageHeader const &,ETabStatus)
0x1004415ef  mov     [r13+17h], al
0x1004415f3  shr     bl, 3
0x1004415f6  and     bl, 1
0x1004415f9  mov     byte ptr [rsp+2B40h+var_2B18], bl; bool
0x1004415fd  mov     word ptr [rsp+2B40h+var_2B20], di; unsigned __int16
0x100441602  movsxd  rdi, [rbp+2B00h+var_2AF8]
0x100441606  mov     r9d, edi; int
0x100441609  mov     r8, rsi; struct PageHeader *
0x10044160c  mov     rdx, [rbp+2B00h+var_2A10]; struct AllocUnitId *
0x100441613  mov     rcx, r13; this
0x100441616  call    ?FillPageInfo@PageLog@@QEAAXAEBVAllocUnitId@@AEBVPageHeader@@HG_N@Z; PageLog::FillPageInfo(AllocUnitId const &,PageHeader const &,int,ushort,bool)
0x10044161b  mov     rax, [rbp+2B00h+var_2910]
0x100441622  mov     [r13+30h], rax
0x100441626  movzx   eax, [rbp+2B00h+var_2AFC]
0x10044162a  mov     [r13+3Ch], ax
0x10044162f  mov     [r13+38h], r12d
0x100441633  mov     ecx, [rbp+2B00h+var_2AE4]
0x100441636  test    ecx, 100008h
0x10044163c  jnz     loc_10048B5AA
0x100441642  test    cl, 4
0x100441645  jnz     loc_1004962B2
0x10044164b  mov     eax, ecx
  ... truncated ...
```
