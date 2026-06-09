# FFileTimeToStr

- ea: `0x180002a00`
- end: `0x180003140`
- name: `FFileTimeToStr`
- size: `1856`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005830`

## callees

- `0x180002a00`
- `0x18000a044`
- `0x18000a224`
- `0x18000a284`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002e45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002e45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003119`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003119`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003128`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002b49`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002b49`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180002a6e`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180002a6e`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180002d3a`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180002fe5`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180002d3a`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x180002fe5`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002be4`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002ed5`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002be4`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatW` at `0x180002ed5`

## pseudocode

```c
__int64 __fastcall FFileTimeToStr(FILETIME a1, _QWORD *a2, unsigned int *a3)
{
  __int64 v5; // rbx
  DWORD LastError; // eax
  __int64 v7; // r8
  DWORD v8; // eax
  __int64 dwHighDateTime; // r9
  const wchar_t *v10; // rdx
  __int64 dwLowDateTime; // r8
  __int64 v13; // rbx
  DWORD v14; // eax
  __int64 v15; // r8
  int DateFormatW; // eax
  __int64 v17; // rdi
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // r14d
  int wDay; // r15d
  int wDayOfWeek; // r12d
  int wMonth; // r13d
  DWORD v25; // eax
  __int64 v26; // r8
  int v27; // ebx
  int v28; // edi
  int v29; // esi
  int v30; // r14d
  int v31; // r15d
  unsigned int v32; // r13d
  int v33; // r12d
  DWORD v34; // eax
  __int64 v35; // r8
  const wchar_t *v36; // rdx
  int TimeFormatW; // eax
  int v38; // esi
  int v39; // ebx
  int v40; // edi
  int v41; // esi
  int v42; // r14d
  int v43; // r15d
  int v44; // r12d
  int v45; // r13d
  DWORD v46; // eax
  __int64 v47; // r8
  unsigned int v48; // ebx
  HANDLE ProcessHeap; // rax
  void *v50; // rax
  _WORD *v51; // rbx
  __int64 v52; // rbx
  DWORD v53; // eax
  __int64 v54; // r8
  DWORD v55; // eax
  int v56; // ebx
  int v57; // edi
  int v58; // esi
  int v59; // r14d
  int v60; // r15d
  int v61; // r12d
  int v62; // r13d
  DWORD v63; // eax
  __int64 v64; // r8
  int v65; // ebx
  int v66; // edi
  int v67; // esi
  int v68; // r14d
  int v69; // r15d
  unsigned int v70; // r13d
  int v71; // r12d
  DWORD v72; // eax
  __int64 v73; // r8
  const wchar_t *v74; // rdx
  int v75; // ebx
  int v76; // edi
  int v77; // esi
  int v78; // r14d
  int v79; // r15d
  int v80; // r12d
  int v81; // r13d
  DWORD v82; // eax
  __int64 v83; // r8
  HANDLE v84; // rax
  LPWSTR lpDateStr; // [rsp+20h] [rbp-E0h]
  LPWSTR lpDateStra; // [rsp+20h] [rbp-E0h]
  LPWSTR lpDateStrb; // [rsp+20h] [rbp-E0h]
  __int64 cchDate; // [rsp+28h] [rbp-D8h]
  __int64 cchDatea; // [rsp+28h] [rbp-D8h]
  __int64 v90; // [rsp+30h] [rbp-D0h]
  __int64 v91; // [rsp+38h] [rbp-C8h]
  __int64 v92; // [rsp+40h] [rbp-C0h]
  __int64 v93; // [rsp+48h] [rbp-B8h]
  __int64 v94; // [rsp+50h] [rbp-B0h]
  unsigned int wYear; // [rsp+60h] [rbp-A0h]
  unsigned int v96; // [rsp+60h] [rbp-A0h]
  unsigned int v97; // [rsp+60h] [rbp-A0h]
  unsigned int v98; // [rsp+60h] [rbp-A0h]
  unsigned int v99; // [rsp+60h] [rbp-A0h]
  unsigned int v100; // [rsp+60h] [rbp-A0h]
  unsigned int v101; // [rsp+60h] [rbp-A0h]
  unsigned int v102; // [rsp+60h] [rbp-A0h]
  __int64 v103; // [rsp+68h] [rbp-98h]
  __int64 v104; // [rsp+68h] [rbp-98h]
  __int64 v105; // [rsp+68h] [rbp-98h]
  __int64 v106; // [rsp+68h] [rbp-98h]
  struct _FILETIME LocalFileTime; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-80h]
  _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  int v111; // [rsp+A0h] [rbp-60h] BYREF
  char v112[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  FileTime = a1;
  LocalFileTime = 0;
  v111 = 0;
  SystemTime = 0;
  memset_0(v112, 0, sizeof(v112));
  if ( !FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_ddd(v5, 175, v7, FileTime.dwLowDateTime, FileTime.dwHighDateTime, LastError);
      }
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      return 0;
    LOWORD(v111) = 0;
    v8 = GetLastError();
    dwHighDateTime = FileTime.dwHighDateTime;
    v10 = L"FileTimeToLocalFileTime(%d %d) failed and returned %d";
    dwLowDateTime = FileTime.dwLowDateTime;
    goto LABEL_8;
  }
  if ( !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v14 = GetLastError();
      WPP_SF_ddd(v13, 176, v15, LocalFileTime.dwLowDateTime, LocalFileTime.dwHighDateTime, v14);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      return 0;
    LOWORD(v111) = 0;
    v8 = GetLastError();
    dwHighDateTime = LocalFileTime.dwHighDateTime;
    v10 = L"FileTimeToSystemTime(%d %d) failed and returned %d";
    dwLowDateTime = LocalFileTime.dwLowDateTime;
LABEL_8:
    LODWORD(lpDateStr) = v8;
    FormatRRASErrorString((wchar_t *)&v111, v10, dwLowDateTime, dwHighDateTime, lpDateStr);
LABEL_9:
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v111);
    return 0;
  }
  DateFormatW = GetDateFormatW(0x400u, 0, &SystemTime, 0, 0, 0);
  v17 = DateFormatW;
  if ( !DateFormatW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wDay = SystemTime.wDay;
      wDayOfWeek = SystemTime.wDayOfWeek;
      wMonth = SystemTime.wMonth;
      wYear = SystemTime.wYear;
      v103 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      WPP_SF_ddddddddd(v103, 177, v26, wYear, wMonth, wDayOfWeek, wDay, wHour, wMinute, wSecond, wMilliseconds, v25);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      return 0;
    v27 = SystemTime.wMilliseconds;
    v28 = SystemTime.wSecond;
    v29 = SystemTime.wMinute;
    v30 = SystemTime.wHour;
    v31 = SystemTime.wDay;
    v32 = SystemTime.wMonth;
    LOWORD(v111) = 0;
    v33 = SystemTime.wDayOfWeek;
    v96 = SystemTime.wYear;
    v34 = GetLastError();
    v35 = v96;
    v36 = L"GetDateFormat(%d %d %d %d %d %d %d %d) failed and returned %d";
    goto LABEL_25;
  }
  TimeFormatW = GetTimeFormatW(0x400u, 0, &SystemTime, 0, 0, 0);
  v38 = TimeFormatW;
  if ( !TimeFormatW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v39 = SystemTime.wMilliseconds;
      v40 = SystemTime.wSecond;
      v41 = SystemTime.wMinute;
      v42 = SystemTime.wHour;
      v43 = SystemTime.wDay;
      v44 = SystemTime.wDayOfWeek;
      v45 = SystemTime.wMonth;
      v97 = SystemTime.wYear;
      v104 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v46 = GetLastError();
      WPP_SF_ddddddddd(v104, 178, v47, v97, v45, v44, v43, v42, v41, v40, v39, v46);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      return 0;
    v27 = SystemTime.wMilliseconds;
    v28 = SystemTime.wSecond;
    v29 = SystemTime.wMinute;
    v30 = SystemTime.wHour;
    v31 = SystemTime.wDay;
    v32 = SystemTime.wMonth;
    LOWORD(v111) = 0;
    v33 = SystemTime.wDayOfWeek;
    v98 = SystemTime.wYear;
    v34 = GetLastError();
    v35 = v98;
    v36 = L"GetTimeFormat(%d %d %d %d %d %d %d %d) failed and returned %d";
LABEL_25:
    LODWORD(v94) = v34;
    LODWORD(v93) = v27;
    LODWORD(v92) = v28;
    LODWORD(v91) = v29;
    LODWORD(v90) = v30;
    LODWORD(cchDate) = v31;
    LODWORD(lpDateStra) = v33;
    FormatRRASErrorString((wchar_t *)&v111, v36, v35, v32, lpDateStra, cchDate, v90, v91, v92, v93, v94);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v111);
    return 0;
  }
  v48 = 2 * (v17 + TimeFormatW);
  *a3 = v48;
  ProcessHeap = GetProcessHeap();
  v50 = HeapAlloc(ProcessHeap, 8u, v48);
  lpMem = v50;
  v51 = v50;
  if ( !v50 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v52 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v53 = GetLastError();
      WPP_SF_d(v52, 0xB3u, v54, v53);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      return 0;
    LOWORD(v111) = 0;
    v55 = GetLastError();
    FormatRRASErrorString((wchar_t *)&v111, L"LocalAlloc failed and returned %d", v55);
    goto LABEL_9;
  }
  if ( !GetDateFormatW(0x400u, 0, &SystemTime, 0, (LPWSTR)v50, v17) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v56 = SystemTime.wMilliseconds;
      v57 = SystemTime.wSecond;
      v58 = SystemTime.wMinute;
      v59 = SystemTime.wHour;
      v60 = SystemTime.wDay;
      v61 = SystemTime.wDayOfWeek;
      v62 = SystemTime.wMonth;
      v99 = SystemTime.wYear;
      v105 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v63 = GetLastError();
      WPP_SF_ddddddddd(v105, 180, v64, v99, v62, v61, v60, v59, v58, v57, v56, v63);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_56;
    v65 = SystemTime.wMilliseconds;
    v66 = SystemTime.wSecond;
    v67 = SystemTime.wMinute;
    v68 = SystemTime.wHour;
    v69 = SystemTime.wDay;
    v70 = SystemTime.wMonth;
    LOWORD(v111) = 0;
    v71 = SystemTime.wDayOfWeek;
    v100 = SystemTime.wYear;
    v72 = GetLastError();
    v73 = v100;
    v74 = L"GetDateFormat(%d %d %d %d %d %d %d %d) failed and returned %d";
LABEL_55:
    LODWORD(v94) = v72;
    LODWORD(v93) = v65;
    LODWORD(v92) = v66;
    LODWORD(v91) = v67;
    LODWORD(v90) = v68;
    LODWORD(cchDatea) = v69;
    LODWORD(lpDateStrb) = v71;
    FormatRRASErrorString((wchar_t *)&v111, v74, v73, v70, lpDateStrb, cchDatea, v90, v91, v92, v93, v94);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v111);
LABEL_56:
    v84 = GetProcessHeap();
    HeapFree(v84, 0, lpMem);
    return 0;
  }
  v51[v17 - 1] = 32;
  if ( !GetTimeFormatW(0x400u, 0, &SystemTime, 0, &v51[v17], v38) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v75 = SystemTime.wMilliseconds;
      v76 = SystemTime.wSecond;
      v77 = SystemTime.wMinute;
      v78 = SystemTime.wHour;
      v79 = SystemTime.wDay;
      v80 = SystemTime.wDayOfWeek;
      v81 = SystemTime.wMonth;
      v101 = SystemTime.wYear;
      v106 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v82 = GetLastError();
      WPP_SF_ddddddddd(v106, 181, v83, v101, v81, v80, v79, v78, v77, v76, v75, v82);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_56;
    v65 = SystemTime.wMilliseconds;
    v66 = SystemTime.wSecond;
    v67 = SystemTime.wMinute;
    v68 = SystemTime.wHour;
    v69 = SystemTime.wDay;
    v70 = SystemTime.wMonth;
    LOWORD(v111) = 0;
    v71 = SystemTime.wDayOfWeek;
    v102 = SystemTime.wYear;
    v72 = GetLastError();
    v73 = v102;
    v74 = L"GetTimeFormat(%d %d %d %d %d %d %d %d) failed and returned %d";
    goto LABEL_55;
  }
  *a2 = v51;
  return 1;
}

```

