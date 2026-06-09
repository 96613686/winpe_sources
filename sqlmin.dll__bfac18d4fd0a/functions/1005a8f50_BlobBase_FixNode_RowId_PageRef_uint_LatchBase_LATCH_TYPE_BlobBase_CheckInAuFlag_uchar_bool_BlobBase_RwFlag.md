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
        __int64 a2,
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
  __int64 v80; // rcx
  struct XDES *v81; // rdi
  struct VersionScanParams *v82; // r15
  int v83; // ebx
  char v84; // si
  char v85; // bl
  __int16 *v86; // rsi
  struct XDES **v87; // r12
  char v88; // cl
  __int16 v90; // cx
  __int64 v91; // rax
  bool v92; // zf
  int v93; // edi
  __int64 *v94; // rbx
  __int64 v95; // rcx
  int v96; // edi
  __int64 v97; // rbx
  __int64 v98; // rcx
  int v99; // ecx
  __int64 v100; // r11
  char v101; // al
  int v102; // eax
  unsigned int v103; // ecx
  __int64 v104; // rdx
  __int64 v105; // rdx
  __int64 v106; // r11
  char v107; // cl
  __int16 v108; // si
  __int64 v109; // xmm1_8
  int v110; // edi
  __int64 *v111; // rbx
  __int64 v112; // rcx
  int v113; // eax
  unsigned int v114; // ecx
  LSN v115; // xmm0_8
  unsigned __int16 v116; // bx
  __int64 v117; // r11
  char v118; // al
  unsigned __int16 v119; // r11
  __int64 v120; // rax
  __int64 v121; // r10
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  int *v125; // rdx
  __int64 v126; // rcx
  int v127; // ecx
  int **v128; // rax
  __int16 v129; // ax
  __int16 v130; // r8
  __int64 v131; // rcx
  int *v132; // rcx
  __int64 v133; // rax
  int *v134; // rcx
  unsigned __int8 *v135; // r14
  __int16 v136; // r11
  char v137; // al
  __int16 v138; // dx
  unsigned __int64 v139; // rcx
  __int64 v140; // rcx
  __int64 v141; // rsi
  unsigned __int8 *v142; // r8
  unsigned __int8 v143; // dl
  __int16 v144; // dx
  __int16 v145; // cx
  unsigned int v146; // eax
  unsigned __int8 *v147; // rax
  __int16 v148; // cx
  PageComprInfoCache *v149; // rcx
  unsigned __int16 v150; // ax
  int v151; // eax
  int v152; // ebx
  unsigned __int16 v153; // cx
  int v154; // eax
  unsigned __int16 *v155; // rsi
  unsigned __int16 v156; // r9
  __int64 v157; // rax
  __int64 v158; // rax
  unsigned int v159; // r10d
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rax
  _BYTE *v164; // rcx
  unsigned int v165; // ebx
  _BYTE *v166; // rdx
  __int16 v167; // ax
  __int16 v168; // cx
  __int16 v169; // ax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  char v174; // cl
  bool v175; // zf
  unsigned int v176; // r9d
  __int64 v177; // r8
  unsigned __int64 v178; // rcx
  int v179; // eax
  unsigned int v180; // eax
  int v181; // ecx
  int v182; // eax
  __int64 v183; // rcx
  int XdesLockIfNecessary; // eax
  __int16 v185; // ax
  __int64 v186; // r8
  unsigned int Lock; // eax
  __int64 v188; // rdx
  int v189; // r15d
  __int64 v190; // rdx
  __int64 v191; // rcx
  _WORD *v192; // rax
  __int64 v193; // rax
  unsigned __int16 v194; // si
  __int64 v195; // r9
  unsigned int v196; // ebx
  __int16 v197; // di
  struct XDES *v198; // r8
  __int64 v199; // rcx
  __int64 v200; // rax
  unsigned int v201; // eax
  __int64 v202; // rdx
  _OWORD *v203; // rbx
  int v204; // edi
  char *v205; // r8
  char v206; // dl
  unsigned __int8 *v207; // r14
  __int16 v208; // r11
  char v209; // al
  __int16 v210; // dx
  unsigned __int64 v211; // rcx
  __int64 v212; // rcx
  __int64 v213; // rsi
  unsigned __int8 *v214; // r8
  unsigned __int8 v215; // dl
  __int16 v216; // dx
  __int16 v217; // cx
  unsigned int v218; // eax
  unsigned __int8 *v219; // rax
  __int16 v220; // cx
  PageComprInfoCache *v221; // rcx
  unsigned __int16 v222; // ax
  int v223; // eax
  int v224; // edi
  unsigned __int16 v225; // cx
  __int16 v226; // dx
  int v227; // ebx
  __int16 v228; // di
  struct XDES *v229; // r8
  __int64 v230; // rax
  __int64 v231; // r9
  __int64 v232; // rcx
  __int64 v233; // r9
  unsigned int v234; // eax
  __int64 v235; // rdx
  struct PageId *v236; // rbx
  __int64 v237; // rcx
  __int64 v238; // rcx
  __int16 v239; // ax
  int v240; // eax
  const struct Page *v241; // r8
  int *v242; // rcx
  int *v243; // rcx
  int *v244; // rcx
  __int64 v245; // r15
  __int128 *v246; // rbx
  unsigned int v247; // edi
  unsigned __int8 *v248; // r8
  unsigned __int8 *v249; // rdi
  __int16 v250; // r11
  char v251; // al
  __int16 v252; // dx
  unsigned __int64 v253; // rcx
  __int64 v254; // rcx
  __int64 v255; // r14
  unsigned __int8 *v256; // r8
  unsigned __int8 v257; // dl
  __int16 v258; // dx
  __int16 v259; // cx
  unsigned int v260; // eax
  unsigned __int8 *v261; // rax
  __int16 v262; // cx
  PageComprInfoCache *v263; // rcx
  unsigned __int16 v264; // ax
  int v265; // eax
  int v266; // esi
  unsigned __int16 v267; // cx
  int v268; // eax
  unsigned int v269; // r10d
  char v270; // al
  int v271; // eax
  unsigned __int16 *v272; // rsi
  __int64 v273; // rax
  __int64 v274; // rax
  unsigned int v275; // r9d
  __int64 v276; // rax
  __int64 v277; // rax
  __int64 v278; // rax
  __int64 v279; // rax
  _BYTE *v280; // rcx
  unsigned int v281; // edi
  unsigned __int16 v282; // r8
  _BYTE *v283; // rdx
  __int16 v284; // ax
  __int16 v285; // cx
  __int16 v286; // ax
  __int16 v287; // cx
  struct RecVersioningInfo *v288; // rax
  int v289; // r8d
  unsigned int v290; // ecx
  __int64 v291; // rax
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rax
  char v295; // cl
  int v296; // ecx
  struct XDES *v297; // rdi
  struct VersionScanParams *v298; // r15
  int v299; // ebx
  char v300; // si
  __int64 v301; // rcx
  struct XDES *v302; // rdx
  __int64 v303; // rcx
  __int64 v304; // rax
  __int64 v305; // rdx
  _QWORD *v306; // rax
  struct XDES **v307; // rbx
  struct XDES *v308; // rax
  __int64 v309; // rax
  __int64 v310; // rax
  __int64 v311; // rax
  int v312; // edi
  struct ForeignXdesContext *v313; // r14
  struct XDES *v314; // rbx
  __int64 Lsn; // rsi
  char *v316; // r13
  __int64 v317; // r15
  char v318; // r12
  __int64 v319; // rcx
  __int64 v320; // rdi
  __int64 v321; // rcx
  unsigned int v322; // ecx
  unsigned int v323; // ecx
  struct VersionScanParams *v324; // rsi
  __int64 v325; // rdi
  struct XVB **v326; // r10
  __int64 v327; // rcx
  LobContext **v328; // r14
  __int64 v329; // rbx
  struct Worker *v330; // rcx
  int v331; // eax
  struct PageId *v332; // r12
  char *v333; // rdx
  struct XDES *Xdes; // rax
  unsigned int v335; // edx
  unsigned __int8 *v336; // rdi
  unsigned __int16 v337; // r8
  __int64 v338; // rax
  __int64 v339; // rax
  unsigned int v340; // r9d
  __int64 v341; // rax
  __int64 v342; // rax
  __int64 v343; // rax
  __int64 v344; // rax
  unsigned __int8 *v345; // rcx
  unsigned int v346; // ebx
  unsigned __int16 v347; // r10
  unsigned int v348; // eax
  __int64 v349; // rax
  struct CSessionTraceFlags *v350; // rcx
  __int64 v351; // rax
  __int64 v352; // rdi
  __int64 v353; // rcx
  unsigned int v354; // ebx
  __int64 v355; // r9
  __int64 v356; // rax
  struct CSessionTraceFlags *v357; // rcx
  HANDLE ProcessHeap; // rax
  CTracePrintStream *v359; // rax
  CTracePrintStream *v360; // rbx
  __int64 v361; // rax
  struct CSessionTraceFlags *v362; // rcx
  __int64 v363; // rax
  __int64 v364; // rdi
  __int64 v365; // rcx
  unsigned int v366; // ebx
  __int64 v367; // r9
  int v368; // edi
  char v369; // al
  struct LSN *v370; // rsi
  struct OffRowPageRequestResult *v371; // r14
  struct XDES *v372; // rbx
  __int64 v373; // r15
  char v374; // r12
  __int64 v375; // rcx
  __int64 v376; // rdi
  __int64 v377; // rcx
  unsigned int v378; // eax
  __int64 v379; // rax
  struct CSessionTraceFlags *v380; // rcx
  __int64 v381; // rax
  __int64 v382; // rdi
  __int64 v383; // rcx
  unsigned int v384; // ebx
  __int64 v385; // r9
  __int64 v386; // rdx
  struct CSessionTraceFlags *v387; // rcx
  HANDLE v388; // rax
  CTracePrintStream *v389; // rax
  CTracePrintStream *v390; // rbx
  __int64 v391; // rax
  struct CSessionTraceFlags *v392; // rcx
  __int64 v393; // rax
  __int64 v394; // rdi
  __int64 v395; // rcx
  unsigned int v396; // ebx
  __int64 v397; // r9
  unsigned int v398; // ecx
  unsigned int v399; // ecx
  __int64 v400; // rdi
  __int64 v401; // rcx
  signed __int64 v402; // rax
  unsigned __int8 *v403; // r8
  __int16 v404; // ax
  __int16 v405; // cx
  struct RecVersioningInfo *v406; // rax
  __int64 v407; // rdx
  int v408; // r9d
  __int64 v409; // rax
  __int64 v410; // rax
  __int64 v411; // rax
  __int64 v412; // rax
  char v413; // cl
  bool v414; // zf
  LobContext *v415; // rdx
  __int64 v416; // rcx
  __int64 v417; // rax
  __int64 v418; // rcx
  _QWORD *ObjectDataImpl; // rax
  unsigned __int8 *v420; // rcx
  char v421; // dl
  LobContext *v422; // r9
  int v423; // r9d
  const struct SQLError *CurrentException; // rax
  signed __int32 v425[8]; // [rsp+0h] [rbp-CD8h] BYREF
  struct Record *v426; // [rsp+20h] [rbp-CB8h]
  struct Worker *v427; // [rsp+28h] [rbp-CB0h]
  struct Record *v428; // [rsp+30h] [rbp-CA8h]
  struct ForeignXdesContext *v429; // [rsp+38h] [rbp-CA0h]
  struct ForeignXdesContext *v430; // [rsp+40h] [rbp-C98h]
  struct LSN *v431; // [rsp+48h] [rbp-C90h]
  struct OffRowPageRequestResult *v432; // [rsp+58h] [rbp-C80h]
  unsigned int v433; // [rsp+60h] [rbp-C78h]
  struct VersionScanParams *v434; // [rsp+68h] [rbp-C70h]
  struct XDES **v435; // [rsp+70h] [rbp-C68h]
  char v436; // [rsp+78h] [rbp-C60h]
  char v437; // [rsp+79h] [rbp-C5Fh]
  PageRef *v438; // [rsp+80h] [rbp-C58h]
  int v439; // [rsp+88h] [rbp-C50h] BYREF
  int v440; // [rsp+8Ch] [rbp-C4Ch] BYREF
  __int16 v441; // [rsp+90h] [rbp-C48h]
  __int16 v442; // [rsp+94h] [rbp-C44h]
  int v443; // [rsp+98h] [rbp-C40h]
  __int16 v444; // [rsp+9Ch] [rbp-C3Ch]
  struct PageId *v445; // [rsp+A0h] [rbp-C38h]
  unsigned __int8 *v446; // [rsp+A8h] [rbp-C30h]
  char v447; // [rsp+B0h] [rbp-C28h]
  char v448; // [rsp+B1h] [rbp-C27h]
  char v449; // [rsp+B2h] [rbp-C26h]
  struct XDES **v450; // [rsp+B8h] [rbp-C20h]
  __int64 v451; // [rsp+C0h] [rbp-C18h] BYREF
  int v452; // [rsp+C8h] [rbp-C10h] BYREF
  int v453; // [rsp+CCh] [rbp-C0Ch]
  unsigned int v454; // [rsp+D0h] [rbp-C08h]
  int v455; // [rsp+D4h] [rbp-C04h] BYREF
  __int16 v456; // [rsp+D8h] [rbp-C00h]
  unsigned int v457; // [rsp+DAh] [rbp-BFEh] BYREF
  unsigned __int16 v458; // [rsp+DEh] [rbp-BFAh]
  __int16 v459; // [rsp+E0h] [rbp-BF8h] BYREF
  int v460; // [rsp+E2h] [rbp-BF6h]
  __int16 v461; // [rsp+E6h] [rbp-BF2h]
  __int64 v462; // [rsp+E8h] [rbp-BF0h]
  int v463; // [rsp+F0h] [rbp-BE8h] BYREF
  __int16 v464; // [rsp+F4h] [rbp-BE4h]
  __int16 v465; // [rsp+F6h] [rbp-BE2h]
  int v466; // [rsp+F8h] [rbp-BE0h] BYREF
  __int16 v467; // [rsp+FCh] [rbp-BDCh]
  __int16 v468; // [rsp+FEh] [rbp-BDAh]
  __int64 v469; // [rsp+100h] [rbp-BD8h] BYREF
  int v470; // [rsp+108h] [rbp-BD0h] BYREF
  __int16 v471; // [rsp+10Ch] [rbp-BCCh]
  int v472; // [rsp+110h] [rbp-BC8h] BYREF
  __int16 v473; // [rsp+114h] [rbp-BC4h]
  unsigned int v474; // [rsp+120h] [rbp-BB8h] BYREF
  unsigned __int16 v475; // [rsp+124h] [rbp-BB4h]
  int v476; // [rsp+130h] [rbp-BA8h] BYREF
  __int16 v477; // [rsp+134h] [rbp-BA4h]
  int v478; // [rsp+136h] [rbp-BA2h] BYREF
  __int16 v479; // [rsp+13Ah] [rbp-B9Eh]
  int v480; // [rsp+13Ch] [rbp-B9Ch]
  struct XDES *v481; // [rsp+140h] [rbp-B98h]
  unsigned int *v482; // [rsp+148h] [rbp-B90h]
  __int64 v483; // [rsp+150h] [rbp-B88h]
  __int64 v484; // [rsp+158h] [rbp-B80h] BYREF
  unsigned __int16 v485; // [rsp+160h] [rbp-B78h]
  LSN v486; // [rsp+168h] [rbp-B70h] BYREF
  unsigned __int16 v487; // [rsp+170h] [rbp-B68h]
  int v488; // [rsp+178h] [rbp-B60h] BYREF
  __int16 v489; // [rsp+17Ch] [rbp-B5Ch]
  int v490; // [rsp+17Eh] [rbp-B5Ah] BYREF
  __int16 v491; // [rsp+182h] [rbp-B56h]
  int v492; // [rsp+184h] [rbp-B54h] BYREF
  __int16 v493; // [rsp+188h] [rbp-B50h]
  int v494; // [rsp+18Ah] [rbp-B4Eh] BYREF
  __int16 v495; // [rsp+18Eh] [rbp-B4Ah]
  struct XDES *v496; // [rsp+190h] [rbp-B48h]
  struct XDES *v497; // [rsp+198h] [rbp-B40h]
  __int64 v498; // [rsp+1A0h] [rbp-B38h] BYREF
  unsigned __int16 v499; // [rsp+1A8h] [rbp-B30h]
  unsigned __int64 v500; // [rsp+1B0h] [rbp-B28h] BYREF
  __int16 v501; // [rsp+1B8h] [rbp-B20h]
  unsigned __int64 v502; // [rsp+1C0h] [rbp-B18h] BYREF
  __int16 v503; // [rsp+1C8h] [rbp-B10h]
  unsigned __int64 v504; // [rsp+1D0h] [rbp-B08h] BYREF
  __int16 v505; // [rsp+1D8h] [rbp-B00h]
  int v506; // [rsp+1E0h] [rbp-AF8h]
  int v507; // [rsp+1F0h] [rbp-AE8h] BYREF
  __int16 v508; // [rsp+1F4h] [rbp-AE4h]
  int v509; // [rsp+200h] [rbp-AD8h] BYREF
  __int16 v510; // [rsp+204h] [rbp-AD4h]
  unsigned int v511; // [rsp+210h] [rbp-AC8h] BYREF
  unsigned __int16 v512; // [rsp+214h] [rbp-AC4h]
  unsigned int v513; // [rsp+220h] [rbp-AB8h] BYREF
  __int16 v514; // [rsp+224h] [rbp-AB4h]
  int v515; // [rsp+230h] [rbp-AA8h] BYREF
  __int16 v516; // [rsp+234h] [rbp-AA4h]
  int v517; // [rsp+238h] [rbp-AA0h] BYREF
  __int16 v518; // [rsp+23Ch] [rbp-A9Ch]
  int v519; // [rsp+240h] [rbp-A98h] BYREF
  __int16 v520; // [rsp+244h] [rbp-A94h]
  int v521; // [rsp+248h] [rbp-A90h] BYREF
  __int16 v522; // [rsp+24Ch] [rbp-A8Ch]
  int v523; // [rsp+250h] [rbp-A88h] BYREF
  __int16 v524; // [rsp+254h] [rbp-A84h]
  int v525; // [rsp+260h] [rbp-A78h] BYREF
  __int16 v526; // [rsp+264h] [rbp-A74h]
  int v527; // [rsp+268h] [rbp-A70h] BYREF
  __int16 v528; // [rsp+26Ch] [rbp-A6Ch]
  int v529; // [rsp+270h] [rbp-A68h] BYREF
  __int16 v530; // [rsp+274h] [rbp-A64h]
  int v531; // [rsp+278h] [rbp-A60h] BYREF
  __int16 v532; // [rsp+27Ch] [rbp-A5Ch]
  int v533; // [rsp+280h] [rbp-A58h] BYREF
  __int16 v534; // [rsp+284h] [rbp-A54h]
  __int64 v535; // [rsp+288h] [rbp-A50h] BYREF
  __int16 v536; // [rsp+290h] [rbp-A48h]
  unsigned __int16 v537; // [rsp+298h] [rbp-A40h]
  unsigned __int16 v538; // [rsp+29Ah] [rbp-A3Eh]
  __int16 v539; // [rsp+2A0h] [rbp-A38h]
  unsigned int v540; // [rsp+2A8h] [rbp-A30h] BYREF
  int v541; // [rsp+2ACh] [rbp-A2Ch] BYREF
  int v542; // [rsp+2B0h] [rbp-A28h]
  int v543; // [rsp+2B8h] [rbp-A20h]
  int v544; // [rsp+2BCh] [rbp-A1Ch]
  int v545; // [rsp+2C0h] [rbp-A18h] BYREF
  __int16 v546; // [rsp+2C4h] [rbp-A14h]
  __int16 v547; // [rsp+2C6h] [rbp-A12h]
  int v548; // [rsp+2C8h] [rbp-A10h] BYREF
  __int16 v549; // [rsp+2CCh] [rbp-A0Ch]
  __int16 v550; // [rsp+2CEh] [rbp-A0Ah]
  int v551; // [rsp+2D0h] [rbp-A08h] BYREF
  __int16 v552; // [rsp+2D4h] [rbp-A04h]
  __int16 v553; // [rsp+2D6h] [rbp-A02h]
  int v554; // [rsp+2D8h] [rbp-A00h] BYREF
  __int16 v555; // [rsp+2DCh] [rbp-9FCh]
  __int16 v556; // [rsp+2DEh] [rbp-9FAh]
  int v557; // [rsp+2E0h] [rbp-9F8h]
  __int16 v558; // [rsp+2E4h] [rbp-9F4h]
  int v559; // [rsp+2E8h] [rbp-9F0h] BYREF
  __int16 v560; // [rsp+2ECh] [rbp-9ECh]
  __int16 v561; // [rsp+2EEh] [rbp-9EAh]
  int v562; // [rsp+2F0h] [rbp-9E8h] BYREF
  __int16 v563; // [rsp+2F4h] [rbp-9E4h]
  __int16 v564; // [rsp+2F6h] [rbp-9E2h]
  int v565; // [rsp+2F8h] [rbp-9E0h] BYREF
  __int16 v566; // [rsp+2FCh] [rbp-9DCh]
  __int16 v567; // [rsp+2FEh] [rbp-9DAh]
  char v568[8]; // [rsp+300h] [rbp-9D8h] BYREF
  char v569[8]; // [rsp+308h] [rbp-9D0h] BYREF
  char v570[8]; // [rsp+310h] [rbp-9C8h] BYREF
  int v571; // [rsp+318h] [rbp-9C0h]
  __int64 v572; // [rsp+31Ch] [rbp-9BCh]
  int v573; // [rsp+324h] [rbp-9B4h]
  LSN v574; // [rsp+328h] [rbp-9B0h]
  int v575; // [rsp+330h] [rbp-9A8h]
  __int64 v576; // [rsp+338h] [rbp-9A0h]
  __int16 v577; // [rsp+340h] [rbp-998h]
  __int64 v578; // [rsp+348h] [rbp-990h] BYREF
  __int16 v579; // [rsp+350h] [rbp-988h]
  struct XDES **v580; // [rsp+358h] [rbp-980h]
  PageRef *v581; // [rsp+360h] [rbp-978h]
  struct PageId *v582; // [rsp+368h] [rbp-970h]
  unsigned int *v583; // [rsp+370h] [rbp-968h]
  char v584[8]; // [rsp+378h] [rbp-960h] BYREF
  char v585[8]; // [rsp+380h] [rbp-958h] BYREF
  char v586[8]; // [rsp+388h] [rbp-950h] BYREF
  __int64 v587; // [rsp+390h] [rbp-948h]
  CTracePrintStream *v588; // [rsp+398h] [rbp-940h]
  __int64 v589; // [rsp+3A0h] [rbp-938h]
  struct ForeignXdesContext *v590; // [rsp+3A8h] [rbp-930h]
  __int128 v591; // [rsp+3B0h] [rbp-928h] BYREF
  unsigned int v592; // [rsp+3C0h] [rbp-918h]
  char v593; // [rsp+3C4h] [rbp-914h]
  __int128 v594; // [rsp+3C8h] [rbp-910h]
  unsigned __int64 v595; // [rsp+3D8h] [rbp-900h]
  int v596; // [rsp+3E0h] [rbp-8F8h]
  __int16 v597; // [rsp+3E4h] [rbp-8F4h]
  int v598; // [rsp+3E8h] [rbp-8F0h]
  int v599; // [rsp+3F0h] [rbp-8E8h]
  int v600; // [rsp+3F8h] [rbp-8E0h]
  unsigned int v601; // [rsp+400h] [rbp-8D8h] BYREF
  __int64 v602; // [rsp+404h] [rbp-8D4h]
  __int64 v603; // [rsp+418h] [rbp-8C0h] BYREF
  __int16 v604; // [rsp+420h] [rbp-8B8h]
  LSN v605; // [rsp+428h] [rbp-8B0h] BYREF
  __int16 v606; // [rsp+430h] [rbp-8A8h]
  struct XDES **v607; // [rsp+438h] [rbp-8A0h]
  struct CSessionTraceFlags *v608; // [rsp+440h] [rbp-898h]
  int v609; // [rsp+448h] [rbp-890h]
  int v610; // [rsp+450h] [rbp-888h]
  int v611; // [rsp+458h] [rbp-880h]
  DWORD v612; // [rsp+45Ch] [rbp-87Ch] BYREF
  DWORD v613; // [rsp+460h] [rbp-878h] BYREF
  DWORD flOldProtect; // [rsp+464h] [rbp-874h] BYREF
  struct CSessionTraceFlags *v615; // [rsp+468h] [rbp-870h]
  struct CSessionTraceFlags *v616; // [rsp+470h] [rbp-868h]
  __int64 v617; // [rsp+478h] [rbp-860h]
  int v618; // [rsp+480h] [rbp-858h]
  _QWORD v619[3]; // [rsp+488h] [rbp-850h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+4A0h] [rbp-838h]
  __int64 *v621; // [rsp+4A8h] [rbp-830h]
  __int64 v622; // [rsp+4B0h] [rbp-828h]
  struct CSessionTraceFlags *v623; // [rsp+4B8h] [rbp-820h]
  __int64 v624; // [rsp+4C0h] [rbp-818h]
  int *v625; // [rsp+4C8h] [rbp-810h]
  __int64 v626; // [rsp+4D0h] [rbp-808h]
  int *v627; // [rsp+4D8h] [rbp-800h]
  __int64 v628; // [rsp+4E0h] [rbp-7F8h]
  signed __int64 v629; // [rsp+4E8h] [rbp-7F0h]
  char *v630; // [rsp+4F0h] [rbp-7E8h]
  _QWORD *v631; // [rsp+4F8h] [rbp-7E0h]
  __int64 *v632; // [rsp+500h] [rbp-7D8h]
  struct CSessionTraceFlags *v633; // [rsp+508h] [rbp-7D0h]
  CTracePrintStream *v634; // [rsp+510h] [rbp-7C8h]
  CTracePrintStream *v635; // [rsp+518h] [rbp-7C0h]
  CTracePrintStream *v636; // [rsp+520h] [rbp-7B8h]
  CTracePrintStream *v637; // [rsp+528h] [rbp-7B0h]
  int *v638; // [rsp+530h] [rbp-7A8h]
  __int64 v639; // [rsp+538h] [rbp-7A0h]
  __int64 v640; // [rsp+540h] [rbp-798h]
  unsigned __int64 v641; // [rsp+548h] [rbp-790h]
  __int64 *v642; // [rsp+550h] [rbp-788h]
  __int64 v643; // [rsp+560h] [rbp-778h]
  __int64 *v644; // [rsp+578h] [rbp-760h]
  __int64 v645; // [rsp+580h] [rbp-758h]
  __int64 v646; // [rsp+588h] [rbp-750h]
  __int64 v647; // [rsp+590h] [rbp-748h]
  __int64 v648; // [rsp+598h] [rbp-740h]
  __int64 v649; // [rsp+5A0h] [rbp-738h]
  char *v650; // [rsp+5A8h] [rbp-730h]
  __int64 v651; // [rsp+5B0h] [rbp-728h]
  __int64 v652; // [rsp+5B8h] [rbp-720h]
  char *v653; // [rsp+5C0h] [rbp-718h]
  _QWORD *v654; // [rsp+5C8h] [rbp-710h]
  __int64 *v655; // [rsp+5D0h] [rbp-708h]
  __int64 v656; // [rsp+5D8h] [rbp-700h]
  struct CSessionTraceFlags *v657; // [rsp+5E0h] [rbp-6F8h]
  _DWORD v658[6]; // [rsp+5E8h] [rbp-6F0h] BYREF
  char v659[16]; // [rsp+600h] [rbp-6D8h] BYREF
  char v660[8]; // [rsp+610h] [rbp-6C8h] BYREF
  int v661; // [rsp+618h] [rbp-6C0h]
  int v662; // [rsp+620h] [rbp-6B8h]
  int **v663; // [rsp+628h] [rbp-6B0h]
  char *v664; // [rsp+630h] [rbp-6A8h]
  __int64 v665; // [rsp+638h] [rbp-6A0h]
  int *v666; // [rsp+640h] [rbp-698h] BYREF
  int v667; // [rsp+648h] [rbp-690h]
  int v668; // [rsp+64Ch] [rbp-68Ch]
  GUID *v669; // [rsp+650h] [rbp-688h]
  int v670; // [rsp+658h] [rbp-680h]
  int v671; // [rsp+65Ch] [rbp-67Ch]
  GUID *v672; // [rsp+660h] [rbp-678h]
  int v673; // [rsp+668h] [rbp-670h]
  int v674; // [rsp+66Ch] [rbp-66Ch]
  wchar_t *v675; // [rsp+670h] [rbp-668h]
  int v676; // [rsp+678h] [rbp-660h]
  int v677; // [rsp+67Ch] [rbp-65Ch]
  wchar_t *v678; // [rsp+680h] [rbp-658h]
  int v679; // [rsp+688h] [rbp-650h]
  int v680; // [rsp+68Ch] [rbp-64Ch]
  __int64 v681; // [rsp+690h] [rbp-648h]
  int v682; // [rsp+698h] [rbp-640h]
  int v683; // [rsp+69Ch] [rbp-63Ch]
  char v684; // [rsp+6A0h] [rbp-638h] BYREF
  __int64 v685; // [rsp+860h] [rbp-478h]
  __int64 v686; // [rsp+868h] [rbp-470h]
  int v687; // [rsp+870h] [rbp-468h] BYREF
  __int16 v688; // [rsp+874h] [rbp-464h]
  int v689; // [rsp+876h] [rbp-462h]
  char v690; // [rsp+87Ah] [rbp-45Eh]
  char v691; // [rsp+87Bh] [rbp-45Dh]
  _BYTE v692[48]; // [rsp+8B0h] [rbp-428h] BYREF
  _BYTE v693[96]; // [rsp+8E0h] [rbp-3F8h] BYREF
  _BYTE v694[96]; // [rsp+940h] [rbp-398h] BYREF
  __int16 v695; // [rsp+9A0h] [rbp-338h] BYREF
  unsigned __int16 v696; // [rsp+9A2h] [rbp-336h] BYREF
  unsigned int v697; // [rsp+9A4h] [rbp-334h]
  struct XDES *v698; // [rsp+9A8h] [rbp-330h]
  __int128 *v699; // [rsp+9B0h] [rbp-328h]
  _BYTE v700[24]; // [rsp+9B8h] [rbp-320h]
  int v701; // [rsp+9D0h] [rbp-308h]
  int v702; // [rsp+9D4h] [rbp-304h]
  __int128 v703; // [rsp+9D8h] [rbp-300h] BYREF
  __int128 v704; // [rsp+9E8h] [rbp-2F0h]
  _BYTE v705[22]; // [rsp+9F8h] [rbp-2E0h] BYREF
  __int16 v706; // [rsp+A0Eh] [rbp-2CAh]
  __int64 v707; // [rsp+A10h] [rbp-2C8h]
  __int128 v708; // [rsp+A18h] [rbp-2C0h]
  __int128 v709; // [rsp+A28h] [rbp-2B0h]
  __int128 v710; // [rsp+A38h] [rbp-2A0h]
  __int64 v711; // [rsp+A48h] [rbp-290h]
  __int64 v712; // [rsp+A50h] [rbp-288h] BYREF
  int v713; // [rsp+A58h] [rbp-280h]
  __int64 v714; // [rsp+A60h] [rbp-278h]
  char v715; // [rsp+A68h] [rbp-270h]
  __int16 v716; // [rsp+A70h] [rbp-268h] BYREF
  __int16 v717; // [rsp+A72h] [rbp-266h] BYREF
  unsigned int v718; // [rsp+A74h] [rbp-264h]
  unsigned __int8 *v719; // [rsp+A78h] [rbp-260h]
  __int64 v720; // [rsp+A80h] [rbp-258h]
  unsigned int v721; // [rsp+A88h] [rbp-250h]
  unsigned __int16 v722; // [rsp+A8Ch] [rbp-24Ch]
  unsigned __int64 v723; // [rsp+A8Eh] [rbp-24Ah]
  _TBYTE v724; // [rsp+A96h] [rbp-242h]
  int v725; // [rsp+AA4h] [rbp-234h]
  int v726; // [rsp+B20h] [rbp-1B8h] BYREF
  __int64 v727; // [rsp+B24h] [rbp-1B4h]
  __int16 v728; // [rsp+B2Ch] [rbp-1ACh]
  char v729; // [rsp+B2Eh] [rbp-1AAh]
  _DWORD v730[2]; // [rsp+B30h] [rbp-1A8h] BYREF
  __int16 v731; // [rsp+B38h] [rbp-1A0h]
  __int64 v732; // [rsp+B40h] [rbp-198h] BYREF
  __int16 v733; // [rsp+B48h] [rbp-190h]
  __int16 v734; // [rsp+B50h] [rbp-188h]
  unsigned __int16 v735; // [rsp+B52h] [rbp-186h] BYREF
  int v736; // [rsp+B54h] [rbp-184h]
  char *v737; // [rsp+B58h] [rbp-180h]
  _OWORD *v738; // [rsp+B60h] [rbp-178h]
  _BYTE v739[24]; // [rsp+B68h] [rbp-170h]
  int v740; // [rsp+B80h] [rbp-158h]
  int v741; // [rsp+B84h] [rbp-154h]
  _OWORD v742[7]; // [rsp+B88h] [rbp-150h] BYREF
  __int64 v743; // [rsp+BF8h] [rbp-E0h]
  __int64 v744; // [rsp+C00h] [rbp-D8h] BYREF
  int v745; // [rsp+C08h] [rbp-D0h]
  __int16 v746; // [rsp+C0Ch] [rbp-CCh]
  __int16 v747; // [rsp+C0Eh] [rbp-CAh]
  __int64 v748; // [rsp+C10h] [rbp-C8h]
  __int64 v749; // [rsp+C18h] [rbp-C0h]
  wchar_t v750[24]; // [rsp+C20h] [rbp-B8h] BYREF
  wchar_t v751[24]; // [rsp+C50h] [rbp-88h] BYREF

  v643 = -2;
  v482 = a4;
  v438 = a3;
  v445 = (struct PageId *)a2;
  v21 = (struct XDES **)a1;
  v450 = (struct XDES **)a1;
  v607 = (struct XDES **)a1;
  v435 = (struct XDES **)a1;
  v580 = (struct XDES **)a1;
  v582 = (struct PageId *)a2;
  v587 = a2;
  v581 = a3;
  v583 = a4;
  v22 = a5;
  v443 = a5;
  v542 = a5;
  v446 = a7;
  v695 = -1;
  v23 = 0;
  v698 = 0;
  v697 = 0;
  *(_QWORD *)&v700[6] = 0;
  *(_QWORD *)&v700[16] = 0;
  v699 = 0;
  v702 = -1;
  v453 = 0;
  v591 = 0;
  v592 &= 0xFFFFFC00;
  v593 &= 0xFCu;
  v594 = 0;
  v596 = -1;
  v597 = -1;
  v24 = (struct XDES **)a1;
  v25 = *(_QWORD *)(a1 + 8);
  v26 = *(struct VersionScanParams **)(v25 + 136);
  v434 = v26;
  v27 = *(_QWORD *)(v25 + 384);
  v462 = v27;
  v454 = NullXdesId;
  v442 = word_10318AB38;
  v483 = 4095;
  v433 = 15;
  while ( 2 )
  {
    while ( 2 )
    {
      LOBYTE(v26) = 105;
      YieldAndCheckForAbort(v26, a2);
      v496 = v24[20];
      v440 = *(_DWORD *)v445;
      v441 = *((_WORD *)v445 + 2);
      if ( v27 )
      {
        if ( !RecoveryUnit::IsForeignPageTrackedByCurrenPageServer(v24[4], v445) )
          ex_raise(164, 1, 25, 1);
        v28 = v24[1];
        v90 = *(_WORD *)(*((_QWORD *)v28 + 48) + 26LL);
        v440 = *(_DWORD *)v445;
        v441 = v90;
      }
      else
      {
        v28 = v21[1];
      }
      v481 = v28;
      v602 = 0;
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
        v92 = (unsigned int)SOS_Task::Sleep(0, yieldWait) == 2;
LABEL_116:
        if ( v92 )
        {
          LOBYTE(v33) = -90;
          RaiseExecutionAbortedError(v33);
        }
        goto LABEL_10;
      }
      v33 = v30[75];
      if ( (*(_DWORD *)(v33 + 188) & 4) != 0 )
      {
        v91 = *(_QWORD *)(v33 + 152);
        if ( (*(_BYTE *)(v91 + 616) & 1) == 0 )
        {
          v92 = (*(_DWORD *)(v91 + 800) & 0x180) == 0;
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
      v40 = v438;
      while ( 1 )
      {
        v452 = 0;
        if ( !*(_QWORD *)v40 )
          goto LABEL_18;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_18;
        }
        v93 = *((__int16 *)v40 + 6);
        v94 = *(__int64 **)v40;
        if ( (*((_WORD *)v94 + 49) & 8) != 0 )
        {
          if ( v93 == 3 )
          {
            v93 = 4;
LABEL_127:
            if ( (*((_DWORD *)v94 + 25) & 8) != 0 )
            {
              v95 = v94[18];
              if ( v95 )
              {
                if ( *(_QWORD *)(v95 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v95 + 1880), v94, (unsigned int)v93);
                }
              }
            }
            goto LABEL_131;
          }
          if ( v93 >= 2 )
            goto LABEL_127;
        }
LABEL_131:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v94 + 25) & 8) != 0
          && v93 >= 3
          && (*((_DWORD *)v94 + 25) & 0xC0000000) != 0x40000000
          && *v94
          && VirtualProtect((LPVOID)*v94, 0x2000u, 2u, &flOldProtect) )
        {
          _InterlockedAnd((volatile signed __int32 *)v94 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v94 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v94 + 19, (unsigned int)v93);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v94, 0, (unsigned int)v93);
        v40 = v438;
        *((_WORD *)v438 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v443;
LABEL_18:
        if ( !*(_QWORD *)(v34 + 1832) )
          goto LABEL_19;
        if ( v22 < 2 )
          goto LABEL_19;
        PageRef::CatchupPageRedos(v40, (const struct PageId *)&v440, (struct RecoveryUnit *)v34);
        if ( !*(_QWORD *)v40 )
          goto LABEL_19;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_19;
        }
        v96 = *((__int16 *)v40 + 6);
        v97 = *(_QWORD *)v40;
        if ( (*(_WORD *)(v97 + 98) & 8) != 0 )
        {
          if ( v96 == 3 )
          {
            v96 = 4;
LABEL_152:
            if ( (*(_DWORD *)(v97 + 100) & 8) != 0 )
            {
              v98 = *(_QWORD *)(v97 + 144);
              if ( v98 )
              {
                if ( *(_QWORD *)(v98 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v98 + 1880), v97, (unsigned int)v96);
                }
              }
            }
            goto LABEL_156;
          }
          if ( v96 >= 2 )
            goto LABEL_152;
        }
