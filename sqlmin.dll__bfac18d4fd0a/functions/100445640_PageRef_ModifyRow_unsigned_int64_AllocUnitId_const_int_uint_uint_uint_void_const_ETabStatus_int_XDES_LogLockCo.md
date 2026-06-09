# PageRef::ModifyRow(unsigned __int64,AllocUnitId const &,int,uint,uint,uint,void const *,ETabStatus,int,XDES *,LogLockCollection const *,uint,void const *,uint,PageRef::CheckDiffMapCalled,RecordHolder const *,RecVersioningInfo const *)

- ea: `0x100445640`
- end: `0x100445e6c`
- name: `?ModifyRow@PageRef@@QEAAI_KAEBVAllocUnitId@@HIIIPEBXW4ETabStatus@@HPEAVXDES@@PEBVLogLockCollection@@I2IW4CheckDiffMapCalled@1@PEBVRecordHolder@@PEBVRecVersioningInfo@@@Z`
- size: `2092`
- prototype: ``
- caller_count: `23`
- callee_count: `45`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1004437c0`
- `0x100444450`
- `0x1004558e0`
- `0x1005b1c20`
- `0x1005b7610`
- `0x1005de550`
- `0x100604ea0`
- `0x100859a60`
- `0x10085a770`
- `0x101281d10`
- `0x101298560`
- `0x1012fa3b0`
- `0x1013016b0`
- `0x10161b1e0`
- `0x101643040`
- `0x101656320`
- `0x101658480`
- `0x1016c6da0`
- `0x10191a930`
- `0x101e7e5b0`
- `0x101e87820`
- `0x101e8a150`
- `0x101ea2520`

## callees

- `0x100401490`
- `0x100402000`
- `0x100415e90`
- `0x10042d750`
- `0x100432c80`
- `0x100441c10`
- `0x100441e00`
- `0x100441e40`
- `0x1004443e0`
- `0x100445640`
- `0x100445e80`
- `0x1004489c0`
- `0x100453ae0`
- `0x100455720`
- `0x10046bf90`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x100480640`
- `0x1004807a0`
- `0x100480b60`
- `0x1004813c0`
- `0x100481c40`
- `0x10048c200`
- `0x1004a6ea0`
- `0x10058cca0`
- `0x1006059f0`
- `0x100605a70`
- `0x100605c50`
- `0x100606760`
- `0x1012c9010`
- `0x10168b160`
- `0x1016c99f0`
- `0x101726350`
- `0x1018b7050`
- `0x1018bd390`
- `0x101912d90`
- `0x101d0fad0`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`
- `0x1021ed230`
- `0x102394d80`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1018e08f7`
- `KERNEL32!HeapAlloc` at `0x1018e08f7`
- `KERNEL32!GetProcessHeap` at `0x1018e08e6`
- `KERNEL32!GetProcessHeap` at `0x1018e08e6`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018e08c3`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1018e08c3`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018e09ce`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1018e09ce`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0a6b`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0a8d`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0a6b`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0a8d`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0b12`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0b3c`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0b12`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x1018e0b3c`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018e092c`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1018e092c`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e0aa8`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e0ad2`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e0aa8`
- `sqldk!?Init@CAutoStreamHeader@@QEAAHPEAVCDStream@@PEBDZZ` at `0x1018e0ad2`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e09b2`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e09c0`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e09b2`
- `sqldk!??1CAutoStreamHeader@@QEAA@XZ` at `0x1018e09c0`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e08d1`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e08df`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e08d1`
- `sqldk!??0CAutoStreamHeader@@QEAA@XZ` at `0x1018e08df`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018e0947`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x1018e0947`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e02b2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e034a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0370`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0399`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e03c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e048b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e04b4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e052b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0556`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0581`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0660`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0689`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e070b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0844`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e088e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e09a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0a20`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0ea4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0f14`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e121d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1248`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1273`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1424`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e14dd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e15a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1a96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1b25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e203f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2105`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e212a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2152`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e217a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e258f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e25ba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2b02`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2bad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2ec7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2f83`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e32cf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e02b2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e034a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0370`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0399`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e03c2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e048b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e04b4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e052b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0556`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0581`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0660`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0689`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e070b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0844`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e088e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e09a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0a20`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0ea4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e0f14`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e121d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1248`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1273`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1424`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e14dd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e15a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1a96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e1b25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e203f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2105`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e212a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2152`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e217a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e258f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e25ba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2b02`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2bad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2ec7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e2f83`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018e32cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df8c6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df97d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfb7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfc20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfd50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfe02`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfeb3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e00a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0140`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0fc8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e107a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e112d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e13e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e149e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1cd7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1d90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1e49`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e2343`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e23f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df814`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df8c6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018df97d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfb7a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfc20`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfd50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfe02`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018dfeb3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e00a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0140`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e0fc8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e107a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e112d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e13e5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e149e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1cd7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1d90`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e1e49`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e2343`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018e23f0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1018e15f5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1018e15f5`
- `sqldk!SystemThread_TlsIndex` at `0x100445a59`
- `sqldk!SystemThread_TlsIndex` at `0x1018df7b7`
- `sqldk!SystemThread_TlsIndex` at `0x1018df869`
- `sqldk!SystemThread_TlsIndex` at `0x1018df920`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfb1d`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfbc3`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfcf3`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfda5`
- `sqldk!SystemThread_TlsIndex` at `0x1018dfe56`
- `sqldk!SystemThread_TlsIndex` at `0x1018e0043`
- `sqldk!SystemThread_TlsIndex` at `0x1018e00e3`
- `sqldk!SystemThread_TlsIndex` at `0x1018e0f6b`
- `sqldk!SystemThread_TlsIndex` at `0x1018e101d`
- `sqldk!SystemThread_TlsIndex` at `0x1018e10d0`
- `sqldk!SystemThread_TlsIndex` at `0x1018e1390`
- `sqldk!SystemThread_TlsIndex` at `0x1018e1449`
- `sqldk!SystemThread_TlsIndex` at `0x1018e1c7a`
- `sqldk!SystemThread_TlsIndex` at `0x1018e1d33`
- `sqldk!SystemThread_TlsIndex` at `0x1018e1dec`
- `sqldk!SystemThread_TlsIndex` at `0x1018e22e6`
- `sqldk!SystemThread_TlsIndex` at `0x1018e2393`
- `sqldk!SystemThread_TlsOffset` at `0x100445a62`
- `sqldk!SystemThread_TlsOffset` at `0x1018df7c0`
- `sqldk!SystemThread_TlsOffset` at `0x1018df872`
- `sqldk!SystemThread_TlsOffset` at `0x1018df929`
- `sqldk!SystemThread_TlsOffset` at `0x1018dfb26`
- `sqldk!SystemThread_TlsOffset` at `0x1018dfbcc`
- `sqldk!SystemThread_TlsOffset` at `0x1018dfcfc`
- `sqldk!SystemThread_TlsOffset` at `0x1018dfdae`
- `sqldk!SystemThread_TlsOffset` at `0x1018dfe5f`
- `sqldk!SystemThread_TlsOffset` at `0x1018e004c`
- `sqldk!SystemThread_TlsOffset` at `0x1018e00ec`
- `sqldk!SystemThread_TlsOffset` at `0x1018e0f74`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1026`
- `sqldk!SystemThread_TlsOffset` at `0x1018e10d9`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1399`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1452`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1c83`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1d3c`
- `sqldk!SystemThread_TlsOffset` at `0x1018e1df5`
- `sqldk!SystemThread_TlsOffset` at `0x1018e22ef`
- `sqldk!SystemThread_TlsOffset` at `0x1018e239c`

## string_xrefs

