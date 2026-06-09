# CBulkError::Init(wchar_t const *,unsigned __int64,wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,CImportStream *,uint,int,IGrantPageAllocator *)

- ea: `0x102089310`
- end: `0x10208a3d7`
- name: `?Init@CBulkError@@QEAAJPEB_W_KPEA_W101PEAVCImportStream@@IHPEAVIGrantPageAllocator@@@Z`
- size: `4295`
- prototype: `__int64 __fastcall(CBulkError *__hidden this, const wchar_t *, unsigned __int64, wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64, struct CImportStream *, unsigned int, DWORD, struct IGrantPageAllocator *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x102071450`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100402050`
- `0x100475060`
- `0x1004ab5a0`
- `0x1004bb180`
- `0x100625f90`
- `0x10063df30`
- `0x10063e990`
- `0x100a7d300`
- `0x100ca7480`
- `0x1017636a0`
- `0x101a84c40`
- `0x102077d10`
- `0x102087ba0`
- `0x102089310`
- `0x10208b340`
- `0x1023920b0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x102089e5f`
- `KERNEL32!SetFilePointerEx` at `0x10208a201`
- `KERNEL32!SetFilePointerEx` at `0x102089e5f`
- `KERNEL32!SetFilePointerEx` at `0x10208a201`
- `KERNEL32!CreateFileW` at `0x102089d21`
- `KERNEL32!CreateFileW` at `0x10208a0df`
- `KERNEL32!CreateFileW` at `0x102089d21`
- `KERNEL32!CreateFileW` at `0x10208a0df`
- `KERNEL32!SetErrorMode` at `0x1020897f8`
- `KERNEL32!SetErrorMode` at `0x10208a396`
- `KERNEL32!SetErrorMode` at `0x1020897f8`
- `KERNEL32!SetErrorMode` at `0x10208a396`
- `KERNEL32!DuplicateHandle` at `0x10208a2c1`
- `KERNEL32!DuplicateHandle` at `0x10208a2c1`
- `KERNEL32!QueryPerformanceCounter` at `0x10208950a`
- `KERNEL32!QueryPerformanceCounter` at `0x102089563`
- `KERNEL32!QueryPerformanceCounter` at `0x1020896a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1020896fe`
- `KERNEL32!QueryPerformanceCounter` at `0x10208950a`
- `KERNEL32!QueryPerformanceCounter` at `0x102089563`
- `KERNEL32!QueryPerformanceCounter` at `0x1020896a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1020896fe`
- `KERNEL32!CloseHandle` at `0x102089ed0`
- `KERNEL32!CloseHandle` at `0x10208a1d2`
- `KERNEL32!CloseHandle` at `0x10208a274`
- `KERNEL32!CloseHandle` at `0x102089ed0`
- `KERNEL32!CloseHandle` at `0x10208a1d2`
- `KERNEL32!CloseHandle` at `0x10208a274`
- `KERNEL32!GetLastError` at `0x102089d2e`
- `KERNEL32!GetLastError` at `0x102089e76`
- `KERNEL32!GetLastError` at `0x10208a0e9`
- `KERNEL32!GetLastError` at `0x10208a21c`
- `KERNEL32!GetLastError` at `0x10208a2cb`
- `KERNEL32!GetLastError` at `0x102089d2e`
- `KERNEL32!GetLastError` at `0x102089e76`
- `KERNEL32!GetLastError` at `0x10208a0e9`
- `KERNEL32!GetLastError` at `0x10208a21c`
- `KERNEL32!GetLastError` at `0x10208a2cb`
- `KERNEL32!GetCurrentProcess` at `0x10208a290`
- `KERNEL32!GetCurrentProcess` at `0x10208a299`
- `KERNEL32!GetCurrentProcess` at `0x10208a290`
- `KERNEL32!GetCurrentProcess` at `0x10208a299`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1020894a9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x102089644`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x102089522`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1020896bd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1020894f7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10208954f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x102089692`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1020896ea`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10208a38c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10208a38c`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x102089828`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089937`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089a52`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089b16`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089bd3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089f57`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089937`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089a52`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089b16`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089bd3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x102089f57`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208946b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020895fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10208946b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1020895fd`
- `sqldk!SystemThread_TlsIndex` at `0x1020894c9`
- `sqldk!SystemThread_TlsIndex` at `0x102089664`
- `sqldk!SystemThread_TlsIndex` at `0x1020898d6`
- `sqldk!SystemThread_TlsIndex` at `0x1020899f4`
- `sqldk!SystemThread_TlsIndex` at `0x102089ab8`
- `sqldk!SystemThread_TlsIndex` at `0x102089b70`
- `sqldk!SystemThread_TlsIndex` at `0x102089c81`
- `sqldk!SystemThread_TlsIndex` at `0x102089cd3`
- `sqldk!SystemThread_TlsIndex` at `0x102089d4a`
- `sqldk!SystemThread_TlsIndex` at `0x102089efd`
- `sqldk!SystemThread_TlsIndex` at `0x10208a03f`
- `sqldk!SystemThread_TlsIndex` at `0x10208a090`
- `sqldk!SystemThread_TlsIndex` at `0x10208a105`
- `sqldk!SystemThread_TlsIndex` at `0x10208a354`
- `sqldk!SystemThread_TlsOffset` at `0x1020894d2`
- `sqldk!SystemThread_TlsOffset` at `0x10208966d`
- `sqldk!SystemThread_TlsOffset` at `0x1020898df`
- `sqldk!SystemThread_TlsOffset` at `0x1020899fd`
- `sqldk!SystemThread_TlsOffset` at `0x102089ac1`
- `sqldk!SystemThread_TlsOffset` at `0x102089b79`
- `sqldk!SystemThread_TlsOffset` at `0x102089c8a`
- `sqldk!SystemThread_TlsOffset` at `0x102089cdc`
- `sqldk!SystemThread_TlsOffset` at `0x102089d53`
- `sqldk!SystemThread_TlsOffset` at `0x102089f06`
- `sqldk!SystemThread_TlsOffset` at `0x10208a048`
- `sqldk!SystemThread_TlsOffset` at `0x10208a099`
- `sqldk!SystemThread_TlsOffset` at `0x10208a10e`
- `sqldk!SystemThread_TlsOffset` at `0x10208a35d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020898f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089a16`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089ada`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089b92`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089f1f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208a376`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1020898f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089a16`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089ada`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089b92`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x102089f1f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10208a376`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102089ca1`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102089d69`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x10208a05e`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x10208a124`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102089ca1`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x102089d69`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x10208a05e`
- `sqllang!?intnl_revert_to_self@@YAHPEAVCSession@@H@Z` at `0x10208a124`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall CBulkError::Init(
        CBulkError *this,
        const wchar_t *a2,
        unsigned __int64 a3,
        wchar_t *a4,
        unsigned __int64 a5,
        wchar_t *a6,
        unsigned __int64 a7,
        struct CImportStream *a8,
        unsigned int a9,
        DWORD a10,
        struct IGrantPageAllocator *a11)
{
  unsigned __int64 v11; // r15
  char *v13; // r12
  char *v14; // rdi
  bool *v15; // rcx
  volatile signed __int64 *v16; // r15
  unsigned __int8 *Pages; // rax
  DirtyPageMgr *QuadPart; // rdi
  signed __int64 UniqueThread_low; // r12
  __int64 v20; // rsi
  __int64 v21; // r8
  DirtyPageMgr *v22; // rax
  signed __int64 v23; // rax
  unsigned __int8 *v24; // rax
  DirtyPageMgr *v25; // rdi
  signed __int64 v26; // r13
  __int64 v27; // rsi
  __int64 v28; // r8
  char *v29; // rcx
  DirtyPageMgr *v30; // rax
  signed __int64 v31; // rax
  char *v32; // rcx
  __int64 v33; // rdx
  char *v34; // rcx
  unsigned int dwCreationDisposition; // r13d
  char v36; // al
  int v37; // ecx
  __int64 v38; // rdi
  __int64 v39; // rcx
  unsigned __int64 v40; // rsi
  unsigned __int64 v41; // rax
  wchar_t *v42; // rax
  wchar_t **v43; // r15
  __int64 v44; // rdi
  __int64 v45; // rcx
  unsigned __int64 v46; // rdi
  unsigned __int64 v47; // rax
  wchar_t *v48; // rax
  __int64 v49; // rdi
  __int64 v50; // rcx
  unsigned __int64 v51; // rax
  wchar_t *v52; // rax
  __int64 v53; // rdi
  __int64 v54; // rcx
  unsigned __int64 v55; // rax
  wchar_t *v56; // rax
  __int64 result; // rax
  DWORD LastError; // edi
  void *v59; // rcx
  unsigned int v60; // r15d
  unsigned int v61; // r13d
  wchar_t **v62; // rsi
  wchar_t *v63; // rsi
  CBulkError *v64; // rcx
  __int64 v65; // rax
  DWORD v66; // r8d
  wchar_t *v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rdi
  __int64 v70; // rcx
  unsigned __int64 v71; // rsi
  unsigned __int64 v72; // rax
  wchar_t *v73; // rax
  DWORD v74; // esi
  void *v75; // rcx
  wchar_t *v76; // rdi
  CBulkError *v77; // rcx
  __int64 v78; // rax
  _DWORD *v79; // rdi
  DWORD v80; // edx
  wchar_t *v81; // r8
  __int64 v82; // rcx
  HANDLE CurrentProcess; // rdi
  HANDLE v84; // rax
  DWORD v85; // r10d
  wchar_t *v86; // r8
  __int64 v87; // rcx
  int v88; // esi
  __int64 v89; // rdi
  struct Worker *v90; // rcx
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-250h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-248h]
  int v93; // [rsp+50h] [rbp-228h]
  int v94; // [rsp+50h] [rbp-228h]
  int v95; // [rsp+50h] [rbp-228h]
  int v96; // [rsp+50h] [rbp-228h]
  int v97; // [rsp+50h] [rbp-228h]
  int v98; // [rsp+50h] [rbp-228h]
  int v99; // [rsp+50h] [rbp-228h]
  _DWORD *v100; // [rsp+58h] [rbp-220h]
  int v101; // [rsp+60h] [rbp-218h] BYREF
  int v102; // [rsp+64h] [rbp-214h] BYREF
  UINT uMode[2]; // [rsp+68h] [rbp-210h]
  int v104; // [rsp+70h] [rbp-208h]
  unsigned __int8 **v105; // [rsp+78h] [rbp-200h]
  __int64 v106; // [rsp+80h] [rbp-1F8h]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-1F0h] BYREF
  LARGE_INTEGER v108; // [rsp+90h] [rbp-1E8h] BYREF
  LARGE_INTEGER v109; // [rsp+98h] [rbp-1E0h] BYREF
  LARGE_INTEGER v110; // [rsp+A0h] [rbp-1D8h] BYREF
  LARGE_INTEGER NewFilePointer; // [rsp+A8h] [rbp-1D0h] BYREF
  LARGE_INTEGER v112; // [rsp+B0h] [rbp-1C8h] BYREF
  char *v113; // [rsp+B8h] [rbp-1C0h] BYREF
  int v114; // [rsp+C0h] [rbp-1B8h]
  volatile signed __int64 *v115; // [rsp+D0h] [rbp-1A8h] BYREF
  int v116; // [rsp+D8h] [rbp-1A0h]
  __int64 v117; // [rsp+E0h] [rbp-198h]
  __int64 v118; // [rsp+E8h] [rbp-190h]
  wchar_t *v119; // [rsp+F0h] [rbp-188h]
  __int64 v120; // [rsp+F8h] [rbp-180h]
  unsigned __int64 v121; // [rsp+100h] [rbp-178h]
  __int64 v122; // [rsp+108h] [rbp-170h]
  __int64 v123; // [rsp+110h] [rbp-168h]
  __int64 v124; // [rsp+118h] [rbp-160h]
  unsigned __int64 v125; // [rsp+120h] [rbp-158h]
  wchar_t *v126; // [rsp+128h] [rbp-150h]
  _BYTE v127[64]; // [rsp+140h] [rbp-138h] BYREF
  _BYTE v128[96]; // [rsp+180h] [rbp-F8h] BYREF
  _BYTE v129[152]; // [rsp+1E0h] [rbp-98h] BYREF
  DWORD v133; // [rsp+2C8h] [rbp+50h]

  v117 = -2;
  v11 = a3;
  *((_QWORD *)this + 4) = a8;
  *((_QWORD *)this + 20) = a11;
  if ( a11 )
  {
    *((_DWORD *)this + 42) = 64;
    *((_DWORD *)this + 38) = 0x80000;
  }
  if ( a5 || a6 )
  {
    v13 = (char *)this + 136;
    v100 = (_DWORD *)((char *)this + 136);
    *((_DWORD *)this + 34) = 1;
    *((_DWORD *)this + 270) = a9;
    if ( a9 )
    {
      v14 = (char *)this + 480;
      v105 = (unsigned __int8 **)((char *)this + 480);
      v15 = (bool *)this + 600;
      *(_QWORD *)uMode = v15;
      v16 = (volatile signed __int64 *)((char *)this + 992);
      v106 = a9;
      v100 = v13;
      do
      {
        Pages = CBufferAllocatorHelper::AllocatePages(
                  *((struct IGrantPageAllocator **)this + 20),
                  *((int *)this + 42),
                  v15 + 472);
        *((_QWORD *)v14 + 59) = Pages;
        if ( !Pages )
        {
          _mm_lfence();
          LODWORD(hTemplateFile) = -2147024882;
          dwFlagsAndAttributes[0] = 1546;
          ex_raise(
            4,
            7,
            16,
            1,
            "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
            *(_QWORD *)dwFlagsAndAttributes,
            hTemplateFile);
        }
        v115 = v16;
        v116 = 0;
        QuadPart = 0;
        UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *(_DWORD *)v16 || _InterlockedCompareExchange64(v16, UniqueThread_low, 0) )
        {
          v20 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v21 && *(_QWORD *)(v21 + 272) == v21 )
              v20 = *(_QWORD *)(v21 + 256);
            if ( v20 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&PerformanceCount);
                QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
              }
              else
              {
                QuadPart = MEMORY[0x7FFE0008];
              }
            }
          }
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v16, UniqueThread_low);
          else
            Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v16, v20, UniqueThread_low);
          if ( v20 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v108);
              v22 = (DirtyPageMgr *)v108.QuadPart;
            }
            else
            {
              v22 = MEMORY[0x7FFE0008];
            }
            if ( v22 < QuadPart )
              v23 = 0;
            else
              v23 = v22 - QuadPart;
            *(_QWORD *)(v20 + 3192) += v23;
          }
        }
        v116 = 1;
        *((_DWORD *)v16 + 2) = 0;
        *((_QWORD *)v16 + 2) = 0;
        SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v115);
        v24 = CBufferAllocatorHelper::AllocatePages(
                *((struct IGrantPageAllocator **)this + 20),
                *((int *)this + 42),
                *(bool **)uMode);
        *v105 = v24;
        if ( !v24 )
        {
          _mm_lfence();
          LODWORD(hTemplateFile) = -2147024882;
          dwFlagsAndAttributes[0] = 1559;
          ex_raise(
            4,
            7,
            16,
            1,
            "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
            *(_QWORD *)dwFlagsAndAttributes,
            hTemplateFile);
        }
        v113 = (char *)(v16 - 59);
        v114 = 0;
        v25 = 0;
        v26 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
        if ( *((_DWORD *)v16 - 118) || _InterlockedCompareExchange64(v16 - 59, v26, 0) )
        {
          v27 = 0;
          if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
          {
            v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            if ( v28 && *(_QWORD *)(v28 + 272) == v28 )
              v27 = *(_QWORD *)(v28 + 256);
            if ( v27 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v109);
                v25 = (DirtyPageMgr *)v109.QuadPart;
              }
              else
              {
                v25 = MEMORY[0x7FFE0008];
              }
            }
          }
          v29 = (char *)(v16 - 59);
          if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
            Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(v29, v26);
          else
            Spinlock<25,1,268435714>::SpinToAcquireOptimistic(v29, v27, v26);
          if ( v27 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v110);
              v30 = (DirtyPageMgr *)v110.QuadPart;
            }
            else
            {
              v30 = MEMORY[0x7FFE0008];
            }
            if ( v30 < v25 )
              v31 = 0;
            else
              v31 = v30 - v25;
            *(_QWORD *)(v27 + 3192) += v31;
          }
        }
        v114 = 1;
        *((_DWORD *)v16 - 116) = 0;
        *((_QWORD *)v16 - 57) = 0;
        SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(&v113);
        v15 = (bool *)++*(_QWORD *)uMode;
        v14 = (char *)++v105;
        v16 += 6;
        --v106;
      }
      while ( v106 );
      v11 = a3;
    }
    v32 = (char *)this + 8 * *((unsigned int *)this + 269);
    *((_QWORD *)this + 136) = *((_QWORD *)v32 + 119);
    v33 = *((int *)this + 38);
    *((_QWORD *)this + 137) = v33 + *((_QWORD *)v32 + 119);
    v34 = (char *)this + 8 * *((unsigned int *)this + 151);
    *((_QWORD *)this + 77) = *((_QWORD *)v34 + 60);
    *((_QWORD *)this + 78) = v33 + *((_QWORD *)v34 + 60);
  }
  else
  {
    v100 = (_DWORD *)((char *)this + 136);
    *((_DWORD *)this + 34) = 0;
  }
  uMode[0] = SetErrorMode(1u);
  dwCreationDisposition = 4;
  if ( !a10 )
    dwCreationDisposition = 1;
  v133 = dwCreationDisposition;
  ExcHandler::ExcHandler((ExcHandler *)v127, 0, 0, 0, hdl_prntbackout, 0);
  if ( !a2 || !v11 )
    goto LABEL_175;
  if ( IsDWCopyStatementEnabled() )
    goto LABEL_70;
  if ( !dword_103172528 )
  {
    v104 = 0;
    v36 = byte_1031852E4;
    goto LABEL_79;
  }
  if ( !byte_1031852E9 && !byte_1031852E8 )
  {
    v36 = byte_1031852E4;
LABEL_67:
    v37 = 0;
    goto LABEL_68;
  }
  v36 = byte_1031852E4;
  v37 = 1;
  if ( byte_1031852E4 )
    goto LABEL_67;
