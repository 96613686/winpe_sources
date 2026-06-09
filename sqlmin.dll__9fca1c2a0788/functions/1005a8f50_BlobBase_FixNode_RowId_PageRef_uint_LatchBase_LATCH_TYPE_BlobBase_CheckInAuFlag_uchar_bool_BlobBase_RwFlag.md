# BlobBase::FixNode(RowId,PageRef &,uint &,LatchBase::LATCH_TYPE,BlobBase::CheckInAuFlag,uchar *,bool,BlobBase::RwFlag)

- ea: `0x1005a8f50`
- end: `0x1005a97e6`
- name: `?FixNode@BlobBase@@IEAAPEAUBlobNode@@URowId@@AEAVPageRef@@AEAIW4LATCH_TYPE@LatchBase@@W4CheckInAuFlag@1@PEAE_NW4RwFlag@1@@Z`
- size: `2198`
- prototype: ``
- caller_count: `4`
- callee_count: `58`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10058f4a0`
- `0x1005a8c00`
- `0x1005a9c00`
- `0x1016b2420`

## callees

- `0x100401010`
- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100403030`
- `0x10040d950`
- `0x10040da40`
- `0x10040eca0`
- `0x10040fc00`
- `0x100415470`
- `0x10043ba50`
- `0x100441e00`
- `0x100441e40`
- `0x100450ee0`
- `0x1004729d0`
- `0x100472a40`
- `0x10047ffb0`
- `0x100480030`
- `0x10048c200`
- `0x10049a0c0`
- `0x10049ff80`
- `0x1004bf030`
- `0x100553e20`
- `0x1005a87b0`
- `0x1005a8f50`
- `0x1005aa280`
- `0x1005ad150`
- `0x1005d9f70`
- `0x10069f4f0`
- `0x101200050`
- `0x10121e710`
- `0x1012c9010`
- `0x10168ef10`
- `0x1016abf50`
- `0x1016bad70`
- `0x1016c9e80`
- `0x1018c9d70`
- `0x101907610`
- `0x101909810`
- `0x101cb13d0`
- `0x101ced0e0`
- `0x101d0fb90`
- `0x101d11730`
- `0x101d19a30`
- `0x101d1a8c0`
- `0x101d66df0`
- `0x101d7f0a0`
- `0x101d7f170`
- `0x101d94000`
- `0x101d97510`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1016a852d`
- `KERNEL32!HeapAlloc` at `0x1016a8c61`
- `KERNEL32!HeapAlloc` at `0x1016a852d`
- `KERNEL32!HeapAlloc` at `0x1016a8c61`
- `KERNEL32!GetProcessHeap` at `0x1016a851c`
- `KERNEL32!GetProcessHeap` at `0x1016a8c50`
- `KERNEL32!GetProcessHeap` at `0x1016a851c`
- `KERNEL32!GetProcessHeap` at `0x1016a8c50`
- `KERNEL32!VirtualProtect` at `0x1016a3cdb`
- `KERNEL32!VirtualProtect` at `0x1016a3e27`
- `KERNEL32!VirtualProtect` at `0x1016a42ae`
- `KERNEL32!VirtualProtect` at `0x1016a3cdb`
- `KERNEL32!VirtualProtect` at `0x1016a3e27`
- `KERNEL32!VirtualProtect` at `0x1016a42ae`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016a8515`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016a8c3c`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016a8515`
- `sqldk!??0CDStream@@QEAA@XZ` at `0x1016a8c3c`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016a85b1`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016a8ccd`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016a85b1`
- `sqldk!??1CDStream@@QEAA@XZ` at `0x1016a8ccd`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016a8574`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016a8c98`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016a8574`
- `sqldk!?AddDevice@CDStream@@QEAAHPEAVCDumpStream@@@Z` at `0x1016a8c98`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1016a46c5`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1005a91c4`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1016a7ebf`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x1016a7925`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016a7e19`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1016a7e19`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4cce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4d6b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4f80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4feb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5379`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a53a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a53cf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5616`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5f56`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5ff3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a62bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6371`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a65d0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6b51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6bee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a718e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7264`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a729c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a72c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a72ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a91ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a91d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a9200`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a969e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a96c7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4cce`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4d6b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4f80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a4feb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5379`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a53a4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a53cf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5555`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5616`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5f56`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a5ff3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a62bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6371`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a65d0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6b51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a6bee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a718e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7264`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a729c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a72c5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a72ee`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7671`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a7eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a91ae`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a91d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a9200`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a969e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1016a96c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a3b7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a50b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a5178`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a5244`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a550e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a55cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6d9a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6e5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6f2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a74bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a756a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a7a32`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a801e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a80e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a81a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a8a2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a8d2c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a93cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a9478`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a961c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a3b7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a50b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a5178`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a5244`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a550e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a55cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6d9a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6e5c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a6f2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a74bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a756a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a7a32`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a801e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a80e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a81a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a8a2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a8d2c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a93cf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a9478`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1016a961c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a3c13`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a83ec`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a84f8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a866f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8b82`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8c26`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8de7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a3c13`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a83ec`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a84f8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a866f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8b82`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8c26`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016a8de7`
- `sqldk!SystemThread_TlsIndex` at `0x1005a914c`
- `sqldk!SystemThread_TlsIndex` at `0x1005a91ea`
- `sqldk!SystemThread_TlsIndex` at `0x1005a9221`
- `sqldk!SystemThread_TlsIndex` at `0x1016a403e`
- `sqldk!SystemThread_TlsIndex` at `0x1016a407e`
- `sqldk!SystemThread_TlsIndex` at `0x1016a5058`
- `sqldk!SystemThread_TlsIndex` at `0x1016a511b`
- `sqldk!SystemThread_TlsIndex` at `0x1016a51e7`
- `sqldk!SystemThread_TlsIndex` at `0x1016a54b9`
- `sqldk!SystemThread_TlsIndex` at `0x1016a557a`
- `sqldk!SystemThread_TlsIndex` at `0x1016a6d3d`
- `sqldk!SystemThread_TlsIndex` at `0x1016a6dff`
- `sqldk!SystemThread_TlsIndex` at `0x1016a6ece`
- `sqldk!SystemThread_TlsIndex` at `0x1016a745e`
- `sqldk!SystemThread_TlsIndex` at `0x1016a750d`
- `sqldk!SystemThread_TlsIndex` at `0x1016a78bb`
- `sqldk!SystemThread_TlsIndex` at `0x1016a7de1`
- `sqldk!SystemThread_TlsIndex` at `0x1016a7fc0`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8084`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8147`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8395`
- `sqldk!SystemThread_TlsIndex` at `0x1016a84a0`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8618`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8b53`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8bef`
- `sqldk!SystemThread_TlsIndex` at `0x1016a8db0`
- `sqldk!SystemThread_TlsIndex` at `0x1016a9371`
- `sqldk!SystemThread_TlsIndex` at `0x1016a941a`
- `sqldk!SystemThread_TlsOffset` at `0x1005a9155`
- `sqldk!SystemThread_TlsOffset` at `0x1005a91f3`
- `sqldk!SystemThread_TlsOffset` at `0x1005a922a`
- `sqldk!SystemThread_TlsOffset` at `0x1016a4047`
- `sqldk!SystemThread_TlsOffset` at `0x1016a4087`
- `sqldk!SystemThread_TlsOffset` at `0x1016a5061`
- `sqldk!SystemThread_TlsOffset` at `0x1016a5124`
- `sqldk!SystemThread_TlsOffset` at `0x1016a51f0`
- `sqldk!SystemThread_TlsOffset` at `0x1016a54c2`
- `sqldk!SystemThread_TlsOffset` at `0x1016a5583`
- `sqldk!SystemThread_TlsOffset` at `0x1016a6d46`
- `sqldk!SystemThread_TlsOffset` at `0x1016a6e08`
- `sqldk!SystemThread_TlsOffset` at `0x1016a6ed7`
- `sqldk!SystemThread_TlsOffset` at `0x1016a7467`
- `sqldk!SystemThread_TlsOffset` at `0x1016a7516`
- `sqldk!SystemThread_TlsOffset` at `0x1016a78c4`
- `sqldk!SystemThread_TlsOffset` at `0x1016a7dea`
- `sqldk!SystemThread_TlsOffset` at `0x1016a7fc9`
- `sqldk!SystemThread_TlsOffset` at `0x1016a808d`
- `sqldk!SystemThread_TlsOffset` at `0x1016a8150`
- `sqldk!SystemThread_TlsOffset` at `0x1016a839e`
- `sqldk!SystemThread_TlsOffset` at `0x1016a84a9`
- `sqldk!SystemThread_TlsOffset` at `0x1016a8621`
- `sqldk!SystemThread_TlsOffset` at `0x1016a8b5c`
- `sqldk!SystemThread_TlsOffset` at `0x1016a8bf8`
- `sqldk!SystemThread_TlsOffset` at `0x1016a8db9`
- `sqldk!SystemThread_TlsOffset` at `0x1016a937a`
- `sqldk!SystemThread_TlsOffset` at `0x1016a9423`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
unsigned __int8 *__fastcall BlobBase::FixNode(
        __int64 a1,
        struct PageId *a2,
        PageRef *a3,
        unsigned int *a4,
        int a5,
        int a6,
        unsigned __int8 *a7,
        char a8,
        int a9)
{
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int16 v11; // ax
  __int64 *v12; // rax
  int v13; // edx
  __int16 v14; // r8
  __int64 v15; // rcx
  int *v16; // rcx
  int *v17; // rcx
  __int16 v18; // ax
  struct XDES *v19; // rcx
  char v20; // al
  struct XDES **v21; // rbx
  int v22; // edi
  BOOL v23; // r13d
  struct XDES **v24; // r12
  __int64 v25; // rax
  struct VersionScanParams *v26; // rcx
  __int64 v27; // r15
  struct XDES *v28; // rsi
  __int64 v29; // rbx
  _QWORD *v30; // r8
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r14
  __int64 v35; // rdx
  struct CSessionTraceFlags *v36; // rcx
  __int64 v37; // rax
  struct SEInternalTLS *SETLSFromTlsMaybeNull; // r12
  _QWORD *v39; // r15
  PageRef *v40; // rbx
  __int64 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  struct XDES *v45; // rsi
  __int64 v46; // r12
  struct XDES **v47; // r11
  struct XDES *v48; // rdi
  int v49; // r8d
  struct PageId *v50; // rsi
  __int64 v51; // r10
  int v52; // r9d
  __int64 v53; // rax
  int *v54; // rcx
  int *v55; // rax
  int v56; // ecx
  __int16 v57; // ax
  __int64 v58; // rdx
  __int16 v59; // cx
  __int64 v60; // r15
  __int128 *v61; // rdi
  unsigned int v62; // ebx
  unsigned __int8 *v63; // r9
  unsigned int v64; // r8d
  __int64 v65; // rdx
  struct XDES *v66; // r14
  char v67; // al
  struct RecVersioningInfo *VersioningInfo; // rax
  int v69; // r9d
  struct VersionScanParams *v70; // rdi
  struct XDES **v71; // r15
  char LockMode; // al
  __int64 v73; // rdx
  __int64 v74; // r8
  struct XDES *v75; // rcx
  _BYTE *v76; // rbx
  PageRef *v77; // rsi
  char v78; // al
  struct XDES **v79; // r15
  __int64 v80; // rdx
  __int64 v81; // rcx
  struct XDES *v82; // rdi
  struct VersionScanParams *v83; // r15
  int v84; // ebx
  char v85; // si
  char v86; // bl
  __int16 *v87; // rsi
  struct XDES **v88; // r12
  char v89; // cl
  __int16 v91; // cx
  __int64 v92; // rax
  bool v93; // zf
  int v94; // edi
  __int64 *v95; // rbx
  __int64 v96; // rcx
  int v97; // edi
  __int64 v98; // rbx
  __int64 v99; // rcx
  int v100; // ecx
  __int64 v101; // r11
  char v102; // al
  int v103; // eax
  unsigned int v104; // ecx
  __int64 v105; // rdx
  __int64 v106; // rdx
  __int64 v107; // r11
  char v108; // cl
  __int16 v109; // si
  __int64 v110; // xmm1_8
  int v111; // edi
  __int64 *v112; // rbx
  __int64 v113; // rcx
  int v114; // eax
  unsigned int v115; // ecx
  LSN v116; // xmm0_8
  unsigned __int16 v117; // bx
  __int64 v118; // r11
  char v119; // al
  unsigned __int16 v120; // r11
  __int64 v121; // rax
  __int64 v122; // r10
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  int *v126; // rdx
  __int64 v127; // rcx
  int v128; // ecx
  int **v129; // rax
  __int16 v130; // ax
  __int16 v131; // r8
  __int64 v132; // rcx
  int *v133; // rcx
  __int64 v134; // rax
  int *v135; // rcx
  unsigned __int8 *v136; // r14
  __int16 v137; // r11
  char v138; // al
  __int16 v139; // dx
  unsigned __int64 v140; // rcx
  __int64 v141; // rcx
  __int64 v142; // rsi
  unsigned __int8 *v143; // r8
  unsigned __int8 v144; // dl
  __int16 v145; // dx
  __int16 v146; // cx
  unsigned int v147; // eax
  unsigned __int8 *v148; // rax
  __int16 v149; // cx
  PageComprInfoCache *v150; // rcx
  unsigned __int16 v151; // ax
  int v152; // eax
  int v153; // ebx
  unsigned __int16 v154; // cx
  int v155; // eax
  unsigned __int16 *v156; // rsi
  unsigned __int16 v157; // r9
  __int64 v158; // rax
  __int64 v159; // rax
  unsigned int v160; // r10d
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  _BYTE *v165; // rcx
  unsigned int v166; // ebx
  _BYTE *v167; // rdx
  __int16 v168; // ax
  __int16 v169; // cx
  __int16 v170; // ax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  char v175; // cl
  bool v176; // zf
  unsigned int v177; // r9d
  __int64 v178; // r8
  unsigned __int64 v179; // rcx
  int v180; // eax
  unsigned int v181; // eax
  int v182; // ecx
  int v183; // eax
  __int64 v184; // rcx
  int XdesLockIfNecessary; // eax
  __int16 v186; // ax
  __int64 v187; // r8
  unsigned int Lock; // eax
  __int64 v189; // rdx
  int v190; // r15d
  __int64 v191; // rdx
  __int64 v192; // rcx
  _WORD *v193; // rax
  __int64 v194; // rax
  unsigned __int16 v195; // si
  __int64 v196; // r9
  unsigned int v197; // ebx
  __int16 v198; // di
  struct XDES *v199; // r8
  __int64 v200; // rcx
  __int64 v201; // rax
  unsigned int v202; // eax
  __int64 v203; // rdx
  _OWORD *v204; // rbx
  int v205; // edi
  char *v206; // r8
  char v207; // dl
  unsigned __int8 *v208; // r14
  __int16 v209; // r11
  char v210; // al
  __int16 v211; // dx
  unsigned __int64 v212; // rcx
  __int64 v213; // rcx
  __int64 v214; // rsi
  unsigned __int8 *v215; // r8
  unsigned __int8 v216; // dl
  __int16 v217; // dx
  __int16 v218; // cx
  unsigned int v219; // eax
  unsigned __int8 *v220; // rax
  __int16 v221; // cx
  PageComprInfoCache *v222; // rcx
  unsigned __int16 v223; // ax
  int v224; // eax
  int v225; // edi
  unsigned __int16 v226; // cx
  __int16 v227; // dx
  int v228; // ebx
  __int16 v229; // di
  struct XDES *v230; // r8
  __int64 v231; // rax
  __int64 v232; // r9
  __int64 v233; // rcx
  __int64 v234; // r9
  unsigned int v235; // eax
  __int64 v236; // rdx
  struct PageId *v237; // rbx
  __int64 v238; // rcx
  __int64 v239; // rcx
  __int16 v240; // ax
  int v241; // eax
  const struct Page *v242; // r8
  int *v243; // rcx
  int *v244; // rcx
  int *v245; // rcx
  __int64 v246; // r15
  __int128 *v247; // rbx
  unsigned int v248; // edi
  unsigned __int8 *v249; // r8
  unsigned __int8 *v250; // rdi
  __int16 v251; // r11
  char v252; // al
  __int16 v253; // dx
  unsigned __int64 v254; // rcx
  __int64 v255; // rcx
  __int64 v256; // r14
  unsigned __int8 *v257; // r8
  unsigned __int8 v258; // dl
  __int16 v259; // dx
  __int16 v260; // cx
  unsigned int v261; // eax
  unsigned __int8 *v262; // rax
  __int16 v263; // cx
  PageComprInfoCache *v264; // rcx
  unsigned __int16 v265; // ax
  int v266; // eax
  int v267; // esi
  unsigned __int16 v268; // cx
  int v269; // eax
  unsigned int v270; // r10d
  char v271; // al
  int v272; // eax
  unsigned __int16 *v273; // rsi
  __int64 v274; // rax
  __int64 v275; // rax
  unsigned int v276; // r9d
  __int64 v277; // rax
  __int64 v278; // rax
  __int64 v279; // rax
  __int64 v280; // rax
  _BYTE *v281; // rcx
  unsigned int v282; // edi
  unsigned __int16 v283; // r8
  _BYTE *v284; // rdx
  __int16 v285; // ax
  __int16 v286; // cx
  __int16 v287; // ax
  __int16 v288; // cx
  struct RecVersioningInfo *v289; // rax
  int v290; // r8d
  unsigned int v291; // ecx
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rax
  char v296; // cl
  int v297; // ecx
  struct XDES *v298; // rdi
  struct VersionScanParams *v299; // r15
  int v300; // ebx
  char v301; // si
  __int64 v302; // rcx
  struct XDES *v303; // rdx
  __int64 v304; // rcx
  __int64 v305; // rax
  __int64 v306; // rdx
  _QWORD *v307; // rax
  struct XDES **v308; // rbx
  struct XDES *v309; // rax
  __int64 v310; // rax
  __int64 v311; // rax
  __int64 v312; // rax
  int v313; // edi
  struct ForeignXdesContext *v314; // r14
  struct XDES *v315; // rbx
  __int64 Lsn; // rsi
  char *v317; // r13
  __int64 v318; // r15
  char v319; // r12
  __int64 v320; // rcx
  __int64 v321; // rdi
  __int64 v322; // rcx
  unsigned int v323; // ecx
  unsigned int v324; // ecx
  struct VersionScanParams *v325; // rsi
  __int64 v326; // rdi
  struct XVB **v327; // r10
  __int64 v328; // rcx
  LobContext **v329; // r14
  __int64 v330; // rbx
  struct Worker *v331; // rcx
  int v332; // eax
  struct PageId *v333; // r12
  char *v334; // rdx
  struct XDES *Xdes; // rax
  unsigned int v336; // edx
  unsigned __int8 *v337; // rdi
  unsigned __int16 v338; // r8
  __int64 v339; // rax
  __int64 v340; // rax
  unsigned int v341; // r9d
  __int64 v342; // rax
  __int64 v343; // rax
  __int64 v344; // rax
  __int64 v345; // rax
  unsigned __int8 *v346; // rcx
  unsigned int v347; // ebx
  unsigned __int16 v348; // r10
  unsigned int v349; // eax
  __int64 v350; // rax
  struct CSessionTraceFlags *v351; // rcx
  __int64 v352; // rax
  __int64 v353; // rdi
  __int64 v354; // rcx
  unsigned int v355; // ebx
  __int64 v356; // r9
  __int64 v357; // rax
  struct CSessionTraceFlags *v358; // rcx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v360; // rax
  CTracePrintStream *v361; // rbx
  __int64 v362; // rax
  struct CSessionTraceFlags *v363; // rcx
  __int64 v364; // rax
  __int64 v365; // rdi
  __int64 v366; // rcx
  unsigned int v367; // ebx
  __int64 v368; // r9
  int v369; // edi
  char v370; // al
  struct LSN *v371; // rsi
  struct OffRowPageRequestResult *v372; // r14
  struct XDES *v373; // rbx
  __int64 v374; // r15
  char v375; // r12
  __int64 v376; // rcx
  __int64 v377; // rdi
  __int64 v378; // rcx
  unsigned int v379; // eax
  __int64 v380; // rax
  struct CSessionTraceFlags *v381; // rcx
  __int64 v382; // rax
  __int64 v383; // rdi
  __int64 v384; // rcx
  unsigned int v385; // ebx
  __int64 v386; // r9
  __int64 v387; // rdx
  struct CSessionTraceFlags *v388; // rcx
  HANDLE v389; // rax
  CTracePrintStream *v390; // rax
  CTracePrintStream *v391; // rbx
  __int64 v392; // rax
  struct CSessionTraceFlags *v393; // rcx
  __int64 v394; // rax
  __int64 v395; // rdi
  __int64 v396; // rcx
  unsigned int v397; // ebx
  __int64 v398; // r9
  unsigned int v399; // ecx
  unsigned int v400; // ecx
  __int64 v401; // rdi
  __int64 v402; // rcx
  signed __int64 v403; // rax
  unsigned __int8 *v404; // r8
  __int16 v405; // ax
  __int16 v406; // cx
  struct RecVersioningInfo *v407; // rax
  __int64 v408; // rdx
  int v409; // r9d
  __int64 v410; // rax
  __int64 v411; // rax
  __int64 v412; // rax
  __int64 v413; // rax
  char v414; // cl
  bool v415; // zf
  LobContext *v416; // rdx
  __int64 v417; // rcx
  __int64 v418; // rax
  __int64 v419; // rcx
  _QWORD *ObjectDataImpl; // rax
  unsigned __int8 *v421; // rcx
  char v422; // dl
  LobContext *v423; // r9
  int v424; // r9d
  const struct SQLError *CurrentException; // rax
  signed __int32 v426[8]; // [rsp+0h] [rbp-CD8h] BYREF
  struct Record *v427; // [rsp+20h] [rbp-CB8h]
  struct Worker *v428; // [rsp+28h] [rbp-CB0h]
  struct Record *v429; // [rsp+30h] [rbp-CA8h]
  struct ForeignXdesContext *v430; // [rsp+38h] [rbp-CA0h]
  struct ForeignXdesContext *v431; // [rsp+40h] [rbp-C98h]
  struct LSN *v432; // [rsp+48h] [rbp-C90h]
  struct OffRowPageRequestResult *v433; // [rsp+58h] [rbp-C80h]
  unsigned int v434; // [rsp+60h] [rbp-C78h]
  struct VersionScanParams *v435; // [rsp+68h] [rbp-C70h]
  struct XDES **v436; // [rsp+70h] [rbp-C68h]
  char v437; // [rsp+78h] [rbp-C60h]
  char v438; // [rsp+79h] [rbp-C5Fh]
  PageRef *v439; // [rsp+80h] [rbp-C58h]
  int v440; // [rsp+88h] [rbp-C50h] BYREF
  int v441; // [rsp+8Ch] [rbp-C4Ch] BYREF
  __int16 v442; // [rsp+90h] [rbp-C48h]
  __int16 v443; // [rsp+94h] [rbp-C44h]
  int v444; // [rsp+98h] [rbp-C40h]
  __int16 v445; // [rsp+9Ch] [rbp-C3Ch]
  struct PageId *v446; // [rsp+A0h] [rbp-C38h]
  unsigned __int8 *v447; // [rsp+A8h] [rbp-C30h]
  char v448; // [rsp+B0h] [rbp-C28h]
  char v449; // [rsp+B1h] [rbp-C27h]
  char v450; // [rsp+B2h] [rbp-C26h]
  struct XDES **v451; // [rsp+B8h] [rbp-C20h]
  __int64 v452; // [rsp+C0h] [rbp-C18h] BYREF
  int v453; // [rsp+C8h] [rbp-C10h] BYREF
  int v454; // [rsp+CCh] [rbp-C0Ch]
  unsigned int v455; // [rsp+D0h] [rbp-C08h]
  int v456; // [rsp+D4h] [rbp-C04h] BYREF
  __int16 v457; // [rsp+D8h] [rbp-C00h]
  unsigned int v458; // [rsp+DAh] [rbp-BFEh] BYREF
  unsigned __int16 v459; // [rsp+DEh] [rbp-BFAh]
  __int16 v460; // [rsp+E0h] [rbp-BF8h] BYREF
  int v461; // [rsp+E2h] [rbp-BF6h]
  __int16 v462; // [rsp+E6h] [rbp-BF2h]
  __int64 v463; // [rsp+E8h] [rbp-BF0h]
  int v464; // [rsp+F0h] [rbp-BE8h] BYREF
  __int16 v465; // [rsp+F4h] [rbp-BE4h]
  __int16 v466; // [rsp+F6h] [rbp-BE2h]
  int v467; // [rsp+F8h] [rbp-BE0h] BYREF
  __int16 v468; // [rsp+FCh] [rbp-BDCh]
  __int16 v469; // [rsp+FEh] [rbp-BDAh]
  __int64 v470; // [rsp+100h] [rbp-BD8h] BYREF
  int v471; // [rsp+108h] [rbp-BD0h] BYREF
  __int16 v472; // [rsp+10Ch] [rbp-BCCh]
  int v473; // [rsp+110h] [rbp-BC8h] BYREF
  __int16 v474; // [rsp+114h] [rbp-BC4h]
  unsigned int v475; // [rsp+120h] [rbp-BB8h] BYREF
  unsigned __int16 v476; // [rsp+124h] [rbp-BB4h]
  int v477; // [rsp+130h] [rbp-BA8h] BYREF
  __int16 v478; // [rsp+134h] [rbp-BA4h]
  int v479; // [rsp+136h] [rbp-BA2h] BYREF
  __int16 v480; // [rsp+13Ah] [rbp-B9Eh]
  int v481; // [rsp+13Ch] [rbp-B9Ch]
  struct XDES *v482; // [rsp+140h] [rbp-B98h]
  unsigned int *v483; // [rsp+148h] [rbp-B90h]
  __int64 v484; // [rsp+150h] [rbp-B88h]
  __int64 v485; // [rsp+158h] [rbp-B80h] BYREF
  unsigned __int16 v486; // [rsp+160h] [rbp-B78h]
  LSN v487; // [rsp+168h] [rbp-B70h] BYREF
  unsigned __int16 v488; // [rsp+170h] [rbp-B68h]
  int v489; // [rsp+178h] [rbp-B60h] BYREF
  __int16 v490; // [rsp+17Ch] [rbp-B5Ch]
  int v491; // [rsp+17Eh] [rbp-B5Ah] BYREF
  __int16 v492; // [rsp+182h] [rbp-B56h]
  int v493; // [rsp+184h] [rbp-B54h] BYREF
  __int16 v494; // [rsp+188h] [rbp-B50h]
  int v495; // [rsp+18Ah] [rbp-B4Eh] BYREF
  __int16 v496; // [rsp+18Eh] [rbp-B4Ah]
  struct XDES *v497; // [rsp+190h] [rbp-B48h]
  struct XDES *v498; // [rsp+198h] [rbp-B40h]
  __int64 v499; // [rsp+1A0h] [rbp-B38h] BYREF
  unsigned __int16 v500; // [rsp+1A8h] [rbp-B30h]
  unsigned __int64 v501; // [rsp+1B0h] [rbp-B28h] BYREF
  __int16 v502; // [rsp+1B8h] [rbp-B20h]
  unsigned __int64 v503; // [rsp+1C0h] [rbp-B18h] BYREF
  __int16 v504; // [rsp+1C8h] [rbp-B10h]
  unsigned __int64 v505; // [rsp+1D0h] [rbp-B08h] BYREF
  __int16 v506; // [rsp+1D8h] [rbp-B00h]
  int v507; // [rsp+1E0h] [rbp-AF8h]
  int v508; // [rsp+1F0h] [rbp-AE8h] BYREF
  __int16 v509; // [rsp+1F4h] [rbp-AE4h]
  int v510; // [rsp+200h] [rbp-AD8h] BYREF
  __int16 v511; // [rsp+204h] [rbp-AD4h]
  unsigned int v512; // [rsp+210h] [rbp-AC8h] BYREF
  unsigned __int16 v513; // [rsp+214h] [rbp-AC4h]
  unsigned int v514; // [rsp+220h] [rbp-AB8h] BYREF
  __int16 v515; // [rsp+224h] [rbp-AB4h]
  int v516; // [rsp+230h] [rbp-AA8h] BYREF
  __int16 v517; // [rsp+234h] [rbp-AA4h]
  int v518; // [rsp+238h] [rbp-AA0h] BYREF
  __int16 v519; // [rsp+23Ch] [rbp-A9Ch]
  int v520; // [rsp+240h] [rbp-A98h] BYREF
  __int16 v521; // [rsp+244h] [rbp-A94h]
  int v522; // [rsp+248h] [rbp-A90h] BYREF
  __int16 v523; // [rsp+24Ch] [rbp-A8Ch]
  int v524; // [rsp+250h] [rbp-A88h] BYREF
  __int16 v525; // [rsp+254h] [rbp-A84h]
  int v526; // [rsp+260h] [rbp-A78h] BYREF
  __int16 v527; // [rsp+264h] [rbp-A74h]
  int v528; // [rsp+268h] [rbp-A70h] BYREF
  __int16 v529; // [rsp+26Ch] [rbp-A6Ch]
  int v530; // [rsp+270h] [rbp-A68h] BYREF
  __int16 v531; // [rsp+274h] [rbp-A64h]
  int v532; // [rsp+278h] [rbp-A60h] BYREF
  __int16 v533; // [rsp+27Ch] [rbp-A5Ch]
  int v534; // [rsp+280h] [rbp-A58h] BYREF
  __int16 v535; // [rsp+284h] [rbp-A54h]
  __int64 v536; // [rsp+288h] [rbp-A50h] BYREF
  __int16 v537; // [rsp+290h] [rbp-A48h]
  unsigned __int16 v538; // [rsp+298h] [rbp-A40h]
  unsigned __int16 v539; // [rsp+29Ah] [rbp-A3Eh]
  __int16 v540; // [rsp+2A0h] [rbp-A38h]
  unsigned int v541; // [rsp+2A8h] [rbp-A30h] BYREF
  int v542; // [rsp+2ACh] [rbp-A2Ch] BYREF
  int v543; // [rsp+2B0h] [rbp-A28h]
  int v544; // [rsp+2B8h] [rbp-A20h]
  int v545; // [rsp+2BCh] [rbp-A1Ch]
  int v546; // [rsp+2C0h] [rbp-A18h] BYREF
  __int16 v547; // [rsp+2C4h] [rbp-A14h]
  __int16 v548; // [rsp+2C6h] [rbp-A12h]
  int v549; // [rsp+2C8h] [rbp-A10h] BYREF
  __int16 v550; // [rsp+2CCh] [rbp-A0Ch]
  __int16 v551; // [rsp+2CEh] [rbp-A0Ah]
  int v552; // [rsp+2D0h] [rbp-A08h] BYREF
  __int16 v553; // [rsp+2D4h] [rbp-A04h]
  __int16 v554; // [rsp+2D6h] [rbp-A02h]
  int v555; // [rsp+2D8h] [rbp-A00h] BYREF
  __int16 v556; // [rsp+2DCh] [rbp-9FCh]
  __int16 v557; // [rsp+2DEh] [rbp-9FAh]
  int v558; // [rsp+2E0h] [rbp-9F8h]
  __int16 v559; // [rsp+2E4h] [rbp-9F4h]
  int v560; // [rsp+2E8h] [rbp-9F0h] BYREF
  __int16 v561; // [rsp+2ECh] [rbp-9ECh]
  __int16 v562; // [rsp+2EEh] [rbp-9EAh]
  int v563; // [rsp+2F0h] [rbp-9E8h] BYREF
  __int16 v564; // [rsp+2F4h] [rbp-9E4h]
  __int16 v565; // [rsp+2F6h] [rbp-9E2h]
  int v566; // [rsp+2F8h] [rbp-9E0h] BYREF
  __int16 v567; // [rsp+2FCh] [rbp-9DCh]
  __int16 v568; // [rsp+2FEh] [rbp-9DAh]
  char v569[8]; // [rsp+300h] [rbp-9D8h] BYREF
  char v570[8]; // [rsp+308h] [rbp-9D0h] BYREF
  char v571[8]; // [rsp+310h] [rbp-9C8h] BYREF
  int v572; // [rsp+318h] [rbp-9C0h]
  __int64 v573; // [rsp+31Ch] [rbp-9BCh]
  int v574; // [rsp+324h] [rbp-9B4h]
  LSN v575; // [rsp+328h] [rbp-9B0h]
  int v576; // [rsp+330h] [rbp-9A8h]
  __int64 v577; // [rsp+338h] [rbp-9A0h]
  __int16 v578; // [rsp+340h] [rbp-998h]
  __int64 v579; // [rsp+348h] [rbp-990h] BYREF
  __int16 v580; // [rsp+350h] [rbp-988h]
  struct XDES **v581; // [rsp+358h] [rbp-980h]
  PageRef *v582; // [rsp+360h] [rbp-978h]
  struct PageId *v583; // [rsp+368h] [rbp-970h]
  unsigned int *v584; // [rsp+370h] [rbp-968h]
  char v585[8]; // [rsp+378h] [rbp-960h] BYREF
  char v586[8]; // [rsp+380h] [rbp-958h] BYREF
  char v587[8]; // [rsp+388h] [rbp-950h] BYREF
  struct PageId *v588; // [rsp+390h] [rbp-948h]
  CTracePrintStream *v589; // [rsp+398h] [rbp-940h]
  __int64 v590; // [rsp+3A0h] [rbp-938h]
  struct ForeignXdesContext *v591; // [rsp+3A8h] [rbp-930h]
  __int128 v592; // [rsp+3B0h] [rbp-928h] BYREF
  unsigned int v593; // [rsp+3C0h] [rbp-918h]
  char v594; // [rsp+3C4h] [rbp-914h]
  __int128 v595; // [rsp+3C8h] [rbp-910h]
  unsigned __int64 v596; // [rsp+3D8h] [rbp-900h]
  int v597; // [rsp+3E0h] [rbp-8F8h]
  __int16 v598; // [rsp+3E4h] [rbp-8F4h]
  int v599; // [rsp+3E8h] [rbp-8F0h]
  int v600; // [rsp+3F0h] [rbp-8E8h]
  int v601; // [rsp+3F8h] [rbp-8E0h]
  unsigned int v602; // [rsp+400h] [rbp-8D8h] BYREF
  __int64 v603; // [rsp+404h] [rbp-8D4h]
  __int64 v604; // [rsp+418h] [rbp-8C0h] BYREF
  __int16 v605; // [rsp+420h] [rbp-8B8h]
  LSN v606; // [rsp+428h] [rbp-8B0h] BYREF
  __int16 v607; // [rsp+430h] [rbp-8A8h]
  struct XDES **v608; // [rsp+438h] [rbp-8A0h]
  struct CSessionTraceFlags *v609; // [rsp+440h] [rbp-898h]
  int v610; // [rsp+448h] [rbp-890h]
  int v611; // [rsp+450h] [rbp-888h]
  int v612; // [rsp+458h] [rbp-880h]
  DWORD v613; // [rsp+45Ch] [rbp-87Ch] BYREF
  DWORD v614; // [rsp+460h] [rbp-878h] BYREF
  DWORD flOldProtect; // [rsp+464h] [rbp-874h] BYREF
  struct CSessionTraceFlags *v616; // [rsp+468h] [rbp-870h]
  struct CSessionTraceFlags *v617; // [rsp+470h] [rbp-868h]
  __int64 v618; // [rsp+478h] [rbp-860h]
  int v619; // [rsp+480h] [rbp-858h]
  _QWORD v620[3]; // [rsp+488h] [rbp-850h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+4A0h] [rbp-838h]
  __int64 *v622; // [rsp+4A8h] [rbp-830h]
  __int64 v623; // [rsp+4B0h] [rbp-828h]
  struct CSessionTraceFlags *v624; // [rsp+4B8h] [rbp-820h]
  __int64 v625; // [rsp+4C0h] [rbp-818h]
  int *v626; // [rsp+4C8h] [rbp-810h]
  __int64 v627; // [rsp+4D0h] [rbp-808h]
  int *v628; // [rsp+4D8h] [rbp-800h]
  __int64 v629; // [rsp+4E0h] [rbp-7F8h]
  signed __int64 v630; // [rsp+4E8h] [rbp-7F0h]
  char *v631; // [rsp+4F0h] [rbp-7E8h]
  _QWORD *v632; // [rsp+4F8h] [rbp-7E0h]
  __int64 *v633; // [rsp+500h] [rbp-7D8h]
  struct CSessionTraceFlags *v634; // [rsp+508h] [rbp-7D0h]
  CTracePrintStream *v635; // [rsp+510h] [rbp-7C8h]
  CTracePrintStream *v636; // [rsp+518h] [rbp-7C0h]
  CTracePrintStream *v637; // [rsp+520h] [rbp-7B8h]
  CTracePrintStream *v638; // [rsp+528h] [rbp-7B0h]
  int *v639; // [rsp+530h] [rbp-7A8h]
  __int64 v640; // [rsp+538h] [rbp-7A0h]
  __int64 v641; // [rsp+540h] [rbp-798h]
  unsigned __int64 v642; // [rsp+548h] [rbp-790h]
  __int64 *v643; // [rsp+550h] [rbp-788h]
  __int64 v644; // [rsp+560h] [rbp-778h]
  __int64 *v645; // [rsp+578h] [rbp-760h]
  __int64 v646; // [rsp+580h] [rbp-758h]
  __int64 v647; // [rsp+588h] [rbp-750h]
  __int64 v648; // [rsp+590h] [rbp-748h]
  __int64 v649; // [rsp+598h] [rbp-740h]
  __int64 v650; // [rsp+5A0h] [rbp-738h]
  char *v651; // [rsp+5A8h] [rbp-730h]
  __int64 v652; // [rsp+5B0h] [rbp-728h]
  __int64 v653; // [rsp+5B8h] [rbp-720h]
  char *v654; // [rsp+5C0h] [rbp-718h]
  _QWORD *v655; // [rsp+5C8h] [rbp-710h]
  __int64 *v656; // [rsp+5D0h] [rbp-708h]
  __int64 v657; // [rsp+5D8h] [rbp-700h]
  struct CSessionTraceFlags *v658; // [rsp+5E0h] [rbp-6F8h]
  _DWORD v659[6]; // [rsp+5E8h] [rbp-6F0h] BYREF
  char v660[16]; // [rsp+600h] [rbp-6D8h] BYREF
  char v661[8]; // [rsp+610h] [rbp-6C8h] BYREF
  int v662; // [rsp+618h] [rbp-6C0h]
  int v663; // [rsp+620h] [rbp-6B8h]
  int **v664; // [rsp+628h] [rbp-6B0h]
  char *v665; // [rsp+630h] [rbp-6A8h]
  __int64 v666; // [rsp+638h] [rbp-6A0h]
  int *v667; // [rsp+640h] [rbp-698h] BYREF
  int v668; // [rsp+648h] [rbp-690h]
  int v669; // [rsp+64Ch] [rbp-68Ch]
  GUID *v670; // [rsp+650h] [rbp-688h]
  int v671; // [rsp+658h] [rbp-680h]
  int v672; // [rsp+65Ch] [rbp-67Ch]
  GUID *v673; // [rsp+660h] [rbp-678h]
  int v674; // [rsp+668h] [rbp-670h]
  int v675; // [rsp+66Ch] [rbp-66Ch]
  wchar_t *v676; // [rsp+670h] [rbp-668h]
  int v677; // [rsp+678h] [rbp-660h]
  int v678; // [rsp+67Ch] [rbp-65Ch]
  wchar_t *v679; // [rsp+680h] [rbp-658h]
  int v680; // [rsp+688h] [rbp-650h]
  int v681; // [rsp+68Ch] [rbp-64Ch]
  __int64 v682; // [rsp+690h] [rbp-648h]
  int v683; // [rsp+698h] [rbp-640h]
  int v684; // [rsp+69Ch] [rbp-63Ch]
  char v685; // [rsp+6A0h] [rbp-638h] BYREF
  __int64 v686; // [rsp+860h] [rbp-478h]
  __int64 v687; // [rsp+868h] [rbp-470h]
  int v688; // [rsp+870h] [rbp-468h] BYREF
  __int16 v689; // [rsp+874h] [rbp-464h]
  int v690; // [rsp+876h] [rbp-462h]
  char v691; // [rsp+87Ah] [rbp-45Eh]
  char v692; // [rsp+87Bh] [rbp-45Dh]
  _BYTE v693[48]; // [rsp+8B0h] [rbp-428h] BYREF
  _BYTE v694[96]; // [rsp+8E0h] [rbp-3F8h] BYREF
  _BYTE v695[96]; // [rsp+940h] [rbp-398h] BYREF
  __int16 v696; // [rsp+9A0h] [rbp-338h] BYREF
  unsigned __int16 v697; // [rsp+9A2h] [rbp-336h] BYREF
  unsigned int v698; // [rsp+9A4h] [rbp-334h]
  struct XDES *v699; // [rsp+9A8h] [rbp-330h]
  __int128 *v700; // [rsp+9B0h] [rbp-328h]
  _BYTE v701[24]; // [rsp+9B8h] [rbp-320h]
  int v702; // [rsp+9D0h] [rbp-308h]
  int v703; // [rsp+9D4h] [rbp-304h]
  __int128 v704; // [rsp+9D8h] [rbp-300h] BYREF
  __int128 v705; // [rsp+9E8h] [rbp-2F0h]
  _BYTE v706[22]; // [rsp+9F8h] [rbp-2E0h] BYREF
  __int16 v707; // [rsp+A0Eh] [rbp-2CAh]
  __int64 v708; // [rsp+A10h] [rbp-2C8h]
  __int128 v709; // [rsp+A18h] [rbp-2C0h]
  __int128 v710; // [rsp+A28h] [rbp-2B0h]
  __int128 v711; // [rsp+A38h] [rbp-2A0h]
  __int64 v712; // [rsp+A48h] [rbp-290h]
  __int64 v713; // [rsp+A50h] [rbp-288h] BYREF
  int v714; // [rsp+A58h] [rbp-280h]
  __int64 v715; // [rsp+A60h] [rbp-278h]
  char v716; // [rsp+A68h] [rbp-270h]
  __int16 v717; // [rsp+A70h] [rbp-268h] BYREF
  __int16 v718; // [rsp+A72h] [rbp-266h] BYREF
  unsigned int v719; // [rsp+A74h] [rbp-264h]
  unsigned __int8 *v720; // [rsp+A78h] [rbp-260h]
  __int64 v721; // [rsp+A80h] [rbp-258h]
  unsigned int v722; // [rsp+A88h] [rbp-250h]
  unsigned __int16 v723; // [rsp+A8Ch] [rbp-24Ch]
  unsigned __int64 v724; // [rsp+A8Eh] [rbp-24Ah]
  _TBYTE v725; // [rsp+A96h] [rbp-242h]
  int v726; // [rsp+AA4h] [rbp-234h]
  int v727; // [rsp+B20h] [rbp-1B8h] BYREF
  __int64 v728; // [rsp+B24h] [rbp-1B4h]
  __int16 v729; // [rsp+B2Ch] [rbp-1ACh]
  char v730; // [rsp+B2Eh] [rbp-1AAh]
  _DWORD v731[2]; // [rsp+B30h] [rbp-1A8h] BYREF
  __int16 v732; // [rsp+B38h] [rbp-1A0h]
  __int64 v733; // [rsp+B40h] [rbp-198h] BYREF
  __int16 v734; // [rsp+B48h] [rbp-190h]
  __int16 v735; // [rsp+B50h] [rbp-188h]
  unsigned __int16 v736; // [rsp+B52h] [rbp-186h] BYREF
  int v737; // [rsp+B54h] [rbp-184h]
  char *v738; // [rsp+B58h] [rbp-180h]
  _OWORD *v739; // [rsp+B60h] [rbp-178h]
  _BYTE v740[24]; // [rsp+B68h] [rbp-170h]
  int v741; // [rsp+B80h] [rbp-158h]
  int v742; // [rsp+B84h] [rbp-154h]
  _OWORD v743[7]; // [rsp+B88h] [rbp-150h] BYREF
  __int64 v744; // [rsp+BF8h] [rbp-E0h]
  __int64 v745; // [rsp+C00h] [rbp-D8h] BYREF
  int v746; // [rsp+C08h] [rbp-D0h]
  __int16 v747; // [rsp+C0Ch] [rbp-CCh]
  __int16 v748; // [rsp+C0Eh] [rbp-CAh]
  __int64 v749; // [rsp+C10h] [rbp-C8h]
  __int64 v750; // [rsp+C18h] [rbp-C0h]
  wchar_t v751[24]; // [rsp+C20h] [rbp-B8h] BYREF
  wchar_t v752[24]; // [rsp+C50h] [rbp-88h] BYREF

  v644 = -2;
  v483 = a4;
  v439 = a3;
  v446 = a2;
  v21 = (struct XDES **)a1;
  v451 = (struct XDES **)a1;
  v608 = (struct XDES **)a1;
  v436 = (struct XDES **)a1;
  v581 = (struct XDES **)a1;
  v583 = a2;
  v588 = a2;
  v582 = a3;
  v584 = a4;
  v22 = a5;
  v444 = a5;
  v543 = a5;
  v447 = a7;
  v696 = -1;
  v23 = 0;
  v699 = 0;
  v698 = 0;
  *(_QWORD *)&v701[6] = 0;
  *(_QWORD *)&v701[16] = 0;
  v700 = 0;
  v703 = -1;
  v454 = 0;
  v592 = 0;
  v593 &= 0xFFFFFC00;
  v594 &= 0xFCu;
  v595 = 0;
  v597 = -1;
  v598 = -1;
  v24 = (struct XDES **)a1;
  v25 = *(_QWORD *)(a1 + 8);
  v26 = *(struct VersionScanParams **)(v25 + 136);
  v435 = v26;
  v27 = *(_QWORD *)(v25 + 384);
  v463 = v27;
  v455 = NullXdesId;
  v443 = word_10318AB38;
  v484 = 4095;
  v434 = 15;
  while ( 2 )
  {
    while ( 2 )
    {
      LOBYTE(v26) = 105;
      YieldAndCheckForAbort(v26);
      v497 = v24[20];
      v441 = *(_DWORD *)v446;
      v442 = *((_WORD *)v446 + 2);
      if ( v27 )
      {
        if ( !RecoveryUnit::IsForeignPageTrackedByCurrenPageServer(v24[4], v446) )
          ex_raise(164, 1, 25, 1);
        v28 = v24[1];
        v91 = *(_WORD *)(*((_QWORD *)v28 + 48) + 26LL);
        v441 = *(_DWORD *)v446;
        v442 = v91;
      }
      else
      {
        v28 = v21[1];
      }
      v482 = v28;
      v603 = 0;
      v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v30 = *(_QWORD **)(v29 + 256);
      if ( !v30 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v30 = *(_QWORD **)(v29 + 256);
      }
      v31 = __rdtsc();
      v32 = v30[104];
      if ( v31 > v32 || v32 != 0x7FFFFFFFFFFFFFFFLL && v32 - v31 > *(_QWORD *)(v30[76] + 3568LL) )
      {
        v93 = (unsigned int)SOS_Task::Sleep(0, yieldWait) == 2;
LABEL_116:
        if ( v93 )
        {
          LOBYTE(v33) = -90;
          RaiseExecutionAbortedError(v33);
        }
        goto LABEL_10;
      }
      v33 = v30[75];
      if ( (*(_DWORD *)(v33 + 188) & 4) != 0 )
      {
        v92 = *(_QWORD *)(v33 + 152);
        if ( (*(_BYTE *)(v92 + 616) & 1) == 0 )
        {
          v93 = (*(_DWORD *)(v92 + 800) & 0x180) == 0;
          goto LABEL_116;
        }
      }
LABEL_10:
      v34 = *(_QWORD *)(*((_QWORD *)v28 + 11) + 32LL);
      if ( !CommonGlobalState::m_CollectingStatistics
        || byte_10317ABE6 < 0
        || (v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset,
            *(_QWORD *)v35)
        && (v36 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v35 + 56LL)) != 0
        && CSessionTraceFlags::CheckSessionTraceInternal(v36, 0x337u)
        || (v37 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                            + SystemThread_TlsOffset
                            + 8LL)) == 0 )
      {
        SETLSFromTlsMaybeNull = 0;
      }
      else
      {
        SETLSFromTlsMaybeNull = *(struct SEInternalTLS **)(v37 + 96);
      }
      v39 = *(_QWORD **)(v34 + 1832);
      v40 = v439;
      while ( 1 )
      {
        v453 = 0;
        if ( !*(_QWORD *)v40 )
          goto LABEL_18;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_18;
        }
        v94 = *((__int16 *)v40 + 6);
        v95 = *(__int64 **)v40;
        if ( (*((_WORD *)v95 + 49) & 8) != 0 )
        {
          if ( v94 == 3 )
          {
            v94 = 4;
LABEL_127:
            if ( (*((_DWORD *)v95 + 25) & 8) != 0 )
            {
              v96 = v95[18];
              if ( v96 )
              {
                if ( *(_QWORD *)(v96 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v96 + 1880), v95, (unsigned int)v94);
                }
              }
            }
            goto LABEL_131;
          }
          if ( v94 >= 2 )
            goto LABEL_127;
        }
