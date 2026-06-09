# WinHttpQueryDataAvailable

- ea: `0x18003bcd0`
- end: `0x18003ca9e`
- name: `WinHttpQueryDataAvailable`
- size: `3534`
- prototype: `BOOL __stdcall(HINTERNET hRequest, LPDWORD lpdwNumberOfBytesAvailable)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013f60`
- `0x180033404`
- `0x18003bc60`
- `0x18003bcd0`
- `0x18003d9b0`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c069`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c273`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c069`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c273`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c05c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c08d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c287`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ca3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c05c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c08d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c287`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ca3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c549`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c549`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c374`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c9d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c374`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c9d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c211`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c36c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c9d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c36c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c9d0`
- `ntdll!EtwEventActivityIdControl` at `0x18003be66`
- `ntdll!EtwEventActivityIdControl` at `0x18003be9d`
- `ntdll!EtwEventActivityIdControl` at `0x18003c1f5`
- `ntdll!EtwEventActivityIdControl` at `0x18003c336`
- `ntdll!EtwEventActivityIdControl` at `0x18003c3ab`
- `ntdll!EtwEventActivityIdControl` at `0x18003c4a7`
- `ntdll!EtwEventActivityIdControl` at `0x18003be66`
- `ntdll!EtwEventActivityIdControl` at `0x18003be9d`
- `ntdll!EtwEventActivityIdControl` at `0x18003c1f5`
- `ntdll!EtwEventActivityIdControl` at `0x18003c336`
- `ntdll!EtwEventActivityIdControl` at `0x18003c3ab`
- `ntdll!EtwEventActivityIdControl` at `0x18003c4a7`

## pseudocode