LABEL_156:
        if ( byte_10317ABE5 < 0
          && (*(_DWORD *)(v97 + 100) & 8) != 0
          && v96 >= 3
          && (*(_DWORD *)(v97 + 100) & 0xC0000000) != 0x40000000
          && *(_QWORD *)v97
          && VirtualProtect(*(LPVOID *)v97, 0x2000u, 2u, &v613) )
        {
          _InterlockedAnd((volatile signed __int32 *)(v97 + 100), 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)(v97 + 100), 0x40000000u);
        }
        LatchBase::ReleaseInternal(v97 + 152, (unsigned int)v96);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v97, 0, (unsigned int)v96);
        v40 = v438;
        *((_WORD *)v438 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v443;
LABEL_19:
        if ( v22 >= 3 )
          RecoveryUnit::PrePageUpdateHint((RecoveryUnit *)v34, (const struct PageId *)&v440);
        LODWORD(v426) = v22;
        v41 = (__int64 *)BPool::Get(qword_10317B628, v34, &v440, &v452, v426, &v601);
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
        *((_BYTE *)v40 + 15) = (v452 & 8) != 0;
        *((_BYTE *)v40 + 16) = (v452 & 0x10) != 0;
        if ( v39 )
        {
          if ( SETLSFromTlsMaybeNull )
          {
            if ( SETLSFromTlsMaybeNull == *(struct SEInternalTLS **)(v34 + 7224) )
            {
              v99 = *((char *)v40 + 15);
              ++v39[2917];
              if ( (_DWORD)v602 )
              {
                ++v39[2918];
                v39[2919] += v601;
                if ( v99 )
                {
                  ++v39[2920];
                  v39[2921] += v601;
                }
              }
            }
          }
        }
        if ( !RecoveryUnit::IsRbIoDb((RecoveryUnit *)v34)
          || !*(_BYTE *)(v34 + 8272)
          || v22 < 2
          || !v440
          || v440 == 9 && v441 == 1 )
        {
          goto LABEL_26;
        }
        v100 = **(_QWORD **)v40;
        if ( !*(_WORD *)(v100 + 36) )
        {
LABEL_211:
          v498 = *(_QWORD *)(v100 + 40);
          v499 = *(_WORD *)(v100 + 48);
          goto LABEL_184;
        }
        v101 = *(_BYTE *)(v100 + 1);
        if ( v101 == 11 )
        {
          if ( *(_DWORD *)(v100 + 24) == 99 )
            goto LABEL_182;
        }
        else if ( v101 == 8 )
        {
          goto LABEL_210;
        }
        if ( v101 != 9 )
          goto LABEL_211;
LABEL_210:
        if ( *(_DWORD *)(v100 + 24) != 99 )
          goto LABEL_211;
LABEL_182:
        v533 = *(_DWORD *)(v100 + 32);
        v534 = *(_WORD *)(v100 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v533, v44) )
          goto LABEL_211;
        PageHeader::GetIcxLsn(v100, &v498);