- `0x1018e0abd`: `BUF in PageRef::ComputeLogMode:`
- `0x1018e0a93`: `DBTABLE in PageRef::ComputeLogMode:`
- `0x1018e0834`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018e0998`: `(pXdes != NULL) && !pXdes->IsReadOnly ()`
- `0x1018e0884`: `!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PageRef::ModifyRow(
        BUF **a1,
        __int64 a2,
        struct AllocUnitId *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        unsigned int a9,
        int a10,
        XDES *a11,
        __int64 a12,
        unsigned int a13,
        void *a14,
        int a15,
        int a16,
        __int64 *a17,
        struct RecVersioningInfo *a18)
{
  struct AllocUnitId *v18; // r14
  int v20; // edi
  __int64 v21; // r12
  unsigned int v22; // esi
  char v23; // al
  int v24; // edx
  __int64 v25; // rax
  BUF *v26; // r11
  Page *v27; // r13
  const void ***v28; // rsi
  XDES *v29; // rsi
  int v30; // r14d
  char v31; // al
  int v32; // r8d
  unsigned int v33; // r9d
  unsigned int v34; // ebx
  int v35; // esi
  int PFSFreeSpaceAfterModify; // r12d
  struct XdesId *v37; // rax
  __int64 result; // rax
  XDES *v39; // rbx
  int v40; // ebx
  unsigned __int16 v41; // si
  const void ***v42; // r14
  const void **v43; // r8
  __int16 v44; // bx
  bool v45; // bl
  unsigned __int16 v46; // ax
  __int64 v47; // r15
  __int64 v48; // rdx
  unsigned __int16 v49; // ax
  struct CSessionTraceFlags *v50; // rcx
  unsigned int v51; // ebx
  unsigned __int16 v52; // r12
  XDES *v53; // rsi
  unsigned __int16 *v54; // r13
  Page *v55; // rbx
  char *v56; // rcx
  BUF **v57; // r15
  bool v58; // zf
  unsigned int v59; // eax
  unsigned __int16 v60; // cx
  unsigned __int16 v61; // ax
  unsigned __int16 v62; // r8
  unsigned __int16 v63; // ax
  XDES *v64; // r14
  unsigned int v65; // ecx
  __int64 v66; // rax
  _WORD *v67; // rcx
  int v68; // r8d
  __int64 v69; // rcx
  _WORD *v70; // rdx
  unsigned int v71; // eax
  unsigned int v72; // r9d
  char *v73; // r8
  unsigned int v74; // ebx
  unsigned __int16 v75; // r10
  unsigned int v76; // ecx
  __int16 v77; // ax
  __int64 v78; // rax
  unsigned __int64 v79; // rdx
  BUF *v80; // r11
  __int64 v81; // rax
  __int64 v82; // r11
  __int64 v83; // rcx
  RecoveryUnit *v84; // rcx
  __int64 v85; // r11
  __int64 v86; // rax
  __int64 v87; // r11
  __int64 v88; // r11
  char v89; // al
  unsigned __int16 v90; // r14
  BUF *v91; // r11
  __int64 v92; // rcx
  __int64 FCB; // rsi
  BUF *v94; // rbx
  __int64 v95; // rax
  BUF *v96; // r11
  unsigned int v97; // eax
  unsigned int v98; // eax
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rax
  __int64 v102; // r11
  __int64 v103; // r8
  unsigned int v104; // ecx
  __int64 v105; // rcx
  __int64 v106; // r11
  __int64 v107; // r11
  char v108; // al
  unsigned __int16 v109; // bx
  __int64 v110; // rax
  __int64 v111; // r11
  __int64 v112; // rcx
  unsigned int v113; // eax
  struct RecoveryUnit *v114; // rcx
  __int64 v115; // r11
  unsigned int v116; // r10d
  char *v117; // r8
  unsigned int v118; // ebx
  char v119; // dl
  unsigned __int16 v120; // cx
  __int16 v121; // ax
  __int16 v122; // r8
  unsigned __int16 *v123; // rsi
  unsigned __int16 v124; // dx
  __int64 v125; // rax
  __int64 v126; // rax
  unsigned int v127; // r9d
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  _BYTE *v132; // rax
  unsigned int v133; // ebx
  unsigned __int16 v134; // r8
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v136; // r9
  __int64 v137; // rdx
  int v138; // r8d
  __int16 v139; // ax
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  char v144; // cl
  __int64 v145; // rax
  __int64 v146; // rbx
  __int64 v147; // rdx
  char *v148; // r8
  char v149; // al
  unsigned __int16 *v150; // r14
  unsigned __int16 v151; // cx
  __int64 v152; // rax
  __int64 v153; // rax
  unsigned int v154; // r8d
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // r8
  __int64 v160; // rax
  unsigned int v161; // esi
  unsigned int v162; // edx
  unsigned int v163; // eax
  unsigned __int16 v164; // cx
  unsigned __int16 v165; // ax
  struct RecVersioningInfo *v166; // rax
  __int64 v167; // r9
  __int64 v168; // rdx
  int v169; // r8d
  __int16 v170; // ax
  unsigned __int64 v171; // r8
  int v172; // ecx
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  char v177; // cl
  __int16 v178; // cx
  __int16 v179; // dx
  int v180; // ecx
  __int64 v181; // r8
  __int16 v182; // dx
  unsigned int v183; // ecx
  _BYTE *v184; // rax
  __int64 v185; // rax
  __int64 v186; // r11
  __int64 v187; // r14
  __int16 v188; // bx
  _WORD *v189; // rcx
  unsigned __int16 v190; // dx
  unsigned __int16 v191; // cx
  __int16 v192; // ax
  XDES *v193; // rcx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v195; // rax
  struct CDumpStream *v196; // rbx
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v198; // r9
  BOOL v199; // esi
  char v200; // bl
  struct DbccThreadContext *Context; // rax
  struct DbccThreadContext *v202; // rax
  struct DbccThreadContext *v203; // rax
  struct DbccThreadContext *v204; // rax
  int v205; // eax
  unsigned __int8 v206; // dl
  unsigned __int8 v207; // cl
  char v208; // dl
  unsigned __int16 v209; // cx
  __int16 v210; // ax
  __int16 v211; // r8
  unsigned __int16 *v212; // rsi
  unsigned __int16 v213; // dx
  __int64 v214; // rax
  __int64 v215; // rax
  unsigned int v216; // r10d
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
  void *v236; // rsp
  unsigned __int8 *v237; // rsi
  char v238; // al
  __int16 v239; // r11
  __int64 v240; // rdx
  __int64 v241; // rcx
  __int64 v242; // r14
  unsigned __int8 *v243; // r8
  unsigned __int8 v244; // dl
  __int16 v245; // dx
  unsigned __int16 v246; // cx
  unsigned __int8 *v247; // rax
  __int16 v248; // cx
  int v249; // ebx
  Page *v250; // rsi
  unsigned __int16 *v251; // r8
  char v252; // dl
  int v253; // eax
  int v254; // ecx
  int v255; // ebx
  unsigned __int16 v256; // cx
  __int16 v257; // r8
  unsigned int v258; // edx
  PageComprInfoCache **v259; // r8
  PageComprInfoCache **v260; // r9
  rsize_t v261; // r15
  char *v262; // r14
  _WORD *v263; // rsi
  __int64 v264; // rax
  __int64 v265; // rax
  unsigned int v266; // r8d
  __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rax
  __int64 v270; // rax
  char *v271; // rax
  unsigned int v272; // ebx
  unsigned __int16 v273; // r9
  char *v274; // r9
  __int16 v275; // ax
  __int16 v276; // cx
  struct RecVersioningInfo *v277; // rax
  __int64 v278; // r9
  __int64 v279; // rdx
  int v280; // r8d
  __int16 v281; // ax
  __int64 v282; // rax
  __int64 v283; // rax
  __int64 v284; // rax
  __int64 v285; // rax
  char v286; // cl
  unsigned int v287; // ecx
  char *v288; // r8
  int v289; // ecx
  unsigned int v290; // eax
  unsigned int v291; // ecx
  PageComprInfoCache **v292; // r15
  int v293; // ebx
  __int64 v294; // r8
  char *v295; // r8
  unsigned __int8 v296; // dl
  unsigned __int8 *v297; // rsi
  char v298; // al
  __int16 v299; // r11
  __int64 v300; // rdx
  __int64 v301; // rcx
  __int64 v302; // r14
  unsigned __int8 *v303; // r8
  unsigned __int8 v304; // dl
  __int16 v305; // dx
  unsigned __int16 v306; // cx
  unsigned __int8 *v307; // rax
  __int16 v308; // cx
  int v309; // eax
  int v310; // ecx
  int v311; // ebx
  unsigned __int16 v312; // cx
  __int16 v313; // ax
  unsigned int v314; // ecx
  unsigned int v315; // ecx
  unsigned __int16 v316; // ax
  _WORD *v317; // rcx
  struct RecVersioningInfo *v318; // rdx
  const struct RecoveryUnit *v319; // rcx
  __int64 v320; // r11
  char v321; // al
  __int16 v322; // r11
  __int64 v323; // xmm1_8
  DirtyPageMgr **v324; // rcx
  const void **v325; // rdx
  __int64 v326; // r11
  __int16 v327; // r8
  __int64 v328; // r10
  __int64 v329; // rcx
  _WORD *v330; // rdx
  char v331; // [rsp+30h] [rbp-1FA0h] BYREF
  rsize_t SourceSize; // [rsp+1FA0h] [rbp-30h]
  unsigned __int16 v333[2]; // [rsp+1FD0h] [rbp+0h] BYREF
  unsigned int v334; // [rsp+1FD4h] [rbp+4h]
  unsigned int v335; // [rsp+1FD8h] [rbp+8h]
  unsigned int v336; // [rsp+1FDCh] [rbp+Ch]
  unsigned int v337; // [rsp+1FE0h] [rbp+10h]
  unsigned int v338; // [rsp+1FE4h] [rbp+14h]
  XDES *v339; // [rsp+1FE8h] [rbp+18h]
  __int16 v340; // [rsp+1FF0h] [rbp+20h]
  unsigned __int16 v341; // [rsp+1FF2h] [rbp+22h] BYREF
  int v342; // [rsp+1FF4h] [rbp+24h]
  _BYTE *v343; // [rsp+1FF8h] [rbp+28h]
  __int64 v344; // [rsp+2000h] [rbp+30h]
  unsigned int v345; // [rsp+2008h] [rbp+38h]
  unsigned __int16 v346; // [rsp+200Ch] [rbp+3Ch]
  char *v347; // [rsp+200Eh] [rbp+3Eh]
  _BYTE v348[10]; // [rsp+2016h] [rbp+46h]
  int v349; // [rsp+2020h] [rbp+50h]
  __int16 v350; // [rsp+2028h] [rbp+58h]
  unsigned __int16 v351; // [rsp+202Ah] [rbp+5Ah] BYREF
  unsigned int v352; // [rsp+202Ch] [rbp+5Ch]
  _BYTE *v353; // [rsp+2030h] [rbp+60h]
  __int64 v354; // [rsp+2038h] [rbp+68h]
  unsigned int v355; // [rsp+2040h] [rbp+70h]
  unsigned __int16 v356; // [rsp+2044h] [rbp+74h]
  char *v357; // [rsp+2046h] [rbp+76h]
  _TBYTE v358; // [rsp+204Eh] [rbp+7Eh]
  int v359; // [rsp+2058h] [rbp+88h]
  __int16 v360[2]; // [rsp+2060h] [rbp+90h] BYREF
  int v361; // [rsp+2064h] [rbp+94h]
  int v362; // [rsp+2068h] [rbp+98h]
  unsigned int v363; // [rsp+206Ch] [rbp+9Ch]
  unsigned int v364; // [rsp+2070h] [rbp+A0h]
  unsigned int v365; // [rsp+2074h] [rbp+A4h]
  const void ***v366; // [rsp+2078h] [rbp+A8h]
  struct AllocUnitId *v367; // [rsp+2080h] [rbp+B0h] BYREF
  int v368; // [rsp+2088h] [rbp+B8h]
  Page *v369; // [rsp+2090h] [rbp+C0h] BYREF
  unsigned int v370; // [rsp+2098h] [rbp+C8h] BYREF
  __int16 v371; // [rsp+209Ch] [rbp+CCh]
  int v372; // [rsp+20A0h] [rbp+D0h]
  int v373; // [rsp+20A4h] [rbp+D4h]
  unsigned int v374; // [rsp+20A8h] [rbp+D8h] BYREF
  __int16 v375; // [rsp+20ACh] [rbp+DCh]
  __int64 v376; // [rsp+20B0h] [rbp+E0h] BYREF
  CTracePrintStream *v377; // [rsp+20B8h] [rbp+E8h]
  struct RecVersioningInfo *v378; // [rsp+20C0h] [rbp+F0h] BYREF
  __int16 v379; // [rsp+20C8h] [rbp+F8h]
  struct XdesId *v380; // [rsp+20D0h] [rbp+100h]
  int v381; // [rsp+20D8h] [rbp+108h] BYREF
  int v382; // [rsp+20E0h] [rbp+110h] BYREF
  __int16 v383; // [rsp+20E4h] [rbp+114h]
  __int64 v384; // [rsp+20E8h] [rbp+118h] BYREF
  void *v385; // [rsp+20F0h] [rbp+120h]
  __int64 v386; // [rsp+20F8h] [rbp+128h] BYREF
  unsigned __int16 v387; // [rsp+2100h] [rbp+130h]
  __int64 v388; // [rsp+2108h] [rbp+138h] BYREF
  unsigned __int16 v389; // [rsp+2110h] [rbp+140h]
  __int64 v390; // [rsp+2118h] [rbp+148h] BYREF
  __int16 v391; // [rsp+2120h] [rbp+150h]
  __int64 v392; // [rsp+2128h] [rbp+158h] BYREF
  __int16 v393; // [rsp+2130h] [rbp+160h]
  __int64 v394; // [rsp+2138h] [rbp+168h]
  __int64 v395; // [rsp+2140h] [rbp+170h]
  __int64 v396; // [rsp+2148h] [rbp+178h] BYREF
  __int16 v397; // [rsp+2150h] [rbp+180h]
  int v398; // [rsp+2158h] [rbp+188h] BYREF
  __int16 v399; // [rsp+215Ch] [rbp+18Ch]
  int v400; // [rsp+2160h] [rbp+190h] BYREF
  __int16 v401; // [rsp+2164h] [rbp+194h]
  struct XdesId *v402; // [rsp+2168h] [rbp+198h]
  __int64 v403; // [rsp+2170h] [rbp+1A0h]
  _BYTE v404[96]; // [rsp+2180h] [rbp+1B0h] BYREF
  __int64 v405; // [rsp+21E0h] [rbp+210h] BYREF
  __int16 v406; // [rsp+21E8h] [rbp+218h]
  __int16 v407; // [rsp+21F0h] [rbp+220h] BYREF
  unsigned __int16 v408; // [rsp+21F2h] [rbp+222h] BYREF
  int v409; // [rsp+21F4h] [rbp+224h]
  void *Source; // [rsp+21F8h] [rbp+228h]
  PageComprInfoCache **v411; // [rsp+2200h] [rbp+230h]
  _BYTE v412[24]; // [rsp+2208h] [rbp+238h]
  int v413; // [rsp+2220h] [rbp+250h]
  int v414; // [rsp+2224h] [rbp+254h]
  PageComprInfoCache *v415[2]; // [rsp+2228h] [rbp+258h] BYREF
  __int128 v416; // [rsp+2238h] [rbp+268h]
  _OWORD v417[4]; // [rsp+2248h] [rbp+278h] BYREF
  __int128 v418; // [rsp+2288h] [rbp+2B8h]
  __int64 v419; // [rsp+2298h] [rbp+2C8h]
  __int16 v420; // [rsp+22A0h] [rbp+2D0h] BYREF
  unsigned __int16 v421; // [rsp+22A2h] [rbp+2D2h] BYREF
  unsigned int v422; // [rsp+22A4h] [rbp+2D4h]
  char *v423; // [rsp+22A8h] [rbp+2D8h]
  PageComprInfoCache **v424; // [rsp+22B0h] [rbp+2E0h]
  unsigned int v425; // [rsp+22B8h] [rbp+2E8h]
  __int16 v426; // [rsp+22BCh] [rbp+2ECh]
  __int64 v427; // [rsp+22BEh] [rbp+2EEh]
  _TBYTE v428; // [rsp+22C6h] [rbp+2F6h]
  void *Destination; // [rsp+22D8h] [rbp+308h]
  rsize_t DestinationSize; // [rsp+22E0h] [rbp+310h]
  __int16 v431; // [rsp+22E8h] [rbp+318h]
  unsigned __int16 v432; // [rsp+22EAh] [rbp+31Ah] BYREF
  int v433; // [rsp+22ECh] [rbp+31Ch]
  unsigned __int8 *v434; // [rsp+22F0h] [rbp+320h]
  PageComprInfoCache **v435; // [rsp+22F8h] [rbp+328h]
  _BYTE v436[24]; // [rsp+2300h] [rbp+330h]
  int v437; // [rsp+2318h] [rbp+348h]
  unsigned int v438; // [rsp+231Ch] [rbp+34Ch]
  PageComprInfoCache *v439[2]; // [rsp+2320h] [rbp+350h] BYREF
  __int128 v440; // [rsp+2330h] [rbp+360h]
  __int64 v441; // [rsp+2340h] [rbp+370h]
  _BYTE v442[14]; // [rsp+2348h] [rbp+378h] BYREF
  _TBYTE v443; // [rsp+2356h] [rbp+386h]
  _OWORD v444[2]; // [rsp+2360h] [rbp+390h] BYREF
  __int128 v445; // [rsp+2380h] [rbp+3B0h]
  __int64 v446; // [rsp+2390h] [rbp+3C0h]
  Page *v447; // [rsp+2398h] [rbp+3C8h] BYREF
  unsigned int v448; // [rsp+23A0h] [rbp+3D0h]
  __int16 v449; // [rsp+23A4h] [rbp+3D4h]
  _BYTE v450[2]; // [rsp+23A8h] [rbp+3D8h] BYREF
  __int16 v451; // [rsp+23AAh] [rbp+3DAh]
  int v452; // [rsp+23B8h] [rbp+3E8h]
  __int16 v453; // [rsp+23BCh] [rbp+3ECh]
  char v454; // [rsp+23BEh] [rbp+3EEh]
  char v455; // [rsp+23BFh] [rbp+3EFh]
  __int64 v456; // [rsp+23D8h] [rbp+408h]
  __int16 v457; // [rsp+23E0h] [rbp+410h]
  __int16 v458; // [rsp+23E2h] [rbp+412h]
  unsigned __int16 v459; // [rsp+23E4h] [rbp+414h]
  unsigned __int16 v460; // [rsp+23E6h] [rbp+416h]
  _WORD v461[68]; // [rsp+23E8h] [rbp+418h] BYREF
  _BYTE v462[528]; // [rsp+2470h] [rbp+4A0h] BYREF
  _BYTE v463[528]; // [rsp+2680h] [rbp+6B0h] BYREF
  unsigned int v464; // [rsp+2890h] [rbp+8C0h] BYREF
  unsigned int v465; // [rsp+2894h] [rbp+8C4h]
  unsigned int v466; // [rsp+2898h] [rbp+8C8h]
  int v467; // [rsp+289Ch] [rbp+8CCh]
  void *v468[8]; // [rsp+28B0h] [rbp+8E0h] BYREF

