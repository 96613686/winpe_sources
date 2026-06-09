# WDiagProcessAcmScanResult(_WD_INTERFACE_CONTEXT *,void *,_DOT11_MSM_SCAN_RESULT_LIST *,_WLAN_AVAILABLE_NETWORK_LIST_V3 *,ulong)

- ea: `0x18000f7d0`
- end: `0x180010609`
- name: `?WDiagProcessAcmScanResult@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_DOT11_MSM_SCAN_RESULT_LIST@@PEAU_WLAN_AVAILABLE_NETWORK_LIST_V3@@K@Z`
- size: `3641`
- prototype: `unsigned int(struct _WD_INTERFACE_CONTEXT *, void *, struct _DOT11_MSM_SCAN_RESULT_LIST *, struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callers

- `0x180011558`

## callees

- `0x18000aa0c`
- `0x18000ec10`
- `0x18000f120`
- `0x18000f7d0`
- `0x180010610`
- `0x1800106c0`
- `0x180011530`
- `0x180029ed4`
- `0x18007d770`
- `0x18009ae14`
- `0x1800df38c`
- `0x180106340`
- `0x180107300`
- `0x180107318`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x18001014f`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x1800101be`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x18001014f`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x1800101be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010033`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010033`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f86f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f86f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f87e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f87e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fde0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fc1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fde0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f924`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fdcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000feef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f924`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fdcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000feef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f93a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fb86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f93a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fb86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ff0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001037d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010442`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001053b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001037d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010442`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001053b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105b6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fbba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ff40`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010116`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010182`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fbba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ff40`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010116`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010182`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fa1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000fa1f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000fa34`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000fa34`

## pseudocode