LABEL_184:
        v102 = *(_DWORD *)(v34 + 8456);
        do
        {
          v103 = v102 & 0xFFFFFFFE;
          v572 = *(_QWORD *)(v34 + 8444);
          v573 = *(_DWORD *)(v34 + 8452);
          _InterlockedOr(v425, 0);
          v102 = *(_DWORD *)(v34 + 8456);
        }
        while ( v103 != v102 );
        if ( (unsigned int)v572 >= (unsigned int)v498
          && ((_DWORD)v572 != (_DWORD)v498
           || HIDWORD(v572) >= HIDWORD(v498) && (HIDWORD(v572) != HIDWORD(v498) || (unsigned __int16)v573 >= v499)) )
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
        v106 = **(_QWORD **)v40;
        if ( !*(_WORD *)(v106 + 36) )
          goto LABEL_215;
        v107 = *(_BYTE *)(v106 + 1);
        if ( v107 != 11 )
        {
          if ( v107 != 8 )
          {
LABEL_213:
            if ( v107 != 9 )
              goto LABEL_215;
          }
          if ( *(_DWORD *)(v106 + 24) != 99 )
            goto LABEL_215;
          goto LABEL_201;
        }
        if ( *(_DWORD *)(v106 + 24) != 99 )
          goto LABEL_213;
LABEL_201:
        v531 = *(_DWORD *)(v106 + 32);
        v532 = *(_WORD *)(v106 + 36);
        if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v531, v105) )
        {
          PageHeader::GetIcxLsn(v106, &v535);
          v108 = v536;
          v109 = v535;
          goto LABEL_203;
        }
LABEL_215:
        v109 = *(_QWORD *)(v106 + 40);
        v535 = v109;
        v108 = *(_WORD *)(v106 + 48);
        v536 = v108;
LABEL_203:
        if ( !*(_QWORD *)v40 )
          goto LABEL_207;
        if ( (*(_WORD *)(*(_QWORD *)v40 + 98LL) & 0x400) != 0 && *((__int16 *)v40 + 6) >= 3 )
        {
          PageRef::UnfixLatchOnly(v40);
          goto LABEL_207;
        }
        v110 = *((__int16 *)v40 + 6);
        v111 = *(__int64 **)v40;
        if ( (*((_WORD *)v111 + 49) & 8) != 0 )
        {
          if ( v110 == 3 )
          {
            v110 = 4;
LABEL_219:
            if ( (*((_DWORD *)v111 + 25) & 8) != 0 )
            {
              v112 = v111[18];
              if ( v112 )
              {
                if ( *(_QWORD *)(v112 + 1880) )
                {
                  _mm_lfence();
                  DirtyPageMgr::OnReleasingBufLatch(*(_QWORD *)(v112 + 1880), v111, (unsigned int)v110);
                }
              }
            }
            goto LABEL_223;
          }
          if ( v110 >= 2 )
            goto LABEL_219;
        }
LABEL_223:
        if ( byte_10317ABE5 < 0
          && (*((_DWORD *)v111 + 25) & 8) != 0
          && v110 >= 3
          && (*((_DWORD *)v111 + 25) & 0xC0000000) != 0x40000000
          && *v111
          && VirtualProtect((LPVOID)*v111, 0x2000u, 2u, &v612) )
        {
          _InterlockedAnd((volatile signed __int32 *)v111 + 25, 0x3FFFFFFFu);
          _InterlockedOr((volatile signed __int32 *)v111 + 25, 0x40000000u);
        }
        LatchBase::ReleaseInternal(v111 + 19, (unsigned int)v110);
        if ( LatchBase::sm_acquireReleaseEnforcementExpensive && (byte_10317AD4F & 2) != 0 )
          BUF::TraceLatchAcquireRelease(v111, 0, (unsigned int)v110);
        v40 = v438;
        *((_WORD *)v438 + 6) = 0;
        *(_QWORD *)v40 = 0;
        v22 = v443;
LABEL_207:
        v603 = v109;
        v604 = v108;
        v426 = 0;
        RecoveryMgr::WaitForRedoLsnToCatchUp(*(_QWORD *)(v34 + 1832), &v603, 4);
      }
      v113 = *(_DWORD *)(v34 + 8456);
      do
      {
        v114 = v113 & 0xFFFFFFFE;
        v115 = *(LSN *)(v34 + 8444);
        v574 = v115;
        v575 = *(_DWORD *)(v34 + 8452);
        _InterlockedOr(v425, 0);
        v113 = *(_DWORD *)(v34 + 8456);
      }
      while ( v114 != v113 );
      v605 = v115;
      v116 = v575;
      v606 = v575;
      v117 = **(_QWORD **)v438;
      if ( !*(_WORD *)(v117 + 36) )
        goto LABEL_252;
      v118 = *(_BYTE *)(v117 + 1);
      if ( v118 != 11 )
      {
        if ( v118 != 8 )
          goto LABEL_250;
        goto LABEL_251;
      }
      if ( *(_DWORD *)(v117 + 24) == 99 )
        goto LABEL_241;
LABEL_250:
      if ( v118 == 9 )
      {
LABEL_251:
        if ( *(_DWORD *)(v117 + 24) != 99 )
          goto LABEL_252;
LABEL_241:
        v529 = *(_DWORD *)(v117 + 32);
        v530 = *(_WORD *)(v117 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v529, v104) )
          goto LABEL_252;
        PageHeader::GetIcxLsn(v117, &v486);
        v119 = v487;
      }
      else
      {
LABEL_252:
        v486 = *(LSN *)(v117 + 40);
        v119 = *(_WORD *)(v117 + 48);
        v487 = v119;
      }
      if ( v574.LowPart < v486.LowPart
        || v574.LowPart == v486.LowPart
        && (v574.HighPart < (unsigned int)v486.HighPart || v574.HighPart == v486.HighPart && v116 < v119) )
      {
        LSN::FormatAsHexString(&v486, v750, &v540);
        LSN::FormatAsHexString(&v605, v751, &v540);
        if ( (qword_10317F730 & 0x1000000000000LL) != 0 )
        {
          v661 = 393216;
          v662 = 0;
          v663 = &v666;
          v664 = &v684;
          v685 = 0;
          v665 = 0;
          v686 = 0;
          v666 = &v687;
          v667 = 52;
          v668 = 5;
          v669 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
          v670 = 16;
          v671 = 5;
          v672 = &Zero<XE_StaticPackage<1304>::LocaleEntry>::sm_val;
          v673 = 16;
          v674 = 6;
          v675 = 0;
          v676 = 0;
          v677 = 7;
          v678 = 0;
          v679 = 0;
          v680 = 8;
          v681 = 0;
          v682 = 0;
          v683 = 9;
          v687 = *(unsigned __int16 *)(v34 + 1720);
          v688 = v441;
          v689 = v440;
          v690 = -1;
          v40 = v438;
          v691 = *(_BYTE *)(**(_QWORD **)v438 + 1LL);
          v669 = (GUID *)(v121 + 596);
          v672 = (GUID *)(v121 + 580);
          v122 = -1;
          do
            ++v122;
          while ( v750[v122] );
          v675 = v750;
          v676 = 2 * v122;
          v123 = -1;
          do
            ++v123;
          while ( v751[v123] );
          v678 = v751;
          v679 = 2 * v123;
          v541 = 0;
          v124 = ((__int64 (__fastcall *)(__int64, int *))g_dbtableFactory[2])(v121, &v541);
          v125 = (int *)v124;
          if ( v124 )
          {
            v126 = -1;
            do
              ++v126;
            while ( *(_WORD *)(v124 + 2 * v126) );
            v127 = 2 * v126;
          }
          else
          {
            v127 = 0;
          }
          v128 = v663;
          v663[10] = v125;
          *((_DWORD *)v128 + 22) = v127;
          *((_DWORD *)v128 + 23) = 9;
          XeSqlPkg::rbio_read_future_page::Publish((XeSqlPkg::rbio_read_future_page *)v660);
        }
        else
        {
          v40 = v438;
        }
      }
      else
      {
        v40 = v438;
      }
LABEL_26:
      v45 = v481;
      if ( *(_QWORD *)v481 )
      {
        if ( (*((_DWORD *)v40 + 3) & 0xFF000000) != 0 )
        {
          ++*(_DWORD *)(*(_QWORD *)v481 + 4LL);
          if ( *((_BYTE *)v40 + 16) )
            ++*(_DWORD *)(*(_QWORD *)v45 + 8LL);
        }
        ++**(_DWORD **)v45;
      }
      if ( (_DWORD)v602 )
        HoBtAccess::UpdateLatchWaitStats(
          *((_QWORD *)v45 + 11),
          *(unsigned __int8 *)(**(_QWORD **)v40 + 1LL),
          &v601,
          *((unsigned int *)v45 + 94));
      v46 = **(_QWORD **)v40;
      v47 = v435;
      v48 = v496;
      if ( a6 != 1 || *((_QWORD *)v435[1] + 48) )
        goto LABEL_32;
      v9 = *((_QWORD *)v496 + 1);
      if ( !v9 || (v120 = *(_QWORD *)(v9 + 8), *(_BYTE *)(v120 + 63)) )
      {
        v10 = *(_QWORD *)(*((_QWORD *)v496 + 2) + 8LL);
        if ( *((_DWORD *)v496 + 16) == 2 )
        {
          if ( *(_QWORD *)(v10 + 1144) )
            v10 = *(_QWORD *)(v10 + 1144);
          v11 = *(_WORD *)(v10 + 1096);
          if ( *(_DWORD *)(v10 + 1092) && v11 )
          {
            LODWORD(v469) = *(_DWORD *)(v10 + 1092);
            HIDWORD(v469) = v11;
            v12 = &v469;
          }
          else
          {
            v469 = 0;
            v12 = &v469;
          }
        }
        else
        {
          v129 = *(_WORD *)(v10 + 1056);
          v130 = *(_WORD *)(v10 + 1058);
          if ( *(_DWORD *)(v10 + 1052) && v129 )
          {
            LODWORD(v451) = *(_DWORD *)(v10 + 1052);
            WORD2(v451) = v129;
            HIWORD(v451) = v130;
          }
          else
          {
            v451 = 0;
          }
          v12 = &v451;
        }
        v13 = *(_DWORD *)v12;
        v472 = *(_DWORD *)v12;
        v14 = *((_WORD *)v12 + 2);
      }
      else
      {
        v13 = *(_DWORD *)(v120 + 56);
        v472 = v13;
        v14 = *(_WORD *)(v120 + 60);
      }
      v473 = v14;
      if ( !v13 && !v14 )
        goto LABEL_107;
      v15 = *((_QWORD *)v496 + 1);
      if ( !v15 || (v131 = *(_QWORD *)(v15 + 8), *(_BYTE *)(v131 + 63)) )
      {
        if ( *((_DWORD *)v496 + 16) == 2 )
        {
          v16 = (int *)*((_QWORD *)v496 + 6);
          v545 = *v16;
          v546 = *((_WORD *)v16 + 2);
          v547 = 0;
          v17 = &v545;
        }
        else
        {
          v132 = (int *)*((_QWORD *)v496 + 5);
          v548 = *v132;
          v549 = *((_WORD *)v132 + 2);
          v550 = 0;
          v17 = &v548;
        }
        v466 = *v17;
        v18 = *((_WORD *)v17 + 2);
      }
      else
      {
        v466 = *(_DWORD *)(v131 + 8);
        v18 = *(_WORD *)(v131 + 12);
      }
      v468 = 0;
      v467 = v18;
      v19 = v435[4];
      if ( !v13 && !v14 )
        goto LABEL_107;
      v749 = 0;
      v745 = v440;
      v746 = v441;
      v747 = 0;
      v744 = 0;
      v748 = 0;
      v20 = IsPageInAllocUnitInternal(v19, &v466, &v472, &v744, 7, v40);
      v47 = v435;
      if ( v20 )
      {
LABEL_32:
        v49 = v453;
      }
      else
      {
LABEL_107:
        v49 = 1;
        v453 = 1;
      }
      v50 = v445;
      v51 = *((__int16 *)v445 + 3);
      if ( (unsigned int)v51 >= *(unsigned __int16 *)(v46 + 22) || (v52 = 1, !*(_WORD *)(v46 + 2 * (v483 - v51))) )
        v52 = 0;
      v53 = *((_QWORD *)v48 + 1);
      if ( !v53 || (v133 = *(_QWORD *)(v53 + 8), *(_BYTE *)(v133 + 63)) )
      {
        if ( *((_DWORD *)v48 + 16) == 2 )
        {
          v54 = (int *)*((_QWORD *)v48 + 6);
          v551 = *v54;
          v552 = *((_WORD *)v54 + 2);
          v553 = 0;
          v55 = &v551;
        }
        else
        {
          v134 = (int *)*((_QWORD *)v48 + 5);
          v554 = *v134;
          v555 = *((_WORD *)v134 + 2);
          v556 = 0;
          v55 = &v554;
        }
        v56 = *v55;
        v557 = *v55;
        v57 = *((_WORD *)v55 + 2);
      }
      else
      {
        v56 = *(_DWORD *)(v133 + 8);
        v557 = v56;
        v57 = *(_WORD *)(v133 + 12);
      }
      v558 = v57;
      v58 = 0;
      if ( *(_DWORD *)(v46 + 24) == v56 )
      {
        v59 = *(_WORD *)(v46 + 6);
        if ( v59 == v57 || (unsigned __int16)(v57 | v59) <= 1u )
          v58 = 1;
      }
      if ( v49 || !v52 || !(_DWORD)v58 )
        BlobBase::TableCorruptException(*(_WORD *)(*((_QWORD *)*v47 + 6) + 1720LL), v445, v51, 9);
      v60 = *((__int16 *)v50 + 3);
      v702 = *((__int16 *)v50 + 3);
      if ( *(char *)(v46 + 2) >= 0 )
      {
        v61 = 0;
        goto LABEL_47;
      }
      v135 = (unsigned __int8 *)(v46 + 96);
      _mm_prefetch((const char *)(v46 + 96), 0);
      if ( v695 && (v61 = v699) != 0 )
      {
        v136 = -1;
      }
      else
      {
        v706 = 0;
        v708 = 0u;
        v709 = 0;
        v711 = 0;
        v703 = 0;
        v136 = -1;
        v704 = 0xFFFFu;
        v707 = 0;
        memset(v705, 0, sizeof(v705));
        v710 = 0u;
        v61 = &v703;
      }
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_302;
      v137 = *(_BYTE *)(v46 + 1);
      if ( v137 != 11 )
      {
        if ( v137 != 8 )
          goto LABEL_300;
        goto LABEL_301;
      }
      if ( *(_DWORD *)(v46 + 24) == 99 )
        goto LABEL_293;