LABEL_131:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v95 + 25) & 8) != 0
          && v94 >= 3
          && (*((_DWORD *)v95 + 25) & 0xC0000000) != 0x40000000
          && *v95
          && VirtualProtect((LPVOID)*v95, 0x2000u, 2u, &flOldProtect) )
        {
          _InterlockedAnd((volatile signed __int32 *)v95 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v95 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v95 + 19, (unsigned int)v94);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v95, 0, (unsigned int)v94);
        v40 = v439;
        *((_WORD *)v439 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v444;
LABEL_18:
        if ( !*(_QWORD *)(v34 + 1832) )
          goto LABEL_19;
        if ( v22 < 2 )
          goto LABEL_19;
        PageRef::CatchupPageRedos(v40, (const struct PageId *)&v441, (struct RecoveryUnit *)v34);
        if ( !*(_QWORD *)v40 )
          goto LABEL_19;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_19;
        }
        v97 = *((__int16 *)v40 + 6);
        v98 = *(_QWORD *)v40;
        if ( (*(_WORD *)(v98 + 98) & 8) != 0 )
        {
          if ( v97 == 3 )
          {
            v97 = 4;
LABEL_152:
            if ( (*(_DWORD *)(v98 + 100) & 8) != 0 )
            {
              v99 = *(_QWORD *)(v98 + 144);
              if ( v99 )
              {
                if ( *(_QWORD *)(v99 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v99 + 1880), v98, (unsigned int)v97);
                }
              }
            }
            goto LABEL_156;
          }
          if ( v97 >= 2 )
            goto LABEL_152;
        }
