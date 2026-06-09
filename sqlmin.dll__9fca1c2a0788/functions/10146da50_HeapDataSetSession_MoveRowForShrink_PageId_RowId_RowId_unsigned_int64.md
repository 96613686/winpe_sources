# HeapDataSetSession::MoveRowForShrink(PageId &,RowId &,RowId &,unsigned __int64 *)

- ea: `0x10146da50`
- end: `0x101475708`
- name: `?MoveRowForShrink@HeapDataSetSession@@QEAAXAEAVPageId@@AEAURowId@@1PEA_K@Z`
- size: `31928`
- prototype: `void __fastcall(HeapDataSetSession *__hidden this, struct PageId *, struct RowId *, struct RowId *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `79`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x101f28420`

## callees

- `0x100401490`
- `0x100402000`
- `0x100402740`
- `0x10040dfe0`
- `0x10040fa20`
- `0x100415e90`
- `0x100418740`
- `0x100427840`
- `0x10042d300`
- `0x10043e110`
- `0x100441e00`
- `0x100441e40`
- `0x100447b40`
- `0x100449af0`
- `0x10044bad0`
- `0x100450ee0`
- `0x10046bf90`
- `0x10046c170`
- `0x1004807a0`
- `0x10048c200`
- `0x100493040`
- `0x100606870`
- `0x100626480`
- `0x10063ea30`
- `0x1006c5960`
- `0x10072ceb0`
- `0x10072dbd0`
- `0x1007c1a10`
- `0x1007c1a20`
- `0x1011f8090`
- `0x101253e30`
- `0x101278130`
- `0x1012c8f30`
- `0x1012c8f90`
- `0x1012c9010`
- `0x1012efeb0`
- `0x1012f0350`
- `0x1012f91c0`
- `0x1012f9640`
- `0x10130cba0`
- `0x10130d530`
- `0x10132dc00`
- `0x10132f140`
- `0x1013307a0`
- `0x101330d30`
- `0x1013310d0`
- `0x101331b90`
- `0x101376e30`
- `0x10137dfc0`
- `0x10137e0d0`

## import_xrefs

- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101473e6d`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10147409a`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1014742c0`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1014743d6`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101474511`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10146db88`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10146db88`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146e9fb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146ea9d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146eceb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146ed8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f277`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f31f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f5a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f64b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014703fb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470493`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470714`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014707b6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470c73`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470d0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470f7f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471021`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147130a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147144d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147151b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014715e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147183f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014718fe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471c7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471d50`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471e21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472087`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472146`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472319`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014723eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014724bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147271c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014727db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473194`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473261`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473329`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147359c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473669`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147381c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014738e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014739b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473c1f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473cde`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473f07`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473f52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473fb2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474129`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474174`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014741d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474730`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014747fd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014748c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474b2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474be4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146e9fb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146ea9d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146eceb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146ed8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f277`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f31f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f5a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10146f64b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014703fb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470493`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470714`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014707b6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470c73`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470d0c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101470f7f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471021`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147130a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147144d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147151b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014715e6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147183f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014718fe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471c7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471d50`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101471e21`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472087`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472146`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101472319`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014723eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014724bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147271c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014727db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473194`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473261`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473329`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147359c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473669`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10147381c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014738e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014739b1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473c1f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473cde`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473f07`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473f52`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101473fb2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474129`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474174`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014741d4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474730`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014747fd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014748c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474b2f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101474be4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147127e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471427`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014714f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014715c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471819`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014718d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471c58`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471d2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471dfb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472061`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472120`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014722f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014723c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472496`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014726f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014727b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147316e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147323b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473303`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473576`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473635`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014737f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014738c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147398b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473bf9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473cb8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147470a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014747d7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147489f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101474b09`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147127e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471427`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014714f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014715c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471819`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014718d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471c58`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471d2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101471dfb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472061`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472120`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014722f3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014723c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101472496`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014726f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014727b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147316e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147323b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473303`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473576`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473635`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014737f6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014738c3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147398b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473bf9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101473cb8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147470a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014747d7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10147489f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101474b09`
- `sqldk!SystemThread_TlsIndex` at `0x1014713d2`
- `sqldk!SystemThread_TlsIndex` at `0x1014714a0`
- `sqldk!SystemThread_TlsIndex` at `0x10147156b`
- `sqldk!SystemThread_TlsIndex` at `0x1014717c4`
- `sqldk!SystemThread_TlsIndex` at `0x101471883`
- `sqldk!SystemThread_TlsIndex` at `0x101471c03`
- `sqldk!SystemThread_TlsIndex` at `0x101471cd5`
- `sqldk!SystemThread_TlsIndex` at `0x101471da6`
- `sqldk!SystemThread_TlsIndex` at `0x10147200c`
- `sqldk!SystemThread_TlsIndex` at `0x1014720cb`
- `sqldk!SystemThread_TlsIndex` at `0x10147229e`
- `sqldk!SystemThread_TlsIndex` at `0x101472370`
- `sqldk!SystemThread_TlsIndex` at `0x101472441`
- `sqldk!SystemThread_TlsIndex` at `0x1014726a1`
- `sqldk!SystemThread_TlsIndex` at `0x101472760`
- `sqldk!SystemThread_TlsIndex` at `0x101473119`
- `sqldk!SystemThread_TlsIndex` at `0x1014731e6`
- `sqldk!SystemThread_TlsIndex` at `0x1014732ae`
- `sqldk!SystemThread_TlsIndex` at `0x101473521`
- `sqldk!SystemThread_TlsIndex` at `0x1014735e0`
- `sqldk!SystemThread_TlsIndex` at `0x1014737a1`
- `sqldk!SystemThread_TlsIndex` at `0x10147386e`
- `sqldk!SystemThread_TlsIndex` at `0x101473936`
- `sqldk!SystemThread_TlsIndex` at `0x101473ba4`
- `sqldk!SystemThread_TlsIndex` at `0x101473c63`
- `sqldk!SystemThread_TlsIndex` at `0x1014746b5`
- `sqldk!SystemThread_TlsIndex` at `0x101474782`

## string_xrefs

- `0x10146db75`: `Sql\Ntdbms\storeng\dfs\access\HeapDataSet.h`
- `0x101473f48`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x10147416a`: `!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101473fa4`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x1014741c6`: `(!m_pHobtAccess->IsOibLobSourceRowset () || m_pHobtAccess->IsOibLobSourceRowsetResumable()) || !m_pHobtAccess->IsCompressedRowstore ()`
- `0x101471300`: `oldRowId.rid_page == tempNewRowId.rid_page && oldRowId.rid_slot == tempNewRowId.rid_slot`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HeapDataSetSession::MoveRowForShrink(
        struct IMemObj **this,
        struct PageId *a2,
        struct RowId *a3,
        struct RowId *a4,
        unsigned __int64 *a5)
{
  unsigned int v7; // r12d
  char *v8; // rax
  char *v9; // rcx
  HeapRowObject *v10; // r13
  _QWORD *v11; // rcx
  __int64 v12; // rax
  HeapRowObject *v13; // rax
  int v14; // r8d
  struct IMemObj *v15; // rbx
  __int64 v16; // r8
  char v17; // cl
  char v18; // cl
  char v19; // dl
  char v20; // dl
  Page ***v21; // r14
  HeapPageManager *v22; // rcx
  _QWORD *v23; // rsi
  __int64 v24; // r9
  __int64 v25; // r15
  int v26; // ecx
  __int64 v27; // r8
  __int64 v28; // rax
  int v29; // ecx
  __int64 v30; // rdx
  Page *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // edx
  unsigned __int16 v36; // r8
  __int16 v37; // cx
  __int64 v38; // rax
  int v39; // eax
  int v40; // edi
  Page *v41; // rcx
  Page **v42; // rcx
  int ValidSlotId; // eax
  __int64 v44; // r8
  int v45; // r15d
  int v46; // esi
  __int64 v47; // rax
  int v48; // ecx
  Record *v49; // rbx
  struct HeapRowObject *v50; // r14
  HeapPageManager ***v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  HeapRowObject *v55; // rdi
  LckInfo *v56; // rbx
  char *v57; // r15
  int v58; // ecx
  __int64 v59; // rax
  __int64 v60; // rcx
  int v61; // edx
  __int64 v62; // r9
  __int64 v63; // rdx
  Page *v64; // rcx
  __int64 v65; // rdx
  int v66; // r13d
  Page **v67; // r15
  struct IMemObj **v68; // rcx
  struct PageComprInfo *v69; // rbx
  unsigned __int8 *v70; // r12
  __int64 Lsn; // rax
  __int64 v72; // rdi
  __int16 v73; // dx
  int v74; // ecx
  __int64 v75; // rcx
  __int64 v76; // rcx
  PageDictionary *v77; // r9
  unsigned __int8 *v78; // rsi
  unsigned int v79; // r8d
  unsigned __int8 v80; // dl
  __int16 v81; // dx
  __int16 v82; // cx
  unsigned __int16 v83; // ax
  unsigned int v84; // eax
  int v85; // edx
  int v86; // r13d
  __int64 v87; // rax
  PageComprInfoCache *v88; // rcx
  int v89; // esi
  char *v90; // rdi
  char v91; // dl
  unsigned __int16 v92; // cx
  __int16 v93; // dx
  __int64 v94; // rcx
  int v95; // edx
  int v96; // eax
  __int64 v97; // rcx
  int v98; // edx
  Page **v99; // r15
  __int64 v100; // rcx
  struct IMemObj **v101; // r13
  struct PageComprInfo *v102; // rbx
  unsigned __int8 *v103; // r12
  __int64 v104; // rax
  __int64 v105; // rdi
  __int16 v106; // dx
  int v107; // ecx
  __int64 v108; // rcx
  __int64 v109; // rcx
  PageDictionary *v110; // r10
  unsigned __int8 *v111; // rsi
  int v112; // r8d
  unsigned int v113; // r9d
  unsigned __int8 v114; // dl
  __int16 v115; // dx
  __int16 v116; // cx
  unsigned __int16 v117; // ax
  unsigned int v118; // eax
  int v119; // edx
  int v120; // r13d
  __int64 v121; // rax
  PageComprInfoCache *v122; // rcx
  int v123; // esi
  char *v124; // rdi
  char v125; // dl
  unsigned __int16 v126; // cx
  __int16 v127; // dx
  HeapRowObject *v128; // rbx
  __int64 v129; // rdx
  bool v130; // bl
  int refreshed; // eax
  __int64 v132; // rcx
  char v133; // al
  struct HeapRowObject *v134; // rdi
  __int64 v135; // rax
  struct HeapRowObject *v136; // r14
  HeapPageManager *v137; // rcx
  HeapPageManager *v138; // r15
  __int64 v139; // r8
  __int64 v140; // r9
  HeapPageManager *v141; // r12
  int v142; // ecx
  HeapPageManager **v143; // rax
  int v144; // ecx
  __int64 v145; // rdx
  HeapPageManager *v146; // rcx
  HeapPageManager **v147; // rax
  __int64 v148; // rdx
  HeapPageManager **v149; // rax
  int v150; // edx
  unsigned __int16 v151; // r8
  __int16 v152; // cx
  HeapPageManager **v153; // rax
  int v154; // eax
  int v155; // r13d
  struct HeapRowObject *v156; // rsi
  int v157; // r15d
  unsigned int v158; // edi
  unsigned int v159; // r14d
  struct HeapRowObject *v160; // r14
  __int64 v161; // rax
  struct HeapRowObject *v162; // rbx
  char *v163; // r12
  HeapRowObject *v164; // rbx
  LckInfo *v165; // rdi
  char *v166; // rsi
  int v167; // ecx
  __int64 v168; // rax
  __int64 v169; // rcx
  int v170; // edx
  __int64 v171; // r9
  __int64 v172; // rdx
  __int64 v173; // rcx
  __int64 v174; // rdx
  int v175; // r15d
  __int64 v176; // r14
  struct IMemObj **v177; // rcx
  struct IMemObj **v178; // r13
  struct PageComprInfo *v179; // rbx
  unsigned __int8 *v180; // r15
  __int64 v181; // rax
  __int64 v182; // rdi
  __int16 v183; // dx
  int v184; // ecx
  __int64 v185; // rcx
  __int64 v186; // rcx
  PageDictionary *v187; // r8
  unsigned __int8 *v188; // rsi
  unsigned __int8 v189; // dl
  __int16 v190; // dx
  __int16 v191; // cx
  unsigned __int16 v192; // ax
  unsigned int v193; // eax
  int v194; // r13d
  __int64 v195; // rdx
  PageComprInfoCache *v196; // rcx
  int v197; // esi
  char *v198; // rdi
  char v199; // dl
  unsigned __int16 v200; // cx
  __int16 v201; // dx
  __int64 v202; // rcx
  int v203; // edx
  int v204; // eax
  __int64 v205; // rcx
  int v206; // edx
  __int64 v207; // r14
  __int64 v208; // rcx
  struct IMemObj **v209; // r13
  struct PageComprInfo *v210; // rbx
  unsigned __int8 *v211; // r15
  __int64 v212; // rax
  __int64 v213; // rdi
  __int16 v214; // dx
  int v215; // ecx
  __int64 v216; // rcx
  __int64 v217; // r8
  PageDictionary *v218; // rcx
  unsigned __int8 *v219; // rsi
  unsigned __int8 v220; // dl
  __int16 v221; // dx
  __int16 v222; // cx
  unsigned __int16 v223; // ax
  unsigned int v224; // eax
  int v225; // r13d
  __int64 v226; // rdx
  PageComprInfoCache *v227; // rcx
  int v228; // esi
  char *v229; // rdi
  char v230; // dl
  unsigned __int16 v231; // cx
  __int16 v232; // dx
  HeapRowObject *v233; // rbx
  __int64 v234; // rdx
  bool v235; // bl
  int v236; // eax
  __int64 v237; // rcx
  char v238; // al
  Record *Record; // rax
  const struct RowId *BackPtr; // rbx
  __int64 v241; // rax
  __int64 v242; // rax
  __int64 v243; // rsi
  __int64 v244; // rdx
  _BYTE *v245; // r8
  char v246; // al
  _BYTE *v247; // rcx
  int v248; // r9d
  unsigned __int16 *v249; // r14
  unsigned __int16 v250; // ax
  __int64 v251; // rax
  __int64 v252; // rax
  unsigned int v253; // edx
  __int64 v254; // rax
  __int64 v255; // rax
  unsigned int v256; // ecx
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rcx
  __int64 v261; // rax
  unsigned int v262; // edi
  unsigned int v263; // eax
  unsigned __int16 v264; // dx
  __int64 v265; // rdx
  __int16 v266; // cx
  __int16 v267; // cx
  int v268; // eax
  struct RecVersioningInfo *VersioningInfo; // rax
  __int64 v270; // rdx
  int v271; // r8d
  unsigned __int64 v272; // r8
  int v273; // edx
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rax
  __int64 v277; // rax
  unsigned int v278; // edx
  char v279; // cl
  int HasSparseVector; // eax
  unsigned __int8 *v281; // r8
  unsigned __int8 *v282; // rdx
  int v283; // ecx
  unsigned int v284; // ebx
  unsigned int v285; // ecx
  __int16 v286; // ax
  __int16 v287; // cx
  _QWORD *v288; // rax
  __int64 v289; // rax
  __int64 v290; // rbx
  int RowAbortState; // eax
  bool v292; // di
  unsigned int v293; // edx
  unsigned __int8 *v294; // rdi
  unsigned __int16 v295; // r8
  __int64 v296; // rax
  __int64 v297; // rax
  unsigned int v298; // r9d
  __int64 v299; // rax
  __int64 v300; // rax
  __int64 v301; // rax
  __int64 v302; // rax
  unsigned __int8 *v303; // rax
  unsigned int v304; // ebx
  unsigned __int16 v305; // r10
  unsigned __int8 *v306; // r8
  __int16 v307; // ax
  __int16 v308; // cx
  struct RecVersioningInfo *v309; // rax
  __int64 v310; // rdx
  int v311; // r8d
  __int64 v312; // rax
  __int64 v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  char v316; // cl
  int v317; // r9d
  unsigned __int8 v318; // cl
  bool v319; // zf
  unsigned int v320; // r8d
  unsigned int v321; // eax
  unsigned __int8 *v322; // rdi
  unsigned __int16 v323; // r8
  __int64 v324; // rax
  __int64 v325; // rax
  unsigned int v326; // r9d
  __int64 v327; // rax
  __int64 v328; // rax
  __int64 v329; // rax
  __int64 v330; // rax
  unsigned __int8 *v331; // rax
  unsigned int v332; // ebx
  unsigned __int16 v333; // r10
  unsigned __int8 *v334; // r8
  __int16 v335; // r9
  __int16 v336; // cx
  struct RecVersioningInfo *v337; // rax
  __int64 v338; // rdx
  int v339; // r8d
  __int64 v340; // rax
  __int64 v341; // rax
  __int64 v342; // rax
  __int64 v343; // rax
  char v344; // cl
  int v345; // r9d
  bool v346; // zf
  unsigned int v347; // r8d
  unsigned int v348; // eax
  unsigned int v349; // eax
  struct HeapRowObject *v350; // r14
  HeapDataSetSession *v351; // rsi
  HeapPageManager ***v352; // r12
  __int64 v353; // rcx
  __int64 v354; // rax
  __int64 v355; // rax
  struct HeapRowObject *v356; // rbx
  __int64 v357; // rax
  struct HeapRowObject *v358; // r15
  __int64 v359; // rdx
  char v360; // r9
  __int64 v361; // rcx
  struct HeapRowObject *v362; // r13
  __int64 v363; // rbx
  void *v364; // rsp
  _QWORD *v365; // rcx
  __int64 v366; // rdx
  _QWORD *v367; // r8
  struct HeapRowObject *v368; // r14
  __int64 v369; // rdx
  int v370; // eax
  int v371; // ecx
  struct HeapRowObject *v372; // r14
  _OWORD *v373; // rdi
  _OWORD *v374; // rax
  unsigned __int8 *v375; // rcx
  __int64 v376; // rdx
  struct HeapRowObject *v377; // rsi
  char v378; // bl
  _OWORD *v379; // rax
  unsigned __int8 *v380; // rcx
  __int64 v381; // rdx
  HeapRowObject **v382; // rax
  HeapRowObject *v383; // r13
  Record *v384; // rdi
  __int16 *v385; // rbx
  __int64 v386; // rdx
  char *v387; // r8
  char v388; // al
  unsigned __int16 *v389; // rsi
  unsigned __int16 v390; // ax
  __int64 v391; // rax
  __int64 v392; // rax
  unsigned int v393; // edx
  __int64 v394; // rax
  __int64 v395; // rax
  unsigned int v396; // ecx
  __int64 v397; // rax
  __int64 v398; // rax
  unsigned __int16 v399; // ax
  __int64 v400; // rdx
  __int64 v401; // r9
  __int64 v402; // rax
  unsigned int v403; // edi
  unsigned int v404; // ecx
  unsigned int v405; // eax
  unsigned __int16 v406; // cx
  __int64 v407; // rdx
  __int16 v408; // cx
  __int16 v409; // cx
  struct RecVersioningInfo *v410; // rax
  __int64 v411; // rdx
  int v412; // r8d
  unsigned __int64 v413; // rdx
  int v414; // ecx
  __int64 v415; // rax
  __int64 v416; // rax
  __int64 v417; // rax
  __int64 v418; // rax
  unsigned int v419; // r15d
  char v420; // cl
  char v421; // cl
  __int64 v422; // rdx
  char *v423; // r8
  char v424; // al
  unsigned __int16 *v425; // rsi
  unsigned __int16 v426; // ax
  __int64 v427; // rax
  __int64 v428; // rax
  unsigned int v429; // edx
  __int64 v430; // rax
  __int64 v431; // rax
  unsigned int v432; // ecx
  __int64 v433; // rax
  __int64 v434; // rax
  unsigned __int16 v435; // ax
  __int64 v436; // rdx
  __int64 v437; // rax
  unsigned int v438; // edi
  unsigned int v439; // ecx
  unsigned int v440; // eax
  unsigned __int16 v441; // dx
  __int64 v442; // rdx
  __int16 v443; // cx
  __int16 v444; // cx
  struct RecVersioningInfo *v445; // rax
  __int64 v446; // rdx
  int v447; // r8d
  unsigned __int64 v448; // rdx
  int v449; // ecx
  __int64 v450; // rax
  __int64 v451; // rax
  __int64 v452; // rax
  __int64 v453; // rax
  char v454; // cl
  bool v455; // zf
  int *v456; // rsi
  char v457; // al
  XDES *v458; // rax
  int DoesXactGenVersion; // eax
  __int64 v460; // rax
  HoBtAccess *v461; // rdi
  __int64 v462; // rax
  bool v463; // cc
  int v464; // eax
  __int64 v465; // rcx
  int v466; // eax
  char v467; // al
  XDES *v468; // rax
  int v469; // eax
  __int64 v470; // rax
  HoBtAccess *v471; // rdi
  __int64 v472; // rax
  bool v473; // cc
  int v474; // eax
  __int64 v475; // rcx
  int v476; // eax
  char v477; // al
  XDES *v478; // rax
  int v479; // eax
  __int64 v480; // rax
  char v481; // al
  XDES *v482; // rax
  int v483; // eax
  __int64 v484; // rax
  __int64 v485; // rdi
  char v486; // al
  XDES *v487; // rax
  int v488; // eax
  __int64 v489; // rax
  Record *v490; // rdi
  int v491; // r8d
  __int16 v492; // dx
  __int64 v493; // rbx
  Record *v494; // rdi
  __int64 v495; // rdx
  char *v496; // r8
  char v497; // al
  unsigned __int16 *v498; // rsi
  unsigned __int16 v499; // ax
  __int64 v500; // rax
  __int64 v501; // rax
  unsigned int v502; // edx
  __int64 v503; // rax
  __int64 v504; // rax
  unsigned int v505; // ecx
  __int64 v506; // rax
  __int64 v507; // rax
  unsigned __int16 v508; // ax
  __int64 v509; // rdx
  __int64 v510; // rax
  unsigned int v511; // edi
  unsigned int v512; // ecx
  unsigned int v513; // eax
  unsigned __int16 v514; // dx
  __int64 v515; // rdx
  __int16 v516; // cx
  __int16 v517; // cx
  struct RecVersioningInfo *v518; // rax
  __int64 v519; // rdx
  int v520; // r8d
  unsigned __int64 v521; // rdx
  int v522; // ecx
  __int64 v523; // rax
  __int64 v524; // rax
  __int64 v525; // rax
  __int64 v526; // rax
  _BYTE *v527; // rax
  HeapPageManager **v528; // rbx
  int v529; // esi
  BOOL v530; // edi
  __int64 FirstDataIAM; // rax
  HeapRowObject *v532; // rsi
  __int64 v533; // rax
  bool v534; // cl
  bool v535; // al
  char v536; // dl
  char v537; // di
  unsigned __int64 I8; // rax
  int v539; // ebx
  __int64 v540; // r8
  __int16 v541; // cx
  HeapPageManager *v542; // r9
  __int64 v543; // rax
  int DataLock; // eax
  _OWORD *v545; // rax
  unsigned __int8 *v546; // rcx
  __int64 v547; // rdx
  HeapPageManager *v548; // rcx
  unsigned int v549; // eax
  unsigned int v550; // eax
  unsigned int v551; // eax
  _OWORD *v552; // rax
  unsigned __int8 *v553; // rcx
  __int64 v554; // rdx
  HeapPageManager **v555; // rcx
  HeapPageManager *v556; // rcx
  _OWORD *v557; // rax
  __int64 v558; // rcx
  __int64 v559; // rcx
  struct HeapRowObject *v560; // r14
  unsigned __int64 *v561; // [rsp+0h] [rbp-24B0h]
  int v562; // [rsp+8h] [rbp-24A8h]
  bool v563[8]; // [rsp+8h] [rbp-24A8h]
  int v564; // [rsp+18h] [rbp-2498h]
  __int128 v565; // [rsp+50h] [rbp-2460h] BYREF
  __int16 v566; // [rsp+60h] [rbp-2450h]
  __int16 v567; // [rsp+62h] [rbp-244Eh]
  int v568; // [rsp+64h] [rbp-244Ch]
  __int64 v569; // [rsp+68h] [rbp-2448h]
  _BYTE v570[22]; // [rsp+70h] [rbp-2440h] BYREF
  __int16 v571; // [rsp+86h] [rbp-242Ah]
  __int64 v572; // [rsp+88h] [rbp-2428h]
  __int64 v573; // [rsp+90h] [rbp-2420h]
  __int64 v574; // [rsp+98h] [rbp-2418h]
  __int128 v575; // [rsp+A0h] [rbp-2410h]
  __int128 v576; // [rsp+B0h] [rbp-2400h]
  __int64 v577; // [rsp+C0h] [rbp-23F0h]
  char v578; // [rsp+D0h] [rbp-23E0h] BYREF
  __int64 v579; // [rsp+2460h] [rbp-50h]
  _DWORD v580[2]; // [rsp+2470h] [rbp-40h] BYREF
  __int64 v581; // [rsp+2478h] [rbp-38h]
  __int64 v582; // [rsp+2480h] [rbp-30h]
  __int64 v583; // [rsp+248Eh] [rbp-22h]
  __int64 v584; // [rsp+2498h] [rbp-18h]
  unsigned int v585; // [rsp+24B0h] [rbp+0h]
  __int16 v586; // [rsp+24B4h] [rbp+4h]
  int v587; // [rsp+24C0h] [rbp+10h] BYREF
  __int16 v588; // [rsp+24C4h] [rbp+14h]
  __int16 v589; // [rsp+24D0h] [rbp+20h]
  __int16 v590; // [rsp+24D8h] [rbp+28h] BYREF
  __int16 v591; // [rsp+24DAh] [rbp+2Ah] BYREF
  unsigned int v592; // [rsp+24DCh] [rbp+2Ch]
  unsigned __int8 *v593; // [rsp+24E0h] [rbp+30h]
  __int64 v594; // [rsp+24E8h] [rbp+38h]
  unsigned int v595; // [rsp+24F0h] [rbp+40h]
  unsigned __int16 v596; // [rsp+24F4h] [rbp+44h]
  unsigned __int64 v597; // [rsp+24F6h] [rbp+46h]
  _TBYTE v598; // [rsp+24FEh] [rbp+4Eh]
  unsigned int v599; // [rsp+2508h] [rbp+58h]
  int v600; // [rsp+2510h] [rbp+60h]
  unsigned int v601; // [rsp+2520h] [rbp+70h] BYREF
  __int16 v602; // [rsp+2524h] [rbp+74h]
  int v603; // [rsp+2530h] [rbp+80h]
  unsigned int v604; // [rsp+2534h] [rbp+84h]
  struct HeapRowObject *v605; // [rsp+2538h] [rbp+88h] BYREF
  int v606; // [rsp+2540h] [rbp+90h] BYREF
  __int16 v607; // [rsp+2544h] [rbp+94h]
  struct HeapRowObject *v608; // [rsp+2548h] [rbp+98h]
  unsigned __int8 v609[4]; // [rsp+2550h] [rbp+A0h] BYREF
  int v610; // [rsp+2554h] [rbp+A4h] BYREF
  __int16 v611; // [rsp+2558h] [rbp+A8h]
  int v612; // [rsp+255Ch] [rbp+ACh] BYREF
  __int16 v613; // [rsp+2560h] [rbp+B0h]
  int v614; // [rsp+2564h] [rbp+B4h] BYREF
  __int16 v615; // [rsp+2568h] [rbp+B8h]
  HeapRowObject *v616; // [rsp+2570h] [rbp+C0h]
  __int64 v617; // [rsp+2578h] [rbp+C8h] BYREF
  __int64 v618; // [rsp+2580h] [rbp+D0h] BYREF
  struct HeapRowObject *v619; // [rsp+2588h] [rbp+D8h]
  struct HeapRowObject *v620; // [rsp+2590h] [rbp+E0h]
  struct IMemObj **v621; // [rsp+2598h] [rbp+E8h]
  Record *v622; // [rsp+25A0h] [rbp+F0h]
  LckInfo *v623; // [rsp+25A8h] [rbp+F8h]
  __int128 v624; // [rsp+25B0h] [rbp+100h]
  HoBtAccess *v625; // [rsp+25C0h] [rbp+110h]
  int v626; // [rsp+25D0h] [rbp+120h] BYREF
  __int16 v627; // [rsp+25D4h] [rbp+124h]
  int v628; // [rsp+25D6h] [rbp+126h] BYREF
  __int16 v629; // [rsp+25DAh] [rbp+12Ah]
  int v630; // [rsp+25DCh] [rbp+12Ch] BYREF
  __int16 v631; // [rsp+25E0h] [rbp+130h]
  int v632; // [rsp+25E2h] [rbp+132h] BYREF
  __int16 v633; // [rsp+25E6h] [rbp+136h]
  __int64 v634; // [rsp+25E8h] [rbp+138h]
  HeapDataSetSession *v635; // [rsp+25F0h] [rbp+140h]
  int v636; // [rsp+25F8h] [rbp+148h] BYREF
  __int16 v637; // [rsp+25FCh] [rbp+14Ch]
  int v638; // [rsp+2600h] [rbp+150h] BYREF
  __int16 v639; // [rsp+2604h] [rbp+154h]
  int v640; // [rsp+2610h] [rbp+160h] BYREF
  __int16 v641; // [rsp+2614h] [rbp+164h]
  int v642; // [rsp+2620h] [rbp+170h] BYREF
  __int16 v643; // [rsp+2624h] [rbp+174h]
  __int16 v644; // [rsp+2626h] [rbp+176h]
  int v645; // [rsp+2628h] [rbp+178h] BYREF
  __int16 v646; // [rsp+262Ch] [rbp+17Ch]
  __int16 v647; // [rsp+262Eh] [rbp+17Eh]
  int v648; // [rsp+2630h] [rbp+180h] BYREF
  __int16 v649; // [rsp+2634h] [rbp+184h]
  __int16 v650; // [rsp+2636h] [rbp+186h]
  int v651; // [rsp+2638h] [rbp+188h] BYREF
  __int16 v652; // [rsp+263Ch] [rbp+18Ch]
  __int16 v653; // [rsp+263Eh] [rbp+18Eh]
  _BYTE v654[4]; // [rsp+2640h] [rbp+190h] BYREF
  unsigned __int16 v655; // [rsp+2644h] [rbp+194h]
  __int16 v656; // [rsp+2646h] [rbp+196h]
  __int64 v657; // [rsp+2648h] [rbp+198h]
  char v658[8]; // [rsp+2650h] [rbp+1A0h] BYREF
  char v659[8]; // [rsp+2658h] [rbp+1A8h] BYREF
  __int128 v660; // [rsp+2660h] [rbp+1B0h] BYREF
  _BYTE v661[24]; // [rsp+2670h] [rbp+1C0h] BYREF
  __int16 *v662; // [rsp+2688h] [rbp+1D8h] BYREF
  _DWORD *v663; // [rsp+2690h] [rbp+1E0h]
  char *v664; // [rsp+2698h] [rbp+1E8h]
  int v665; // [rsp+26A0h] [rbp+1F0h]
  __int128 *v666; // [rsp+26A8h] [rbp+1F8h]
  __int64 v667; // [rsp+26B0h] [rbp+200h] BYREF
  __int64 v668; // [rsp+26B8h] [rbp+208h] BYREF
  char v669[8]; // [rsp+26C0h] [rbp+210h] BYREF
  struct RowId *v670; // [rsp+26C8h] [rbp+218h]
  unsigned __int64 *v671; // [rsp+26D0h] [rbp+220h]
  char v672[16]; // [rsp+26E8h] [rbp+238h] BYREF
  _BYTE v673[16]; // [rsp+26F8h] [rbp+248h] BYREF
  int v674; // [rsp+2708h] [rbp+258h]
  char v675; // [rsp+2718h] [rbp+268h]
  __int64 v676; // [rsp+2720h] [rbp+270h]
  _BYTE v677[16]; // [rsp+2728h] [rbp+278h] BYREF
  _BYTE v678[16]; // [rsp+2738h] [rbp+288h] BYREF
  _BYTE v679[40]; // [rsp+2748h] [rbp+298h] BYREF
  _BYTE v680[36]; // [rsp+2770h] [rbp+2C0h] BYREF
  __int64 v681; // [rsp+2794h] [rbp+2E4h]
  int v682; // [rsp+27A4h] [rbp+2F4h]
  unsigned __int8 v683; // [rsp+27D0h] [rbp+320h] BYREF
  char v684; // [rsp+27D1h] [rbp+321h]
  __int128 v685; // [rsp+27D8h] [rbp+328h]
  _BYTE v686[256]; // [rsp+28D0h] [rbp+420h] BYREF
  _BYTE v687[256]; // [rsp+29D0h] [rbp+520h] BYREF
  _BYTE v688[256]; // [rsp+2AD0h] [rbp+620h] BYREF
  _BYTE v689[256]; // [rsp+2BD0h] [rbp+720h] BYREF
  int v690; // [rsp+2CD0h] [rbp+820h] BYREF
  __int64 v691; // [rsp+2CD4h] [rbp+824h]
  __int16 v692; // [rsp+2CDCh] [rbp+82Ch]
  char v693; // [rsp+2CDEh] [rbp+82Eh]
  int v694; // [rsp+2CE0h] [rbp+830h] BYREF
  __int64 v695; // [rsp+2CE4h] [rbp+834h]
  __int16 v696; // [rsp+2CECh] [rbp+83Ch]
  char v697; // [rsp+2CEEh] [rbp+83Eh]
  __int64 v698; // [rsp+2CF0h] [rbp+840h] BYREF
  int v699; // [rsp+2CF8h] [rbp+848h]
  __int16 v700; // [rsp+2CFCh] [rbp+84Ch]
  __int16 v701; // [rsp+2CFEh] [rbp+84Eh]
  __int64 v702; // [rsp+2D00h] [rbp+850h]
  __int16 v703; // [rsp+2D08h] [rbp+858h]
  __int16 v704; // [rsp+2D0Ah] [rbp+85Ah]
  int v705; // [rsp+2D0Ch] [rbp+85Ch]
  int v706; // [rsp+2D10h] [rbp+860h] BYREF
  __int64 v707; // [rsp+2D14h] [rbp+864h]
  __int64 v708; // [rsp+2D1Ch] [rbp+86Ch]
  int v709; // [rsp+2D24h] [rbp+874h]
  __int64 v710; // [rsp+2D28h] [rbp+878h]
  int v711; // [rsp+2D30h] [rbp+880h] BYREF
  __int64 v712; // [rsp+2D34h] [rbp+884h]
  __int16 v713; // [rsp+2D3Ch] [rbp+88Ch]
  char v714; // [rsp+2D3Eh] [rbp+88Eh]
  __int16 v715; // [rsp+2D40h] [rbp+890h]
  unsigned __int16 v716; // [rsp+2D42h] [rbp+892h] BYREF
  int v717; // [rsp+2D44h] [rbp+894h]
  char *v718; // [rsp+2D48h] [rbp+898h]
  struct PageComprInfo *v719; // [rsp+2D50h] [rbp+8A0h]
  __int16 v720; // [rsp+2D58h] [rbp+8A8h]
  __int16 v721; // [rsp+2D5Ah] [rbp+8AAh]
  __int16 v722; // [rsp+2D5Ch] [rbp+8ACh]
  Page **v723; // [rsp+2D5Eh] [rbp+8AEh]
  _TBYTE v724; // [rsp+2D66h] [rbp+8B6h]
  int v725; // [rsp+2D70h] [rbp+8C0h]
  int v726; // [rsp+2D74h] [rbp+8C4h]
  __int128 v727; // [rsp+2D78h] [rbp+8C8h] BYREF
  __int128 v728; // [rsp+2D88h] [rbp+8D8h]
  __int128 v729; // [rsp+2D98h] [rbp+8E8h]
  __int128 v730; // [rsp+2DA8h] [rbp+8F8h]
  __int128 v731; // [rsp+2DB8h] [rbp+908h]
  __int128 v732; // [rsp+2DC8h] [rbp+918h]
  __int128 v733; // [rsp+2DD8h] [rbp+928h]
  __int64 v734; // [rsp+2DE8h] [rbp+938h]
  __int16 v735; // [rsp+2DF0h] [rbp+940h]
  unsigned __int16 v736; // [rsp+2DF2h] [rbp+942h] BYREF
  int v737; // [rsp+2DF4h] [rbp+944h]
  char *v738; // [rsp+2DF8h] [rbp+948h]
  struct PageComprInfo *v739; // [rsp+2E00h] [rbp+950h]
  __int16 v740; // [rsp+2E08h] [rbp+958h]
  __int16 v741; // [rsp+2E0Ah] [rbp+95Ah]
  __int16 v742; // [rsp+2E0Ch] [rbp+95Ch]
  __int64 v743; // [rsp+2E0Eh] [rbp+95Eh]
  _TBYTE v744; // [rsp+2E16h] [rbp+966h]
  int v745; // [rsp+2E20h] [rbp+970h]
  int v746; // [rsp+2E24h] [rbp+974h]
  __int128 v747; // [rsp+2E28h] [rbp+978h] BYREF
  __int128 v748; // [rsp+2E38h] [rbp+988h]
  __int128 v749; // [rsp+2E48h] [rbp+998h]
  __int128 v750; // [rsp+2E58h] [rbp+9A8h]
  __int128 v751; // [rsp+2E68h] [rbp+9B8h]
  __int128 v752; // [rsp+2E78h] [rbp+9C8h]
  __int128 v753; // [rsp+2E88h] [rbp+9D8h]
  __int64 v754; // [rsp+2E98h] [rbp+9E8h]
  _BYTE v755[16]; // [rsp+2EA0h] [rbp+9F0h] BYREF
  _BYTE v756[16]; // [rsp+2EB0h] [rbp+A00h] BYREF
  _BYTE v757[16]; // [rsp+2EC0h] [rbp+A10h] BYREF
  _BYTE v758[16]; // [rsp+2ED0h] [rbp+A20h] BYREF
  char v759[16]; // [rsp+2EE0h] [rbp+A30h] BYREF
  char v760[16]; // [rsp+2EF0h] [rbp+A40h] BYREF
  char v761[16]; // [rsp+2F00h] [rbp+A50h] BYREF
  char v762[16]; // [rsp+2F10h] [rbp+A60h] BYREF
  unsigned __int8 Destination[8096]; // [rsp+2F20h] [rbp+A70h] BYREF

  v676 = -2;
  v670 = a4;
  v622 = a3;
  v635 = (HeapDataSetSession *)this;
  v621 = this;
  v671 = a5;
  v590 = -1;
  v593 = 0;
  v592 = 0;
  v597 = 0;
  *(_QWORD *)((char *)&v598 + 2) = 0;
  v594 = 0;
  v704 = 0;
  v660 = INVALID_HPAGE;
  v600 = -1;
  v7 = 0;
  v587 = 1;
  v657 = *(_QWORD *)(*((_QWORD *)this[92] + 1) + 48LL);
  *a5 = 0;
  v8 = (char *)(this + 348);
  v9 = (char *)this[349];
  if ( v9 == v8 )
    goto LABEL_6;
  v10 = 0;
  if ( v9 )
    v10 = (HeapRowObject *)(v9 - 16);
  v608 = v10;
  if ( !v10 )
  {
LABEL_6:
    v604 = 1887;
    v13 = (HeapRowObject *)operator new(0x638u, this[62], "Sql\\Ntdbms\\storeng\\dfs\\access\\HeapDataSet.h", 1887, 5u);
    v616 = v13;
    if ( v13 )
      v10 = HeapRowObject::HeapRowObject(v13);
    else
      v10 = 0;
    v608 = v10;
    HeapRowObject::Init(v10, this[91]);
  }
  else
  {
    v11 = (_QWORD *)*((_QWORD *)v10 + 3);
    v12 = *((_QWORD *)v10 + 2);
    *(_QWORD *)(v12 + 8) = v11;
    *v11 = v12;
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 2) = 0;
  }
  *((_QWORD *)v10 + 3) = this[351];
  *(_QWORD *)this[351] = (char *)v10 + 16;
  this[351] = (HeapRowObject *)((char *)v10 + 16);
  *((_QWORD *)v10 + 2) = this + 350;
  v14 = (*(_DWORD *)this[33] >> 27) & 1;
  v15 = this[92];
  v604 = 16;
  if ( *((_DWORD *)v10 + 396) == 1 )
  {
    *((_QWORD *)v10 + 5) = v15;
    *((_QWORD *)v10 + 7) = v15;
    *((_QWORD *)v10 + 32) = *(_QWORD *)(*((_QWORD *)v10 + 6) + 72LL) + 40LL;
    *((_DWORD *)v10 + 60) = 2;
    if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 4) + 72LL) + 24LL) != 1 )
    {
      HoBtVersioningStatus::Init((HeapRowObject *)((char *)v10 + 1336), *(struct HoBtAccess **)v15, v14);
      v16 = *((_QWORD *)v10 + 4);
      v17 = 0;
      if ( *(_DWORD *)(v16 + 64) == 3 )
        v17 = 8;
      v18 = *((_BYTE *)v10 + 1328) & 0xF7 | v17;
      *((_BYTE *)v10 + 1328) = v18;
      v19 = 0;
      if ( *(_DWORD *)(v16 + 64) == 4 )
        v19 = 16;
      v20 = v18 & 0xEF | v19;
      *((_BYTE *)v10 + 1328) = v20;
      *((_BYTE *)v10 + 1328) = v20
                             ^ (v20
                              ^ (32 * ((int)(*(_DWORD *)(*(_QWORD *)(v16 + 16) + 80LL) << 31) >> 31)))
                             & 0x20;
      *((_DWORD *)v10 + 338) = *(_DWORD *)(*(_QWORD *)(v16 + 72) + 392LL);
      *((_DWORD *)v10 + 339) = *((_DWORD *)v15 + 8);
    }
    *((_DWORD *)v10 + 396) = 2;
  }
  v605 = v10;
  v699 = *(_DWORD *)a2;
  v700 = *((_WORD *)a2 + 2);
  v701 = 0;
  v698 = 0;
  v705 = 0;
  v702 = 0;
  v703 = 0;
  if ( !(unsigned int)HeapPageManager::GetPageWithIdInternal(**((_QWORD **)v635 + 91), &v698, 3, 2, &v660) )
    goto LABEL_40;
  *((_DWORD *)v10 + 397) &= ~1u;
  v21 = (Page ***)((char *)v10 + 48);
  v693 = 1;
  v22 = (HeapPageManager *)**((_QWORD **)v10 + 6);
  v23 = *(_QWORD **)(*((_QWORD *)v10 + 7) + 8LL);
  *((_OWORD *)v10 + 4) = v660;
  HeapPageManager::GetPageRef(v22, (HeapRowObject *)((char *)v10 + 64), (HeapRowObject *)((char *)v10 + 88));
  *((_QWORD *)v10 + 81) = **((_QWORD **)v10 + 11);
  *((_DWORD *)v10 + 34) = 3;
  *((_DWORD *)v10 + 167) = 0;
  v25 = *(_QWORD *)(*((_QWORD *)v10 + 6) + 24LL);
  v26 = *(_DWORD *)(*((_QWORD *)v10 + 32) + 16LL);
  if ( (v26 & 1) != 0 && (v26 & 0x40) == 0 )
  {
    v27 = v23[6];
    if ( *(_BYTE *)(v27 + 7378) )
    {
      if ( !*(_BYTE *)(v27 + 8272) )
      {
        v28 = *((_QWORD *)v10 + 8);
        v29 = *(_DWORD *)(v28 + 144);
        v30 = *(unsigned __int16 *)(v28 + 148);
        LOWORD(v28) = *(_WORD *)(v27 + 1720);
        v693 = 6;
        v692 = v28;
        v690 = v29;
        v691 = (unsigned __int16)v30;
        LOBYTE(v24) = 1;
        LOBYTE(v30) = 6;
        if ( !(unsigned __int8)VersionMgr::GetInstantLockInRecoveryNoWait(
                                 *(_QWORD *)(*((_QWORD *)v10 + 7) + 8LL),
                                 v30,
                                 &v690,
                                 v24) )
        {
          HeapFragment::ReleasePageAccess((HeapRowObject *)((char *)v10 + 48));
          v31 = (*v21)[3];
          v32 = *((_QWORD *)v10 + 7);
          LOBYTE(v579) = 1;
          LOBYTE(v33) = 6;
          VersionMgr::GetInstantLockInRecoveryWithWait(
            *(_QWORD *)(v32 + 8),
            v33,
            *((unsigned int *)v31 + 6),
            &v690,
            v579);
        }
      }
    }
  }
  if ( *(_BYTE *)(v25 + 2) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *))(*v23 + 40LL))(v23) )
    {
      v34 = *((_QWORD *)v10 + 8);
      v35 = *(_DWORD *)(v34 + 144);
      v36 = *(_WORD *)(v34 + 148);
      v37 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 7) + 8LL) + 48LL) + 1720LL);
      v693 = 6;
      v692 = v37;
      v690 = v35;
      v691 = v36;
      if ( (int)HeapFragment::LockResource((char *)v10 + 48, &v690, 2, v25, (char *)v10 + 192, 1, 1, 1) < 0 )
      {
        if ( *((_QWORD *)v10 + 8) != INVALID_HPAGE || *((_QWORD *)v10 + 9) != *(&INVALID_HPAGE + 1) )
        {
          _mm_lfence();
          if ( (*((_BYTE *)v10 + 160) & 2) != 0 )
          {
            _mm_lfence();
            if ( (unsigned int)LockReference::Release((HeapRowObject *)((char *)v10 + 168)) )
            {
              _mm_lfence();
              (*v21)[6] = (Page *)((char *)(*v21)[6] - 1);
            }
          }
          *((_BYTE *)v10 + 160) = 0;
          *((_DWORD *)v10 + 39) = 0;
          *((_DWORD *)v10 + 46) = 0;
          if ( (*((_BYTE *)v10 + 208) & 2) != 0 )
          {
            _mm_lfence();
            if ( (unsigned int)LockReference::Release((HeapRowObject *)((char *)v10 + 216)) )
            {
              _mm_lfence();
              (*v21)[6] = (Page *)((char *)(*v21)[6] - 1);
            }
          }
          *((_BYTE *)v10 + 208) = 0;
          *((_DWORD *)v10 + 51) = 0;
          *((_DWORD *)v10 + 58) = 0;
          if ( *((_QWORD *)v10 + 11) )
          {
            _mm_lfence();
            v38 = *((_QWORD *)v10 + 8);
            *((_BYTE *)v10 + 102) = 0;
            *((_QWORD *)v10 + 11) = 0;
            *((_WORD *)v10 + 50) = 0;
            *(_DWORD *)(v38 + 72) = 0;
          }
          HeapPageManager::ReleaseHPage(**v21, (HeapRowObject *)((char *)v10 + 64));
          *((_OWORD *)v10 + 4) = INVALID_HPAGE;
          *((_DWORD *)v10 + 20) = -1;
          *((_DWORD *)v10 + 156) = 0;
          *((_QWORD *)v10 + 81) = 0;
          *((_QWORD *)v10 + 80) = 0;
          *((_QWORD *)v10 + 82) = 0;
          *((_DWORD *)v10 + 168) = -1;
          *((_WORD *)v10 + 338) = -1;
          *(_QWORD *)((char *)v10 + 678) = 0;
          *((_DWORD *)v10 + 60) = 2;
        }
        *((_DWORD *)v10 + 397) |= 1u;
        goto LABEL_40;
      }
    }
  }
  *((_DWORD *)v10 + 60) = 3;
  if ( !*((_QWORD *)v10 + 11) )
  {
    HeapFragment::ReAcquirePageAccessLong((char *)v10 + 48, 1);
    if ( *((_DWORD *)v10 + 60) != 3 )
    {
      *((_DWORD *)v10 + 397) |= 1u;
      goto LABEL_40;
    }
  }
  v39 = *((_DWORD *)v10 + 397) | 1;
  *((_DWORD *)v10 + 397) = v39;
  v40 = v604;
  do
  {
    v41 = (Page *)*((_QWORD *)v10 + 81);
    if ( !v41 )
    {
      *((_DWORD *)v10 + 397) = v39 & 0xFFFFFFFE;
      if ( *((_DWORD *)v10 + 220) == 4 )
        HeapFragment::ReleasePageAccess((HeapRowObject *)((char *)v10 + 688));
      v42 = v21[5];
      if ( v42 )
      {
        v41 = *v42;
      }
      else if ( *((_DWORD *)v21 + 48) == 2
             || (HeapFragment::ReAcquirePageAccessLong(v21, 1), *((_DWORD *)v21 + 48) == 2) )
      {
        v41 = 0;
      }
      else
      {
        v41 = *v21[5];
      }
      if ( !*(_BYTE *)(*((_QWORD *)v10 + 5) + 181LL) )
        *((_DWORD *)v10 + 397) |= 1u;
    }
    ValidSlotId = Page::NextValidSlotId(v41, v600);
    v600 = ValidSlotId;
    *((_DWORD *)v10 + 397) &= ~1u;
    if ( ValidSlotId == -1 )
    {
      if ( *((_DWORD *)v10 + 220) == 4 )
        HeapFragment::ReleasePageAccess((HeapRowObject *)((char *)v10 + 688));
      HeapFragment::TryPageDeallocation(v21, 0, 0);
      *((_DWORD *)v10 + 397) |= 1u;
      return;
    }
    v45 = 0;
    v606 = 0;
    v46 = v587;
    while ( 1 )
    {
      v587 = v46;
      v585 = v7;
      if ( *((_DWORD *)v10 + 220) == 4
        && (*((_QWORD *)v10 + 88) != INVALID_HPAGE || *((_QWORD *)v10 + 89) != *(&INVALID_HPAGE + 1)) )
      {
        if ( (*((_BYTE *)v10 + 800) & 2) != 0
          && (unsigned int)LockReference::Release((HeapRowObject *)((char *)v10 + 808)) )
        {
          --*(_QWORD *)(*((_QWORD *)v10 + 86) + 48LL);
        }
        *((_BYTE *)v10 + 800) = 0;
        *((_DWORD *)v10 + 199) = 0;
        *((_DWORD *)v10 + 206) = 0;
        if ( (*((_BYTE *)v10 + 848) & 2) != 0
          && (unsigned int)LockReference::Release((HeapRowObject *)((char *)v10 + 856)) )
        {
          --*(_QWORD *)(*((_QWORD *)v10 + 86) + 48LL);
        }
        *((_BYTE *)v10 + 848) = 0;
        *((_DWORD *)v10 + 211) = 0;
        *((_DWORD *)v10 + 218) = 0;
        if ( *((_QWORD *)v10 + 91) )
        {
          v47 = *((_QWORD *)v10 + 88);
          *((_BYTE *)v10 + 742) = 0;
          *((_QWORD *)v10 + 91) = 0;
          *((_WORD *)v10 + 370) = 0;
          *(_DWORD *)(v47 + 72) = 0;
        }
        HeapPageManager::ReleaseHPage(**((HeapPageManager ***)v10 + 86), (HeapRowObject *)((char *)v10 + 704));
        *((_OWORD *)v10 + 44) = INVALID_HPAGE;
        *((_DWORD *)v10 + 180) = -1;
        *((_DWORD *)v10 + 316) = 0;
        *((_QWORD *)v10 + 161) = 0;
        *((_QWORD *)v10 + 160) = 0;
        *((_QWORD *)v10 + 162) = 0;
        *((_DWORD *)v10 + 328) = -1;
        *((_WORD *)v10 + 658) = -1;
        *(_QWORD *)((char *)v10 + 1318) = 0;
        *((_DWORD *)v10 + 220) = 2;
      }
      if ( v45 <= 0 )
      {
        if ( !v45 )
          goto LABEL_96;
      }
      else
      {
        if ( !v21[5] )
          HeapFragment::ReAcquirePageAccessLong(v21, 0);
        if ( !*((_DWORD *)v21 + 144) )
          HeapFragment::SetupCachedRowInfo(v21, 1);
        v7 = *((_DWORD *)v21 + 142);
        v585 = v7;
        v46 = *((_DWORD *)v21 + 143);
        v587 = v46;
      }
      if ( *(_BYTE *)(*((_QWORD *)v10 + 5) + 41LL) )
      {
LABEL_96:
        v55 = v21[1][1];
        v616 = v55;
        v715 = -1;
        v718 = 0;
        v717 = 0;
        v723 = 0;
        *(_QWORD *)((char *)&v724 + 2) = 0;
        v719 = 0;
        v726 = -1;
        v612 = 0;
        v613 = 0;
        v56 = (*v21)[3];
        v623 = v56;
        LOBYTE(v586) = 0;
        v57 = (char *)(v21 + 12);
        if ( ((_BYTE)v21[14] & 2) != 0 && (unsigned int)LockReference::Release((LockReference *)(v21 + 15)) )
          (*v21)[6] = (Page *)((char *)(*v21)[6] - 1);
        *((_BYTE *)v21 + 112) = 0;
        *((_DWORD *)v21 + 27) = 0;
        *((_DWORD *)v21 + 34) = 0;
        *((_DWORD *)v21 + 8) = v600;
        v58 = *((_DWORD *)v21[26] + 4);
        if ( (v58 & 1) != 0 && (v58 & 0x40) == 0 )
        {
          v59 = *((_QWORD *)v55 + 6);
          if ( *(_BYTE *)(v59 + 7378) )
          {
            if ( !*(_BYTE *)(v59 + 8272) )
            {
              v755[14] = 1;
              v60 = (__int64)*v21[5];
              v61 = *((_DWORD *)v21 + 8);
              v642 = *(_DWORD *)(v60 + 32);
              v643 = *(_WORD *)(v60 + 36);
              v644 = v61;
              LockRes::SetRidResource(
                (LockRes *)v755,
                *(_WORD *)(*((_QWORD *)v55 + 6) + 1720LL),
                (const struct RowId *)&v642);
              LOBYTE(v62) = 1;
              LOBYTE(v63) = 3;
              if ( !(unsigned __int8)VersionMgr::GetInstantLockInRecoveryNoWait(v55, v63, v755, v62) )
              {
                HeapFragment::ReleasePageAccess((HeapFragment *)v21);
                v64 = (*v21)[3];
                LOBYTE(v579) = 1;
                LOBYTE(v65) = 3;
                VersionMgr::GetInstantLockInRecoveryWithWait(v55, v65, *((unsigned int *)v64 + 6), v755, v579);
                if ( !v21[5] )
                  HeapFragment::ReAcquirePageAccessLong(v21, 0);
              }
            }
          }
        }
        v610 = NullXdesId;
        v589 = word_10318AB38;
        while ( 1 )
        {
          v66 = v46;
          v601 = v7;
          if ( *((_BYTE *)v21[1] + 41) && (*((_DWORD *)v56 + 1) & 0x140) == 0 )
          {
            v67 = v21[75];
            if ( *((_WORD *)v21 + 16) < *((_WORD *)v67 + 11) )
            {
              v68 = (struct IMemObj **)*((int *)v21 + 8);
              v621 = v68;
              if ( *((_WORD *)v67 + 4095LL - (_QWORD)v68) )
              {
                v726 = (int)v68;
                if ( *((char *)v67 + 2) < 0 )
                {
                  v70 = (unsigned __int8 *)(v67 + 12);
                  _mm_prefetch((const char *)v67 + 96, 0);
                  if ( !v715 || (v69 = v719) == 0 )
                  {
                    v727 = 0;
                    v728 = 0;
                    v729 = 0;
                    v730 = 0;
                    v731 = 0;
                    v732 = 0;
                    v733 = 0;
                    v734 = 0;
                    v69 = PageComprMgr::PageComprMgr((PageComprMgr *)&v727);
                  }
                  Lsn = Page::GetLsn(v67, v759, 0, 0);
                  v72 = Lsn;
                  if ( v70 == *(unsigned __int8 **)v69 )
                    LSN::operator==(Lsn, (char *)v69 + 96);
                  *(_QWORD *)v69 = v70;
                  v73 = *(_WORD *)(v72 + 8);
                  v74 = *(_DWORD *)(v72 + 4);
                  *((_DWORD *)v69 + 24) = *(_DWORD *)v72;
                  *((_DWORD *)v69 + 25) = v74;
                  *((_WORD *)v69 + 52) = v73;
                  *((_DWORD *)v69 + 27) = *((_DWORD *)v67 + 8);
                  *((_WORD *)v69 + 56) = *((_WORD *)v67 + 18);
                  *((_WORD *)v69 + 57) = 0;
                  v75 = 3LL * *v70;
                  LODWORD(v619) = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v70);
                  v76 = word_102883984[v75];
                  LOWORD(v603) = v76;
                  *((_WORD *)v69 + 8) = -1;
                  *((_QWORD *)v69 + 3) = 0;
                  *((_DWORD *)v69 + 5) = 0;
                  *(_QWORD *)((char *)v69 + 46) = 0;
                  *((_QWORD *)v69 + 7) = 0;
                  *((_QWORD *)v69 + 4) = 0;
                  v77 = (struct PageComprInfo *)((char *)v69 + 72);
                  *((_QWORD *)v69 + 9) = 0;
                  *((_QWORD *)v69 + 10) = 0;
                  *((_WORD *)v69 + 44) = 0;
                  if ( (**(_BYTE **)v69 & 2) != 0 )
                  {
                    v78 = &v70[v76];
                    if ( (v70[v76] & 1) != 0 )
                    {
                      *((_WORD *)v69 + 8) = 1;
                      v587 = v66;
                      v79 = v601;
                      v585 = v601;
                      *((_QWORD *)v69 + 3) = v78;
                      v80 = *v78;
                      switch ( *v78 & 0x1C )
                      {
                        case 0:
                        case 0xC:
                        case 0x10:
                        case 0x14:
                        case 0x18:
                        case 0x1C:
                          if ( (v78[1] & 0x80u) != 0 )
                          {
                            v83 = *(_WORD *)(v78 + 1);
                            *((_WORD *)v69 + 9) = v83;
                            v81 = 3;
                            v82 = HIBYTE(v83) | ((v83 & 0x7F) << 8);
                          }
                          else
                          {
                            v81 = 2;
                            v82 = v78[1];
                          }
                          *((_WORD *)v69 + 9) = v82;
                          *((_WORD *)v69 + 20) = v81;
                          *((_WORD *)v69 + 22) = v81 + (((unsigned int)*((unsigned __int16 *)v69 + 9) + 1) >> 1);
                          v84 = *((unsigned __int16 *)v69 + 9);
                          if ( v84 > 0x1E )
                            v85 = (int)(v84 - 1) / 30;
                          else
                            LOWORD(v85) = 0;
                          *((_WORD *)v69 + 21) = v85;
                          *((_DWORD *)v69 + 5) = 0;
                          *((_DWORD *)v69 + 16) = 0;
                          v585 = v79;
                          v587 = v66;
                          *((_QWORD *)v69 + 7) = 0;
                          *((_QWORD *)v69 + 4) = 0;
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
                          goto LABEL_134;
                        case 4:
                          if ( (v80 & 0x1C) == 4 && (v80 & 2) != 0 )
                          {
                            CDRecord::Reset((struct PageComprInfo *)((char *)v69 + 18));
                            *((_QWORD *)v69 + 3) = v78;
                            *((_DWORD *)v69 + 5) = 15;
                            *((_DWORD *)v69 + 16) = 0;
                            *((_DWORD *)v69 + 16) = 1;
                            v77 = (struct PageComprInfo *)((char *)v69 + 72);
                            *((_QWORD *)v69 + 7) = 0;
                            *((_QWORD *)v69 + 4) = 0;
                          }
                          else
                          {
                            CDRecord::Reset((struct PageComprInfo *)((char *)v69 + 18));
                            *((_QWORD *)v69 + 3) = v78;
                            *((_DWORD *)v69 + 5) = 1;
                            v585 = v601;
                            v587 = v66;
                            *((_DWORD *)v69 + 16) = 0;
                            v77 = (struct PageComprInfo *)((char *)v69 + 72);
                            *((_QWORD *)v69 + 7) = 0;
                            *((_QWORD *)v69 + 4) = 0;
                          }
                          break;
                        case 8:
                          CDRecord::Reset((struct PageComprInfo *)((char *)v69 + 18));
                          *((_QWORD *)v69 + 3) = v78;
                          *((_DWORD *)v69 + 5) = 9;
                          *((_DWORD *)v69 + 16) = 0;
LABEL_134:
                          v77 = (struct PageComprInfo *)((char *)v69 + 72);
                          v585 = v601;
                          v587 = v66;
                          *((_QWORD *)v69 + 7) = 0;
                          *((_QWORD *)v69 + 4) = 0;
                          break;
                      }
                    }
                    else
                    {
                      *((_WORD *)v69 + 8) = 0;
                      v86 = 0;
                      *((_QWORD *)v69 + 3) = v78;
                      *((_DWORD *)v69 + 5) = 0;
                      *(_DWORD *)((char *)v69 + 54) = 0;
                      switch ( *v78 & 0xE )
                      {
                        case 0:
                        case 2:
                        case 8:
                        case 0xC:
                          v86 = *((unsigned __int16 *)v78 + 1);
                          if ( (unsigned int)(v86 - 1) > 0x1F9D )
                          {
                            RaiseInconsistencyError(&v70[v76], 6);
                            goto LABEL_141;
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
LABEL_141:
                          v77 = (struct PageComprInfo *)((char *)v69 + 72);
                          break;
                        case 4:
                          v86 = 9;
                          break;
                        case 6:
                        case 0xA:
                          break;
                        case 0xE:
                          v86 = 1;
                          break;
                      }
                      *((_DWORD *)v69 + 8) = v86;
                      *(_QWORD *)((char *)v69 + 46) = 0;
                    }
                    LOWORD(v76) = v603;
                  }
                  if ( (**(_BYTE **)v69 & 4) != 0 )
                  {
                    if ( WORD1(v619) )
                      v87 = *(unsigned __int16 *)&v70[2 * SWORD1(v619) + 1];
                    else
                      v87 = (__int16)v76;
                    PageDictionary::Init(v77, &v70[v87]);
                  }
                  v88 = (PageComprInfoCache *)*((_QWORD *)v69 + 1);
                  if ( v88 )
                    PageComprInfoCache::Init(v88, v69);
                  v7 = v585;
                }
                else
                {
                  v69 = 0;
                }
                v89 = *((unsigned __int16 *)v67 + 7);
                v90 = (char *)v67 + *((unsigned __int16 *)v67 + 4095LL - (_QWORD)v621);
                v319 = (*v90 & 1) == 0;
                v718 = v90;
                if ( v319 )
                {
                  v715 = 0;
                  v717 = 0;
                  LODWORD(v724) = 0;
                  switch ( *v90 & 0xE )
                  {
                    case 0:
                    case 2:
                    case 8:
                    case 0xC:
                      v89 = *((unsigned __int16 *)v90 + 1);
                      if ( (unsigned int)(v89 - 1) > 0x1F9D )
                        RaiseInconsistencyError(v90, 6);
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
                      v89 = 9;
                      break;
                    case 6:
                    case 0xA:
                      break;
                    case 0xE:
                      v89 = 1;
                      break;
                  }
                  LODWORD(v719) = v89;
                  v723 = v67 + 1024;
                }
                else
                {
                  v715 = 1;
                  v91 = *v90;
                  switch ( *v90 & 0x1C )
                  {
                    case 0:
                    case 0xC:
                    case 0x10:
                    case 0x14:
                    case 0x18:
                    case 0x1C:
                      if ( v90[1] < 0 )
                      {
                        v92 = HIBYTE(*(_WORD *)(v90 + 1)) | ((*(_WORD *)(v90 + 1) & 0x7F) << 8);
                        v716 = v92;
                        v93 = 3;
                        v720 = 3;
                      }
                      else
                      {
                        v92 = (unsigned __int8)v90[1];
                        v716 = v92;
                        v93 = 2;
                        v720 = 2;
                      }
                      v722 = v93 + (((unsigned int)v92 + 1) >> 1);
                      if ( v92 > 0x1Eu )
                        v721 = (v92 - 1) / 30;
                      else
                        v721 = 0;
                      v717 = 0;
                      v725 = 0;
                      goto LABEL_167;
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
                      goto LABEL_167;
                    case 4:
                      if ( (v91 & 0x1C) == 4 && (v91 & 2) != 0 )
                      {
                        CDRecord::Reset((CDRecord *)&v716);
                        v718 = v90;
                        v717 = 15;
                        v725 = 1;
LABEL_167:
                        *(_QWORD *)((char *)&v724 + 2) = v67 + 1024;
                        v719 = v69;
                      }
                      else
                      {
                        CDRecord::Reset((CDRecord *)&v716);
                        v718 = v90;
                        v717 = 1;
                        v725 = 0;
                        *(_QWORD *)((char *)&v724 + 2) = v67 + 1024;
                        v719 = v69;
                      }
                      break;
                    case 8:
                      CDRecord::Reset((CDRecord *)&v716);
                      v718 = v90;
                      v717 = 9;
                      v725 = 0;
                      *(_QWORD *)((char *)&v724 + 2) = v67 + 1024;
                      v719 = v69;
                      break;
                  }
                }
                if ( v715 )
                  CDRecord::GetXdesTs(&v716, &v632);
                else
                  FixedVarRecord::GetXdesTs(&v716, &v632);
                v612 = v632;
                v613 = v633;
                if ( v633 == v589 && v632 == v610 )
                {
                  v55 = v616;
                }
                else
                {
                  v640 = v632;
                  v641 = v633;
                  v55 = v616;
                  if ( (unsigned int)XDES::GetTIDLockOption(v616, &v640) == 3 )
                  {
                    v40 = 1;
                    v10 = v608;
                    goto LABEL_79;
                  }
                  v610 = v612;
                  v589 = v613;
                }
                v46 = v587;
              }
              v56 = v623;
            }
            v57 = (char *)(v21 + 12);
          }
          v603 = v46;
          v601 = v7;
          if ( (_BYTE)v586 )
            break;
          v757[14] = 1;
          v94 = (__int64)*v21[5];
          v95 = *((_DWORD *)v21 + 8);
          v645 = *(_DWORD *)(v94 + 32);
          v646 = *(_WORD *)(v94 + 36);
          v647 = v95;
          LockRes::SetRidResource(
            (LockRes *)v757,
            *(_WORD *)(*((_QWORD *)v55 + 6) + 1720LL),
            (const struct RowId *)&v645);
          v96 = HeapFragment::LockResource(v21, v757, 3, v56, v57, 1, 0, 1);
          if ( v96 < 0 )
          {
            *((_DWORD *)v21 + 48) = 3;
            *((_DWORD *)v21 + 8) = -1;
            v40 = 1;
            v10 = v608;
            goto LABEL_79;
          }
          if ( v96 != 1 )
            break;
          LOBYTE(v586) = 1;
        }
        *((_DWORD *)v21 + 48) = 4;
        v97 = *((_QWORD *)v55 + 6);
        if ( !*(_QWORD *)(v97 + 6952) )
          goto LABEL_266;
        v98 = *((_DWORD *)v21[26] + 4);
        if ( ((v98 & 1) == 0 || (v98 & 0x40) != 0 || !*(_BYTE *)(v97 + 7378) || *(_BYTE *)(v97 + 8272))
          && LckInfo::IsNoLock(v56) )
        {
          goto LABEL_266;
        }
        v99 = v21[75];
        if ( *((_WORD *)v21 + 16) >= *((_WORD *)v99 + 11) )
          goto LABEL_266;
        v100 = *((int *)v21 + 8);
        v101 = (struct IMemObj **)(4095 - v100);
        v621 = (struct IMemObj **)(4095 - v100);
        if ( !*((_WORD *)v99 + 4095 - v100) )
          goto LABEL_266;
        v726 = v100;
        if ( *((char *)v99 + 2) < 0 )
        {
          v103 = (unsigned __int8 *)(v99 + 12);
          _mm_prefetch((const char *)v99 + 96, 0);
          if ( !v715 || (v102 = v719) == 0 )
          {
            v727 = 0;
            v728 = 0;
            v729 = 0;
            v730 = 0;
            v731 = 0;
            v732 = 0;
            v733 = 0;
            v734 = 0;
            v102 = PageComprMgr::PageComprMgr((PageComprMgr *)&v727);
          }
          v104 = Page::GetLsn(v99, v760, 0, 0);
          v105 = v104;
          if ( v103 == *(unsigned __int8 **)v102 )
            LSN::operator==(v104, (char *)v102 + 96);
          *(_QWORD *)v102 = v103;
          v106 = *(_WORD *)(v105 + 8);
          v107 = *(_DWORD *)(v105 + 4);
          *((_DWORD *)v102 + 24) = *(_DWORD *)v105;
          *((_DWORD *)v102 + 25) = v107;
          *((_WORD *)v102 + 52) = v106;
          *((_DWORD *)v102 + 27) = *((_DWORD *)v99 + 8);
          *((_WORD *)v102 + 56) = *((_WORD *)v99 + 18);
          *((_WORD *)v102 + 57) = 0;
          v108 = 3LL * *v103;
          LODWORD(v620) = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v103);
          v109 = word_102883984[v108];
          v589 = v109;
          *((_WORD *)v102 + 8) = -1;
          *((_QWORD *)v102 + 3) = 0;
          *((_DWORD *)v102 + 5) = 0;
          *(_QWORD *)((char *)v102 + 46) = 0;
          *((_QWORD *)v102 + 7) = 0;
          *((_QWORD *)v102 + 4) = 0;
          v110 = (struct PageComprInfo *)((char *)v102 + 72);
          *((_QWORD *)v102 + 9) = 0;
          *((_QWORD *)v102 + 10) = 0;
          *((_WORD *)v102 + 44) = 0;
          if ( (**(_BYTE **)v102 & 2) != 0 )
          {
            v111 = &v103[v109];
            if ( (v103[v109] & 1) != 0 )
            {
              *((_WORD *)v102 + 8) = 1;
              v112 = v603;
              v587 = v603;
              v113 = v601;
              v585 = v601;
              *((_QWORD *)v102 + 3) = v111;
              v114 = *v111;
              switch ( (unsigned __int64)&____PchSym__00_UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq_4B2008FD98C1DD4 )
              {
                case 0uLL:
                  if ( (v111[1] & 0x80u) != 0 )
                  {
                    v117 = *(_WORD *)(v111 + 1);
                    *((_WORD *)v102 + 9) = v117;
                    v115 = 3;
                    v116 = HIBYTE(v117) | ((v117 & 0x7F) << 8);
                  }
                  else
                  {
                    v115 = 2;
                    v116 = v111[1];
                  }
                  *((_WORD *)v102 + 9) = v116;
                  *((_WORD *)v102 + 20) = v115;
                  *((_WORD *)v102 + 22) = v115 + (((unsigned int)*((unsigned __int16 *)v102 + 9) + 1) >> 1);
                  v118 = *((unsigned __int16 *)v102 + 9);
                  if ( v118 > 0x1E )
                    v119 = (int)(v118 - 1) / 30;
                  else
                    LOWORD(v119) = 0;
                  *((_WORD *)v102 + 21) = v119;
                  *((_DWORD *)v102 + 5) = 0;
                  *((_DWORD *)v102 + 16) = 0;
                  v587 = v112;
                  v585 = v113;
                  *((_QWORD *)v102 + 7) = 0;
                  *((_QWORD *)v102 + 4) = 0;
                  break;
                case 1uLL:
                  if ( (v114 & 0x1C) == 4 && (v114 & 2) != 0 )
                  {
                    CDRecord::Reset((struct PageComprInfo *)((char *)v102 + 18));
                    *((_QWORD *)v102 + 3) = v111;
                    *((_DWORD *)v102 + 5) = 15;
                    *((_DWORD *)v102 + 16) = 0;
                    *((_DWORD *)v102 + 16) = 1;
                    v110 = (struct PageComprInfo *)((char *)v102 + 72);
                    *((_QWORD *)v102 + 7) = 0;
                    *((_QWORD *)v102 + 4) = 0;
                  }
                  else
                  {
                    CDRecord::Reset((struct PageComprInfo *)((char *)v102 + 18));
                    *((_QWORD *)v102 + 3) = v111;
                    *((_DWORD *)v102 + 5) = 1;
                    v585 = v601;
                    v587 = v603;
                    *((_DWORD *)v102 + 16) = 0;
                    v110 = (struct PageComprInfo *)((char *)v102 + 72);
                    *((_QWORD *)v102 + 7) = 0;
                    *((_QWORD *)v102 + 4) = 0;
                  }
                  break;
                case 2uLL:
                  CDRecord::Reset((struct PageComprInfo *)((char *)v102 + 18));
                  *((_QWORD *)v102 + 3) = v111;
                  *((_DWORD *)v102 + 5) = 9;
                  *((_DWORD *)v102 + 16) = 0;
                  goto LABEL_221;
                case 3uLL:
                  utassert_fail(
                    1u,
                    "FALSE",
                    "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                    207,
                    "Invalid switch value");
LABEL_221:
                  v110 = (struct PageComprInfo *)((char *)v102 + 72);
                  v587 = v603;
                  v585 = v601;
                  *((_QWORD *)v102 + 7) = 0;
                  *((_QWORD *)v102 + 4) = 0;
                  break;
              }
            }
            else
            {
              *((_WORD *)v102 + 8) = 0;
              v120 = 0;
              *((_QWORD *)v102 + 3) = v111;
              *((_DWORD *)v102 + 5) = 0;
              *(_DWORD *)((char *)v102 + 54) = 0;
              switch ( *v111 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v120 = *((unsigned __int16 *)v111 + 1);
                  if ( (unsigned int)(v120 - 1) > 0x1F9D )
                  {
                    RaiseInconsistencyError(&v103[v109], 6);
                    goto LABEL_228;
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
LABEL_228:
                  v110 = (struct PageComprInfo *)((char *)v102 + 72);
                  break;
                case 4:
                  v120 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v120 = 1;
                  break;
              }
              *((_DWORD *)v102 + 8) = v120;
              *(_QWORD *)((char *)v102 + 46) = 0;
              v101 = v621;
            }
            LOWORD(v109) = v589;
          }
          if ( (**(_BYTE **)v102 & 4) != 0 )
          {
            if ( WORD1(v620) )
              v121 = *(unsigned __int16 *)&v103[2 * SWORD1(v620) + 1];
            else
              v121 = (__int16)v109;
            PageDictionary::Init(v110, &v103[v121]);
          }
          v122 = (PageComprInfoCache *)*((_QWORD *)v102 + 1);
          if ( v122 )
            PageComprInfoCache::Init(v122, v102);
          v7 = v585;
        }
        else
        {
          v102 = 0;
        }
        v123 = *((unsigned __int16 *)v99 + 7);
        v124 = (char *)v99 + *((unsigned __int16 *)v99 + (_QWORD)v101);
        v319 = (*v124 & 1) == 0;
        v718 = v124;
        if ( v319 )
        {
          v715 = 0;
          v717 = 0;
          LODWORD(v724) = 0;
          switch ( *v124 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v123 = *((unsigned __int16 *)v124 + 1);
              if ( (unsigned int)(v123 - 1) > 0x1F9D )
                RaiseInconsistencyError(v124, 6);
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
              v123 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v123 = 1;
              break;
          }
          LODWORD(v719) = v123;
          v723 = v99 + 1024;
        }
        else
        {
          v715 = 1;
          v125 = *v124;
          switch ( *v124 & 0x1C )
          {
            case 0:
            case 0xC:
            case 0x10:
            case 0x14:
            case 0x18:
            case 0x1C:
              if ( v124[1] < 0 )
              {
                v126 = HIBYTE(*(_WORD *)(v124 + 1)) | ((*(_WORD *)(v124 + 1) & 0x7F) << 8);
                v716 = v126;
                v127 = 3;
                v720 = 3;
              }
              else
              {
                v126 = (unsigned __int8)v124[1];
                v716 = v126;
                v127 = 2;
                v720 = 2;
              }
              v722 = v127 + (((unsigned int)v126 + 1) >> 1);
              if ( v126 > 0x1Eu )
                v721 = (v126 - 1) / 30;
              else
                v721 = 0;
              v717 = 0;
              v725 = 0;
              *(_QWORD *)((char *)&v724 + 2) = v99 + 1024;
              v719 = v102;
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
              *(_QWORD *)((char *)&v724 + 2) = v99 + 1024;
              v719 = v102;
              break;
            case 4:
              if ( (v125 & 0x1C) == 4 && (v125 & 2) != 0 )
              {
                CDRecord::Reset((CDRecord *)&v716);
                v718 = v124;
                v717 = 15;
                v725 = 1;
                *(_QWORD *)((char *)&v724 + 2) = v99 + 1024;
                v719 = v102;
              }
              else
              {
                CDRecord::Reset((CDRecord *)&v716);
                v718 = v124;
                v717 = 1;
                v725 = 0;
                *(_QWORD *)((char *)&v724 + 2) = v99 + 1024;
                v719 = v102;
              }
              break;
            case 8:
              CDRecord::Reset((CDRecord *)&v716);
              v718 = v124;
              v717 = 9;
              v725 = 0;
              *(_QWORD *)((char *)&v724 + 2) = v99 + 1024;
              v719 = v102;
              break;
          }
        }
        if ( v715 )
          CDRecord::GetXdesTs(&v716, &v630);
        else
          FixedVarRecord::GetXdesTs(&v716, &v630);
        v612 = v630;
        v613 = v631;
        v638 = v630;
        v639 = v631;
        v128 = v616;
        if ( !(unsigned __int8)RecoveryUnit::ShouldOnlineTranTakeTIDLockOnDeferredTran(*((_QWORD *)v616 + 6), &v638)
          || (LOBYTE(v129) = 3, (unsigned __int8)VersionMgr::GetInstantXdesIdLockInRecoveryNoWait(v128, v129, &v612)) )
        {
LABEL_266:
          HeapFragment::SetupCachedRowInfo(v21, 1);
          v7 = *((_DWORD *)v21 + 142);
          v585 = v7;
          v46 = *((_DWORD *)v21 + 143);
          v587 = v46;
          v40 = 0;
          v10 = v608;
          v45 = v606;
          goto LABEL_267;
        }
        *((_DWORD *)v21 + 48) = 3;
        *((_DWORD *)v21 + 8) = -1;
        v40 = 1;
        v10 = v608;
LABEL_79:
        v48 = v587;
        goto LABEL_80;
      }
      if ( v40 )
        goto LABEL_79;
LABEL_267:
      if ( v7 != 3 )
        goto LABEL_79;
      v130 = 0;
      if ( *(_BYTE *)(*((_QWORD *)v10 + 5) + 41LL) )
      {
        v130 = v45 < 50;
        goto LABEL_270;
      }
      v132 = *(_QWORD *)(*((_QWORD *)v10 + 4) + 24LL);
      if ( *(_DWORD *)(v132 + 28) )
      {
        v133 = *(_BYTE *)(v132 + 1);
        if ( v133 != 1 && v133 != 8 )
          break;
        if ( *(_BYTE *)(v132 + 2) || *(_BYTE *)(v132 + 3) )
          break;
      }
      if ( v45 < 3 )
      {
        v618 = 0;
        LOBYTE(v44) = 1;
        refreshed = HeapRowObject::RefreshSecondaryFragment(v10, 1, v44, &v618);
        goto LABEL_271;
      }
LABEL_270:
      v618 = 0;
      refreshed = HeapRowObject::RefreshSecondaryFragment(v10, 1, v130, &v618);
      if ( !v130 )
        goto LABEL_285;
LABEL_271:
      if ( (unsigned int)(refreshed - 1) > 1 )
        goto LABEL_285;
      v606 = ++v45;
      HeapFragment::ReleasePageAccess((HeapFragment *)v21);
      if ( !*(_BYTE *)(*((_QWORD *)v10 + 5) + 41LL) )
        SOS_Task::Sleep(10);
    }
    v618 = 0;
    HeapRowObject::RefreshSecondaryFragment(v10, 1, 0, &v618);
LABEL_285:
    if ( !*((_QWORD *)v10 + 91) )
      HeapFragment::ReAcquirePageAccessLong((char *)v10 + 688, 0);
    if ( !*((_DWORD *)v10 + 316) )
      HeapFragment::SetupCachedRowInfo((char *)v10 + 688, 1);
    v48 = *((_DWORD *)v10 + 315);
    v587 = v48;
LABEL_80:
    *((_DWORD *)v10 + 397) |= 1u;
    v39 = *((_DWORD *)v10 + 397);
  }
  while ( v40 || v7 == 1 || !v48 );
  v49 = v622;
  v50 = v605;
  HeapRowObject::GetRidAndPageVersionId(v605, v622, 0, 1);
  if ( v7 != 4 )
    goto LABEL_538;
  v699 = *(_DWORD *)v49;
  v700 = *((_WORD *)v49 + 2);
  v701 = 0;
  v698 = 0;
  v705 = 0;
  v702 = 0;
  v703 = 0;
  if ( !(unsigned int)HeapPageManager::GetPageWithIdInternal(**((_QWORD **)v635 + 91), &v698, 3, 2, &v660) )
    goto LABEL_40;
  v51 = (HeapPageManager ***)((char *)v605 + 48);
  v52 = INVALID_HPAGE;
  if ( *((_QWORD *)v605 + 8) != INVALID_HPAGE
    || (v53 = *(&INVALID_HPAGE + 1), *((_QWORD *)v605 + 9) != *(&INVALID_HPAGE + 1)) )
  {
    if ( (*((_BYTE *)v605 + 160) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v605 + 168)) )
    {
      (*v51)[6] = (HeapPageManager *)((char *)(*v51)[6] - 1);
    }
    *((_BYTE *)v50 + 160) = 0;
    *((_DWORD *)v50 + 39) = 0;
    *((_DWORD *)v50 + 46) = 0;
    if ( (*((_BYTE *)v50 + 208) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v50 + 216)) )
    {
      (*v51)[6] = (HeapPageManager *)((char *)(*v51)[6] - 1);
    }
    *((_BYTE *)v50 + 208) = 0;
    *((_DWORD *)v50 + 51) = 0;
    *((_DWORD *)v50 + 58) = 0;
    if ( *((_QWORD *)v50 + 11) )
    {
      v54 = *((_QWORD *)v50 + 8);
      *((_BYTE *)v50 + 102) = 0;
      *((_QWORD *)v50 + 11) = 0;
      *((_WORD *)v50 + 50) = 0;
      *(_DWORD *)(v54 + 72) = 0;
    }
    HeapPageManager::ReleaseHPage(**v51, (struct HeapRowObject *)((char *)v50 + 64));
    *((_OWORD *)v50 + 4) = INVALID_HPAGE;
    *((_DWORD *)v50 + 20) = -1;
    *((_DWORD *)v50 + 156) = 0;
    *((_QWORD *)v50 + 81) = 0;
    *((_QWORD *)v50 + 80) = 0;
    *((_QWORD *)v50 + 82) = 0;
    *((_DWORD *)v50 + 168) = -1;
    *((_WORD *)v50 + 338) = -1;
    *(_QWORD *)((char *)v50 + 678) = 0;
    *((_DWORD *)v50 + 60) = 2;
    v53 = *(&INVALID_HPAGE + 1);
    v52 = INVALID_HPAGE;
  }
  v134 = v605;
  if ( *((_QWORD *)v605 + 88) != v52 || *((_QWORD *)v605 + 89) != v53 )
  {
    if ( (*((_BYTE *)v605 + 800) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v605 + 808)) )
    {
      --*(_QWORD *)(*((_QWORD *)v605 + 86) + 48LL);
    }
    *((_BYTE *)v134 + 800) = 0;
    *((_DWORD *)v134 + 199) = 0;
    *((_DWORD *)v134 + 206) = 0;
    if ( (*((_BYTE *)v134 + 848) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v134 + 856)) )
    {
      --*(_QWORD *)(*((_QWORD *)v134 + 86) + 48LL);
    }
    *((_BYTE *)v134 + 848) = 0;
    *((_DWORD *)v134 + 211) = 0;
    *((_DWORD *)v134 + 218) = 0;
    if ( *((_QWORD *)v134 + 91) )
    {
      v135 = *((_QWORD *)v134 + 88);
      *((_BYTE *)v134 + 742) = 0;
      *((_QWORD *)v134 + 91) = 0;
      *((_WORD *)v134 + 370) = 0;
      *(_DWORD *)(v135 + 72) = 0;
    }
    HeapPageManager::ReleaseHPage(**((HeapPageManager ***)v134 + 86), (struct HeapRowObject *)((char *)v134 + 704));
    *((_OWORD *)v134 + 44) = INVALID_HPAGE;
    *((_DWORD *)v134 + 180) = -1;
    *((_DWORD *)v134 + 316) = 0;
    *((_QWORD *)v134 + 161) = 0;
    *((_QWORD *)v134 + 160) = 0;
    *((_QWORD *)v134 + 162) = 0;
    *((_DWORD *)v134 + 328) = -1;
    *((_WORD *)v134 + 658) = -1;
    *(_QWORD *)((char *)v134 + 1318) = 0;
    *((_DWORD *)v134 + 220) = 2;
  }
  v136 = v605;
  *((_DWORD *)v605 + 397) = 0;
  v697 = 1;
  v137 = **v51;
  v138 = v51[1][1];
  *((_OWORD *)v51 + 1) = v660;
  HeapPageManager::GetPageRef(v137, (const struct HPageHandle *)(v51 + 2), (struct HeapPageRef *)(v51 + 5));
  v51[75] = (HeapPageManager **)*v51[5];
  *((_DWORD *)v51 + 22) = 3;
  *((_DWORD *)v51 + 155) = 0;
  v141 = (*v51)[3];
  v142 = *((_DWORD *)v51[26] + 4);
  if ( (v142 & 1) != 0 && (v142 & 0x40) == 0 )
  {
    v139 = *((_QWORD *)v138 + 6);
    if ( *(_BYTE *)(v139 + 7378) )
    {
      if ( !*(_BYTE *)(v139 + 8272) )
      {
        v143 = v51[2];
        v144 = *((_DWORD *)v143 + 36);
        v145 = *((unsigned __int16 *)v143 + 74);
        LOWORD(v143) = *(_WORD *)(v139 + 1720);
        v697 = 6;
        v696 = (__int16)v143;
        v694 = v144;
        v695 = (unsigned __int16)v145;
        LOBYTE(v140) = 1;
        LOBYTE(v145) = 6;
        if ( !(unsigned __int8)VersionMgr::GetInstantLockInRecoveryNoWait(v51[1][1], v145, &v694, v140) )
        {
          HeapFragment::ReleasePageAccess((HeapFragment *)v51);
          v146 = (*v51)[3];
          v147 = v51[1];
          LOBYTE(v579) = 1;
          LOBYTE(v148) = 6;
          VersionMgr::GetInstantLockInRecoveryWithWait(v147[1], v148, *((unsigned int *)v146 + 6), &v694, v579);
        }
      }
    }
  }
  if ( *((_BYTE *)v141 + 2) )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(HeapPageManager *))(*(_QWORD *)v138 + 40LL))(v138) )
    {
      v149 = v51[2];
      v150 = *((_DWORD *)v149 + 36);
      v151 = *((_WORD *)v149 + 74);
      v152 = *(_WORD *)(*((_QWORD *)v51[1][1] + 6) + 1720LL);
      v697 = 6;
      v696 = v152;
      v694 = v150;
      v695 = v151;
      if ( (int)HeapFragment::LockResource(v51, &v694, 2, v141, v51 + 18, 1, 1, 1) < 0 )
      {
        if ( v51[2] != (HeapPageManager **)INVALID_HPAGE || v51[3] != (HeapPageManager **)*(&INVALID_HPAGE + 1) )
        {
          _mm_lfence();
          if ( ((_BYTE)v51[14] & 2) != 0 )
          {
            _mm_lfence();
            if ( (unsigned int)LockReference::Release((LockReference *)(v51 + 15)) )
            {
              _mm_lfence();
              (*v51)[6] = (HeapPageManager *)((char *)(*v51)[6] - 1);
            }
          }
          *((_BYTE *)v51 + 112) = 0;
          *((_DWORD *)v51 + 27) = 0;
          *((_DWORD *)v51 + 34) = 0;
          if ( ((_BYTE)v51[20] & 2) != 0 )
          {
            _mm_lfence();
            if ( (unsigned int)LockReference::Release((LockReference *)(v51 + 21)) )
            {
              _mm_lfence();
              (*v51)[6] = (HeapPageManager *)((char *)(*v51)[6] - 1);
            }
          }
          *((_BYTE *)v51 + 160) = 0;
          *((_DWORD *)v51 + 39) = 0;
          *((_DWORD *)v51 + 46) = 0;
          if ( v51[5] )
          {
            _mm_lfence();
            v153 = v51[2];
            *((_BYTE *)v51 + 54) = 0;
            v51[5] = 0;
            *((_WORD *)v51 + 26) = 0;
            *((_DWORD *)v153 + 18) = 0;
          }
          HeapPageManager::ReleaseHPage(**v51, (struct HPageHandle *)(v51 + 2));
          *((_OWORD *)v51 + 1) = INVALID_HPAGE;
          *((_DWORD *)v51 + 8) = -1;
          *((_DWORD *)v51 + 144) = 0;
          v51[75] = 0;
          v51[74] = 0;
          v51[76] = 0;
          *((_DWORD *)v51 + 156) = -1;
          *((_WORD *)v51 + 314) = -1;
          *(HeapPageManager ***)((char *)v51 + 630) = 0;
          *((_DWORD *)v51 + 48) = 2;
        }
        goto LABEL_321;
      }
    }
  }
  *((_DWORD *)v51 + 48) = 3;
  if ( !v51[5] )
  {
    HeapFragment::ReAcquirePageAccessLong(v51, 1);
    if ( *((_DWORD *)v51 + 48) != 3 )
    {
LABEL_321:
      *((_DWORD *)v136 + 397) |= 1u;
      goto LABEL_40;
    }
  }
  v154 = *((_DWORD *)v136 + 397) | 1;
  *((_DWORD *)v136 + 397) = v154;
  v155 = *((__int16 *)v622 + 3);
  v610 = v155;
  v156 = v605;
  v608 = v605;
  v157 = 0;
  v606 = 0;
  *((_DWORD *)v136 + 397) = v154 & 0xFFFFFFFE;
  v158 = v604;
  v159 = v585;
  while ( 2 )
  {
    v585 = v159;
    v160 = v605;
    if ( *((_DWORD *)v605 + 220) == 4
      && (*((_QWORD *)v605 + 88) != INVALID_HPAGE || *((_QWORD *)v605 + 89) != *(&INVALID_HPAGE + 1)) )
    {
      if ( (*((_BYTE *)v605 + 800) & 2) != 0
        && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v605 + 808)) )
      {
        --*(_QWORD *)(*((_QWORD *)v160 + 86) + 48LL);
      }
      *((_BYTE *)v160 + 800) = 0;
      *((_DWORD *)v160 + 199) = 0;
      *((_DWORD *)v160 + 206) = 0;
      if ( (*((_BYTE *)v160 + 848) & 2) != 0
        && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v160 + 856)) )
      {
        --*(_QWORD *)(*((_QWORD *)v160 + 86) + 48LL);
      }
      *((_BYTE *)v160 + 848) = 0;
      *((_DWORD *)v160 + 211) = 0;
      *((_DWORD *)v160 + 218) = 0;
      if ( *((_QWORD *)v160 + 91) )
      {
        v161 = *((_QWORD *)v160 + 88);
        *((_BYTE *)v160 + 742) = 0;
        *((_QWORD *)v160 + 91) = 0;
        *((_WORD *)v160 + 370) = 0;
        *(_DWORD *)(v161 + 72) = 0;
      }
      HeapPageManager::ReleaseHPage(**((HeapPageManager ***)v160 + 86), (struct HeapRowObject *)((char *)v160 + 704));
      *((_OWORD *)v160 + 44) = INVALID_HPAGE;
      *((_DWORD *)v160 + 180) = -1;
      *((_DWORD *)v160 + 316) = 0;
      *((_QWORD *)v160 + 161) = 0;
      *((_QWORD *)v160 + 160) = 0;
      *((_QWORD *)v160 + 162) = 0;
      *((_DWORD *)v160 + 328) = -1;
      *((_WORD *)v160 + 658) = -1;
      *(_QWORD *)((char *)v160 + 1318) = 0;
      *((_DWORD *)v160 + 220) = 2;
    }
    if ( v157 <= 0 )
    {
      if ( v157 )
      {
        v159 = v585;
        goto LABEL_345;
      }
    }
    else
    {
      v162 = v605;
      if ( !*((_QWORD *)v605 + 11) )
        HeapFragment::ReAcquirePageAccessLong((char *)v605 + 48, 0);
      if ( !*((_DWORD *)v162 + 156) )
        HeapFragment::SetupCachedRowInfo((char *)v162 + 48, 1);
      v159 = *((_DWORD *)v162 + 154);
LABEL_345:
      if ( !*(_BYTE *)(*((_QWORD *)v605 + 5) + 41LL) )
      {
        if ( v158 )
          goto LABEL_532;
        goto LABEL_511;
      }
    }
    v163 = (char *)v605 + 48;
    v164 = *(HeapRowObject **)(*((_QWORD *)v605 + 7) + 8LL);
    v616 = v164;
    v735 = -1;
    v738 = 0;
    v737 = 0;
    v743 = 0;
    *(_QWORD *)((char *)&v744 + 2) = 0;
    v739 = 0;
    v746 = -1;
    v614 = 0;
    v615 = 0;
    v165 = *(LckInfo **)(*((_QWORD *)v605 + 6) + 24LL);
    v623 = v165;
    LOBYTE(v586) = 0;
    v166 = (char *)v605 + 144;
    if ( (*((_BYTE *)v605 + 160) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v605 + 168)) )
    {
      --*(_QWORD *)(*(_QWORD *)v163 + 48LL);
    }
    v163[112] = 0;
    *((_DWORD *)v163 + 27) = 0;
    *((_DWORD *)v163 + 34) = 0;
    *((_DWORD *)v163 + 8) = v155;
    v167 = *(_DWORD *)(*((_QWORD *)v163 + 26) + 16LL);
    if ( (v167 & 1) != 0 && (v167 & 0x40) == 0 )
    {
      v168 = *((_QWORD *)v164 + 6);
      if ( *(_BYTE *)(v168 + 7378) )
      {
        if ( !*(_BYTE *)(v168 + 8272) )
        {
          v756[14] = 1;
          v169 = **((_QWORD **)v163 + 5);
          v170 = *((_DWORD *)v163 + 8);
          v648 = *(_DWORD *)(v169 + 32);
          v649 = *(_WORD *)(v169 + 36);
          v650 = v170;
          LockRes::SetRidResource(
            (LockRes *)v756,
            *(_WORD *)(*((_QWORD *)v164 + 6) + 1720LL),
            (const struct RowId *)&v648);
          LOBYTE(v171) = 1;
          LOBYTE(v172) = 3;
          if ( !(unsigned __int8)VersionMgr::GetInstantLockInRecoveryNoWait(v164, v172, v756, v171) )
          {
            HeapFragment::ReleasePageAccess((HeapFragment *)v163);
            v173 = *(_QWORD *)(*(_QWORD *)v163 + 24LL);
            LOBYTE(v579) = 1;
            LOBYTE(v174) = 3;
            VersionMgr::GetInstantLockInRecoveryWithWait(v164, v174, *(unsigned int *)(v173 + 24), v756, v579);
            if ( !*((_QWORD *)v163 + 5) )
              HeapFragment::ReAcquirePageAccessLong(v163, 0);
          }
        }
      }
    }
    v175 = NullXdesId;
    v600 = NullXdesId;
    LOWORD(v603) = word_10318AB38;
    while ( 1 )
    {
      if ( *(_BYTE *)(*((_QWORD *)v163 + 1) + 41LL) )
      {
        if ( (*((_DWORD *)v165 + 1) & 0x140) == 0 )
        {
          v176 = *((_QWORD *)v163 + 75);
          if ( *((_WORD *)v163 + 16) < *(_WORD *)(v176 + 22) )
          {
            v177 = (struct IMemObj **)*((int *)v163 + 8);
            v178 = v177;
            v621 = v177;
            if ( *(_WORD *)(v176 + 2 * (4095LL - (_QWORD)v177)) )
            {
              v746 = (int)v177;
              if ( *(char *)(v176 + 2) < 0 )
              {
                v180 = (unsigned __int8 *)(v176 + 96);
                _mm_prefetch((const char *)(v176 + 96), 0);
                if ( !v735 || (v179 = v739) == 0 )
                {
                  v747 = 0;
                  v748 = 0;
                  v749 = 0;
                  v750 = 0;
                  v751 = 0;
                  v752 = 0;
                  v753 = 0;
                  v754 = 0;
                  v179 = PageComprMgr::PageComprMgr((PageComprMgr *)&v747);
                }
                v181 = Page::GetLsn(v176, v761, 0, 0);
                v182 = v181;
                if ( v180 == *(unsigned __int8 **)v179 )
                  LSN::operator==(v181, (char *)v179 + 96);
                *(_QWORD *)v179 = v180;
                v183 = *(_WORD *)(v182 + 8);
                v184 = *(_DWORD *)(v182 + 4);
                *((_DWORD *)v179 + 24) = *(_DWORD *)v182;
                *((_DWORD *)v179 + 25) = v184;
                *((_WORD *)v179 + 52) = v183;
                *((_DWORD *)v179 + 27) = *(_DWORD *)(v176 + 32);
                *((_WORD *)v179 + 56) = *(_WORD *)(v176 + 36);
                *((_WORD *)v179 + 57) = 0;
                v185 = 3LL * *v180;
                LODWORD(v620) = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v180);
                v186 = word_102883984[v185];
                v589 = v186;
                *((_WORD *)v179 + 8) = -1;
                *((_QWORD *)v179 + 3) = 0;
                *((_DWORD *)v179 + 5) = 0;
                *(_QWORD *)((char *)v179 + 46) = 0;
                *((_QWORD *)v179 + 7) = 0;
                *((_QWORD *)v179 + 4) = 0;
                v187 = (struct PageComprInfo *)((char *)v179 + 72);
                *((_QWORD *)v179 + 9) = 0;
                *((_QWORD *)v179 + 10) = 0;
                *((_WORD *)v179 + 44) = 0;
                if ( (**(_BYTE **)v179 & 2) != 0 )
                {
                  v188 = &v180[v186];
                  if ( (v180[v186] & 1) != 0 )
                  {
                    *((_WORD *)v179 + 8) = 1;
                    *((_QWORD *)v179 + 3) = v188;
                    v189 = *v188;
                    switch ( *v188 & 0x1C )
                    {
                      case 0:
                      case 0xC:
                      case 0x10:
                      case 0x14:
                      case 0x18:
                      case 0x1C:
                        if ( (v188[1] & 0x80u) != 0 )
                        {
                          v192 = *(_WORD *)(v188 + 1);
                          *((_WORD *)v179 + 9) = v192;
                          v190 = 3;
                          v191 = HIBYTE(v192) | ((v192 & 0x7F) << 8);
                        }
                        else
                        {
                          v190 = 2;
                          v191 = v188[1];
                        }
                        *((_WORD *)v179 + 9) = v191;
                        *((_WORD *)v179 + 20) = v190;
                        *((_WORD *)v179 + 22) = v190 + (((unsigned int)*((unsigned __int16 *)v179 + 9) + 1) >> 1);
                        v193 = *((unsigned __int16 *)v179 + 9);
                        if ( v193 > 0x1E )
                          *((_WORD *)v179 + 21) = (int)(v193 - 1) / 30;
                        else
                          *((_WORD *)v179 + 21) = 0;
                        *((_DWORD *)v179 + 5) = 0;
                        *((_DWORD *)v179 + 16) = 0;
                        *((_QWORD *)v179 + 7) = 0;
                        *((_QWORD *)v179 + 4) = 0;
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
                        v187 = (struct PageComprInfo *)((char *)v179 + 72);
                        *((_QWORD *)v179 + 7) = 0;
                        *((_QWORD *)v179 + 4) = 0;
                        break;
                      case 4:
                        if ( (v189 & 0x1C) == 4 && (v189 & 2) != 0 )
                        {
                          CDRecord::Reset((struct PageComprInfo *)((char *)v179 + 18));
                          *((_QWORD *)v179 + 3) = v188;
                          *((_DWORD *)v179 + 5) = 15;
                          *((_DWORD *)v179 + 16) = 0;
                          *((_DWORD *)v179 + 16) = 1;
                          v187 = (struct PageComprInfo *)((char *)v179 + 72);
                          *((_QWORD *)v179 + 7) = 0;
                          *((_QWORD *)v179 + 4) = 0;
                        }
                        else
                        {
                          CDRecord::Reset((struct PageComprInfo *)((char *)v179 + 18));
                          *((_QWORD *)v179 + 3) = v188;
                          *((_DWORD *)v179 + 5) = 1;
                          *((_DWORD *)v179 + 16) = 0;
                          v187 = (struct PageComprInfo *)((char *)v179 + 72);
                          *((_QWORD *)v179 + 7) = 0;
                          *((_QWORD *)v179 + 4) = 0;
                        }
                        break;
                      case 8:
                        CDRecord::Reset((struct PageComprInfo *)((char *)v179 + 18));
                        *((_QWORD *)v179 + 3) = v188;
                        *((_DWORD *)v179 + 5) = 9;
                        *((_DWORD *)v179 + 16) = 0;
                        v187 = (struct PageComprInfo *)((char *)v179 + 72);
                        *((_QWORD *)v179 + 7) = 0;
                        *((_QWORD *)v179 + 4) = 0;
                        break;
                    }
                  }
                  else
                  {
                    *((_WORD *)v179 + 8) = 0;
                    v194 = 0;
                    *((_QWORD *)v179 + 3) = v188;
                    *((_DWORD *)v179 + 5) = 0;
                    *(_DWORD *)((char *)v179 + 54) = 0;
                    switch ( *v188 & 0xE )
                    {
                      case 0:
                      case 2:
                      case 8:
                      case 0xC:
                        v194 = *((unsigned __int16 *)v188 + 1);
                        if ( (unsigned int)(v194 - 1) > 0x1F9D )
                        {
                          RaiseInconsistencyError(&v180[v186], 6);
                          goto LABEL_392;
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
LABEL_392:
                        v187 = (struct PageComprInfo *)((char *)v179 + 72);
                        break;
                      case 4:
                        v194 = 9;
                        break;
                      case 6:
                      case 0xA:
                        break;
                      case 0xE:
                        v194 = 1;
                        break;
                    }
                    *((_DWORD *)v179 + 8) = v194;
                    *(_QWORD *)((char *)v179 + 46) = 0;
                    v178 = v621;
                  }
                  LOWORD(v186) = v589;
                }
                if ( (**(_BYTE **)v179 & 4) != 0 )
                {
                  v195 = (__int16)v186;
                  if ( WORD1(v620) )
                    v195 = *(unsigned __int16 *)&v180[2 * SWORD1(v620) + 1];
                  PageDictionary::Init(v187, &v180[v195]);
                }
                v196 = (PageComprInfoCache *)*((_QWORD *)v179 + 1);
                if ( v196 )
                  PageComprInfoCache::Init(v196, v179);
                v175 = v600;
              }
              else
              {
                v179 = 0;
              }
              v197 = *(unsigned __int16 *)(v176 + 14);
              v198 = (char *)(v176 + *(unsigned __int16 *)(v176 + 2 * (4095LL - (_QWORD)v178)));
              v319 = (*v198 & 1) == 0;
              v738 = v198;
              if ( v319 )
              {
                v735 = 0;
                v737 = 0;
                LODWORD(v744) = 0;
                switch ( *v198 & 0xE )
                {
                  case 0:
                  case 2:
                  case 8:
                  case 0xC:
                    v197 = *((unsigned __int16 *)v198 + 1);
                    if ( (unsigned int)(v197 - 1) > 0x1F9D )
                      RaiseInconsistencyError(v198, 6);
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
                    v197 = 9;
                    break;
                  case 6:
                  case 0xA:
                    break;
                  case 0xE:
                    v197 = 1;
                    break;
                }
                LODWORD(v739) = v197;
                v743 = v176 + 0x2000;
              }
              else
              {
                v735 = 1;
                v199 = *v198;
                switch ( *v198 & 0x1C )
                {
                  case 0:
                  case 0xC:
                  case 0x10:
                  case 0x14:
                  case 0x18:
                  case 0x1C:
                    if ( v198[1] < 0 )
                    {
                      v200 = HIBYTE(*(_WORD *)(v198 + 1)) | ((*(_WORD *)(v198 + 1) & 0x7F) << 8);
                      v736 = v200;
                      v201 = 3;
                      v740 = 3;
                    }
                    else
                    {
                      v200 = (unsigned __int8)v198[1];
                      v736 = v200;
                      v201 = 2;
                      v740 = 2;
                    }
                    v742 = v201 + (((unsigned int)v200 + 1) >> 1);
                    if ( v200 > 0x1Eu )
                      v741 = (v200 - 1) / 30;
                    else
                      v741 = 0;
                    v737 = 0;
                    v745 = 0;
                    *(_QWORD *)((char *)&v744 + 2) = v176 + 0x2000;
                    v739 = v179;
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
                    *(_QWORD *)((char *)&v744 + 2) = v176 + 0x2000;
                    v739 = v179;
                    break;
                  case 4:
                    if ( (v199 & 0x1C) == 4 && (v199 & 2) != 0 )
                    {
                      CDRecord::Reset((CDRecord *)&v736);
                      v738 = v198;
                      v737 = 15;
                      v745 = 1;
                      *(_QWORD *)((char *)&v744 + 2) = v176 + 0x2000;
                      v739 = v179;
                    }
                    else
                    {
                      CDRecord::Reset((CDRecord *)&v736);
                      v738 = v198;
                      v737 = 1;
                      v745 = 0;
                      *(_QWORD *)((char *)&v744 + 2) = v176 + 0x2000;
                      v739 = v179;
                    }
                    break;
                  case 8:
                    CDRecord::Reset((CDRecord *)&v736);
                    v738 = v198;
                    v737 = 9;
                    v745 = 0;
                    *(_QWORD *)((char *)&v744 + 2) = v176 + 0x2000;
                    v739 = v179;
                    break;
                }
              }
              if ( v735 )
                CDRecord::GetXdesTs(&v736, &v628);
              else
                FixedVarRecord::GetXdesTs(&v736, &v628);
              v614 = v628;
              v615 = v629;
              if ( v629 == (_WORD)v603 && v628 == v175 )
              {
                v164 = v616;
              }
              else
              {
                v601 = v628;
                v602 = v629;
                v164 = v616;
                if ( (unsigned int)XDES::GetTIDLockOption(v616, &v601) == 3 )
                  goto LABEL_526;
                v175 = v614;
                v600 = v614;
                LOWORD(v603) = v615;
              }
              v166 = v163 + 96;
              v165 = v623;
            }
          }
        }
      }
      if ( (_BYTE)v586 )
        break;
      v758[14] = 1;
      v202 = **((_QWORD **)v163 + 5);
      v203 = *((_DWORD *)v163 + 8);
      v651 = *(_DWORD *)(v202 + 32);
      v652 = *(_WORD *)(v202 + 36);
      v653 = v203;
      LockRes::SetRidResource((LockRes *)v758, *(_WORD *)(*((_QWORD *)v164 + 6) + 1720LL), (const struct RowId *)&v651);
      v204 = HeapFragment::LockResource(v163, v758, 3, v165, v166, 1, 0, 1);
      if ( v204 < 0 )
        goto LABEL_525;
      if ( v204 != 1 )
        break;
      LOBYTE(v586) = 1;
    }
    *((_DWORD *)v163 + 48) = 4;
    v205 = *((_QWORD *)v164 + 6);
    if ( *(_QWORD *)(v205 + 6952) )
    {
      if ( (v206 = *(_DWORD *)(*((_QWORD *)v163 + 26) + 16LL), (v206 & 1) != 0)
        && (v206 & 0x40) == 0
        && *(_BYTE *)(v205 + 7378)
        && !*(_BYTE *)(v205 + 8272)
        || !LckInfo::IsNoLock(v165) )
      {
        v207 = *((_QWORD *)v163 + 75);
        if ( *((_WORD *)v163 + 16) < *(_WORD *)(v207 + 22) )
        {
          v208 = *((int *)v163 + 8);
          v209 = (struct IMemObj **)(4095 - v208);
          v621 = (struct IMemObj **)(4095 - v208);
          if ( *(_WORD *)(v207 + 2 * (4095 - v208)) )
          {
            v746 = v208;
            if ( *(char *)(v207 + 2) < 0 )
            {
              v211 = (unsigned __int8 *)(v207 + 96);
              _mm_prefetch((const char *)(v207 + 96), 0);
              if ( !v735 || (v210 = v739) == 0 )
              {
                v747 = 0;
                v748 = 0;
                v749 = 0;
                v750 = 0;
                v751 = 0;
                v752 = 0;
                v753 = 0;
                v754 = 0;
                v210 = PageComprMgr::PageComprMgr((PageComprMgr *)&v747);
              }
              v212 = Page::GetLsn(v207, v762, 0, 0);
              v213 = v212;
              if ( v211 == *(unsigned __int8 **)v210 )
                LSN::operator==(v212, (char *)v210 + 96);
              *(_QWORD *)v210 = v211;
              v214 = *(_WORD *)(v213 + 8);
              v215 = *(_DWORD *)(v213 + 4);
              *((_DWORD *)v210 + 24) = *(_DWORD *)v213;
              *((_DWORD *)v210 + 25) = v215;
              *((_WORD *)v210 + 52) = v214;
              *((_DWORD *)v210 + 27) = *(_DWORD *)(v207 + 32);
              *((_WORD *)v210 + 56) = *(_WORD *)(v207 + 36);
              *((_WORD *)v210 + 57) = 0;
              v216 = 3LL * *v211;
              LODWORD(v619) = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v211);
              v217 = word_102883984[v216];
              v586 = word_102883984[v216];
              *((_WORD *)v210 + 8) = -1;
              *((_QWORD *)v210 + 3) = 0;
              *((_DWORD *)v210 + 5) = 0;
              *(_QWORD *)((char *)v210 + 46) = 0;
              *((_QWORD *)v210 + 7) = 0;
              *((_QWORD *)v210 + 4) = 0;
              v218 = (struct PageComprInfo *)((char *)v210 + 72);
              *((_QWORD *)v210 + 9) = 0;
              *((_QWORD *)v210 + 10) = 0;
              *((_WORD *)v210 + 44) = 0;
              if ( (**(_BYTE **)v210 & 2) != 0 )
              {
                v219 = &v211[v217];
                if ( (v211[v217] & 1) != 0 )
                {
                  *((_WORD *)v210 + 8) = 1;
                  *((_QWORD *)v210 + 3) = v219;
                  v220 = *v219;
                  switch ( *v219 & 0x1C )
                  {
                    case 0:
                    case 0xC:
                    case 0x10:
                    case 0x14:
                    case 0x18:
                    case 0x1C:
                      if ( (v219[1] & 0x80u) != 0 )
                      {
                        v223 = *(_WORD *)(v219 + 1);
                        *((_WORD *)v210 + 9) = v223;
                        v221 = 3;
                        v222 = HIBYTE(v223) | ((v223 & 0x7F) << 8);
                      }
                      else
                      {
                        v221 = 2;
                        v222 = v219[1];
                      }
                      *((_WORD *)v210 + 9) = v222;
                      *((_WORD *)v210 + 20) = v221;
                      *((_WORD *)v210 + 22) = v221 + (((unsigned int)*((unsigned __int16 *)v210 + 9) + 1) >> 1);
                      v224 = *((unsigned __int16 *)v210 + 9);
                      if ( v224 > 0x1E )
                        *((_WORD *)v210 + 21) = (int)(v224 - 1) / 30;
                      else
                        *((_WORD *)v210 + 21) = 0;
                      *((_DWORD *)v210 + 5) = 0;
                      *((_DWORD *)v210 + 16) = 0;
                      *((_QWORD *)v210 + 7) = 0;
                      *((_QWORD *)v210 + 4) = 0;
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
                      LOWORD(v217) = v586;
                      *((_QWORD *)v210 + 7) = 0;
                      *((_QWORD *)v210 + 4) = 0;
                      break;
                    case 4:
                      if ( (v220 & 0x1C) == 4 && (v220 & 2) != 0 )
                      {
                        CDRecord::Reset((struct PageComprInfo *)((char *)v210 + 18));
                        *((_QWORD *)v210 + 3) = v219;
                        *((_DWORD *)v210 + 5) = 15;
                        *((_DWORD *)v210 + 16) = 0;
                        *((_DWORD *)v210 + 16) = 1;
                        LOWORD(v217) = v586;
                        *((_QWORD *)v210 + 7) = 0;
                        *((_QWORD *)v210 + 4) = 0;
                      }
                      else
                      {
                        CDRecord::Reset((struct PageComprInfo *)((char *)v210 + 18));
                        *((_QWORD *)v210 + 3) = v219;
                        *((_DWORD *)v210 + 5) = 1;
                        *((_DWORD *)v210 + 16) = 0;
                        LOWORD(v217) = v586;
                        *((_QWORD *)v210 + 7) = 0;
                        *((_QWORD *)v210 + 4) = 0;
                      }
                      break;
                    case 8:
                      CDRecord::Reset((struct PageComprInfo *)((char *)v210 + 18));
                      *((_QWORD *)v210 + 3) = v219;
                      *((_DWORD *)v210 + 5) = 9;
                      *((_DWORD *)v210 + 16) = 0;
                      LOWORD(v217) = v586;
                      *((_QWORD *)v210 + 7) = 0;
                      *((_QWORD *)v210 + 4) = 0;
                      break;
                  }
                }
                else
                {
                  *((_WORD *)v210 + 8) = 0;
                  v225 = 0;
                  *((_QWORD *)v210 + 3) = v219;
                  *((_DWORD *)v210 + 5) = 0;
                  *(_DWORD *)((char *)v210 + 54) = 0;
                  switch ( *v219 & 0xE )
                  {
                    case 0:
                    case 2:
                    case 8:
                    case 0xC:
                      v225 = *((unsigned __int16 *)v219 + 1);
                      if ( (unsigned int)(v225 - 1) > 0x1F9D )
                      {
                        RaiseInconsistencyError(&v211[v217], 6);
                        goto LABEL_474;
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
LABEL_474:
                      LOWORD(v217) = v586;
                      break;
                    case 4:
                      v225 = 9;
                      break;
                    case 6:
                    case 0xA:
                      break;
                    case 0xE:
                      v225 = 1;
                      break;
                  }
                  *((_DWORD *)v210 + 8) = v225;
                  *(_QWORD *)((char *)v210 + 46) = 0;
                  v209 = v621;
                }
                v218 = (struct PageComprInfo *)((char *)v210 + 72);
              }
              if ( (**(_BYTE **)v210 & 4) != 0 )
              {
                v226 = (__int16)v217;
                if ( WORD1(v619) )
                  v226 = *(unsigned __int16 *)&v211[2 * SWORD1(v619) + 1];
                PageDictionary::Init(v218, &v211[v226]);
              }
              v227 = (PageComprInfoCache *)*((_QWORD *)v210 + 1);
              if ( v227 )
                PageComprInfoCache::Init(v227, v210);
            }
            else
            {
              v210 = 0;
            }
            v228 = *(unsigned __int16 *)(v207 + 14);
            v229 = (char *)(v207 + *(unsigned __int16 *)(v207 + 2LL * (_QWORD)v209));
            v319 = (*v229 & 1) == 0;
            v738 = v229;
            if ( v319 )
            {
              v735 = 0;
              v737 = 0;
              LODWORD(v744) = 0;
              switch ( *v229 & 0xE )
              {
                case 0:
                case 2:
                case 8:
                case 0xC:
                  v228 = *((unsigned __int16 *)v229 + 1);
                  if ( (unsigned int)(v228 - 1) > 0x1F9D )
                    RaiseInconsistencyError(v229, 6);
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
                  v228 = 9;
                  break;
                case 6:
                case 0xA:
                  break;
                case 0xE:
                  v228 = 1;
                  break;
              }
              LODWORD(v739) = v228;
              v743 = v207 + 0x2000;
            }
            else
            {
              v735 = 1;
              v230 = *v229;
              switch ( *v229 & 0x1C )
              {
                case 0:
                case 0xC:
                case 0x10:
                case 0x14:
                case 0x18:
                case 0x1C:
                  if ( v229[1] < 0 )
                  {
                    v231 = HIBYTE(*(_WORD *)(v229 + 1)) | ((*(_WORD *)(v229 + 1) & 0x7F) << 8);
                    v736 = v231;
                    v232 = 3;
                    v740 = 3;
                  }
                  else
                  {
                    v231 = (unsigned __int8)v229[1];
                    v736 = v231;
                    v232 = 2;
                    v740 = 2;
                  }
                  v742 = v232 + (((unsigned int)v231 + 1) >> 1);
                  if ( v231 > 0x1Eu )
                    v741 = (v231 - 1) / 30;
                  else
                    v741 = 0;
                  v737 = 0;
                  v745 = 0;
                  *(_QWORD *)((char *)&v744 + 2) = v207 + 0x2000;
                  v739 = v210;
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
                  *(_QWORD *)((char *)&v744 + 2) = v207 + 0x2000;
                  v739 = v210;
                  break;
                case 4:
                  if ( (v230 & 0x1C) == 4 && (v230 & 2) != 0 )
                  {
                    CDRecord::Reset((CDRecord *)&v736);
                    v738 = v229;
                    v737 = 15;
                    v745 = 1;
                    *(_QWORD *)((char *)&v744 + 2) = v207 + 0x2000;
                    v739 = v210;
                  }
                  else
                  {
                    CDRecord::Reset((CDRecord *)&v736);
                    v738 = v229;
                    v737 = 1;
                    v745 = 0;
                    *(_QWORD *)((char *)&v744 + 2) = v207 + 0x2000;
                    v739 = v210;
                  }
                  break;
                case 8:
                  CDRecord::Reset((CDRecord *)&v736);
                  v738 = v229;
                  v737 = 9;
                  v745 = 0;
                  *(_QWORD *)((char *)&v744 + 2) = v207 + 0x2000;
                  v739 = v210;
                  break;
              }
            }
            if ( v735 )
              CDRecord::GetXdesTs(&v736, &v626);
            else
              FixedVarRecord::GetXdesTs(&v736, &v626);
            v614 = v626;
            v615 = v627;
            v587 = v626;
            v588 = v627;
            v233 = v616;
            if ( (unsigned __int8)RecoveryUnit::ShouldOnlineTranTakeTIDLockOnDeferredTran(*((_QWORD *)v616 + 6), &v587) )
            {
              LOBYTE(v234) = 3;
              if ( !(unsigned __int8)VersionMgr::GetInstantXdesIdLockInRecoveryNoWait(v233, v234, &v614) )
              {
LABEL_525:
                *((_DWORD *)v163 + 48) = 3;
                *((_DWORD *)v163 + 8) = -1;
LABEL_526:
                *((_DWORD *)v608 + 397) |= 1u;
                goto LABEL_40;
              }
            }
          }
        }
      }
    }
    HeapFragment::SetupCachedRowInfo(v163, 1);
    v159 = *((_DWORD *)v163 + 142);
    v158 = 0;
    v156 = v608;
    v157 = v606;
    v155 = v610;
LABEL_511:
    if ( v159 != 3 )
      goto LABEL_532;
    v235 = 0;
    if ( *(_BYTE *)(*((_QWORD *)v156 + 5) + 41LL) )
    {
      v235 = v157 < 50;
LABEL_514:
      v617 = 0;
      v236 = HeapRowObject::RefreshSecondaryFragment(v156, 1, v235, &v617);
      if ( !v235 )
        goto LABEL_528;
      goto LABEL_515;
    }
    v237 = *(_QWORD *)(*((_QWORD *)v156 + 4) + 24LL);
    if ( !*(_DWORD *)(v237 + 28)
      || ((v238 = *(_BYTE *)(v237 + 1), v238 == 1) || v238 == 8) && !*(_BYTE *)(v237 + 2) && !*(_BYTE *)(v237 + 3) )
    {
      if ( v157 >= 3 )
        goto LABEL_514;
      v617 = 0;
      LOBYTE(v139) = 1;
      v236 = HeapRowObject::RefreshSecondaryFragment(v156, 1, v139, &v617);
LABEL_515:
      if ( (unsigned int)(v236 - 1) > 1 )
        goto LABEL_528;
      v606 = ++v157;
      HeapFragment::ReleasePageAccess((struct HeapRowObject *)((char *)v156 + 48));
      if ( !*(_BYTE *)(*((_QWORD *)v156 + 5) + 41LL) )
        SOS_Task::Sleep(10);
      continue;
    }
    break;
  }
  v617 = 0;
  HeapRowObject::RefreshSecondaryFragment(v156, 1, 0, &v617);
LABEL_528:
  if ( !*((_QWORD *)v156 + 91) )
    HeapFragment::ReAcquirePageAccessLong((char *)v156 + 688, 0);
  if ( !*((_DWORD *)v156 + 316) )
    HeapFragment::SetupCachedRowInfo((char *)v156 + 688, 1);
LABEL_532:
  *((_DWORD *)v156 + 397) |= 1u;
  if ( v158 )
  {
LABEL_40:
    HeapDataSetSession::DeAllocateHeapRowObject(v635, &v605);
    return;
  }
  Record = (Record *)HeapRowObject::GetRecord(v605, 1, 0);
  BackPtr = Record::GetBackPtr(Record);
  ex_raise(6, 85, 16, 1);
  if ( BackPtr )
  {
    v241 = *(_QWORD *)BackPtr;
    v634 = *(_QWORD *)BackPtr;
  }
  else
  {
    v634 = 0;
    *_errno() = 22;
    _invalid_parameter_noinfo();
    LODWORD(v241) = v634;
  }
  if ( *(_QWORD *)v622 != __PAIR64__(HIDWORD(v634), v241) )
    utassert_fail(
      1u,
      "oldRowId.rid_page == tempNewRowId.rid_page && oldRowId.rid_slot == tempNewRowId.rid_slot",
      "HeapDataSet.cpp",
      5041,
      0);
LABEL_538:
  v242 = HeapRowObject::GetRecord(v605, 1, 0);
  v243 = v242;
  v590 = *(_WORD *)v242;
  if ( v590 )
  {
    if ( *(_WORD *)v242 && (v288 = *(_QWORD **)(v242 + 16)) != 0 && *v288 )
    {
      Record::DecompressRec((Record *)&v590, Destination, 0x1F9Eu, (const struct Record *)v243);
    }
    else
    {
      CDRecord::CopyNewRec((CDRecord *)&v591, Destination, 0x1F9Eu, (const struct CDRecord *)(v243 + 2));
      v289 = 0;
      if ( *(_WORD *)v243 )
        v289 = *(_QWORD *)(v243 + 16);
      v594 = v289;
    }
    v281 = v593;
    goto LABEL_650;
  }
  if ( *(_DWORD *)(v242 + 4) )
    goto LABEL_624;
  *(_WORD *)(v242 + 2) = 0;
  v244 = *(unsigned int *)(v242 + 16);
  *(_DWORD *)(v242 + 20) = v244;
  v245 = *(_BYTE **)(v242 + 8);
  v246 = *v245;
  v247 = v245;
  v248 = v244;
  if ( (*v245 & 0x10) != 0 )
  {
    LODWORD(v244) = (((unsigned int)*(unsigned __int16 *)&v245[v244] + 7) >> 3) + 2 + v244;
    *(_DWORD *)(v243 + 20) = v244;
    v246 = *v245;
    v247 = v245;
    v248 = v244;
  }
  if ( (v246 & 0x20) == 0 )
  {
    *(_DWORD *)(v243 + 4) = v244;
    *(_WORD *)(v243 + 28) = 0;
    *(_DWORD *)(v243 + 24) = v248;
    goto LABEL_592;
  }
  v249 = (unsigned __int16 *)&v245[(unsigned int)v244];
  v250 = *v249;
  *(_WORD *)(v243 + 28) = *v249;
  if ( !v250 )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v251 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v251 )
      {
        v252 = *(_QWORD *)(v251 + 96);
        if ( v252 )
        {
          if ( *(_BYTE *)(v252 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
            else
              ex_raise(34, 68, 21, 1003);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v243 + 8), 3);
    v250 = *(_WORD *)(v243 + 28);
    v248 = *(_DWORD *)(v243 + 20);
  }
  v253 = v248 + 2 * (v250 + 1);
  *(_DWORD *)(v243 + 24) = v253;
  if ( v253 > 0x1F9E )
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
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v243 + 8), 4);
    v253 = *(_DWORD *)(v243 + 24);
  }
  v256 = v249[*(unsigned __int16 *)(v243 + 28)] & 0x7FFF;
  *(_DWORD *)(v243 + 4) = v256;
  if ( v253 > v256 )
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
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
            else
              ex_raise(34, 68, 21, 1004);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v243 + 8), 4);
  }
  while ( 2 )
  {
    v259 = *(unsigned __int16 *)(v243 + 28);
    if ( (v249[(unsigned int)(v259 - 1) + 1] & 0x8000u) == 0 )
    {
LABEL_586:
      v247 = *(_BYTE **)(v243 + 8);
      goto LABEL_592;
    }
    v260 = *(_QWORD *)(v243 + 8);
    v261 = v260 + *(unsigned int *)(v243 + 20);
    if ( (_DWORD)v259 == 1 )
    {
      v262 = *(_DWORD *)(v243 + 24);
      v263 = *(_WORD *)(v261 + 2 * v259) & 0x7FFF;
      goto LABEL_580;
    }
    v262 = *(_WORD *)(v261 + 2 * v259 - 2) & 0x7FFF;
    v263 = *(_WORD *)(v261 + 2 * v259) & 0x7FFF;
    if ( v262 < *(_DWORD *)(v243 + 24) )
    {
LABEL_581:
      RaiseInconsistencyError(v260, 7);
      v260 = *(_QWORD *)(v243 + 8);
      if ( v262 < *(_DWORD *)(v243 + 24) )
        goto LABEL_624;
    }
    else
    {
LABEL_580:
      if ( v263 < v262 )
        goto LABEL_581;
    }
    if ( v262 > *(_DWORD *)(v243 + 4) )
      goto LABEL_624;
    v264 = *(_WORD *)(v260 + v262);
    if ( v264 != 5 )
    {
      if ( v264 < 0x400u )
        goto LABEL_586;
      *(_WORD *)(v243 + 2) |= 1u;
      v319 = (*(_WORD *)(v243 + 28))-- == 1;
      if ( v319 )
        goto LABEL_586;
      continue;
    }
    break;
  }
  *(_WORD *)(v243 + 2) |= 2u;
  --*(_WORD *)(v243 + 28);
  *(_WORD *)(v243 + 42) = v262;
  v265 = *(_QWORD *)(v243 + 8) + (unsigned __int16)v262;
  v266 = *(_WORD *)(v265 + 2);
  if ( (v266 & 0x4000) != 0 )
    v267 = *(_WORD *)(v243 + 44) & 0xC7FF | v266 & 0x3800;
  else
    v267 = *(_WORD *)(v243 + 44) & 0xC7FF;
  *(_WORD *)(v243 + 44) = v267;
  *(_WORD *)(v243 + 44) = v267 ^ (*(_WORD *)(v265 + 2) ^ v267) & 0x7FF;
  v247 = *(_BYTE **)(v243 + 8);
LABEL_592:
  if ( (*v247 & 0x40) != 0 )
  {
    v268 = *(_DWORD *)(v243 + 4);
    *(_DWORD *)(v243 + 38) = v268;
    *(_DWORD *)(v243 + 4) = v268 + 14;
    VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)(v243 + 2));
    v270 = HIWORD(*(_QWORD *)VersioningInfo);
    v271 = 0;
    if ( (((__int16)v270 ^ ((unsigned int)(__int16)v270 >> 1)) & 0x2000) != 0 )
    {
      if ( (v270 & 0x4000) != 0 )
        LOWORD(v270) = v270 | 0x2000;
      else
        LOWORD(v270) = v270 & 0xDFFF;
    }
    if ( (_WORD)v270 == 0xFFFC )
      v271 = (unsigned __int16)WORD2(*(_QWORD *)VersioningInfo) >> 5;
    *(_DWORD *)(v243 + 4) += v271;
    v247 = *(_BYTE **)(v243 + 8);
  }
  else
  {
    *(_DWORD *)(v243 + 38) = 0;
  }
  v272 = *(_QWORD *)(v243 + 30);
  v273 = *(_DWORD *)(v243 + 4);
  if ( v272 && v272 < (unsigned __int64)&v247[*(unsigned int *)(v243 + 4)] )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v274 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v274 )
      {
        v275 = *(_QWORD *)(v274 + 96);
        if ( v275 )
        {
          if ( *(_BYTE *)(v275 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v243 + 8), 18);
    v273 = *(_DWORD *)(v243 + 4);
  }
  if ( (unsigned int)(v273 - 1) > 0x3F3B )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v276 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v276 )
      {
        v277 = *(_QWORD *)(v276 + 96);
        if ( v277 )
        {
          if ( *(_BYTE *)(v277 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            else
              ex_raise(34, 68, 21, 1005);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v243 + 8), 5);
  }
LABEL_624:
  v278 = *(_DWORD *)(v243 + 4);
  if ( v278 < 9 )
  {
    v279 = **(_BYTE **)(v243 + 8) & 0xE;
    if ( !v279 || v279 == 12 )
      v278 = 9;
  }
  LODWORD(v594) = *(_DWORD *)(v243 + 16);
  v591 = *(_WORD *)(v243 + 2);
  v592 = *(_DWORD *)(v243 + 4);
  v596 = *(_WORD *)(v243 + 28);
  HIDWORD(v594) = *(_DWORD *)(v243 + 20);
  v595 = *(_DWORD *)(v243 + 24);
  LODWORD(v598) = *(_DWORD *)(v243 + 38);
  memcpy_s(Destination, 0x1F9Eu, *(const void *const *)(v243 + 8), v278);
  v593 = Destination;
  HasSparseVector = FixedVarRecord::HasSparseVector((FixedVarRecord *)&v591);
  v281 = v593;
  if ( HasSparseVector )
  {
    v282 = &v593[HIDWORD(v594)];
    v283 = *(unsigned __int16 *)v282 - 1;
    if ( (v591 & 1) == 0 )
      v283 = *(unsigned __int16 *)v282;
    if ( v283 == 1 )
      v284 = v595;
    else
      v284 = *(_WORD *)&v282[2 * v283 - 2] & 0x7FFF;
    v285 = *(_WORD *)&v282[2 * v283] & 0x7FFF;
    if ( v284 < v595 || v285 < v284 )
    {
      RaiseInconsistencyError(v593, 7);
      v281 = v593;
    }
    WORD2(v598) = v284;
    v286 = *(_WORD *)&v281[(unsigned __int16)v284 + 2];
    if ( (v286 & 0x4000) != 0 )
      v287 = (WORD3(v598) ^ v286) & 0x3800 ^ WORD3(v598);
    else
      v287 = WORD3(v598) & 0xC7FF;
    WORD3(v598) = v287;
    WORD3(v598) = v287 ^ (*(_WORD *)&v281[(unsigned __int16)v284 + 2] ^ v287) & 0x7FF;
  }
LABEL_650:
  v290 = v657;
  if ( *(_BYTE *)(v657 + 7390) )
  {
    if ( v590 )
      CDRecord::GetXdesTs(&v591, &v606);
    else
      FixedVarRecord::GetXdesTs(&v591, &v606);
    v610 = v606;
    v611 = v607;
    if ( v590 )
      CDRecord::GetVersionRecPtr(&v591, v658);
    else
      FixedVarRecord::GetVersionRecPtr(&v591, v658);
    RowAbortState = XdesMgr::GetRowAbortState(v290 + 6600, &v610, v658);
    v292 = RowAbortState != 0;
    if ( RowAbortState )
      AbortedXdesSweepMgr::SetMoveRow((AbortedXdesSweepMgr *)(v290 + 6960), (const struct XdesTs *)&v606);
    if ( v292 || XdesMgr::IsXdesDeferred((XdesMgr *)(v290 + 6600), (const struct XdesId *)&v610) )
      goto LABEL_889;
    v293 = v592;
    if ( v590 )
    {
      if ( (((*v593 & 0x1C) - 16) & 0xFFFFFFFB) != 0 )
      {
        if ( !v592 )
        {
          CDRecord::Resize((CDRecord *)&v591);
          v293 = v592;
          if ( !v592 )
          {
            CDRecord::Resize((CDRecord *)&v591);
            v293 = v592;
          }
        }
        if ( v293 >= 9 || (*v593 & 0x1C) != 0 && (*v593 & 0x1C) != 0xC )
          v317 = v293;
        else
          v317 = 9;
        v318 = *v593;
        v319 = (*v593 & 2) == 0;
        v320 = v599;
        goto LABEL_765;
      }
LABEL_770:
      if ( !v590 )
        goto LABEL_771;
      if ( !v293 )
      {
        CDRecord::Resize((CDRecord *)&v591);
        v293 = v592;
        if ( !v592 )
        {
          CDRecord::Resize((CDRecord *)&v591);
          v293 = v592;
        }
      }
      if ( v293 >= 9 || (*v593 & 0x1C) != 0 && (*v593 & 0x1C) != 0xC )
        v345 = v293;
      else
        v345 = 9;
      v318 = *v593;
      v346 = (*v593 & 2) == 0;
      v347 = v599;
    }
    else
    {
      if ( (*v593 & 0xE) != 2 )
      {
        if ( !v592 )
        {
          v591 = 0;
          v293 = v594;
          HIDWORD(v594) = v594;
          if ( (*v593 & 0x10) != 0 )
          {
            v293 = (((unsigned int)*(unsigned __int16 *)&v593[(unsigned int)v594] + 7) >> 3) + v594 + 2;
            HIDWORD(v594) = v293;
          }
          if ( (*v593 & 0x20) != 0 )
          {
            v294 = &v593[v293];
            v295 = *(_WORD *)v294;
            v596 = v295;
            if ( !v295 )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v296 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v296 )
                {
                  v297 = *(_QWORD *)(v296 + 96);
                  if ( v297 )
                  {
                    if ( *(_BYTE *)(v297 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                      else
                        ex_raise(34, 68, 21, 1003);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v593, 3);
              v295 = v596;
            }
            v298 = HIDWORD(v594) + 2 + 2 * v295;
            v595 = v298;
            if ( v298 > 0x1F9E )
            {
              if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
              {
                v299 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                 + SystemThread_TlsOffset
                                 + 8LL);
                if ( v299 )
                {
                  v300 = *(_QWORD *)(v299 + 96);
                  if ( v300 )
                  {
                    if ( *(_BYTE *)(v300 + 1177) )
                    {
                      if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v593, 4);
              v295 = v596;
              v298 = v595;
            }
            v293 = *(_WORD *)&v294[2 * v295] & 0x7FFF;
            v592 = v293;
            if ( v298 > v293 )
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
                        utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                      else
                        ex_raise(34, 68, 21, 1004);
                    }
                  }
                }
              }
              RaiseInconsistencyError(v593, 4);
              v295 = v596;
              v298 = v595;
              v293 = v592;
            }
            while ( *(__int16 *)&v294[2 * v295] < 0 )
            {
              v303 = &v593[HIDWORD(v594)];
              if ( v295 == 1 )
                v304 = v298;
              else
                v304 = *(_WORD *)&v303[2 * v295 - 2] & 0x7FFF;
              if ( v304 < v298 || (*(_WORD *)&v303[2 * v295] & 0x7FFFu) < v304 )
              {
                RaiseInconsistencyError(v593, 7);
                v295 = v596;
                v298 = v595;
                v293 = v592;
              }
              if ( v304 < v298 || v304 > v293 )
                goto LABEL_750;
              v305 = *(_WORD *)&v593[v304];
              if ( v305 == 5 )
              {
                v591 |= 2u;
                v596 = v295 - 1;
                WORD2(v598) = v304;
                v306 = &v593[(unsigned __int16)v304];
                v307 = *((_WORD *)v306 + 1);
                if ( (v307 & 0x4000) != 0 )
                  v308 = (WORD3(v598) ^ v307) & 0x3800 ^ WORD3(v598);
                else
                  v308 = WORD3(v598) & 0xC7FF;
                WORD3(v598) = v308;
                WORD3(v598) = v308 ^ (*((_WORD *)v306 + 1) ^ v308) & 0x7FF;
                break;
              }
              if ( v305 >= 0x400u )
              {
                v591 |= 1u;
                v319 = v295-- == 1;
                v596 = v295;
                if ( !v319 )
                  continue;
              }
              break;
            }
          }
          else
          {
            v592 = v293;
            v596 = 0;
            v595 = v293;
          }
          if ( (*v593 & 0x40) != 0 )
          {
            LODWORD(v598) = v293;
            v592 = v293 + 14;
            v309 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v591);
            v310 = HIWORD(*(_QWORD *)v309);
            v311 = 0;
            if ( (((__int16)v310 ^ ((unsigned int)(__int16)v310 >> 1)) & 0x2000) != 0 )
            {
              if ( (v310 & 0x4000) != 0 )
                LOWORD(v310) = v310 | 0x2000;
              else
                LOWORD(v310) = v310 & 0xDFFF;
            }
            if ( (_WORD)v310 == 0xFFFC )
              v311 = (unsigned __int16)WORD2(*(_QWORD *)v309) >> 5;
            v293 = v311 + v592;
            v592 += v311;
          }
          else
          {
            LODWORD(v598) = 0;
          }
          if ( v597 && v597 < (unsigned __int64)&v593[v293] )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                    else
                      ex_raise(34, 68, 21, 1018);
                  }
                }
              }
            }
            RaiseInconsistencyError(v593, 18);
            v293 = v592;
          }
          if ( v293 - 1 > 0x3F3B )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                    else
                      ex_raise(34, 68, 21, 1005);
                  }
                }
              }
            }
            RaiseInconsistencyError(v593, 5);
            v293 = v592;
          }
        }
LABEL_750:
        if ( v293 >= 9 || (v316 = *v593 & 0xE) != 0 && v316 != 12 )
        {
          v317 = v293;
          v318 = *v593;
          v319 = (*v593 & 0x40) == 0;
          v320 = LODWORD(v598);
        }
        else
        {
          v317 = 9;
          v318 = *v593;
          v319 = (*v593 & 0x40) == 0;
          v320 = LODWORD(v598);
        }
LABEL_765:
        if ( v319 )
          v320 = v317;
        v321 = 16;
        if ( !v590 )
          v321 = 22;
        if ( v320 < v321 )
          goto LABEL_770;
LABEL_877:
        if ( !v590 )
        {
LABEL_878:
          FixedVarRecord::ClearVersioningInfo((FixedVarRecord *)&v591);
          goto LABEL_889;
        }
        if ( (v318 & 2) != 0 )
        {
          if ( !v293 )
            CDRecord::Resize((CDRecord *)&v591);
          *v593 &= ~2u;
          goto LABEL_888;
        }
        goto LABEL_889;
      }
LABEL_771:
      if ( !v293 )
      {
        v591 = 0;
        v293 = v594;
        HIDWORD(v594) = v594;
        if ( (*v593 & 0x10) != 0 )
        {
          v293 = (((unsigned int)*(unsigned __int16 *)&v593[(unsigned int)v594] + 7) >> 3) + v594 + 2;
          HIDWORD(v594) = v293;
        }
        if ( (*v593 & 0x20) != 0 )
        {
          v322 = &v593[v293];
          v323 = *(_WORD *)v322;
          v596 = v323;
          if ( !v323 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(v593, 3);
            v323 = v596;
          }
          v326 = HIDWORD(v594) + 2 + 2 * v323;
          v595 = v326;
          if ( v326 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v327 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v327 )
              {
                v328 = *(_QWORD *)(v327 + 96);
                if ( v328 )
                {
                  if ( *(_BYTE *)(v328 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(v593, 4);
            v323 = v596;
            v326 = v595;
          }
          v293 = *(_WORD *)&v322[2 * v323] & 0x7FFF;
          v592 = v293;
          if ( v326 > v293 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v329 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v329 )
              {
                v330 = *(_QWORD *)(v329 + 96);
                if ( v330 )
                {
                  if ( *(_BYTE *)(v330 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(v593, 4);
            v323 = v596;
            v326 = v595;
            v293 = v592;
          }
          while ( *(__int16 *)&v322[2 * v323] < 0 )
          {
            v331 = &v593[HIDWORD(v594)];
            if ( v323 == 1 )
              v332 = v326;
            else
              v332 = *(_WORD *)&v331[2 * v323 - 2] & 0x7FFF;
            if ( v332 < v326 || (*(_WORD *)&v331[2 * v323] & 0x7FFFu) < v332 )
            {
              RaiseInconsistencyError(v593, 7);
              v323 = v596;
              v326 = v595;
              v293 = v592;
            }
            if ( v332 < v326 || v332 > v293 )
              goto LABEL_858;
            v333 = *(_WORD *)&v593[v332];
            if ( v333 == 5 )
            {
              v591 |= 2u;
              v596 = v323 - 1;
              WORD2(v598) = v332;
              v334 = &v593[(unsigned __int16)v332];
              v335 = *((_WORD *)v334 + 1);
              if ( (v335 & 0x4000) != 0 )
                v336 = (v335 ^ WORD3(v598)) & 0x3800 ^ WORD3(v598);
              else
                v336 = WORD3(v598) & 0xC7FF;
              WORD3(v598) = v336;
              WORD3(v598) = v336 ^ (*((_WORD *)v334 + 1) ^ v336) & 0x7FF;
              break;
            }
            if ( v333 >= 0x400u )
            {
              v591 |= 1u;
              v319 = v323-- == 1;
              v596 = v323;
              if ( !v319 )
                continue;
            }
            break;
          }
        }
        else
        {
          v592 = v293;
          v596 = 0;
          v595 = v293;
        }
        if ( (*v593 & 0x40) != 0 )
        {
          LODWORD(v598) = v293;
          v592 = v293 + 14;
          v337 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v591);
          v338 = HIWORD(*(_QWORD *)v337);
          v339 = 0;
          if ( (((__int16)v338 ^ ((unsigned int)(__int16)v338 >> 1)) & 0x2000) != 0 )
          {
            if ( (v338 & 0x4000) != 0 )
              LOWORD(v338) = v338 | 0x2000;
            else
              LOWORD(v338) = v338 & 0xDFFF;
          }
          if ( (_WORD)v338 == 0xFFFC )
            v339 = (unsigned __int16)WORD2(*(_QWORD *)v337) >> 5;
          v293 = v339 + v592;
          v592 += v339;
        }
        else
        {
          LODWORD(v598) = 0;
        }
        if ( v597 && v597 < (unsigned __int64)&v593[v293] )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v340 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v340 )
            {
              v341 = *(_QWORD *)(v340 + 96);
              if ( v341 )
              {
                if ( *(_BYTE *)(v341 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(v593, 18);
          v293 = v592;
        }
        if ( v293 - 1 > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v342 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v342 )
            {
              v343 = *(_QWORD *)(v342 + 96);
              if ( v343 )
              {
                if ( *(_BYTE *)(v343 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(v593, 5);
          v293 = v592;
        }
      }
LABEL_858:
      if ( v293 >= 9 || (v344 = *v593 & 0xE) != 0 && v344 != 12 )
      {
        v345 = v293;
        v318 = *v593;
        v346 = (*v593 & 0x40) == 0;
        v347 = LODWORD(v598);
      }
      else
      {
        v345 = 9;
        v318 = *v593;
        v346 = (*v593 & 0x40) == 0;
        v347 = LODWORD(v598);
      }
    }
    if ( v346 )
      v347 = v345;
    v348 = 24;
    if ( !v590 )
      v348 = 32;
    if ( v347 >= v348 )
      goto LABEL_877;
    goto LABEL_889;
  }
  if ( !v590 )
    goto LABEL_878;
  if ( (*v281 & 2) != 0 )
  {
    if ( !v592 )
    {
      CDRecord::Resize((CDRecord *)&v591);
      v281 = v593;
    }
    *v281 &= ~2u;
LABEL_888:
    v349 = v599;
    v599 = 0;
    v592 = v349;
  }
LABEL_889:
  if ( v590 )
    CDRecord::MakePrimaryRec((CDRecord *)&v591);
  else
    FixedVarRecord::MakePrimaryRec((FixedVarRecord *)&v591);
  v350 = v605;
  v351 = v635;
  HeapDataSetSession::DeleteRowInternal(v635, v605, 0, 0);
  v352 = (HeapPageManager ***)((char *)v350 + 48);
  v353 = INVALID_HPAGE;
  if ( *((_QWORD *)v350 + 8) != INVALID_HPAGE
    || (v354 = *(&INVALID_HPAGE + 1), *((_QWORD *)v350 + 9) != *(&INVALID_HPAGE + 1)) )
  {
    if ( (*((_BYTE *)v350 + 160) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v350 + 168)) )
    {
      (*v352)[6] = (HeapPageManager *)((char *)(*v352)[6] - 1);
    }
    *((_BYTE *)v350 + 160) = 0;
    *((_DWORD *)v350 + 39) = 0;
    *((_DWORD *)v350 + 46) = 0;
    if ( (*((_BYTE *)v350 + 208) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v350 + 216)) )
    {
      (*v352)[6] = (HeapPageManager *)((char *)(*v352)[6] - 1);
    }
    *((_BYTE *)v350 + 208) = 0;
    *((_DWORD *)v350 + 51) = 0;
    *((_DWORD *)v350 + 58) = 0;
    if ( *((_QWORD *)v350 + 11) )
    {
      v355 = *((_QWORD *)v350 + 8);
      *((_BYTE *)v350 + 102) = 0;
      *((_QWORD *)v350 + 11) = 0;
      *((_WORD *)v350 + 50) = 0;
      *(_DWORD *)(v355 + 72) = 0;
    }
    HeapPageManager::ReleaseHPage(**v352, (struct HeapRowObject *)((char *)v350 + 64));
    *((_OWORD *)v350 + 4) = INVALID_HPAGE;
    *((_DWORD *)v350 + 20) = -1;
    *((_DWORD *)v350 + 156) = 0;
    *((_QWORD *)v350 + 81) = 0;
    *((_QWORD *)v350 + 80) = 0;
    *((_QWORD *)v350 + 82) = 0;
    *((_DWORD *)v350 + 168) = -1;
    *((_WORD *)v350 + 338) = -1;
    *(_QWORD *)((char *)v350 + 678) = 0;
    *((_DWORD *)v350 + 60) = 2;
    v354 = *(&INVALID_HPAGE + 1);
    v353 = INVALID_HPAGE;
  }
  v356 = v605;
  if ( *((_QWORD *)v605 + 88) != v353 || *((_QWORD *)v605 + 89) != v354 )
  {
    if ( (*((_BYTE *)v605 + 800) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v605 + 808)) )
    {
      --*(_QWORD *)(*((_QWORD *)v356 + 86) + 48LL);
    }
    *((_BYTE *)v356 + 800) = 0;
    *((_DWORD *)v356 + 199) = 0;
    *((_DWORD *)v356 + 206) = 0;
    if ( (*((_BYTE *)v356 + 848) & 2) != 0
      && (unsigned int)LockReference::Release((struct HeapRowObject *)((char *)v356 + 856)) )
    {
      --*(_QWORD *)(*((_QWORD *)v356 + 86) + 48LL);
    }
    *((_BYTE *)v356 + 848) = 0;
    *((_DWORD *)v356 + 211) = 0;
    *((_DWORD *)v356 + 218) = 0;
    if ( *((_QWORD *)v356 + 91) )
    {
      v357 = *((_QWORD *)v356 + 88);
      *((_BYTE *)v356 + 742) = 0;
      *((_QWORD *)v356 + 91) = 0;
      *((_WORD *)v356 + 370) = 0;
      *(_DWORD *)(v357 + 72) = 0;
    }
    HeapPageManager::ReleaseHPage(**((HeapPageManager ***)v356 + 86), (struct HeapRowObject *)((char *)v356 + 704));
    *((_OWORD *)v356 + 44) = INVALID_HPAGE;
    *((_DWORD *)v356 + 180) = -1;
    *((_DWORD *)v356 + 316) = 0;
    *((_QWORD *)v356 + 161) = 0;
    *((_QWORD *)v356 + 160) = 0;
    *((_QWORD *)v356 + 162) = 0;
    *((_DWORD *)v356 + 328) = -1;
    *((_WORD *)v356 + 658) = -1;
    *(_QWORD *)((char *)v356 + 1318) = 0;
    *((_DWORD *)v356 + 220) = 2;
  }
  v358 = v605;
  v620 = v605;
  *((_DWORD *)v605 + 397) = 0;
  v359 = *((_QWORD *)v351 + 33);
  if ( (*(_BYTE *)(*(_QWORD *)(**(_QWORD **)(v359 + 32) + 8LL) + 263LL) & 0x40) == 0
    || (*(_DWORD *)v359 & 0x1000000) != 0 )
  {
    v360 = 0;
  }
  else
  {
    v360 = 4;
  }
  v361 = **((_QWORD **)v351 + 92);
  v362 = v605;
  v619 = v605;
  v363 = *(_QWORD *)(*((_QWORD *)v605 + 5) + 8LL);
  v663 = 0;
  v606 = 0;
  v662 = &v590;
  if ( *(_DWORD *)(*(_QWORD *)(v361 + 8) + 256LL) == 2 )
  {
    LOWORD(v580[0]) = -1;
    v581 = 0;
    v580[1] = 0;
    v583 = 0;
    v584 = 0;
    v582 = 0;
    v364 = alloca(9120);
    v565 = 0;
    v567 = 0;
    memset(v570, 0, sizeof(v570));
    v571 = 0;
    v573 = 0;
    v575 = 0;
    v576 = 0;
    v577 = 0;
    v566 = -1;
    v569 = 0;
    v568 = 0;
    v572 = 0;
    *(_QWORD *)v570 = 0;
    v574 = 0;
    *(_QWORD *)&v576 = 0;
    DWORD2(v576) = 0;
    v663 = v580;
    v664 = &v578;
    v665 = 9118;
    v666 = &v565;
  }
  v365 = (_QWORD *)*((_QWORD *)v605 + 5);
  v366 = v365[3];
  v367 = v365;
  if ( !v366 )
  {
    v366 = v365[1] + 520LL;
    v365[3] = v366;
    v367 = (_QWORD *)*((_QWORD *)v362 + 5);
  }
  if ( *(_QWORD *)v366 == (*(unsigned int *)(*v365 + 20LL)
                         | ((unsigned __int64)*(unsigned __int16 *)(*v365 + 24LL) << 32)) << 16
    && *(_DWORD *)(v366 + 8) )
  {
    v606 = 1;
    v600 = 0;
    v368 = v605;
    v601 = *((_DWORD *)v605 + 338);
    if ( v601 )
    {
      v600 = 1;
      v585 = *((_DWORD *)v605 + 339);
      v369 = v367[3];
      v370 = *(_DWORD *)(v369 + 8);
      if ( !v370 || *(_DWORD *)(v369 + 12) )
      {
        v371 = 0;
        if ( v370 )
          goto LABEL_929;
      }
      else
      {
        v371 = 2;
LABEL_929:
        if ( *(_DWORD *)(v369 + 12) == v370 - 1 )
          v371 |= 1u;
      }
      *((_DWORD *)v605 + 338) = v371;
      *((_DWORD *)v368 + 339) = *((_DWORD *)v367 + 8);
    }
    else
    {
      v601 = v604;
      v585 = v604;
    }
  }
  else
  {
    v600 = v604;
    v601 = v604;
    v585 = v604;
  }
  *((_DWORD *)v358 + 397) &= ~1u;
  v372 = v605;
  v373 = (_OWORD *)((char *)v605 + 1328);
  *((_BYTE *)v605 + 1328) = v360 & 0x7F | *((_BYTE *)v605 + 1328) & 0x7A;
  *((_DWORD *)v372 + 339) = *(_DWORD *)(*((_QWORD *)v362 + 5) + 32LL);
  if ( *(_DWORD *)(*((_QWORD *)v372 + 4) + 64LL) != 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v363 + 624LL))(v363);
  *((_BYTE *)v605 + 1329) &= ~4u;
  v374 = v373;
  v375 = &v683;
  v376 = 2;
  do
  {
    *(_OWORD *)v375 = *v374;
    *((_OWORD *)v375 + 1) = v374[1];
    *((_OWORD *)v375 + 2) = v374[2];
    *((_OWORD *)v375 + 3) = v374[3];
    *((_OWORD *)v375 + 4) = v374[4];
    *((_OWORD *)v375 + 5) = v374[5];
    *((_OWORD *)v375 + 6) = v374[6];
    v375 += 128;
    *((_OWORD *)v375 - 1) = v374[7];
    v374 += 8;
    --v376;
  }
  while ( v376 );
  v377 = (HeapDataSetSession *)((char *)v351 + 2624);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v363 + 40LL))(v363) )
    v377 = 0;
  v608 = v377;
  v378 = v684;
  if ( v377
    && (*((_DWORD *)v377 + 2) || *((_WORD *)v377 + 6))
    && (v684 & 4) == 0
    && (unsigned int)HeapPageManager::GetPageWithIdInternal(**v352, v377, 3, 2, v677) )
  {
    v379 = v686;
    v380 = &v683;
    v381 = 2;
    do
    {
      *v379 = *(_OWORD *)v380;
      v379[1] = *((_OWORD *)v380 + 1);
      v379[2] = *((_OWORD *)v380 + 2);
      v379[3] = *((_OWORD *)v380 + 3);
      v379[4] = *((_OWORD *)v380 + 4);
      v379[5] = *((_OWORD *)v380 + 5);
      v379[6] = *((_OWORD *)v380 + 6);
      v379 += 8;
      *(v379 - 1) = *((_OWORD *)v380 + 7);
      v380 += 128;
      --v381;
    }
    while ( v381 );
    HeapFragment::SetupFragmentForInsert(v352, v677, &v662, 0, 0, v686, 0);
  }
  if ( *((_DWORD *)v352 + 48) == 4 )
    goto LABEL_1458;
  if ( (v378 & 4) != 0 )
    goto LABEL_1446;
  v674 = 0;
  v675 = 0;
  v710 = 0;
  v707 = 0;
  v708 = 0;
  v706 = 0;
  v709 = 0;
  v681 = 0;
  v682 = 0;
  v382 = v352[1];
  v616 = *v382;
  v657 = *((_QWORD *)v616 + 1) + 960LL;
  v383 = v382[1];
  (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 88LL))(v383);
  v714 = 1;
  v661[0] &= 0xFCu;
  HoBtVersioningStatus::HoBtVersioningStatus((HoBtVersioningStatus *)&v661[8]);
  *(_OWORD *)&v661[8] = v685;
  v661[0] = v683 & 1 | v661[0] & 0xFC | (v683 >> 6) & 2;
  v624 = *(_OWORD *)v661;
  v625 = (HoBtAccess *)*(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v661[8], *(__m128d *)&v661[8]);
  v384 = (Record *)v662;
  v622 = (Record *)v662;
  v385 = v662 + 1;
  if ( *v662 )
  {
    v419 = *((_DWORD *)v662 + 1);
    if ( !v419 )
    {
      CDRecord::Resize((CDRecord *)(v662 + 1));
      v419 = *(_DWORD *)(v385 + 1);
      if ( !v419 )
      {
        CDRecord::Resize((CDRecord *)v385);
        v419 = *(_DWORD *)(v385 + 1);
      }
    }
    if ( v419 >= 9 || (v421 = **(_BYTE **)(v385 + 3), (v421 & 0x1C) != 0) && (**(_BYTE **)(v385 + 3) & 0x1C) != 0xC )
      v421 = **(_BYTE **)(v385 + 3);
    else
      v419 = 9;
    if ( (v421 & 2) != 0 )
      v419 = *(_DWORD *)(v385 + 23);
    goto LABEL_1056;
  }
  if ( !*((_DWORD *)v662 + 1) )
  {
    *v385 = 0;
    v386 = *(unsigned int *)(v385 + 7);
    *(_DWORD *)(v385 + 9) = v386;
    v387 = *(char **)(v385 + 3);
    v388 = *v387;
    if ( (*v387 & 0x10) != 0 )
    {
      LODWORD(v386) = (((unsigned int)*(unsigned __int16 *)&v387[v386] + 7) >> 3) + v386 + 2;
      *(_DWORD *)(v385 + 9) = v386;
      v388 = *v387;
    }
    if ( (v388 & 0x20) != 0 )
    {
      v389 = (unsigned __int16 *)&v387[(unsigned int)v386];
      v390 = *v389;
      v385[13] = *v389;
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
        RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 3);
        v390 = v385[13];
      }
      v393 = *(_DWORD *)(v385 + 9) + 2 + 2 * v390;
      *(_DWORD *)(v385 + 11) = v393;
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
        RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
      }
      v396 = v389[(unsigned __int16)v385[13]] & 0x7FFF;
      *(_DWORD *)(v385 + 1) = v396;
      if ( *(_DWORD *)(v385 + 11) > v396 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v397 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v397 )
          {
            v398 = *(_QWORD *)(v397 + 96);
            if ( v398 )
            {
              if ( *(_BYTE *)(v398 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                else
                  ex_raise(34, 68, 21, 1004);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
      }
      v399 = v385[13];
      while ( 1 )
      {
        v400 = v399;
        if ( (v389[v399] & 0x8000u) == 0 )
          goto LABEL_1006;
        v401 = *(_QWORD *)(v385 + 3);
        v402 = v401 + *(unsigned int *)(v385 + 9);
        if ( (_DWORD)v400 == 1 )
        {
          v403 = *(_DWORD *)(v385 + 11);
          v404 = v403;
          v405 = *(_WORD *)(v402 + 2 * v400) & 0x7FFF;
        }
        else
        {
          v403 = *(_WORD *)(v402 + 2 * v400 - 2) & 0x7FFF;
          v404 = *(_DWORD *)(v385 + 11);
          v405 = *(_WORD *)(v402 + 2 * v400) & 0x7FFF;
          if ( v403 < v404 )
            goto LABEL_994;
        }
        if ( v405 < v403 )
        {
LABEL_994:
          RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 7);
          v404 = *(_DWORD *)(v385 + 11);
          v401 = *(_QWORD *)(v385 + 3);
        }
        if ( v403 < v404 || v403 > *(_DWORD *)(v385 + 1) )
          goto LABEL_1038;
        v406 = *(_WORD *)(v401 + v403);
        if ( v406 == 5 )
        {
          *v385 |= 2u;
          --v385[13];
          v385[20] = v403;
          v407 = *(_QWORD *)(v385 + 3) + (unsigned __int16)v403;
          v408 = *(_WORD *)(v407 + 2);
          if ( (v408 & 0x4000) != 0 )
            v409 = v385[21] & 0xC7FF | v408 & 0x3800;
          else
            v409 = v385[21] & 0xC7FF;
          v385[21] = v409;
          v385[21] = v409 ^ (*(_WORD *)(v407 + 2) ^ v409) & 0x7FF;
          goto LABEL_1006;
        }
        if ( v406 >= 0x400u )
        {
          *v385 |= 1u;
          v399 = v385[13] - 1;
          v385[13] = v399;
          if ( v399 )
            continue;
        }
        goto LABEL_1006;
      }
    }
    *(_DWORD *)(v385 + 1) = v386;
    v385[13] = 0;
    *(_DWORD *)(v385 + 11) = *(_DWORD *)(v385 + 9);
LABEL_1006:
    if ( (**(_BYTE **)(v385 + 3) & 0x40) != 0 )
    {
      *((_DWORD *)v385 + 9) = *(_DWORD *)(v385 + 1);
      *(_DWORD *)(v385 + 1) += 14;
      v410 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v385);
      v411 = HIWORD(*(_QWORD *)v410);
      v412 = 0;
      if ( (((__int16)v411 ^ ((unsigned int)(__int16)v411 >> 1)) & 0x2000) != 0 )
      {
        if ( (v411 & 0x4000) != 0 )
          LOWORD(v411) = v411 | 0x2000;
        else
          LOWORD(v411) = v411 & 0xDFFF;
      }
      if ( (_WORD)v411 == 0xFFFC )
        v412 = (unsigned __int16)WORD2(*(_QWORD *)v410) >> 5;
      *(_DWORD *)(v385 + 1) += v412;
    }
    else
    {
      *((_DWORD *)v385 + 9) = 0;
    }
    v413 = *(_QWORD *)(v385 + 14);
    v414 = *(_DWORD *)(v385 + 1);
    if ( v413 && v413 < *(_QWORD *)(v385 + 3) + (unsigned __int64)*(unsigned int *)(v385 + 1) )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v415 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v415 )
        {
          v416 = *(_QWORD *)(v415 + 96);
          if ( v416 )
          {
            if ( *(_BYTE *)(v416 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
              else
                ex_raise(34, 68, 21, 1018);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 18);
      v414 = *(_DWORD *)(v385 + 1);
    }
    if ( (unsigned int)(v414 - 1) > 0x3F3B )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v417 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v417 )
        {
          v418 = *(_QWORD *)(v417 + 96);
          if ( v418 )
          {
            if ( *(_BYTE *)(v418 + 1177) )
            {
              if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
              {
                ex_raise(34, 68, 21, 1005);
                RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 5);
                goto LABEL_1038;
              }
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 5);
    }
  }
LABEL_1038:
  v419 = *(_DWORD *)(v385 + 1);
  if ( v419 >= 9 || (v420 = **(_BYTE **)(v385 + 3), (v420 & 0xE) != 0) && (v420 & 0xE) != 0xC )
    v420 = **(_BYTE **)(v385 + 3);
  else
    v419 = 9;
  if ( (v420 & 0x40) != 0 )
    v419 = *((_DWORD *)v385 + 9);
  v384 = v622;
LABEL_1056:
  if ( (**(unsigned __int8 (__fastcall ***)(HeapRowObject *))v383)(v383) )
  {
    if ( !*(_WORD *)v384 )
    {
      if ( *(_DWORD *)(v385 + 1) )
        goto LABEL_1145;
      *v385 = 0;
      v422 = *(unsigned int *)(v385 + 7);
      *(_DWORD *)(v385 + 9) = v422;
      v423 = *(char **)(v385 + 3);
      v424 = *v423;
      if ( (*v423 & 0x10) != 0 )
      {
        LODWORD(v422) = (((unsigned int)*(unsigned __int16 *)&v423[v422] + 7) >> 3) + v422 + 2;
        *(_DWORD *)(v385 + 9) = v422;
        v424 = *v423;
      }
      if ( (v424 & 0x20) != 0 )
      {
        v425 = (unsigned __int16 *)&v423[(unsigned int)v422];
        v426 = *v425;
        v385[13] = *v425;
        if ( !v426 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v427 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v427 )
            {
              v428 = *(_QWORD *)(v427 + 96);
              if ( v428 )
              {
                if ( *(_BYTE *)(v428 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 3);
          v426 = v385[13];
        }
        v429 = *(_DWORD *)(v385 + 9) + 2 + 2 * v426;
        *(_DWORD *)(v385 + 11) = v429;
        if ( v429 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v430 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v430 )
            {
              v431 = *(_QWORD *)(v430 + 96);
              if ( v431 )
              {
                if ( *(_BYTE *)(v431 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
        }
        v432 = v425[(unsigned __int16)v385[13]] & 0x7FFF;
        *(_DWORD *)(v385 + 1) = v432;
        if ( *(_DWORD *)(v385 + 11) > v432 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v433 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v433 )
            {
              v434 = *(_QWORD *)(v433 + 96);
              if ( v434 )
              {
                if ( *(_BYTE *)(v434 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
        }
        v435 = v385[13];
        while ( 1 )
        {
          v436 = v435;
          if ( (v425[v435] & 0x8000u) == 0 )
            goto LABEL_1113;
          v437 = *(_QWORD *)(v385 + 3) + *(unsigned int *)(v385 + 9);
          if ( (_DWORD)v436 == 1 )
          {
            v438 = *(_DWORD *)(v385 + 11);
            v439 = v438;
            v440 = *(_WORD *)(v437 + 2 * v436) & 0x7FFF;
          }
          else
          {
            v438 = *(_WORD *)(v437 + 2 * v436 - 2) & 0x7FFF;
            v439 = *(_DWORD *)(v385 + 11);
            v440 = *(_WORD *)(v437 + 2 * v436) & 0x7FFF;
            if ( v438 < v439 )
              goto LABEL_1101;
          }
          if ( v440 < v438 )
          {
LABEL_1101:
            RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 7);
            v439 = *(_DWORD *)(v385 + 11);
          }
          if ( v438 < v439 || v438 > *(_DWORD *)(v385 + 1) )
            goto LABEL_1145;
          v441 = *(_WORD *)(v438 + *(_QWORD *)(v385 + 3));
          if ( v441 == 5 )
          {
            *v385 |= 2u;
            --v385[13];
            v385[20] = v438;
            v442 = *(_QWORD *)(v385 + 3) + (unsigned __int16)v438;
            v443 = *(_WORD *)(v442 + 2);
            if ( (v443 & 0x4000) != 0 )
              v444 = v385[21] & 0xC7FF | v443 & 0x3800;
            else
              v444 = v385[21] & 0xC7FF;
            v385[21] = v444;
            v385[21] = v444 ^ (*(_WORD *)(v442 + 2) ^ v444) & 0x7FF;
            goto LABEL_1113;
          }
          if ( v441 >= 0x400u )
          {
            *v385 |= 1u;
            v435 = v385[13] - 1;
            v385[13] = v435;
            if ( v435 )
              continue;
          }
          goto LABEL_1113;
        }
      }
      *(_DWORD *)(v385 + 1) = v422;
      v385[13] = 0;
      *(_DWORD *)(v385 + 11) = *(_DWORD *)(v385 + 9);
LABEL_1113:
      if ( (**(_BYTE **)(v385 + 3) & 0x40) != 0 )
      {
        *((_DWORD *)v385 + 9) = *(_DWORD *)(v385 + 1);
        *(_DWORD *)(v385 + 1) += 14;
        v445 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v385);
        v446 = HIWORD(*(_QWORD *)v445);
        v447 = 0;
        if ( (((__int16)v446 ^ ((unsigned int)(__int16)v446 >> 1)) & 0x2000) != 0 )
        {
          if ( (v446 & 0x4000) != 0 )
            LOWORD(v446) = v446 | 0x2000;
          else
            LOWORD(v446) = v446 & 0xDFFF;
        }
        if ( (_WORD)v446 == 0xFFFC )
          v447 = (unsigned __int16)WORD2(*(_QWORD *)v445) >> 5;
        *(_DWORD *)(v385 + 1) += v447;
      }
      else
      {
        *((_DWORD *)v385 + 9) = 0;
      }
      v448 = *(_QWORD *)(v385 + 14);
      v449 = *(_DWORD *)(v385 + 1);
      if ( v448 && v448 < *(_QWORD *)(v385 + 3) + (unsigned __int64)*(unsigned int *)(v385 + 1) )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v450 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v450 )
          {
            v451 = *(_QWORD *)(v450 + 96);
            if ( v451 )
            {
              if ( *(_BYTE *)(v451 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 18);
        v449 = *(_DWORD *)(v385 + 1);
      }
      if ( (unsigned int)(v449 - 1) <= 0x3F3B )
        goto LABEL_1145;
      if ( !byte_10316E8D7 && (qword_10317B120 & 1) == 0 )
        goto LABEL_1144;
      v452 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( !v452 )
        goto LABEL_1144;
      v453 = *(_QWORD *)(v452 + 96);
      if ( !v453 || !*(_BYTE *)(v453 + 1177) )
        goto LABEL_1144;
      if ( !byte_10316E7C7 && (qword_10317B120 & 2) == 0 )
        goto LABEL_1142;
LABEL_1143:
      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
      goto LABEL_1144;
    }
LABEL_1393:
    v419 = *(_DWORD *)(v385 + 1);
    if ( !v419 )
    {
      CDRecord::Resize((CDRecord *)v385);
      v419 = *(_DWORD *)(v385 + 1);
    }
    if ( v419 >= 9 )
      goto LABEL_1400;
    v527 = *(_BYTE **)(v385 + 3);
    if ( (*v527 & 0x1C) == 0 )
      goto LABEL_1399;
    v455 = (*v527 & 0x1C) == 12;
    goto LABEL_1398;
  }
  if ( (v624 & 1) != 0
    && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
    && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
  {
    goto LABEL_1306;
  }
  v456 = (int *)*((_QWORD *)v383 + 26);
  if ( (BYTE8(v624) & 1) != 0 || (**(unsigned __int8 (__fastcall ***)(HeapRowObject *))v383)(v383) )
    goto LABEL_1306;
  if ( (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383) )
  {
    if ( BYTE9(v624) || !v456 && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
      goto LABEL_1306;
    v457 = *((_BYTE *)v383 + 592);
    if ( (v457 & 4) == 0 )
    {
      if ( (v457 & 0x5A) != 0 )
        goto LABEL_1176;
      if ( (*((_BYTE *)v383 + 536) & 1) == 0 )
        goto LABEL_1177;
      if ( !*((_QWORD *)v383 + 26)
        && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
        && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
      {
        *((_BYTE *)v383 + 592) |= 4u;
        goto LABEL_1177;
      }
      if ( !(unsigned int)XDES::IsActive(v383) )
        (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
      if ( (*((_BYTE *)v383 + 536) & 4) != 0 )
      {
        v458 = (XDES *)(*(__int64 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 488LL))(v383);
        DoesXactGenVersion = XDES::DoesXactGenVersion(v458);
      }
      else
      {
        if ( (*((_BYTE *)v383 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v383 + 26)) )
        {
          v460 = *((_QWORD *)v383 + 26);
          if ( !*(_BYTE *)(v460 + 304) )
          {
            *(_BYTE *)(v460 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
              PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
          }
        }
        DoesXactGenVersion = (*((_BYTE *)v383 + 592) & 0x5A) != 0;
      }
      if ( DoesXactGenVersion )
      {
LABEL_1176:
        if ( (*((_BYTE *)v383 + 592) & 0x40) != 0 && BYTE10(v624) )
          goto LABEL_1306;
      }
    }
  }
LABEL_1177:
  if ( (BYTE8(v624) & 0x1C) != 0 )
    goto LABEL_1210;
  v461 = v625;
  if ( v625 )
  {
    v462 = *((_QWORD *)v625 + 1);
    v463 = *(_DWORD *)(v462 + 104) <= 0;
    if ( *(int *)(v462 + 104) < 0 )
    {
      utassert_fail(1u, "m_pHoBt->m_verRefCount >= 0", "Sql\\Ntdbms\\storeng\\include\\schemamgr.inl", 3229, 0);
      v463 = *(_DWORD *)(*((_QWORD *)v461 + 1) + 104LL) <= 0;
    }
    if ( !v463 )
    {
      v464 = *(_DWORD *)(*((_QWORD *)v625 + 1) + 256LL);
      if ( v464 )
      {
        if ( (unsigned int)(v464 - 3) > 1 )
          utassert_fail(
            1u,
            "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
            "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
            278,
            0);
      }
    }
    if ( (unsigned int)HoBtAccess::IsOibLobSourceRowset(v625) )
    {
      v465 = *((_QWORD *)v625 + 1);
      if ( (*(_BYTE *)(v465 + 265) & 1) == 0 )
      {
        v466 = *(_DWORD *)(v465 + 256);
        if ( v466 )
        {
          if ( (unsigned int)(v466 - 3) > 1 )
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
  }
  if ( !v456 || v456[30] <= 0 && v456[29] <= 0 )
  {
    v467 = *((_BYTE *)v383 + 592);
    if ( (v467 & 4) != 0 )
      goto LABEL_1306;
    if ( (v467 & 0x5A) == 0 )
    {
      if ( (*((_BYTE *)v383 + 536) & 1) == 0 )
        goto LABEL_1306;
      if ( !*((_QWORD *)v383 + 26)
        && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
        && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
      {
        goto LABEL_1305;
      }
      if ( !(unsigned int)XDES::IsActive(v383) )
        (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
      if ( (*((_BYTE *)v383 + 536) & 4) != 0 )
      {
        v468 = (XDES *)(*(__int64 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 488LL))(v383);
        v469 = XDES::DoesXactGenVersion(v468);
      }
      else
      {
        if ( (*((_BYTE *)v383 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v383 + 26)) )
        {
          v470 = *((_QWORD *)v383 + 26);
          if ( !*(_BYTE *)(v470 + 304) )
          {
            *(_BYTE *)(v470 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
              PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
          }
        }
        v469 = (*((_BYTE *)v383 + 592) & 0x5A) != 0;
      }
      if ( !v469 )
        goto LABEL_1306;
    }
LABEL_1210:
    if ( !v456 )
      goto LABEL_1265;
  }
  if ( (BYTE8(v624) & 0x1C) != 0 )
    goto LABEL_1264;
  v471 = v625;
  if ( v625 )
  {
    v472 = *((_QWORD *)v625 + 1);
    v473 = *(_DWORD *)(v472 + 104) <= 0;
    if ( *(int *)(v472 + 104) < 0 )
    {
      utassert_fail(1u, "m_pHoBt->m_verRefCount >= 0", "Sql\\Ntdbms\\storeng\\include\\schemamgr.inl", 3229, 0);
      v473 = *(_DWORD *)(*((_QWORD *)v471 + 1) + 104LL) <= 0;
    }
    if ( !v473 )
    {
      v474 = *(_DWORD *)(*((_QWORD *)v625 + 1) + 256LL);
      if ( v474 )
      {
        if ( (unsigned int)(v474 - 3) > 1 )
          utassert_fail(
            1u,
            "!m_pHobtAccess->IsVersioned () || !m_pHobtAccess->IsCompressedRowstore ()",
            "Sql\\Ntdbms\\storeng\\include\\RecVerMgr.inl",
            278,
            0);
      }
    }
    if ( (unsigned int)HoBtAccess::IsOibLobSourceRowset(v625) )
    {
      v475 = *((_QWORD *)v625 + 1);
      if ( (*(_BYTE *)(v475 + 265) & 1) == 0 )
      {
        v476 = *(_DWORD *)(v475 + 256);
        if ( v476 )
        {
          if ( (unsigned int)(v476 - 3) > 1 )
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
  }
  if ( v456[30] > 0 || v456[29] > 0 )
    goto LABEL_1264;
  v477 = *((_BYTE *)v383 + 592);
  if ( (v477 & 4) == 0 )
  {
    if ( (v477 & 0x5A) != 0 )
      goto LABEL_1244;
    if ( (*((_BYTE *)v383 + 536) & 1) == 0 )
      goto LABEL_1245;
    if ( !*((_QWORD *)v383 + 26)
      && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
      && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
    {
      *((_BYTE *)v383 + 592) |= 4u;
      goto LABEL_1245;
    }
    if ( !(unsigned int)XDES::IsActive(v383) )
      (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
    if ( (*((_BYTE *)v383 + 536) & 4) != 0 )
    {
      v478 = (XDES *)(*(__int64 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 488LL))(v383);
      v479 = XDES::DoesXactGenVersion(v478);
    }
    else
    {
      if ( (*((_BYTE *)v383 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v383 + 26)) )
      {
        v480 = *((_QWORD *)v383 + 26);
        if ( !*(_BYTE *)(v480 + 304) )
        {
          *(_BYTE *)(v480 + 304) = 1;
          if ( CommonGlobalState::m_PerfCountersEnabled )
            PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
        }
      }
      v479 = (*((_BYTE *)v383 + 592) & 0x5A) != 0;
    }
    if ( v479 )
    {
LABEL_1244:
      if ( (*((_BYTE *)v383 + 592) & 0x10) != 0 )
        goto LABEL_1265;
    }
  }
LABEL_1245:
  v481 = *((_BYTE *)v383 + 592);
  if ( (v481 & 4) != 0 )
    goto LABEL_1264;
  if ( (v481 & 0x5A) == 0 )
  {
    if ( (*((_BYTE *)v383 + 536) & 1) != 0 )
    {
      if ( !*((_QWORD *)v383 + 26)
        && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
        && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
      {
        *((_BYTE *)v383 + 592) |= 4u;
        goto LABEL_1264;
      }
      if ( !(unsigned int)XDES::IsActive(v383) )
        (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
      if ( (*((_BYTE *)v383 + 536) & 4) != 0 )
      {
        v482 = (XDES *)(*(__int64 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 488LL))(v383);
        v483 = XDES::DoesXactGenVersion(v482);
      }
      else
      {
        if ( (*((_BYTE *)v383 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v383 + 26)) )
        {
          v484 = *((_QWORD *)v383 + 26);
          if ( !*(_BYTE *)(v484 + 304) )
          {
            *(_BYTE *)(v484 + 304) = 1;
            if ( CommonGlobalState::m_PerfCountersEnabled )
              PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
          }
        }
        v483 = (*((_BYTE *)v383 + 592) & 0x5A) != 0;
      }
      if ( !v483 )
        goto LABEL_1264;
      goto LABEL_1263;
    }
LABEL_1264:
    XVB::Enqueue((XVB *)v456, 0);
    goto LABEL_1265;
  }
LABEL_1263:
  if ( (*((_BYTE *)v383 + 592) & 0x40) == 0 )
    goto LABEL_1264;
LABEL_1265:
  if ( !(unsigned int)XDES::IsActive(v383) )
    (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
  v485 = *((_QWORD *)v383 + 26);
  if ( (BYTE8(v624) & 0x24) != 0 )
    goto LABEL_1287;
  v486 = *((_BYTE *)v383 + 592);
  if ( (v486 & 4) != 0 )
    goto LABEL_1285;
  if ( (v486 & 0x5A) != 0 )
  {
LABEL_1287:
    v490 = v622;
    if ( (unsigned int)Record::HasVersioningInfo(v622) )
    {
      if ( *(_WORD *)v490 )
        CDRecord::GetVersionRecPtr(v385, v654);
      else
        FixedVarRecord::GetVersionRecPtr(v385, v654);
      v491 = 0;
      v492 = v656;
      if ( ((v656 ^ ((unsigned int)v656 >> 1)) & 0x2000) != 0 )
      {
        if ( (v656 & 0x4000) != 0 )
          v492 = v656 | 0x2000;
        else
          v492 = v656 & 0xDFFF;
      }
      if ( v492 == -4 )
        v491 = v655 >> 5;
      v419 += v491;
    }
    v493 = *((_QWORD *)v383 + 26);
    if ( !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
      && v493
      && (*(int *)(v493 + 120) > 0 || *(int *)(v493 + 116) > 0)
      && v419 < 0x1F74 )
    {
      v419 += 8;
    }
    v419 += 14;
    goto LABEL_1400;
  }
  if ( (*((_BYTE *)v383 + 536) & 1) == 0 )
    goto LABEL_1285;
  if ( !v485
    && (*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 136LL))(v383)
    && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 24LL))(v383) )
  {
LABEL_1305:
    *((_BYTE *)v383 + 592) |= 4u;
    goto LABEL_1306;
  }
  if ( !(unsigned int)XDES::IsActive(v383) )
    (*(void (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 624LL))(v383);
  if ( (*((_BYTE *)v383 + 536) & 4) != 0 )
  {
    v487 = (XDES *)(*(__int64 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 488LL))(v383);
    v488 = XDES::DoesXactGenVersion(v487);
  }
  else
  {
    if ( (*((_BYTE *)v383 + 592) & 0x52) == 2 && XVB::IsSnapshot(*((XVB **)v383 + 26)) )
    {
      v489 = *((_QWORD *)v383 + 26);
      if ( !*(_BYTE *)(v489 + 304) )
      {
        *(_BYTE *)(v489 + 304) = 1;
        if ( CommonGlobalState::m_PerfCountersEnabled )
          PerfmonManager::IncrementCounterValue((PerfmonManager *)&ResourceStr, 0x1Cu, 0x10u, 1, 0);
      }
    }
    v488 = (*((_BYTE *)v383 + 592) & 0x5A) != 0;
  }
  if ( v488 )
    goto LABEL_1287;
LABEL_1285:
  if ( v485 && *(int *)(v485 + 116) > 0 )
    goto LABEL_1287;
LABEL_1306:
  v494 = v622;
  if ( !(unsigned int)Record::HasVersioningInfo(v622) )
    goto LABEL_1400;
  if ( *(_WORD *)v494 )
    goto LABEL_1393;
  if ( *(_DWORD *)(v385 + 1) )
    goto LABEL_1145;
  *v385 = 0;
  v495 = *(unsigned int *)(v385 + 7);
  *(_DWORD *)(v385 + 9) = v495;
  v496 = *(char **)(v385 + 3);
  v497 = *v496;
  if ( (*v496 & 0x10) != 0 )
  {
    LODWORD(v495) = (((unsigned int)*(unsigned __int16 *)&v496[v495] + 7) >> 3) + v495 + 2;
    *(_DWORD *)(v385 + 9) = v495;
    v497 = *v496;
  }
  if ( (v497 & 0x20) != 0 )
  {
    v498 = (unsigned __int16 *)&v496[(unsigned int)v495];
    v499 = *v498;
    v385[13] = *v498;
    if ( !v499 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v500 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v500 )
        {
          v501 = *(_QWORD *)(v500 + 96);
          if ( v501 )
          {
            if ( *(_BYTE *)(v501 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
              else
                ex_raise(34, 68, 21, 1003);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 3);
      v499 = v385[13];
    }
    v502 = *(_DWORD *)(v385 + 9) + 2 + 2 * v499;
    *(_DWORD *)(v385 + 11) = v502;
    if ( v502 > 0x1F9E )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v503 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v503 )
        {
          v504 = *(_QWORD *)(v503 + 96);
          if ( v504 )
          {
            if ( *(_BYTE *)(v504 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
    }
    v505 = v498[(unsigned __int16)v385[13]] & 0x7FFF;
    *(_DWORD *)(v385 + 1) = v505;
    if ( *(_DWORD *)(v385 + 11) > v505 )
    {
      if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
      {
        v506 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                         + SystemThread_TlsOffset
                         + 8LL);
        if ( v506 )
        {
          v507 = *(_QWORD *)(v506 + 96);
          if ( v507 )
          {
            if ( *(_BYTE *)(v507 + 1177) )
            {
              if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
              else
                ex_raise(34, 68, 21, 1004);
            }
          }
        }
      }
      RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 4);
    }
    v508 = v385[13];
    while ( 1 )
    {
      v509 = v508;
      if ( (v498[v508] & 0x8000u) == 0 )
        goto LABEL_1363;
      v510 = *(_QWORD *)(v385 + 3) + *(unsigned int *)(v385 + 9);
      if ( (_DWORD)v509 == 1 )
      {
        v511 = *(_DWORD *)(v385 + 11);
        v512 = v511;
        v513 = *(_WORD *)(v510 + 2 * v509) & 0x7FFF;
      }
      else
      {
        v511 = *(_WORD *)(v510 + 2 * v509 - 2) & 0x7FFF;
        v512 = *(_DWORD *)(v385 + 11);
        v513 = *(_WORD *)(v510 + 2 * v509) & 0x7FFF;
        if ( v511 < v512 )
          goto LABEL_1351;
      }
      if ( v513 < v511 )
      {
LABEL_1351:
        RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 7);
        v512 = *(_DWORD *)(v385 + 11);
      }
      if ( v511 < v512 || v511 > *(_DWORD *)(v385 + 1) )
        goto LABEL_1145;
      v514 = *(_WORD *)(v511 + *(_QWORD *)(v385 + 3));
      if ( v514 == 5 )
      {
        *v385 |= 2u;
        --v385[13];
        v385[20] = v511;
        v515 = *(_QWORD *)(v385 + 3) + (unsigned __int16)v511;
        v516 = *(_WORD *)(v515 + 2);
        if ( (v516 & 0x4000) != 0 )
          v517 = v385[21] & 0xC7FF | v516 & 0x3800;
        else
          v517 = v385[21] & 0xC7FF;
        v385[21] = v517;
        v385[21] = v517 ^ (*(_WORD *)(v515 + 2) ^ v517) & 0x7FF;
        goto LABEL_1363;
      }
      if ( v514 >= 0x400u )
      {
        *v385 |= 1u;
        v508 = v385[13] - 1;
        v385[13] = v508;
        if ( v508 )
          continue;
      }
      goto LABEL_1363;
    }
  }
  *(_DWORD *)(v385 + 1) = v495;
  v385[13] = 0;
  *(_DWORD *)(v385 + 11) = *(_DWORD *)(v385 + 9);
LABEL_1363:
  if ( (**(_BYTE **)(v385 + 3) & 0x40) != 0 )
  {
    *((_DWORD *)v385 + 9) = *(_DWORD *)(v385 + 1);
    *(_DWORD *)(v385 + 1) += 14;
    v518 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)v385);
    v519 = HIWORD(*(_QWORD *)v518);
    v520 = 0;
    if ( (((__int16)v519 ^ ((unsigned int)(__int16)v519 >> 1)) & 0x2000) != 0 )
    {
      if ( (v519 & 0x4000) != 0 )
        LOWORD(v519) = v519 | 0x2000;
      else
        LOWORD(v519) = v519 & 0xDFFF;
    }
    if ( (_WORD)v519 == 0xFFFC )
      v520 = (unsigned __int16)WORD2(*(_QWORD *)v518) >> 5;
    *(_DWORD *)(v385 + 1) += v520;
  }
  else
  {
    *((_DWORD *)v385 + 9) = 0;
  }
  v521 = *(_QWORD *)(v385 + 14);
  v522 = *(_DWORD *)(v385 + 1);
  if ( v521 && v521 < *(_QWORD *)(v385 + 3) + (unsigned __int64)*(unsigned int *)(v385 + 1) )
  {
    if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
    {
      v523 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset
                       + 8LL);
      if ( v523 )
      {
        v524 = *(_QWORD *)(v523 + 96);
        if ( v524 )
        {
          if ( *(_BYTE *)(v524 + 1177) )
          {
            if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
              utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
            else
              ex_raise(34, 68, 21, 1018);
          }
        }
      }
    }
    RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 18);
    v522 = *(_DWORD *)(v385 + 1);
  }
  if ( (unsigned int)(v522 - 1) <= 0x3F3B )
    goto LABEL_1145;
  if ( !byte_10316E8D7 && (qword_10317B120 & 1) == 0 )
    goto LABEL_1144;
  v525 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset
                   + 8LL);
  if ( !v525 )
    goto LABEL_1144;
  v526 = *(_QWORD *)(v525 + 96);
  if ( !v526 || !*(_BYTE *)(v526 + 1177) )
    goto LABEL_1144;
  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
    goto LABEL_1143;
LABEL_1142:
  ex_raise(34, 68, 21, 1005);
LABEL_1144:
  RaiseInconsistencyError(*(_QWORD *)(v385 + 3), 5);
LABEL_1145:
  v419 = *(_DWORD *)(v385 + 1);
  if ( v419 >= 9 )
    goto LABEL_1400;
  v454 = **(_BYTE **)(v385 + 3) & 0xE;
  if ( !v454 )
  {
LABEL_1399:
    v419 = 9;
    goto LABEL_1400;
  }
  v455 = v454 == 12;
LABEL_1398:
  if ( v455 )
    goto LABEL_1399;
LABEL_1400:
  v528 = *v352;
  v529 = (*(unsigned __int8 *)(*((_QWORD *)v616 + 1) + 263LL) >> 6) & 1;
  v530 = *((_DWORD *)*v352 + 16) != 1;
  FirstDataIAM = HoBtAccess::AtomicGetFirstDataIAM(v616, v672);
  v562 = v529;
  v532 = v616;
  AllocParam::Init(v680, v383, FirstDataIAM, v616, v530, v562, v657, *(_WORD *)(v657 + 8), v528[2]);
  *((_BYTE *)v352 + 638) = 0;
  v533 = *((_QWORD *)v532 + 4);
  if ( *(_BYTE *)(v533 + 7391) )
  {
    v536 = *(_BYTE *)(v533 + 7388);
    if ( v536 )
      v534 = (*(_BYTE *)(*((_QWORD *)v532 + 1) + 265LL) & 0x40) != 0;
    else
      v534 = 0;
    if ( v536 )
      v535 = (*(_BYTE *)(*((_QWORD *)v532 + 1) + 265LL) & 0x40) != 0;
    else
      v535 = 0;
  }
  else
  {
    v534 = 0;
    v535 = 0;
  }
  FreeSpaceScan::Init(v673, v680, (*v352)[4], v419, v535, 2 * v534);
  v537 = 0;
  v667 = *(_QWORD *)((char *)v532 + 20);
  I8 = UnalignedAllocUnitId::GetI8((UnalignedAllocUnitId *)&v667);
  if ( RecoveryUnit::IsPVSRowsetId(*((RecoveryUnit **)v383 + 6), I8) )
  {
    v537 = 1;
    v604 = 1;
  }
  v539 = 0;
  while ( 1 )
  {
    FreeSpaceScan::GetNextPage((FreeSpaceScan *)v673, (struct AllocationPageId *)&v706);
    if ( !HIDWORD(v707) && !(_WORD)v708 )
      break;
    if ( *((_BYTE *)(*v352)[4] + 1) != 5
      && !(*(unsigned __int8 (__fastcall **)(HeapRowObject *))(*(_QWORD *)v383 + 40LL))(v383)
      && ((*((_DWORD *)v532 + 5) & 0xE0000000) != 0x80000000 || *((_WORD *)v532 + 12) > 0xFFu) )
    {
      v541 = *(_WORD *)(*((_QWORD *)v383 + 6) + 1720LL);
      v714 = 6;
      v713 = v541;
      v711 = HIDWORD(v707);
      v712 = (unsigned __int16)v708;
      v542 = (*v352)[4];
      if ( *((_BYTE *)v542 + 2)
        || (v543 = *((_QWORD *)v532 + 4), *(_BYTE *)(v543 + 7391))
        && *(_BYTE *)(v543 + 7388)
        && (*(_BYTE *)(*((_QWORD *)v532 + 1) + 265LL) & 0x40) != 0 )
      {
        DataLock = HeapFragment::LockResource(v352, &v711, 2, v542, v352 + 18, 0, 0, 1);
LABEL_1425:
        if ( DataLock < 0 )
          goto LABEL_1431;
        goto LABEL_1426;
      }
      if ( (unsigned int)*(_QWORD *)((char *)v532 + 20) != 8 || (unsigned __int16)WORD2(*(_QWORD *)((char *)v532 + 20)) )
      {
        v668 = *(_QWORD *)((char *)v532 + 20);
        LOBYTE(v564) = 0;
        *(_DWORD *)v563 = 1;
        LODWORD(v561) = 1;
        LOBYTE(v540) = 8;
        DataLock = GetDataLock(v352[1][1], &v711, v540, 1, v561, *(_QWORD *)v563, 0, v564, 0, 0, &v668, v352 + 18, 0);
        goto LABEL_1425;
      }
    }
LABEL_1426:
    if ( (unsigned int)HeapPageManager::GetPageWithIdInternal(**v352, &v706, 3, 2, v678) )
    {
      v545 = v687;
      v546 = &v683;
      v547 = 2;
      do
      {
        *v545 = *(_OWORD *)v546;
        v545[1] = *((_OWORD *)v546 + 1);
        v545[2] = *((_OWORD *)v546 + 2);
        v545[3] = *((_OWORD *)v546 + 3);
        v545[4] = *((_OWORD *)v546 + 4);
        v545[5] = *((_OWORD *)v546 + 5);
        v545[6] = *((_OWORD *)v546 + 6);
        v545 += 8;
        *(v545 - 1) = *((_OWORD *)v546 + 7);
        v546 += 128;
        --v547;
      }
      while ( v547 );
      HeapFragment::SetupFragmentForInsert(v352, v678, &v662, 0, 0, v687, 1);
    }
    else
    {
      v548 = (*v352)[4];
      if ( *((_BYTE *)v548 + 1) != 5 && *((_BYTE *)v548 + 2) )
      {
        if ( ((_BYTE)v352[20] & 2) != 0 && (unsigned int)LockReference::Release((LockReference *)(v352 + 21)) )
          (*v352)[6] = (HeapPageManager *)((char *)(*v352)[6] - 1);
        *((_BYTE *)v352 + 160) = 0;
        *((_DWORD *)v352 + 39) = 0;
        *((_DWORD *)v352 + 46) = 0;
        goto LABEL_1431;
      }
    }
    if ( *((_DWORD *)v352 + 48) == 4 )
    {
      *((_BYTE *)v352 + 638) = SegmentMetadataWrapper::GetMetadataVersion((SegmentMetadataWrapper *)v673);
LABEL_1440:
      if ( v537 && *((_DWORD *)v352 + 48) != 4 && (HIDWORD(v707) || (_WORD)v708) )
      {
        HoBtId::HoBtId((HoBtId *)v659);
        AllocationCachesId::Set((AllocationCachesId *)v659, (const struct AllocUnitId *)(*((_QWORD *)v532 + 1) + 960LL));
        v636 = HIDWORD(v707);
        v637 = v708;
        AllocUnitId::AllocUnitId((AllocUnitId *)v669, (const struct AllocUnitId *)&v636);
        v609[0] = 4;
        v549 = operator|(4, 1);
        v550 = operator|(v549, 2);
        v551 = operator|(v550, 32);
        Worker::TaskAutoOnFlags::TaskAutoOnFlags(v679, v551);
        ChangeFreeSpaceValue(
          *((struct RecoveryUnit **)v383 + 6),
          (const struct AllocationCachesId *)v659,
          (const struct AlignedPageId *)v669,
          v609,
          1u,
          1,
          v383);
        Worker::TaskAutoOnFlags::~TaskAutoOnFlags((Worker::TaskAutoOnFlags *)v679);
        v373 = (_OWORD *)((char *)v372 + 1328);
        v377 = v608;
        v358 = v620;
        v362 = v619;
        goto LABEL_1446;
      }
      break;
    }
LABEL_1431:
    if ( ++v539 >= v604 )
      goto LABEL_1440;
  }
  v362 = v619;
  v358 = v620;
  v377 = v608;
  v373 = (_OWORD *)((char *)v372 + 1328);
LABEL_1446:
  if ( *((_DWORD *)v352 + 48) != 4 )
  {
    v552 = v688;
    v553 = &v683;
    v554 = 2;
    do
    {
      *v552 = *(_OWORD *)v553;
      v552[1] = *((_OWORD *)v553 + 1);
      v552[2] = *((_OWORD *)v553 + 2);
      v552[3] = *((_OWORD *)v553 + 3);
      v552[4] = *((_OWORD *)v553 + 4);
      v552[5] = *((_OWORD *)v553 + 5);
      v552[6] = *((_OWORD *)v553 + 6);
      v552 += 8;
      *(v552 - 1) = *((_OWORD *)v553 + 7);
      v553 += 128;
      --v554;
    }
    while ( v554 );
    HeapFragment::AllocateNewPageToConstructFragment(v352, &v662, 0, 0, v688);
  }
  if ( v377 )
  {
    v555 = v352[5];
    if ( v555 )
    {
      v556 = *v555;
    }
    else if ( *((_DWORD *)v352 + 48) == 2
           || (HeapFragment::ReAcquirePageAccessLong(v352, 1), *((_DWORD *)v352 + 48) == 2) )
    {
      v556 = 0;
    }
    else
    {
      v556 = *v352[5];
    }
    *((_DWORD *)v377 + 2) = *((_DWORD *)v556 + 8);
    *((_DWORD *)v377 + 3) = *((unsigned __int16 *)v556 + 18);
    *(_QWORD *)v377 = 0;
    *((_DWORD *)v377 + 7) = 1;
    *((_QWORD *)v377 + 2) = 0;
    *((_WORD *)v377 + 12) = 0;
  }
LABEL_1458:
  v557 = v689;
  v558 = 2;
  do
  {
    *v557 = *v373;
    v557[1] = v373[1];
    v557[2] = v373[2];
    v557[3] = v373[3];
    v557[4] = v373[4];
    v557[5] = v373[5];
    v557[6] = v373[6];
    v557 += 8;
    *(v557 - 1) = v373[7];
    v373 += 8;
    --v558;
  }
  while ( v558 );
  HeapFragment::Update(v352, &v662, v689, 1, 0);
  *((_DWORD *)v358 + 397) |= 1u;
  if ( v606 )
  {
    v559 = *(_QWORD *)(*((_QWORD *)v362 + 5) + 24LL);
    if ( ++*(_DWORD *)(v559 + 12) >= *(_DWORD *)(v559 + 8) )
    {
      *(_DWORD *)(v559 + 8) = 0;
      *(_QWORD *)v559 = 0;
    }
    if ( v600 )
    {
      *((_DWORD *)v605 + 338) = v601;
      *((_DWORD *)v372 + 339) = v585;
    }
  }
  v560 = v605;
  HeapRowObject::GetRidAndPageVersionId(v605, v670, 0, 1);
  *v671 = (unsigned __int64)v560;
}

```

