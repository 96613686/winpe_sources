# WinHttpWriteData

- ea: `0x18003a2b0`
- end: `0x18003b0d2`
- name: `WinHttpWriteData`
- size: `3618`
- prototype: `BOOL __stdcall(HINTERNET hRequest, LPCVOID lpBuffer, DWORD dwNumberOfBytesToWrite, LPDWORD lpdwNumberOfBytesWritten)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013f60`
- `0x180033404`
- `0x180039380`
- `0x18003a2b0`
- `0x18003bc60`
- `0x1800716a0`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dbfac`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a6be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a6be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a6b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a6e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b049`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a6b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a6e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b049`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003abec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003abec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a490`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a9ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a490`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a9ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a893`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a893`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a488`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a9a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a488`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a9a3`
- `ntdll!EtwEventActivityIdControl` at `0x18003a452`
- `ntdll!EtwEventActivityIdControl` at `0x18003a4cf`
- `ntdll!EtwEventActivityIdControl` at `0x18003a877`
- `ntdll!EtwEventActivityIdControl` at `0x18003a972`
- `ntdll!EtwEventActivityIdControl` at `0x18003a9e2`
- `ntdll!EtwEventActivityIdControl` at `0x18003aa97`
- `ntdll!EtwEventActivityIdControl` at `0x18003a452`
- `ntdll!EtwEventActivityIdControl` at `0x18003a4cf`
- `ntdll!EtwEventActivityIdControl` at `0x18003a877`
- `ntdll!EtwEventActivityIdControl` at `0x18003a972`
- `ntdll!EtwEventActivityIdControl` at `0x18003a9e2`
- `ntdll!EtwEventActivityIdControl` at `0x18003aa97`

## pseudocode