LABEL_156:
        if ( byte_10317ABE5 < 0
          && (*(_DWORD *)(v98 + 100) & 8) != 0
          && v97 >= 3
          && (*(_DWORD *)(v98 + 100) & 0xC0000000) != 0x40000000
          && *(_QWORD *)v98
          && VirtualProtect(*(LPVOID *)v98, 0x2000u, 2u, &v614) )
        {
          _InterlockedAnd((volatile signed __int32 *)(v98 + 100), 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)(v98 + 100), 0x40000000u);
        }
        LatchBase::ReleaseInternal(v98 + 152, (unsigned int)v97);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v98, 0, (unsigned int)v97);
        v40 = v439;
        *((_WORD *)v439 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v444;
LABEL_19:
        if ( v22 >= 3 )
          RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v34, (const struct PageId *)&v441);
        LODWORD(v427) = v22;
        v41 = (__int64 *)BPool::Get(qword_10317B628, v34, &v441, &v453, v427, &v602);
        *(_QWORD *)v40 = v41;
        *((_WORD *)v40 + 6) = v22;
        if ( SETLSFromTlsMaybeNull )
        {
          v42 = *v41;
          v43 = *((_DWORD *)SETLSFromTlsMaybeNull + 320) & 0xF;
          if ( *((_QWORD *)SETLSFromTlsMaybeNull + v43 + 161) != v42 )
          {
            *((_QWORD *)SETLSFromTlsMaybeNull + v43 + 161) = v42;
            ++*((_QWORD *)SETLSFromTlsMaybeNull + 160);
          }
        }
        *((_BYTE *)v40 + 15) = (v453 & 8) != 0;
        *((_BYTE *)v40 + 16) = (v453 & 0x10) != 0;
        if ( v39 )
        {
          if ( SETLSFromTlsMaybeNull )
          {
            if ( SETLSFromTlsMaybeNull == *(struct SEInternalTLS **)(v34 + 7224) )
            {
              v100 = *((char *)v40 + 15);
              ++v39[2917];
              if ( (_DWORD)v603 )
              {
                ++v39[2918];
                v39[2919] += v602;
                if ( v100 )
                {
                  ++v39[2920];
                  v39[2921] += v602;
                }
              }
            }
          }
        }
        if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v34)
          || !*(_BYTE *)(v34 + 8272)
          || v22 < 2
          || !v441
          || v441 == 9 && v442 == 1 )
        {
          goto LABEL_26;
        }
        v101 = **(_QWORD **)v40;
        if ( !*(_WORD *)(v101 + 36) )
        {
LABEL_211:
          v499 = *(_QWORD *)(v101 + 40);
          v500 = *(_WORD *)(v101 + 48);
          goto LABEL_184;
        }
        v102 = *(_BYTE *)(v101 + 1);
        if ( v102 == 11 )
        {
          if ( *(_DWORD *)(v101 + 24) == 99 )
            goto LABEL_182;
        }
        else if ( v102 == 8 )
        {
          goto LABEL_210;
        }
        if ( v102 != 9 )
          goto LABEL_211;
LABEL_210:
        if ( *(_DWORD *)(v101 + 24) != 99 )
          goto LABEL_211;
LABEL_182:
        v534 = *(_DWORD *)(v101 + 32);
        v535 = *(_WORD *)(v101 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v534, v44) )
          goto LABEL_211;
        PageHeader::GetIcxLsn(v101, &v499);
LABEL_184:
        v103 = *(_DWORD *)(v34 + 8456);
        do
        {
          v104 = v103 & 0xFFFFFFFE;
          v573 = *(_QWORD *)(v34 + 8444);
          v574 = *(_DWORD *)(v34 + 8452);
          _InterlockedOr(v426, 0);
          v103 = *(_DWORD *)(v34 + 8456);
        }
        while ( v104 != v103 );
        if ( (unsigned int)v573 >= (unsigned int)v499
          && ((_DWORD)v573 != (_DWORD)v499
           || HIDWORD(v573) >= HIDWORD(v499) && (HIDWORD(v573) != HIDWORD(v499) || (unsigned __int16)v574 >= v500)) )
        {
          goto LABEL_26;
        }
        if ( !*(_BYTE *)(v34 + 27336)
          && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL)
                       + 96LL) != *(_QWORD *)(v34 + 8480)
          && !RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v34) )
        {
          break;
        }
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL)
                       + 96LL) == *(_QWORD *)(v34 + 8480)
          || RecoveryUnit::IsParallelRedoThread((RecoveryUnit *)v34) )
        {
          goto LABEL_26;
        }
        if ( !SETLSFromTlsMaybeNull )
          SETLSFromTlsMaybeNull = GetSETLSFromTlsMaybeNull();
        v107 = **(_QWORD **)v40;
        if ( !*(_WORD *)(v107 + 36) )
          goto LABEL_215;
        v108 = *(_BYTE *)(v107 + 1);
        if ( v108 != 11 )
        {
          if ( v108 != 8 )
          {
LABEL_213:
            if ( v108 != 9 )
              goto LABEL_215;
          }
          if ( *(_DWORD *)(v107 + 24) != 99 )
            goto LABEL_215;
          goto LABEL_201;
        }
        if ( *(_DWORD *)(v107 + 24) != 99 )
          goto LABEL_213;
LABEL_201:
        v532 = *(_DWORD *)(v107 + 32);
        v533 = *(_WORD *)(v107 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v532, v106) )
        {
          PageHeader::GetIcxLsn(v107, &v536);
          v109 = v537;
          v110 = v536;
          goto LABEL_203;
        }
LABEL_215:
        v110 = *(_QWORD *)(v107 + 40);
        v536 = v110;
        v109 = *(_WORD *)(v107 + 48);
        v537 = v109;
LABEL_203:
        if ( !*(_QWORD *)v40 )
          goto LABEL_207;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_207;
        }
        v111 = *((__int16 *)v40 + 6);
        v112 = *(__int64 **)v40;
        if ( (*((_WORD *)v112 + 49) & 8) != 0 )
        {
          if ( v111 == 3 )
          {
            v111 = 4;
LABEL_219:
            if ( (*((_DWORD *)v112 + 25) & 8) != 0 )
            {
              v113 = v112[18];
              if ( v113 )
              {
                if ( *(_QWORD *)(v113 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v113 + 1880), v112, (unsigned int)v111);
                }
              }
            }
            goto LABEL_223;
          }
          if ( v111 >= 2 )
            goto LABEL_219;
        }
LABEL_223:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v112 + 25) & 8) != 0
          && v111 >= 3
          && (*((_DWORD *)v112 + 25) & 0xC0000000) != 0x40000000
          && *v112
          && VirtualProtect((LPVOID)*v112, 0x2000u, 2u, &v613) )
        {
          _InterlockedAnd((volatile signed __int32 *)v112 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v112 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v112 + 19, (unsigned int)v111);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v112, 0, (unsigned int)v111);
        v40 = v439;
        *((_WORD *)v439 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v444;
LABEL_207:
        v604 = v110;
        v605 = v109;
        v427 = 0;
        RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v34 + 1832), &v604, 4);
      }
      v114 = *(_DWORD *)(v34 + 8456);
      do
      {
        v115 = v114 & 0xFFFFFFFE;
        v116 = *(LSN *)(v34 + 8444);
        v575 = v116;
        v576 = *(_DWORD *)(v34 + 8452);
        _InterlockedOr(v426, 0);
        v114 = *(_DWORD *)(v34 + 8456);
      }
      while ( v115 != v114 );
      v606 = v116;
      v117 = v576;
      v607 = v576;
      v118 = **(_QWORD **)v439;
      if ( !*(_WORD *)(v118 + 36) )
        goto LABEL_252;
      v119 = *(_BYTE *)(v118 + 1);
      if ( v119 != 11 )
      {
        if ( v119 != 8 )
          goto LABEL_250;
        goto LABEL_251;
      }
      if ( *(_DWORD *)(v118 + 24) == 99 )
        goto LABEL_241;
LABEL_250:
      if ( v119 == 9 )
      {
LABEL_251:
        if ( *(_DWORD *)(v118 + 24) != 99 )
          goto LABEL_252;
LABEL_241:
        v530 = *(_DWORD *)(v118 + 32);
        v531 = *(_WORD *)(v118 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v530, v105) )
          goto LABEL_252;
        PageHeader::GetIcxLsn(v118, &v487);
        v120 = v488;
      }
      else
      {
LABEL_252:
        v487 = *(LSN *)(v118 + 40);
        v120 = *(_WORD *)(v118 + 48);
        v488 = v120;
      }
      if ( v575.LowPart < v487.LowPart
        || v575.LowPart == v487.LowPart
        && (v575.HighPart < (unsigned int)v487.HighPart || v575.HighPart == v487.HighPart && v117 < v120) )
      {
        LSN::FormatAsHexString(&v487, v751, &v541);
        LSN::FormatAsHexString(&v606, v752, &v541);
        if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
        {
          v662 = 393216;
          v663 = 0;
          v664 = &v667;
          v665 = &v685;
          v686 = 0;
          v666 = 0;
          v687 = 0;
          v667 = &v688;
          v668 = 52;
          v669 = 5;
          v670 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
          v671 = 16;
          v672 = 5;
          v673 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
          v674 = 16;
          v675 = 6;
          v676 = 0;
          v677 = 0;
          v678 = 7;
          v679 = 0;
          v680 = 0;
          v681 = 8;
          v682 = 0;
          v683 = 0;
          v684 = 9;
          v688 = *(unsigned __int16 *)(v34 + 1720);
          v689 = v442;
          v690 = v441;
          v691 = -1;
          v40 = v439;
          v692 = *(_BYTE *)(**(_QWORD **)v439 + 1LL);
          v670 = (GUID *)(v122 + 596);
          v673 = (GUID *)(v122 + 580);
          v123 = -1;
          do
            ++v123;
          while ( v751[v123] );
          v676 = v751;
          v677 = 2 * v123;
          v124 = -1;
          do
            ++v124;
          while ( v752[v124] );
          v679 = v752;
          v680 = 2 * v124;
          v542 = 0;
          v125 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v122, &v542);
          v126 = (int *)v125;
          if ( v125 )
          {
            v127 = -1;
            do
              ++v127;
            while ( *(_WORD *)(v125 + 2 * v127) );
            v128 = 2 * v127;
          }
          else
          {
            v128 = 0;
          }
          v129 = v664;
          v664[10] = v126;
          *((_DWORD *)v129 + 22) = v128;
          *((_DWORD *)v129 + 23) = 9;
          XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v661);
        }
        else
        {
          v40 = v439;
        }
      }
      else
      {
        v40 = v439;
      }