LABEL_300:
      if ( v137 == 9 )
      {
LABEL_301:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_302;
LABEL_293:
        v525 = *(_DWORD *)(v46 + 32);
        v526 = *(_WORD *)(v46 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v525, v58) )
          goto LABEL_302;
        PageHeader::GetIcxLsn(v46, &v500);
      }
      else
      {
LABEL_302:
        v500 = *(_QWORD *)(v46 + 40);
        v501 = *(_WORD *)(v46 + 48);
      }
      *(_QWORD *)v61 = v135;
      v138 = v501;
      v139 = HIDWORD(v500);
      *((_DWORD *)v61 + 24) = v500;
      *((_DWORD *)v61 + 25) = v139;
      *((_WORD *)v61 + 52) = v138;
      *((_DWORD *)v61 + 27) = *(_DWORD *)(v46 + 32);
      *((_WORD *)v61 + 56) = *(_WORD *)(v46 + 36);
      *((_WORD *)v61 + 57) = 0;
      v140 = 3LL * *v135;
      v600 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v135);
      v141 = word_102883984[v140];
      *((_WORD *)v61 + 8) = v136;
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
        v142 = &v135[v141];
        if ( (v135[v141] & 1) != 0 )
        {
          *((_WORD *)v61 + 8) = 1;
          *((_QWORD *)v61 + 3) = v142;
          v143 = *v142;
          switch ( *((_BYTE *)&loc_1005A8CD0 + (*v142 & 0x1C)) )
          {
            case 0:
              if ( (v142[1] & 0x80u) != 0 )
              {
                v150 = *(_WORD *)(v142 + 1);
                *((_WORD *)v61 + 9) = v150;
                v144 = 3;
                v145 = HIBYTE(v150) | ((v150 & 0x7F) << 8);
              }
              else
              {
                v144 = 2;
                v145 = v142[1];
              }
              *((_WORD *)v61 + 9) = v145;
              *((_WORD *)v61 + 20) = v144;
              *((_WORD *)v61 + 22) = v144 + (((unsigned int)*((unsigned __int16 *)v61 + 9) + 1) >> 1);
              v146 = *((unsigned __int16 *)v61 + 9);
              if ( v146 > 0x1E )
                *((_WORD *)v61 + 21) = (int)(v146 - 1) / 30;
              else
                *((_WORD *)v61 + 21) = 0;
              *((_DWORD *)v61 + 5) = 0;
              *((_DWORD *)v61 + 16) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 4) = 0;
              break;
            case 1:
              if ( (v143 & 0x1C) != 4 || (v151 = 1, (v143 & 2) == 0) )
                v151 = 0;
              *((_DWORD *)v61 + 5) = 0;
              *((_QWORD *)v61 + 5) = 0;
              *((_WORD *)v61 + 9) = 0;
              *((_QWORD *)v61 + 6) = 0;
              *((_QWORD *)v61 + 4) = 0;
              *((_DWORD *)v61 + 16) = 0;
              *((_QWORD *)v61 + 7) = 0;
              *((_QWORD *)v61 + 3) = v142;
              if ( v151 )
              {
                *((_DWORD *)v61 + 5) = v433;
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
              *((_QWORD *)v61 + 3) = v142;
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
          v152 = 0;
          *((_QWORD *)v61 + 3) = v142;
          *((_DWORD *)v61 + 5) = 0;
          *(_DWORD *)((char *)v61 + 54) = 0;
          switch ( *v142 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v152 = *((unsigned __int16 *)v142 + 1);
              if ( (unsigned int)(v152 - 1) > 0x1F9D )
                RaiseInconsistencyError(&v135[v141], 6);
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
              v152 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v152 = 1;
              break;
          }
          *((_DWORD *)v61 + 8) = v152;
          *(_QWORD *)((char *)v61 + 46) = 0;
        }
      }
      if ( (**(_BYTE **)v61 & 4) != 0 )
      {
        if ( HIWORD(v600) )
          v147 = &v135[*(unsigned __int16 *)&v135[2 * SHIWORD(v600) + 1]];
        else
          v147 = &v135[v141];
        *((_QWORD *)v61 + 9) = v147;
        v148 = *(_WORD *)v147;
        *((_QWORD *)v61 + 10) = v147 + 2;
        *((_WORD *)v61 + 44) = 2 * (v148 + 1);
      }
      v149 = (PageComprInfoCache *)*((_QWORD *)v61 + 1);
      if ( v149 )
        PageComprInfoCache::Init(v149, (const struct PageComprInfo *)v61);
LABEL_47:
      v62 = *(unsigned __int16 *)(v46 + 14);
      v63 = (unsigned __int8 *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v483 - v60)));
      v92 = (*v63 & 1) == 0;
      v698 = (struct XDES *)v63;
      if ( v92 )
      {
        v695 = 0;
        v64 = 0;
        v697 = 0;
        *(_DWORD *)&v700[14] = 0;
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
            v64 = v697;
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
        LODWORD(v699) = v62;
        *(_QWORD *)&v700[6] = v46 + 0x2000;
        LODWORD(v61) = v62;
      }
      else
      {
        v695 = 1;
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
              v153 = HIBYTE(*(_WORD *)(v63 + 1)) | ((*(_WORD *)(v63 + 1) & 0x7F) << 8);
              v696 = v153;
              v65 = 3;
              *(_WORD *)v700 = 3;
            }
            else
            {
              v153 = v63[1];
              v696 = v153;
              v65 = 2;
              *(_WORD *)v700 = 2;
            }
            *(_WORD *)&v700[4] = v65 + (((unsigned int)v153 + 1) >> 1);
            if ( v153 > 0x1Eu )
            {
              v65 = (unsigned int)((v153 - 1) / 30);
              *(_WORD *)&v700[2] = (v153 - 1) / 30;
            }
            else
            {
              *(_WORD *)&v700[2] = 0;
            }
            v64 = 0;
            v697 = 0;
            v701 = 0;
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
            v64 = v697;
            break;
          case 4:
            if ( (v65 & 0x1C) == 4 && (v65 & 2) != 0 )
            {
              *(_QWORD *)v700 = 0;
              v696 = 0;
              *(_QWORD *)&v700[8] = 0;
              v64 = v433;
              v697 = v433;
              v701 = 1;
            }
            else
            {
              *(_QWORD *)v700 = 0;
              v696 = 0;
              *(_QWORD *)&v700[8] = 0;
              v64 = 1;
              v697 = 1;
              v701 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v700 = 0;
            v696 = 0;
            *(_QWORD *)&v700[8] = 0;
            v64 = 9;
            v697 = 9;
            v701 = 0;
            break;
        }
        *(_QWORD *)&v700[16] = v46 + 0x2000;
        v699 = v61;
        v62 = (unsigned int)v61;
      }
      v66 = v698;
      v481 = v698;
      if ( v695 )
      {
        if ( !v64 )
        {
          CDRecord::Resize((CDRecord *)&v696);
          v64 = v697;
        }
        if ( v64 >= 9 )
          goto LABEL_65;
        if ( (*(_BYTE *)v698 & 0x1C) != 0 )
        {
          v175 = (*(_BYTE *)v698 & 0x1C) == 12;
LABEL_432:
          if ( !v175 )
            goto LABEL_65;
        }
LABEL_433:
        v64 = 9;
        goto LABEL_65;
      }
      if ( !v64 )
      {
        v696 = 0;
        HIDWORD(v699) = v62;
        v67 = *(_BYTE *)v698;
        HIDWORD(v699) = (_DWORD)v61;
        if ( (v67 & 0x10) != 0 )
        {
          if ( (*(_BYTE *)v698 & 0x10) != 0 )
            v154 = *(unsigned __int16 *)((char *)v698 + v62);
          else
            v154 = 0;
          LODWORD(v61) = ((unsigned int)(v154 + 7) >> 3) + (_DWORD)v61 + 2;
          HIDWORD(v699) = (_DWORD)v61;
        }
        if ( (*(_BYTE *)v698 & 0x20) != 0 )
        {
          v155 = (unsigned __int16 *)((char *)v698 + (unsigned int)v61);
          v156 = *v155;
          *(_WORD *)&v700[4] = v156;
          if ( !v156 )
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
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                    else
                      ex_raise(34, 68, 21, 1003);
                  }
                }
              }
            }
            RaiseInconsistencyError(v698, 3);
            v156 = *(_WORD *)&v700[4];
            LODWORD(v61) = HIDWORD(v699);
          }
          v159 = (_DWORD)v61 + 2 * (v156 + 1);
          *(_DWORD *)v700 = v159;
          if ( v159 > 0x1F9E )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v160 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v160 )
              {
                v161 = *(_QWORD *)(v160 + 96);
                if ( v161 )
                {
                  if ( *(_BYTE *)(v161 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(v698, 4);
            v156 = *(_WORD *)&v700[4];
            v159 = *(_DWORD *)v700;
            LODWORD(v61) = HIDWORD(v699);
          }
          v64 = v155[v156] & 0x7FFF;
          v697 = v64;
          if ( v159 > v64 )
          {
            if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
            {
              v162 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                               + SystemThread_TlsOffset
                               + 8LL);
              if ( v162 )
              {
                v163 = *(_QWORD *)(v162 + 96);
                if ( v163 )
                {
                  if ( *(_BYTE *)(v163 + 1177) )
                  {
                    if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                      utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                    else
                      ex_raise(34, 68, 21, 1004);
                  }
                }
              }
            }
            RaiseInconsistencyError(v698, 4);
            v156 = *(_WORD *)&v700[4];
            v159 = *(_DWORD *)v700;
            LODWORD(v61) = HIDWORD(v699);
            v64 = v697;
          }
          while ( 1 )
          {
            v65 = v156;
            if ( (v155[v156] & 0x8000u) == 0 )
              break;
            v164 = (char *)v698 + (unsigned int)v61;
            if ( v156 == 1 )
              v165 = v159;
            else
              v165 = *(_WORD *)&v164[2 * v156 - 2] & 0x7FFF;
            v65 = *(_WORD *)&v164[2 * v156] & 0x7FFF;
            if ( v165 < v159 || (unsigned int)v65 < v165 )
            {
              RaiseInconsistencyError(v698, 7);
              v156 = *(_WORD *)&v700[4];
              v159 = *(_DWORD *)v700;
              LODWORD(v61) = HIDWORD(v699);
              v64 = v697;
            }
            if ( v165 < v159 || v165 > v64 )
              goto LABEL_64;
            v65 = *(unsigned __int16 *)((char *)v698 + v165);
            if ( (_WORD)v65 == 5 )
            {
              v696 |= 2u;
              *(_WORD *)&v700[4] = v156 - 1;
              *(_WORD *)&v700[18] = v165;
              v166 = (char *)v698 + (unsigned __int16)v165;
              v167 = *((_WORD *)v166 + 1);
              if ( (v167 & 0x4000) != 0 )
                v168 = (*(_WORD *)&v700[20] ^ v167) & 0x3800 ^ *(_WORD *)&v700[20];
              else
                v168 = *(_WORD *)&v700[20] & 0xC7FF;
              *(_WORD *)&v700[20] = v168;
              v169 = *((_WORD *)v166 + 1) ^ v168;
              v65 = 2047;
              *(_WORD *)&v700[20] = v169 & 0x7FF ^ v168;
              break;
            }
            if ( (unsigned __int16)v65 >= 0x400u )
            {
              v696 |= 1u;
              v92 = v156-- == 1;
              *(_WORD *)&v700[4] = v156;
              if ( !v92 )
                continue;
            }
            break;
          }
        }
        else
        {
          v64 = (unsigned int)v61;
          v697 = (unsigned int)v61;
          *(_WORD *)&v700[4] = 0;
          *(_DWORD *)v700 = (_DWORD)v61;
        }
        if ( (*(_BYTE *)v698 & 0x40) != 0 )
        {
          *(_DWORD *)&v700[14] = v64;
          v697 = v64 + 14;
          VersioningInfo = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v696);
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
          v64 = v69 + v697;
          v697 += v69;
        }
        else
        {
          *(_DWORD *)&v700[14] = 0;
        }
        if ( *(_QWORD *)&v700[6] && *(_QWORD *)&v700[6] < (unsigned __int64)v698 + v64 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v170 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v170 )
            {
              v171 = *(_QWORD *)(v170 + 96);
              if ( v171 )
              {
                if ( *(_BYTE *)(v171 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                  else
                    ex_raise(34, 68, 21, 1018);
                }
              }
            }
          }
          RaiseInconsistencyError(v698, 18);
          v64 = v697;
        }
        if ( v64 - 1 > 0x3F3B )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v172 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v172 )
            {
              v173 = *(_QWORD *)(v172 + 96);
              if ( v173 )
              {
                if ( *(_BYTE *)(v173 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                  else
                    ex_raise(34, 68, 21, 1005);
                }
              }
            }
          }
          RaiseInconsistencyError(v698, 5);
          v64 = v697;
        }
      }
LABEL_64:
      if ( v64 < 9 )
      {
        v174 = *(_BYTE *)v698 & 0xE;
        if ( v174 )
        {
          v175 = v174 == 12;
          goto LABEL_432;
        }
        goto LABEL_433;
      }
LABEL_65:
      *v482 = v64;
      v70 = v434;
      v71 = v435;
      if ( v434 )
        goto LABEL_66;
      if ( !*((_BYTE *)v435[4] + 7390) )
        goto LABEL_81;
      v176 = v592 & 0xFFFFFEFC | 2;
      v592 = v176;
      v65 = (__int64)v435[1];
      v177 = *(_QWORD *)(v65 + 88);
      v178 = (*(unsigned int *)(v177 + 20) | ((unsigned __int64)*(unsigned __int16 *)(v177 + 24) << 32)) << 16;
      *((_QWORD *)&v594 + 1) = *(_QWORD *)(v65 + 48);
      v595 = v178;
      *(_QWORD *)&v594 = v177;
      v592 = v176 & 0xFFFFFDE3;
      if ( !(_QWORD)v591 || (v179 = (_DWORD)v434 + 32, (*(_BYTE *)(v591 + 48) & 1) == 0) )
        v179 = 0;
      v180 = v176 & 0xFFFFFD43 | v179 & 0xFFFFFF7F;
      if ( *((_QWORD *)&v591 + 1) )
      {
        v180 |= 1u;
LABEL_449:
        v181 = 0;
        goto LABEL_447;
      }
      if ( (v180 & 0x20) == 0 )
        goto LABEL_449;
      v180 |= 1u;
      if ( (v180 & 0x20) == 0 )
        goto LABEL_449;
      v181 = 64;
LABEL_447:
      v592 = v181 | v180 & 0xFFFFFEBD;
      v593 &= 0xFCu;
      v70 = (struct VersionScanParams *)&v591;
      v434 = (struct VersionScanParams *)&v591;
