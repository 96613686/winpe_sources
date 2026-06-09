# VersionMgr::GenerateVersion(HoBtVersioningStatus,unsigned __int64,XDES *,Page *,Record const &,VersionMgr::OperationType,VersionMgr::OldRowStatus,VersionMgr::CompressionStatus,Record *,VersionMgr::VersionChainOption,MergeTriggerType,VersionMgr::GenerateResult &,VersionRecPtr &,uchar (*)[200],uint)

- ea: `0x10049b060`
- end: `0x10049b330`
- name: `?GenerateVersion@VersionMgr@@SAXVHoBtVersioningStatus@@_KPEAVXDES@@PEAVPage@@AEBVRecord@@W4OperationType@1@W4OldRowStatus@1@W4CompressionStatus@1@PEAV5@W4VersionChainOption@1@W4MergeTriggerType@@AEAW4GenerateResult@1@AEAVVersionRecPtr@@PEAY0MI@EI@Z`
- size: `720`
- prototype: ``
- caller_count: `8`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1004437c0`
- `0x10048abf0`
- `0x1005b7610`
- `0x100604ea0`
- `0x1012fa3b0`
- `0x1013016b0`
- `0x10191a930`
- `0x10191e410`

## callees

- `0x100401490`
- `0x100402000`
- `0x100402d60`
- `0x100403030`
- `0x100415e90`
- `0x100427840`
- `0x10043e110`
- `0x100441e00`
- `0x100441e40`
- `0x1004807a0`
- `0x10048c200`
- `0x10049b060`
- `0x10049b340`
- `0x1011ffd80`
- `0x10130d530`
- `0x1018d0f10`
- `0x101c9bed0`
- `0x101d17010`
- `0x101d1b810`
- `0x101d1e980`
- `0x1021d45f0`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`
- `0x102394d80`
- `0x1023aee60`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x101d123c3`
- `KERNEL32!HeapAlloc` at `0x101d13d2c`
- `KERNEL32!HeapAlloc` at `0x101d123c3`
- `KERNEL32!HeapAlloc` at `0x101d13d2c`
- `KERNEL32!GetProcessHeap` at `0x101d123b2`
- `KERNEL32!GetProcessHeap` at `0x101d13d1b`
- `KERNEL32!GetProcessHeap` at `0x101d123b2`
- `KERNEL32!GetProcessHeap` at `0x101d13d1b`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x101d123ab`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x101d13d14`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x101d123ab`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x101d13d14`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x101d1241d`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x101d13d85`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x101d1241d`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x101d13d85`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x101d123ee`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x101d13d57`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x101d123ee`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x101d13d57`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d11b90`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d11d67`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d1205a`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d12157`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101d1249e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11a73`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11c23`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11c6c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11cc0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11df5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11e3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11e93`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11eeb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12019`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12117`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1228b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d125ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d126f2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12781`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12bec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12c17`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12c42`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1320a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13235`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1329f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d132ca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d132f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1396b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13996`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a62`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1410c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d14137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1451d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d14548`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d147dc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15965`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15aaf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b3b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b88`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15bb2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15c9f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15cca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d2e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d84`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15e6c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15e97`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15ef7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15f22`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15f4d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1603c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16067`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d168ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1692a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16955`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16a3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16a68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16ac8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16af3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16b1e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16e7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16ea6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11a73`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11c23`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11c6c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11cc0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11df5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11e3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11e93`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d11eeb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12019`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12117`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1228b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d125ed`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d126f2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12781`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12bec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12c17`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d12c42`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1320a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13235`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1329f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d132ca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d132f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1396b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13996`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d13a62`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1410c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d14137`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d141ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1451d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d14548`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d147dc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15965`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15aaf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b3b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b60`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15b88`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15bb2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15c9f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15cca`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d2e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d59`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15d84`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15e6c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15e97`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15ef7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15f22`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d15f4d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1603c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16067`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d168ff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d1692a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16955`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16a3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16a68`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16ac8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16af3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16b1e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16e7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101d16ea6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12975`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12a1f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12ac6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12de1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12e81`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12fa9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13053`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d130fa`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13492`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13532`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d136fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d137ad`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13858`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13c07`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13ca7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13ead`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13f57`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d13ffe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1439e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1443e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d149a3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14a5b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14b11`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14d05`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14da7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14ed5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d14f8d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d15043`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d15235`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d152d7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d15406`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d154b8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1556b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1575e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d15800`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d161a2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1625a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d16310`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1650a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d165ac`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d166d5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d16780`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d1682a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d16cbd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d16d5d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12975`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12a1f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12ac6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101d12de1`

## string_xrefs

- `0x101d11c62`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101d11e33`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101d11cb6`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101d11e89`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101d1210d`: `!xdes->DoesXactGenVersionForHadronReadSecOnly()`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall VersionMgr::GenerateVersion(
        unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        int a8,
        struct Record *a9,
        int a10,
        unsigned int a11,
        _DWORD *a12,
        VersionRecPtr *a13,
        void *a14,
        rsize_t DestinationSize)
{
  __int64 v17; // rax
  int v18; // r13d
  __int16 v19; // r12
  FixedVarRecord *v20; // rdi
  __int64 v21; // rcx
  XDES *v22; // rbx
  char v23; // al
  int v24; // r14d
  char v25; // r15
  char v26; // al
  char v27; // si
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // r14d
  unsigned int v32; // r12d
  XDES *v33; // r15
  char v34; // al
  __int64 v35; // rbx
  Record *v36; // r13
  __int64 v37; // rsi
  unsigned __int8 v38; // al
  struct RecoveryUnit *v39; // rsi
  VersionRecPtr *v40; // r12
  unsigned int v41; // edx
  __int64 result; // rax
  int v43; // ebx
  Record *v44; // rsi
  unsigned int v45; // eax
  int v46; // r8d
  int v47; // edx
  __int16 v48; // cx
  XDES *v49; // rax
  int DoesXactGenVersion; // ecx
  __int64 v51; // rax
  char *v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rax
  int v57; // eax
  XDES *v58; // rax
  int v59; // eax
  __int64 v60; // rax
  char *v61; // rdx
  __int64 v62; // rbx
  __int64 v63; // rax
  bool v64; // cc
  __int64 v65; // rax
  int v66; // eax
  __int64 v67; // rax
  int v68; // eax
  char v69; // al
  XDES *v70; // rax
  int v71; // ecx
  __int64 v72; // rax
  char *v73; // rdx
  XDES *v74; // rax
  int v75; // eax
  __int64 v76; // rax
  char *v77; // rdx
  const unsigned __int16 *v78; // r8
  unsigned int CtrNestIdFromVersionRecPtr; // ebx
  int v80; // eax
  VersionRecPtr *v81; // r9
  unsigned int v82; // esi
  struct RecoveryUnit *v83; // r13
  __int64 v84; // rdx
  struct CSessionTraceFlags *v85; // rcx
  __int64 v86; // r14
  int v87; // ebx
  unsigned int *v88; // rax
  unsigned __int64 v89; // rdi
  __int64 v90; // rax
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v92; // rax
  CTracePrintStream *v93; // rbx
  __int64 v94; // r14
  unsigned int *v95; // rax
  unsigned __int64 v96; // rdi
  unsigned int v97; // ebx
  __int64 v98; // rax
  unsigned __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rcx
  char *v102; // rdx
  _QWORD *v103; // rbx
  __int64 v104; // rbx
  VersionRecPtr *v105; // r14
  int v106; // edi
  int v107; // ebx
  __int64 v108; // rax
  __int16 v109; // si
  __int16 v110; // r14
  _QWORD *v111; // rdx
  unsigned int v112; // r12d
  unsigned int v113; // r12d
  _BYTE *v114; // rax
  int v115; // ecx
  char v116; // dl
  char v117; // al
  __int16 v118; // dx
  __int64 v119; // rdx
  char *v120; // r8
  char v121; // al
  int v122; // ecx
  unsigned __int16 *v123; // rsi
  unsigned __int16 v124; // ax
  __int64 v125; // rax
  __int64 v126; // rax
  unsigned int v127; // edx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rcx
  unsigned int v131; // eax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rdx
  __int64 v135; // rax
  unsigned int v136; // ebx
  unsigned int v137; // ecx
  unsigned int v138; // eax
  unsigned __int16 v139; // dx
  __int16 v140; // ax
  __int64 v141; // rdx
  __int16 v142; // cx
  __int16 v143; // cx
  int v144; // eax
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v146; // rdx
  int v147; // r8d
  unsigned __int64 v148; // rdx
  int v149; // ecx
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  unsigned int v154; // ebx
  char v155; // cl
  bool v156; // zf
  unsigned int v157; // eax
  __int64 v158; // rdx
  char *v159; // r8
  char v160; // al
  int v161; // ecx
  unsigned __int16 *v162; // rsi
  unsigned __int16 v163; // ax
  __int64 v164; // rax
  __int64 v165; // rax
  unsigned int v166; // edx
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rcx
  unsigned int v170; // eax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rdx
  __int64 v174; // rax
  unsigned int v175; // ebx
  unsigned int v176; // ecx
  unsigned int v177; // eax
  unsigned __int16 v178; // dx
  __int16 v179; // ax
  _BYTE *v180; // rax
  __int64 v181; // rdx
  __int16 v182; // cx
  __int16 v183; // cx
  struct RecVersioningInfo *v184; // rax
  __int64 v185; // rdx
  int v186; // r8d
  unsigned __int64 v187; // rdx
  int v188; // ecx
  __int64 v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rax
  char v193; // cl
  int v194; // eax
  VersionRecPtr *v195; // r9
  __int64 v196; // rdx
  struct CSessionTraceFlags *v197; // rcx
  __int64 v198; // r12
  int v199; // ebx
  unsigned int *v200; // rax
  unsigned __int64 v201; // r15
  __int64 v202; // rdx
  char *v203; // r8
  char v204; // al
  int v205; // ecx
  unsigned __int16 *v206; // r14
  unsigned __int16 v207; // ax
  __int64 v208; // rax
  __int64 v209; // rax
  unsigned int v210; // edx
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // rcx
  unsigned int v214; // eax
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rdx
  __int64 v218; // rax
  unsigned int v219; // esi
  unsigned int v220; // ecx
  unsigned int v221; // eax
  unsigned __int16 v222; // dx
  __int16 v223; // ax
  _BYTE *v224; // rax
  __int64 v225; // rdx
  __int16 v226; // cx
  __int16 v227; // cx
  int v228; // eax
  struct RecVersioningInfo *v229; // rax
  __int64 v230; // rdx
  int v231; // r8d
  unsigned __int64 v232; // rdx
  int v233; // ecx
  __int64 v234; // rax
  __int64 v235; // rax
  __int64 v236; // rax
  __int64 v237; // rax
  unsigned int v238; // esi
  char v239; // cl
  bool v240; // zf
  __int64 v241; // rax
  HANDLE v242; // rax
  CTracePrintStream *v243; // rax
  CTracePrintStream *v244; // rbx
  __int64 v245; // r15
  unsigned int *v246; // rax
  unsigned __int64 v247; // r14
  __int64 v248; // rdx
  char *v249; // r8
  char v250; // al
  int v251; // ecx
  unsigned __int16 *v252; // rsi
  unsigned __int16 v253; // ax
  __int64 v254; // rax
  __int64 v255; // rax
  unsigned int v256; // edx
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rcx
  unsigned int v260; // eax
  __int64 v261; // rax
  __int64 v262; // rax
  __int64 v263; // rdx
  __int64 v264; // rax
  unsigned int v265; // ebx
  unsigned int v266; // ecx
  unsigned int v267; // eax
  unsigned __int16 v268; // dx
  __int16 v269; // ax
  _BYTE *v270; // rax
  __int64 v271; // rdx
  __int16 v272; // cx
  __int16 v273; // cx
  int v274; // eax
  struct RecVersioningInfo *v275; // rax
  __int64 v276; // rdx
  int v277; // r8d
  unsigned __int64 v278; // rdx
  int v279; // ecx
  __int64 v280; // rax
  __int64 v281; // rax
  __int64 v282; // rax
  __int64 v283; // rax
  char v284; // cl
  unsigned int v285; // ebx
  __int64 v286; // rax
  unsigned int v287; // ecx
  _BYTE *v288; // rax
  __int64 v289; // rdx
  __int64 v290; // rcx
  _DWORD *v291; // r8
  __int64 v292; // rax
  __int64 v293; // rcx
  _DWORD *v294; // r8
  __int64 v295; // rcx
  _DWORD *v296; // r8
  __int16 v297; // dx
  __int16 v298; // ax
  unsigned int v299; // r15d
  char *v300; // r8
  char v301; // dl
  int v302; // eax
  unsigned __int16 v303; // cx
  __int16 v304; // r8
  void *v305; // rsi
  unsigned int v306; // edx
  unsigned __int16 *v307; // rdi
  unsigned __int16 v308; // r8
  __int64 v309; // rax
  __int64 v310; // rax
  unsigned int v311; // r10d
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  unsigned int v317; // ebx
  unsigned __int16 v318; // r9
  struct RecVersioningInfo *v319; // rax
  __int64 v320; // rdx
  int v321; // r8d
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // rax
  __int64 v325; // rax
  char v326; // cl
  bool v327; // zf
  unsigned int v328; // eax
  unsigned __int16 *v329; // rdi
  unsigned __int16 v330; // r8
  __int64 v331; // rax
  __int64 v332; // rax
  unsigned int v333; // r10d
  __int64 v334; // rax
  __int64 v335; // rax
  __int64 v336; // rax
  __int64 v337; // rax
  __int64 v338; // rax
  unsigned int v339; // ebx
  unsigned __int16 v340; // r9
  struct RecVersioningInfo *v341; // rax
  __int64 v342; // rdx
  int v343; // r8d
  __int64 v344; // rax
  __int64 v345; // rax
  __int64 v346; // rax
  __int64 v347; // rax
  char v348; // cl
  bool v349; // zf
  unsigned int v350; // edx
  unsigned __int16 *v351; // rdi
  unsigned __int16 v352; // r8
  __int64 v353; // rax
  __int64 v354; // rax
  unsigned int v355; // r9d
  __int64 v356; // rax
  __int64 v357; // rax
  __int64 v358; // rax
  __int64 v359; // rax
  __int64 v360; // rax
  unsigned int v361; // ebx
  unsigned __int16 v362; // r10
  struct RecVersioningInfo *v363; // rax
  __int64 v364; // rdx
  int v365; // r8d
  __int64 v366; // rax
  __int64 v367; // rax
  __int64 v368; // rax
  __int64 v369; // rax
  char v370; // cl
  XDES *v371; // rbx
  int v372; // eax
  _DWORD *v373; // rax
  __int64 v374; // r13
  _BYTE *v375; // rcx
  unsigned int v376; // eax
  unsigned int v377; // eax
  unsigned int v378; // edx
  __int64 v379; // r8
  __int16 v380; // ax
  __int16 v381; // cx
  __int64 v382; // r8
  __int16 v383; // ax
  __int16 v384; // cx
  __int64 v385; // r8
  __int16 v386; // ax
  __int16 v387; // cx
  unsigned int v388; // ecx
  unsigned __int16 *v389; // rdi
  unsigned __int16 v390; // r8
  __int64 v391; // rax
  __int64 v392; // rax
  unsigned int v393; // r10d
  __int64 v394; // rax
  __int64 v395; // rax
  __int64 v396; // rax
  __int64 v397; // rax
  __int64 v398; // rax
  unsigned int v399; // ebx
  unsigned __int16 v400; // r9
  struct RecVersioningInfo *v401; // rax
  __int64 v402; // rdx
  int v403; // r8d
  __int64 v404; // rax
  __int64 v405; // rax
  __int64 v406; // rax
  __int64 v407; // rax
  char v408; // cl
  bool v409; // zf
  struct Record *v410; // r8
  char *v411; // rbx
  __int64 v412; // rdx
  char *v413; // r8
  char v414; // al
  int v415; // ecx
  unsigned __int16 *v416; // rsi
  unsigned __int16 v417; // ax
  __int64 v418; // rax
  __int64 v419; // rax
  unsigned int v420; // edx
  __int64 v421; // rax
  __int64 v422; // rax
  __int64 v423; // rcx
  unsigned int v424; // eax
  __int64 v425; // rax
  __int64 v426; // rax
  __int64 v427; // rdx
  __int64 v428; // rax
  unsigned int v429; // edi
  unsigned int v430; // ecx
  unsigned int v431; // eax
  unsigned __int16 v432; // dx
  __int16 v433; // ax
  __int64 v434; // r8
  __int16 v435; // ax
  __int16 v436; // cx
  __int64 v437; // rdx
  __int16 v438; // cx
  __int16 v439; // cx
  int v440; // eax
  struct RecVersioningInfo *v441; // rax
  __int64 v442; // rdx
  int v443; // r8d
  unsigned __int64 v444; // rdx
  int v445; // ecx
  __int64 v446; // rax
  __int64 v447; // rax
  __int64 v448; // rax
  __int64 v449; // rax
  char v450; // cl
  bool ModDiffForVersion; // al
  int v452; // eax
  unsigned int v453; // ecx
  _BYTE *v454; // rax
  struct Record *v455; // [rsp+20h] [rbp-E0h]
  struct Record *v456; // [rsp+20h] [rbp-E0h]
  struct Record *v457; // [rsp+20h] [rbp-E0h]
  struct Record *v458; // [rsp+28h] [rbp-D8h]
  __int16 v459; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v460; // [rsp+52h] [rbp-AEh] BYREF
  _DWORD SourceSize[3]; // [rsp+54h] [rbp-ACh]
  __int64 v462; // [rsp+60h] [rbp-A0h]
  unsigned int v463; // [rsp+68h] [rbp-98h]
  unsigned __int16 v464; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v465; // [rsp+6Eh] [rbp-92h]
  _TBYTE v466; // [rsp+76h] [rbp-8Ah]
  int v467; // [rsp+80h] [rbp-80h]
  unsigned int v468; // [rsp+88h] [rbp-78h] BYREF
  __int16 v469; // [rsp+8Ch] [rbp-74h]
  XDES *v470; // [rsp+90h] [rbp-70h]
  struct RecoveryUnit *v471; // [rsp+98h] [rbp-68h]
  VersionRecPtr *v472; // [rsp+A0h] [rbp-60h]
  __int64 v473; // [rsp+A8h] [rbp-58h]
  _DWORD *v474; // [rsp+B0h] [rbp-50h]
  unsigned int v475; // [rsp+B8h] [rbp-48h]
  Record *v476; // [rsp+C0h] [rbp-40h]
  __int64 v477; // [rsp+C8h] [rbp-38h]
  __int64 v478; // [rsp+D0h] [rbp-30h]
  _DWORD *v479; // [rsp+D8h] [rbp-28h]
  struct Record *v480; // [rsp+E0h] [rbp-20h]
  __int64 v481; // [rsp+E8h] [rbp-18h] BYREF
  void *Destination; // [rsp+F0h] [rbp-10h]
  int v483; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v484; // [rsp+FCh] [rbp-4h]
  __int16 v485; // [rsp+FEh] [rbp-2h]
  int v486; // [rsp+100h] [rbp+0h] BYREF
  __int16 v487; // [rsp+104h] [rbp+4h]
  __int16 v488; // [rsp+106h] [rbp+6h]
  _QWORD *v489; // [rsp+108h] [rbp+8h]
  __int64 v490; // [rsp+110h] [rbp+10h]
  int v491; // [rsp+118h] [rbp+18h] BYREF
  __int16 v492; // [rsp+11Ch] [rbp+1Ch]
  __int16 v493; // [rsp+11Eh] [rbp+1Eh]
  __int64 v494; // [rsp+120h] [rbp+20h]
  _BYTE v495[6]; // [rsp+128h] [rbp+28h] BYREF
  __int16 v496; // [rsp+12Eh] [rbp+2Eh]
  __int64 v497; // [rsp+170h] [rbp+70h]
  _BYTE v498[96]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v499[96]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v500[80]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v501; // [rsp+290h] [rbp+190h] BYREF
  __int16 v502; // [rsp+298h] [rbp+198h]
  unsigned __int8 v503[8096]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v497 = -2;
  v473 = a4;
  v470 = (XDES *)a3;
  v477 = a2;
  v476 = (Record *)a5;
  v480 = a9;
  v474 = a12;
  v472 = a13;
  Destination = a14;
  v494 = *(_QWORD *)(a3 + 208);
  if ( (*(_BYTE *)(a3 + 536) & 4) != 0 )
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 488LL))(a3) + 40;
  else
    v17 = a3 + 40;
  v18 = *(_DWORD *)v17;
  v19 = *(_WORD *)(v17 + 4);
  v20 = (FixedVarRecord *)(a5 + 2);
  v21 = a5 + 2;
  if ( *(_WORD *)a5 )
    CDRecord::GetXdesTs(v21, &v468);
  else
    FixedVarRecord::GetXdesTs(v21, &v468);
  v475 = (*a1 >> 3) & 1;
  v22 = v470;
  v471 = (struct RecoveryUnit *)*((_QWORD *)v470 + 6);
  v479 = 0;
  v478 = 0;
  v489 = 0;
  v490 = 0;
  *(_QWORD *)a13 = 0;
  if ( (v469 || v468) && (*(_WORD *)(a4 + 4) & 0x2000) == 0 )
    utassert_fail(1u, "pPage->IsFlag(PAGE::VERSION_INFO)", "RecVerMgr.cpp", 456, 0);
  v23 = *((_BYTE *)v22 + 592);
  if ( (v23 & 4) != 0 )
    goto LABEL_12;
  if ( (v23 & 0x5A) == 0 )
  {
    if ( (*((_BYTE *)v22 + 536) & 1) == 0 )
      goto LABEL_12;
    if ( !*((_QWORD *)v22 + 26)
      && (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 136LL))(v22)
      && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 24LL))(v22) )
    {
      *((_BYTE *)v22 + 592) |= 4u;
      goto LABEL_12;
    }
    if ( !(unsigned int)XDES::IsActive(v22) )
      (*(void (__fastcall **)(XDES *))(*(_QWORD *)v22 + 624LL))(v22);
    if ( (*((_BYTE *)v22 + 536) & 4) != 0 )
    {
      v49 = (XDES *)(*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 488LL))(v22);
      DoesXactGenVersion = XDES::DoesXactGenVersion(v49);
      v23 = *((_BYTE *)v22 + 592);
    }
    else
    {
      if ( (*((_BYTE *)v22 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v22 + 26)) )
      {
        v51 = *((_QWORD *)v22 + 26);
        if ( !*(_BYTE *)(v51 + 304) )
        {
          *(_BYTE *)(v51 + 304) = 1;
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v52 = 0;
            if ( pCounterLookupBlocks )
              v52 = (char *)pCounterLookupBlocks + 57344;
            if ( v52 && *(_QWORD *)v52 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v52 + 16LL), 1u);
          }
        }
      }
      v23 = *((_BYTE *)v22 + 592);
      DoesXactGenVersion = (v23 & 0x5A) != 0;
    }
    if ( !DoesXactGenVersion )
      goto LABEL_12;
  }
  if ( (v23 & 8) != 0 && (*a1 & 0x1C) == 0 )
  {
    v53 = *((_QWORD *)a1 + 1);
    if ( v53 )
    {
      v54 = *(_QWORD *)(v53 + 8);
      if ( *(int *)(v54 + 104) < 0 )
      {
        utassert_fail(1u, "m_pHoBt->m_verRefCount >= 0", "Sql\\Ntdbms\\storeng\\include\\schemamgr.inl", 3229, 0);
        v54 = *(_QWORD *)(v53 + 8);
        v53 = *((_QWORD *)a1 + 1);
      }
      if ( *(int *)(v54 + 104) > 0 )
      {
        v55 = *(_DWORD *)(*(_QWORD *)(v53 + 8) + 256LL);
        if ( v55 )
        {
          if ( (unsigned int)(v55 - 3) > 1 )
          {
            utassert_fail(
              1u,
              "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
              "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
              278,
              0);
            v53 = *((_QWORD *)a1 + 1);
          }
        }
      }
      v56 = *(_QWORD *)(v53 + 8);
      if ( (*(char *)(v56 + 65) < 0 || (*(_BYTE *)(v56 + 265) & 1) != 0) && (*(_BYTE *)(v56 + 265) & 1) == 0 )
      {
        v57 = *(_DWORD *)(v56 + 256);
        if ( v57 )
        {
          if ( (unsigned int)(v57 - 3) > 1 )
            utassert_fail(
              1u,
              "(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAcc"
              "ess->IsCompressedRowstore ()",
              "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
              281,
              0);
        }
      }
    }
    v22 = v470;
    if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v470 + 16LL))(v470) )
    {
      v24 = 1;
      goto LABEL_13;
    }
  }
LABEL_12:
  v24 = 0;
LABEL_13:
  v25 = 0;
  v26 = *((_BYTE *)v22 + 592);
  if ( (v26 & 4) != 0 )
    goto LABEL_16;
  if ( (v26 & 0x5A) != 0 )
    goto LABEL_15;
  if ( (*((_BYTE *)v22 + 536) & 1) == 0 )
  {
LABEL_16:
    v27 = 0;
    goto LABEL_17;
  }
  if ( !*((_QWORD *)v22 + 26)
    && (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 136LL))(v22)
    && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 24LL))(v22) )
  {
    *((_BYTE *)v22 + 592) |= 4u;
    goto LABEL_16;
  }
  if ( !(unsigned int)XDES::IsActive(v22) )
    (*(void (__fastcall **)(XDES *))(*(_QWORD *)v22 + 624LL))(v22);
  if ( (*((_BYTE *)v22 + 536) & 4) != 0 )
  {
    v58 = (XDES *)(*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 488LL))(v22);
    v59 = XDES::DoesXactGenVersion(v58);
  }
  else
  {
    if ( (*((_BYTE *)v22 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v22 + 26)) )
    {
      v60 = *((_QWORD *)v22 + 26);
      if ( !*(_BYTE *)(v60 + 304) )
      {
        *(_BYTE *)(v60 + 304) = 1;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v61 = 0;
          if ( pCounterLookupBlocks )
            v61 = (char *)pCounterLookupBlocks + 57344;
          if ( v61 && *(_QWORD *)v61 )
            _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v61 + 16LL), 1u);
        }
      }
    }
    v59 = (*((_BYTE *)v22 + 592) & 0x5A) != 0;
  }
  if ( !v59 )
    goto LABEL_16;
LABEL_15:
  if ( (*((_BYTE *)v22 + 592) & 0x40) == 0 || (*a1 & 0x1C) != 0 )
    goto LABEL_16;
  v62 = *((_QWORD *)a1 + 1);
  if ( v62 )
  {
    v63 = *(_QWORD *)(v62 + 8);
    v64 = *(_DWORD *)(v63 + 104) <= 0;
    if ( *(int *)(v63 + 104) < 0 )
    {
      utassert_fail(1u, "m_pHoBt->m_verRefCount >= 0", "Sql\\Ntdbms\\storeng\\include\\schemamgr.inl", 3229, 0);
      v65 = *(_QWORD *)(v62 + 8);
      v62 = *((_QWORD *)a1 + 1);
      v64 = *(_DWORD *)(v65 + 104) <= 0;
    }
    if ( !v64 )
    {
      v66 = *(_DWORD *)(*(_QWORD *)(v62 + 8) + 256LL);
      if ( v66 )
      {
        if ( (unsigned int)(v66 - 3) > 1 )
        {
          utassert_fail(
            1u,
            "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
            "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
            278,
            0);
          v62 = *((_QWORD *)a1 + 1);
        }
      }
    }
    v67 = *(_QWORD *)(v62 + 8);
    if ( (*(char *)(v67 + 65) < 0 || (*(_BYTE *)(v67 + 265) & 1) != 0) && (*(_BYTE *)(v67 + 265) & 1) == 0 )
    {
      v68 = *(_DWORD *)(v67 + 256);
      if ( v68 )
      {
        if ( (unsigned int)(v68 - 3) > 1 )
          utassert_fail(
            1u,
            "(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAcces"
            "s->IsCompressedRowstore ()",
            "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
            281,
            0);
      }
    }
  }
  if ( v494 && (*(int *)(v494 + 120) > 0 || *(int *)(v494 + 116) > 0) )
  {
    v22 = v470;
    goto LABEL_16;
  }
  v27 = 1;
  v22 = v470;
  if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v470 + 136LL))(v470) )
    utassert_fail(1u, "!xdes->DoesXactSupportCTR()", "RecVerMgr.cpp", 498, 0);
  v69 = *((_BYTE *)v22 + 592);
  if ( (v69 & 4) != 0 )
    goto LABEL_17;
  if ( (v69 & 0x5A) != 0 )
    goto LABEL_152;
  if ( (*((_BYTE *)v22 + 536) & 1) != 0 )
  {
    if ( !*((_QWORD *)v22 + 26)
      && (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 136LL))(v22)
      && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 24LL))(v22) )
    {
      *((_BYTE *)v22 + 592) |= 4u;
LABEL_139:
      v69 = *((_BYTE *)v22 + 592);
      goto LABEL_140;
    }
    if ( !(unsigned int)XDES::IsActive(v22) )
      (*(void (__fastcall **)(XDES *))(*(_QWORD *)v22 + 624LL))(v22);
    if ( (*((_BYTE *)v22 + 536) & 4) != 0 )
    {
      v70 = (XDES *)(*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 488LL))(v22);
      v71 = XDES::DoesXactGenVersion(v70);
      v69 = *((_BYTE *)v22 + 592);
    }
    else
    {
      if ( (*((_BYTE *)v22 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v22 + 26)) )
      {
        v72 = *((_QWORD *)v22 + 26);
        if ( !*(_BYTE *)(v72 + 304) )
        {
          *(_BYTE *)(v72 + 304) = 1;
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v73 = 0;
            if ( pCounterLookupBlocks )
              v73 = (char *)pCounterLookupBlocks + 57344;
            if ( v73 && *(_QWORD *)v73 )
              _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v73 + 16LL), 1u);
          }
        }
      }
      v69 = *((_BYTE *)v22 + 592);
      v71 = (v69 & 0x5A) != 0;
    }
    if ( !v71 )
      goto LABEL_140;
LABEL_152:
    if ( (v69 & 0x10) == 0 )
      goto LABEL_140;
    utassert_fail(1u, "!xdes->DoesXactGenVersionForCTROnly()", "RecVerMgr.cpp", 499, 0);
    goto LABEL_139;
  }
LABEL_140:
  if ( (v69 & 4) == 0 )
  {
    if ( (v69 & 0x5A) != 0 )
      goto LABEL_169;
    if ( (*((_BYTE *)v22 + 536) & 1) != 0 )
    {
      if ( !*((_QWORD *)v22 + 26)
        && (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 136LL))(v22)
        && !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 24LL))(v22) )
      {
        *((_BYTE *)v22 + 592) |= 4u;
        goto LABEL_17;
      }
      if ( !(unsigned int)XDES::IsActive(v22) )
        (*(void (__fastcall **)(XDES *))(*(_QWORD *)v22 + 624LL))(v22);
      if ( (*((_BYTE *)v22 + 536) & 4) != 0 )
      {
        v74 = (XDES *)(*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 488LL))(v22);
        v75 = XDES::DoesXactGenVersion(v74);
      }
      else
      {
        if ( (*((_BYTE *)v22 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v22 + 26)) )
        {
          v76 = *((_QWORD *)v22 + 26);
          if ( !*(_BYTE *)(v76 + 304) )
          {
            *(_BYTE *)(v76 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v77 = 0;
              if ( pCounterLookupBlocks )
                v77 = (char *)pCounterLookupBlocks + 57344;
              if ( v77 && *(_QWORD *)v77 )
                _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v77 + 16LL), 1u);
            }
          }
        }
        v75 = (*((_BYTE *)v22 + 592) & 0x5A) != 0;
      }
      if ( v75 )
      {
LABEL_169:
        if ( (*((_BYTE *)v22 + 592) & 8) != 0 )
          utassert_fail(1u, "!xdes->DoesXactGenVersionForHadronReadSecOnly()", "RecVerMgr.cpp", 500, 0);
      }
    }
  }
LABEL_17:
  if ( !(*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v22 + 136LL))(v22) && v469 == v19 && v468 == v18 )
  {
    if ( *(_WORD *)v476 )
      CDRecord::GetVersionRecPtr(v20, &v483);
    else
      FixedVarRecord::GetVersionRecPtr(v20, &v483);
    v491 = v483;
    v492 = v484;
    v493 = v485;
    v501 = 0;
    v502 = 0;
    CtrNestIdFromVersionRecPtr = VersionMgr::GetCtrNestIdFromVersionRecPtr(
                                   (const struct VersionRecPtr *)&v491,
                                   *((struct RecoveryUnit **)v22 + 6),
                                   v78,
                                   (const struct LSN *)&v501,
                                   (struct VersionRecPtr *)&v481,
                                   0);
    v156 = (*(unsigned int (__fastcall **)(XDES *))(*(_QWORD *)v470 + 80LL))(v470) == CtrNestIdFromVersionRecPtr;
    v22 = v470;
    if ( !v156 )
    {
      v25 = 1;
      ++*((_QWORD *)v471 + 120);
    }
  }
  else
  {
    v481 = 0;
  }
  v29 = a6;
  v30 = 0x4000;
  if ( (v469 != v19 || v468 != v18) && !v24 && !v27
    || v494 && (*(int *)(v494 + 120) > 0 || *(int *)(v494 + 116) > 0)
    || v25 )
  {
    v31 = a10;
    v32 = a11;
    if ( a10 )
    {
      if ( a10 == 1 )
      {
        if ( (*((_BYTE *)v22 + 536) & 4) != 0 )
        {
          v103 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**((_QWORD **)v22 + 82) + 368LL))(
                             *((_QWORD *)v22 + 82),
                             v28,
                             a6,
                             0x4000);
        }
        else
        {
          v104 = *((_QWORD *)v22 + 26);
          if ( v104 )
            v103 = (_QWORD *)(v104 + 336);
          else
            v103 = 0;
        }
        v489 = v103;
        HIDWORD(v490) = 4;
        LODWORD(v458) = 0;
        v455 = 0;
        LODWORD(v490) = LatchBase::AcquireInternal(v103, 4, 0xFFFFFFFFLL);
        if ( a11 < 2 )
        {
          v479 = (_DWORD *)v103[4];
          v478 = v103[5];
          v29 = a6;
        }
        else if ( a11 == 2 )
        {
          v479 = (_DWORD *)v103[6];
          v478 = v103[7];
          v29 = a6;
        }
        else
        {
          if ( a11 == 3 )
          {
            v479 = (_DWORD *)v103[8];
            v478 = v103[9];
          }
          else
          {
            utassert_fail(
              1u,
              "FALSE",
              "Sql\\Ntdbms\\storeng\\include\\XactVerMgr.inl",
              372,
              "Invalid switch value",
              v458,
              0,
              0,
              0);
          }
          v29 = a6;
        }
      }
      else
      {
        utassert_fail(1u, "FALSE", "RecVerMgr.cpp", 553, "Invalid switch value");
        v29 = a6;
      }
    }
    if ( Destination && (_DWORD)v29 != 2 )
    {
      v33 = v470;
      v80 = (*(__int64 (__fastcall **)(XDES *, __int64, __int64, __int64, struct Record *))(*(_QWORD *)v470 + 80LL))(
              v470,
              v28,
              v29,
              v30,
              v455);
      v81 = v472;
      *(_DWORD *)v472 = v80;
      v82 = DestinationSize;
      *((_WORD *)v81 + 2) = (32 * DestinationSize) | 2;
      *((_WORD *)v81 + 3) = -4;
      v83 = v471;
      ++*((_QWORD *)v471 + 19);
      if ( (byte_10317AD6E & 2) == 0 )
      {
        v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( !*(_QWORD *)v84
          || (v85 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v84 + 56LL)) == 0
          || !CSessionTraceFlags::CheckSessionTraceInternal(v85, 0xF71u) )
        {
          v82 = DestinationSize;
LABEL_205:
          if ( (qword_10317F738 & 0x400000000000000LL) != 0 )
          {
            v94 = *((_QWORD *)v33 + 82);
            if ( (*((_BYTE *)v33 + 536) & 4) != 0 )
              v95 = (unsigned int *)((*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v33 + 488LL))(v33) + 40);
            else
              v95 = (unsigned int *)((char *)v33 + 40);
            v96 = *v95 + ((unsigned __int64)*((unsigned __int16 *)v95 + 2) << 32);
            v97 = *((unsigned __int16 *)v83 + 860);
            v98 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v94 + 312LL))(v94);
            PersistVerStore::XeventTrace(
              v97,
              (const wchar_t *)(*((_QWORD *)v83 + 214) + 936LL),
              L"PVS(InRowDiff) generates in-row version diff %d bytes (xactid=%I64d, xdesTs=%I64d) rowsetid=%I64d",
              v82,
              v98,
              v96,
              v477);
          }
          v39 = v471;
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v99 = *((unsigned __int16 *)v471 + 860);
            _mm_lfence();
            v100 = (__int64)*(&pCounterLookupBlocks + (v99 >> 8));
            if ( v100 )
            {
              v101 = v100 + 8LL * (unsigned __int8)v99 + 10240;
              if ( v101 )
              {
                if ( *(_QWORD *)v101 )
                {
                  _mm_lfence();
                  _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v101 + 704LL), 1u);
                  if ( (g_fObjectHasTotalInstance & 0x20) != 0 )
                  {
                    v102 = 0;
                    if ( pCounterLookupBlocks )
                      v102 = (char *)pCounterLookupBlocks + 10240;
                    if ( v102 && *(_QWORD *)v102 )
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v102 + 704LL), 1u);
                  }
                }
              }
            }
          }
          goto LABEL_219;
        }
        v82 = DestinationSize;
      }
      v86 = *((_QWORD *)v33 + 82);
      v87 = *(_DWORD *)(*((_QWORD *)v33 + 6) + 1720LL);
      if ( (*((_BYTE *)v33 + 536) & 4) != 0 )
        v88 = (unsigned int *)((*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v33 + 488LL))(v33) + 40);
      else
        v88 = (unsigned int *)((char *)v33 + 40);
      v89 = *v88 + ((unsigned __int64)*((unsigned __int16 *)v88 + 2) << 32);
      v90 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 312LL))(v86);
      LODWORD(v457) = v87;
      LogSystemMetadata(
        L"Generate in-row version diff %d bytes (xactid=%I64d, xdesTs=%I64d, dbid= %d rowsetid=%I64d)\n",
        v82,
        v90,
        v89,
        v457,
        v477);
      CDStream::CDStream((CDStream *)v498);
      ProcessHeap = GetProcessHeap();
      v92 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
      Destination = v92;
      if ( v92 )
        v92 = CTracePrintStream::CTracePrintStream(v92, 0);
      v93 = v92;
      if ( v92 && !CDStream::AddDevice((CDStream *)v498, v92) )
        (**(void (__fastcall ***)(CTracePrintStream *, __int64))v93)(v93, 1);
      Record::Dump(v476, (struct CDStream *)v498);
      CDStream::~CDStream((CDStream *)v498);
      goto LABEL_205;
    }
    v33 = v470;
    v34 = (*(__int64 (__fastcall **)(XDES *, __int64, __int64, __int64, struct Record *))(*(_QWORD *)v470 + 32LL))(
            v470,
            v28,
            v29,
            v30,
            v455);
    v35 = v478;
    v36 = v476;
    if ( v34 && a6 != 1 && !v478 && a8 != 1 )
    {
      v114 = (_BYTE *)*((_QWORD *)v476 + 1);
      v115 = 0;
      if ( *(_WORD *)v476 )
      {
        LOBYTE(v115) = (((*v114 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
      }
      else
      {
        v116 = *v114 & 0xE;
        if ( v116 == 2 )
        {
          v115 = (v114[1] & 1) != 0;
        }
        else if ( ((v116 - 10) & 0xF9) == 0 )
        {
          v115 = v478 + 1;
        }
      }
      if ( !v115 && (a7 || a6 != 2) )
      {
        v37 = v473;
        v117 = *(_BYTE *)(v473 + 1);
        if ( v117 != 1 && (v117 != 2 || *(_BYTE *)(v473 + 3) || *(_WORD *)(v473 + 6) <= 1u) || v469 || v468 )
          goto LABEL_27;
        if ( *(_WORD *)v476 )
          CDRecord::GetVersionRecPtr(v20, v495);
        else
          FixedVarRecord::GetVersionRecPtr(v20, v495);
        v118 = v496;
        if ( ((v496 ^ ((unsigned int)v496 >> 1)) & 0x2000) != 0 )
        {
          if ( (v496 & 0x4000) != 0 )
            v118 = v496 | 0x2000;
          else
            v118 = v496 & 0xDFFF;
        }
        if ( v118 == -4 )
          goto LABEL_27;
        if ( !*(_WORD *)v36 )
        {
          if ( *(_DWORD *)(a5 + 4) )
            goto LABEL_359;
          *(_WORD *)v20 = 0;
          v119 = *(unsigned int *)(a5 + 16);
          *(_DWORD *)(a5 + 20) = v119;
          v120 = *(char **)(a5 + 8);
          v121 = *v120;
          v122 = v119;
          if ( (*v120 & 0x10) != 0 )
          {
            LODWORD(v119) = (((unsigned int)*(unsigned __int16 *)&v120[v119] + 7) >> 3) + v119 + 2;
            *(_DWORD *)(a5 + 20) = v119;
            v121 = *v120;
            v122 = v119;
          }
          if ( (v121 & 0x20) == 0 )
          {
            *(_DWORD *)(a5 + 4) = v119;
            *(_WORD *)(a5 + 28) = 0;
            *(_DWORD *)(a5 + 24) = v122;
            goto LABEL_331;
          }
          v123 = (unsigned __int16 *)&v120[(unsigned int)v119];
          v124 = *v123;
          *(_WORD *)(a5 + 28) = *v123;
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
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 3);
            v124 = *(_WORD *)(a5 + 28);
            v122 = *(_DWORD *)(a5 + 20);
          }
          v127 = v122 + 2 * (v124 + 1);
          *(_DWORD *)(a5 + 24) = v127;
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
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
            v127 = *(_DWORD *)(a5 + 24);
          }
          v130 = *(unsigned __int16 *)(a5 + 28);
          v131 = v123[v130] & 0x7FFF;
          *(_DWORD *)(a5 + 4) = v131;
          if ( v127 > v131 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v132 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v132 )
              {
                v133 = *(_QWORD *)(v132 + 96);
                if ( v133 )
                {
                  if ( *(_BYTE *)(v133 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
            LOWORD(v130) = *(_WORD *)(a5 + 28);
          }
          while ( 1 )
          {
            v134 = (unsigned __int16)v130;
            if ( (v123[(unsigned __int16)v130] & 0x8000u) == 0 )
              goto LABEL_330;
            v135 = *(_QWORD *)(a5 + 8) + *(unsigned int *)(a5 + 20);
            if ( (unsigned __int16)v130 == 1 )
            {
              v136 = *(_DWORD *)(a5 + 24);
              v137 = v136;
              v138 = *(_WORD *)(v135 + 2 * v134) & 0x7FFF;
            }
            else
            {
              v136 = *(_WORD *)(v135 + 2LL * (unsigned __int16)v130 - 2) & 0x7FFF;
              v137 = *(_DWORD *)(a5 + 24);
              v138 = *(_WORD *)(v135 + 2 * v134) & 0x7FFF;
              if ( v136 < v137 )
              {
LABEL_311:
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 7);
                v137 = *(_DWORD *)(a5 + 24);
                goto LABEL_312;
              }
            }
            if ( v138 < v136 )
              goto LABEL_311;
LABEL_312:
            if ( v136 < v137 || v136 > *(_DWORD *)(a5 + 4) )
              goto LABEL_359;
            v139 = *(_WORD *)(v136 + *(_QWORD *)(a5 + 8));
            if ( v139 == 5 )
            {
              *(_WORD *)v20 |= 2u;
              --*(_WORD *)(a5 + 28);
              *(_WORD *)(a5 + 42) = v136;
              v141 = *(_QWORD *)(a5 + 8) + (unsigned __int16)v136;
              v142 = *(_WORD *)(v141 + 2);
              if ( (v142 & 0x4000) != 0 )
                v143 = *(_WORD *)(a5 + 44) & 0xC7FF | v142 & 0x3800;
              else
                v143 = *(_WORD *)(a5 + 44) & 0xC7FF;
              *(_WORD *)(a5 + 44) = v143;
              *(_WORD *)(a5 + 44) = v143 ^ (*(_WORD *)(v141 + 2) ^ v143) & 0x7FF;
LABEL_330:
              v120 = *(char **)(a5 + 8);
LABEL_331:
              if ( (*v120 & 0x40) != 0 )
              {
                v144 = *(_DWORD *)(a5 + 4);
                *(_DWORD *)(a5 + 38) = v144;
                *(_DWORD *)(a5 + 4) = v144 + 14;
                VersioningInfo = FixedVarRecord::FindVersioningInfo(v20);
                v146 = HIWORD(*(_QWORD *)VersioningInfo);
                v147 = 0;
                if ( (((__int16)v146 ^ ((unsigned int)(__int16)v146 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v146 & 0x4000) != 0 )
                    LOWORD(v146) = v146 | 0x2000;
                  else
                    LOWORD(v146) = v146 & 0xDFFF;
                }
                if ( (_WORD)v146 == 0xFFFC )
                  v147 = (unsigned __int16)WORD2(*(_QWORD *)VersioningInfo) >> 5;
                *(_DWORD *)(a5 + 4) += v147;
              }
              else
              {
                *(_DWORD *)(a5 + 38) = 0;
              }
              v148 = *(_QWORD *)(a5 + 30);
              v149 = *(_DWORD *)(a5 + 4);
              if ( v148 && v148 < *(_QWORD *)(a5 + 8) + (unsigned __int64)*(unsigned int *)(a5 + 4) )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v150 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v150 )
                  {
                    v151 = *(_QWORD *)(v150 + 96);
                    if ( v151 )
                    {
                      if ( *(_BYTE *)(v151 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 18);
                v149 = *(_DWORD *)(a5 + 4);
              }
              if ( (unsigned int)(v149 - 1) > 0x3F3B )
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
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 5);
              }
LABEL_359:
              v154 = *(_DWORD *)(a5 + 4);
              v468 = 9;
              if ( v154 < 9 )
              {
                v155 = **(_BYTE **)(a5 + 8) & 0xE;
                if ( v155 )
                {
                  v156 = v155 == 12;
                  goto LABEL_362;
                }
                goto LABEL_363;
              }
LABEL_422:
              v157 = v154;
              goto LABEL_364;
            }
            if ( v139 < 0x400u )
              goto LABEL_330;
            *(_WORD *)v20 |= 1u;
            v140 = *(_WORD *)(a5 + 28) - 1;
            *(_WORD *)(a5 + 28) = v140;
            if ( !v140 )
              goto LABEL_330;
            LOWORD(v130) = v140;
          }
        }
        v154 = *(_DWORD *)(a5 + 4);
        if ( !v154 )
        {
          CDRecord::Resize(v20);
          v154 = *(_DWORD *)(a5 + 4);
        }
        v468 = 9;
        if ( v154 >= 9 )
          goto LABEL_422;
        v180 = *(_BYTE **)(a5 + 8);
        if ( (*v180 & 0x1C) != 0 )
        {
          v156 = (*v180 & 0x1C) == 12;
LABEL_362:
          if ( !v156 )
            goto LABEL_422;
        }
LABEL_363:
        v157 = 9;
LABEL_364:
        if ( v157 <= 0x14 )
        {
          if ( *(_WORD *)v36 )
          {
            if ( !v154 )
            {
              CDRecord::Resize(v20);
              v154 = *(_DWORD *)(a5 + 4);
            }
            if ( v154 < 9 )
            {
              v224 = *(_BYTE **)(a5 + 8);
              if ( (*v224 & 0x1C) == 0 || (*v224 & 0x1C) == 0xC )
                LOWORD(v154) = 9;
            }
            goto LABEL_464;
          }
          if ( v154 )
            goto LABEL_460;
          *(_WORD *)v20 = 0;
          v158 = *(unsigned int *)(a5 + 16);
          *(_DWORD *)(a5 + 20) = v158;
          v159 = *(char **)(a5 + 8);
          v160 = *v159;
          v161 = v158;
          if ( (*v159 & 0x10) != 0 )
          {
            LODWORD(v158) = (((unsigned int)*(unsigned __int16 *)&v159[v158] + 7) >> 3) + v158 + 2;
            *(_DWORD *)(a5 + 20) = v158;
            v160 = *v159;
            v161 = v158;
          }
          if ( (v160 & 0x20) == 0 )
          {
            *(_DWORD *)(a5 + 4) = v158;
            *(_WORD *)(a5 + 28) = 0;
            *(_DWORD *)(a5 + 24) = v161;
            goto LABEL_432;
          }
          v162 = (unsigned __int16 *)&v159[(unsigned int)v158];
          v163 = *v162;
          *(_WORD *)(a5 + 28) = *v162;
          if ( !v163 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v164 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v164 )
              {
                v165 = *(_QWORD *)(v164 + 96);
                if ( v165 )
                {
                  if ( *(_BYTE *)(v165 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 3);
            v163 = *(_WORD *)(a5 + 28);
            v161 = *(_DWORD *)(a5 + 20);
          }
          v166 = v161 + 2 * (v163 + 1);
          *(_DWORD *)(a5 + 24) = v166;
          if ( v166 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v167 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v167 )
              {
                v168 = *(_QWORD *)(v167 + 96);
                if ( v168 )
                {
                  if ( *(_BYTE *)(v168 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
            v166 = *(_DWORD *)(a5 + 24);
          }
          v169 = *(unsigned __int16 *)(a5 + 28);
          v170 = v162[v169] & 0x7FFF;
          *(_DWORD *)(a5 + 4) = v170;
          if ( v166 > v170 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v171 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v171 )
              {
                v172 = *(_QWORD *)(v171 + 96);
                if ( v172 )
                {
                  if ( *(_BYTE *)(v172 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
            LOWORD(v169) = *(_WORD *)(a5 + 28);
          }
          while ( 1 )
          {
            v173 = (unsigned __int16)v169;
            if ( (v162[(unsigned __int16)v169] & 0x8000u) == 0 )
              goto LABEL_431;
            v174 = *(_QWORD *)(a5 + 8) + *(unsigned int *)(a5 + 20);
            if ( (unsigned __int16)v169 == 1 )
            {
              v175 = *(_DWORD *)(a5 + 24);
              v176 = v175;
              v177 = *(_WORD *)(v174 + 2 * v173) & 0x7FFF;
            }
            else
            {
              v175 = *(_WORD *)(v174 + 2LL * (unsigned __int16)v169 - 2) & 0x7FFF;
              v176 = *(_DWORD *)(a5 + 24);
              v177 = *(_WORD *)(v174 + 2 * v173) & 0x7FFF;
              if ( v175 < v176 )
              {
LABEL_404:
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 7);
                v176 = *(_DWORD *)(a5 + 24);
                goto LABEL_405;
              }
            }
            if ( v177 < v175 )
              goto LABEL_404;
LABEL_405:
            if ( v175 < v176 || v175 > *(_DWORD *)(a5 + 4) )
              goto LABEL_460;
            v178 = *(_WORD *)(v175 + *(_QWORD *)(a5 + 8));
            if ( v178 == 5 )
            {
              *(_WORD *)v20 |= 2u;
              --*(_WORD *)(a5 + 28);
              *(_WORD *)(a5 + 42) = v175;
              v181 = *(_QWORD *)(a5 + 8) + (unsigned __int16)v175;
              v182 = *(_WORD *)(v181 + 2);
              if ( (v182 & 0x4000) != 0 )
                v183 = *(_WORD *)(a5 + 44) & 0xC7FF | v182 & 0x3800;
              else
                v183 = *(_WORD *)(a5 + 44) & 0xC7FF;
              *(_WORD *)(a5 + 44) = v183;
              *(_WORD *)(a5 + 44) = v183 ^ (*(_WORD *)(v181 + 2) ^ v183) & 0x7FF;
LABEL_431:
              v159 = *(char **)(a5 + 8);
LABEL_432:
              if ( (*v159 & 0x40) != 0 )
              {
                *(_DWORD *)(a5 + 38) = *(_DWORD *)(a5 + 4);
                *(_DWORD *)(a5 + 4) += 14;
                v184 = FixedVarRecord::FindVersioningInfo(v20);
                v185 = HIWORD(*(_QWORD *)v184);
                v186 = 0;
                if ( (((__int16)v185 ^ ((unsigned int)(__int16)v185 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v185 & 0x4000) != 0 )
                    LOWORD(v185) = v185 | 0x2000;
                  else
                    LOWORD(v185) = v185 & 0xDFFF;
                }
                if ( (_WORD)v185 == 0xFFFC )
                  v186 = (unsigned __int16)WORD2(*(_QWORD *)v184) >> 5;
                *(_DWORD *)(a5 + 4) += v186;
              }
              else
              {
                *(_DWORD *)(a5 + 38) = 0;
              }
              v187 = *(_QWORD *)(a5 + 30);
              v188 = *(_DWORD *)(a5 + 4);
              if ( v187 && v187 < *(_QWORD *)(a5 + 8) + (unsigned __int64)*(unsigned int *)(a5 + 4) )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v189 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v189 )
                  {
                    v190 = *(_QWORD *)(v189 + 96);
                    if ( v190 )
                    {
                      if ( *(_BYTE *)(v190 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 18);
                v188 = *(_DWORD *)(a5 + 4);
              }
              if ( (unsigned int)(v188 - 1) > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v191 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v191 )
                  {
                    v192 = *(_QWORD *)(v191 + 96);
                    if ( v192 )
                    {
                      if ( *(_BYTE *)(v192 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 5);
              }
LABEL_460:
              v154 = *(_DWORD *)(a5 + 4);
              if ( v154 < 9 )
              {
                v193 = **(_BYTE **)(a5 + 8) & 0xE;
                if ( !v193 || v193 == 12 )
                  LOWORD(v154) = 9;
              }
LABEL_464:
              v194 = (*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v33 + 80LL))(v33);
              v195 = v472;
              *(_DWORD *)v472 = v194;
              *((_WORD *)v195 + 2) = (32 * v154) | 1;
              *((_WORD *)v195 + 3) = -4;
              if ( (byte_10317AD6E & 2) != 0
                || (v196 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset,
                    *(_QWORD *)v196)
                && (v197 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v196 + 56LL)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v197, 0xF71u) )
              {
                v198 = *((_QWORD *)v33 + 82);
                v199 = *(_DWORD *)(*((_QWORD *)v33 + 6) + 1720LL);
                if ( (*((_BYTE *)v33 + 536) & 4) != 0 )
                  v200 = (unsigned int *)((*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v33 + 488LL))(v33) + 40);
                else
                  v200 = (unsigned int *)((char *)v33 + 40);
                v201 = *v200 + ((unsigned __int64)*((unsigned __int16 *)v200 + 2) << 32);
                if ( !*(_WORD *)v36 )
                {
                  if ( *(_DWORD *)(a5 + 4) )
                    goto LABEL_566;
                  *(_WORD *)v20 = 0;
                  v202 = *(unsigned int *)(a5 + 16);
                  *(_DWORD *)(a5 + 20) = v202;
                  v203 = *(char **)(a5 + 8);
                  v204 = *v203;
                  v205 = v202;
                  if ( (*v203 & 0x10) != 0 )
                  {
                    LODWORD(v202) = (((unsigned int)*(unsigned __int16 *)&v203[v202] + 7) >> 3) + v202 + 2;
                    *(_DWORD *)(a5 + 20) = v202;
                    v204 = *v203;
                    v205 = v202;
                  }
                  if ( (v204 & 0x20) == 0 )
                  {
                    *(_DWORD *)(a5 + 4) = v202;
                    *(_WORD *)(a5 + 28) = 0;
                    *(_DWORD *)(a5 + 24) = v205;
                    goto LABEL_538;
                  }
                  v206 = (unsigned __int16 *)&v203[(unsigned int)v202];
                  v207 = *v206;
                  *(_WORD *)(a5 + 28) = *v206;
                  if ( !v207 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v208 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v208 )
                      {
                        v209 = *(_QWORD *)(v208 + 96);
                        if ( v209 )
                        {
                          if ( *(_BYTE *)(v209 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                            else
                              ex_raise(34, 68, 21, 1003);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 3);
                    v207 = *(_WORD *)(a5 + 28);
                    v205 = *(_DWORD *)(a5 + 20);
                  }
                  v210 = v205 + 2 * (v207 + 1);
                  *(_DWORD *)(a5 + 24) = v210;
                  if ( v210 > 0x1F9E )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v211 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v211 )
                      {
                        v212 = *(_QWORD *)(v211 + 96);
                        if ( v212 )
                        {
                          if ( *(_BYTE *)(v212 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
                    v210 = *(_DWORD *)(a5 + 24);
                  }
                  v213 = *(unsigned __int16 *)(a5 + 28);
                  v214 = v206[v213] & 0x7FFF;
                  *(_DWORD *)(a5 + 4) = v214;
                  if ( v210 > v214 )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v215 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v215 )
                      {
                        v216 = *(_QWORD *)(v215 + 96);
                        if ( v216 )
                        {
                          if ( *(_BYTE *)(v216 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                            else
                              ex_raise(34, 68, 21, 1004);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
                    LOWORD(v213) = *(_WORD *)(a5 + 28);
                  }
                  while ( 1 )
                  {
                    v217 = (unsigned __int16)v213;
                    if ( (v206[(unsigned __int16)v213] & 0x8000u) == 0 )
                      goto LABEL_537;
                    v218 = *(_QWORD *)(a5 + 8) + *(unsigned int *)(a5 + 20);
                    if ( (unsigned __int16)v213 == 1 )
                    {
                      v219 = *(_DWORD *)(a5 + 24);
                      v220 = v219;
                      v221 = *(_WORD *)(v218 + 2 * v217) & 0x7FFF;
                    }
                    else
                    {
                      v219 = *(_WORD *)(v218 + 2LL * (unsigned __int16)v213 - 2) & 0x7FFF;
                      v220 = *(_DWORD *)(a5 + 24);
                      v221 = *(_WORD *)(v218 + 2 * v217) & 0x7FFF;
                      if ( v219 < v220 )
                      {
LABEL_509:
                        RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 7);
                        v220 = *(_DWORD *)(a5 + 24);
                        goto LABEL_510;
                      }
                    }
                    if ( v221 < v219 )
                      goto LABEL_509;
LABEL_510:
                    if ( v219 < v220 || v219 > *(_DWORD *)(a5 + 4) )
                      goto LABEL_566;
                    v222 = *(_WORD *)(v219 + *(_QWORD *)(a5 + 8));
                    if ( v222 == 5 )
                    {
                      *(_WORD *)v20 |= 2u;
                      --*(_WORD *)(a5 + 28);
                      *(_WORD *)(a5 + 42) = v219;
                      v225 = *(_QWORD *)(a5 + 8) + (unsigned __int16)v219;
                      v226 = *(_WORD *)(v225 + 2);
                      if ( (v226 & 0x4000) != 0 )
                        v227 = *(_WORD *)(a5 + 44) & 0xC7FF | v226 & 0x3800;
                      else
                        v227 = *(_WORD *)(a5 + 44) & 0xC7FF;
                      *(_WORD *)(a5 + 44) = v227;
                      *(_WORD *)(a5 + 44) = v227 ^ (*(_WORD *)(v225 + 2) ^ v227) & 0x7FF;
LABEL_537:
                      v203 = *(char **)(a5 + 8);
LABEL_538:
                      if ( (*v203 & 0x40) != 0 )
                      {
                        v228 = *(_DWORD *)(a5 + 4);
                        *(_DWORD *)(a5 + 38) = v228;
                        *(_DWORD *)(a5 + 4) = v228 + 14;
                        v229 = FixedVarRecord::FindVersioningInfo(v20);
                        v230 = HIWORD(*(_QWORD *)v229);
                        v231 = 0;
                        if ( (((__int16)v230 ^ ((unsigned int)(__int16)v230 >> 1)) & 0x2000) != 0 )
                        {
                          if ( (v230 & 0x4000) != 0 )
                            LOWORD(v230) = v230 | 0x2000;
                          else
                            LOWORD(v230) = v230 & 0xDFFF;
                        }
                        if ( (_WORD)v230 == 0xFFFC )
                          v231 = (unsigned __int16)WORD2(*(_QWORD *)v229) >> 5;
                        *(_DWORD *)(a5 + 4) += v231;
                      }
                      else
                      {
                        *(_DWORD *)(a5 + 38) = 0;
                      }
                      v232 = *(_QWORD *)(a5 + 30);
                      v233 = *(_DWORD *)(a5 + 4);
                      if ( v232 && v232 < *(_QWORD *)(a5 + 8) + (unsigned __int64)*(unsigned int *)(a5 + 4) )
                      {
                        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                        {
                          v234 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL);
                          if ( v234 )
                          {
                            v235 = *(_QWORD *)(v234 + 96);
                            if ( v235 )
                            {
                              if ( *(_BYTE *)(v235 + 1177) )
                              {
                                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                                else
                                  ex_raise(34, 68, 21, 1018);
                              }
                            }
                          }
                        }
                        RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 18);
                        v233 = *(_DWORD *)(a5 + 4);
                      }
                      if ( (unsigned int)(v233 - 1) > 0x3F3B )
                      {
                        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                        {
                          v236 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset
                                           + 8LL);
                          if ( v236 )
                          {
                            v237 = *(_QWORD *)(v236 + 96);
                            if ( v237 )
                            {
                              if ( *(_BYTE *)(v237 + 1177) )
                              {
                                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                                else
                                  ex_raise(34, 68, 21, 1005);
                              }
                            }
                          }
                        }
                        RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 5);
                      }
LABEL_566:
                      v238 = *(_DWORD *)(a5 + 4);
                      if ( v238 < 9 )
                      {
                        v239 = **(_BYTE **)(a5 + 8) & 0xE;
                        if ( v239 )
                        {
                          v240 = v239 == 12;
                          goto LABEL_569;
                        }
                        goto LABEL_570;
                      }
                      goto LABEL_571;
                    }
                    if ( v222 < 0x400u )
                      goto LABEL_537;
                    *(_WORD *)v20 |= 1u;
                    v223 = *(_WORD *)(a5 + 28) - 1;
                    *(_WORD *)(a5 + 28) = v223;
                    if ( !v223 )
                      goto LABEL_537;
                    LOWORD(v213) = v223;
                  }
                }
                v238 = *(_DWORD *)(a5 + 4);
                if ( !v238 )
                {
                  CDRecord::Resize(v20);
                  v238 = *(_DWORD *)(a5 + 4);
                }
                if ( v238 < 9 )
                {
                  v270 = *(_BYTE **)(a5 + 8);
                  if ( (*v270 & 0x1C) == 0 )
                    goto LABEL_570;
                  v240 = (*v270 & 0x1C) == 12;
LABEL_569:
                  if ( v240 )
LABEL_570:
                    v238 = 9;
                }
LABEL_571:
                v241 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 312LL))(v198);
                LODWORD(v456) = v199;
                LogSystemMetadata(
                  L"Generate in-row version fullrow %d bytes (xactid=%I64d, xdesTs=%I64d, dbid= %d rowsetid=%I64d)\n",
                  v238,
                  v241,
                  v201,
                  v456,
                  v477);
                CDStream::CDStream((CDStream *)v499);
                v242 = GetProcessHeap();
                v243 = (CTracePrintStream *)HeapAlloc(v242, 0, 0x6C0u);
                Destination = v243;
                if ( v243 )
                  v243 = CTracePrintStream::CTracePrintStream(v243, 0);
                v244 = v243;
                if ( v243 && !CDStream::AddDevice((CDStream *)v499, v243) )
                  (**(void (__fastcall ***)(CTracePrintStream *, __int64))v244)(v244, 1);
                Record::Dump(v36, (struct CDStream *)v499);
                CDStream::~CDStream((CDStream *)v499);
                v33 = v470;
                v32 = a11;
              }
              if ( (qword_10317F738 & 0x400000000000000LL) == 0 )
              {
                v39 = v471;
                ++*((_QWORD *)v471 + 20);
                v33 = v470;
                goto LABEL_219;
              }
              v245 = *((_QWORD *)v33 + 82);
              if ( (*((_BYTE *)v470 + 536) & 4) != 0 )
                v246 = (unsigned int *)((*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v470 + 488LL))(v470) + 40);
              else
                v246 = (unsigned int *)((char *)v470 + 40);
              v247 = *v246 + ((unsigned __int64)*((unsigned __int16 *)v246 + 2) << 32);
              if ( *(_WORD *)v36 )
              {
                v287 = *(_DWORD *)(a5 + 4);
                if ( !v287 )
                {
                  CDRecord::Resize(v20);
                  v287 = *(_DWORD *)(a5 + 4);
                }
                if ( v287 >= 9 || (v288 = *(_BYTE **)(a5 + 8), (*v288 & 0x1C) != 0) && (*v288 & 0x1C) != 0xC )
                  v468 = v287;
                else
                  v468 = 9;
                goto LABEL_679;
              }
              if ( *(_DWORD *)(a5 + 4) )
                goto LABEL_675;
              *(_WORD *)v20 = 0;
              v248 = *(unsigned int *)(a5 + 16);
              *(_DWORD *)(a5 + 20) = v248;
              v249 = *(char **)(a5 + 8);
              v250 = *v249;
              v251 = v248;
              if ( (*v249 & 0x10) != 0 )
              {
                LODWORD(v248) = (((unsigned int)*(unsigned __int16 *)&v249[v248] + 7) >> 3) + v248 + 2;
                *(_DWORD *)(a5 + 20) = v248;
                v250 = *v249;
                v251 = v248;
              }
              if ( (v250 & 0x20) == 0 )
              {
                *(_DWORD *)(a5 + 4) = v248;
                *(_WORD *)(a5 + 28) = 0;
                *(_DWORD *)(a5 + 24) = v251;
                goto LABEL_647;
              }
              v252 = (unsigned __int16 *)&v249[(unsigned int)v248];
              v253 = *v252;
              *(_WORD *)(a5 + 28) = *v252;
              if ( !v253 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v254 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v254 )
                  {
                    v255 = *(_QWORD *)(v254 + 96);
                    if ( v255 )
                    {
                      if ( *(_BYTE *)(v255 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                        else
                          ex_raise(34, 68, 21, 1003);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 3);
                v253 = *(_WORD *)(a5 + 28);
                v251 = *(_DWORD *)(a5 + 20);
              }
              v256 = v251 + 2 * (v253 + 1);
              *(_DWORD *)(a5 + 24) = v256;
              if ( v256 > 0x1F9E )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v257 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v257 )
                  {
                    v258 = *(_QWORD *)(v257 + 96);
                    if ( v258 )
                    {
                      if ( *(_BYTE *)(v258 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
                v256 = *(_DWORD *)(a5 + 24);
              }
              v259 = *(unsigned __int16 *)(a5 + 28);
              v260 = v252[v259] & 0x7FFF;
              *(_DWORD *)(a5 + 4) = v260;
              if ( v256 > v260 )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v261 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v261 )
                  {
                    v262 = *(_QWORD *)(v261 + 96);
                    if ( v262 )
                    {
                      if ( *(_BYTE *)(v262 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                        else
                          ex_raise(34, 68, 21, 1004);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 4);
                LOWORD(v259) = *(_WORD *)(a5 + 28);
              }
              while ( 2 )
              {
                v263 = (unsigned __int16)v259;
                if ( (v252[(unsigned __int16)v259] & 0x8000u) == 0 )
                  goto LABEL_646;
                v264 = *(_QWORD *)(a5 + 8) + *(unsigned int *)(a5 + 20);
                if ( (unsigned __int16)v259 == 1 )
                {
                  v265 = *(_DWORD *)(a5 + 24);
                  v266 = v265;
                  v267 = *(_WORD *)(v264 + 2 * v263) & 0x7FFF;
                  goto LABEL_618;
                }
                v265 = *(_WORD *)(v264 + 2LL * (unsigned __int16)v259 - 2) & 0x7FFF;
                v266 = *(_DWORD *)(a5 + 24);
                v267 = *(_WORD *)(v264 + 2 * v263) & 0x7FFF;
                if ( v265 >= v266 )
                {
LABEL_618:
                  if ( v267 < v265 )
                    goto LABEL_619;
                }
                else
                {
LABEL_619:
                  RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 7);
                  v266 = *(_DWORD *)(a5 + 24);
                }
                if ( v265 < v266 || v265 > *(_DWORD *)(a5 + 4) )
                  goto LABEL_675;
                v268 = *(_WORD *)(v265 + *(_QWORD *)(a5 + 8));
                if ( v268 == 5 )
                {
                  *(_WORD *)v20 |= 2u;
                  --*(_WORD *)(a5 + 28);
                  *(_WORD *)(a5 + 42) = v265;
                  v271 = *(_QWORD *)(a5 + 8) + (unsigned __int16)v265;
                  v272 = *(_WORD *)(v271 + 2);
                  if ( (v272 & 0x4000) != 0 )
                    v273 = *(_WORD *)(a5 + 44) & 0xC7FF | v272 & 0x3800;
                  else
                    v273 = *(_WORD *)(a5 + 44) & 0xC7FF;
                  *(_WORD *)(a5 + 44) = v273;
                  *(_WORD *)(a5 + 44) = v273 ^ (*(_WORD *)(v271 + 2) ^ v273) & 0x7FF;
LABEL_646:
                  v249 = *(char **)(a5 + 8);
LABEL_647:
                  if ( (*v249 & 0x40) != 0 )
                  {
                    v274 = *(_DWORD *)(a5 + 4);
                    *(_DWORD *)(a5 + 38) = v274;
                    *(_DWORD *)(a5 + 4) = v274 + 14;
                    v275 = FixedVarRecord::FindVersioningInfo(v20);
                    v276 = HIWORD(*(_QWORD *)v275);
                    v277 = 0;
                    if ( (((__int16)v276 ^ ((unsigned int)(__int16)v276 >> 1)) & 0x2000) != 0 )
                    {
                      if ( (v276 & 0x4000) != 0 )
                        LOWORD(v276) = v276 | 0x2000;
                      else
                        LOWORD(v276) = v276 & 0xDFFF;
                    }
                    if ( (_WORD)v276 == 0xFFFC )
                      v277 = (unsigned __int16)WORD2(*(_QWORD *)v275) >> 5;
                    *(_DWORD *)(a5 + 4) += v277;
                  }
                  else
                  {
                    *(_DWORD *)(a5 + 38) = 0;
                  }
                  v278 = *(_QWORD *)(a5 + 30);
                  v279 = *(_DWORD *)(a5 + 4);
                  if ( v278 && v278 < *(_QWORD *)(a5 + 8) + (unsigned __int64)*(unsigned int *)(a5 + 4) )
                  {
                    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                    {
                      v280 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL);
                      if ( v280 )
                      {
                        v281 = *(_QWORD *)(v280 + 96);
                        if ( v281 )
                        {
                          if ( *(_BYTE *)(v281 + 1177) )
                          {
                            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                            else
                              ex_raise(34, 68, 21, 1018);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 18);
                    v279 = *(_DWORD *)(a5 + 4);
                  }
                  if ( (unsigned int)(v279 - 1) > 0x3F3B )
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
                              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                            else
                              ex_raise(34, 68, 21, 1005);
                          }
                        }
                      }
                    }
                    RaiseInconsistencyError(*(_QWORD *)(a5 + 8), 5);
                  }
LABEL_675:
                  if ( *(_DWORD *)(a5 + 4) >= 9u || (v284 = **(_BYTE **)(a5 + 8) & 0xE) != 0 && v284 != 12 )
                    v468 = *(_DWORD *)(a5 + 4);
LABEL_679:
                  v39 = v471;
                  v285 = *((unsigned __int16 *)v471 + 860);
                  v286 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v245 + 312LL))(v245);
                  PersistVerStore::XeventTrace(
                    v285,
                    (const wchar_t *)(*((_QWORD *)v39 + 214) + 936LL),
                    L"PVS(InRowFull) generates in-row version fullrow %d bytes (xactid=%I64d, xdesTs=%I64d) rowsetid=%I64d",
                    v468,
                    v286,
                    v247,
                    v477);
                  ++*((_QWORD *)v39 + 20);
                  v33 = v470;
LABEL_219:
                  v31 = a10;
LABEL_31:
                  if ( v494 && (*(int *)(v494 + 120) > 0 || *(int *)(v494 + 116) > 0) && v31 == 1 )
                  {
                    v105 = v472;
                    v106 = *(_DWORD *)v472;
                    if ( *(int *)v472 >= 0 )
                    {
                      v108 = 0;
                      v107 = 0;
                    }
                    else
                    {
                      if ( VersionRecPtr::IsInRowDiff(v472) )
                      {
                        utassert_fail(1u, "!IsInRowDiff()", "setypes.cpp", 1260, 0);
                        v106 = *(_DWORD *)v105;
                      }
                      v107 = *(_DWORD *)(*((_QWORD *)v33 + 6) + 1720LL);
                      v108 = 0;
                    }
                    v109 = *((_WORD *)v105 + 2);
                    v110 = *((_WORD *)v105 + 3);
                    if ( (*((_BYTE *)v33 + 536) & 4) != 0 )
                    {
                      v108 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v33 + 82) + 368LL))(*((_QWORD *)v33 + 82));
                      goto LABEL_243;
                    }
                    v289 = *((_QWORD *)v33 + 26);
                    if ( v289 )
                      v111 = (_QWORD *)(v289 + 336);
                    else
LABEL_243:
                      v111 = (_QWORD *)v108;
                    if ( v32 && (v112 = v32 - 1) != 0 )
                    {
                      v113 = v112 - 1;
                      if ( v113 )
                      {
                        if ( v113 != 1 )
                        {
                          utassert_fail(
                            1u,
                            "FALSE",
                            "Sql\\Ntdbms\\storeng\\include\\XactVerMgr.inl",
                            427,
                            "Invalid switch value");
                          goto LABEL_249;
                        }
                        v290 = v111[8];
                        v291 = v479;
                        *(_DWORD *)v290 = *v479;
                        *(_WORD *)(v290 + 4) = *((_WORD *)v291 + 2);
                        *(_WORD *)(v290 + 6) = *((_WORD *)v291 + 3);
                        *(_DWORD *)(v290 + 8) = v291[2];
                        v292 = v111[9];
                      }
                      else
                      {
                        v293 = v111[6];
                        v294 = v479;
                        *(_DWORD *)v293 = *v479;
                        *(_WORD *)(v293 + 4) = *((_WORD *)v294 + 2);
                        *(_WORD *)(v293 + 6) = *((_WORD *)v294 + 3);
                        *(_DWORD *)(v293 + 8) = v294[2];
                        v292 = v111[7];
                      }
                    }
                    else
                    {
                      v295 = v111[4];
                      v296 = v479;
                      *(_DWORD *)v295 = *v479;
                      *(_WORD *)(v295 + 4) = *((_WORD *)v296 + 2);
                      *(_WORD *)(v295 + 6) = *((_WORD *)v296 + 3);
                      *(_DWORD *)(v295 + 8) = v296[2];
                      v292 = v111[5];
                    }
                    *(_DWORD *)v292 = v106;
                    *(_WORD *)(v292 + 4) = v109;
                    *(_WORD *)(v292 + 6) = v110;
                    *(_DWORD *)(v292 + 8) = v107;
LABEL_249:
                    v39 = v471;
                    ++*((_QWORD *)v471 + 15);
                  }
                  *v474 = 2;
                  v40 = v472;
LABEL_35:
                  LODWORD(v29) = a6;
                  goto LABEL_36;
                }
                if ( v268 < 0x400u )
                  goto LABEL_646;
                *(_WORD *)v20 |= 1u;
                v269 = *(_WORD *)(a5 + 28) - 1;
                *(_WORD *)(a5 + 28) = v269;
                if ( !v269 )
                  goto LABEL_646;
                LOWORD(v259) = v269;
                continue;
              }
            }
            if ( v178 < 0x400u )
              goto LABEL_431;
            *(_WORD *)v20 |= 1u;
            v179 = *(_WORD *)(a5 + 28) - 1;
            *(_WORD *)(a5 + 28) = v179;
            if ( !v179 )
              goto LABEL_431;
            LOWORD(v169) = v179;
          }
        }
        v35 = v478;
      }
    }
    v37 = v473;
LABEL_27:
    if ( (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v33 + 16LL))(v33) )
      VersionMgr::AddRecordToPVS(v475, v33, v477, v36, v35, 0, v37 + 32, &v481, v472);
    else
      AppendOnlyVerStoreMgr::AddRecord(VersionStore, v475, v33, v477, v36, v35, v472);
    v38 = *(_BYTE *)(v37 + 1) - 3;
    v39 = v471;
    if ( v38 <= 1u )
      ++*((_QWORD *)v471 + 35);
    goto LABEL_31;
  }
  v43 = 1;
  *v474 = 1;
  if ( v24 || v27 )
  {
    v40 = v472;
    *(_QWORD *)v472 = 0;
    v39 = v471;
    goto LABEL_36;
  }
  v44 = v476;
  if ( *(_WORD *)v476 )
    CDRecord::GetVersionRecPtr(v20, &v486);
  else
    FixedVarRecord::GetVersionRecPtr(v20, &v486);
  v40 = v472;
  *(_DWORD *)v472 = v486;
  *((_WORD *)v40 + 2) = v487;
  v45 = v488;
  *((_WORD *)v40 + 3) = v488;
  v46 = (v45 >> 14) & 1;
  v47 = (v45 >> 13) & 1;
  v48 = v45;
  if ( v47 != v46 )
  {
    if ( (v45 & 0x4000) != 0 )
      v48 = v45 | 0x2000;
    else
      v48 = v45 & 0xDFFF;
  }
  if ( v48 != -4 )
    goto LABEL_51;
  if ( v47 != v46 )
  {
    if ( (v45 & 0x4000) != 0 )
      LOWORD(v45) = v45 | 0x2000;
    else
      LOWORD(v45) = v45 & 0xDFFF;
  }
  if ( (_WORD)v45 == 0xFFFC )
  {
    v298 = *((_WORD *)v40 + 2) & 0x1F;
  }
  else
  {
    utassert_fail(1u, "false", "setypes.cpp", 1210, 0);
    v298 = *((_WORD *)v40 + 2);
  }
  if ( v298 == 3 )
  {
LABEL_51:
    v39 = v471;
    ++*((_QWORD *)v471 + 36);
    goto LABEL_35;
  }
  SourceSize[0] = 0;
  v465 = 0;
  *(_QWORD *)((char *)&v466 + 2) = 0;
  v462 = 0;
  v299 = 9;
  v300 = (char *)*((_QWORD *)v44 + 1);
  if ( *(_WORD *)v44 )
  {
    v302 = *v300 & 0x1C;
    if ( v302 != 4 )
    {
      if ( v302 == 16 )
        v43 = 9;
      else
        v43 = *((unsigned __int16 *)v44 + 13) + *((unsigned __int16 *)v44 + 14);
    }
  }
  else
  {
    v43 = *((_DWORD *)v44 + 4);
  }
  v156 = (*v300 & 1) == 0;
  *(_QWORD *)&SourceSize[1] = *((_QWORD *)v44 + 1);
  if ( v156 )
  {
    v459 = 0;
    LODWORD(v466) = 0;
    switch ( *v300 & 0xE )
    {
      case 0:
      case 2:
      case 8:
      case 0xC:
        v43 = *((unsigned __int16 *)v300 + 1);
        if ( (unsigned int)(v43 - 1) > 0x1F9D )
          RaiseInconsistencyError(v300, 6);
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
        v43 = 9;
        break;
      case 6:
      case 0xA:
        break;
      case 0xE:
        v43 = 1;
        break;
    }
    LODWORD(v462) = v43;
  }
  else
  {
    v459 = 1;
    v301 = *v300;
    switch ( byte_100611450[*v300 & 0x1C] )
    {
      case 0:
        if ( v300[1] < 0 )
        {
          v303 = HIBYTE(*(_WORD *)(v300 + 1)) | ((*(_WORD *)(v300 + 1) & 0x7F) << 8);
          v460 = v303;
          LOWORD(v463) = 3;
          v304 = 3;
        }
        else
        {
          v303 = (unsigned __int8)v300[1];
          v460 = v303;
          LOWORD(v463) = 2;
          v304 = 2;
        }
        v464 = v304 + (((unsigned int)v303 + 1) >> 1);
        if ( v303 > 0x1Eu )
          HIWORD(v463) = (v303 - 1) / 30;
        else
          HIWORD(v463) = 0;
        v467 = 0;
        break;
      case 1:
        if ( (v301 & 0x1C) == 4 && (v301 & 2) != 0 )
        {
          v463 = 0;
          v460 = 0;
          v464 = 0;
          LOWORD(v466) = 0;
          *(_QWORD *)&SourceSize[1] = v300;
          SourceSize[0] = 15;
          v467 = 1;
        }
        else
        {
          v463 = 0;
          v460 = 0;
          v464 = 0;
          LOWORD(v466) = 0;
          *(_QWORD *)&SourceSize[1] = v300;
          SourceSize[0] = 1;
          v467 = 0;
        }
        break;
      case 2:
        v463 = 0;
        v460 = 0;
        v464 = 0;
        LOWORD(v466) = 0;
        *(_QWORD *)&SourceSize[1] = v300;
        SourceSize[0] = 9;
        v467 = 0;
        break;
      case 3:
        utassert_fail(1u, "FALSE", "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl", 207, "Invalid switch value");
        break;
    }
  }
  v39 = v471;
  VersionMgr::GetRecordFromInRow((struct Record *)&v459, v503, 0x1F9Eu, v472, 0, v471);
  LODWORD(v29) = a6;
  if ( a6 != 2 )
    goto LABEL_1268;
  v305 = Destination;
  if ( !Destination || !a7 )
  {
    v39 = v471;
LABEL_1268:
    v371 = v470;
    v40 = v472;
    v373 = v474;
LABEL_972:
    v374 = v473;
    goto LABEL_973;
  }
  v306 = SourceSize[0];
  if ( v459 )
  {
    if ( !SourceSize[0] )
    {
      CDRecord::Resize((CDRecord *)&v460);
      v306 = SourceSize[0];
    }
    if ( v306 >= 9 )
      goto LABEL_1023;
    if ( (**(_BYTE **)&SourceSize[1] & 0x1C) == 0 )
      goto LABEL_812;
    v327 = (**(_BYTE **)&SourceSize[1] & 0x1C) == 12;
  }
  else
  {
    if ( !SourceSize[0] )
    {
      v460 = 0;
      v306 = v462;
      HIDWORD(v462) = v462;
      if ( (**(_BYTE **)&SourceSize[1] & 0x10) != 0 )
      {
        v306 = (((unsigned int)*(unsigned __int16 *)((unsigned int)v462 + *(_QWORD *)&SourceSize[1]) + 7) >> 3)
             + v462
             + 2;
        HIDWORD(v462) = v306;
      }
      if ( (**(_BYTE **)&SourceSize[1] & 0x20) != 0 )
      {
        v307 = (unsigned __int16 *)(*(_QWORD *)&SourceSize[1] + v306);
        v308 = *v307;
        v464 = v308;
        if ( !v308 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v309 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v309 )
            {
              v310 = *(_QWORD *)(v309 + 96);
              if ( v310 )
              {
                if ( *(_BYTE *)(v310 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 3);
          v308 = v464;
        }
        v311 = HIDWORD(v462) + 2 + 2 * v308;
        v463 = v311;
        if ( v311 > 0x1F9E )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
          v308 = v464;
          v311 = v463;
        }
        v306 = v307[v308] & 0x7FFF;
        SourceSize[0] = v306;
        if ( v311 > v306 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v314 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v314 )
            {
              v315 = *(_QWORD *)(v314 + 96);
              if ( v315 )
              {
                if ( *(_BYTE *)(v315 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
          v308 = v464;
          v311 = v463;
          v306 = SourceSize[0];
        }
        while ( (v307[v308] & 0x8000u) != 0 )
        {
          v316 = *(_QWORD *)&SourceSize[1] + HIDWORD(v462);
          if ( v308 == 1 )
            v317 = v311;
          else
            v317 = *(_WORD *)(v316 + 2LL * v308 - 2) & 0x7FFF;
          if ( v317 < v311 || (*(_WORD *)(v316 + 2LL * v308) & 0x7FFFu) < v317 )
          {
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 7);
            v308 = v464;
            v311 = v463;
            v306 = SourceSize[0];
          }
          if ( v317 < v311 || v317 > v306 )
            goto LABEL_808;
          v318 = *(_WORD *)(v317 + *(_QWORD *)&SourceSize[1]);
          if ( v318 == 5 )
          {
            v460 |= 2u;
            v464 = v308 - 1;
            WORD2(v466) = v317;
            v379 = *(_QWORD *)&SourceSize[1] + (unsigned __int16)v317;
            v380 = *(_WORD *)(v379 + 2);
            if ( (v380 & 0x4000) != 0 )
              v381 = (WORD3(v466) ^ v380) & 0x3800 ^ WORD3(v466);
            else
              v381 = WORD3(v466) & 0xC7FF;
            WORD3(v466) = v381;
            WORD3(v466) = v381 ^ (*(_WORD *)(v379 + 2) ^ v381) & 0x7FF;
            break;
          }
          if ( v318 >= 0x400u )
          {
            v460 |= 1u;
            v156 = v308-- == 1;
            v464 = v308;
            if ( !v156 )
              continue;
          }
          break;
        }
      }
      else
      {
        SourceSize[0] = v306;
        v464 = 0;
        v463 = v306;
      }
      if ( (**(_BYTE **)&SourceSize[1] & 0x40) != 0 )
      {
        LODWORD(v466) = v306;
        SourceSize[0] = v306 + 14;
        v319 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v460);
        v320 = HIWORD(*(_QWORD *)v319);
        v321 = 0;
        if ( (((__int16)v320 ^ ((unsigned int)(__int16)v320 >> 1)) & 0x2000) != 0 )
        {
          if ( (v320 & 0x4000) != 0 )
            LOWORD(v320) = v320 | 0x2000;
          else
            LOWORD(v320) = v320 & 0xDFFF;
        }
        if ( (_WORD)v320 == 0xFFFC )
          v321 = (unsigned __int16)WORD2(*(_QWORD *)v319) >> 5;
        v306 = v321 + SourceSize[0];
        SourceSize[0] += v321;
      }
      else
      {
        LODWORD(v466) = 0;
      }
      if ( v465 && v465 < *(_QWORD *)&SourceSize[1] + (unsigned __int64)v306 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v322 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v322 )
          {
            v323 = *(_QWORD *)(v322 + 96);
            if ( v323 )
            {
              if ( *(_BYTE *)(v323 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 18);
        v306 = SourceSize[0];
      }
      if ( v306 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v324 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v324 )
          {
            v325 = *(_QWORD *)(v324 + 96);
            if ( v325 )
            {
              if ( *(_BYTE *)(v325 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 5);
        v306 = SourceSize[0];
      }
    }
LABEL_808:
    if ( v306 >= 9 )
      goto LABEL_1023;
    v326 = **(_BYTE **)&SourceSize[1] & 0xE;
    if ( !v326 )
    {
LABEL_812:
      v328 = 9;
      goto LABEL_813;
    }
    v327 = v326 == 12;
  }
  if ( v327 )
    goto LABEL_812;
LABEL_1023:
  v328 = v306;
LABEL_813:
  if ( v328 <= 0x14 )
  {
    if ( v459 )
    {
      if ( !v306 )
      {
        CDRecord::Resize((CDRecord *)&v460);
        v306 = SourceSize[0];
      }
      if ( v306 >= 9 )
        goto LABEL_893;
      if ( (**(_BYTE **)&SourceSize[1] & 0x1C) == 0 )
        goto LABEL_892;
      v349 = (**(_BYTE **)&SourceSize[1] & 0x1C) == 12;
    }
    else
    {
      if ( !v306 )
      {
        v460 = 0;
        v306 = v462;
        HIDWORD(v462) = v462;
        if ( (**(_BYTE **)&SourceSize[1] & 0x10) != 0 )
        {
          v306 = (((unsigned int)*(unsigned __int16 *)((unsigned int)v462 + *(_QWORD *)&SourceSize[1]) + 7) >> 3)
               + v462
               + 2;
          HIDWORD(v462) = v306;
        }
        if ( (**(_BYTE **)&SourceSize[1] & 0x20) != 0 )
        {
          v329 = (unsigned __int16 *)(*(_QWORD *)&SourceSize[1] + v306);
          v330 = *v329;
          v464 = v330;
          if ( !v330 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v331 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v331 )
              {
                v332 = *(_QWORD *)(v331 + 96);
                if ( v332 )
                {
                  if ( *(_BYTE *)(v332 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 3);
            v330 = v464;
          }
          v333 = HIDWORD(v462) + 2 + 2 * v330;
          v463 = v333;
          if ( v333 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v334 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v334 )
              {
                v335 = *(_QWORD *)(v334 + 96);
                if ( v335 )
                {
                  if ( *(_BYTE *)(v335 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
            v330 = v464;
            v333 = v463;
          }
          v306 = v329[v330] & 0x7FFF;
          SourceSize[0] = v306;
          if ( v333 > v306 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v336 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v336 )
              {
                v337 = *(_QWORD *)(v336 + 96);
                if ( v337 )
                {
                  if ( *(_BYTE *)(v337 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
            v330 = v464;
            v333 = v463;
            v306 = SourceSize[0];
          }
          while ( (v329[v330] & 0x8000u) != 0 )
          {
            v338 = *(_QWORD *)&SourceSize[1] + HIDWORD(v462);
            if ( v330 == 1 )
              v339 = v333;
            else
              v339 = *(_WORD *)(v338 + 2LL * v330 - 2) & 0x7FFF;
            if ( v339 < v333 || (*(_WORD *)(v338 + 2LL * v330) & 0x7FFFu) < v339 )
            {
              RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 7);
              v330 = v464;
              v333 = v463;
              v306 = SourceSize[0];
            }
            if ( v339 < v333 || v339 > v306 )
              goto LABEL_888;
            v340 = *(_WORD *)(v339 + *(_QWORD *)&SourceSize[1]);
            if ( v340 == 5 )
            {
              v460 |= 2u;
              v464 = v330 - 1;
              WORD2(v466) = v339;
              v382 = *(_QWORD *)&SourceSize[1] + (unsigned __int16)v339;
              v383 = *(_WORD *)(v382 + 2);
              if ( (v383 & 0x4000) != 0 )
                v384 = (WORD3(v466) ^ v383) & 0x3800 ^ WORD3(v466);
              else
                v384 = WORD3(v466) & 0xC7FF;
              WORD3(v466) = v384;
              WORD3(v466) = v384 ^ (*(_WORD *)(v382 + 2) ^ v384) & 0x7FF;
              break;
            }
            if ( v340 >= 0x400u )
            {
              v460 |= 1u;
              v156 = v330-- == 1;
              v464 = v330;
              if ( !v156 )
                continue;
            }
            break;
          }
        }
        else
        {
          SourceSize[0] = v306;
          v464 = 0;
          v463 = v306;
        }
        if ( (**(_BYTE **)&SourceSize[1] & 0x40) != 0 )
        {
          LODWORD(v466) = v306;
          SourceSize[0] = v306 + 14;
          v341 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v460);
          v342 = HIWORD(*(_QWORD *)v341);
          v343 = 0;
          if ( (((__int16)v342 ^ ((unsigned int)(__int16)v342 >> 1)) & 0x2000) != 0 )
          {
            if ( (v342 & 0x4000) != 0 )
              LOWORD(v342) = v342 | 0x2000;
            else
              LOWORD(v342) = v342 & 0xDFFF;
          }
          if ( (_WORD)v342 == 0xFFFC )
            v343 = (unsigned __int16)WORD2(*(_QWORD *)v341) >> 5;
          v306 = v343 + SourceSize[0];
          SourceSize[0] += v343;
        }
        else
        {
          LODWORD(v466) = 0;
        }
        if ( v465 && v465 < *(_QWORD *)&SourceSize[1] + (unsigned __int64)v306 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v344 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v344 )
            {
              v345 = *(_QWORD *)(v344 + 96);
              if ( v345 )
              {
                if ( *(_BYTE *)(v345 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 18);
          v306 = SourceSize[0];
        }
        if ( v306 - 1 > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v346 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v346 )
            {
              v347 = *(_QWORD *)(v346 + 96);
              if ( v347 )
              {
                if ( *(_BYTE *)(v347 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 5);
          v306 = SourceSize[0];
        }
      }
LABEL_888:
      if ( v306 >= 9 )
        goto LABEL_893;
      v348 = **(_BYTE **)&SourceSize[1] & 0xE;
      if ( !v348 )
        goto LABEL_892;
      v349 = v348 == 12;
    }
    if ( !v349 )
    {
LABEL_893:
      memcpy_s(v305, (unsigned int)DestinationSize, *(const void *const *)&SourceSize[1], v306);
      if ( v459 )
      {
        v388 = SourceSize[0];
        if ( !SourceSize[0] )
        {
          CDRecord::Resize((CDRecord *)&v460);
          v388 = SourceSize[0];
        }
        if ( v388 >= 9 || (**(_BYTE **)&SourceSize[1] & 0x1C) != 0 && (**(_BYTE **)&SourceSize[1] & 0x1C) != 0xC )
          LOWORD(v299) = v388;
      }
      else
      {
        v350 = SourceSize[0];
        if ( !SourceSize[0] )
        {
          v460 = 0;
          v350 = v462;
          HIDWORD(v462) = v462;
          if ( (**(_BYTE **)&SourceSize[1] & 0x10) != 0 )
          {
            v350 = (((unsigned int)*(unsigned __int16 *)((unsigned int)v462 + *(_QWORD *)&SourceSize[1]) + 7) >> 3)
                 + v462
                 + 2;
            HIDWORD(v462) = v350;
          }
          if ( (**(_BYTE **)&SourceSize[1] & 0x20) != 0 )
          {
            v351 = (unsigned __int16 *)(*(_QWORD *)&SourceSize[1] + v350);
            v352 = *v351;
            v464 = v352;
            if ( !v352 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v353 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v353 )
                {
                  v354 = *(_QWORD *)(v353 + 96);
                  if ( v354 )
                  {
                    if ( *(_BYTE *)(v354 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 3);
              v352 = v464;
            }
            v355 = HIDWORD(v462) + 2 + 2 * v352;
            v463 = v355;
            if ( v355 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v356 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v356 )
                {
                  v357 = *(_QWORD *)(v356 + 96);
                  if ( v357 )
                  {
                    if ( *(_BYTE *)(v357 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
              v352 = v464;
              v355 = v463;
            }
            v350 = v351[v352] & 0x7FFF;
            SourceSize[0] = v350;
            if ( v355 > v350 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v358 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v358 )
                {
                  v359 = *(_QWORD *)(v358 + 96);
                  if ( v359 )
                  {
                    if ( *(_BYTE *)(v359 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
              v352 = v464;
              v355 = v463;
              v350 = SourceSize[0];
            }
            while ( (v351[v352] & 0x8000u) != 0 )
            {
              v360 = *(_QWORD *)&SourceSize[1] + HIDWORD(v462);
              if ( v352 == 1 )
                v361 = v355;
              else
                v361 = *(_WORD *)(v360 + 2LL * v352 - 2) & 0x7FFF;
              if ( v361 < v355 || (*(_WORD *)(v360 + 2LL * v352) & 0x7FFFu) < v361 )
              {
                RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 7);
                v352 = v464;
                v355 = v463;
                v350 = SourceSize[0];
              }
              if ( v361 < v355 || v361 > v350 )
                goto LABEL_967;
              v362 = *(_WORD *)(v361 + *(_QWORD *)&SourceSize[1]);
              if ( v362 == 5 )
              {
                v460 |= 2u;
                v464 = v352 - 1;
                WORD2(v466) = v361;
                v385 = *(_QWORD *)&SourceSize[1] + (unsigned __int16)v361;
                v386 = *(_WORD *)(v385 + 2);
                if ( (v386 & 0x4000) != 0 )
                  v387 = (WORD3(v466) ^ v386) & 0x3800 ^ WORD3(v466);
                else
                  v387 = WORD3(v466) & 0xC7FF;
                WORD3(v466) = v387;
                WORD3(v466) = v387 ^ (*(_WORD *)(v385 + 2) ^ v387) & 0x7FF;
                break;
              }
              if ( v362 >= 0x400u )
              {
                v460 |= 1u;
                v156 = v352-- == 1;
                v464 = v352;
                if ( !v156 )
                  continue;
              }
              break;
            }
          }
          else
          {
            SourceSize[0] = v350;
            v464 = 0;
            v463 = v350;
          }
          if ( (**(_BYTE **)&SourceSize[1] & 0x40) != 0 )
          {
            LODWORD(v466) = v350;
            SourceSize[0] = v350 + 14;
            v363 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v460);
            v364 = HIWORD(*(_QWORD *)v363);
            v365 = 0;
            if ( (((__int16)v364 ^ ((unsigned int)(__int16)v364 >> 1)) & 0x2000) != 0 )
            {
              if ( (v364 & 0x4000) != 0 )
                LOWORD(v364) = v364 | 0x2000;
              else
                LOWORD(v364) = v364 & 0xDFFF;
            }
            if ( (_WORD)v364 == 0xFFFC )
              v365 = (unsigned __int16)WORD2(*(_QWORD *)v363) >> 5;
            v350 = v365 + SourceSize[0];
            SourceSize[0] += v365;
          }
          else
          {
            LODWORD(v466) = 0;
          }
          if ( v465 && v465 < *(_QWORD *)&SourceSize[1] + (unsigned __int64)v350 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v366 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v366 )
              {
                v367 = *(_QWORD *)(v366 + 96);
                if ( v367 )
                {
                  if ( *(_BYTE *)(v367 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 18);
            v350 = SourceSize[0];
          }
          if ( v350 - 1 > 0x3F3B )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v368 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v368 )
              {
                v369 = *(_QWORD *)(v368 + 96);
                if ( v369 )
                {
                  if ( *(_BYTE *)(v369 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
            }
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 5);
            v350 = SourceSize[0];
          }
        }
LABEL_967:
        if ( v350 >= 9 || (v370 = **(_BYTE **)&SourceSize[1] & 0xE) != 0 && v370 != 12 )
          LOWORD(v299) = v350;
      }
      v371 = v470;
      v372 = (*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v470 + 80LL))(v470);
      v40 = v472;
      *(_DWORD *)v472 = v372;
      *((_WORD *)v40 + 2) = (32 * v299) | 1;
      *((_WORD *)v40 + 3) = -4;
      v373 = v474;
      *v474 = 2;
      v39 = v471;
      ++*((_QWORD *)v471 + 20);
      LODWORD(v29) = 2;
      goto LABEL_972;
    }
LABEL_892:
    v306 = 9;
    goto LABEL_893;
  }
  v374 = v473;
  if ( *(_BYTE *)(v473 + 1) != 1 )
    goto LABEL_1265;
  if ( v459 )
  {
    if ( !v306 )
    {
      CDRecord::Resize((CDRecord *)&v460);
      v306 = SourceSize[0];
    }
    if ( v306 >= 9 )
      goto LABEL_1142;
    if ( (**(_BYTE **)&SourceSize[1] & 0x1C) == 0 )
      goto LABEL_1141;
    v409 = (**(_BYTE **)&SourceSize[1] & 0x1C) == 12;
  }
  else
  {
    if ( !v306 )
    {
      v460 = 0;
      v306 = v462;
      HIDWORD(v462) = v462;
      if ( (**(_BYTE **)&SourceSize[1] & 0x10) != 0 )
      {
        v306 = (((unsigned int)*(unsigned __int16 *)((unsigned int)v462 + *(_QWORD *)&SourceSize[1]) + 7) >> 3)
             + v462
             + 2;
        HIDWORD(v462) = v306;
      }
      if ( (**(_BYTE **)&SourceSize[1] & 0x20) != 0 )
      {
        v389 = (unsigned __int16 *)(*(_QWORD *)&SourceSize[1] + v306);
        v390 = *v389;
        v464 = v390;
        if ( !v390 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v391 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v391 )
            {
              v392 = *(_QWORD *)(v391 + 96);
              if ( v392 )
              {
                if ( *(_BYTE *)(v392 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 3);
          v390 = v464;
        }
        v393 = HIDWORD(v462) + 2 + 2 * v390;
        v463 = v393;
        if ( v393 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v394 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v394 )
            {
              v395 = *(_QWORD *)(v394 + 96);
              if ( v395 )
              {
                if ( *(_BYTE *)(v395 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
          v390 = v464;
          v393 = v463;
        }
        v306 = v389[v390] & 0x7FFF;
        SourceSize[0] = v306;
        if ( v393 > v306 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v396 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v396 )
            {
              v397 = *(_QWORD *)(v396 + 96);
              if ( v397 )
              {
                if ( *(_BYTE *)(v397 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 4);
          v390 = v464;
          v393 = v463;
          v306 = SourceSize[0];
        }
        while ( (v389[v390] & 0x8000u) != 0 )
        {
          v398 = *(_QWORD *)&SourceSize[1] + HIDWORD(v462);
          if ( v390 == 1 )
            v399 = v393;
          else
            v399 = *(_WORD *)(v398 + 2LL * v390 - 2) & 0x7FFF;
          if ( v399 < v393 || (*(_WORD *)(v398 + 2LL * v390) & 0x7FFFu) < v399 )
          {
            RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 7);
            v390 = v464;
            v393 = v463;
            v306 = SourceSize[0];
          }
          if ( v399 < v393 || v399 > v306 )
            goto LABEL_1137;
          v400 = *(_WORD *)(v399 + *(_QWORD *)&SourceSize[1]);
          if ( v400 == 5 )
          {
            v460 |= 2u;
            v464 = v390 - 1;
            WORD2(v466) = v399;
            v434 = *(_QWORD *)&SourceSize[1] + (unsigned __int16)v399;
            v435 = *(_WORD *)(v434 + 2);
            if ( (v435 & 0x4000) != 0 )
              v436 = (WORD3(v466) ^ v435) & 0x3800 ^ WORD3(v466);
            else
              v436 = WORD3(v466) & 0xC7FF;
            WORD3(v466) = v436;
            WORD3(v466) = v436 ^ (*(_WORD *)(v434 + 2) ^ v436) & 0x7FF;
            break;
          }
          if ( v400 >= 0x400u )
          {
            v460 |= 1u;
            v156 = v390-- == 1;
            v464 = v390;
            if ( !v156 )
              continue;
          }
          break;
        }
      }
      else
      {
        SourceSize[0] = v306;
        v464 = 0;
        v463 = v306;
      }
      if ( (**(_BYTE **)&SourceSize[1] & 0x40) != 0 )
      {
        LODWORD(v466) = v306;
        SourceSize[0] = v306 + 14;
        v401 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v460);
        v402 = HIWORD(*(_QWORD *)v401);
        v403 = 0;
        if ( (((__int16)v402 ^ ((unsigned int)(__int16)v402 >> 1)) & 0x2000) != 0 )
        {
          if ( (v402 & 0x4000) != 0 )
            LOWORD(v402) = v402 | 0x2000;
          else
            LOWORD(v402) = v402 & 0xDFFF;
        }
        if ( (_WORD)v402 == 0xFFFC )
          v403 = (unsigned __int16)WORD2(*(_QWORD *)v401) >> 5;
        v306 = v403 + SourceSize[0];
        SourceSize[0] += v403;
      }
      else
      {
        LODWORD(v466) = 0;
      }
      if ( v465 && v465 < *(_QWORD *)&SourceSize[1] + (unsigned __int64)v306 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v404 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v404 )
          {
            v405 = *(_QWORD *)(v404 + 96);
            if ( v405 )
            {
              if ( *(_BYTE *)(v405 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 18);
        v306 = SourceSize[0];
      }
      if ( v306 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v406 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v406 )
          {
            v407 = *(_QWORD *)(v406 + 96);
            if ( v407 )
            {
              if ( *(_BYTE *)(v407 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)&SourceSize[1], 5);
        v306 = SourceSize[0];
      }
    }
LABEL_1137:
    if ( v306 >= 9 )
      goto LABEL_1142;
    v408 = **(_BYTE **)&SourceSize[1] & 0xE;
    if ( !v408 )
      goto LABEL_1141;
    v409 = v408 == 12;
  }
  if ( v409 )
LABEL_1141:
    v306 = 9;
LABEL_1142:
  if ( v306 > 0x7D0 )
    goto LABEL_1265;
  v410 = v480;
  v411 = (char *)v480 + 2;
  if ( *(_WORD *)v480 )
  {
    v453 = *((_DWORD *)v480 + 1);
    if ( !v453 )
    {
      CDRecord::Resize((struct Record *)((char *)v480 + 2));
      v453 = *(_DWORD *)(v411 + 2);
      v410 = v480;
    }
    if ( v453 >= 9 || (v454 = *(_BYTE **)(v411 + 6), (*v454 & 0x1C) != 0) && (*v454 & 0x1C) != 0xC )
      v299 = v453;
    goto LABEL_1250;
  }
  if ( *((_DWORD *)v480 + 1) )
    goto LABEL_1245;
  *(_WORD *)v411 = 0;
  v412 = *(unsigned int *)(v411 + 14);
  *(_DWORD *)(v411 + 18) = v412;
  v413 = *(char **)(v411 + 6);
  v414 = *v413;
  v415 = v412;
  if ( (*v413 & 0x10) != 0 )
  {
    LODWORD(v412) = (((unsigned int)*(unsigned __int16 *)&v413[v412] + 7) >> 3) + v412 + 2;
    *(_DWORD *)(v411 + 18) = v412;
    v414 = *v413;
    v415 = v412;
  }
  if ( (v414 & 0x20) == 0 )
  {
    *(_DWORD *)(v411 + 2) = v412;
    *((_WORD *)v411 + 13) = 0;
    *(_DWORD *)(v411 + 22) = v415;
    goto LABEL_1216;
  }
  v416 = (unsigned __int16 *)&v413[(unsigned int)v412];
  v417 = *v416;
  *((_WORD *)v411 + 13) = *v416;
  if ( !v417 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v418 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v418 )
      {
        v419 = *(_QWORD *)(v418 + 96);
        if ( v419 )
        {
          if ( *(_BYTE *)(v419 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 3);
    v417 = *((_WORD *)v411 + 13);
    v415 = *(_DWORD *)(v411 + 18);
  }
  v420 = v415 + 2 * (v417 + 1);
  *(_DWORD *)(v411 + 22) = v420;
  if ( v420 > 0x1F9E )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v421 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v421 )
      {
        v422 = *(_QWORD *)(v421 + 96);
        if ( v422 )
        {
          if ( *(_BYTE *)(v422 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 4);
    v420 = *(_DWORD *)(v411 + 22);
  }
  v423 = *((unsigned __int16 *)v411 + 13);
  v424 = v416[v423] & 0x7FFF;
  *(_DWORD *)(v411 + 2) = v424;
  if ( v420 > v424 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v425 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v425 )
      {
        v426 = *(_QWORD *)(v425 + 96);
        if ( v426 )
        {
          if ( *(_BYTE *)(v426 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 4);
    LOWORD(v423) = *((_WORD *)v411 + 13);
  }
  while ( 1 )
  {
    v427 = (unsigned __int16)v423;
    if ( (v416[(unsigned __int16)v423] & 0x8000u) == 0 )
      break;
    v428 = *(_QWORD *)(v411 + 6) + *(unsigned int *)(v411 + 18);
    if ( (unsigned __int16)v423 == 1 )
    {
      v429 = *(_DWORD *)(v411 + 22);
      v430 = v429;
      v431 = *(_WORD *)(v428 + 2 * v427) & 0x7FFF;
    }
    else
    {
      v429 = *(_WORD *)(v428 + 2LL * (unsigned __int16)v423 - 2) & 0x7FFF;
      v430 = *(_DWORD *)(v411 + 22);
      v431 = *(_WORD *)(v428 + 2 * v427) & 0x7FFF;
      if ( v429 < v430 )
      {
LABEL_1182:
        RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 7);
        v430 = *(_DWORD *)(v411 + 22);
        goto LABEL_1183;
      }
    }
    if ( v431 < v429 )
      goto LABEL_1182;
LABEL_1183:
    if ( v429 < v430 || v429 > *(_DWORD *)(v411 + 2) )
      goto LABEL_1244;
    v432 = *(_WORD *)(v429 + *(_QWORD *)(v411 + 6));
    if ( v432 == 5 )
    {
      *(_WORD *)v411 |= 2u;
      --*((_WORD *)v411 + 13);
      *((_WORD *)v411 + 20) = v429;
      v437 = *(_QWORD *)(v411 + 6) + (unsigned __int16)v429;
      v438 = *(_WORD *)(v437 + 2);
      if ( (v438 & 0x4000) != 0 )
        v439 = *((_WORD *)v411 + 21) & 0xC7FF | v438 & 0x3800;
      else
        v439 = *((_WORD *)v411 + 21) & 0xC7FF;
      *((_WORD *)v411 + 21) = v439;
      *((_WORD *)v411 + 21) = v439 ^ (*(_WORD *)(v437 + 2) ^ v439) & 0x7FF;
      break;
    }
    if ( v432 < 0x400u )
      break;
    *(_WORD *)v411 |= 1u;
    v433 = *((_WORD *)v411 + 13) - 1;
    *((_WORD *)v411 + 13) = v433;
    if ( !v433 )
      break;
    LOWORD(v423) = v433;
  }
  v413 = *(char **)(v411 + 6);
LABEL_1216:
  if ( (*v413 & 0x40) != 0 )
  {
    v440 = *(_DWORD *)(v411 + 2);
    *((_DWORD *)v411 + 9) = v440;
    *(_DWORD *)(v411 + 2) = v440 + 14;
    v441 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v411);
    v442 = HIWORD(*(_QWORD *)v441);
    v443 = 0;
    if ( (((__int16)v442 ^ ((unsigned int)(__int16)v442 >> 1)) & 0x2000) != 0 )
    {
      if ( (v442 & 0x4000) != 0 )
        LOWORD(v442) = v442 | 0x2000;
      else
        LOWORD(v442) = v442 & 0xDFFF;
    }
    if ( (_WORD)v442 == 0xFFFC )
      v443 = (unsigned __int16)WORD2(*(_QWORD *)v441) >> 5;
    *(_DWORD *)(v411 + 2) += v443;
  }
  else
  {
    *((_DWORD *)v411 + 9) = 0;
  }
  v444 = *(_QWORD *)(v411 + 28);
  v445 = *(_DWORD *)(v411 + 2);
  if ( v444 && v444 < *(_QWORD *)(v411 + 6) + (unsigned __int64)*(unsigned int *)(v411 + 2) )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v446 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v446 )
      {
        v447 = *(_QWORD *)(v446 + 96);
        if ( v447 )
        {
          if ( *(_BYTE *)(v447 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 18);
    v445 = *(_DWORD *)(v411 + 2);
  }
  if ( (unsigned int)(v445 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v448 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v448 )
      {
        v449 = *(_QWORD *)(v448 + 96);
        if ( v449 )
        {
          if ( *(_BYTE *)(v449 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            else
              ex_raise(34, 68, 21, 1005);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v411 + 6), 5);
  }
LABEL_1244:
  v410 = v480;
LABEL_1245:
  if ( *(_DWORD *)(v411 + 2) >= 9u || (v450 = **(_BYTE **)(v411 + 6) & 0xE) != 0 && v450 != 12 )
    v299 = *(_DWORD *)(v411 + 2);
  v305 = Destination;
LABEL_1250:
  if ( v299 <= 0x7D0 )
  {
    ModDiffForVersion = PageRef::TryGenerateModDiffForVersion(
                          (unsigned int *)&DestinationSize,
                          (unsigned __int8 (*)[200])v305,
                          v471,
                          (struct ModifyRowVector *)v500,
                          (struct Record *)&v459,
                          v410);
    v371 = v470;
    if ( ModDiffForVersion )
    {
      v452 = (*(__int64 (__fastcall **)(XDES *))(*(_QWORD *)v470 + 80LL))(v470);
      v40 = v472;
      *(_DWORD *)v472 = v452;
      *((_WORD *)v40 + 2) = (32 * DestinationSize) | 2;
      *((_WORD *)v40 + 3) = -4;
      v39 = v471;
      ++*((_QWORD *)v471 + 19);
      v373 = v474;
      *v474 = 2;
      LODWORD(v29) = 2;
    }
    else
    {
      v39 = v471;
      v40 = v472;
      LODWORD(v29) = 2;
      v373 = v474;
    }
    goto LABEL_973;
  }
LABEL_1265:
  v39 = v471;
  ++*((_QWORD *)v471 + 22);
  v371 = v470;
  v40 = v472;
  LODWORD(v29) = 2;
  v373 = v474;
LABEL_973:
  if ( *v373 == 1 )
  {
    v375 = *(_BYTE **)&SourceSize[1];
    v376 = (unsigned __int8)**(_BYTE **)&SourceSize[1];
    if ( v459 )
      v377 = v376 >> 1;
    else
      v377 = v376 >> 6;
    if ( (v377 & 1) != 0 )
    {
      if ( v459 )
      {
        if ( (**(_BYTE **)&SourceSize[1] & 2) != 0 )
        {
          if ( !SourceSize[0] )
          {
            CDRecord::Resize((CDRecord *)&v460);
            v375 = *(_BYTE **)&SourceSize[1];
          }
          *v375 &= ~2u;
          SourceSize[0] = v467;
          v467 = 0;
        }
      }
      else
      {
        FixedVarRecord::ClearVersioningInfo((FixedVarRecord *)&v460);
      }
    }
    if ( (*(unsigned __int8 (__fastcall **)(XDES *))(*(_QWORD *)v371 + 16LL))(v371) )
      VersionMgr::AddRecordToPVS(v475, v371, v477, &v459, 0, 0, v374 + 32, &v481, v40);
    else
      AppendOnlyVerStoreMgr::AddRecord(VersionStore, v475, v371, v477, &v459, 0, v40);
    v378 = *((__int16 *)v40 + 3);
    if ( ((v378 ^ (v378 >> 1)) & 0x2000) != 0 )
    {
      if ( (v378 & 0x4000) != 0 )
        LOWORD(v378) = v378 | 0x2000;
      else
        LOWORD(v378) = v378 & 0xDFFF;
    }
    if ( (_WORD)v378 == 0xFFFC )
      utassert_fail(1u, "!versionRecPtr.IsInRowDiff()", "RecVerMgr.cpp", 871, 0);
    *v474 = 2;
    ++*((_QWORD *)v39 + 24);
    LODWORD(v29) = a6;
    if ( a6 == 2 )
      ++*((_QWORD *)v39 + 25);
    if ( (unsigned __int8)(*(_BYTE *)(v374 + 1) - 3) <= 1u )
      ++*((_QWORD *)v39 + 35);
  }
LABEL_36:
  v41 = *((__int16 *)v40 + 3);
  result = 0x2000;
  if ( ((v41 ^ (v41 >> 1)) & 0x2000) != 0 )
  {
    if ( (v41 & 0x4000) != 0 )
      v297 = v41 | 0x2000;
    else
      v297 = v41 & 0xDFFF;
    *((_WORD *)v40 + 3) = v297;
  }
  if ( (_DWORD)v29 == 1 )
    ++*((_QWORD *)v39 + 26);
  if ( (_DWORD)v490 )
    return LatchBase::ReleaseInternal(v489, HIDWORD(v490));
  return result;
}

```