LABEL_26:
      v45 = v482;
      if ( *(_QWORD *)v482 )
      {
        if ( (*((_DWORD *)v40 + 3) & 0xFF000000) != 0 )
        {
          ++*(_DWORD *)(*(_QWORD *)v482 + 4LL);
          if ( *((_BYTE *)v40 + 16) )
            ++*(_DWORD *)(*(_QWORD *)v45 + 8LL);
        }
        ++**(_DWORD **)v45;
      }
      if ( (_DWORD)v603 )
        HoBtAccess::UpdateLatchWaitStats(
          *((_QWORD *)v45 + 11),
          *(unsigned __int8 *)(**(_QWORD **)v40 + 1LL),
          &v602,
          *((unsigned int *)v45 + 94));
      v46 = **(_QWORD **)v40;
      v47 = v436;
      v48 = v497;
      if ( a6 != 1 || *((_QWORD *)v436[1] + 48) )
        goto LABEL_32;
      v9 = *((_QWORD *)v497 + 1);
      if ( !v9 || (v121 = *(_QWORD *)(v9 + 8), *(_BYTE *)(v121 + 63)) )
      {
        v10 = *(_QWORD *)(*((_QWORD *)v497 + 2) + 8LL);
        if ( *((_DWORD *)v497 + 16) == 2 )
        {
          if ( *(_QWORD *)(v10 + 1144) )
            v10 = *(_QWORD *)(v10 + 1144);
          v11 = *(_WORD *)(v10 + 1096);
          if ( *(_DWORD *)(v10 + 1092) && v11 )
          {
            LODWORD(v470) = *(_DWORD *)(v10 + 1092);
            HIDWORD(v470) = v11;
            v12 = &v470;
          }
          else
          {
            v470 = 0;
            v12 = &v470;
          }
        }
        else
        {
          v130 = *(_WORD *)(v10 + 1056);
          v131 = *(_WORD *)(v10 + 1058);
          if ( *(_DWORD *)(v10 + 1052) && v130 )
          {
            LODWORD(v452) = *(_DWORD *)(v10 + 1052);
            WORD2(v452) = v130;
            HIWORD(v452) = v131;
          }
          else
          {
            v452 = 0;
          }
          v12 = &v452;
        }
        v13 = *(_DWORD *)v12;
        v473 = *(_DWORD *)v12;
        v14 = *((_WORD *)v12 + 2);
      }
      else
      {
        v13 = *(_DWORD *)(v121 + 56);
        v473 = v13;
        v14 = *(_WORD *)(v121 + 60);
      }
      v474 = v14;
      if ( !v13 && !v14 )
        goto LABEL_107;
      v15 = *((_QWORD *)v497 + 1);
      if ( !v15 || (v132 = *(_QWORD *)(v15 + 8), *(_BYTE *)(v132 + 63)) )
      {
        if ( *((_DWORD *)v497 + 16) == 2 )
        {
          v16 = (int *)*((_QWORD *)v497 + 6);
          v546 = *v16;
          v547 = *((_WORD *)v16 + 2);
          v548 = 0;
          v17 = &v546;
        }
        else
        {
          v133 = (int *)*((_QWORD *)v497 + 5);
          v549 = *v133;
          v550 = *((_WORD *)v133 + 2);
          v551 = 0;
          v17 = &v549;
        }
        v467 = *v17;
        v18 = *((_WORD *)v17 + 2);
      }
      else
      {
        v467 = *(_DWORD *)(v132 + 8);
        v18 = *(_WORD *)(v132 + 12);
      }
      v469 = 0;
      v468 = v18;
      v19 = v436[4];
      if ( !v13 && !v14 )
        goto LABEL_107;
      v750 = 0;
      v746 = v441;
      v747 = v442;
      v748 = 0;
      v745 = 0;
      v749 = 0;
      v20 = IsPageInAllocUnitInternal(v19, &v467, &v473, &v745, 7, v40);
      v47 = v436;
      if ( v20 )
      {
LABEL_32:
        v49 = v454;
      }
      else
      {
LABEL_107:
        v49 = 1;
        v454 = 1;
      }
      v50 = v446;
      v51 = *((__int16 *)v446 + 3);
      if ( (unsigned int)v51 >= *(unsigned __int16 *)(v46 + 22) || (v52 = 1, !*(_WORD *)(v46 + 2 * (v484 - v51))) )
        v52 = 0;
      v53 = *((_QWORD *)v48 + 1);
      if ( !v53 || (v134 = *(_QWORD *)(v53 + 8), *(_BYTE *)(v134 + 63)) )
      {
        if ( *((_DWORD *)v48 + 16) == 2 )
        {
          v54 = (int *)*((_QWORD *)v48 + 6);
          v552 = *v54;
          v553 = *((_WORD *)v54 + 2);
          v554 = 0;
          v55 = &v552;
        }
        else
        {
          v135 = (int *)*((_QWORD *)v48 + 5);
          v555 = *v135;
          v556 = *((_WORD *)v135 + 2);
          v557 = 0;
          v55 = &v555;
        }
        v56 = *v55;
        v558 = *v55;
        v57 = *((_WORD *)v55 + 2);
      }
      else
      {
        v56 = *(_DWORD *)(v134 + 8);
        v558 = v56;
        v57 = *(_WORD *)(v134 + 12);
      }
      v559 = v57;
      v58 = 0;
      if ( *(_DWORD *)(v46 + 24) == v56 )
      {
        v59 = *(_WORD *)(v46 + 6);
        if ( v59 == v57 || (unsigned __int16)(v57 | v59) <= 1u )
          v58 = 1;
      }
      if ( v49 || !v52 || !(_DWORD)v58 )
        BlobBase::TableCorruptException(*(_WORD *)(*((_QWORD *)*v47 + 6) + 1720LL), v446, v51, 9);
      v60 = *((__int16 *)v50 + 3);
      v703 = *((__int16 *)v50 + 3);
      if ( *(char *)(v46 + 2) >= 0 )
      {
        v61 = 0;
        goto LABEL_47;
      }
      v136 = (unsigned __int8 *)(v46 + 96);
      _mm_prefetch((const char *)(v46 + 96), 0);
      if ( v696 && (v61 = v700) != 0 )
      {
        v137 = -1;
      }
      else
      {
        v707 = 0;
        v709 = 0u;
        v710 = 0;
        v712 = 0;
        v704 = 0;
        v137 = -1;
        v705 = 0xFFFFu;
        v708 = 0;
        memset(v706, 0, sizeof(v706));
        v711 = 0u;
        v61 = &v704;
      }
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_302;
      v138 = *(_BYTE *)(v46 + 1);
      if ( v138 != 11 )
      {
        if ( v138 != 8 )
          goto LABEL_300;
        goto LABEL_301;
      }
      if ( *(_DWORD *)(v46 + 24) == 99 )
        goto LABEL_293;
LABEL_300:
      if ( v138 == 9 )
      {
LABEL_301:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_302;
LABEL_293:
        v526 = *(_DWORD *)(v46 + 32);
        v527 = *(_WORD *)(v46 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v526, v58) )
          goto LABEL_302;
        PageHeader::GetIcxLsn(v46, &v501);
      }
      else
      {
LABEL_302:
        v501 = *(_QWORD *)(v46 + 40);
        v502 = *(_WORD *)(v46 + 48);
      }
      *(_QWORD *)v61 = v136;
      v139 = v502;
      v140 = HIDWORD(v501);
      *((_DWORD *)v61 + 24) = v501;
      *((_DWORD *)v61 + 25) = v140;
      *((_WORD *)v61 + 52) = v139;
      *((_DWORD *)v61 + 27) = *(_DWORD *)(v46 + 32);
      *((_WORD *)v61 + 56) = *(_WORD *)(v46 + 36);
      *((_WORD *)v61 + 57) = 0;
      v141 = 3LL * *v136;
      v601 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v136);
      v142 = word_102883984[v141];
      *((_WORD *)v61 + 8) = v137;
      *((_QWORD *)v61 + 3) = 0;
      *((_DWORD *)v61 + 5) = 0;
      *(_QWORD *)((char *)v61 + 46) = 0;
      *((_QWORD *)v61 + 7) = 0;
      *((_QWORD *)v61 + 4) = 0;
      *((_QWORD *)v61 + 9) = 0;
      *((_QWORD *)v61 + 10) = 0;
      *((_WORD *)v61 + 44) = 0;
      if ( (**(_BYTE **)v61 & 2) != 0 )
      {
        v143 = &v136[v142];
        if ( (v136[v142] & 1) != 0 )
        {
          *((_WORD *)v61 + 8) = 1;
          *((_QWORD *)v61 + 3) = v143;
          v144 = *v143;
          switch ( *((_BYTE *)&loc_1005A8CD0 + (*v143 & 0x1C)) )
          {
            case 0:
              if ( (v143[1] & 0x80u) != 0 )
              {
                v151 = *(_WORD *)(v143 + 1);
                *((_WORD *)v61 + 9) = v151;
                v145 = 3;
                v146 = HIBYTE(v151) | ((v151 & 0x7F) << 8);
              }
              else
              {
                v145 = 2;
                v146 = v143[1];
              }
              *((_WORD *)v61 + 9) = v146;
              *((_WORD *)v61 + 20) = v145;
              *((_WORD *)v61 + 22) = v145 + (((unsigned int)*((unsigned __int16 *)v61 + 9) + 1) >> 1);
              v147 = *((unsigned __int16 *)v61 + 9);
              if ( v147 > 0x1E )
                *((_WORD *)v61 + 21) = (int)(v147 - 1) / 30;
              else
                *((_WORD *)v61 + 21) = 0;
              *((_DWORD *)v61 + 5) = 0;
              *((_DWORD *)v61 + 16) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 4) = 0;
              break;
            case 1:
              if ( (v144 & 0x1C) != 4 || (v152 = 1, (v144 & 2) == 0) )
                v152 = 0;
              *((_DWORD *)v61 + 5) = 0;
              *((_QWORD *)v61 + 5) = 0;
              *((_WORD *)v61 + 9) = 0;
              *((_QWORD *)v61 + 6) = 0;
              *((_QWORD *)v61 + 4) = 0;
              *((_DWORD *)v61 + 16) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 3) = v143;
              if ( v152 )
              {
                *((_DWORD *)v61 + 5) = v434;
                *((_DWORD *)v61 + 16) = 0;
                *((_DWORD *)v61 + 16) = 1;
              }
              else
              {
                *((_DWORD *)v61 + 5) = 1;
                *((_DWORD *)v61 + 16) = 0;
              }
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 4) = 0;
              break;
            case 2:
              *((_QWORD *)v61 + 5) = 0;
              *((_WORD *)v61 + 9) = 0;
              *((_QWORD *)v61 + 6) = 0;
              *((_QWORD *)v61 + 4) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 3) = v143;
              *((_DWORD *)v61 + 5) = 9;
              *((_DWORD *)v61 + 16) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 4) = 0;
              break;
            case 3:
              utassert_fail(
                1u,
                "FALSE",
                "Sql\\Ntdbms\\storeng\\drs\\include\\cdrecord.inl",
                207,
                "Invalid switch value");
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 4) = 0;
              break;
          }
        }
        else
        {
          *((_WORD *)v61 + 8) = 0;
          v153 = 0;
          *((_QWORD *)v61 + 3) = v143;
          *((_DWORD *)v61 + 5) = 0;
          *(_DWORD *)((char *)v61 + 54) = 0;
          switch ( *v143 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v153 = *((unsigned __int16 *)v143 + 1);
              if ( (unsigned int)(v153 - 1) > 0x1F9D )
                RaiseInconsistencyError(&v136[v142], 6);
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
              v153 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v153 = 1;
              break;
          }
          *((_DWORD *)v61 + 8) = v153;
          *(_QWORD *)((char *)v61 + 46) = 0;
        }
      }
      if ( (**(_BYTE **)v61 & 4) != 0 )
      {
        if ( HIWORD(v601) )
          v148 = &v136[*(unsigned __int16 *)&v136[2 * SHIWORD(v601) + 1]];
        else
          v148 = &v136[v142];
        *((_QWORD *)v61 + 9) = v148;
        v149 = *(_WORD *)v148;
        *((_QWORD *)v61 + 10) = v148 + 2;
        *((_WORD *)v61 + 44) = 2 * (v149 + 1);
      }
      v150 = (PageComprInfoCache *)*((_QWORD *)v61 + 1);
      if ( v150 )
        PageComprInfoCache::Init(v150, (const struct PageComprInfo *)v61);
LABEL_47:
      v62 = *(unsigned __int16 *)(v46 + 14);
      v63 = (unsigned __int8 *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v484 - v60)));
      v93 = (*v63 & 1) == 0;
      v699 = (struct XDES *)v63;
      if ( v93 )
      {
        v696 = 0;
        v64 = 0;
        v698 = 0;
        *(_DWORD *)&v701[14] = 0;
        v65 = *v63 & 0xE;
        switch ( *v63 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v62 = *((unsigned __int16 *)v63 + 1);
            if ( v62 - 1 > 0x1F9D )
            {
              RaiseInconsistencyError(v63, 6);
              goto LABEL_349;
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
LABEL_349:
            v64 = v698;
            break;
          case 4:
            v62 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v62 = 1;
            break;
        }
        LODWORD(v700) = v62;
        *(_QWORD *)&v701[6] = v46 + 0x2000;
        LODWORD(v61) = v62;
      }
      else
      {
        v696 = 1;
        v65 = *v63;
        switch ( *v63 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( (v63[1] & 0x80u) != 0 )
            {
              v154 = HIBYTE(*(_WORD *)(v63 + 1)) | ((*(_WORD *)(v63 + 1) & 0x7F) << 8);
              v697 = v154;
              v65 = 3;
              *(_WORD *)v701 = 3;
            }
            else
            {
              v154 = v63[1];
              v697 = v154;
              v65 = 2;
              *(_WORD *)v701 = 2;
            }
            *(_WORD *)&v701[4] = v65 + (((unsigned int)v154 + 1) >> 1);
            if ( v154 > 0x1Eu )
            {
              v65 = (unsigned int)((v154 - 1) / 30);
              *(_WORD *)&v701[2] = (v154 - 1) / 30;
            }
            else
            {
              *(_WORD *)&v701[2] = 0;
            }
            v64 = 0;
            v698 = 0;
            v702 = 0;
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
            v64 = v698;
            break;
          case 4:
            if ( (v65 & 0x1C) == 4 && (v65 & 2) != 0 )
            {
              *(_QWORD *)v701 = 0;
              v697 = 0;
              *(_QWORD *)&v701[8] = 0;
              v64 = v434;
              v698 = v434;
              v702 = 1;
            }
            else
            {
              *(_QWORD *)v701 = 0;
              v697 = 0;
              *(_QWORD *)&v701[8] = 0;
              v64 = 1;
              v698 = 1;
              v702 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v701 = 0;
            v697 = 0;
            *(_QWORD *)&v701[8] = 0;
            v64 = 9;
            v698 = 9;
            v702 = 0;
            break;
        }
        *(_QWORD *)&v701[16] = v46 + 0x2000;
        v700 = v61;
        v62 = (unsigned int)v61;
      }
      v66 = v699;
      v482 = v699;
      if ( v696 )
      {
        if ( !v64 )
        {
          CDRecord::Resize((CDRecord *)&v697);
          v64 = v698;
        }
        if ( v64 >= 9 )
          goto LABEL_65;
        if ( (*(_BYTE *)v699 & 0x1C) != 0 )
        {
          v176 = (*(_BYTE *)v699 & 0x1C) == 12;
LABEL_432:
          if ( !v176 )
            goto LABEL_65;
        }
LABEL_433:
        v64 = 9;
        goto LABEL_65;
      }
      if ( !v64 )
      {
        v697 = 0;
        HIDWORD(v700) = v62;
        v67 = *(_BYTE *)v699;
        HIDWORD(v700) = (_DWORD)v61;
        if ( (v67 & 0x10) != 0 )
        {
          if ( (*(_BYTE *)v699 & 0x10) != 0 )
            v155 = *(unsigned __int16 *)((char *)v699 + v62);
          else
            v155 = 0;
          LODWORD(v61) = ((unsigned int)(v155 + 7) >> 3) + (_DWORD)v61 + 2;
          HIDWORD(v700) = (_DWORD)v61;
        }
        if ( (*(_BYTE *)v699 & 0x20) != 0 )
        {
          v156 = (unsigned __int16 *)((char *)v699 + (unsigned int)v61);
          v157 = *v156;
          *(_WORD *)&v701[4] = v157;
          if ( !v157 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v158 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v158 )
              {
                v159 = *(_QWORD *)(v158 + 96);
                if ( v159 )
                {
                  if ( *(_BYTE *)(v159 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(v699, 3);
            v157 = *(_WORD *)&v701[4];
            LODWORD(v61) = HIDWORD(v700);
          }
          v160 = (_DWORD)v61 + 2 * (v157 + 1);
          *(_DWORD *)v701 = v160;
          if ( v160 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v161 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v161 )
              {
                v162 = *(_QWORD *)(v161 + 96);
                if ( v162 )
                {
                  if ( *(_BYTE *)(v162 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(v699, 4);
            v157 = *(_WORD *)&v701[4];
            v160 = *(_DWORD *)v701;
            LODWORD(v61) = HIDWORD(v700);
          }
          v64 = v156[v157] & 0x7FFF;
          v698 = v64;
          if ( v160 > v64 )
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
            RaiseInconsistencyError(v699, 4);
            v157 = *(_WORD *)&v701[4];
            v160 = *(_DWORD *)v701;
            LODWORD(v61) = HIDWORD(v700);
            v64 = v698;
          }
          while ( 1 )
          {
            v65 = v157;
            if ( (v156[v157] & 0x8000u) == 0 )
              break;
            v165 = (char *)v699 + (unsigned int)v61;
            if ( v157 == 1 )
              v166 = v160;
            else
              v166 = *(_WORD *)&v165[2 * v157 - 2] & 0x7FFF;
            v65 = *(_WORD *)&v165[2 * v157] & 0x7FFF;
            if ( v166 < v160 || (unsigned int)v65 < v166 )
            {
              RaiseInconsistencyError(v699, 7);
              v157 = *(_WORD *)&v701[4];
              v160 = *(_DWORD *)v701;
              LODWORD(v61) = HIDWORD(v700);
              v64 = v698;
            }
            if ( v166 < v160 || v166 > v64 )
              goto LABEL_64;
            v65 = *(unsigned __int16 *)((char *)v699 + v166);
            if ( (_WORD)v65 == 5 )
            {
              v697 |= 2u;
              *(_WORD *)&v701[4] = v157 - 1;
              *(_WORD *)&v701[18] = v166;
              v167 = (char *)v699 + (unsigned __int16)v166;
              v168 = *((_WORD *)v167 + 1);
              if ( (v168 & 0x4000) != 0 )
                v169 = (*(_WORD *)&v701[20] ^ v168) & 0x3800 ^ *(_WORD *)&v701[20];
              else
                v169 = *(_WORD *)&v701[20] & 0xC7FF;
              *(_WORD *)&v701[20] = v169;
              v170 = *((_WORD *)v167 + 1) ^ v169;
              v65 = 2047;
              *(_WORD *)&v701[20] = v170 & 0x7FF ^ v169;
              break;
            }
            if ( (unsigned __int16)v65 >= 0x400u )
            {
              v697 |= 1u;
              v93 = v157-- == 1;
              *(_WORD *)&v701[4] = v157;
              if ( !v93 )
                continue;
            }
            break;
          }
        }
        else
        {
          v64 = (unsigned int)v61;
          v698 = (unsigned int)v61;
          *(_WORD *)&v701[4] = 0;
          *(_DWORD *)v701 = (_DWORD)v61;
        }
        if ( (*(_BYTE *)v699 & 0x40) != 0 )
        {
          *(_DWORD *)&v701[14] = v64;
          v698 = v64 + 14;
          VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v697);
          v65 = HIWORD(*(_QWORD *)VersioningInfo);
          v69 = 0;
          if ( (((__int16)v65 ^ ((unsigned int)(__int16)v65 >> 1)) & 0x2000) != 0 )
          {
            if ( (v65 & 0x4000) != 0 )
              LOWORD(v65) = v65 | 0x2000;
            else
              LOWORD(v65) = v65 & 0xDFFF;
          }
          if ( (_WORD)v65 == 0xFFFC )
            v69 = (unsigned __int16)WORD2(*(_QWORD *)VersioningInfo) >> 5;
          v64 = v69 + v698;
          v698 += v69;
        }
        else
        {
          *(_DWORD *)&v701[14] = 0;
        }
        if ( *(_QWORD *)&v701[6] && *(_QWORD *)&v701[6] < (unsigned __int64)v699 + v64 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(v699, 18);
          v64 = v698;
        }
        if ( v64 - 1 > 0x3F3B )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(v699, 5);
          v64 = v698;
        }
      }
LABEL_64:
      if ( v64 < 9 )
      {
        v175 = *(_BYTE *)v699 & 0xE;
        if ( v175 )
        {
          v176 = v175 == 12;
          goto LABEL_432;
        }
        goto LABEL_433;
      }
LABEL_65:
      *v483 = v64;
      v70 = v435;
      v71 = v436;
      if ( v435 )
        goto LABEL_66;
      if ( !*((_BYTE *)v436[4] + 7390) )
        goto LABEL_81;
      v177 = v593 & 0xFFFFFEFC | 2;
      v593 = v177;
      v65 = (__int64)v436[1];
      v178 = *(_QWORD *)(v65 + 88);
      v179 = (*(unsigned int *)(v178 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v178 + 24) << 32)) << 16;
      *((_QWORD *)&v595 + 1) = *(_QWORD *)(v65 + 48);
      v596 = v179;
      *(_QWORD *)&v595 = v178;
      v593 = v177 & 0xFFFFFDE3;
      if ( !(_QWORD)v592 || (v180 = (_DWORD)v435 + 32, (*(_BYTE *)(v592 + 48) & 1) == 0) )
        v180 = 0;
      v181 = v177 & 0xFFFFFD43 | v180 & 0xFFFFFF7F;
      if ( *((_QWORD *)&v592 + 1) )
      {
        v181 |= 1u;
LABEL_449:
        v182 = 0;
        goto LABEL_447;
      }
      if ( (v181 & 0x20) == 0 )
        goto LABEL_449;
      v181 |= 1u;
      if ( (v181 & 0x20) == 0 )
        goto LABEL_449;
      v182 = 64;
LABEL_447:
      v593 = v182 | v181 & 0xFFFFFEBD;
      v594 &= 0xFCu;
      v70 = (struct VersionScanParams *)&v592;
      v435 = (struct VersionScanParams *)&v592;
LABEL_66:
      LockMode = LobContext::GetLockMode(v436[1], v65);
      v75 = v581[1];
      if ( LockMode == 3 )
        v76 = (_BYTE *)*((_QWORD *)v75 + 8);
      else
        v76 = (_BYTE *)*((_QWORD *)v75 + 9);
      LOBYTE(v73) = !*(_DWORD *)(*((_QWORD *)v75 + 8) + 28LL) || v76[1] == 1 && !v76[2] && !v76[3];
      if ( *((_QWORD *)v71[4] + 869) )
      {
        if ( (_BYTE)v73 )
        {
          if ( (unsigned __int8)LobContext::GetLockMode(v75, v73) != 3 )
            goto LABEL_72;
          if ( v76[2] )
            goto LABEL_72;
          if ( v76[3] )
            goto LABEL_72;
          v183 = *((_DWORD *)v70 + 4);
          if ( (v183 & 1) == 0 )
            goto LABEL_72;
          if ( (v183 & 0x40) != 0 )
            goto LABEL_72;
          v184 = *((_QWORD *)*v71 + 6);
          if ( !*(_BYTE *)(v184 + 7378) || *(_BYTE *)(v184 + 8272) )
            goto LABEL_72;
          v21 = v451;
          v75 = v451[1];
        }
        else
        {
          v21 = v451;
        }
        v77 = v439;
        XdesLockIfNecessary = GetXdesLockIfNecessary(
                                *((_QWORD *)*v71 + 6),
                                *v71,
                                &v696,
                                *(unsigned int *)(*((_QWORD *)v75 + 8) + 24LL),
                                v439);
        v22 = v444;
        v27 = v463;
        if ( XdesLockIfNecessary == 1 )
          goto LABEL_466;
        v71 = v436;
      }
      else
      {
LABEL_72:
        v77 = v439;
      }
      v735 = -1;
      v738 = 0;
      v737 = 0;
      *(_QWORD *)&v740[6] = 0;
      *(_QWORD *)&v740[16] = 0;
      v739 = 0;
      v742 = -1;
      v78 = *(_BYTE *)(v46 + 2);
      v730 = 1;
      if ( (v78 & 0x20) == 0 || *((_WORD *)v77 + 6) != 4 )
        goto LABEL_74;
      v186 = *(_WORD *)(*((_QWORD *)*v71 + 6) + 1720LL);
      v730 = 6;
      v729 = v186;
      v728 = 0;
      v727 = *(_DWORD *)(v46 + 32);
      LOWORD(v728) = *(_WORD *)(v46 + 36);
      LOBYTE(v429) = 0;
      LOBYTE(v428) = 1;
      LOBYTE(v74) = 8;
      if ( (int)BlobBase::GetLock(v71, &v727, v74, 1, 0, v428, (_DWORD)v429) < 0 )
      {
        _mm_lfence();
        PageRef::Unlatch(v77);
        LOBYTE(v429) = 0;
        LOBYTE(v428) = 1;
        LOBYTE(v187) = 8;
        Lock = BlobBase::GetLock(v71, &v727, v187, 0, 0, v428, (_DWORD)v429);
        LOBYTE(v189) = 13;
        goto LABEL_465;
      }
      v190 = 0;
      v191 = *(unsigned __int16 *)(v46 + 22);
      if ( !*(_WORD *)(v46 + 22) )
        goto LABEL_471;
      v192 = 0;
      v193 = (_WORD *)(v46 + 8190);
      while ( !*v193 )
      {
        ++v190;
        ++v192;
        --v193;
        if ( v192 >= v191 )
          goto LABEL_471;
      }
      if ( v190 == -1 )
      {
LABEL_471:
        PageRef::SetBulkInsertBitOnPage(v77, 0);
LABEL_74:
        v79 = v436;
        break;
      }
      _mm_lfence();
      v742 = v190;
      if ( *(char *)(v46 + 2) >= 0 )
      {
        v204 = 0;
        goto LABEL_492;
      }
      v208 = (unsigned __int8 *)(v46 + 96);
      _mm_prefetch((const char *)(v46 + 96), 0);
      if ( v735 && (v204 = v739) != 0 )
      {
        v209 = -1;
      }
      else
      {
        v744 = 0;
        v743[0] = 0;
        v209 = -1;
        v743[1] = 0xFFFFu;
        memset(&v743[2], 0, 80);
        v204 = v743;
      }
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_509;
      v210 = *(_BYTE *)(v46 + 1);
      if ( v210 != 11 )
      {
        if ( v210 != 8 )
          goto LABEL_507;
        goto LABEL_508;
      }
      if ( *(_DWORD *)(v46 + 24) == 99 )
        goto LABEL_500;
LABEL_507:
      if ( v210 == 9 )
      {
LABEL_508:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_509;
LABEL_500:
        v528 = *(_DWORD *)(v46 + 32);
        v529 = *(_WORD *)(v46 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v528, v191) )
          goto LABEL_509;
        PageHeader::GetIcxLsn(v46, &v503);
      }
      else
      {
LABEL_509:
        v503 = *(_QWORD *)(v46 + 40);
        v504 = *(_WORD *)(v46 + 48);
      }
      *(_QWORD *)v204 = v208;
      v211 = v504;
      v212 = HIDWORD(v503);
      *((_DWORD *)v204 + 24) = v503;
      *((_DWORD *)v204 + 25) = v212;
      *((_WORD *)v204 + 52) = v211;
      *((_DWORD *)v204 + 27) = *(_DWORD *)(v46 + 32);
      *((_WORD *)v204 + 56) = *(_WORD *)(v46 + 36);
      *((_WORD *)v204 + 57) = 0;
      v213 = 3LL * *v208;
      v600 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v208);
      v214 = word_102883984[v213];
      *((_WORD *)v204 + 8) = v209;
      *((_QWORD *)v204 + 3) = 0;
      *((_DWORD *)v204 + 5) = 0;
      *(_QWORD *)((char *)v204 + 46) = 0;
      *((_QWORD *)v204 + 7) = 0;
      *((_QWORD *)v204 + 4) = 0;
      *((_QWORD *)v204 + 9) = 0;
      *((_QWORD *)v204 + 10) = 0;
      *((_WORD *)v204 + 44) = 0;
      if ( (**(_BYTE **)v204 & 2) != 0 )
      {
        v215 = &v208[v214];
        if ( (v208[v214] & 1) != 0 )
        {
          *((_WORD *)v204 + 8) = 1;
          *((_QWORD *)v204 + 3) = v215;
          v216 = *v215;
          switch ( *v215 & 0x1C )
          {
            case 0:
            case 0xC:
            case 0x10:
            case 0x14:
            case 0x18:
            case 0x1C:
              if ( (v215[1] & 0x80u) != 0 )
              {
                v223 = *(_WORD *)(v215 + 1);
                *((_WORD *)v204 + 9) = v223;
                v217 = 3;
                v218 = HIBYTE(v223) | ((v223 & 0x7F) << 8);
              }
              else
              {
                v217 = 2;
                v218 = v215[1];
              }
              *((_WORD *)v204 + 9) = v218;
              *((_WORD *)v204 + 20) = v217;
              *((_WORD *)v204 + 22) = v217 + (((unsigned int)*((unsigned __int16 *)v204 + 9) + 1) >> 1);
              v219 = *((unsigned __int16 *)v204 + 9);
              if ( v219 > 0x1E )
                *((_WORD *)v204 + 21) = (int)(v219 - 1) / 30;
              else
                *((_WORD *)v204 + 21) = 0;
              *((_DWORD *)v204 + 5) = 0;
              *((_DWORD *)v204 + 16) = 0;
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 4) = 0;
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
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 4) = 0;
              break;
            case 4:
              if ( (v216 & 0x1C) != 4 || (v224 = 1, (v216 & 2) == 0) )
                v224 = 0;
              *((_DWORD *)v204 + 5) = 0;
              *((_QWORD *)v204 + 5) = 0;
              *((_WORD *)v204 + 9) = 0;
              *((_QWORD *)v204 + 6) = 0;
              *((_QWORD *)v204 + 4) = 0;
              *((_DWORD *)v204 + 16) = 0;
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 3) = v215;
              if ( v224 )
              {
                *((_DWORD *)v204 + 5) = v434;
                *((_DWORD *)v204 + 16) = 0;
                *((_DWORD *)v204 + 16) = 1;
              }
              else
              {
                *((_DWORD *)v204 + 5) = 1;
                *((_DWORD *)v204 + 16) = 0;
              }
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 4) = 0;
              break;
            case 8:
              *((_QWORD *)v204 + 5) = 0;
              *((_WORD *)v204 + 9) = 0;
              *((_QWORD *)v204 + 6) = 0;
              *((_QWORD *)v204 + 4) = 0;
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 3) = v215;
              *((_DWORD *)v204 + 5) = 9;
              *((_DWORD *)v204 + 16) = 0;
              *((_QWORD *)v204 + 7) = 0;
              *((_QWORD *)v204 + 4) = 0;
              break;
          }
        }
        else
        {
          *((_WORD *)v204 + 8) = 0;
          v225 = 0;
          *((_QWORD *)v204 + 3) = v215;
          *((_DWORD *)v204 + 5) = 0;
          *(_DWORD *)((char *)v204 + 54) = 0;
          switch ( *v215 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v225 = *((unsigned __int16 *)v215 + 1);
              if ( (unsigned int)(v225 - 1) > 0x1F9D )
                RaiseInconsistencyError(&v208[v214], 6);
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
              v225 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v225 = 1;
              break;
          }
          *((_DWORD *)v204 + 8) = v225;
          *(_QWORD *)((char *)v204 + 46) = 0;
        }
      }
      if ( (**(_BYTE **)v204 & 4) != 0 )
      {
        if ( HIWORD(v600) )
          v220 = &v208[*(unsigned __int16 *)&v208[2 * SHIWORD(v600) + 1]];
        else
          v220 = &v208[v214];
        *((_QWORD *)v204 + 9) = v220;
        v221 = *(_WORD *)v220;
        *((_QWORD *)v204 + 10) = v220 + 2;
        *((_WORD *)v204 + 44) = 2 * (v221 + 1);
      }
      v222 = (PageComprInfoCache *)*((_QWORD *)v204 + 1);
      if ( v222 )
        PageComprInfoCache::Init(v222, (const struct PageComprInfo *)v204);
      v77 = v439;
      v66 = v482;