```c
BOOL __stdcall WinHttpWriteData(
        HINTERNET hRequest,
        LPCVOID lpBuffer,
        DWORD dwNumberOfBytesToWrite,
        LPDWORD lpdwNumberOfBytesWritten)
{
  DWORD v4; // edi
  LPCVOID v6; // r8
  signed __int32 v8; // ecx
  unsigned int v9; // r12d
  int v10; // esi
  char *v11; // rbx
  signed __int32 v12; // eax
  struct _GUID *v13; // rbx
  __int128 *v14; // rax
  __int64 v15; // rcx
  __int128 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int128 *v19; // rax
  int v20; // eax
  unsigned __int64 v21; // rcx
  const struct _GUID *v22; // r9
  bool v23; // sf
  signed __int32 v24; // esi
  DWORD v25; // ebx
  DWORD CurrentProcessId; // eax
  int v27; // eax
  bool v28; // sf
  __int64 v29; // rbx
  unsigned int IsValid; // esi
  __int64 v31; // r8
  __int64 v32; // r9
  void (*v33)(void *, unsigned __int64, unsigned int, void *, unsigned int); // r13
  HTTP_REQUEST_HANDLE_OBJECT *v34; // r14
  HTTP_USER_REQUEST *v35; // rbx
  signed __int32 v36; // eax
  char v37; // al
  HTTP_REQUEST_HANDLE_OBJECT *v38; // rsi
  int v39; // r12d
  int v40; // esi
  unsigned __int64 v41; // r15
  DWORD *v42; // r15
  HTTP_REQUEST_HANDLE_OBJECT *v43; // rbx
  __int64 v44; // r8
  unsigned int v45; // r14d
  __int64 v46; // r9
  BOOL v47; // esi
  int v49; // edx
  __int64 v50; // rcx
  __int128 *v51; // rax
  __int128 *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int128 *v55; // rax
  int v56; // eax
  bool v57; // sf
  signed __int32 v58; // esi
  DWORD TickCount; // ebx
  unsigned __int64 v60; // rcx
  const struct _GUID *v61; // r9
  int v62; // eax
  bool v63; // sf
  int v64; // edx
  int v65; // eax
  bool v66; // sf
  char *v67; // rax
  _DWORD *v68; // rcx
  unsigned int v69; // esi
  __int64 v70; // r9
  int v71[2]; // [rsp+28h] [rbp-99h]
  unsigned int v72; // [rsp+38h] [rbp-89h]
  unsigned int v73; // [rsp+4Ch] [rbp-75h]
  DWORD *v74; // [rsp+50h] [rbp-71h]
  int v76[2]; // [rsp+60h] [rbp-61h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v77; // [rsp+68h] [rbp-59h] BYREF
  unsigned int v78[4]; // [rsp+78h] [rbp-49h] BYREF
  struct _GUID v79; // [rsp+88h] [rbp-39h] BYREF
  __int128 v80; // [rsp+98h] [rbp-29h] BYREF
  int v81; // [rsp+A8h] [rbp-19h]
  __int128 v82; // [rsp+B8h] [rbp-9h] BYREF
  _UNKNOWN *retaddr; // [rsp+120h] [rbp+5Fh]

  v4 = 0;
  v6 = lpBuffer;
  v74 = lpdwNumberOfBytesWritten;
  v8 = 0;
  v73 = dwNumberOfBytesToWrite;
  v9 = 0;
  v10 = 1;
  v77 = 0;
  v80 = 0;
  v81 = 0;
  *(_QWORD *)v76 = 0;
  if ( WinHttpEtwInitialized )
  {
    if ( !hRequest )
    {
      v50 = 16;
      v51 = &v80;
      do
      {
        *(_BYTE *)v51 = 0;
        v51 = (__int128 *)((char *)v51 + 1);
        --v50;
      }
      while ( v50 );
      v81 = 0;
      v52 = &v80;
      v79 = 0;
      v53 = 16;
      v82 = 0;
      do
      {
        *(_BYTE *)v52 = 0;
        v52 = (__int128 *)((char *)v52 + 1);
        --v53;
      }
      while ( v53 );
      *(_OWORD *)v78 = 0;
      v54 = 16;
      v55 = &v82;
      do
      {
        *(_BYTE *)v55 = 0;
        v55 = (__int128 *)((char *)v55 + 1);
        --v54;
      }
      while ( v54 );
      v56 = EtwEventActivityIdControl(1, v78);
      v57 = v56 < 0;
      if ( v56 > 0 )
        v57 = 1;
      if ( v57 )
        v78[1] = 128;
      else
        v82 = *(_OWORD *)v78;
      v58 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
      TickCount = GetTickCount();
      *(_DWORD *)&v79.Data4[4] = GetCurrentProcessId();
      v79.Data1 = (unsigned int)retaddr;
      *(_DWORD *)&v79.Data2 = v58;
      *(_DWORD *)v79.Data4 = TickCount;
      if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v60, &ActivityStart, &v79, v61, v71[0]);
      v4 = 0;
      v78[1] = 0;
      v62 = EtwEventActivityIdControl(2, &v79);
      v63 = v62 < 0;
      if ( v62 > 0 )
        v63 = 1;
      if ( v63 )
        v78[1] = 144;
      v10 = 1;
      v80 = v82;
      v81 = 1;
      goto LABEL_58;
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_qqD(
        1041,
        10,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hRequest,
        (__int64)v76);
    if ( (unsigned int)HANDLE_OBJECT::IsValid(hRequest, 1684826455) )
    {
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v64 = 11;
        goto LABEL_163;
      }
    }
    else
    {
      v11 = (char *)hRequest;
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      if ( *((_DWORD *)hRequest + 12) )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_qq(
            1032,
            20,
            (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
            *((_QWORD *)hRequest + 4),
            (__int64)hRequest);
        v4 = 6;
      }
      while ( 1 )
      {
        v12 = *((_DWORD *)hRequest + 11);
        if ( v12 <= 0 )
          break;
        v8 = v12 + 1;
        if ( v12 == _InterlockedCompareExchange((volatile signed __int32 *)hRequest + 11, v12 + 1, v12) )
          goto LABEL_11;
      }
      v4 = 5;
LABEL_11:
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(
          1045,
          21,
          (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
          *((_QWORD *)hRequest + 4),
          (__int64)hRequest);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v4, *(_QWORD *)v71);
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, *(_QWORD *)v71);
      if ( v4 == 6 || !v4 )
        goto LABEL_18;
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v64 = 13;
LABEL_163:
        WPP_SF_qq(
          529,
          v64,
          (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
          (_DWORD)hRequest,
          (__int64)hRequest);
      }
    }
    v11 = 0;
    v4 = 6;
LABEL_18:
    *(_QWORD *)v76 = v11;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, *(_QWORD *)v71);
      v11 = *(char **)v76;
    }
    v4 = 0;
    if ( v11 )
    {
      if ( v81 )
      {
        v78[1] = 0;
        v65 = EtwEventActivityIdControl(2, &v80);
        v66 = v65 < 0;
        if ( v65 > 0 )
          v66 = 1;
        if ( v66 )
          v78[1] = 144;
        v11 = *(char **)v76;
      }
      v13 = (struct _GUID *)(v11 + 184);
      v14 = &v80;
      v15 = 16;
      do
      {
        *(_BYTE *)v14 = 0;
        v14 = (__int128 *)((char *)v14 + 1);
        --v15;
      }
      while ( v15 );
      v81 = 0;
      v16 = &v80;
      v79 = 0;
      v17 = 16;
      v82 = 0;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (__int128 *)((char *)v16 + 1);
        --v17;
      }
      while ( v17 );
      *(_OWORD *)v78 = 0;
      v18 = 16;
      v19 = &v82;
      do
      {
        *(_BYTE *)v19 = 0;
        v19 = (__int128 *)((char *)v19 + 1);
        --v18;
      }
      while ( v18 );
      v20 = EtwEventActivityIdControl(1, v78);
      v23 = v20 < 0;
      if ( v20 > 0 )
        v23 = 1;
      if ( v23 )
        v78[1] = 128;
      else
        v82 = *(_OWORD *)v78;
      if ( !v13 )
      {
        v24 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        v25 = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        v79.Data1 = (unsigned int)retaddr;
        v4 = 0;
        *(_DWORD *)&v79.Data2 = v24;
        *(_DWORD *)v79.Data4 = v25;
        v13 = &v79;
        *(_DWORD *)&v79.Data4[4] = CurrentProcessId;
      }
      if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v21, &ActivityStart, v13, v22, v71[0]);
      v78[1] = 0;
      v27 = EtwEventActivityIdControl(2, v13);
      v28 = v27 < 0;
      if ( v27 > 0 )
        v28 = 1;
      if ( v28 )
        v78[1] = 144;
      v29 = *(_QWORD *)v76;
      v80 = v82;
      v81 = 1;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
      IsValid = HANDLE_OBJECT::IsValid(v29, 1684826455);
      if ( !IsValid )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
        v32 = *(_QWORD *)(v29 + 32);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v29 + 44)) )
          v4 = 1;
        if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v32, v29);
        if ( v4 )
          (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v29)(v29, 1, v31, v32);
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v4, *(_QWORD *)v71);
        v4 = 0;
      }
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, *(_QWORD *)v71);
      v10 = 1;
    }
LABEL_58:
    lpdwNumberOfBytesWritten = v74;
    v6 = lpBuffer;
    dwNumberOfBytesToWrite = v73;
  }
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qqdq(
      v8,
      26,
      (_DWORD)v6,
      (_DWORD)hRequest,
      (__int64)v6,
      dwNumberOfBytesToWrite,
      (__int64)lpdwNumberOfBytesWritten);
  if ( !GlobalDataInitialized )
  {
    v42 = v74;
    v4 = 12172;
    goto LABEL_98;
  }
  v33 = 0;
  v76[0] = 1;
  v34 = 0;
  v35 = 0;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)hRequest, (__int64)&v77);
  if ( !hRequest || (unsigned int)HANDLE_OBJECT::IsValid(hRequest, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v49 = 11;
      goto LABEL_154;
    }
LABEL_121:
    hRequest = 0;
    v4 = 6;
    goto LABEL_78;
  }
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  if ( *((_DWORD *)hRequest + 12) )
  {
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_qq(
        1032,
        20,
        (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
        *((_QWORD *)hRequest + 4),
        (__int64)hRequest);
    v4 = 6;
  }
  while ( 1 )
  {
    v36 = *((_DWORD *)hRequest + 11);
    if ( v36 <= 0 )
      break;
    if ( v36 == _InterlockedCompareExchange((volatile signed __int32 *)hRequest + 11, v36 + 1, v36) )
      goto LABEL_71;
  }
  v4 = 5;
LABEL_71:
  if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_qqD(
      1045,
      21,
      (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
      *((_QWORD *)hRequest + 4),
      (__int64)hRequest);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v4, *(_QWORD *)v71);
  v37 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, *(_QWORD *)v71);
    v37 = BYTE2(xmmword_180107A50);
  }
  if ( v4 != 6 && v4 )
  {
    if ( (v37 & 2) != 0 )
    {
      v49 = 13;
LABEL_154:
      WPP_SF_qq(
        529,
        v49,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hRequest,
        (__int64)hRequest);
      goto LABEL_121;
    }
    goto LABEL_121;
  }
LABEL_78:
  v77 = (HTTP_REQUEST_HANDLE_OBJECT *)hRequest;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, *(_QWORD *)v71);
  if ( v4 )
    goto LABEL_90;
  v38 = v77;
  v4 = HANDLE_OBJECT::IsValid(v77, 1902465608);
  if ( v4 )
  {
    v10 = v76[0];
    goto LABEL_90;
  }
  v34 = v77;
  if ( !v73 && (lpBuffer || (*((_DWORD *)v77 + 168) & 0x200) == 0) )
  {
    v42 = v74;
    v4 = 87;
    goto LABEL_98;
  }
  v39 = *((_DWORD *)v38 + 35);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v77 + 328));
  v35 = (HTTP_USER_REQUEST *)*((_QWORD *)v34 + 56);
  if ( !v35 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v34 + 328));
    v9 = 0;
    v4 = 6;
    v42 = v74;
    goto LABEL_98;
  }
  (**(void (__fastcall ***)(_QWORD))v35)(*((_QWORD *)v34 + 56));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v34 + 328));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v34 + 328));
  v33 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))*((_QWORD *)v34 + 21);
  v40 = *((_DWORD *)v34 + 45);
  v41 = *((_QWORD *)v34 + 8);
  ++*((_DWORD *)v34 + 110);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v34 + 328));
  if ( *((_DWORD *)v34 + 35) && v33 && (v40 & 0x300000) == 0x300000 )
    v76[0] = 0;
  v72 = v40 & 0xF681FFFF;
  v10 = v76[0];
  v78[0] = 0;
  v4 = HTTP_USER_REQUEST::WriteData(v35, (unsigned __int8 *const)lpBuffer, v73, v78, v76[0], v33, v72, v41);
  if ( v4 )
  {
    v9 = 0;
LABEL_90:
    v42 = v74;
LABEL_91:
    if ( v4 == 997 )
      v9 = 1;
    goto LABEL_93;
  }
  if ( v10 )
  {
    v42 = v74;
    v9 = 1;
    if ( v74 )
      *v74 = v78[0];
    goto LABEL_93;
  }
  v67 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
  if ( v67 )
  {
    *((_QWORD *)v67 + 9) = 0;
    *((_QWORD *)v67 + 11) = 0;
    *((_QWORD *)v67 + 10) = 0;
    *((_OWORD *)v67 + 6) = 0;
    *((_QWORD *)v67 + 8) = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
    v68 = v67 + 36;
    *((_DWORD *)v67 + 9) = 0;
    *(_QWORD *)v67 = 0;
    *((_QWORD *)v67 + 1) = 0;
    *((_QWORD *)v67 + 2) = 0;
    *((_QWORD *)v67 + 3) = 0;
    *((_DWORD *)v67 + 8) = 0;
    *(_OWORD *)(v67 + 40) = 0;
    *((_QWORD *)v67 + 7) = 0;
    v69 = v78[0];
    if ( v39 )
    {
      *v68 = v78[0];
      *((_QWORD *)v67 + 3) = v68;
      *(_QWORD *)v67 = v33;
      *((_QWORD *)v67 + 1) = v41;
      *((_DWORD *)v67 + 4) = 4;
      *((_DWORD *)v67 + 5) = 0x100000;
      *((_DWORD *)v67 + 8) = 4;
      v4 = HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(v34, (struct HTTP_COMPLETION_PACKET *)v67, 1);
      v9 = v4 == 0;
    }
    else
    {
      v9 = 1;
    }
    v42 = v74;
    if ( v74 )
      *v74 = v69;
    v10 = v76[0];
    goto LABEL_91;
  }
  v42 = v74;
  v9 = 0;
  v4 = 8;
LABEL_93:
  if ( v33 && (v10 || !v9) )
    HTTP_REQUEST_HANDLE_OBJECT::SafeReleaseCallbackInfo(v34);
  if ( v35 )
    (*(void (__fastcall **)(HTTP_USER_REQUEST *))(*(_QWORD *)v35 + 8LL))(v35);
LABEL_98:
  v43 = v77;
  if ( v77 )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
    v45 = HANDLE_OBJECT::IsValid(v43, 1684826455);
    if ( !v45 )
    {
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      v46 = *((_QWORD *)v43 + 4);
      v47 = _InterlockedDecrement((volatile signed __int32 *)v43 + 11) == 0;
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v46, (__int64)v43);
      if ( v47 )
        (**(void (__fastcall ***)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64, __int64))v43)(v43, 1, v44, v46);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v47, *(_QWORD *)v71);
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v45, *(_QWORD *)v71);
    v77 = 0;
  }
  if ( (xmmword_180107A60 & 2) != 0 )
  {
    if ( v42 )
      v70 = *v42;
    else
      v70 = 0;
    WPP_SF_d(1025, 27, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v70, *(_QWORD *)v71);
  }
  if ( !v9 && (xmmword_180107A50 & 4) != 0 )
    WPP_SF_d(514, 28, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v4, *(_QWORD *)v71);
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 29, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v9, *(_QWORD *)v71);
  if ( v81 )
    EtwEventActivityIdControl(2, &v80);
  SetLastError(v4);
  return v9;
}

```