LABEL_66:
      LockMode = LobContext::GetLockMode(v435[1], v65);
      v75 = v580[1];
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
          v182 = *((_DWORD *)v70 + 4);
          if ( (v182 & 1) == 0 )
            goto LABEL_72;
          if ( (v182 & 0x40) != 0 )
            goto LABEL_72;
          v183 = *((_QWORD *)*v71 + 6);
          if ( !*(_BYTE *)(v183 + 7378) || *(_BYTE *)(v183 + 8272) )
            goto LABEL_72;
          v21 = v450;
          v75 = v450[1];
        }
        else
        {
          v21 = v450;
        }
        v77 = v438;
        XdesLockIfNecessary = GetXdesLockIfNecessary(
                                *((_QWORD *)*v71 + 6),
                                *v71,
                                &v695,
                                *(unsigned int *)(*((_QWORD *)v75 + 8) + 24LL),
                                v438);
        v22 = v443;
        v27 = v462;
        if ( XdesLockIfNecessary == 1 )
          goto LABEL_466;
        v71 = v435;
      }
      else
      {
LABEL_72:
        v77 = v438;
      }
      v734 = -1;
      v737 = 0;
      v736 = 0;
      *(_QWORD *)&v739[6] = 0;
      *(_QWORD *)&v739[16] = 0;
      v738 = 0;
      v741 = -1;
      v78 = *(_BYTE *)(v46 + 2);
      v729 = 1;
      if ( (v78 & 0x20) == 0 || *((_WORD *)v77 + 6) != 4 )
        goto LABEL_74;
      v185 = *(_WORD *)(*((_QWORD *)*v71 + 6) + 1720LL);
      v729 = 6;
      v728 = v185;
      v727 = 0;
      v726 = *(_DWORD *)(v46 + 32);
      LOWORD(v727) = *(_WORD *)(v46 + 36);
      LOBYTE(v428) = 0;
      LOBYTE(v427) = 1;
      LOBYTE(v74) = 8;
      if ( (int)BlobBase::GetLock(v71, &v726, v74, 1, 0, v427, (_DWORD)v428) < 0 )
      {
        _mm_lfence();
        PageRef::Unlatch(v77);
        LOBYTE(v428) = 0;
        LOBYTE(v427) = 1;
        LOBYTE(v186) = 8;
        Lock = BlobBase::GetLock(v71, &v726, v186, 0, 0, v427, (_DWORD)v428);
        LOBYTE(v188) = 13;
        goto LABEL_465;
      }
      v189 = 0;
      v190 = *(unsigned __int16 *)(v46 + 22);
      if ( !*(_WORD *)(v46 + 22) )
        goto LABEL_471;
      v191 = 0;
      v192 = (_WORD *)(v46 + 8190);
      while ( !*v192 )
      {
        ++v189;
        ++v191;
        --v192;
        if ( v191 >= v190 )
          goto LABEL_471;
      }
      if ( v189 == -1 )
      {
LABEL_471:
        PageRef::SetBulkInsertBitOnPage(v77, 0);
LABEL_74:
        v79 = v435;
        break;
      }
      _mm_lfence();
      v741 = v189;
      if ( *(char *)(v46 + 2) >= 0 )
      {
        v203 = 0;
        goto LABEL_492;
      }
      v207 = (unsigned __int8 *)(v46 + 96);
      _mm_prefetch((const char *)(v46 + 96), 0);
      if ( v734 && (v203 = v738) != 0 )
      {
        v208 = -1;
      }
      else
      {
        v743 = 0;
        v742[0] = 0;
        v208 = -1;
        v742[1] = 0xFFFFu;
        memset(&v742[2], 0, 80);
        v203 = v742;
      }
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_509;
      v209 = *(_BYTE *)(v46 + 1);
      if ( v209 != 11 )
      {
        if ( v209 != 8 )
          goto LABEL_507;
        goto LABEL_508;
      }
      if ( *(_DWORD *)(v46 + 24) == 99 )
        goto LABEL_500;
LABEL_507:
      if ( v209 == 9 )
      {
LABEL_508:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_509;
LABEL_500:
        v527 = *(_DWORD *)(v46 + 32);
        v528 = *(_WORD *)(v46 + 36);
        if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v527, v190) )
          goto LABEL_509;
        PageHeader::GetIcxLsn(v46, &v502);
      }
      else
      {
LABEL_509:
        v502 = *(_QWORD *)(v46 + 40);
        v503 = *(_WORD *)(v46 + 48);
      }
      *(_QWORD *)v203 = v207;
      v210 = v503;
      v211 = HIDWORD(v502);
      *((_DWORD *)v203 + 24) = v502;
      *((_DWORD *)v203 + 25) = v211;
      *((_WORD *)v203 + 52) = v210;
      *((_DWORD *)v203 + 27) = *(_DWORD *)(v46 + 32);
      *((_WORD *)v203 + 56) = *(_WORD *)(v46 + 36);
      *((_WORD *)v203 + 57) = 0;
      v212 = 3LL * *v207;
      v599 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v207);
      v213 = word_102883984[v212];
      *((_WORD *)v203 + 8) = v208;
      *((_QWORD *)v203 + 3) = 0;
      *((_DWORD *)v203 + 5) = 0;
      *(_QWORD *)((char *)v203 + 46) = 0;
      *((_QWORD *)v203 + 7) = 0;
      *((_QWORD *)v203 + 4) = 0;
      *((_QWORD *)v203 + 9) = 0;
      *((_QWORD *)v203 + 10) = 0;
      *((_WORD *)v203 + 44) = 0;
      if ( (**(_BYTE **)v203 & 2) != 0 )
      {
        v214 = &v207[v213];
        if ( (v207[v213] & 1) != 0 )
        {
          *((_WORD *)v203 + 8) = 1;
          *((_QWORD *)v203 + 3) = v214;
          v215 = *v214;
          switch ( *v214 & 0x1C )
          {
            case 0:
            case 0xC:
            case 0x10:
            case 0x14:
            case 0x18:
            case 0x1C:
              if ( (v214[1] & 0x80u) != 0 )
              {
                v222 = *(_WORD *)(v214 + 1);
                *((_WORD *)v203 + 9) = v222;
                v216 = 3;
                v217 = HIBYTE(v222) | ((v222 & 0x7F) << 8);
              }
              else
              {
                v216 = 2;
                v217 = v214[1];
              }
              *((_WORD *)v203 + 9) = v217;
              *((_WORD *)v203 + 20) = v216;
              *((_WORD *)v203 + 22) = v216 + (((unsigned int)*((unsigned __int16 *)v203 + 9) + 1) >> 1);
              v218 = *((unsigned __int16 *)v203 + 9);
              if ( v218 > 0x1E )
                *((_WORD *)v203 + 21) = (int)(v218 - 1) / 30;
              else
                *((_WORD *)v203 + 21) = 0;
              *((_DWORD *)v203 + 5) = 0;
              *((_DWORD *)v203 + 16) = 0;
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 4) = 0;
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
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 4) = 0;
              break;
            case 4:
              if ( (v215 & 0x1C) != 4 || (v223 = 1, (v215 & 2) == 0) )
                v223 = 0;
              *((_DWORD *)v203 + 5) = 0;
              *((_QWORD *)v203 + 5) = 0;
              *((_WORD *)v203 + 9) = 0;
              *((_QWORD *)v203 + 6) = 0;
              *((_QWORD *)v203 + 4) = 0;
              *((_DWORD *)v203 + 16) = 0;
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 3) = v214;
              if ( v223 )
              {
                *((_DWORD *)v203 + 5) = v433;
                *((_DWORD *)v203 + 16) = 0;
                *((_DWORD *)v203 + 16) = 1;
              }
              else
              {
                *((_DWORD *)v203 + 5) = 1;
                *((_DWORD *)v203 + 16) = 0;
              }
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 4) = 0;
              break;
            case 8:
              *((_QWORD *)v203 + 5) = 0;
              *((_WORD *)v203 + 9) = 0;
              *((_QWORD *)v203 + 6) = 0;
              *((_QWORD *)v203 + 4) = 0;
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 3) = v214;
              *((_DWORD *)v203 + 5) = 9;
              *((_DWORD *)v203 + 16) = 0;
              *((_QWORD *)v203 + 7) = 0;
              *((_QWORD *)v203 + 4) = 0;
              break;
          }
        }
        else
        {
          *((_WORD *)v203 + 8) = 0;
          v224 = 0;
          *((_QWORD *)v203 + 3) = v214;
          *((_DWORD *)v203 + 5) = 0;
          *(_DWORD *)((char *)v203 + 54) = 0;
          switch ( *v214 & 0xE )
          {
            case 0:
            case 2:
            case 8:
            case 0xC:
              v224 = *((unsigned __int16 *)v214 + 1);
              if ( (unsigned int)(v224 - 1) > 0x1F9D )
                RaiseInconsistencyError(&v207[v213], 6);
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
              v224 = 9;
              break;
            case 6:
            case 0xA:
              break;
            case 0xE:
              v224 = 1;
              break;
          }
          *((_DWORD *)v203 + 8) = v224;
          *(_QWORD *)((char *)v203 + 46) = 0;
        }
      }
      if ( (**(_BYTE **)v203 & 4) != 0 )
      {
        if ( HIWORD(v599) )
          v219 = &v207[*(unsigned __int16 *)&v207[2 * SHIWORD(v599) + 1]];
        else
          v219 = &v207[v213];
        *((_QWORD *)v203 + 9) = v219;
        v220 = *(_WORD *)v219;
        *((_QWORD *)v203 + 10) = v219 + 2;
        *((_WORD *)v203 + 44) = 2 * (v220 + 1);
      }
      v221 = (PageComprInfoCache *)*((_QWORD *)v203 + 1);
      if ( v221 )
        PageComprInfoCache::Init(v221, (const struct PageComprInfo *)v203);
      v77 = v438;
      v66 = v481;
LABEL_492:
      v204 = *(unsigned __int16 *)(v46 + 14);
      v205 = (char *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v483 - v189)));
      v92 = (*v205 & 1) == 0;
      v737 = v205;
      if ( v92 )
      {
        v734 = 0;
        v736 = 0;
        *(_DWORD *)&v739[14] = 0;
        switch ( *v205 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v204 = *((unsigned __int16 *)v205 + 1);
            if ( (unsigned int)(v204 - 1) > 0x1F9D )
              RaiseInconsistencyError(v205, 6);
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
            v204 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v204 = 1;
            break;
        }
        LODWORD(v738) = v204;
        *(_QWORD *)&v739[6] = v46 + 0x2000;
      }
      else
      {
        v734 = 1;
        v206 = *v205;
        switch ( *v205 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( v205[1] < 0 )
            {
              v225 = HIBYTE(*(_WORD *)(v205 + 1)) | ((*(_WORD *)(v205 + 1) & 0x7F) << 8);
              v735 = v225;
              v226 = 3;
              *(_WORD *)v739 = 3;
            }
            else
            {
              v225 = (unsigned __int8)v205[1];
              v735 = v225;
              v226 = 2;
              *(_WORD *)v739 = 2;
            }
            *(_WORD *)&v739[4] = v226 + (((unsigned int)v225 + 1) >> 1);
            if ( v225 > 0x1Eu )
              *(_WORD *)&v739[2] = (v225 - 1) / 30;
            else
              *(_WORD *)&v739[2] = 0;
            v736 = 0;
            v740 = 0;
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
            if ( (v206 & 0x1C) == 4 && (v206 & 2) != 0 )
            {
              *(_QWORD *)v739 = 0;
              v735 = 0;
              *(_QWORD *)&v739[8] = 0;
              v736 = v433;
              v740 = 1;
            }
            else
            {
              *(_QWORD *)v739 = 0;
              v735 = 0;
              *(_QWORD *)&v739[8] = 0;
              v736 = 1;
              v740 = 0;
            }
            break;
          case 8:
            *(_QWORD *)v739 = 0;
            v735 = 0;
            *(_QWORD *)&v739[8] = 0;
            v736 = 9;
            v740 = 0;
            break;
        }
        *(_QWORD *)&v739[16] = v46 + 0x2000;
        v738 = v203;
      }
      if ( v734 )
        CDRecord::GetXdesTs(&v735, &v455);
      else
        FixedVarRecord::GetXdesTs(&v735, &v455);
      v227 = v455;
      v228 = v456;
      v79 = v435;
      if ( v456 != *((_WORD *)*v435 + 22) || v455 != *((_DWORD *)*v435 + 10) )
      {
        _mm_lfence();
        if ( (*(_DWORD *)(*((_QWORD *)v435[1] + 8) + 4LL) & 0x140) == 0 )
        {
          _mm_lfence();
          v507 = v455;
          v508 = v456;
          if ( (unsigned int)XDES::GetTIDLockOption(*v435, &v507) == 3 )
          {
            _mm_lfence();
            PageRef::Unlatch(v77);
            v509 = v227;
            v510 = v228;
            v229 = *v79;
            v230 = *((_QWORD *)*v79 + 6);
            LODWORD(v427) = *(_DWORD *)(*((_QWORD *)v79[1] + 8) + 24LL);
            LOBYTE(v426) = 3;
            LOBYTE(v231) = 1;
            Lock = AcquireTransactionLock(*(unsigned __int16 *)(v230 + 1720), &v509, v229, v231, v426, v427);
            LOBYTE(v188) = 72;
LABEL_465:
            lck_StandardHandler(Lock, v188);
            v22 = v443;
            v21 = v450;
            v27 = v462;
LABEL_466:
            v24 = v435;
            continue;
          }
        }
        PageRef::SetBulkInsertBitOnPage(v77, 0);
      }
      break;
    }
    a2 = (__int64)v79[1];
    v80 = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 8LL);
    if ( *(_BYTE *)(v80 + 1873) )
    {
      v193 = a9 ? *(_QWORD *)(a2 + 72) : *(_QWORD *)(a2 + 64);
      if ( (*(_DWORD *)(v193 + 4) & 0x140) == 0 )
      {
        v194 = *(_WORD *)(*((_QWORD *)*v79 + 6) + 1720LL);
        if ( v695 )
          CDRecord::GetXdesTs(&v696, &v457);
        else
          FixedVarRecord::GetXdesTs(&v696, &v457);
        v196 = v457;
        v197 = v458;
        if ( v458 != v442 || v457 != v454 )
        {
          v474 = v457;
          v475 = v458;
          v198 = *v79;
          if ( (word_10318AB38 != v458 || NullXdesId != v457)
            && (v458 != *((_WORD *)v198 + 22) || v457 != *((_DWORD *)v198 + 10)) )
          {
            v199 = *((_QWORD *)v198 + 6);
            if ( *(_BYTE *)(v199 + 8272) )
            {
              if ( XdesMgr::IsXdesActive((XdesMgr *)(v199 + 6600), (const struct XdesId *)&v474) )
              {
LABEL_580:
                PageRef::Unlatch(v438);
                v513 = v196;
                v514 = v197;
                LODWORD(v427) = *(_DWORD *)(*((_QWORD *)v79[1] + 8) + 24LL);
                LOBYTE(v426) = 3;
                LOBYTE(v233) = 1;
                v234 = AcquireTransactionLock(v194, &v513, *v79, v233, v426, v427);
                LOBYTE(v235) = 72;
                lck_StandardHandler(v234, v235);
                v454 = v196;
                v442 = v197;
                v22 = v443;
                v21 = v450;
                v27 = v462;
                goto LABEL_466;
              }
            }
            else
            {
              a2 = *(_QWORD *)(v199 + 7192);
              if ( v458 >= WORD2(a2) && (v458 != WORD2(a2) || v457 >= (unsigned int)a2) )
              {
                v511 = v474;
                v512 = v475;
                v200 = *((_QWORD *)v198 + 6);
                LODWORD(v427) = 0;
                LOBYTE(v426) = 3;
                LOBYTE(v195) = 1;
                v201 = AcquireTransactionLock(*(unsigned __int16 *)(v200 + 1720), &v511, v198, v195, v426, v427);
                if ( v201 == -1 )
                  goto LABEL_580;
                LOBYTE(v202) = 72;
                lck_StandardHandler(v201, v202);
              }
            }
          }
        }
      }
    }
    if ( *((_QWORD *)v79[1] + 48) )
    {
      v70 = v434;
    }
    else
    {
      v81 = *v79;
      v82 = v434;
      v83 = (int)(*((_DWORD *)v434 + 4) << 31) >> 31;
      v84 = *(_BYTE *)(*((_QWORD *)v81 + 6) + 7390LL);
      if ( (**(unsigned __int8 (__fastcall ***)(struct XDES *))v81)(v81) )
        goto LABEL_80;
      if ( v84 )
        goto LABEL_594;
      if ( !v83 )
        goto LABEL_80;
      if ( (*((_BYTE *)v82 + 16) & 0x40) == 0 )
      {
LABEL_594:
        v70 = v82;
      }
      else
      {
        v232 = *((_QWORD *)v81 + 26);
        if ( !v232 )
        {
LABEL_80:
          v70 = v82;
          goto LABEL_81;
        }
        v70 = v82;
        if ( !*(_BYTE *)(v232 + 52)
          || !*(_QWORD *)(v232 + 64)
          || *(_QWORD *)(*(_QWORD *)v82 + 40LL) == _InterlockedCompareExchange64(
                                                     (volatile signed __int64 *)(v232 + 296),
                                                     0,
                                                     0) )
        {
LABEL_81:
          v85 = a8;
          goto LABEL_82;
        }
      }
      v79 = v435;
    }
    if ( !*((_BYTE *)v79[4] + 7390) || a9 != 1 )
      goto LABEL_762;
    v236 = v445;
    v565 = *(_DWORD *)v445;
    v566 = *((_WORD *)v445 + 2);
    v567 = *((_WORD *)v445 + 3);
    v237 = *((_QWORD *)v496 + 1);
    if ( !v237 || (v238 = *(_QWORD *)(v237 + 8), *(_BYTE *)(v238 + 63)) )
    {
      if ( *((_DWORD *)v496 + 16) == 2 )
      {
        v242 = (int *)*((_QWORD *)v496 + 6);
        v559 = *v242;
        v560 = *((_WORD *)v242 + 2);
        v561 = 0;
        v243 = &v559;
      }
      else
      {
        v244 = (int *)*((_QWORD *)v496 + 5);
        v562 = *v244;
        v563 = *((_WORD *)v244 + 2);
        v564 = 0;
        v243 = &v562;
      }
      v463 = *v243;
      v239 = *((_WORD *)v243 + 2);
    }
    else
    {
      v463 = *(_DWORD *)(v238 + 8);
      v239 = *(_WORD *)(v238 + 12);
    }
    v465 = 0;
    v464 = v239;
    LOBYTE(v430) = 1;
    LOBYTE(v429) = 0;
    v240 = BlobManager::RevertFromVersion(
             *v79,
             &v463,
             v79[1],
             &v695,
             v46,
             &v565,
             v70,
             (_DWORD)v429,
             (_DWORD)v430,
             0,
             v438);
    if ( v240 == 3 )
    {
      utassert_fail(1u, "lrRetCode != LOGICAL_REVERT_BLOB_COULD_NOT_TAKE_LOCKS", "blobbase.cpp", 1886, 0);
      goto LABEL_591;
    }
    if ( v240 != 4 )
    {
      v22 = v443;
      v21 = v450;
      v27 = v462;
      if ( v240 == 2 )
        goto LABEL_466;
      goto LABEL_762;
    }
    v245 = *((__int16 *)v236 + 3);
    v702 = *((__int16 *)v236 + 3);
    if ( *(char *)(v46 + 2) >= 0 )
    {
      v246 = 0;
      goto LABEL_603;
    }
    v249 = (unsigned __int8 *)(v46 + 96);
    _mm_prefetch((const char *)(v46 + 96), 0);
    if ( v695 && (v246 = v699) != 0 )
    {
      v250 = -1;
    }
    else
    {
      v706 = 0;
      v708 = 0u;
      v709 = 0;
      v711 = 0;
      v703 = 0;
      v250 = -1;
      v704 = 0xFFFFu;
      v707 = 0;
      memset(v705, 0, sizeof(v705));
      v710 = 0u;
      v246 = &v703;
    }
    if ( !*(_WORD *)(v46 + 36) )
      goto LABEL_620;
    v251 = *(_BYTE *)(v46 + 1);
    if ( v251 != 11 )
    {
      if ( v251 != 8 )
        goto LABEL_618;
      goto LABEL_619;
    }
    if ( *(_DWORD *)(v46 + 24) == 99 )
      goto LABEL_611;
