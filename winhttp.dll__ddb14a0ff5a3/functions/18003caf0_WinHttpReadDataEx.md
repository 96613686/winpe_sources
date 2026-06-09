# WinHttpReadDataEx

- ea: `0x18003caf0`
- end: `0x18003d99c`
- name: `WinHttpReadDataEx`
- size: `3756`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003dc40`

## callees

- `0x180010f50`
- `0x1800141e0`
- `0x180033058`
- `0x180033404`
- `0x1800339d0`
- `0x180033a70`
- `0x18003bc60`
- `0x18003caf0`
- `0x18003dd30`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dc0a8`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d3ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cedd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d3ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d400`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d93e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d400`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d93e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cfd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cfd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ccd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d361`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ccd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d361`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ccd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003d359`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ccd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003d359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0b6`
- `ntdll!EtwEventActivityIdControl` at `0x18003cc96`
- `ntdll!EtwEventActivityIdControl` at `0x18003cd13`
- `ntdll!EtwEventActivityIdControl` at `0x18003d1d9`
- `ntdll!EtwEventActivityIdControl` at `0x18003d398`
- `ntdll!EtwEventActivityIdControl` at `0x18003d472`
- `ntdll!EtwEventActivityIdControl` at `0x18003cc96`
- `ntdll!EtwEventActivityIdControl` at `0x18003cd13`
- `ntdll!EtwEventActivityIdControl` at `0x18003d1d9`
- `ntdll!EtwEventActivityIdControl` at `0x18003d398`
- `ntdll!EtwEventActivityIdControl` at `0x18003d472`

## pseudocode

