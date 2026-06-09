# CCacheContainer::AddUrl(ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,_FILETIME,_FILETIME,_FILETIME,uchar const *,ulong,uchar const *,ulong,ulong,ushort * *,int)

- ea: `0x18007c810`
- end: `0x18007e53d`
- name: `?AddUrl@CCacheContainer@@QEAAJKKPEBG000U_FILETIME@@11PEBEK2KKPEAPEAGH@Z`
- size: `7469`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, struct _FILETIME, struct _FILETIME, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `41`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180086d80`
- `0x180115e60`
- `0x1801aa40c`

## callees

- `0x180020fc4`
- `0x180023590`
- `0x1800701d0`
- `0x18007c810`
- `0x18007e620`
- `0x18007ec9c`
- `0x180082700`
- `0x180083540`
- `0x180083dc4`
- `0x180085414`
- `0x180085460`
- `0x180085898`
- `0x180085988`
- `0x180085a44`
- `0x1800867cc`
- `0x180086aa4`
- `0x1800b4a7c`
- `0x1800b5bdc`
- `0x1800b6bac`
- `0x1800d6ea4`
- `0x1800ec97c`
- `0x1800f125c`
- `0x1800fc68c`
- `0x1800ffb10`
- `0x18011a46c`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801ab060`
- `0x1801e0b60`
- `0x1801e0ff0`
- `0x1801e1790`
- `0x1801e17f0`
- `0x1801e1b00`
- `0x1801e1b60`
- `0x1801e1c40`
- `0x1801e2f9c`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e4c70`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e08d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e08d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007e0e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007e0e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007da6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007daf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007df14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007da6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007daf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007df14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cf7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007da79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dabc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dc25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dedb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cf7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007da79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dabc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dc25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dedb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007dfcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007dfcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007da61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007da61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007cbf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007cbf4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007df8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007df8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007dbcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007dbcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ca2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ca2b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e388`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e388`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007de38`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007e402`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007de38`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007e402`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e3b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e3b9`
- `ESENT!JetSetCurrentIndex2W` at `0x18007e049`
- `ESENT!JetSetCurrentIndex2W` at `0x18007e049`
- `ESENT!JetSetColumn` at `0x18007ce30`
- `ESENT!JetSetColumn` at `0x18007ce9e`
- `ESENT!JetSetColumn` at `0x18007d021`
- `ESENT!JetSetColumn` at `0x18007d05e`
- `ESENT!JetSetColumn` at `0x18007d0eb`
- `ESENT!JetSetColumn` at `0x18007d1ab`
- `ESENT!JetSetColumn` at `0x18007d219`
- `ESENT!JetSetColumn` at `0x18007d256`
- `ESENT!JetSetColumn` at `0x18007d2d4`
- `ESENT!JetSetColumn` at `0x18007d37e`
- `ESENT!JetSetColumn` at `0x18007d40e`
- `ESENT!JetSetColumn` at `0x18007d479`
- `ESENT!JetSetColumn` at `0x18007d4b6`
- `ESENT!JetSetColumn` at `0x18007d4f3`
- `ESENT!JetSetColumn` at `0x18007d530`
- `ESENT!JetSetColumn` at `0x18007d56d`
- `ESENT!JetSetColumn` at `0x18007d5aa`
- `ESENT!JetSetColumn` at `0x18007d5e7`
- `ESENT!JetSetColumn` at `0x18007d624`
- `ESENT!JetSetColumn` at `0x18007d661`
- `ESENT!JetSetColumn` at `0x18007d69e`
- `ESENT!JetSetColumn` at `0x18007d6db`
- `ESENT!JetSetColumn` at `0x18007d75c`
- `ESENT!JetSetColumn` at `0x18007d7f4`
- `ESENT!JetSetColumn` at `0x18007ce30`
- `ESENT!JetSetColumn` at `0x18007ce9e`
- `ESENT!JetSetColumn` at `0x18007d021`
- `ESENT!JetSetColumn` at `0x18007d05e`
- `ESENT!JetSetColumn` at `0x18007d0eb`
- `ESENT!JetSetColumn` at `0x18007d1ab`
- `ESENT!JetSetColumn` at `0x18007d219`
- `ESENT!JetSetColumn` at `0x18007d256`
- `ESENT!JetSetColumn` at `0x18007d2d4`
- `ESENT!JetSetColumn` at `0x18007d37e`
- `ESENT!JetSetColumn` at `0x18007d40e`
- `ESENT!JetSetColumn` at `0x18007d479`
- `ESENT!JetSetColumn` at `0x18007d4b6`
- `ESENT!JetSetColumn` at `0x18007d4f3`
- `ESENT!JetSetColumn` at `0x18007d530`
- `ESENT!JetSetColumn` at `0x18007d56d`
- `ESENT!JetSetColumn` at `0x18007d5aa`
- `ESENT!JetSetColumn` at `0x18007d5e7`
- `ESENT!JetSetColumn` at `0x18007d624`
- `ESENT!JetSetColumn` at `0x18007d661`
- `ESENT!JetSetColumn` at `0x18007d69e`
- `ESENT!JetSetColumn` at `0x18007d6db`
- `ESENT!JetSetColumn` at `0x18007d75c`
- `ESENT!JetSetColumn` at `0x18007d7f4`
- `ESENT!JetCommitTransaction` at `0x18007d86a`
- `ESENT!JetCommitTransaction` at `0x18007d86a`
- `ESENT!JetUpdate` at `0x18007d847`
- `ESENT!JetUpdate` at `0x18007d847`
- `ESENT!JetPrepareUpdate` at `0x18007cd91`
- `ESENT!JetPrepareUpdate` at `0x18007e521`
- `ESENT!JetPrepareUpdate` at `0x18007cd91`
- `ESENT!JetPrepareUpdate` at `0x18007e521`
- `ESENT!JetRollback` at `0x18007e532`
- `ESENT!JetRollback` at `0x18007e532`
- `ESENT!JetBeginTransaction` at `0x18007cd20`
- `ESENT!JetBeginTransaction` at `0x18007cd20`

## pseudocode