```c
BOOL __stdcall WinHttpQueryDataAvailable(HINTERNET hRequest, LPDWORD lpdwNumberOfBytesAvailable)
{
  DWORD v2; // edi
  signed __int32 *v4; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v5; // r15
  HTTP_USER_REQUEST *v6; // r13
  HTTP_REQUEST_HANDLE_OBJECT *v7; // rbx
  signed __int32 v8; // eax
  struct _GUID *v9; // rbx
  __int128 *v10; // rax
  __int64 v11; // rcx
  __int128 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int128 *v15; // rax
  int v16; // eax
  bool v17; // sf
  int v18; // eax
  bool v19; // sf
  HTTP_REQUEST_HANDLE_OBJECT *v20; // rbx
  unsigned int IsValid; // esi
  __int64 v22; // r8
  __int64 v23; // r9
  signed __int32 v24; // eax
  char v25; // al
  signed __int32 *v26; // rbx
  signed __int32 *v27; // rsi
  signed __int32 v28; // r12d
  void (*v29)(void *, unsigned __int64, unsigned int, void *, unsigned int); // r14
  signed __int32 v30; // edi
  unsigned __int64 v31; // r15
  int v32; // ebx
  unsigned int DataAvailable; // eax
  unsigned int v34; // esi
  __int64 v35; // rbx
  __int64 v36; // r8
  unsigned int v37; // r15d
  __int64 v38; // r9
  BOOL v39; // r14d
  int v41; // edx
  __int64 v42; // rcx
  __int128 *v43; // rax
  __int128 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int128 *v47; // rax
  int v48; // eax
  bool v49; // sf
  signed __int32 v50; // esi
  DWORD v51; // ebx
  unsigned __int64 v52; // rcx
  const struct _GUID *v53; // r9
  int v54; // eax
  bool v55; // sf
  int v56; // edx
  int v57; // eax
  bool v58; // sf
  char *v59; // rax
  DWORD *v60; // rcx
  DWORD v61; // ebx
  signed __int32 v62; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v65; // r9
  unsigned int v66[2]; // [rsp+20h] [rbp-69h]
  int v67; // [rsp+30h] [rbp-59h]
  HTTP_REQUEST_HANDLE_OBJECT *v69; // [rsp+40h] [rbp-49h] BYREF
  signed __int32 *v70; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v71[4]; // [rsp+50h] [rbp-39h] BYREF
  struct _GUID v72; // [rsp+60h] [rbp-29h] BYREF
  __int128 v73; // [rsp+70h] [rbp-19h] BYREF
  int v74; // [rsp+80h] [rbp-9h]
  __int128 v75; // [rsp+90h] [rbp+7h] BYREF
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = 0;
  v70 = 0;
  v67 = 1;
  v4 = (signed __int32 *)hRequest;
  v74 = 0;
  v5 = 0;
  v69 = 0;
  v6 = 0;
  v73 = 0;
  if ( !WinHttpEtwInitialized )
    goto LABEL_54;
  if ( hRequest )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_qqD(
        1041,
        10,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hRequest,
        (__int64)&v69);
    if ( (unsigned int)HANDLE_OBJECT::IsValid(v4, 1684826455) )
    {
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v56 = 11;
        goto LABEL_167;
      }
    }
    else
    {
      v7 = (HTTP_REQUEST_HANDLE_OBJECT *)v4;
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      if ( v4[12] )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_qq(
            1032,
            20,
            (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
            *((_QWORD *)v4 + 4),
            (__int64)v4);
        v2 = 6;
      }
      while ( 1 )
      {
        v8 = v4[11];
        if ( v8 <= 0 )
          break;
        if ( v8 == _InterlockedCompareExchange(v4 + 11, v8 + 1, v8) )
          goto LABEL_11;
      }
      v2 = 5;
LABEL_11:
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(
          1045,
          21,
          (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
          *((_QWORD *)v4 + 4),
          (__int64)v4);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v2, *(_QWORD *)v66);
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v2, *(_QWORD *)v66);
      if ( v2 == 6 || !v2 )
        goto LABEL_18;
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v56 = 13;
LABEL_167:
        WPP_SF_qq(529, v56, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v4, (__int64)v4);
      }
    }
    v7 = 0;
    v2 = 6;
LABEL_18:
    v69 = v7;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v2, *(_QWORD *)v66);
      v7 = v69;
    }
    v2 = 0;
    if ( v7 )
    {
      if ( v74 )
      {
        v71[1] = 0;
        v57 = EtwEventActivityIdControl(2, &v73);
        v58 = v57 < 0;
        if ( v57 > 0 )
          v58 = 1;
        if ( v58 )
          v71[1] = 144;
        v7 = v69;
      }
      v9 = (struct _GUID *)((char *)v7 + 184);
      v10 = &v73;
      v11 = 16;
      do
      {
        *(_BYTE *)v10 = 0;
        v10 = (__int128 *)((char *)v10 + 1);
        --v11;
      }
      while ( v11 );
      v74 = 0;
      v12 = &v73;
      v72 = 0;
      v13 = 16;
      v75 = 0;
      do
      {
        *(_BYTE *)v12 = 0;
        v12 = (__int128 *)((char *)v12 + 1);
        --v13;
      }
      while ( v13 );
      *(_OWORD *)v71 = 0;
      v14 = 16;
      v15 = &v75;
      do
      {
        *(_BYTE *)v15 = 0;
        v15 = (__int128 *)((char *)v15 + 1);
        --v14;
      }
      while ( v14 );
      v16 = EtwEventActivityIdControl(1, v71);
      v17 = v16 < 0;
      if ( v16 > 0 )
        v17 = 1;
      if ( v17 )
        v71[1] = 128;
      else
        v75 = *(_OWORD *)v71;
      if ( !v9 )
      {
        v62 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        TickCount = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        v72.Data1 = (unsigned int)retaddr;
        v2 = 0;
        *(_DWORD *)v72.Data4 = TickCount;
        v9 = &v72;
        *(_DWORD *)&v72.Data4[4] = CurrentProcessId;
        *(_DWORD *)&v72.Data2 = v62;
      }
      v71[1] = 0;
      v18 = EtwEventActivityIdControl(2, v9);
      v19 = v18 < 0;
      if ( v18 > 0 )
        v19 = 1;
      if ( v19 )
        v71[1] = 144;
      v20 = v69;
      v73 = v75;
      v74 = 1;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
      IsValid = HANDLE_OBJECT::IsValid(v20, 1684826455);
      if ( !IsValid )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
        v23 = *((_QWORD *)v20 + 4);
        if ( !_InterlockedDecrement((volatile signed __int32 *)v20 + 11) )
          v2 = 1;
        if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v23, (__int64)v20);
        if ( v2 )
          (**(void (__fastcall ***)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64, __int64))v20)(v20, 1, v22, v23);
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v2, *(_QWORD *)v66);
        v2 = 0;
      }
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, *(_QWORD *)v66);
    }
    goto LABEL_54;
  }
  v42 = 16;
  v43 = &v73;
  do
  {
    *(_BYTE *)v43 = 0;
    v43 = (__int128 *)((char *)v43 + 1);
    --v42;
  }
  while ( v42 );
  v74 = 0;
  v44 = &v73;
  v72 = 0;
  v45 = 16;
  v75 = 0;
  do
  {
    *(_BYTE *)v44 = 0;
    v44 = (__int128 *)((char *)v44 + 1);
    --v45;
  }
  while ( v45 );
  *(_OWORD *)v71 = 0;
  v46 = 16;
  v47 = &v75;
  do
  {
    *(_BYTE *)v47 = 0;
    v47 = (__int128 *)((char *)v47 + 1);
    --v46;
  }
  while ( v46 );
  v48 = EtwEventActivityIdControl(1, v71);
  v49 = v48 < 0;
  if ( v48 > 0 )
    v49 = 1;
  if ( v49 )
    v71[1] = 128;
  else
    v75 = *(_OWORD *)v71;
  v50 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
  v51 = GetTickCount();
  *(_DWORD *)&v72.Data4[4] = GetCurrentProcessId();
  v72.Data1 = (unsigned int)retaddr;
  *(_DWORD *)&v72.Data2 = v50;
  *(_DWORD *)v72.Data4 = v51;
  if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
    EtwEx_tidActivityInfo(v52, &ActivityStart, &v72, v53, v66[0]);
  v2 = 0;
  v71[1] = 0;
  v54 = EtwEventActivityIdControl(2, &v72);
  v55 = v54 < 0;
  if ( v54 > 0 )
    v55 = 1;
  if ( v55 )
    v71[1] = 144;
  v73 = v75;
  v74 = 1;
LABEL_54:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qq(
      1026,
      30,
      (unsigned int)WPP_7824605398d33d290c3775842414c2fd_Traceguids,
      (_DWORD)v4,
      (__int64)lpdwNumberOfBytesAvailable);
  if ( !GlobalDataInitialized )
  {
    v2 = 12172;
LABEL_145:
    v29 = 0;
    v34 = 0;
    goto LABEL_146;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v4, (__int64)&v70);
  if ( !v4 || (unsigned int)HANDLE_OBJECT::IsValid(v4, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v41 = 11;
      goto LABEL_165;
    }
LABEL_116:
    v4 = 0;
    v2 = 6;
    goto LABEL_73;
  }
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  if ( v4[12] )
  {
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_qq(
        1032,
        20,
        (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
        *((_QWORD *)v4 + 4),
        (__int64)v4);
    v2 = 6;
  }
  while ( 1 )
  {
    v24 = v4[11];
    if ( v24 <= 0 )
      break;
    if ( v24 == _InterlockedCompareExchange(v4 + 11, v24 + 1, v24) )
      goto LABEL_66;
  }
  v2 = 5;
LABEL_66:
  if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_qqD(
      1045,
      21,
      (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
      *((_QWORD *)v4 + 4),
      (__int64)v4);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v2, *(_QWORD *)v66);
  v25 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v2, *(_QWORD *)v66);
    v25 = BYTE2(xmmword_180107A50);
  }
  if ( v2 != 6 && v2 )
  {
    if ( (v25 & 2) != 0 )
    {
      v41 = 13;
LABEL_165:
      WPP_SF_qq(529, v41, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v4, (__int64)v4);
      goto LABEL_116;
    }
    goto LABEL_116;
  }
LABEL_73:
  v70 = v4;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v2, *(_QWORD *)v66);
  if ( v2 )
    goto LABEL_145;
  v26 = v70;
  v2 = HANDLE_OBJECT::IsValid(v70, 1902465608);
  if ( v2 )
    goto LABEL_145;
  v27 = v70;
  v28 = v26[35];
  v69 = (HTTP_REQUEST_HANDLE_OBJECT *)v70;
  EnterCriticalSection((LPCRITICAL_SECTION)(v70 + 82));
  v6 = (HTTP_USER_REQUEST *)*((_QWORD *)v27 + 56);
  if ( !v6 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v27 + 82));
    v6 = 0;
    v2 = 6;
    v5 = (HTTP_REQUEST_HANDLE_OBJECT *)v27;
    goto LABEL_145;
  }
  (**(void (__fastcall ***)(_QWORD))v6)(*((_QWORD *)v27 + 56));
  LeaveCriticalSection((LPCRITICAL_SECTION)(v27 + 82));
  EnterCriticalSection((LPCRITICAL_SECTION)(v27 + 82));
  v29 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))*((_QWORD *)v27 + 21);
  v30 = v27[45];
  v31 = *((_QWORD *)v27 + 8);
  ++v27[110];
  LeaveCriticalSection((LPCRITICAL_SECTION)(v27 + 82));
  if ( v27[35] && v29 && (v30 & 0x240000) == 0x240000 )
  {
    v32 = 0;
    v67 = 0;
  }
  else
  {
    v32 = 1;
  }
  v71[0] = 0;
  DataAvailable = HTTP_USER_REQUEST::QueryDataAvailable(v6, v71, v32, v29, v30 & 0xF681FFFF, v31);
  v2 = DataAvailable;
  if ( DataAvailable )
  {
    if ( DataAvailable != 997 )
    {
      v5 = v69;
      v34 = 0;
      goto LABEL_87;
    }
    v5 = (HTTP_REQUEST_HANDLE_OBJECT *)v27;
LABEL_86:
    v34 = 1;
    goto LABEL_87;
  }
  v34 = 1;
  if ( !v32 )
  {
    v59 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
    if ( !v59 )
    {
      v5 = v69;
      v34 = 0;
      v2 = 8;
      goto LABEL_87;
    }
    *((_QWORD *)v59 + 9) = 0;
    *((_QWORD *)v59 + 11) = 0;
    *((_QWORD *)v59 + 10) = 0;
    *((_OWORD *)v59 + 6) = 0;
    *((_QWORD *)v59 + 8) = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
    v60 = (DWORD *)(v59 + 36);
    *((_DWORD *)v59 + 9) = 0;
    *(_QWORD *)v59 = 0;
    *((_QWORD *)v59 + 1) = 0;
    *((_QWORD *)v59 + 2) = 0;
    *((_QWORD *)v59 + 3) = 0;
    *((_DWORD *)v59 + 8) = 0;
    *(_OWORD *)(v59 + 40) = 0;
    *((_QWORD *)v59 + 7) = 0;
    v61 = v71[0];
    if ( v28 )
    {
      *((_QWORD *)v59 + 1) = v31;
      *v60 = v61;
      *(_QWORD *)v59 = v29;
      *((_DWORD *)v59 + 4) = 2;
      *((_DWORD *)v59 + 5) = 0x40000;
      *((_DWORD *)v59 + 8) = 4;
      *((_QWORD *)v59 + 3) = v60;
      v5 = v69;
      v2 = HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(v69, (struct HTTP_COMPLETION_PACKET *)v59, 1);
      v34 = v2 == 0;
    }
    else
    {
      v5 = v69;
    }
    if ( lpdwNumberOfBytesAvailable )
      *lpdwNumberOfBytesAvailable = v61;
LABEL_146:
    if ( v2 != 997 )
      goto LABEL_87;
    goto LABEL_86;
  }
  v5 = v69;
  if ( lpdwNumberOfBytesAvailable )
    *lpdwNumberOfBytesAvailable = v71[0];
LABEL_87:
  if ( v29 && (v67 || !v34) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 328));
    --*((_DWORD *)v5 + 110);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 328));
  }
  if ( v6 )
    (*(void (__fastcall **)(HTTP_USER_REQUEST *))(*(_QWORD *)v6 + 8LL))(v6);
  v35 = (__int64)v70;
  if ( v70 )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
    v37 = HANDLE_OBJECT::IsValid(v35, 1684826455);
    if ( !v37 )
    {
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      v38 = *(_QWORD *)(v35 + 32);
      v39 = _InterlockedDecrement((volatile signed __int32 *)(v35 + 44)) == 0;
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v38, v35);
      if ( v39 )
        (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v35)(v35, 1, v36, v38);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v39, *(_QWORD *)v66);
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v37, *(_QWORD *)v66);
    v70 = 0;
  }
  if ( v67 || !v34 )
  {
    if ( (xmmword_180107A60 & 2) != 0 )
    {
      if ( lpdwNumberOfBytesAvailable )
        v65 = *lpdwNumberOfBytesAvailable;
      else
        v65 = 0;
      WPP_SF_d(1025, 31, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v65, *(_QWORD *)v66);
    }
    if ( !v34 && (xmmword_180107A50 & 4) != 0 )
      WPP_SF_d(514, 32, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v2, *(_QWORD *)v66);
  }
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 33, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v34, *(_QWORD *)v66);
  if ( v74 )
    EtwEventActivityIdControl(2, &v73);
  SetLastError(v2);
  return v34;
}

```

