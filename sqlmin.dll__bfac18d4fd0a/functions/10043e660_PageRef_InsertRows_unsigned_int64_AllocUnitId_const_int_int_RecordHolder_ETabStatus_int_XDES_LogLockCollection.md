# PageRef::InsertRows(unsigned __int64,AllocUnitId const &,int,int,RecordHolder *,ETabStatus,int,XDES *,LogLockCollection const *,uint,PageRef::CheckDiffMapCalled)

- ea: `0x10043e660`
- end: `0x10043f041`
- name: `?InsertRows@PageRef@@QEAAX_KAEBVAllocUnitId@@HHPEAVRecordHolder@@W4ETabStatus@@HPEAVXDES@@PEBVLogLockCollection@@IW4CheckDiffMapCalled@1@@Z`
- size: `2529`
- prototype: `void __high(unsigned __int64, const struct AllocUnitId *, int, int, struct RecordHolder *, enum ETabStatus, int, struct XDES *, const struct LogLockCollection *, unsigned int, enum PageRef::CheckDiffMapCalled)`
- caller_count: `18`
- callee_count: `46`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10043e380`
- `0x100452460`
- `0x100459aa0`
- `0x10057d390`
- `0x1005b1c20`
- `0x1005b7610`
- `0x1005bc080`
- `0x100601a90`
- `0x1012a6660`
- `0x1012ab8a0`
- `0x1012f97b0`
- `0x1018ed9f0`
- `0x1018eeca0`
- `0x101945bf0`
- `0x10194e5b0`
- `0x1019517a0`
- `0x101e8ea00`
- `0x101e9a4c0`

## callees

- `0x100401490`
- `0x100402000`
- `0x10042d750`
- `0x100432c80`
- `0x10043d7b0`
- `0x10043da40`
- `0x10043dd90`
- `0x10043e240`
- `0x10043e660`
- `0x100441c10`
- `0x100441e00`
- `0x100441e40`
- `0x1004443e0`
- `0x100445e80`
- `0x1004489c0`
- `0x100453ae0`
- `0x100455720`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x100480640`
- `0x1004807a0`
- `0x1004813c0`
- `0x100481c40`
- `0x10048a4a0`
- `0x10048c200`
- `0x1004a6ea0`
- `0x10058cca0`
- `0x1005b8120`
- `0x1006059f0`
- `0x100605a70`
- `0x100605c50`
- `0x100606760`
- `0x1012c9010`
- `0x10168b160`
- `0x1016c99f0`
- `0x101726350`
- `0x1018b1210`
- `0x1018bd390`
- `0x101d0fad0`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`
- `0x102394d80`
- `0x1023aea90`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1018d431f`
- `KERNEL32!HeapAlloc` at `0x1018d431f`
- `KERNEL32!GetProcessHeap` at `0x1018d430e`
- `KERNEL32!GetProcessHeap` at `0x1018d430e`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018d42eb`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018d42eb`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018d43f7`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018d43f7`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d45a4`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d45c6`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d45a4`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d45c6`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d464b`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d4675`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d464b`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018d4675`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018d4354`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018d4354`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d45e1`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d460b`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d45e1`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018d460b`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d43db`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d43e9`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d43db`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018d43e9`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d42f9`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d4307`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d42f9`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018d4307`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018d436f`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018d436f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3dd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3e01`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3e2a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d40be`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d40e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4186`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4272`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d42bb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d43cd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4446`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4bc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4c85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4cad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4cd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4d03`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d50cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d50f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d51b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d56f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d579e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d57c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d57f1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d581c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d5ae1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d5b0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6084`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d615f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d618a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d61b5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d64c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d64ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6556`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d658e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d65ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d66a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6bf7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6c22`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6c4d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6d2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6d57`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d72c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d72f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d731b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d73fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7425`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7947`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d79ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7bc5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7c1d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3dd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3e01`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d3e2a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d40be`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d40e7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4186`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4272`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d42bb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d43cd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4446`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4bc9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4c85`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4cad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4cd8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d4d03`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d50cc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d50f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d51b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d56f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d579e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d57c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d57f1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d581c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d5ae1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d5b0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6084`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d615f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d618a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d61b5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d64c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d64ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6556`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d658e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d65ec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d66a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6bf7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6c22`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6c4d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6d2c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d6d57`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d72c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d72f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d731b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d73fa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7425`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7947`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d79ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7bc5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018d7c1d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3ba8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3c52`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3cfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3fd1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4069`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d47d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4896`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4955`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4ecb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4f73`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5395`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5447`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d54fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d59ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5a5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5cfd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5daf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5e62`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d635f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6401`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d67c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6878`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d692a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6b1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6bbb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6e8c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6f3d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6fef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d71e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d7283`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d7502`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3ba8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3c52`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3cfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d3fd1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4069`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d47d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4896`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4955`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4ecb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d4f73`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5395`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5447`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d54fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d59ba`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5a5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5cfd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5daf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d5e62`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d635f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6401`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d67c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6878`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d692a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6b1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6bbb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6e8c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6f3d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d6fef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d71e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d7283`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018d7502`
- `sqldk!SystemThread_TlsIndex` at `0x1018d3b4b`
- `sqldk!SystemThread_TlsIndex` at `0x1018d3bf5`
- `sqldk!SystemThread_TlsIndex` at `0x1018d3c9f`
- `sqldk!SystemThread_TlsIndex` at `0x1018d3f74`
- `sqldk!SystemThread_TlsIndex` at `0x1018d4014`
- `sqldk!SystemThread_TlsIndex` at `0x1018d477b`

## string_xrefs

- `0x1018d45f6`: `BUF in PageRef::ComputeLogMode:`
- `0x1018d45cc`: `DBTABLE in PageRef::ComputeLogMode:`
- `0x1018d6584`: `pPage->IsEmpty () || pXdes->InRollback ()`
- `0x1018d4264`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018d43c1`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018d669f`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018d42b2`: `!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PageRef::InsertRows(
        BUF **a1,
        __int64 a2,
        const struct AllocUnitId *a3,
        int a4,
        int a5,
        struct RecordHolder *a6,
        unsigned int a7,
        unsigned int a8,
        struct RecoveryUnit **a9,
        __int64 a10,
        unsigned int a11,
        int a12)
{
  BUF **v13; // rsi
  struct RecordHolder *v14; // rbx
  int v15; // r15d
  struct XdesId *v16; // r14
  char v17; // al
  int v18; // edx
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  BUF *v21; // r11
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r11
  char v26; // al
  BUF *v27; // r11
  __int64 v28; // rcx
  __int64 FCB; // rdi
  BUF *v30; // rbx
  __int64 v31; // rax
  BUF *v32; // r11
  unsigned int v33; // eax
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 v36; // r11
  __int64 v37; // rax
  unsigned __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rbx
  BUF *v42; // r11
  __int64 v43; // r9
  int v44; // edi
  XDES *v45; // rbx
  Page *v46; // rsi
  char v47; // al
  __int64 v48; // rdx
  __int64 v49; // r9
  __int16 v50; // ax
  struct XdesId *v51; // rdi
  unsigned int v52; // r14d
  unsigned int v53; // ebx
  unsigned int v54; // eax
  unsigned __int16 v55; // dx
  unsigned __int16 v56; // cx
  __int64 v57; // rdx
  __int16 v58; // bx
  XDES *v59; // rdi
  char v60; // al
  int v61; // ecx
  __int64 v62; // rdi
  unsigned __int16 v63; // bx
  unsigned __int16 v64; // si
  _BYTE *v65; // r14
  void **v66; // rax
  __int64 v67; // r8
  unsigned __int16 v68; // di
  BUF **v69; // rdx
  __int16 v70; // bx
  Page *v71; // r12
  int v72; // r14d
  PageLog *v73; // rbx
  __int64 v74; // rdx
  __int16 v75; // cx
  __int16 v76; // ax
  unsigned int v77; // edi
  __int64 i; // r12
  __int64 v79; // r13
  unsigned int v80; // ecx
  __int64 v81; // r14
  unsigned int *v82; // r8
  unsigned int v83; // ecx
  void *v84; // rax
  const void **v85; // r13
  unsigned int *v86; // r8
  XDES *v87; // rdi
  char v88; // r9
  unsigned __int16 v89; // ax
  struct BUF **v90; // r12
  int v91; // r13d
  unsigned int v92; // ebx
  struct RecordHolder *v93; // r14
  int v94; // r12d
  struct XdesId *v95; // r15
  const struct Record *v96; // r8
  XDES *v97; // r8
  void *v98; // rsp
  __int64 v99; // rdx
  unsigned __int64 v100; // rcx
  unsigned __int64 v101; // rcx
  void *v102; // rsp
  void *v103; // rsp
  unsigned __int64 v104; // rcx
  unsigned __int64 v105; // rcx
  void *v106; // rsp
  void *v107; // rsp
  unsigned int v108; // eax
  __int64 v109; // rax
  __int64 v110; // rcx
  struct RecoveryUnit *v111; // rcx
  __int64 v112; // rax
  __int64 v113; // rsi
  __int16 v114; // bx
  char v115; // al
  __int64 v116; // xmm1_8
  __int16 v117; // r11
  __int64 v118; // rcx
  struct BUF *v119; // rdx
  char v120; // al
  __int64 v121; // rax
  __int64 v122; // rcx
  unsigned int v123; // eax
  __int16 v124; // r8
  PageComprInfoCache **v125; // r14
  int v126; // ebx
  char *v127; // r9
  char *v128; // rax
  bool v129; // cc
  __int64 v130; // r8
  __int64 v131; // rcx
  unsigned int v132; // edi
  unsigned int v133; // r10d
  __int64 v134; // rax
  _WORD *v135; // rcx
  int v136; // eax
  int v137; // ebx
  unsigned __int8 v138; // cl
  struct BUF *v139; // r10
  __int16 v140; // r11
  __int64 v141; // r11
  RecoveryUnit *v142; // rcx
  __int64 v143; // r11
  __int64 v144; // r11
  __int64 v145; // r11
  unsigned int v146; // ecx
  __int64 v147; // rcx
  __int64 v148; // r11
  __int64 v149; // r11
  __int64 v150; // r11
  __int64 v151; // rdx
  char v152; // al
  int v153; // ecx
  unsigned __int16 *v154; // rsi
  unsigned __int16 v155; // ax
  __int64 v156; // rax
  __int64 v157; // rax
  unsigned int v158; // edx
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rcx
  unsigned int v162; // eax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  unsigned int v166; // edi
  unsigned int v167; // ecx
  unsigned int v168; // eax
  unsigned __int16 v169; // dx
  __int16 v170; // ax
  __int64 v171; // r8
  __int16 v172; // dx
  int v173; // eax
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v175; // r9
  __int64 v176; // rdx
  __int16 v177; // ax
  int v178; // ecx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  char v183; // cl
  unsigned int v184; // ecx
  _BYTE *v185; // rax
  __int64 v186; // r11
  __int16 v187; // cx
  __int16 v188; // ax
  XDES *v189; // rcx
  HANDLE ProcessHeap; // rax
  void **v191; // rax
  struct CDumpStream *v192; // rbx
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v194; // r9
  int v195; // r8d
  __int64 v196; // rcx
  _WORD *v197; // rdx
  int v198; // esi
  unsigned int v199; // r10d
  char *v200; // r8
  unsigned int v201; // ebx
  char v202; // dl
  BOOL v203; // edi
  char v204; // bl
  struct DbccThreadContext *Context; // rax
  struct DbccThreadContext *v206; // rax
  struct DbccThreadContext *v207; // rax
  struct DbccThreadContext *v208; // rax
  unsigned __int16 v209; // cx
  __int16 v210; // ax
  __int16 v211; // r8
  unsigned __int16 *v212; // rdi
  unsigned __int16 v213; // dx
  __int64 v214; // rax
  __int64 v215; // rax
  unsigned int v216; // r9d
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  _BYTE *v221; // rax
  unsigned int v222; // ebx
  unsigned __int16 v223; // r8
  __int16 v224; // cx
  __int16 v225; // dx
  struct RecVersioningInfo *v226; // rax
  __int64 v227; // r9
  __int64 v228; // rdx
  int v229; // r8d
  __int16 v230; // ax
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // rax
  __int64 v234; // rax
  char v235; // cl
  bool v236; // zf
  int PFSFreeSpaceAfterModify; // r9d
  unsigned __int8 v238; // dl
  unsigned __int8 v239; // cl
  unsigned int v240; // edi
  unsigned int v241; // ebx
  __int64 v242; // rcx
  __int64 v243; // rdx
  __int64 v244; // rcx
  _WORD *v245; // rdx
  char *v246; // r8
  unsigned int v247; // ebx
  char v248; // dl
  unsigned __int16 v249; // cx
  __int16 v250; // r8
  unsigned __int16 *v251; // rdi
  unsigned __int16 v252; // dx
  __int64 v253; // rax
  __int64 v254; // rax
  unsigned int v255; // r9d
  __int64 v256; // rax
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rax
  _BYTE *v260; // rax
  unsigned int v261; // ebx
  unsigned __int16 v262; // r8
  __int16 v263; // cx
  __int16 v264; // dx
  struct RecVersioningInfo *v265; // rax
  __int64 v266; // r9
  __int64 v267; // rdx
  int v268; // r8d
  __int16 v269; // ax
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  __int64 v273; // rax
  char v274; // cl
  unsigned int v275; // r10d
  char *v276; // r8
  unsigned int v277; // ebx
  char v278; // dl
  unsigned __int16 v279; // cx
  __int16 v280; // ax
  __int16 v281; // r8
  unsigned __int16 *v282; // rdi
  unsigned __int16 v283; // dx
  __int64 v284; // rax
  __int64 v285; // rax
  unsigned int v286; // r9d
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rax
  __int64 v290; // rax
  _BYTE *v291; // rax
  unsigned int v292; // ebx
  unsigned __int16 v293; // r8
  __int16 v294; // cx
  __int16 v295; // dx
  struct RecVersioningInfo *v296; // rax
  __int64 v297; // r9
  __int64 v298; // rdx
  int v299; // r8d
  __int16 v300; // ax
  __int64 v301; // rax
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  char v305; // cl
  __int64 v306; // r11
  char *v307; // r8
  char v308; // al
  int v309; // ecx
  __int16 *v310; // rsi
  __int16 v311; // ax
  __int64 v312; // rax
  __int64 v313; // rax
  int v314; // edx
  unsigned int v315; // r8d
  __int64 v316; // rax
  __int64 v317; // rax
  unsigned int v318; // ecx
  __int64 v319; // rax
  __int64 v320; // rax
  unsigned __int16 v321; // cx
  __int64 v322; // rax
  unsigned int v323; // edi
  unsigned int v324; // eax
  unsigned __int16 v325; // dx
  unsigned __int16 v326; // ax
  int v327; // eax
  struct RecVersioningInfo *v328; // rax
  __int64 v329; // r9
  __int64 v330; // rdx
  int v331; // r8d
  __int16 v332; // ax
  unsigned __int64 v333; // r8
  int v334; // ecx
  __int64 v335; // rax
  __int64 v336; // rax
  __int64 v337; // rax
  __int64 v338; // rax
  __int64 v339; // r8
  __int16 v340; // dx
  _BYTE *v341; // rax
  char *v342; // r8
  char v343; // al
  int v344; // ecx
  __int16 *v345; // rsi
  __int16 v346; // ax
  __int64 v347; // rax
  __int64 v348; // rax
  int v349; // edx
  unsigned int v350; // r8d
  __int64 v351; // rax
  __int64 v352; // rax
  unsigned int v353; // ecx
  __int64 v354; // rax
  __int64 v355; // rax
  unsigned __int16 v356; // cx
  __int64 v357; // rax
  unsigned int v358; // edi
  unsigned int v359; // eax
  unsigned __int16 v360; // dx
  unsigned __int16 v361; // ax
  int v362; // eax
  struct RecVersioningInfo *v363; // rax
  __int64 v364; // r9
  __int64 v365; // rdx
  int v366; // r8d
  __int16 v367; // ax
  unsigned __int64 v368; // r8
  int v369; // ecx
  __int64 v370; // rax
  __int64 v371; // rax
  __int64 v372; // rax
  __int64 v373; // rax
  __int64 v374; // r8
  __int16 v375; // dx
  _BYTE *v376; // rax
  BUF **v377; // r14
  __int64 v378; // r9
  struct RecoveryUnit *v379; // r12
  __int64 v380; // rdx
  int v381; // ecx
  int v382; // r8d
  _BYTE *v383; // rdi
  char v384; // al
  __int16 v385; // r11
  __int64 v386; // rcx
  __int64 v387; // rsi
  _BYTE *v388; // r8
  char v389; // dl
  __int16 v390; // dx
  unsigned __int16 v391; // cx
  __int64 v392; // rax
  __int16 v393; // cx
  int v394; // eax
  int v395; // ebx
  char v396; // dl
  unsigned __int16 v397; // cx
  __int16 v398; // ax
  char *v399; // rax
  _WORD *v400; // rdi
  __int64 v401; // rcx
  _WORD *v402; // rcx
  __int16 v403; // r8
  __int64 v404; // r10
  __int64 v405; // rcx
  _WORD *v406; // rdx
  _BYTE v407[8240]; // [rsp+0h] [rbp-2060h] BYREF
  struct XdesId *v408; // [rsp+2030h] [rbp-30h]
  struct XdesId *v409; // [rsp+2038h] [rbp-28h]
  unsigned __int16 *v410; // [rsp+2040h] [rbp-20h]
  __int64 v411; // [rsp+2048h] [rbp-18h]
  char v412; // [rsp+2060h] [rbp+0h]
  int v413; // [rsp+2064h] [rbp+4h]
  __int16 v414; // [rsp+2068h] [rbp+8h]
  unsigned int v415; // [rsp+206Ch] [rbp+Ch]
  __int16 v416; // [rsp+2070h] [rbp+10h]
  unsigned int v417; // [rsp+2074h] [rbp+14h]
  unsigned int v418; // [rsp+2078h] [rbp+18h]
  int v419; // [rsp+207Ch] [rbp+1Ch]
  unsigned __int16 v420[2]; // [rsp+2080h] [rbp+20h] BYREF
  unsigned __int16 v421[2]; // [rsp+2084h] [rbp+24h] BYREF
  __int16 v422; // [rsp+2088h] [rbp+28h]
  unsigned __int16 v423; // [rsp+208Ah] [rbp+2Ah] BYREF
  int v424; // [rsp+208Ch] [rbp+2Ch]
  _BYTE *v425; // [rsp+2090h] [rbp+30h]
  __int64 v426; // [rsp+2098h] [rbp+38h]
  unsigned int v427; // [rsp+20A0h] [rbp+40h]
  unsigned __int16 v428; // [rsp+20A4h] [rbp+44h]
  char *v429; // [rsp+20A6h] [rbp+46h]
  _TBYTE v430; // [rsp+20AEh] [rbp+4Eh]
  int v431; // [rsp+20B8h] [rbp+58h]
  __int16 v432; // [rsp+20C0h] [rbp+60h]
  unsigned __int16 v433; // [rsp+20C2h] [rbp+62h] BYREF
  int v434; // [rsp+20C4h] [rbp+64h]
  _BYTE *v435; // [rsp+20C8h] [rbp+68h]
  __int64 v436; // [rsp+20D0h] [rbp+70h]
  unsigned int v437; // [rsp+20D8h] [rbp+78h]
  unsigned __int16 v438; // [rsp+20DCh] [rbp+7Ch]
  char *v439; // [rsp+20DEh] [rbp+7Eh]
  _TBYTE v440; // [rsp+20E6h] [rbp+86h]
  int v441; // [rsp+20F0h] [rbp+90h]
  __int16 v442; // [rsp+20F8h] [rbp+98h]
  unsigned __int16 v443; // [rsp+20FAh] [rbp+9Ah] BYREF
  int v444; // [rsp+20FCh] [rbp+9Ch]
  _BYTE *v445; // [rsp+2100h] [rbp+A0h]
  __int64 v446; // [rsp+2108h] [rbp+A8h]
  unsigned int v447; // [rsp+2110h] [rbp+B0h]
  unsigned __int16 v448; // [rsp+2114h] [rbp+B4h]
  char *v449; // [rsp+2116h] [rbp+B6h]
  _TBYTE v450; // [rsp+211Eh] [rbp+BEh]
  int v451; // [rsp+2128h] [rbp+C8h]
  BUF **v452; // [rsp+2130h] [rbp+D0h]
  XDES *v453; // [rsp+2138h] [rbp+D8h]
  unsigned int v454; // [rsp+2140h] [rbp+E0h]
  unsigned int v455; // [rsp+2144h] [rbp+E4h]
  Page *v456; // [rsp+2148h] [rbp+E8h]
  unsigned int *v457; // [rsp+2150h] [rbp+F0h]
  int v458; // [rsp+2158h] [rbp+F8h]
  struct RecordHolder *v459; // [rsp+2160h] [rbp+100h]
  int v460; // [rsp+2168h] [rbp+108h]
  __int16 v461; // [rsp+2170h] [rbp+110h]
  int v462; // [rsp+2174h] [rbp+114h] BYREF
  int v463; // [rsp+2178h] [rbp+118h]
  struct XdesId *v464; // [rsp+2180h] [rbp+120h]
  __int64 v465; // [rsp+2188h] [rbp+128h] BYREF
  __int64 v466; // [rsp+2190h] [rbp+130h]
  int v467; // [rsp+2198h] [rbp+138h]
  PageLog *v468; // [rsp+21A0h] [rbp+140h]
  __int64 v469; // [rsp+21A8h] [rbp+148h]
  int v470; // [rsp+21B0h] [rbp+150h]
  int v471; // [rsp+21B8h] [rbp+158h] BYREF
  __int16 v472; // [rsp+21BCh] [rbp+15Ch]
  int v473; // [rsp+21C0h] [rbp+160h] BYREF
  __int16 v474; // [rsp+21C4h] [rbp+164h]
  int v475; // [rsp+21C8h] [rbp+168h] BYREF
  __int16 v476; // [rsp+21CCh] [rbp+16Ch]
  struct RecoveryUnit *v477; // [rsp+21D0h] [rbp+170h]
  void **v478; // [rsp+21D8h] [rbp+178h]
  __int64 v479; // [rsp+21E0h] [rbp+180h] BYREF
  unsigned __int16 v480; // [rsp+21E8h] [rbp+188h]
  __int64 v481; // [rsp+21F0h] [rbp+190h] BYREF
  unsigned __int16 v482; // [rsp+21F8h] [rbp+198h]
  __int64 v483; // [rsp+2200h] [rbp+1A0h] BYREF
  __int16 v484; // [rsp+2208h] [rbp+1A8h]
  int v485; // [rsp+2210h] [rbp+1B0h] BYREF
  __int16 v486; // [rsp+2214h] [rbp+1B4h]
  int v487; // [rsp+2218h] [rbp+1B8h] BYREF
  __int16 v488; // [rsp+221Ch] [rbp+1BCh]
  int v489; // [rsp+2220h] [rbp+1C0h] BYREF
  __int16 v490; // [rsp+2224h] [rbp+1C4h]
  __int64 v491; // [rsp+2228h] [rbp+1C8h] BYREF
  __int16 v492; // [rsp+2230h] [rbp+1D0h]
  int v493; // [rsp+2238h] [rbp+1D8h] BYREF
  __int16 v494; // [rsp+223Ch] [rbp+1DCh]
  __int64 v495; // [rsp+2240h] [rbp+1E0h]
  int v496; // [rsp+2248h] [rbp+1E8h]
  __int64 v497; // [rsp+2250h] [rbp+1F0h] BYREF
  __int16 v498; // [rsp+2258h] [rbp+1F8h]
  __int64 v499; // [rsp+2260h] [rbp+200h] BYREF
  __int64 v500; // [rsp+2268h] [rbp+208h] BYREF
  XDES *v501; // [rsp+2270h] [rbp+210h]
  __int64 v502; // [rsp+2290h] [rbp+230h]
  _BYTE v503[96]; // [rsp+22B0h] [rbp+250h] BYREF
  __int64 v504; // [rsp+2310h] [rbp+2B0h] BYREF
  __int16 v505; // [rsp+2318h] [rbp+2B8h]
  __int16 v506; // [rsp+2320h] [rbp+2C0h]
  unsigned __int16 v507; // [rsp+2322h] [rbp+2C2h] BYREF
  int v508; // [rsp+2324h] [rbp+2C4h]
  char *v509; // [rsp+2328h] [rbp+2C8h]
  PageComprInfoCache **v510; // [rsp+2330h] [rbp+2D0h]
  _BYTE v511[24]; // [rsp+2338h] [rbp+2D8h]
  int v512; // [rsp+2350h] [rbp+2F0h]
  int v513; // [rsp+2354h] [rbp+2F4h]
  PageComprInfoCache *v514[2]; // [rsp+2358h] [rbp+2F8h] BYREF
  __int128 v515; // [rsp+2368h] [rbp+308h]
  __int64 v516; // [rsp+2378h] [rbp+318h]
  _BYTE v517[14]; // [rsp+2380h] [rbp+320h] BYREF
  _TBYTE v518; // [rsp+238Eh] [rbp+32Eh]
  _OWORD v519[2]; // [rsp+2398h] [rbp+338h] BYREF
  __int128 v520; // [rsp+23B8h] [rbp+358h]
  __int64 v521; // [rsp+23C8h] [rbp+368h]
  __int64 v522; // [rsp+23D0h] [rbp+370h] BYREF
  int v523; // [rsp+23D8h] [rbp+378h]
  __int16 v524; // [rsp+23DCh] [rbp+37Ch]
  _BYTE v525[192]; // [rsp+23E0h] [rbp+380h] BYREF
  char v526; // [rsp+24A0h] [rbp+440h] BYREF
  char v527; // [rsp+24B0h] [rbp+450h] BYREF
  _BYTE v528[528]; // [rsp+24D0h] [rbp+470h] BYREF
  _BYTE v529[528]; // [rsp+26E0h] [rbp+680h] BYREF

  v502 = -2;
  v413 = a4;
  v466 = a2;
  v13 = a1;
  v452 = a1;
  v458 = a5;
  v14 = a6;
  v459 = a6;
  v453 = (XDES *)a9;
  v415 = 1;
  v15 = 0;
  v464 = 0;
  v16 = 0;
  v473 = 0;
  v474 = 0;
  v465 = 0;
  v462 = 0;
  v421[0] = 0;
  v495 = 0;
  v522 = 0;
  v523 = 0;
  v524 = 0;
  v420[0] = 0;
  v477 = 0;
  v455 = 0;
  v417 = a11;
  if ( a9 )
  {
    v477 = a9[6];
    v17 = (*(__int64 (__fastcall **)(struct RecoveryUnit **))*a9)(a9);
    v18 = (a11 >> 21) & 2;
    if ( v17 )
      v18 = 1;
    v455 = v18;
  }
  if ( !a12 )
  {
    v19 = BPool::PrepareToDirty(qword_10317B628, *v13, 1, 0);
    *(_WORD *)(v19 + 4) &= 0xEDFFu;
    *(_DWORD *)(v19 + 64) = 1;
    v21 = *v13;
    if ( *((_WORD *)*v13 + 22) == 2 )
      goto LABEL_29;
    v22 = *((_QWORD *)v21 + 18);
    if ( !v22 )
    {
      BUF::FixupPru(*v13);
      v22 = *(_QWORD *)(v141 + 144);
      v21 = *v13;
    }
    v23 = *(_QWORD *)(v22 + 1712);
    if ( (*(_BYTE *)(v23 + 60) & 1) != 0 && !*(_QWORD *)(v23 + 640) )
    {
      v142 = (RecoveryUnit *)*((_QWORD *)v21 + 18);
      if ( !v142 )
      {
        BUF::FixupPru(v21);
        v142 = *(RecoveryUnit **)(v143 + 144);
      }
      if ( !RecoveryUnit::IsBackupAllowedOnRbIoDb(v142) )
        goto LABEL_29;
    }
    v24 = *((_QWORD *)*v13 + 18);
    if ( !v24 )
    {
      BUF::FixupPru(*v13);
      v24 = *(_QWORD *)(v144 + 144);
    }
    if ( (*(_BYTE *)(v24 + 7376) & 0x20) != 0 )
    {
LABEL_29:
      v36 = *(_QWORD *)*v13;
      if ( (*(_WORD *)(v36 + 4) & 0x2000) == 0 )
        goto LABEL_30;
      if ( !*(_WORD *)(v36 + 36) )
        goto LABEL_169;
      v120 = *(_BYTE *)(v36 + 1);
      if ( v120 == 11 )
      {
        if ( *(_DWORD *)(v36 + 24) == 99 )
        {
LABEL_249:
          v485 = *(_DWORD *)(v36 + 32);
          v486 = *(_WORD *)(v36 + 36);
          if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v485, v20) )
          {
            PageHeader::GetIcxLsn(v36, &v481);
            goto LABEL_170;
          }
LABEL_169:
          v481 = *(_QWORD *)(v36 + 40);
          v482 = *(_WORD *)(v36 + 48);
LABEL_170:
          v121 = *((_QWORD *)*v13 + 18);
          if ( !v121 )
          {
            BUF::FixupPru(*v13);
            v121 = *(_QWORD *)(v150 + 144);
          }
          v122 = *(_QWORD *)(*(_QWORD *)(v121 + 1712) + 704LL);
          if ( (*(_WORD *)(v122 + 10) != 2 || (_DWORD)v481) && (unsigned int)v481 <= *(_DWORD *)v122 )
          {
            if ( (_DWORD)v481 != *(_DWORD *)v122
              || (v123 = *(_DWORD *)(v122 + 4), HIDWORD(v481) <= v123)
              && (HIDWORD(v481) != v123 || v482 <= *(_WORD *)(v122 + 8)) )
            {
              PageRef::RemoveOldVersionInfo((PageRef *)v13, v20, a3);
            }
          }
          goto LABEL_30;
        }
      }
      else if ( v120 == 8 )
      {
LABEL_251:
        if ( *(_DWORD *)(v36 + 24) != 99 )
          goto LABEL_169;
        goto LABEL_249;
      }
      if ( v120 != 9 )
        goto LABEL_169;
      goto LABEL_251;
    }
    v25 = *(_QWORD *)*v13;
    if ( !*(_WORD *)(v25 + 36) )
      goto LABEL_17;
    v26 = *(_BYTE *)(v25 + 1);
    if ( v26 == 11 )
    {
      if ( *(_DWORD *)(v25 + 24) == 99 )
      {
LABEL_238:
        v493 = *(_DWORD *)(v25 + 32);
        v494 = *(_WORD *)(v25 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v493, v20) )
        {
          PageHeader::GetIcxLsn(v25, &v479);
          goto LABEL_18;
        }
LABEL_17:
        v479 = *(_QWORD *)(v25 + 40);
        v480 = *(_WORD *)(v25 + 48);
LABEL_18:
        v27 = *v13;
        v28 = *((_QWORD *)*v13 + 18);
        if ( !v28 )
        {
          BUF::FixupPru(*v13);
          v28 = *((_QWORD *)v27 + 18);
        }
        FCB = FileMgr::GetFCB(*(_QWORD *)(v28 + 1696), *((unsigned __int16 *)v27 + 58), 0);
        v30 = *v13;
        v31 = *((_QWORD *)*v13 + 18);
        v32 = *v13;
        if ( !v31 )
        {
          BUF::FixupPru(*v13);
          v31 = *((_QWORD *)v30 + 18);
          v30 = *v13;
          v32 = *v13;
        }
        if ( !*(_DWORD *)(*(_QWORD *)(v31 + 1960) + 88LL) )
        {
          v33 = *(_DWORD *)(FCB + 304);
          if ( v33 <= (unsigned int)v479 )
          {
            if ( v33 != (_DWORD)v479 )
              goto LABEL_25;
            v108 = *(_DWORD *)(FCB + 308);
            if ( v108 <= HIDWORD(v479) && (v108 != HIDWORD(v479) || *(_WORD *)(FCB + 312) <= v480) )
              goto LABEL_25;
          }
        }
        v109 = *((_QWORD *)v30 + 18);
        if ( !v109 )
        {
          BUF::FixupPru(v30);
          v109 = *((_QWORD *)v30 + 18);
          v32 = *v13;
        }
        v110 = *(_QWORD *)(v109 + 1712);
        if ( (*(_BYTE *)(v110 + 60) & 1) == 0 || *(_QWORD *)(v110 + 640) )
        {
          v111 = (struct RecoveryUnit *)*((_QWORD *)v32 + 18);
          if ( !v111 )
          {
            BUF::FixupPru(v32);
            v111 = *(struct RecoveryUnit **)(v149 + 144);
            v32 = *v13;
          }
          PageRef::SetDiffMapChangeBit(v111, (const struct PageId *)(*(_QWORD *)v32 + 32LL));
        }
        else
        {
LABEL_25:
          v34 = *((_QWORD *)v32 + 18);
          if ( !v34 )
          {
            BUF::FixupPru(v32);
            v34 = *(_QWORD *)(v145 + 144);
            v32 = *v13;
          }
          v35 = *(_QWORD *)v32;
          if ( *(_DWORD *)(*(_QWORD *)(v34 + 1960) + 272LL) )
          {
            v146 = *(_DWORD *)(v35 + 32) & 0xFFFFFFF8;
            v20 = v146 / 0x7CD00;
            if ( v146 != 511232 * (_DWORD)v20 )
            {
              v147 = *((_QWORD *)v32 + 18);
              if ( !v147 )
              {
                BUF::FixupPru(v32);
                v147 = *(_QWORD *)(v148 + 144);
                v35 = *(_QWORD *)*v13;
              }
              BackupManager::MarkExtentInBackupBitmapList(
                *(BackupManager **)(v147 + 1960),
                (const struct PageId *)(v35 + 32));
            }
          }
        }
        v14 = v459;
        goto LABEL_29;
      }
    }
    else if ( v26 == 8 )
    {
LABEL_240:
      if ( *(_DWORD *)(v25 + 24) != 99 )
        goto LABEL_17;
      goto LABEL_238;
    }
    if ( v26 != 9 )
      goto LABEL_17;
    goto LABEL_240;
  }
LABEL_30:
  v37 = BPool::PrepareToDirty(qword_10317B628, *v13, 1, 0);
  *(_WORD *)(v37 + 4) &= 0xEDFFu;
  *(_DWORD *)(v37 + 64) = 1;
  v456 = *(Page **)*v13;
  v461 = *((_WORD *)v456 + 29);
  v496 = *((unsigned __int8 *)v456 + 2) >> 7;
  if ( v496 )
    v40 = *((_QWORD *)v14 + 1);
  else
    v40 = *(_QWORD *)v14;
  v41 = v40 + 2;
  v467 = 3;
  if ( !*(_WORD *)v40 )
  {
    if ( *(_DWORD *)(v40 + 4) )
    {
LABEL_34:
      v418 = *(_DWORD *)(v41 + 2);
      if ( v418 < 9 )
      {
        v183 = **(_BYTE **)(v41 + 6) & 0xE;
        if ( !v183 || v183 == 12 )
          v418 = 9;
      }
      v13 = v452;
      goto LABEL_36;
    }
    *(_WORD *)v41 = 0;
    v151 = *(unsigned int *)(v40 + 16);
    *(_DWORD *)(v40 + 20) = v151;
    v39 = *(_QWORD *)(v40 + 8);
    v152 = *(_BYTE *)v39;
    v153 = v151;
    if ( (*(_BYTE *)v39 & 0x10) != 0 )
    {
      LODWORD(v151) = (((unsigned int)*(unsigned __int16 *)(v151 + v39) + 7) >> 3) + 2 + v151;
      *(_DWORD *)(v41 + 18) = v151;
      v152 = *(_BYTE *)v39;
      v153 = v151;
    }
    if ( (v152 & 0x20) == 0 )
    {
      *(_DWORD *)(v41 + 2) = v151;
      *(_WORD *)(v41 + 26) = 0;
      *(_DWORD *)(v41 + 22) = v153;
LABEL_309:
      if ( (*(_BYTE *)v39 & 0x40) != 0 )
      {
        v173 = *(_DWORD *)(v41 + 2);
        *(_DWORD *)(v41 + 36) = v173;
        *(_DWORD *)(v41 + 2) = v173 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v41);
        v175 = HIDWORD(*(_QWORD *)VersioningInfo);
        v176 = HIWORD(*(_QWORD *)VersioningInfo);
        v39 = 0;
        if ( (((__int16)v176 ^ ((unsigned int)(__int16)v176 >> 1)) & 0x2000) != 0 )
        {
          v177 = v176 & 0xDFFF;
          if ( (v176 & 0x4000) != 0 )
            v177 = v176 | 0x2000;
          LOWORD(v176) = v177;
        }
        if ( (_WORD)v176 == 0xFFFC )
          v39 = (unsigned __int16)v175 >> 5;
        *(_DWORD *)(v41 + 2) += v39;
      }
      else
      {
        *(_DWORD *)(v41 + 36) = 0;
      }
      v38 = *(_QWORD *)(v41 + 28);
      v178 = *(_DWORD *)(v41 + 2);
      if ( v38 && v38 < *(_QWORD *)(v41 + 6) + (unsigned __int64)*(unsigned int *)(v41 + 2) )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v179 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v179 )
          {
            v180 = *(_QWORD *)(v179 + 96);
            if ( v180 )
            {
              if ( *(_BYTE *)(v180 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 18);
        v178 = *(_DWORD *)(v41 + 2);
      }
      if ( (unsigned int)(v178 - 1) > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v181 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v181 )
          {
            v182 = *(_QWORD *)(v181 + 96);
            if ( v182 )
            {
              if ( *(_BYTE *)(v182 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 5);
      }
      goto LABEL_34;
    }
    v154 = (unsigned __int16 *)(v39 + (unsigned int)v151);
    v155 = *v154;
    *(_WORD *)(v41 + 26) = *v154;
    if ( !v155 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v156 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v156 )
        {
          v157 = *(_QWORD *)(v156 + 96);
          if ( v157 )
          {
            if ( *(_BYTE *)(v157 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 3);
      v155 = *(_WORD *)(v41 + 26);
      v153 = *(_DWORD *)(v41 + 18);
    }
    v158 = v153 + 2 * (v155 + 1);
    *(_DWORD *)(v41 + 22) = v158;
    if ( v158 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v159 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v159 )
        {
          v160 = *(_QWORD *)(v159 + 96);
          if ( v160 )
          {
            if ( *(_BYTE *)(v160 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 4);
      v158 = *(_DWORD *)(v41 + 22);
    }
    v161 = *(unsigned __int16 *)(v41 + 26);
    v162 = v154[v161] & 0x7FFF;
    *(_DWORD *)(v41 + 2) = v162;
    if ( v158 > v162 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v163 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v163 )
        {
          v164 = *(_QWORD *)(v163 + 96);
          if ( v164 )
          {
            if ( *(_BYTE *)(v164 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 4);
      LOWORD(v161) = *(_WORD *)(v41 + 26);
    }
    while ( 1 )
    {
      v38 = (unsigned __int16)v161;
      if ( (v154[(unsigned __int16)v161] & 0x8000u) == 0 )
      {
LABEL_308:
        v39 = *(_QWORD *)(v41 + 6);
        goto LABEL_309;
      }
      v165 = *(_QWORD *)(v41 + 6) + *(unsigned int *)(v41 + 18);
      if ( (unsigned __int16)v161 == 1 )
      {
        v166 = *(_DWORD *)(v41 + 22);
        v167 = v166;
        v168 = *(_WORD *)(v165 + 2 * v38) & 0x7FFF;
      }
      else
      {
        v166 = *(_WORD *)(v165 + 2LL * (unsigned __int16)v161 - 2) & 0x7FFF;
        v167 = *(_DWORD *)(v41 + 22);
        v168 = *(_WORD *)(v165 + 2 * v38) & 0x7FFF;
        if ( v166 < v167 )
        {
LABEL_293:
          RaiseInconsistencyError(*(_QWORD *)(v41 + 6), 7);
          v167 = *(_DWORD *)(v41 + 22);
          goto LABEL_294;
        }
      }
      if ( v168 < v166 )
        goto LABEL_293;
LABEL_294:
      if ( v166 < v167 || v166 > *(_DWORD *)(v41 + 2) )
        goto LABEL_34;
      v169 = *(_WORD *)(v166 + *(_QWORD *)(v41 + 6));
      if ( v169 == 5 )
      {
        *(_WORD *)v41 |= 2u;
        --*(_WORD *)(v41 + 26);
        *(_WORD *)(v41 + 40) = v166;
        v171 = *(_QWORD *)(v41 + 6) + (unsigned __int16)v166;
        v172 = *(_WORD *)(v41 + 42) & 0xC7FF;
        if ( _bittest16((const signed __int16 *)(v171 + 2), 0xEu) )
          v172 |= *(_WORD *)(v171 + 2) & 0x3800;
        *(_WORD *)(v41 + 42) = v172;
        *(_WORD *)(v41 + 42) = v172 ^ (*(_WORD *)(v171 + 2) ^ v172) & 0x7FF;
        goto LABEL_308;
      }
      if ( v169 < 0x400u )
        goto LABEL_308;
      *(_WORD *)v41 |= 1u;
      v170 = *(_WORD *)(v41 + 26) - 1;
      *(_WORD *)(v41 + 26) = v170;
      if ( !v170 )
        goto LABEL_308;
      LOWORD(v161) = v170;
    }
  }
  v184 = *(_DWORD *)(v40 + 4);
  v418 = v184;
  if ( !v184 )
  {
    CDRecord::Resize((CDRecord *)(v40 + 2));
    v184 = *(_DWORD *)(v41 + 2);
    v418 = v184;
  }
  if ( v184 < 9 )
  {
    v185 = *(_BYTE **)(v41 + 6);
    if ( (*v185 & 0x1C) == 0 || (*v185 & 0x1C) == 0xC )
      v418 = 9;
  }
LABEL_36:
  v465 = *(_QWORD *)a3;
  v42 = *v13;
  v43 = 255;
  if ( (a7 & 0x400000) != 0 )
  {
    v112 = *((_QWORD *)v42 + 18);
    if ( !v112 )
    {
      BUF::FixupPru(*v13);
      v112 = *(_QWORD *)(v186 + 144);
      v42 = *v13;
      v43 = 255;
    }
    v113 = *(_QWORD *)(v112 + 1712);
    v114 = *(_WORD *)(v113 + 40);
    v39 = 2;
    if ( v114 == 2 )
    {
      v38 = *(unsigned __int16 *)(*(_QWORD *)v42 + 6LL);
      if ( (*(_DWORD *)(*(_QWORD *)v42 + 24LL) & 0xE0000000) == 0x80000000 && (unsigned __int16)v38 <= 0xFFu )
        goto LABEL_155;
      if ( *(_DWORD *)(*(_QWORD *)v42 + 24LL) == x_SYSALLOCPGAllocationUnitId )
      {
        v187 = 0;
        if ( (_WORD)v38 != 1 )
          v187 = *(_WORD *)(*(_QWORD *)v42 + 6LL);
        v188 = *(&x_SYSALLOCPGAllocationUnitId + 2);
        if ( *(&x_SYSALLOCPGAllocationUnitId + 2) == 1 )
          v188 = 0;
        if ( v187 == v188 )
        {
          v44 = 2;
          goto LABEL_39;
        }
      }
      v189 = v453;
      if ( !v453 )
        goto LABEL_155;
      if ( (*((_BYTE *)v453 + 536) & 1) == 0 )
      {
        v44 = 2;
        goto LABEL_39;
      }
    }
    else
    {
      v189 = v453;
    }
    if ( (*((_DWORD *)v42 + 25) & 0x80000) != 0 )
    {
      v44 = 2;
      goto LABEL_39;
    }
    if ( (*(_BYTE *)(v113 + 632) & 0xC) != 0 )
    {
      if ( (*((_DWORD *)*v452 + 25) & 0x80000) == 0 )
      {
        if ( !v189 || (*((_BYTE *)v189 + 536) & 1) == 0 )
          utassert_fail(1u, "(pXdes != NULL) && !pXdes->IsReadOnly ()", "pageref.cpp", 2392, 0);
        if ( (*(_BYTE *)(*(_QWORD *)*v452 + 4LL) & 0x20) != 0 && (*((_DWORD *)*v452 + 25) & 2) != 0 && v114 != 2 )
          utassert_fail(
            1u,
            "!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)",
            "pageref.cpp",
            2410,
            0);
        goto LABEL_38;
      }
LABEL_155:
      v44 = 2;
      goto LABEL_39;
    }
    if ( v189 && (*((_BYTE *)v189 + 536) & 1) != 0 )
    {
LABEL_388:
      if ( (*((_DWORD *)*v452 + 25) & 0x80000) != 0 && (unsigned __int8)(*(_BYTE *)(*(_QWORD *)*v452 + 1LL) - 3) > 1u )
        utassert_fail(
          1u,
          "IS_OFF (BUF_MINLOGGED, m_buf->bstat) || pageModifyType != PageModifyType_Contents || GetPagePtr ()->IsTextPage ()",
          "pageref.cpp",
          2488,
          0);
      goto LABEL_38;
    }
    CDStream::CDStream((CDStream *)v503);
    CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v529);
    CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v528);
    ProcessHeap = GetProcessHeap();
    v191 = (void **)HeapAlloc(ProcessHeap, 0, 0x6C0u);
    v478 = v191;
    if ( v191 )
      v192 = CTracePrintStream::CTracePrintStream((CTracePrintStream *)v191, 0);
    else
      v192 = 0;
    if ( v192 )
    {
      if ( CDStream::AddDevice((CDStream *)v503, v192) )
      {
        v203 = (byte_10317ACB9 & 2) != 0;
        v204 = (unsigned __int8)byte_10317AD42 >> 5;
        Context = UtilDbccGetContext();
        UtilDbccTraceOn(2505, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)Context + 10) + 72LL) + 16LL), 0, 0);
        v206 = UtilDbccGetContext();
        UtilDbccTraceOn(3605, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v206 + 10) + 72LL) + 16LL), 0, 0);
        CAutoStreamHeader::Init(
          (CAutoStreamHeader *)v529,
          (struct CDStream *)v503,
          "DBTABLE in PageRef::ComputeLogMode:");
        DBTABLE::Dump((DBTABLE *)v113, (struct CDStream *)v503);
        CAutoStreamHeader::Init((CAutoStreamHeader *)v528, (struct CDStream *)v503, "BUF in PageRef::ComputeLogMode:");
        BUF::Dump(*v452, (struct CDStream *)v503, 0);
        if ( (v204 & 1) == 0 )
        {
          v207 = UtilDbccGetContext();
          UtilDbccTraceOff(3605, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v207 + 10) + 72LL) + 16LL), 0, 0);
        }
        if ( !v203 )
        {
          v208 = UtilDbccGetContext();
          UtilDbccTraceOff(2505, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v208 + 10) + 72LL) + 16LL), 0, 0);
        }
        goto LABEL_384;
      }
      (**(void (__fastcall ***)(struct CDumpStream *, __int64))v192)(v192, 1);
    }
    ErrorReportingManager = GetErrorReportingManager();
    LOBYTE(v194) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)ErrorReportingManager + 168LL))(
      ErrorReportingManager,
      L"\nAllocation error of trace stream",
      33,
      v194,
      -1);
LABEL_384:
    if ( !v453 || (*((_BYTE *)v453 + 536) & 1) == 0 )
      utassert_fail(1u, "(pXdes != NULL) && !pXdes->IsReadOnly ()", "pageref.cpp", 2478, 0);
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v528);
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v529);
    CDStream::~CDStream((CDStream *)v503);
    goto LABEL_388;
  }
  if ( (*((_DWORD *)v42 + 25) & 0x80000) != 0 && (unsigned __int8)(*(_BYTE *)(*(_QWORD *)*v13 + 1LL) - 3) > 1u )
    utassert_fail(
      1u,
      "IS_OFF (BUF_MINLOGGED, m_buf->bstat) || pageModifyType != PageModifyType_Contents || GetPagePtr ()->IsTextPage ()",
      "pageref.cpp",
      2525,
      0);
LABEL_38:
  v44 = 0;
LABEL_39:
  v419 = v44;
  v412 = 0;
  v45 = v453;
  if ( v453
    && (*(unsigned __int8 (__fastcall **)(XDES *, unsigned __int64, __int64, __int64))(*(_QWORD *)v453 + 40LL))(
         v453,
         v38,
         v39,
         v43) )
  {
    v44 = 3;
    v419 = 3;
    v412 = 1;
  }
  v46 = v456;
  v47 = *((_BYTE *)v456 + 1);
  v48 = 4095;
  v49 = 16;
  if ( v47 == 3 )
    goto LABEL_201;
  if ( v47 == 1 && (a7 & 1) == 0 )
  {
    if ( (*((_DWORD *)v456 + 6) & 0xE0000000) == 0x80000000 )
    {
      v129 = *((_WORD *)v456 + 3) <= 0xFFu;
      v454 = 1;
      if ( v129 )
      {
LABEL_202:
        if ( !v44 )
        {
          if ( !(unsigned int)XDES::IsActive(v453) )
            (*(void (__fastcall **)(XDES *))(*(_QWORD *)v453 + 624LL))(v453);
          v464 = (XDES *)((char *)v453 + 40);
          XdesMgr::GetOldestInterestingXdesId((struct RecoveryUnit *)((char *)v477 + 6600), (struct XdesId *)&v473);
          v16 = (struct XdesId *)&v473;
          v48 = 4095;
          v49 = 16;
        }
        v130 = 0;
        v131 = *((unsigned __int16 *)v456 + 11) - 1LL;
        if ( v131 >= 0 )
        {
          v48 = (__int64)v456 + 2 * (4095 - v131);
          do
          {
            if ( *(_WORD *)v48 )
              break;
            v130 = (unsigned int)(v130 + 1);
            v48 += 2;
            --v131;
          }
          while ( v131 >= 0 );
        }
        v463 = *((unsigned __int16 *)v456 + 14) + 2 * v130;
        v132 = 0;
        v415 = 0;
        if ( v455 == 1 )
        {
          if ( (v417 & 0x80000) == 0 )
            v132 = 16;
          v415 = v132;
        }
        if ( v453
          && (*(unsigned __int8 (__fastcall **)(XDES *, __int64, __int64, __int64))(*(_QWORD *)v453 + 88LL))(
               v453,
               v48,
               v130,
               16) )
        {
          v132 |= 0x80u;
          v415 = v132;
        }
        if ( !(*(unsigned int (__fastcall **)(XDES *, __int64, __int64, __int64))(*(_QWORD *)v453 + 616LL))(
                v453,
                v48,
                v130,
                v49) )
        {
LABEL_212:
          v50 = v417;
          if ( (v417 & 0x10) != 0 )
            v415 = v132 | 8;
          goto LABEL_46;
        }
        v415 = v132 | 2;
        if ( (v417 & 0x8000) == 0 )
        {
          v240 = (unsigned __int16)(~((1 << (*((_WORD *)v456 + 2) & 2)) - 1)
                                  & ((1 << (*((_WORD *)v456 + 2) & 2)) - 1 + v418));
          v241 = 0;
          v242 = *((unsigned __int16 *)v456 + 11);
          if ( v413 < (int)v242 )
          {
            v244 = v242 - 1;
            if ( v244 > v413 )
            {
              v245 = (_WORD *)((char *)v456 + 2 * (4095 - v244));
              do
              {
                if ( *v245 )
                  break;
                ++v241;
                --v244;
                ++v245;
              }
              while ( v244 > v413 );
            }
          }
          else
          {
            v240 += 2 * (v413 - v242) + 2;
          }
          v243 = *((unsigned __int16 *)v456 + 14);
          if ( v243 + 2 * (unsigned __int64)v241 < v240 )
          {
            utassert_fail(1u, "m_freeCnt + emptySlots * sizeof(PageSlot) >= spaceNeeded", "page.cpp", 5731, 0);
            LOWORD(v243) = *((_WORD *)v456 + 14);
          }
          PFSFreeSpaceAfterModify = (unsigned __int16)v243 + 2 * v241 - v240;
          goto LABEL_516;
        }
        v195 = 0;
        v196 = *((unsigned __int16 *)v456 + 11) - 1LL;
        if ( v196 >= 0 )
        {
          v197 = (_WORD *)((char *)v456 + 2 * (4095 - v196));
          do
          {
            if ( *v197 )
              break;
            ++v195;
            ++v197;
            --v196;
          }
          while ( v196 >= 0 );
        }
        v198 = *((unsigned __int16 *)v456 + 14) + 2 * v195;
        v199 = 0;
        v444 = 0;
        v449 = 0;
        *(_QWORD *)((char *)&v450 + 2) = 0;
        v446 = 0;
        v200 = (char *)v456 + *((unsigned __int16 *)v456 + 4095LL - v413);
        v201 = *((unsigned __int16 *)v456 + 7);
        v236 = (*v200 & 1) == 0;
        v445 = v200;
        if ( v236 )
        {
          v442 = 0;
          LODWORD(v450) = 0;
          switch ( *v200 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v201 = *((unsigned __int16 *)v200 + 1);
              if ( v201 - 1 > 0x1F9D )
              {
                RaiseInconsistencyError(v200, 6);
                goto LABEL_469;
              }
              break;
            case 1:
            case 3:
            case 5:
            case 7:
            case 9:
            case 0xB:
            case 0xD:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                294,
                "Invalid switch value");
LABEL_469:
              v199 = v444;
              break;
            case 4:
              v201 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v201 = 1;
              break;
          }
          LODWORD(v446) = v201;
          v449 = (char *)v456 + 0x2000;
        }
        else
        {
          v442 = 1;
          v202 = *v200;
          switch ( byte_1005F1630[*v200 & 0x1C] )
          {
            case 0:
              if ( v200[1] < 0 )
              {
                v209 = HIBYTE(*(_WORD *)(v200 + 1)) | ((*(_WORD *)(v200 + 1) & 0x7F) << 8);
                v443 = v209;
                v210 = 3;
                v211 = 3;
              }
              else
              {
                v209 = (unsigned __int8)v200[1];
                v443 = v209;
                v210 = 2;
                v211 = 2;
              }
              LOWORD(v447) = v210;
              v448 = v211 + (((unsigned int)v209 + 1) >> 1);
              if ( v209 > 0x1Eu )
                HIWORD(v447) = (v209 - 1) / 30;
              else
                HIWORD(v447) = 0;
              v451 = 0;
              *(_QWORD *)((char *)&v450 + 2) = (char *)v456 + 0x2000;
              v201 = 0;
              break;
            case 1:
              if ( (v202 & 0x1C) == 4 && (v202 & 2) != 0 )
              {
                v447 = 0;
                v443 = 0;
                v448 = 0;
                LOWORD(v450) = 0;
                v199 = 15;
                v444 = 15;
                v451 = 1;
                *(_QWORD *)((char *)&v450 + 2) = (char *)v456 + 0x2000;
                v201 = 0;
              }
              else
              {
                v447 = 0;
                v443 = 0;
                v448 = 0;
                LOWORD(v450) = 0;
                v199 = 1;
                v444 = 1;
                v451 = 0;
                *(_QWORD *)((char *)&v450 + 2) = (char *)v456 + 0x2000;
                v201 = 0;
              }
              break;
            case 2:
              v447 = 0;
              v443 = 0;
              v448 = 0;
              LOWORD(v450) = 0;
              v199 = 9;
              v444 = 9;
              v451 = 0;
              *(_QWORD *)((char *)&v450 + 2) = (char *)v456 + 0x2000;
              v201 = 0;
              break;
            case 3:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                207,
                "Invalid switch value");
              v199 = v444;
              *(_QWORD *)((char *)&v450 + 2) = (char *)v456 + 0x2000;
              v201 = 0;
              break;
          }
        }
        if ( v442 )
        {
          if ( !v199 )
          {
            CDRecord::Resize((CDRecord *)&v443);
            v199 = v444;
          }
          if ( v199 >= 9 )
            goto LABEL_515;
          if ( (*v445 & 0x1C) == 0 )
            goto LABEL_514;
          v236 = (*v445 & 0x1C) == 12;
        }
        else
        {
          if ( !v199 )
          {
            v443 = 0;
            HIDWORD(v446) = v201;
            v199 = v201;
            if ( (*v445 & 0x10) != 0 )
            {
              v199 = (((unsigned int)*(unsigned __int16 *)&v445[v201] + 7) >> 3) + v201 + 2;
              HIDWORD(v446) = v199;
            }
            if ( (*v445 & 0x20) != 0 )
            {
              v212 = (unsigned __int16 *)&v445[v199];
              v213 = *v212;
              v448 = v213;
              if ( !v213 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v214 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v214 )
                  {
                    v215 = *(_QWORD *)(v214 + 96);
                    if ( v215 )
                    {
                      if ( *(_BYTE *)(v215 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                        else
                          ex_raise(34, 68, 21, 1003);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v445, 3);
                v213 = v448;
              }
              v216 = HIDWORD(v446) + 2 + 2 * v213;
              v447 = v216;
              if ( v216 > 0x1F9E )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v217 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v217 )
                  {
                    v218 = *(_QWORD *)(v217 + 96);
                    if ( v218 )
                    {
                      if ( *(_BYTE *)(v218 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v445, 4);
                v213 = v448;
                v216 = v447;
              }
              v199 = v212[v213] & 0x7FFF;
              v444 = v199;
              if ( v216 > v199 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v219 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v219 )
                  {
                    v220 = *(_QWORD *)(v219 + 96);
                    if ( v220 )
                    {
                      if ( *(_BYTE *)(v220 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v445, 4);
                v213 = v448;
                v216 = v447;
                v199 = v444;
              }
              while ( (v212[v213] & 0x8000u) != 0 )
              {
                v221 = &v445[HIDWORD(v446)];
                if ( v213 == 1 )
                  v222 = v216;
                else
                  v222 = *(_WORD *)&v221[2 * v213 - 2] & 0x7FFF;
                if ( v222 < v216 || (*(_WORD *)&v221[2 * v213] & 0x7FFFu) < v222 )
                {
                  RaiseInconsistencyError(v445, 7);
                  v213 = v448;
                  v216 = v447;
                  v199 = v444;
                }
                if ( v222 < v216 || v222 > v199 )
                  goto LABEL_510;
                v223 = *(_WORD *)&v445[v222];
                if ( v223 == 5 )
                {
                  v443 |= 2u;
                  v448 = v213 - 1;
                  WORD2(v450) = v222;
                  v224 = *(_WORD *)&v445[(unsigned __int16)v222 + 2];
                  v225 = WORD3(v450) & 0xC7FF;
                  if ( (v224 & 0x4000) != 0 )
                    v225 = WORD3(v450) ^ (v224 ^ WORD3(v450)) & 0x3800;
                  WORD3(v450) = v225 ^ (v224 ^ v225) & 0x7FF;
                  break;
                }
                if ( v223 >= 0x400u )
                {
                  v443 |= 1u;
                  v236 = v213-- == 1;
                  v448 = v213;
                  if ( !v236 )
                    continue;
                }
                break;
              }
            }
            else
            {
              v444 = v199;
              v448 = 0;
              v447 = v199;
            }
            if ( (*v445 & 0x40) != 0 )
            {
              LODWORD(v450) = v199;
              v444 = v199 + 14;
              v226 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v443);
              v227 = HIDWORD(*(_QWORD *)v226);
              v228 = HIWORD(*(_QWORD *)v226);
              v229 = 0;
              if ( (((__int16)v228 ^ ((unsigned int)(__int16)v228 >> 1)) & 0x2000) != 0 )
              {
                v230 = v228 & 0xDFFF;
                if ( (v228 & 0x4000) != 0 )
                  v230 = v228 | 0x2000;
                LOWORD(v228) = v230;
              }
              if ( (_WORD)v228 == 0xFFFC )
                v229 = (unsigned __int16)v227 >> 5;
              v199 = v229 + v444;
              v444 += v229;
            }
            else
            {
              LODWORD(v450) = 0;
            }
            if ( v449 && v449 < &v445[v199] )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v231 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v231 )
                {
                  v232 = *(_QWORD *)(v231 + 96);
                  if ( v232 )
                  {
                    if ( *(_BYTE *)(v232 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                      else
                        ex_raise(34, 68, 21, 1018);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v445, 18);
              v199 = v444;
            }
            if ( v199 - 1 > 0x3F3B )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v233 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v233 )
                {
                  v234 = *(_QWORD *)(v233 + 96);
                  if ( v234 )
                  {
                    if ( *(_BYTE *)(v234 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                      else
                        ex_raise(34, 68, 21, 1005);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v445, 5);
              v199 = v444;
            }
          }
LABEL_510:
          if ( v199 >= 9 )
            goto LABEL_515;
          v235 = *v445 & 0xE;
          if ( !v235 )
            goto LABEL_514;
          v236 = v235 == 12;
        }
        if ( !v236 )
        {
LABEL_515:
          LODWORD(v409) = v198;
          v46 = v456;
          PFSFreeSpaceAfterModify = Page::GetPFSFreeSpaceAfterModify(v456, v199, v418, 0, v413, (_DWORD)v409);
LABEL_516:
          v45 = v453;
          if ( (*((_DWORD *)v453 + 134) & 5) == 1 && (*((_DWORD *)v453 + 182) & 1) != 0 )
            goto LABEL_527;
          v238 = 0;
          while ( v463 < dword_102830E28[v238] )
          {
            if ( ++v238 >= 4u )
            {
              v238 = 4;
              break;
            }
          }
          v239 = 0;
          while ( PFSFreeSpaceAfterModify < dword_102830E28[v239] )
          {
            if ( ++v239 >= 4u )
            {
              v239 = 4;
              break;
            }
          }
          if ( v238 != v239 )
          {
LABEL_527:
            SetFreeSpaceState(
              *((struct RecoveryUnit **)v453 + 6),
              (const struct AllocationCachesId *)&v465,
              (const struct PageId *)(*(_QWORD *)*v452 + 32LL),
              PFSFreeSpaceAfterModify,
              v453);
            v132 = v415;
          }
          else
          {
            v132 = v415;
          }
          goto LABEL_212;
        }
LABEL_514:
        v199 = 9;
        goto LABEL_515;
      }
    }
LABEL_201:
    v454 = 0;
    goto LABEL_202;
  }
  v454 = 2;
  v463 = v460;
  v50 = v417;
LABEL_46:
  if ( v458 == 1 )
  {
    if ( (v50 & 2) != 0 )
    {
      v54 = Page::CheckSpaceForInsertOverGhost(v46, v413, v418);
    }
    else
    {
      v51 = v464;
      if ( v464 )
      {
        v133 = 0;
        if ( v50 < 0 )
        {
          v424 = 0;
          v429 = 0;
          *(_QWORD *)((char *)&v430 + 2) = 0;
          v426 = 0;
          v246 = (char *)v46 + *((unsigned __int16 *)v46 + 4095LL - v413);
          v247 = *((unsigned __int16 *)v46 + 7);
          v236 = (*v246 & 1) == 0;
          v425 = v246;
          if ( v236 )
          {
            v422 = 0;
            LODWORD(v430) = 0;
            switch ( *v246 & 0xE )
            {
              case 0:
              case 2:
              case 8:
              case 0xC:
                v247 = *((unsigned __int16 *)v246 + 1);
                if ( v247 - 1 > 0x1F9D )
                {
                  RaiseInconsistencyError(v246, 6);
                  goto LABEL_614;
                }
                break;
              case 1:
              case 3:
              case 5:
              case 7:
              case 9:
              case 0xB:
              case 0xD:
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                  294,
                  "Invalid switch value");
LABEL_614:
                v133 = v424;
                break;
              case 4:
                v247 = 9;
                break;
              case 6:
              case 0xA:
                break;
              case 0xE:
                v247 = 1;
                break;
            }
            LODWORD(v426) = v247;
            v429 = (char *)v46 + 0x2000;
          }
          else
          {
            v422 = 1;
            v248 = *v246;
            switch ( *v246 & 0x1C )
            {
              case 0:
              case 0xC:
              case 0x10:
              case 0x14:
              case 0x18:
              case 0x1C:
                if ( v246[1] < 0 )
                {
                  v249 = HIBYTE(*(_WORD *)(v246 + 1)) | ((*(_WORD *)(v246 + 1) & 0x7F) << 8);
                  v423 = v249;
                  LOWORD(v427) = 3;
                  v250 = 3;
                }
                else
                {
                  v249 = (unsigned __int8)v246[1];
                  v423 = v249;
                  LOWORD(v427) = 2;
                  v250 = 2;
                }
                v428 = v250 + (((unsigned int)v249 + 1) >> 1);
                if ( v249 > 0x1Eu )
                  HIWORD(v427) = (v249 - 1) / 30;
                else
                  HIWORD(v427) = 0;
                v431 = 0;
                *(_QWORD *)((char *)&v430 + 2) = (char *)v46 + 0x2000;
                v247 = 0;
                break;
              case 1:
              case 2:
              case 3:
              case 5:
              case 6:
              case 7:
              case 9:
              case 0xA:
              case 0xB:
              case 0xD:
              case 0xE:
              case 0xF:
              case 0x11:
              case 0x12:
              case 0x13:
              case 0x15:
              case 0x16:
              case 0x17:
              case 0x19:
              case 0x1A:
              case 0x1B:
                utassert_fail(
                  1u,
                  "FALSE",
                  "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                  207,
                  "Invalid switch value");
                v133 = v424;
                *(_QWORD *)((char *)&v430 + 2) = (char *)v46 + 0x2000;
                v247 = 0;
                break;
              case 4:
                if ( (v248 & 0x1C) == 4 && (v248 & 2) != 0 )
                {
                  v427 = 0;
                  v423 = 0;
                  v428 = 0;
                  LOWORD(v430) = 0;
                  v133 = 15;
                  v424 = 15;
                  v431 = 1;
                  *(_QWORD *)((char *)&v430 + 2) = (char *)v46 + 0x2000;
                  v247 = 0;
                }
                else
                {
                  v427 = 0;
                  v423 = 0;
                  v428 = 0;
                  LOWORD(v430) = 0;
                  v133 = 1;
                  v424 = 1;
                  v431 = 0;
                  *(_QWORD *)((char *)&v430 + 2) = (char *)v46 + 0x2000;
                  v247 = 0;
                }
                break;
              case 8:
                v427 = 0;
                v423 = 0;
                v428 = 0;
                LOWORD(v430) = 0;
                v133 = 9;
                v424 = 9;
                v431 = 0;
                *(_QWORD *)((char *)&v430 + 2) = (char *)v46 + 0x2000;
                v247 = 0;
                break;
            }
          }
          if ( v422 )
          {
            if ( !v133 )
            {
              CDRecord::Resize((CDRecord *)&v423);
              v133 = v424;
            }
            if ( v133 < 9 && ((*v425 & 0x1C) == 0 || (*v425 & 0x1C) == 0xC) )
              v133 = 9;
          }
          else
          {
            if ( !v133 )
            {
              v423 = 0;
              HIDWORD(v426) = v247;
              v133 = v247;
              if ( (*v425 & 0x10) != 0 )
              {
                v133 = (((unsigned int)*(unsigned __int16 *)&v425[v247] + 7) >> 3) + v247 + 2;
                HIDWORD(v426) = v133;
              }
              if ( (*v425 & 0x20) != 0 )
              {
                v251 = (unsigned __int16 *)&v425[v133];
                v252 = *v251;
                v428 = v252;
                if ( !v252 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v253 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v253 )
                    {
                      v254 = *(_QWORD *)(v253 + 96);
                      if ( v254 )
                      {
                        if ( *(_BYTE *)(v254 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v425, 3);
                  v252 = v428;
                }
                v255 = HIDWORD(v426) + 2 + 2 * v252;
                v427 = v255;
                if ( v255 > 0x1F9E )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v256 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v256 )
                    {
                      v257 = *(_QWORD *)(v256 + 96);
                      if ( v257 )
                      {
                        if ( *(_BYTE *)(v257 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v425, 4);
                  v252 = v428;
                  v255 = v427;
                }
                v133 = v251[v252] & 0x7FFF;
                v424 = v133;
                if ( v255 > v133 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v258 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v258 )
                    {
                      v259 = *(_QWORD *)(v258 + 96);
                      if ( v259 )
                      {
                        if ( *(_BYTE *)(v259 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v425, 4);
                  v252 = v428;
                  v255 = v427;
                  v133 = v424;
                }
                while ( (v251[v252] & 0x8000u) != 0 )
                {
                  v260 = &v425[HIDWORD(v426)];
                  if ( v252 == 1 )
                    v261 = v255;
                  else
                    v261 = *(_WORD *)&v260[2 * v252 - 2] & 0x7FFF;
                  if ( v261 < v255 || (*(_WORD *)&v260[2 * v252] & 0x7FFFu) < v261 )
                  {
                    RaiseInconsistencyError(v425, 7);
                    v252 = v428;
                    v255 = v427;
                    v133 = v424;
                  }
                  if ( v261 < v255 || v261 > v133 )
                    goto LABEL_655;
                  v262 = *(_WORD *)&v425[v261];
                  if ( v262 == 5 )
                  {
                    v423 |= 2u;
                    v428 = v252 - 1;
                    WORD2(v430) = v261;
                    v263 = *(_WORD *)&v425[(unsigned __int16)v261 + 2];
                    v264 = WORD3(v430) & 0xC7FF;
                    if ( (v263 & 0x4000) != 0 )
                      v264 = WORD3(v430) ^ (v263 ^ WORD3(v430)) & 0x3800;
                    WORD3(v430) = v264 ^ (v263 ^ v264) & 0x7FF;
                    break;
                  }
                  if ( v262 >= 0x400u )
                  {
                    v423 |= 1u;
                    v236 = v252-- == 1;
                    v428 = v252;
                    if ( !v236 )
                      continue;
                  }
                  break;
                }
              }
              else
              {
                v424 = v133;
                v428 = 0;
                v427 = v133;
              }
              if ( (*v425 & 0x40) != 0 )
              {
                LODWORD(v430) = v133;
                v424 = v133 + 14;
                v265 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v423);
                v266 = HIDWORD(*(_QWORD *)v265);
                v267 = HIWORD(*(_QWORD *)v265);
                v268 = 0;
                if ( (((__int16)v267 ^ ((unsigned int)(__int16)v267 >> 1)) & 0x2000) != 0 )
                {
                  v269 = v267 & 0xDFFF;
                  if ( (v267 & 0x4000) != 0 )
                    v269 = v267 | 0x2000;
                  LOWORD(v267) = v269;
                }
                if ( (_WORD)v267 == 0xFFFC )
                  v268 = (unsigned __int16)v266 >> 5;
                v133 = v268 + v424;
                v424 += v268;
              }
              else
              {
                LODWORD(v430) = 0;
              }
              if ( v429 && v429 < &v425[v133] )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v270 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v270 )
                  {
                    v271 = *(_QWORD *)(v270 + 96);
                    if ( v271 )
                    {
                      if ( *(_BYTE *)(v271 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v425, 18);
                v133 = v424;
              }
              if ( v133 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v272 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v272 )
                  {
                    v273 = *(_QWORD *)(v272 + 96);
                    if ( v273 )
                    {
                      if ( *(_BYTE *)(v273 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v425, 5);
                v133 = v424;
              }
            }
LABEL_655:
            if ( v133 < 9 )
            {
              v274 = *v425 & 0xE;
              if ( !v274 || v274 == 12 )
                v133 = 9;
            }
            v51 = v464;
          }
        }
        v409 = v16;
        v53 = v415;
        v52 = v418;
        Page::ComputeAcquireOrRelease(v46, v133, v418, v415, v51, v409, v420);
        v50 = v417;
      }
      else
      {
        v52 = v418;
        v53 = v415;
      }
      if ( v50 < 0 )
      {
        v275 = 0;
        v434 = 0;
        v439 = 0;
        *(_QWORD *)((char *)&v440 + 2) = 0;
        v436 = 0;
        v276 = (char *)v46 + *((unsigned __int16 *)v46 + 4095LL - v413);
        v277 = *((unsigned __int16 *)v46 + 7);
        v236 = (*v276 & 1) == 0;
        v435 = v276;
        if ( v236 )
        {
          v432 = 0;
          LODWORD(v440) = 0;
          switch ( *v276 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v277 = *((unsigned __int16 *)v276 + 1);
              if ( v277 - 1 > 0x1F9D )
              {
                RaiseInconsistencyError(v276, 6);
                goto LABEL_736;
              }
              break;
            case 1:
            case 3:
            case 5:
            case 7:
            case 9:
            case 0xB:
            case 0xD:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                294,
                "Invalid switch value");
LABEL_736:
              v275 = v434;
              break;
            case 4:
              v277 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v277 = 1;
              break;
          }
          LODWORD(v436) = v277;
          v439 = (char *)v46 + 0x2000;
        }
        else
        {
          v432 = 1;
          v278 = *v276;
          switch ( *v276 & 0x1C )
          {
            case 0:
            case 0xC:
            case 0x10:
            case 0x14:
            case 0x18:
            case 0x1C:
              if ( v276[1] < 0 )
              {
                v279 = HIBYTE(*(_WORD *)(v276 + 1)) | ((*(_WORD *)(v276 + 1) & 0x7F) << 8);
                v433 = v279;
                v280 = 3;
                v281 = 3;
              }
              else
              {
                v279 = (unsigned __int8)v276[1];
                v433 = v279;
                v280 = 2;
                v281 = 2;
              }
              LOWORD(v437) = v280;
              v438 = v281 + (((unsigned int)v279 + 1) >> 1);
              if ( v279 > 0x1Eu )
                HIWORD(v437) = (v279 - 1) / 30;
              else
                HIWORD(v437) = 0;
              v441 = 0;
              *(_QWORD *)((char *)&v440 + 2) = (char *)v46 + 0x2000;
              v277 = 0;
              break;
            case 1:
            case 2:
            case 3:
            case 5:
            case 6:
            case 7:
            case 9:
            case 0xA:
            case 0xB:
            case 0xD:
            case 0xE:
            case 0xF:
            case 0x11:
            case 0x12:
            case 0x13:
            case 0x15:
            case 0x16:
            case 0x17:
            case 0x19:
            case 0x1A:
            case 0x1B:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                207,
                "Invalid switch value");
              v275 = v434;
              *(_QWORD *)((char *)&v440 + 2) = (char *)v46 + 0x2000;
              v277 = 0;
              break;
            case 4:
              if ( (v278 & 0x1C) == 4 && (v278 & 2) != 0 )
              {
                v437 = 0;
                v433 = 0;
                v438 = 0;
                LOWORD(v440) = 0;
                v275 = 15;
                v434 = 15;
                v441 = 1;
                *(_QWORD *)((char *)&v440 + 2) = (char *)v46 + 0x2000;
                v277 = 0;
              }
              else
              {
                v437 = 0;
                v433 = 0;
                v438 = 0;
                LOWORD(v440) = 0;
                v275 = 1;
                v434 = 1;
                v441 = 0;
                *(_QWORD *)((char *)&v440 + 2) = (char *)v46 + 0x2000;
                v277 = 0;
              }
              break;
            case 8:
              v437 = 0;
              v433 = 0;
              v438 = 0;
              LOWORD(v440) = 0;
              v275 = 9;
              v434 = 9;
              v441 = 0;
              *(_QWORD *)((char *)&v440 + 2) = (char *)v46 + 0x2000;
              v277 = 0;
              break;
          }
        }
        if ( v432 )
        {
          if ( !v275 )
          {
            CDRecord::Resize((CDRecord *)&v433);
            v275 = v434;
          }
          if ( v275 < 9 && ((*v435 & 0x1C) == 0 || (*v435 & 0x1C) == 0xC) )
            v275 = 9;
        }
        else
        {
          if ( !v275 )
          {
            v433 = 0;
            HIDWORD(v436) = v277;
            v275 = v277;
            if ( (*v435 & 0x10) != 0 )
            {
              v275 = (((unsigned int)*(unsigned __int16 *)&v435[v277] + 7) >> 3) + v277 + 2;
              HIDWORD(v436) = v275;
            }
            if ( (*v435 & 0x20) != 0 )
            {
              v282 = (unsigned __int16 *)&v435[v275];
              v283 = *v282;
              v438 = v283;
              if ( !v283 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v284 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v284 )
                  {
                    v285 = *(_QWORD *)(v284 + 96);
                    if ( v285 )
                    {
                      if ( *(_BYTE *)(v285 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                        else
                          ex_raise(34, 68, 21, 1003);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v435, 3);
                v283 = v438;
              }
              v286 = HIDWORD(v436) + 2 + 2 * v283;
              v437 = v286;
              if ( v286 > 0x1F9E )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v287 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v287 )
                  {
                    v288 = *(_QWORD *)(v287 + 96);
                    if ( v288 )
                    {
                      if ( *(_BYTE *)(v288 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v435, 4);
                v283 = v438;
                v286 = v437;
              }
              v275 = v282[v283] & 0x7FFF;
              v434 = v275;
              if ( v286 > v275 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v289 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v289 )
                  {
                    v290 = *(_QWORD *)(v289 + 96);
                    if ( v290 )
                    {
                      if ( *(_BYTE *)(v290 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v435, 4);
                v283 = v438;
                v286 = v437;
                v275 = v434;
              }
              while ( (v282[v283] & 0x8000u) != 0 )
              {
                v291 = &v435[HIDWORD(v436)];
                if ( v283 == 1 )
                  v292 = v286;
                else
                  v292 = *(_WORD *)&v291[2 * v283 - 2] & 0x7FFF;
                if ( v292 < v286 || (*(_WORD *)&v291[2 * v283] & 0x7FFFu) < v292 )
                {
                  RaiseInconsistencyError(v435, 7);
                  v283 = v438;
                  v286 = v437;
                  v275 = v434;
                }
                if ( v292 < v286 || v292 > v275 )
                  goto LABEL_777;
                v293 = *(_WORD *)&v435[v292];
                if ( v293 == 5 )
                {
                  v433 |= 2u;
                  v438 = v283 - 1;
                  WORD2(v440) = v292;
                  v294 = *(_WORD *)&v435[(unsigned __int16)v292 + 2];
                  v295 = WORD3(v440) & 0xC7FF;
                  if ( (v294 & 0x4000) != 0 )
                    v295 = WORD3(v440) ^ (v294 ^ WORD3(v440)) & 0x3800;
                  WORD3(v440) = v295 ^ (v294 ^ v295) & 0x7FF;
                  break;
                }
                if ( v293 >= 0x400u )
                {
                  v433 |= 1u;
                  v236 = v283-- == 1;
                  v438 = v283;
                  if ( !v236 )
                    continue;
                }
                break;
              }
            }
            else
            {
              v434 = v275;
              v438 = 0;
              v437 = v275;
            }
            if ( (*v435 & 0x40) != 0 )
            {
              LODWORD(v440) = v275;
              v434 = v275 + 14;
              v296 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v433);
              v297 = HIDWORD(*(_QWORD *)v296);
              v298 = HIWORD(*(_QWORD *)v296);
              v299 = 0;
              if ( (((__int16)v298 ^ ((unsigned int)(__int16)v298 >> 1)) & 0x2000) != 0 )
              {
                v300 = v298 & 0xDFFF;
                if ( (v298 & 0x4000) != 0 )
                  v300 = v298 | 0x2000;
                LOWORD(v298) = v300;
              }
              if ( (_WORD)v298 == 0xFFFC )
                v299 = (unsigned __int16)v297 >> 5;
              v275 = v299 + v434;
              v434 += v299;
            }
            else
            {
              LODWORD(v440) = 0;
            }
            if ( v439 && v439 < &v435[v275] )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v301 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v301 )
                {
                  v302 = *(_QWORD *)(v301 + 96);
                  if ( v302 )
                  {
                    if ( *(_BYTE *)(v302 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                      else
                        ex_raise(34, 68, 21, 1018);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v435, 18);
              v275 = v434;
            }
            if ( v275 - 1 > 0x3F3B )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v303 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v303 )
                {
                  v304 = *(_QWORD *)(v303 + 96);
                  if ( v304 )
                  {
                    if ( *(_BYTE *)(v304 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                      else
                        ex_raise(34, 68, 21, 1005);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v435, 5);
              v275 = v434;
            }
          }
LABEL_777:
          if ( v275 < 9 )
          {
            v305 = *v435 & 0xE;
            if ( !v305 || v305 == 12 )
              v275 = 9;
          }
          v51 = v464;
        }
        v54 = Page::CheckForModifySpace(v46, (unsigned int)v413, v275, v52, 0, &v462, v421, v415, v51);
      }
      else
      {
        v54 = Page::CheckInsertSpace(v46, v413, v52, v53, v51, &v462, v421);
      }
    }
    if ( v54 )
      utassert_fail(1u, "0 == pageFull", "pageref.cpp", 3546, 0);
  }
  else
  {
    if ( *((_WORD *)v46 + 11) && !(unsigned int)XDES::InRollback(v45) )
      utassert_fail(1u, "pPage->IsEmpty () || pXdes->InRollback ()", "pageref.cpp", 3556, 0);
    Page::CompactPage(v46, -1);
  }
  v55 = v420[0] | 0x80;
  if ( (v417 & 0x100) == 0 )
    v55 = v420[0];
  v460 = v417 & 0x200;
  v56 = v55 | 0x200;
  if ( (v417 & 0x200) == 0 )
    v56 = v55;
  v57 = v56;
  LOWORD(v57) = v56 | 0x800;
  if ( (v417 & 0x800) == 0 )
    LOWORD(v57) = v56;
  v470 = v417 & 0x2000;
  v58 = v57 | 0x1000;
  if ( (v417 & 0x2000) == 0 )
    v58 = v57;
  v59 = v453;
  v60 = *((_DWORD *)v453 + 134) & 5;
  v414 = v58;
  if ( v60 == 1 && (*((_BYTE *)v453 + 728) & 1) != 0 )
  {
    v414 = v58;
    if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v453 + 16LL))(v453) )
    {
      v414 = v58;
      if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v59 + 24LL))(v59) )
      {
        if ( v455 == 1 )
          utassert_fail(1u, "pgOpCtxt != OPCTX_IN_LOGICAL_REVERT_TRAN", "pageref.cpp", 3609, 0);
        v414 = v58 | 0x100;
        v46 = v456;
      }
    }
  }
  v61 = v458;
  v62 = v458;
  v469 = v458;
  if ( v419 && v419 != 3 )
  {
    if ( !*((_WORD *)v46 + 18) )
      goto LABEL_161;
    v115 = *((_BYTE *)v46 + 1);
    if ( v115 == 11 )
    {
      if ( *((_DWORD *)v46 + 6) == 99 )
      {
LABEL_802:
        v487 = *((_DWORD *)v46 + 8);
        v488 = *((_WORD *)v46 + 18);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v487, v57) )
        {
          PageHeader::GetIcxLsn(v46, &v491);
          v117 = v492;
          v116 = v491;
          goto LABEL_162;
        }
LABEL_161:
        v116 = *((_QWORD *)v46 + 5);
        v491 = v116;
        v117 = *((_WORD *)v46 + 24);
        v492 = v117;
LABEL_162:
        v504 = v116;
        v505 = v117;
        v90 = v452;
        v118 = *((_QWORD *)*v452 + 18);
        v119 = *v452;
        if ( !v118 )
        {
          BUF::FixupPru(*v452);
          v119 = *v90;
          v118 = *(_QWORD *)(v306 + 144);
        }
        DirtyPageMgr::PreNonLoggedDirty(*(DirtyPageMgr **)(v118 + 1880), v119, 0);
        goto LABEL_107;
      }
    }
    else if ( v115 == 8 )
    {
LABEL_804:
      if ( *((_DWORD *)v46 + 6) != 99 )
        goto LABEL_161;
      goto LABEL_802;
    }
    if ( v115 != 9 )
      goto LABEL_161;
    goto LABEL_804;
  }
  v63 = 0;
  v64 = 1;
  v416 = 1;
  if ( (*((_BYTE *)v453 + 536) & 1) == 0 )
  {
    utassert_fail(1u, "(pXdes != NULL) && !pXdes->IsReadOnly ()", "pageref.cpp", 3637, 0);
    v61 = v458;
  }
  if ( v61 > 1 )
  {
    v98 = alloca(8288);
    v65 = v407;
    v468 = (PageLog *)v407;
    v99 = v61 + 3;
    v100 = 4 * v99 + 15;
    if ( v100 <= 4 * v99 )
      v100 = 0xFFFFFFFFFFFFFF0LL;
    v101 = v100 & 0xFFFFFFFFFFFFFFF0uLL;
    v102 = alloca(v101);
    v103 = alloca(v101);
    v457 = (unsigned int *)v407;
    v104 = 8 * v99 + 15;
    if ( v104 <= 8 * v99 )
      v104 = 0xFFFFFFFFFFFFFF0LL;
    v105 = v104 & 0xFFFFFFFFFFFFFFF0uLL;
    v106 = alloca(v105);
    v107 = alloca(v105);
    v66 = (void **)v407;
  }
  else
  {
    v65 = v525;
    v468 = (PageLog *)v525;
    v457 = (unsigned int *)&v526;
    v66 = (void **)&v527;
  }
  v478 = v66;
  *((_DWORD *)v65 + 4) = 0;
  *((_WORD *)v65 + 10) = 0;
  *((_WORD *)v65 + 31) = 0;
  v67 = a8;
  if ( *((_BYTE *)v456 + 1) == 1 )
    v63 = a8 != 0 ? 4 : 0;
  v68 = v63 | 0x400;
  if ( (v417 & 0x1000000) == 0 )
    v68 = v63;
  v69 = v452;
  if ( (unsigned __int8)(*(_BYTE *)(*(_QWORD *)*v452 + 1LL) - 3) <= 1u || (v417 & 0x40000) != 0 )
  {
    v67 = -a8;
    v68 |= a8 != 0 ? 4 : 0;
  }
  v65[22] = 2;
  v70 = *((_WORD *)*v69 + 49);
  v71 = v456;
  v65[23] = PageLog::MapContext(v456, a7, v67);
  LOBYTE(v409) = (v70 & 8) != 0;
  v72 = v413;
  v73 = v468;
  PageLog::FillPageInfo(v468, a3, v71, v413, v68, (bool)v409);
  *((_QWORD *)v73 + 6) = v466;
  *((_WORD *)v73 + 30) = v414;
  *((_DWORD *)v73 + 14) = 0;
  v75 = v417;
  if ( (v417 & 4) != 0 )
    *((_BYTE *)v73 + 23) = 14;
  v76 = v75 & 3;
  *((_WORD *)v73 + 29) = v76;
  if ( v75 < 0 )
  {
    v74 = 1024;
    *((_WORD *)v73 + 29) = v76 | 0x400;
  }
  v77 = 0;
  LODWORD(v466) = 0;
  if ( v469 <= 0 )
  {
    v85 = (const void **)v478;
    goto LABEL_96;
  }
  for ( i = 0; i < v469; ++i )
  {
    if ( v470 )
      v79 = *((_QWORD *)v459 + 5 * i + 1);
    else
      v79 = *((_QWORD *)v459 + 5 * i);
    if ( (unsigned int)PageRef::NotToLogNewData(v452, v454) )
    {
      v80 = 0;
      goto LABEL_88;
    }
    if ( !*(_WORD *)v79 )
    {
      if ( *(_DWORD *)(v79 + 4) )
      {
LABEL_86:
        v80 = *(_DWORD *)(v79 + 4);
        if ( v80 < 9 )
        {
          v74 = **(unsigned __int8 **)(v79 + 8);
          LOBYTE(v74) = v74 & 0xE;
          if ( !(_BYTE)v74 || (_BYTE)v74 == 12 )
            v80 = 9;
        }
        v64 = v416;
        v77 = v466;
        goto LABEL_88;
      }
      *(_WORD *)(v79 + 2) = 0;
      v74 = *(unsigned int *)(v79 + 16);
      *(_DWORD *)(v79 + 20) = v74;
      v307 = *(char **)(v79 + 8);
      v308 = *v307;
      v309 = v74;
      if ( (*v307 & 0x10) != 0 )
      {
        v74 = (((unsigned int)*(unsigned __int16 *)&v307[v74] + 7) >> 3) + 2 + (unsigned int)v74;
        *(_DWORD *)(v79 + 20) = v74;
        v308 = *v307;
        v309 = v74;
      }
      if ( (v308 & 0x20) != 0 )
      {
        v310 = (__int16 *)&v307[(unsigned int)v74];
        v311 = *v310;
        *(_WORD *)(v79 + 28) = *v310;
        if ( !v311 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v312 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v312 )
            {
              v313 = *(_QWORD *)(v312 + 96);
              if ( v313 )
              {
                if ( *(_BYTE *)(v313 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 3);
          v309 = *(_DWORD *)(v79 + 20);
        }
        v314 = *(unsigned __int16 *)(v79 + 28);
        v315 = v309 + 2 * (v314 + 1);
        *(_DWORD *)(v79 + 24) = v315;
        if ( v315 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v316 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v316 )
            {
              v317 = *(_QWORD *)(v316 + 96);
              if ( v317 )
              {
                if ( *(_BYTE *)(v317 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 4);
          LOWORD(v314) = *(_WORD *)(v79 + 28);
          v315 = *(_DWORD *)(v79 + 24);
        }
        v318 = v310[(unsigned __int16)v314] & 0x7FFF;
        *(_DWORD *)(v79 + 4) = v318;
        if ( v315 > v318 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v319 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v319 )
            {
              v320 = *(_QWORD *)(v319 + 96);
              if ( v320 )
              {
                if ( *(_BYTE *)(v320 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 4);
          LOWORD(v314) = *(_WORD *)(v79 + 28);
        }
        v321 = v314;
        if ( v310[(unsigned __int16)v314] < 0 )
        {
          while ( 1 )
          {
            v322 = *(_QWORD *)(v79 + 8) + *(unsigned int *)(v79 + 20);
            if ( v321 == 1 )
            {
              v323 = *(_DWORD *)(v79 + 24);
              v74 = v323;
              v324 = *(_WORD *)(v322 + 2LL * v321) & 0x7FFF;
            }
            else
            {
              v323 = *(_WORD *)(v322 + 2LL * v321 - 2) & 0x7FFF;
              v74 = *(unsigned int *)(v79 + 24);
              v324 = *(_WORD *)(v322 + 2LL * v321) & 0x7FFF;
              if ( v323 < (unsigned int)v74 )
              {
LABEL_845:
                RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 7);
                v74 = *(unsigned int *)(v79 + 24);
                goto LABEL_846;
              }
            }
            if ( v324 < v323 )
              goto LABEL_845;
LABEL_846:
            if ( v323 < (unsigned int)v74 || v323 > *(_DWORD *)(v79 + 4) )
              goto LABEL_86;
            v325 = *(_WORD *)(v323 + *(_QWORD *)(v79 + 8));
            if ( v325 == 5 )
            {
              *(_WORD *)(v79 + 2) |= 2u;
              --*(_WORD *)(v79 + 28);
              *(_WORD *)(v79 + 42) = v323;
              v339 = *(_QWORD *)(v79 + 8) + (unsigned __int16)v323;
              v340 = *(_WORD *)(v79 + 44) & 0xC7FF;
              if ( _bittest16((const signed __int16 *)(v339 + 2), 0xEu) )
                v340 |= *(_WORD *)(v339 + 2) & 0x3800;
              *(_WORD *)(v79 + 44) = v340;
              *(_WORD *)(v79 + 44) = v340 ^ (*(_WORD *)(v339 + 2) ^ v340) & 0x7FF;
              break;
            }
            if ( v325 < 0x400u )
              break;
            *(_WORD *)(v79 + 2) |= 1u;
            v326 = *(_WORD *)(v79 + 28) - 1;
            *(_WORD *)(v79 + 28) = v326;
            if ( !v326 )
              break;
            v321 = v326;
            if ( v310[v326] >= 0 )
            {
              v307 = *(char **)(v79 + 8);
              v74 = *(unsigned int *)(v79 + 4);
              goto LABEL_853;
            }
          }
        }
        v307 = *(char **)(v79 + 8);
        v74 = *(unsigned int *)(v79 + 4);
      }
      else
      {
        *(_DWORD *)(v79 + 4) = v74;
        *(_WORD *)(v79 + 28) = 0;
        *(_DWORD *)(v79 + 24) = v309;
      }
LABEL_853:
      if ( (*v307 & 0x40) != 0 )
      {
        v327 = *(_DWORD *)(v79 + 4);
        *(_DWORD *)(v79 + 38) = v327;
        *(_DWORD *)(v79 + 4) = v327 + 14;
        v328 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v79 + 2));
        v329 = HIDWORD(*(_QWORD *)v328);
        v330 = HIWORD(*(_QWORD *)v328);
        v331 = 0;
        if ( (((__int16)v330 ^ ((unsigned int)(__int16)v330 >> 1)) & 0x2000) != 0 )
        {
          v332 = v330 & 0xDFFF;
          if ( (v330 & 0x4000) != 0 )
            v332 = v330 | 0x2000;
          LOWORD(v330) = v332;
        }
        if ( (_WORD)v330 == 0xFFFC )
          v331 = (unsigned __int16)v329 >> 5;
        *(_DWORD *)(v79 + 4) += v331;
        v74 = *(unsigned int *)(v79 + 4);
      }
      else
      {
        *(_DWORD *)(v79 + 38) = 0;
      }
      v333 = *(_QWORD *)(v79 + 30);
      v334 = v74;
      if ( v333 && v333 < *(_QWORD *)(v79 + 8) + (unsigned __int64)(unsigned int)v74 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v335 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v335 )
          {
            v336 = *(_QWORD *)(v335 + 96);
            if ( v336 )
            {
              if ( *(_BYTE *)(v336 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 18);
        v334 = *(_DWORD *)(v79 + 4);
      }
      if ( (unsigned int)(v334 - 1) > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v337 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v337 )
          {
            v338 = *(_QWORD *)(v337 + 96);
            if ( v338 )
            {
              if ( *(_BYTE *)(v338 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 5);
      }
      goto LABEL_86;
    }
    v80 = *(_DWORD *)(v79 + 4);
    if ( !v80 )
    {
      CDRecord::Resize((CDRecord *)(v79 + 2));
      v80 = *(_DWORD *)(v79 + 4);
    }
    if ( v80 < 9 )
    {
      v341 = *(_BYTE **)(v79 + 8);
      v74 = *v341 & 0x1C;
      if ( (*v341 & 0x1C) == 0 || (_DWORD)v74 == 12 )
        v80 = 9;
    }
LABEL_88:
    v81 = v64;
    v82 = v457;
    v457[v64] = v80;
    if ( !*(_WORD *)v79 )
    {
      if ( *(_DWORD *)(v79 + 4) )
      {
LABEL_90:
        v83 = *(_DWORD *)(v79 + 4);
        if ( v83 < 9 )
        {
          v74 = **(unsigned __int8 **)(v79 + 8);
          LOBYTE(v74) = v74 & 0xE;
          if ( !(_BYTE)v74 || (_BYTE)v74 == 12 )
            v83 = 9;
        }
        v64 = v416;
        v77 = v466;
        goto LABEL_92;
      }
      *(_WORD *)(v79 + 2) = 0;
      v74 = *(unsigned int *)(v79 + 16);
      *(_DWORD *)(v79 + 20) = v74;
      v342 = *(char **)(v79 + 8);
      v343 = *v342;
      v344 = v74;
      if ( (*v342 & 0x10) != 0 )
      {
        v74 = (((unsigned int)*(unsigned __int16 *)&v342[v74] + 7) >> 3) + 2 + (unsigned int)v74;
        *(_DWORD *)(v79 + 20) = v74;
        v343 = *v342;
        v344 = v74;
      }
      if ( (v343 & 0x20) != 0 )
      {
        v345 = (__int16 *)&v342[(unsigned int)v74];
        v346 = *v345;
        *(_WORD *)(v79 + 28) = *v345;
        if ( !v346 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v347 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v347 )
            {
              v348 = *(_QWORD *)(v347 + 96);
              if ( v348 )
              {
                if ( *(_BYTE *)(v348 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 3);
          v344 = *(_DWORD *)(v79 + 20);
        }
        v349 = *(unsigned __int16 *)(v79 + 28);
        v350 = v344 + 2 * (v349 + 1);
        *(_DWORD *)(v79 + 24) = v350;
        if ( v350 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v351 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v351 )
            {
              v352 = *(_QWORD *)(v351 + 96);
              if ( v352 )
              {
                if ( *(_BYTE *)(v352 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 4);
          LOWORD(v349) = *(_WORD *)(v79 + 28);
          v350 = *(_DWORD *)(v79 + 24);
        }
        v353 = v345[(unsigned __int16)v349] & 0x7FFF;
        *(_DWORD *)(v79 + 4) = v353;
        if ( v350 > v353 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v354 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v354 )
            {
              v355 = *(_QWORD *)(v354 + 96);
              if ( v355 )
              {
                if ( *(_BYTE *)(v355 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 4);
          LOWORD(v349) = *(_WORD *)(v79 + 28);
        }
        v356 = v349;
        if ( v345[(unsigned __int16)v349] < 0 )
        {
          while ( 1 )
          {
            v357 = *(_QWORD *)(v79 + 8) + *(unsigned int *)(v79 + 20);
            if ( v356 == 1 )
            {
              v358 = *(_DWORD *)(v79 + 24);
              v74 = v358;
              v359 = *(_WORD *)(v357 + 2LL * v356) & 0x7FFF;
            }
            else
            {
              v358 = *(_WORD *)(v357 + 2LL * v356 - 2) & 0x7FFF;
              v74 = *(unsigned int *)(v79 + 24);
              v359 = *(_WORD *)(v357 + 2LL * v356) & 0x7FFF;
              if ( v358 < (unsigned int)v74 )
              {
LABEL_941:
                RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 7);
                v74 = *(unsigned int *)(v79 + 24);
                goto LABEL_942;
              }
            }
            if ( v359 < v358 )
              goto LABEL_941;
LABEL_942:
            if ( v358 < (unsigned int)v74 || v358 > *(_DWORD *)(v79 + 4) )
              goto LABEL_978;
            v360 = *(_WORD *)(v358 + *(_QWORD *)(v79 + 8));
            if ( v360 == 5 )
            {
              *(_WORD *)(v79 + 2) |= 2u;
              --*(_WORD *)(v79 + 28);
              *(_WORD *)(v79 + 42) = v358;
              v374 = *(_QWORD *)(v79 + 8) + (unsigned __int16)v358;
              v375 = *(_WORD *)(v79 + 44) & 0xC7FF;
              if ( _bittest16((const signed __int16 *)(v374 + 2), 0xEu) )
                v375 |= *(_WORD *)(v374 + 2) & 0x3800;
              *(_WORD *)(v79 + 44) = v375;
              *(_WORD *)(v79 + 44) = v375 ^ (*(_WORD *)(v374 + 2) ^ v375) & 0x7FF;
              break;
            }
            if ( v360 < 0x400u )
              break;
            *(_WORD *)(v79 + 2) |= 1u;
            v361 = *(_WORD *)(v79 + 28) - 1;
            *(_WORD *)(v79 + 28) = v361;
            if ( !v361 )
              break;
            v356 = v361;
            if ( v345[v361] >= 0 )
            {
              v342 = *(char **)(v79 + 8);
              v74 = *(unsigned int *)(v79 + 4);
              goto LABEL_949;
            }
          }
        }
        v342 = *(char **)(v79 + 8);
        v74 = *(unsigned int *)(v79 + 4);
      }
      else
      {
        *(_DWORD *)(v79 + 4) = v74;
        *(_WORD *)(v79 + 28) = 0;
        *(_DWORD *)(v79 + 24) = v344;
      }
LABEL_949:
      if ( (*v342 & 0x40) != 0 )
      {
        v362 = *(_DWORD *)(v79 + 4);
        *(_DWORD *)(v79 + 38) = v362;
        *(_DWORD *)(v79 + 4) = v362 + 14;
        v363 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v79 + 2));
        v364 = HIDWORD(*(_QWORD *)v363);
        v365 = HIWORD(*(_QWORD *)v363);
        v366 = 0;
        if ( (((__int16)v365 ^ ((unsigned int)(__int16)v365 >> 1)) & 0x2000) != 0 )
        {
          v367 = v365 & 0xDFFF;
          if ( (v365 & 0x4000) != 0 )
            v367 = v365 | 0x2000;
          LOWORD(v365) = v367;
        }
        if ( (_WORD)v365 == 0xFFFC )
          v366 = (unsigned __int16)v364 >> 5;
        *(_DWORD *)(v79 + 4) += v366;
        v74 = *(unsigned int *)(v79 + 4);
      }
      else
      {
        *(_DWORD *)(v79 + 38) = 0;
      }
      v368 = *(_QWORD *)(v79 + 30);
      v369 = v74;
      if ( v368 && v368 < *(_QWORD *)(v79 + 8) + (unsigned __int64)(unsigned int)v74 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v370 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v370 )
          {
            v371 = *(_QWORD *)(v370 + 96);
            if ( v371 )
            {
              if ( *(_BYTE *)(v371 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 18);
        v369 = *(_DWORD *)(v79 + 4);
      }
      if ( (unsigned int)(v369 - 1) > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v372 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v372 )
          {
            v373 = *(_QWORD *)(v372 + 96);
            if ( v373 )
            {
              if ( *(_BYTE *)(v373 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v79 + 8), 5);
      }
LABEL_978:
      v82 = v457;
      goto LABEL_90;
    }
    v83 = *(_DWORD *)(v79 + 4);
    if ( !v83 )
    {
      CDRecord::Resize((CDRecord *)(v79 + 2));
      v83 = *(_DWORD *)(v79 + 4);
      v82 = v457;
    }
    if ( v83 < 9 )
    {
      v376 = *(_BYTE **)(v79 + 8);
      v74 = *v376 & 0x1C;
      if ( (*v376 & 0x1C) == 0 || (_DWORD)v74 == 12 )
        v83 = 9;
    }
LABEL_92:
    v77 += v83 + 2;
    LODWORD(v466) = v77;
    v73 = v468;
    *((_WORD *)v468 + *((unsigned __int16 *)v468 + 31) + 32) = v82[v81];
    ++*((_WORD *)v73 + 31);
    v84 = *(void **)(v79 + 8);
    v85 = (const void **)v478;
    v478[v81] = v84;
    v416 = ++v64;
  }
  if ( v77 > 0x1FA0 )
  {
    _mm_lfence();
    v377 = v452;
    v378 = *((unsigned __int16 *)*v452 + 58);
    v379 = v477;
    v380 = *((unsigned __int16 *)v477 + 860);
    LODWORD(v408) = *((_DWORD *)*v452 + 28);
    scierrlog(0x5600u, v380, v77, v378, v408);
    v381 = *((unsigned __int16 *)*v377 + 58);
    v382 = *((unsigned __int16 *)v379 + 860);
    LODWORD(v411) = *((_DWORD *)*v377 + 28);
    LODWORD(v410) = v381;
    LODWORD(v409) = v77;
    LODWORD(v408) = v382;
    ex_raise(220, 16, 16, 2, v408, v409, v410, v411);
  }
  v75 = v417;
  v72 = v413;
  v71 = v456;
LABEL_96:
  if ( (v75 & 0x80u) != 0 )
  {
    v506 = -1;
    v509 = 0;
    v508 = 0;
    *(_QWORD *)&v511[6] = 0;
    *(_QWORD *)&v511[16] = 0;
    v510 = 0;
    v513 = v72;
    if ( *((char *)v71 + 2) >= 0 )
    {
      v125 = 0;
LABEL_186:
      v126 = *((unsigned __int16 *)v71 + 7);
      v127 = (char *)v71 + *((unsigned __int16 *)v71 + 4095LL - v413);
      v236 = (*v127 & 1) == 0;
      v509 = v127;
      if ( v236 )
      {
        v506 = 0;
        v508 = 0;
        *(_DWORD *)&v511[14] = 0;
        switch ( *v127 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v126 = *((unsigned __int16 *)v127 + 1);
            if ( (unsigned int)(v126 - 1) > 0x1F9D )
              RaiseInconsistencyError(v127, 6);
            break;
          case 1:
          case 3:
          case 5:
          case 7:
          case 9:
          case 0xB:
          case 0xD:
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
              294,
              "Invalid switch value");
            break;
          case 4:
            v126 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v126 = 1;
            break;
        }
        LODWORD(v510) = v126;
        v128 = (char *)v71 + 0x2000;
        if ( !v71 )
          v128 = 0;
        *(_QWORD *)&v511[6] = v128;
      }
      else
      {
        v506 = 1;
        v396 = *v127;
        switch ( *v127 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( v127[1] < 0 )
            {
              v397 = HIBYTE(*(_WORD *)(v127 + 1)) | ((*(_WORD *)(v127 + 1) & 0x7F) << 8);
              v507 = v397;
              v398 = 3;
            }
            else
            {
              v397 = (unsigned __int8)v127[1];
              v507 = v397;
              v398 = 2;
              LOWORD(v467) = 2;
            }
            *(_WORD *)v511 = v398;
            *(_WORD *)&v511[4] = v467 + (((unsigned int)v397 + 1) >> 1);
            if ( v397 > 0x1Eu )
              *(_WORD *)&v511[2] = (v397 - 1) / 30;
            else
              *(_WORD *)&v511[2] = 0;
            v508 = 0;
            v512 = 0;
            break;
          case 1:
          case 2:
          case 3:
          case 5:
          case 6:
          case 7:
          case 9:
          case 0xA:
          case 0xB:
          case 0xD:
          case 0xE:
          case 0xF:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x19:
          case 0x1A:
          case 0x1B:
            utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
            break;
          case 4:
            if ( (v396 & 0x1C) == 4 && (v396 & 2) != 0 )
            {
              *(_QWORD *)v511 = 0;
              v507 = 0;
              *(_QWORD *)&v511[8] = 0;
              v508 = 15;
              v512 = 1;
            }
            else
            {
              *(_QWORD *)v511 = 0;
              v507 = 0;
              *(_QWORD *)&v511[8] = 0;
              v508 = 1;
              v512 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v511 = 0;
            v507 = 0;
            *(_QWORD *)&v511[8] = 0;
            v508 = 9;
            v512 = 0;
            break;
        }
        v399 = (char *)v71 + 0x2000;
        if ( !v71 )
          v399 = 0;
        *(_QWORD *)&v511[16] = v399;
        v510 = v125;
      }
      if ( v506 )
        CDRecord::GetXdesTs(&v507, &v475);
      else
        FixedVarRecord::GetXdesTs(&v507, &v475);
      v523 = v475;
      v524 = v476;
      if ( v506 )
        CDRecord::GetVersionRecPtr(&v507, &v499);
      else
        FixedVarRecord::GetVersionRecPtr(&v507, &v499);
      v522 = v499;
      v73 = v468;
      *((_WORD *)v468 + *((unsigned __int16 *)v468 + 31) + 32) = 14;
      ++*((_WORD *)v73 + 31);
      v86 = v457;
      v457[v64] = 14;
      v85[v64++] = &v522;
      goto LABEL_99;
    }
    v383 = (char *)v71 + 96;
    _mm_prefetch((const char *)v71 + 96, 0);
    memset(v517, 0, sizeof(v517));
    v518 = 0.0;
    memset(v519, 0, sizeof(v519));
    v521 = 0;
    *(_OWORD *)v514 = 0;
    v515 = 0xFFFFu;
    v516 = 0;
    v520 = 0u;
    v125 = v514;
    if ( !*((_WORD *)v71 + 18) )
      goto LABEL_1013;
    v384 = *((_BYTE *)v71 + 1);
    if ( v384 == 11 )
    {
      if ( *((_DWORD *)v71 + 6) == 99 )
      {
LABEL_1005:
        v489 = *((_DWORD *)v71 + 8);
        v490 = *((_WORD *)v71 + 18);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v489, v74) )
        {
          PageHeader::GetIcxLsn(v71, &v483);
          v385 = v484;
LABEL_1007:
          v514[0] = (Page *)((char *)v71 + 96);
          *(_QWORD *)&v520 = v483;
          WORD4(v520) = v385;
          HIDWORD(v520) = *((_DWORD *)v71 + 8);
          LODWORD(v521) = *((unsigned __int16 *)v71 + 18);
          v386 = 3LL * (unsigned __int8)*v383;
          v470 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * (unsigned __int8)*v383);
          v387 = word_102883984[v386];
          LOWORD(v515) = -1;
          *((_QWORD *)&v515 + 1) = 0;
          DWORD1(v515) = 0;
          *(_QWORD *)&v517[6] = 0;
          *(_QWORD *)((char *)&v518 + 2) = 0;
          v516 = 0;
          memset((char *)v519 + 8, 0, 18);
          if ( (*v383 & 2) != 0 )
          {
            v388 = &v383[v387];
            v236 = (v383[v387] & 1) == 0;
            *((_QWORD *)&v515 + 1) = &v383[v387];
            if ( v236 )
            {
              LOWORD(v515) = 0;
              v395 = 0;
              LODWORD(v518) = 0;
              switch ( *v388 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v395 = *((unsigned __int16 *)v388 + 1);
                  if ( (unsigned int)(v395 - 1) > 0x1F9D )
                    RaiseInconsistencyError(&v383[v387], 6);
                  break;
                case 1:
                case 3:
                case 5:
                case 7:
                case 9:
                case 0xB:
                case 0xD:
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\fixedvarrecord.inl",
                    294,
                    "Invalid switch value");
                  break;
                case 4:
                  v395 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v395 = 1;
                  break;
              }
              LODWORD(v516) = v395;
              *(_QWORD *)&v517[6] = 0;
            }
            else
            {
              LOWORD(v515) = 1;
              v389 = *v388;
              switch ( *v388 & 0x1C )
              {
                case 0:
                case 0xC:
                case 0x10:
                case 0x14:
                case 0x18:
                case 0x1C:
                  if ( (char)v388[1] < 0 )
                  {
                    v390 = 3;
                    v391 = HIBYTE(*(_WORD *)(v388 + 1)) | ((*(_WORD *)(v388 + 1) & 0x7F) << 8);
                  }
                  else
                  {
                    v390 = 2;
                    v391 = (unsigned __int8)v388[1];
                  }
                  WORD1(v515) = v391;
                  *(_WORD *)v517 = v390;
                  *(_WORD *)&v517[4] = v390 + (((unsigned int)v391 + 1) >> 1);
                  if ( v391 > 0x1Eu )
                    *(_WORD *)&v517[2] = (v391 - 1) / 30;
                  else
                    *(_WORD *)&v517[2] = 0;
                  LODWORD(v519[0]) = 0;
                  *(_QWORD *)((char *)&v518 + 2) = 0;
                  v516 = 0;
                  break;
                case 1:
                case 2:
                case 3:
                case 5:
                case 6:
                case 7:
                case 9:
                case 0xA:
                case 0xB:
                case 0xD:
                case 0xE:
                case 0xF:
                case 0x11:
                case 0x12:
                case 0x13:
                case 0x15:
                case 0x16:
                case 0x17:
                case 0x19:
                case 0x1A:
                case 0x1B:
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                    207,
                    "Invalid switch value");
                  *(_QWORD *)((char *)&v518 + 2) = 0;
                  v516 = 0;
                  break;
                case 4:
                  if ( (v389 & 0x1C) == 4 && (v389 & 2) != 0 )
                  {
                    v394 = 1;
                    DWORD1(v515) = 15;
                  }
                  else
                  {
                    v394 = 0;
                    DWORD1(v515) = 1;
                  }
                  v518 = 0.0;
                  *(_WORD *)&v517[4] = 0;
                  WORD1(v515) = 0;
                  *(_DWORD *)v517 = 0;
                  LODWORD(v519[0]) = v394;
                  v516 = 0;
                  break;
                case 8:
                  *(_DWORD *)v517 = 0;
                  WORD1(v515) = 0;
                  *(_WORD *)&v517[4] = 0;
                  v518 = 0.0;
                  DWORD1(v515) = 9;
                  LODWORD(v519[0]) = 0;
                  v516 = 0;
                  break;
              }
            }
          }
          if ( (*(_BYTE *)v514[0] & 4) != 0 )
          {
            if ( HIWORD(v470) )
              v392 = *(unsigned __int16 *)&v383[2 * SHIWORD(v470) + 1];
            else
              v392 = v387;
            *((_QWORD *)&v519[0] + 1) = &v383[v392];
            v393 = *(_WORD *)&v383[v392];
            *(_QWORD *)&v519[1] = &v383[v392 + 2];
            WORD4(v519[1]) = 2 * (v393 + 1);
          }
          if ( v514[1] )
            PageComprInfoCache::Init(v514[1], (const struct PageComprInfo *)v514);
          v64 = v416;
          goto LABEL_186;
        }
LABEL_1013:
        v483 = *((_QWORD *)v71 + 5);
        v385 = *((_WORD *)v71 + 24);
        v484 = v385;
        goto LABEL_1007;
      }
    }
    else if ( v384 == 8 )
    {
LABEL_1012:
      if ( *((_DWORD *)v71 + 6) != 99 )
        goto LABEL_1013;
      goto LABEL_1005;
    }
    if ( v384 != 9 )
      goto LABEL_1013;
    goto LABEL_1012;
  }
  if ( (v75 & 0x1000) != 0 )
  {
    v400 = *(_WORD **)v459;
    v401 = *(_QWORD *)v459 + 2LL;
    if ( **(_WORD **)v459 )
      CDRecord::GetXdesTs(v401, &v471);
    else
      FixedVarRecord::GetXdesTs(v401, &v471);
    v523 = v471;
    v524 = v472;
    v402 = v400 + 1;
    if ( *v400 )
      CDRecord::GetVersionRecPtr(v402, &v500);
    else
      FixedVarRecord::GetVersionRecPtr(v402, &v500);
    v522 = v500;
    v73 = v468;
    *((_WORD *)v468 + *((unsigned __int16 *)v468 + 31) + 32) = 14;
    ++*((_WORD *)v73 + 31);
    v86 = v457;
    v457[v64] = 14;
    v85[v64++] = &v522;
  }
  else
  {
    *((_WORD *)v73 + (unsigned __int16)(*((_WORD *)v73 + 31))++ + 32) = 0;
    v86 = v457;
  }
LABEL_99:
  v87 = v453;
  v88 = v412;
  if ( a10 && *((_DWORD *)v453 + 56) && !v412 )
  {
    *((_WORD *)v73 + (unsigned __int16)(*((_WORD *)v73 + 31))++ + 32) = *(_DWORD *)(a10 + 40);
    v86[v64] = *(_DWORD *)(a10 + 40);
    v85[v64++] = *(const void **)(a10 + 48);
  }
  else
  {
    *((_WORD *)v73 + (unsigned __int16)(*((_WORD *)v73 + 31))++ + 32) = 0;
  }
  v89 = *((_WORD *)v73 + 31);
  *((_WORD *)v73 + 1) = 62;
  *v86 = 2 * v89 + 64;
  *v85 = v73;
  if ( v419 == 3 )
  {
    if ( v88 )
    {
      *((_BYTE *)v73 + 23) = 35;
      *((_WORD *)v73 + 7) &= ~2u;
    }
    *(_QWORD *)((char *)v73 + 4) = 0;
    *((_WORD *)v73 + 6) = 0;
    XDES::GenerateNonXactLogRec(v477, v64, v86, v85, (struct LSN *)&v504, 0, 0);
  }
  else if ( v455 == 2 )
  {
    v501 = v87;
    *((_BYTE *)v87 + 714) = 1;
    (*(void (__fastcall **)(XDES *, _QWORD, unsigned int *, const void **, __int64 *))(*(_QWORD *)v87 + 648LL))(
      v87,
      v64,
      v86,
      v85,
      &v504);
    *((_BYTE *)v87 + 714) = 0;
    v501 = 0;
  }
  else
  {
    (*(void (__fastcall **)(XDES *, _QWORD, unsigned int *, const void **, __int64 *))(*(_QWORD *)v87 + 648LL))(
      v87,
      v64,
      v86,
      v85,
      &v504);
  }
  v62 = v469;
  v46 = v456;
  v90 = v452;
LABEL_107:
  if ( (v417 & 0x8000) == 0 )
  {
    if ( v458 == 1 )
    {
      if ( (v417 & 2) != 0 )
      {
        v91 = v413;
        Page::DeleteRow(v46, v413, v415, 0, v464);
        v124 = 1 << (*((_WORD *)v46 + 2) & 2);
        if ( 2 * (4096 - *((unsigned __int16 *)v46 + 11)) - (unsigned int)*((unsigned __int16 *)v46 + 15) < (unsigned int)(unsigned __int16)(-v124 & (v124 + v418 - 1)) + 2 )
          Page::CompactPage(v46, -1);
        goto LABEL_114;
      }
      if ( v421[0] )
      {
        v403 = 0;
        v404 = *((unsigned __int16 *)v46 + 11);
        v405 = v404 - 1;
        if ( v404 - 1 >= (unsigned __int16)(v404 - v421[0]) )
        {
          v406 = (_WORD *)((char *)v46 + 2 * (4095 - v405));
          do
          {
            if ( *v406 )
              break;
            ++v403;
            --v405;
            ++v406;
          }
          while ( v405 >= (unsigned __int16)(v404 - v421[0]) );
        }
        *((_WORD *)v46 + 11) = v404 - v403;
        *((_WORD *)v46 + 14) += 2 * v403;
      }
      if ( v462 )
        Page::CompactPage(v46, -1);
    }
    v91 = v413;
LABEL_114:
    v92 = v415 | 0x40;
    if ( (v414 & 0x100) == 0 )
      v92 = v415;
    if ( v62 > 0 )
    {
      v93 = v459;
      v94 = v496;
      v95 = v464;
      do
      {
        if ( v94 )
          v96 = (const struct Record *)*((_QWORD *)v93 + 1);
        else
          v96 = *(const struct Record **)v93;
        Page::InsertRow(v46, v91++, v96, v92, v420[0], v95);
        v93 = (struct RecordHolder *)((char *)v93 + 40);
        --v62;
      }
      while ( v62 );
      v15 = 0;
      v90 = v452;
    }
    goto LABEL_122;
  }
  v92 = v415 | 0x40;
  if ( (v414 & 0x100) == 0 )
    v92 = v415;
  Page::DeleteRowAndReplaceWithNewRow(v46, v413, v92, v459, v420[0], v464);
LABEL_122:
  if ( *((_WORD *)v46 + 24) != v505 || *((_QWORD *)v46 + 5) != v504 )
  {
    *((_QWORD *)v46 + 5) = v504;
    *((_WORD *)v46 + 24) = v505;
    *((_WORD *)v46 + 2) &= ~0x20u;
  }
  v497 = 0;
  v498 = 0;
  BPool::Dirty(qword_10317B628, *v90, 0, (struct LSN *)&v497);
  if ( (byte_10317AD49 & 2) != 0 )
    _InterlockedAnd((volatile signed __int32 *)*v90 + 25, 0xFFFFFFEF);
  if ( v461 || !*((_WORD *)v46 + 29) || (*((_WORD *)*v90 + 49) & 4) != 0 )
  {
    v97 = v453;
  }
  else
  {
    ChangeGhostPageState(*v90, (unsigned int)(*((_WORD *)*v90 + 22) != 2) + 2, 1);
    v97 = v453;
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v453 + 6) + 1712LL) + 5440LL), 0xFFFFFFF7);
  }
  if ( !v454 && (v92 & 2) == 0 )
  {
    v134 = *((unsigned __int16 *)v46 + 11) - 1LL;
    if ( v134 >= 0 )
    {
      v135 = (_WORD *)((char *)v46 + 2 * (4095 - v134));
      do
      {
        if ( *v135 )
          break;
        ++v15;
        ++v135;
        --v134;
      }
      while ( v134 >= 0 );
    }
    v136 = *((unsigned __int16 *)v46 + 14);
    v137 = v136 + 2 * v15;
    if ( !v460 )
    {
      if ( (unsigned __int8)PageRef::UpdateFreeSpaceStateInPFS(v90, &v465, v97, v455, v463, v136 + 2 * v15) )
      {
        v138 = 0;
        while ( v137 < dword_102830E28[v138] )
        {
          if ( ++v138 >= 4u )
          {
            v139 = *v90;
            v140 = 2;
            if ( *((unsigned __int16 *)qword_10317B628 + 388) - 3600 > 2 )
              v140 = *((_WORD *)qword_10317B628 + 388) - 3600;
            *(_WORD *)(*((_QWORD *)qword_10317B628 + 10)
                     + 2
                     * ((unsigned __int16)v139 / 0xC0uLL
                      + 341 * (((__int64)v139 - *((_QWORD *)qword_10317B628 + 728)) / 0x10000))) = v140;
            *((_WORD *)v139 + 48) = v140;
            return;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x10043e660  push    rbp
0x10043e662  push    rsi
0x10043e663  push    rdi
0x10043e664  push    r12
0x10043e666  push    r13
0x10043e668  push    r14
0x10043e66a  push    r15
0x10043e66c  sub     rsp, 8F0h
0x10043e673  lea     rbp, [rsp+50h]
0x10043e678  mov     [rbp+8D0h+var_6A0], 0FFFFFFFFFFFFFFFEh
0x10043e683  mov     [rbp+8D0h+arg_8], rbx
0x10043e68a  mov     rax, cs:__security_cookie
0x10043e691  xor     rax, rbp
0x10043e694  mov     [rbp+8D0h+var_40], rax
0x10043e69b  mov     [rbp+8D0h+var_8CC], r9d
0x10043e69f  mov     r13, r8
0x10043e6a2  mov     [rbp+8D0h+var_7A0], rdx
0x10043e6a9  mov     rsi, rcx
0x10043e6ac  mov     [rbp+8D0h+var_800], rcx
0x10043e6b3  mov     eax, [rbp+8D0h+arg_20]
0x10043e6b9  mov     [rbp+8D0h+var_7D8], eax
0x10043e6bf  mov     rbx, [rbp+8D0h+arg_28]
0x10043e6c6  mov     [rbp+8D0h+var_7D0], rbx
0x10043e6cd  mov     rcx, [rbp+8D0h+arg_40]
0x10043e6d4  mov     [rbp+8D0h+var_7F8], rcx
0x10043e6db  mov     edx, 1
0x10043e6e0  mov     [rbp+8D0h+var_8C4], edx
0x10043e6e3  xor     r15d, r15d
0x10043e6e6  mov     [rbp+8D0h+var_7B0], r15
0x10043e6ed  mov     r14d, r15d
0x10043e6f0  mov     [rbp+8D0h+var_770], r15d
0x10043e6f7  mov     [rbp+8D0h+var_76C], r15w
0x10043e6ff  mov     [rbp+8D0h+var_7A8], r15
0x10043e706  mov     [rbp+8D0h+var_7BC], r15d
0x10043e70d  mov     [rbp+8D0h+var_8AC], r15w
0x10043e712  mov     [rbp+8D0h+var_6F0], r15
0x10043e719  mov     eax, r15d
0x10043e71c  mov     [rbp+8D0h+var_560], rax
0x10043e723  mov     [rbp+8D0h+var_558], r15d
0x10043e72a  mov     [rbp+8D0h+var_554], r15w
0x10043e732  mov     [rbp+8D0h+var_8B0], r15w
0x10043e737  mov     [rbp+8D0h+var_760], r15
0x10043e73e  mov     [rbp+8D0h+var_7EC], r15d
0x10043e745  mov     edi, [rbp+8D0h+arg_50]
0x10043e74b  mov     [rbp+8D0h+var_8BC], edi
0x10043e74e  test    rcx, rcx
0x10043e751  jz      short loc_10043E77D
0x10043e753  mov     rax, [rcx+30h]
0x10043e757  mov     [rbp+8D0h+var_760], rax
0x10043e75e  mov     rax, [rcx]
0x10043e761  call    qword ptr [rax]
0x10043e763  mov     edx, edi
0x10043e765  shr     edx, 15h
0x10043e768  and     edx, 2
0x10043e76b  test    al, al
0x10043e76d  mov     eax, 1
0x10043e772  cmovnz  edx, eax
0x10043e775  mov     [rbp+8D0h+var_7EC], edx
0x10043e77b  mov     edx, eax
0x10043e77d  mov     edi, 2
0x10043e782  mov     r12d, 0EDFFh
0x10043e788  cmp     [rbp+8D0h+arg_58], r14d
0x10043e78f  jnz     loc_10043E8F6
0x10043e795  xor     r9d, r9d
0x10043e798  mov     r8d, edx
0x10043e79b  mov     rdx, [rsi]
0x10043e79e  mov     rcx, cs:qword_10317B628
0x10043e7a5  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x10043e7aa  and     [rax+4], r12w
0x10043e7af  mov     dword ptr [rax+40h], 1
0x10043e7b6  mov     r11, [rsi]
0x10043e7b9  cmp     di, [r11+2Ch]
0x10043e7be  jz      loc_10043E8E0
0x10043e7c4  mov     rax, [r11+90h]
0x10043e7cb  test    rax, rax
0x10043e7ce  jz      loc_1018D38B8
0x10043e7d4  mov     rcx, [rax+6B0h]
0x10043e7db  test    byte ptr [rcx+3Ch], 1
0x10043e7df  jnz     loc_1018D38D0
0x10043e7e5  mov     r11, [rsi]
0x10043e7e8  mov     rax, [r11+90h]
0x10043e7ef  test    rax, rax
0x10043e7f2  jz      loc_1018D390B
0x10043e7f8  test    byte ptr [rax+1CD0h], 20h
0x10043e7ff  jnz     loc_10043E8E0
0x10043e805  mov     rax, [rsi]
0x10043e808  mov     r11, [rax]
0x10043e80b  cmp     [r11+24h], r14w
0x10043e810  jz      short loc_10043E82F
0x10043e812  movzx   eax, byte ptr [r11+1]
0x10043e817  cmp     al, 0Bh
0x10043e819  jz      loc_1018D3920
0x10043e81f  cmp     al, 8
0x10043e821  jz      loc_1018D396D
0x10043e827  cmp     al, 9
0x10043e829  jz      loc_1018D396D
0x10043e82f  movsd   xmm0, qword ptr [r11+28h]
0x10043e835  movsd   [rbp+8D0h+var_750], xmm0
0x10043e83d  movzx   eax, word ptr [r11+30h]
0x10043e842  mov     [rbp+8D0h+var_748], ax
0x10043e849  mov     r11, [rsi]
0x10043e84c  mov     rcx, [r11+90h]
0x10043e853  test    rcx, rcx
0x10043e856  jz      loc_1018D397A
0x10043e85c  movzx   edx, word ptr [r11+74h]
0x10043e861  xor     r8d, r8d
0x10043e864  mov     rcx, [rcx+6A0h]
0x10043e86b  call    ?GetFCB@FileMgr@@QEBAPEAVFCB@@JW4LookupFailureMode@@@Z; FileMgr::GetFCB(long,LookupFailureMode)
0x10043e870  mov     rdi, rax
0x10043e873  mov     rbx, [rsi]
0x10043e876  mov     rax, [rbx+90h]
0x10043e87d  mov     r11, rbx
0x10043e880  test    rax, rax
0x10043e883  jz      loc_1018D398F
0x10043e889  mov     rax, [rax+7A8h]
0x10043e890  cmp     [rax+58h], r14d
0x10043e894  jnz     loc_100479C49
0x10043e89a  mov     eax, [rdi+130h]
0x10043e8a0  cmp     eax, dword ptr [rbp+8D0h+var_750]
0x10043e8a6  ja      loc_100479C49
0x10043e8ac  jz      loc_100479C21
0x10043e8b2  mov     rax, [r11+90h]
0x10043e8b9  test    rax, rax
0x10043e8bc  jz      loc_1018D39D5
0x10043e8c2  mov     r8, [r11]
0x10043e8c5  mov     rax, [rax+7A8h]
0x10043e8cc  cmp     [rax+110h], r14d
0x10043e8d3  jnz     loc_1018D39ED
0x10043e8d9  mov     rbx, [rbp+8D0h+var_7D0]
0x10043e8e0  mov     rax, [rsi]
0x10043e8e3  mov     r11, [rax]
0x10043e8e6  mov     eax, 2000h
0x10043e8eb  test    [r11+4], ax
0x10043e8f0  jnz     loc_10049D1ED
0x10043e8f6  xor     r9d, r9d
0x10043e8f9  lea     r8d, [r9+1]
0x10043e8fd  mov     rdx, [rsi]
0x10043e900  mov     rcx, cs:qword_10317B628
0x10043e907  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x10043e90c  and     [rax+4], r12w
0x10043e911  mov     r12d, 1
0x10043e917  mov     [rax+40h], r12d
0x10043e91b  mov     rax, [rsi]
0x10043e91e  mov     rdi, [rax]
0x10043e921  mov     [rbp+8D0h+var_7E8], rdi
0x10043e928  movzx   eax, word ptr [rdi+3Ah]
0x10043e92c  mov     [rbp+8D0h+var_7C0], ax
0x10043e933  movzx   eax, byte ptr [rdi+2]
0x10043e937  shr     eax, 7
0x10043e93a  mov     [rbp+8D0h+var_6E8], eax
0x10043e940  test    eax, eax
0x10043e942  jnz     loc_1018D3AD8
0x10043e948  mov     rax, [rbx]
0x10043e94b  jmp     short loc_10043E94E
0x10043e94e  lea     rbx, [rax+2]
0x10043e952  mov     edi, 3
0x10043e957  mov     [rbp+8D0h+var_798], edi
0x10043e95d  cmp     [rax], r14w
0x10043e961  jnz     loc_1018D4113
0x10043e967  cmp     [rbx+2], r14d
0x10043e96b  jz      loc_1018D3AE2
0x10043e971  mov     ecx, [rbx+2]
0x10043e974  mov     [rbp+8D0h+var_8B8], ecx
0x10043e977  cmp     ecx, 9
0x10043e97a  jb      loc_1018D40F1
0x10043e980  mov     rsi, [rbp+8D0h+var_800]
0x10043e987  jmp     short loc_10043E98A
0x10043e98a  mov     eax, [r13+0]
0x10043e98e  mov     dword ptr [rbp+8D0h+var_7A8], eax
0x10043e994  movzx   eax, word ptr [r13+4]
0x10043e999  mov     word ptr [rbp+8D0h+var_7A8+4], ax
0x10043e9a0  movzx   eax, word ptr [r13+6]
0x10043e9a5  mov     word ptr [rbp+8D0h+var_7A8+6], ax
0x10043e9ac  mov     r11, [rsi]
0x10043e9af  mov     r12d, [rbp+8D0h+arg_30]
0x10043e9b6  mov     edi, 0FFFFFFFFh
0x10043e9bb  mov     r9d, 0FFh
0x10043e9c1  bt      r12d, 16h
0x10043e9c6  jb      loc_100492BCE
0x10043e9cc  mov     eax, [r11+64h]
0x10043e9d0  bt      eax, 13h
0x10043e9d4  jb      loc_1018D4156
0x10043e9da  mov     edi, r15d
0x10043e9dd  mov     [rbp+8D0h+var_8B4], edi
0x10043e9e0  mov     [rbp+8D0h+var_8D0], 0
0x10043e9e4  mov     rbx, [rbp+8D0h+var_7F8]
0x10043e9eb  test    rbx, rbx
0x10043e9ee  jz      short loc_10043EA01
0x10043e9f0  mov     rax, [rbx]
0x10043e9f3  mov     rcx, rbx
0x10043e9f6  call    qword ptr [rax+28h]
0x10043e9f9  test    al, al
0x10043e9fb  jnz     loc_1018D445C
0x10043ea01  mov     rsi, [rbp+8D0h+var_7E8]
0x10043ea08  movzx   eax, byte ptr [rsi+1]
0x10043ea0c  mov     edx, 0FFFh
0x10043ea11  mov     r9d, 10h
0x10043ea17  lea     r11, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x10043ea1e  cmp     al, 3
0x10043ea20  jz      loc_10060590B
0x10043ea26  cmp     al, 1
0x10043ea28  jnz     short loc_10043EA33
0x10043ea2a  test    al, r12b
0x10043ea2d  jz      loc_1006058E7
0x10043ea33  mov     r9d, 2
0x10043ea39  mov     [rbp+8D0h+var_7F0], r9d
0x10043ea40  mov     eax, [rbp+8D0h+var_7C8]
0x10043ea46  mov     [rbp+8D0h+var_7B8], eax
0x10043ea4c  mov     eax, [rbp+8D0h+var_8BC]
0x10043ea4f  cmp     [rbp+8D0h+var_7D8], 1
0x10043ea56  jnz     loc_100452FFA
0x10043ea5c  test    al, 2
0x10043ea5e  jnz     loc_1005B8010
0x10043ea64  mov     rdi, [rbp+8D0h+var_7B0]
0x10043ea6b  test    rdi, rdi
0x10043ea6e  jnz     loc_100605A20
0x10043ea74  mov     r14d, [rbp+8D0h+var_8B8]
0x10043ea78  mov     ebx, [rbp+8D0h+var_8C4]
0x10043ea7b  bt      eax, 0Fh
0x10043ea7f  jb      loc_1018D5B56
0x10043ea85  lea     rax, [rbp+8D0h+var_8AC]
0x10043ea89  mov     [rsp+920h+var_8F0], rax; unsigned __int16 *
0x10043ea8e  lea     rax, [rbp+8D0h+var_7BC]
0x10043ea95  mov     [rsp+920h+var_8F8], rax; int *
0x10043ea9a  mov     [rsp+920h+var_900], rdi; struct XdesId *
0x10043ea9f  mov     r9d, ebx; unsigned int
0x10043eaa2  mov     r8d, r14d; unsigned int
0x10043eaa5  mov     edx, [rbp+8D0h+var_8CC]; int
0x10043eaa8  mov     rcx, rsi; this
0x10043eaab  call    ?CheckInsertSpace@Page@@QEAAIHIIPEBVXdesId@@AEAHAEAG@Z; Page::CheckInsertSpace(int,uint,uint,XdesId const *,int &,ushort &)
0x10043eab0  test    eax, eax
0x10043eab2  jnz     loc_1018D6538
0x10043eab8  mov     r8d, [rbp+8D0h+var_8BC]
0x10043eabc  mov     ecx, r8d
0x10043eabf  mov     eax, 100h
0x10043eac4  movzx   edx, [rbp+8D0h+var_8B0]
0x10043eac8  mov     r9d, 80h
0x10043eace  or      dx, r9w
0x10043ead2  and     ecx, eax
0x10043ead4  cmovz   dx, [rbp+8D0h+var_8B0]
0x10043ead9  mov     eax, r8d
0x10043eadc  mov     r9d, 200h
0x10043eae2  and     eax, r9d
0x10043eae5  mov     [rbp+8D0h+var_7C8], eax
0x10043eaeb  movzx   ecx, dx
0x10043eaee  or      cx, r9w
0x10043eaf2  test    eax, eax
0x10043eaf4  cmovz   cx, dx
0x10043eaf8  mov     eax, r8d
0x10043eafb  mov     r9d, 800h
0x10043eb01  movzx   edx, cx
0x10043eb04  or      dx, r9w
0x10043eb08  and     eax, r9d
0x10043eb0b  cmovz   dx, cx
0x10043eb0f  mov     eax, r8d
0x10043eb12  and     eax, 2000h
0x10043eb17  mov     [rbp+8D0h+var_780], eax
0x10043eb1d  mov     r14d, 1000h
0x10043eb23  movzx   ebx, dx
0x10043eb26  or      bx, r14w
0x10043eb2a  test    eax, eax
0x10043eb2c  cmovz   bx, dx
0x10043eb30  mov     rdi, [rbp+8D0h+var_7F8]
0x10043eb37  mov     eax, [rdi+218h]
0x10043eb3d  and     al, 5
0x10043eb3f  mov     [rbp+8D0h+var_8C8], bx
0x10043eb43  cmp     al, 1
0x10043eb45  jnz     short loc_10043EB53
0x10043eb47  test    [rdi+2D8h], al
0x10043eb4d  jnz     loc_1018D659B
0x10043eb53  movsxd  rcx, [rbp+8D0h+var_7D8]
0x10043eb5a  mov     rdi, rcx
0x10043eb5d  mov     [rbp+8D0h+var_788], rcx
0x10043eb64  mov     eax, [rbp+8D0h+var_8B4]
0x10043eb67  test    eax, eax
0x10043eb69  jnz     loc_100492C28
0x10043eb6f  movzx   ebx, r15w
0x10043eb73  mov     r10d, 1
0x10043eb79  movzx   esi, r10w
0x10043eb7d  mov     [rbp+8D0h+var_8C0], r10w
0x10043eb82  mov     r8, [rbp+8D0h+var_7F8]
0x10043eb89  mov     eax, [r8+218h]
0x10043eb90  not     eax
0x10043eb92  test    r10b, al
0x10043eb95  jnz     loc_1018D668D
0x10043eb9b  cmp     ecx, 1
0x10043eb9e  jg      loc_100453019
0x10043eba4  lea     r14, [rbp+8D0h+var_550]
0x10043ebab  mov     [rbp+8D0h+var_790], r14
0x10043ebb2  lea     rax, [rbp+8D0h+var_490]
0x10043ebb9  mov     [rbp+8D0h+var_7E0], rax
0x10043ebc0  lea     rax, [rbp+8D0h+var_480]
0x10043ebc7  mov     [rbp+8D0h+var_758], rax
0x10043ebce  mov     [r14+10h], r15d
0x10043ebd2  mov     [r14+14h], r15w
0x10043ebd7  mov     [r14+3Eh], r15w
0x10043ebdc  mov     r8d, [rbp+8D0h+arg_38]
0x10043ebe3  mov     rdi, [rbp+8D0h+var_7E8]
0x10043ebea  cmp     [rdi+1], sil
0x10043ebee  jnz     short loc_10043EBFC
  ... truncated ...
```