LABEL_68:
  v104 = v37;
  if ( v37 && byte_10316EA87 )
    goto LABEL_70;
LABEL_79:
  if ( v36 && byte_10316EA86 )
  {
LABEL_70:
    _mm_lfence();
    v125 = v11 + 9;
    v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v39 = *(_QWORD *)(v38 + 256);
    if ( !v39 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v39 = *(_QWORD *)(v38 + 256);
    }
    v40 = v11 + 10;
    v41 = 2 * (v11 + 10);
    if ( !is_mul_ok(v11 + 10, 2u) )
      v41 = -1;
    v42 = (wchar_t *)operator new[](
                       v41,
                       *(struct IMemObj **)(v39 + 1000),
                       "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
                       1607,
                       5u);
    v43 = (wchar_t **)((char *)this + 104);
    *((_QWORD *)this + 13) = v42;
    v93 = StringCchCopyNW(v42, v40, a2, a3);
    if ( v93 < 0 )
    {
      _mm_lfence();
      StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1610, v93);
    }
    v94 = StringCchCatNW(*v43, v40, L".Row.Txt", 0x12u);
    if ( v94 < 0 )
    {
      _mm_lfence();
      StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1615, v94);
    }
    goto LABEL_87;
  }
  _mm_lfence();
  v44 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v45 = *(_QWORD *)(v44 + 256);
  if ( !v45 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v45 = *(_QWORD *)(v44 + 256);
  }
  v46 = v11 + 1;
  v47 = 2 * (v11 + 1);
  if ( !is_mul_ok(v11 + 1, 2u) )
    v47 = -1;
  v48 = (wchar_t *)operator new[](
                     v47,
                     *(struct IMemObj **)(v45 + 1000),
                     "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
                     1619,
                     5u);
  v43 = (wchar_t **)((char *)this + 104);
  *((_QWORD *)this + 13) = v48;
  v95 = StringCchCopyNW(v48, v46, a2, a3);
  if ( v95 < 0 )
  {
    _mm_lfence();
    StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1624, v95);
  }