## disassembly

```asm
0x10049b060  push    rbp
0x10049b062  push    rbx
0x10049b063  push    rsi
0x10049b064  push    rdi
0x10049b065  push    r12
0x10049b067  push    r13
0x10049b069  push    r14
0x10049b06b  push    r15
0x10049b06d  lea     rbp, [rsp-2158h]
0x10049b075  mov     eax, 2258h
0x10049b07a  call    _alloca_probe
0x10049b07f  sub     rsp, rax
0x10049b082  mov     [rbp+2190h+var_2120], 0FFFFFFFFFFFFFFFEh
0x10049b08a  mov     rax, cs:__security_cookie
0x10049b091  xor     rax, rsp
0x10049b094  mov     [rbp+2190h+var_50], rax
0x10049b09b  mov     r14, r9
0x10049b09e  mov     [rbp+2190h+var_21E8], r9
0x10049b0a2  mov     [rbp+2190h+var_2200], r8
0x10049b0a6  mov     [rbp+2190h+var_21C8], rdx
0x10049b0aa  mov     rsi, rcx
0x10049b0ad  mov     rbx, [rbp+2190h+arg_20]
0x10049b0b4  mov     [rbp+2190h+var_21D0], rbx
0x10049b0b8  mov     rax, [rbp+2190h+arg_40]
0x10049b0bf  mov     [rbp+2190h+var_21B0], rax
0x10049b0c3  mov     rax, [rbp+2190h+arg_58]
0x10049b0ca  mov     [rbp+2190h+var_21E0], rax
0x10049b0ce  mov     r15, [rbp+2190h+arg_60]
0x10049b0d5  mov     [rbp+2190h+var_21F0], r15
0x10049b0d9  mov     rax, [rbp+2190h+arg_68]
0x10049b0e0  mov     [rbp+2190h+Destination], rax
0x10049b0e4  mov     rax, [r8+0D0h]
0x10049b0eb  mov     [rbp+2190h+var_2170], rax
0x10049b0ef  test    byte ptr [r8+218h], 4
0x10049b0f7  jnz     loc_101D11A35
0x10049b0fd  lea     rax, [r8+28h]
0x10049b101  jmp     short loc_10049B104
0x10049b104  mov     r13d, [rax]
0x10049b107  movzx   r12d, word ptr [rax+4]
0x10049b10c  lea     rdi, [rbx+2]
0x10049b110  lea     rdx, [rbp+2190h+var_2208]
0x10049b114  mov     rcx, rdi
0x10049b117  cmp     word ptr [rbx], 0
0x10049b11b  jnz     loc_101D11A4B
0x10049b121  call    ?GetXdesTs@FixedVarRecord@@AEBA?AVXdesTs@@XZ; FixedVarRecord::GetXdesTs(void)
0x10049b126  jmp     short loc_10049B129
0x10049b129  movzx   eax, byte ptr [rsi]
0x10049b12c  shr     eax, 3
0x10049b12f  and     eax, 1
0x10049b132  mov     [rbp+2190h+var_21D8], eax
0x10049b135  mov     rbx, [rbp+2190h+var_2200]
0x10049b139  mov     r8, [rbx+30h]
0x10049b13d  mov     [rbp+2190h+var_21F8], r8
0x10049b141  xor     ecx, ecx
0x10049b143  mov     [rbp+2190h+var_21B8], rcx
0x10049b147  mov     [rbp+2190h+var_21C0], rcx
0x10049b14b  mov     [rbp+2190h+var_2188], rcx
0x10049b14f  mov     [rbp+2190h+var_2180], rcx
0x10049b153  mov     [r15], rcx
0x10049b156  mov     eax, 2000h
0x10049b15b  lea     r15d, [rcx+1]
0x10049b15f  cmp     [rbp+2190h+var_2204], cx
0x10049b163  jnz     short loc_10049B16A
0x10049b165  cmp     [rbp+2190h+var_2208], ecx
0x10049b168  jz      short loc_10049B175
0x10049b16a  test    [r14+4], ax
0x10049b16f  jz      loc_101D11A57
0x10049b175  movzx   eax, byte ptr [rbx+250h]
0x10049b17c  test    al, 4
0x10049b17e  jnz     short loc_10049B190
0x10049b180  test    al, 5Ah
0x10049b182  jz      loc_101D11A80
0x10049b188  test    al, 8
0x10049b18a  jnz     loc_101D11BE0
0x10049b190  xor     eax, eax
0x10049b192  mov     r14d, eax
0x10049b195  xor     r15b, r15b
0x10049b198  movzx   eax, byte ptr [rbx+250h]
0x10049b19f  test    al, 4
0x10049b1a1  jnz     short loc_10049B1B8
0x10049b1a3  test    al, 5Ah
0x10049b1a5  jz      loc_101D11AC1
0x10049b1ab  test    byte ptr [rbx+250h], 40h
0x10049b1b2  jnz     loc_101D11DB7
0x10049b1b8  xor     sil, sil
0x10049b1bb  mov     rax, [rbx]
0x10049b1be  mov     rcx, rbx
0x10049b1c1  call    qword ptr [rax+88h]
0x10049b1c7  test    al, al
0x10049b1c9  jz      loc_101D121B1
0x10049b1cf  xor     eax, eax
0x10049b1d1  mov     [rbp+2190h+var_21A8], rax
0x10049b1d5  mov     r8d, [rbp+2190h+arg_28]
0x10049b1dc  mov     r9d, 4000h
0x10049b1e2  mov     r10d, 0FFFFDFFFh
0x10049b1e8  cmp     [rbp+2190h+var_2204], r12w
0x10049b1ed  jnz     short loc_10049B1F9
0x10049b1ef  cmp     [rbp+2190h+var_2208], r13d
0x10049b1f3  jz      loc_10049EC17
0x10049b1f9  test    r14d, r14d
0x10049b1fc  jnz     loc_10049EC17
0x10049b202  test    sil, sil
0x10049b205  jnz     loc_10049EC17
0x10049b20b  mov     r14d, [rbp+2190h+arg_48]
0x10049b212  mov     r12d, [rbp+2190h+arg_50]
0x10049b219  test    r14d, r14d
0x10049b21c  jnz     loc_101D1225C
0x10049b222  xor     esi, esi
0x10049b224  cmp     [rbp+2190h+Destination], 0
0x10049b229  jnz     loc_101D1229E
0x10049b22f  mov     r15, [rbp+2190h+var_2200]
0x10049b233  mov     rax, [r15]
0x10049b236  mov     rcx, r15
0x10049b239  call    qword ptr [rax+20h]
0x10049b23c  mov     rbx, [rbp+2190h+var_21C0]
0x10049b240  mov     r13, [rbp+2190h+var_21D0]
0x10049b244  test    al, al
0x10049b246  jnz     loc_101D12798
0x10049b24c  mov     rsi, [rbp+2190h+var_21E8]
0x10049b250  mov     rax, [r15]
0x10049b253  mov     rcx, r15
0x10049b256  call    qword ptr [rax+10h]
0x10049b259  mov     r9, [rbp+2190h+var_21F0]
0x10049b25d  test    al, al
0x10049b25f  jnz     loc_101D145B1
0x10049b265  mov     [rsp+2290h+var_2260], r9
0x10049b26a  mov     [rsp+2290h+var_2268], rbx
0x10049b26f  mov     [rsp+2290h+var_2270], r13
0x10049b274  mov     r9, [rbp+2190h+var_21C8]
0x10049b278  mov     r8, r15
0x10049b27b  mov     edx, [rbp+2190h+var_21D8]
0x10049b27e  lea     rcx, ?VersionStore@@3VAppendOnlyVerStoreMgr@@A; AppendOnlyVerStoreMgr VersionStore
0x10049b285  call    ?AddRecord@AppendOnlyVerStoreMgr@@QEAAXW4VersionStoreType@@PEAVXDES@@_KAEBVRecord@@PEBVVersionRecPtr@@AEAV5@@Z; AppendOnlyVerStoreMgr::AddRecord(VersionStoreType,XDES *,unsigned __int64,Record const &,VersionRecPtr const *,VersionRecPtr &)
0x10049b28a  movzx   eax, byte ptr [rsi+1]
0x10049b28e  sub     al, 3
0x10049b290  mov     rsi, [rbp+2190h+var_21F8]
0x10049b294  cmp     al, 1
0x10049b296  jbe     loc_101D145EC
0x10049b29c  mov     rax, [rbp+2190h+var_2170]
0x10049b2a0  test    rax, rax
0x10049b2a3  jz      short loc_10049B2B9
0x10049b2a5  cmp     dword ptr [rax+78h], 0
0x10049b2a9  jg      loc_101D126AF
0x10049b2af  cmp     dword ptr [rax+74h], 0
0x10049b2b3  jg      loc_101D126AF
0x10049b2b9  mov     r14d, 2
0x10049b2bf  mov     rax, [rbp+2190h+var_21E0]
0x10049b2c3  mov     [rax], r14d
0x10049b2c6  mov     r12, [rbp+2190h+var_21F0]
0x10049b2ca  mov     r8d, [rbp+2190h+arg_28]
0x10049b2d1  xor     r15d, r15d
0x10049b2d4  mov     r9d, 4000h
0x10049b2da  mov     r10d, 0FFFFDFFFh
0x10049b2e0  movsx   edx, word ptr [r12+6]
0x10049b2e6  mov     ecx, edx
0x10049b2e8  shr     ecx, 1
0x10049b2ea  xor     ecx, edx
0x10049b2ec  mov     eax, 2000h
0x10049b2f1  test    eax, ecx
0x10049b2f3  jnz     loc_101D146B8
0x10049b2f9  cmp     r8d, 1
0x10049b2fd  jz      loc_10049E65E
0x10049b303  cmp     dword ptr [rbp+2190h+var_2180], 0
0x10049b307  jnz     loc_101D16FE5
0x10049b30d  mov     rcx, [rbp+2190h+var_50]
0x10049b314  xor     rcx, rsp; StackCookie
0x10049b317  call    __security_check_cookie
0x10049b31c  add     rsp, 2258h
0x10049b323  pop     r15
0x10049b325  pop     r14
0x10049b327  pop     r13
0x10049b329  pop     r12
0x10049b32b  pop     rdi
0x10049b32c  pop     rsi
0x10049b32d  pop     rbx
0x10049b32e  pop     rbp
0x10049b32f  retn
0x10049e65e  inc     qword ptr [rsi+0D0h]
0x10049e665  jmp     loc_10049B303
0x10049ec17  mov     rax, [rbp+2190h+var_2170]
0x10049ec1b  test    rax, rax
0x10049ec1e  jz      short loc_10049EC34
0x10049ec20  cmp     dword ptr [rax+78h], 0
0x10049ec24  jg      loc_10049B20B
0x10049ec2a  cmp     dword ptr [rax+74h], 0
0x10049ec2e  jg      loc_10049B20B
0x10049ec34  test    r15b, r15b
0x10049ec37  jnz     loc_10049B20B
0x10049ec3d  mov     rax, [rbp+2190h+var_21E0]
0x10049ec41  mov     ebx, 1
0x10049ec46  mov     [rax], ebx
0x10049ec48  test    r14d, r14d
0x10049ec4b  jnz     loc_101D16FC7
0x10049ec51  test    sil, sil
0x10049ec54  jnz     loc_101D16FC7
0x10049ec5a  mov     rsi, [rbp+2190h+var_21D0]
0x10049ec5e  lea     rdx, [rbp+2190h+var_2190]
0x10049ec62  mov     rcx, rdi
0x10049ec65  cmp     [rsi], r14w
0x10049ec69  jnz     loc_101D146D4
0x10049ec6f  call    ?GetVersionRecPtr@FixedVarRecord@@AEBA?AVVersionRecPtr@@XZ; FixedVarRecord::GetVersionRecPtr(void)
0x10049ec74  jmp     short loc_10049EC77
0x10049ec77  mov     eax, [rbp+2190h+var_2190]
0x10049ec7a  mov     r12, [rbp+2190h+var_21F0]
0x10049ec7e  mov     [r12], eax
0x10049ec82  movzx   eax, [rbp+2190h+var_218C]
0x10049ec86  mov     [r12+4], ax
0x10049ec8c  movsx   eax, [rbp+2190h+var_218A]
0x10049ec90  mov     [r12+6], ax
0x10049ec96  mov     edx, eax
0x10049ec98  mov     r8d, eax
0x10049ec9b  shr     r8d, 0Eh
0x10049ec9f  and     r8d, ebx
0x10049eca2  shr     edx, 0Dh
0x10049eca5  and     edx, ebx
0x10049eca7  mov     r9d, 4000h
0x10049ecad  movzx   ecx, ax
0x10049ecb0  mov     r10d, 0FFFFDFFFh
0x10049ecb6  cmp     edx, r8d
0x10049ecb9  jnz     loc_101D146E0
0x10049ecbf  mov     r11d, 2000h
0x10049ecc5  mov     edi, 0FFFFFFFCh
0x10049ecca  cmp     di, cx
0x10049eccd  jz      loc_101D146FF
0x10049ecd3  mov     rsi, [rbp+2190h+var_21F8]
0x10049ecd7  inc     qword ptr [rsi+120h]
0x10049ecde  jmp     loc_10049B2CA
0x100611451  add     eax, [rbx]
0x100611453  add     eax, [rcx]
0x100611455  add     eax, [rbx]
0x100611457  add     eax, [rdx]
0x100611459  add     eax, [rbx]
0x10061145b  add     eax, [rax]
0x10061145d  add     eax, [rbx]
0x10061145f  add     eax, [rax]
0x100611461  add     eax, [rbx]
0x100611463  add     eax, [rax]
0x100611465  add     eax, [rbx]
0x100611467  add     eax, [rax]
0x100611469  add     eax, [rbx]
0x10061146b  add     eax, [rax]
0x10061146d  nop     dword ptr [rax]
0x101d11a35  mov     rax, [r8]
0x101d11a38  mov     rcx, r8
0x101d11a3b  call    qword ptr [rax+1E8h]
0x101d11a41  add     rax, 28h ; '('
0x101d11a45  jmp     loc_10049B104
0x101d11a4b  call    ?GetXdesTs@CDRecord@@AEBA?AVXdesTs@@XZ; CDRecord::GetXdesTs(void)
0x101d11a50  nop
0x101d11a51  jmp     loc_10049B129
0x101d11a57  mov     [rsp+2290h+var_2270], rcx
0x101d11a5c  mov     r9d, 1C8h
0x101d11a62  lea     r8, aRecvermgrCpp; "RecVerMgr.cpp"
0x101d11a69  lea     rdx, aPpageIsflagPag; "pPage->IsFlag(PAGE::VERSION_INFO)"
0x101d11a70  mov     ecx, r15d
0x101d11a73  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101d11a79  nop
0x101d11a7a  jmp     loc_10049B175
0x101d11a80  test    [rbx+218h], r15b
0x101d11a87  jz      loc_10049B190
0x101d11a8d  cmp     qword ptr [rbx+0D0h], 0
0x101d11a95  jnz     short loc_101D11B0D
0x101d11a97  mov     rax, [rbx]
0x101d11a9a  mov     rcx, rbx
0x101d11a9d  call    qword ptr [rax+88h]
0x101d11aa3  test    al, al
0x101d11aa5  jz      short loc_101D11B0D
0x101d11aa7  mov     rax, [rbx]
0x101d11aaa  mov     rcx, rbx
0x101d11aad  call    qword ptr [rax+18h]
0x101d11ab0  test    al, al
0x101d11ab2  jnz     short loc_101D11B0D
0x101d11ab4  or      byte ptr [rbx+250h], 4
0x101d11abb  jmp     loc_10049B190
0x101d11ac1  test    byte ptr [rbx+218h], 1
0x101d11ac8  jz      loc_10049B1B8
0x101d11ace  cmp     qword ptr [rbx+0D0h], 0
0x101d11ad6  jnz     loc_101D11CED
0x101d11adc  mov     rax, [rbx]
0x101d11adf  mov     rcx, rbx
0x101d11ae2  call    qword ptr [rax+88h]
0x101d11ae8  test    al, al
0x101d11aea  jz      loc_101D11CED
0x101d11af0  mov     rax, [rbx]
0x101d11af3  mov     rcx, rbx
0x101d11af6  call    qword ptr [rax+18h]
0x101d11af9  test    al, al
0x101d11afb  jnz     loc_101D11CED
0x101d11b01  or      byte ptr [rbx+250h], 4
0x101d11b08  jmp     loc_10049B1B8
0x101d11b0d  mov     rcx, rbx; this
0x101d11b10  call    ?IsActive@XDES@@QEBAHXZ; XDES::IsActive(void)
0x101d11b15  test    eax, eax
0x101d11b17  jnz     short loc_101D11B25
0x101d11b19  mov     rax, [rbx]
0x101d11b1c  mov     rcx, rbx
0x101d11b1f  call    qword ptr [rax+270h]
0x101d11b25  test    byte ptr [rbx+218h], 4
0x101d11b2c  jz      short loc_101D11B5C
0x101d11b2e  mov     rax, [rbx]
  ... truncated ...
```