LABEL_492:
      v205 = *(unsigned __int16 *)(v46 + 14);
      v206 = (char *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v484 - v190)));
      v93 = (*v206 & 1) == 0;
      v738 = v206;
      if ( v93 )
      {
        v735 = 0;
        v737 = 0;
        *(_DWORD *)&v740[14] = 0;
        switch ( *v206 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v205 = *((unsigned __int16 *)v206 + 1);
            if ( (unsigned int)(v205 - 1) > 0x1F9D )
              RaiseInconsistencyError(v206, 6);
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
            v205 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v205 = 1;
            break;
        }
        LODWORD(v739) = v205;
        *(_QWORD *)&v740[6] = v46 + 0x2000;
      }
      else
      {
        v735 = 1;
        v207 = *v206;
        switch ( *v206 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( v206[1] < 0 )
            {
              v226 = HIBYTE(*(_WORD *)(v206 + 1)) | ((*(_WORD *)(v206 + 1) & 0x7F) << 8);
              v736 = v226;
              v227 = 3;
              *(_WORD *)v740 = 3;
            }
            else
            {
              v226 = (unsigned __int8)v206[1];
              v736 = v226;
              v227 = 2;
              *(_WORD *)v740 = 2;
            }
            *(_WORD *)&v740[4] = v227 + (((unsigned int)v226 + 1) >> 1);
            if ( v226 > 0x1Eu )
              *(_WORD *)&v740[2] = (v226 - 1) / 30;
            else
              *(_WORD *)&v740[2] = 0;
            v737 = 0;
            v741 = 0;
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
            if ( (v207 & 0x1C) == 4 && (v207 & 2) != 0 )
            {
              *(_QWORD *)v740 = 0;
              v736 = 0;
              *(_QWORD *)&v740[8] = 0;
              v737 = v434;
              v741 = 1;
            }
            else
            {
              *(_QWORD *)v740 = 0;
              v736 = 0;
              *(_QWORD *)&v740[8] = 0;
              v737 = 1;
              v741 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v740 = 0;
            v736 = 0;
            *(_QWORD *)&v740[8] = 0;
            v737 = 9;
            v741 = 0;
            break;
        }
        *(_QWORD *)&v740[16] = v46 + 0x2000;
        v739 = v204;
      }
      if ( v735 )
        CDRecord::GetXdesTs(&v736, &v456);
      else
        FixedVarRecord::GetXdesTs(&v736, &v456);
      v228 = v456;
      v229 = v457;
      v79 = v436;
      if ( v457 != *((_WORD *)*v436 + 22) || v456 != *((_DWORD *)*v436 + 10) )
      {
        _mm_lfence();
        if ( (*(_DWORD *)(*((_QWORD *)v436[1] + 8) + 4LL) & 0x140) == 0 )
        {
          _mm_lfence();
          v508 = v456;
          v509 = v457;
          if ( (unsigned int)XDES::GetTIDLockOption(*v436, &v508) == 3 )
          {
            _mm_lfence();
            PageRef::Unlatch(v77);
            v510 = v228;
            v511 = v229;
            v230 = *v79;
            v231 = *((_QWORD *)*v79 + 6);
            LODWORD(v428) = *(_DWORD *)(*((_QWORD *)v79[1] + 8) + 24LL);
            LOBYTE(v427) = 3;
            LOBYTE(v232) = 1;
            Lock = AcquireTransactionLock(*(unsigned __int16 *)(v231 + 1720), &v510, v230, v232, v427, v428);
            LOBYTE(v189) = 72;
LABEL_465:
            lck_StandardHandler(Lock, v189);
            v22 = v444;
            v21 = v451;
            v27 = v463;
LABEL_466:
            v24 = v436;
            continue;
          }
        }
        PageRef::SetBulkInsertBitOnPage(v77, 0);
      }
      break;
    }
    v80 = (__int64)v79[1];
    v81 = *(_QWORD *)(*(_QWORD *)(v80 + 88) + 8LL);
    if ( *(_BYTE *)(v81 + 1873) )
    {
      v194 = a9 ? *(_QWORD *)(v80 + 72) : *(_QWORD *)(v80 + 64);
      if ( (*(_DWORD *)(v194 + 4) & 0x140) == 0 )
      {
        v195 = *(_WORD *)(*((_QWORD *)*v79 + 6) + 1720LL);
        if ( v696 )
          CDRecord::GetXdesTs(&v697, &v458);
        else
          FixedVarRecord::GetXdesTs(&v697, &v458);
        v197 = v458;
        v198 = v459;
        if ( v459 != v443 || v458 != v455 )
        {
          v475 = v458;
          v476 = v459;
          v199 = *v79;
          if ( (word_10318AB38 != v459 || NullXdesId != v458)
            && (v459 != *((_WORD *)v199 + 22) || v458 != *((_DWORD *)v199 + 10)) )
          {
            v200 = *((_QWORD *)v199 + 6);
            if ( *(_BYTE *)(v200 + 8272) )
            {
              if ( XdesMgr::IsXdesActive((XdesMgr *)(v200 + 6600), (const struct XdesId *)&v475) )
              {
LABEL_580:
                PageRef::Unlatch(v439);
                v514 = v197;
                v515 = v198;
                LODWORD(v428) = *(_DWORD *)(*((_QWORD *)v79[1] + 8) + 24LL);
                LOBYTE(v427) = 3;
                LOBYTE(v234) = 1;
                v235 = AcquireTransactionLock(v195, &v514, *v79, v234, v427, v428);
                LOBYTE(v236) = 72;
                lck_StandardHandler(v235, v236);
                v455 = v197;
                v443 = v198;
                v22 = v444;
                v21 = v451;
                v27 = v463;
                goto LABEL_466;
              }
            }
            else
            {
              v80 = *(_QWORD *)(v200 + 7192);
              if ( v459 >= WORD2(v80) && (v459 != WORD2(v80) || v458 >= (unsigned int)v80) )
              {
                v512 = v475;
                v513 = v476;
                v201 = *((_QWORD *)v199 + 6);
                LODWORD(v428) = 0;
                LOBYTE(v427) = 3;
                LOBYTE(v196) = 1;
                v202 = AcquireTransactionLock(*(unsigned __int16 *)(v201 + 1720), &v512, v199, v196, v427, v428);
                if ( v202 == -1 )
                  goto LABEL_580;
                LOBYTE(v203) = 72;
                lck_StandardHandler(v202, v203);
              }
            }
          }
        }
      }
    }
    if ( *((_QWORD *)v79[1] + 48) )
    {
      v70 = v435;
    }
    else
    {
      v82 = *v79;
      v83 = v435;
      v84 = (int)(*((_DWORD *)v435 + 4) << 31) >> 31;
      v85 = *(_BYTE *)(*((_QWORD *)v82 + 6) + 7390LL);
      if ( (**(unsigned __int8 (__fastcall ***)(struct XDES *))v82)(v82) )
        goto LABEL_80;
      if ( v85 )
        goto LABEL_594;
      if ( !v84 )
        goto LABEL_80;
      if ( (*((_BYTE *)v83 + 16) & 0x40) == 0 )
      {
LABEL_594:
        v70 = v83;
      }
      else
      {
        v233 = *((_QWORD *)v82 + 26);
        if ( !v233 )
        {
LABEL_80:
          v70 = v83;
          goto LABEL_81;
        }
        v70 = v83;
        if ( !*(_BYTE *)(v233 + 52)
          || !*(_QWORD *)(v233 + 64)
          || *(_QWORD *)(*(_QWORD *)v83 + 40LL) == _InterlockedCompareExchange64(
                                                     (volatile signed __int64 *)(v233 + 296),
                                                     0,
                                                     0) )
        {
LABEL_81:
          v86 = a8;
          goto LABEL_82;
        }
      }
      v79 = v436;
    }
    if ( !*((_BYTE *)v79[4] + 7390) || a9 != 1 )
      goto LABEL_762;
    v237 = v446;
    v566 = *(_DWORD *)v446;
    v567 = *((_WORD *)v446 + 2);
    v568 = *((_WORD *)v446 + 3);
    v238 = *((_QWORD *)v497 + 1);
    if ( !v238 || (v239 = *(_QWORD *)(v238 + 8), *(_BYTE *)(v239 + 63)) )
    {
      if ( *((_DWORD *)v497 + 16) == 2 )
      {
        v243 = (int *)*((_QWORD *)v497 + 6);
        v560 = *v243;
        v561 = *((_WORD *)v243 + 2);
        v562 = 0;
        v244 = &v560;
      }
      else
      {
        v245 = (int *)*((_QWORD *)v497 + 5);
        v563 = *v245;
        v564 = *((_WORD *)v245 + 2);
        v565 = 0;
        v244 = &v563;
      }
      v464 = *v244;
      v240 = *((_WORD *)v244 + 2);
    }
    else
    {
      v464 = *(_DWORD *)(v239 + 8);
      v240 = *(_WORD *)(v239 + 12);
    }
    v466 = 0;
    v465 = v240;
    LOBYTE(v431) = 1;
    LOBYTE(v430) = 0;
    v241 = BlobManager::RevertFromVersion(
             *v79,
             &v464,
             v79[1],
             &v696,
             v46,
             &v566,
             v70,
             (_DWORD)v430,
             (_DWORD)v431,
             0,
             v439);
    if ( v241 == 3 )
    {
      utassert_fail(1u, "lrRetCode != LOGICAL_REVERT_BLOB_COULD_NOT_TAKE_LOCKS", "blobbase.cpp", 1886, 0);
      goto LABEL_591;
    }
    if ( v241 != 4 )
    {
      v22 = v444;
      v21 = v451;
      v27 = v463;
      if ( v241 == 2 )
        goto LABEL_466;
      goto LABEL_762;
    }
    v246 = *((__int16 *)v237 + 3);
    v703 = *((__int16 *)v237 + 3);
    if ( *(char *)(v46 + 2) >= 0 )
    {
      v247 = 0;
      goto LABEL_603;
    }
    v250 = (unsigned __int8 *)(v46 + 96);
    _mm_prefetch((const char *)(v46 + 96), 0);
    if ( v696 && (v247 = v700) != 0 )
    {
      v251 = -1;
    }
    else
    {
      v707 = 0;
      v709 = 0u;
      v710 = 0;
      v712 = 0;
      v704 = 0;
      v251 = -1;
      v705 = 0xFFFFu;
      v708 = 0;
      memset(v706, 0, sizeof(v706));
      v711 = 0u;
      v247 = &v704;
    }
    if ( !*(_WORD *)(v46 + 36) )
      goto LABEL_620;
    v252 = *(_BYTE *)(v46 + 1);
    if ( v252 != 11 )
    {
      if ( v252 != 8 )
        goto LABEL_618;
      goto LABEL_619;
    }
    if ( *(_DWORD *)(v46 + 24) == 99 )
      goto LABEL_611;
LABEL_618:
    if ( v252 == 9 )
    {
LABEL_619:
      if ( *(_DWORD *)(v46 + 24) != 99 )
        goto LABEL_620;
LABEL_611:
      v516 = *(_DWORD *)(v46 + 32);
      v517 = *(_WORD *)(v46 + 36);
      if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v516, v80) )
        goto LABEL_620;
      PageHeader::GetIcxLsn(v46, &v505);
    }
    else
    {
LABEL_620:
      v505 = *(_QWORD *)(v46 + 40);
      v506 = *(_WORD *)(v46 + 48);
    }
    *(_QWORD *)v247 = v250;
    v253 = v506;
    v254 = HIDWORD(v505);
    *((_DWORD *)v247 + 24) = v505;
    *((_DWORD *)v247 + 25) = v254;
    *((_WORD *)v247 + 52) = v253;
    *((_DWORD *)v247 + 27) = *(_DWORD *)(v46 + 32);
    *((_WORD *)v247 + 56) = *(_WORD *)(v46 + 36);
    *((_WORD *)v247 + 57) = 0;
    v255 = 3LL * *v250;
    v599 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v250);
    v256 = word_102883984[v255];
    *((_WORD *)v247 + 8) = v251;
    *((_QWORD *)v247 + 3) = 0;
    *((_DWORD *)v247 + 5) = 0;
    *(_QWORD *)((char *)v247 + 46) = 0;
    *((_QWORD *)v247 + 7) = 0;
    *((_QWORD *)v247 + 4) = 0;
    *((_QWORD *)v247 + 9) = 0;
    *((_QWORD *)v247 + 10) = 0;
    *((_WORD *)v247 + 44) = 0;
    if ( (**(_BYTE **)v247 & 2) != 0 )
    {
      v257 = &v250[v256];
      if ( (v250[v256] & 1) != 0 )
      {
        *((_WORD *)v247 + 8) = 1;
        *((_QWORD *)v247 + 3) = v257;
        v258 = *v257;
        switch ( *v257 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( (v257[1] & 0x80u) != 0 )
            {
              v265 = *(_WORD *)(v257 + 1);
              *((_WORD *)v247 + 9) = v265;
              v259 = 3;
              v260 = HIBYTE(v265) | ((v265 & 0x7F) << 8);
            }
            else
            {
              v259 = 2;
              v260 = v257[1];
            }
            *((_WORD *)v247 + 9) = v260;
            *((_WORD *)v247 + 20) = v259;
            *((_WORD *)v247 + 22) = v259 + (((unsigned int)*((unsigned __int16 *)v247 + 9) + 1) >> 1);
            v261 = *((unsigned __int16 *)v247 + 9);
            if ( v261 > 0x1E )
              *((_WORD *)v247 + 21) = (int)(v261 - 1) / 30;
            else
              *((_WORD *)v247 + 21) = 0;
            *((_DWORD *)v247 + 5) = 0;
            *((_DWORD *)v247 + 16) = 0;
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 4) = 0;
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
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 4) = 0;
            break;
          case 4:
            if ( (v258 & 0x1C) != 4 || (v266 = 1, (v258 & 2) == 0) )
              v266 = 0;
            *((_DWORD *)v247 + 5) = 0;
            *((_QWORD *)v247 + 5) = 0;
            *((_WORD *)v247 + 9) = 0;
            *((_QWORD *)v247 + 6) = 0;
            *((_QWORD *)v247 + 4) = 0;
            *((_DWORD *)v247 + 16) = 0;
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 3) = v257;
            if ( v266 )
            {
              *((_DWORD *)v247 + 5) = v434;
              *((_DWORD *)v247 + 16) = 0;
              *((_DWORD *)v247 + 16) = 1;
            }
            else
            {
              *((_DWORD *)v247 + 5) = 1;
              *((_DWORD *)v247 + 16) = 0;
            }
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 4) = 0;
            break;
          case 8:
            *((_QWORD *)v247 + 5) = 0;
            *((_WORD *)v247 + 9) = 0;
            *((_QWORD *)v247 + 6) = 0;
            *((_QWORD *)v247 + 4) = 0;
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 3) = v257;
            *((_DWORD *)v247 + 5) = 9;
            *((_DWORD *)v247 + 16) = 0;
            *((_QWORD *)v247 + 7) = 0;
            *((_QWORD *)v247 + 4) = 0;
            break;
        }
      }
      else
      {
        *((_WORD *)v247 + 8) = 0;
        v267 = 0;
        *((_QWORD *)v247 + 3) = v257;
        *((_DWORD *)v247 + 5) = 0;
        *(_DWORD *)((char *)v247 + 54) = 0;
        switch ( *v257 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v267 = *((unsigned __int16 *)v257 + 1);
            if ( (unsigned int)(v267 - 1) > 0x1F9D )
              RaiseInconsistencyError(&v250[v256], 6);
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
            v267 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v267 = 1;
            break;
        }
        *((_DWORD *)v247 + 8) = v267;
        *(_QWORD *)((char *)v247 + 46) = 0;
      }
    }
    if ( (**(_BYTE **)v247 & 4) != 0 )
    {
      if ( HIWORD(v599) )
        v262 = &v250[*(unsigned __int16 *)&v250[2 * SHIWORD(v599) + 1]];
      else
        v262 = &v250[v256];
      *((_QWORD *)v247 + 9) = v262;
      v263 = *(_WORD *)v262;
      *((_QWORD *)v247 + 10) = v262 + 2;
      *((_WORD *)v247 + 44) = 2 * (v263 + 1);
    }
    v264 = (PageComprInfoCache *)*((_QWORD *)v247 + 1);
    if ( v264 )
      PageComprInfoCache::Init(v264, (const struct PageComprInfo *)v247);
