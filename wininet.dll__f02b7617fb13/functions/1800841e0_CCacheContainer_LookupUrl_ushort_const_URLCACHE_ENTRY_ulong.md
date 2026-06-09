# CCacheContainer::LookupUrl(ushort const *,_URLCACHE_ENTRY *,ulong)

- ea: `0x1800841e0`
- end: `0x18008540b`
- name: `?LookupUrl@CCacheContainer@@QEAAJPEBGPEAU_URLCACHE_ENTRY@@K@Z`
- size: `4651`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, const unsigned __int16 *, struct _URLCACHE_ENTRY *, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800875d0`
- `0x1801c2678`

## callees

- `0x18007e620`
- `0x18007ec9c`
- `0x180080d10`
- `0x180083dc4`
- `0x1800841e0`
- `0x180085414`
- `0x180085460`
- `0x180085898`
- `0x180085988`
- `0x180086aa4`
- `0x1800b4614`
- `0x18012e53c`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e13c0`
- `0x1801e1790`
- `0x1801e17f0`
- `0x1801e1b60`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084f85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084f85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800842fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008459e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084869`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800842fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084459`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008459e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084869`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800849fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800842f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008441e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084481`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800848fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800849c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800842f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008441e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084481`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800848fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800849c3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180084c0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180084c0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008485f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008485f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800845ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800845ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084bcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084bcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800846c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800846ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008471a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084747`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084774`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800847a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800847ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800846c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800846ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008471a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084747`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180084774`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800847a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800847ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084daf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008538a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180084daf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008538a`
- `ESENT!JetSetCurrentIndex2W` at `0x180085159`
- `ESENT!JetSetCurrentIndex2W` at `0x180085159`
- `ESENT!JetSetColumn` at `0x180084e24`
- `ESENT!JetSetColumn` at `0x180084e64`
- `ESENT!JetSetColumn` at `0x180084e24`
- `ESENT!JetSetColumn` at `0x180084e64`
- `ESENT!JetDelete` at `0x180085324`
- `ESENT!JetDelete` at `0x180085324`
- `ESENT!JetCommitTransaction` at `0x180084ebe`
- `ESENT!JetCommitTransaction` at `0x180085352`
- `ESENT!JetCommitTransaction` at `0x180084ebe`
- `ESENT!JetCommitTransaction` at `0x180085352`
- `ESENT!JetUpdate` at `0x180084e90`
- `ESENT!JetUpdate` at `0x180084e90`
- `ESENT!JetPrepareUpdate` at `0x180084dd0`
- `ESENT!JetPrepareUpdate` at `0x180085400`
- `ESENT!JetPrepareUpdate` at `0x180084dd0`
- `ESENT!JetPrepareUpdate` at `0x180085400`
- `ESENT!JetRollback` at `0x180084818`
- `ESENT!JetRollback` at `0x180084818`
- `ESENT!JetBeginTransaction` at `0x180084d14`
- `ESENT!JetBeginTransaction` at `0x180084d14`

## pseudocode