```c
__int64 __fastcall WinHttpReadDataEx(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  __int64 v7; // rdi
  signed __int32 v9; // ecx
  char v10; // al
  HTTP_REQUEST_HANDLE_OBJECT *v11; // r13
  HTTP_USER_REQUEST *v12; // r12
  __int64 v13; // rbx
  unsigned int v14; // edi
  signed __int32 v15; // eax
  struct _GUID *v16; // rbx
  struct _GUID *v17; // rax
  __int64 v18; // rcx
  struct _GUID *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  struct _GUID *v22; // rax
  int v23; // eax
  unsigned __int64 v24; // rcx
  const struct _GUID *v25; // r9
  bool v26; // sf
  signed __int32 v27; // esi
  DWORD v28; // ebx
  DWORD CurrentProcessId; // eax
  int v30; // eax
  bool v31; // sf
  __int64 v32; // rbx
  unsigned int IsValid; // esi
  __int64 v34; // r9
  BOOL v35; // edi
  unsigned int v36; // edi
  signed __int32 v37; // eax
  char v38; // al
  HTTP_REQUEST_HANDLE_OBJECT *v39; // rbx
  int v40; // r14d
  void (*v41)(void *, unsigned __int64, unsigned int, void *, unsigned int); // rax
  int v42; // edi
  unsigned __int64 v43; // rsi
  unsigned int v44; // eax
  unsigned int v45; // r14d
  void (*v46)(void *, unsigned __int64, unsigned int, void *, unsigned int); // rax
  char *v47; // rax
  HTTP_COMPLETION_PACKET *v48; // rbx
  unsigned int v49; // r15d
  unsigned __int8 *v50; // rcx
  struct _INTERNET_THREAD_INFO *ThreadInfo; // rax
  struct _INTERNET_THREAD_INFO *v52; // rsi
  unsigned int v53; // ecx
  void *v54; // rcx
  HTTP_REQUEST_HANDLE_OBJECT *v55; // rbx
  __int64 v56; // r8
  unsigned int v57; // r15d
  __int64 v58; // r9
  BOOL v59; // esi
  int v60; // eax
  bool v61; // sf
  bool v63; // zf
  int v64; // edx
  __int64 v65; // rcx
  struct _GUID *v66; // rax
  struct _GUID *v67; // rax
  __int64 v68; // rcx
  signed __int32 v69; // esi
  DWORD TickCount; // ebx
  unsigned __int64 v71; // rcx
  const struct _GUID *v72; // r9
  int v73; // eax
  bool v74; // sf
  int v75; // edx
  int v76; // eax
  bool v77; // sf
  unsigned __int64 v78; // r9
  int v79[2]; // [rsp+20h] [rbp-D1h]
  void (*v80)(void *, unsigned __int64, unsigned int, void *, unsigned int); // [rsp+50h] [rbp-A1h]
  int v81; // [rsp+58h] [rbp-99h]
  unsigned int v82; // [rsp+5Ch] [rbp-95h]
  unsigned int v83; // [rsp+60h] [rbp-91h] BYREF
  _DWORD *v84; // [rsp+68h] [rbp-89h]
  unsigned __int8 *v85; // [rsp+70h] [rbp-81h]
  __int64 v86; // [rsp+78h] [rbp-79h]
  HTTP_REQUEST_HANDLE_OBJECT *v87; // [rsp+80h] [rbp-71h] BYREF
  __int64 v88; // [rsp+88h] [rbp-69h] BYREF
  struct _GUID v89; // [rsp+90h] [rbp-61h] BYREF
  struct _GUID v90; // [rsp+A0h] [rbp-51h] BYREF
  struct _GUID v91; // [rsp+B0h] [rbp-41h] BYREF
  int v92; // [rsp+C0h] [rbp-31h]
  struct _GUID v93; // [rsp+D0h] [rbp-21h] BYREF
  _UNKNOWN *retaddr; // [rsp+138h] [rbp+47h]

  v7 = a7;
  v84 = (_DWORD *)a4;
  v9 = 0;
  v85 = a2;
  v10 = a3;
  v82 = a3;
  v86 = a7;
  v11 = 0;
  v87 = 0;
  v12 = 0;
  v83 = 0;
  v81 = 1;
  v91 = 0;
  v92 = 0;
  v88 = 0;
  if ( WinHttpEtwInitialized )
  {
    if ( !a1 )
    {
      v65 = 16;
      v66 = &v91;
      do
      {
        LOBYTE(v66->Data1) = 0;
        v66 = (struct _GUID *)((char *)v66 + 1);
        --v65;
      }
      while ( v65 );
      v92 = 0;
      v67 = &v91;
      v90 = 0;
      v68 = 16;
      v93 = 0;
      do
      {
        LOBYTE(v67->Data1) = 0;
        v67 = (struct _GUID *)((char *)v67 + 1);
        --v68;
      }
      while ( v68 );
      WxEtwGetActivityId(&v93);
      v69 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
      TickCount = GetTickCount();
      *(_DWORD *)&v90.Data4[4] = GetCurrentProcessId();
      v90.Data1 = (unsigned int)retaddr;
      *(_DWORD *)&v90.Data2 = v69;
      *(_DWORD *)v90.Data4 = TickCount;
      if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v71, &ActivityStart, &v90, v72, v79[0]);
      *(_DWORD *)&v89.Data2 = 0;
      v73 = EtwEventActivityIdControl(2, &v90);
      v74 = v73 < 0;
      if ( v73 > 0 )
        v74 = 1;
      if ( v74 )
        *(_DWORD *)&v89.Data2 = 144;
      v92 = 1;
      v91 = v93;
      goto LABEL_55;
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, a1, (__int64)&v88);
    if ( (unsigned int)HANDLE_OBJECT::IsValid(a1, 1684826455) )
    {
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v75 = 11;
        goto LABEL_177;
      }
    }
    else
    {
      v13 = a1;
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      if ( *(_DWORD *)(a1 + 48) )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_qq(1032, 20, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, *(_QWORD *)(a1 + 32), a1);
        v14 = 6;
      }
      else
      {
        v14 = 0;
      }
      while ( 1 )
      {
        v15 = *(_DWORD *)(a1 + 44);
        if ( v15 <= 0 )
          break;
        v9 = v15 + 1;
        if ( v15 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 44), v15 + 1, v15) )
          goto LABEL_12;
      }
      v14 = 5;
LABEL_12:
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(1045, 21, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, *(_QWORD *)(a1 + 32), a1);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v14, *(_QWORD *)v79);
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v14, *(_QWORD *)v79);
      if ( v14 == 6 || !v14 )
        goto LABEL_19;
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v75 = 13;
LABEL_177:
        WPP_SF_qq(529, v75, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, a1, a1);
      }
    }
    v13 = 0;
    v14 = 6;
LABEL_19:
    v88 = v13;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v14, *(_QWORD *)v79);
      v13 = v88;
    }
    if ( v13 )
    {
      if ( v92 )
      {
        *(_DWORD *)&v89.Data2 = 0;
        v76 = EtwEventActivityIdControl(2, &v91);
        v77 = v76 < 0;
        if ( v76 > 0 )
          v77 = 1;
        if ( v77 )
          *(_DWORD *)&v89.Data2 = 144;
        v13 = v88;
      }
      v16 = (struct _GUID *)(v13 + 184);
      v17 = &v91;
      v18 = 16;
      do
      {
        LOBYTE(v17->Data1) = 0;
        v17 = (struct _GUID *)((char *)v17 + 1);
        --v18;
      }
      while ( v18 );
      v92 = 0;
      v19 = &v91;
      v90 = 0;
      v20 = 16;
      v93 = 0;
      do
      {
        LOBYTE(v19->Data1) = 0;
        v19 = (struct _GUID *)((char *)v19 + 1);
        --v20;
      }
      while ( v20 );
      v89 = 0;
      v21 = 16;
      v22 = &v93;
      do
      {
        LOBYTE(v22->Data1) = 0;
        v22 = (struct _GUID *)((char *)v22 + 1);
        --v21;
      }
      while ( v21 );
      v23 = EtwEventActivityIdControl(1, &v89);
      v26 = v23 < 0;
      if ( v23 > 0 )
        v26 = 1;
      if ( v26 )
        *(_DWORD *)&v89.Data2 = 128;
      else
        v93 = v89;
      if ( !v16 )
      {
        v27 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        v28 = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        *(_DWORD *)&v90.Data2 = v27;
        *(_DWORD *)v90.Data4 = v28;
        v16 = &v90;
        *(_DWORD *)&v90.Data4[4] = CurrentProcessId;
        v90.Data1 = (unsigned int)retaddr;
      }
      if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v24, &ActivityStart, v16, v25, v79[0]);
      *(_DWORD *)&v89.Data2 = 0;
      v30 = EtwEventActivityIdControl(2, v16);
      v31 = v30 < 0;
      if ( v30 > 0 )
        v31 = 1;
      if ( v31 )
        *(_DWORD *)&v89.Data2 = 144;
      v32 = v88;
      v91 = v93;
      v92 = 1;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
      IsValid = HANDLE_OBJECT::IsValid(v32, 1684826455);
      if ( !IsValid )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
        v34 = *(_QWORD *)(v32 + 32);
        v35 = _InterlockedDecrement((volatile signed __int32 *)(v32 + 44)) == 0;
        if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v34, v32);
        if ( v35 )
          (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v32)(v32, 1, a3, v34);
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v35, *(_QWORD *)v79);
      }
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, *(_QWORD *)v79);
    }
LABEL_55:
    v7 = v86;
    v10 = v82;
    a2 = v85;
    a4 = (__int64)v84;
  }
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qqdqIdq(v9, (_DWORD)a2, a3, a1, (__int64)a2, v10, a4, a5, a6, v7);
  if ( !GlobalDataInitialized )
  {
    v36 = 12172;
    v46 = 0;
    goto LABEL_173;
  }
  if ( (a5 & 0xFFFFFFFFFFFFFFFEuLL) != 0 || a6 || v7 )
  {
    v36 = 87;
    v46 = 0;
    goto LABEL_173;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, a1, (__int64)&v87);
  if ( !a1 || (unsigned int)HANDLE_OBJECT::IsValid(a1, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v64 = 11;
      goto LABEL_175;
    }
LABEL_136:
    a1 = 0;
    v36 = 6;
    goto LABEL_79;
  }
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  if ( *(_DWORD *)(a1 + 48) )
  {
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_qq(1032, 20, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, *(_QWORD *)(a1 + 32), a1);
    v36 = 6;
  }
  else
  {
    v36 = 0;
  }
  while ( 1 )
  {
    v37 = *(_DWORD *)(a1 + 44);
    if ( v37 <= 0 )
      break;
    if ( v37 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 44), v37 + 1, v37) )
      goto LABEL_72;
  }
  v36 = 5;
LABEL_72:
  if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_qqD(1045, 21, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, *(_QWORD *)(a1 + 32), a1);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v36, *(_QWORD *)v79);
  v38 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v36, *(_QWORD *)v79);
    v38 = BYTE2(xmmword_180107A50);
  }
  if ( v36 != 6 && v36 )
  {
    if ( (v38 & 2) != 0 )
    {
      v64 = 13;
LABEL_175:
      WPP_SF_qq(529, v64, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, a1, a1);
      goto LABEL_136;
    }
    goto LABEL_136;
  }
LABEL_79:
  v87 = (HTTP_REQUEST_HANDLE_OBJECT *)a1;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v36, *(_QWORD *)v79);
  if ( v36 || (v39 = v87, (v36 = HANDLE_OBJECT::IsValid(v87, 1902465608)) != 0) )
  {
    v46 = 0;
    goto LABEL_144;
  }
  v11 = v87;
  v40 = *((_DWORD *)v39 + 35);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v87 + 328));
  v12 = (HTTP_USER_REQUEST *)*((_QWORD *)v11 + 56);
  if ( !v12 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
    v46 = 0;
    v12 = 0;
    v36 = 6;
    goto LABEL_173;
  }
  (**(void (__fastcall ***)(_QWORD))v12)(*((_QWORD *)v11 + 56));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
  v41 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))*((_QWORD *)v11 + 21);
  v42 = *((_DWORD *)v11 + 45);
  v43 = *((_QWORD *)v11 + 8);
  ++*((_DWORD *)v11 + 110);
  v80 = v41;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
  if ( *((_DWORD *)v11 + 35) && v80 && (v42 & 0x280000) == 0x280000 )
    v81 = 0;
  v44 = HTTP_USER_REQUEST::ReadData(v12, v85, v82, &v83, v81, a5 & 1, v80, v42 & 0xF681FFFF, v43);
  v36 = v44;
  if ( v44 )
  {
    v63 = v44 == 997;
    v46 = v80;
    if ( v63 )
    {
LABEL_145:
      v45 = 1;
      goto LABEL_102;
    }
    goto LABEL_144;
  }
  if ( v81 )
  {
    v45 = 1;
    if ( v84 )
      *v84 = v83;
    v46 = v80;
    goto LABEL_102;
  }
  v47 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
  v48 = (HTTP_COMPLETION_PACKET *)v47;
  if ( !v47 )
  {
    v46 = v80;
    v36 = 8;
    goto LABEL_173;
  }
  v81 = 0;
  *((_QWORD *)v47 + 9) = 0;
  *((_QWORD *)v47 + 11) = 0;
  *((_QWORD *)v47 + 10) = 0;
  *((_OWORD *)v47 + 6) = 0;
  *((_QWORD *)v47 + 8) = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
  *(_QWORD *)v47 = 0;
  *((_QWORD *)v47 + 1) = 0;
  *((_QWORD *)v47 + 2) = 0;
  *((_QWORD *)v47 + 3) = 0;
  *((_QWORD *)v47 + 4) = 0;
  *(_OWORD *)(v47 + 40) = 0;
  *((_QWORD *)v47 + 7) = 0;
  v49 = v83;
  if ( v40 )
  {
    v36 = 0;
    v50 = v85;
    *(_QWORD *)v47 = v80;
    *((_QWORD *)v47 + 1) = v43;
    *((_DWORD *)v47 + 4) = 3;
    *((_DWORD *)v47 + 5) = 0x80000;
    *((_QWORD *)v47 + 3) = v50;
    *((_DWORD *)v47 + 8) = v49;
    if ( (char *)v80 == (char *)HTTP_USER_REQUEST::PrvResendStatusCallback )
    {
      v79[0] = v49;
      ((void (__fastcall *)(_QWORD, unsigned __int64, __int64, unsigned __int8 *))v80)(0, v43, 0x80000, v50);
      HTTP_COMPLETION_PACKET::`scalar deleting destructor'(v48);
    }
    else if ( v80 )
    {
      ThreadInfo = InternetGetThreadInfo();
      v52 = ThreadInfo;
      if ( ThreadInfo && (v53 = *((_DWORD *)ThreadInfo + 6), v53 <= 2) )
      {
        *((_DWORD *)ThreadInfo + 6) = v53 + 1;
        HTTP_REQUEST_HANDLE_OBJECT::_SafeAppCallback(v11, v48);
        --*((_DWORD *)v52 + 6);
        v54 = (void *)*((_QWORD *)v48 + 10);
        *((_QWORD *)v48 + 8) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
        if ( v54 )
        {
          CloseHandle(v54);
          *((_QWORD *)v48 + 10) = 0;
        }
        operator delete(v48);
      }
      else
      {
        v36 = HTTP_REQUEST_HANDLE_OBJECT::QueueCompletionPacket(v11, v48);
      }
    }
  }
  if ( v84 )
    *v84 = v49;
  v46 = v80;
  v45 = 1;
  if ( v36 )
  {
LABEL_144:
    if ( v36 == 997 )
      goto LABEL_145;
LABEL_173:
    v45 = 0;
  }