LABEL_618:
    if ( v251 == 9 )
    {
LABEL_619:
      if ( *(_DWORD *)(v46 + 24) != 99 )
        goto LABEL_620;
LABEL_611:
      v515 = *(_DWORD *)(v46 + 32);
      v516 = *(_WORD *)(v46 + 36);
      if ( !(unsigned __int8)IsConcurrentUpdateSupportedPageId(&v515, a2) )
        goto LABEL_620;
      PageHeader::GetIcxLsn(v46, &v504);
    }
    else
    {
LABEL_620:
      v504 = *(_QWORD *)(v46 + 40);
      v505 = *(_WORD *)(v46 + 48);
    }
    *(_QWORD *)v246 = v249;
    v252 = v505;
    v253 = HIDWORD(v504);
    *((_DWORD *)v246 + 24) = v504;
    *((_DWORD *)v246 + 25) = v253;
    *((_WORD *)v246 + 52) = v252;
    *((_DWORD *)v246 + 27) = *(_DWORD *)(v46 + 32);
    *((_WORD *)v246 + 56) = *(_WORD *)(v46 + 36);
    *((_WORD *)v246 + 57) = 0;
    v254 = 3LL * *v249;
    v598 = *(_DWORD *)((char *)&PageComprInfo::sm_OffsetMap + 6 * *v249);
    v255 = word_102883984[v254];
    *((_WORD *)v246 + 8) = v250;
    *((_QWORD *)v246 + 3) = 0;
    *((_DWORD *)v246 + 5) = 0;
    *(_QWORD *)((char *)v246 + 46) = 0;
    *((_QWORD *)v246 + 7) = 0;
    *((_QWORD *)v246 + 4) = 0;
    *((_QWORD *)v246 + 9) = 0;
    *((_QWORD *)v246 + 10) = 0;
    *((_WORD *)v246 + 44) = 0;
    if ( (**(_BYTE **)v246 & 2) != 0 )
    {
      v256 = &v249[v255];
      if ( (v249[v255] & 1) != 0 )
      {
        *((_WORD *)v246 + 8) = 1;
        *((_QWORD *)v246 + 3) = v256;
        v257 = *v256;
        switch ( *v256 & 0x1C )
        {
          case 0:
          case 0xC:
          case 0x10:
          case 0x14:
          case 0x18:
          case 0x1C:
            if ( (v256[1] & 0x80u) != 0 )
            {
              v264 = *(_WORD *)(v256 + 1);
              *((_WORD *)v246 + 9) = v264;
              v258 = 3;
              v259 = HIBYTE(v264) | ((v264 & 0x7F) << 8);
            }
            else
            {
              v258 = 2;
              v259 = v256[1];
            }
            *((_WORD *)v246 + 9) = v259;
            *((_WORD *)v246 + 20) = v258;
            *((_WORD *)v246 + 22) = v258 + (((unsigned int)*((unsigned __int16 *)v246 + 9) + 1) >> 1);
            v260 = *((unsigned __int16 *)v246 + 9);
            if ( v260 > 0x1E )
              *((_WORD *)v246 + 21) = (int)(v260 - 1) / 30;
            else
              *((_WORD *)v246 + 21) = 0;
            *((_DWORD *)v246 + 5) = 0;
            *((_DWORD *)v246 + 16) = 0;
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 4) = 0;
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
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 4) = 0;
            break;
          case 4:
            if ( (v257 & 0x1C) != 4 || (v265 = 1, (v257 & 2) == 0) )
              v265 = 0;
            *((_DWORD *)v246 + 5) = 0;
            *((_QWORD *)v246 + 5) = 0;
            *((_WORD *)v246 + 9) = 0;
            *((_QWORD *)v246 + 6) = 0;
            *((_QWORD *)v246 + 4) = 0;
            *((_DWORD *)v246 + 16) = 0;
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 3) = v256;
            if ( v265 )
            {
              *((_DWORD *)v246 + 5) = v433;
              *((_DWORD *)v246 + 16) = 0;
              *((_DWORD *)v246 + 16) = 1;
            }
            else
            {
              *((_DWORD *)v246 + 5) = 1;
              *((_DWORD *)v246 + 16) = 0;
            }
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 4) = 0;
            break;
          case 8:
            *((_QWORD *)v246 + 5) = 0;
            *((_WORD *)v246 + 9) = 0;
            *((_QWORD *)v246 + 6) = 0;
            *((_QWORD *)v246 + 4) = 0;
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 3) = v256;
            *((_DWORD *)v246 + 5) = 9;
            *((_DWORD *)v246 + 16) = 0;
            *((_QWORD *)v246 + 7) = 0;
            *((_QWORD *)v246 + 4) = 0;
            break;
        }
      }
      else
      {
        *((_WORD *)v246 + 8) = 0;
        v266 = 0;
        *((_QWORD *)v246 + 3) = v256;
        *((_DWORD *)v246 + 5) = 0;
        *(_DWORD *)((char *)v246 + 54) = 0;
        switch ( *v256 & 0xE )
        {
          case 0:
          case 2:
          case 8:
          case 0xC:
            v266 = *((unsigned __int16 *)v256 + 1);
            if ( (unsigned int)(v266 - 1) > 0x1F9D )
              RaiseInconsistencyError(&v249[v255], 6);
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
            v266 = 9;
            break;
          case 6:
          case 0xA:
            break;
          case 0xE:
            v266 = 1;
            break;
        }
        *((_DWORD *)v246 + 8) = v266;
        *(_QWORD *)((char *)v246 + 46) = 0;
      }
    }
    if ( (**(_BYTE **)v246 & 4) != 0 )
    {
      if ( HIWORD(v598) )
        v261 = &v249[*(unsigned __int16 *)&v249[2 * SHIWORD(v598) + 1]];
      else
        v261 = &v249[v255];
      *((_QWORD *)v246 + 9) = v261;
      v262 = *(_WORD *)v261;
      *((_QWORD *)v246 + 10) = v261 + 2;
      *((_WORD *)v246 + 44) = 2 * (v262 + 1);
    }
    v263 = (PageComprInfoCache *)*((_QWORD *)v246 + 1);
    if ( v263 )
      PageComprInfoCache::Init(v263, (const struct PageComprInfo *)v246);
LABEL_603:
    v247 = *(unsigned __int16 *)(v46 + 14);
    v248 = (unsigned __int8 *)(v46 + *(unsigned __int16 *)(v46 + 2 * (v483 - v245)));
    v92 = (*v248 & 1) == 0;
    v698 = (struct XDES *)v248;
    if ( v92 )
    {
      v695 = 0;
      v433 = 0;
      v697 = 0;
      *(_DWORD *)&v700[14] = 0;
      a2 = *v248 & 0xE;
      switch ( *v248 & 0xE )
      {
        case 0:
        case 2:
        case 8:
        case 0xC:
          v247 = *((unsigned __int16 *)v248 + 1);
          if ( v247 - 1 > 0x1F9D )
          {
            RaiseInconsistencyError(v248, 6);
            v433 = v697;
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
          v433 = v697;
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
      LODWORD(v699) = v247;
      *(_QWORD *)&v700[6] = v46 + 0x2000;
      LODWORD(v246) = v247;
    }
    else
    {
      v695 = 1;
      a2 = *v248;
      switch ( *v248 & 0x1C )
      {
        case 0:
        case 0xC:
        case 0x10:
        case 0x14:
        case 0x18:
        case 0x1C:
          if ( (v248[1] & 0x80u) != 0 )
          {
            v267 = HIBYTE(*(_WORD *)(v248 + 1)) | ((*(_WORD *)(v248 + 1) & 0x7F) << 8);
            v696 = v267;
            a2 = 3;
            *(_WORD *)v700 = 3;
          }
          else
          {
            v267 = v248[1];
            v696 = v267;
            a2 = 2;
            *(_WORD *)v700 = 2;
          }
          *(_WORD *)&v700[4] = a2 + (((unsigned int)v267 + 1) >> 1);
          if ( v267 > 0x1Eu )
          {
            a2 = (unsigned int)((v267 - 1) / 30);
            *(_WORD *)&v700[2] = (v267 - 1) / 30;
          }
          else
          {
            *(_WORD *)&v700[2] = 0;
          }
          v268 = 0;
          v697 = 0;
          v701 = 0;
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
          v268 = v697;
          goto LABEL_656;
        case 4:
          if ( (a2 & 0x1C) == 4 && (a2 & 2) != 0 )
          {
            *(_QWORD *)v700 = 0;
            v696 = 0;
            *(_QWORD *)&v700[8] = 0;
            v697 = v433;
            v701 = 1;
          }
          else
          {
            *(_QWORD *)v700 = 0;
            v696 = 0;
            *(_QWORD *)&v700[8] = 0;
            v268 = 1;
            v697 = 1;
            v701 = 0;
LABEL_656:
            v433 = v268;
          }
          *(_QWORD *)&v700[16] = v46 + 0x2000;
          v699 = v246;
          v247 = (unsigned int)v246;
          break;
        case 8:
          *(_QWORD *)v700 = 0;
          v696 = 0;
          *(_QWORD *)&v700[8] = 0;
          v268 = 9;
          v697 = 9;
          v701 = 0;
          goto LABEL_656;
      }
    }
    v66 = v698;
    if ( v695 )
    {
      a2 = v433;
      if ( !v433 )
      {
        CDRecord::Resize((CDRecord *)&v696);
        a2 = v697;
      }
      if ( (unsigned int)a2 >= 9 )
        goto LABEL_774;
      v296 = *(_BYTE *)v698 & 0x1C;
      if ( (*(_BYTE *)v698 & 0x1C) == 0 )
        goto LABEL_761;
      v433 = 9;
      if ( v296 != 12 )
LABEL_774:
        v433 = a2;
      goto LABEL_775;
    }
    v269 = v433;
    if ( !v433 )
    {
      v696 = 0;
      HIDWORD(v699) = v247;
      v270 = *(_BYTE *)v698;
      HIDWORD(v699) = (_DWORD)v246;
      if ( (v270 & 0x10) != 0 )
      {
        if ( (*(_BYTE *)v698 & 0x10) != 0 )
          v271 = *(unsigned __int16 *)((char *)v698 + v247);
        else
          v271 = 0;
        LODWORD(v246) = ((unsigned int)(v271 + 7) >> 3) + (_DWORD)v246 + 2;
        HIDWORD(v699) = (_DWORD)v246;
      }
      if ( (*(_BYTE *)v698 & 0x20) != 0 )
      {
        v272 = (unsigned __int16 *)((char *)v698 + (unsigned int)v246);
        a2 = *v272;
        *(_WORD *)&v700[4] = a2;
        if ( !(_WORD)a2 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v273 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v273 )
            {
              v274 = *(_QWORD *)(v273 + 96);
              if ( v274 )
              {
                if ( *(_BYTE *)(v274 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                  else
                    ex_raise(34, 68, 21, 1003);
                }
              }
            }
          }
          RaiseInconsistencyError(v698, 3);
          a2 = *(unsigned __int16 *)&v700[4];
          LODWORD(v246) = HIDWORD(v699);
        }
        v275 = (_DWORD)v246 + 2 * ((unsigned __int16)a2 + 1);
        *(_DWORD *)v700 = v275;
        if ( v275 > 0x1F9E )
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
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v698, 4);
          a2 = *(unsigned __int16 *)&v700[4];
          v275 = *(_DWORD *)v700;
          LODWORD(v246) = HIDWORD(v699);
        }
        v269 = v272[(unsigned __int16)a2] & 0x7FFF;
        v433 = v269;
        v697 = v269;
        if ( v275 > v269 )
        {
          if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
          {
            v278 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                             + SystemThread_TlsOffset
                             + 8LL);
            if ( v278 )
            {
              v279 = *(_QWORD *)(v278 + 96);
              if ( v279 )
              {
                if ( *(_BYTE *)(v279 + 1177) )
                {
                  if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                    utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                  else
                    ex_raise(34, 68, 21, 1004);
                }
              }
            }
          }
          RaiseInconsistencyError(v698, 4);
          a2 = *(unsigned __int16 *)&v700[4];
          v275 = *(_DWORD *)v700;
          LODWORD(v246) = HIDWORD(v699);
          v269 = v697;
          v433 = v697;
        }
        while ( (v272[(unsigned __int16)a2] & 0x8000u) != 0 )
        {
          v280 = (char *)v698 + (unsigned int)v246;
          if ( (unsigned __int16)a2 == 1 )
            v281 = v275;
          else
            v281 = *(_WORD *)&v280[2 * (unsigned __int16)a2 - 2] & 0x7FFF;
          if ( v281 < v275 || (*(_WORD *)&v280[2 * (unsigned __int16)a2] & 0x7FFFu) < v281 )
          {
            RaiseInconsistencyError(v698, 7);
            a2 = *(unsigned __int16 *)&v700[4];
            v275 = *(_DWORD *)v700;
            LODWORD(v246) = HIDWORD(v699);
            v269 = v697;
            v433 = v697;
          }
          if ( v281 < v275 || v281 > v269 )
            goto LABEL_758;
          v282 = *(_WORD *)((char *)v698 + v281);
          if ( v282 == 5 )
          {
            v696 |= 2u;
            *(_WORD *)&v700[4] = a2 - 1;
            *(_WORD *)&v700[18] = v281;
            v283 = (char *)v698 + (unsigned __int16)v281;
            v284 = *((_WORD *)v283 + 1);
            if ( (v284 & 0x4000) != 0 )
              v285 = (*(_WORD *)&v700[20] ^ v284) & 0x3800 ^ *(_WORD *)&v700[20];
            else
              v285 = *(_WORD *)&v700[20] & 0xC7FF;
            *(_WORD *)&v700[20] = v285;
            v286 = *((_WORD *)v283 + 1) ^ v285;
            a2 = 2047;
            v287 = v286 & 0x7FF ^ v285;
            *(_WORD *)&v700[20] = v287;
            break;
          }
          if ( v282 >= 0x400u )
          {
            v696 |= 1u;
            v92 = (_WORD)a2 == 1;
            LOWORD(a2) = a2 - 1;
            *(_WORD *)&v700[4] = a2;
            if ( !v92 )
              continue;
          }
          break;
        }
      }
      else
      {
        v269 = (unsigned int)v246;
        v433 = (unsigned int)v246;
        v697 = (unsigned int)v246;
        *(_WORD *)&v700[4] = 0;
        *(_DWORD *)v700 = (_DWORD)v246;
      }
      if ( (*(_BYTE *)v698 & 0x40) != 0 )
      {
        *(_DWORD *)&v700[14] = v269;
        v697 = v269 + 14;
        v288 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v696);
        a2 = HIWORD(*(_QWORD *)v288);
        v289 = 0;
        v290 = (__int16)a2 ^ ((unsigned int)(__int16)a2 >> 1);
        if ( (v290 & 0x2000) != 0 )
        {
          if ( (a2 & 0x4000) != 0 )
            LOWORD(a2) = a2 | 0x2000;
          else
            LOWORD(a2) = a2 & 0xDFFF;
        }
        if ( (_WORD)a2 == 0xFFFC )
          v289 = (unsigned __int16)WORD2(*(_QWORD *)v288) >> 5;
        v269 = v289 + v697;
        v433 = v289 + v697;
        v697 += v289;
      }
      else
      {
        *(_DWORD *)&v700[14] = 0;
      }
      if ( *(_QWORD *)&v700[6] && *(_QWORD *)&v700[6] < (unsigned __int64)v698 + v269 )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v291 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v291 )
          {
            v292 = *(_QWORD *)(v291 + 96);
            if ( v292 )
            {
              if ( *(_BYTE *)(v292 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                else
                  ex_raise(34, 68, 21, 1018);
              }
            }
          }
        }
        RaiseInconsistencyError(v698, 18);
        v269 = v697;
        v433 = v697;
      }
      if ( v269 - 1 > 0x3F3B )
      {
        if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
        {
          v293 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v293 )
          {
            v294 = *(_QWORD *)(v293 + 96);
            if ( v294 )
            {
              if ( *(_BYTE *)(v294 + 1177) )
              {
                if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                  utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                else
                  ex_raise(34, 68, 21, 1005);
              }
            }
          }
        }
        RaiseInconsistencyError(v698, 5);
        v269 = v697;
        v433 = v697;
      }
    }
LABEL_758:
    if ( v269 >= 9 || (v295 = *(_BYTE *)v698 & 0xE) != 0 && v295 != 12 )
    {
LABEL_775:
      *v482 = v433;
      goto LABEL_762;
    }
LABEL_761:
    v433 = 9;
    *v482 = 9;
LABEL_762:
    v70 = v434;
