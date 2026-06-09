# GetTriggerRunTimes(_TASK_TRIGGER &,_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *,ulong,ulong,ushort,ushort)

- ea: `0x180001f20`
- end: `0x180002b87`
- name: `?GetTriggerRunTimes@@YAJAEAU_TASK_TRIGGER@@PEBU_SYSTEMTIME@@1PEAGGPEAVCTimeRunList@@2KKGG@Z`
- size: `3175`
- prototype: `int __fastcall(struct _TASK_TRIGGER *, const struct _SYSTEMTIME *, const struct _SYSTEMTIME *, unsigned __int16 *, unsigned __int16, struct CTimeRunList *, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025500`

## callees

- `0x180001f20`
- `0x180005960`
- `0x180008538`
- `0x180023fa4`
- `0x180026b5c`
- `0x18002b4ac`
- `0x18002b618`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000208f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000208f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000204c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800020e8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800020fe`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002679`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002690`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002772`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000204c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800020e8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800020fe`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002679`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002690`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002772`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001fba`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001ff8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000203a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000206b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002085`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002274`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002621`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000282a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002b01`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001fba`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001ff8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000203a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000206b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002085`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002274`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002621`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000282a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002b01`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002283`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000254a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002839`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002283`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000254a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180002839`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall GetTriggerRunTimes(
        struct _TASK_TRIGGER *a1,
        const struct _SYSTEMTIME *a2,
        const struct _SYSTEMTIME *a3,
        unsigned __int16 *a4,
        unsigned __int16 a5,
        struct CTimeRunList *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned __int16 a10,
        unsigned __int16 a11)
{
  DWORD rgFlags; // edx
  __int32 v15; // ecx
  int v16; // esi
  int result; // eax
  TASK_TRIGGER_TYPE TriggerType; // ecx
  FILETIME v19; // rbx
  WORD v20; // dx
  int v21; // r14d
  int v22; // r13d
  WORD v23; // r15
  __int32 v24; // ecx
  __int32 v25; // ecx
  __int16 v26; // ax
  unsigned __int16 k; // r8
  __int64 v28; // rax
  __int16 v29; // dx
  int wBeginMonth; // r8d
  unsigned __int16 v31; // r12
  int wBeginYear; // r15d
  unsigned __int16 v33; // r13
  unsigned int v34; // edx
  unsigned __int16 v35; // cx
  __int16 v36; // ax
  unsigned __int16 v37; // ax
  int dwLowDateTime_low; // r8d
  unsigned __int16 v39; // r15
  unsigned __int16 v40; // ax
  WORD DaysInterval; // ax
  WORD v42; // bx
  DWORD rgfDays; // r9d
  int v44; // r12d
  unsigned __int16 jj; // r8
  char v46; // cl
  __int64 v47; // rax
  unsigned __int16 kk; // r8
  __int64 v49; // rax
  __int16 v50; // dx
  int v51; // eax
  int wBeginDay; // esi
  unsigned __int16 mm; // cx
  int v54; // r15d
  __int16 nn; // cx
  unsigned __int16 v56; // ax
  int v57; // esi
  unsigned __int16 v58; // r15
  unsigned __int16 i; // r8
  __int64 v60; // rax
  __int16 v61; // dx
  unsigned __int16 j; // dx
  unsigned __int16 v63; // ax
  unsigned __int16 v64; // r8
  WORD wStartMinute; // ax
  __int64 MinutesDuration; // rax
  FILETIME v67; // rbx
  struct _FILETIME v68; // rax
  bool v69; // zf
  unsigned __int16 v70; // ax
  DWORD MinutesInterval; // edx
  TASK_TRIGGER_TYPE v72; // ecx
  __int32 v73; // ecx
  __int32 v74; // ecx
  __int32 v75; // ecx
  int v76; // r10d
  __int16 v77; // dx
  unsigned __int16 m; // cx
  WORD v79; // dx
  WORD v80; // bx
  WORD v81; // ax
  WORD v82; // si
  int v83; // r9d
  __int16 v84; // dx
  unsigned __int16 v85; // r8
  unsigned __int16 v86; // cx
  unsigned __int16 v87; // si
  unsigned __int16 v88; // ax
  int v89; // ebx
  int v90; // edx
  int v91; // r15d
  int v92; // ebx
  int v93; // r14d
  unsigned __int16 v94; // cx
  unsigned __int16 v95; // si
  unsigned __int16 v96; // r9
  unsigned __int16 v97; // ax
  unsigned __int16 v98; // bx
  __int16 n; // dx
  unsigned __int16 v100; // ax
  unsigned __int16 v101; // cx
  int v102; // r8d
  unsigned __int16 ii; // dx
  __int16 v104; // ax
  __int64 v105; // r9
  unsigned __int16 v106; // r9
  WORD v107; // dx
  DWORD v108; // edx
  WORD wEndYear; // ax
  WORD wEndMonth; // ax
  unsigned __int16 *v111; // [rsp+20h] [rbp-E0h]
  int v112; // [rsp+50h] [rbp-B0h]
  int v113; // [rsp+54h] [rbp-ACh]
  unsigned __int16 v114[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v115; // [rsp+5Ch] [rbp-A4h]
  int wDayOfWeek; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v117; // [rsp+64h] [rbp-9Ch] BYREF
  FILETIME v118; // [rsp+68h] [rbp-98h] BYREF
  int v119; // [rsp+70h] [rbp-90h]
  int v120; // [rsp+74h] [rbp-8Ch]
  DWORD dwLowDateTime; // [rsp+78h] [rbp-88h]
  FILETIME FileTime1; // [rsp+80h] [rbp-80h] BYREF
  FILETIME v123; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v124; // [rsp+90h] [rbp-70h] BYREF
  FILETIME v125; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME v127; // [rsp+A8h] [rbp-58h] BYREF
  _FILETIME FileTime; // [rsp+B0h] [rbp-50h] BYREF
  CTimeRunList *v129; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v130[12]; // [rsp+C0h] [rbp-40h]
  SYSTEMTIME SystemTime; // [rsp+120h] [rbp+20h] BYREF
  _WORD v132[8]; // [rsp+130h] [rbp+30h]

  v130[0] = a4;
  rgFlags = a1->rgFlags;
  v129 = a6;
  if ( (rgFlags & 0x10004) != 0 )
    return 267015;
  v15 = a1->TriggerType - 5;
  if ( v15 && (unsigned int)(v15 - 1) >= 2 )
  {
    v16 = 0;
    *(_QWORD *)&SystemTime.wYear = 0;
    *(_QWORD *)&SystemTime.wHour = 0;
    v125 = 0;
    FileTime1 = 0;
    FileTime = 0;
    FileTime2 = 0;
    if ( !SystemTimeToFileTime(a2, &FileTime) )
      goto LABEL_13;
    SystemTime.wYear = a1->wBeginYear;
    SystemTime.wMonth = a1->wBeginMonth;
    SystemTime.wDay = a1->wBeginDay;
    SystemTime.wHour = a1->wStartHour;
    SystemTime.wMinute = a1->wStartMinute;
    if ( !SystemTimeToFileTime(&SystemTime, &v125) )
      goto LABEL_13;
    v69 = (a1->rgFlags & 1) == 0;
    *(_DWORD *)&SystemTime.wHour = 3866647;
    *(_DWORD *)&SystemTime.wSecond = 59;
    if ( v69 )
    {
      *(_DWORD *)&SystemTime.wYear = 788632;
      SystemTime.wDay = 31;
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime1) )
        goto LABEL_13;
    }
    else
    {
      SystemTime.wYear = a1->wEndYear;
      SystemTime.wMonth = a1->wEndMonth;
      SystemTime.wDay = a1->wEndDay;
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime1) )
        goto LABEL_13;
      if ( CompareFileTime(&FileTime1, &FileTime) < 0 )
        return 0;
    }
    if ( !a3 )
      goto LABEL_18;
    if ( !SystemTimeToFileTime(a3, &FileTime2) )
    {
LABEL_13:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    if ( CompareFileTime(&v125, &FileTime2) >= 0 )
      return 0;
    if ( CompareFileTime(&FileTime1, &FileTime2) < 0 )
LABEL_18:
      FileTime2 = FileTime1;
    TriggerType = a1->TriggerType;
    v124 = 0;
    v19 = 0;
    v118 = 0;
    v20 = 0;
    v123 = 0;
    v21 = 0;
    v120 = 0;
    LOWORD(v22) = 0;
    wDayOfWeek = 0;
    v23 = 0;
    v113 = 0;
    v114[0] = 0;
    v112 = 0;
    v115 = 0;
    dwLowDateTime = 0;
    v119 = 0;
    if ( (unsigned int)TriggerType < TASK_TIME_TRIGGER_WEEKLY )
    {
      v19 = v125;
      v118 = v125;
      goto LABEL_105;
    }
    v24 = TriggerType - 2;
    if ( !v24 )
    {
      if ( a1->Type.Weekly.rgfDaysOfTheWeek )
      {
        FileTimeToSystemTime(&v125, &SystemTime);
        for ( i = 0; i < 7u; ++i )
        {
          v60 = i;
          v61 = (a1->Type.Weekly.rgfDaysOfTheWeek >> i) & 1;
          v132[v60] = v61;
        }
        for ( j = 0; ; ++j )
        {
          if ( j >= 7u )
            goto LABEL_100;
          v63 = j + SystemTime.wDayOfWeek - 7;
          if ( (unsigned __int16)(j + SystemTime.wDayOfWeek) < 7u )
            v63 = j + SystemTime.wDayOfWeek;
          if ( v132[v63] )
            break;
          LOWORD(v21) = v63;
          wDayOfWeek = v63;
        }
        v118 = v125;
        AddDaysToFileTime(&v118, j);
        LOWORD(v21) = v64;
        wDayOfWeek = v64;
LABEL_100:
        v19 = v118;
        v20 = 0;
        goto LABEL_105;
      }
      return 0;
    }
    v25 = v24 - 1;
    if ( v25 )
    {
      if ( v25 == 1 )
      {
        dwLowDateTime = 0;
        while ( v20 < 7u )
        {
          if ( ((a1->Type.Weekly.rgfDaysOfTheWeek >> v20) & 1) != 0 )
          {
            ++LOWORD(v19.dwLowDateTime);
            v26 = 1;
            dwLowDateTime = v19.dwLowDateTime;
          }
          else
          {
            if ( 2 * (unsigned __int64)v20 >= 0xE )
              _report_rangecheckfailure();
            v26 = 0;
          }
          v132[v20++] = v26;
        }
        for ( k = 0; k < 0xCu; ++k )
        {
          v28 = k;
          v29 = (a1->Type.MonthlyDate.rgfMonths >> k) & 1;
          *((_WORD *)&v130[1] + v28) = v29;
        }
        wBeginMonth = a1->wBeginMonth;
        v31 = 0;
        wBeginYear = a1->wBeginYear;
        v112 = wBeginMonth;
        v115 = wBeginYear;
LABEL_34:
        v33 = v31;
        v34 = v31 + 12;
        if ( v31 < v34 )
        {
          do
          {
            if ( *((_WORD *)v130 + (unsigned __int16)wBeginMonth + 3) )
              break;
            ++v33;
            v35 = wBeginMonth + 1;
            v36 = -11;
            if ( (unsigned __int16)(wBeginMonth + 1) <= 0xCu )
              v36 = 1;
            LOWORD(wBeginMonth) = v36 + wBeginMonth;
            v37 = wBeginYear + 1;
            if ( v35 <= 0xCu )
              v37 = wBeginYear;
            wBeginYear = v37;
          }
          while ( v33 < v34 );
          v115 = wBeginYear;
          v112 = wBeginMonth;
        }
        SystemTime.wMonth = wBeginMonth;
        SystemTime.wDay = 1;
        SystemTime.wYear = wBeginYear;
        SystemTimeToFileTime(&SystemTime, &v118);
        FileTimeToSystemTime(&v118, &SystemTime);
        v20 = v113;
        dwLowDateTime_low = LOWORD(v19.dwLowDateTime);
        v119 = LOWORD(v19.dwLowDateTime);
        while ( 1 )
        {
          if ( (unsigned __int16)v16 >= 7u )
            goto LABEL_56;
          v39 = v16 + 1;
          v40 = v16 + SystemTime.wDayOfWeek - 7;
          if ( (unsigned __int16)(v16 + SystemTime.wDayOfWeek) < 7u )
            v40 = v16 + SystemTime.wDayOfWeek;
          v21 = v40;
          if ( v132[v40] )
          {
            LOWORD(dwLowDateTime_low) = dwLowDateTime_low - 1;
            DaysInterval = a1->Type.Daily.DaysInterval;
            v119 = dwLowDateTime_low;
            v42 = v16 + 1 + 7 * DaysInterval - 7;
            MonthDays(v112, v115, v114);
            if ( v42 > v114[0] )
              v42 -= 7;
            wDayOfWeek = (unsigned __int16)v21;
            v20 = v42;
            v113 = v42;
            if ( v33 || (wDayOfWeek = (unsigned __int16)v21, v42 >= a1->wBeginDay) )
            {
              LOWORD(v21) = wDayOfWeek;
LABEL_56:
              v19 = v118;
              LOWORD(v22) = v112;
              v120 = v16 + 1;
LABEL_103:
              v23 = v115;
LABEL_104:
              v16 = 0;
LABEL_105:
              if ( (unsigned int)(a1->TriggerType - 3) <= 1 )
              {
                SystemTime.wHour = a1->wStartHour;
                wStartMinute = a1->wStartMinute;
                SystemTime.wDay = v20;
                SystemTime.wMinute = wStartMinute;
                SystemTime.wYear = v23;
                SystemTime.wMonth = v22;
                *(_DWORD *)&SystemTime.wSecond = 0;
                SystemTimeToFileTime(&SystemTime, &v118);
                v19 = v118;
              }
              MinutesDuration = a1->MinutesDuration;
              v123 = v19;
              v124 = v19;
              if ( (_DWORD)MinutesDuration )
              {
                v127 = v19;
                v123 = (FILETIME)(600000000 * MinutesDuration + *(_QWORD *)&v19);
              }
              do
              {
LABEL_109:
                if ( CompareFileTime(&v118, &FileTime2) >= 0 )
                  return 0;
                if ( CompareFileTime(&v118, &FileTime) >= 0 )
                {
                  if ( v129 )
                  {
                    v67 = (FILETIME)0x7FFFFFFFFFFFFFFFLL;
                    if ( (a1->rgFlags & 2) != 0 )
                      v67 = v123;
                    if ( (a8 & 0x10) != 0 )
                    {
                      v127 = v118;
                      AddMinutesToFileTime(&v127, a11);
                      v68 = minFileTime(FileTime1, v127);
                    }
                    else
                    {
                      v68 = FileTime1;
                    }
                    result = CTimeRunList::AddSorted(v129, v118, v68, v67, v111, a8, a9, a10, v130[0], a5);
                    if ( result < 0 )
                      return result;
                    if ( result == 1 )
                      return 0;
                  }
                  else
                  {
                    v69 = *v130[0] == a5;
                    if ( *v130[0] < a5 )
                    {
                      v70 = *v130[0] + 1;
                      *v130[0] = v70;
                      v69 = v70 == a5;
                    }
                    if ( v69 )
                      return 0;
                  }
                }
                MinutesInterval = a1->MinutesInterval;
                if ( MinutesInterval )
                {
                  AddMinutesToFileTime(&v118, MinutesInterval);
                  if ( CompareFileTime(&v123, &v118) <= 0 )
                    v16 = 1;
                }
              }
              while ( a1->MinutesInterval && !v16 );
              v72 = a1->TriggerType;
              if ( v72 == TASK_TIME_TRIGGER_ONCE )
                return 0;
              v73 = v72 - 1;
              if ( v73 )
              {
                v74 = v73 - 1;
                if ( v74 )
                {
                  v75 = v74 - 1;
                  if ( v75 )
                  {
                    if ( v75 != 1 )
                      return -2147467259;
                    v76 = v119;
                    if ( (_WORD)v119 )
                    {
                      LOWORD(v83) = v112;
                      v84 = 1;
                    }
                    else
                    {
                      v77 = v112;
                      for ( m = 0; m < 0xCu; ++m )
                      {
                        v79 = v77 + 1;
                        v80 = v23 + 1;
                        v81 = 1;
                        if ( v79 <= 0xCu )
                        {
                          v81 = v79;
                          v80 = v23;
                        }
                        v82 = v81;
                        if ( *((_WORD *)v130 + v81 + 3) )
                          break;
                        v77 = v81;
                        v23 = v80;
                      }
                      SystemTime.wMonth = v81;
                      v120 = 1;
                      SystemTime.wDay = 1;
                      SystemTime.wYear = v80;
                      SystemTimeToFileTime(&SystemTime, &v118);
                      FileTimeToSystemTime(&v118, &SystemTime);
                      v76 = (unsigned __int16)dwLowDateTime;
                      LOWORD(v83) = v82;
                      LOWORD(v21) = SystemTime.wDayOfWeek;
                      v23 = v80;
                      v119 = (unsigned __int16)dwLowDateTime;
                      v84 = 0;
                      v112 = v82;
                      wDayOfWeek = SystemTime.wDayOfWeek;
                      v115 = v80;
                    }
                    v85 = v120;
                    while ( (unsigned __int16)v84 <= 7u )
                    {
                      v86 = v21 + 1;
                      v87 = v85 + 1;
                      if ( !v84 )
                      {
                        v86 = v21;
                        v87 = v85;
                      }
                      v88 = v86 - 7;
                      if ( v86 < 7u )
                        v88 = v86;
                      v21 = v88;
                      if ( v132[v88] )
                      {
                        LOWORD(v76) = v76 - 1;
                        v89 = 7 * a1->Type.Daily.DaysInterval;
                        v119 = v76;
                        v117 = 0;
                        LOWORD(v89) = v87 + v89 - 7;
                        MonthDays(v83, v23, &v117);
                        LOWORD(v83) = v112;
                        v120 = v87;
                        wDayOfWeek = v21;
                        if ( (unsigned __int16)v89 <= v117 )
                        {
                          LOWORD(v90) = v89;
                          v113 = (unsigned __int16)v89;
                        }
                        else
                        {
                          LOWORD(v90) = v89 - 7;
                          v113 = v89 - 7;
                        }
                        goto LABEL_191;
                      }
                      v85 = v87;
                      wDayOfWeek = v88;
                      v120 = v87;
                      ++v84;
                    }
LABEL_190:
                    LOWORD(v90) = v113;
                  }
                  else
                  {
                    LOWORD(v83) = v112;
                    v91 = 0;
                    v92 = v115;
                    v93 = 0;
                    while ( 1 )
                    {
                      MonthDays(v83, v92, v114);
                      v94 = v114[0];
                      v83 = v112;
                      v95 = 1;
                      v90 = v113;
                      while ( v95 <= v94 )
                      {
                        LOWORD(v90) = v90 + 1;
                        if ( (unsigned __int16)v90 <= v94 )
                        {
                          v113 = v90;
                        }
                        else
                        {
                          v96 = v83 + 1;
                          LOWORD(v113) = 1;
                          v91 = 1;
                          if ( v96 > 0xCu )
                          {
                            LOWORD(v92) = v92 + 1;
                            v115 = v92;
                          }
                          v97 = 1;
                          if ( v96 <= 0xCu )
                            v97 = v96;
                          v98 = v97;
                          MonthDays(v97, v115, v114);
                          v94 = v114[0];
                          v83 = v98;
                          v92 = v115;
                          v90 = v113;
                          v112 = v83;
                        }
                        if ( *((_WORD *)&v130[3] + (unsigned __int16)v90 + 3) )
                        {
                          v93 = 1;
                          break;
                        }
                        ++v95;
                      }
                      if ( !v91 && v93 )
                        break;
                      for ( n = 1; (unsigned __int16)n <= 0xCu; ++n )
                      {
                        v100 = v83;
                        if ( (unsigned __int16)v83 > 0xCu )
                        {
                          v83 = 1;
                          v112 = 1;
                        }
                        v101 = v92 + 1;
                        if ( v100 <= 0xCu )
                          v101 = v92;
                        v92 = v101;
                        v115 = v101;
                        if ( *((_WORD *)v130 + (unsigned __int16)v83 + 3) )
                        {
                          v91 = 0;
                          break;
                        }
                        LOWORD(v83) = v83 + 1;
                        v112 = v83;
                      }
                      if ( v93 )
                      {
                        v23 = v115;
                        LOWORD(v21) = wDayOfWeek;
                        goto LABEL_190;
                      }
                    }
                    v23 = v115;
                    LOWORD(v21) = wDayOfWeek;
                  }
LABEL_191:
                  if ( (unsigned int)(a1->TriggerType - 3) <= 1 )
                  {
                    SystemTime.wHour = a1->wStartHour;
                    SystemTime.wMinute = a1->wStartMinute;
                    SystemTime.wDay = v90;
                    *(_DWORD *)&SystemTime.wSecond = 0;
                    SystemTime.wYear = v23;
                    SystemTime.wMonth = v83;
                    SystemTimeToFileTime(&SystemTime, &v124);
                  }
                  v108 = a1->MinutesDuration;
                  v123 = v124;
                  v118 = v124;
                  AddMinutesToFileTime(&v123, v108);
                  v16 = 0;
                  goto LABEL_109;
                }
                v102 = 0;
                for ( ii = 1; ii <= 7u; ++ii )
                {
                  v104 = -6;
                  if ( (unsigned __int16)(v21 + 1) >= 7u )
                    v102 = 1;
                  else
                    v104 = 1;
                  v105 = (unsigned __int16)(v21 + v104);
                  if ( v132[v105] )
                  {
                    AddDaysToFileTime(&v124, ii);
                    LOWORD(v21) = v106;
                    wDayOfWeek = v106;
                    break;
                  }
                  LOWORD(v21) = v21 + v104;
                  wDayOfWeek = (unsigned __int16)v105;
                }
                if ( v102 )
                {
                  v107 = 7 * a1->Type.Daily.DaysInterval - 7;
                  goto LABEL_188;
                }
              }
              else
              {
                v107 = a1->Type.Daily.DaysInterval;
LABEL_188:
                AddDaysToFileTime(&v124, v107);
              }
              LOWORD(v83) = v112;
              goto LABEL_190;
            }
            dwLowDateTime_low = v119;
            if ( !(_WORD)v119 )
            {
              wBeginMonth = v112;
              ++v31;
              wBeginYear = v115;
              v16 = 0;
              LOWORD(v19.dwLowDateTime) = dwLowDateTime;
              wDayOfWeek = v21;
              goto LABEL_34;
            }
          }
          else
          {
            v20 = v16 + 1;
            v113 = v39;
          }
          v16 = v39;
          wDayOfWeek = v21;
        }
      }
      return -2147467259;
    }
    rgfDays = a1->Type.MonthlyDate.rgfDays;
    if ( rgfDays )
    {
      v44 = 0;
      for ( jj = 0; jj < 0x1Fu; ++jj )
      {
        v46 = jj;
        v47 = jj;
        *((_WORD *)&v130[4] + v47) = (rgfDays >> v46) & 1;
      }
      for ( kk = 0; kk < 0xCu; ++kk )
      {
        v49 = kk;
        v50 = (a1->Type.MonthlyDate.rgfMonths >> kk) & 1;
        *((_WORD *)&v130[1] + v49) = v50;
      }
      v51 = a1->wBeginYear;
      wBeginDay = a1->wBeginDay;
      v22 = a1->wBeginMonth;
      v113 = wBeginDay;
      v117 = v51 + 2;
      v115 = v51;
      while ( 1 )
      {
        MonthDays(v22, v51, v114);
        for ( mm = 0; ; ++mm )
        {
          if ( mm >= v114[0] )
            goto LABEL_70;
          if ( (unsigned __int16)wBeginDay > v114[0] )
          {
            wBeginDay = 1;
            v44 = 1;
            v113 = 1;
          }
          if ( *((_WORD *)&v130[3] + (unsigned __int16)wBeginDay + 3) )
            break;
          LOWORD(wBeginDay) = wBeginDay + 1;
          v113 = wBeginDay;
        }
        v21 = 1;
LABEL_70:
        v54 = v115;
        for ( nn = 0; ; nn = 1 )
        {
          while ( 1 )
          {
            v56 = v22;
            if ( (unsigned __int16)v22 > 0xCu )
              v22 = 1;
            v57 = v54 + 1;
            if ( v56 <= 0xCu )
              LOWORD(v57) = v54;
            if ( *((_WORD *)v130 + (unsigned __int16)v22 + 3) )
              break;
            LOWORD(v22) = v22 + 1;
            ++nn;
            v54 = (unsigned __int16)v57;
            if ( (unsigned __int16)nn >= 0xCu )
              goto LABEL_80;
          }
          if ( !v44 || nn )
            break;
          v44 = 0;
          LOWORD(v22) = v22 + 1;
          v54 = (unsigned __int16)v57;
        }
LABEL_80:
        v58 = v117;
        v112 = v22;
        if ( v21 )
        {
          MonthDays(v22, v57, v114);
          v20 = v113;
          if ( (unsigned __int16)v113 <= v114[0] )
          {
            LOWORD(v21) = wDayOfWeek;
            v23 = v57;
            v115 = (unsigned __int16)v57;
            goto LABEL_104;
          }
          v21 = 0;
          LOWORD(v22) = v22 + 1;
          v20 = 1;
          v113 = 1;
          if ( (unsigned __int16)v22 > 0xCu )
          {
            v22 = 1;
            v51 = v57 + 1;
            v112 = 1;
            goto LABEL_87;
          }
          v112 = v22;
        }
        else
        {
          v20 = 1;
          v113 = 1;
        }
        v51 = (unsigned __int16)v57;
LABEL_87:
        v115 = v51;
        if ( (unsigned __int16)v51 >= v58 )
        {
          LOWORD(v21) = wDayOfWeek;
          goto LABEL_103;
        }
        wBeginDay = 1;
      }
    }
    return 0;
  }
  if ( (rgFlags & 1) != 0 )
  {
    wEndYear = a1->wEndYear;
    if ( wEndYear <= a2->wYear )
    {
      if ( wEndYear != a2->wYear )
        return 0;
      wEndMonth = a1->wEndMonth;
      if ( wEndMonth <= a2->wMonth && (wEndMonth != a2->wMonth || a1->wEndDay < a2->wDay) )
        return 0;
    }
  }
  return 267016;
}

