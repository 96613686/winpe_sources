# WapQueryConnectionManager

- ea: `0x180025860`
- end: `0x1800264fc`
- name: `WapQueryConnectionManager`
- size: `3228`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023bf0`
- `0x180024eb0`
- `0x180025860`

## callees

- `0x180013820`
- `0x180014f30`
- `0x180021840`
- `0x1800223bc`
- `0x180023324`
- `0x180025860`
- `0x180026504`
- `0x180026544`
- `0x18002e460`
- `0x1800391c0`
- `0x18005cfe8`
- `0x18005d8e8`
- `0x180065850`
- `0x1800722f0`
- `0x180072c70`
- `0x180091678`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025acc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180025acc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800262c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800262c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025c1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180025c1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025998`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025998`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800259b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025b79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025eb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800259b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025b79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025eb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025ec5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025ec5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002612c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002612c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025cb6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180025cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800262b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800262eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800262eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180025c5d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180025c5d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800262a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800262a1`
- `ntdll!RtlDowncaseUnicodeChar` at `0x180026253`
- `ntdll!RtlDowncaseUnicodeChar` at `0x18002638d`
- `ntdll!RtlDowncaseUnicodeChar` at `0x180026253`
- `ntdll!RtlDowncaseUnicodeChar` at `0x18002638d`
- `ntdll!RtlCompareUnicodeStrings` at `0x180025aa9`
- `ntdll!RtlCompareUnicodeStrings` at `0x180025f38`
- `ntdll!RtlCompareUnicodeStrings` at `0x180025aa9`
- `ntdll!RtlCompareUnicodeStrings` at `0x180025f38`

## pseudocode