LABEL_87:
  if ( a5 )
  {
    v49 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v50 = *(_QWORD *)(v49 + 256);
    if ( !v50 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v50 = *(_QWORD *)(v49 + 256);
    }
    v51 = 2 * (a5 + 1);
    if ( !is_mul_ok(a5 + 1, 2u) )
      v51 = -1;
    v52 = (wchar_t *)operator new[](
                       v51,
                       *(struct IMemObj **)(v50 + 1000),
                       "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
                       1629,
                       5u);
    *((_QWORD *)this + 15) = v52;
    v96 = StringCchCopyNW(v52, a5 + 1, a4, a5);
    if ( v96 < 0 )
    {
      _mm_lfence();
      StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1634, v96);
    }
  }
  if ( a6 )
  {
    v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v54 = *(_QWORD *)(v53 + 256);
    if ( !v54 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v54 = *(_QWORD *)(v53 + 256);
    }
    v55 = 2 * (a7 + 1);
    if ( !is_mul_ok(a7 + 1, 2u) )
      v55 = -1;
    v56 = (wchar_t *)operator new[](
                       v55,
                       *(struct IMemObj **)(v54 + 1000),
                       "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
                       1640,
                       5u);
    *((_QWORD *)this + 12) = v56;
    v97 = StringCchCopyNW(v56, a7 + 1, a6, a7);
    if ( v97 < 0 )
    {
      _mm_lfence();
      StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1645, v97);
    }
  }
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(v128, 536871477, 1);
  AutoImpersonateClient::AutoImpersonateClient((AutoImpersonateClient *)&v101);
  if ( *v100 )
  {
    if ( !(unsigned int)CreateAzureFileWrite(
                          *v43,
                          *((wchar_t **)this + 15),
                          *((wchar_t **)this + 12),
                          *((struct CImpImportProvider **)this + 5),
                          dwCreationDisposition,
                          (void **)this + 1) )
    {
      if ( v101 )
        intnl_revert_to_self(
          *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL),
          1);
      SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v128);
      ExcHandler::~ExcHandler((ExcHandler *)v127);
      return 0;
    }
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset)
                                  + 72LL)
                      + 270LL)
           & 4) == 0 )
  {
    *((_QWORD *)this + 1) = CreateFileW(*v43, 0x40000000u, 1u, 0, dwCreationDisposition, 0x100000u, 0);
  }
  _mm_lfence();
  LastError = GetLastError();
  if ( v101 )
    intnl_revert_to_self(
      *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset)
                          + 72LL),
      1);
  SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v128);
  v59 = (void *)*((_QWORD *)this + 1);
  if ( v59 == (void *)-1LL )
  {
    if ( LastError == 2 )
    {
      v61 = 60;
      v62 = v43;
      v60 = 61;
    }
    else
    {
      v60 = 61;
      if ( LastError == 53 )
      {
        v61 = 4;
        v62 = (wchar_t **)((char *)this + 120);
      }
      else if ( LastError == 87 )
      {
        v61 = 3;
        v62 = (wchar_t **)((char *)this + 120);
      }
      else
      {
        v61 = 61;
        v62 = (wchar_t **)((char *)this + 104);
      }
    }
    v63 = *v62;
    v126 = v63;
    EmitXeventFileCreationFailed(*((const wchar_t **)this + 13), LastError);
    if ( v63 )
    {
      v65 = -1;
      do
        ++v65;
      while ( v63[v65] );
      v118 = v65;
    }
    else
    {
      LODWORD(v65) = 0;
    }
    CBulkError::PrintError(v64, v61, LastError, 0, 0, 0, (unsigned int)v65, v63, 0, 0);
    dwCreationDisposition = v133;
  }
  else
  {
    if ( !*v100 )
    {
      if ( SetFilePointerEx(v59, 0, &NewFilePointer, 2u) )
      {
        *(LARGE_INTEGER *)this = NewFilePointer;
      }
      else
      {
        v66 = GetLastError();
        v67 = *v43;
        v119 = *v43;
        v68 = -1;
        do
          ++v68;
        while ( v67[v68] );
        v120 = v68;
        CBulkError::PrintError((CBulkError *)v68, 0x46u, v66, 0, 0, 0, (unsigned int)v68, v67, 0, 0);
        CloseHandle(*((HANDLE *)this + 1));
        *((_QWORD *)this + 1) = -1;
      }
    }
    v60 = 61;
  }
  v121 = a3 + 11;
  v69 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v70 = *(_QWORD *)(v69 + 256);
  if ( !v70 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v70 = *(_QWORD *)(v69 + 256);
  }
  v71 = a3 + 12;
  v72 = 2 * (a3 + 12);
  if ( !is_mul_ok(a3 + 12, 2u) )
    v72 = -1;
  v73 = (wchar_t *)operator new[](
                     v72,
                     *(struct IMemObj **)(v70 + 1000),
                     "sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp",
                     1755,
                     5u);
  *((_QWORD *)this + 14) = v73;
  v98 = StringCchCopyNW(v73, v71, a2, a3);
  if ( v98 < 0 )
  {
    _mm_lfence();
    StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1759, v98);
  }
  v99 = StringCchCatW(*((wchar_t **)this + 14), v71, L".Error.Txt");
  if ( v99 < 0 )
  {
    _mm_lfence();
    StringFailureError("sql\\ntdbms\\storeng\\dmu\\impprov\\src\\imperr.cpp", 1763, v99);
  }
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(v129, 536871477, 1);
  AutoImpersonateClient::AutoImpersonateClient((AutoImpersonateClient *)&v102);
  if ( *v100 )
  {
    if ( !(unsigned int)CreateAzureFileWrite(
                          *((wchar_t **)this + 14),
                          *((wchar_t **)this + 15),
                          *((wchar_t **)this + 12),
                          *((struct CImpImportProvider **)this + 5),
                          dwCreationDisposition,
                          (void **)this + 3) )
    {
      if ( v102 )
        intnl_revert_to_self(
          *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL),
          1);
      SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v129);
      ExcHandler::~ExcHandler((ExcHandler *)v127);
      return 0;
    }
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                + SystemThread_TlsIndex)
                                              + SystemThread_TlsOffset)
                                  + 72LL)
                      + 270LL)
           & 4) == 0 )
  {
    *((_QWORD *)this + 3) = CreateFileW(
                              *((LPCWSTR *)this + 14),
                              0x40000000u,
                              1u,
                              0,
                              dwCreationDisposition,
                              0x100000u,
                              0);
  }
  v74 = GetLastError();
  if ( v102 )
    intnl_revert_to_self(
      *(struct CSession **)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset)
                          + 72LL),
      1);
  SOS_Task::AutoSwitchPreemptive::~AutoSwitchPreemptive((SOS_Task::AutoSwitchPreemptive *)v129);
  v75 = (void *)*((_QWORD *)this + 3);
  if ( v75 == (void *)-1LL )
  {
    switch ( v74 )
    {
      case 2u:
        v60 = 60;
        break;
      case 0x35u:
        v60 = 4;
        v76 = (wchar_t *)*((_QWORD *)this + 15);
        goto LABEL_156;
      case 0x57u:
        v60 = 3;
        v76 = (wchar_t *)*((_QWORD *)this + 15);
LABEL_156:
        EmitXeventFileCreationFailed(*((const wchar_t **)this + 14), v74);
        if ( v76 )
        {
          v78 = -1;
          do
            ++v78;
          while ( v76[v78] );
          v122 = v78;
        }
        else
        {
          LODWORD(v78) = 0;
        }
        CBulkError::PrintError(v77, v60, v74, 0, 0, 0, (unsigned int)v78, v76, 0, 0);
        CloseHandle(*((HANDLE *)this + 3));
        v79 = v100;
        goto LABEL_168;
    }
    v76 = (wchar_t *)*((_QWORD *)this + 14);
    goto LABEL_156;
  }
  v79 = v100;
  if ( *v100 )
    goto LABEL_170;
  if ( SetFilePointerEx(v75, 0, &v112, 2u) )
  {
    *((LARGE_INTEGER *)this + 138) = v112;
    goto LABEL_169;
  }
  v80 = GetLastError();
  v81 = (wchar_t *)*((_QWORD *)this + 14);
  v82 = -1;
  do
    ++v82;
  while ( v81[v82] );
  v123 = v82;
  CBulkError::PrintError((CBulkError *)v82, 0x46u, v80, 0, 0, 0, (unsigned int)v82, v81, 0, 0);
  CloseHandle(*((HANDLE *)this + 3));