LABEL_603:
    v248 = *(unsigned __int16 *)(v46 + 14);
    v249 = (unsigned __int8 *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v484 - v246)));
    v93 = (*v249 & 1) == 0;
    v699 = (struct XDES *)v249;
    if ( v93 )
    {
      v696 = 0;
      v434 = 0;
      v698 = 0;
      *(_DWORD *)&v701[14] = 0;
      v80 = *v249 & 0xE;
      switch ( *v249 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v248 = *((unsigned __int16 *)v249 + 1);
          if ( v248 - 1 > 0x1F9D )
          {
            RaiseInconsistencyError(v249, 6);
            v434 = v698;
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
          v434 = v698;
          break;
        case 4:
          v248 = 9;
          break;
        case 6:
        case 0xA:
          break;
        case 0xE:
          v248 = 1;
          break;
      }
      LODWORD(v700) = v248;
      *(_QWORD *)&v701[6] = v46 + 0x2000;
      LODWORD(v247) = v248;
    }
    else
    {
      v696 = 1;
      v80 = *v249;
      switch ( *v249 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v249[1] & 0x80u) != 0 )
          {
            v268 = HIBYTE(*(_WORD *)(v249 + 1)) | ((*(_WORD *)(v249 + 1) & 0x7F) << 8);
            v697 = v268;
            v80 = 3;
            *(_WORD *)v701 = 3;
          }
          else
          {
            v268 = v249[1];
            v697 = v268;
            v80 = 2;
            *(_WORD *)v701 = 2;
          }
          *(_WORD *)&v701[4] = v80 + (((unsigned int)v268 + 1) >> 1);
          if ( v268 > 0x1Eu )
          {
            v80 = (unsigned int)((v268 - 1) / 30);
            *(_WORD *)&v701[2] = (v268 - 1) / 30;
          }
          else
          {
            *(_WORD *)&v701[2] = 0;
          }
          v269 = 0;
          v698 = 0;
          v702 = 0;
          goto LABEL_656;
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
          v269 = v698;
          goto LABEL_656;
        case 4:
          if ( (v80 & 0x1C) == 4 && (v80 & 2) != 0 )
          {
            *(_QWORD *)v701 = 0;
            v697 = 0;
            *(_QWORD *)&v701[8] = 0;
            v698 = v434;
            v702 = 1;
          }
          else
          {
            *(_QWORD *)v701 = 0;
            v697 = 0;
            *(_QWORD *)&v701[8] = 0;
            v269 = 1;
            v698 = 1;
            v702 = 0;
LABEL_656:
            v434 = v269;
          }
          *(_QWORD *)&v701[16] = v46 + 0x2000;
          v700 = v247;
          v248 = (unsigned int)v247;
          break;
        case 8:
          *(_QWORD *)v701 = 0;
          v697 = 0;
          *(_QWORD *)&v701[8] = 0;
          v269 = 9;
          v698 = 9;
          v702 = 0;
          goto LABEL_656;
      }
    }
    v66 = v699;
    if ( v696 )
    {
      v80 = v434;
      if ( !v434 )
      {
        CDRecord::Resize((CDRecord *)&v697);
        v80 = v698;
      }
      if ( (unsigned int)v80 >= 9 )
        goto LABEL_774;
      v297 = *(_BYTE *)v699 & 0x1C;
      if ( (*(_BYTE *)v699 & 0x1C) == 0 )
        goto LABEL_761;
      v434 = 9;
      if ( v297 != 12 )
LABEL_774:
        v434 = v80;
      goto LABEL_775;
    }
    v270 = v434;
    if ( !v434 )
    {
      v697 = 0;
      HIDWORD(v700) = v248;
      v271 = *(_BYTE *)v699;
      HIDWORD(v700) = (_DWORD)v247;
      if ( (v271 & 0x10) != 0 )
      {
        if ( (*(_BYTE *)v699 & 0x10) != 0 )
          v272 = *(unsigned __int16 *)((char *)v699 + v248);
        else
          v272 = 0;
        LODWORD(v247) = ((unsigned int)(v272 + 7) >> 3) + (_DWORD)v247 + 2;
        HIDWORD(v700) = (_DWORD)v247;
      }
      if ( (*(_BYTE *)v699 & 0x20) != 0 )
      {
        v273 = (unsigned __int16 *)((char *)v699 + (unsigned int)v247);
        v80 = *v273;
        *(_WORD *)&v701[4] = v80;
        if ( !(_WORD)v80 )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v699, 3);
          v80 = *(unsigned __int16 *)&v701[4];
          LODWORD(v247) = HIDWORD(v700);
        }
        v276 = (_DWORD)v247 + 2 * ((unsigned __int16)v80 + 1);
        *(_DWORD *)v701 = v276;
        if ( v276 > 0x1F9E )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v277 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v277 )
            {
              v278 = *(_QWORD *)(v277 + 96);
              if ( v278 )
              {
                if ( *(_BYTE *)(v278 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v699, 4);
          v80 = *(unsigned __int16 *)&v701[4];
          v276 = *(_DWORD *)v701;
          LODWORD(v247) = HIDWORD(v700);
        }
        v270 = v273[(unsigned __int16)v80] & 0x7FFF;
        v434 = v270;
        v698 = v270;
        if ( v276 > v270 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v279 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v279 )
            {
              v280 = *(_QWORD *)(v279 + 96);
              if ( v280 )
              {
                if ( *(_BYTE *)(v280 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v699, 4);
          v80 = *(unsigned __int16 *)&v701[4];
          v276 = *(_DWORD *)v701;
          LODWORD(v247) = HIDWORD(v700);
          v270 = v698;
          v434 = v698;
        }
        while ( (v273[(unsigned __int16)v80] & 0x8000u) != 0 )
        {
          v281 = (char *)v699 + (unsigned int)v247;
          if ( (unsigned __int16)v80 == 1 )
            v282 = v276;
          else
            v282 = *(_WORD *)&v281[2 * (unsigned __int16)v80 - 2] & 0x7FFF;
          if ( v282 < v276 || (*(_WORD *)&v281[2 * (unsigned __int16)v80] & 0x7FFFu) < v282 )
          {
            RaiseInconsistencyError(v699, 7);
            v80 = *(unsigned __int16 *)&v701[4];
            v276 = *(_DWORD *)v701;
            LODWORD(v247) = HIDWORD(v700);
            v270 = v698;
            v434 = v698;
          }
          if ( v282 < v276 || v282 > v270 )
            goto LABEL_758;
          v283 = *(_WORD *)((char *)v699 + v282);
          if ( v283 == 5 )
          {
            v697 |= 2u;
            *(_WORD *)&v701[4] = v80 - 1;
            *(_WORD *)&v701[18] = v282;
            v284 = (char *)v699 + (unsigned __int16)v282;
            v285 = *((_WORD *)v284 + 1);
            if ( (v285 & 0x4000) != 0 )
              v286 = (*(_WORD *)&v701[20] ^ v285) & 0x3800 ^ *(_WORD *)&v701[20];
            else
              v286 = *(_WORD *)&v701[20] & 0xC7FF;
            *(_WORD *)&v701[20] = v286;
            v287 = *((_WORD *)v284 + 1) ^ v286;
            v80 = 2047;
            v288 = v287 & 0x7FF ^ v286;
            *(_WORD *)&v701[20] = v288;
            break;
          }
          if ( v283 >= 0x400u )
          {
            v697 |= 1u;
            v93 = (_WORD)v80 == 1;
            LOWORD(v80) = v80 - 1;
            *(_WORD *)&v701[4] = v80;
            if ( !v93 )
              continue;
          }
          break;
        }
      }
      else
      {
        v270 = (unsigned int)v247;
        v434 = (unsigned int)v247;
        v698 = (unsigned int)v247;
        *(_WORD *)&v701[4] = 0;
        *(_DWORD *)v701 = (_DWORD)v247;
      }
      if ( (*(_BYTE *)v699 & 0x40) != 0 )
      {
        *(_DWORD *)&v701[14] = v270;
        v698 = v270 + 14;
        v289 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v697);
        v80 = HIWORD(*(_QWORD *)v289);
        v290 = 0;
        v291 = (__int16)v80 ^ ((unsigned int)(__int16)v80 >> 1);
        if ( (v291 & 0x2000) != 0 )
        {
          if ( (v80 & 0x4000) != 0 )
            LOWORD(v80) = v80 | 0x2000;
          else
            LOWORD(v80) = v80 & 0xDFFF;
        }
        if ( (_WORD)v80 == 0xFFFC )
          v290 = (unsigned __int16)WORD2(*(_QWORD *)v289) >> 5;
        v270 = v290 + v698;
        v434 = v290 + v698;
        v698 += v290;
      }
      else
      {
        *(_DWORD *)&v701[14] = 0;
      }
      if ( *(_QWORD *)&v701[6] && *(_QWORD *)&v701[6] < (unsigned __int64)v699 + v270 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v292 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v292 )
          {
            v293 = *(_QWORD *)(v292 + 96);
            if ( v293 )
            {
              if ( *(_BYTE *)(v293 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v699, 18);
        v270 = v698;
        v434 = v698;
      }
      if ( v270 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v294 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v294 )
          {
            v295 = *(_QWORD *)(v294 + 96);
            if ( v295 )
            {
              if ( *(_BYTE *)(v295 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v699, 5);
        v270 = v698;
        v434 = v698;
      }
    }
LABEL_758:
    if ( v270 >= 9 || (v296 = *(_BYTE *)v699 & 0xE) != 0 && v296 != 12 )
    {
LABEL_775:
      *v483 = v434;
      goto LABEL_762;
    }
LABEL_761:
    v434 = 9;
    *v483 = 9;
LABEL_762:
    v70 = v435;
LABEL_591:
    if ( v447 )
    {
      v717 = -1;
      v720 = 0;
      v719 = 0;
      v724 = 0;
      *(_QWORD *)((char *)&v725 + 2) = 0;
      v721 = 0;
      v726 = -1;
      v440 = 0;
      v308 = v436;
      v309 = v436[4];
      if ( *((_BYTE *)v309 + 8272) )
      {
        v310 = *((_QWORD *)v309 + 214);
        if ( (*(_BYTE *)(v310 + 60) & 1) != 0 && !*(_QWORD *)(v310 + 640) )
        {
          v577 = 0;
          v578 = 0;
          v713 = 0;
          v714 = 0;
          v311 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v311 )
          {
            v312 = *(_QWORD *)(v311 + 96);
            v715 = v312;
            v716 = 0;
            if ( v312 && !*(_QWORD *)(v312 + 1464) )
            {
              *(_QWORD *)(v312 + 1464) = &v713;
              v716 = 1;
            }
          }
          else
          {
            v715 = 0;
            v716 = 0;
          }
          try
          {
            ExcHandler::ExcHandler(
              (ExcHandler *)v693,
              6u,
              0x5Du,
              0,
              (int (*)(int, int, int, int, char *))hdl_backout,
              0);
            v731[0] = 0;
            v731[1] = 0;
            v732 = 0;
            v313 = *(_WORD *)(v46 + 4) & 0x2000;
            v612 = v313;
            v314 = (struct ForeignXdesContext *)*((_QWORD *)v308[1] + 48);
            v591 = v314;
            v315 = *v308;
            v498 = v315;
            Lsn = Page::GetLsn(v46, v660, 0, 0);
            v646 = Lsn;
            v317 = (char *)v315 + 48;
            v318 = *((_QWORD *)v315 + 6);
            v590 = v318;
            v319 = *(_BYTE *)(v318 + 7390);
            v438 = v319;
            if ( *(_BYTE *)(v318 + 8272) && (*((_BYTE *)v435 + 16) & 1) != 0 )
            {
              v320 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v315 + 240LL))(v315)
                   ? *(_QWORD *)((*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v315 + 488LL))(v315) + 584)
                   : *((_QWORD *)v315 + 73);
              v647 = v320;
              v648 = v320;
              if ( !*(_BYTE *)(v320 + 22) )
                ex_raise(39, 48, 16, 2);
            }
            PageRow::Clone((PageRow *)&v717, (const struct PageRow *)&v696);
            v440 = 1;
            if ( !v314 )
            {
              if ( !v313 )
              {
                v449 = (unsigned __int8)byte_10317AD6E >> 3;
                if ( (byte_10317AD6E & 8) == 0 )
                {
                  v545 = 0;
                  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v622 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v362 = *v622;
                  v623 = v362;
                  if ( !v362 || (v363 = **(struct CSessionTraceFlags ***)(v362 + 56), (v624 = v363) == 0) )
                  {
                    v616 = 0;
                    goto LABEL_932;
                  }
                  v616 = v363;
                  v545 = CSessionTraceFlags::CheckSessionTraceInternal(v363, 0xF73u);
                  if ( !v545 )
                  {
LABEL_932:
                    v437 = 1;
                    goto LABEL_933;
                  }
                  v315 = v498;
                }
                v364 = *((_QWORD *)v315 + 26);
                v625 = v364;
                if ( v364 )
                  v365 = *(_QWORD *)(v364 + 64);
                else
                  v365 = 0;
                v366 = *((_QWORD *)v315 + 82);
                v539 = *(_WORD *)(*(_QWORD *)v317 + 1720LL);
                v367 = v539;
                v368 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v366 + 312LL))(v366);
                LogSystemMetadata(
                  L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v367,
                  *((_QWORD *)v435 + 5),
                  v368,
                  v365);
                goto LABEL_932;
              }
              v321 = *(_QWORD *)v317;
              v649 = v321;
              if ( *(_BYTE *)(v321 + 6872) )
                goto LABEL_815;
              if ( v696 )
                CDRecord::GetVersionRecPtr(&v697, v569);
              else
                FixedVarRecord::GetVersionRecPtr(&v697, v569);
              v651 = v569;
              if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v569) )
              {
LABEL_815:
                v322 = *(_QWORD *)(*(_QWORD *)(v321 + 1712) + 704LL);
                v652 = v322;
                if ( *(_WORD *)(v322 + 10) == 2 && !*(_DWORD *)Lsn
                  || (v653 = v322, *(_DWORD *)Lsn > *(_DWORD *)v322)
                  || *(_DWORD *)Lsn == *(_DWORD *)v322
                  && ((v349 = *(_DWORD *)(Lsn + 4), v349 > *(_DWORD *)(v322 + 4))
                   || v349 == *(_DWORD *)(v322 + 4) && *(_WORD *)(Lsn + 8) > *(_WORD *)(v322 + 8)) )
                {
                  v481 = 1;
                }
                else
                {
                  v481 = 0;
                  if ( !*(_BYTE *)(v321 + 8272) )
                    goto LABEL_924;
                  if ( v696 )
                    CDRecord::GetVersionRecPtr(&v697, v570);
                  else
                    FixedVarRecord::GetVersionRecPtr(&v697, v570);
                  v654 = v570;
                  if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v570) )
                  {
LABEL_924:
                    v448 = (unsigned __int8)byte_10317AD6E >> 3;
                    if ( (byte_10317AD6E & 8) != 0 )
                    {
LABEL_929:
                      v352 = *((_QWORD *)v315 + 26);
                      v620[2] = v352;
                      if ( v352 )
                        v353 = *(_QWORD *)(v352 + 64);
                      else
                        v353 = 0;
                      v354 = *((_QWORD *)v315 + 82);
                      v538 = *(_WORD *)(*(_QWORD *)v317 + 1720LL);
                      v355 = v538;
                      v356 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v354 + 312LL))(v354);
                      LogSystemMetadata(
                        L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                        v355,
                        *((_QWORD *)v435 + 5),
                        v356,
                        v353);
                      goto LABEL_932;
                    }
                    v544 = 0;
                    v655 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v656 = (__int64 *)(v655[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                    v350 = *v656;
                    v657 = v350;
                    if ( v350 && (v351 = **(struct CSessionTraceFlags ***)(v350 + 56), (v658 = v351) != 0) )
                    {
                      v609 = v351;
                      v544 = CSessionTraceFlags::CheckSessionTraceInternal(v351, 0xF73u);
                      if ( v544 )
                      {
                        v315 = v498;
                        goto LABEL_929;
                      }
                    }
                    else
                    {
                      v609 = 0;
                    }
                    goto LABEL_932;
                  }
                }
              }
            }
            v437 = 0;
            v323 = *v720;
            if ( v717 )
              v324 = v323 >> 1;
            else
              v324 = v323 >> 6;
            v610 = v324 & 1;
            if ( (v324 & 1) != 0 )
            {
              v23 = 0;
              v444 = 0;
              v445 = 0;
              if ( v717 )
                CDRecord::GetXdesTs(&v718, &v477);
              else
                FixedVarRecord::GetXdesTs(&v718, &v477);
              v626 = &v477;
              if ( v478 || v477 )
              {
                v325 = v435;
                if ( v314 || !v435 || (*((_BYTE *)v435 + 16) & 0x20) == 0 )
                  goto LABEL_963;
                v326 = (*((_BYTE *)v315 + 536) & 4) != 0
                     ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v315 + 488LL))(v315) + 40
                     : (__int64)v315 + 40;
                v627 = v326;
                if ( v717 )
                  CDRecord::GetXdesTs(&v718, &v479);
                else
                  FixedVarRecord::GetXdesTs(&v718, &v479);
                v628 = &v479;
                if ( v480 != *(_WORD *)(v326 + 4) || v479 != *(_DWORD *)v326 )
                  goto LABEL_963;
                v327 = (struct XVB **)((char *)v315 + 208);
                v328 = *((_QWORD *)v315 + 26);
                v629 = v328;
                if ( !v319
                  || v328
                  && *(_BYTE *)(v328 + 52)
                  && *(_QWORD *)(v328 + 64)
                  && (v630 = _InterlockedCompareExchange64((volatile signed __int64 *)(v328 + 296), 0, 0),
                      v319 = v438,
                      v318 = v590,
                      v314 = v591,
                      v315 = v498,
                      *(_QWORD *)(*(_QWORD *)v325 + 40LL) != v630) )
                {
                  VersionMgr::GetVersionWithUpdateMarker(
                    *v327,
                    *((const struct UserInfo **)v325 + 4),
                    *(const struct DBTABLE **)(v318 + 1712),
                    v447,
                    0x1F9Eu,
                    *(const struct UpdateSequenceMarker **)v325,
                    (struct Record *)&v717,
                    0,
                    1,
                    (struct VersionMgr::GetVersionResult *)&v440,
                    0);
                }
                if ( v319 )
                {
                  if ( v717 )
                    CDRecord::GetVersionRecPtr(&v718, v571);
                  else
                    FixedVarRecord::GetVersionRecPtr(&v718, v571);
                  v631 = v571;
                  if ( v717 )
                    CDRecord::GetXdesTs(&v718, &v471);
                  else
                    FixedVarRecord::GetXdesTs(&v718, &v471);
                  v639 = &v471;
                  v611 = v471;
                  v540 = v472;
                  v518 = v471;
                  v519 = v472;
                  if ( (unsigned int)XdesMgr::GetRowAbortState(v318 + 6600, &v518, v571) )
                  {
LABEL_963:
                    v433 = 0;
                    if ( v696 == 1 )
                    {
                      v507 = 1;
                      VersionMgr::GetVersionFromCompressed(
                        (const struct PageRow *)&v696,
                        v447,
                        0x1F9Eu,
                        v315,
                        v325,
                        (struct PageRow *)&v717,
                        (struct VersionMgr::GetVersionResult *)&v440,
                        0,
                        0,
                        v314,
                        (const struct LSN *)v731,
                        v433);
                    }
                    else
                    {
                      v507 = 0;
                      VersionMgr::GetVersionLong(
                        v447,
                        0x1F9Eu,
                        v315,
                        v325,
                        (struct Record *)&v717,
                        (struct VersionMgr::GetVersionResult *)&v440,
                        0,
                        0,
                        v314,
                        (const struct LSN *)v731,
                        1,
                        v433);
                    }
                  }
                }
                goto LABEL_846;
              }
            }
