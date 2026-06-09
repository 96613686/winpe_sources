# TakeLSActions(StateInfo *)

- ea: `0x1800118c0`
- end: `0x1800120e8`
- name: `?TakeLSActions@@YAXPEAUStateInfo@@@Z`
- size: `2088`
- prototype: `void __fastcall(struct StateInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011120`

## callees

- `0x180003ac0`
- `0x1800092a0`
- `0x18000a7e0`
- `0x1800118c0`
- `0x180018138`
- `0x18001d9a0`
- `0x1800294f0`
- `0x180029fa0`
- `0x180029ff0`
- `0x18002c8c8`
- `0x18003d270`
- `0x18003dd2c`
- `0x18004f97c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011901`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011a8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011aa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011f50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012088`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800120c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011901`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011a8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011aa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180011f50`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012088`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800120c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180011ca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180011fb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180011ca6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180011fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011994`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011994`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a25`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800119dc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800119dc`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180011cc7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180011cc7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800119ff`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800119ff`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800119aa`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800119aa`

## string_xrefs

- `0x180012098`: `Ignoring*leap*Second at EOD indicated by Provider LI. There is no matching local leap second configured.\n Provider:%s LI:%d FirstSeenAtTicks:%I64u CurrentTicks:%I64u\n`
- `0x1800120d0`: `Ignoring*leap*Second at EOD indicated by one of the providers. There is no matching local leap second configured.\nCurrentTicks:%I64u\n`

## pseudocode