LABEL_168:
  *((_QWORD *)this + 3) = -1;
LABEL_169:
  if ( !*v79 )
  {
    CurrentProcess = GetCurrentProcess();
    v84 = GetCurrentProcess();
    if ( !DuplicateHandle(v84, *((HANDLE *)this + 1), CurrentProcess, (LPHANDLE)this + 2, 0, 1, 2u) )
    {
      v85 = GetLastError();
      v86 = (wchar_t *)*((_QWORD *)this + 13);
      v87 = -1;
      do
        ++v87;
      while ( v86[v87] );
      v124 = v87;
      CBulkError::PrintError((CBulkError *)v87, (v85 != 2) + 60, v85, 0, 0, 0, (unsigned int)v87, v86, 0, 0);
      *((_QWORD *)this + 2) = -1;
    }
    goto LABEL_175;
  }
LABEL_170:
  *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
LABEL_175:
  ExcHandler::~ExcHandler((ExcHandler *)v127);
  v88 = 1;
  v89 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v90 = *(struct Worker **)(v89 + 256);
  if ( !v90 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v90 = *(struct Worker **)(v89 + 256);
  }
  if ( *((_DWORD *)v90 + 139) )
    ExceptionPostCatchActions(v90);
  SetErrorMode(uMode[0]);
  if ( *((_QWORD *)this + 1) == -1 || *((_QWORD *)this + 3) == -1 || *((_QWORD *)this + 2) == -1 )
    v88 = 0;
  *((_DWORD *)this + 35) = v88;
  result = 2147500037LL;
  if ( v88 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x102089310  mov     [rsp+arg_18], r9
0x102089315  mov     [rsp+arg_10], r8
0x10208931a  mov     [rsp+arg_8], rdx
0x10208931f  mov     [rsp+arg_0], rcx
0x102089324  push    rbx
0x102089325  push    rsi
0x102089326  push    rdi
0x102089327  push    r12
0x102089329  push    r13
0x10208932b  push    r14
0x10208932d  push    r15
0x10208932f  sub     rsp, 240h
0x102089336  mov     [rsp+278h+var_198], 0FFFFFFFFFFFFFFFEh
0x102089342  mov     r15, r8
0x102089345  mov     r14, rcx
0x102089348  mov     rax, [rsp+278h+arg_38]
0x102089350  mov     [rcx+20h], rax
0x102089354  mov     rax, [rsp+278h+arg_50]
0x10208935c  mov     [rcx+0A0h], rax
0x102089363  test    rax, rax
0x102089366  jz      short loc_10208937C
0x102089368  mov     dword ptr [rcx+0A8h], 40h ; '@'
0x102089372  mov     dword ptr [rcx+98h], 80000h
0x10208937c  cmp     [rsp+278h+arg_20], 0
0x102089385  jnz     short loc_1020893B4
0x102089387  cmp     [rsp+278h+arg_28], 0
0x102089390  jnz     short loc_1020893B4
0x102089392  lea     r12, [rcx+88h]
0x102089399  mov     [rsp+278h+var_220], r12
0x10208939e  xor     ebx, ebx
0x1020893a0  mov     [r12], ebx
0x1020893a4  lea     r13d, [rbx+1]
0x1020893a8  lea     rsi, aSqlNtdbmsStore_258; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020893af  jmp     loc_1020897F5
0x1020893b4  lea     r12, [rcx+88h]
0x1020893bb  mov     [rsp+278h+var_220], r12
0x1020893c0  mov     r13d, 1
0x1020893c6  mov     [r12], r13d
0x1020893ca  mov     eax, [rsp+278h+arg_40]
0x1020893d1  mov     [rcx+438h], eax
0x1020893d7  lea     rsi, aSqlNtdbmsStore_258; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x1020893de  test    eax, eax
0x1020893e0  jz      loc_102089798
0x1020893e6  lea     rdi, [rcx+1E0h]
0x1020893ed  mov     [rsp+278h+var_200], rdi
0x1020893f2  add     rcx, 258h
0x1020893f9  mov     qword ptr [rsp+278h+uMode], rcx
0x1020893fe  lea     r15, [r14+3E0h]
0x102089405  mov     [rsp+278h+var_1F8], rax
0x10208940d  mov     [rsp+278h+var_220], r12
0x102089412  xor     ebx, ebx
0x102089414  nop     dword ptr [rax+00h]
0x102089418  nop     dword ptr [rax+rax+00000000h]
0x102089420  lea     r8, [rcx+1D8h]; bool *
0x102089427  movsxd  rdx, dword ptr [r14+0A8h]; __int64
0x10208942e  mov     rcx, [r14+0A0h]; struct IGrantPageAllocator *
0x102089435  call    ?AllocatePages@CBufferAllocatorHelper@@SAPEAEPEAVIGrantPageAllocator@@_JAEA_N@Z; CBufferAllocatorHelper::AllocatePages(IGrantPageAllocator *,__int64,bool &)
0x10208943a  mov     [rdi+1D8h], rax
0x102089441  test    rax, rax
0x102089444  jnz     short loc_102089471
0x102089446  lfence
0x102089449  mov     dword ptr [rsp+278h+hTemplateFile], 8007000Eh
0x102089451  mov     [rsp+278h+dwFlagsAndAttributes], 60Ah
0x102089459  mov     qword ptr [rsp+278h+dwCreationDisposition], rsi
0x10208945e  mov     r9d, r13d
0x102089461  lea     edx, [rax+7]
0x102089464  lea     ecx, [rax+4]
0x102089467  lea     r8d, [rax+10h]
0x10208946b  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x102089471  mov     [rsp+278h+var_1A8], r15
0x102089479  mov     [rsp+278h+var_1A0], ebx
0x102089480  mov     rdi, rbx
0x102089483  mov     eax, gs:48h
0x10208948b  mov     r12d, eax
0x10208948e  mov     eax, [r15]
0x102089491  test    eax, eax
0x102089493  jnz     short loc_1020894A9
0x102089495  xor     eax, eax
0x102089497  lock cmpxchg [r15], r12
0x10208949c  mov     eax, ebx
0x10208949e  setz    al
0x1020894a1  test    eax, eax
0x1020894a3  jnz     loc_102089596
0x1020894a9  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1020894b0  mov     ecx, [rax]
0x1020894b2  and     ecx, 84h
0x1020894b8  mov     rsi, rbx
0x1020894bb  cmp     cl, 84h
0x1020894be  jnz     short loc_102089522
0x1020894c0  mov     rdx, gs:58h
0x1020894c9  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1020894d0  mov     ecx, [rax]
0x1020894d2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1020894d9  mov     r8d, [rax]
0x1020894dc  add     r8, [rdx+rcx*8]
0x1020894e0  jz      short loc_1020894F2
0x1020894e2  cmp     [r8+110h], r8
0x1020894e9  jnz     short loc_1020894F2
0x1020894eb  mov     rsi, [r8+100h]
0x1020894f2  test    rsi, rsi
0x1020894f5  jz      short loc_102089522
0x1020894f7  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1020894fe  cmp     [rax], edi
0x102089500  jz      short loc_10208951A
0x102089502  lea     rcx, [rsp+278h+PerformanceCount]; lpPerformanceCount
0x10208950a  call    cs:__imp_QueryPerformanceCounter
0x102089510  mov     rdi, qword ptr [rsp+278h+PerformanceCount]
0x102089518  jmp     short loc_102089522
0x10208951a  mov     rdi, ds:7FFE0008h
0x102089522  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x102089529  mov     rcx, r15
0x10208952c  cmp     byte ptr [rax+0C7h], 0
0x102089533  jge     short loc_102089542
0x102089535  mov     r8, r12
0x102089538  mov     rdx, rsi
0x10208953b  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x102089540  jmp     short loc_10208954A
0x102089542  mov     rdx, r12
0x102089545  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10208954a  test    rsi, rsi
0x10208954d  jz      short loc_10208958F
0x10208954f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x102089556  cmp     dword ptr [rax], 0
0x102089559  jz      short loc_102089573
0x10208955b  lea     rcx, [rsp+278h+var_1E8]; lpPerformanceCount
0x102089563  call    cs:__imp_QueryPerformanceCounter
0x102089569  mov     rax, qword ptr [rsp+278h+var_1E8]
0x102089571  jmp     short loc_10208957B
0x102089573  mov     rax, ds:7FFE0008h
0x10208957b  cmp     rax, rdi
0x10208957e  jb      short loc_102089585
0x102089580  sub     rax, rdi
0x102089583  jmp     short loc_102089588
0x102089585  mov     rax, rbx
0x102089588  add     [rsi+0C78h], rax
0x10208958f  lea     rsi, aSqlNtdbmsStore_258; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x102089596  mov     [rsp+278h+var_1A0], r13d
0x10208959e  mov     [r15+8], ebx
0x1020895a2  mov     [r15+10h], rbx
0x1020895a6  lea     rcx, [rsp+278h+var_1A8]
0x1020895ae  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x1020895b3  movsxd  rdx, dword ptr [r14+0A8h]; __int64
0x1020895ba  mov     r8, qword ptr [rsp+278h+uMode]; bool *
0x1020895bf  mov     rcx, [r14+0A0h]; struct IGrantPageAllocator *
0x1020895c6  call    ?AllocatePages@CBufferAllocatorHelper@@SAPEAEPEAVIGrantPageAllocator@@_JAEA_N@Z; CBufferAllocatorHelper::AllocatePages(IGrantPageAllocator *,__int64,bool &)
0x1020895cb  mov     rcx, [rsp+278h+var_200]
0x1020895d0  mov     [rcx], rax
0x1020895d3  test    rax, rax
0x1020895d6  jnz     short loc_102089603
0x1020895d8  lfence
0x1020895db  mov     dword ptr [rsp+278h+hTemplateFile], 8007000Eh
0x1020895e3  mov     [rsp+278h+dwFlagsAndAttributes], 617h
0x1020895eb  mov     qword ptr [rsp+278h+dwCreationDisposition], rsi
0x1020895f0  mov     r9d, r13d
0x1020895f3  lea     edx, [rax+7]
0x1020895f6  lea     ecx, [rax+4]
0x1020895f9  lea     r8d, [rax+10h]
0x1020895fd  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x102089603  lea     r12, [r15-1D8h]
0x10208960a  mov     [rsp+278h+var_1C0], r12
0x102089612  mov     [rsp+278h+var_1B8], ebx
0x102089619  mov     rdi, rbx
0x10208961c  mov     eax, gs:48h
0x102089624  mov     r13d, eax
0x102089627  mov     eax, [r12]
0x10208962b  test    eax, eax
0x10208962d  jnz     short loc_102089644
0x10208962f  xor     eax, eax
0x102089631  lock cmpxchg [r12], r13
0x102089637  mov     eax, ebx
0x102089639  setz    al
0x10208963c  test    eax, eax
0x10208963e  jnz     loc_10208972A
0x102089644  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10208964b  mov     ecx, [rax]
0x10208964d  and     ecx, 84h
0x102089653  mov     rsi, rbx
0x102089656  cmp     cl, 84h
0x102089659  jnz     short loc_1020896BD
0x10208965b  mov     rdx, gs:58h
0x102089664  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10208966b  mov     ecx, [rax]
0x10208966d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x102089674  mov     r8d, [rax]
0x102089677  add     r8, [rdx+rcx*8]
0x10208967b  jz      short loc_10208968D
0x10208967d  cmp     [r8+110h], r8
0x102089684  jnz     short loc_10208968D
0x102089686  mov     rsi, [r8+100h]
0x10208968d  test    rsi, rsi
0x102089690  jz      short loc_1020896BD
0x102089692  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x102089699  cmp     [rax], edi
0x10208969b  jz      short loc_1020896B5
0x10208969d  lea     rcx, [rsp+278h+var_1E0]; lpPerformanceCount
0x1020896a5  call    cs:__imp_QueryPerformanceCounter
0x1020896ab  mov     rdi, qword ptr [rsp+278h+var_1E0]
0x1020896b3  jmp     short loc_1020896BD
0x1020896b5  mov     rdi, ds:7FFE0008h
0x1020896bd  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x1020896c4  mov     rcx, r12
0x1020896c7  cmp     byte ptr [rax+0C7h], 0
0x1020896ce  jge     short loc_1020896DD
0x1020896d0  mov     r8, r13
0x1020896d3  mov     rdx, rsi
0x1020896d6  call    ?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1020896db  jmp     short loc_1020896E5
0x1020896dd  mov     rdx, r13
0x1020896e0  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z; Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1020896e5  test    rsi, rsi
0x1020896e8  jz      short loc_10208972A
0x1020896ea  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1020896f1  cmp     dword ptr [rax], 0
0x1020896f4  jz      short loc_10208970E
0x1020896f6  lea     rcx, [rsp+278h+var_1D8]; lpPerformanceCount
0x1020896fe  call    cs:__imp_QueryPerformanceCounter
0x102089704  mov     rax, qword ptr [rsp+278h+var_1D8]
0x10208970c  jmp     short loc_102089716
0x10208970e  mov     rax, ds:7FFE0008h
0x102089716  cmp     rax, rdi
0x102089719  jb      short loc_102089720
0x10208971b  sub     rax, rdi
0x10208971e  jmp     short loc_102089723
0x102089720  mov     rax, rbx
0x102089723  add     [rsi+0C78h], rax
0x10208972a  mov     r13d, 1
0x102089730  mov     [rsp+278h+var_1B8], r13d
0x102089738  mov     [r15-1D0h], ebx
0x10208973f  mov     [r15-1C8h], rbx
0x102089746  lea     rcx, [rsp+278h+var_1C0]
0x10208974e  call    ??1?$SpinlockHolder@$0BJ@$00$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<25,1,268435714>::~SpinlockHolder<25,1,268435714>(void)
0x102089753  mov     rcx, qword ptr [rsp+278h+uMode]
0x102089758  inc     rcx
0x10208975b  mov     qword ptr [rsp+278h+uMode], rcx
0x102089760  mov     rdi, [rsp+278h+var_200]
0x102089765  add     rdi, 8
0x102089769  mov     [rsp+278h+var_200], rdi
0x10208976e  add     r15, 30h ; '0'
0x102089772  sub     [rsp+278h+var_1F8], r13
0x10208977a  lea     rsi, aSqlNtdbmsStore_258; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x102089781  jnz     loc_102089420
0x102089787  lea     rsi, aSqlNtdbmsStore_258; "sql\\ntdbms\\storeng\\dmu\\impprov\\src"...
0x10208978e  mov     r15, [rsp+278h+arg_10]
0x102089796  jmp     short loc_10208979A
0x102089798  xor     ebx, ebx
0x10208979a  mov     eax, [r14+434h]
0x1020897a1  lea     rcx, [r14+rax*8]
0x1020897a5  mov     rax, [rcx+3B8h]
0x1020897ac  mov     [r14+440h], rax
0x1020897b3  movsxd  rdx, dword ptr [r14+98h]
0x1020897ba  mov     rcx, [rcx+3B8h]
0x1020897c1  add     rcx, rdx
0x1020897c4  mov     [r14+448h], rcx
0x1020897cb  mov     eax, [r14+25Ch]
0x1020897d2  lea     rcx, [r14+rax*8]
0x1020897d6  mov     rax, [rcx+1E0h]
0x1020897dd  mov     [r14+268h], rax
0x1020897e4  mov     rcx, [rcx+1E0h]
0x1020897eb  add     rcx, rdx
0x1020897ee  mov     [r14+270h], rcx
0x1020897f5  mov     ecx, r13d; uMode
0x1020897f8  call    cs:__imp_SetErrorMode
0x1020897fe  mov     [rsp+278h+uMode], eax
0x102089802  mov     r13d, 4
0x102089808  cmp     [rsp+278h+arg_48], 0
0x102089810  mov     edi, 1
0x102089815  cmovz   r13d, edi
0x102089819  mov     [rsp+278h+arg_48], r13d
0x102089821  xor     edx, edx; unsigned __int16
0x102089823  mov     qword ptr [rsp+278h+dwFlagsAndAttributes], rbx; struct Worker *
0x102089828  mov     rcx, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10208982f  mov     qword ptr [rsp+278h+dwCreationDisposition], rcx; int (*)(int, int, int, int, char *)
0x102089834  xor     r9d, r9d; unsigned __int8
0x102089837  xor     r8d, r8d; unsigned __int8
0x10208983a  lea     rcx, [rsp+278h+var_138]; this
0x102089842  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x102089847  nop
0x102089848  cmp     [rsp+278h+arg_8], 0
0x102089851  jz      loc_10208A32C
0x102089857  test    r15, r15
0x10208985a  jz      loc_10208A32C
0x102089860  call    ?IsDWCopyStatementEnabled@@YA_NXZ; IsDWCopyStatementEnabled(void)
0x102089865  test    al, al
0x102089867  jnz     short loc_1020898BE
0x102089869  cmp     cs:dword_103172528, 0
0x102089870  jz      loc_1020899C5
0x102089876  cmp     cs:byte_1031852E9, al
0x10208987c  jnz     short loc_10208988F
0x10208987e  cmp     cs:byte_1031852E8, al
0x102089884  jnz     short loc_10208988F
0x102089886  movzx   eax, cs:byte_1031852E4
0x10208988d  jmp     short loc_1020898A3
0x10208988f  movzx   eax, cs:byte_1031852E4
0x102089896  mov     byte ptr [rsp+278h+arg_38], al
0x10208989d  test    al, al
0x10208989f  mov     ecx, edi
0x1020898a1  jz      short loc_1020898A5
0x1020898a3  mov     ecx, ebx
0x1020898a5  mov     [rsp+278h+var_208], ecx
0x1020898a9  test    ecx, ecx
  ... truncated ...
```