  v403 = -2;
  v337 = a4;
  v18 = a3;
  v367 = a3;
  v384 = a2;
  v366 = (const void ***)a1;
  v363 = a5;
  v385 = a8;
  v339 = a11;
  v378 = a18;
  v20 = 0;
  v360[0] = 0;
  v335 = 1;
  v380 = 0;
  v382 = 0;
  v383 = 0;
  v402 = 0;
  v376 = 0;
  v333[0] = 0;
  v338 = 0;
  v394 = 0;
  v447 = 0;
  v448 = 0;
  v449 = 0;
  v395 = 0;
  v21 = 0;
  v365 = 0;
  v22 = a13;
  if ( a11 )
  {
    v21 = *((_QWORD *)a11 + 6);
    v23 = (**(__int64 (__fastcall ***)(XDES *))a11)(a11);
    v24 = (a13 >> 21) & 2;
    if ( v23 )
      v24 = 1;
    v365 = v24;
  }
  v368 = 2;
  if ( !a16 )
  {
    v78 = BPool::PrepareToDirty(qword_10317B628, *a1, 1, 0);
    *(_WORD *)(v78 + 4) &= 0xEDFFu;
    *(_DWORD *)(v78 + 64) = 1;
    v80 = *a1;
    if ( *((_WORD *)*a1 + 22) == 2 )
      goto LABEL_169;
    v81 = *((_QWORD *)v80 + 18);
    if ( !v81 )
    {
      BUF::FixupPru(*a1);
      v81 = *(_QWORD *)(v82 + 144);
      v80 = *a1;
    }
    v83 = *(_QWORD *)(v81 + 1712);
    if ( (*(_BYTE *)(v83 + 60) & 1) != 0 && !*(_QWORD *)(v83 + 640) )
    {
      v84 = (RecoveryUnit *)*((_QWORD *)v80 + 18);
      if ( !v84 )
      {
        BUF::FixupPru(v80);
        v84 = *(RecoveryUnit **)(v85 + 144);
      }
      if ( !RecoveryUnit::IsBackupAllowedOnRbIoDb(v84) )
        goto LABEL_169;
    }
    v86 = *((_QWORD *)*a1 + 18);
    if ( !v86 )
    {
      BUF::FixupPru(*a1);
      v86 = *(_QWORD *)(v87 + 144);
    }
    if ( (*(_BYTE *)(v86 + 7376) & 0x20) != 0 )
    {
LABEL_169:
      v107 = *(_QWORD *)*a1;
      if ( (*(_WORD *)(v107 + 4) & 0x2000) == 0 )
        goto LABEL_6;
      if ( !*(_WORD *)(v107 + 36) )
        goto LABEL_195;
      v108 = *(_BYTE *)(v107 + 1);
      if ( v108 == 11 )
      {
        if ( *(_DWORD *)(v107 + 24) == 99 )
        {
LABEL_173:
          v398 = *(_DWORD *)(v107 + 32);
          v399 = *(_WORD *)(v107 + 36);
          if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v398, v79) )
          {
            PageHeader::GetIcxLsn(v107, &v388);
            v109 = v389;
LABEL_175:
            v110 = *((_QWORD *)*a1 + 18);
            if ( !v110 )
            {
              BUF::FixupPru(*a1);
              v110 = *(_QWORD *)(v111 + 144);
            }
            v112 = *(_QWORD *)(*(_QWORD *)(v110 + 1712) + 704LL);
            if ( (*(_WORD *)(v112 + 10) != 2 || (_DWORD)v388) && (unsigned int)v388 <= *(_DWORD *)v112 )
            {
              if ( (_DWORD)v388 != *(_DWORD *)v112
                || (v113 = *(_DWORD *)(v112 + 4), HIDWORD(v388) <= v113)
                && (HIDWORD(v388) != v113 || v109 <= *(_WORD *)(v112 + 8)) )
              {
                PageRef::RemoveOldVersionInfo((PageRef *)a1, v79, v18);
              }
            }
            goto LABEL_6;
          }
LABEL_195:
          v388 = *(_QWORD *)(v107 + 40);
          v109 = *(_WORD *)(v107 + 48);
          v389 = v109;
          goto LABEL_175;
        }
      }
      else if ( v108 == 8 )
      {
LABEL_194:
        if ( *(_DWORD *)(v107 + 24) != 99 )
          goto LABEL_195;
        goto LABEL_173;
      }
      if ( v108 != 9 )
        goto LABEL_195;
      goto LABEL_194;
    }
    v88 = *(_QWORD *)*a1;
    if ( !*(_WORD *)(v88 + 36) )
      goto LABEL_188;
    v89 = *(_BYTE *)(v88 + 1);
    if ( v89 == 11 )
    {
      if ( *(_DWORD *)(v88 + 24) == 99 )
      {
LABEL_145:
        v400 = *(_DWORD *)(v88 + 32);
        v401 = *(_WORD *)(v88 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v400, v79) )
        {
          PageHeader::GetIcxLsn(v88, &v386);
          v90 = v387;
LABEL_147:
          v91 = *a1;
          v92 = *((_QWORD *)*a1 + 18);
          if ( !v92 )
          {
            BUF::FixupPru(*a1);
            v92 = *((_QWORD *)v91 + 18);
          }
          FCB = FileMgr::GetFCB(*(_QWORD *)(v92 + 1696), *((unsigned __int16 *)v91 + 58), 0);
          v94 = *a1;
          v95 = *((_QWORD *)*a1 + 18);
          v96 = *a1;
          if ( !v95 )
          {
            BUF::FixupPru(*a1);
            v95 = *((_QWORD *)v94 + 18);
            v94 = *a1;
            v96 = *a1;
          }
          if ( !*(_DWORD *)(*(_QWORD *)(v95 + 1960) + 88LL) )
          {
            v97 = *(_DWORD *)(FCB + 304);
            if ( v97 <= (unsigned int)v386 )
            {
              if ( v97 != (_DWORD)v386 )
                goto LABEL_161;
              v98 = *(_DWORD *)(FCB + 308);
              if ( v98 <= HIDWORD(v386) && (v98 != HIDWORD(v386) || *(_WORD *)(FCB + 312) <= v90) )
                goto LABEL_161;
            }
          }
          v99 = *((_QWORD *)v94 + 18);
          if ( !v99 )
          {
            BUF::FixupPru(v94);
            v99 = *((_QWORD *)v94 + 18);
            v96 = *a1;
          }
          v100 = *(_QWORD *)(v99 + 1712);
          if ( (*(_BYTE *)(v100 + 60) & 1) == 0 || *(_QWORD *)(v100 + 640) )
          {
            v114 = (struct RecoveryUnit *)*((_QWORD *)v96 + 18);
            if ( !v114 )
            {
              BUF::FixupPru(v96);
              v114 = *(struct RecoveryUnit **)(v115 + 144);
              v96 = *a1;
            }
            PageRef::SetDiffMapChangeBit(v114, (const struct PageId *)(*(_QWORD *)v96 + 32LL));
          }
          else
          {
LABEL_161:
            v101 = *((_QWORD *)v96 + 18);
            if ( !v101 )
            {
              BUF::FixupPru(v96);
              v101 = *(_QWORD *)(v102 + 144);
              v96 = *a1;
            }
            v103 = *(_QWORD *)v96;
            if ( *(_DWORD *)(*(_QWORD *)(v101 + 1960) + 272LL) )
            {
              v104 = *(_DWORD *)(v103 + 32) & 0xFFFFFFF8;
              v79 = v104 / 0x7CD00;
              if ( v104 != 511232 * (_DWORD)v79 )
              {
                v105 = *((_QWORD *)v96 + 18);
                if ( !v105 )
                {
                  BUF::FixupPru(v96);
                  v105 = *(_QWORD *)(v106 + 144);
                  v103 = *(_QWORD *)*a1;
                }
                BackupManager::MarkExtentInBackupBitmapList(
                  *(BackupManager **)(v105 + 1960),
                  (const struct PageId *)(v103 + 32));
              }
            }
          }
          v18 = v367;
          v22 = a13;
          goto LABEL_169;
        }
LABEL_188:
        v386 = *(_QWORD *)(v88 + 40);
        v90 = *(_WORD *)(v88 + 48);
        v387 = v90;
        goto LABEL_147;
      }
    }
    else if ( v89 == 8 )
    {
LABEL_187:
      if ( *(_DWORD *)(v88 + 24) != 99 )
        goto LABEL_188;
      goto LABEL_145;
    }
    if ( v89 != 9 )
      goto LABEL_188;
    goto LABEL_187;
  }