LABEL_591:
    if ( v446 )
    {
      v716 = -1;
      v719 = 0;
      v718 = 0;
      v723 = 0;
      *(_QWORD *)((char *)&v724 + 2) = 0;
      v720 = 0;
      v725 = -1;
      v439 = 0;
      v307 = v435;
      v308 = v435[4];
      if ( *((_BYTE *)v308 + 8272) )
      {
        v309 = *((_QWORD *)v308 + 214);
        if ( (*(_BYTE *)(v309 + 60) & 1) != 0 && !*(_QWORD *)(v309 + 640) )
        {
          v576 = 0;
          v577 = 0;
          v712 = 0;
          v713 = 0;
          v310 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                           + SystemThread_TlsOffset
                           + 8LL);
          if ( v310 )
          {
            v311 = *(_QWORD *)(v310 + 96);
            v714 = v311;
            v715 = 0;
            if ( v311 && !*(_QWORD *)(v311 + 1464) )
            {
              *(_QWORD *)(v311 + 1464) = &v712;
              v715 = 1;
            }
          }
          else
          {
            v714 = 0;
            v715 = 0;
          }
          try
          {
            ExcHandler::ExcHandler(
              (ExcHandler *)v692,
              6u,
              0x5Du,
              0,
              (int (*)(int, int, int, int, char *))hdl_backout,
              0);
            v730[0] = 0;
            v730[1] = 0;
            v731 = 0;
            v312 = *(_WORD *)(v46 + 4) & 0x2000;
            v611 = v312;
            v313 = (struct ForeignXdesContext *)*((_QWORD *)v307[1] + 48);
            v590 = v313;
            v314 = *v307;
            v497 = v314;
            Lsn = Page::GetLsn(v46, v659, 0, 0);
            v645 = Lsn;
            v316 = (char *)v314 + 48;
            v317 = *((_QWORD *)v314 + 6);
            v589 = v317;
            v318 = *(_BYTE *)(v317 + 7390);
            v437 = v318;
            if ( *(_BYTE *)(v317 + 8272) && (*((_BYTE *)v434 + 16) & 1) != 0 )
            {
              v319 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v314 + 240LL))(v314)
                   ? *(_QWORD *)((*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v314 + 488LL))(v314) + 584)
                   : *((_QWORD *)v314 + 73);
              v646 = v319;
              v647 = v319;
              if ( !*(_BYTE *)(v319 + 22) )
                ex_raise(39, 48, 16, 2);
            }
            PageRow::Clone((PageRow *)&v716, (const struct PageRow *)&v695);
            v439 = 1;
            if ( !v313 )
            {
              if ( !v312 )
              {
                v448 = (unsigned __int8)byte_10317AD6E >> 3;
                if ( (byte_10317AD6E & 8) == 0 )
                {
                  v544 = 0;
                  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
                  v621 = (__int64 *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                  v361 = *v621;
                  v622 = v361;
                  if ( !v361 || (v362 = **(struct CSessionTraceFlags ***)(v361 + 56), (v623 = v362) == 0) )
                  {
                    v615 = 0;
                    goto LABEL_932;
                  }
                  v615 = v362;
                  v544 = CSessionTraceFlags::CheckSessionTraceInternal(v362, 0xF73u);
                  if ( !v544 )
                  {
LABEL_932:
                    v436 = 1;
                    goto LABEL_933;
                  }
                  v314 = v497;
                }
                v363 = *((_QWORD *)v314 + 26);
                v624 = v363;
                if ( v363 )
                  v364 = *(_QWORD *)(v363 + 64);
                else
                  v364 = 0;
                v365 = *((_QWORD *)v314 + 82);
                v538 = *(_WORD *)(*(_QWORD *)v316 + 1720LL);
                v366 = v538;
                v367 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v365 + 312LL))(v365);
                LogSystemMetadata(
                  L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v366,
                  *((_QWORD *)v434 + 5),
                  v367,
                  v364);
                goto LABEL_932;
              }
              v320 = *(_QWORD *)v316;
              v648 = v320;
              if ( *(_BYTE *)(v320 + 6872) )
                goto LABEL_815;
              if ( v695 )
                CDRecord::GetVersionRecPtr(&v696, v568);
              else
                FixedVarRecord::GetVersionRecPtr(&v696, v568);
              v650 = v568;
              if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v568) )
              {
LABEL_815:
                v321 = *(_QWORD *)(*(_QWORD *)(v320 + 1712) + 704LL);
                v651 = v321;
                if ( *(_WORD *)(v321 + 10) == 2 && !*(_DWORD *)Lsn
                  || (v652 = v321, *(_DWORD *)Lsn > *(_DWORD *)v321)
                  || *(_DWORD *)Lsn == *(_DWORD *)v321
                  && ((v348 = *(_DWORD *)(Lsn + 4), v348 > *(_DWORD *)(v321 + 4))
                   || v348 == *(_DWORD *)(v321 + 4) && *(_WORD *)(Lsn + 8) > *(_WORD *)(v321 + 8)) )
                {
                  v480 = 1;
                }
                else
                {
                  v480 = 0;
                  if ( !*(_BYTE *)(v320 + 8272) )
                    goto LABEL_924;
                  if ( v695 )
                    CDRecord::GetVersionRecPtr(&v696, v569);
                  else
                    FixedVarRecord::GetVersionRecPtr(&v696, v569);
                  v653 = v569;
                  if ( !VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v569) )
                  {
LABEL_924:
                    v447 = (unsigned __int8)byte_10317AD6E >> 3;
                    if ( (byte_10317AD6E & 8) != 0 )
                    {
LABEL_929:
                      v351 = *((_QWORD *)v314 + 26);
                      v619[2] = v351;
                      if ( v351 )
                        v352 = *(_QWORD *)(v351 + 64);
                      else
                        v352 = 0;
                      v353 = *((_QWORD *)v314 + 82);
                      v537 = *(_WORD *)(*(_QWORD *)v316 + 1720LL);
                      v354 = v537;
                      v355 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v353 + 312LL))(v353);
                      LogSystemMetadata(
                        L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                        v354,
                        *((_QWORD *)v434 + 5),
                        v355,
                        v352);
                      goto LABEL_932;
                    }
                    v543 = 0;
                    v654 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    v655 = (__int64 *)(v654[SystemThread_TlsIndex] + SystemThread_TlsOffset);
                    v349 = *v655;
                    v656 = v349;
                    if ( v349 && (v350 = **(struct CSessionTraceFlags ***)(v349 + 56), (v657 = v350) != 0) )
                    {
                      v608 = v350;
                      v543 = CSessionTraceFlags::CheckSessionTraceInternal(v350, 0xF73u);
                      if ( v543 )
                      {
                        v314 = v497;
                        goto LABEL_929;
                      }
                    }
                    else
                    {
                      v608 = 0;
                    }
                    goto LABEL_932;
                  }
                }
              }
            }
            v436 = 0;
            v322 = *v719;
            if ( v716 )
              v323 = v322 >> 1;
            else
              v323 = v322 >> 6;
            v609 = v323 & 1;
            if ( (v323 & 1) != 0 )
            {
              v23 = 0;
              v443 = 0;
              v444 = 0;
              if ( v716 )
                CDRecord::GetXdesTs(&v717, &v476);
              else
                FixedVarRecord::GetXdesTs(&v717, &v476);
              v625 = &v476;
              if ( v477 || v476 )
              {
                v324 = v434;
                if ( v313 || !v434 || (*((_BYTE *)v434 + 16) & 0x20) == 0 )
                  goto LABEL_963;
                v325 = (*((_BYTE *)v314 + 536) & 4) != 0
                     ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v314 + 488LL))(v314) + 40
                     : (__int64)v314 + 40;
                v626 = v325;
                if ( v716 )
                  CDRecord::GetXdesTs(&v717, &v478);
                else
                  FixedVarRecord::GetXdesTs(&v717, &v478);
                v627 = &v478;
                if ( v479 != *(_WORD *)(v325 + 4) || v478 != *(_DWORD *)v325 )
                  goto LABEL_963;
                v326 = (struct XVB **)((char *)v314 + 208);
                v327 = *((_QWORD *)v314 + 26);
                v628 = v327;
                if ( !v318
                  || v327
                  && *(_BYTE *)(v327 + 52)
                  && *(_QWORD *)(v327 + 64)
                  && (v629 = _InterlockedCompareExchange64((volatile signed __int64 *)(v327 + 296), 0, 0),
                      v318 = v437,
                      v317 = v589,
                      v313 = v590,
                      v314 = v497,
                      *(_QWORD *)(*(_QWORD *)v324 + 40LL) != v629) )
                {
                  VersionMgr::GetVersionWithUpdateMarker(
                    *v326,
                    *((const struct UserInfo **)v324 + 4),
                    *(const struct DBTABLE **)(v317 + 1712),
                    v446,
                    0x1F9Eu,
                    *(const struct UpdateSequenceMarker **)v324,
                    (struct Record *)&v716,
                    0,
                    1,
                    (struct VersionMgr::GetVersionResult *)&v439,
                    0);
                }
                if ( v318 )
                {
                  if ( v716 )
                    CDRecord::GetVersionRecPtr(&v717, v570);
                  else
                    FixedVarRecord::GetVersionRecPtr(&v717, v570);
                  v630 = v570;
                  if ( v716 )
                    CDRecord::GetXdesTs(&v717, &v470);
                  else
                    FixedVarRecord::GetXdesTs(&v717, &v470);
                  v638 = &v470;
                  v610 = v470;
                  v539 = v471;
                  v517 = v470;
                  v518 = v471;
                  if ( (unsigned int)XdesMgr::GetRowAbortState(v317 + 6600, &v517, v570) )
                  {
LABEL_963:
                    v432 = 0;
                    if ( v695 == 1 )
                    {
                      v506 = 1;
                      VersionMgr::GetVersionFromCompressed(
                        (const struct PageRow *)&v695,
                        v446,
                        0x1F9Eu,
                        v314,
                        v324,
                        (struct PageRow *)&v716,
                        (struct VersionMgr::GetVersionResult *)&v439,
                        0,
                        0,
                        v313,
                        (const struct LSN *)v730,
                        v432);
                    }
                    else
                    {
                      v506 = 0;
                      VersionMgr::GetVersionLong(
                        v446,
                        0x1F9Eu,
                        v314,
                        v324,
                        (struct Record *)&v716,
                        (struct VersionMgr::GetVersionResult *)&v439,
                        0,
                        0,
                        v313,
                        (const struct LSN *)v730,
                        1,
                        v432);
                    }
                  }
                }
                goto LABEL_846;
              }
            }
LABEL_933:
            v449 = (unsigned __int8)byte_10317AD6E >> 3;
            v23 = 0;
            if ( (byte_10317AD6E & 8) == 0 )
            {
              v571 = 0;
              v631 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v632 = (__int64 *)(v631[SystemThread_TlsIndex] + SystemThread_TlsOffset);
              v356 = *v632;
              v649 = v356;
              if ( v356 && (v357 = **(struct CSessionTraceFlags ***)(v356 + 56), (v633 = v357) != 0) )
              {
                v616 = v357;
                v571 = CSessionTraceFlags::CheckSessionTraceInternal(v357, 0xF73u);
                if ( v571 )
                  goto LABEL_937;
              }
              else
              {
                v616 = 0;
              }
LABEL_943:
              v324 = v434;
LABEL_846:
              ExcHandler::~ExcHandler((ExcHandler *)v692);
              goto LABEL_1162;
            }
LABEL_937:
            CDStream::CDStream((CDStream *)v693);
            ProcessHeap = GetProcessHeap();
            v359 = (CTracePrintStream *)HeapAlloc(ProcessHeap, 0, 0x6C0u);
            v634 = v359;
            if ( v359 )
              v360 = CTracePrintStream::CTracePrintStream(v359, 0);
            else
              v360 = 0;
            v635 = v360;
            v636 = v360;
            if ( v360 && !CDStream::AddDevice((CDStream *)v693, v360) )
            {
              v637 = v360;
              (**(void (__fastcall ***)(CTracePrintStream *, __int64))v360)(v360, 1);
            }
            Record::Dump((Record *)&v716, (struct CDStream *)v693);
            CDStream::~CDStream((CDStream *)v693);
            goto LABEL_943;
          }
          catch ( SQLError v658 )
          {
            try
            {
              ExceptionBackout::ExceptionBackout((ExceptionBackout *)v619, (const struct SQLError *)v658);
              if ( v658[0] / 100 != 6 || v658[0] != 693 )
              {
                CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v619);
                ExceptionRethrow(CurrentException);
              }
              PageRef::Unlatch(v581);
              if ( v715 )
              {
                *(_QWORD *)(v714 + 1464) = 0;
                v715 = 0;
              }
              v644 = &v578;
              v639 = *((_QWORD *)v435[1] + 11);
              v640 = *(_QWORD *)(v639 + 20);
              v641 = ((unsigned int)v640 | ((unsigned __int64)WORD2(v640) << 32)) << 16;
              v642 = &v712;
              v617 = v712;
              v618 = v713;
              v578 = v712;
              v579 = v713;
              RecoveryUnit::WaitForRedoLsnToCatchUp(v435[4], &v578, 5);
              v453 = 0;
              ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v619);
            }
            catch ( ShortStackException )
            {
              JUMPOUT(0x1016A88D3LL);
            }
            v23 = 0;
            if ( v715 )
            {
              *(_QWORD *)(v714 + 1464) = 0;
              v715 = 0;
            }
            v483 = 4095;
            v433 = 15;
            v27 = v462;
            v21 = v607;
            v450 = v607;
            v580 = v607;
            v24 = v607;
            v445 = v582;
            v438 = v581;
            v482 = v583;
            v22 = v542;
            v443 = v542;
            continue;
          }
LABEL_1162:
          v328 = v435;
          v329 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          v330 = *(struct Worker **)(v329 + 256);
          if ( !v330 )
          {
            SystemThread::MakeMiniSOSThread(0);
            v330 = *(struct Worker **)(v329 + 256);
          }
          if ( *((_DWORD *)v330 + 139) )
            ExceptionPostCatchActions(v330);
          if ( v715 )
          {
            *(_QWORD *)(v714 + 1464) = 0;
            v715 = 0;
          }
LABEL_853:
          v331 = v439;
          v332 = v445;
          if ( !v439 )
          {
            BlobBase::TableCorruptException(
              *(_WORD *)(*((_QWORD *)*v328 + 6) + 1720LL),
              v445,
              *((__int16 *)v445 + 3),
              10);
            v331 = v439;
          }
          if ( a9 == 1 && v331 != 1 )
          {
            if ( (*((_BYTE *)v324 + 16) & 8) == 0 )
              utassert_fail(1u, "plocalVerScanParams->IsSnapshotIso ()", "blobbase.cpp", 2059, 0);
            if ( CommonGlobalState::m_PerfCountersEnabled )
            {
              v333 = 0;
              if ( pCounterLookupBlocks )
                v333 = (char *)pCounterLookupBlocks + 57344;
              if ( v333 && *(_QWORD *)v333 )
                _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v333 + 40LL), 1u);
            }
            Xdes = LobContext::GetXdes(v328[1]);
            XVMgr::RaiseError(
              60,
              *(const struct DBTABLE **)(*((_QWORD *)Xdes + 6) + 1712LL),
              *((const struct UserInfo **)v324 + 4),
              7);
          }
          v335 = v718;
          if ( v716 )
          {
            if ( !v718 )
            {
              CDRecord::Resize((CDRecord *)&v717);
              v335 = v718;
            }
            if ( v335 >= 9 )
              goto LABEL_1117;
            if ( (*v719 & 0x1C) != 0 )
            {
              v414 = (*v719 & 0x1C) == 12;
LABEL_1115:
              if ( !v414 )
                goto LABEL_1117;
            }
          }
          else
          {
            if ( !v718 )
            {
              v717 = 0;
              v335 = v720;
              HIDWORD(v720) = v720;
              if ( (*v719 & 0x10) != 0 )
              {
                v335 = (((unsigned int)*(unsigned __int16 *)&v719[(unsigned int)v720] + 7) >> 3) + v720 + 2;
                HIDWORD(v720) = v335;
              }
              if ( (*v719 & 0x20) != 0 )
              {
                v336 = &v719[v335];
                v337 = *(_WORD *)v336;
                v722 = v337;
                if ( !v337 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v338 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v338 )
                    {
                      v339 = *(_QWORD *)(v338 + 96);
                      if ( v339 )
                      {
                        if ( *(_BYTE *)(v339 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2010, 0);
                          else
                            ex_raise(34, 68, 21, 1003);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v719, 3);
                  v337 = v722;
                }
                v340 = HIDWORD(v720) + 2 + 2 * v337;
                v721 = v340;
                if ( v340 > 0x1F9E )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v341 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v341 )
                    {
                      v342 = *(_QWORD *)(v341 + 96);
                      if ( v342 )
                      {
                        if ( *(_BYTE *)(v342 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2017, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v719, 4);
                  v337 = v722;
                  v340 = v721;
                }
                v335 = *(_WORD *)&v336[2 * v337] & 0x7FFF;
                v718 = v335;
                if ( v340 > v335 )
                {
                  if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                  {
                    v343 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL);
                    if ( v343 )
                    {
                      v344 = *(_QWORD *)(v343 + 96);
                      if ( v344 )
                      {
                        if ( *(_BYTE *)(v344 + 1177) )
                        {
                          if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                            utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2024, 0);
                          else
                            ex_raise(34, 68, 21, 1004);
                        }
                      }
                    }
                  }
                  RaiseInconsistencyError(v719, 4);
                  v337 = v722;
                  v340 = v721;
                  v335 = v718;
                }
                while ( 1 )
                {
                  if ( *(__int16 *)&v336[2 * v337] >= 0 )
                    goto LABEL_1084;
                  v345 = &v719[HIDWORD(v720)];
                  if ( v337 == 1 )
                  {
                    v346 = v340;
                  }
                  else
                  {
                    v346 = *(_WORD *)&v345[2 * v337 - 2] & 0x7FFF;
                    if ( v346 < v340 )
                    {
LABEL_905:
                      RaiseInconsistencyError(v719, 7);
                      v337 = v722;
                      v340 = v721;
                      v335 = v718;
                      goto LABEL_906;
                    }
                  }
                  if ( (*(_WORD *)&v345[2 * v337] & 0x7FFFu) < v346 )
                    goto LABEL_905;
LABEL_906:
                  if ( v346 < v340 || v346 > v335 )
                    goto LABEL_1112;
                  v347 = *(_WORD *)&v719[v346];
                  if ( v347 == 5 )
                  {
                    v717 |= 2u;
                    v722 = v337 - 1;
                    WORD2(v724) = v346;
                    v403 = &v719[(unsigned __int16)v346];
                    v404 = *((_WORD *)v403 + 1);
                    if ( (v404 & 0x4000) != 0 )
                      v405 = (WORD3(v724) ^ v404) & 0x3800 ^ WORD3(v724);
                    else
                      v405 = WORD3(v724) & 0xC7FF;
                    WORD3(v724) = v405;
                    WORD3(v724) = v405 ^ (*((_WORD *)v403 + 1) ^ v405) & 0x7FF;
                    goto LABEL_1084;
                  }
                  if ( v347 >= 0x400u )
                  {
                    v717 |= 1u;
                    v92 = v337-- == 1;
                    v722 = v337;
                    if ( !v92 )
                      continue;
                  }
                  goto LABEL_1084;
                }
              }
              v718 = v335;
              v722 = 0;
              v721 = v335;
LABEL_1084:
              if ( (*v719 & 0x40) != 0 )
              {
                LODWORD(v724) = v335;
                v718 = v335 + 14;
                v406 = FixedVarRecord::FindVersioningInfo((FixedVarRecord *)&v717);
                v407 = HIWORD(*(_QWORD *)v406);
                v408 = 0;
                if ( (((__int16)v407 ^ ((unsigned int)(__int16)v407 >> 1)) & 0x2000) != 0 )
                {
                  if ( (v407 & 0x4000) != 0 )
                    LOWORD(v407) = v407 | 0x2000;
                  else
                    LOWORD(v407) = v407 & 0xDFFF;
                }
                if ( (_WORD)v407 == 0xFFFC )
                  v408 = (unsigned __int16)WORD2(*(_QWORD *)v406) >> 5;
                v335 = v408 + v718;
                v718 += v408;
              }
              else
              {
                LODWORD(v724) = 0;
              }
              if ( v723 && v723 < (unsigned __int64)&v719[v335] )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v409 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v409 )
                  {
                    v410 = *(_QWORD *)(v409 + 96);
                    if ( v410 )
                    {
                      if ( *(_BYTE *)(v410 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2114, 0);
                        else
                          ex_raise(34, 68, 21, 1018);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v719, 18);
                v335 = v718;
              }
              if ( v335 - 1 > 0x3F3B )
              {
                if ( byte_10316E8D7 || (qword_10317B120 & 1) != 0 )
                {
                  v411 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                   + SystemThread_TlsOffset
                                   + 8LL);
                  if ( v411 )
                  {
                    v412 = *(_QWORD *)(v411 + 96);
                    if ( v412 )
                    {
                      if ( *(_BYTE *)(v412 + 1177) )
                      {
                        if ( byte_10316E7C7 || (qword_10317B120 & 2) != 0 )
                          utassert_fail(1u, "false", "Sql\\Ntdbms\\storeng\\drs\\fixedvarrecord.cpp", 2119, 0);
                        else
                          ex_raise(34, 68, 21, 1005);
                      }
                    }
                  }
                }
                RaiseInconsistencyError(v719, 5);
                v335 = v718;
              }
            }