LABEL_933:
            v450 = (unsigned __int8)byte_10317AD6E >> 3;
            v23 = 0;
            if ( (byte_10317AD6E & 8) == 0 )
            {
              v572 = 0;
              v632 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v633 = (__int64 *)(v632[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v357 = *v633;
              v650 = v357;
              if ( v357 && (v358 = **(struct CSessionTraceFlags ***)(v357 + 56), (v634 = v358) != 0) )
              {
                v617 = v358;
                v572 = CSessionTraceFlags::CheckSessionTraceInternal(v358, 0xF73u);
                if ( v572 )
                  goto LABEL_937;
              }
              else
              {
                v617 = 0;
              }
LABEL_943:
              v325 = v435;
LABEL_846:
              ExcHandler::~ExcHandler((ExcHandler *)v693);
              goto LABEL_1162;
            }
LABEL_937:
            CDStream::CDStream((CDStream *)v694);
            ProcessHeap = GetProcessHeap();
            v360 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
            v635 = v360;
            if ( v360 )
              v361 = CTracePrintStream::CTracePrintStream(v360, 0);
            else
              v361 = 0;
            v636 = v361;
            v637 = v361;
            if ( v361 && !CDStream::AddDevice((CDStream *)v694, v361) )
            {
              v638 = v361;
              (**(void (__fastcall ***)(CTracePrintStream *, __int64))v361)(v361, 1);
            }
            Record::Dump((Record *)&v717, (struct CDStream *)v694);
            CDStream::~CDStream((CDStream *)v694);
            goto LABEL_943;
          }
          catch ( SQLError v659 )
          {
            try
            {
              ExceptionBackout::ExceptionBackout((ExceptionBackout *)v620, (const struct SQLError *)v659);
              if ( v659[0] / 100 != 6 || v659[0] != 693 )
              {
                CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v620);
                ExceptionRethrow(CurrentException);
              }
              PageRef::Unlatch(v582);
              if ( v716 )
              {
                *(_QWORD *)(v715 + 1464) = 0;
                v716 = 0;
              }
              v645 = &v579;
              v640 = *((_QWORD *)v436[1] + 11);
              v641 = *(_QWORD *)(v640 + 20);
              v642 = ((unsigned int)v641 | ((unsigned __int64)WORD2(v641) << 32)) << 16;
              v643 = &v713;
              v618 = v713;
              v619 = v714;
              v579 = v713;
              v580 = v714;
              RecoveryUnit::WaitForRedoLsnToCatchUp(v436[4], &v579, 5);
              v454 = 0;
              ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v620);
            }
            catch ( ShortStackException )
            {
              JUMPOUT(0x1016A88D3LL);
            }
            v23 = 0;
            if ( v716 )
            {
              *(_QWORD *)(v715 + 1464) = 0;
              v716 = 0;
            }
            v484 = 4095;
            v434 = 15;
            v27 = v463;
            v21 = v608;
            v451 = v608;
            v581 = v608;
            v24 = v608;
            v446 = v583;
            v439 = v582;
            v483 = v584;
            v22 = v543;
            v444 = v543;
            continue;
          }
LABEL_1162:
          v329 = v436;
          v330 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v331 = *(struct Worker **)(v330 + 256);
          if ( !v331 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v331 = *(struct Worker **)(v330 + 256);
          }
          if ( *((_DWORD *)v331 + 139) )
            ExceptionPostCatchActions(v331);
          if ( v716 )
          {
            *(_QWORD *)(v715 + 1464) = 0;
            v716 = 0;
          }
LABEL_853:
          v332 = v440;
          v333 = v446;
          if ( !v440 )
          {
            BlobBase::TableCorruptException(
              *(_WORD *)(*((_QWORD *)*v329 + 6) + 1720LL),
              v446,
              *((__int16 *)v446 + 3),
              10);
            v332 = v440;
          }
          if ( a9 == 1 && v332 != 1 )
          {
            if ( (*((_BYTE *)v325 + 16) & 8) == 0 )
              utassert_fail(1u, "plocalVerScanParams->IsSnapshotIso ()", "blobbase.cpp", 2059, 0);
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v334 = 0;
              if ( pCounterLookupBlocks )
                v334 = (char *)pCounterLookupBlocks + 57344;
              if ( v334 && *(_QWORD *)v334 )
                _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v334 + 40LL), 1u);
            }
            Xdes = LobContext::GetXdes(v329[1]);
            XVMgr::RaiseError(
              60,
              *(const struct DBTABLE **)(*((_QWORD *)Xdes + 6) + 1712LL),
              *((const struct UserInfo **)v325 + 4),
              7);
          }
          v336 = v719;
          if ( v717 )
          {
            if ( !v719 )
            {
              CDRecord::Resize((CDRecord *)&v718);
              v336 = v719;
            }
            if ( v336 >= 9 )
              goto LABEL_1117;
            if ( (*v720 & 0x1C) != 0 )
            {
              v415 = (*v720 & 0x1C) == 12;
LABEL_1115:
              if ( !v415 )
                goto LABEL_1117;
            }
          }
          else
          {
            if ( !v719 )
            {
              v718 = 0;
              v336 = v721;
              HIDWORD(v721) = v721;
              if ( (*v720 & 0x10) != 0 )
              {
                v336 = (((unsigned int)*(unsigned __int16 *)&v720[(unsigned int)v721] + 7) >> 3) + v721 + 2;
                HIDWORD(v721) = v336;
              }
              if ( (*v720 & 0x20) != 0 )
              {
                v337 = &v720[v336];
                v338 = *(_WORD *)v337;
                v723 = v338;
                if ( !v338 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v339 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v339 )
                    {
                      v340 = *(_QWORD *)(v339 + 96);
                      if ( v340 )
                      {
                        if ( *(_BYTE *)(v340 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v720, 3);
                  v338 = v723;
                }
                v341 = HIDWORD(v721) + 2 + 2 * v338;
                v722 = v341;
                if ( v341 > 0x1F9E )
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
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v720, 4);
                  v338 = v723;
                  v341 = v722;
                }
                v336 = *(_WORD *)&v337[2 * v338] & 0x7FFF;
                v719 = v336;
                if ( v341 > v336 )
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
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v720, 4);
                  v338 = v723;
                  v341 = v722;
                  v336 = v719;
                }
                while ( 1 )
                {
                  if ( *(__int16 *)&v337[2 * v338] >= 0 )
                    goto LABEL_1084;
                  v346 = &v720[HIDWORD(v721)];
                  if ( v338 == 1 )
                  {
                    v347 = v341;
                  }
                  else
                  {
                    v347 = *(_WORD *)&v346[2 * v338 - 2] & 0x7FFF;
                    if ( v347 < v341 )
                    {
LABEL_905:
                      RaiseInconsistencyError(v720, 7);
                      v338 = v723;
                      v341 = v722;
                      v336 = v719;
                      goto LABEL_906;
                    }
                  }
                  if ( (*(_WORD *)&v346[2 * v338] & 0x7FFFu) < v347 )
                    goto LABEL_905;
LABEL_906:
                  if ( v347 < v341 || v347 > v336 )
                    goto LABEL_1112;
                  v348 = *(_WORD *)&v720[v347];
                  if ( v348 == 5 )
                  {
                    v718 |= 2u;
                    v723 = v338 - 1;
                    WORD2(v725) = v347;
                    v404 = &v720[(unsigned __int16)v347];
                    v405 = *((_WORD *)v404 + 1);
                    if ( (v405 & 0x4000) != 0 )
                      v406 = (WORD3(v725) ^ v405) & 0x3800 ^ WORD3(v725);
                    else
                      v406 = WORD3(v725) & 0xC7FF;
                    WORD3(v725) = v406;
                    WORD3(v725) = v406 ^ (*((_WORD *)v404 + 1) ^ v406) & 0x7FF;
                    goto LABEL_1084;
                  }
                  if ( v348 >= 0x400u )
                  {
                    v718 |= 1u;
                    v93 = v338-- == 1;
                    v723 = v338;
                    if ( !v93 )
                      continue;
                  }
                  goto LABEL_1084;
                }
              }
              v719 = v336;
              v723 = 0;
              v722 = v336;
LABEL_1084:
              if ( (*v720 & 0x40) != 0 )
              {
                LODWORD(v725) = v336;
                v719 = v336 + 14;
                v407 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v718);
                v408 = HIWORD(*(_QWORD *)v407);
                v409 = 0;
                if ( (((__int16)v408 ^ ((unsigned int)(__int16)v408 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v408 & 0x4000) != 0 )
                    LOWORD(v408) = v408 | 0x2000;
                  else
                    LOWORD(v408) = v408 & 0xDFFF;
                }
                if ( (_WORD)v408 == 0xFFFC )
                  v409 = (unsigned __int16)WORD2(*(_QWORD *)v407) >> 5;
                v336 = v409 + v719;
                v719 += v409;
              }
              else
              {
                LODWORD(v725) = 0;
              }
              if ( v724 && v724 < (unsigned __int64)&v720[v336] )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v410 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v410 )
                  {
                    v411 = *(_QWORD *)(v410 + 96);
                    if ( v411 )
                    {
                      if ( *(_BYTE *)(v411 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v720, 18);
                v336 = v719;
              }
              if ( v336 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v412 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v412 )
                  {
                    v413 = *(_QWORD *)(v412 + 96);
                    if ( v413 )
                    {
                      if ( *(_BYTE *)(v413 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v720, 5);
                v336 = v719;
              }
            }
LABEL_1112:
            if ( v336 >= 9 )
            {
LABEL_1117:
              *v483 = v336;
              if ( dword_103172528 )
              {
                v416 = v329[1];
                v417 = *((_QWORD *)v416 + 12);
                if ( v417 && *(_BYTE *)(*(_QWORD *)(v417 + 8) + 63LL) )
                  v418 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)(v417 + 592) + 88LL))(
                           **(_QWORD **)(v417 + 592),
                           *(_QWORD *)(*(_QWORD *)(v417 + 64) + 48LL));
                else
                  v418 = *((_QWORD *)v416 + 14);
                v419 = *(_QWORD *)(v418 + 48);
                if ( *(_DWORD *)(*(_QWORD *)(v419 + 1712) + 1516LL) == 1 )
                {
                  ObjectDataImpl = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)(v419 + 40));
                  ++*ObjectDataImpl;
                }
              }
              v421 = v720;
              if ( v717 )
              {
                v23 = (((*v720 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
              }
              else
              {
                v422 = *v720 & 0xE;
                if ( v422 == 2 )
                {
                  if ( (v720[1] & 1) != 0 )
                    v23 = 1;
                }
                else if ( ((v422 - 10) & 0xF9) == 0 )
                {
                  v23 = 1;
                }
              }
              if ( v23 && !a8 )
              {
                if ( v717 )
                  CDRecord::GetXdesTs(&v718, &v489);
                else
                  FixedVarRecord::GetXdesTs(&v718, &v489);
                v423 = *v329;
                if ( v490 == *((_WORD *)*v329 + 22) && v489 == *((_DWORD *)v423 + 10) )
                {
                  v524 = *(_DWORD *)v333;
                  v525 = *((_WORD *)v333 + 2);
                  v424 = *(unsigned __int16 *)(*((_QWORD *)v423 + 6) + 1720LL);
                  LODWORD(v429) = *((__int16 *)v588 + 3);
                  LODWORD(v427) = v424;
                  ex_raise(71, 9, 16, 13, v427, &v524, v429);
                }
                else
                {
                  BlobBase::TableCorruptException(
                    *(_WORD *)(*((_QWORD *)v423 + 6) + 1720LL),
                    v333,
                    *((__int16 *)v588 + 3),
                    13);
                }
                return v720;
              }
              return v421;
            }
            v414 = *v720 & 0xE;
            if ( v414 )
            {
              v415 = v414 == 12;
              goto LABEL_1115;
            }
          }
          v336 = 9;
          goto LABEL_1117;
        }
      }
      v460 = 257;
      v461 = 0;
      v462 = 0;
      v733 = 0;
      v734 = 0;
      v369 = *(_WORD *)(v46 + 4) & 0x2000;
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_1026;
      v370 = *(_BYTE *)(v46 + 1);
      if ( v370 == 11 )
      {
        if ( *(_DWORD *)(v46 + 24) == 99 )
        {
LABEL_974:
          v520 = *(_DWORD *)(v46 + 32);
          v521 = *(_WORD *)(v46 + 36);
          if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v520, v80) )
          {
            PageHeader::GetIcxLsn(v46, &v485);
LABEL_976:
            v371 = (struct LSN *)*((_QWORD *)v308[1] + 48);
            v372 = (struct OffRowPageRequestResult *)&v460;
            if ( !v371 )
              v372 = 0;
            v373 = *v308;
            v374 = *((_QWORD *)v373 + 6);
            v375 = *(_BYTE *)(v374 + 7390);
            if ( *(_BYTE *)(v374 + 8272) && (*((_BYTE *)v435 + 16) & 1) != 0 )
            {
              v376 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v373 + 240LL))(v373)
                   ? *(_QWORD *)((*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v373 + 488LL))(v373) + 584)
                   : *((_QWORD *)v373 + 73);
              if ( !*(_BYTE *)(v376 + 22) )
                ex_raise(39, 48, 16, 2);
            }
            PageRow::Clone((PageRow *)&v717, (const struct PageRow *)&v696);
            v440 = 1;
            if ( v371 )
              goto LABEL_1039;
            if ( !v369 )
            {
              if ( (byte_10317AD6E & 8) != 0
                || (v392 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v393 = **(struct CSessionTraceFlags ***)(v392 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v393, 0xF73u) )
              {
                v394 = *((_QWORD *)v373 + 26);
                if ( v394 )
                  v395 = *(_QWORD *)(v394 + 64);
                else
                  v395 = 0;
                v396 = *((_QWORD *)v373 + 82);
                v397 = *(unsigned __int16 *)(*((_QWORD *)v373 + 6) + 1720LL);
                v398 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v396 + 312LL))(v396);
                LogSystemMetadata(
                  L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v397,
                  *((_QWORD *)v435 + 5),
                  v398,
                  v395);
              }
              goto LABEL_1008;
            }
            v377 = *((_QWORD *)v373 + 6);
            if ( !*(_BYTE *)(v377 + 6872) )
            {
              if ( v696 )
                CDRecord::GetVersionRecPtr(&v697, v585);
              else
                FixedVarRecord::GetVersionRecPtr(&v697, v585);
              if ( VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v585) )
                goto LABEL_1039;
            }
            v378 = *(_QWORD *)(*(_QWORD *)(v377 + 1712) + 704LL);
            if ( *(_WORD *)(v378 + 10) == 2 && !(_DWORD)v485 )
              goto LABEL_1039;
            if ( (unsigned int)v485 > *(_DWORD *)v378 )
              goto LABEL_1039;
            if ( (_DWORD)v485 == *(_DWORD *)v378 )
            {
              v379 = *(_DWORD *)(v378 + 4);
              if ( HIDWORD(v485) > v379 || HIDWORD(v485) == v379 && v486 > *(_WORD *)(v378 + 8) )
                goto LABEL_1039;
            }
            if ( !*(_BYTE *)(v377 + 8272) )
              goto LABEL_1172;
            if ( v696 )
              CDRecord::GetVersionRecPtr(&v697, v586);
            else
              FixedVarRecord::GetVersionRecPtr(&v697, v586);
            if ( VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v586) )
            {
LABEL_1039:
              v399 = *v720;
              if ( v717 )
                v400 = v399 >> 1;
              else
                v400 = v399 >> 6;
              if ( (v400 & 1) != 0 )
              {
                if ( v717 )
                  CDRecord::GetXdesTs(&v718, &v495);
                else
                  FixedVarRecord::GetXdesTs(&v718, &v495);
                if ( v496 || v495 )
                {
                  if ( v371 || !v435 || (*((_BYTE *)v435 + 16) & 0x20) == 0 )
                    goto LABEL_1066;
                  v401 = (*((_BYTE *)v373 + 536) & 4) != 0
                       ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v373 + 488LL))(v373) + 40
                       : (__int64)v373 + 40;
                  if ( v717 )
                    CDRecord::GetXdesTs(&v718, &v491);
                  else
                    FixedVarRecord::GetXdesTs(&v718, &v491);
                  if ( v492 != *(_WORD *)(v401 + 4) || v491 != *(_DWORD *)v401 )
                    goto LABEL_1066;
                  if ( (v402 = *((_QWORD *)v373 + 26), v375)
                    && (!v402
                     || !*(_BYTE *)(v402 + 52)
                     || !*(_QWORD *)(v402 + 64)
                     || (v403 = _InterlockedCompareExchange64((volatile signed __int64 *)(v402 + 296), 0, 0),
                         *(_QWORD *)(*(_QWORD *)v435 + 40LL) == v403))
                    || (VersionMgr::GetVersionWithUpdateMarker(
                          *((struct XVB **)v373 + 26),
                          *((const struct UserInfo **)v435 + 4),
                          *(const struct DBTABLE **)(v374 + 1712),
                          v447,
                          0x1F9Eu,
                          *(const struct UpdateSequenceMarker **)v435,
                          (struct Record *)&v717,
                          0,
                          1,
                          (struct VersionMgr::GetVersionResult *)&v440,
                          v372),
                        v375) )
                  {
                    if ( v717 )
                      CDRecord::GetVersionRecPtr(&v718, v587);
                    else
                      FixedVarRecord::GetVersionRecPtr(&v718, v587);
                    if ( v717 )
                      CDRecord::GetXdesTs(&v718, &v493);
                    else
                      FixedVarRecord::GetXdesTs(&v718, &v493);
                    v522 = v493;
                    v523 = v494;
                    if ( (unsigned int)XdesMgr::GetRowAbortState(v374 + 6600, &v522, v587) )
                    {
LABEL_1066:
                      v433 = v372;
                      if ( v696 == 1 )
                      {
                        v432 = v371;
                        v325 = v435;
                        VersionMgr::GetVersionFromCompressed(
                          (const struct PageRow *)&v696,
                          v447,
                          0x1F9Eu,
                          v373,
                          v435,
                          (struct PageRow *)&v717,
                          (struct VersionMgr::GetVersionResult *)&v440,
                          0,
                          0,
                          v432,
                          (const struct LSN *)&v733,
                          v433);
                      }
                      else
                      {
                        v431 = v371;
                        v325 = v435;
                        VersionMgr::GetVersionLong(
                          v447,
                          0x1F9Eu,
                          v373,
                          v435,
                          (struct Record *)&v717,
                          (struct VersionMgr::GetVersionResult *)&v440,
                          0,
                          0,
                          v431,
                          (const struct LSN *)&v733,
                          1,
                          v433);
                      }
LABEL_1019:
                      v329 = v436;
                      if ( *((_QWORD *)v436[1] + 48) && (!(_BYTE)v460 || !HIBYTE(v460)) )
                      {
                        PageRef::Unlatch(v439);
                        ex_raise(164, 1, 25, 2);
                      }
                      goto LABEL_853;
                    }
                  }
LABEL_1018:
                  v325 = v435;
                  goto LABEL_1019;
                }
              }
            }
            else
            {
LABEL_1172:
              if ( (byte_10317AD6E & 8) != 0
                || (v380 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v381 = **(struct CSessionTraceFlags ***)(v380 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v381, 0xF73u) )
              {
                v382 = *((_QWORD *)v373 + 26);
                if ( v382 )
                  v383 = *(_QWORD *)(v382 + 64);
                else
                  v383 = 0;
                v384 = *((_QWORD *)v373 + 82);
                v385 = *(unsigned __int16 *)(*((_QWORD *)v373 + 6) + 1720LL);
                v386 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v384 + 312LL))(v384);
                LogSystemMetadata(
                  L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v385,
                  *((_QWORD *)v435 + 5),
                  v386,
                  v383);
              }
            }
LABEL_1008:
            if ( (byte_10317AD6E & 8) != 0
              || (v387 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset,
                  *(_QWORD *)v387)
              && (v388 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v387 + 56LL)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v388, 0xF73u) )
            {
              CDStream::CDStream((CDStream *)v695);
              v389 = GetProcessHeap();
              v390 = (CTracePrintStream *)HeapAlloc(v389, 0, 0x6C0u);
              v589 = v390;
              if ( v390 )
                v391 = CTracePrintStream::CTracePrintStream(v390, 0);
              else
                v391 = 0;
              if ( v391 && !CDStream::AddDevice((CDStream *)v695, v391) )
                (**(void (__fastcall ***)(CTracePrintStream *, __int64))v391)(v391, 1);
              Record::Dump((Record *)&v717, (struct CDStream *)v695);
              CDStream::~CDStream((CDStream *)v695);
            }
            goto LABEL_1018;
          }