```c
__int64 __fastcall WapQueryConnectionManager(
        __int64 a1,
        BOOL a2,
        int a3,
        void *a4,
        __int64 a5,
        int a6,
        char a7,
        char a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int a12,
        volatile signed __int32 **a13,
        volatile signed __int32 **a14,
        __int64 *a15)
{
  unsigned __int8 v15; // r15
  __int64 v17; // r10
  volatile signed __int32 *v18; // r13
  __int64 v19; // r8
  unsigned int v20; // r14d
  __int64 v21; // rdi
  WCHAR *v22; // rsi
  int v23; // ebx
  WCHAR v24; // cx
  WCHAR v25; // ax
  RTL_SRWLOCK *v26; // rsi
  volatile signed __int32 *v27; // rbx
  unsigned int ConnectionManager; // edi
  __int64 v29; // r15
  int v31; // r8d
  int v32; // edx
  int v33; // r13d
  _QWORD *v34; // r12
  _QWORD *i; // r14
  __int64 v36; // rdx
  int v37; // edx
  char v38; // r15
  __int64 v39; // rcx
  volatile signed __int32 *v40; // r14
  volatile signed __int32 *v41; // r13
  volatile signed __int32 **v42; // r12
  volatile signed __int32 *v43; // rax
  volatile signed __int32 *k; // rax
  __int64 v45; // rcx
  char *v46; // rax
  char *v47; // r14
  PTP_WORK ThreadpoolWork; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  _QWORD *v52; // rcx
  __int64 v53; // rax
  unsigned int v54; // ecx
  __int64 v55; // rax
  int v56; // eax
  LPVOID v57; // rax
  volatile signed __int32 ***v58; // rcx
  bool v59; // zf
  int v60; // r15d
  __int64 v61; // rsi
  WCHAR *v62; // r14
  int v63; // edi
  WCHAR v64; // cx
  WCHAR v65; // ax
  int v66; // eax
  _QWORD *j; // r14
  __int64 v68; // rdx
  size_t v69; // r15
  unsigned __int64 v70; // rdi
  __int64 v71; // rcx
  __int64 (*v72)(void); // rax
  __int64 v73; // rax
  unsigned __int64 v74; // r14
  volatile signed __int32 *Heap; // rax
  const void *v76; // rdx
  int v77; // ecx
  int v78; // ecx
  unsigned int v79; // eax
  volatile signed __int32 *v80; // r14
  _QWORD *v81; // rcx
  int v82; // r14d
  unsigned int v83; // eax
  __int64 v84; // r14
  HANDLE *v85; // r12
  struct _TP_WORK *v86; // rcx
  int v87; // edx
  unsigned int LastError; // eax
  __int64 v89; // rdx
  __int64 v90; // r9
  int v91; // [rsp+20h] [rbp-E0h]
  int v92; // [rsp+30h] [rbp-D0h]
  bool v94; // [rsp+84h] [rbp-7Ch]
  volatile signed __int32 *v95; // [rsp+88h] [rbp-78h]
  volatile signed __int32 *v96; // [rsp+88h] [rbp-78h]
  __int64 Endpoint; // [rsp+90h] [rbp-70h]
  volatile signed __int32 *v98; // [rsp+98h] [rbp-68h] BYREF
  int v99; // [rsp+A0h] [rbp-60h]
  int v100; // [rsp+A4h] [rbp-5Ch]
  int v101; // [rsp+A8h] [rbp-58h]
  __int64 v102; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v103; // [rsp+B8h] [rbp-48h] BYREF
  BOOL v104; // [rsp+C0h] [rbp-40h]
  __int64 v105; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v106; // [rsp+D0h] [rbp-30h]
  __int64 v107; // [rsp+D8h] [rbp-28h]
  __int64 v108; // [rsp+E0h] [rbp-20h]
  LPVOID lpMem; // [rsp+E8h] [rbp-18h]
  volatile signed __int32 **v110; // [rsp+F0h] [rbp-10h]
  volatile signed __int32 **v111; // [rsp+F8h] [rbp-8h]
  __int64 *v112; // [rsp+100h] [rbp+0h]
  void *Src[2]; // [rsp+108h] [rbp+8h] BYREF

  v15 = a8;
  v17 = a10;
  v18 = 0;
  v101 = a6;
  v100 = a9;
  v99 = a12;
  v110 = a13;
  v111 = a14;
  v19 = a11;
  v94 = a2;
  LOBYTE(a2) = 1;
  v98 = (volatile signed __int32 *)a1;
  v112 = a15;
  Src[0] = a4;
  v108 = a5;
  v107 = a10;
  v106 = a11;
  Endpoint = 0;
  v104 = a2;
  LODWORD(v103) = 0;
  lpMem = 0;
  LODWORD(v105) = 0;
  if ( a8 )
    v104 = a7 != 0;
  v20 = *(_DWORD *)(a1 + 36);
  v21 = a5;
  LODWORD(v102) = v20;
  v22 = (WCHAR *)a4;
  v23 = 0;
  if ( a5 )
  {
    do
    {
      v24 = *v22;
      --v21;
      if ( *v22 >= 0x80u )
        v25 = RtlDowncaseUnicodeChar(v24);
      else
        v25 = *((unsigned __int8 *)WaToLowerTable + (unsigned __int8)v24);
      ++v22;
      v23 = v25 + 127 * v23;
    }
    while ( v21 );
    v18 = 0;
    v19 = v106;
    v17 = v107;
  }
  if ( a8 )
  {
    v60 = *(_DWORD *)(a1 + 36);
    v61 = v19;
    v62 = (WCHAR *)v17;
    v63 = 0;
    if ( v19 )
    {
      do
      {
        v64 = *v62;
        --v61;
        if ( *v62 >= 0x80u )
          v65 = RtlDowncaseUnicodeChar(v64);
        else
          v65 = *((unsigned __int8 *)WaToLowerTable + (unsigned __int8)v64);
        ++v62;
        v63 = v65 + 127 * v63;
      }
      while ( v61 );
      v18 = 0;
    }
    v20 = v102;
    LODWORD(v105) = v63 + v99 + v100 + 1;
    v66 = v60 & v105;
    v15 = a8;
    LODWORD(v103) = v66;
  }
  v26 = (RTL_SRWLOCK *)(a1 + 80);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 80));
  if ( !*(_BYTE *)(a1 + 24) )
  {
    v27 = 0;
    ConnectionManager = 995;
    v29 = 0;
    goto LABEL_11;
  }
  v31 = v101;
  ConnectionManager = 0;
  LODWORD(v102) = v15;
  v32 = a3;
  v33 = v23 + v101 + a3;
  v34 = (_QWORD *)(16 * ((v33 & v20) + 6LL) + a1);
  for ( i = (_QWORD *)*v34; i != v34; i = (_QWORD *)*i )
  {
    v27 = (volatile signed __int32 *)(i - 1);
    if ( *((_DWORD *)i - 1) == v33 && !*((_DWORD *)v27 + 16) && *((_DWORD *)v27 + 17) == v32 )
    {
      v36 = *((_QWORD *)v27 + 11);
      if ( v36 == v108 && *((_DWORD *)v27 + 18) == v31 )
      {
        LOBYTE(v91) = 1;
        if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v27 + 10), v36, Src[0], v108, v91) )
        {
          _InterlockedIncrement(v27 + 6);
          goto LABEL_31;
        }
        v31 = v101;
      }
      v32 = a3;
    }
  }
  v27 = 0;
LABEL_31:
  if ( v15 )
  {
    Endpoint = WapFindEndpoint((_DWORD)v98, 1, v100, v107, v106, v99, v103, v105);
    v37 = (unsigned __int8)v102;
    if ( Endpoint )
      v37 = 0;
    LODWORD(v102) = v37;
  }
  else
  {
    LOBYTE(v37) = v102;
  }
  if ( v27 )
  {
    v38 = 0;
    if ( !(_BYTE)v37 )
      goto LABEL_35;
  }
  ReleaseSRWLockShared(v26);
  AcquireSRWLockExclusive(v26);
  if ( !*((_BYTE *)v98 + 24) )
  {
    v18 = 0;
    ConnectionManager = 995;
LABEL_157:
    v29 = Endpoint;
LABEL_80:
    ReleaseSRWLockExclusive(v26);
    goto LABEL_12;
  }
  if ( v27 )
    goto LABEL_114;
  for ( j = (_QWORD *)*v34; ; j = (_QWORD *)*j )
  {
    if ( j == v34 )
      goto LABEL_100;
    v27 = (volatile signed __int32 *)(j - 1);
    if ( *((_DWORD *)j - 1) == v33 && !*((_DWORD *)v27 + 16) && *((_DWORD *)v27 + 17) == a3 )
    {
      v68 = *((_QWORD *)v27 + 11);
      if ( v68 == v108 && *((_DWORD *)v27 + 18) == v101 )
      {
        LOBYTE(v91) = 1;
        if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v27 + 10), v68, Src[0], v108, v91) )
          break;
      }
    }
  }
  _InterlockedIncrement(v27 + 6);
  if ( j != (_QWORD *)8 )
    goto LABEL_114;
LABEL_100:
  v69 = 2 * v108;
  v70 = (2 * v108 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
  v71 = (unsigned int)(a3 - 1);
  if ( a3 == 1 )
  {
    v72 = WaHttpEndpointDispatch[0];
    goto LABEL_103;
  }
  if ( a3 == 2 )
  {
    v72 = WaHttpsEndpointDispatch[0];
LABEL_103:
    v73 = v72();
    goto LABEL_104;
  }
  v73 = 0;
LABEL_104:
  v74 = v70 + v73;
  Heap = (volatile signed __int32 *)WxAllocateHeapEx(v71, v70 + v73 + 104);
  v27 = Heap;
  if ( !Heap )
  {
    ConnectionManager = 8;
LABEL_159:
    v29 = Endpoint;
    v27 = 0;
    v18 = 0;
    goto LABEL_80;
  }
  memset_0((void *)Heap, 0, v74 + 104);
  v76 = Src[0];
  *v27 = 1346653765;
  *((_DWORD *)v27 + 1) = v33;
  *((_QWORD *)v27 + 2) = v27 + 2;
  *((_QWORD *)v27 + 1) = v27 + 2;
  *((_DWORD *)v27 + 6) = 1;
  *((_QWORD *)v27 + 7) = v27 + 12;
  *((_QWORD *)v27 + 6) = v27 + 12;
  *((_DWORD *)v27 + 17) = a3;
  *((_DWORD *)v27 + 18) = v101;
  *((_QWORD *)v27 + 11) = v108;
  *((_DWORD *)v27 + 16) = 0;
  *((_QWORD *)v27 + 10) = v27 + 26;
  memcpy_0((void *)(v27 + 26), v76, v69);
  *(_WORD *)(v69 + *((_QWORD *)v27 + 10)) = 0;
  v77 = *((_DWORD *)v27 + 17);
  *((_QWORD *)v27 + 12) = (char *)v27 + v70 + 104;
  v78 = v77 - 1;
  if ( v78 )
  {
    if ( v78 != 1 )
    {
      ConnectionManager = 87;
      goto LABEL_165;
    }
    v79 = ((__int64 (__fastcall *)(volatile signed __int32 *))off_1800AC068[0])(v27);
  }
  else
  {
    v79 = ((__int64 (__fastcall *)(volatile signed __int32 *))off_1800AC050[0])(v27);
  }
  ConnectionManager = v79;
  if ( v79 )
  {
LABEL_165:
    _InterlockedDecrement(v27 + 6);
    Src[0] = (void *)v27;
    WxFreeHeapEx(Src);
    goto LABEL_159;
  }
  v80 = v98;
  *((_QWORD *)v27 + 5) = v98;
  _InterlockedIncrement(v80 + 7);
  v81 = (_QWORD *)*v34;
  if ( *(_QWORD **)(*v34 + 8LL) != v34 )
    goto LABEL_129;
  *((_QWORD *)v27 + 1) = v81;
  *((_QWORD *)v27 + 2) = v34;
  v81[1] = v27 + 2;
  *v34 = v27 + 2;
  if ( *((_BYTE *)v80 + 44) != (_BYTE)v79 && *((_BYTE *)v80 + 92) == (_BYTE)v79 )
  {
    v89 = *((unsigned int *)v80 + 10);
    v90 = *((unsigned int *)v80 + 22);
    *((_BYTE *)v80 + 92) = 1;
    WaSetTimer(v80 + 12, v89, v89, v90);
  }
  _InterlockedIncrement(v27 + 6);
LABEL_114:
  v38 = 1;
  if ( !(_BYTE)v102 )
  {
LABEL_35:
    v39 = Endpoint;
LABEL_36:
    v40 = v98;
LABEL_37:
    v41 = (volatile signed __int32 *)v39;
    if ( v104 )
      v41 = v27;
    v42 = (volatile signed __int32 **)(v41 + 12);
    if ( !v38 )
    {
      v43 = *v42;
      v29 = Endpoint;
      while ( 1 )
      {
        if ( v43 == (volatile signed __int32 *)v42 )
        {
          v95 = 0;
          goto LABEL_47;
        }
        v95 = v43 - 4;
        if ( *((_QWORD *)v43 + 10) == Endpoint )
          break;
        v43 = *(volatile signed __int32 **)v43;
      }
      _InterlockedIncrement(v43 - 3);
      if ( v43 != (volatile signed __int32 *)16 )
      {
        v18 = v43 - 4;
        goto LABEL_11;
      }
LABEL_47:
      ReleaseSRWLockShared(v26);
      AcquireSRWLockExclusive(v26);
      if ( !*((_BYTE *)v40 + 24) )
      {
        v18 = v95;
        ConnectionManager = 995;
        goto LABEL_80;
      }
      v39 = Endpoint;
      v38 = 1;
    }
    for ( k = *v42; ; k = *(volatile signed __int32 **)k )
    {
      if ( k == (volatile signed __int32 *)v42 )
      {
        v96 = 0;
        goto LABEL_53;
      }
      v96 = k - 4;
      if ( *((_QWORD *)k + 10) == v39 )
        break;
    }
    _InterlockedIncrement(k - 3);
    if ( k == (volatile signed __int32 *)16 )
    {
LABEL_53:
      if ( v94 )
      {
        v103 = 0;
        v98 = 0;
        v105 = 0;
        v102 = 0;
        v83 = WapQueryGlobalEndpointManager(&v103);
        v84 = v103;
        ConnectionManager = v83;
        if ( !v83 )
        {
          ConnectionManager = WapQueryConnectionManager(
                                v103,
                                0,
                                a3,
                                Src[0],
                                v108,
                                v101,
                                a7,
                                a8,
                                v100,
                                v107,
                                v106,
                                v99,
                                (__int64)&v98,
                                (__int64)&v105,
                                (__int64)&v102);
          if ( !ConnectionManager )
          {
            lpMem = (LPVOID)v98;
            v98 = 0;
          }
        }
        if ( v84 )
          WaDereferenceEndpointManager(v84);
        if ( v105 )
          ((void (*)(void))WaDereferenceEndpoint)();
        if ( v102 )
          ((void (*)(void))WaDereferenceEndpoint)();
        if ( ConnectionManager )
        {
          v18 = v96;
LABEL_79:
          v59 = v38 == 0;
          v29 = Endpoint;
          if ( v59 )
          {
LABEL_11:
            ReleaseSRWLockShared(v26);
            goto LABEL_12;
          }
          goto LABEL_80;
        }
      }
      v45 = (__int64)v27;
      if ( !v104 )
        v45 = 0;
      v106 = v45;
      v46 = (char *)WxAllocateHeapEx(v45, 680);
      v47 = v46;
      if ( !v46 )
      {
        ConnectionManager = 8;
LABEL_78:
        v18 = 0;
        goto LABEL_79;
      }
      memset_0(v46, 0, 0x2A8u);
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v47 + 32), 0xFA0u) )
      {
        memset_0(v47 + 272, 0, 0x40u);
        *((_DWORD *)v47 + 68) = 1331122260;
        ThreadpoolWork = CreateThreadpoolWork(WapTpWorkItemCallback, v47 + 272, &WaTpEnvironment);
        *((_QWORD *)v47 + 35) = ThreadpoolWork;
        v52 = v47 + 304;
        Src[0] = v47 + 304;
        if ( ThreadpoolWork )
        {
          *((_QWORD *)v47 + 37) = v47;
          *((_QWORD *)v47 + 36) = &WapBackgroundConnectionCallback;
          *v52 = 0;
          ConnectionManager = WaGetCurrentThreadToken(v52, v49, v50, v51);
          if ( !ConnectionManager )
          {
            *(_OWORD *)Src = 0;
            if ( EventActivityIdControl(1u, (LPGUID)(v47 + 312)) )
              *(_OWORD *)(v47 + 312) = 0;
            v47[328] = 1;
            goto LABEL_63;
          }
          v85 = (HANDLE *)Src[0];
          *(_QWORD *)Src[0] = 0;
        }
        else
        {
          ConnectionManager = WaGetLastError();
          if ( !ConnectionManager )
          {
LABEL_63:
            *(_DWORD *)v47 = 1380404547;
            *((_DWORD *)v47 + 1) = 1;
            *((_QWORD *)v47 + 3) = v47 + 16;
            *((_QWORD *)v47 + 2) = v47 + 16;
            *((_QWORD *)v47 + 10) = v41;
            _InterlockedIncrement(v41 + 6);
            v53 = v106;
            *((_QWORD *)v47 + 11) = v106;
            if ( v53 )
              _InterlockedIncrement((volatile signed __int32 *)(v53 + 24));
            *((_QWORD *)v47 + 12) = Endpoint;
            if ( Endpoint )
              _InterlockedIncrement((volatile signed __int32 *)(Endpoint + 24));
            v54 = 0x80000000;
            *((_QWORD *)v47 + 14) = v47 + 104;
            *((_QWORD *)v47 + 13) = v47 + 104;
            *((_QWORD *)v47 + 16) = v47 + 120;
            *((_QWORD *)v47 + 15) = v47 + 120;
            *((_QWORD *)v47 + 18) = v47 + 136;
            *((_QWORD *)v47 + 17) = v47 + 136;
            *((_QWORD *)v47 + 20) = v47 + 152;
            *((_QWORD *)v47 + 19) = v47 + 152;
            *((_QWORD *)v47 + 22) = v47 + 168;
            *((_QWORD *)v47 + 21) = v47 + 168;
            *((_QWORD *)v47 + 24) = v47 + 184;
            *((_QWORD *)v47 + 23) = v47 + 184;
            *((_QWORD *)v47 + 26) = v47 + 200;
            *((_QWORD *)v47 + 25) = v47 + 200;
            *((_QWORD *)v47 + 28) = v47 + 216;
            *((_QWORD *)v47 + 27) = v47 + 216;
            *((_QWORD *)v47 + 30) = v47 + 232;
            *((_QWORD *)v47 + 29) = v47 + 232;
            v55 = *((_QWORD *)v47 + 11);
            *((_DWORD *)v47 + 62) = -1;
            if ( v55 )
            {
              v56 = *(_DWORD *)(v55 + 68);
              if ( v56 == 1 )
              {
                v54 = -1879048192;
              }
              else if ( v56 == 2 )
              {
                v54 = -1342177280;
              }
              if ( a7 )
              {
                v54 |= 0x40000000u;
                if ( *(_DWORD *)(*((_QWORD *)v47 + 12) + 68LL) == 2 )
                  v54 |= 0x8000000u;
              }
            }
            else
            {
              v87 = *(_DWORD *)(*((_QWORD *)v47 + 12) + 68LL);
              if ( v87 == 1 )
              {
                v54 = -1879048192;
              }
              else if ( v87 == 2 )
              {
                v54 = -1744830464;
              }
            }
            v57 = lpMem;
            if ( lpMem )
            {
              _InterlockedIncrement((volatile signed __int32 *)lpMem + 1);
              *((_QWORD *)v47 + 84) = v57;
            }
            *((_DWORD *)v47 + 66) = 60000;
            v18 = (volatile signed __int32 *)v47;
            *((_DWORD *)v47 + 65) = v54;
            ConnectionManager = 0;
LABEL_75:
            v58 = (volatile signed __int32 ***)v42[1];
            if ( *v58 == v42 )
            {
              *((_QWORD *)v18 + 2) = v42;
              *((_QWORD *)v18 + 3) = v58;
              *v58 = (volatile signed __int32 **)(v18 + 4);
              v42[1] = v18 + 4;
              _InterlockedIncrement(v18 + 1);
              goto LABEL_77;
            }
LABEL_129:
            __fastfail(3u);
          }
          v85 = (HANDLE *)Src[0];
        }
        v86 = (struct _TP_WORK *)*((_QWORD *)v47 + 35);
        if ( v86 )
          CloseThreadpoolWork(v86);
        if ( *v85 )
          CloseHandle(*v85);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v47 + 32));
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v47);
        else
          HeapFree(g_hWxProcessHeap, 0, v47);
        v18 = v96;
      }
      else
      {
        v18 = 0;
        LastError = WaGetLastError();
        Src[0] = v47;
        ConnectionManager = LastError;
        WxFreeHeapEx(Src);
        if ( !ConnectionManager )
          goto LABEL_75;
        v18 = v96;
      }
LABEL_77:
      if ( !ConnectionManager )
        goto LABEL_79;
      goto LABEL_78;
    }
    v18 = k - 4;
    goto LABEL_157;
  }
  v82 = v103;
  Endpoint = WapFindEndpoint((_DWORD)v98, 1, v100, v107, v106, v99, v103, v105);
  v39 = Endpoint;
  v103 = Endpoint;
  if ( Endpoint )
    goto LABEL_36;
  v92 = v82;
  v40 = v98;
  ConnectionManager = WapCreateAndAddEndpoint((_DWORD)v98, 1, v100, v107, v106, v99, v92, v105, (__int64)&v103);
  if ( !ConnectionManager )
  {
    v39 = v103;
    Endpoint = v103;
    goto LABEL_37;
  }
  v29 = 0;
  v18 = 0;
  ReleaseSRWLockExclusive(v26);
LABEL_12:
  if ( lpMem )
    WaDereferenceConnectionManager(lpMem);
  if ( ConnectionManager )
  {
    if ( v18 )
      WaDereferenceConnectionManager((LPVOID)v18);
    if ( v27 )
      WaDereferenceEndpoint(v27);
    if ( v29 )
      WaDereferenceEndpoint(v29);
  }
  else
  {
    *v110 = v18;
    *v111 = v27;
    if ( v112 )
    {
      *v112 = v29;
    }
    else if ( v29 )
    {
      *(_QWORD *)(v29 + 32) = GetTickCount64();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 24), 0xFFFFFFFF) == 1 )
        WapDestroyEndpoint(v29);
    }
  }
  return ConnectionManager;
}

```