LABEL_1112:
            if ( v335 >= 9 )
            {
LABEL_1117:
              *v482 = v335;
              if ( dword_103172528 )
              {
                v415 = v328[1];
                v416 = *((_QWORD *)v415 + 12);
                if ( v416 && *(_BYTE *)(*(_QWORD *)(v416 + 8) + 63LL) )
                  v417 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)(v416 + 592) + 88LL))(
                           **(_QWORD **)(v416 + 592),
                           *(_QWORD *)(*(_QWORD *)(v416 + 64) + 48LL));
                else
                  v417 = *((_QWORD *)v415 + 14);
                v418 = *(_QWORD *)(v417 + 48);
                if ( *(_DWORD *)(*(_QWORD *)(v418 + 1712) + 1516LL) == 1 )
                {
                  ObjectDataImpl = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)(v418 + 40));
                  ++*ObjectDataImpl;
                }
              }
              v420 = v719;
              if ( v716 )
              {
                v23 = (((*v719 & 0x1C) - 4) & 0xFFFFFFE7) == 0;
              }
              else
              {
                v421 = *v719 & 0xE;
                if ( v421 == 2 )
                {
                  if ( (v719[1] & 1) != 0 )
                    v23 = 1;
                }
                else if ( ((v421 - 10) & 0xF9) == 0 )
                {
                  v23 = 1;
                }
              }
              if ( v23 && !a8 )
              {
                if ( v716 )
                  CDRecord::GetXdesTs(&v717, &v488);
                else
                  FixedVarRecord::GetXdesTs(&v717, &v488);
                v422 = *v328;
                if ( v489 == *((_WORD *)*v328 + 22) && v488 == *((_DWORD *)v422 + 10) )
                {
                  v523 = *(_DWORD *)v332;
                  v524 = *((_WORD *)v332 + 2);
                  v423 = *(unsigned __int16 *)(*((_QWORD *)v422 + 6) + 1720LL);
                  LODWORD(v428) = *(__int16 *)(v587 + 6);
                  LODWORD(v426) = v423;
                  ex_raise(71, 9, 16, 13, v426, &v523, v428);
                }
                else
                {
                  BlobBase::TableCorruptException(
                    *(_WORD *)(*((_QWORD *)v422 + 6) + 1720LL),
                    v332,
                    *(__int16 *)(v587 + 6),
                    13);
                }
                return v719;
              }
              return v420;
            }
            v413 = *v719 & 0xE;
            if ( v413 )
            {
              v414 = v413 == 12;
              goto LABEL_1115;
            }
          }
          v335 = 9;
          goto LABEL_1117;
        }
      }
      v459 = 257;
      v460 = 0;
      v461 = 0;
      v732 = 0;
      v733 = 0;
      v368 = *(_WORD *)(v46 + 4) & 0x2000;
      if ( !*(_WORD *)(v46 + 36) )
        goto LABEL_1026;
      v369 = *(_BYTE *)(v46 + 1);
      if ( v369 == 11 )
      {
        if ( *(_DWORD *)(v46 + 24) == 99 )
        {
LABEL_974:
          v519 = *(_DWORD *)(v46 + 32);
          v520 = *(_WORD *)(v46 + 36);
          if ( (unsigned __int8)IsConcurrentUpdateSupportedPageId(&v519, a2) )
          {
            PageHeader::GetIcxLsn(v46, &v484);
LABEL_976:
            v370 = (struct LSN *)*((_QWORD *)v307[1] + 48);
            v371 = (struct OffRowPageRequestResult *)&v459;
            if ( !v370 )
              v371 = 0;
            v372 = *v307;
            v373 = *((_QWORD *)v372 + 6);
            v374 = *(_BYTE *)(v373 + 7390);
            if ( *(_BYTE *)(v373 + 8272) && (*((_BYTE *)v434 + 16) & 1) != 0 )
            {
              v375 = (*(unsigned int (__fastcall **)(struct XDES *))(*(_QWORD *)v372 + 240LL))(v372)
                   ? *(_QWORD *)((*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v372 + 488LL))(v372) + 584)
                   : *((_QWORD *)v372 + 73);
              if ( !*(_BYTE *)(v375 + 22) )
                ex_raise(39, 48, 16, 2);
            }
            PageRow::Clone((PageRow *)&v716, (const struct PageRow *)&v695);
            v439 = 1;
            if ( v370 )
              goto LABEL_1039;
            if ( !v368 )
            {
              if ( (byte_10317AD6E & 8) != 0
                || (v391 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v392 = **(struct CSessionTraceFlags ***)(v391 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v392, 0xF73u) )
              {
                v393 = *((_QWORD *)v372 + 26);
                if ( v393 )
                  v394 = *(_QWORD *)(v393 + 64);
                else
                  v394 = 0;
                v395 = *((_QWORD *)v372 + 82);
                v396 = *(unsigned __int16 *)(*((_QWORD *)v372 + 6) + 1720LL);
                v397 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v395 + 312LL))(v395);
                LogSystemMetadata(
                  L"Page is current (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v396,
                  *((_QWORD *)v434 + 5),
                  v397,
                  v394);
              }
              goto LABEL_1008;
            }
            v376 = *((_QWORD *)v372 + 6);
            if ( !*(_BYTE *)(v376 + 6872) )
            {
              if ( v695 )
                CDRecord::GetVersionRecPtr(&v696, v584);
              else
                FixedVarRecord::GetVersionRecPtr(&v696, v584);
              if ( VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v584) )
                goto LABEL_1039;
            }
            v377 = *(_QWORD *)(*(_QWORD *)(v376 + 1712) + 704LL);
            if ( *(_WORD *)(v377 + 10) == 2 && !(_DWORD)v484 )
              goto LABEL_1039;
            if ( (unsigned int)v484 > *(_DWORD *)v377 )
              goto LABEL_1039;
            if ( (_DWORD)v484 == *(_DWORD *)v377 )
            {
              v378 = *(_DWORD *)(v377 + 4);
              if ( HIDWORD(v484) > v378 || HIDWORD(v484) == v378 && v485 > *(_WORD *)(v377 + 8) )
                goto LABEL_1039;
            }
            if ( !*(_BYTE *)(v376 + 8272) )
              goto LABEL_1172;
            if ( v695 )
              CDRecord::GetVersionRecPtr(&v696, v585);
            else
              FixedVarRecord::GetVersionRecPtr(&v696, v585);
            if ( VersionRecPtr::IsVersionPersisted((VersionRecPtr *)v585) )
            {
LABEL_1039:
              v398 = *v719;
              if ( v716 )
                v399 = v398 >> 1;
              else
                v399 = v398 >> 6;
              if ( (v399 & 1) != 0 )
              {
                if ( v716 )
                  CDRecord::GetXdesTs(&v717, &v494);
                else
                  FixedVarRecord::GetXdesTs(&v717, &v494);
                if ( v495 || v494 )
                {
                  if ( v370 || !v434 || (*((_BYTE *)v434 + 16) & 0x20) == 0 )
                    goto LABEL_1066;
                  v400 = (*((_BYTE *)v372 + 536) & 4) != 0
                       ? (*(__int64 (__fastcall **)(struct XDES *))(*(_QWORD *)v372 + 488LL))(v372) + 40
                       : (__int64)v372 + 40;
                  if ( v716 )
                    CDRecord::GetXdesTs(&v717, &v490);
                  else
                    FixedVarRecord::GetXdesTs(&v717, &v490);
                  if ( v491 != *(_WORD *)(v400 + 4) || v490 != *(_DWORD *)v400 )
                    goto LABEL_1066;
                  if ( (v401 = *((_QWORD *)v372 + 26), v374)
                    && (!v401
                     || !*(_BYTE *)(v401 + 52)
                     || !*(_QWORD *)(v401 + 64)
                     || (v402 = _InterlockedCompareExchange64((volatile signed __int64 *)(v401 + 296), 0, 0),
                         *(_QWORD *)(*(_QWORD *)v434 + 40LL) == v402))
                    || (VersionMgr::GetVersionWithUpdateMarker(
                          *((struct XVB **)v372 + 26),
                          *((const struct UserInfo **)v434 + 4),
                          *(const struct DBTABLE **)(v373 + 1712),
                          v446,
                          0x1F9Eu,
                          *(const struct UpdateSequenceMarker **)v434,
                          (struct Record *)&v716,
                          0,
                          1,
                          (struct VersionMgr::GetVersionResult *)&v439,
                          v371),
                        v374) )
                  {
                    if ( v716 )
                      CDRecord::GetVersionRecPtr(&v717, v586);
                    else
                      FixedVarRecord::GetVersionRecPtr(&v717, v586);
                    if ( v716 )
                      CDRecord::GetXdesTs(&v717, &v492);
                    else
                      FixedVarRecord::GetXdesTs(&v717, &v492);
                    v521 = v492;
                    v522 = v493;
                    if ( (unsigned int)XdesMgr::GetRowAbortState(v373 + 6600, &v521, v586) )
                    {
LABEL_1066:
                      v432 = v371;
                      if ( v695 == 1 )
                      {
                        v431 = v370;
                        v324 = v434;
                        VersionMgr::GetVersionFromCompressed(
                          (const struct PageRow *)&v695,
                          v446,
                          0x1F9Eu,
                          v372,
                          v434,
                          (struct PageRow *)&v716,
                          (struct VersionMgr::GetVersionResult *)&v439,
                          0,
                          0,
                          v431,
                          (const struct LSN *)&v732,
                          v432);
                      }
                      else
                      {
                        v430 = v370;
                        v324 = v434;
                        VersionMgr::GetVersionLong(
                          v446,
                          0x1F9Eu,
                          v372,
                          v434,
                          (struct Record *)&v716,
                          (struct VersionMgr::GetVersionResult *)&v439,
                          0,
                          0,
                          v430,
                          (const struct LSN *)&v732,
                          1,
                          v432);
                      }
LABEL_1019:
                      v328 = v435;
                      if ( *((_QWORD *)v435[1] + 48) && (!(_BYTE)v459 || !HIBYTE(v459)) )
                      {
                        PageRef::Unlatch(v438);
                        ex_raise(164, 1, 25, 2);
                      }
                      goto LABEL_853;
                    }
                  }
LABEL_1018:
                  v324 = v434;
                  goto LABEL_1019;
                }
              }
            }
            else
            {
LABEL_1172:
              if ( (byte_10317AD6E & 8) != 0
                || (v379 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset)) != 0
                && (v380 = **(struct CSessionTraceFlags ***)(v379 + 56)) != 0
                && CSessionTraceFlags::CheckSessionTraceInternal(v380, 0xF73u) )
              {
                v381 = *((_QWORD *)v372 + 26);
                if ( v381 )
                  v382 = *(_QWORD *)(v381 + 64);
                else
                  v382 = 0;
                v383 = *((_QWORD *)v372 + 82);
                v384 = *(unsigned __int16 *)(*((_QWORD *)v372 + 6) + 1720LL);
                v385 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v383 + 312LL))(v383);
                LogSystemMetadata(
                  L"Before recovery version (dbid= %d rowsetid=%I64d) by xact (xactid=%I64d, xts=%I64d)\n",
                  v384,
                  *((_QWORD *)v434 + 5),
                  v385,
                  v382);
              }
            }
LABEL_1008:
            if ( (byte_10317AD6E & 8) != 0
              || (v386 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset,
                  *(_QWORD *)v386)
              && (v387 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v386 + 56LL)) != 0
              && CSessionTraceFlags::CheckSessionTraceInternal(v387, 0xF73u) )
            {
              CDStream::CDStream((CDStream *)v694);
              v388 = GetProcessHeap();
              v389 = (CTracePrintStream *)HeapAlloc(v388, 0, 0x6C0u);
              v588 = v389;
              if ( v389 )
                v390 = CTracePrintStream::CTracePrintStream(v389, 0);
              else
                v390 = 0;
              if ( v390 && !CDStream::AddDevice((CDStream *)v694, v390) )
                (**(void (__fastcall ***)(CTracePrintStream *, __int64))v390)(v390, 1);
              Record::Dump((Record *)&v716, (struct CDStream *)v694);
              CDStream::~CDStream((CDStream *)v694);
            }
            goto LABEL_1018;
          }
LABEL_1026:
          v484 = *(_QWORD *)(v46 + 40);
          v485 = *(_WORD *)(v46 + 48);
          goto LABEL_976;
        }
      }
      else if ( v369 == 8 )
      {
LABEL_1025:
        if ( *(_DWORD *)(v46 + 24) != 99 )
          goto LABEL_1026;
        goto LABEL_974;
      }
      if ( v369 != 9 )
        goto LABEL_1026;
      goto LABEL_1025;
    }
    break;
  }
  v85 = a8;
  if ( a8 )
  {
LABEL_82:
    v86 = (__int16 *)v445;
    v87 = v435;
  }
  else
  {
    v86 = (__int16 *)v445;
    v241 = (const struct Page *)v46;
    v87 = v435;
    VersionMgr::VerifyRowIsCurrent(*v435, v70, v241, *((__int16 *)v445 + 3));
  }
  v88 = *(_BYTE *)v698;
  if ( v695 )
  {
    if ( (v88 & 0x1C) == 4 && (v88 & 2) != 0 )
      goto LABEL_581;
  }
  else
  {
    if ( (v88 & 0xE) != 0xE )
      goto LABEL_85;
LABEL_581:
    if ( !v85 )
      BlobBase::TableCorruptException(
        *(_WORD *)(*((_QWORD *)*v87 + 6) + 1720LL),
        (const struct PageId *)v86,
        v86[3],
        11);
  }
LABEL_85:
  if ( dword_103172528 )
  {
    if ( v70 )
    {
      v297 = *v87;
      v298 = v434;
      v299 = (int)(*((_DWORD *)v434 + 4) << 31) >> 31;
      v300 = *(_BYTE *)(*((_QWORD *)*v87 + 6) + 7390LL);
      if ( !(**(unsigned __int8 (__fastcall ***)(struct XDES *))*v87)(*v87)
        && (v300
         || v299
         && ((*((_BYTE *)v298 + 16) & 0x40) == 0
          || (v301 = *((_QWORD *)v297 + 26)) != 0
          && *(_BYTE *)(v301 + 52)
          && *(_QWORD *)(v301 + 64)
          && *(_QWORD *)(*(_QWORD *)v298 + 40LL) != _InterlockedCompareExchange64(
                                                      (volatile signed __int64 *)(v301 + 296),
                                                      0,
                                                      0))) )
      {
        v302 = v87[1];
        v303 = *((_QWORD *)v302 + 12);
        if ( v303 && *(_BYTE *)(*(_QWORD *)(v303 + 8) + 63LL) )
          v304 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)(v303 + 592) + 88LL))(
                   **(_QWORD **)(v303 + 592),
                   *(_QWORD *)(*(_QWORD *)(v303 + 64) + 48LL));
        else
          v304 = *((_QWORD *)v302 + 14);
        v305 = *(_QWORD *)(v304 + 48);
        if ( *(_DWORD *)(*(_QWORD *)(v305 + 1712) + 1516LL) == 1 )
        {
          v306 = PerCPUDataImpl::GetObjectDataImpl((PerCPUDataImpl *)(v305 + 24));
          ++*v306;
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