LABEL_6:
  v25 = BPool::PrepareToDirty(qword_10317B628, *a1, 1, 0);
  *(_WORD *)(v25 + 4) &= 0xEDFFu;
  *(_DWORD *)(v25 + 64) = 1;
  v26 = *a1;
  v27 = *(Page **)*a1;
  v369 = v27;
  v370 = a7;
  v374 = a6;
  v373 = v22 & 0x20000;
  if ( (v22 & 0x20000) == 0 )
  {
    v334 = a6;
    v336 = a7;
    v28 = v366;
    goto LABEL_8;
  }
  v116 = 0;
  v334 = 0;
  v352 = 0;
  v357 = 0;
  *(_QWORD *)((char *)&v358 + 2) = 0;
  v354 = 0;
  v117 = (char *)v27 + *((unsigned __int16 *)v27 + 4095LL - (int)v337);
  v118 = *((unsigned __int16 *)v27 + 7);
  v58 = (*v117 & 1) == 0;
  v353 = v117;
  if ( v58 )
  {
    v350 = 0;
    LODWORD(v358) = 0;
    switch ( *v117 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v118 = *((unsigned __int16 *)v117 + 1);
        if ( v118 - 1 > 0x1F9D )
        {
          RaiseInconsistencyError(v117, 6);
          goto LABEL_378;
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
LABEL_378:
        v116 = v352;
        v334 = v352;
        break;
      case 4:
        v118 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v118 = 1;
        break;
    }
    LODWORD(v354) = v118;
    v357 = (char *)v27 + 0x2000;
  }
  else
  {
    v350 = 1;
    v119 = *v117;
    switch ( *v117 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( v117[1] < 0 )
        {
          v120 = HIBYTE(*(_WORD *)(v117 + 1)) | ((*(_WORD *)(v117 + 1) & 0x7F) << 8);
          v351 = v120;
          v121 = 3;
          v122 = 3;
        }
        else
        {
          v120 = (unsigned __int8)v117[1];
          v351 = v120;
          v121 = 2;
          v122 = 2;
        }
        LOWORD(v355) = v121;
        v356 = v122 + (((unsigned int)v120 + 1) >> 1);
        if ( v120 > 0x1Eu )
          HIWORD(v355) = (v120 - 1) / 30;
        else
          HIWORD(v355) = 0;
        v359 = 0;
        *(_QWORD *)((char *)&v358 + 2) = (char *)v27 + 0x2000;
        v118 = 0;
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
        v116 = v352;
        goto LABEL_369;
      case 4:
        if ( (v119 & 0x1C) == 4 && (v119 & 2) != 0 )
        {
          v355 = 0;
          v351 = 0;
          v356 = 0;
          LOWORD(v358) = 0;
          v116 = 15;
          v352 = 15;
          v359 = 1;
LABEL_369:
          v334 = v116;
          *(_QWORD *)((char *)&v358 + 2) = (char *)v27 + 0x2000;
          v118 = 0;
        }
        else
        {
          v355 = 0;
          v351 = 0;
          v356 = 0;
          LOWORD(v358) = 0;
          v116 = 1;
          v334 = 1;
          v352 = 1;
          v359 = 0;
          *(_QWORD *)((char *)&v358 + 2) = (char *)v27 + 0x2000;
          v118 = 0;
        }
        break;
      case 8:
        v355 = 0;
        v351 = 0;
        v356 = 0;
        LOWORD(v358) = 0;
        v116 = 9;
        v352 = 9;
        v359 = 0;
        goto LABEL_369;
    }
  }
  if ( !v350 )
  {
    if ( !v116 )
    {
      v351 = 0;
      HIDWORD(v354) = v118;
      v116 = v118;
      v334 = v118;
      if ( (*v353 & 0x10) != 0 )
      {
        v116 = (((unsigned int)*(unsigned __int16 *)&v353[v118] + 7) >> 3) + v118 + 2;
        v334 = v116;
        HIDWORD(v354) = v116;
      }
      if ( (*v353 & 0x20) != 0 )
      {
        v123 = (unsigned __int16 *)&v353[v116];
        v124 = *v123;
        v356 = v124;
        if ( !v124 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v125 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v125 )
            {
              v126 = *(_QWORD *)(v125 + 96);
              if ( v126 )
              {
                if ( *(_BYTE *)(v126 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v353, 3);
          v124 = v356;
        }
        v127 = HIDWORD(v354) + 2 + 2 * v124;
        v355 = v127;
        if ( v127 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v128 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v128 )
            {
              v129 = *(_QWORD *)(v128 + 96);
              if ( v129 )
              {
                if ( *(_BYTE *)(v129 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v353, 4);
          v124 = v356;
          v127 = v355;
        }
        v116 = v123[v124] & 0x7FFF;
        v334 = v116;
        v352 = v116;
        if ( v127 > v116 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v130 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v130 )
            {
              v131 = *(_QWORD *)(v130 + 96);
              if ( v131 )
              {
                if ( *(_BYTE *)(v131 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v353, 4);
          v124 = v356;
          v127 = v355;
          v116 = v352;
          v334 = v352;
        }
        while ( (v123[v124] & 0x8000u) != 0 )
        {
          v132 = &v353[HIDWORD(v354)];
          if ( v124 == 1 )
            v133 = v127;
          else
            v133 = *(_WORD *)&v132[2 * v124 - 2] & 0x7FFF;
          if ( v133 < v127 || (*(_WORD *)&v132[2 * v124] & 0x7FFFu) < v133 )
          {
            RaiseInconsistencyError(v353, 7);
            v124 = v356;
            v127 = v355;
            v116 = v352;
            v334 = v352;
          }
          if ( v133 < v127 || v133 > v116 )
            goto LABEL_278;
          v134 = *(_WORD *)&v353[v133];
          if ( v134 == 5 )
          {
            v351 |= 2u;
            v356 = v124 - 1;
            WORD2(v358) = v133;
            v178 = *(_WORD *)&v353[(unsigned __int16)v133 + 2];
            v179 = WORD3(v358) & 0xC7FF;
            if ( (v178 & 0x4000) != 0 )
              v179 = WORD3(v358) ^ (v178 ^ WORD3(v358)) & 0x3800;
            WORD3(v358) = v179 ^ (v178 ^ v179) & 0x7FF;
            break;
          }
          if ( v134 >= 0x400u )
          {
            v351 |= 1u;
            v58 = v124-- == 1;
            v356 = v124;
            if ( !v58 )
              continue;
          }
          break;
        }
      }
      else
      {
        v352 = v116;
        v356 = 0;
        v355 = v116;
      }
      if ( (*v353 & 0x40) != 0 )
      {
        LODWORD(v358) = v116;
        v352 = v116 + 14;
        VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v351);
        v136 = HIDWORD(*(_QWORD *)VersioningInfo);
        v137 = HIWORD(*(_QWORD *)VersioningInfo);
        v138 = 0;
        if ( (((__int16)v137 ^ ((unsigned int)(__int16)v137 >> 1)) & 0x2000) != 0 )
        {
          v139 = v137 & 0xDFFF;
          if ( (v137 & 0x4000) != 0 )
            v139 = v137 | 0x2000;
          LOWORD(v137) = v139;
        }
        if ( (_WORD)v137 == 0xFFFC )
          v138 = (unsigned __int16)v136 >> 5;
        v116 = v138 + v352;
        v334 = v138 + v352;
        v352 += v138;
      }
      else
      {
        LODWORD(v358) = 0;
      }
      if ( v357 && v357 < &v353[v116] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v140 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v140 )
          {
            v141 = *(_QWORD *)(v140 + 96);
            if ( v141 )
            {
              if ( *(_BYTE *)(v141 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v353, 18);
        v116 = v352;
        v334 = v352;
      }
      if ( v116 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v142 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v142 )
          {
            v143 = *(_QWORD *)(v142 + 96);
            if ( v143 )
            {
              if ( *(_BYTE *)(v143 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v353, 5);
        v116 = v352;
        v334 = v352;
      }
    }
LABEL_278:
    if ( v116 >= 9 )
      goto LABEL_282;
    v144 = *v353 & 0xE;
    if ( v144 )
    {
      if ( v144 != 12 )
        goto LABEL_282;
    }
    goto LABEL_281;
  }
  if ( !v116 )
  {
    CDRecord::Resize((CDRecord *)&v351);
    v116 = v352;
  }
  if ( v116 >= 9 )
  {
LABEL_399:
    v334 = v116;
    goto LABEL_282;
  }
  v180 = *v353 & 0x1C;
  if ( (*v353 & 0x1C) != 0 )
  {
    v334 = 9;
    if ( v180 == 12 )
      goto LABEL_282;
    goto LABEL_399;
  }
LABEL_281:
  v334 = 9;
LABEL_282:
  if ( *((char *)v27 + 2) < 0 )
    v145 = a17[1];
  else
    v145 = *a17;
  v395 = v145;
  v146 = v145 + 2;
  if ( *(_WORD *)v145 )
  {
    v183 = *(_DWORD *)(v145 + 4);
    v336 = v183;
    if ( !v183 )
    {
      CDRecord::Resize((CDRecord *)(v145 + 2));
      v183 = *(_DWORD *)(v146 + 2);
      v336 = v183;
    }
    if ( v183 < 9 )
    {
      v184 = *(_BYTE **)(v146 + 6);
      if ( (*v184 & 0x1C) == 0 || (*v184 & 0x1C) == 0xC )
        v336 = 9;
    }
    v28 = v366;
    v26 = (BUF *)*v366;
    goto LABEL_8;
  }
  if ( *(_DWORD *)(v145 + 4) )
    goto LABEL_361;
  *(_WORD *)v146 = 0;
  v147 = *(unsigned int *)(v145 + 16);
  *(_DWORD *)(v145 + 20) = v147;
  v148 = *(char **)(v145 + 8);
  v149 = *v148;
  if ( (*v148 & 0x10) != 0 )
  {
    LODWORD(v147) = (((unsigned int)*(unsigned __int16 *)&v148[v147] + 7) >> 3) + v147 + 2;
    *(_DWORD *)(v146 + 18) = v147;
    v149 = *v148;
  }
  if ( (v149 & 0x20) == 0 )
  {
    *(_DWORD *)(v146 + 2) = v147;
    *(_WORD *)(v146 + 26) = 0;
    *(_DWORD *)(v146 + 22) = v147;
    goto LABEL_332;
  }
  v150 = (unsigned __int16 *)&v148[(unsigned int)v147];
  v151 = *v150;
  *(_WORD *)(v146 + 26) = *v150;
  if ( !v151 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v152 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v152 )
      {
        v153 = *(_QWORD *)(v152 + 96);
        if ( v153 )
        {
          if ( *(_BYTE *)(v153 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v146 + 6), 3);
    v151 = *(_WORD *)(v146 + 26);
    LODWORD(v147) = *(_DWORD *)(v146 + 18);
  }
  v154 = v147 + 2 * (v151 + 1);
  *(_DWORD *)(v146 + 22) = v154;
  if ( v154 > 0x1F9E )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v155 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v155 )
      {
        v156 = *(_QWORD *)(v155 + 96);
        if ( v156 )
        {
          if ( *(_BYTE *)(v156 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v146 + 6), 4);
    v151 = *(_WORD *)(v146 + 26);
    v154 = *(_DWORD *)(v146 + 22);
  }
  LODWORD(v147) = v150[v151] & 0x7FFF;
  *(_DWORD *)(v146 + 2) = v147;
  if ( v154 > (unsigned int)v147 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v157 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v157 )
      {
        v158 = *(_QWORD *)(v157 + 96);
        if ( v158 )
        {
          if ( *(_BYTE *)(v158 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v146 + 6), 4);
    v151 = *(_WORD *)(v146 + 26);
    LODWORD(v147) = *(_DWORD *)(v146 + 2);
  }
  if ( (v150[v151] & 0x8000u) == 0 )
  {
LABEL_331:
    v148 = *(char **)(v146 + 6);
    goto LABEL_332;
  }
  v159 = *(_QWORD *)(v146 + 6);
  while ( 1 )
  {
    v160 = v159 + *(unsigned int *)(v146 + 18);
    if ( v151 == 1 )
    {
      v161 = *(_DWORD *)(v146 + 22);
      v162 = v161;
      v163 = *(_WORD *)(v160 + 2LL * v151) & 0x7FFF;
    }
    else
    {
      v161 = *(_WORD *)(v160 + 2LL * v151 - 2) & 0x7FFF;
      v162 = *(_DWORD *)(v146 + 22);
      v163 = *(_WORD *)(v160 + 2LL * v151) & 0x7FFF;
      if ( v161 < v162 )
      {
LABEL_324:
        RaiseInconsistencyError(v159, 7);
        v162 = *(_DWORD *)(v146 + 22);
        goto LABEL_325;
      }
    }
    if ( v163 < v161 )
      goto LABEL_324;
LABEL_325:
    if ( v161 < v162 )
      goto LABEL_361;
    LODWORD(v147) = *(_DWORD *)(v146 + 2);
    if ( v161 > (unsigned int)v147 )
      goto LABEL_361;
    v159 = *(_QWORD *)(v146 + 6);
    v164 = *(_WORD *)(v161 + v159);
    if ( v164 == 5 )
      break;
    if ( v164 >= 0x400u )
    {
      *(_WORD *)v146 |= 1u;
      v165 = *(_WORD *)(v146 + 26) - 1;
      *(_WORD *)(v146 + 26) = v165;
      if ( v165 )
      {
        v151 = v165;
        if ( (v150[v165] & 0x8000u) != 0 )
          continue;
      }
    }
    goto LABEL_331;
  }
  *(_WORD *)v146 |= 2u;
  --*(_WORD *)(v146 + 26);
  *(_WORD *)(v146 + 40) = v161;
  v181 = *(_QWORD *)(v146 + 6) + (unsigned __int16)v161;
  v182 = *(_WORD *)(v146 + 42) & 0xC7FF;
  if ( (*(_WORD *)(v181 + 2) & 0x4000) != 0 )
    v182 |= *(_WORD *)(v181 + 2) & 0x3800;
  *(_WORD *)(v146 + 42) = v182;
  *(_WORD *)(v146 + 42) = v182 ^ (*(_WORD *)(v181 + 2) ^ v182) & 0x7FF;
  LODWORD(v147) = *(_DWORD *)(v146 + 2);
  v148 = *(char **)(v146 + 6);
LABEL_332:
  if ( (*v148 & 0x40) != 0 )
  {
    *(_DWORD *)(v146 + 36) = v147;
    *(_DWORD *)(v146 + 2) = v147 + 14;
    v166 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v146);
    v167 = HIDWORD(*(_QWORD *)v166);
    v168 = HIWORD(*(_QWORD *)v166);
    v169 = 0;
    if ( (((__int16)v168 ^ ((unsigned int)(__int16)v168 >> 1)) & 0x2000) != 0 )
    {
      v170 = v168 & 0xDFFF;
      if ( (v168 & 0x4000) != 0 )
        v170 = v168 | 0x2000;
      LOWORD(v168) = v170;
    }
    if ( (_WORD)v168 == 0xFFFC )
      v169 = (unsigned __int16)v167 >> 5;
    *(_DWORD *)(v146 + 2) += v169;
    LODWORD(v147) = *(_DWORD *)(v146 + 2);
  }
  else
  {
    *(_DWORD *)(v146 + 36) = 0;
  }
  v171 = *(_QWORD *)(v146 + 28);
  v172 = v147;
  if ( v171 && v171 < *(_QWORD *)(v146 + 6) + (unsigned __int64)(unsigned int)v147 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v173 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v173 )
      {
        v174 = *(_QWORD *)(v173 + 96);
        if ( v174 )
        {
          if ( *(_BYTE *)(v174 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v146 + 6), 18);
    v172 = *(_DWORD *)(v146 + 2);
  }
  if ( (unsigned int)(v172 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v175 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v175 )
      {
        v176 = *(_QWORD *)(v175 + 96);
        if ( v176 )
        {
          if ( *(_BYTE *)(v176 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            else
              ex_raise(34, 68, 21, 1005);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v146 + 6), 5);
  }
LABEL_361:
  v336 = *(_DWORD *)(v146 + 2);
  if ( v336 < 9 )
  {
    v177 = **(_BYTE **)(v146 + 6) & 0xE;
    if ( !v177 || v177 == 12 )
      v336 = 9;
  }
  v28 = v366;
  v26 = (BUF *)*v366;
LABEL_8:
  v376 = *(_QWORD *)v367;
  if ( (a9 & 0x400000) == 0 )
  {
    if ( (*((_DWORD *)v26 + 25) & 0x80000) != 0 && (unsigned __int8)(*((_BYTE *)**v28 + 1) - 3) > 1u )
      utassert_fail(
        1u,
        "IS_OFF (BUF_MINLOGGED, m_buf->bstat) || pageModifyType != PageModifyType_Contents || GetPagePtr ()->IsTextPage ()",
        "pageref.cpp",
        2525,
        0);
    goto LABEL_10;
  }
  v185 = *((_QWORD *)v26 + 18);
  if ( !v185 )
  {
    BUF::FixupPru(v26);
    v185 = *(_QWORD *)(v186 + 144);
  }
  v187 = *(_QWORD *)(v185 + 1712);
  v188 = *(_WORD *)(v187 + 40);
  if ( v188 == 2 )
  {
    v189 = **v28;
    v190 = v189[3];
    if ( (*((_DWORD *)v189 + 6) & 0xE0000000) == 0x80000000 && v190 <= 0xFFu )
    {
LABEL_427:
      v30 = 2;
      v29 = v339;
      goto LABEL_12;
    }
    if ( *((_DWORD *)v189 + 6) == x_SYSALLOCPGAllocationUnitId )
    {
      v191 = 0;
      if ( v190 != 1 )
        v191 = v190;
      v192 = *(&x_SYSALLOCPGAllocationUnitId + 2);
      if ( *(&x_SYSALLOCPGAllocationUnitId + 2) == 1 )
        v192 = 0;
      if ( v191 == v192 )
      {
        v30 = 2;
        v29 = v339;
        goto LABEL_12;
      }
    }
    v193 = v339;
    if ( !v339 || (*((_BYTE *)v339 + 536) & 1) == 0 )
    {
      v30 = 2;
      v29 = v339;
      goto LABEL_12;
    }
  }
  else
  {
    v193 = v339;
  }
  if ( (*((_DWORD *)*v28 + 25) & 0x80000) == 0 )
  {
    if ( (*(_BYTE *)(v187 + 632) & 0xC) != 0 )
    {
      if ( (*((_DWORD *)*v28 + 25) & 0x80000) != 0 )
        goto LABEL_427;
      if ( !v193 || (*((_BYTE *)v193 + 536) & 1) == 0 )
        utassert_fail(1u, "(pXdes != NULL) && !pXdes->IsReadOnly ()", "pageref.cpp", 2392, 0);
      if ( (*((_BYTE *)**v28 + 4) & 0x20) != 0 && (*((_DWORD *)*v28 + 25) & 2) != 0 && v188 != 2 )
      {
        utassert_fail(
          1u,
          "!m_buf->bpage->IsFlag(PageHeader::ALLOC_NONLOGGED) || IS_OFF (BUF_DIRTY, m_buf->bstat) || (dbid == TEMPDBID)",
          "pageref.cpp",
          2410,
          0);
        v29 = v339;
      }
      else
      {
LABEL_10:
        v29 = v339;
      }
      goto LABEL_11;
    }
    if ( v193 && (*((_BYTE *)v193 + 536) & 1) != 0 )
    {
      v29 = v339;
LABEL_463:
      if ( (*((_DWORD *)*v366 + 25) & 0x80000) != 0 && (unsigned __int8)(*((_BYTE *)**v366 + 1) - 3) > 1u )
        utassert_fail(
          1u,
          "IS_OFF (BUF_MINLOGGED, m_buf->bstat) || pageModifyType != PageModifyType_Contents || GetPagePtr ()->IsTextPage ()",
          "pageref.cpp",
          2488,
          0);
LABEL_11:
      v30 = 0;
      goto LABEL_12;
    }
    CDStream::CDStream((CDStream *)v404);
    CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v462);
    CAutoStreamHeader::CAutoStreamHeader((CAutoStreamHeader *)v463);
    ProcessHeap = GetProcessHeap();
    v195 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
    v377 = v195;
    if ( v195 )
      v196 = CTracePrintStream::CTracePrintStream(v195, 0);
    else
      v196 = 0;
    if ( v196 )
    {
      if ( CDStream::AddDevice((CDStream *)v404, v196) )
      {
        v199 = (byte_10317ACB9 & 2) != 0;
        v200 = (unsigned __int8)byte_10317AD42 >> 5;
        Context = UtilDbccGetContext();
        UtilDbccTraceOn(2505, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)Context + 10) + 72LL) + 16LL), 0, 0);
        v202 = UtilDbccGetContext();
        UtilDbccTraceOn(3605, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v202 + 10) + 72LL) + 16LL), 0, 0);
        CAutoStreamHeader::Init(
          (CAutoStreamHeader *)v462,
          (struct CDStream *)v404,
          "DBTABLE in PageRef::ComputeLogMode:");
        DBTABLE::Dump((DBTABLE *)v187, (struct CDStream *)v404);
        CAutoStreamHeader::Init((CAutoStreamHeader *)v463, (struct CDStream *)v404, "BUF in PageRef::ComputeLogMode:");
        BUF::Dump(*v366, (struct CDStream *)v404, 0);
        if ( (v200 & 1) == 0 )
        {
          v203 = UtilDbccGetContext();
          UtilDbccTraceOff(3605, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v203 + 10) + 72LL) + 16LL), 0, 0);
        }
        if ( !v199 )
        {
          v204 = UtilDbccGetContext();
          UtilDbccTraceOff(2505, *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v204 + 10) + 72LL) + 16LL), 0, 0);
        }
        goto LABEL_459;
      }
      (**(void (__fastcall ***)(struct CDumpStream *, __int64))v196)(v196, 1);
    }
    ErrorReportingManager = GetErrorReportingManager();
    LOBYTE(v198) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)ErrorReportingManager + 168LL))(
      ErrorReportingManager,
      L"\nAllocation error of trace stream",
      33,
      v198,
      -1);
LABEL_459:
    v29 = v339;
    if ( !v339 || (*((_BYTE *)v339 + 536) & 1) == 0 )
      utassert_fail(1u, "(pXdes != NULL) && !pXdes->IsReadOnly ()", "pageref.cpp", 2478, 0);
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v463);
    CAutoStreamHeader::~CAutoStreamHeader((CAutoStreamHeader *)v462);
    CDStream::~CDStream((CDStream *)v404);
    goto LABEL_463;
  }
  v30 = 2;
  v29 = v339;
LABEL_12:
  v31 = *((_BYTE *)v27 + 1);
  if ( v31 == 3 )
    goto LABEL_90;
  if ( v31 != 1 || (a9 & 1) != 0 )
  {
    v32 = 2;
    v364 = 2;
    goto LABEL_16;
  }
  if ( (*((_DWORD *)v27 + 6) & 0xE0000000) != 0x80000000 || *((_WORD *)v27 + 3) > 0xFFu )
  {
LABEL_90:
    v32 = 0;
    v364 = 0;
  }
  else
  {
    v32 = 1;
    v364 = 1;
  }