```c
void __fastcall TakeLSActions(struct StateInfo *a1)
{
  __int64 v1; // r13
  ULONGLONG TickCount64; // rsi
  unsigned int v4; // r12d
  unsigned int v5; // eax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r14
  __int64 v8; // rdx
  unsigned __int64 v9; // rdi
  FILETIME v10; // rax
  signed int v11; // ecx
  signed int LastError; // eax
  int v13; // edx
  int v14; // r8d
  ULONGLONG v15; // rax
  ULONGLONG v16; // rax
  unsigned __int64 v17; // rax
  int v18; // edi
  int v19; // r13d
  struct TimeProvider *v20; // rdi
  int v21; // ecx
  __int64 i; // r9
  __int64 v23; // r10
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rcx
  int v26; // edx
  __int64 *v27; // r14
  const unsigned __int16 *v28; // rax
  const wchar_t *v29; // r9
  int v30; // r14d
  ULONGLONG v31; // rax
  const wchar_t *v32; // r9
  ULONGLONG v33; // rax
  ULONGLONG v34; // rax
  unsigned __int16 *v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v37; // [rsp+28h] [rbp-D8h]
  __int64 v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+30h] [rbp-D0h]
  __int64 v40; // [rsp+30h] [rbp-D0h]
  struct TimeProvider *v41; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME FileTime[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME v45; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v46; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v47[78]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v49[78]; // [rsp+D2h] [rbp-2Eh] BYREF

  v1 = *((_QWORD *)a1 + 129);
  v42 = 0;
  *(_QWORD *)&v45.wYear = 0;
  v41 = (struct TimeProvider *)v1;
  TickCount64 = GetTickCount64();
  if ( TickCount64 < *((_QWORD *)a1 + 539) + 300000LL )
    return;
  v4 = *((_DWORD *)a1 + 1076);
  EnterCriticalSection(&stru_1800A4610);
  v5 = dword_1800A5284;
  v6 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  if ( (unsigned int)v6 < dword_1800A5278 )
    v5 = ++dword_1800A5284;
  dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  v7 = (unsigned int)v6 + ((unsigned __int64)v5 << 32);
  LeaveCriticalSection(&stru_1800A4610);
  FileTime[0] = 0;
  GetSystemTimePreciseAsFileTime(FileTime, v8);
  v9 = FileTime[0].dwLowDateTime + ((unsigned __int64)FileTime[0].dwHighDateTime << 32);
  FileTime[0] = (FILETIME)v9;
  SystemTime = 0;
  if ( FileTimeToSystemTime(FileTime, &SystemTime) )
  {
    *(_QWORD *)&SystemTime.wHour = 23;
    if ( SystemTimeToFileTime(&SystemTime, FileTime) )
    {
      v10 = FileTime[0];
      v11 = 0;
LABEL_7:
      v9 = *(_QWORD *)&v10 + 35990000000LL;
      goto LABEL_11;
    }
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  v10 = 0;
  if ( v11 >= 0 )
    goto LABEL_7;
LABEL_11:
  if ( v11 >= 0 )
    v11 = 0;
  if ( v11 < 0 )
  {
    *((_DWORD *)a1 + 1076) = 0;
    *((_DWORD *)a1 + 1054) = 0;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    if ( *((_DWORD *)a1 + 1056) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 1060); i = (unsigned int)(i + 1) )
      {
        v23 = *((_QWORD *)a1 + 529) + 40 * i;
        if ( v9 == *(_QWORD *)v23 )
        {
          v14 = *(_DWORD *)(v23 + 24);
          v13 = 1;
          break;
        }
      }
    }
    if ( *((_DWORD *)a1 + 1076) )
    {
      if ( v13 )
      {
        *((_DWORD *)a1 + 1054) = (v14 != 0) + 1;
        *((_DWORD *)a1 + 1076) = 2;
        if ( (unsigned int)ProviderIndicatedConsistenLs((struct TimeProvider *)v1) )
          *((_DWORD *)a1 + 1076) = 3;
      }
      else
      {
        *((_DWORD *)a1 + 1076) = 1;
        *((_DWORD *)a1 + 1054) = 0;
        if ( v1 )
        {
          v15 = GetTickCount64();
          if ( (unsigned int)(*(_DWORD *)(v1 + 104) - 1) > 1 || v15 - *(_QWORD *)(v1 + 112) - 3600001 > 0x4EF6D7E )
          {
            v16 = GetTickCount64();
            if ( (unsigned int)(*(_DWORD *)(v1 + 104) - 1) <= 1 && v16 - *(_QWORD *)(v1 + 112) - 900001 <= 0x518A05E )
              *((_DWORD *)a1 + 1076) = 4;
          }
          else if ( (unsigned int)ProviderIndicatedConsistenLs((struct TimeProvider *)v1) )
          {
            *((_DWORD *)a1 + 1076) = 5;
          }
        }
      }
    }
  }
  if ( *((_DWORD *)a1 + 1076) )
  {
    v17 = *((_QWORD *)a1 + 539);
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(18) )
      FileLogAdd(
        L"Leap second state is inconsistent between settings and the runtime. Verify the data with w32tm.exe /leapseconds "
         "/getstatus /verbose\n");
    *((_QWORD *)a1 + 539) = v7;
    v17 = v7;
  }
  v18 = *((_DWORD *)a1 + 1076);
  if ( v4 == v18 )
  {
    v7 = v17;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(18) )
      FileLogAdd(L"eLSState State changed. Old State:%d. New State:%d\n", v4, *((unsigned int *)a1 + 1076));
    *((_QWORD *)a1 + 539) = v7;
    v18 = *((_DWORD *)a1 + 1076);
  }
  v19 = *((_DWORD *)a1 + 1054);
  if ( TickCount64 <= v7 + 3600000 )
    goto LABEL_25;
  v48 = 0;
  memset_0(v49, 0, sizeof(v49));
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
  *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
  SystemTime = 0;
  if ( v18 == 3 )
  {
    if ( TickCount64 > v7 + 14400000 )
    {
      v27 = W32TIME_OPS_UPCOMING_LEAP_SECOND;
      goto LABEL_45;
    }
LABEL_25:
    v20 = v41;
    goto LABEL_26;
  }
  if ( v18 == 4 )
  {
    v27 = W32TIME_OPS_NEW_UPCOMING_LEAP_SECOND;
    goto LABEL_45;
  }
  if ( v18 != 2 )
    goto LABEL_25;
  v27 = W32TIME_OPS_NO_UPCOMING_LEAP_SECOND;
LABEL_45:
  GetSystemTime((LPSYSTEMTIME)FileTime);
  FileTime[1] = (FILETIME)23LL;
  SystemTimeToTzSpecificLocalTime(0, (const SYSTEMTIME *)FileTime, &SystemTime);
  StringCchPrintfW(
    &v48,
    0x28u,
    L"%04u-%02u-%02uT%02u:59:59",
    LOWORD(FileTime[0].dwLowDateTime),
    HIWORD(FileTime[0].dwLowDateTime),
    HIWORD(FileTime[0].dwHighDateTime),
    LOWORD(FileTime[1].dwLowDateTime));
  LODWORD(v40) = SystemTime.wHour;
  LODWORD(v38) = SystemTime.wDay;
  LODWORD(v36) = SystemTime.wMonth;
  StringCchPrintfW(&v46, 0x28u, L"%04u-%02u-%02uT%02u:59:59", SystemTime.wYear, v36, v38, v40);
  v20 = v41;
  if ( v41 )
    v28 = (const unsigned __int16 *)*((_QWORD *)v41 + 1);
  else
    v28 = &qword_180071478;
  HIDWORD(v39) = HIDWORD(v28);
  v29 = L"subtracted";
  v37 = &v46;
  if ( v19 != 2 )
    v29 = L"added";
  v35 = &v48;
  LogEvent(&_W32TimeRegistrationHandle, v27, L"SSSSi", v29);
  *((_QWORD *)a1 + 539) = TickCount64;
LABEL_26:
  v21 = *((_DWORD *)a1 + 1076);
  if ( ((v21 - 2) & 0xFFFFFFFC) == 0 && v21 != 3 )
  {
    AccurateGetSystemTime(&v42);
    v24 = v42;
    if ( (int)GetFTForEODKernelLSEntry((unsigned __int64 *)&v45.wYear, v42) >= 0 )
    {
      v25 = *(_QWORD *)&v45.wYear - v24;
      if ( (__int64)(*(_QWORD *)&v45.wYear - v24) >= 0 )
      {
        v26 = *((_DWORD *)a1 + 1076);
        if ( ((v26 - 2) & 0xFFFFFFFD) == 0 && v25 < 0x10C388D000LL )
        {
          if ( *((_DWORD *)a1 + 99) > (signed int)((unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 396) + 100LL)
                                                                + *(_DWORD *)(*((_QWORD *)a1 + 396) + 104LL)) >> 1) )
          {
            if ( (unsigned __int8)FileLogAllowEntry(136) )
              FileLogAdd(
                L"Leap Second Approaching. Poll interval changed [Poll: %d->%d]\n",
                *((unsigned int *)a1 + 99),
                *(unsigned int *)(*((_QWORD *)a1 + 396) + 100LL));
            *((_DWORD *)a1 + 99) = *(_DWORD *)(*((_QWORD *)a1 + 396) + 100LL);
            *((_BYTE *)a1 + 1064) = 1;
          }
LABEL_84:
          *((_QWORD *)a1 + 539) = TickCount64;
          return;
        }
        if ( v26 == 5 && v25 - 0x218711A01LL <= 0x649534DFELL )
        {
          if ( v20 )
          {
            if ( *((_DWORD *)a1 + 1053) )
            {
              v30 = AddLeapSecondAtEOD(v24, v19 == 2);
              if ( (unsigned __int8)FileLogAllowEntry(18) )
              {
                v31 = GetTickCount64();
                LODWORD(v37) = v30;
                FileLogAdd(
                  L"Adding a new*leap*second at EOD based on Provider LI. Provider:%s LI:%d FirstSeenAtTicks:%I64u Current"
                   "Ticks:%I64u Result:%0x%08X\n",
                  *((_QWORD *)v20 + 1),
                  *((unsigned int *)v20 + 26),
                  *((_QWORD *)v20 + 14),
                  v31,
                  v37);
              }
              v48 = 0;
              memset_0(v49, 0, sizeof(v49));
              v46 = 0;
              memset_0(v47, 0, sizeof(v47));
              v45 = 0;
              GetSystemTime(&v45);
              LODWORD(v39) = 23;
              LODWORD(v37) = v45.wDay;
              LODWORD(v35) = v45.wMonth;
              *(_QWORD *)&v45.wHour = 23;
              StringCchPrintfW(&v48, 0x28u, L"%04u-%02u-%02uT%02u:59:59", v45.wYear, v35, v37, v39);
              v32 = L"-";
              if ( v19 != 2 )
                v32 = L"+";
              StringCchPrintfW(&v46, 0x28u, L"%s%s", v32, &v48);
              LogEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_W32TIME_ADD_LEAP_SECOND, L"Sei", &v46);
              if ( v30 >= 0 && (int)ReadLeapSecondSettings((struct StateInfo *)((char *)a1 + 4208)) >= 0 )
                UpdateLsState((struct StateInfo *)((char *)a1 + 4208), v20);
            }
            else if ( (unsigned __int8)FileLogAllowEntry(18) )
            {
              v33 = GetTickCount64();
              FileLogAdd(
                L"Ignoring*leap*Second at EOD indicated by Provider LI. There is no matching local leap second configured."
                 "\n"
                 " Provider:%s LI:%d FirstSeenAtTicks:%I64u CurrentTicks:%I64u\n",
                *((_QWORD *)v20 + 1),
                *((unsigned int *)v20 + 26),
                *((_QWORD *)v20 + 14),
                v33);
            }
          }
          else if ( (unsigned __int8)FileLogAllowEntry(18) )
          {
            v34 = GetTickCount64();
            FileLogAdd(
              L"Ignoring*leap*Second at EOD indicated by one of the providers. There is no matching local leap second conf"
               "igured.\n"
               "CurrentTicks:%I64u\n",
              v34);
          }
          goto LABEL_84;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800118c0  mov     [rsp-8+arg_18], rbx
0x1800118c5  push    rbp
0x1800118c6  push    rsi
0x1800118c7  push    rdi
0x1800118c8  push    r13
0x1800118ca  push    r15
0x1800118cc  lea     rbp, [rsp-30h]
0x1800118d1  sub     rsp, 130h
0x1800118d8  mov     rax, cs:__security_cookie
0x1800118df  xor     rax, rsp
0x1800118e2  mov     [rbp+50h+var_30], rax
0x1800118e6  mov     r13, [rcx+408h]
0x1800118ed  xor     edi, edi
0x1800118ef  mov     [rsp+150h+var_108], rdi
0x1800118f4  mov     rbx, rcx
0x1800118f7  mov     qword ptr [rsp+150h+var_E0.wYear], rdi
0x1800118fc  mov     [rsp+150h+var_110], r13
0x180011901  call    cs:__imp_GetTickCount64
0x180011908  nop     dword ptr [rax+rax+00h]
0x18001190d  lea     r15, [rbx+1070h]
0x180011914  mov     rsi, rax
0x180011917  mov     rcx, [r15+68h]
0x18001191b  add     rcx, 493E0h
0x180011922  cmp     rax, rcx
0x180011925  jb      loc_180011B2D
0x18001192b  mov     [rsp+150h+arg_8], r12
0x180011933  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001193a  mov     r12d, [r15+60h]
0x18001193e  mov     [rsp+150h+arg_10], r14
0x180011946  call    cs:__imp_EnterCriticalSection
0x18001194d  nop     dword ptr [rax+rax+00h]
0x180011952  mov     eax, 7FFE0320h
0x180011957  mov     rax, [rax]
0x18001195a  mov     ecx, ds:7FFE0004h
0x180011961  imul    rcx, rax
0x180011965  mov     eax, cs:dword_1800A5284
0x18001196b  shr     rcx, 18h
0x18001196f  cmp     ecx, cs:dword_1800A5278
0x180011975  jb      loc_180011D56
0x18001197b  mov     r14d, eax
0x18001197e  mov     eax, ecx
0x180011980  mov     cs:dword_1800A5278, ecx
0x180011986  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001198d  shl     r14, 20h
0x180011991  add     r14, rax
0x180011994  call    cs:__imp_LeaveCriticalSection
0x18001199b  nop     dword ptr [rax+rax+00h]
0x1800119a0  lea     rcx, [rsp+150h+FileTime]
0x1800119a5  mov     qword ptr [rsp+150h+FileTime.dwLowDateTime], rdi
0x1800119aa  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800119b1  nop     dword ptr [rax+rax+00h]
0x1800119b6  mov     edi, [rsp+150h+FileTime.dwHighDateTime]
0x1800119ba  lea     rdx, [rsp+150h+SystemTime]; lpSystemTime
0x1800119bf  mov     eax, [rsp+150h+FileTime.dwLowDateTime]
0x1800119c3  lea     rcx, [rsp+150h+FileTime]; lpFileTime
0x1800119c8  xorps   xmm0, xmm0
0x1800119cb  shl     rdi, 20h
0x1800119cf  add     rdi, rax
0x1800119d2  mov     qword ptr [rsp+150h+FileTime.dwLowDateTime], rdi
0x1800119d7  movups  xmmword ptr [rsp+150h+SystemTime.wYear], xmm0
0x1800119dc  call    cs:__imp_FileTimeToSystemTime
0x1800119e3  nop     dword ptr [rax+rax+00h]
0x1800119e8  test    eax, eax
0x1800119ea  jz      short loc_180011A25
0x1800119ec  lea     rdx, [rsp+150h+FileTime]; lpFileTime
0x1800119f1  mov     qword ptr [rsp+150h+SystemTime.wHour], 17h
0x1800119fa  lea     rcx, [rsp+150h+SystemTime]; lpSystemTime
0x1800119ff  call    cs:__imp_SystemTimeToFileTime
0x180011a06  nop     dword ptr [rax+rax+00h]
0x180011a0b  test    eax, eax
0x180011a0d  jz      short loc_180011A25
0x180011a0f  mov     rax, qword ptr [rsp+150h+FileTime.dwLowDateTime]
0x180011a14  xor     ecx, ecx
0x180011a16  mov     rdi, 8612BD180h
0x180011a20  add     rdi, rax
0x180011a23  jmp     short loc_180011A46
0x180011a25  call    cs:__imp_GetLastError
0x180011a2c  nop     dword ptr [rax+rax+00h]
0x180011a31  mov     ecx, eax
0x180011a33  test    eax, eax
0x180011a35  jle     short loc_180011A40
0x180011a37  movzx   ecx, ax
0x180011a3a  or      ecx, 80070000h
0x180011a40  xor     eax, eax
0x180011a42  test    ecx, ecx
0x180011a44  jns     short loc_180011A16
0x180011a46  xor     eax, eax
0x180011a48  test    ecx, ecx
0x180011a4a  cmovns  ecx, eax
0x180011a4d  test    ecx, ecx
0x180011a4f  js      loc_180011D63
0x180011a55  xor     edx, edx
0x180011a57  xor     r8d, r8d
0x180011a5a  cmp     [rbx+1080h], eax
0x180011a60  jnz     loc_180011B51
0x180011a66  cmp     dword ptr [r15+60h], 0
0x180011a6b  jz      short loc_180011AC0
0x180011a6d  test    edx, edx
0x180011a6f  jnz     loc_180011DDA
0x180011a75  mov     dword ptr [rbx+10D0h], 1
0x180011a7f  mov     [rbx+1078h], edx
0x180011a85  test    r13, r13
0x180011a88  jz      short loc_180011AC0
0x180011a8a  call    cs:__imp_GetTickCount64
0x180011a91  nop     dword ptr [rax+rax+00h]
0x180011a96  mov     ecx, [r13+68h]
0x180011a9a  dec     ecx
0x180011a9c  cmp     ecx, 1
0x180011a9f  jbe     loc_180011D80
0x180011aa5  call    cs:__imp_GetTickCount64
0x180011aac  nop     dword ptr [rax+rax+00h]
0x180011ab1  mov     ecx, [r13+68h]
0x180011ab5  dec     ecx
0x180011ab7  cmp     ecx, 1
0x180011aba  jbe     loc_180011DB5
0x180011ac0  cmp     dword ptr [rbx+10D0h], 0
0x180011ac7  jz      loc_180011E13
0x180011acd  mov     rax, [rbx+10D8h]
0x180011ad4  mov     edi, [rbx+10D0h]
0x180011ada  cmp     r12d, edi
0x180011add  jnz     loc_180011E3C
0x180011ae3  mov     r14, rax
0x180011ae6  mov     r13d, [rbx+1078h]
0x180011aed  lea     rax, [r14+36EE80h]
0x180011af4  xor     r12d, r12d
0x180011af7  cmp     r13d, 2
0x180011afb  setz    r12b
0x180011aff  cmp     rsi, rax
0x180011b02  ja      loc_180011C41
0x180011b08  mov     rdi, [rsp+150h+var_110]
0x180011b0d  mov     ecx, [rbx+10D0h]
0x180011b13  lea     eax, [rcx-2]
0x180011b16  test    eax, 0FFFFFFFCh
0x180011b1b  jz      short loc_180011B7F
0x180011b1d  mov     r12, [rsp+150h+arg_8]
0x180011b25  mov     r14, [rsp+150h+arg_10]
0x180011b2d  mov     rcx, [rbp+50h+var_30]
0x180011b31  xor     rcx, rsp; StackCookie
0x180011b34  call    __security_check_cookie
0x180011b39  mov     rbx, [rsp+150h+arg_18]
0x180011b41  add     rsp, 130h
0x180011b48  pop     r15
0x180011b4a  pop     r13
0x180011b4c  pop     rdi
0x180011b4d  pop     rsi
0x180011b4e  pop     rbp
0x180011b4f  retn
0x180011b51  xor     r9d, r9d
0x180011b54  cmp     r9d, [rbx+1090h]
0x180011b5b  jnb     loc_180011A66
0x180011b61  mov     rax, [rbx+1088h]
0x180011b68  lea     rcx, [r9+r9*4]
0x180011b6c  cmp     rdi, [rax+rcx*8]
0x180011b70  lea     r10, [rax+rcx*8]
0x180011b74  jz      loc_180011D72
0x180011b7a  inc     r9d
0x180011b7d  jmp     short loc_180011B54
0x180011b7f  cmp     ecx, 3
0x180011b82  jz      short loc_180011B1D
0x180011b84  lea     rcx, [rsp+150h+var_108]; unsigned __int64 *
0x180011b89  call    ?AccurateGetSystemTime@@YAXPEA_K@Z; AccurateGetSystemTime(unsigned __int64 *)
0x180011b8e  mov     r14, [rsp+150h+var_108]
0x180011b93  lea     rcx, [rsp+150h+var_E0]; unsigned __int64 *
0x180011b98  mov     rdx, r14; unsigned __int64
0x180011b9b  call    ?GetFTForEODKernelLSEntry@@YAJPEA_K_K@Z; GetFTForEODKernelLSEntry(unsigned __int64 *,unsigned __int64)
0x180011ba0  test    eax, eax
0x180011ba2  js      loc_180011B1D
0x180011ba8  mov     rcx, qword ptr [rsp+150h+var_E0.wYear]
0x180011bad  sub     rcx, r14
0x180011bb0  js      loc_180011B1D
0x180011bb6  mov     edx, [rbx+10D0h]
0x180011bbc  lea     eax, [rdx-2]
0x180011bbf  test    eax, 0FFFFFFFDh
0x180011bc4  jnz     loc_180011EF5
0x180011bca  mov     rax, 10C388D000h
0x180011bd4  cmp     rcx, rax
0x180011bd7  jnb     loc_180011EF5
0x180011bdd  mov     rax, [rbx+0C60h]
0x180011be4  mov     ecx, [rax+68h]
0x180011be7  add     ecx, [rax+64h]
0x180011bea  mov     eax, [rbx+18Ch]
0x180011bf0  shr     ecx, 1
0x180011bf2  cmp     eax, ecx
0x180011bf4  jle     loc_1800120DC
0x180011bfa  mov     ecx, 88h
0x180011bff  call    FileLogAllowEntry
0x180011c04  test    al, al
0x180011c06  jz      short loc_180011C25
0x180011c08  mov     rax, [rbx+0C60h]
0x180011c0f  lea     rcx, aLeapSecondAppr; "Leap Second Approaching. Poll interval "...
0x180011c16  mov     edx, [rbx+18Ch]
0x180011c1c  mov     r8d, [rax+64h]
0x180011c20  call    FileLogAdd
0x180011c25  mov     rax, [rbx+0C60h]
0x180011c2c  mov     ecx, [rax+64h]
0x180011c2f  mov     [rbx+18Ch], ecx
0x180011c35  mov     byte ptr [rbx+428h], 1
0x180011c3c  jmp     loc_1800120DC
0x180011c41  xor     eax, eax
0x180011c43  lea     rcx, [rbp+50h+var_7E]; void *
0x180011c47  xor     edx, edx; Val
0x180011c49  mov     [rbp+50h+var_80], ax
0x180011c4d  mov     r8d, 4Eh ; 'N'; Size
0x180011c53  call    memset_0
0x180011c58  xor     eax, eax
0x180011c5a  lea     rcx, [rbp+50h+var_CE]; void *
0x180011c5e  xor     edx, edx; Val
0x180011c60  mov     [rbp+50h+var_D0], ax
0x180011c64  mov     r8d, 4Eh ; 'N'; Size
0x180011c6a  call    memset_0
0x180011c6f  xorps   xmm0, xmm0
0x180011c72  xorps   xmm1, xmm1
0x180011c75  movups  xmmword ptr [rsp+150h+FileTime.dwLowDateTime], xmm0
0x180011c7a  movups  xmmword ptr [rsp+150h+SystemTime.wYear], xmm1
0x180011c7f  cmp     edi, 3
0x180011c82  jz      loc_180011E72
0x180011c88  cmp     edi, 4
0x180011c8b  jz      loc_180011E8E
0x180011c91  cmp     edi, 2
0x180011c94  jnz     loc_180011B08
0x180011c9a  lea     r14, W32TIME_OPS_NO_UPCOMING_LEAP_SECOND
0x180011ca1  lea     rcx, [rsp+150h+FileTime]; lpSystemTime
0x180011ca6  call    cs:__imp_GetSystemTime
0x180011cad  nop     dword ptr [rax+rax+00h]
0x180011cb2  lea     r8, [rsp+150h+SystemTime]; lpLocalTime
0x180011cb7  mov     qword ptr [rsp+150h+FileTime.dwLowDateTime+8], 17h
0x180011cc0  lea     rdx, [rsp+150h+FileTime]; lpUniversalTime
0x180011cc5  xor     ecx, ecx; lpTimeZoneInformation
0x180011cc7  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180011cce  nop     dword ptr [rax+rax+00h]
0x180011cd3  movzx   ecx, word ptr [rsp+150h+FileTime.dwHighDateTime+2]
0x180011cd8  lea     r8, a04u02u02ut02u5; "%04u-%02u-%02uT%02u:59:59"
0x180011cdf  movzx   edx, word ptr [rsp+150h+FileTime.dwLowDateTime+2]
0x180011ce4  movzx   eax, word ptr [rsp+150h+FileTime.dwLowDateTime+8]
0x180011ce9  movzx   r9d, word ptr [rsp+150h+FileTime.dwLowDateTime]
0x180011cef  mov     dword ptr [rsp+150h+var_120], eax
0x180011cf3  mov     dword ptr [rsp+150h+var_128], ecx
0x180011cf7  lea     rcx, [rbp+50h+var_80]; unsigned __int16 *
0x180011cfb  mov     dword ptr [rsp+150h+var_130], edx
0x180011cff  mov     edx, 28h ; '('; unsigned __int64
0x180011d04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011d09  movzx   ecx, [rsp+150h+SystemTime.wDay]
0x180011d0e  lea     r8, a04u02u02ut02u5; "%04u-%02u-%02uT%02u:59:59"
0x180011d15  movzx   edx, [rsp+150h+SystemTime.wMonth]
0x180011d1a  movzx   eax, [rsp+150h+SystemTime.wHour]
0x180011d1f  movzx   r9d, [rsp+150h+SystemTime.wYear]
0x180011d25  mov     dword ptr [rsp+150h+var_120], eax
0x180011d29  mov     dword ptr [rsp+150h+var_128], ecx
0x180011d2d  lea     rcx, [rbp+50h+var_D0]; unsigned __int16 *
0x180011d31  mov     dword ptr [rsp+150h+var_130], edx
0x180011d35  mov     edx, 28h ; '('; unsigned __int64
0x180011d3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011d3f  mov     rdi, [rsp+150h+var_110]
0x180011d44  test    rdi, rdi
0x180011d47  jz      loc_180011E9A
0x180011d4d  mov     rax, [rdi+8]
0x180011d51  jmp     loc_180011EA1
0x180011d56  inc     eax
0x180011d58  mov     cs:dword_1800A5284, eax
0x180011d5e  jmp     loc_18001197B
0x180011d63  mov     [r15+60h], eax
0x180011d67  mov     [rbx+1078h], eax
0x180011d6d  jmp     loc_180011AC0
0x180011d72  mov     r8d, [r10+18h]
0x180011d76  mov     edx, 1
0x180011d7b  jmp     loc_180011A66
0x180011d80  sub     rax, [r13+70h]
0x180011d84  sub     rax, 36EE81h
0x180011d8a  cmp     rax, 4EF6D7Eh
0x180011d90  ja      loc_180011AA5
0x180011d96  mov     rcx, r13; struct TimeProvider *
0x180011d99  call    ?ProviderIndicatedConsistenLs@@YAHPEAUTimeProvider@@@Z; ProviderIndicatedConsistenLs(TimeProvider *)
0x180011d9e  test    eax, eax
0x180011da0  jz      loc_180011AC0
0x180011da6  mov     dword ptr [rbx+10D0h], 5
0x180011db0  jmp     loc_180011AC0
0x180011db5  sub     rax, [r13+70h]
0x180011db9  sub     rax, 0DBBA1h
0x180011dbf  cmp     rax, 518A05Eh
0x180011dc5  ja      loc_180011AC0
0x180011dcb  mov     dword ptr [rbx+10D0h], 4
0x180011dd5  jmp     loc_180011AC0
0x180011dda  xor     eax, eax
0x180011ddc  mov     rcx, r13; struct TimeProvider *
0x180011ddf  test    r8d, r8d
0x180011de2  setnz   al
0x180011de5  inc     eax
0x180011de7  mov     [rbx+1078h], eax
0x180011ded  mov     dword ptr [rbx+10D0h], 2
0x180011df7  call    ?ProviderIndicatedConsistenLs@@YAHPEAUTimeProvider@@@Z; ProviderIndicatedConsistenLs(TimeProvider *)
0x180011dfc  test    eax, eax
0x180011dfe  jz      loc_180011AC0
0x180011e04  mov     dword ptr [rbx+10D0h], 3
0x180011e0e  jmp     loc_180011AC0
0x180011e13  mov     ecx, 12h
0x180011e18  call    FileLogAllowEntry
0x180011e1d  test    al, al
0x180011e1f  jz      short loc_180011E2D
0x180011e21  lea     rcx, aLeapSecondStat; "Leap second state is inconsistent betwe"...
0x180011e28  call    FileLogAdd
  ... truncated ...
```