## disassembly

```asm
0x18003bcd0  mov     [rsp-8+arg_10], rbx
0x18003bcd5  push    rbp
0x18003bcd6  push    rsi
0x18003bcd7  push    rdi
0x18003bcd8  push    r12
0x18003bcda  push    r13
0x18003bcdc  push    r14
0x18003bcde  push    r15
0x18003bce0  lea     rbp, [rsp-27h]
0x18003bce5  sub     rsp, 0B0h
0x18003bcec  mov     rax, cs:__security_cookie
0x18003bcf3  xor     rax, rsp
0x18003bcf6  mov     [rbp+57h+var_40], rax
0x18003bcfa  xor     edi, edi
0x18003bcfc  mov     [rbp+57h+var_A8], rdx
0x18003bd00  xor     eax, eax
0x18003bd02  mov     [rbp+57h+var_98], rdi
0x18003bd06  cmp     cs:?WinHttpEtwInitialized@@3EA, al; uchar WinHttpEtwInitialized
0x18003bd0c  xorps   xmm0, xmm0
0x18003bd0f  mov     r12, rdx
0x18003bd12  mov     [rbp+57h+var_B0], 1
0x18003bd19  mov     r14, rcx
0x18003bd1c  mov     [rbp+57h+var_60], eax
0x18003bd1f  mov     r15d, edi
0x18003bd22  mov     [rbp+57h+var_A0], rdi
0x18003bd26  mov     r13d, edi
0x18003bd29  movups  [rbp+57h+var_70], xmm0
0x18003bd2d  jz      loc_18003BF3F
0x18003bd33  test    rcx, rcx
0x18003bd36  jz      loc_18003C2C1
0x18003bd3c  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bd43  jnz     loc_18003C6FD
0x18003bd49  mov     edx, 646C6957h
0x18003bd4e  mov     rcx, r14
0x18003bd51  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003bd56  test    eax, eax
0x18003bd58  jnz     loc_18003C292
0x18003bd5e  mov     rbx, r14
0x18003bd61  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bd68  jnz     loc_18003C4CA
0x18003bd6e  mov     eax, [r14+30h]
0x18003bd72  test    eax, eax
0x18003bd74  jnz     loc_18003C7C9
0x18003bd7a  mov     eax, [r14+2Ch]
0x18003bd7e  test    eax, eax
0x18003bd80  jle     loc_18003C8D9
0x18003bd86  lea     ecx, [rax+1]
0x18003bd89  lock cmpxchg [r14+2Ch], ecx
0x18003bd8f  jnz     short loc_18003BD7A
0x18003bd91  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003bd98  jnz     loc_18003C824
0x18003bd9e  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bda5  jnz     loc_18003C512
0x18003bdab  test    byte ptr cs:xmmword_180107A50+2, 2
0x18003bdb2  jnz     loc_18003C77F
0x18003bdb8  cmp     edi, 6
0x18003bdbb  jnz     loc_18003C3D9
0x18003bdc1  mov     [rbp+57h+var_A0], rbx
0x18003bdc5  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bdcc  jnz     loc_18003C728
0x18003bdd2  xor     edi, edi
0x18003bdd4  test    rbx, rbx
0x18003bdd7  jz      loc_18003BF3F
0x18003bddd  cmp     [rbp+57h+var_60], r13d
0x18003bde1  jnz     loc_18003C49B
0x18003bde7  add     rbx, 0B8h
0x18003bdee  lea     rax, [rbp+57h+var_70]
0x18003bdf2  mov     ecx, 10h
0x18003bdf7  nop     word ptr [rax+rax+00000000h]
0x18003be00  mov     [rax], r13b
0x18003be03  lea     rax, [rax+1]
0x18003be07  sub     rcx, 1
0x18003be0b  jnz     short loc_18003BE00
0x18003be0d  xorps   xmm0, xmm0
0x18003be10  mov     [rbp+57h+var_60], edi
0x18003be13  xorps   xmm1, xmm1
0x18003be16  lea     rax, [rbp+57h+var_70]
0x18003be1a  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x18003be1e  mov     ecx, 10h
0x18003be23  movups  [rbp+57h+var_50], xmm1
0x18003be27  nop     word ptr [rax+rax+00000000h]
0x18003be30  mov     [rax], r13b
0x18003be33  lea     rax, [rax+1]
0x18003be37  sub     rcx, 1
0x18003be3b  jnz     short loc_18003BE30
0x18003be3d  xorps   xmm0, xmm0
0x18003be40  mov     [rbp+57h+var_90+4], edi
0x18003be43  movups  xmmword ptr [rbp-39h], xmm0
0x18003be47  mov     ecx, 10h
0x18003be4c  lea     rax, [rbp+57h+var_50]
0x18003be50  mov     [rax], r13b
0x18003be53  lea     rax, [rax+1]
0x18003be57  sub     rcx, 1
0x18003be5b  jnz     short loc_18003BE50
0x18003be5d  lea     rdx, [rbp+57h+var_90]
0x18003be61  mov     ecx, 1
0x18003be66  call    cs:__imp_EtwEventActivityIdControl
0x18003be6c  test    eax, eax
0x18003be6e  jle     short loc_18003BE7A
0x18003be70  movzx   eax, ax
0x18003be73  or      eax, 80070000h
0x18003be78  test    eax, eax
0x18003be7a  js      loc_18003C818
0x18003be80  movaps  xmm0, xmmword ptr [rbp+57h+var_90]
0x18003be84  movdqa  [rbp+57h+var_50], xmm0
0x18003be89  test    rbx, rbx
0x18003be8c  jz      loc_18003C9BD
0x18003be92  mov     rdx, rbx
0x18003be95  mov     [rbp+57h+var_90+4], edi
0x18003be98  mov     ecx, 2
0x18003be9d  call    cs:__imp_EtwEventActivityIdControl
0x18003bea3  test    eax, eax
0x18003bea5  jle     short loc_18003BEB1
0x18003bea7  movzx   eax, ax
0x18003beaa  or      eax, 80070000h
0x18003beaf  test    eax, eax
0x18003beb1  js      loc_18003C9F5
0x18003beb7  movaps  xmm0, [rbp+57h+var_50]
0x18003bebb  mov     rbx, [rbp+57h+var_A0]
0x18003bebf  movups  [rbp+57h+var_70], xmm0
0x18003bec3  mov     [rbp+57h+var_60], 1
0x18003beca  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bed1  jnz     loc_18003C696
0x18003bed7  mov     edx, 646C6957h
0x18003bedc  mov     rcx, rbx
0x18003bedf  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003bee4  mov     esi, eax
0x18003bee6  test    eax, eax
0x18003bee8  jnz     short loc_18003BF32
0x18003beea  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bef1  jnz     loc_18003C920
0x18003bef7  mov     r9, [rbx+20h]
0x18003befb  mov     eax, 0FFFFFFFFh
0x18003bf00  lock xadd [rbx+2Ch], eax
0x18003bf05  sub     eax, 1
0x18003bf08  jz      loc_18003C530
0x18003bf0e  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003bf15  jnz     loc_18003C981
0x18003bf1b  test    edi, edi
0x18003bf1d  jnz     loc_18003C61A
0x18003bf23  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bf2a  jnz     loc_18003C93F
0x18003bf30  xor     edi, edi
0x18003bf32  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bf39  jnz     loc_18003C416
0x18003bf3f  test    byte ptr cs:xmmword_180107A60, 4
0x18003bf46  jnz     loc_18003CA01
0x18003bf4c  cmp     cs:?GlobalDataInitialized@@3HA, r13d; int GlobalDataInitialized
0x18003bf53  jz      loc_18003CA24
0x18003bf59  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bf60  jnz     loc_18003C6B4
0x18003bf66  test    r14, r14
0x18003bf69  jz      loc_18003C249
0x18003bf6f  mov     edx, 646C6957h
0x18003bf74  mov     rcx, r14
0x18003bf77  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003bf7c  test    eax, eax
0x18003bf7e  jnz     loc_18003C249
0x18003bf84  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bf8b  jnz     loc_18003C457
0x18003bf91  mov     eax, [r14+30h]
0x18003bf95  test    eax, eax
0x18003bf97  jnz     loc_18003C7B2
0x18003bf9d  mov     eax, [r14+2Ch]
0x18003bfa1  test    eax, eax
0x18003bfa3  jle     loc_18003C8AB
0x18003bfa9  lea     ecx, [rax+1]
0x18003bfac  lock cmpxchg [r14+2Ch], ecx
0x18003bfb2  jnz     short loc_18003BF9D
0x18003bfb4  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003bfbb  jnz     loc_18003C7EC
0x18003bfc1  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003bfc8  jnz     loc_18003C4E9
0x18003bfce  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x18003bfd5  test    al, 2
0x18003bfd7  jnz     loc_18003C75A
0x18003bfdd  cmp     edi, 6
0x18003bfe0  jnz     loc_18003C2AB
0x18003bfe6  mov     [rbp+57h+var_98], r14
0x18003bfea  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003bff1  jnz     loc_18003C6DF
0x18003bff7  test    edi, edi
0x18003bff9  jnz     loc_18003C434
0x18003bfff  mov     rbx, [rbp+57h+var_98]
0x18003c003  mov     edx, 71655248h
0x18003c008  mov     rcx, rbx
0x18003c00b  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003c010  mov     edi, eax
0x18003c012  test    eax, eax
0x18003c014  jnz     loc_18003C434
0x18003c01a  mov     rsi, [rbp+57h+var_98]
0x18003c01e  mov     r12d, [rbx+8Ch]
0x18003c025  mov     [rbp+57h+var_A0], rsi
0x18003c029  lea     rcx, [rsi+148h]; lpCriticalSection
0x18003c030  call    cs:__imp_EnterCriticalSection
0x18003c036  mov     r13, [rsi+1C0h]
0x18003c03d  test    r13, r13
0x18003c040  jz      loc_18003CA37
0x18003c046  mov     rax, [r13+0]
0x18003c04a  mov     rcx, r13
0x18003c04d  mov     rax, [rax]
0x18003c050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c055  lea     rcx, [rsi+148h]; lpCriticalSection
0x18003c05c  call    cs:__imp_LeaveCriticalSection
0x18003c062  lea     rcx, [rsi+148h]; lpCriticalSection
0x18003c069  call    cs:__imp_EnterCriticalSection
0x18003c06f  mov     r14, [rsi+0A8h]
0x18003c076  lea     rcx, [rsi+148h]; lpCriticalSection
0x18003c07d  mov     edi, [rsi+0B4h]
0x18003c083  mov     r15, [rsi+40h]
0x18003c087  inc     dword ptr [rsi+1B8h]
0x18003c08d  call    cs:__imp_LeaveCriticalSection
0x18003c093  cmp     dword ptr [rsi+8Ch], 0
0x18003c09a  jnz     loc_18003C476
0x18003c0a0  mov     ebx, [rbp+57h+var_B0]
0x18003c0a3  and     edi, 0F681FFFFh
0x18003c0a9  mov     [rsp+0E0h+var_B8], r15; unsigned __int64
0x18003c0ae  mov     r9, r14; void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x18003c0b1  mov     [rsp+0E0h+var_C0], edi; unsigned int
0x18003c0b5  mov     r8d, ebx; int
0x18003c0b8  mov     [rbp+57h+var_90], 0
0x18003c0bf  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x18003c0c3  mov     rcx, r13; this
0x18003c0c6  call    ?QueryDataAvailable@HTTP_USER_REQUEST@@QEAAKPEAKHP6AXPEAX_KK1K@ZK2@Z; HTTP_USER_REQUEST::QueryDataAvailable(ulong *,int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)
0x18003c0cb  mov     edi, eax
0x18003c0cd  test    eax, eax
0x18003c0cf  jnz     short loc_18003C0F2
0x18003c0d1  mov     esi, 1
0x18003c0d6  test    ebx, ebx
0x18003c0d8  jz      loc_18003C53A
0x18003c0de  mov     rcx, [rbp+57h+var_A8]
0x18003c0e2  mov     r15, [rbp+57h+var_A0]
0x18003c0e6  test    rcx, rcx
0x18003c0e9  jz      short loc_18003C105
0x18003c0eb  mov     eax, [rbp+57h+var_90]
0x18003c0ee  mov     [rcx], eax
0x18003c0f0  jmp     short loc_18003C105
0x18003c0f2  cmp     eax, 3E5h
0x18003c0f7  jnz     loc_18003C5F7
0x18003c0fd  mov     r15, rsi
0x18003c100  mov     esi, 1
0x18003c105  mov     r12d, [rbp+57h+var_B0]
0x18003c109  test    r14, r14
0x18003c10c  jnz     loc_18003C263
0x18003c112  test    r13, r13
0x18003c115  jz      short loc_18003C127
0x18003c117  mov     rax, [r13+0]
0x18003c11b  mov     rcx, r13
0x18003c11e  mov     rax, [rax+8]
0x18003c122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c127  mov     rbx, [rbp+57h+var_98]
0x18003c12b  test    rbx, rbx
0x18003c12e  jz      loc_18003C1B4
0x18003c134  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003c13b  jnz     loc_18003C655
0x18003c141  mov     edx, 646C6957h
0x18003c146  mov     rcx, rbx
0x18003c149  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003c14e  mov     r15d, eax
0x18003c151  test    eax, eax
0x18003c153  jnz     short loc_18003C19F
0x18003c155  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003c15c  jnz     loc_18003C8E3
0x18003c162  mov     r9, [rbx+20h]
0x18003c166  mov     eax, 0FFFFFFFFh
0x18003c16b  lock xadd [rbx+2Ch], eax
0x18003c170  sub     eax, 1
0x18003c173  jz      loc_18003C507
0x18003c179  xor     r14d, r14d
0x18003c17c  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003c183  jnz     loc_18003C95D
0x18003c189  test    r14d, r14d
0x18003c18c  jnz     loc_18003C602
0x18003c192  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003c199  jnz     loc_18003C902
0x18003c19f  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003c1a6  jnz     loc_18003C3F8
0x18003c1ac  mov     [rbp+57h+var_98], 0
0x18003c1b4  test    r12d, r12d
0x18003c1b7  jz      loc_18003C240
0x18003c1bd  test    byte ptr cs:xmmword_180107A60, 2
0x18003c1c4  jnz     loc_18003CA54
0x18003c1ca  test    esi, esi
0x18003c1cc  jz      loc_18003C850
0x18003c1d2  test    byte ptr cs:xmmword_180107A60, 4
0x18003c1d9  jnz     loc_18003CA80
0x18003c1df  cmp     [rbp+57h+var_60], 0
0x18003c1e3  jz      short loc_18003C20F
0x18003c1e5  lea     rdx, [rbp+57h+var_70]
0x18003c1e9  mov     dword ptr [rbp+57h+var_A8+4], 0
0x18003c1f0  mov     ecx, 2
0x18003c1f5  call    cs:__imp_EtwEventActivityIdControl
0x18003c1fb  test    eax, eax
0x18003c1fd  jle     short loc_18003C209
0x18003c1ff  movzx   eax, ax
0x18003c202  or      eax, 80070000h
0x18003c207  test    eax, eax
0x18003c209  js      loc_18003C7E0
0x18003c20f  mov     ecx, edi; dwErrCode
0x18003c211  call    cs:__imp_SetLastError
  ... truncated ...
```