## disassembly

```asm
0x180025860  mov     [rsp-8+arg_8], rbx
0x180025865  push    rbp
0x180025866  push    rsi
0x180025867  push    rdi
0x180025868  push    r12
0x18002586a  push    r13
0x18002586c  push    r14
0x18002586e  push    r15
0x180025870  lea     rbp, [rsp-20h]
0x180025875  sub     rsp, 120h
0x18002587c  mov     rax, cs:__security_cookie
0x180025883  xor     rax, rsp
0x180025886  mov     [rbp+50h+var_38], rax
0x18002588a  mov     eax, [rbp+50h+arg_28]
0x180025890  xor     r11d, r11d
0x180025893  movzx   r15d, [rbp+50h+arg_38]
0x18002589b  mov     r12, rcx
0x18002589e  mov     r10, [rbp+50h+arg_48]
0x1800258a5  mov     r13d, r11d
0x1800258a8  mov     [rbp+50h+var_A8], eax
0x1800258ab  mov     eax, [rbp+50h+arg_40]
0x1800258b1  mov     [rbp+50h+var_AC], eax
0x1800258b4  mov     eax, [rbp+50h+arg_58]
0x1800258ba  mov     [rbp+50h+var_B0], eax
0x1800258bd  mov     rax, [rbp+50h+arg_60]
0x1800258c4  mov     [rbp+50h+var_60], rax
0x1800258c8  mov     rax, [rbp+50h+arg_68]
0x1800258cf  mov     [rbp+50h+var_58], rax
0x1800258d3  mov     rax, [rbp+50h+arg_70]
0x1800258da  mov     [rbp+50h+var_D0], r8d
0x1800258de  mov     r8, [rbp+50h+arg_50]
0x1800258e5  mov     [rbp+50h+var_CC], dl
0x1800258e8  mov     dl, 1
0x1800258ea  mov     [rbp+50h+var_B8], rcx
0x1800258ee  mov     rcx, [rbp+50h+arg_20]
0x1800258f5  mov     [rbp+50h+var_50], rax
0x1800258f9  mov     [rbp+50h+Src], r9
0x1800258fd  mov     [rbp+50h+var_70], rcx
0x180025901  mov     [rbp+50h+var_78], r10
0x180025905  mov     [rbp+50h+var_80], r8
0x180025909  mov     [rbp+50h+var_C0], r11
0x18002590d  mov     [rbp+50h+var_90], edx
0x180025910  mov     dword ptr [rbp+50h+var_98], r11d
0x180025914  mov     [rbp+50h+var_C8], r11
0x180025918  mov     [rbp+50h+lpMem], r11
0x18002591c  mov     dword ptr [rbp+50h+var_88], r11d
0x180025920  test    r15b, r15b
0x180025923  jnz     loc_1800263A5
0x180025929  mov     r14d, [r12+24h]
0x18002592e  mov     rdi, rcx
0x180025931  mov     dword ptr [rbp+50h+var_A0], r14d
0x180025935  mov     rsi, r9
0x180025938  lea     rdx, WaToLowerTable
0x18002593f  mov     ebx, r11d
0x180025942  test    rcx, rcx
0x180025945  jz      short loc_180025987
0x180025947  mov     r13d, 80h
0x18002594d  nop     dword ptr [rax]
0x180025950  movzx   ecx, word ptr [rsi]; Source
0x180025953  dec     rdi
0x180025956  cmp     cx, r13w
0x18002595a  jnb     loc_180026253
0x180025960  movzx   eax, cl
0x180025963  movzx   eax, byte ptr [rax+rdx]
0x180025967  imul    ebx, 7Fh
0x18002596a  add     rsi, 2
0x18002596e  movzx   eax, ax
0x180025971  add     ebx, eax
0x180025973  test    rdi, rdi
0x180025976  jnz     short loc_180025950
0x180025978  mov     r13, [rbp+50h+var_C8]
0x18002597c  xor     r11d, r11d
0x18002597f  mov     r8, [rbp+50h+var_80]
0x180025983  mov     r10, [rbp+50h+var_78]
0x180025987  test    r15b, r15b
0x18002598a  jnz     loc_180025E49
0x180025990  lea     rsi, [r12+50h]
0x180025995  mov     rcx, rsi; SRWLock
0x180025998  call    cs:__imp_AcquireSRWLockShared
0x18002599f  nop     dword ptr [rax+rax+00h]
0x1800259a4  cmp     byte ptr [r12+18h], 0
0x1800259aa  jnz     short loc_180025A26
0x1800259ac  xor     ebx, ebx
0x1800259ae  mov     edi, 3E3h
0x1800259b3  mov     r15d, ebx
0x1800259b6  mov     rcx, rsi; SRWLock
0x1800259b9  call    cs:__imp_ReleaseSRWLockShared
0x1800259c0  nop     dword ptr [rax+rax+00h]
0x1800259c5  mov     rax, [rbp+50h+lpMem]
0x1800259c9  test    rax, rax
0x1800259cc  jz      short loc_1800259D6
0x1800259ce  mov     rcx, rax; lpMem
0x1800259d1  call    WaDereferenceConnectionManager
0x1800259d6  test    edi, edi
0x1800259d8  jnz     loc_1800264CC
0x1800259de  mov     rax, [rbp+50h+var_60]
0x1800259e2  mov     [rax], r13
0x1800259e5  mov     rax, [rbp+50h+var_58]
0x1800259e9  mov     [rax], rbx
0x1800259ec  mov     rax, [rbp+50h+var_50]
0x1800259f0  test    rax, rax
0x1800259f3  jz      loc_180025AC3
0x1800259f9  mov     [rax], r15
0x1800259fc  mov     eax, edi
0x1800259fe  mov     rcx, [rbp+50h+var_38]
0x180025a02  xor     rcx, rsp; StackCookie
0x180025a05  call    __security_check_cookie
0x180025a0a  mov     rbx, [rsp+150h+arg_8]
0x180025a12  add     rsp, 120h
0x180025a19  pop     r15
0x180025a1b  pop     r14
0x180025a1d  pop     r13
0x180025a1f  pop     r12
0x180025a21  pop     rdi
0x180025a22  pop     rsi
0x180025a23  pop     rbp
0x180025a24  retn
0x180025a26  mov     r8d, [rbp+50h+var_A8]
0x180025a2a  movzx   edx, r15b
0x180025a2e  mov     ecx, r14d
0x180025a31  xor     edi, edi
0x180025a33  mov     dword ptr [rbp+50h+var_A0], edx
0x180025a36  mov     edx, [rbp+50h+var_D0]
0x180025a39  lea     r13d, [r8+rdx]
0x180025a3d  add     r13d, ebx
0x180025a40  mov     eax, r13d
0x180025a43  and     rcx, rax
0x180025a46  add     rcx, 6
0x180025a4a  shl     rcx, 4
0x180025a4e  add     r12, rcx
0x180025a51  mov     r14, [r12]
0x180025a55  cmp     r14, r12
0x180025a58  jz      loc_180025AFD
0x180025a5e  cmp     [r14-4], r13d
0x180025a62  lea     rbx, [r14-8]
0x180025a66  jnz     loc_18002632B
0x180025a6c  cmp     [rbx+40h], edi
0x180025a6f  jnz     loc_18002632B
0x180025a75  cmp     [rbx+44h], edx
0x180025a78  jnz     loc_18002632B
0x180025a7e  mov     rdx, [rbx+58h]
0x180025a82  mov     rax, [rbp+50h+var_70]
0x180025a86  cmp     rdx, rax
0x180025a89  jnz     loc_180026328
0x180025a8f  cmp     [rbx+48h], r8d
0x180025a93  jnz     loc_180026328
0x180025a99  mov     r8, [rbp+50h+Src]
0x180025a9d  mov     r9, rax
0x180025aa0  mov     rcx, [rbx+50h]
0x180025aa4  mov     byte ptr [rsp+150h+var_130], 1
0x180025aa9  call    cs:__imp_RtlCompareUnicodeStrings
0x180025ab0  nop     dword ptr [rax+rax+00h]
0x180025ab5  test    eax, eax
0x180025ab7  jnz     loc_180026324
0x180025abd  lock inc dword ptr [rbx+18h]
0x180025ac1  jmp     short loc_180025AFF
0x180025ac3  test    r15, r15
0x180025ac6  jz      loc_1800259FC
0x180025acc  call    cs:__imp_GetTickCount64
0x180025ad3  nop     dword ptr [rax+rax+00h]
0x180025ad8  mov     [r15+20h], rax
0x180025adc  mov     eax, 0FFFFFFFFh
0x180025ae1  lock xadd [r15+18h], eax
0x180025ae7  cmp     eax, 1
0x180025aea  jnz     loc_1800259FC
0x180025af0  mov     rcx, r15
0x180025af3  call    WapDestroyEndpoint
0x180025af8  jmp     loc_1800259FC
0x180025afd  xor     ebx, ebx
0x180025aff  mov     r14, [rbp+50h+var_B8]
0x180025b03  test    r15b, r15b
0x180025b06  jnz     loc_18002633D
0x180025b0c  mov     edx, dword ptr [rbp+50h+var_A0]
0x180025b0f  test    rbx, rbx
0x180025b12  jz      loc_180025EB3
0x180025b18  xor     r15b, r15b
0x180025b1b  test    dl, dl
0x180025b1d  jnz     loc_180025EB3
0x180025b23  mov     rcx, [rbp+50h+var_C0]
0x180025b27  mov     r14, [rbp+50h+var_B8]
0x180025b2b  cmp     byte ptr [rbp+50h+var_90], 0
0x180025b2f  mov     r13, rcx
0x180025b32  cmovnz  r13, rbx
0x180025b36  lea     r12, [r13+30h]
0x180025b3a  test    r15b, r15b
0x180025b3d  jnz     short loc_180025BA6
0x180025b3f  mov     rax, [r12]
0x180025b43  mov     r15, [rbp+50h+var_C0]
0x180025b47  cmp     rax, r12
0x180025b4a  jz      short loc_180025B70
0x180025b4c  lea     rdx, [rax-10h]
0x180025b50  mov     [rbp+50h+var_C8], rdx
0x180025b54  cmp     [rdx+60h], r15
0x180025b58  jnz     short loc_180025B6B
0x180025b5a  lock inc dword ptr [rdx+4]
0x180025b5e  test    rdx, rdx
0x180025b61  jz      short loc_180025B76
0x180025b63  mov     r13, rdx
0x180025b66  jmp     loc_1800259B6
0x180025b6b  mov     rax, [rax]
0x180025b6e  jmp     short loc_180025B47
0x180025b70  xor     edx, edx
0x180025b72  mov     [rbp+50h+var_C8], rdx
0x180025b76  mov     rcx, rsi; SRWLock
0x180025b79  call    cs:__imp_ReleaseSRWLockShared
0x180025b80  nop     dword ptr [rax+rax+00h]
0x180025b85  mov     rcx, rsi; SRWLock
0x180025b88  call    cs:__imp_AcquireSRWLockExclusive
0x180025b8f  nop     dword ptr [rax+rax+00h]
0x180025b94  cmp     byte ptr [r14+18h], 0
0x180025b99  jz      loc_18002647B
0x180025b9f  mov     rcx, [rbp+50h+var_C0]
0x180025ba3  mov     r15b, 1
0x180025ba6  mov     rax, [r12]
0x180025baa  cmp     rax, r12
0x180025bad  jz      loc_18002626B
0x180025bb3  lea     rdx, [rax-10h]
0x180025bb7  mov     [rbp+50h+var_C8], rdx
0x180025bbb  cmp     [rdx+60h], rcx
0x180025bbf  jnz     loc_180025F05
0x180025bc5  lock inc dword ptr [rdx+4]
0x180025bc9  test    rdx, rdx
0x180025bcc  jnz     loc_1800264C4
0x180025bd2  cmp     [rbp+50h+var_CC], 0
0x180025bd6  jnz     loc_18002613D
0x180025bdc  xor     eax, eax
0x180025bde  mov     rcx, rbx
0x180025be1  cmp     byte ptr [rbp+50h+var_90], al
0x180025be4  mov     edx, 2A8h
0x180025be9  cmovz   rcx, rax
0x180025bed  mov     [rbp+50h+var_80], rcx
0x180025bf1  call    WxAllocateHeapEx
0x180025bf6  mov     r14, rax
0x180025bf9  test    rax, rax
0x180025bfc  jz      loc_180026333
0x180025c02  xor     edx, edx; Val
0x180025c04  mov     r8d, 2A8h; Size
0x180025c0a  mov     rcx, rax; void *
0x180025c0d  call    memset_0
0x180025c12  lea     rcx, [r14+20h]; lpCriticalSection
0x180025c16  mov     edx, 0FA0h; dwSpinCount
0x180025c1b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025c22  nop     dword ptr [rax+rax+00h]
0x180025c27  test    eax, eax
0x180025c29  jz      loc_1800263FE
0x180025c2f  lea     rdi, [r14+110h]
0x180025c36  xor     edx, edx; Val
0x180025c38  mov     rcx, rdi; void *
0x180025c3b  mov     r8d, 40h ; '@'; Size
0x180025c41  call    memset_0
0x180025c46  lea     r8, WaTpEnvironment; pcbe
0x180025c4d  mov     dword ptr [rdi], 4F575054h
0x180025c53  mov     rdx, rdi; pv
0x180025c56  lea     rcx, WapTpWorkItemCallback; pfnwk
0x180025c5d  call    cs:__imp_CreateThreadpoolWork
0x180025c64  nop     dword ptr [rax+rax+00h]
0x180025c69  mov     [rdi+8], rax
0x180025c6d  lea     rcx, [rdi+20h]
0x180025c71  mov     [rbp+50h+Src], rcx
0x180025c75  test    rax, rax
0x180025c78  jz      loc_180026282
0x180025c7e  lea     rax, WapBackgroundConnectionCallback
0x180025c85  mov     [rdi+18h], r14
0x180025c89  mov     [rdi+10h], rax
0x180025c8d  mov     qword ptr [rcx], 0
0x180025c94  call    WaGetCurrentThreadToken
0x180025c99  mov     edi, eax
0x180025c9b  test    eax, eax
0x180025c9d  jnz     loc_1800263C8
0x180025ca3  xorps   xmm0, xmm0
0x180025ca6  lea     rdx, [r14+138h]; ActivityId
0x180025cad  mov     ecx, 1; ControlCode
0x180025cb2  movups  xmmword ptr [rbp+50h+Src], xmm0
0x180025cb6  call    cs:__imp_EventActivityIdControl
0x180025cbd  nop     dword ptr [rax+rax+00h]
0x180025cc2  test    eax, eax
0x180025cc4  jnz     loc_180026489
0x180025cca  mov     byte ptr [r14+148h], 1
0x180025cd2  lea     rax, [r14+10h]
0x180025cd6  mov     dword ptr [r14], 52474D43h
0x180025cdd  mov     dword ptr [r14+4], 1
0x180025ce5  mov     [rax+8], rax
0x180025ce9  mov     [rax], rax
0x180025cec  mov     [r14+50h], r13
0x180025cf0  lock inc dword ptr [r13+18h]
0x180025cf5  mov     rax, [rbp+50h+var_80]
0x180025cf9  mov     [r14+58h], rax
0x180025cfd  test    rax, rax
0x180025d00  jz      short loc_180025D06
0x180025d02  lock inc dword ptr [rax+18h]
0x180025d06  mov     rax, [rbp+50h+var_C0]
0x180025d0a  mov     [r14+60h], rax
0x180025d0e  test    rax, rax
0x180025d11  jz      short loc_180025D17
0x180025d13  lock inc dword ptr [rax+18h]
0x180025d17  lea     rax, [r14+68h]
0x180025d1b  mov     ecx, 80000000h
0x180025d20  mov     [rax+8], rax
0x180025d24  mov     [rax], rax
0x180025d27  lea     rax, [r14+78h]
  ... truncated ...
```