## disassembly

```asm
0x180002a00  mov     [rsp-8+arg_18], rbx
0x180002a05  push    rbp
0x180002a06  push    rsi
0x180002a07  push    rdi
0x180002a08  push    r12
0x180002a0a  push    r13
0x180002a0c  push    r14
0x180002a0e  push    r15
0x180002a10  lea     rbp, [rsp-7B0h]
0x180002a18  sub     rsp, 8B0h
0x180002a1f  mov     rax, cs:__security_cookie
0x180002a26  xor     rax, rsp
0x180002a29  mov     [rbp+7E0h+var_40], rax
0x180002a30  xor     r12d, r12d
0x180002a33  mov     qword ptr [rsp+8E0h+FileTime.dwLowDateTime], rcx
0x180002a38  mov     r15, r8
0x180002a3b  mov     qword ptr [rsp+8E0h+LocalFileTime.dwLowDateTime], r12
0x180002a40  mov     r14, rdx
0x180002a43  mov     [rsp+8E0h+var_87C], r12d
0x180002a48  xorps   xmm0, xmm0
0x180002a4b  mov     [rbp+7E0h+var_840], r12d
0x180002a4f  xor     edx, edx; Val
0x180002a51  lea     rcx, [rbp+7E0h+var_83C]; void *
0x180002a55  mov     r8d, 7FCh; Size
0x180002a5b  movups  xmmword ptr [rbp+7E0h+SystemTime.wYear], xmm0
0x180002a5f  call    memset_0
0x180002a64  lea     rdx, [rsp+8E0h+LocalFileTime]; lpLocalFileTime
0x180002a69  lea     rcx, [rsp+8E0h+FileTime]; lpFileTime
0x180002a6e  call    cs:__imp_FileTimeToLocalFileTime
0x180002a74  test    eax, eax
0x180002a76  jnz     loc_180002B40
0x180002a7c  mov     rbx, cs:WPP_GLOBAL_Control
0x180002a83  lea     rax, WPP_GLOBAL_Control
0x180002a8a  cmp     rbx, rax
0x180002a8d  jz      short loc_180002AC3
0x180002a8f  test    byte ptr [rbx+1Ch], 40h
0x180002a93  jz      short loc_180002AC3
0x180002a95  cmp     byte ptr [rbx+19h], 1
0x180002a99  jb      short loc_180002AC3
0x180002a9b  mov     rbx, [rbx+10h]
0x180002a9f  call    cs:__imp_GetLastError
0x180002aa5  mov     r9d, [rsp+8E0h+FileTime.dwLowDateTime]
0x180002aaa  mov     edx, 0AFh
0x180002aaf  mov     dword ptr [rsp+8E0h+cchDate], eax
0x180002ab3  mov     rcx, rbx
0x180002ab6  mov     eax, [rsp+8E0h+FileTime.dwHighDateTime]
0x180002aba  mov     dword ptr [rsp+8E0h+lpDateStr], eax
0x180002abe  call    WPP_SF_ddd
0x180002ac3  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180002aca  jz      short loc_180002B13
0x180002acc  mov     word ptr [rbp+7E0h+var_840], r12w
0x180002ad1  call    cs:__imp_GetLastError
0x180002ad7  mov     r9d, [rsp+8E0h+FileTime.dwHighDateTime]
0x180002adc  lea     rdx, aFiletimetoloca; "FileTimeToLocalFileTime(%d %d) failed a"...
0x180002ae3  mov     r8d, [rsp+8E0h+FileTime.dwLowDateTime]
0x180002ae8  lea     rcx, [rbp+7E0h+var_840]
0x180002aec  mov     dword ptr [rsp+8E0h+lpDateStr], eax
0x180002af0  call    FormatRRASErrorString
0x180002af5  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180002afc  lea     r8, [rbp+7E0h+var_840]
0x180002b00  mov     rcx, cs:gSstpCfgEtwContext
0x180002b07  mov     rax, cs:gSstpCfgTemplateFunc
0x180002b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b13  mov     eax, r12d
0x180002b16  mov     rcx, [rbp+7E0h+var_40]
0x180002b1d  xor     rcx, rsp; StackCookie
0x180002b20  call    __security_check_cookie
0x180002b25  mov     rbx, [rsp+8E0h+arg_18]
0x180002b2d  add     rsp, 8B0h
0x180002b34  pop     r15
0x180002b36  pop     r14
0x180002b38  pop     r13
0x180002b3a  pop     r12
0x180002b3c  pop     rdi
0x180002b3d  pop     rsi
0x180002b3e  pop     rbp
0x180002b3f  retn
0x180002b40  lea     rdx, [rbp+7E0h+SystemTime]; lpSystemTime
0x180002b44  lea     rcx, [rsp+8E0h+LocalFileTime]; lpFileTime
0x180002b49  call    cs:__imp_FileTimeToSystemTime
0x180002b4f  test    eax, eax
0x180002b51  jnz     short loc_180002BC8
0x180002b53  mov     rbx, cs:WPP_GLOBAL_Control
0x180002b5a  lea     rax, WPP_GLOBAL_Control
0x180002b61  cmp     rbx, rax
0x180002b64  jz      short loc_180002B9A
0x180002b66  test    byte ptr [rbx+1Ch], 40h
0x180002b6a  jz      short loc_180002B9A
0x180002b6c  cmp     byte ptr [rbx+19h], 1
0x180002b70  jb      short loc_180002B9A
0x180002b72  mov     rbx, [rbx+10h]
0x180002b76  call    cs:__imp_GetLastError
0x180002b7c  mov     r9d, [rsp+8E0h+LocalFileTime.dwLowDateTime]
0x180002b81  mov     edx, 0B0h
0x180002b86  mov     dword ptr [rsp+8E0h+cchDate], eax
0x180002b8a  mov     rcx, rbx
0x180002b8d  mov     eax, [rsp+8E0h+LocalFileTime.dwHighDateTime]
0x180002b91  mov     dword ptr [rsp+8E0h+lpDateStr], eax
0x180002b95  call    WPP_SF_ddd
0x180002b9a  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180002ba1  jz      loc_180002B13
0x180002ba7  mov     word ptr [rbp+7E0h+var_840], r12w
0x180002bac  call    cs:__imp_GetLastError
0x180002bb2  mov     r9d, [rsp+8E0h+LocalFileTime.dwHighDateTime]
0x180002bb7  lea     rdx, aFiletimetosyst; "FileTimeToSystemTime(%d %d) failed and "...
0x180002bbe  mov     r8d, [rsp+8E0h+LocalFileTime.dwLowDateTime]
0x180002bc3  jmp     loc_180002AE8
0x180002bc8  mov     r13d, 400h
0x180002bce  mov     dword ptr [rsp+8E0h+cchDate], r12d; cchDate
0x180002bd3  mov     ecx, r13d; Locale
0x180002bd6  mov     [rsp+8E0h+lpDateStr], r12; lpDateStr
0x180002bdb  xor     r9d, r9d; lpFormat
0x180002bde  lea     r8, [rbp+7E0h+SystemTime]; lpDate
0x180002be2  xor     edx, edx; dwFlags
0x180002be4  call    cs:__imp_GetDateFormatW
0x180002bea  movsxd  rdi, eax
0x180002bed  test    eax, eax
0x180002bef  jnz     loc_180002D24
0x180002bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bfc  lea     rax, WPP_GLOBAL_Control
0x180002c03  cmp     rcx, rax
0x180002c06  jz      short loc_180002C86
0x180002c08  test    byte ptr [rcx+1Ch], 40h
0x180002c0c  jz      short loc_180002C86
0x180002c0e  cmp     byte ptr [rcx+19h], 1
0x180002c12  jb      short loc_180002C86
0x180002c14  movzx   eax, [rbp+7E0h+SystemTime.wYear]
0x180002c18  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x180002c1c  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x180002c20  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x180002c24  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x180002c29  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
0x180002c2e  movzx   r12d, [rbp+7E0h+SystemTime.wDayOfWeek]
0x180002c33  movzx   r13d, [rbp+7E0h+SystemTime.wMonth]
0x180002c38  mov     [rsp+8E0h+var_880], eax
0x180002c3c  mov     rax, [rcx+10h]
0x180002c40  mov     [rsp+8E0h+var_878], rax
0x180002c45  call    cs:__imp_GetLastError
0x180002c4b  mov     r9d, [rsp+8E0h+var_880]
0x180002c50  mov     edx, 0B1h
0x180002c55  mov     rcx, [rsp+8E0h+var_878]
0x180002c5a  mov     [rsp+8E0h+var_888], eax
0x180002c5e  mov     dword ptr [rsp+8E0h+var_890], ebx
0x180002c62  mov     dword ptr [rsp+8E0h+var_898], edi
0x180002c66  mov     dword ptr [rsp+8E0h+var_8A0], esi
0x180002c6a  mov     dword ptr [rsp+8E0h+var_8A8], r14d
0x180002c6f  mov     dword ptr [rsp+8E0h+var_8B0], r15d
0x180002c74  mov     dword ptr [rsp+8E0h+cchDate], r12d
0x180002c79  mov     dword ptr [rsp+8E0h+lpDateStr], r13d
0x180002c7e  call    WPP_SF_ddddddddd
0x180002c83  xor     r12d, r12d
0x180002c86  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180002c8d  jz      loc_180002D1B
0x180002c93  movzx   eax, [rbp+7E0h+SystemTime.wYear]
0x180002c97  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x180002c9b  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x180002c9f  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x180002ca3  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x180002ca8  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
0x180002cad  movzx   r13d, [rbp+7E0h+SystemTime.wMonth]
0x180002cb2  mov     word ptr [rbp+7E0h+var_840], r12w
0x180002cb7  movzx   r12d, [rbp+7E0h+SystemTime.wDayOfWeek]
0x180002cbc  mov     [rsp+8E0h+var_880], eax
0x180002cc0  call    cs:__imp_GetLastError
0x180002cc6  mov     r8d, [rsp+8E0h+var_880]
0x180002ccb  lea     rdx, aGetdateformatD; "GetDateFormat(%d %d %d %d %d %d %d %d) "...
0x180002cd2  mov     dword ptr [rsp+8E0h+var_890], eax
0x180002cd6  lea     rcx, [rbp+7E0h+var_840]
0x180002cda  mov     dword ptr [rsp+8E0h+var_898], ebx
0x180002cde  mov     r9d, r13d
0x180002ce1  mov     dword ptr [rsp+8E0h+var_8A0], edi
0x180002ce5  mov     dword ptr [rsp+8E0h+var_8A8], esi
0x180002ce9  mov     dword ptr [rsp+8E0h+var_8B0], r14d
0x180002cee  mov     dword ptr [rsp+8E0h+cchDate], r15d
0x180002cf3  mov     dword ptr [rsp+8E0h+lpDateStr], r12d
0x180002cf8  call    FormatRRASErrorString
0x180002cfd  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180002d04  lea     r8, [rbp+7E0h+var_840]
0x180002d08  mov     rcx, cs:gSstpCfgEtwContext
0x180002d0f  mov     rax, cs:gSstpCfgTemplateFunc
0x180002d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1b  mov     eax, [rsp+8E0h+var_87C]
0x180002d1f  jmp     loc_180002B16
0x180002d24  mov     dword ptr [rsp+8E0h+cchDate], r12d; cchTime
0x180002d29  lea     r8, [rbp+7E0h+SystemTime]; lpTime
0x180002d2d  xor     r9d, r9d; lpFormat
0x180002d30  mov     [rsp+8E0h+lpDateStr], r12; lpTimeStr
0x180002d35  xor     edx, edx; dwFlags
0x180002d37  mov     ecx, r13d; Locale
0x180002d3a  call    cs:__imp_GetTimeFormatW
0x180002d40  mov     esi, eax
0x180002d42  test    eax, eax
0x180002d44  jnz     loc_180002E2C
0x180002d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d51  lea     rax, WPP_GLOBAL_Control
0x180002d58  cmp     rcx, rax
0x180002d5b  jz      short loc_180002DDB
0x180002d5d  test    byte ptr [rcx+1Ch], 40h
0x180002d61  jz      short loc_180002DDB
0x180002d63  cmp     byte ptr [rcx+19h], 1
0x180002d67  jb      short loc_180002DDB
0x180002d69  movzx   eax, [rbp+7E0h+SystemTime.wYear]
0x180002d6d  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x180002d71  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x180002d75  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x180002d79  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x180002d7e  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
0x180002d83  movzx   r12d, [rbp+7E0h+SystemTime.wDayOfWeek]
0x180002d88  movzx   r13d, [rbp+7E0h+SystemTime.wMonth]
0x180002d8d  mov     [rsp+8E0h+var_880], eax
0x180002d91  mov     rax, [rcx+10h]
0x180002d95  mov     [rsp+8E0h+var_878], rax
0x180002d9a  call    cs:__imp_GetLastError
0x180002da0  mov     r9d, [rsp+8E0h+var_880]
0x180002da5  mov     edx, 0B2h
0x180002daa  mov     rcx, [rsp+8E0h+var_878]
0x180002daf  mov     [rsp+8E0h+var_888], eax
0x180002db3  mov     dword ptr [rsp+8E0h+var_890], ebx
0x180002db7  mov     dword ptr [rsp+8E0h+var_898], edi
0x180002dbb  mov     dword ptr [rsp+8E0h+var_8A0], esi
0x180002dbf  mov     dword ptr [rsp+8E0h+var_8A8], r14d
0x180002dc4  mov     dword ptr [rsp+8E0h+var_8B0], r15d
0x180002dc9  mov     dword ptr [rsp+8E0h+cchDate], r12d
0x180002dce  mov     dword ptr [rsp+8E0h+lpDateStr], r13d
0x180002dd3  call    WPP_SF_ddddddddd
0x180002dd8  xor     r12d, r12d
0x180002ddb  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180002de2  jz      loc_180002D1B
0x180002de8  movzx   eax, [rbp+7E0h+SystemTime.wYear]
0x180002dec  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x180002df0  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x180002df4  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x180002df8  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x180002dfd  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
0x180002e02  movzx   r13d, [rbp+7E0h+SystemTime.wMonth]
0x180002e07  mov     word ptr [rbp+7E0h+var_840], r12w
0x180002e0c  movzx   r12d, [rbp+7E0h+SystemTime.wDayOfWeek]
0x180002e11  mov     [rsp+8E0h+var_880], eax
0x180002e15  call    cs:__imp_GetLastError
0x180002e1b  mov     r8d, [rsp+8E0h+var_880]
0x180002e20  lea     rdx, aGettimeformatD; "GetTimeFormat(%d %d %d %d %d %d %d %d) "...
0x180002e27  jmp     loc_180002CD2
0x180002e2c  add     eax, edi
0x180002e2e  lea     ebx, [rax+rax]
0x180002e31  mov     [r15], ebx
0x180002e34  call    cs:__imp_GetProcessHeap
0x180002e3a  mov     r8d, ebx; dwBytes
0x180002e3d  mov     edx, 8; dwFlags
0x180002e42  mov     rcx, rax; hHeap
0x180002e45  call    cs:__imp_HeapAlloc
0x180002e4b  mov     [rbp+7E0h+lpMem], rax
0x180002e4f  mov     rbx, rax
0x180002e52  test    rax, rax
0x180002e55  jnz     short loc_180002EC0
0x180002e57  mov     rbx, cs:WPP_GLOBAL_Control
0x180002e5e  lea     rax, WPP_GLOBAL_Control
0x180002e65  cmp     rbx, rax
0x180002e68  jz      short loc_180002E90
0x180002e6a  test    byte ptr [rbx+1Ch], 40h
0x180002e6e  jz      short loc_180002E90
0x180002e70  cmp     byte ptr [rbx+19h], 1
0x180002e74  jb      short loc_180002E90
0x180002e76  mov     rbx, [rbx+10h]
0x180002e7a  call    cs:__imp_GetLastError
0x180002e80  mov     edx, 0B3h
0x180002e85  mov     rcx, rbx
0x180002e88  mov     r9d, eax
0x180002e8b  call    WPP_SF_d
0x180002e90  cmp     qword ptr cs:xmmword_1800146E0, r12
0x180002e97  jz      loc_180002B13
0x180002e9d  mov     word ptr [rbp+7E0h+var_840], r12w
0x180002ea2  call    cs:__imp_GetLastError
0x180002ea8  mov     r8d, eax
0x180002eab  lea     rdx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x180002eb2  lea     rcx, [rbp+7E0h+var_840]
0x180002eb6  call    FormatRRASErrorString
0x180002ebb  jmp     loc_180002AF5
0x180002ec0  mov     dword ptr [rsp+8E0h+cchDate], edi; cchDate
0x180002ec4  lea     r8, [rbp+7E0h+SystemTime]; lpDate
0x180002ec8  xor     r9d, r9d; lpFormat
0x180002ecb  mov     [rsp+8E0h+lpDateStr], rbx; lpDateStr
0x180002ed0  xor     edx, edx; dwFlags
0x180002ed2  mov     ecx, r13d; Locale
0x180002ed5  call    cs:__imp_GetDateFormatW
0x180002edb  test    eax, eax
0x180002edd  jnz     loc_180002FC5
0x180002ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eea  lea     rax, WPP_GLOBAL_Control
0x180002ef1  cmp     rcx, rax
0x180002ef4  jz      short loc_180002F74
0x180002ef6  test    byte ptr [rcx+1Ch], 40h
0x180002efa  jz      short loc_180002F74
0x180002efc  cmp     byte ptr [rcx+19h], 1
0x180002f00  jb      short loc_180002F74
0x180002f02  movzx   eax, [rbp+7E0h+SystemTime.wYear]
0x180002f06  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x180002f0a  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x180002f0e  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x180002f12  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x180002f17  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
  ... truncated ...
```