```c
__int64 __fastcall CCacheContainer::LookupUrl(
        __int64 this,
        const unsigned __int16 *a2,
        struct _URLCACHE_ENTRY *a3,
        char a4)
{
  const unsigned __int16 *v4; // rdi
  struct _URLCACHE_ENTRY *v6; // r13
  __int64 v7; // rsi
  CJetContext *v8; // r14
  volatile signed __int32 *v9; // r15
  int v10; // ebx
  struct _URLCACHE_ENTRY *v11; // rax
  __int64 v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  unsigned int v14; // edi
  int updated; // r12d
  unsigned int v16; // r10d
  unsigned int v17; // edx
  const unsigned __int16 *i; // r9
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned __int64 v22; // rbx
  __int64 v23; // rax
  int v24; // esi
  __int64 v25; // r15
  __int64 v26; // rbx
  struct _RTL_CRITICAL_SECTION *v27; // r13
  char *v28; // r14
  volatile signed __int32 *v29; // rax
  __int64 v30; // rbx
  __int64 j; // rsi
  int v32; // eax
  int v33; // r12d
  _OWORD *v34; // rax
  _OWORD *v35; // rdi
  volatile signed __int32 **v36; // rdi
  volatile signed __int32 *v37; // rbx
  __int64 v38; // rdi
  int v39; // r15d
  void *v40; // r8
  void *v41; // r8
  void *v42; // r8
  void *v43; // r8
  void *v44; // r8
  void *v45; // r8
  void *v46; // r8
  __int64 v47; // rbx
  int v48; // r12d
  __int64 v49; // r13
  bool v50; // zf
  volatile signed __int32 *v51; // rdi
  __int64 v52; // rsi
  __int64 v53; // rbx
  struct _FILETIME *v54; // r15
  int v55; // eax
  int v56; // esi
  __int64 v57; // rbx
  int v59; // esi
  __int64 v60; // rbx
  __int64 v61; // rdi
  int v62; // eax
  __int64 v63; // rax
  _QWORD *v64; // rsi
  __int64 *v65; // rax
  char v66; // dl
  __int64 v67; // rcx
  _QWORD *v68; // r8
  __int64 v69; // rcx
  _QWORD *v70; // rcx
  __int64 *v71; // r15
  char v72; // al
  _OWORD *v73; // rdx
  char v74; // al
  int v75; // eax
  int v76; // edx
  JET_ERR v77; // eax
  int v78; // eax
  JET_ERR v79; // eax
  JET_ERR v80; // eax
  JET_ERR v81; // eax
  __int128 v82; // xmm1
  __int128 v83; // xmm0
  __int128 v84; // xmm1
  __int128 v85; // xmm0
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int64 v90; // rcx
  _QWORD *v91; // rax
  _QWORD *v92; // rax
  JET_TABLEID v93; // rdx
  JET_SESID v94; // rcx
  JET_ERR v95; // eax
  JET_ERR v96; // eax
  JET_ERR v97; // eax
  unsigned __int64 v98; // rbx
  JET_ERR CacheEntryAtCursor; // [rsp+40h] [rbp-C0h]
  _OWORD *v100; // [rsp+48h] [rbp-B8h]
  volatile signed __int32 *v101; // [rsp+50h] [rbp-B0h]
  int v102; // [rsp+58h] [rbp-A8h]
  unsigned int v103; // [rsp+5Ch] [rbp-A4h]
  int v104; // [rsp+60h] [rbp-A0h]
  int v105; // [rsp+64h] [rbp-9Ch]
  int v106; // [rsp+68h] [rbp-98h]
  BOOL v107; // [rsp+6Ch] [rbp-94h]
  __int64 v108; // [rsp+70h] [rbp-90h]
  unsigned __int64 v109; // [rsp+78h] [rbp-88h]
  unsigned int v112; // [rsp+8Ch] [rbp-74h] BYREF
  struct CJetContext *v113; // [rsp+90h] [rbp-70h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp-68h]
  __int64 v115; // [rsp+A0h] [rbp-60h]
  CJetContext *v116; // [rsp+A8h] [rbp-58h] BYREF
  volatile signed __int32 *v117; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME v118; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v119[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v121; // [rsp+E0h] [rbp-20h]
  __int128 v122; // [rsp+F0h] [rbp-10h]
  __int128 v123; // [rsp+100h] [rbp+0h]
  __int128 pvData; // [rsp+110h] [rbp+10h] BYREF
  LPVOID lpMem[2]; // [rsp+120h] [rbp+20h]
  LPVOID v126[2]; // [rsp+130h] [rbp+30h]
  LPVOID v127[2]; // [rsp+140h] [rbp+40h]
  LPVOID v128; // [rsp+150h] [rbp+50h]

  v4 = a2;
  v118 = (struct _FILETIME)a3;
  v108 = this;
  v128 = 0;
  v6 = a3;
  v7 = this;
  v116 = 0;
  v8 = 0;
  v113 = 0;
  v105 = 0;
  v9 = 0;
  v104 = 0;
  v10 = 0;
  v101 = 0;
  *(_OWORD *)v119 = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  v112 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  pvData = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v126 = 0;
  *(_OWORD *)v127 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSqd(
      1036,
      24,
      (unsigned int)WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids,
      this,
      (__int64)a2,
      (__int64)a3,
      a4);
  if ( v6 )
  {
    this = 152;
    v11 = v6;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (struct _URLCACHE_ENTRY *)((char *)v11 + 1);
      --this;
    }
    while ( this );
  }
  if ( (*(_BYTE *)(v7 + 32) & 1) == 0 )
  {
    updated = -2147024891;
    CacheEntryAtCursor = -2147024891;
    goto LABEL_67;
  }
  v12 = *(_QWORD *)(v7 + 40);
  v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 32);
  if ( v12 == -32 )
  {
    v14 = MEMORY[0x40];
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 32));
    v14 = *(_DWORD *)(v12 + 96);
    LeaveCriticalSection(v13);
  }
  v103 = v14;
  v107 = (a4 & 2) != 0 || v14;
  v106 = a4 & 1;
  if ( (a4 & 1) != 0 && (*(_BYTE *)(v7 + 32) & 4) == 0 )
  {
    v4 = a2;
    updated = -2147024891;
    v10 = 0;
    CacheEntryAtCursor = -2147024891;
    goto LABEL_67;
  }
  v4 = a2;
  updated = CContainerProps::UpdateLastAccessTime(*(CContainerProps **)(v7 + 40));
  CacheEntryAtCursor = updated;
  if ( updated < 0 )
  {
    v10 = 0;
    goto LABEL_67;
  }
  v16 = 0;
  if ( a2 )
  {
    v17 = 0;
    for ( i = a2; *i; v17 = v20 )
    {
      if ( v17 >= 3 )
        break;
      v19 = *i++;
      v16 = *((_DWORD *)qword_180226530 + ((unsigned __int64)v19 >> 8))
          ^ __ROL4__(*((_DWORD *)qword_180226530 + (unsigned __int8)v19) ^ __ROL4__(v16, 1), 1);
      v20 = v17 + 1;
      if ( v19 != 47 )
        v20 = v17;
    }
    v21 = 0;
    LODWORD(a3) = 0;
    do
    {
      v21 = *((_DWORD *)qword_180226530 + ((unsigned __int64)*i >> 8))
          ^ __ROL4__(*((_DWORD *)qword_180226530 + (unsigned __int8)*i) ^ __ROL4__(v21, 1), 1);
      if ( !*i )
        break;
      ++i;
      LODWORD(a3) = (_DWORD)a3 + 1;
    }
    while ( (_DWORD)a3 != -1 );
  }
  else
  {
    v21 = 0;
  }
  LODWORD(this) = v21;
  v22 = v21 ^ ((unsigned __int64)v16 << 31);
  v109 = v22;
  if ( v107 )
  {
    v23 = *(_QWORD *)(v7 + 40);
    v24 = 0;
    v102 = 0;
    v25 = *(_QWORD *)(v23 + 144);
    v115 = v25;
    v26 = *(_QWORD *)(v25 + 64);
    v27 = (struct _RTL_CRITICAL_SECTION *)(v25 + 16);
    lpCriticalSection = (LPCRITICAL_SECTION)(v25 + 16);
    if ( v26 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
      v24 = 1;
    }
    v28 = *(char **)(v26 + 48);
    if ( v28 )
    {
      updated = 0;
      *(_QWORD *)(v26 + 48) = *((_QWORD *)v28 + 1);
      *((_QWORD *)v28 + 1) = 0;
    }
    else
    {
      v28 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x48u);
      if ( !v28 )
      {
        v28 = 0;
        updated = -2147024882;
        goto LABEL_30;
      }
      *(_QWORD *)v28 = 1;
      *(_QWORD *)(v28 + 28) = 0;
      *(_QWORD *)(v28 + 36) = 0;
      *(_QWORD *)(v28 + 44) = 0;
      *(_QWORD *)(v28 + 52) = 0;
      *(_QWORD *)(v28 + 60) = 0;
      *((_DWORD *)v28 + 17) = 0;
      *((_QWORD *)v28 + 1) = 0;
      *((_QWORD *)v28 + 2) = 0;
      *((_DWORD *)v28 + 6) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v28 + 32));
      updated = 0;
      *((_QWORD *)v28 + 1) = 0;
      ++*(_DWORD *)(v26 + 56);
    }
    ++*(_DWORD *)(v26 + 60);
LABEL_30:
    CacheEntryAtCursor = updated;
    if ( v24 && v26 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
    if ( updated >= 0 )
    {
      *((_DWORD *)v28 + 6) = 0;
      *((_QWORD *)v28 + 2) = v109;
      if ( v25 != -16 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 16));
        v102 = 1;
      }
      v29 = *(volatile signed __int32 **)(v25 + 56);
      v117 = (volatile signed __int32 *)v28;
      _InterlockedIncrement(v29 + 2);
      v30 = *(_QWORD *)v29;
      if ( *(_DWORD *)(*(_QWORD *)v29 + 44LL) )
      {
        for ( j = *(_QWORD *)(v30 + 16); ; j = *(_QWORD *)(j + 16) )
        {
          while ( 1 )
          {
            v32 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 **, __int64))(v30 + 72))(
                    v30,
                    &v117,
                    j + 32);
            if ( v32 )
              break;
            if ( !*(_QWORD *)(j + 8) )
            {
              v33 = 2;
              goto LABEL_42;
            }
            j = *(_QWORD *)(j + 8);
          }
          if ( v32 != 1 )
          {
            v33 = 1;
            v35 = (_OWORD *)j;
            goto LABEL_46;
          }
          if ( !*(_QWORD *)(j + 16) )
            break;
        }
        v33 = 3;
      }
      else
      {
        j = 0;
        v33 = 0;
      }
LABEL_42:
      v34 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(v30 + 80))(v30, 40);
      v100 = v34;
      v35 = v34;
      if ( !v34 )
        goto LABEL_176;
      *v34 = 0;
      v34[1] = 0;
      ++*(_DWORD *)(v30 + 44);
      if ( v33 )
      {
        v73 = v34;
        if ( v33 == 2 )
          *(_QWORD *)(j + 8) = v34;
        else
          *(_QWORD *)(j + 16) = v34;
        *(_QWORD *)v34 = j;
        *(_BYTE *)(v30 + 24) = -1;
        for ( this = *(_QWORD *)v34; ; j = this )
        {
          v50 = *(_QWORD *)(this + 8) == (_QWORD)v73;
          v74 = -1;
          LODWORD(this) = *(unsigned __int8 *)(j + 24);
          if ( !v50 )
            v74 = 1;
          if ( (_BYTE)this )
            break;
          this = *(_QWORD *)j;
          v73 = (_OWORD *)j;
          *(_BYTE *)(j + 24) = v74;
        }
        v35 = v100;
        if ( (_BYTE)this == v74 )
        {
          RebalanceNode((struct _WX_BALANCED_LINKS *)j);
        }
        else
        {
          *(_BYTE *)(j + 24) = 0;
          if ( !*(_BYTE *)(v30 + 24) )
            ++*(_DWORD *)(v30 + 48);
        }
      }
      else
      {
        *(_QWORD *)(v30 + 16) = v34;
        *(_QWORD *)v34 = v30;
        *(_DWORD *)(v30 + 48) = 1;
      }
      v27 = lpCriticalSection;
      v25 = v115;
      *((_QWORD *)v35 + 4) = v117;
LABEL_46:
      v36 = (volatile signed __int32 **)(v35 + 2);
      if ( v36 )
      {
        if ( v33 == 1 )
        {
          _InterlockedIncrement(*v36);
          v37 = *v36;
          updated = 1;
          CacheEntryAtCursor = 1;
          v101 = *v36;
        }
        else
        {
          _InterlockedIncrement(v117);
          _InterlockedIncrement(*v36);
          v37 = *v36;
          updated = 0;
          v101 = *v36;
          CacheEntryAtCursor = 0;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28, 0xFFFFFFFF) == 1 )
          {
            DeleteCriticalSection((LPCRITICAL_SECTION)(v28 + 32));
            operator delete(v28, 0x48u);
          }
          v28 = 0;
        }
        ++*((_DWORD *)v37 + 6);
        if ( v27 && v102 )
        {
          LeaveCriticalSection(v27);
          v102 = 0;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v37 + 8));
        AcquireSRWLockShared((PSRWLOCK)(v25 + 8));
      }
      else
      {
LABEL_176:
        v27 = lpCriticalSection;
        updated = -2147024882;
        v25 = v115;
        CacheEntryAtCursor = -2147024882;
      }
    }
    if ( !v28 )
      goto LABEL_62;
    v38 = *(_QWORD *)(v25 + 64);
    v39 = 0;
    *((_QWORD *)v28 + 1) = 0;
    if ( v38 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v38 + 8));
      v39 = 1;
    }
    --*(_DWORD *)(v38 + 60);
    LODWORD(this) = *(_DWORD *)(v38 + 56);
    if ( (unsigned int)(this - *(_DWORD *)(v38 + 60)) > *(_DWORD *)(v38 + 64) )
    {
      *(_DWORD *)(v38 + 56) = this - 1;
      CInFlightEntry::Release((CInFlightEntry *)v28);
      if ( !v39 || v38 == -8 )
        goto LABEL_62;
    }
    else
    {
      *((_QWORD *)v28 + 1) = *(_QWORD *)(v38 + 48);
      *(_QWORD *)(v38 + 48) = v28;
      if ( !v39 || v38 == -8 )
        goto LABEL_62;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v38 + 8));
LABEL_62:
    if ( v102 && v27 )
      LeaveCriticalSection(v27);
    v9 = v101;
    v7 = v108;
    v6 = (struct _URLCACHE_ENTRY *)v118;
    v4 = a2;
    if ( updated < 0 )
    {
      v8 = v116;
      v10 = (int)v116;
      goto LABEL_67;
    }
    v22 = v109;
  }
  v75 = CJetContextList::AcquireContext(*(CJetContextList **)(*(_QWORD *)(v7 + 40) + 152LL), &v113, 0);
  v8 = v113;
  updated = v75;
  CacheEntryAtCursor = v75;
  if ( v75 < 0 )
  {
    v10 = 0;
    goto LABEL_67;
  }
  HIDWORD(v116) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD(this, v76, (_DWORD)a3, (_DWORD)v113, 0, (__int64)L"HashEntryIdIndex", 0);
  if ( *((_DWORD *)v8 + 12) )
  {
    v93 = *((_QWORD *)v8 + 4);
    v94 = *((_QWORD *)v8 + 2);
    *((_DWORD *)v8 + 12) = -1;
    v95 = JetSetCurrentIndex2W(v94, v93, L"HashEntryIdIndex", 0);
    CacheEntryAtCursor = HRESULTFromJET_ERR(v95, 1);
    updated = CacheEntryAtCursor;
    if ( CacheEntryAtCursor >= 0 )
      *((_DWORD *)v8 + 12) = 0;
  }
  else
  {
    updated = 0;
    CacheEntryAtCursor = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0
    || (v77 = JetBeginTransaction(*((_QWORD *)v8 + 2)),
        CacheEntryAtCursor = HRESULTFromJET_ERR(v77, 1),
        updated = CacheEntryAtCursor,
        CacheEntryAtCursor < 0) )
  {
LABEL_241:
    v10 = 0;
    goto LABEL_67;
  }
  v105 = 1;
  v78 = SeekToEntry(v8, v4, v22);
  CacheEntryAtCursor = v78;
  updated = v78;
  if ( v78 < 0 )
  {
    v10 = 0;
    goto LABEL_67;
  }
  if ( v78 )
  {
    updated = -2147024894;
    CacheEntryAtCursor = -2147024894;
    goto LABEL_241;
  }
  v10 = v106;
  CacheEntryAtCursor = CCacheContainer::GetCacheEntryAtCursor(
                         (CCacheContainer *)v7,
                         v8,
                         v106,
                         (struct _URLCACHE_ENTRY *)v119);
  updated = CacheEntryAtCursor;
  if ( CacheEntryAtCursor < 0 )
  {
    v10 = 0;
    goto LABEL_67;
  }
  if ( (HIDWORD(v123) & 0x10000) != 0 )
  {
    v10 = 0;
    if ( (a4 & 4) == 0 )
    {
      updated = -2147024894;
      CacheEntryAtCursor = -2147024894;
      goto LABEL_67;
    }
    v96 = JetDelete(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4));
    CacheEntryAtCursor = HRESULTFromJET_ERR(v96, 1);
    updated = CacheEntryAtCursor;
    if ( CacheEntryAtCursor < 0 )
      goto LABEL_67;
    v97 = JetCommitTransaction(*((_QWORD *)v8 + 2), 1u);
    CacheEntryAtCursor = HRESULTFromJET_ERR(v97, 1);
    updated = CacheEntryAtCursor;
    if ( CacheEntryAtCursor < 0 )
      goto LABEL_67;
    v105 = 0;
    goto LABEL_224;
  }
  if ( v103 )
  {
    v98 = (unsigned __int64)SystemTimeAsFileTime[0];
    v118 = 0;
    GetSystemTimeAsFileTime(&v118);
    if ( *(_QWORD *)&v118 > v98 && (*(_QWORD *)&v118 - v98) / 0x989680 <= v103 / 0xA )
      goto LABEL_224;
    v10 = v106;
  }
  if ( !v107 )
  {
LABEL_224:
    v82 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
    *(_OWORD *)v6 = *(_OWORD *)v119;
    v10 = 0;
    v83 = v121;
    *((_OWORD *)v6 + 1) = v82;
    v84 = v122;
    *((_OWORD *)v6 + 2) = v83;
    v85 = v123;
    *((_OWORD *)v6 + 3) = v84;
    v86 = pvData;
    *((_OWORD *)v6 + 4) = v85;
    v87 = *(_OWORD *)lpMem;
    *((_OWORD *)v6 + 5) = v86;
    v88 = *(_OWORD *)v126;
    *((_OWORD *)v6 + 6) = v87;
    v89 = *(_OWORD *)v127;
    *((_OWORD *)v6 + 7) = v88;
    *(_QWORD *)&v88 = v128;
    *((_OWORD *)v6 + 8) = v89;
    *((_QWORD *)v6 + 18) = v88;
    memset_0(v119, 0, 0x98u);
    if ( (*(_BYTE *)(*(_QWORD *)(v7 + 40) + 92LL) & 8) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)&CCacheStore::g_ulCacheReadCountSinceLastCleanup);
    updated = 0;
    v104 = 0;
    CacheEntryAtCursor = 0;
    goto LABEL_67;
  }
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  if ( DWORD1(pvData) != -1 )
    ++DWORD1(pvData);
  v79 = JetPrepareUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 2u);
  CacheEntryAtCursor = HRESULTFromJET_ERR(v79, 1);
  updated = CacheEntryAtCursor;
  if ( CacheEntryAtCursor >= 0 )
  {
    v104 = 1;
    CacheEntryAtCursor = JetSetColumn(
                           *((_QWORD *)v8 + 2),
                           *((_QWORD *)v8 + 4),
                           *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 8LL) + 76LL),
                           SystemTimeAsFileTime,
                           8u,
                           0,
                           0);
    updated = CacheEntryAtCursor;
    if ( CacheEntryAtCursor >= 0 )
    {
      CacheEntryAtCursor = JetSetColumn(
                             *((_QWORD *)v8 + 2),
                             *((_QWORD *)v8 + 4),
                             *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 8LL) + 56LL),
                             (char *)&pvData + 4,
                             4u,
                             0,
                             0);
      updated = CacheEntryAtCursor;
      if ( CacheEntryAtCursor >= 0 )
      {
        v80 = JetUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 0, 0, 0);
        CacheEntryAtCursor = HRESULTFromJET_ERR(v80, 1);
        updated = CacheEntryAtCursor;
        if ( CacheEntryAtCursor >= 0 )
        {
          v81 = JetCommitTransaction(*((_QWORD *)v8 + 2), 1u);
          CacheEntryAtCursor = HRESULTFromJET_ERR(v81, 1);
          updated = CacheEntryAtCursor;
          if ( CacheEntryAtCursor < 0 )
          {
            v104 = 0;
            goto LABEL_67;
          }
          v105 = 0;
          goto LABEL_224;
        }
      }
    }
  }
LABEL_67:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISDD(this, 25, (_DWORD)a3, *(_QWORD *)(v7 + 24), (__int64)v4, *((_DWORD *)v6 + 17), updated);
  if ( v10 )
    CClientLocks::UnlockEntry(*(CClientLocks **)(v7 + 96), v119[0], &v112);
  v40 = lpMem[0];
  if ( lpMem[0] )
  {
    lpMem[0] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v40);
    else
      HeapFree(g_hWxProcessHeap, 0, v40);
    lpMem[0] = 0;
  }
  v41 = lpMem[1];
  if ( lpMem[1] )
  {
    lpMem[1] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v41);
    else
      HeapFree(g_hWxProcessHeap, 0, v41);
    lpMem[1] = 0;
  }
  v42 = v126[0];
  if ( v126[0] )
  {
    v126[0] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v42);
    else
      HeapFree(g_hWxProcessHeap, 0, v42);
    v126[0] = 0;
  }
  v43 = v126[1];
  if ( v126[1] )
  {
    v126[1] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v43);
    else
      HeapFree(g_hWxProcessHeap, 0, v43);
    v126[1] = 0;
  }
  v44 = v127[0];
  if ( v127[0] )
  {
    v127[0] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v44);
    else
      HeapFree(g_hWxProcessHeap, 0, v44);
    v127[0] = 0;
  }
  v45 = v127[1];
  if ( v127[1] )
  {
    v127[1] = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v45);
    else
      HeapFree(g_hWxProcessHeap, 0, v45);
    v127[1] = 0;
  }
  v46 = v128;
  if ( v128 )
  {
    v128 = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v46);
    else
      HeapFree(g_hWxProcessHeap, 0, v46);
  }
  *(_OWORD *)v119 = 0;
  v128 = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  pvData = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v126 = 0;
  *(_OWORD *)v127 = 0;
  if ( v104 )
    JetPrepareUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 3u);
  if ( v105 )
    JetRollback(*((_QWORD *)v8 + 2), 0);
  v47 = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 152LL);
  if ( v8 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v47 + 80));
    *((_QWORD *)v8 + 1) = 0;
    v59 = 0;
    if ( v47 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v47 + 8));
      v59 = 1;
    }
    --*(_DWORD *)(v47 + 60);
    if ( (unsigned int)(*(_DWORD *)(v47 + 56) - *(_DWORD *)(v47 + 60)) > *(_DWORD *)(v47 + 64) )
    {
      --*(_DWORD *)(v47 + 56);
      CJetContext::Release(v8);
      if ( !v59 || v47 == -8 )
        goto LABEL_138;
    }
    else
    {
      *((_QWORD *)v8 + 1) = *(_QWORD *)(v47 + 48);
      *(_QWORD *)(v47 + 48) = v8;
      if ( !v59 || v47 == -8 )
        goto LABEL_138;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v47 + 8));
LABEL_138:
    v7 = v108;
  }
  if ( !v9 )
    goto LABEL_126;
  v48 = 0;
  v49 = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 144LL);
  ReleaseSRWLockShared((PSRWLOCK)(v49 + 8));
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
  if ( v49 != -16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v49 + 16));
    v48 = 1;
  }
  v50 = (*((_DWORD *)v9 + 6))-- == 1;
  if ( v50 )
  {
    v51 = *(volatile signed __int32 **)(v49 + 56);
    v116 = (CJetContext *)v9;
    v52 = *(_QWORD *)v51;
    if ( *(_DWORD *)(*(_QWORD *)v51 + 44LL) )
    {
      v53 = *(_QWORD *)(v52 + 16);
      while ( 1 )
      {
        while ( 1 )
        {
          v54 = (struct _FILETIME *)(v53 + 32);
          v55 = (*(__int64 (__fastcall **)(__int64, CJetContext **, __int64))(v52 + 72))(v52, &v116, v53 + 32);
          if ( v55 )
            break;
          v53 = *(_QWORD *)(v53 + 8);
          if ( !v53 )
            goto LABEL_115;
        }
        if ( v55 != 1 )
          break;
        v53 = *(_QWORD *)(v53 + 16);
        if ( !v53 )
          goto LABEL_115;
      }
      if ( v53 != -32 )
      {
        _InterlockedIncrement(v51 + 2);
        v60 = *(_QWORD *)v51;
        if ( *(_DWORD *)(*(_QWORD *)v51 + 44LL) )
        {
          v61 = *(_QWORD *)(v60 + 16);
          v118 = *v54;
          while ( 1 )
          {
            while ( 1 )
            {
              v62 = (*(__int64 (__fastcall **)(__int64, struct _FILETIME *, __int64))(v60 + 72))(v60, v54, v61 + 32);
              if ( v62 )
                break;
              v61 = *(_QWORD *)(v61 + 8);
              if ( !v61 )
                goto LABEL_115;
            }
            if ( v62 != 1 )
              break;
            v61 = *(_QWORD *)(v61 + 16);
            if ( !v61 )
              goto LABEL_115;
          }
          if ( v61 == *(_QWORD *)(v60 + 56) )
            *(_QWORD *)(v60 + 56) = RealPredecessor((struct _WX_BALANCED_LINKS *)v61);
          ++*(_DWORD *)(v60 + 64);
          v63 = *(_QWORD *)(v61 + 8);
          if ( v63 && (v64 = *(_QWORD **)(v61 + 16)) != 0 )
          {
            if ( *(char *)(v61 + 24) < 0 )
            {
              v64 = *(_QWORD **)(v61 + 8);
              if ( *(_QWORD *)(v63 + 16) )
              {
                do
                  v64 = (_QWORD *)v64[2];
                while ( v64[2] );
              }
            }
            else
            {
              for ( ; v64[1]; v64 = (_QWORD *)v64[1] )
                ;
            }
          }
          else
          {
            v64 = (_QWORD *)v61;
          }
          v65 = (__int64 *)*v64;
          v66 = -1;
          v67 = v64[1];
          v68 = *(_QWORD **)(*v64 + 8LL);
          if ( v67 )
          {
            if ( v68 == v64 )
            {
              v65[1] = v67;
            }
            else
            {
              v65[2] = v67;
              v66 = 1;
            }
            v70 = (_QWORD *)v64[1];
          }
          else
          {
            v69 = v64[2];
            if ( v68 == v64 )
            {
              v65[1] = v69;
            }
            else
            {
              v65[2] = v69;
              v66 = 1;
            }
            v70 = (_QWORD *)v64[2];
            if ( !v70 )
              goto LABEL_160;
          }
          *v70 = *v64;
LABEL_160:
          *(_BYTE *)(v60 + 24) = 0;
          v71 = (__int64 *)*v64;
          while ( 1 )
          {
            v72 = *((_BYTE *)v71 + 24);
            if ( v72 == v66 )
            {
              *((_BYTE *)v71 + 24) = 0;
            }
            else
            {
              if ( !v72 )
              {
                *((_BYTE *)v71 + 24) = -v66;
                if ( *(_BYTE *)(v60 + 24) )
                  --*(_DWORD *)(v60 + 48);
LABEL_165:
                if ( (_QWORD *)v61 != v64 )
                {
                  *(_OWORD *)v64 = *(_OWORD *)v61;
                  *((_OWORD *)v64 + 1) = *(_OWORD *)(v61 + 16);
                  v90 = *v64;
                  if ( *(_QWORD *)(*(_QWORD *)v61 + 8LL) == v61 )
                    *(_QWORD *)(v90 + 8) = v64;
                  else
                    *(_QWORD *)(v90 + 16) = v64;
                  v91 = (_QWORD *)v64[1];
                  if ( v91 )
                    *v91 = v64;
                  v92 = (_QWORD *)v64[2];
                  if ( v92 )
                    *v92 = v64;
                }
                --*(_DWORD *)(v60 + 44);
                *(_DWORD *)(v60 + 40) = 0;
                *(_QWORD *)(v60 + 32) = 0;
                (*(void (__fastcall **)(__int64, __int64))(v60 + 88))(v60, v61);
                CInFlightEntry::Release(*(CInFlightEntry **)&v118);
                break;
              }
              if ( RebalanceNode((struct _WX_BALANCED_LINKS *)v71) )
                goto LABEL_165;
              v71 = (__int64 *)*v71;
            }
            v66 = 1;
            v50 = *(_QWORD *)(*v71 + 16) == (_QWORD)v71;
            v71 = (__int64 *)*v71;
            if ( !v50 )
              v66 = -1;
          }
        }
      }
LABEL_115:
      v9 = v101;
    }
    *((_QWORD *)v9 + 2) = 0;
    v56 = 0;
    v57 = *(_QWORD *)(v49 + 64);
    *((_QWORD *)v9 + 1) = 0;
    if ( v57 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v57 + 8));
      v56 = 1;
    }
    --*(_DWORD *)(v57 + 60);
    if ( (unsigned int)(*(_DWORD *)(v57 + 56) - *(_DWORD *)(v57 + 60)) > *(_DWORD *)(v57 + 64) )
    {
      --*(_DWORD *)(v57 + 56);
      CInFlightEntry::Release((CInFlightEntry *)v9);
      if ( !v56 || v57 == -8 )
        goto LABEL_122;
    }
    else
    {
      *((_QWORD *)v9 + 1) = *(_QWORD *)(v57 + 48);
      *(_QWORD *)(v57 + 48) = v9;
      if ( !v56 || v57 == -8 )
        goto LABEL_122;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v57 + 8));
  }
  else
  {
    CInFlightEntry::Release((CInFlightEntry *)v9);
  }
LABEL_122:
  if ( v48 && v49 != -16 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v49 + 16));
  updated = CacheEntryAtCursor;
LABEL_126:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 26, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800841e0  push    rbp
0x1800841e2  push    rbx
0x1800841e3  push    rsi
0x1800841e4  push    rdi
0x1800841e5  push    r12
0x1800841e7  push    r13
0x1800841e9  push    r14
0x1800841eb  push    r15
0x1800841ed  lea     rbp, [rsp-78h]
0x1800841f2  sub     rsp, 178h
0x1800841f9  mov     rax, cs:__security_cookie
0x180084200  xor     rax, rsp
0x180084203  mov     [rbp+0B0h+var_50], rax
0x180084207  xorps   xmm0, xmm0
0x18008420a  mov     [rbp+0B0h+var_130], rdx
0x18008420e  mov     rdi, rdx
0x180084211  mov     qword ptr [rbp+0B0h+var_F8.dwLowDateTime], r8
0x180084215  xor     edx, edx
0x180084217  mov     [rbp+0B0h+var_128], r9d
0x18008421b  xor     eax, eax
0x18008421d  mov     [rsp+1B0h+var_140], rcx
0x180084222  mov     [rbp+0B0h+var_60], rax
0x180084226  mov     r12d, r9d
0x180084229  mov     r13, r8
0x18008422c  mov     [rsp+1B0h+var_164], edx
0x180084230  mov     rsi, rcx
0x180084233  mov     [rbp+0B0h+var_108], rdx
0x180084237  mov     r14d, edx
0x18008423a  mov     [rbp+0B0h+var_120], rdx
0x18008423e  mov     [rsp+1B0h+var_14C], edx
0x180084242  mov     r15d, edx
0x180084245  mov     [rsp+1B0h+var_150], edx
0x180084249  mov     ebx, edx
0x18008424b  mov     [rsp+1B0h+var_160], rdx
0x180084250  movups  xmmword ptr [rbp+0B0h+var_F0], xmm0
0x180084254  mov     [rsp+1B0h+var_16C], edx
0x180084258  movups  xmmword ptr [rbp+0B0h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18008425c  mov     [rbp+0B0h+var_124], edx
0x18008425f  movups  [rbp+0B0h+var_D0], xmm0
0x180084263  movups  [rbp+0B0h+var_C0], xmm0
0x180084267  movups  [rbp+0B0h+var_B0], xmm0
0x18008426b  movups  [rbp+0B0h+pvData], xmm0
0x18008426f  movups  xmmword ptr [rbp+0B0h+lpMem], xmm0
0x180084273  movups  xmmword ptr [rbp+0B0h+var_80], xmm0
0x180084277  movups  xmmword ptr [rbp+0B0h+var_70], xmm0
0x18008427b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180084282  jz      short loc_1800842AE
0x180084284  mov     dword ptr [rsp+1B0h+psetinfo], r9d
0x180084289  mov     edx, 18h
0x18008428e  mov     qword ptr [rsp+1B0h+grbit], r8
0x180084293  mov     ecx, 40Ch
0x180084298  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x18008429f  mov     qword ptr [rsp+1B0h+cbData], rdi
0x1800842a4  mov     r9, rsi
0x1800842a7  call    WPP_SF_qSqd
0x1800842ac  xor     edx, edx
0x1800842ae  test    r13, r13
0x1800842b1  jz      short loc_1800842CC
0x1800842b3  mov     ecx, 98h
0x1800842b8  mov     rax, r13
0x1800842bb  nop     dword ptr [rax+rax+00h]
0x1800842c0  mov     [rax], bl
0x1800842c2  lea     rax, [rax+1]
0x1800842c6  sub     rcx, 1
0x1800842ca  jnz     short loc_1800842C0
0x1800842cc  mov     eax, 1
0x1800842d1  mov     [rsp+1B0h+var_134], edx
0x1800842d5  test    [rsi+20h], al
0x1800842d8  jz      loc_1800852AD
0x1800842de  mov     rdi, [rsi+28h]
0x1800842e2  lea     rbx, [rdi+20h]
0x1800842e6  test    rbx, rbx
0x1800842e9  jz      loc_1800852CD
0x1800842ef  mov     rcx, rbx; lpCriticalSection
0x1800842f2  call    cs:__imp_EnterCriticalSection
0x1800842f8  mov     edi, [rdi+60h]
0x1800842fb  mov     rcx, rbx; lpCriticalSection
0x1800842fe  call    cs:__imp_LeaveCriticalSection
0x180084304  xor     edx, edx
0x180084306  mov     eax, 1
0x18008430b  mov     [rsp+1B0h+var_154], edi
0x18008430f  test    r12b, 2
0x180084313  jz      loc_18008506F
0x180084319  mov     [rsp+1B0h+var_144], eax
0x18008431d  mov     eax, r12d
0x180084320  and     eax, 1
0x180084323  mov     [rsp+1B0h+var_148], eax
0x180084327  jnz     loc_18008510E
0x18008432d  mov     rcx, [rsi+28h]; this
0x180084331  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x180084336  mov     rdi, [rbp+0B0h+var_130]
0x18008433a  mov     r12d, eax
0x18008433d  mov     [rsp+1B0h+var_170], eax
0x180084341  test    eax, eax
0x180084343  js      loc_1800852D5
0x180084349  xor     r10d, r10d
0x18008434c  test    rdi, rdi
0x18008434f  jz      loc_1800843CD
0x180084355  xor     edx, edx
0x180084357  lea     r11, qword_180226530
0x18008435e  mov     r9, rdi
0x180084361  cmp     [rdi], dx
0x180084364  jz      short loc_18008439B
0x180084366  cmp     edx, 3
0x180084369  jnb     short loc_18008439B
0x18008436b  movzx   ecx, word ptr [r9]
0x18008436f  add     r9, 2
0x180084373  rol     r10d, 1
0x180084376  movzx   eax, cl
0x180084379  xor     r10d, [r11+rax*4]
0x18008437d  mov     eax, ecx
0x18008437f  shr     rax, 8
0x180084383  rol     r10d, 1
0x180084386  xor     r10d, [r11+rax*4]
0x18008438a  lea     eax, [rdx+1]
0x18008438d  cmp     ecx, 2Fh ; '/'
0x180084390  cmovnz  eax, edx
0x180084393  mov     edx, eax
0x180084395  cmp     [r9], r14w
0x180084399  jnz     short loc_180084366
0x18008439b  xor     eax, eax
0x18008439d  xor     r8d, r8d
0x1800843a0  movzx   edx, word ptr [r9]
0x1800843a4  rol     eax, 1
0x1800843a6  movzx   ecx, dl
0x1800843a9  xor     eax, [r11+rcx*4]
0x1800843ad  mov     ecx, edx
0x1800843af  shr     rcx, 8
0x1800843b3  rol     eax, 1
0x1800843b5  xor     eax, [r11+rcx*4]
0x1800843b9  test    dx, dx
0x1800843bc  jz      short loc_1800843CF
0x1800843be  add     r9, 2
0x1800843c2  inc     r8d
0x1800843c5  cmp     r8d, 0FFFFFFFFh
0x1800843c9  jb      short loc_1800843A0
0x1800843cb  jmp     short loc_1800843CF
0x1800843cd  xor     eax, eax
0x1800843cf  mov     ebx, r10d
0x1800843d2  shl     rbx, 1Fh
0x1800843d6  mov     ecx, eax
0x1800843d8  xor     rbx, rcx
0x1800843db  mov     [rsp+78h], rbx
0x1800843e0  cmp     [rsp+1B0h+var_144], r14d
0x1800843e5  jz      loc_180084C7D
0x1800843eb  mov     rax, [rsi+28h]
0x1800843ef  xor     esi, esi
0x1800843f1  mov     [rsp+1B0h+var_158], r14d
0x1800843f6  mov     r15, [rax+90h]
0x1800843fd  mov     [rbp+0B0h+var_110], r15
0x180084401  mov     [rsp+1B0h+var_164], r14d
0x180084406  mov     rbx, [r15+40h]
0x18008440a  lea     r13, [r15+10h]
0x18008440e  mov     [rbp+0B0h+lpCriticalSection], r13
0x180084412  lea     rdi, [rbx+8]
0x180084416  test    rdi, rdi
0x180084419  jz      short loc_180084429
0x18008441b  mov     rcx, rdi; lpCriticalSection
0x18008441e  call    cs:__imp_EnterCriticalSection
0x180084424  mov     esi, 1
0x180084429  mov     r14, [rbx+30h]
0x18008442d  test    r14, r14
0x180084430  jz      loc_180084BBD
0x180084436  mov     rax, [r14+8]
0x18008443a  xor     r12d, r12d
0x18008443d  mov     [rbx+30h], rax
0x180084441  mov     [r14+8], r12
0x180084445  inc     dword ptr [rbx+3Ch]
0x180084448  mov     [rsp+1B0h+var_170], r12d
0x18008444d  test    esi, esi
0x18008444f  jz      short loc_18008445F
0x180084451  test    rdi, rdi
0x180084454  jz      short loc_18008445F
0x180084456  mov     rcx, rdi; lpCriticalSection
0x180084459  call    cs:__imp_LeaveCriticalSection
0x18008445f  test    r12d, r12d
0x180084462  js      loc_180084A7E
0x180084468  mov     rax, [rsp+78h]
0x18008446d  mov     dword ptr [r14+18h], 0
0x180084475  mov     [r14+10h], rax
0x180084479  test    r13, r13
0x18008447c  jz      short loc_18008448F
0x18008447e  mov     rcx, r13; lpCriticalSection
0x180084481  call    cs:__imp_EnterCriticalSection
0x180084487  mov     [rsp+1B0h+var_158], 1
0x18008448f  mov     rax, [r15+38h]
0x180084493  mov     [rbp+0B0h+var_100], r14
0x180084497  lock inc dword ptr [rax+8]
0x18008449b  mov     rbx, [rax]
0x18008449e  cmp     dword ptr [rbx+2Ch], 0
0x1800844a2  jz      short loc_1800844D9
0x1800844a4  mov     rsi, [rbx+10h]
0x1800844a8  mov     rax, [rbx+48h]
0x1800844ac  lea     r8, [rsi+20h]
0x1800844b0  lea     rdx, [rbp+0B0h+var_100]
0x1800844b4  mov     rcx, rbx
0x1800844b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844bc  test    eax, eax
0x1800844be  jnz     loc_180084996
0x1800844c4  mov     rax, [rsi+8]
0x1800844c8  test    rax, rax
0x1800844cb  jnz     loc_180084A18
0x1800844d1  mov     r12d, 2
0x1800844d7  jmp     short loc_1800844DE
0x1800844d9  xor     esi, esi
0x1800844db  xor     r12d, r12d
0x1800844de  mov     rax, [rbx+50h]
0x1800844e2  mov     edx, 28h ; '('
0x1800844e7  mov     rcx, rbx
0x1800844ea  mov     r13, rbx
0x1800844ed  mov     r15d, 10h
0x1800844f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844f8  mov     [rsp+48h], rax
0x1800844fd  mov     rdi, rax
0x180084500  test    rax, rax
0x180084503  jz      loc_180084B9D
0x180084509  xorps   xmm0, xmm0
0x18008450c  movups  xmmword ptr [rax], xmm0
0x18008450f  movups  xmmword ptr [rax+10h], xmm0
0x180084513  inc     dword ptr [rbx+2Ch]
0x180084516  test    r12d, r12d
0x180084519  jnz     loc_180084B41
0x18008451f  mov     [r15+rbx], rax
0x180084523  mov     [rax], rbx
0x180084526  mov     dword ptr [rbx+30h], 1
0x18008452d  mov     rax, [rbp+0B0h+var_100]
0x180084531  mov     r13, [rbp+0B0h+lpCriticalSection]
0x180084535  mov     r15, [rbp+0B0h+var_110]
0x180084539  mov     [rdi+20h], rax
0x18008453d  add     rdi, 20h ; ' '
0x180084541  jz      loc_180084B9D
0x180084547  cmp     r12d, 1
0x18008454b  jz      loc_180084C49
0x180084551  mov     eax, [rsp+1B0h+var_154]
0x180084555  mov     [rsp+1B0h+var_154], eax
0x180084559  mov     rax, [rbp+0B0h+var_100]
0x18008455d  lock inc dword ptr [rax]
0x180084560  mov     rax, [rdi]
0x180084563  lock inc dword ptr [rax]
0x180084566  mov     rbx, [rdi]
0x180084569  xor     r12d, r12d
0x18008456c  mov     [rsp+1B0h+var_160], rbx
0x180084571  mov     eax, 0FFFFFFFFh
0x180084576  mov     [rsp+1B0h+var_170], r12d
0x18008457b  lock xadd [r14], eax
0x180084580  cmp     eax, 1
0x180084583  jz      loc_180084F81
0x180084589  xor     r14d, r14d
0x18008458c  inc     dword ptr [rbx+18h]
0x18008458f  test    r13, r13
0x180084592  jz      short loc_1800845AC
0x180084594  cmp     [rsp+1B0h+var_158], 0
0x180084599  jz      short loc_1800845AC
0x18008459b  mov     rcx, r13; lpCriticalSection
0x18008459e  call    cs:__imp_LeaveCriticalSection
0x1800845a4  mov     [rsp+1B0h+var_158], 0
0x1800845ac  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800845b0  call    cs:__imp_EnterCriticalSection
0x1800845b6  lea     rcx, [r15+8]; SRWLock
0x1800845ba  call    cs:__imp_AcquireSRWLockShared
0x1800845c0  xor     ebx, ebx
0x1800845c2  test    r14, r14
0x1800845c5  jz      short loc_18008461D
0x1800845c7  mov     rdi, [r15+40h]
0x1800845cb  xor     r15d, r15d
0x1800845ce  mov     [r14+8], r15
0x1800845d2  lea     rsi, [rdi+8]
0x1800845d6  test    rsi, rsi
0x1800845d9  jz      short loc_1800845EA
0x1800845db  mov     rcx, rsi; lpCriticalSection
0x1800845de  call    cs:__imp_EnterCriticalSection
0x1800845e4  mov     r15d, 1
0x1800845ea  dec     dword ptr [rdi+3Ch]
0x1800845ed  mov     ecx, [rdi+38h]
0x1800845f0  mov     eax, ecx
0x1800845f2  sub     eax, [rdi+3Ch]
0x1800845f5  cmp     eax, [rdi+40h]
0x1800845f8  ja      loc_180085240
0x1800845fe  mov     rax, [rdi+30h]
0x180084602  mov     [r14+8], rax
0x180084606  mov     [rdi+30h], r14
0x18008460a  test    r15d, r15d
0x18008460d  jz      short loc_18008461D
0x18008460f  test    rsi, rsi
0x180084612  jz      short loc_18008461D
0x180084614  mov     rcx, rsi; lpCriticalSection
0x180084617  call    cs:__imp_LeaveCriticalSection
0x18008461d  test    rbx, rbx
0x180084620  jz      short loc_18008462A
0x180084622  mov     rcx, rbx; this
0x180084625  call    ?Release@CInFlightEntry@@QEAAKXZ; CInFlightEntry::Release(void)
0x18008462a  cmp     [rsp+1B0h+var_158], 0
0x18008462f  jz      short loc_18008463F
0x180084631  test    r13, r13
0x180084634  jz      short loc_18008463F
0x180084636  mov     rcx, r13; lpCriticalSection
0x180084639  call    cs:__imp_LeaveCriticalSection
0x18008463f  mov     r15, [rsp+1B0h+var_160]
0x180084644  mov     rsi, [rsp+1B0h+var_140]
0x180084649  mov     r13, qword ptr [rbp+0B0h+var_F8.dwLowDateTime]
  ... truncated ...
```