LABEL_16:
  v33 = a13;
  v372 = a13 & 0x10000;
  if ( (a13 & 0x10000) != 0 )
  {
    v205 = (*((unsigned __int8 *)v27 + *((unsigned __int16 *)v27 + 4095LL - (int)v337)) >> 6) & 1;
    if ( (*((_BYTE *)v27 + *((unsigned __int16 *)v27 + 4095LL - (int)v337)) & 1) != 0 )
      v205 = (*((unsigned __int8 *)v27 + *((unsigned __int16 *)v27 + 4095LL - (int)v337)) >> 1) & 1;
    if ( v205 )
    {
      v34 = 2;
      if ( v378 )
        v34 = 0;
      v338 = v34;
    }
    else
    {
      v34 = v338;
      if ( v378 != (struct RecVersioningInfo *)v338 )
        v34 = 1;
      v338 = v34;
    }
  }
  else
  {
    v34 = v338;
  }
  if ( v32 == 2 )
  {
    v35 = (int)v377;
    v362 = (int)v377;
    PFSFreeSpaceAfterModify = v368;
    v361 = v368;
    v37 = 0;
  }
  else
  {
    if ( !v30 )
    {
      if ( !(unsigned int)XDES::IsActive(v29) )
        (*(void (__fastcall **)(XDES *))(*(_QWORD *)v29 + 624LL))(v29);
      v380 = (XDES *)((char *)v29 + 40);
      XdesMgr::GetOldestInterestingXdesId((XdesMgr *)(v21 + 6600), (struct XdesId *)&v382);
      v402 = (struct XdesId *)&v382;
      v33 = a13;
    }
    v68 = 0;
    v69 = *((unsigned __int16 *)v27 + 11) - 1LL;
    if ( v69 >= 0 )
    {
      v70 = (_WORD *)((char *)v27 + 2 * (4095 - v69));
      do
      {
        if ( *v70 )
          break;
        ++v68;
        ++v70;
        --v69;
      }
      while ( v69 >= 0 );
    }
    v35 = *((unsigned __int16 *)v27 + 14) + 2 * v68;
    v362 = v35;
    v71 = 0;
    v335 = 0;
    if ( v365 == 1 )
    {
      if ( (v33 & 0x80000) == 0 )
        v71 = 16;
      v335 = v71;
    }
    if ( v339 && (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v339 + 88LL))(v339) )
      v335 |= 0x80u;
    if ( (*(unsigned int (__fastcall **)(XDES *))(*(_QWORD *)v339 + 616LL))(v339) )
    {
      v335 |= 2u;
      PFSFreeSpaceAfterModify = Page::GetPFSFreeSpaceAfterModify(v27, v334, v336, v34, v337, v35);
      v361 = PFSFreeSpaceAfterModify;
      if ( (*((_DWORD *)v339 + 134) & 5) == 1 && (*((_DWORD *)v339 + 182) & 1) != 0 )
        goto LABEL_501;
      v206 = 0;
      while ( v35 < dword_102830E28[v206] )
      {
        if ( ++v206 >= 4u )
        {
          v206 = 4;
          break;
        }
      }
      v207 = 0;
      while ( PFSFreeSpaceAfterModify < dword_102830E28[v207] )
      {
        if ( ++v207 >= 4u )
        {
          v207 = 4;
          break;
        }
      }
      if ( v206 != v207 && (a13 & 0x400) == 0 )
LABEL_501:
        SetFreeSpaceState(
          *((struct RecoveryUnit **)v339 + 6),
          (const struct AllocationCachesId *)&v376,
          (const struct PageId *)((char *)**v366 + 32),
          PFSFreeSpaceAfterModify,
          v339);
    }
    else
    {
      PFSFreeSpaceAfterModify = v368;
      v361 = v368;
    }
    v37 = v380;
    if ( v380 )
    {
      v72 = 0;
      v342 = 0;
      v347 = 0;
      *(_QWORD *)&v348[2] = 0;
      v344 = 0;
      v73 = (char *)v27 + *((unsigned __int16 *)v27 + 4095LL - (int)v337);
      v74 = *((unsigned __int16 *)v27 + 7);
      v58 = (*v73 & 1) == 0;
      v343 = v73;
      if ( v58 )
      {
        v340 = 0;
        *(_DWORD *)v348 = 0;
        switch ( *v73 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v74 = *((unsigned __int16 *)v73 + 1);
            if ( v74 - 1 > 0x1F9D )
            {
              RaiseInconsistencyError(v73, 6);
              goto LABEL_517;
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
LABEL_517:
            v72 = v342;
            break;
          case 4:
            v74 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v74 = 1;
            break;
        }
        LODWORD(v344) = v74;
        v347 = (char *)v27 + 0x2000;
      }
      else
      {
        v340 = 1;
        v208 = *v73;
        switch ( *v73 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( v73[1] < 0 )
            {
              v209 = HIBYTE(*(_WORD *)(v73 + 1)) | ((*(_WORD *)(v73 + 1) & 0x7F) << 8);
              v341 = v209;
              v210 = 3;
              v211 = 3;
            }
            else
            {
              v209 = (unsigned __int8)v73[1];
              v341 = v209;
              v210 = 2;
              v211 = 2;
            }
            LOWORD(v345) = v210;
            v346 = v211 + (((unsigned int)v209 + 1) >> 1);
            if ( v209 > 0x1Eu )
              HIWORD(v345) = (v209 - 1) / 30;
            else
              HIWORD(v345) = 0;
            v349 = 0;
            *(_QWORD *)&v348[2] = (char *)v27 + 0x2000;
            v74 = 0;
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
            v72 = v342;
            *(_QWORD *)&v348[2] = (char *)v27 + 0x2000;
            v74 = 0;
            break;
          case 4:
            if ( (v208 & 0x1C) == 4 && (v208 & 2) != 0 )
            {
              v345 = 0;
              v341 = 0;
              v346 = 0;
              *(_WORD *)v348 = 0;
              v72 = 15;
              v342 = 15;
              v349 = 1;
              *(_QWORD *)&v348[2] = (char *)v27 + 0x2000;
              v74 = 0;
            }
            else
            {
              v345 = 0;
              v341 = 0;
              v346 = 0;
              *(_WORD *)v348 = 0;
              v72 = 1;
              v342 = 1;
              v349 = 0;
              *(_QWORD *)&v348[2] = (char *)v27 + 0x2000;
              v74 = 0;
            }
            break;
          case 8:
            v345 = 0;
            v341 = 0;
            v346 = 0;
            *(_WORD *)v348 = 0;
            v72 = 9;
            v342 = 9;
            v349 = 0;
            *(_QWORD *)&v348[2] = (char *)v27 + 0x2000;
            v74 = 0;
            break;
        }
      }
      if ( v340 )
      {
        if ( !v72 )
        {
          CDRecord::Resize((CDRecord *)&v341);
          v72 = v342;
        }
        if ( v72 < 9 && ((*v343 & 0x1C) == 0 || (*v343 & 0x1C) == 0xC) )
          LOWORD(v72) = 9;
      }
      else
      {
        if ( !v72 )
        {
          v341 = 0;
          HIDWORD(v344) = v74;
          v72 = v74;
          if ( (*v343 & 0x10) != 0 )
          {
            v72 = (((unsigned int)*(unsigned __int16 *)&v343[v74] + 7) >> 3) + v74 + 2;
            HIDWORD(v344) = v72;
          }
          if ( (*v343 & 0x20) != 0 )
          {
            v212 = (unsigned __int16 *)&v343[v72];
            v213 = *v212;
            v346 = v213;
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
              RaiseInconsistencyError(v343, 3);
              v213 = v346;
            }
            v216 = HIDWORD(v344) + 2 + 2 * v213;
            v345 = v216;
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
              RaiseInconsistencyError(v343, 4);
              v213 = v346;
              v216 = v345;
            }
            v72 = v212[v213] & 0x7FFF;
            v342 = v72;
            if ( v216 > v72 )
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
              RaiseInconsistencyError(v343, 4);
              v213 = v346;
              v216 = v345;
              v72 = v342;
            }
            while ( (v212[v213] & 0x8000u) != 0 )
            {
              v221 = &v343[HIDWORD(v344)];
              if ( v213 == 1 )
                v222 = v216;
              else
                v222 = *(_WORD *)&v221[2 * v213 - 2] & 0x7FFF;
              if ( v222 < v216 || (*(_WORD *)&v221[2 * v213] & 0x7FFFu) < v222 )
              {
                RaiseInconsistencyError(v343, 7);
                v213 = v346;
                v216 = v345;
                v72 = v342;
              }
              if ( v222 < v216 || v222 > v72 )
                goto LABEL_127;
              v223 = *(_WORD *)&v343[v222];
              if ( v223 == 5 )
              {
                v341 |= 2u;
                v346 = v213 - 1;
                *(_WORD *)&v348[4] = v222;
                v224 = *(_WORD *)&v343[(unsigned __int16)v222 + 2];
                v225 = *(_WORD *)&v348[6] & 0xC7FF;
                if ( (v224 & 0x4000) != 0 )
                  v225 = *(_WORD *)&v348[6] ^ (*(_WORD *)&v348[6] ^ v224) & 0x3800;
                *(_WORD *)&v348[6] = v225 ^ (v224 ^ v225) & 0x7FF;
                break;
              }
              if ( v223 >= 0x400u )
              {
                v341 |= 1u;
                v58 = v213-- == 1;
                v346 = v213;
                if ( !v58 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v342 = v72;
            v346 = 0;
            v345 = v72;
          }
          if ( (*v343 & 0x40) != 0 )
          {
            *(_DWORD *)v348 = v72;
            v342 = v72 + 14;
            v226 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v341);
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
            v72 = v229 + v342;
            v342 += v229;
          }
          else
          {
            *(_DWORD *)v348 = 0;
          }
          if ( v347 && v347 < &v343[v72] )
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
            RaiseInconsistencyError(v343, 18);
            v72 = v342;
          }
          if ( v72 - 1 > 0x3F3B )
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
            RaiseInconsistencyError(v343, 5);
            v72 = v342;
          }
        }
LABEL_127:
        if ( v72 < 9 )
        {
          v235 = *v343 & 0xE;
          if ( !v235 || v235 == 12 )
            LOWORD(v72) = 9;
        }
        v35 = v362;
      }
      v75 = ~((1 << (*((_WORD *)v27 + 2) & 2)) - 1);
      v76 = v75 & (v72 + (1 << (*((_WORD *)v27 + 2) & 2)) - 1);
      v77 = v76 + v336 - v334;
      v34 = v338;
      if ( v338 )
      {
        if ( v338 == 1 )
          v77 += 14;
        else
          v77 -= 14;
      }
      Page::ComputeAcquireOrRelease(
        v27,
        v76,
        v75 & (unsigned __int16)(v77 + (1 << (*((_WORD *)v27 + 2) & 2)) - 1),
        v335,
        v380,
        v402,
        v333);
      v37 = v380;
    }
  }
  result = Page::CheckForModifySpace(v27, v337, v334, v336, v34, &v381, v360, v335, v37);
  if ( (_DWORD)result )
    return result;
  v39 = v339;
  if ( v339
    && (*((_DWORD *)v339 + 134) & 5) == 1
    && (*((_DWORD *)v339 + 182) & 1) != 0
    && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v339 + 16LL))(v339)
    && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v39 + 24LL))(v39) )
  {
    if ( v365 == 1 )
      utassert_fail(1u, "pgOpCtxt != OPCTX_IN_LOGICAL_REVERT_TRAN", "pageref.cpp", 5296, 0);
    v333[0] |= 0x100u;
  }
  v40 = a13 & 0x200;
  v338 = v40;
  if ( (a13 & 0x200) != 0 )
    v333[0] |= 0x200u;
  if ( (a13 & 0x800) != 0 )
    v333[0] |= 0x800u;
  if ( v373 )
    v333[0] |= 0x2000u;
  if ( v372 )
    v333[0] |= 0x8000u;
  if ( (a13 & 0x200000) != 0 )
    v333[0] |= 0x4000u;
  if ( v30 == 2 )
  {
    if ( !*((_WORD *)v27 + 18) )
      goto LABEL_889;
    v321 = *((_BYTE *)v27 + 1);
    if ( v321 == 11 )
    {
      if ( *((_DWORD *)v27 + 6) == 99 )
      {
LABEL_881:
        LODWORD(v367) = *((_DWORD *)v27 + 8);
        WORD2(v367) = *((_WORD *)v27 + 18);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v367, a13) )
        {
          PageHeader::GetIcxLsn(v27, &v396);
          v322 = v397;
          v323 = v396;
LABEL_883:
          v405 = v323;
          v406 = v322;
          v57 = (BUF **)v366;
          v324 = (DirtyPageMgr **)(*v366)[18];
          v325 = *v366;
          if ( !v324 )
          {
            BUF::FixupPru((BUF *)*v366);
            v325 = (const void **)*v57;
            v324 = *(DirtyPageMgr ***)(v326 + 144);
          }
          DirtyPageMgr::PreNonLoggedDirty(v324[235], (struct BUF *)v325, 0);
          v64 = v339;
          goto LABEL_66;
        }
LABEL_889:
        v323 = *((_QWORD *)v27 + 5);
        v396 = v323;
        v322 = *((_WORD *)v27 + 24);
        v397 = v322;
        goto LABEL_883;
      }
    }
    else if ( v321 == 8 )
    {
LABEL_888:
      if ( *((_DWORD *)v27 + 6) != 99 )
        goto LABEL_889;
      goto LABEL_881;
    }
    if ( v321 != 9 )
      goto LABEL_889;
    goto LABEL_888;
  }
  v452 = 0;
  v453 = 0;
  v460 = 0;
  v41 = 0;
  v42 = v366;
  v43 = *v366;
  if ( (unsigned __int8)(*((_BYTE *)**v366 + 1) - 3) <= 1u || (a13 & 0x40000) != 0 )
    v41 = a10 != 0 ? 4 : 0;
  v454 = 4;
  v44 = *((_WORD *)v43 + 49);
  v455 = PageLog::MapContext(v27, a9, v43);
  v45 = (v44 & 8) != 0;
  v46 = v41 | 0x400;
  if ( (a13 & 0x1000000) == 0 )
    v46 = v41;
  v47 = (int)v337;
  PageLog::FillPageInfo((PageLog *)v450, v367, v27, v337, v46, v45);
  v456 = v384;
  v49 = v333[0];
  v459 = v333[0];
  v457 = v363;
  if ( (byte_10317AC09 & 0x40) != 0 )
  {
LABEL_44:
    v459 = v49 & 0xFBFF;
    v51 = v374;
    v458 = v374;
  }
  else
  {
    v48 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( *(_QWORD *)v48
      && (v50 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v48 + 56LL)) != 0
      && CSessionTraceFlags::CheckSessionTraceInternal(v50, 0x44Eu)
      || *((_WORD *)*v42 + 22) != 2 )
    {
      v49 = v459;
      goto LABEL_44;
    }
    v459 |= 0x400u;
    v458 = v370;
    v51 = v374;
  }
  v52 = 3;
  v53 = v339;
  if ( v339
    && (!(*(unsigned int (__fastcall **)(XDES *))(*(_QWORD *)v339 + 616LL))(v339)
     || *((_BYTE *)v27 + 1) == 11 && *((_DWORD *)v27 + 6) == 99) )
  {
    v465 = v51;
  }
  else
  {
    v465 = 0;
  }
  if ( !v373 || *((char *)v27 + 2) >= 0 )
  {
    v54 = (unsigned __int16 *)((char *)v27 + 2 * (4095 - v47));
    v55 = v369;
    v56 = (char *)v369 + v363 + *v54;
    goto LABEL_50;
  }
  v407 = -1;
  Source = 0;
  v409 = 0;
  *(_QWORD *)&v412[6] = 0;
  *(_QWORD *)&v412[16] = 0;
  v411 = 0;
  v420 = -1;
  v423 = 0;
  v422 = 0;
  v427 = 0;
  *(_QWORD *)((char *)&v428 + 2) = 0;
  v424 = 0;
  v236 = alloca(8096);
  Destination = &v331;
  LODWORD(DestinationSize) = 8094;
  v414 = v47;
  v237 = (unsigned __int8 *)v27 + 96;
  _mm_prefetch((const char *)v27 + 96, 0);
  v415[0] = 0;
  v416 = 0;
  memset(v417, 0, sizeof(v417));
  v418 = 0;
  v419 = 0;
  v415[1] = 0;
  WORD5(v418) = 0;
  if ( !*((_WORD *)v27 + 18) )
    goto LABEL_630;
  v238 = *((_BYTE *)v27 + 1);
  if ( v238 != 11 )
  {
    if ( v238 != 8 )
      goto LABEL_628;
    goto LABEL_629;
  }
  if ( *((_DWORD *)v27 + 6) == 99 )
    goto LABEL_622;