```

## disassembly

```asm
0x180001f20  mov     r11, rsp
0x180001f23  push    rbp
0x180001f24  push    rbx
0x180001f25  push    rdi
0x180001f26  lea     rbp, [rsp-80h]
0x180001f2b  sub     rsp, 180h
0x180001f32  mov     rax, cs:__security_cookie
0x180001f39  xor     rax, rsp
0x180001f3c  mov     [rbp+90h+var_50], rax
0x180001f40  mov     rax, [rbp+90h+arg_28]
0x180001f47  mov     rbx, r8
0x180001f4a  mov     r8, rdx
0x180001f4d  mov     [rbp+90h+var_D0], r9
0x180001f51  mov     edx, [rcx+1Ch]
0x180001f54  mov     rdi, rcx
0x180001f57  mov     [rbp+90h+var_D8], rax
0x180001f5b  test    edx, 10004h
0x180001f61  jnz     loc_180002B7D
0x180001f67  mov     ecx, [rcx+20h]
0x180001f6a  mov     [r11-20h], rsi
0x180001f6e  mov     [r11-28h], r12
0x180001f72  mov     [r11-30h], r13
0x180001f76  mov     [r11-38h], r14
0x180001f7a  mov     [r11-40h], r15
0x180001f7e  sub     ecx, 5
0x180001f81  jz      loc_180002B43
0x180001f87  sub     ecx, 1
0x180001f8a  jz      loc_180002B43
0x180001f90  cmp     ecx, 1
0x180001f93  jz      loc_180002B43
0x180001f99  xor     esi, esi
0x180001f9b  lea     rdx, [rbp+90h+FileTime]; lpFileTime
0x180001f9f  mov     rcx, r8; lpSystemTime
0x180001fa2  mov     qword ptr [rbp+90h+SystemTime.wYear], rsi
0x180001fa6  mov     qword ptr [rbp+90h+SystemTime.wHour], rsi
0x180001faa  mov     qword ptr [rbp+90h+var_F8.dwLowDateTime], rsi
0x180001fae  mov     qword ptr [rbp+90h+FileTime1.dwLowDateTime], rsi
0x180001fb2  mov     qword ptr [rbp+90h+FileTime.dwLowDateTime], rsi
0x180001fb6  mov     qword ptr [rbp+90h+FileTime2.dwLowDateTime], rsi
0x180001fba  call    cs:__imp_SystemTimeToFileTime
0x180001fc0  test    eax, eax
0x180001fc2  jz      loc_18000208F
0x180001fc8  movzx   eax, word ptr [rdi+4]
0x180001fcc  lea     rdx, [rbp+90h+var_F8]; lpFileTime
0x180001fd0  mov     [rbp+90h+SystemTime.wYear], ax
0x180001fd4  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x180001fd8  movzx   eax, word ptr [rdi+6]
0x180001fdc  mov     [rbp+90h+SystemTime.wMonth], ax
0x180001fe0  movzx   eax, word ptr [rdi+8]
0x180001fe4  mov     [rbp+90h+SystemTime.wDay], ax
0x180001fe8  movzx   eax, word ptr [rdi+10h]
0x180001fec  mov     [rbp+90h+SystemTime.wHour], ax
0x180001ff0  movzx   eax, word ptr [rdi+12h]
0x180001ff4  mov     [rbp+90h+SystemTime.wMinute], ax
0x180001ff8  call    cs:__imp_SystemTimeToFileTime
0x180001ffe  test    eax, eax
0x180002000  jz      loc_18000208F
0x180002006  test    byte ptr [rdi+1Ch], 1
0x18000200a  lea     rdx, [rbp+90h+FileTime1]; lpFileTime
0x18000200e  mov     dword ptr [rbp+90h+SystemTime.wHour], 3B0017h
0x180002015  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x180002019  mov     dword ptr [rbp+90h+SystemTime.wSecond], 3Bh ; ';'
0x180002020  jz      short loc_18000205B
0x180002022  movzx   eax, word ptr [rdi+0Ah]
0x180002026  mov     [rbp+90h+SystemTime.wYear], ax
0x18000202a  movzx   eax, word ptr [rdi+0Ch]
0x18000202e  mov     [rbp+90h+SystemTime.wMonth], ax
0x180002032  movzx   eax, word ptr [rdi+0Eh]
0x180002036  mov     [rbp+90h+SystemTime.wDay], ax
0x18000203a  call    cs:__imp_SystemTimeToFileTime
0x180002040  test    eax, eax
0x180002042  jz      short loc_18000208F
0x180002044  lea     rdx, [rbp+90h+FileTime]; lpFileTime2
0x180002048  lea     rcx, [rbp+90h+FileTime1]; lpFileTime1
0x18000204c  call    cs:__imp_CompareFileTime
0x180002052  test    eax, eax
0x180002054  jns     short loc_180002075
0x180002056  jmp     loc_180002B6C
0x18000205b  mov     eax, 1Fh
0x180002060  mov     dword ptr [rbp+90h+SystemTime.wYear], 0C0898h
0x180002067  mov     [rbp+90h+SystemTime.wDay], ax
0x18000206b  call    cs:__imp_SystemTimeToFileTime
0x180002071  test    eax, eax
0x180002073  jz      short loc_18000208F
0x180002075  test    rbx, rbx
0x180002078  jz      loc_180002108
0x18000207e  lea     rdx, [rbp+90h+FileTime2]; lpFileTime
0x180002082  mov     rcx, rbx; lpSystemTime
0x180002085  call    cs:__imp_SystemTimeToFileTime
0x18000208b  test    eax, eax
0x18000208d  jnz     short loc_1800020E0
0x18000208f  call    cs:__imp_GetLastError
0x180002095  test    eax, eax
0x180002097  jle     short loc_1800020A1
0x180002099  movzx   eax, ax
0x18000209c  or      eax, 80070000h
0x1800020a1  mov     r14, [rsp+190h+var_30]
0x1800020a9  mov     r13, [rsp+190h+var_28]
0x1800020b1  mov     r12, [rsp+190h+var_20]
0x1800020b9  mov     rsi, [rsp+190h+var_18]
0x1800020c1  mov     r15, [rsp+190h+var_38]
0x1800020c9  mov     rcx, [rbp+90h+var_50]
0x1800020cd  xor     rcx, rsp; StackCookie
0x1800020d0  call    __security_check_cookie
0x1800020d5  add     rsp, 180h
0x1800020dc  pop     rdi
0x1800020dd  pop     rbx
0x1800020de  pop     rbp
0x1800020df  retn
0x1800020e0  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x1800020e4  lea     rcx, [rbp+90h+var_F8]; lpFileTime1
0x1800020e8  call    cs:__imp_CompareFileTime
0x1800020ee  test    eax, eax
0x1800020f0  jns     loc_180002B6C
0x1800020f6  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x1800020fa  lea     rcx, [rbp+90h+FileTime1]; lpFileTime1
0x1800020fe  call    cs:__imp_CompareFileTime
0x180002104  test    eax, eax
0x180002106  jns     short loc_180002110
0x180002108  mov     rax, qword ptr [rbp+90h+FileTime1.dwLowDateTime]
0x18000210c  mov     qword ptr [rbp+90h+FileTime2.dwLowDateTime], rax
0x180002110  mov     ecx, [rdi+20h]
0x180002113  mov     r9d, 1
0x180002119  mov     qword ptr [rbp+90h+var_100.dwLowDateTime], rsi
0x18000211d  mov     rbx, rsi
0x180002120  mov     qword ptr [rsp+190h+var_128.dwLowDateTime], rbx
0x180002125  mov     edx, esi
0x180002127  mov     qword ptr [rbp+90h+var_108.dwLowDateTime], rsi
0x18000212b  mov     r14d, esi
0x18000212e  mov     [rsp+190h+var_11C], esi
0x180002132  mov     r13d, esi
0x180002135  mov     [rsp+190h+var_130], esi
0x180002139  mov     r15d, esi
0x18000213c  mov     [rsp+190h+var_13C], edx
0x180002140  mov     [rsp+190h+var_138], si
0x180002145  mov     [rsp+190h+var_140], esi
0x180002149  mov     [rsp+190h+var_134], esi
0x18000214d  mov     [rsp+190h+var_118], esi
0x180002151  mov     [rsp+190h+var_120], esi
0x180002155  cmp     ecx, r9d
0x180002158  jz      loc_1800025D1
0x18000215e  test    ecx, ecx
0x180002160  jz      loc_1800025D1
0x180002166  sub     ecx, 2
0x180002169  jz      loc_180002538
0x18000216f  sub     ecx, r9d
0x180002172  jz      loc_180002383
0x180002178  cmp     ecx, r9d
0x18000217b  jnz     loc_180002B39
0x180002181  mov     [rsp+190h+var_118], ebx
0x180002185  cmp     dx, 7
0x180002189  jnb     short loc_1800021C7
0x18000218b  movzx   eax, dx
0x18000218e  movzx   ecx, dx
0x180002191  lea     r8, [rax+rax]
0x180002195  movzx   eax, word ptr [rdi+26h]
0x180002199  shr     ax, cl
0x18000219c  test    r9b, al
0x18000219f  jz      short loc_1800021AE
0x1800021a1  inc     bx
0x1800021a4  movzx   eax, r9w
0x1800021a8  mov     [rsp+190h+var_118], ebx
0x1800021ac  jmp     short loc_1800021B6
0x1800021ae  cmp     r8, 0Eh
0x1800021b2  jnb     short loc_1800021C1
0x1800021b4  mov     eax, esi
0x1800021b6  mov     [rbp+r8+90h+var_60], ax
0x1800021bc  inc     dx
0x1800021bf  jmp     short loc_180002185
0x1800021c1  call    __report_rangecheckfailure
0x1800021c7  mov     r8d, esi
0x1800021ca  movzx   edx, word ptr [rdi+28h]
0x1800021ce  movzx   ecx, r8w
0x1800021d2  shr     dx, cl
0x1800021d5  movzx   eax, r8w
0x1800021d9  and     dx, r9w
0x1800021dd  inc     r8w
0x1800021e1  mov     [rbp+rax*2+90h+var_C8], dx
0x1800021e6  cmp     r8w, 0Ch
0x1800021eb  jb      short loc_1800021CA
0x1800021ed  movzx   r8d, word ptr [rdi+6]
0x1800021f2  mov     r12d, esi
0x1800021f5  movzx   r15d, word ptr [rdi+4]
0x1800021fa  mov     [rsp+190h+var_140], r8d
0x1800021ff  mov     [rsp+190h+var_134], r15d
0x180002204  movzx   eax, r12w
0x180002208  movzx   r13d, r12w
0x18000220c  lea     edx, [rax+0Ch]
0x18000220f  cmp     eax, edx
0x180002211  jnb     short loc_18000225C
0x180002213  movzx   eax, r8w
0x180002217  cmp     word ptr [rbp+rax*2+90h+var_D0+6], 0
0x18000221d  jnz     short loc_180002252
0x18000221f  inc     r13w
0x180002223  lea     ecx, [r8+1]
0x180002227  cmp     cx, 0Ch
0x18000222b  mov     eax, 0FFF5h
0x180002230  cmovbe  ax, r9w
0x180002235  add     r8w, ax
0x180002239  lea     eax, [r15+1]
0x18000223d  cmp     cx, 0Ch
0x180002241  cmovbe  ax, r15w
0x180002246  movzx   r15d, ax
0x18000224a  movzx   eax, r13w
0x18000224e  cmp     eax, edx
0x180002250  jb      short loc_180002213
0x180002252  mov     [rsp+190h+var_134], r15d
0x180002257  mov     [rsp+190h+var_140], r8d
0x18000225c  lea     rdx, [rsp+190h+var_128]; lpFileTime
0x180002261  mov     [rbp+90h+SystemTime.wMonth], r8w
0x180002266  lea     rcx, [rbp+90h+SystemTime]; lpSystemTime
0x18000226a  mov     [rbp+90h+SystemTime.wDay], r9w
0x18000226f  mov     [rbp+90h+SystemTime.wYear], r15w
0x180002274  call    cs:__imp_SystemTimeToFileTime
0x18000227a  lea     rdx, [rbp+90h+SystemTime]; lpSystemTime
0x18000227e  lea     rcx, [rsp+190h+var_128]; lpFileTime
0x180002283  call    cs:__imp_FileTimeToSystemTime
0x180002289  mov     edx, [rsp+190h+var_13C]
0x18000228d  movzx   r8d, bx
0x180002291  mov     [rsp+190h+var_120], r8d
0x180002296  cmp     si, 7
0x18000229a  jnb     loc_18000236D
0x1800022a0  movzx   ecx, [rbp+90h+SystemTime.wDayOfWeek]
0x1800022a4  lea     r15d, [rsi+1]
0x1800022a8  add     cx, si
0x1800022ab  cmp     cx, 7
0x1800022af  lea     eax, [rcx-7]
0x1800022b2  cmovb   ax, cx
0x1800022b6  movzx   r14d, ax
0x1800022ba  cmp     [rbp+r14*2+90h+var_60], 0
0x1800022c1  jz      loc_180002352
0x1800022c7  movzx   edx, word ptr [rsp+190h+var_134]; unsigned __int16
0x1800022cc  mov     eax, 0FFFFh
0x1800022d1  movzx   ecx, word ptr [rsp+190h+var_140]; unsigned __int16
0x1800022d6  add     r8w, ax
0x1800022da  movzx   eax, word ptr [rdi+24h]
0x1800022de  imul    ebx, eax, 7
0x1800022e1  mov     [rsp+190h+var_120], r8d
0x1800022e6  lea     r8, [rsp+190h+var_138]; unsigned __int16 *
0x1800022eb  sub     bx, 7
0x1800022ef  add     bx, r15w
0x1800022f3  call    ?MonthDays@@YAJGGPEAG@Z; MonthDays(ushort,ushort,ushort *)
0x1800022f8  cmp     bx, [rsp+190h+var_138]
0x1800022fd  lea     eax, [rbx-7]
0x180002300  cmova   bx, ax
0x180002304  movzx   eax, r14w
0x180002308  mov     [rsp+190h+var_130], eax
0x18000230c  movzx   edx, bx
0x18000230f  mov     [rsp+190h+var_13C], edx
0x180002313  test    r13w, r13w
0x180002317  jnz     short loc_180002368
0x180002319  mov     [rsp+190h+var_130], eax
0x18000231d  cmp     bx, [rdi+8]
0x180002321  jnb     short loc_180002368
0x180002323  mov     r8d, [rsp+190h+var_120]
0x180002328  test    r8w, r8w
0x18000232c  jnz     short loc_18000235A
0x18000232e  mov     r8d, [rsp+190h+var_140]
0x180002333  inc     r12w
0x180002337  mov     r15d, [rsp+190h+var_134]
0x18000233c  xor     esi, esi
0x18000233e  mov     ebx, [rsp+190h+var_118]
0x180002342  mov     r9d, 1
0x180002348  mov     [rsp+190h+var_130], r14d
0x18000234d  jmp     loc_180002204
0x180002352  movzx   edx, r15w
0x180002356  mov     [rsp+190h+var_13C], edx
0x18000235a  movzx   esi, r15w
0x18000235e  mov     [rsp+190h+var_130], r14d
0x180002363  jmp     loc_180002296
0x180002368  mov     r14d, [rsp+190h+var_130]
0x18000236d  mov     rbx, qword ptr [rsp+190h+var_128.dwLowDateTime]
0x180002372  lea     eax, [rsi+1]
0x180002375  mov     r13d, [rsp+190h+var_140]
0x18000237a  mov     [rsp+190h+var_11C], eax
0x18000237e  jmp     loc_1800025E1
0x180002383  mov     r9d, [rdi+24h]
0x180002387  test    r9d, r9d
0x18000238a  jz      loc_180002B6C
0x180002390  mov     r12d, esi
0x180002393  mov     r8d, esi
0x180002396  movzx   ecx, r8b
0x18000239a  movzx   eax, r8w
0x18000239e  mov     edx, r9d
0x1800023a1  inc     r8w
0x1800023a5  shr     edx, cl
0x1800023a7  and     dx, 1
0x1800023ab  mov     [rbp+rax*2+90h+var_B0], dx
0x1800023b0  cmp     r8w, 1Fh
0x1800023b5  jb      short loc_180002396
0x1800023b7  mov     r8d, esi
0x1800023ba  movzx   edx, word ptr [rdi+28h]
0x1800023be  movzx   ecx, r8w
0x1800023c2  shr     dx, cl
0x1800023c5  movzx   eax, r8w
0x1800023c9  and     dx, 1
0x1800023cd  inc     r8w
0x1800023d1  mov     [rbp+rax*2+90h+var_C8], dx
0x1800023d6  cmp     r8w, 0Ch
0x1800023db  jb      short loc_1800023BA
  ... truncated ...
```