LABEL_102:
  if ( v46 && (v81 || !v45) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
    --*((_DWORD *)v11 + 110);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 328));
  }
  if ( v12 )
    (*(void (__fastcall **)(HTTP_USER_REQUEST *))(*(_QWORD *)v12 + 8LL))(v12);
  v55 = v87;
  if ( v87 )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
    v57 = HANDLE_OBJECT::IsValid(v55, 1684826455);
    if ( !v57 )
    {
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      v58 = *((_QWORD *)v55 + 4);
      v59 = _InterlockedDecrement((volatile signed __int32 *)v55 + 11) == 0;
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v58, (__int64)v55);
      if ( v59 )
        (**(void (__fastcall ***)(HTTP_REQUEST_HANDLE_OBJECT *, __int64, __int64, __int64))v55)(v55, 1, v56, v58);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v59, *(_QWORD *)v79);
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v57, *(_QWORD *)v79);
    v87 = 0;
  }
  if ( v81 || !v45 )
  {
    if ( (xmmword_180107A60 & 2) != 0 )
    {
      v78 = (unsigned __int64)v84;
      if ( v84 )
        v78 = (unsigned int)*v84;
      WPP_SF_d(1025, 23, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v78, *(_QWORD *)v79);
    }
    if ( !v45 && (xmmword_180107A50 & 4) != 0 )
      WPP_SF_d(514, 24, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v36, *(_QWORD *)v79);
  }
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 25, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v45, *(_QWORD *)v79);
  if ( v92 )
  {
    HIDWORD(v86) = 0;
    v60 = EtwEventActivityIdControl(2, &v91);
    v61 = v60 < 0;
    if ( v60 > 0 )
      v61 = 1;
    if ( v61 )
      HIDWORD(v86) = 144;
  }
  return v36;
}