## disassembly

```asm
0x18003a2b0  mov     r11, rsp
0x18003a2b3  push    rbp
0x18003a2b4  push    rdi
0x18003a2b5  push    r12
0x18003a2b7  lea     rbp, [r11-5Fh]
0x18003a2bb  sub     rsp, 100h
0x18003a2c2  mov     rax, cs:__security_cookie
0x18003a2c9  xor     rax, rsp
0x18003a2cc  mov     [rbp+57h+var_50], rax
0x18003a2d0  xor     edi, edi
0x18003a2d2  mov     [r11-20h], rbx
0x18003a2d6  mov     [r11-28h], rsi
0x18003a2da  mov     eax, r8d
0x18003a2dd  mov     [r11-30h], r13
0x18003a2e1  xorps   xmm0, xmm0
0x18003a2e4  mov     [r11-40h], r15
0x18003a2e8  mov     r8, rdx
0x18003a2eb  mov     r15, rcx
0x18003a2ee  mov     [rbp+57h+var_C8], r9
0x18003a2f2  xor     ecx, ecx
0x18003a2f4  mov     [rbp+57h+var_CC], eax
0x18003a2f7  cmp     cs:?WinHttpEtwInitialized@@3EA, cl; uchar WinHttpEtwInitialized
0x18003a2fd  mov     r12d, edi
0x18003a300  mov     [rbp+57h+var_C0], rdx
0x18003a304  mov     esi, 1
0x18003a309  mov     [rbp+57h+var_D0], edi
0x18003a30c  mov     r13d, 0FFFFFFFFh
0x18003a312  mov     [rbp+57h+var_B0], rdi
0x18003a316  movups  [rbp+57h+var_80], xmm0
0x18003a31a  mov     [rbp+57h+var_70], ecx
0x18003a31d  mov     qword ptr [rbp+57h+var_B8], rdi
0x18003a321  jz      loc_18003A57B
0x18003a327  test    r15, r15
0x18003a32a  jz      loc_18003A8FD
0x18003a330  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a337  jnz     loc_18003AD53
0x18003a33d  mov     edx, 646C6957h
0x18003a342  mov     rcx, r15
0x18003a345  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003a34a  test    eax, eax
0x18003a34c  jnz     loc_18003A8CE
0x18003a352  mov     rbx, r15
0x18003a355  test    byte ptr cs:xmmword_180107A60+1, sil
0x18003a35c  jnz     loc_18003AABA
0x18003a362  mov     eax, [r15+30h]
0x18003a366  test    eax, eax
0x18003a368  jnz     loc_18003AE37
0x18003a36e  mov     eax, [r15+2Ch]
0x18003a372  test    eax, eax
0x18003a374  jle     loc_18003AF1C
0x18003a37a  lea     ecx, [rax+1]
0x18003a37d  lock cmpxchg [r15+2Ch], ecx
0x18003a383  jnz     short loc_18003A36E
0x18003a385  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003a38c  jnz     loc_18003AE92
0x18003a392  test    byte ptr cs:xmmword_180107A60+1, sil
0x18003a399  jnz     loc_18003AB01
0x18003a39f  test    byte ptr cs:xmmword_180107A50+2, 2
0x18003a3a6  jnz     loc_18003ADD1
0x18003a3ac  cmp     edi, 6
0x18003a3af  jnz     loc_18003AA11
0x18003a3b5  mov     qword ptr [rbp+57h+var_B8], rbx
0x18003a3b9  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a3c0  jnz     loc_18003AD7E
0x18003a3c6  xor     edi, edi
0x18003a3c8  test    rbx, rbx
0x18003a3cb  jz      loc_18003A570
0x18003a3d1  cmp     [rbp+57h+var_70], r12d
0x18003a3d5  jnz     loc_18003AA8B
0x18003a3db  add     rbx, 0B8h
0x18003a3e2  lea     rax, [rbp+57h+var_80]
0x18003a3e6  mov     ecx, 10h
0x18003a3eb  nop     dword ptr [rax+rax+00h]
0x18003a3f0  mov     [rax], r12b
0x18003a3f3  lea     rax, [rax+1]
0x18003a3f7  sub     rcx, rsi
0x18003a3fa  jnz     short loc_18003A3F0
0x18003a3fc  xorps   xmm0, xmm0
0x18003a3ff  mov     [rbp+57h+var_70], edi
0x18003a402  xorps   xmm1, xmm1
0x18003a405  lea     rax, [rbp+57h+var_80]
0x18003a409  movups  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18003a40d  mov     ecx, 10h
0x18003a412  movups  [rbp+57h+var_60], xmm1
0x18003a416  nop     word ptr [rax+rax+00000000h]
0x18003a420  mov     [rax], r12b
0x18003a423  lea     rax, [rax+1]
0x18003a427  sub     rcx, rsi
0x18003a42a  jnz     short loc_18003A420
0x18003a42c  xorps   xmm0, xmm0
0x18003a42f  mov     [rbp+57h+var_A0+4], edi
0x18003a432  movups  xmmword ptr [rbp-49h], xmm0
0x18003a436  mov     ecx, 10h
0x18003a43b  lea     rax, [rbp+57h+var_60]
0x18003a43f  nop
0x18003a440  mov     [rax], r12b
0x18003a443  lea     rax, [rax+1]
0x18003a447  sub     rcx, rsi
0x18003a44a  jnz     short loc_18003A440
0x18003a44c  lea     rdx, [rbp+57h+var_A0]
0x18003a450  mov     ecx, esi
0x18003a452  call    cs:__imp_EtwEventActivityIdControl
0x18003a458  test    eax, eax
0x18003a45a  jle     short loc_18003A466
0x18003a45c  movzx   eax, ax
0x18003a45f  or      eax, 80070000h
0x18003a464  test    eax, eax
0x18003a466  js      loc_18003AE86
0x18003a46c  movaps  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18003a470  movdqa  [rbp+57h+var_60], xmm0
0x18003a475  test    rbx, rbx
0x18003a478  jnz     short loc_18003A4AD
0x18003a47a  mov     rdi, [rbp+5Fh]
0x18003a47e  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18003a486  inc     esi
0x18003a488  call    cs:__imp_GetTickCount
0x18003a48e  mov     ebx, eax
0x18003a490  call    cs:__imp_GetCurrentProcessId
0x18003a496  mov     [rbp+57h+var_90.Data1], edi
0x18003a499  xor     edi, edi
0x18003a49b  mov     dword ptr [rbp+57h+var_90.Data2], esi
0x18003a49e  mov     esi, 1
0x18003a4a3  mov     dword ptr [rbp+57h+var_90.Data4], ebx
0x18003a4a6  lea     rbx, [rbp+57h+var_90]
0x18003a4aa  mov     dword ptr [rbp+57h+var_90.Data4+4], eax
0x18003a4ad  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r12d; int g_fEtwCorrelationProviderInitialized
0x18003a4b4  jz      short loc_18003A4C4
0x18003a4b6  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18003a4bc  test    eax, eax
0x18003a4be  jnz     loc_18003AB9C
0x18003a4c4  mov     rdx, rbx
0x18003a4c7  mov     [rbp+57h+var_A0+4], edi
0x18003a4ca  mov     ecx, 2
0x18003a4cf  call    cs:__imp_EtwEventActivityIdControl
0x18003a4d5  test    eax, eax
0x18003a4d7  jle     short loc_18003A4E3
0x18003a4d9  movzx   eax, ax
0x18003a4dc  or      eax, 80070000h
0x18003a4e1  test    eax, eax
0x18003a4e3  js      loc_18003B00E
0x18003a4e9  movaps  xmm0, [rbp+57h+var_60]
0x18003a4ed  mov     rbx, qword ptr [rbp+57h+var_B8]
0x18003a4f1  movups  [rbp+57h+var_80], xmm0
0x18003a4f5  mov     [rbp+57h+var_70], esi
0x18003a4f8  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a4ff  jnz     loc_18003ACBF
0x18003a505  mov     edx, 646C6957h
0x18003a50a  mov     rcx, rbx
0x18003a50d  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003a512  mov     esi, eax
0x18003a514  test    eax, eax
0x18003a516  jnz     short loc_18003A55E
0x18003a518  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003a51f  jnz     loc_18003AF70
0x18003a525  mov     r9, [rbx+20h]
0x18003a529  mov     eax, r13d
0x18003a52c  lock xadd [rbx+2Ch], eax
0x18003a531  sub     eax, 1
0x18003a534  jz      loc_18003AB1F
0x18003a53a  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003a541  jnz     loc_18003AFD2
0x18003a547  test    edi, edi
0x18003a549  jnz     loc_18003AB41
0x18003a54f  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003a556  jnz     loc_18003AF8F
0x18003a55c  xor     edi, edi
0x18003a55e  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a565  jnz     loc_18003AA4E
0x18003a56b  mov     esi, 1
0x18003a570  mov     r9, [rbp+57h+var_C8]
0x18003a574  mov     r8, [rbp+57h+var_C0]
0x18003a578  mov     eax, [rbp+57h+var_CC]
0x18003a57b  test    byte ptr cs:xmmword_180107A60, 4
0x18003a582  jnz     loc_18003AB59
0x18003a588  cmp     cs:?GlobalDataInitialized@@3HA, r12d; int GlobalDataInitialized
0x18003a58f  mov     [rsp+110h+var_30], r14
0x18003a597  jz      loc_18003B01A
0x18003a59d  mov     r13, rdi
0x18003a5a0  mov     [rbp+57h+var_B8], esi
0x18003a5a3  mov     r14, rdi
0x18003a5a6  mov     rbx, rdi
0x18003a5a9  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a5b0  jnz     loc_18003ACE5
0x18003a5b6  test    r15, r15
0x18003a5b9  jz      loc_18003A8B4
0x18003a5bf  mov     edx, 646C6957h
0x18003a5c4  mov     rcx, r15
0x18003a5c7  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003a5cc  test    eax, eax
0x18003a5ce  jnz     loc_18003A8B4
0x18003a5d4  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003a5db  jnz     loc_18003AA6C
0x18003a5e1  mov     eax, [r15+30h]
0x18003a5e5  test    eax, eax
0x18003a5e7  jnz     loc_18003AE20
0x18003a5ed  mov     eax, [r15+2Ch]
0x18003a5f1  test    eax, eax
0x18003a5f3  jle     loc_18003AEEE
0x18003a5f9  lea     ecx, [rax+1]
0x18003a5fc  lock cmpxchg [r15+2Ch], ecx
0x18003a602  jnz     short loc_18003A5ED
0x18003a604  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003a60b  jnz     loc_18003AE5A
0x18003a611  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003a618  jnz     loc_18003AAD9
0x18003a61e  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x18003a625  test    al, 2
0x18003a627  jnz     loc_18003ADAC
0x18003a62d  cmp     edi, 6
0x18003a630  jnz     loc_18003A8E7
0x18003a636  mov     [rbp+57h+var_B0], r15
0x18003a63a  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a641  jnz     loc_18003AD10
0x18003a647  test    edi, edi
0x18003a649  jnz     loc_18003A74F
0x18003a64f  mov     rsi, [rbp+57h+var_B0]
0x18003a653  mov     edx, 71655248h
0x18003a658  mov     rcx, rsi
0x18003a65b  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003a660  mov     edi, eax
0x18003a662  test    eax, eax
0x18003a664  jnz     loc_18003ACDD
0x18003a66a  mov     r14, [rbp+57h+var_B0]
0x18003a66e  cmp     [rbp+57h+var_CC], r12d
0x18003a672  jz      loc_18003AD2E
0x18003a678  mov     r12d, [rsi+8Ch]
0x18003a67f  lea     rcx, [r14+148h]; lpCriticalSection
0x18003a686  call    cs:__imp_EnterCriticalSection
0x18003a68c  mov     rbx, [r14+1C0h]
0x18003a693  test    rbx, rbx
0x18003a696  jz      loc_18003B042
0x18003a69c  mov     rax, [rbx]
0x18003a69f  mov     rcx, rbx
0x18003a6a2  mov     rax, [rax]
0x18003a6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6aa  lea     rcx, [r14+148h]; lpCriticalSection
0x18003a6b1  call    cs:__imp_LeaveCriticalSection
0x18003a6b7  lea     rcx, [r14+148h]; lpCriticalSection
0x18003a6be  call    cs:__imp_EnterCriticalSection
0x18003a6c4  mov     r13, [r14+0A8h]
0x18003a6cb  lea     rcx, [r14+148h]; lpCriticalSection
0x18003a6d2  mov     esi, [r14+0B4h]
0x18003a6d9  mov     r15, [r14+40h]
0x18003a6dd  inc     dword ptr [r14+1B8h]
0x18003a6e4  call    cs:__imp_LeaveCriticalSection
0x18003a6ea  cmp     dword ptr [r14+8Ch], 0
0x18003a6f2  jz      short loc_18003A70B
0x18003a6f4  test    r13, r13
0x18003a6f7  jz      short loc_18003A70B
0x18003a6f9  mov     eax, esi
0x18003a6fb  and     eax, 300000h
0x18003a700  cmp     eax, 300000h
0x18003a705  jz      loc_18003ADA0
0x18003a70b  mov     r8d, [rbp+57h+var_CC]; unsigned int
0x18003a70f  lea     r9, [rbp+57h+var_A0]; unsigned int *
0x18003a713  mov     rdx, [rbp+57h+var_C0]; unsigned __int8 *
0x18003a717  and     esi, 0F681FFFFh
0x18003a71d  mov     qword ptr [rsp+110h+var_E0+8], r15; unsigned __int64
0x18003a722  mov     rcx, rbx; this
0x18003a725  mov     [rsp+110h+var_E0], esi; unsigned int
0x18003a729  mov     esi, [rbp+57h+var_B8]
0x18003a72c  mov     [rsp+110h+var_E8], r13; void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x18003a731  mov     [rsp+110h+var_F0], esi; int
0x18003a735  mov     [rbp+57h+var_A0], 0
0x18003a73c  call    ?WriteData@HTTP_USER_REQUEST@@QEAAKQEAEKPEAKHP6AXPEAX_KK2K@ZK3@Z; HTTP_USER_REQUEST::WriteData(uchar * const,ulong,ulong *,int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)
0x18003a741  mov     edi, eax
0x18003a743  test    eax, eax
0x18003a745  jz      loc_18003ABCE
0x18003a74b  mov     r12d, [rbp+57h+var_D0]
0x18003a74f  mov     r15, [rbp+57h+var_C8]
0x18003a753  cmp     edi, 3E5h
0x18003a759  mov     eax, 1
0x18003a75e  cmovz   r12d, eax
0x18003a762  test    r13, r13
0x18003a765  jz      short loc_18003A778
0x18003a767  test    esi, esi
0x18003a769  jnz     loc_18003AF45
0x18003a76f  test    r12d, r12d
0x18003a772  jz      loc_18003AF45
0x18003a778  test    rbx, rbx
0x18003a77b  jz      short loc_18003A78C
0x18003a77d  mov     rax, [rbx]
0x18003a780  mov     rcx, rbx
0x18003a783  mov     rax, [rax+8]
0x18003a787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a78c  mov     r13d, 0FFFFFFFFh
0x18003a792  mov     rbx, [rbp+57h+var_B0]
0x18003a796  test    rbx, rbx
0x18003a799  jz      short loc_18003A816
0x18003a79b  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003a7a2  jnz     loc_18003ABB0
0x18003a7a8  mov     edx, 646C6957h
0x18003a7ad  mov     rcx, rbx
0x18003a7b0  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003a7b5  mov     r14d, eax
0x18003a7b8  test    eax, eax
0x18003a7ba  jnz     short loc_18003A801
0x18003a7bc  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003a7c3  jnz     loc_18003AF26
0x18003a7c9  mov     r9, [rbx+20h]
  ... truncated ...
```