LABEL_1026:
          v485 = *(_QWORD *)(v46 + 40);
          v486 = *(_WORD *)(v46 + 48);
          goto LABEL_976;
        }
      }
      else if ( v370 == 8 )
      {
LABEL_1025:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_1026;
        goto LABEL_974;
      }
      if ( v370 != 9 )
        goto LABEL_1026;
      goto LABEL_1025;
    }
    break;
  }
  v86 = a8;
  if ( a8 )
  {
LABEL_82:
    v87 = (__int16 *)v446;
    v88 = v436;
  }
  else
  {
    v87 = (__int16 *)v446;
    v242 = (const struct Page *)v46;
    v88 = v436;
    VersionMgr::VerifyRowIsCurrent(*v436, v70, v242, *((__int16 *)v446 + 3));
  }
  v89 = *(_BYTE *)v699;
  if ( v696 )
  {
    if ( (v89 & 0x1C) == 4 && (v89 & 2) != 0 )
      goto LABEL_581;
  }
  else
  {
    if ( (v89 & 0xE) != 0xE )
      goto LABEL_85;
LABEL_581:
    if ( !v86 )
      BlobBase::TableCorruptException(
        *(_WORD *)(*((_QWORD *)*v88 + 6) + 1720LL),
        (const struct PageId *)v87,
        v87[3],
        11);
  }
LABEL_85:
  if ( dword_103172528 )
  {
    if ( v70 )
    {
      v298 = *v88;
      v299 = v435;
      v300 = (int)(*((_DWORD *)v435 + 4) << 31) >> 31;
      v301 = *(_BYTE *)(*((_QWORD *)*v88 + 6) + 7390LL);
      if ( !(**(unsigned __int8 (__fastcall ***)(struct XDES *))*v88)(*v88)
        && (v301
         || v300
         && ((*((_BYTE *)v299 + 16) & 0x40) == 0
          || (v302 = *((_QWORD *)v298 + 26)) != 0
          && *(_BYTE *)(v302 + 52)
          && *(_QWORD *)(v302 + 64)
          && *(_QWORD *)(*(_QWORD *)v299 + 40LL) != _InterlockedCompareExchange64(
                                                      (volatile signed __int64 *)(v302 + 296),
                                                      0,
                                                      0))) )
      {
        v303 = v88[1];
        v304 = *((_QWORD *)v303 + 12);
        if ( v304 && *(_BYTE *)(*(_QWORD *)(v304 + 8) + 63LL) )
          v305 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)(v304 + 592) + 88LL))(
                   **(_QWORD **)(v304 + 592),
                   *(_QWORD *)(*(_QWORD *)(v304 + 64) + 48LL));
        else
          v305 = *((_QWORD *)v303 + 14);
        v306 = *(_QWORD *)(v305 + 48);
        if ( *(_DWORD *)(*(_QWORD *)(v306 + 1712) + 1516LL) == 1 )
        {
          v307 = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)(v306 + 24));
          ++*v307;
        }
      }
    }
  }
  return (unsigned __int8 *)v66;
}

```

## disassembly

```asm
0x1005a8f50  mov     r11, rsp
0x1005a8f53  push    rbx
0x1005a8f54  push    rsi
0x1005a8f55  push    rdi
0x1005a8f56  push    r12
0x1005a8f58  push    r13
0x1005a8f5a  push    r14
0x1005a8f5c  push    r15
0x1005a8f5e  sub     rsp, 0CA0h
0x1005a8f65  mov     qword ptr [r11-778h], 0FFFFFFFFFFFFFFFEh
0x1005a8f70  movaps  xmmword ptr [r11-48h], xmm6
0x1005a8f75  mov     rax, cs:__security_cookie
0x1005a8f7c  xor     rax, rsp
0x1005a8f7f  mov     [rsp+0CD8h+var_58], rax
0x1005a8f87  mov     [rsp+0CD8h+var_B90], r9
0x1005a8f8f  mov     rax, r8
0x1005a8f92  mov     [rsp+0CD8h+var_C58], rax
0x1005a8f9a  mov     [rsp+0CD8h+var_C38], rdx
0x1005a8fa2  mov     rbx, rcx
0x1005a8fa5  mov     [rsp+0CD8h+var_C20], rcx
0x1005a8fad  mov     [rsp+0CD8h+var_8A0], rcx
0x1005a8fb5  mov     [rsp+0CD8h+var_C68], rcx
0x1005a8fba  mov     [rsp+0CD8h+var_980], rcx
0x1005a8fc2  mov     [rsp+0CD8h+var_970], rdx
0x1005a8fca  mov     [rsp+0CD8h+var_948], rdx
0x1005a8fd2  mov     [rsp+0CD8h+var_978], rax
0x1005a8fda  mov     [rsp+0CD8h+var_968], r9
0x1005a8fe2  mov     edi, dword ptr [rsp+0CD8h+arg_20]
0x1005a8fe9  mov     [rsp+0CD8h+var_C40], edi
0x1005a8ff0  mov     [rsp+0CD8h+var_A28], edi
0x1005a8ff7  mov     rax, [rsp+0CD8h+arg_30]
0x1005a8fff  mov     [rsp+0CD8h+var_C30], rax
0x1005a9007  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1005a900e  mov     [rsp+0CD8h+var_338], ax
0x1005a9016  xor     r13d, r13d
0x1005a9019  mov     [r11-330h], r13
0x1005a9020  mov     [r11-334h], r13d
0x1005a9027  mov     [r11-31Ah], r13
0x1005a902e  mov     [r11-310h], r13
0x1005a9035  mov     [r11-328h], r13
0x1005a903c  mov     [rsp+0CD8h+var_304], eax
0x1005a9043  mov     [r11-0C0Ch], r13d
0x1005a904a  xorps   xmm0, xmm0
0x1005a904d  movdqu  [rsp+0CD8h+var_928], xmm0
0x1005a9056  and     [rsp+0CD8h+var_918], 0FFFFFC00h
0x1005a9061  and     [rsp+0CD8h+var_914], 0FCh
0x1005a9069  movdqu  [rsp+0CD8h+var_910], xmm0
0x1005a9072  mov     [rsp+0CD8h+var_8F8], 0FFFFFFFFh
0x1005a907d  mov     eax, 0FFFFh
0x1005a9082  mov     [rsp+0CD8h+var_8F4], ax
0x1005a908a  mov     r12, rcx
0x1005a908d  mov     rax, [rcx+8]
0x1005a9091  mov     rcx, [rax+88h]
0x1005a9098  mov     [rsp+0CD8h+var_C70], rcx
0x1005a909d  mov     r15, [rax+180h]
0x1005a90a4  mov     [rsp+0CD8h+var_BF0], r15
0x1005a90ac  mov     esi, cs:?NullXdesId@@3VXdesId@@B; XdesId const NullXdesId
0x1005a90b2  mov     [rsp+0CD8h+var_C08], esi
0x1005a90b9  movzx   esi, cs:word_10318AB38
0x1005a90c0  mov     [rsp+0CD8h+var_C44], si
0x1005a90c8  mov     [rsp+0CD8h+var_B88], 0FFFh
0x1005a90d4  mov     [rsp+0CD8h+var_C78], 0Fh
0x1005a90dc  jmp     short loc_1005A90DF
0x1005a90df  mov     esi, 1
0x1005a90e4  mov     r14, 7FFFFFFFFFFFFFFFh
0x1005a90ee  mov     cl, 69h ; 'i'
0x1005a90f0  call    ?YieldAndCheckForAbort@@YAXW4ABORT_AND_LCK_EXCEPTIONS@@@Z; YieldAndCheckForAbort(ABORT_AND_LCK_EXCEPTIONS)
0x1005a90f5  mov     rax, [r12+0A0h]
0x1005a90fd  mov     [rsp+0CD8h+var_B48], rax
0x1005a9105  mov     rcx, [rsp+0CD8h+var_C38]
0x1005a910d  mov     eax, [rcx]
0x1005a910f  mov     [rsp+0CD8h+var_C4C], eax
0x1005a9116  movzx   eax, word ptr [rcx+4]
0x1005a911a  mov     [rsp+0CD8h+var_C48], ax
0x1005a9122  test    r15, r15
0x1005a9125  jnz     loc_1016A3B5C
0x1005a912b  mov     rsi, [rbx+8]
0x1005a912f  mov     [rsp+0CD8h+var_B98], rsi
0x1005a9137  mov     [rsp+0CD8h+var_8D4], 0
0x1005a9143  mov     rdx, gs:58h
0x1005a914c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a9153  mov     ecx, [rax]
0x1005a9155  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a915c  mov     ebx, [rax]
0x1005a915e  add     rbx, [rdx+rcx*8]
0x1005a9162  mov     r8, [rbx+100h]
0x1005a9169  test    r8, r8
0x1005a916c  jz      loc_1016A3BB0
0x1005a9172  rdtsc
0x1005a9174  shl     rdx, 20h
0x1005a9178  or      rax, rdx
0x1005a917b  mov     rdx, [r8+340h]
0x1005a9182  cmp     rax, rdx
0x1005a9185  ja      loc_1016A3BFA
0x1005a918b  cmp     rdx, r14
0x1005a918e  jz      short loc_1005A91A7
0x1005a9190  mov     rcx, [r8+260h]
0x1005a9197  sub     rdx, rax
0x1005a919a  cmp     rdx, [rcx+0DF0h]
0x1005a91a1  ja      loc_1016A3BFA
0x1005a91a7  mov     rcx, [r8+258h]
0x1005a91ae  mov     eax, [rcx+0BCh]
0x1005a91b4  test    al, 4
0x1005a91b6  jnz     loc_1016A3BC5
0x1005a91bc  mov     rax, [rsi+58h]
0x1005a91c0  mov     r14, [rax+20h]
0x1005a91c4  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x1005a91cb  cmp     byte ptr [rax], 0
0x1005a91ce  jz      loc_1016A3C21
0x1005a91d4  test    cs:byte_10317ABE6, 80h
0x1005a91db  jnz     loc_1016A3C21
0x1005a91e1  mov     r8, gs:58h
0x1005a91ea  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a91f1  mov     ecx, [rax]
0x1005a91f3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a91fa  mov     edx, [rax]
0x1005a91fc  add     rdx, [r8+rcx*8]
0x1005a9200  mov     rax, [rdx]
0x1005a9203  test    rax, rax
0x1005a9206  jz      short loc_1005A9218
0x1005a9208  mov     rax, [rax+38h]
0x1005a920c  mov     rcx, [rax]
0x1005a920f  test    rcx, rcx
0x1005a9212  jnz     loc_1016A3C0E
0x1005a9218  mov     r8, gs:58h
0x1005a9221  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1005a9228  mov     ecx, [rax]
0x1005a922a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1005a9231  mov     edx, [rax]
0x1005a9233  add     rdx, [r8+rcx*8]
0x1005a9237  mov     rax, [rdx+8]
0x1005a923b  test    rax, rax
0x1005a923e  jz      loc_1016A3C21
0x1005a9244  mov     r12, [rax+60h]
0x1005a9248  jmp     short loc_1005A924B
0x1005a924b  mov     r15, [r14+728h]
0x1005a9252  mov     rbx, [rsp+0CD8h+var_C58]
0x1005a925a  mov     [rsp+0CD8h+var_C10], r13d
0x1005a9262  mov     rax, [rbx]
0x1005a9265  mov     esi, 400h
0x1005a926a  test    rax, rax
0x1005a926d  jnz     loc_1016A3C2A
0x1005a9273  cmp     qword ptr [r14+728h], 0
0x1005a927b  jnz     loc_1016A3D4E
0x1005a9281  cmp     edi, 3
0x1005a9284  jge     loc_100601761
0x1005a928a  lea     rax, [rsp+0CD8h+var_8D8]
0x1005a9292  mov     [rsp+0CD8h+var_CB0], rax
0x1005a9297  mov     dword ptr [rsp+0CD8h+var_CB8], edi
0x1005a929b  lea     r9, [rsp+0CD8h+var_C10]
0x1005a92a3  lea     r8, [rsp+0CD8h+var_C4C]
0x1005a92ab  mov     rdx, r14
0x1005a92ae  mov     rcx, cs:qword_10317B628
0x1005a92b5  call    ?Get@BPool@@QEAAPEAUBUF@@AEAVRecoveryUnit@@AEBVPageId@@AEAHW4LATCH_TYPE@LatchBase@@PEAVLatchSuspendInfo@@@Z; BPool::Get(RecoveryUnit &,PageId const &,int &,LatchBase::LATCH_TYPE,LatchSuspendInfo *)
0x1005a92ba  mov     [rbx], rax
0x1005a92bd  mov     [rbx+0Ch], di
0x1005a92c1  test    r12, r12
0x1005a92c4  jz      short loc_1005A92EE
0x1005a92c6  mov     rcx, [rax]
0x1005a92c9  mov     eax, [r12+500h]
0x1005a92d1  and     eax, 0Fh
0x1005a92d4  cmp     [r12+rax*8+508h], rcx
0x1005a92dc  jz      short loc_1005A92EE
0x1005a92de  mov     [r12+rax*8+508h], rcx
0x1005a92e6  inc     qword ptr [r12+500h]
0x1005a92ee  mov     eax, [rsp+0CD8h+var_C10]
0x1005a92f5  shr     eax, 3
0x1005a92f8  and     al, 1
0x1005a92fa  mov     [rbx+0Fh], al
0x1005a92fd  mov     eax, [rsp+0CD8h+var_C10]
0x1005a9304  shr     eax, 4
0x1005a9307  and     al, 1
0x1005a9309  mov     [rbx+10h], al
0x1005a930c  test    r15, r15
0x1005a930f  jnz     loc_1016A3E9A
0x1005a9315  mov     rcx, r14; this
0x1005a9318  call    ?IsRbIoDb@RecoveryUnit@@QEBA_NXZ; RecoveryUnit::IsRbIoDb(void)
0x1005a931d  test    al, al
0x1005a931f  jnz     loc_1016A3F01
0x1005a9325  mov     r15d, 7
0x1005a932b  mov     rsi, [rsp+0CD8h+var_B98]
0x1005a9333  mov     rax, [rsi]
0x1005a9336  test    rax, rax
0x1005a9339  jz      short loc_1005A934D
0x1005a933b  test    dword ptr [rbx+0Ch], 0FF000000h
0x1005a9342  jnz     loc_1005AA56D
0x1005a9348  mov     rax, [rsi]
0x1005a934b  inc     dword ptr [rax]
0x1005a934d  cmp     dword ptr [rsp+0CD8h+var_8D4], 0
0x1005a9355  jnz     loc_1005AA586
0x1005a935b  mov     rax, [rbx]
0x1005a935e  mov     r12, [rax]
0x1005a9361  mov     r11, [rsp+0CD8h+var_C68]
0x1005a9366  mov     rdi, [rsp+0CD8h+var_B48]
0x1005a936e  cmp     dword ptr [rsp+0CD8h+arg_28], 1
0x1005a9376  jz      loc_1005A1063
0x1005a937c  mov     r8d, [rsp+0CD8h+var_C0C]
0x1005a9384  mov     ebx, 1
0x1005a9389  mov     rsi, [rsp+0CD8h+var_C38]
0x1005a9391  movsx   r10, word ptr [rsi+6]
0x1005a9396  movzx   eax, word ptr [r12+16h]
0x1005a939c  cmp     r10d, eax
0x1005a939f  jnb     loc_1016A481A
0x1005a93a5  mov     rcx, [rsp+0CD8h+var_B88]
0x1005a93ad  sub     rcx, r10
0x1005a93b0  cmp     word ptr [r12+rcx*2], 0
0x1005a93b6  mov     r9d, ebx
0x1005a93b9  jz      loc_1016A481A
0x1005a93bf  mov     rax, [rdi+8]
0x1005a93c3  test    rax, rax
0x1005a93c6  jnz     loc_1016A4823
0x1005a93cc  cmp     dword ptr [rdi+40h], 2
0x1005a93d0  jnz     loc_1016A4845
0x1005a93d6  mov     rcx, [rdi+30h]
0x1005a93da  mov     eax, [rcx]
0x1005a93dc  mov     [rsp+0CD8h+var_A08], eax
0x1005a93e3  movzx   eax, word ptr [rcx+4]
0x1005a93e7  mov     [rsp+0CD8h+var_A04], ax
0x1005a93ef  mov     [rsp+0CD8h+var_A02], r13w
0x1005a93f8  lea     rax, [rsp+0CD8h+var_A08]
0x1005a9400  jmp     short loc_1005A9403
0x1005a9403  mov     ecx, [rax]
0x1005a9405  mov     [rsp+0CD8h+var_9F8], ecx
0x1005a940c  movzx   eax, word ptr [rax+4]
0x1005a9410  mov     [rsp+0CD8h+var_9F4], ax
0x1005a9418  mov     edx, r13d
0x1005a941b  cmp     [r12+18h], ecx
0x1005a9420  jnz     short loc_1005A9433
0x1005a9422  movzx   ecx, word ptr [r12+6]
0x1005a9428  cmp     cx, ax
0x1005a942b  jnz     loc_1016A4875
0x1005a9431  mov     edx, ebx
0x1005a9433  test    r8d, r8d
0x1005a9436  jnz     loc_1016A4888
0x1005a943c  test    r9d, r9d
0x1005a943f  jz      loc_1016A4888
0x1005a9445  test    edx, edx
0x1005a9447  jz      loc_1016A4888
0x1005a944d  movsx   r15, word ptr [rsi+6]
0x1005a9452  mov     [rsp+0CD8h+var_304], r15d
0x1005a945a  cmp     byte ptr [r12+2], 0
0x1005a9460  jl      loc_1016A48AE
0x1005a9466  mov     rdi, r13
0x1005a9469  jmp     short loc_1005A946C
0x1005a946c  movzx   ebx, word ptr [r12+0Eh]
0x1005a9472  mov     rcx, [rsp+0CD8h+var_B88]
0x1005a947a  sub     rcx, r15
0x1005a947d  movzx   r9d, word ptr [r12+rcx*2]
0x1005a9482  add     r9, r12
0x1005a9485  lea     r15, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x1005a948c  test    byte ptr [r9], 1
0x1005a9490  mov     [rsp+0CD8h+var_330], r9
0x1005a9498  jnz     loc_1016A4D84
0x1005a949e  mov     [rsp+0CD8h+var_338], r13w
0x1005a94a7  mov     r8d, r13d
0x1005a94aa  mov     [rsp+0CD8h+var_334], r13d
0x1005a94b2  mov     dword ptr [rsp+0CD8h+var_312], r13d
0x1005a94ba  movzx   eax, byte ptr [r9]
0x1005a94be  and     eax, 0Eh
0x1005a94c1  movsxd  rdx, eax
0x1005a94c4  mov     eax, ds:(jpt_1005A94CF - 100400000h)[r15+rdx*4]; switch 15 cases
0x1005a94cc  add     rax, r15
0x1005a94cf  jmp     rax; switch jump
0x1005a94d1  movzx   ebx, word ptr [r9+2]; jumptable 00000001005A94CF cases 0,2,8,12
0x1005a94d6  lea     eax, [rbx-1]
0x1005a94d9  cmp     eax, 1F9Dh
0x1005a94de  ja      loc_1016A4F94
0x1005a94e4  mov     dword ptr [rsp+0CD8h+var_328], ebx; jumptable 00000001005A94CF cases 6,10
0x1005a94eb  lea     rax, [r12+2000h]
0x1005a94f3  mov     [rsp+0CD8h+var_320+6], rax
0x1005a94fb  mov     edi, ebx
0x1005a94fd  mov     rcx, [rsp+0CD8h+var_330]
0x1005a9505  mov     r14, rcx
0x1005a9508  mov     [rsp+0CD8h+var_B98], rcx
0x1005a9510  cmp     [rsp+0CD8h+var_338], 0
0x1005a9519  jnz     loc_1016A5648
0x1005a951f  test    r8d, r8d
0x1005a9522  jnz     loc_1005A9627
0x1005a9528  mov     [rsp+0CD8h+var_336], r13w
0x1005a9531  mov     dword ptr [rsp+0CD8h+var_328+4], ebx
0x1005a9538  movzx   eax, byte ptr [rcx]
0x1005a953b  mov     dword ptr [rsp+0CD8h+var_328+4], edi
0x1005a9542  test    al, 10h
0x1005a9544  jnz     loc_1016A4FF5
0x1005a954a  mov     rcx, [rsp+0CD8h+var_330]
0x1005a9552  test    byte ptr [rcx], 20h
0x1005a9555  jnz     loc_1016A5021
0x1005a955b  mov     r8d, edi
0x1005a955e  mov     [rsp+0CD8h+var_334], edi
0x1005a9565  mov     word ptr [rsp+0CD8h+var_320+4], r13w
0x1005a956e  mov     dword ptr [rsp+0CD8h+var_320], edi
0x1005a9575  mov     ebx, 4000h
0x1005a957a  mov     rax, [rsp+0CD8h+var_330]
0x1005a9582  test    byte ptr [rax], 40h
0x1005a9585  jz      loc_1004CD840
0x1005a958b  mov     dword ptr [rsp+0CD8h+var_312], r8d
0x1005a9593  add     r8d, 0Eh
0x1005a9597  mov     [rsp+0CD8h+var_334], r8d
0x1005a959f  lea     rcx, [rsp+0CD8h+var_336]; this
0x1005a95a7  call    ?FindVersioningInfo@FixedVarRecord@@AEBAPEAVRecVersioningInfo@@XZ; FixedVarRecord::FindVersioningInfo(void)
  ... truncated ...
```