```

## disassembly

```asm
0x18003caf0  push    rbp
0x18003caf2  push    rbx
0x18003caf3  push    rsi
0x18003caf4  push    rdi
0x18003caf5  push    r12
0x18003caf7  push    r13
0x18003caf9  push    r14
0x18003cafb  push    r15
0x18003cafd  lea     rbp, [rsp-7]
0x18003cb02  sub     rsp, 0F8h
0x18003cb09  mov     rax, cs:__security_cookie
0x18003cb10  xor     rax, rsp
0x18003cb13  mov     [rbp+3Fh+var_50], rax
0x18003cb17  mov     rdi, [rbp+3Fh+arg_30]
0x18003cb1b  xor     esi, esi
0x18003cb1d  mov     r14, rcx
0x18003cb20  mov     [rsp+130h+var_C8], r9
0x18003cb25  xor     ecx, ecx
0x18003cb27  mov     [rsp+130h+var_C0], rdx
0x18003cb2c  cmp     cs:?WinHttpEtwInitialized@@3EA, cl; uchar WinHttpEtwInitialized
0x18003cb32  mov     eax, r8d
0x18003cb35  xorps   xmm0, xmm0
0x18003cb38  mov     [rsp+130h+var_D4], eax
0x18003cb3c  mov     [rbp+3Fh+var_B8], rdi
0x18003cb40  mov     r13d, esi
0x18003cb43  mov     [rbp+3Fh+var_B0], rsi
0x18003cb47  mov     r12d, esi
0x18003cb4a  mov     [rsp+130h+var_D0], esi
0x18003cb4e  mov     [rsp+130h+var_E0], rsi
0x18003cb53  mov     [rsp+130h+var_D8], 1
0x18003cb5b  movups  [rbp+3Fh+var_80], xmm0
0x18003cb5f  mov     [rbp+3Fh+var_70], ecx
0x18003cb62  mov     [rbp+3Fh+var_A8], rsi
0x18003cb66  jz      loc_18003CDC9
0x18003cb6c  test    r14, r14
0x18003cb6f  jz      loc_18003D2EF
0x18003cb75  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003cb7c  jnz     loc_18003D63F
0x18003cb82  mov     edx, 646C6957h
0x18003cb87  mov     rcx, r14
0x18003cb8a  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003cb8f  test    eax, eax
0x18003cb91  jnz     loc_18003D257
0x18003cb97  mov     rbx, r14
0x18003cb9a  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003cba1  jnz     loc_18003D495
0x18003cba7  mov     eax, [r14+30h]
0x18003cbab  test    eax, eax
0x18003cbad  jnz     loc_18003D756
0x18003cbb3  mov     edi, esi
0x18003cbb5  mov     eax, [r14+2Ch]
0x18003cbb9  test    eax, eax
0x18003cbbb  jle     loc_18003D848
0x18003cbc1  lea     ecx, [rax+1]
0x18003cbc4  lock cmpxchg [r14+2Ch], ecx
0x18003cbca  jnz     short loc_18003CBB5
0x18003cbcc  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003cbd3  jnz     loc_18003D7BE
0x18003cbd9  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003cbe0  jnz     loc_18003D4DC
0x18003cbe6  test    byte ptr cs:xmmword_180107A50+2, 2
0x18003cbed  jnz     loc_18003D6E7
0x18003cbf3  cmp     edi, 6
0x18003cbf6  jnz     loc_18003D3C6
0x18003cbfc  mov     [rbp+3Fh+var_A8], rbx
0x18003cc00  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003cc07  jnz     loc_18003D693
0x18003cc0d  test    rbx, rbx
0x18003cc10  jz      loc_18003CDB7
0x18003cc16  cmp     [rbp+3Fh+var_70], esi
0x18003cc19  jnz     loc_18003D466
0x18003cc1f  add     rbx, 0B8h
0x18003cc26  lea     rax, [rbp+3Fh+var_80]
0x18003cc2a  mov     ecx, 10h
0x18003cc2f  nop
0x18003cc30  mov     [rax], sil
0x18003cc33  lea     rax, [rax+1]
0x18003cc37  sub     rcx, 1
0x18003cc3b  jnz     short loc_18003CC30
0x18003cc3d  xorps   xmm0, xmm0
0x18003cc40  mov     [rbp+3Fh+var_70], esi
0x18003cc43  xorps   xmm1, xmm1
0x18003cc46  lea     rax, [rbp+3Fh+var_80]
0x18003cc4a  movups  xmmword ptr [rbp+3Fh+var_90.Data1], xmm0
0x18003cc4e  mov     ecx, 10h
0x18003cc53  movups  xmmword ptr [rbp+3Fh+var_60.Data1], xmm1
0x18003cc57  nop     word ptr [rax+rax+00000000h]
0x18003cc60  mov     [rax], sil
0x18003cc63  lea     rax, [rax+1]
0x18003cc67  sub     rcx, 1
0x18003cc6b  jnz     short loc_18003CC60
0x18003cc6d  xorps   xmm0, xmm0
0x18003cc70  mov     dword ptr [rbp+3Fh+var_A0+4], esi
0x18003cc73  movups  xmmword ptr [rbp-61h], xmm0
0x18003cc77  mov     ecx, 10h
0x18003cc7c  lea     rax, [rbp+3Fh+var_60]
0x18003cc80  mov     [rax], sil
0x18003cc83  lea     rax, [rax+1]
0x18003cc87  sub     rcx, 1
0x18003cc8b  jnz     short loc_18003CC80
0x18003cc8d  lea     rdx, [rbp+3Fh+var_A0]
0x18003cc91  mov     ecx, 1
0x18003cc96  call    cs:__imp_EtwEventActivityIdControl
0x18003cc9c  test    eax, eax
0x18003cc9e  jle     short loc_18003CCAA
0x18003cca0  movzx   eax, ax
0x18003cca3  or      eax, 80070000h
0x18003cca8  test    eax, eax
0x18003ccaa  js      loc_18003D7B2
0x18003ccb0  movaps  xmm0, [rbp+3Fh+var_A0]
0x18003ccb4  movdqa  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x18003ccb9  test    rbx, rbx
0x18003ccbc  jnz     short loc_18003CCF1
0x18003ccbe  mov     rdi, [rbp+47h]
0x18003ccc2  mov     esi, 1
0x18003ccc7  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18003cccf  inc     esi
0x18003ccd1  call    cs:__imp_GetTickCount
0x18003ccd7  mov     ebx, eax
0x18003ccd9  call    cs:__imp_GetCurrentProcessId
0x18003ccdf  mov     dword ptr [rbp+3Fh+var_90.Data2], esi
0x18003cce2  xor     esi, esi
0x18003cce4  mov     dword ptr [rbp+3Fh+var_90.Data4], ebx
0x18003cce7  lea     rbx, [rbp+3Fh+var_90]
0x18003cceb  mov     dword ptr [rbp+3Fh+var_90.Data4+4], eax
0x18003ccee  mov     [rbp+3Fh+var_90.Data1], edi
0x18003ccf1  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r12d; int g_fEtwCorrelationProviderInitialized
0x18003ccf8  jz      short loc_18003CD08
0x18003ccfa  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18003cd00  test    eax, eax
0x18003cd02  jnz     loc_18003D560
0x18003cd08  mov     rdx, rbx
0x18003cd0b  mov     dword ptr [rbp+3Fh+var_A0+4], esi
0x18003cd0e  mov     ecx, 2
0x18003cd13  call    cs:__imp_EtwEventActivityIdControl
0x18003cd19  test    eax, eax
0x18003cd1b  jle     short loc_18003CD27
0x18003cd1d  movzx   eax, ax
0x18003cd20  or      eax, 80070000h
0x18003cd25  test    eax, eax
0x18003cd27  js      loc_18003D920
0x18003cd2d  movaps  xmm0, xmmword ptr [rbp+3Fh+var_60.Data1]
0x18003cd31  mov     rbx, [rbp+3Fh+var_A8]
0x18003cd35  movups  [rbp+3Fh+var_80], xmm0
0x18003cd39  mov     [rbp+3Fh+var_70], 1
0x18003cd40  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003cd47  jnz     loc_18003D5D8
0x18003cd4d  mov     edx, 646C6957h
0x18003cd52  mov     rcx, rbx
0x18003cd55  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003cd5a  mov     esi, eax
0x18003cd5c  test    eax, eax
0x18003cd5e  jnz     short loc_18003CDA8
0x18003cd60  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003cd67  jnz     loc_18003D88F
0x18003cd6d  mov     r9, [rbx+20h]
0x18003cd71  mov     eax, 0FFFFFFFFh
0x18003cd76  lock xadd [rbx+2Ch], eax
0x18003cd7b  sub     eax, 1
0x18003cd7e  jz      loc_18003D4FA
0x18003cd84  xor     edi, edi
0x18003cd86  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003cd8d  jnz     loc_18003D8F0
0x18003cd93  test    edi, edi
0x18003cd95  jnz     loc_18003D524
0x18003cd9b  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003cda2  jnz     loc_18003D8AE
0x18003cda8  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003cdaf  jnz     loc_18003D429
0x18003cdb5  xor     esi, esi
0x18003cdb7  mov     rdi, [rbp+3Fh+var_B8]
0x18003cdbb  mov     eax, [rsp+130h+var_D4]
0x18003cdbf  mov     rdx, [rsp+130h+var_C0]
0x18003cdc4  mov     r9, [rsp+130h+var_C8]
0x18003cdc9  test    byte ptr cs:xmmword_180107A60, 4
0x18003cdd0  mov     ebx, [rbp+3Fh+arg_28]
0x18003cdd3  mov     r15, [rbp+3Fh+arg_20]
0x18003cdd7  jnz     loc_18003D66A
0x18003cddd  cmp     cs:?GlobalDataInitialized@@3HA, r12d; int GlobalDataInitialized
0x18003cde4  jz      loc_18003D779
0x18003cdea  test    r15, 0FFFFFFFFFFFFFFFEh
0x18003cdf1  jnz     loc_18003D6DA
0x18003cdf7  test    ebx, ebx
0x18003cdf9  jnz     loc_18003D6DA
0x18003cdff  test    rdi, rdi
0x18003ce02  jnz     loc_18003D6DA
0x18003ce08  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003ce0f  jnz     loc_18003D5F6
0x18003ce15  test    r14, r14
0x18003ce18  jz      loc_18003D23D
0x18003ce1e  mov     edx, 646C6957h
0x18003ce23  mov     rcx, r14
0x18003ce26  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003ce2b  test    eax, eax
0x18003ce2d  jnz     loc_18003D23D
0x18003ce33  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003ce3a  jnz     loc_18003D447
0x18003ce40  mov     eax, [r14+30h]
0x18003ce44  test    eax, eax
0x18003ce46  jnz     loc_18003D71A
0x18003ce4c  mov     edi, esi
0x18003ce4e  mov     eax, [r14+2Ch]
0x18003ce52  test    eax, eax
0x18003ce54  jle     loc_18003D81A
0x18003ce5a  lea     ecx, [rax+1]
0x18003ce5d  lock cmpxchg [r14+2Ch], ecx
0x18003ce63  jnz     short loc_18003CE4E
0x18003ce65  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18003ce6c  jnz     loc_18003D786
0x18003ce72  test    byte ptr cs:xmmword_180107A60+1, 1
0x18003ce79  jnz     loc_18003D4B4
0x18003ce7f  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x18003ce86  test    al, 2
0x18003ce88  jnz     loc_18003D6B5
0x18003ce8e  cmp     edi, 6
0x18003ce91  jnz     loc_18003D2D5
0x18003ce97  mov     [rbp+3Fh+var_B0], r14
0x18003ce9b  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003cea2  jnz     loc_18003D621
0x18003cea8  test    edi, edi
0x18003ceaa  jnz     loc_18003D504
0x18003ceb0  mov     rbx, [rbp+3Fh+var_B0]
0x18003ceb4  mov     edx, 71655248h
0x18003ceb9  mov     rcx, rbx
0x18003cebc  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003cec1  mov     edi, eax
0x18003cec3  test    eax, eax
0x18003cec5  jnz     loc_18003D504
0x18003cecb  mov     r13, [rbp+3Fh+var_B0]
0x18003cecf  mov     r14d, [rbx+8Ch]
0x18003ced6  lea     rcx, [r13+148h]; lpCriticalSection
0x18003cedd  call    cs:__imp_EnterCriticalSection
0x18003cee3  mov     r12, [r13+1C0h]
0x18003ceea  test    r12, r12
0x18003ceed  jz      loc_18003D937
0x18003cef3  mov     rax, [r12]
0x18003cef7  mov     rcx, r12
0x18003cefa  mov     rax, [rax]
0x18003cefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf02  lea     rcx, [r13+148h]; lpCriticalSection
0x18003cf09  call    cs:__imp_LeaveCriticalSection
0x18003cf0f  lea     rcx, [r13+148h]; lpCriticalSection
0x18003cf16  and     r15d, 1
0x18003cf1a  call    cs:__imp_EnterCriticalSection
0x18003cf20  mov     rax, [r13+0A8h]
0x18003cf27  lea     rcx, [r13+148h]; lpCriticalSection
0x18003cf2e  mov     edi, [r13+0B4h]
0x18003cf35  mov     rsi, [r13+40h]
0x18003cf39  inc     dword ptr [r13+1B8h]
0x18003cf40  mov     [rsp+130h+var_E0], rax
0x18003cf45  call    cs:__imp_LeaveCriticalSection
0x18003cf4b  cmp     dword ptr [r13+8Ch], 0
0x18003cf53  mov     rcx, [rsp+130h+var_E0]
0x18003cf58  jnz     loc_18003D215
0x18003cf5e  mov     r8d, [rsp+130h+var_D4]; unsigned int
0x18003cf63  lea     r9, [rsp+130h+var_D0]; unsigned int *
0x18003cf68  mov     rdx, [rsp+130h+var_C0]; unsigned __int8 *
0x18003cf6d  and     edi, 0F681FFFFh
0x18003cf73  mov     [rsp+130h+var_F0], rsi; unsigned __int64
0x18003cf78  mov     [rsp+130h+var_F8], edi; unsigned int
0x18003cf7c  mov     [rsp+130h+var_100], rcx; void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x18003cf81  mov     rcx, r12; this
0x18003cf84  mov     [rsp+130h+var_108], r15d; int
0x18003cf89  mov     r15d, [rsp+130h+var_D8]
0x18003cf8e  mov     [rsp+130h+var_110], r15d; int
0x18003cf93  call    ?ReadData@HTTP_USER_REQUEST@@QEAAKPEAEKPEAKHHP6AXPEAX_KK2K@ZK3@Z; HTTP_USER_REQUEST::ReadData(uchar *,ulong,ulong *,int,int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)
0x18003cf98  mov     edi, eax
0x18003cf9a  test    eax, eax
0x18003cf9c  jnz     loc_18003D2B2
0x18003cfa2  test    r15d, r15d
0x18003cfa5  jz      short loc_18003CFC5
0x18003cfa7  mov     rcx, [rsp+130h+var_C8]
0x18003cfac  mov     r14d, 1
0x18003cfb2  test    rcx, rcx
0x18003cfb5  jnz     loc_18003D92C
0x18003cfbb  mov     rax, [rsp+130h+var_E0]
0x18003cfc0  jmp     loc_18003D0ED
0x18003cfc5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18003cfcc  xor     edx, edx; dwFlags
0x18003cfce  mov     r8d, 80h; dwBytes
0x18003cfd4  call    cs:__imp_HeapAlloc
0x18003cfda  mov     rbx, rax
0x18003cfdd  test    rax, rax
0x18003cfe0  jz      loc_18003D54E
0x18003cfe6  xor     edx, edx
0x18003cfe8  mov     [rsp+130h+var_D8], r15d
0x18003cfed  mov     [rax+48h], rdx
0x18003cff1  xorps   xmm0, xmm0
0x18003cff4  mov     [rax+58h], rdx
0x18003cff8  mov     [rax+50h], rdx
0x18003cffc  movups  xmmword ptr [rax+60h], xmm0
0x18003d000  lea     rax, ??_7WORK_ITEM@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::WORK_ITEM::`vftable'
0x18003d007  mov     [rbx+40h], rax
0x18003d00b  mov     [rbx], rdx
0x18003d00e  mov     [rbx+8], rdx
0x18003d012  mov     [rbx+10h], rdx
0x18003d016  mov     [rbx+18h], rdx
0x18003d01a  mov     [rbx+20h], rdx
0x18003d01e  movups  xmmword ptr [rbx+28h], xmm0
0x18003d022  mov     [rbx+38h], rdx
  ... truncated ...
```