LABEL_628:
  if ( v238 == 9 )
  {
LABEL_629:
    if ( *((_DWORD *)v27 + 6) != 99 )
      goto LABEL_630;
LABEL_622:
    v374 = *((_DWORD *)v27 + 8);
    v375 = *((_WORD *)v27 + 18);
    if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v374, v48) )
      goto LABEL_630;
    PageHeader::GetIcxLsn(v27, &v390);
    v239 = v391;
  }
  else
  {
LABEL_630:
    v390 = *((_QWORD *)v27 + 5);
    v239 = *((_WORD *)v27 + 24);
    v391 = v239;
  }
  v415[0] = (Page *)((char *)v27 + 96);
  *(_QWORD *)&v418 = v390;
  WORD4(v418) = v239;
  HIDWORD(v418) = *((_DWORD *)v27 + 8);
  LODWORD(v419) = *((unsigned __int16 *)v27 + 18);
  v240 = *v237;
  v241 = 6 * v240 + 38287744;
  LODWORD(v377) = *(unsigned int *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4.Data1
                                  + v241);
  v242 = *(__int16 *)((char *)&word_100400002[1] + v241);
  LOWORD(v416) = -1;
  *((_QWORD *)&v416 + 1) = 0;
  DWORD1(v416) = 0;
  *(_QWORD *)((char *)v417 + 14) = 0;
  *((_QWORD *)&v417[1] + 1) = 0;
  *(_QWORD *)&v417[0] = 0;
  memset((char *)&v417[2] + 8, 0, 18);
  if ( (v240 & 2) != 0 )
  {
    v243 = &v237[v242];
    v58 = (v237[v242] & 1) == 0;
    *((_QWORD *)&v416 + 1) = &v237[v242];
    if ( v58 )
    {
      LOWORD(v416) = 0;
      v255 = 0;
      *(_DWORD *)((char *)&v417[1] + 6) = 0;
      switch ( *v243 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v255 = *((unsigned __int16 *)v243 + 1);
          if ( (unsigned int)(v255 - 1) > 0x1F9D )
            RaiseInconsistencyError(&v237[v242], 6);
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
          v255 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v255 = 1;
          break;
      }
      LODWORD(v417[0]) = v255;
    }
    else
    {
      LOWORD(v416) = 1;
      v244 = *v243;
      switch ( *v243 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v243[1] & 0x80u) != 0 )
          {
            v245 = 3;
            v246 = HIBYTE(*(_WORD *)(v243 + 1)) | ((*(_WORD *)(v243 + 1) & 0x7F) << 8);
          }
          else
          {
            v245 = 2;
            v246 = v243[1];
          }
          WORD1(v416) = v246;
          WORD4(v417[0]) = v245;
          WORD6(v417[0]) = v245 + (((unsigned int)v246 + 1) >> 1);
          if ( v246 > 0x1Eu )
            WORD5(v417[0]) = (v246 - 1) / 30;
          else
            WORD5(v417[0]) = 0;
          LODWORD(v417[2]) = 0;
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
          if ( (v244 & 0x1C) == 4 && (v244 & 2) != 0 )
          {
            v253 = 1;
            v254 = 15;
          }
          else
          {
            v253 = 0;
            v254 = 1;
          }
          DWORD2(v417[0]) = 0;
          WORD1(v416) = 0;
          WORD6(v417[0]) = 0;
          WORD3(v417[1]) = 0;
          DWORD1(v416) = v254;
          LODWORD(v417[2]) = v253;
          break;
        case 8:
          DWORD2(v417[0]) = 0;
          WORD1(v416) = 0;
          WORD6(v417[0]) = 0;
          WORD3(v417[1]) = 0;
          DWORD1(v416) = 9;
          LODWORD(v417[2]) = 0;
          break;
      }
    }
  }
  if ( (*(_BYTE *)v415[0] & 4) != 0 )
  {
    if ( WORD1(v377) )
      v247 = &v237[*(unsigned __int16 *)&v237[2 * SWORD1(v377) + 1]];
    else
      v247 = &v237[v242];
    *((_QWORD *)&v417[2] + 1) = v247;
    v248 = *(_WORD *)v247;
    *(_QWORD *)&v417[3] = v247 + 2;
    WORD4(v417[3]) = 2 * (v248 + 1);
  }
  if ( v415[1] )
    PageComprInfoCache::Init(v415[1], (const struct PageComprInfo *)v415);
  v249 = *((unsigned __int16 *)v27 + 7);
  v54 = (unsigned __int16 *)((char *)v27 + 2 * (4095 - v47));
  v250 = v369;
  v251 = (unsigned __int16 *)((char *)v369 + *v54);
  v58 = (*(_BYTE *)v251 & 1) == 0;
  Source = v251;
  if ( v58 )
  {
    v407 = 0;
    v258 = 0;
    v409 = 0;
    *(_DWORD *)&v412[14] = 0;
    switch ( *(_BYTE *)v251 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v249 = v251[1];
        if ( (unsigned int)(v249 - 1) > 0x1F9D )
        {
          RaiseInconsistencyError(v251, 6);
          goto LABEL_726;
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
LABEL_726:
        v258 = v409;
        break;
      case 4:
        v249 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v249 = 1;
        break;
    }
    LODWORD(v411) = v249;
    *(_QWORD *)&v412[6] = (char *)v250 + 0x2000;
    LODWORD(v260) = v249;
    v259 = v411;
  }
  else
  {
    v407 = 1;
    v252 = *(_BYTE *)v251;
    switch ( *(_BYTE *)v251 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( *((char *)v251 + 1) < 0 )
        {
          v256 = HIBYTE(*(unsigned __int16 *)((char *)v251 + 1))
               | ((*(unsigned __int16 *)((char *)v251 + 1) & 0x7F) << 8);
          v408 = v256;
          *(_WORD *)v412 = 3;
          v257 = 3;
        }
        else
        {
          v256 = *((unsigned __int8 *)v251 + 1);
          v408 = v256;
          *(_WORD *)v412 = 2;
          v257 = 2;
        }
        *(_WORD *)&v412[4] = v257 + (((unsigned int)v256 + 1) >> 1);
        if ( v256 > 0x1Eu )
          *(_WORD *)&v412[2] = (__int16)(v256 - 1) / 30;
        else
          *(_WORD *)&v412[2] = 0;
        v258 = 0;
        v409 = 0;
        v413 = 0;
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
        v258 = v409;
        break;
      case 4:
        if ( (v252 & 0x1C) == 4 && (v252 & 2) != 0 )
        {
          *(_QWORD *)v412 = 0;
          v408 = 0;
          *(_QWORD *)&v412[8] = 0;
          v258 = 15;
          v409 = 15;
          v413 = 1;
        }
        else
        {
          *(_QWORD *)v412 = 0;
          v408 = 0;
          *(_QWORD *)&v412[8] = 0;
          v258 = 1;
          v409 = 1;
          v413 = 0;
        }
        break;
      case 8:
        *(_QWORD *)v412 = 0;
        v408 = 0;
        *(_QWORD *)&v412[8] = 0;
        v258 = 9;
        v409 = 9;
        v413 = 0;
        break;
    }
    *(_QWORD *)&v412[16] = (char *)v250 + 0x2000;
    v259 = v415;
    v411 = v415;
    v260 = v415;
  }
  v56 = (char *)Source;
  if ( *(char *)(((unsigned __int64)Source & 0xFFFFFFFFFFFFE000uLL) + 2) >= 0 )
    goto LABEL_793;
  v261 = (unsigned int)DestinationSize;
  v262 = (char *)Destination;
  v420 = v407;
  if ( v407 )
  {
    if ( !v259 || !*v259 )
    {
      CDRecord::CopyNewRec(
        (CDRecord *)&v421,
        (unsigned __int8 *)Destination,
        DestinationSize,
        (const struct CDRecord *)&v408);
      goto LABEL_792;
    }
    Record::DecompressRec(
      (Record *)&v420,
      (unsigned __int8 *)Destination,
      DestinationSize,
      (const struct Record *)&v407);
    v56 = v423;
    v55 = v369;
    v53 = v339;
  }
  else
  {
    if ( v258 )
      goto LABEL_767;
    v408 = 0;
    HIDWORD(v411) = (_DWORD)v260;
    v258 = (unsigned int)v260;
    if ( (*(_BYTE *)Source & 0x10) != 0 )
    {
      v258 = (((unsigned int)*(unsigned __int16 *)((char *)Source + (unsigned int)v260) + 7) >> 3) + (_DWORD)v260 + 2;
      HIDWORD(v411) = v258;
    }
    if ( (*(_BYTE *)Source & 0x20) != 0 )
    {
      v263 = (char *)Source + v258;
      *(_WORD *)&v412[4] = *v263;
      if ( !*(_WORD *)&v412[4] )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v264 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v264 )
          {
            v265 = *(_QWORD *)(v264 + 96);
            if ( v265 )
            {
              if ( *(_BYTE *)(v265 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                else
                  ex_raise(34, 68, 21, 1003);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 3);
      }
      v266 = HIDWORD(v411) + 2 * (*(unsigned __int16 *)&v412[4] + 1);
      *(_DWORD *)v412 = v266;
      if ( v266 > 0x1F9E )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v267 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v267 )
          {
            v268 = *(_QWORD *)(v267 + 96);
            if ( v268 )
            {
              if ( *(_BYTE *)(v268 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 4);
        v266 = *(_DWORD *)v412;
      }
      v258 = v263[*(unsigned __int16 *)&v412[4]] & 0x7FFF;
      v409 = v258;
      if ( v266 > v258 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v269 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v269 )
          {
            v270 = *(_QWORD *)(v269 + 96);
            if ( v270 )
            {
              if ( *(_BYTE *)(v270 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(Source, 4);
        v266 = *(_DWORD *)v412;
        v258 = v409;
      }
      while ( (__int16)v263[*(unsigned __int16 *)&v412[4]] < 0 )
      {
        v271 = (char *)Source + HIDWORD(v411);
        if ( *(unsigned __int16 *)&v412[4] == 1 )
          v272 = v266;
        else
          v272 = *(_WORD *)&v271[2 * *(unsigned __int16 *)&v412[4] - 2] & 0x7FFF;
        if ( v272 < v266 || (*(_WORD *)&v271[2 * *(unsigned __int16 *)&v412[4]] & 0x7FFFu) < v272 )
        {
          RaiseInconsistencyError(Source, 7);
          v266 = *(_DWORD *)v412;
          v258 = v409;
        }
        if ( v272 < v266 || v272 > v258 )
          goto LABEL_768;
        v273 = *(_WORD *)((char *)Source + v272);
        if ( v273 == 5 )
        {
          v408 |= 2u;
          --*(_WORD *)&v412[4];
          *(_WORD *)&v412[18] = v272;
          v274 = (char *)Source + (unsigned __int16)v272;
          v275 = *((_WORD *)v274 + 1);
          if ( (v275 & 0x4000) != 0 )
            v276 = (*(_WORD *)&v412[20] ^ v275) & 0x3800 ^ *(_WORD *)&v412[20];
          else
            v276 = *(_WORD *)&v412[20] & 0xC7FF;
          *(_WORD *)&v412[20] = v276;
          *(_WORD *)&v412[20] = v276 ^ (*((_WORD *)v274 + 1) ^ v276) & 0x7FF;
          break;
        }
        if ( v273 >= 0x400u )
        {
          v408 |= 1u;
          if ( --*(_WORD *)&v412[4] )
            continue;
        }
        break;
      }
    }
    else
    {
      v409 = v258;
      *(_WORD *)&v412[4] = 0;
      v266 = v258;
      *(_DWORD *)v412 = v258;
    }
    if ( (*(_BYTE *)Source & 0x40) != 0 )
    {
      *(_DWORD *)&v412[14] = v258;
      v409 = v258 + 14;
      v277 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v408);
      v278 = HIDWORD(*(_QWORD *)v277);
      v279 = HIWORD(*(_QWORD *)v277);
      v280 = 0;
      if ( (((__int16)v279 ^ ((unsigned int)(__int16)v279 >> 1)) & 0x2000) != 0 )
      {
        v281 = v279 & 0xDFFF;
        if ( (v279 & 0x4000) != 0 )
          v281 = v279 | 0x2000;
        LOWORD(v279) = v281;
      }
      if ( (_WORD)v279 == 0xFFFC )
        v280 = (unsigned __int16)v278 >> 5;
      v258 = v280 + v409;
      v409 += v280;
      v266 = *(_DWORD *)v412;
    }
    else
    {
      *(_DWORD *)&v412[14] = 0;
    }
    if ( *(_QWORD *)&v412[6] && *(_QWORD *)&v412[6] < (unsigned __int64)Source + v258 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v282 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v282 )
        {
          v283 = *(_QWORD *)(v282 + 96);
          if ( v283 )
          {
            if ( *(_BYTE *)(v283 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(Source, 18);
      v266 = *(_DWORD *)v412;
      v258 = v409;
    }
    if ( v258 - 1 > 0x3F3B )
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
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
              else
                ex_raise(34, 68, 21, 1005);
            }
          }
        }
      }
      RaiseInconsistencyError(Source, 5);
      v258 = v409;
LABEL_767:
      v266 = *(_DWORD *)v412;
    }
LABEL_768:
    if ( v258 >= 9 || (v286 = *(_BYTE *)Source & 0xE) != 0 && v286 != 12 )
      v287 = v258;
    else
      v287 = 9;
    v424 = v411;
    v421 = v408;
    v422 = v258;
    v426 = *(_WORD *)&v412[4];
    v425 = v266;
    LODWORD(v428) = *(_DWORD *)&v412[14];
    memcpy_s(v262, v261, Source, v287);
    v423 = v262;
    if ( (unsigned int)FixedVarRecord::HasSparseVector((FixedVarRecord *)&v421) )
    {
      v288 = &v423[HIDWORD(v424)];
      v289 = *(unsigned __int16 *)v288 - 1;
      if ( (v421 & 1) == 0 )
        v289 = *(unsigned __int16 *)v288;
      v290 = v289 == 1 ? v425 : *(_WORD *)&v288[2 * v289 - 2] & 0x7FFF;
      v291 = *(_WORD *)&v288[2 * v289] & 0x7FFF;
      if ( v290 < v425 || v291 < v290 )
      {
        RaiseInconsistencyError(v423, 7);
        v56 = v423;
        v55 = v369;
        v53 = v339;
        goto LABEL_50;
      }
    }
LABEL_792:
    v56 = v423;
LABEL_793:
    v55 = v369;
    v53 = v339;
  }
LABEL_50:
  v468[1] = v56;
  v461[v460++] = v465;
  v57 = (BUF **)v366;
  v58 = (unsigned int)PageRef::NotToLogNewData(v366, v364) == 0;
  v59 = v370;
  if ( !v58 )
    v59 = 0;
  v466 = v59;
  v461[v460] = v59;
  v60 = ++v460;
  v468[2] = v385;
  if ( (unsigned __int8)(v455 - 2) > 1u || (*((_BYTE *)v53 + 536) & 2) != 0 )
    goto LABEL_89;
  if ( (*(unsigned int (__fastcall **)(XDES *))(*(_QWORD *)v53 + 616LL))(v53) )
  {
    v60 = v460;
LABEL_89:
    v461[v60] = 0;
    goto LABEL_56;
  }
  v467 = a15;
  v468[3] = a14;
  v461[v460] = a15;
  v52 = 4;
LABEL_56:
  v61 = ++v460;
  if ( a12 && v53 && *((_DWORD *)v53 + 56) )
  {
    v461[v61] = *(_DWORD *)(a12 + 40);
    v62 = ++v460;
    *(&v464 + v52) = *(_DWORD *)(a12 + 40);
    v468[v52++] = *(void **)(a12 + 48);
  }
  else
  {
    v461[v61] = 0;
    v62 = ++v460;
  }
  if ( !v372 )
  {
    v461[v62] = 0;
    v461[++v460] = 0;
    v63 = v460 + 1;
    v27 = v369;
    goto LABEL_62;
  }
  v431 = -1;
  v434 = 0;
  v433 = 0;
  *(_QWORD *)&v436[6] = 0;
  *(_QWORD *)&v436[16] = 0;
  v435 = 0;
  v438 = v337;
  if ( *((char *)v55 + 2) < 0 )
  {
    v297 = (unsigned __int8 *)v55 + 96;
    _mm_prefetch((const char *)v55 + 96, 0);
    memset(v442, 0, sizeof(v442));
    v443 = 0.0;
    memset(v444, 0, sizeof(v444));
    v446 = 0;
    *(_OWORD *)v439 = 0;
    v440 = 0xFFFFu;
    v441 = 0;
    v445 = 0u;
    v292 = v439;
    if ( !*((_WORD *)v55 + 18) )
      goto LABEL_809;
    v298 = *((_BYTE *)v55 + 1);
    if ( v298 == 11 )
    {
      if ( *((_DWORD *)v55 + 6) == 99 )
      {
LABEL_801:
        LODWORD(v384) = *((_DWORD *)v55 + 8);
        WORD2(v384) = *((_WORD *)v55 + 18);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v384, a12) )
        {
          PageHeader::GetIcxLsn(v55, &v392);
          v299 = v393;
LABEL_803:
          v439[0] = (Page *)((char *)v55 + 96);
          *(_QWORD *)&v445 = v392;
          WORD4(v445) = v299;
          HIDWORD(v445) = *((_DWORD *)v55 + 8);
          LODWORD(v446) = *((unsigned __int16 *)v55 + 18);
          v300 = *v297;
          v301 = 6 * v300 + 38287744;
          LODWORD(v377) = *(unsigned int *)((char *)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4.Data1
                                          + v301);
          v302 = *(__int16 *)((char *)&word_100400002[1] + v301);
          LOWORD(v440) = -1;
          *((_QWORD *)&v440 + 1) = 0;
          DWORD1(v440) = 0;
          *(_QWORD *)&v442[6] = 0;
          *(_QWORD *)((char *)&v443 + 2) = 0;
          v441 = 0;
          memset((char *)v444 + 8, 0, 18);
          if ( (v300 & 2) != 0 )
          {
            v303 = &v297[v302];
            v58 = (v297[v302] & 1) == 0;
            *((_QWORD *)&v440 + 1) = &v297[v302];
            if ( v58 )
            {
              LOWORD(v440) = 0;
              v311 = 0;
              LODWORD(v443) = 0;
              switch ( *v303 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v311 = *((unsigned __int16 *)v303 + 1);
                  if ( (unsigned int)(v311 - 1) > 0x1F9D )
                    RaiseInconsistencyError(&v297[v302], 6);
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
                  v311 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v311 = 1;
                  break;
              }
              LODWORD(v441) = v311;
              *(_QWORD *)&v442[6] = 0;
              v55 = v369;
            }
            else
            {
              LOWORD(v440) = 1;
              v304 = *v303;
              switch ( *v303 & 0x1C )
              {
                case 0:
                case 0xC:
                case 0x10:
                case 0x14:
                case 0x18:
                case 0x1C:
                  if ( (v303[1] & 0x80u) != 0 )
                  {
                    v305 = 3;
                    v306 = HIBYTE(*(_WORD *)(v303 + 1)) | ((*(_WORD *)(v303 + 1) & 0x7F) << 8);
                  }
                  else
                  {
                    v305 = 2;
                    v306 = v303[1];
                  }
                  WORD1(v440) = v306;
                  *(_WORD *)v442 = v305;
                  *(_WORD *)&v442[4] = v305 + (((unsigned int)v306 + 1) >> 1);
                  if ( v306 > 0x1Eu )
                    *(_WORD *)&v442[2] = (v306 - 1) / 30;
                  else
                    *(_WORD *)&v442[2] = 0;
                  LODWORD(v444[0]) = 0;
                  *(_QWORD *)((char *)&v443 + 2) = 0;
                  v441 = 0;
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
                  *(_QWORD *)((char *)&v443 + 2) = 0;
                  v441 = 0;
                  break;
                case 4:
                  if ( (v304 & 0x1C) == 4 && (v304 & 2) != 0 )
                  {
                    v309 = 1;
                    v310 = 15;
                  }
                  else
                  {
                    v309 = 0;
                    v310 = 1;
                  }
                  *(_DWORD *)v442 = 0;
                  WORD1(v440) = 0;
                  *(_WORD *)&v442[4] = 0;
                  v443 = 0.0;
                  DWORD1(v440) = v310;
                  LODWORD(v444[0]) = v309;
                  v441 = 0;
                  break;
                case 8:
                  *(_DWORD *)v442 = 0;
                  WORD1(v440) = 0;
                  *(_WORD *)&v442[4] = 0;
                  v443 = 0.0;
                  DWORD1(v440) = 9;
                  LODWORD(v444[0]) = 0;
                  v441 = 0;
                  break;
              }
            }
          }
          if ( (*(_BYTE *)v439[0] & 4) != 0 )
          {
            if ( WORD1(v377) )
              v307 = &v297[*(unsigned __int16 *)&v297[2 * SWORD1(v377) + 1]];
            else
              v307 = &v297[v302];
            *((_QWORD *)&v444[0] + 1) = v307;
            v308 = *(_WORD *)v307;
            *(_QWORD *)&v444[1] = v307 + 2;
            WORD4(v444[1]) = 2 * (v308 + 1);
          }
          if ( v439[1] )
            PageComprInfoCache::Init(v439[1], (const struct PageComprInfo *)v439);
          goto LABEL_796;
        }
LABEL_809:
        v392 = *((_QWORD *)v55 + 5);
        v299 = *((_WORD *)v55 + 24);
        v393 = v299;
        goto LABEL_803;
      }
    }
    else if ( v298 == 8 )
    {
LABEL_808:
      if ( *((_DWORD *)v55 + 6) != 99 )
        goto LABEL_809;
      goto LABEL_801;
    }
    if ( v298 != 9 )
      goto LABEL_809;
    goto LABEL_808;
  }
  v292 = 0;
LABEL_796:
  v293 = *((unsigned __int16 *)v55 + 7);
  v294 = *v54;
  v27 = v369;
  v295 = (char *)v369 + v294;
  v58 = (*v295 & 1) == 0;
  v434 = (unsigned __int8 *)v295;
  if ( v58 )
  {
    v431 = 0;
    v433 = 0;
    *(_DWORD *)&v436[14] = 0;
    switch ( *v295 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v293 = *((unsigned __int16 *)v295 + 1);
        if ( (unsigned int)(v293 - 1) > 0x1F9D )
          RaiseInconsistencyError(v295, 6);
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
        v293 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v293 = 1;
        break;
    }
    LODWORD(v435) = v293;
    *(_QWORD *)&v436[6] = (char *)v27 + 0x2000;
  }
  else
  {
    v431 = 1;
    v296 = *v295;
    switch ( *v295 & 0x1C )
    {
      case 0:
      case 0xC:
      case 0x10:
      case 0x14:
      case 0x18:
      case 0x1C:
        if ( v295[1] < 0 )
        {
          v312 = HIBYTE(*(_WORD *)(v295 + 1)) | ((*(_WORD *)(v295 + 1) & 0x7F) << 8);
          v432 = v312;
          v313 = 3;
          LOWORD(v368) = 3;
        }
        else
        {
          v312 = (unsigned __int8)v295[1];
          v432 = v312;
          v313 = 2;
        }
        *(_WORD *)v436 = v313;
        *(_WORD *)&v436[4] = v368 + (((unsigned int)v312 + 1) >> 1);
        if ( v312 > 0x1Eu )
          *(_WORD *)&v436[2] = (v312 - 1) / 30;
        else
          *(_WORD *)&v436[2] = 0;
        v433 = 0;
        v437 = 0;
        *(_QWORD *)&v436[16] = (char *)v369 + 0x2000;
        v435 = v292;
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
        *(_QWORD *)&v436[16] = (char *)v27 + 0x2000;
        v435 = v292;
        break;
      case 4:
        if ( (v296 & 0x1C) == 4 && (v296 & 2) != 0 )
        {
          *(_QWORD *)v436 = 0;
          v432 = 0;
          *(_QWORD *)&v436[8] = 0;
          v433 = 15;
          v437 = 1;
          *(_QWORD *)&v436[16] = (char *)v369 + 0x2000;
          v435 = v292;
        }
        else
        {
          *(_QWORD *)v436 = 0;
          v432 = 0;
          *(_QWORD *)&v436[8] = 0;
          v433 = 1;
          v437 = 0;
          *(_QWORD *)&v436[16] = (char *)v369 + 0x2000;
          v435 = v292;
        }
        break;
      case 8:
        *(_QWORD *)v436 = 0;
        v432 = 0;
        *(_QWORD *)&v436[8] = 0;
        v433 = 9;
        v437 = 0;
        *(_QWORD *)&v436[16] = (char *)v369 + 0x2000;
        v435 = v292;
        break;
    }
  }
  v314 = *v434;
  if ( v431 )
    v315 = v314 >> 1;
  else
    v315 = v314 >> 6;
  if ( (v315 & 1) != 0 )
  {
    if ( v431 )
      CDRecord::GetXdesTs(&v432, &v370);
    else
      FixedVarRecord::GetXdesTs(&v432, &v370);
    v448 = v370;
    v449 = v371;
    if ( v431 )
      CDRecord::GetVersionRecPtr(&v432, &v369);
    else
      FixedVarRecord::GetVersionRecPtr(&v432, &v369);
    v447 = v369;
    *(&v464 + v52) = 14;
    v468[v52] = &v447;
    v461[v460] = 14;
    v316 = v460 + 1;
    ++v52;
  }
  else
  {
    v461[v460] = 0;
    v316 = v460 + 1;
  }
  v460 = v316;
  v317 = &v461[v316];
  v318 = v378;
  if ( v378 )
  {
    *(&v464 + v52) = 14;
    v468[v52] = v318;
    *v317 = 14;
    v63 = v460 + 1;
    ++v52;
  }
  else
  {
    *v317 = 0;
    v63 = v460 + 1;
  }
  v57 = (BUF **)v366;
LABEL_62:
  v460 = v63;
  v451 = 62;
  v464 = 2 * v63 + 64;
  v468[0] = v450;
  v64 = v339;
  if ( v339 )
  {
    if ( v365 == 2 )
    {
      v366 = (const void ***)v339;
      *((_BYTE *)v339 + 714) = 1;
      (*(void (__fastcall **)(XDES *, _QWORD, unsigned int *, void **, __int64 *))(*(_QWORD *)v64 + 648LL))(
        v64,
        v52,
        &v464,
        v468,
        &v405);
      *((_BYTE *)v64 + 714) = 0;
      v366 = 0;
    }
    else
    {
      (*(void (__fastcall **)(XDES *, _QWORD, unsigned int *, void **, __int64 *))(*(_QWORD *)v339 + 648LL))(
        v339,
        v52,
        &v464,
        v468,
        &v405);
    }
    v40 = v338;
    PFSFreeSpaceAfterModify = v361;
    v35 = v362;
  }
  else
  {
    v319 = (const struct RecoveryUnit *)*((_QWORD *)*v57 + 18);
    if ( !v319 )
    {
      BUF::FixupPru(*v57);
      v319 = *(const struct RecoveryUnit **)(v320 + 144);
    }
    XDES::GenerateNonXactLogRec(v319, v52, &v464, (const void **)v468, (struct LSN *)&v405, 0, 0);
    v40 = v338;
    PFSFreeSpaceAfterModify = v361;
    v35 = v362;
  }
LABEL_66:
  if ( v360[0] )
  {
    v327 = 0;
    v328 = *((unsigned __int16 *)v27 + 11);
    v329 = v328 - 1;
    if ( v328 - 1 >= (unsigned __int16)(v328 - v360[0]) )
    {
      v330 = (_WORD *)((char *)v27 + 2 * (4095 - v329));
      do
      {
        if ( *v330 )
          break;
        ++v327;
        --v329;
        ++v330;
      }
      while ( v329 >= (unsigned __int16)(v328 - v360[0]) );
    }
    *((_WORD *)v27 + 11) = v328 - v327;
    *((_WORD *)v27 + 14) += 2 * v327;
  }
  if ( v381 )
    Page::CompactPage(v27, v337);
  v65 = v335;
  if ( (v333[0] & 0x100) != 0 )
  {
    v65 = v335 | 0x40;
    v335 |= 0x40u;
  }
  if ( v372 )
  {
    Page::ModifyRowAndReplaceVersionInfo(v27, v337, v363, v334, v336, v385, v65, v333[0], v380, v378);
  }
  else
  {
    if ( v373 )
    {
      v363 = 0;
      v385 = *(void **)(v395 + 8);
    }
    LODWORD(SourceSize) = v336;
    Page::ModifyRow(v27, v337, v363, v334, SourceSize, v385, v65, v333[0], v380);
  }
  if ( *((_WORD *)v27 + 24) != v406 || *((_QWORD *)v27 + 5) != v405 )
  {
    *((_QWORD *)v27 + 5) = v405;
    *((_WORD *)v27 + 24) = v406;
    *((_WORD *)v27 + 2) &= ~0x20u;
  }
  v378 = 0;
  v379 = 0;
  BPool::Dirty(qword_10317B628, *v57, 0, (struct LSN *)&v378);
  if ( (byte_10317AD49 & 2) != 0 )
    _InterlockedAnd((volatile signed __int32 *)*v57 + 25, 0xFFFFFFEF);
  if ( !v364 )
  {
    if ( (v335 & 2) != 0 )
    {
      if ( PFSFreeSpaceAfterModify != Page::GetPFSFreeSpace(v27) )
        utassert_fail(1u, "newPFSFreeSpace == pPage->GetPFSFreeSpace ()", "pageref.cpp", 5768, 0);
    }
    else
    {
      v66 = *((unsigned __int16 *)v27 + 11) - 1LL;
      if ( v66 >= 0 )
      {
        v67 = (_WORD *)((char *)v27 + 2 * (4095 - v66));
        do
        {
          if ( *v67 )
            break;
          ++v20;
          ++v67;
          --v66;
        }
        while ( v66 >= 0 );
      }
      if ( !v40 )
        PageRef::UpdateFreeSpaceStateInPFS(v57, &v376, v64, v365, v35, *((unsigned __int16 *)v27 + 14) + 2 * v20);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100445640  push    rbp
0x100445642  push    rsi
0x100445643  push    rdi
0x100445644  push    r12
0x100445646  push    r13
0x100445648  push    r14
0x10044564a  push    r15
0x10044564c  sub     rsp, 980h
0x100445653  lea     rbp, [rsp+50h]
0x100445658  mov     [rbp+960h+var_7C0], 0FFFFFFFFFFFFFFFEh
0x100445663  mov     [rbp+960h+arg_8], rbx
0x10044566a  mov     rax, cs:__security_cookie
0x100445671  xor     rax, rbp
0x100445674  mov     [rbp+960h+var_40], rax
0x10044567b  mov     dword ptr [rbp+960h+var_954+4], r9d
0x10044567f  mov     r14, r8
0x100445682  mov     [rbp+960h+var_8B0], r8
0x100445689  mov     [rbp+960h+var_848], rdx
0x100445690  mov     r13, rcx
0x100445693  mov     [rbp+960h+var_8B8], rcx
0x10044569a  mov     eax, [rbp+960h+arg_20]
0x1004456a0  mov     [rbp+960h+var_8C4], eax
0x1004456a6  mov     rax, [rbp+960h+arg_38]
0x1004456ad  mov     [rbp+960h+var_840], rax
0x1004456b4  mov     rcx, [rbp+960h+arg_50]
0x1004456bb  mov     [rbp+960h+var_948], rcx
0x1004456bf  mov     r15, [rbp+960h+arg_80]
0x1004456c6  mov     rax, [rbp+960h+arg_88]
0x1004456cd  mov     [rbp+960h+var_870], rax
0x1004456d4  xor     edi, edi
0x1004456d6  mov     [rbp+960h+var_8D0], di
0x1004456dd  mov     edx, 1
0x1004456e2  mov     [rbp+960h+var_958], edx
0x1004456e5  mov     [rbp+960h+var_860], rdi
0x1004456ec  mov     [rbp+960h+var_850], edi
0x1004456f2  mov     [rbp+960h+var_84C], di
0x1004456f9  mov     [rbp+960h+var_7C8], rdi
0x100445700  mov     [rbp+960h+var_880], rdi
0x100445707  mov     [rbp+960h+var_960], di
0x10044570b  mov     [rbp+960h+var_94C], edi
0x10044570e  mov     [rbp+960h+var_7F8], rdi
0x100445715  mov     eax, edi
0x100445717  mov     [rbp+960h+var_598], rax
0x10044571e  mov     [rbp+960h+var_590], edi
0x100445724  mov     [rbp+960h+var_58C], di
0x10044572b  mov     [rbp+960h+var_7F0], rdi
0x100445732  mov     r12d, edi
0x100445735  mov     [rbp+960h+var_8BC], edi
0x10044573b  mov     esi, [rbp+960h+arg_60]
0x100445741  test    rcx, rcx
0x100445744  jz      short loc_100445769
0x100445746  mov     r12, [rcx+30h]
0x10044574a  mov     rax, [rcx]
0x10044574d  call    qword ptr [rax]
0x10044574f  mov     edx, esi
0x100445751  shr     edx, 15h
0x100445754  and     edx, 2
0x100445757  test    al, al
0x100445759  mov     ecx, 1
0x10044575e  cmovnz  edx, ecx
0x100445761  mov     [rbp+960h+var_8BC], edx
0x100445767  mov     edx, ecx
0x100445769  mov     ebx, 2
0x10044576e  mov     [rbp+960h+var_8A8], ebx
0x100445774  cmp     [rbp+960h+arg_78], edi
0x10044577a  jz      loc_1018DF252
0x100445780  xor     r9d, r9d
0x100445783  mov     r14d, 1
0x100445789  mov     r8d, r14d
0x10044578c  mov     rdx, [r13+0]
0x100445790  mov     rcx, cs:qword_10317B628
0x100445797  call    ?PrepareToDirty@BPool@@QEAAPEAVPage@@PEAUBUF@@W4ChangeMode@1@_N@Z; BPool::PrepareToDirty(BUF *,BPool::ChangeMode,bool)
0x10044579c  mov     ecx, 0EDFFh
0x1004457a1  and     [rax+4], cx
0x1004457a5  mov     [rax+40h], r14d
0x1004457a9  mov     r11, [r13+0]
0x1004457ad  mov     r13, [r11]
0x1004457b0  mov     [rbp+960h+var_8A0], r13
0x1004457b7  mov     edx, esi
0x1004457b9  mov     ecx, [rbp+960h+arg_30]
0x1004457bf  mov     [rbp+960h+var_898], ecx
0x1004457c5  mov     eax, [rbp+960h+arg_28]
0x1004457cb  mov     [rbp+960h+var_888], eax
0x1004457d1  lea     r9, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x1004457d8  mov     esi, 4000h
0x1004457dd  and     edx, 20000h
0x1004457e3  mov     [rbp+960h+var_88C], edx
0x1004457e9  jnz     loc_1018DF674
0x1004457ef  mov     [rbp+960h+var_95C], eax
0x1004457f2  mov     dword ptr [rbp+960h+var_954], ecx
0x1004457f5  mov     rsi, [rbp+960h+var_8B8]
0x1004457fc  mov     rcx, [rbp+960h+var_8B0]
0x100445803  mov     eax, [rcx]
0x100445805  mov     dword ptr [rbp+960h+var_880], eax
0x10044580b  movzx   eax, word ptr [rcx+4]
0x10044580f  mov     word ptr [rbp+960h+var_880+4], ax
0x100445816  movzx   eax, word ptr [rcx+6]
0x10044581a  mov     word ptr [rbp+960h+var_880+6], ax
0x100445821  mov     r15d, [rbp+960h+arg_40]
0x100445828  mov     r10d, 0FFh
0x10044582e  bt      r15d, 16h
0x100445833  jb      loc_1018E0718
0x100445839  mov     eax, [r11+64h]
0x10044583d  bt      eax, 13h
0x100445841  jb      loc_1018E06DB
0x100445847  mov     rsi, [rbp+960h+var_948]
0x10044584b  jmp     short loc_10044584E
0x10044584e  mov     r14d, edi
0x100445851  movzx   eax, byte ptr [r13+1]
0x100445856  cmp     al, 3
0x100445858  jz      loc_1006019E0
0x10044585e  cmp     al, 1
0x100445860  jnz     short loc_10044586B
0x100445862  test    al, r15b
0x100445865  jz      loc_1018E0B51
0x10044586b  mov     r8d, 2
0x100445871  mov     [rbp+960h+var_8C0], r8d
0x100445878  mov     r10d, 1
0x10044587e  mov     r9d, [rbp+960h+arg_60]
0x100445885  mov     eax, r9d
0x100445888  and     eax, 10000h
0x10044588d  mov     [rbp+960h+var_890], eax
0x100445893  jnz     loc_1018E0B8B
0x100445899  mov     ebx, [rbp+960h+var_94C]
0x10044589c  cmp     r8d, 2
0x1004458a0  jnz     loc_100604B48
0x1004458a6  mov     esi, dword ptr [rbp+960h+var_878]
0x1004458ac  mov     [rbp+960h+var_8C8], esi
0x1004458b2  mov     r12d, [rbp+960h+var_8A8]
0x1004458b9  mov     [rbp+960h+var_8CC], r12d
0x1004458c0  mov     rax, rdi
0x1004458c3  mov     [rsp+9B0h+var_970], rax
0x1004458c8  mov     eax, [rbp+960h+var_958]
0x1004458cb  mov     dword ptr [rsp+9B0h+var_978], eax
0x1004458cf  lea     rax, [rbp+960h+var_8D0]
0x1004458d6  mov     [rsp+9B0h+var_980], rax
0x1004458db  lea     rax, [rbp+960h+var_858]
0x1004458e2  mov     [rsp+9B0h+var_988], rax
0x1004458e7  mov     dword ptr [rsp+9B0h+SourceSize], ebx
0x1004458eb  mov     r9d, dword ptr [rbp+960h+var_954]
0x1004458ef  mov     r8d, [rbp+960h+var_95C]
0x1004458f3  mov     edx, dword ptr [rbp+960h+var_954+4]
0x1004458f6  mov     rcx, r13
0x1004458f9  call    ?CheckForModifySpace@Page@@QEAAIHIIW4VersionOverhead@1@AEAHAEAGIPEBVXdesId@@@Z; Page::CheckForModifySpace(int,uint,uint,Page::VersionOverhead,int &,ushort &,uint,XdesId const *)
0x1004458fe  test    eax, eax
0x100445900  jnz     loc_100445E43
0x100445906  mov     rbx, [rbp+960h+var_948]
0x10044590a  test    rbx, rbx
0x10044590d  jz      short loc_10044592A
0x10044590f  mov     eax, [rbx+218h]
0x100445915  and     al, 5
0x100445917  cmp     al, 1
0x100445919  jnz     short loc_10044592A
0x10044591b  mov     eax, [rbx+2D8h]
0x100445921  and     eax, 1
0x100445924  jnz     loc_1018E155B
0x10044592a  mov     edx, [rbp+960h+arg_60]
0x100445930  mov     ebx, edx
0x100445932  mov     eax, 200h
0x100445937  and     ebx, eax
0x100445939  mov     [rbp+960h+var_94C], ebx
0x10044593c  jnz     loc_1006019EF
0x100445942  mov     eax, 800h
0x100445947  test    eax, edx
0x100445949  jnz     loc_1018E15B9
0x10044594f  cmp     [rbp+960h+var_88C], 0
0x100445956  jnz     loc_1018E15C3
0x10044595c  cmp     [rbp+960h+var_890], 0
0x100445963  jnz     loc_1018E15D2
0x100445969  bt      edx, 15h
0x10044596d  jb      loc_1018E15E1
0x100445973  cmp     r14d, 2
0x100445977  jz      loc_1018E309F
0x10044597d  mov     [rbp+960h+var_578], edi
0x100445983  mov     [rbp+960h+var_574], di
0x10044598a  mov     [rbp+960h+var_54A], di
0x100445991  movzx   esi, di
0x100445994  mov     r14, [rbp+960h+var_8B8]
0x10044599b  mov     r8, [r14]
0x10044599e  mov     rax, [r8]
0x1004459a1  movzx   ecx, byte ptr [rax+1]
0x1004459a5  sub     cl, 3
0x1004459a8  cmp     cl, 1
0x1004459ab  jbe     loc_1006019F9
0x1004459b1  bt      edx, 12h
0x1004459b5  jb      loc_1006019F9
0x1004459bb  mov     [rbp+960h+var_572], 4
0x1004459c2  movzx   ebx, word ptr [r8+62h]
0x1004459c7  mov     edx, r15d
0x1004459ca  mov     rcx, r13
0x1004459cd  call    ?MapContext@PageLog@@SA?AW4LogContext@@AEBVPageHeader@@W4ETabStatus@@@Z; PageLog::MapContext(PageHeader const &,ETabStatus)
0x1004459d2  mov     [rbp+960h+var_571], al
0x1004459d8  shr     bl, 3
0x1004459db  and     bl, 1
0x1004459de  mov     ecx, [rbp+960h+arg_60]
0x1004459e4  movzx   eax, si
0x1004459e7  mov     r12d, 400h
0x1004459ed  or      ax, r12w
0x1004459f1  and     ecx, 1000000h
0x1004459f7  cmovz   ax, si
0x1004459fb  mov     byte ptr [rsp+9B0h+var_988], bl; bool
0x1004459ff  mov     word ptr [rsp+9B0h+SourceSize], ax; unsigned __int16
0x100445a04  movsxd  r15, dword ptr [rbp+960h+var_954+4]
0x100445a08  mov     r9d, r15d; int
0x100445a0b  mov     r8, r13; struct PageHeader *
0x100445a0e  mov     rdx, [rbp+960h+var_8B0]; struct AllocUnitId *
0x100445a15  lea     rcx, [rbp+960h+var_588]; this
0x100445a1c  call    ?FillPageInfo@PageLog@@QEAAXAEBVAllocUnitId@@AEBVPageHeader@@HG_N@Z; PageLog::FillPageInfo(AllocUnitId const &,PageHeader const &,int,ushort,bool)
0x100445a21  mov     rax, [rbp+960h+var_848]
0x100445a28  mov     [rbp+960h+var_558], rax
0x100445a2f  movzx   eax, [rbp+960h+var_960]
0x100445a33  mov     [rbp+960h+var_54C], ax
0x100445a3a  mov     ecx, [rbp+960h+var_8C4]
0x100445a40  mov     [rbp+960h+var_550], cx
0x100445a47  test    cs:byte_10317AC09, 40h
0x100445a4e  jnz     short loc_100445A9C
0x100445a50  mov     r8, gs:58h
0x100445a59  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100445a60  mov     ecx, [rax]
0x100445a62  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100445a69  mov     edx, [rax]
0x100445a6b  add     rdx, [r8+rcx*8]
0x100445a6f  mov     rax, [rdx]
0x100445a72  test    rax, rax
0x100445a75  jz      short loc_100445A87
0x100445a77  mov     rax, [rax+38h]
0x100445a7b  mov     rcx, [rax]
0x100445a7e  test    rcx, rcx
0x100445a81  jnz     loc_1018E15F0
0x100445a87  mov     rax, [r14]
0x100445a8a  cmp     word ptr [rax+2Ch], 2
0x100445a8f  jz      loc_100523F12
0x100445a95  movzx   eax, [rbp+960h+var_54C]
0x100445a9c  mov     ecx, 0FBFFh
0x100445aa1  and     ax, cx
0x100445aa4  mov     [rbp+960h+var_54C], ax
0x100445aab  mov     ebx, [rbp+960h+var_888]
0x100445ab1  mov     [rbp+960h+var_54E], bx
0x100445ab8  mov     r12d, 3
0x100445abe  mov     rsi, [rbp+960h+var_948]
0x100445ac2  test    rsi, rsi
0x100445ac5  jz      loc_1004B8D55
0x100445acb  mov     rax, [rsi]
0x100445ace  mov     rcx, rsi
0x100445ad1  call    qword ptr [rax+268h]
0x100445ad7  test    eax, eax
0x100445ad9  jnz     loc_1004B8D4A
0x100445adf  mov     [rbp+960h+var_9C], ebx
0x100445ae5  jmp     short loc_100445AE8
0x100445ae8  cmp     [rbp+960h+var_88C], 0
0x100445aef  jnz     loc_1018E161A
0x100445af5  mov     ecx, 0FFFh
0x100445afa  sub     rcx, r15
0x100445afd  lea     r13, [r13+rcx*2+0]
0x100445b02  mov     eax, [rbp+960h+var_8C4]
0x100445b08  movzx   ecx, word ptr [r13+0]
0x100445b0d  mov     rbx, [rbp+960h+var_8A0]
0x100445b14  add     rax, rbx
0x100445b17  add     rcx, rax
0x100445b1a  mov     [rbp+960h+var_78], rcx
0x100445b21  movzx   ecx, [rbp+960h+var_54A]
0x100445b28  movzx   eax, word ptr [rbp+960h+var_9C]
0x100445b2f  mov     [rbp+rcx*2+960h+var_548], ax
0x100445b37  inc     [rbp+960h+var_54A]
0x100445b3e  mov     edx, [rbp+960h+var_8C0]
0x100445b44  mov     r15, [rbp+960h+var_8B8]
0x100445b4b  mov     rcx, r15
0x100445b4e  call    ?NotToLogNewData@PageRef@@AEAAHW4PageSlotOrder@1@@Z; PageRef::NotToLogNewData(PageRef::PageSlotOrder)
0x100445b53  test    eax, eax
0x100445b55  mov     eax, [rbp+960h+var_898]
0x100445b5b  cmovnz  eax, edi
0x100445b5e  mov     [rbp+960h+var_98], eax
0x100445b64  movzx   ecx, [rbp+960h+var_54A]
0x100445b6b  mov     [rbp+rcx*2+960h+var_548], ax
0x100445b73  movzx   ecx, [rbp+960h+var_54A]
0x100445b7a  inc     cx
0x100445b7d  mov     [rbp+960h+var_54A], cx
0x100445b84  mov     rax, [rbp+960h+var_840]
0x100445b8b  mov     [rbp+960h+var_70], rax
0x100445b92  movzx   eax, [rbp+960h+var_571]
0x100445b99  sub     al, 2
0x100445b9b  cmp     al, 1
0x100445b9d  ja      loc_1005D9449
0x100445ba3  test    byte ptr [rsi+218h], 2
0x100445baa  jnz     loc_1005D9449
0x100445bb0  mov     rax, [rsi]
0x100445bb3  mov     rcx, rsi
0x100445bb6  call    qword ptr [rax+268h]
0x100445bbc  test    eax, eax
0x100445bbe  jnz     loc_1005D9442
0x100445bc4  mov     ecx, [rbp+960h+arg_70]
0x100445bca  mov     [rbp+960h+var_94], ecx
0x100445bd0  mov     rax, [rbp+960h+arg_68]
0x100445bd7  mov     [rbp+960h+var_68], rax
0x100445bde  movzx   eax, [rbp+960h+var_54A]
0x100445be5  mov     [rbp+rax*2+960h+var_548], cx
0x100445bed  mov     r12d, 4
0x100445bf3  jmp     short loc_100445BF6
0x100445bf6  movzx   eax, [rbp+960h+var_54A]
0x100445bfd  inc     ax
  ... truncated ...
```