```c
__int64 __fastcall CCacheContainer::AddUrl(
        CContainerProps **this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        struct _FILETIME a8,
        FILETIME a9,
        struct _FILETIME a10,
        unsigned __int8 *a11,
        unsigned int a12,
        unsigned __int8 *a13,
        unsigned int a14,
        unsigned int a15,
        unsigned __int16 **a16,
        int a17)
{
  char v17; // r12
  char v18; // r15
  volatile signed __int32 *v19; // r14
  int v20; // edx
  __int64 *j; // rcx
  int v22; // r8d
  WCHAR *v23; // rsi
  const unsigned __int16 *v24; // rbx
  CCacheContainer *v25; // r12
  int v26; // r15d
  bool v27; // zf
  int updated; // edi
  __int64 v29; // rdx
  unsigned __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // r13
  int v33; // r12d
  __int64 v34; // rbx
  char *v35; // r15
  struct _RTL_CRITICAL_SECTION *v36; // r13
  volatile signed __int32 *Ptr; // rax
  __int64 v38; // rdi
  __int64 *i; // rsi
  int v40; // eax
  int v41; // r12d
  _OWORD *v42; // rax
  _OWORD *v43; // rbx
  volatile signed __int32 **v44; // rbx
  volatile signed __int32 *v45; // rbx
  RTL_SRWLOCK *v46; // rsi
  char *v47; // rsi
  int v48; // r13d
  int v49; // eax
  int v50; // edx
  CJetContext *v51; // r13
  JET_ERR v52; // eax
  const unsigned __int16 *v53; // rbx
  int v54; // eax
  unsigned int v55; // ebx
  JET_ERR v56; // eax
  JET_TABLEID v57; // rsi
  unsigned int cbData; // ebx
  JET_SESID v59; // r15
  __int64 v60; // rcx
  JET_COLUMNID v61; // edi
  __int64 v62; // rax
  JET_ERR v63; // eax
  unsigned int v64; // eax
  __int64 v65; // rbx
  int v66; // esi
  const unsigned __int16 *v67; // r10
  int v68; // edx
  const unsigned __int16 *v69; // r9
  int v70; // r8d
  unsigned __int16 v71; // cx
  int v72; // eax
  const unsigned __int16 *v73; // rdx
  JET_TABLEID v74; // rsi
  unsigned int v75; // ebx
  JET_SESID v76; // r15
  JET_COLUMNID v77; // edi
  __int64 v78; // rax
  JET_ERR v79; // eax
  unsigned int v80; // eax
  JET_TABLEID v81; // rsi
  unsigned int v82; // ebx
  JET_SESID v83; // r15
  JET_COLUMNID v84; // edi
  __int64 v85; // rax
  JET_ERR v86; // eax
  unsigned int v87; // eax
  int v88; // edx
  JET_TABLEID v89; // rdi
  JET_SESID v90; // rsi
  JET_COLUMNID v91; // ebx
  void *v92; // r15
  const void *v93; // r9
  JET_ERR v94; // eax
  unsigned int v95; // eax
  int v96; // edx
  JET_TABLEID v97; // rdi
  JET_SESID v98; // rsi
  JET_COLUMNID v99; // ebx
  void *v100; // r9
  JET_ERR v101; // eax
  unsigned int v102; // eax
  int v103; // edx
  JET_TABLEID v104; // rdi
  JET_SESID v105; // rsi
  __int64 v106; // rcx
  JET_COLUMNID v107; // ebx
  JET_ERR v108; // eax
  unsigned int v109; // eax
  int v110; // edx
  JET_TABLEID v111; // r15
  JET_SESID v112; // r12
  unsigned __int64 *v113; // rbx
  unsigned int v114; // edi
  JET_COLUMNID v115; // esi
  JET_ERR v116; // eax
  unsigned int v117; // eax
  int v118; // edx
  JET_TABLEID v119; // rdi
  JET_SESID v120; // rsi
  __int64 v121; // rcx
  JET_COLUMNID v122; // ebx
  JET_ERR v123; // eax
  unsigned int v124; // eax
  JET_ERR v125; // eax
  JET_SESID v126; // rcx
  JET_ERR v127; // eax
  CContainerProps *v128; // rax
  __int64 v129; // rbx
  CJetContext *v130; // rdi
  unsigned __int64 v131; // rcx
  unsigned __int64 v132; // r9
  unsigned __int16 **v133; // rbx
  __int64 v134; // rbx
  CInFlightEntry *v135; // rbx
  __int64 v136; // rax
  int v137; // r15d
  __int64 v138; // rsi
  struct _RTL_CRITICAL_SECTION *v139; // r12
  int v140; // r13d
  __int64 v141; // rsi
  void *v142; // r8
  int v144; // edx
  LPCWSTR v145; // rdi
  char v146; // si
  char v147; // bl
  _OWORD *v148; // rdx
  char v149; // al
  __int64 v150; // rcx
  JET_TABLEID v151; // rdx
  JET_SESID v152; // rcx
  JET_ERR v153; // eax
  int LastError; // eax
  char grbit; // [rsp+28h] [rbp-F8h]
  CJetContext *v158; // [rsp+B8h] [rbp-68h] BYREF
  unsigned int v159; // [rsp+C0h] [rbp-60h] BYREF
  int v160; // [rsp+C4h] [rbp-5Ch]
  int v161; // [rsp+C8h] [rbp-58h]
  int v162; // [rsp+CCh] [rbp-54h]
  LPCRITICAL_SECTION v163; // [rsp+D0h] [rbp-50h]
  void *v164; // [rsp+D8h] [rbp-48h]
  LPCWSTR lpFileName; // [rsp+E8h] [rbp-38h]
  void *v166; // [rsp+F0h] [rbp-30h]
  void *v167; // [rsp+F8h] [rbp-28h]
  void *v168; // [rsp+100h] [rbp-20h]
  RTL_SRWLOCK *v169; // [rsp+108h] [rbp-18h]
  unsigned __int16 **v170; // [rsp+110h] [rbp-10h]
  CInFlightEntry *v171; // [rsp+118h] [rbp-8h] BYREF
  unsigned int v172; // [rsp+120h] [rbp+0h] BYREF
  volatile signed __int32 *v173; // [rsp+128h] [rbp+8h] BYREF
  unsigned __int64 v174[2]; // [rsp+130h] [rbp+10h] BYREF
  char v175[8]; // [rsp+140h] [rbp+20h] BYREF
  char v176[8]; // [rsp+148h] [rbp+28h] BYREF
  LPCWSTR v177; // [rsp+150h] [rbp+30h] BYREF
  char v178[8]; // [rsp+158h] [rbp+38h] BYREF
  unsigned int v179; // [rsp+160h] [rbp+40h]
  int v180; // [rsp+164h] [rbp+44h]
  int v181; // [rsp+16Ch] [rbp+4Ch]
  unsigned __int64 v182; // [rsp+170h] [rbp+50h]
  FILETIME FileTime1; // [rsp+198h] [rbp+78h] BYREF
  char v184[16]; // [rsp+1A8h] [rbp+88h] BYREF
  char v185[24]; // [rsp+1B8h] [rbp+98h] BYREF
  unsigned __int64 *v186; // [rsp+1D0h] [rbp+B0h] BYREF
  unsigned int v187; // [rsp+1D8h] [rbp+B8h]
  char v188[16]; // [rsp+1E0h] [rbp+C0h] BYREF
  unsigned int v189; // [rsp+1F0h] [rbp+D0h] BYREF
  unsigned int v190; // [rsp+1F8h] [rbp+D8h] BYREF
  unsigned int v191; // [rsp+1FCh] [rbp+DCh] BYREF
  int v192; // [rsp+200h] [rbp+E0h] BYREF
  int v193; // [rsp+204h] [rbp+E4h] BYREF
  LPVOID lpMem; // [rsp+208h] [rbp+E8h] BYREF
  unsigned int v195; // [rsp+210h] [rbp+F0h] BYREF
  unsigned __int64 v196; // [rsp+218h] [rbp+F8h] BYREF
  unsigned __int64 v197; // [rsp+220h] [rbp+100h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+228h] [rbp+108h] BYREF
  FILETIME FileTime2; // [rsp+230h] [rbp+110h] BYREF
  __int64 v200; // [rsp+238h] [rbp+118h] BYREF
  struct _FILETIME v201; // [rsp+240h] [rbp+120h] BYREF
  struct _FILETIME v202; // [rsp+248h] [rbp+128h] BYREF
  __int64 v203; // [rsp+250h] [rbp+130h] BYREF
  __int128 FileInformation; // [rsp+258h] [rbp+138h] BYREF
  __int128 v205; // [rsp+268h] [rbp+148h]
  unsigned int v206; // [rsp+278h] [rbp+158h]
  _BYTE v207[36]; // [rsp+280h] [rbp+160h] BYREF

  v17 = a3;
  v18 = a2;
  v164 = a13;
  v167 = a11;
  lpFileName = a6;
  v168 = a7;
  v189 = a2;
  v19 = 0;
  v195 = a3;
  v170 = a16;
  v158 = 0;
  v162 = 0;
  v161 = 0;
  v196 = 0;
  v190 = 0;
  v200 = 0;
  v203 = 0;
  SystemTimeAsFileTime = 0;
  v197 = 0;
  v171 = 0;
  v191 = 0;
  v192 = 0;
  v159 = 0;
  v172 = 0;
  lpMem = 0;
  v202 = a8;
  FileTime2 = a9;
  v201 = a10;
  v206 = 0;
  FileInformation = 0;
  v193 = 1;
  v205 = 0;
  memset_0(v174, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    v23 = (WCHAR *)lpFileName;
    v24 = a4;
    grbit = v17;
    v25 = (CCacheContainer *)this;
    WPP_SF_qddSSSSiiiqdqddql(
      (_DWORD)j,
      v20,
      v22,
      (_DWORD)this,
      v18,
      grbit,
      (__int64)a4,
      (__int64)a5,
      (__int64)lpFileName,
      (__int64)v168,
      a8.dwLowDateTime,
      a9.dwLowDateTime,
      a10.dwLowDateTime,
      (__int64)v167,
      a12,
      (__int64)v164,
      a14,
      a15,
      (__int64)v170,
      a17);
  }
  else
  {
    v25 = (CCacheContainer *)this;
    v24 = a4;
    v23 = (WCHAR *)lpFileName;
  }
  v26 = 0;
  if ( v170 )
    *v170 = 0;
  v27 = (*((_BYTE *)v25 + 32) & 2) == 0;
  HIDWORD(v163) = 0;
  if ( v27 )
  {
    HIDWORD(v163) = 3123;
    updated = -2147024891;
    v51 = 0;
    goto LABEL_176;
  }
  updated = CContainerProps::UpdateLastAccessTime(*((CContainerProps **)v25 + 5));
  if ( updated < 0 )
  {
    v51 = 0;
    goto LABEL_176;
  }
  v166 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( v23 && *v23 )
  {
    v27 = (*((_BYTE *)v25 + 32) & 8) == 0;
    HIDWORD(v163) = 0;
    if ( v27 )
    {
      HIDWORD(v163) = 3123;
      updated = -2147024891;
      v51 = 0;
      goto LABEL_176;
    }
    if ( !GetFileAttributesExW(v23, GetFileExInfoStandard, &FileInformation) )
    {
      LastError = WxGetLastError(v150, v29);
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      v51 = 0;
      if ( updated >= 0 )
        updated = -2147418113;
      goto LABEL_176;
    }
    v200 = *(_QWORD *)((char *)&FileInformation + 4);
    v196 = v206 | ((unsigned __int64)HIDWORD(v205) << 32);
    if ( (v189 & 8) != 0 )
    {
      v166 = v23;
    }
    else
    {
      updated = CContainerProps::VerifyCacheEntryPath(*((CContainerProps **)v25 + 5), v23, &v172, &v190);
      if ( updated < 0 )
      {
        v51 = 0;
        goto LABEL_176;
      }
      v166 = &v23[v172];
    }
  }
  v30 = WxComputeUrlHash(v24, v29);
  v31 = *((_QWORD *)v25 + 5);
  v32 = v30;
  v197 = v30;
  v33 = 0;
  v160 = 0;
  j = *(__int64 **)(v31 + 144);
  v169 = (RTL_SRWLOCK *)j;
  v34 = j[8];
  v163 = (LPCRITICAL_SECTION)(j + 2);
  if ( v34 != -8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v34 + 8));
    v33 = 1;
  }
  v35 = *(char **)(v34 + 48);
  if ( v35 )
  {
    updated = 0;
    *(_QWORD *)(v34 + 48) = *((_QWORD *)v35 + 1);
    *((_QWORD *)v35 + 1) = 0;
  }
  else
  {
    v35 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x48u);
    if ( !v35 )
    {
      v35 = 0;
      updated = -2147024882;
      goto LABEL_13;
    }
    *(_QWORD *)v35 = 1;
    *(_QWORD *)(v35 + 28) = 0;
    *(_QWORD *)(v35 + 36) = 0;
    *(_QWORD *)(v35 + 44) = 0;
    *(_QWORD *)(v35 + 52) = 0;
    *(_QWORD *)(v35 + 60) = 0;
    *((_DWORD *)v35 + 17) = 0;
    *((_QWORD *)v35 + 1) = 0;
    *((_QWORD *)v35 + 2) = 0;
    *((_DWORD *)v35 + 6) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v35 + 32));
    updated = 0;
    *((_QWORD *)v35 + 1) = 0;
    ++*(_DWORD *)(v34 + 56);
  }
  ++*(_DWORD *)(v34 + 60);
LABEL_13:
  if ( v33 && v34 != -8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v34 + 8));
  if ( updated < 0 )
    goto LABEL_231;
  *((_DWORD *)v35 + 6) = 0;
  *((_QWORD *)v35 + 2) = v32;
  v36 = v163;
  if ( v163 )
  {
    EnterCriticalSection(v163);
    v160 = 1;
  }
  v173 = (volatile signed __int32 *)v35;
  Ptr = (volatile signed __int32 *)v169[7].Ptr;
  _InterlockedIncrement(Ptr + 2);
  v38 = *(_QWORD *)Ptr;
  if ( *(_DWORD *)(*(_QWORD *)Ptr + 44LL) )
  {
    for ( i = *(__int64 **)(v38 + 16); ; i = (__int64 *)i[2] )
    {
      while ( 1 )
      {
        v40 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 **, __int64 *))(v38 + 72))(v38, &v173, i + 4);
        if ( v40 )
          break;
        if ( !i[1] )
        {
          v41 = 2;
          goto LABEL_25;
        }
        i = (__int64 *)i[1];
      }
      if ( v40 != 1 )
      {
        v41 = 1;
        v43 = i;
        goto LABEL_29;
      }
      if ( !i[2] )
        break;
    }
    v41 = 3;
  }
  else
  {
    i = 0;
    v41 = 0;
  }
LABEL_25:
  v42 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(v38 + 80))(v38, 40);
  v43 = v42;
  if ( !v42 )
    goto LABEL_257;
  *v42 = 0;
  v42[1] = 0;
  ++*(_DWORD *)(v38 + 44);
  if ( v41 )
  {
    v148 = v42;
    if ( v41 == 2 )
      i[1] = (__int64)v42;
    else
      i[2] = (__int64)v42;
    *(_QWORD *)v42 = i;
    v22 = 1;
    *(_BYTE *)(v38 + 24) = -1;
    for ( j = *(__int64 **)v42; ; i = j )
    {
      v27 = j[1] == (_QWORD)v148;
      v149 = -1;
      LODWORD(j) = *((unsigned __int8 *)i + 24);
      if ( !v27 )
        v149 = 1;
      if ( (_BYTE)j )
        break;
      j = (__int64 *)*i;
      v148 = i;
      *((_BYTE *)i + 24) = v149;
    }
    if ( (_BYTE)j == v149 )
    {
      RebalanceNode((struct _WX_BALANCED_LINKS *)i);
    }
    else
    {
      *((_BYTE *)i + 24) = 0;
      if ( !*(_BYTE *)(v38 + 24) )
        ++*(_DWORD *)(v38 + 48);
    }
  }
  else
  {
    *(_QWORD *)(v38 + 16) = v42;
    *(_QWORD *)v42 = v38;
    *(_DWORD *)(v38 + 48) = 1;
  }
  v36 = v163;
  *((_QWORD *)v43 + 4) = v173;
LABEL_29:
  v44 = (volatile signed __int32 **)(v43 + 2);
  if ( !v44 )
  {
LABEL_257:
    updated = -2147024882;
LABEL_231:
    v46 = v169;
    goto LABEL_38;
  }
  if ( v41 == 1 )
  {
    _InterlockedIncrement(*v44);
    v45 = *v44;
    updated = 1;
  }
  else
  {
    _InterlockedIncrement(v173);
    _InterlockedIncrement(*v44);
    v45 = *v44;
    updated = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v35, 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v35 + 32));
      operator delete(v35, 0x48u);
    }
    v35 = 0;
  }
  ++*((_DWORD *)v45 + 6);
  if ( v36 && v160 )
  {
    LeaveCriticalSection(v36);
    v160 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v45 + 8));
  v46 = v169;
  AcquireSRWLockShared(v169 + 1);
  v171 = (CInFlightEntry *)v45;
LABEL_38:
  if ( v35 )
  {
    v47 = (char *)v46[8].Ptr;
    v48 = 0;
    *((_QWORD *)v35 + 1) = 0;
    if ( v47 != (char *)-8LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v47 + 8));
      v48 = 1;
    }
    --*((_DWORD *)v47 + 15);
    LODWORD(j) = *((_DWORD *)v47 + 14);
    if ( (unsigned int)((_DWORD)j - *((_DWORD *)v47 + 15)) > *((_DWORD *)v47 + 16) )
    {
      *((_DWORD *)v47 + 14) = (_DWORD)j - 1;
      CInFlightEntry::Release((CInFlightEntry *)v35);
      if ( v48 && v47 != (char *)-8LL )
        goto LABEL_44;
    }
    else
    {
      *((_QWORD *)v35 + 1) = *((_QWORD *)v47 + 6);
      *((_QWORD *)v47 + 6) = v35;
      if ( v48 && v47 != (char *)-8LL )
LABEL_44:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v47 + 8));
    }
  }
  if ( v160 && v163 )
    LeaveCriticalSection(v163);
  v25 = (CCacheContainer *)this;
  if ( updated < 0 )
  {
    v51 = 0;
    v26 = 0;
    goto LABEL_176;
  }
  v49 = CJetContextList::AcquireContext(*((CJetContextList **)this[5] + 19), &v158, 0);
  v51 = v158;
  v26 = 0;
  updated = v49;
  if ( v49 < 0 )
    goto LABEL_176;
  HIDWORD(v158) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD((_DWORD)j, v50, v22, (_DWORD)v51, 0, (__int64)L"HashEntryIdIndex", 0);
  if ( *((_DWORD *)v51 + 12) )
  {
    v151 = *((_QWORD *)v51 + 4);
    v152 = *((_QWORD *)v51 + 2);
    *((_DWORD *)v51 + 12) = -1;
    v153 = JetSetCurrentIndex2W(v152, v151, L"HashEntryIdIndex", 0);
    updated = HRESULTFromJET_ERR(v153, 1);
    if ( updated >= 0 )
      *((_DWORD *)v51 + 12) = 0;
  }
  else
  {
    updated = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0 )
    goto LABEL_176;
  v52 = JetBeginTransaction(*((_QWORD *)v51 + 2));
  v53 = a4;
  updated = HRESULTFromJET_ERR(v52, 1);
  if ( updated >= 0 )
  {
    v191 = a15;
    v162 = 1;
    v54 = SeekToEntry(v51, a4, v197);
    updated = v54;
    if ( v54 >= 0 )
    {
      v55 = 0;
      if ( !v54 )
      {
        updated = GetEntryFixedInfoAtCursor(
                    *((_QWORD *)v51 + 2),
                    *((_QWORD *)v51 + 4),
                    *(unsigned int **)(*((_QWORD *)v51 + 5) + 8LL),
                    (struct ENTRY_INFO *)v174);
        if ( updated < 0 )
          goto LABEL_176;
        v19 = (volatile signed __int32 *)*((_QWORD *)this[5] + 17);
        if ( v19 )
          _InterlockedIncrement(v19 + 4);
        updated = CAggregateLocks::GetLockCount((CAggregateLocks *)v19, v174[0], &v159);
        if ( updated < 0 )
          goto LABEL_176;
        if ( v159 )
        {
          updated = -2147024864;
          goto LABEL_176;
        }
        updated = GetEntryFilenameGroupInfoAtCursor(
                    *((_QWORD *)v51 + 2),
                    *((_QWORD *)v51 + 4),
                    *(unsigned int **)(*((_QWORD *)v51 + 5) + 8LL),
                    (struct ENTRY_INFO *)v174);
        if ( updated < 0 )
          goto LABEL_176;
        if ( a17 && CompareFileTime(&FileTime1, &FileTime2) > 0 )
        {
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 21, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids);
          DeleteFileW(lpFileName);
          DeleteRoamingData(lpFileName);
          updated = -2147024864;
          goto LABEL_176;
        }
        v145 = v177;
        v146 = v180;
        v147 = v189;
        v193 = v181 + 1;
        v191 = 0;
        HIDWORD(v158) = 0;
        memset(v207, 0, sizeof(v207));
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_ddS((_DWORD)j, v144, v22, v189, v180, (__int64)v177);
        if ( (v147 & 8) == 0
          && (v146 & 8) != 0
          && v145
          && *v145
          && GetFileAttributesExW(v145, GetFileExInfoStandard, v207)
          && *(_QWORD *)&v207[28] )
        {
          updated = -2147024864;
          HIDWORD(v158) = 367;
        }
        else
        {
          updated = 0;
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 17, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
        if ( updated < 0 )
          goto LABEL_176;
        v55 = 2;
      }
      if ( (v189 & 4) != 0 )
        v192 = 86400;
      v56 = JetPrepareUpdate(*((_QWORD *)v51 + 2), *((_QWORD *)v51 + 4), v55);
      updated = HRESULTFromJET_ERR(v56, 1);
      if ( updated < 0 )
        goto LABEL_176;
      v161 = 1;
      if ( !v55 )
      {
        v57 = *((_QWORD *)v51 + 4);
        cbData = 0;
        v59 = *((_QWORD *)v51 + 2);
        v60 = *(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL);
        v61 = *(_DWORD *)(v60 + 16);
        HIDWORD(v158) = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_iiiS(v60, 0, (_DWORD)a4, v59, v57, v61, (__int64)a4);
        if ( a4 )
        {
          v62 = -1;
          do
            v27 = a4[++v62] == 0;
          while ( !v27 );
          cbData = 2 * v62 + 2;
        }
        v63 = JetSetColumn(v59, v57, v61, a4, cbData, 0, 0);
        v64 = HRESULTFromJET_ERR(v63, 1);
        updated = v64;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 19, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v64);
        v26 = 0;
        if ( updated < 0 )
          goto LABEL_176;
        updated = JetSetColumn(
                    *((_QWORD *)v51 + 2),
                    *((_QWORD *)v51 + 4),
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 12LL),
                    &v197,
                    8u,
                    0,
                    0);
        if ( updated < 0 )
          goto LABEL_176;
        v65 = *((_QWORD *)this[5] + 24);
        if ( v65 )
        {
          v66 = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_qSq(1036, 22, (unsigned int)WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids, v65, (__int64)a4, 0);
          v67 = a4;
          v68 = 0;
          v69 = a4;
          v70 = 0;
          if ( a4 )
          {
            do
            {
              v68 = *((_DWORD *)qword_180226530 + ((unsigned __int64)*v69 >> 8))
                  ^ __ROL4__(*((_DWORD *)qword_180226530 + (unsigned __int8)*v69) ^ __ROL4__(v68, 1), 1);
              if ( !*v69 )
                break;
              ++v69;
              ++v70;
            }
            while ( v70 != -1 );
          }
          v71 = *a4;
          v72 = 5381;
          LODWORD(v158) = v68;
          if ( v71 )
          {
            v73 = a4;
            do
            {
              ++v73;
              v72 = v71 ^ (33 * v72);
              v71 = *v73;
            }
            while ( *v73 );
          }
          HIDWORD(v158) = v72;
          if ( v65 != -16 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v65 + 16));
            v67 = a4;
            v66 = 1;
          }
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_S(1036, 24, WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids, v67);
          WxBloomFilterAddPreHashedMember(
            (const struct WxBloomEntryHashes *)&v158,
            *(unsigned __int8 **)(v65 + 64),
            *(_DWORD *)(v65 + 84),
            *(_DWORD *)(v65 + 88));
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 25, WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids);
          if ( v66 && v65 != -16 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v65 + 16));
        }
      }
      updated = JetSetColumn(
                  *((_QWORD *)v51 + 2),
                  *((_QWORD *)v51 + 4),
                  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 4LL),
                  this + 3,
                  8u,
                  0,
                  0);
      if ( updated >= 0 )
      {
        updated = JetSetColumn(
                    *((_QWORD *)v51 + 2),
                    *((_QWORD *)v51 + 4),
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 8LL),
                    &v203,
                    8u,
                    0,
                    0);
        if ( updated >= 0 )
        {
          v74 = *((_QWORD *)v51 + 4);
          v75 = 0;
          v76 = *((_QWORD *)v51 + 2);
          v77 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 20LL);
          HIDWORD(v158) = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_iiiS((_DWORD)v166, 0, v22, v76, v74, v77, (__int64)v166);
          if ( v166 )
          {
            v78 = -1;
            do
              v27 = *((_WORD *)v166 + ++v78) == 0;
            while ( !v27 );
            v75 = 2 * v78 + 2;
          }
          v79 = JetSetColumn(v76, v74, v77, v166, v75, 0, 0);
          v80 = HRESULTFromJET_ERR(v79, 1);
          updated = v80;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_d(1036, 19, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v80);
          if ( updated < 0 )
          {
            v26 = 0;
          }
          else
          {
            v81 = *((_QWORD *)v51 + 4);
            v82 = 0;
            v83 = *((_QWORD *)v51 + 2);
            v84 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 28LL);
            HIDWORD(v158) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiS((_DWORD)v168, 0, v22, v83, v81, v84, (__int64)v168);
            if ( v168 )
            {
              v85 = -1;
              do
                v27 = *((_WORD *)v168 + ++v85) == 0;
              while ( !v27 );
              v82 = 2 * v85 + 2;
            }
            v86 = JetSetColumn(v83, v81, v84, v168, v82, 0, 0);
            v87 = HRESULTFromJET_ERR(v86, 1);
            updated = v87;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 19, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v87);
            v26 = 0;
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 24LL),
                        &v190,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 32LL),
                        &v196,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            v89 = *((_QWORD *)v51 + 4);
            v90 = *((_QWORD *)v51 + 2);
            v91 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 36LL);
            HIDWORD(v168) = 0;
            v92 = v167;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(a12, v88, v22, v90, v89, v91, (__int64)v167);
            v93 = 0;
            if ( a12 )
              v93 = v92;
            v26 = 0;
            v94 = JetSetColumn(v90, v89, v91, v93, a12, 0, 0);
            v95 = HRESULTFromJET_ERR(v94, 1);
            updated = v95;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v95);
            if ( updated < 0 )
              goto LABEL_176;
            v97 = *((_QWORD *)v51 + 4);
            v98 = *((_QWORD *)v51 + 2);
            v99 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 40LL);
            HIDWORD(v167) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd((_DWORD)v164, v96, v22, v98, v97, v99, (__int64)v164);
            v100 = 0;
            if ( a14 )
              v100 = v164;
            v101 = JetSetColumn(v98, v97, v99, v100, a14, 0, 0);
            v102 = HRESULTFromJET_ERR(v101, 1);
            updated = v102;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v102);
            if ( updated < 0 )
              goto LABEL_176;
            v104 = *((_QWORD *)v51 + 4);
            v105 = *((_QWORD *)v51 + 2);
            v106 = *(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL);
            v107 = *(_DWORD *)(v106 + 44);
            HIDWORD(v164) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiS(v106, v103, v22, v105, v104, v107, 0);
            v108 = JetSetColumn(v105, v104, v107, 0, 0, 0, 0);
            v109 = HRESULTFromJET_ERR(v108, 1);
            updated = v109;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 19, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v109);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 48LL),
                        &v189,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 52LL),
                        &v195,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 56LL),
                        &v193,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 60LL),
                        &SystemTimeAsFileTime,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 64LL),
                        &v200,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 68LL),
                        &v202,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 72LL),
                        &FileTime2,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 76LL),
                        &SystemTimeAsFileTime,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 80LL),
                        &v201,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 84LL),
                        &v191,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v51 + 2),
                        *((_QWORD *)v51 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 88LL),
                        &v192,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            v111 = *((_QWORD *)v51 + 4);
            v112 = *((_QWORD *)v51 + 2);
            v113 = v186;
            v114 = 8 * v187;
            v115 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL) + 92LL);
            HIDWORD(v164) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(0, v110, v22, v112, v111, v115, (__int64)v186);
            if ( !v114 )
              v113 = 0;
            v116 = JetSetColumn(v112, v111, v115, v113, v114, 0, 0);
            v117 = HRESULTFromJET_ERR(v116, 1);
            updated = v117;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v117);
            v26 = 0;
            if ( updated < 0 )
              goto LABEL_348;
            v119 = *((_QWORD *)v51 + 4);
            v120 = *((_QWORD *)v51 + 2);
            v121 = *(_QWORD *)(*((_QWORD *)v51 + 5) + 8LL);
            v122 = *(_DWORD *)(v121 + 96);
            HIDWORD(v164) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(v121, v118, v22, v120, v119, v122, 0);
            v123 = JetSetColumn(v120, v119, v122, 0, 0, 0, 0);
            v124 = HRESULTFromJET_ERR(v123, 1);
            updated = v124;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v124);
            if ( updated < 0
              || (v125 = JetUpdate(*((_QWORD *)v51 + 2), *((_QWORD *)v51 + 4), 0, 0, 0),
                  updated = HRESULTFromJET_ERR(v125, 1),
                  updated < 0) )
            {
LABEL_348:
              v25 = (CCacheContainer *)this;
            }
            else
            {
              v126 = *((_QWORD *)v51 + 2);
              v161 = 0;
              v127 = JetCommitTransaction(v126, 1u);
              v25 = (CCacheContainer *)this;
              updated = HRESULTFromJET_ERR(v127, 1);
              if ( updated >= 0 )
              {
                v128 = this[5];
                v162 = 0;
                if ( *((_DWORD *)v128 + 56) )
                {
                  if ( !a17 )
                  {
                    v53 = a4;
                    updated = WriteRoamingData(
                                lpFileName,
                                v189,
                                v195,
                                a4,
                                (union FILETIMEEX *)&v202,
                                (union FILETIMEEX *)&FileTime2,
                                (union FILETIMEEX *)&v201,
                                *((_DWORD *)v128 + 58));
                    if ( updated < 0 )
                      goto LABEL_177;
                  }
                }
                v129 = *((_QWORD *)this[5] + 19);
                CCacheStore::EndActivity(*(CCacheStore **)(v129 + 80));
                v130 = v51;
                if ( !v51 )
                  goto LABEL_160;
                v51 = 0;
                *((_QWORD *)v130 + 1) = 0;
                if ( v129 != -8 )
                {
                  EnterCriticalSection((LPCRITICAL_SECTION)(v129 + 8));
                  v26 = 1;
                }
                --*(_DWORD *)(v129 + 60);
                if ( (unsigned int)(*(_DWORD *)(v129 + 56) - *(_DWORD *)(v129 + 60)) > *(_DWORD *)(v129 + 64) )
                {
                  --*(_DWORD *)(v129 + 56);
                  CJetContext::Release(v130);
                  if ( !v26 || v129 == -8 )
                    goto LABEL_256;
                }
                else
                {
                  *((_QWORD *)v130 + 1) = *(_QWORD *)(v129 + 48);
                  *(_QWORD *)(v129 + 48) = v130;
                  if ( !v26 || v129 == -8 )
                    goto LABEL_256;
                }
                LeaveCriticalSection((LPCRITICAL_SECTION)(v129 + 8));
LABEL_256:
                v26 = 0;
LABEL_160:
                CInFlightLocks::ReleaseLock(*((CInFlightLocks **)this[5] + 18), &v171);
                if ( lpFileName && *lpFileName && (v189 & 8) == 0 )
                {
                  v131 = v196;
                }
                else
                {
                  v131 = 0;
                  v196 = 0;
                }
                if ( v177 && *v177 && (v180 & 8) == 0 )
                {
                  v132 = v182;
                }
                else
                {
                  v132 = 0;
                  v182 = 0;
                }
                updated = CContainerProps::AdjustContainerUsage(this[5], v186, v187, v132, v179, v131, v190);
                if ( updated >= 0 )
                {
                  v133 = v170;
                  if ( !v170
                    || !lpFileName
                    || !*lpFileName
                    || (updated = CContainerProps::GetNextDirectoryAsCaller(this[5], (unsigned __int16 **)&lpMem),
                        updated >= 0) )
                  {
                    if ( v190 == v179 && v166 && v177 && !(unsigned int)_o__wcsicmp(v166)
                      || (updated = CContainerProps::DeleteEntryFile(this[5], (struct ENTRY_INFO *)v174, 0, 1, 1, 1),
                          updated >= 0) )
                    {
                      if ( v133 && lpMem )
                      {
                        *v133 = (unsigned __int16 *)lpMem;
                        lpMem = 0;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_176:
      v53 = a4;
    }
  }
LABEL_177:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISDD((_DWORD)j, 22, v22, *((_QWORD *)v25 + 3), (__int64)v53, a14, updated);
  if ( v161 )
    JetPrepareUpdate(*((_QWORD *)v51 + 2), *((_QWORD *)v51 + 4), 3u);
  if ( v162 )
    JetRollback(*((_QWORD *)v51 + 2), 0);
  v134 = *(_QWORD *)(*((_QWORD *)v25 + 5) + 152LL);
  if ( v51 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v134 + 80));
    *((_QWORD *)v51 + 1) = 0;
    if ( v134 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v134 + 8));
      v26 = 1;
    }
    --*(_DWORD *)(v134 + 60);
    if ( (unsigned int)(*(_DWORD *)(v134 + 56) - *(_DWORD *)(v134 + 60)) > *(_DWORD *)(v134 + 64) )
    {
      --*(_DWORD *)(v134 + 56);
      CJetContext::Release(v51);
      if ( v26 && v134 != -8 )
        goto LABEL_213;
    }
    else
    {
      *((_QWORD *)v51 + 1) = *(_QWORD *)(v134 + 48);
      *(_QWORD *)(v134 + 48) = v51;
      if ( v26 && v134 != -8 )
LABEL_213:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v134 + 8));
    }
  }
  v135 = v171;
  if ( !v171 )
    goto LABEL_199;
  v136 = *((_QWORD *)v25 + 5);
  v137 = 0;
  v159 = 0;
  v138 = *(_QWORD *)(v136 + 144);
  v139 = (struct _RTL_CRITICAL_SECTION *)(v138 + 16);
  ReleaseSRWLockShared((PSRWLOCK)(v138 + 8));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v135 + 32));
  if ( v138 != -16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v138 + 16));
    v137 = 1;
    v159 = 1;
  }
  v27 = (*((_DWORD *)v135 + 6))-- == 1;
  if ( v27 )
  {
    CWxRefMap<CInFlightMap,CInFlightEntry>::Delete(*(_QWORD *)(v138 + 56), v135);
    *((_QWORD *)v135 + 2) = 0;
    v140 = 0;
    v141 = *(_QWORD *)(v138 + 64);
    *((_QWORD *)v135 + 1) = 0;
    if ( v141 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v141 + 8));
      v140 = 1;
    }
    --*(_DWORD *)(v141 + 60);
    if ( (unsigned int)(*(_DWORD *)(v141 + 56) - *(_DWORD *)(v141 + 60)) > *(_DWORD *)(v141 + 64) )
    {
      --*(_DWORD *)(v141 + 56);
      CInFlightEntry::Release(v135);
      if ( v140 && v141 != -8 )
        goto LABEL_194;
    }
    else
    {
      *((_QWORD *)v135 + 1) = *(_QWORD *)(v141 + 48);
      *(_QWORD *)(v141 + 48) = v135;
      if ( v140 && v141 != -8 )
LABEL_194:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v141 + 8));
    }
    if ( !v159 || !v139 )
      goto LABEL_198;
    goto LABEL_197;
  }
  CInFlightEntry::Release(v135);
  if ( !v137 || v138 == -16 )
    goto LABEL_198;
LABEL_197:
  LeaveCriticalSection(v139);
LABEL_198:
  v25 = (CCacheContainer *)this;
LABEL_199:
  WxHeapFree<_WX_AVL_TABLE>(v175);
  WxHeapFree<_WX_AVL_TABLE>(v176);
  WxHeapFree<_WX_AVL_TABLE>(&v177);
  WxHeapFree<_WX_AVL_TABLE>(v178);
  WxHeapFree<_WX_AVL_TABLE>(v184);
  WxHeapFree<_WX_AVL_TABLE>(v185);
  WxHeapFree<unsigned __int64>(&v186);
  WxHeapFree<_WX_AVL_TABLE>(v188);
  memset_0(v174, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 23, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, v25, updated);
  v142 = lpMem;
  if ( lpMem )
  {
    lpMem = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v142);
    else
      HeapFree(g_hWxProcessHeap, 0, v142);
  }
  if ( v19 && _InterlockedExchangeAdd(v19 + 4, 0xFFFFFFFF) == 1 )
  {
    CAggregateLocks::~CAggregateLocks((CAggregateLocks *)v19);
    operator delete((void *)v19, 0x48u);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18007c810  push    rbp
0x18007c812  push    rbx
0x18007c813  push    rsi
0x18007c814  push    rdi
0x18007c815  push    r12
0x18007c817  push    r13
0x18007c819  push    r14
0x18007c81b  push    r15
0x18007c81d  lea     rbp, [rsp-198h]
0x18007c825  sub     rsp, 2B8h
0x18007c82c  mov     rax, cs:__security_cookie
0x18007c833  xor     rax, rsp
0x18007c836  mov     [rbp+1D0h+var_48], rax
0x18007c83d  mov     rax, [rbp+1D0h+arg_60]
0x18007c844  xorps   xmm0, xmm0
0x18007c847  mov     rbx, qword ptr [rbp+1D0h+arg_38.dwLowDateTime]
0x18007c84e  mov     r12d, r8d
0x18007c851  mov     rdi, qword ptr [rbp+1D0h+arg_40.dwLowDateTime]
0x18007c858  mov     r15d, edx
0x18007c85b  mov     rsi, qword ptr [rbp+1D0h+arg_48.dwLowDateTime]
0x18007c862  mov     r13, [rbp+1D0h+arg_20]
0x18007c869  mov     [rbp+1D0h+var_218], rax
0x18007c86d  mov     rax, [rbp+1D0h+arg_50]
0x18007c874  mov     [rbp+1D0h+var_1F8], rax
0x18007c878  mov     rax, [rbp+1D0h+arg_28]
0x18007c87f  mov     [rbp+1D0h+lpFileName], rax
0x18007c883  mov     rax, [rbp+1D0h+arg_30]
0x18007c88a  mov     [rbp+1D0h+var_1F0], rax
0x18007c88e  mov     rax, [rbp+1D0h+arg_78]
0x18007c895  mov     [rbp+1D0h+var_240], rcx
0x18007c899  xor     ecx, ecx
0x18007c89b  mov     [rbp+1D0h+var_100], edx
0x18007c8a1  mov     r14d, ecx
0x18007c8a4  mov     [rbp+1D0h+var_E0], r8d
0x18007c8ab  xor     edx, edx; Val
0x18007c8ad  mov     [rbp+1D0h+var_1E0], rax
0x18007c8b1  mov     r8d, 0C0h; Size
0x18007c8b7  xor     eax, eax
0x18007c8b9  mov     [rbp+1D0h+var_238], rcx
0x18007c8bd  mov     [rbp+1D0h+var_224], ecx
0x18007c8c0  mov     [rbp+1D0h+var_228], ecx
0x18007c8c3  mov     [rbp+1D0h+var_D8], rcx
0x18007c8ca  mov     [rbp+1D0h+var_F8], ecx
0x18007c8d0  mov     [rbp+1D0h+var_B8], rcx
0x18007c8d7  mov     [rbp+1D0h+var_A0], rcx
0x18007c8de  mov     qword ptr [rbp+1D0h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18007c8e5  mov     [rbp+1D0h+var_D0], rcx
0x18007c8ec  mov     [rbp+1D0h+var_1D8], rcx
0x18007c8f0  mov     [rbp+1D0h+var_F4], ecx
0x18007c8f6  mov     [rbp+1D0h+var_F0], ecx
0x18007c8fc  mov     [rbp+1D0h+var_230], ecx
0x18007c8ff  mov     [rbp+1D0h+var_1D0], ecx
0x18007c902  mov     [rbp+1D0h+lpMem], rcx
0x18007c909  mov     [rbp+1D0h+var_A8], rbx
0x18007c910  mov     qword ptr [rbp+1D0h+FileTime2.dwLowDateTime], rdi
0x18007c917  mov     [rbp+1D0h+var_B0], rsi
0x18007c91e  mov     [rbp+1D0h+var_244], ecx
0x18007c921  lea     rcx, [rbp+1D0h+var_1C0]; void *
0x18007c925  mov     [rbp+1D0h+var_78], eax
0x18007c92b  mov     [rbp+1D0h+pvData], r9
0x18007c92f  movups  [rbp+1D0h+FileInformation], xmm0
0x18007c936  mov     [rbp+1D0h+var_EC], 1
0x18007c940  movups  [rbp+1D0h+var_88], xmm0
0x18007c947  call    memset_0
0x18007c94c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007c953  jz      loc_18007DDA8
0x18007c959  mov     eax, [rbp+1D0h+arg_80]
0x18007c95f  mov     [rsp+2F0h+var_258], eax
0x18007c966  mov     rax, [rbp+1D0h+var_1E0]
0x18007c96a  mov     [rsp+2F0h+var_260], rax
0x18007c972  mov     eax, [rbp+1D0h+arg_70]
0x18007c978  mov     [rsp+2F0h+var_268], eax
0x18007c97f  mov     eax, [rbp+1D0h+arg_68]
0x18007c985  mov     [rsp+2F0h+var_270], eax
0x18007c98c  mov     rax, [rbp+1D0h+var_218]
0x18007c990  mov     [rsp+2F0h+var_278], rax
0x18007c995  mov     eax, [rbp+1D0h+arg_58]
0x18007c99b  mov     [rsp+2F0h+var_280], eax
0x18007c99f  mov     rax, [rbp+1D0h+var_1F8]
0x18007c9a3  mov     [rsp+2F0h+var_288], rax
0x18007c9a8  mov     rax, [rbp+1D0h+var_1F0]
0x18007c9ac  mov     [rsp+2F0h+var_290], rsi
0x18007c9b1  mov     rsi, [rbp+1D0h+lpFileName]
0x18007c9b5  mov     [rsp+2F0h+var_298], rdi
0x18007c9ba  mov     [rsp+2F0h+var_2A0], rbx
0x18007c9bf  mov     rbx, [rbp+1D0h+pvData]
0x18007c9c3  mov     [rsp+2F0h+var_2A8], rax
0x18007c9c8  mov     [rsp+2F0h+var_2B0], rsi
0x18007c9cd  mov     qword ptr [rsp+2F0h+var_2B8], r13
0x18007c9d2  mov     [rsp+2F0h+psetinfo], rbx
0x18007c9d7  mov     [rsp+2F0h+grbit], r12d
0x18007c9dc  mov     r12, [rbp+1D0h+var_240]
0x18007c9e0  mov     r9, r12
0x18007c9e3  mov     [rsp+2F0h+cbData], r15d
0x18007c9e8  call    WPP_SF_qddSSSSiiiqdqddql
0x18007c9ed  mov     rax, [rbp+1D0h+var_1E0]
0x18007c9f1  xor     r15d, r15d
0x18007c9f4  test    rax, rax
0x18007c9f7  jz      short loc_18007C9FC
0x18007c9f9  mov     [rax], r15
0x18007c9fc  test    byte ptr [r12+20h], 2
0x18007ca02  mov     [rbp+1D0h+var_21C], r15d
0x18007ca06  jz      loc_18007E2DC
0x18007ca0c  mov     rcx, [r12+28h]; this
0x18007ca11  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x18007ca16  mov     edi, eax
0x18007ca18  test    eax, eax
0x18007ca1a  js      loc_18007E200
0x18007ca20  lea     rcx, [rbp+1D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007ca27  mov     [rbp+1D0h+var_200], r15
0x18007ca2b  call    cs:__imp_GetSystemTimeAsFileTime
0x18007ca31  test    rsi, rsi
0x18007ca34  jnz     loc_18007DE12
0x18007ca3a  mov     rcx, rbx
0x18007ca3d  call    WxComputeUrlHash
0x18007ca42  mov     rcx, [r12+28h]
0x18007ca47  mov     r13, rax
0x18007ca4a  mov     [rbp+1D0h+var_D0], rax
0x18007ca51  mov     r12d, r15d
0x18007ca54  mov     [rbp+1D0h+var_22C], r15d
0x18007ca58  mov     rcx, [rcx+90h]
0x18007ca5f  mov     [rbp+1D0h+var_1E8], rcx
0x18007ca63  mov     [rbp+1D0h+var_244], r15d
0x18007ca67  mov     rbx, [rcx+40h]
0x18007ca6b  lea     rax, [rcx+10h]
0x18007ca6f  mov     [rbp-50h], rax
0x18007ca73  lea     rsi, [rbx+8]
0x18007ca77  test    rsi, rsi
0x18007ca7a  jz      short loc_18007CA8B
0x18007ca7c  mov     rcx, rsi; lpCriticalSection
0x18007ca7f  call    cs:__imp_EnterCriticalSection
0x18007ca85  mov     r12d, 1
0x18007ca8b  mov     r15, [rbx+30h]
0x18007ca8f  test    r15, r15
0x18007ca92  jz      loc_18007DF7D
0x18007ca98  mov     rax, [r15+8]
0x18007ca9c  xor     edi, edi
0x18007ca9e  mov     [rbx+30h], rax
0x18007caa2  mov     [r15+8], rdi
0x18007caa6  inc     dword ptr [rbx+3Ch]
0x18007caa9  test    r12d, r12d
0x18007caac  jz      short loc_18007CABC
0x18007caae  test    rsi, rsi
0x18007cab1  jz      short loc_18007CABC
0x18007cab3  mov     rcx, rsi; lpCriticalSection
0x18007cab6  call    cs:__imp_LeaveCriticalSection
0x18007cabc  test    edi, edi
0x18007cabe  js      loc_18007DD98
0x18007cac4  mov     [r15+18h], r14d
0x18007cac8  mov     [r15+10h], r13
0x18007cacc  mov     r13, [rbp-50h]
0x18007cad0  test    r13, r13
0x18007cad3  jz      short loc_18007CAE5
0x18007cad5  mov     rcx, r13; lpCriticalSection
0x18007cad8  call    cs:__imp_EnterCriticalSection
0x18007cade  mov     [rbp+1D0h+var_22C], 1
0x18007cae5  mov     rax, [rbp+1D0h+var_1E8]
0x18007cae9  mov     [rbp+1D0h+var_1C8], r15
0x18007caed  mov     rax, [rax+38h]
0x18007caf1  lock inc dword ptr [rax+8]
0x18007caf5  mov     rdi, [rax]
0x18007caf8  cmp     [rdi+2Ch], r14d
0x18007cafc  jz      short loc_18007CB33
0x18007cafe  mov     rsi, [rdi+10h]
0x18007cb02  mov     rax, [rdi+48h]
0x18007cb06  lea     r8, [rsi+20h]
0x18007cb0a  lea     rdx, [rbp+1D0h+var_1C8]
0x18007cb0e  mov     rcx, rdi
0x18007cb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb16  test    eax, eax
0x18007cb18  jnz     loc_18007D9AE
0x18007cb1e  mov     rax, [rsi+8]
0x18007cb22  test    rax, rax
0x18007cb25  jnz     loc_18007DC7F
0x18007cb2b  mov     r12d, 2
0x18007cb31  jmp     short loc_18007CB38
0x18007cb33  xor     esi, esi
0x18007cb35  xor     r12d, r12d
0x18007cb38  mov     rax, [rdi+50h]
0x18007cb3c  mov     edx, 28h ; '('
0x18007cb41  mov     rcx, rdi
0x18007cb44  mov     r13d, 10h
0x18007cb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb4f  mov     rbx, rax
0x18007cb52  test    rax, rax
0x18007cb55  jz      loc_18007DF22
0x18007cb5b  xorps   xmm0, xmm0
0x18007cb5e  movups  xmmword ptr [rax], xmm0
0x18007cb61  movups  xmmword ptr [rax+10h], xmm0
0x18007cb65  inc     dword ptr [rdi+2Ch]
0x18007cb68  test    r12d, r12d
0x18007cb6b  jnz     loc_18007DDB9
0x18007cb71  mov     [rdi+r13], rax
0x18007cb75  mov     [rax], rdi
0x18007cb78  mov     dword ptr [rdi+30h], 1
0x18007cb7f  mov     rax, [rbp+1D0h+var_1C8]
0x18007cb83  mov     r13, [rbp-50h]
0x18007cb87  mov     [rbx+20h], rax
0x18007cb8b  add     rbx, 20h ; ' '
0x18007cb8f  jz      loc_18007DF22
0x18007cb95  cmp     r12d, 1
0x18007cb99  jz      loc_18007E00A
0x18007cb9f  mov     rax, [rbp+1D0h+var_1C8]
0x18007cba3  lock inc dword ptr [rax]
0x18007cba6  mov     rax, [rbx]
0x18007cba9  lock inc dword ptr [rax]
0x18007cbac  mov     rbx, [rbx]
0x18007cbaf  xor     edi, edi
0x18007cbb1  mov     eax, 0FFFFFFFFh
0x18007cbb6  lock xadd [r15], eax
0x18007cbbb  cmp     eax, 1
0x18007cbbe  jz      loc_18007E0E3
0x18007cbc4  xor     r15d, r15d
0x18007cbc7  inc     dword ptr [rbx+18h]
0x18007cbca  test    r13, r13
0x18007cbcd  jz      short loc_18007CBE2
0x18007cbcf  cmp     [rbp+1D0h+var_22C], r14d
0x18007cbd3  jz      short loc_18007CBE2
0x18007cbd5  mov     rcx, r13; lpCriticalSection
0x18007cbd8  call    cs:__imp_LeaveCriticalSection
0x18007cbde  mov     [rbp+1D0h+var_22C], r14d
0x18007cbe2  lea     rcx, [rbx+20h]; lpCriticalSection
0x18007cbe6  call    cs:__imp_EnterCriticalSection
0x18007cbec  mov     rsi, [rbp+1D0h+var_1E8]
0x18007cbf0  lea     rcx, [rsi+8]; SRWLock
0x18007cbf4  call    cs:__imp_AcquireSRWLockShared
0x18007cbfa  mov     [rbp+1D0h+var_1D8], rbx
0x18007cbfe  xor     ebx, ebx
0x18007cc00  test    r15, r15
0x18007cc03  jz      short loc_18007CC5B
0x18007cc05  mov     rsi, [rsi+40h]
0x18007cc09  xor     r13d, r13d
0x18007cc0c  mov     [r15+8], r13
0x18007cc10  lea     r12, [rsi+8]
0x18007cc14  test    r12, r12
0x18007cc17  jz      short loc_18007CC28
0x18007cc19  mov     rcx, r12; lpCriticalSection
0x18007cc1c  call    cs:__imp_EnterCriticalSection
0x18007cc22  mov     r13d, 1
0x18007cc28  dec     dword ptr [rsi+3Ch]
0x18007cc2b  mov     ecx, [rsi+38h]
0x18007cc2e  mov     eax, ecx
0x18007cc30  sub     eax, [rsi+3Ch]
0x18007cc33  cmp     eax, [rsi+40h]
0x18007cc36  ja      loc_18007E21B
0x18007cc3c  mov     rax, [rsi+30h]
0x18007cc40  mov     [r15+8], rax
0x18007cc44  mov     [rsi+30h], r15
0x18007cc48  test    r13d, r13d
0x18007cc4b  jz      short loc_18007CC5B
0x18007cc4d  test    r12, r12
0x18007cc50  jz      short loc_18007CC5B
0x18007cc52  mov     rcx, r12; lpCriticalSection
0x18007cc55  call    cs:__imp_LeaveCriticalSection
0x18007cc5b  test    rbx, rbx
0x18007cc5e  jz      short loc_18007CC68
0x18007cc60  mov     rcx, rbx; this
0x18007cc63  call    ?Release@CInFlightEntry@@QEAAKXZ; CInFlightEntry::Release(void)
0x18007cc68  cmp     [rbp+1D0h+var_22C], r14d
0x18007cc6c  jz      short loc_18007CC80
0x18007cc6e  mov     rax, [rbp-50h]
0x18007cc72  test    rax, rax
0x18007cc75  jz      short loc_18007CC80
0x18007cc77  mov     rcx, rax; lpCriticalSection
0x18007cc7a  call    cs:__imp_LeaveCriticalSection
0x18007cc80  mov     r12, [rbp+1D0h+var_240]
0x18007cc84  test    edi, edi
0x18007cc86  js      loc_18007E32A
0x18007cc8c  mov     rcx, [r12+28h]
0x18007cc91  lea     rdx, [rbp+1D0h+var_238]; struct CJetContext **
0x18007cc95  xor     r8d, r8d; int *
0x18007cc98  mov     rcx, [rcx+98h]; this
0x18007cc9f  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18007cca4  mov     r13, [rbp+1D0h+var_238]
0x18007cca8  xor     r15d, r15d
0x18007ccab  mov     edi, eax
0x18007ccad  test    eax, eax
0x18007ccaf  js      loc_18007E33C
0x18007ccb5  mov     dword ptr [rbp+1D0h+var_238+4], r15d
0x18007ccb9  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007ccc0  lea     rbx, aHashentryidind; "HashEntryIdIndex"
0x18007ccc7  jz      short loc_18007CCE0
0x18007ccc9  mov     dword ptr [rsp+2F0h+psetinfo], r15d
0x18007ccce  mov     r9, r13
0x18007ccd1  mov     qword ptr [rsp+2F0h+grbit], rbx
0x18007ccd6  mov     [rsp+2F0h+cbData], r15d
0x18007ccdb  call    WPP_SF_qdSD
0x18007cce0  cmp     [r13+30h], r14d
0x18007cce4  jnz     loc_18007E033
0x18007ccea  mov     edi, r15d
0x18007cced  mov     esi, 1
0x18007ccf2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007ccf9  jz      short loc_18007CD14
0x18007ccfb  mov     edx, 0Eh
0x18007cd00  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007cd07  mov     ecx, 40Ch
0x18007cd0c  mov     r9d, edi
0x18007cd0f  call    WPP_SF_d
0x18007cd14  test    edi, edi
0x18007cd16  js      loc_18007E348
  ... truncated ...
```