```c
__int64 __fastcall WDiagProcessAcmScanResult(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        struct _DOT11_MSM_SCAN_RESULT_LIST *a3,
        struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *a4,
        unsigned int a5)
{
  struct _DOT11_MSM_SCAN_RESULT_LIST *v6; // r14
  struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *v7; // r15
  char *v8; // r13
  DWORD CurrentThreadId; // ebx
  char *v10; // r12
  unsigned int v11; // esi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  void *v14; // rdi
  int v15; // ecx
  HANDLE v16; // rax
  PVOID *v17; // rax
  unsigned int v18; // esi
  __m128i si128; // xmm6
  __int64 v20; // rbx
  char *v21; // rdi
  void **v22; // r9
  void **v23; // rcx
  WCHAR *lpWideCharStr; // rbx
  HANDLE v25; // rax
  int v26; // eax
  __int64 v27; // r14
  HANDLE v28; // rax
  void *v29; // rcx
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  const struct std::nothrow_t *v32; // rdx
  unsigned int v33; // ebx
  unsigned int v34; // esi
  HANDLE v35; // rax
  int v36; // r8d
  void *v37; // rax
  void *v38; // rbx
  void *v39; // rdi
  int v40; // r14d
  HANDLE v41; // rax
  unsigned int v42; // ebx
  __int64 v43; // rdx
  int v44; // r14d
  char *v45; // rsi
  char *v46; // r12
  WCHAR *v47; // rdi
  HANDLE v48; // rax
  int v49; // eax
  __int64 v50; // r15
  HANDLE v51; // rax
  int v53; // eax
  unsigned int v54; // esi
  __int64 v55; // r15
  int v56; // eax
  unsigned int v57; // r14d
  __int64 v58; // r12
  __int64 v59; // r15
  __int64 v60; // r14
  char v61; // al
  int cchWideChar; // [rsp+30h] [rbp-D8h]
  int v63; // [rsp+88h] [rbp-80h]
  int v64; // [rsp+88h] [rbp-80h]
  void *v65; // [rsp+90h] [rbp-78h] BYREF
  char v66[8]; // [rsp+98h] [rbp-70h] BYREF
  char v67[4]; // [rsp+A0h] [rbp-68h]
  char v68[4]; // [rsp+A4h] [rbp-64h]
  char v69[4]; // [rsp+A8h] [rbp-60h]
  char v70[4]; // [rsp+ACh] [rbp-5Ch]
  char v71[8]; // [rsp+B0h] [rbp-58h]
  void *Src; // [rsp+B8h] [rbp-50h]
  struct _DOT11_MSM_SCAN_RESULT_LIST *v73; // [rsp+C0h] [rbp-48h]
  struct _FILETIME *v74; // [rsp+C8h] [rbp-40h]
  __int64 v75; // [rsp+D0h] [rbp-38h]
  char v76[8]; // [rsp+D8h] [rbp-30h]
  char *v77; // [rsp+E0h] [rbp-28h]
  _SYSTEMTIME SystemTime; // [rsp+E8h] [rbp-20h] BYREF
  void *v79[2]; // [rsp+F8h] [rbp-10h] BYREF
  __m128i v80; // [rsp+108h] [rbp+0h]
  void *v81[3]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 v82; // [rsp+130h] [rbp+28h]
  wchar_t S1[40]; // [rsp+138h] [rbp+30h] BYREF

  v6 = a3;
  v7 = a4;
  Src = a4;
  v73 = a3;
  v74 = (struct _FILETIME *)a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 91, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  v8 = (char *)a1 + 3352;
  *(_QWORD *)v76 = (char *)a1 + 3352;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
  WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
  if ( (*((_BYTE *)a1 + 3448) & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      *((_DWORD *)a1 + 864),
      *((_QWORD *)a1 + 433),
      *((_DWORD *)a1 + 865),
      CurrentThreadId,
      (__int64)"WDiagProcessAcmScanResult",
      209);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_QWORD *)a1 + 433) = "WDiagProcessAcmScanResult";
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 1489;
  v10 = (char *)a1 + 624 * ((*((_DWORD *)a1 + 42) - 1) % 5u);
  v77 = v10;
  if ( v6 )
  {
    v11 = 504 * *(_DWORD *)v6 + 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 19, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
    v12 = 0;
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
      {
        v12 = HeapAlloc(ProcessHeap, 8u, v11);
        if ( !v12 )
          SetLastError(8u);
      }
      if ( !v12 )
      {
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 225) && *((char *)WPP_GLOBAL_Control + 228) < 0 )
          {
            GetLastError();
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_79512908d13336da9f44adf151438c1a_Traceguids, v11);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) && *((char *)v17 + 228) < 0 )
          {
            WPP_SF_d(v17[27], 20, &WPP_79512908d13336da9f44adf151438c1a_Traceguids, v11);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        v15 = 8;
        v63 = 8;
LABEL_20:
        if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 57) & 0x200) != 0 )
        {
          WPP_SF_(v17[27], 21, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
          v17 = (PVOID *)WPP_GLOBAL_Control;
          v15 = v63;
        }
        if ( v15 )
        {
          if ( v17 == &WPP_GLOBAL_Control || !*((_BYTE *)v17 + 225) || (*((_BYTE *)v17 + 228) & 4) == 0 )
            goto LABEL_64;
          cchWideChar = v15;
          WPP_SF_lll(v17[27], 94, &WPP_fec73b95d5a537674450248f38664378_Traceguids, v11);
        }
        else
        {
          if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) >= 3u && (*((_BYTE *)v17 + 228) & 4) != 0 )
            WPP_SF_d(v17[27], 92, &WPP_fec73b95d5a537674450248f38664378_Traceguids, *(unsigned int *)v6);
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          if ( !SystemTimeToFileTime(&SystemTime, v74 + 18) )
            GetLastError();
          v18 = 0;
          if ( *(_DWORD *)v6 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            while ( 1 )
            {
              v20 = 504LL * v18;
              v21 = (char *)v6 + v20 + 8;
              AlgoListToString<enum _DOT11_AUTH_ALGORITHM>(v81, (char *)v6 + v20 + 392, *((unsigned int *)v21 + 95));
              AlgoListToString<enum _DOT11_CIPHER_ALGORITHM>(v79, (char *)v6 + v20 + 416, *((unsigned int *)v21 + 101));
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
                || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
              {
                goto LABEL_54;
              }
              v22 = v79;
              v23 = v81;
              if ( v80.m128i_i64[1] > 7uLL )
                v22 = (void **)v79[0];
              v75 = (__int64)v22;
              if ( v82 > 7 )
                v23 = (void **)v81[0];
              *(_QWORD *)&SystemTime.wYear = v23;
              *(_DWORD *)v67 = *((_DWORD *)v21 + 94);
              *(_DWORD *)v68 = *((_DWORD *)v21 + 90);
              *(_DWORD *)v69 = *((_DWORD *)v21 + 89);
              *(_DWORD *)v70 = *((_DWORD *)v21 + 14);
              *(_DWORD *)v71 = *((_DWORD *)v21 + 9);
              LODWORD(v65) = *((_DWORD *)v21 + 12);
              *(_DWORD *)v66 = *((_DWORD *)v21 + 11);
              if ( v21 )
              {
                if ( *(_DWORD *)v21 <= 0x20u && (unsigned int)(*(_DWORD *)v21 + 1) <= 0x21 )
                {
                  S1[0] = 0;
                  if ( v21 != (char *)-4LL )
                    break;
                }
              }
LABEL_53:
              WPP_SF_ddSdddddLLSS(
                (TRACEHANDLE)v17[27],
                *((_DWORD *)v21 + 107),
                (__int64)S1,
                v66[0],
                (char)v65,
                v71[0],
                v70[0],
                v69[0],
                v68[0],
                v67[0],
                *(__int64 *)&SystemTime.wYear,
                v75);
              v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_54:
              if ( v80.m128i_i64[1] > 7uLL )
              {
                v29 = v79[0];
                v30 = (const struct std::nothrow_t *)(2 * v80.m128i_i64[1] + 2);
                *(_QWORD *)v66 = v30;
                v65 = v79[0];
                if ( (unsigned __int64)v30 >= 0x1000 )
                {
                  std::_Adjust_manually_vector_aligned(&v65, (unsigned __int64 *)v66);
                  v30 = *(const struct std::nothrow_t **)v66;
                  v29 = v65;
                }
                operator delete(v29, v30);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              LOWORD(v79[0]) = 0;
              v80 = si128;
              if ( v82 > 7 )
              {
                v31 = v81[0];
                v32 = (const struct std::nothrow_t *)(2 * v82 + 2);
                *(_QWORD *)v66 = v32;
                v65 = v81[0];
                if ( (unsigned __int64)v32 >= 0x1000 )
                {
                  std::_Adjust_manually_vector_aligned(&v65, (unsigned __int64 *)v66);
                  v32 = *(const struct std::nothrow_t **)v66;
                  v31 = v65;
                }
                operator delete(v31, v32);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( ++v18 >= *(_DWORD *)v6 )
              {
                v8 = *(char **)v76;
                v7 = (struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *)Src;
                v10 = v77;
                goto LABEL_64;
              }
            }
            lpWideCharStr = 0;
            v25 = GetProcessHeap();
            if ( v25 )
            {
              lpWideCharStr = (WCHAR *)HeapAlloc(v25, 8u, 0x42u);
              if ( lpWideCharStr )
              {
                *lpWideCharStr = 0;
                v26 = MultiByteToWideChar(0xFDE9u, 8u, v21 + 4, *(_DWORD *)v21, lpWideCharStr, 32);
                if ( v26 <= 0 )
                {
                  GetLastError();
                }
                else
                {
                  v27 = v26;
                  if ( !o_wmemcpy_s_0(S1, 0x21u, lpWideCharStr, v26) )
                  {
                    S1[v27] = 0;
                    goto LABEL_50;
                  }
                }
                v56 = MultiByteToWideChar(0, 8u, v21 + 4, *(_DWORD *)v21, lpWideCharStr, 32);
                if ( v56 > 0 )
                {
                  v60 = v56;
                  if ( !o_wmemcpy_s_0(S1, 0x21u, lpWideCharStr, v56) )
                  {
                    S1[v60] = 0;
                    goto LABEL_50;
                  }
                }
                else
                {
                  GetLastError();
                }
              }
              else
              {
                SetLastError(8u);
              }
            }
            v57 = *(_DWORD *)v21;
            v58 = 0;
            if ( *(_DWORD *)v21 <= 0x20u )
            {
              if ( !v57 )
                goto LABEL_49;
            }
            else
            {
              v57 = 32;
            }
            do
            {
              mbtowc(&S1[v58], &v21[v58 + 4], 1u);
              v58 = (unsigned int)(v58 + 1);
            }
            while ( (unsigned int)v58 < v57 );
LABEL_49:
            S1[v57] = 0;
            if ( !lpWideCharStr )
            {
LABEL_52:
              v6 = v73;
              v17 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_53;
            }
LABEL_50:
            v28 = GetProcessHeap();
            if ( v28 )
              HeapFree(v28, 0, lpWideCharStr);
            goto LABEL_52;
          }
        }
        v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
        v33 = v63;
        goto LABEL_65;
      }
      memcpy_0(v12, v6, v11);
    }
    v14 = (void *)*((_QWORD *)v10 + 98);
    v15 = 0;
    v63 = 0;
    if ( v14 )
    {
      v16 = GetProcessHeap();
      if ( v16 )
        HeapFree(v16, 0, v14);
      v15 = 0;
    }
    *((_QWORD *)v10 + 98) = v12;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  v33 = 1168;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 95, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a5);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_65:
  if ( !v7 )
  {
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) >= 3u && (*((_BYTE *)v17 + 228) & 4) != 0 )
    {
      WPP_SF_d(v17[27], 99, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a5);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_104;
  }
  v34 = 688 * *(_DWORD *)v7 + 8;
  if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 57) & 0x200) != 0 )
    WPP_SF_(v17[27], 19, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
  v35 = GetProcessHeap();
  if ( !v35 )
    goto LABEL_159;
  v37 = HeapAlloc(v35, 8u, v34);
  v38 = v37;
  if ( !v37 )
  {
    SetLastError(8u);
LABEL_159:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 225) && *((char *)WPP_GLOBAL_Control + 228) < 0 )
      {
        GetLastError();
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_79512908d13336da9f44adf151438c1a_Traceguids, v34);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) && *((char *)v17 + 228) < 0 )
      {
        WPP_SF_d(v17[27], 20, &WPP_79512908d13336da9f44adf151438c1a_Traceguids, v34);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    v40 = 8;
    v64 = 8;
    goto LABEL_75;
  }
  memcpy_0(v37, v7, v34);
  v39 = (void *)*((_QWORD *)v10 + 99);
  v40 = 0;
  v64 = 0;
  if ( v39 )
  {
    v41 = GetProcessHeap();
    if ( v41 )
      HeapFree(v41, 0, v39);
  }
  *((_QWORD *)v10 + 99) = v38;
  v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_75:
  if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 57) & 0x200) != 0 )
  {
    WPP_SF_(v17[27], 21, &WPP_79512908d13336da9f44adf151438c1a_Traceguids);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 )
  {
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) && (*((_BYTE *)v17 + 228) & 4) != 0 )
    {
      cchWideChar = v40;
      WPP_SF_lll(v17[27], 98, &WPP_fec73b95d5a537674450248f38664378_Traceguids, v34);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) >= 3u && (*((_BYTE *)v17 + 228) & 4) != 0 )
    {
      WPP_SF_d(v17[27], 96, &WPP_fec73b95d5a537674450248f38664378_Traceguids, *(unsigned int *)v7);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    v42 = 0;
    if ( *(_DWORD *)v7 )
    {
      while ( 1 )
      {
        if ( v17 == &WPP_GLOBAL_Control || *((_BYTE *)v17 + 225) < 3u || (*((_BYTE *)v17 + 228) & 4) == 0 )
          goto LABEL_102;
        v43 = 688LL * v42;
        v44 = *(_DWORD *)((char *)v7 + v43 + 636);
        v45 = (char *)v7 + v43 + 520;
        if ( v45 )
        {
          if ( *(_DWORD *)v45 <= 0x20u && (unsigned int)(*(_DWORD *)v45 + 1) <= 0x21 )
          {
            v46 = v45 + 4;
            S1[0] = 0;
            if ( v45 != (char *)-4LL )
              break;
          }
        }
LABEL_101:
        WPP_SF_dSD((unsigned int)v17[27], v43, v36, v42 + 1, (__int64)S1, v44);
        v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_102:
        if ( ++v42 >= *(_DWORD *)v7 )
          goto LABEL_103;
      }
      v47 = 0;
      v48 = GetProcessHeap();
      if ( v48 )
      {
        v47 = (WCHAR *)HeapAlloc(v48, 8u, 0x42u);
        if ( v47 )
        {
          *v47 = 0;
          v49 = MultiByteToWideChar(0xFDE9u, 8u, v45 + 4, *(_DWORD *)v45, v47, 32);
          if ( v49 <= 0 )
          {
            GetLastError();
          }
          else
          {
            v50 = v49;
            if ( !o_wmemcpy_s_0(S1, 0x21u, v47, v49) )
            {
              S1[v50] = 0;
              goto LABEL_98;
            }
          }
          v53 = MultiByteToWideChar(0, 8u, v45 + 4, *(_DWORD *)v45, v47, 32);
          if ( v53 > 0 )
          {
            v59 = v53;
            if ( !o_wmemcpy_s_0(S1, 0x21u, v47, v53) )
            {
              S1[v59] = 0;
              goto LABEL_98;
            }
          }
          else
          {
            GetLastError();
          }
        }
        else
        {
          SetLastError(8u);
        }
      }
      v54 = *(_DWORD *)v45;
      v55 = 0;
      if ( v54 <= 0x20 )
      {
        if ( !v54 )
          goto LABEL_97;
      }
      else
      {
        v54 = 32;
      }
      do
      {
        mbtowc(&S1[v55], &v46[v55], 1u);
        v55 = (unsigned int)(v55 + 1);
      }
      while ( (unsigned int)v55 < v54 );
LABEL_97:
      S1[v54] = 0;
      if ( !v47 )
      {
LABEL_100:
        v7 = (struct _WLAN_AVAILABLE_NETWORK_LIST_V3 *)Src;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_101;
      }
LABEL_98:
      v51 = GetProcessHeap();
      if ( v51 )
        HeapFree(v51, 0, v47);
      goto LABEL_100;
    }
  }
LABEL_103:
  v33 = v64;
LABEL_104:
  if ( (v8[96] & 4) == 0 && v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 225) && (*((_BYTE *)v17 + 228) & 0x40) != 0 )
  {
    v61 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)v8,
      cchWideChar,
      *((_QWORD *)v8 + 16),
      *((_DWORD *)v8 + 30),
      v61,
      (__int64)"WDiagProcessAcmScanResult",
      57);
  }
  *((_DWORD *)v8 + 24) &= ~4u;
  *((_DWORD *)v8 + 30) = 1593;
  *((_QWORD *)v8 + 16) = "WDiagProcessAcmScanResult";
  *((_DWORD *)v8 + 26) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 100, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return v33;
}

```