## disassembly

```asm
0x10146da50  push    rbp
0x10146da52  push    rsi
0x10146da53  push    rdi
0x10146da54  push    r12
0x10146da56  push    r13
0x10146da58  push    r14
0x10146da5a  push    r15
0x10146da5c  mov     eax, 2A90h
0x10146da61  call    _alloca_probe
0x10146da66  sub     rsp, rax
0x10146da69  lea     rbp, [rsp+70h]
0x10146da6e  mov     [rbp+2A50h+var_27E0], 0FFFFFFFFFFFFFFFEh
0x10146da79  mov     [rbp+2A50h+arg_8], rbx
0x10146da80  mov     rax, cs:__security_cookie
0x10146da87  xor     rax, rbp
0x10146da8a  mov     [rbp+2A50h+var_40], rax
0x10146da91  mov     [rbp+2A50h+var_2838], r9
0x10146da98  mov     [rbp+2A50h+var_2960], r8
0x10146da9f  mov     rdi, rdx
0x10146daa2  mov     rbx, rcx
0x10146daa5  mov     [rbp+2A50h+var_2910], rcx
0x10146daac  mov     [rbp+2A50h+var_2968], rcx
0x10146dab3  mov     rdx, [rbp+2A50h+arg_20]
0x10146daba  mov     [rbp+2A50h+var_2830], rdx
0x10146dac1  mov     eax, 0FFFFFFFFh
0x10146dac6  mov     [rbp+2A50h+var_2A28], ax
0x10146daca  xor     r15d, r15d
0x10146dacd  mov     [rbp+2A50h+var_2A20], r15
0x10146dad1  mov     [rbp+2A50h+var_2A24], r15d
0x10146dad5  mov     [rbp+2A50h+var_2A0A], r15
0x10146dad9  mov     [rbp+2A50h+var_2A00], r15
0x10146dadd  mov     [rbp+2A50h+var_2A18], r15
0x10146dae1  mov     [rbp+2A50h+var_21F6], r15w
0x10146dae9  movups  xmm0, cs:?INVALID_HPAGE@@3VHPageHandle@@B; HPageHandle const INVALID_HPAGE
0x10146daf0  movups  [rbp+2A50h+var_28A0], xmm0
0x10146daf7  mov     [rbp+2A50h+var_29F0], eax
0x10146dafa  mov     r12d, r15d
0x10146dafd  mov     [rbp+2A50h+var_2A40], 1
0x10146db04  mov     rax, [rcx+2E0h]
0x10146db0b  mov     rcx, [rax+8]
0x10146db0f  mov     rax, [rcx+30h]
0x10146db13  mov     [rbp+2A50h+var_28B8], rax
0x10146db1a  mov     [rdx], r15
0x10146db1d  lea     rax, [rbx+0AE0h]
0x10146db24  mov     rcx, [rax+8]
0x10146db28  cmp     rcx, rax
0x10146db2b  jz      short loc_10146DB60
0x10146db2d  lea     rax, [rcx-10h]
0x10146db31  mov     r13d, r15d
0x10146db34  test    rcx, rcx
0x10146db37  cmovnz  r13, rax
0x10146db3b  mov     [rbp+2A50h+var_29B8], r13
0x10146db42  test    r13, r13
0x10146db45  jz      short loc_10146DB60
0x10146db47  mov     rcx, [r13+18h]
0x10146db4b  mov     rax, [r13+10h]
0x10146db4f  mov     [rax+8], rcx
0x10146db53  mov     [rcx], rax
0x10146db56  mov     [r13+18h], r15
0x10146db5a  mov     [r13+10h], r15
0x10146db5e  jmp     short loc_10146DBC0
0x10146db60  mov     [rbp+2A50h+var_29CC], 75Fh
0x10146db6a  mov     byte ptr [rsp+2AC0h+var_2AA0], 5
0x10146db6f  mov     r9d, 75Fh
0x10146db75  lea     r8, aSqlNtdbmsStore_225; "Sql\\Ntdbms\\storeng\\dfs\\access\\Heap"...
0x10146db7c  mov     rdx, [rbx+1F0h]
0x10146db83  mov     ecx, 638h
0x10146db88  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10146db8e  mov     [rbp+2A50h+var_2990], rax
0x10146db95  test    rax, rax
0x10146db98  jz      short loc_10146DBA7
0x10146db9a  mov     rcx, rax; this
0x10146db9d  call    ??0HeapRowObject@@QEAA@XZ; HeapRowObject::HeapRowObject(void)
0x10146dba2  mov     r13, rax
0x10146dba5  jmp     short loc_10146DBAA
0x10146dba7  mov     r13, r15
0x10146dbaa  mov     [rbp+2A50h+var_29B8], r13
0x10146dbb1  mov     rdx, [rbx+2D8h]; struct HeapParam *
0x10146dbb8  mov     rcx, r13; this
0x10146dbbb  call    ?Init@HeapRowObject@@QEAAXPEAVHeapParam@@@Z; HeapRowObject::Init(HeapParam *)
0x10146dbc0  lea     rdx, [r13+10h]
0x10146dbc4  lea     rcx, [rbx+0AF0h]
0x10146dbcb  mov     rax, [rcx+8]
0x10146dbcf  mov     [rdx+8], rax
0x10146dbd3  mov     rax, [rcx+8]
0x10146dbd7  mov     [rax], rdx
0x10146dbda  mov     [rcx+8], rdx
0x10146dbde  mov     [rdx], rcx
0x10146dbe1  mov     rax, [rbx+108h]
0x10146dbe8  mov     r8d, [rax]
0x10146dbeb  shr     r8d, 1Bh
0x10146dbef  and     r8d, 1; int
0x10146dbf3  mov     rbx, [rbx+2E0h]
0x10146dbfa  mov     esi, 2
0x10146dbff  mov     r14d, 10h
0x10146dc05  mov     [rbp+2A50h+var_29CC], r14d
0x10146dc0c  cmp     dword ptr [r13+630h], 1
0x10146dc14  jnz     loc_10146DCDC
0x10146dc1a  mov     [r13+28h], rbx
0x10146dc1e  mov     [r13+38h], rbx
0x10146dc22  mov     rax, [r13+30h]
0x10146dc26  mov     rcx, [rax+48h]
0x10146dc2a  add     rcx, 28h ; '('
0x10146dc2e  mov     [r13+100h], rcx
0x10146dc35  mov     [r13+0F0h], esi
0x10146dc3c  mov     rax, [r13+20h]
0x10146dc40  mov     rcx, [rax+48h]
0x10146dc44  cmp     dword ptr [rcx+18h], 1
0x10146dc48  jz      loc_10146DCD5
0x10146dc4e  lea     rcx, [r13+538h]; this
0x10146dc55  mov     rdx, [rbx]; struct HoBtAccess *
0x10146dc58  call    ?Init@HoBtVersioningStatus@@QEAAXPEAVHoBtAccess@@H@Z; HoBtVersioningStatus::Init(HoBtAccess *,int)
0x10146dc5d  mov     r8, [r13+20h]
0x10146dc61  mov     ecx, r15d
0x10146dc64  mov     eax, 8
0x10146dc69  cmp     dword ptr [r8+40h], 3
0x10146dc6e  cmovz   ecx, eax
0x10146dc71  movzx   eax, byte ptr [r13+530h]
0x10146dc79  and     al, 0F7h
0x10146dc7b  or      cl, al
0x10146dc7d  mov     [r13+530h], cl
0x10146dc84  mov     edx, r15d
0x10146dc87  cmp     dword ptr [r8+40h], 4
0x10146dc8c  cmovz   edx, r14d
0x10146dc90  and     cl, 0EFh
0x10146dc93  or      dl, cl
0x10146dc95  mov     [r13+530h], dl
0x10146dc9c  mov     rax, [r8+10h]
0x10146dca0  mov     ecx, [rax+50h]
0x10146dca3  shl     ecx, 1Fh
0x10146dca6  sar     ecx, 1Fh
0x10146dca9  shl     cl, 5
0x10146dcac  xor     cl, dl
0x10146dcae  and     cl, 20h
0x10146dcb1  xor     cl, dl
0x10146dcb3  mov     [r13+530h], cl
0x10146dcba  mov     rax, [r8+48h]
0x10146dcbe  mov     ecx, [rax+188h]
0x10146dcc4  mov     [r13+548h], ecx
0x10146dccb  mov     eax, [rbx+20h]
0x10146dcce  mov     [r13+54Ch], eax
0x10146dcd5  mov     [r13+630h], esi
0x10146dcdc  mov     [rbp+2A50h+var_29C8], r13
0x10146dce3  mov     eax, [rdi]
0x10146dce5  mov     [rbp+2A50h+var_2208], eax
0x10146dceb  movzx   eax, word ptr [rdi+4]
0x10146dcef  mov     [rbp+2A50h+var_2204], ax
0x10146dcf6  mov     [rbp+2A50h+var_2202], r15w
0x10146dcfe  mov     [rbp+2A50h+var_2210], r15
0x10146dd05  mov     [rbp+2A50h+var_21F4], r15d
0x10146dd0c  mov     [rbp+2A50h+var_2200], r15
0x10146dd13  mov     [rbp+2A50h+var_21F8], r15w
0x10146dd1b  mov     rax, [rbp+2A50h+var_2910]
0x10146dd22  mov     rax, [rax+2D8h]
0x10146dd29  lea     rcx, [rbp+2A50h+var_28A0]
0x10146dd30  mov     [rsp+2AC0h+var_2AA0], rcx
0x10146dd35  mov     r9d, esi
0x10146dd38  mov     r8d, 3
0x10146dd3e  lea     rdx, [rbp+2A50h+var_2210]
0x10146dd45  mov     rcx, [rax]
0x10146dd48  call    ?GetPageWithIdInternal@HeapPageManager@@AEAAHPEAVAllocationPageId@@W4AccessMode@@IAEAVHPageHandle@@@Z; HeapPageManager::GetPageWithIdInternal(AllocationPageId *,AccessMode,uint,HPageHandle &)
0x10146dd4d  test    eax, eax
0x10146dd4f  jz      loc_10146E03C
0x10146dd55  and     dword ptr [r13+634h], 0FFFFFFFEh
0x10146dd5d  lea     r14, [r13+30h]
0x10146dd61  mov     [rbp+2A50h+var_2222], 1
0x10146dd68  mov     rax, [r14]
0x10146dd6b  mov     rcx, [rax]; this
0x10146dd6e  mov     rax, [r14+8]
0x10146dd72  mov     rsi, [rax+8]
0x10146dd76  movups  xmm0, [rbp+2A50h+var_28A0]
0x10146dd7d  movups  xmmword ptr [r14+10h], xmm0
0x10146dd82  lea     r8, [r14+28h]; struct HeapPageRef *
0x10146dd86  lea     rdx, [r14+10h]; struct HPageHandle *
0x10146dd8a  call    ?GetPageRef@HeapPageManager@@AEAAXAEBVHPageHandle@@AEAVHeapPageRef@@@Z; HeapPageManager::GetPageRef(HPageHandle const &,HeapPageRef &)
0x10146dd8f  mov     rax, [r14+28h]
0x10146dd93  mov     rcx, [rax]
0x10146dd96  mov     [r14+258h], rcx
0x10146dd9d  mov     dword ptr [r14+58h], 3
0x10146dda5  mov     [r14+26Ch], r15d
0x10146ddac  mov     rax, [r14]
0x10146ddaf  mov     r15, [rax+18h]
0x10146ddb3  mov     rax, [r14+0D0h]
0x10146ddba  mov     ecx, [rax+10h]
0x10146ddbd  test    cl, 1
0x10146ddc0  jz      loc_10146DE77
0x10146ddc6  test    cl, 40h
0x10146ddc9  jnz     loc_10146DE77
0x10146ddcf  mov     r8, [rsi+30h]
0x10146ddd3  cmp     byte ptr [r8+1CD2h], 0
0x10146dddb  jz      loc_10146DE77
0x10146dde1  cmp     byte ptr [r8+2050h], 0
0x10146dde9  jnz     loc_10146DE77
0x10146ddef  mov     rax, [r14+10h]
0x10146ddf3  mov     ecx, [rax+90h]
0x10146ddf9  movzx   edx, word ptr [rax+94h]
0x10146de00  movzx   eax, word ptr [r8+6B8h]
0x10146de08  mov     [rbp+2A50h+var_2222], 6
0x10146de0f  mov     [rbp+2A50h+var_2224], ax
0x10146de16  xor     eax, eax
0x10146de18  mov     [rbp+2A50h+var_222C], rax
0x10146de1f  mov     [rbp+2A50h+var_2230], ecx
0x10146de25  mov     word ptr [rbp+2A50h+var_222C], dx
0x10146de2c  mov     rcx, [r14+8]
0x10146de30  mov     r9b, 1
0x10146de33  lea     r8, [rbp+2A50h+var_2230]
0x10146de3a  mov     dl, 6
0x10146de3c  mov     rcx, [rcx+8]
0x10146de40  call    ?GetInstantLockInRecoveryNoWait@VersionMgr@@SA_NPEAVXDES@@W4LCK_MODE@@AEAVLockRes@@_N@Z; VersionMgr::GetInstantLockInRecoveryNoWait(XDES *,LCK_MODE,LockRes &,bool)
0x10146de45  test    al, al
0x10146de47  jnz     short loc_10146DE77
0x10146de49  mov     rcx, r14; this
0x10146de4c  call    ?ReleasePageAccess@HeapFragment@@QEAAXXZ; HeapFragment::ReleasePageAccess(void)
0x10146de51  mov     rax, [r14]
0x10146de54  mov     rcx, [rax+18h]
0x10146de58  mov     rax, [r14+8]
0x10146de5c  mov     byte ptr [rsp+2AC0h+var_2AA0], 1
0x10146de61  lea     r9, [rbp+2A50h+var_2230]
0x10146de68  mov     r8d, [rcx+18h]
0x10146de6c  mov     dl, 6
0x10146de6e  mov     rcx, [rax+8]
0x10146de72  call    ?GetInstantLockInRecoveryWithWait@VersionMgr@@SAXPEAVXDES@@W4LCK_MODE@@KAEAVLockRes@@_N@Z; VersionMgr::GetInstantLockInRecoveryWithWait(XDES *,LCK_MODE,ulong,LockRes &,bool)
0x10146de77  cmp     byte ptr [r15+2], 0
0x10146de7c  jz      loc_10146E078
0x10146de82  mov     rax, [rsi]
0x10146de85  mov     rcx, rsi
0x10146de88  call    qword ptr [rax+28h]
0x10146de8b  test    al, al
0x10146de8d  jnz     loc_10146E078
0x10146de93  mov     rax, [r14+10h]
0x10146de97  mov     edx, [rax+90h]
0x10146de9d  movzx   r8d, word ptr [rax+94h]
0x10146dea5  mov     rax, [r14+8]
0x10146dea9  mov     rcx, [rax+8]
0x10146dead  mov     rax, [rcx+30h]
0x10146deb1  movzx   ecx, word ptr [rax+6B8h]
0x10146deb8  mov     [rbp+2A50h+var_2222], 6
0x10146debf  mov     [rbp+2A50h+var_2224], cx
0x10146dec6  xor     eax, eax
0x10146dec8  mov     [rbp+2A50h+var_222C], rax
0x10146decf  mov     [rbp+2A50h+var_2230], edx
0x10146ded5  mov     word ptr [rbp+2A50h+var_222C], r8w
0x10146dedd  lea     rax, [r14+90h]
0x10146dee4  mov     ecx, 1
0x10146dee9  mov     dword ptr [rsp+2AC0h+var_2A88], ecx
0x10146deed  mov     [rsp+2AC0h+var_2A90], ecx
0x10146def1  mov     [rsp+2AC0h+var_2A98], ecx
0x10146def5  mov     [rsp+2AC0h+var_2AA0], rax
0x10146defa  mov     r9, r15
0x10146defd  mov     esi, 2
0x10146df02  mov     r8d, esi
0x10146df05  lea     rdx, [rbp+2A50h+var_2230]
0x10146df0c  mov     rcx, r14
0x10146df0f  call    ?LockResource@HeapFragment@@AEAA?AW4LCK_RESULT@@AEAVLockRes@@W4Granularity@@PEBVLckInfo@@AEAVHeapFragmentLockInfo@1@W4SkipRowLockOption@@W4LockWaitOption@@W4InstantLockOption@@@Z; HeapFragment::LockResource(LockRes &,Granularity,LckInfo const *,HeapFragment::HeapFragmentLockInfo &,SkipRowLockOption,LockWaitOption,InstantLockOption)
0x10146df14  test    eax, eax
0x10146df16  jns     loc_10146E078
0x10146df1c  mov     rax, qword ptr cs:?INVALID_HPAGE@@3VHPageHandle@@B; HPageHandle const INVALID_HPAGE
0x10146df23  cmp     [r14+10h], rax
0x10146df27  jnz     short loc_10146DF3A
0x10146df29  mov     rax, qword ptr cs:?INVALID_HPAGE@@3VHPageHandle@@B+8; HPageHandle const INVALID_HPAGE
0x10146df30  cmp     [r14+18h], rax
0x10146df34  jz      loc_10146E034
0x10146df3a  lfence
0x10146df3d  test    [r14+70h], sil
0x10146df41  jz      short loc_10146DF5D
0x10146df43  lfence
0x10146df46  lea     rcx, [r14+78h]; this
0x10146df4a  call    ?Release@LockReference@@QEAAHXZ; LockReference::Release(void)
0x10146df4f  test    eax, eax
0x10146df51  jz      short loc_10146DF5D
0x10146df53  lfence
0x10146df56  mov     rax, [r14]
0x10146df59  dec     qword ptr [rax+30h]
0x10146df5d  mov     byte ptr [r14+70h], 0
0x10146df62  xor     r15d, r15d
0x10146df65  mov     [r14+6Ch], r15d
0x10146df69  mov     [r14+88h], r15d
0x10146df70  test    [r14+0A0h], sil
0x10146df77  jz      short loc_10146DF96
0x10146df79  lfence
0x10146df7c  lea     rcx, [r14+0A8h]; this
0x10146df83  call    ?Release@LockReference@@QEAAHXZ; LockReference::Release(void)
0x10146df88  test    eax, eax
0x10146df8a  jz      short loc_10146DF96
0x10146df8c  lfence
0x10146df8f  mov     rax, [r14]
0x10146df92  dec     qword ptr [rax+30h]
0x10146df96  mov     [r14+0A0h], r15b
0x10146df9d  mov     [r14+9Ch], r15d
0x10146dfa4  mov     [r14+0B8h], r15d
0x10146dfab  cmp     [r14+28h], r15
0x10146dfaf  jz      short loc_10146DFCF
0x10146dfb1  lfence
0x10146dfb4  mov     rax, [r14+10h]
0x10146dfb8  cmp     [r14+28h], r15
0x10146dfbc  jz      short loc_10146DFCB
0x10146dfbe  mov     [r14+36h], r15b
0x10146dfc2  mov     [r14+28h], r15
0x10146dfc6  mov     [r14+34h], r15w
0x10146dfcb  mov     [rax+48h], r15d
  ... truncated ...
```