## disassembly

```asm
0x18000f7d0  mov     r11, rsp
0x18000f7d3  push    rbp
0x18000f7d4  push    rbx
0x18000f7d5  lea     rbp, [r11-0D8h]
0x18000f7dc  sub     rsp, 1C8h
0x18000f7e3  mov     rax, cs:__security_cookie
0x18000f7ea  xor     rax, rsp
0x18000f7ed  mov     [rbp+0D0h+var_50], rax
0x18000f7f4  mov     [r11+10h], rsi
0x18000f7f8  mov     [r11-18h], rdi
0x18000f7fc  mov     rdi, rcx
0x18000f7ff  mov     [r11-20h], r12
0x18000f803  mov     [r11-28h], r13
0x18000f807  mov     [r11-30h], r14
0x18000f80b  mov     r14, r8
0x18000f80e  mov     [r11-38h], r15
0x18000f812  mov     r15, r9
0x18000f815  mov     [rbp+0D0h+Src], r9
0x18000f819  mov     [rbp+0D0h+var_118], r8
0x18000f81d  mov     [rbp+0D0h+var_110], rcx
0x18000f821  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f828  lea     rsi, WPP_GLOBAL_Control
0x18000f82f  cmp     rcx, rsi
0x18000f832  jz      short loc_18000F858
0x18000f834  test    dword ptr [rcx+0E4h], 200h
0x18000f83e  jz      short loc_18000F858
0x18000f840  mov     rcx, [rcx+0D8h]
0x18000f847  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18000f84e  mov     edx, 5Bh ; '['
0x18000f853  call    WPP_SF_
0x18000f858  lea     r13, [rdi+0D18h]
0x18000f85f  mov     qword ptr [rbp+0D0h+var_100], r13
0x18000f863  call    cs:__imp_GetCurrentThreadId
0x18000f869  lea     rcx, [r13+8]; lpCriticalSection
0x18000f86d  mov     ebx, eax
0x18000f86f  call    cs:__imp_EnterCriticalSection
0x18000f875  mov     rcx, [r13+58h]; hHandle
0x18000f879  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f87e  call    cs:__imp_WaitForSingleObject
0x18000f884  test    byte ptr [r13+60h], 4
0x18000f889  lea     r12, aWdiagprocessac_0; "WDiagProcessAcmScanResult"
0x18000f890  jnz     loc_18001030B
0x18000f896  or      dword ptr [r13+60h], 4
0x18000f89b  mov     eax, 0CCCCCCCDh
0x18000f8a0  mov     [r13+70h], r12
0x18000f8a4  mov     [r13+68h], ebx
0x18000f8a8  mov     dword ptr [r13+6Ch], 5D1h
0x18000f8b0  mov     ecx, [rdi+0A8h]
0x18000f8b6  dec     ecx
0x18000f8b8  mul     ecx
0x18000f8ba  shr     edx, 2
0x18000f8bd  lea     eax, [rdx+rdx*4]
0x18000f8c0  sub     ecx, eax
0x18000f8c2  mov     eax, ecx
0x18000f8c4  imul    r12, rax, 270h
0x18000f8cb  add     r12, rdi
0x18000f8ce  mov     [rbp+0D0h+var_F8], r12
0x18000f8d2  test    r14, r14
0x18000f8d5  jz      loc_18001009C
0x18000f8db  imul    esi, [r14], 1F8h
0x18000f8e2  add     esi, 8
0x18000f8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8ec  lea     rax, WPP_GLOBAL_Control
0x18000f8f3  cmp     rcx, rax
0x18000f8f6  jz      short loc_18000F91C
0x18000f8f8  test    dword ptr [rcx+0E4h], 200h
0x18000f902  jz      short loc_18000F91C
0x18000f904  mov     rcx, [rcx+0D8h]
0x18000f90b  lea     r8, WPP_79512908d13336da9f44adf151438c1a_Traceguids
0x18000f912  mov     edx, 13h
0x18000f917  call    WPP_SF_
0x18000f91c  xor     ebx, ebx
0x18000f91e  test    esi, esi
0x18000f920  jz      short loc_18000F963
0x18000f922  mov     edi, esi
0x18000f924  call    cs:__imp_GetProcessHeap
0x18000f92a  test    rax, rax
0x18000f92d  jz      short loc_18000F94C
0x18000f92f  mov     r8d, edi; dwBytes
0x18000f932  mov     edx, 8; dwFlags
0x18000f937  mov     rcx, rax; hHeap
0x18000f93a  call    cs:__imp_HeapAlloc
0x18000f940  mov     rbx, rax
0x18000f943  test    rax, rax
0x18000f946  jz      loc_180010378
0x18000f94c  test    rbx, rbx
0x18000f94f  jz      loc_180010388
0x18000f955  mov     r8, rdi; Size
0x18000f958  mov     rdx, r14; Src
0x18000f95b  mov     rcx, rbx; void *
0x18000f95e  call    memcpy_0
0x18000f963  mov     rdi, [r12+310h]
0x18000f96b  xor     ecx, ecx
0x18000f96d  mov     [rbp+0D0h+var_150], ecx
0x18000f970  test    rdi, rdi
0x18000f973  jz      short loc_18000F991
0x18000f975  call    cs:__imp_GetProcessHeap
0x18000f97b  test    rax, rax
0x18000f97e  jz      short loc_18000F98E
0x18000f980  mov     r8, rdi; lpMem
0x18000f983  xor     edx, edx; dwFlags
0x18000f985  mov     rcx, rax; hHeap
0x18000f988  call    cs:__imp_HeapFree
0x18000f98e  mov     ecx, [rbp+0D0h+var_150]
0x18000f991  mov     [r12+310h], rbx
0x18000f999  lea     rbx, WPP_GLOBAL_Control
0x18000f9a0  mov     rax, cs:WPP_GLOBAL_Control
0x18000f9a7  cmp     rax, rbx
0x18000f9aa  jz      short loc_18000F9DA
0x18000f9ac  test    dword ptr [rax+0E4h], 200h
0x18000f9b6  jz      short loc_18000F9DA
0x18000f9b8  mov     rcx, [rax+0D8h]
0x18000f9bf  lea     r8, WPP_79512908d13336da9f44adf151438c1a_Traceguids
0x18000f9c6  mov     edx, 15h
0x18000f9cb  call    WPP_SF_
0x18000f9d0  mov     rax, cs:WPP_GLOBAL_Control
0x18000f9d7  mov     ecx, [rbp+0D0h+var_150]
0x18000f9da  test    ecx, ecx
0x18000f9dc  jnz     loc_18001023A
0x18000f9e2  cmp     rax, rbx
0x18000f9e5  jz      short loc_18000FA14
0x18000f9e7  cmp     byte ptr [rax+0E1h], 3
0x18000f9ee  jb      short loc_18000FA14
0x18000f9f0  test    byte ptr [rax+0E4h], 4
0x18000f9f7  jz      short loc_18000FA14
0x18000f9f9  mov     r9d, [r14]
0x18000f9fc  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18000fa03  mov     rcx, [rax+0D8h]
0x18000fa0a  mov     edx, 5Ch ; '\'
0x18000fa0f  call    WPP_SF_d
0x18000fa14  xorps   xmm0, xmm0
0x18000fa17  lea     rcx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18000fa1b  movups  xmmword ptr [rbp+0D0h+SystemTime.wYear], xmm0
0x18000fa1f  call    cs:__imp_GetSystemTime
0x18000fa25  mov     rdx, [rbp+0D0h+var_110]
0x18000fa29  lea     rcx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18000fa2d  add     rdx, 90h; lpFileTime
0x18000fa34  call    cs:__imp_SystemTimeToFileTime
0x18000fa3a  test    eax, eax
0x18000fa3c  jz      loc_180010432
0x18000fa42  xor     esi, esi
0x18000fa44  cmp     [r14], esi
0x18000fa47  jbe     loc_180010283
0x18000fa4d  movaps  [rsp+1D0h+var_48+8], xmm6
0x18000fa55  lea     r13, WPP_GLOBAL_Control
0x18000fa5c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000fa64  nop     dword ptr [rax+00h]
0x18000fa68  nop     dword ptr [rax+rax+00000000h]
0x18000fa70  mov     eax, esi
0x18000fa72  lea     rdi, [r14+8]
0x18000fa76  imul    rbx, rax, 1F8h
0x18000fa7d  lea     rcx, [rbp+0D0h+var_C0]
0x18000fa81  add     rdi, rbx
0x18000fa84  lea     rdx, [rbx+188h]
0x18000fa8b  mov     r8d, [rdi+17Ch]
0x18000fa92  add     rdx, r14
0x18000fa95  call    ??$AlgoListToString@W4_DOT11_AUTH_ALGORITHM@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBW4_DOT11_AUTH_ALGORITHM@@K@Z; AlgoListToString<_DOT11_AUTH_ALGORITHM>(_DOT11_AUTH_ALGORITHM const *,ulong)
0x18000fa9a  mov     r8d, [rdi+194h]
0x18000faa1  lea     rdx, [r14+1A0h]
0x18000faa8  add     rdx, rbx
0x18000faab  lea     rcx, [rbp+0D0h+var_E0]
0x18000faaf  call    ??$AlgoListToString@W4_DOT11_CIPHER_ALGORITHM@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBW4_DOT11_CIPHER_ALGORITHM@@K@Z; AlgoListToString<_DOT11_CIPHER_ALGORITHM>(_DOT11_CIPHER_ALGORITHM const *,ulong)
0x18000fab4  mov     rax, cs:WPP_GLOBAL_Control
0x18000fabb  cmp     rax, r13
0x18000fabe  jz      loc_18000FC98
0x18000fac4  cmp     byte ptr [rax+0E1h], 3
0x18000facb  jb      loc_18000FC98
0x18000fad1  test    byte ptr [rax+0E4h], 4
0x18000fad8  jz      loc_18000FC98
0x18000fade  cmp     [rbp+0D0h+var_C8], 7
0x18000fae3  lea     r9, [rbp+0D0h+var_E0]
0x18000fae7  lea     rcx, [rbp+0D0h+var_C0]
0x18000faeb  cmova   r9, [rbp+0D0h+var_E0]
0x18000faf0  cmp     [rbp+0D0h+var_A8], 7
0x18000faf5  mov     [rbp+0D0h+var_108], r9
0x18000faf9  cmova   rcx, [rbp+0D0h+var_C0]
0x18000fafe  mov     qword ptr [rbp+0D0h+SystemTime.wYear], rcx
0x18000fb02  mov     ecx, [rdi+178h]
0x18000fb08  mov     dword ptr [rbp+0D0h+var_138], ecx
0x18000fb0b  mov     ecx, [rdi+168h]
0x18000fb11  mov     dword ptr [rbp+0D0h+var_134], ecx
0x18000fb14  mov     ecx, [rdi+164h]
0x18000fb1a  mov     dword ptr [rbp+0D0h+var_130], ecx
0x18000fb1d  mov     ecx, [rdi+38h]
0x18000fb20  mov     dword ptr [rbp+0D0h+var_12C], ecx
0x18000fb23  mov     ecx, [rdi+24h]
0x18000fb26  mov     dword ptr [rbp+0D0h+var_128], ecx
0x18000fb29  mov     ecx, [rdi+30h]
0x18000fb2c  mov     dword ptr [rbp+0D0h+var_148], ecx
0x18000fb2f  mov     ecx, [rdi+2Ch]
0x18000fb32  mov     dword ptr [rbp+0D0h+var_140], ecx
0x18000fb35  test    rdi, rdi
0x18000fb38  jz      loc_18000FC2B
0x18000fb3e  mov     ecx, [rdi]
0x18000fb40  cmp     ecx, 20h ; ' '
0x18000fb43  ja      loc_18000FC2B
0x18000fb49  inc     ecx
0x18000fb4b  cmp     ecx, 21h ; '!'
0x18000fb4e  ja      loc_18000FC2B
0x18000fb54  xor     ecx, ecx
0x18000fb56  lea     r15, [rdi+4]
0x18000fb5a  mov     [rbp+0D0h+S1], cx
0x18000fb5e  test    r15, r15
0x18000fb61  jz      loc_18000FC2B
0x18000fb67  xor     ebx, ebx
0x18000fb69  call    cs:__imp_GetProcessHeap
0x18000fb6f  test    rax, rax
0x18000fb72  jz      loc_180010196
0x18000fb78  mov     edx, 8; dwFlags
0x18000fb7d  mov     r8d, 42h ; 'B'; dwBytes
0x18000fb83  mov     rcx, rax; hHeap
0x18000fb86  call    cs:__imp_HeapAlloc
0x18000fb8c  mov     rbx, rax
0x18000fb8f  test    rax, rax
0x18000fb92  jz      loc_18001043D
0x18000fb98  xor     eax, eax
0x18000fb9a  mov     [rsp+1D0h+cchWideChar], 20h ; ' '; cchWideChar
0x18000fba2  mov     [rbx], ax
0x18000fba5  mov     r8, r15; lpMultiByteStr
0x18000fba8  mov     r9d, [rdi]; cbMultiByte
0x18000fbab  mov     edx, 8; dwFlags
0x18000fbb0  mov     ecx, 0FDE9h; CodePage
0x18000fbb5  mov     [rsp+1D0h+lpWideCharStr], rbx; lpWideCharStr
0x18000fbba  call    cs:__imp_MultiByteToWideChar
0x18000fbc0  test    eax, eax
0x18000fbc2  jle     loc_180010162
0x18000fbc8  movsxd  r14, eax
0x18000fbcb  lea     rcx, [rbp+0D0h+S1]; S1
0x18000fbcf  mov     r9, r14; N
0x18000fbd2  mov     r8, rbx; S2
0x18000fbd5  mov     edx, 21h ; '!'; N1
0x18000fbda  call    _o_wmemcpy_s_0
0x18000fbdf  test    eax, eax
0x18000fbe1  jnz     loc_180010168
0x18000fbe7  mov     [rbp+r14*2+0D0h+S1], ax
0x18000fbed  jmp     short loc_18000FC07
0x18000fbef  test    r14d, r14d
0x18000fbf2  jnz     loc_1800101AC
0x18000fbf8  xor     eax, eax
0x18000fbfa  mov     ecx, r14d
0x18000fbfd  mov     [rbp+rcx*2+0D0h+S1], ax
0x18000fc02  test    rbx, rbx
0x18000fc05  jz      short loc_18000FC20
0x18000fc07  call    cs:__imp_GetProcessHeap
0x18000fc0d  test    rax, rax
0x18000fc10  jz      short loc_18000FC20
0x18000fc12  mov     r8, rbx; lpMem
0x18000fc15  xor     edx, edx; dwFlags
0x18000fc17  mov     rcx, rax; hHeap
0x18000fc1a  call    cs:__imp_HeapFree
0x18000fc20  mov     r14, [rbp+0D0h+var_118]
0x18000fc24  mov     rax, cs:WPP_GLOBAL_Control
0x18000fc2b  mov     rcx, [rbp+0D0h+var_108]
0x18000fc2f  lea     r9d, [rsi+1]
0x18000fc33  mov     [rsp+70h], rcx; __int64
0x18000fc38  mov     rcx, qword ptr [rbp+0D0h+SystemTime.wYear]
0x18000fc3c  mov     [rsp+1D0h+var_168], rcx; __int64
0x18000fc41  mov     ecx, dword ptr [rbp+0D0h+var_138]
0x18000fc44  mov     dword ptr [rsp+1D0h+var_170], ecx; char
0x18000fc48  mov     ecx, dword ptr [rbp+0D0h+var_134]
0x18000fc4b  mov     dword ptr [rsp+1D0h+var_178], ecx; char
0x18000fc4f  mov     ecx, dword ptr [rbp+0D0h+var_130]
0x18000fc52  mov     dword ptr [rsp+1D0h+var_180], ecx; char
0x18000fc56  mov     ecx, dword ptr [rbp+0D0h+var_12C]
0x18000fc59  mov     dword ptr [rsp+1D0h+var_188], ecx; char
0x18000fc5d  mov     ecx, dword ptr [rbp+0D0h+var_128]
0x18000fc60  mov     dword ptr [rsp+1D0h+var_190], ecx; char
0x18000fc64  mov     ecx, dword ptr [rbp+0D0h+var_148]
0x18000fc67  mov     dword ptr [rsp+1D0h+var_198], ecx; char
0x18000fc6b  mov     ecx, dword ptr [rbp+0D0h+var_140]
0x18000fc6e  mov     dword ptr [rsp+1D0h+var_1A0], ecx; char
0x18000fc72  lea     rcx, [rbp+0D0h+S1]
0x18000fc76  mov     qword ptr [rsp+1D0h+cchWideChar], rcx; __int64
0x18000fc7b  mov     ecx, [rdi+1ACh]
0x18000fc81  mov     dword ptr [rsp+1D0h+lpWideCharStr], ecx; char
0x18000fc85  mov     rcx, [rax+0D8h]; LoggerHandle
0x18000fc8c  call    WPP_SF_ddSdddddLLSS
0x18000fc91  mov     rax, cs:WPP_GLOBAL_Control
0x18000fc98  mov     rdx, [rbp+0D0h+var_C8]
0x18000fc9c  cmp     rdx, 7
0x18000fca0  jbe     short loc_18000FCCF
0x18000fca2  mov     rcx, [rbp+0D0h+var_E0]; void *
0x18000fca6  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18000fcae  mov     qword ptr [rbp+0D0h+var_140], rdx
0x18000fcb2  mov     [rbp+0D0h+var_148], rcx
0x18000fcb6  cmp     rdx, 1000h
0x18000fcbd  jnb     loc_18001044D
0x18000fcc3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fcc8  mov     rax, cs:WPP_GLOBAL_Control
0x18000fccf  mov     rdx, [rbp+0D0h+var_A8]
0x18000fcd3  xor     ecx, ecx
0x18000fcd5  mov     word ptr [rbp+0D0h+var_E0], cx
0x18000fcd9  movdqu  xmmword ptr [rbp+0], xmm6
0x18000fcde  cmp     rdx, 7
0x18000fce2  jbe     short loc_18000FD11
0x18000fce4  mov     rcx, [rbp+0D0h+var_C0]; void *
0x18000fce8  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18000fcf0  mov     qword ptr [rbp+0D0h+var_140], rdx
0x18000fcf4  mov     [rbp+0D0h+var_148], rcx
0x18000fcf8  cmp     rdx, 1000h
  ... truncated ...
```
