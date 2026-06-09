# ClockDisciplineThread(void *)

- ea: `0x18001da40`
- end: `0x18001fcad`
- name: `?ClockDisciplineThread@@YAKPEAX@Z`
- size: `8813`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a7e0`
- `0x18000bde0`
- `0x18000bff4`
- `0x18000e758`
- `0x1800127a0`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x18001da40`
- `0x18001fcc0`
- `0x1800274e0`
- `0x180029930`
- `0x180029f50`
- `0x180029fa0`
- `0x18002a0b0`
- `0x18002a3b4`
- `0x18002a6e0`
- `0x18002aa44`
- `0x18002aed4`
- `0x18002cfb8`
- `0x18002d620`
- `0x18003d270`
- `0x18003dce4`
- `0x18003dcf0`
- `0x18003dd08`
- `0x18003dd20`
- `0x18004b9ac`
- `0x18004ba04`
- `0x18004bac4`
- `0x18004bdc0`
- `0x18004c018`
- `0x18004f8fc`
- `0x180063f44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001dace`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001fc37`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001dace`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001fc37`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e16c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e16c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001df41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fb60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbeb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001df41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fb60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fbeb`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001f2ad`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001f2ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f77e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbff`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001de8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001de8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001de76`
- `ntdll!NtSetSystemInformation` at `0x18001f8c9`
- `ntdll!NtSetSystemInformation` at `0x18001f8c9`
- `ntdll!NtQuerySystemInformation` at `0x18001f833`
- `ntdll!NtQuerySystemInformation` at `0x18001f833`

## string_xrefs

- `0x18001ded0`: `ClockDisciplineThread: Starting:`
- `0x18001e13c`: `ClockDispln: we're a reliable time service with no time source: LS: %I64d, %TN: %I64d, WAIT: %d\n`
- `0x18001e1c3`: `ClockDisciplineThread: hShutDownEvent signaled. Exiting.\n`
- `0x18001e272`: `ClockDisciplineThread: ParamChange. Reloading constants.\n`
- `0x18001e6b5`: `ClockDispln Update:`
- `0x18001fb4d`: `Service was started as a task.  Synchronization complete, shutting down now.\n`
- `0x18001e23b`: `Service is shutting down, but no time adjustment occured.\n`

## pseudocode

```c
__int64 __fastcall ClockDisciplineThread(PVOID Parameter)
{
  unsigned int i; // ecx
  char v2; // r15
  __int64 v3; // rcx
  __int64 v4; // r8
  const wchar_t *v5; // rdx
  const wchar_t *v6; // r10
  __int64 v7; // r9
  unsigned __int16 *v8; // rax
  __int64 v9; // r11
  wchar_t v10; // bx
  __int64 v11; // r8
  const wchar_t *v12; // r10
  __int64 v13; // r9
  wchar_t *v14; // rax
  __int64 v15; // r11
  wchar_t v16; // bx
  __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // r9
  wchar_t v20; // r10
  int Priveleges; // r12d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v24; // eax
  unsigned __int32 v25; // xmm13_4
  char v26; // di
  __int64 v27; // rax
  unsigned int v28; // ecx
  unsigned __int64 v29; // rbx
  DWORD v30; // r13d
  int v31; // eax
  unsigned __int64 v32; // rbx
  DWORD v33; // r14d
  signed int v34; // eax
  int v35; // eax
  __m128i v36; // xmm6
  __int64 v37; // rbx
  unsigned __int64 v38; // rsi
  double v39; // xmm1_8
  double v40; // xmm0_8
  double v41; // xmm1_8
  double v42; // xmm6_8
  double v43; // xmm0_8
  __int64 v44; // rbx
  __int64 Value; // rax
  char v46; // di
  char v47; // r13
  char v48; // bl
  unsigned __int64 v49; // r15
  __int64 v50; // r12
  __int64 v51; // r12
  __int64 v52; // r14
  char v53; // si
  __int64 v54; // rax
  const wchar_t *v55; // rcx
  char v56; // al
  __int64 v57; // rdx
  unsigned int j; // ecx
  double v59; // xmm0_8
  unsigned __int64 v60; // rax
  __int64 v61; // rbx
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rax
  int v65; // r10d
  __int64 v66; // r9
  WCHAR *v67; // rax
  int v68; // ecx
  int v69; // edx
  double v70; // xmm0_8
  int v71; // ecx
  int v72; // ebx
  int v73; // eax
  __int64 v74; // rax
  BOOL v75; // ebx
  bool v76; // al
  __int64 v77; // r15
  unsigned int v78; // r12d
  double v79; // xmm1_8
  unsigned __int64 v80; // rax
  double v81; // xmm0_8
  __int64 v82; // r14
  __int64 v83; // rbx
  float v84; // xmm1_4
  __int64 v85; // rdi
  __int64 v86; // rsi
  __int64 v87; // rcx
  __int64 v88; // rbx
  __int64 v89; // rax
  __int64 v90; // rsi
  int v91; // ecx
  __int64 v92; // rbx
  float v93; // xmm6_4
  unsigned __int64 v94; // rax
  __int64 v95; // rcx
  int v96; // r12d
  __int64 v97; // r13
  unsigned __int64 v98; // r15
  bool v99; // cc
  __int64 v100; // rdi
  unsigned __int64 v101; // rcx
  unsigned int v102; // eax
  unsigned __int64 v103; // r14
  NTSTATUS v104; // eax
  int v105; // eax
  __int64 v106; // rdi
  NTSTATUS v107; // eax
  int v108; // eax
  float v109; // xmm2_4
  int v110; // ecx
  int v111; // ecx
  float v112; // xmm1_4
  float v113; // xmm0_4
  float v114; // xmm0_4
  unsigned __int64 v115; // rax
  unsigned __int64 v116; // rdx
  float v117; // xmm0_4
  float v118; // xmm0_4
  unsigned __int64 v119; // rcx
  signed int v120; // eax
  signed int v121; // eax
  BOOL bAlertable[2]; // [rsp+20h] [rbp-398h]
  unsigned __int64 v124; // [rsp+28h] [rbp-390h]
  unsigned int v125; // [rsp+30h] [rbp-388h]
  bool v126; // [rsp+51h] [rbp-367h]
  char v127; // [rsp+59h] [rbp-35Fh]
  char v128; // [rsp+5Bh] [rbp-35Dh]
  char v129; // [rsp+5Ch] [rbp-35Ch]
  DWORD v130; // [rsp+60h] [rbp-358h]
  __int64 v131; // [rsp+60h] [rbp-358h]
  int v132; // [rsp+60h] [rbp-358h]
  DWORD v133; // [rsp+68h] [rbp-350h]
  char v134; // [rsp+78h] [rbp-340h]
  int v135; // [rsp+78h] [rbp-340h]
  unsigned __int64 v136; // [rsp+80h] [rbp-338h] BYREF
  __int64 v137; // [rsp+88h] [rbp-330h]
  __int64 v138; // [rsp+90h] [rbp-328h]
  int v139; // [rsp+98h] [rbp-320h] BYREF
  unsigned int v140; // [rsp+9Ch] [rbp-31Ch]
  int v141; // [rsp+A0h] [rbp-318h]
  unsigned __int64 v142; // [rsp+A8h] [rbp-310h] BYREF
  __int64 v143; // [rsp+B0h] [rbp-308h]
  __int64 v144; // [rsp+B8h] [rbp-300h]
  __int64 v145; // [rsp+C0h] [rbp-2F8h]
  int v146; // [rsp+C8h] [rbp-2F0h]
  unsigned __int64 v147; // [rsp+D0h] [rbp-2E8h] BYREF
  unsigned __int64 v148; // [rsp+D8h] [rbp-2E0h] BYREF
  unsigned __int16 *v149; // [rsp+E0h] [rbp-2D8h]
  __int64 v150; // [rsp+E8h] [rbp-2D0h]
  wchar_t *v151; // [rsp+F0h] [rbp-2C8h]
  __int64 v152; // [rsp+F8h] [rbp-2C0h]
  unsigned __int16 *v153; // [rsp+100h] [rbp-2B8h]
  __int64 v154; // [rsp+108h] [rbp-2B0h]
  unsigned __int64 v155; // [rsp+110h] [rbp-2A8h]
  unsigned __int64 v156; // [rsp+118h] [rbp-2A0h]
  __int128 v157; // [rsp+120h] [rbp-298h] BYREF
  __int128 v158; // [rsp+130h] [rbp-288h]
  __int128 v159; // [rsp+140h] [rbp-278h]
  __int128 v160; // [rsp+150h] [rbp-268h]
  __m128i v161; // [rsp+160h] [rbp-258h]
  __int128 v162; // [rsp+170h] [rbp-248h]
  __m128i v163; // [rsp+180h] [rbp-238h]
  __int128 v164; // [rsp+190h] [rbp-228h]
  __int128 v165; // [rsp+1A0h] [rbp-218h]
  __int128 v166; // [rsp+1B0h] [rbp-208h]
  __int128 v167; // [rsp+1C0h] [rbp-1F8h]
  __int128 v168; // [rsp+1D0h] [rbp-1E8h]
  __int64 v169; // [rsp+1E0h] [rbp-1D8h]
  __int64 v170; // [rsp+1F0h] [rbp-1C8h]
  __int64 v171; // [rsp+1F8h] [rbp-1C0h]
  const wchar_t *v172; // [rsp+200h] [rbp-1B8h]
  __int64 v173; // [rsp+208h] [rbp-1B0h]
  __int64 v174; // [rsp+210h] [rbp-1A8h]
  const wchar_t *v175; // [rsp+218h] [rbp-1A0h]
  __int64 v176; // [rsp+220h] [rbp-198h]
  __int64 v177; // [rsp+228h] [rbp-190h]
  __int64 v178; // [rsp+230h] [rbp-188h]
  const wchar_t *v179; // [rsp+238h] [rbp-180h]
  __int64 v180; // [rsp+240h] [rbp-178h]
  __int64 v181; // [rsp+248h] [rbp-170h]
  HANDLE Handles[2]; // [rsp+250h] [rbp-168h] BYREF
  unsigned __int64 v183; // [rsp+260h] [rbp-158h]
  __int64 v184; // [rsp+268h] [rbp-150h]
  unsigned __int64 v185; // [rsp+270h] [rbp-148h]
  __int64 v186; // [rsp+278h] [rbp-140h]
  __int128 SystemInformation; // [rsp+2B8h] [rbp-100h] BYREF
  __int64 v188; // [rsp+2C8h] [rbp-F0h]

  Handles[0] = hEvent;
  Handles[1] = qword_1800A36D0;
  v180 = _set_se_translator(SeTransFunc);
  AccurateGetInterruptCount(&qword_1800A3CD8);
  AccurateGetInterruptCount(&qword_1800A3CE0);
  qword_1800A3CD0 = 0;
  dword_1800A3820 = 0;
  qword_1800A3824 = 0;
  xmmword_1800A3E98 = 0u;
  dword_1800A3E8C = 0;
  dword_1800A3E94 = 0;
  dword_1800A3E90 = 0;
  *(_DWORD *)&Data = *((_DWORD *)qword_1800A42F0 + 4);
  qword_1800A3CF0 = *((_QWORD *)qword_1800A42F0 + 4);
  dword_1800A3EB4 = 0;
  for ( i = 0; i < 4; ++i )
    *((_QWORD *)&g_state + i + 261) = 0;
  dword_1800A3ED8 = 0;
  dword_1800A3EDC = 0;
  v2 = 0;
  v127 = 0;
  v3 = 2147483646;
  v4 = 2147483646;
  v171 = 2147483646;
  v5 = L"Local CMOS Clock";
  v6 = L"Local CMOS Clock";
  v179 = L"Local CMOS Clock";
  v7 = 256;
  v170 = 256;
  v8 = &qword_1800A3AC8;
  v149 = &qword_1800A3AC8;
  v9 = 0;
  v150 = 0;
  while ( v7 )
  {
    if ( !v4 )
      goto LABEL_10;
    v10 = *v6;
    if ( !*v6 )
      goto LABEL_10;
    v179 = ++v6;
    *v8++ = v10;
    v149 = v8;
    v170 = --v7;
    v171 = --v4;
    v150 = ++v9;
  }
  v149 = --v8;
  v150 = v9 - 1;
LABEL_10:
  *v8 = 0;
  v11 = 2147483646;
  v174 = 2147483646;
  v12 = L"Local CMOS Clock";
  v172 = L"Local CMOS Clock";
  v13 = 256;
  v173 = 256;
  v14 = &Str;
  v151 = &Str;
  v15 = 0;
  v152 = 0;
  while ( v13 )
  {
    if ( !v11 )
      goto LABEL_16;
    v16 = *v12;
    if ( !*v12 )
      goto LABEL_16;
    v172 = ++v12;
    *v14++ = v16;
    v151 = v14;
    v173 = --v13;
    v174 = --v11;
    v152 = ++v15;
  }
  v151 = --v14;
  v152 = v15 - 1;
LABEL_16:
  *v14 = 0;
  v177 = 2147483646;
  v175 = L"Local CMOS Clock";
  v17 = 256;
  v176 = 256;
  v18 = &qword_1800A3EF0;
  v153 = &qword_1800A3EF0;
  v19 = 0;
  v154 = 0;
  while ( v17 )
  {
    if ( !v3 )
      goto LABEL_22;
    v20 = *v5;
    if ( !*v5 )
      goto LABEL_22;
    v175 = ++v5;
    *v18++ = v20;
    v153 = v18;
    v176 = --v17;
    v177 = --v3;
    v154 = ++v19;
  }
  v153 = --v18;
  v154 = v19 - 1;
LABEL_22:
  *v18 = 0;
  v157 = *((_OWORD *)qword_1800A42F0 + 1);
  v158 = *((_OWORD *)qword_1800A42F0 + 2);
  v159 = *((_OWORD *)qword_1800A42F0 + 3);
  v160 = *((_OWORD *)qword_1800A42F0 + 4);
  v161 = *((__m128i *)qword_1800A42F0 + 5);
  v162 = *((_OWORD *)qword_1800A42F0 + 6);
  v163 = *((__m128i *)qword_1800A42F0 + 7);
  v164 = *((_OWORD *)qword_1800A42F0 + 8);
  v165 = *((_OWORD *)qword_1800A42F0 + 9);
  v166 = *((_OWORD *)qword_1800A42F0 + 10);
  v167 = *((_OWORD *)qword_1800A42F0 + 11);
  v168 = *((_OWORD *)qword_1800A42F0 + 12);
  v169 = *((_QWORD *)qword_1800A42F0 + 26);
  v140 = _mm_cvtsi128_si32(v161);
  dword_1800A3EB0 = 6368 * v140;
  Priveleges = GetPriveleges();
  if ( Priveleges < 0 )
    return (unsigned int)Priveleges;
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 15) )
  {
    LastError = GetLastError();
    Priveleges = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)Priveleges;
  }
  if ( (unsigned __int8)FileLogAllowEntry(62) )
    FileLogAdd(L"ClockDisciplineThread: Starting:");
  SetClockUnsynchronized((struct LocalClockConfigInfo *)&v157);
  SetNetlogonServiceBits(dword_1800A468C);
  Priveleges = 0;
  if ( (unsigned __int8)FileLogAllowEntry(120) )
    FileLogAppend(L" LastUTC:%I64u", qword_1800A3CE0);
  if ( (unsigned __int8)FileLogAllowEntry(62) )
    FileLogAppend(L"\n");
  if ( !SetEvent(qword_1800A36D8) )
  {
    v24 = GetLastError();
    Priveleges = v24;
    if ( v24 > 0 )
      return (unsigned __int16)v24 | 0x80070000;
    return (unsigned int)Priveleges;
  }
  v25 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  do
  {
    while ( 1 )
    {
      v142 = 0;
      v26 = dword_1800A381C;
      v134 = dword_1800A381C;
      v129 = 0;
      v128 = 0;
      v27 = (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24);
      v145 = v27;
      v28 = dword_1800A526C;
      if ( (unsigned int)v27 < dword_1800A5280 )
        v28 = ++dword_1800A526C;
      dword_1800A5280 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
      v29 = v27 + ((unsigned __int64)v28 << 32);
      v142 = v29;
      if ( (unsigned __int8)FileLogAllowEntry(1003) )
        FileLogAdd(L"ClockDispln Discipline: Check and set secure time\n");
      if ( (unsigned int)RefreshAndEnforceSecureTime(1) && (unsigned __int8)FileLogAllowEntry(107) )
        FileLogAdd(L"ClockDispln Discipline: *SET*SECURE*TIME*\n");
      if ( byte_1800A3CC9 )
      {
        if ( HIDWORD(v160) )
        {
          v31 = HIDWORD(v160);
          if ( HIDWORD(v160) > 0x19999999 )
            v31 = 429496729;
          v30 = 10 * v31;
        }
        else
        {
          v30 = 10;
        }
        goto LABEL_60;
      }
      if ( !(unsigned int)IsTimeServiceReliable() )
      {
        v30 = -1;
LABEL_60:
        v130 = v30;
        goto LABEL_61;
      }
      v32 = v29 - asint64::getValue((asint64 *)&dword_1800A382C);
      if ( v32 > 0x5265C00 )
      {
        v30 = 5000;
LABEL_56:
        v130 = v30;
        goto LABEL_57;
      }
      v30 = 86400000 - v32;
      v130 = 86400000 - v32;
      if ( dword_1800A3810 == 1 || dword_1800A3810 == 2 )
      {
        if ( v30 > 0x7530 )
          v30 = 30000;
        goto LABEL_56;
      }
LABEL_57:
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAdd(
          L"ClockDispln: we're a reliable time service with no time source: LS: %I64d, %TN: %I64d, WAIT: %d\n",
          v32,
          864000000000LL,
          v30);
LABEL_61:
      v33 = WaitForMultipleObjectsEx(2u, Handles, 0, v30, 0);
      v133 = v33;
      if ( v33 == -1 )
      {
        v34 = GetLastError();
        Priveleges = v34;
        if ( v34 > 0 )
          return (unsigned __int16)v34 | 0x80070000;
        return (unsigned int)Priveleges;
      }
      if ( !v33 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(62) )
          FileLogAdd(L"ClockDisciplineThread: hShutDownEvent signaled. Exiting.\n");
        if ( v2 )
        {
          v136 = 0;
          AccurateGetSystemTime(&v136);
          AccurateSetSystemTimeWrapper(v136);
          v35 = SetSystemTimeAdjustmentWrapper(0, 0, 0, 0, 1, 0, v125, 0, 0);
          if ( v35 < 0 && Priveleges >= 0 )
            Priveleges = v35;
        }
        else if ( (unsigned __int8)FileLogAllowEntry(73) )
        {
          FileLogAdd(L"Service is shutting down, but no time adjustment occured.\n");
        }
        _set_se_translator(v180);
        if ( Priveleges >= 0 )
          return 0;
        return (unsigned int)Priveleges;
      }
      if ( v33 == 1 )
        break;
      if ( byte_1800A3CC9 || v33 != 258 )
        goto LABEL_82;
      if ( (unsigned int)IsTimeServiceReliable() )
      {
        AccurateGetTickCount(&v142);
        v155 = v142;
        dword_1800A382C = HIDWORD(v142);
        qword_1800A3830 = v142;
        AccurateGetSystemTime((unsigned __int64 *)&qword_1800A4340);
        if ( byte_1800A45A0 )
        {
          dword_1800A3810 = (unsigned __int8)byte_1800A4398;
          dword_1800A3814 = (unsigned __int8)byte_1800A4399;
          dword_1800A3818 = dword_1800A4384;
          dword_1800A3838 = 0;
          qword_1800A383C = 0;
          dword_1800A3844 = HIDWORD(qword_1800A4388);
          qword_1800A3848 = qword_1800A4388;
          dword_1800A3850 = dword_1800A439C;
        }
        else if ( !byte_1800A45A1 && dword_1800A4700 )
        {
          CheckAndUpdateLI((struct LSState *)&dword_1800A4700);
        }
        SaveLastKnownGoodTimeInRegistry(&qword_1800A4340);
      }
    }
    if ( !dword_1800A3AA8 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAdd(L"ClockDisciplineThread: ParamChange. Reloading constants.\n");
      v157 = *((_OWORD *)qword_1800A42F0 + 1);
      v158 = *((_OWORD *)qword_1800A42F0 + 2);
      v159 = *((_OWORD *)qword_1800A42F0 + 3);
      v160 = *((_OWORD *)qword_1800A42F0 + 4);
      v161 = *((__m128i *)qword_1800A42F0 + 5);
      v162 = *((_OWORD *)qword_1800A42F0 + 6);
      v36 = *((__m128i *)qword_1800A42F0 + 7);
      v163 = v36;
      v164 = *((_OWORD *)qword_1800A42F0 + 8);
      v165 = *((_OWORD *)qword_1800A42F0 + 9);
      v166 = *((_OWORD *)qword_1800A42F0 + 10);
      v167 = *((_OWORD *)qword_1800A42F0 + 11);
      v168 = *((_OWORD *)qword_1800A42F0 + 12);
      v169 = *((_QWORD *)qword_1800A42F0 + 26);
      v140 = _mm_cvtsi128_si32(v161);
      dword_1800A3EB0 = 6368 * v140;
      ClampClockRate((struct LocalClockConfigInfo *)&v157);
      if ( dword_1800A3818 == 1279479628 )
      {
        v37 = 10000000LL * (unsigned int)_mm_cvtsi128_si32(v36);
        if ( v37 != asint64::getValue((asint64 *)&dword_1800A3844) )
        {
          if ( (unsigned __int8)FileLogAllowEntry(62) )
            FileLogAdd(L"ClockDispln: LocalClockDispersion adjusted.\n");
          v156 = v37;
          dword_1800A3844 = HIDWORD(v37);
          qword_1800A3848 = v37;
        }
      }
    }
LABEL_82:
    if ( MEMORY[0x7FFE0320] < (unsigned int)dword_1800A5270 )
      ++dword_1800A5274;
    dword_1800A5270 = MEMORY[0x7FFE0320];
    v38 = MEMORY[0x7FFE0320] + ((unsigned __int64)(unsigned int)dword_1800A5274 << 32) - qword_1800A3CD8;
    v156 = v38;
    qword_1800A3CD8 += v38;
    UpdateSettingsWithAppliedCorrectionHA(v38);
    if ( (__int64)v158 < 0 )
      v39 = (double)(int)(v158 & 1 | ((unsigned __int64)v158 >> 1))
          + (double)(int)(v158 & 1 | ((unsigned __int64)v158 >> 1));
    else
      v39 = (double)(int)v158;
    v40 = *(double *)&xmmword_1800A3E98 / v39 * 10000000.0;
    if ( (v38 & 0x8000000000000000uLL) != 0LL )
      v41 = (double)(int)(v38 & 1 | (v38 >> 1)) + (double)(int)(v38 & 1 | (v38 >> 1));
    else
      v41 = (double)(int)v38;
    *((double *)&xmmword_1800A3E98 + 1) = *((double *)&xmmword_1800A3E98 + 1) + v40 * (v41 * 0.015625);
    v42 = *((double *)&xmmword_1800A3E98 + 1);
    v43 = *((double *)&xmmword_1800A3E98 + 1);
    if ( *((double *)&xmmword_1800A3E98 + 1) >= 0.0 )
      v43 = floor(*((double *)&xmmword_1800A3E98 + 1));
    else
      o_ceil_0();
    v44 = (unsigned int)(int)v43;
    qword_1800A3CD0 += v44;
    *((double *)&xmmword_1800A3E98 + 1) = v42 - (double)(int)v44;
    while ( dword_1800A3820 != HIDWORD(qword_1800A3824) )
      ;
    v183 = (unsigned int)qword_1800A3824 + ((unsigned __int64)dword_1800A3820 << 32) - v44;
    dword_1800A3820 = HIDWORD(v183);
    LODWORD(qword_1800A3824) = qword_1800A3824 - v44;
    HIDWORD(qword_1800A3824) = HIDWORD(v183);
    if ( (unsigned __int8)FileLogAllowEntry(301) )
    {
      Value = asint64::getValue((asint64 *)&dword_1800A3820);
      FileLogAdd(
        L"USO:%0.9f URA:%0.9f UO:%I64d kPHO:%I64d spO:%I64d\n",
        *((_QWORD *)&xmmword_1800A3E98 + 1),
        (_QWORD)xmmword_1800A3E98,
        v44,
        qword_1800A3CD0,
        Value);
    }
    if ( (unsigned __int8)FileLogAllowEntry(107) )
      FileLogAppend(L" PCT: %I64u ", v38);
    if ( v33 == 1 )
    {
      if ( (unsigned int)(dword_1800A3AA8 - 2) > 1 )
      {
        v72 = DWORD1(v162);
LABEL_244:
        if ( dword_1800A3AA8 == 1 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(62) )
            FileLogAdd(L"ClockDispln TimeSlip:");
          qword_1800A3AB0 = gc_toZero;
          byte_1800A3AAC = 1;
          *(_DWORD *)&Data = *((_DWORD *)qword_1800A42F0 + 4);
          qword_1800A3CF0 = *((_QWORD *)qword_1800A42F0 + 4);
          qword_1800A3CD0 = 0;
          dword_1800A3820 = 0;
          qword_1800A3824 = 0;
          xmmword_1800A3E98 = 0u;
          dword_1800A3E8C = 0;
          dword_1800A3E94 = 0;
          AccurateGetInterruptCount(&qword_1800A3CD8);
          AccurateGetInterruptCount(&qword_1800A3CE0);
          if ( (unsigned __int8)FileLogAllowEntry(120) )
            FileLogAppend(L"TimeSlip LastUTC:%I64u", qword_1800A3CE0);
          dword_1800A3ED8 = 0;
          dword_1800A3EDC = 0;
          StringCchCopyW(&qword_1800A3AC8, 0x100u, L"Free-running System Clock");
          if ( dword_1800A381C > v72 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L" [Poll: %d->%d]", (unsigned int)dword_1800A381C, (unsigned int)v72);
            dword_1800A381C = v72;
            byte_1800A3AB8 = 1;
          }
          SetClockUnsynchronized((struct LocalClockConfigInfo *)&v157);
          if ( (unsigned __int8)FileLogAllowEntry(62) )
            FileLogAppend(L"\n");
        }
        goto LABEL_255;
      }
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAdd(L"ClockDispln Update:");
      byte_1800A3AB8 = 0;
      byte_1800A3AAC = 0;
      byte_1800A3AB9 = 0;
      byte_1800A3ABA = 0;
      byte_1800A3CC8 = 0;
      byte_1800A3CCA = 0;
      byte_1800A3CCB = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      if ( qword_1800A3878 < qword_1800A3CE0 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(62) )
          FileLogAppend(L" *STALE*(NextSTC=%I64u <= LastUTC=%I64u)", qword_1800A3878, qword_1800A3CE0);
        byte_1800A3AB9 = 1;
LABEL_207:
        v147 = 0;
        AccurateGetSystemTime(&v147);
        switch ( dword_1800A3EDC )
        {
          case 0:
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L" Unset->Hold");
            dword_1800A3EDC = 1;
            dword_1800A3EE0 = 0;
            break;
          case 1:
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L" Hold(%u)", (unsigned int)dword_1800A3EE0);
            if ( ++dword_1800A3EE0 < (unsigned int)v162 )
              break;
            dword_1800A3EDC = 2;
            if ( !(unsigned __int8)FileLogAllowEntry(62) )
              break;
            goto LABEL_235;
          case 2:
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L" Sync");
            if ( v46 && v47 )
            {
              dword_1800A3EDC = 3;
              qword_1800A3EE8 = v147;
              v70 = o_log_0((double)v161.m128i_i32[3]);
              v71 = (int)floor(v70 / 1.38629436);
              v72 = DWORD1(v162);
              if ( dword_1800A381C > v71 )
              {
                v73 = DWORD1(v162);
                if ( v71 > SDWORD1(v162) )
                  v73 = v71;
                dword_1800A381C = v73;
                byte_1800A3AB8 = 1;
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                  FileLogAppend(L" Poll(Spike):", (unsigned int)dword_1800A381C);
              }
              if ( (unsigned __int8)FileLogAllowEntry(62) )
                FileLogAppend(L"->Spike");
              goto LABEL_240;
            }
            break;
          case 3:
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L" Spike");
            if ( !v46 || v47 )
            {
              if ( v147 - qword_1800A3EE8 > 10000000 * (unsigned __int64)v161.m128i_u32[3] )
              {
                dword_1800A3EDC = 0;
                dword_1800A3810 = 3;
                byte_1800A3CCA = v47;
                byte_1800A3CCB = 0;
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                  FileLogAppend(L"->Unset");
              }
              break;
            }
            dword_1800A3EDC = 2;
            if ( (unsigned __int8)FileLogAllowEntry(62) )
LABEL_235:
              FileLogAppend(L"->Sync");
            break;
        }
        v72 = DWORD1(v162);
LABEL_240:
        if ( (unsigned __int8)FileLogAllowEntry(62) )
          FileLogAppend(L"\n");
        v30 = v130;
        v26 = v134;
        goto LABEL_244;
      }
      v49 = qword_1800A3878 - qword_1800A3CE0 + 1;
      qword_1800A3CE0 = qword_1800A3878 + 1;
      if ( (unsigned __int8)FileLogAllowEntry(120) )
        FileLogAppend(L" LastUTC:%I64u", qword_1800A3CE0);
      v50 = qword_1800A3860 + qword_1800A3880;
      v51 = v50 - asint64::getValue((asint64 *)&dword_1800A3820);
      v52 = v51 - qword_1800A3CD0;
      if ( v51 - qword_1800A3CD0 < -(__int64)v161.m128i_u32[2] || v52 > v161.m128i_u32[2] )
      {
        v47 = 1;
        v53 = 1;
      }
      else
      {
        v53 = 0;
      }
      if ( (unsigned __int8)FileLogAllowEntry(62) )
      {
        v54 = asint64::getValue((asint64 *)&dword_1800A3820);
        v55 = L"*";
        if ( !v53 )
          v55 = &qword_180071478;
        v125 = v49;
        FileLogAppend(L" SO:%I64d KPhO:%I64d spO:%I64d %sPhO:%I64d uT:%I64u\n", v51, qword_1800A3CD0, v54, v55, v52);
      }
      if ( v163.m128i_i32[1] != -1 && v51 < -10000000LL * v163.m128i_u32[1] )
        v46 = 1;
      if ( v163.m128i_i32[2] != -1 && v51 > 10000000LL * v163.m128i_u32[2] )
        v48 = 1;
      v139 = 0;
      if ( (int)DetermineIfOffsetInSecureTimeRange(v51, &v139) < 0 )
      {
        if ( !v46 && !v48 )
        {
LABEL_141:
          v56 = byte_1800A45C4;
          goto LABEL_142;
        }
        v56 = byte_1800A45C4;
        if ( byte_1800A45C4 )
        {
          if ( v46 && byte_1800A45C4 )
          {
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L"Negative phase correction beyond MaxNegPhaseCorrection boundary. Syncing anyway");
            goto LABEL_145;
          }
          if ( v48 )
          {
            if ( !byte_1800A45C4 )
            {
LABEL_146:
              if ( dword_1800A3EDC )
              {
                if ( !v53 || (unsigned int)(dword_1800A3EDC - 2) > 1 )
                {
                  qword_1800A3CD0 = v51;
                  ComputePllAndFllRateAdjust(v49, v52, v51, v140);
                  ClampRateAdjustmentAndCalculateNewClockRate(v49, v51, (struct LocalClockConfigInfo *)&v157);
                  CorrectForClockErrorSinceSampleCollection((struct LocalClockConfigInfo *)&v157);
                  if ( dword_1800A3E94 )
                    dword_1800A3E90 = 0;
                }
              }
              else
              {
                qword_1800A3CD0 = v51;
              }
              *((_QWORD *)&g_state + (unsigned int)dword_1800A3EB4 + 261) = qword_1800A3AA0 * qword_1800A3AA0
                                                                          + qword_1800A3870 * qword_1800A3870;
              dword_1800A3EB4 = ((_BYTE)dword_1800A3EB4 + 1) & 3;
              v57 = 0;
              v144 = 0;
              for ( j = 0; j < 4; ++j )
              {
                v57 += *((_QWORD *)&g_state + j + 261);
                v144 = v57;
              }
              v59 = sqrt((double)(int)v57 * 0.25);
              v60 = 0;
              if ( v59 >= 9.223372036854776e18 )
              {
                v59 = v59 - 9.223372036854776e18;
                if ( v59 < 9.223372036854776e18 )
                  v60 = 0x8000000000000000uLL;
              }
              v61 = v60 + (unsigned int)(int)v59;
              v144 = v61;
              if ( (unsigned __int8)FileLogAllowEntry(62) )
                FileLogAppend(L" SD:%I64u", v61);
              if ( v52 < 0 )
                v52 = -v52;
              if ( dword_1800A3AA8 == 3 )
              {
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                  FileLogAppend(L" (i)");
LABEL_187:
                dword_1800A3810 = (unsigned __int8)byte_1800A3888;
                dword_1800A3814 = (unsigned __int8)byte_1800A3889 + 1;
                if ( qword_1800A3A98 )
                  *(_DWORD *)(qword_1800A3A98 + 64) = dword_1800A3814;
                dword_1800A3818 = dword_1800A385C;
                v184 = qword_1800A3868;
                dword_1800A3838 = HIDWORD(qword_1800A3868);
                qword_1800A383C = qword_1800A3868;
                v63 = qword_1800A3AA0;
                v144 = qword_1800A3AA0;
                if ( (unsigned __int64)qword_1800A3AA0 < 0x186A0 )
                  v63 = 100000;
                v144 = v63;
                v186 = qword_1800A3870 + v63;
                dword_1800A3844 = (unsigned __int64)(qword_1800A3870 + v63) >> 32;
                qword_1800A3848 = qword_1800A3870 + v63;
                dword_1800A3850 = dword_1800A388C;
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                {
                  asint64::getValue((asint64 *)&dword_1800A3844);
                  v64 = asint64::getValue((asint64 *)&dword_1800A3838);
                  LODWORD(v124) = v65;
                  FileLogAppend(
                    L" LI:%u S:%u RDl:%I64d RDs:%I64u TSF:0x%X\n",
                    (unsigned int)dword_1800A3810,
                    dword_1800A3814,
                    v64,
                    v66,
                    v124);
                }
                word_1800A3A8E = 0;
                v67 = &SourceString;
                do
                {
                  v68 = *(WCHAR *)((char *)v67 + (char *)&Str - (char *)&SourceString);
                  v69 = *v67 - v68;
                  if ( v69 )
                    break;
                  ++v67;
                }
                while ( v68 );
                if ( v69 )
                {
                  byte_1800A3CC8 = 1;
                  StringCchCopyW(&Str, 0x100u, &SourceString);
                  StringCchCopyW(&qword_1800A3AC8, 0x100u, &SourceString);
                }
                byte_1800A3CC9 = 1;
                AccurateGetTickCount(&v142);
                v185 = v142;
                dword_1800A382C = HIDWORD(v142);
                qword_1800A3830 = v142;
                AccurateGetSystemTime((unsigned __int64 *)&qword_1800A4340);
                if ( v51 <= 0 )
                {
                  if ( v51 >= 0 || qword_1800A4350 >= -v51 )
                    goto LABEL_205;
                  v51 = -v51;
                }
                else if ( qword_1800A4350 >= v51 )
                {
                  goto LABEL_205;
                }
                qword_1800A4350 = v51;
LABEL_205:
                SaveLastKnownGoodTimeInRegistry(&qword_1800A4340);
                v128 = 1;
LABEL_206:
                v2 = v127;
                v33 = v133;
                v46 = 1;
                goto LABEL_207;
              }
              if ( v52 <= v61 * (unsigned __int64)v161.m128i_u32[1] )
              {
                if ( ++dword_1800A3ED8 != 4 || dword_1800A381C >= SDWORD2(v162) )
                  goto LABEL_187;
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                  FileLogAppend(L" Poll++");
                dword_1800A3ED8 = 0;
                v62 = dword_1800A381C + 1;
              }
              else
              {
                dword_1800A3ED8 = 0;
                if ( dword_1800A381C <= SDWORD1(v162) )
                  goto LABEL_187;
                if ( (unsigned __int8)FileLogAllowEntry(62) )
                  FileLogAppend(L" Poll--");
                v62 = dword_1800A381C - 1;
              }
              dword_1800A381C = v62;
              byte_1800A3AB8 = 1;
              goto LABEL_187;
            }
            if ( (unsigned __int8)FileLogAllowEntry(62) )
              FileLogAppend(L"Positive phase correction beyond MaxPosPhaseCorrection boundary. Syncing anyway");
LABEL_145:
            byte_1800A45C4 = 0;
            goto LABEL_146;
          }
LABEL_142:
          if ( !v56 )
            goto LABEL_146;
          if ( (unsigned __int8)FileLogAllowEntry(62) )
            FileLogAppend(L"Sample was within boundaries, but resync is forced");
          goto LABEL_145;
        }
      }
      else if ( v139 )
      {
        if ( v46 || v48 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(62) )
            FileLogAppend(L"Phase correction with in secure time boundary but beyond MaxNeg/PosPhaseCorrection boundary.");
          byte_1800A46F8 = 1;
          goto LABEL_145;
        }
        goto LABEL_141;
      }
      byte_1800A3ABA = 1;
      qword_1800A3AC0 = v51;
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAppend(L" *TOO BIG*");
      goto LABEL_206;
    }
LABEL_255:
    v74 = qword_1800A3CD0 / -10;
    if ( qword_1800A3CD0 / -10 < 0 )
      v74 = qword_1800A3CD0 / 10;
    g_ullComputedTimeOffsetUSec = v74;
    if ( v33 == 1 && dword_1800A3AA8 == 4 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAdd(L"ClockDispln GoUnsyncd:");
      byte_1800A3CC8 = 0;
      if ( wcscmp_0(L"Free-running System Clock", &Str) )
      {
        StringCchCopyW(&Str, 0x100u, L"Free-running System Clock");
        StringCchCopyW(&qword_1800A3EF0, 0x100u, &qword_1800A3AC8);
        StringCchCopyW(&qword_1800A3AC8, 0x100u, L"Free-running System Clock");
        byte_1800A3CC8 = 1;
      }
      SetClockUnsynchronized((struct LocalClockConfigInfo *)&v157);
      if ( (unsigned __int8)FileLogAllowEntry(62) )
        FileLogAppend(L"\n");
    }
    if ( _InterlockedCompareExchange(&dword_1800A460C, 0, 0) )
    {
      v75 = 0;
    }
    else
    {
      v75 = TryEnterCriticalSection(&stru_1800A45E0);
      if ( v75 && _InterlockedCompareExchange(&dword_1800A460C, 0, 0) )
      {
        v75 = 0;
        LeaveCriticalSection(&stru_1800A45E0);
      }
    }
    v76 = v75;
    Priveleges = 0;
    v135 = 0;
    v126 = v75;
    if ( byte_1800A3CC9 )
    {
      if ( !v75 )
        goto LABEL_369;
      v77 = 1LL << v26;
      v138 = 0;
      v78 = DWORD2(v160);
      v143 = 0;
      v79 = (double)(v30 / 0x3E8);
      v80 = 0x989680uLL / qword_1800A3CF0;
      if ( ((0x989680uLL / qword_1800A3CF0) & 0x8000000000000000uLL) != 0LL )
        v81 = (double)(int)((0x989680uLL / qword_1800A3CF0) & 1 | (v80 >> 1))
            + (double)(int)((0x989680uLL / qword_1800A3CF0) & 1 | (v80 >> 1));
      else
        v81 = (double)(int)v80;
      v82 = 1LL - (unsigned int)(int)(v81 * v79 * -0.5);
      v83 = (unsigned int)(int)((double)(int)qword_1800A3CD0 / v79);
      v84 = (float)((float)(int)qword_1800A3CD0 * 64.0) / (float)(v77 * 16 * DWORD2(v160));
      v85 = (unsigned int)(int)v84;
      v143 = v85;
      if ( (int)v84 )
      {
        if ( v85 >= v83 )
          v85 = v83;
      }
      else if ( v85 <= v83 )
      {
        v85 = v83;
      }
      v86 = v85;
      v143 = v85;
      if ( !v85 )
      {
        if ( qword_1800A3CD0 <= v82 )
        {
          if ( qword_1800A3CD0 < -v82 )
          {
            v85 = -1;
            v143 = -1;
            v86 = -1;
          }
        }
        else
        {
          v85 = 1;
          v143 = 1;
          v86 = 1;
        }
      }
      if ( (unsigned __int8)FileLogAllowEntry(301) )
      {
        v125 = v82;
        bAlertable[0] = v30;
        FileLogAdd(
          L"tPC:%I64d PCR:%d UI:%d WT:%d PI:%I64u oT:%I64d mC:%I64d\n",
          v85,
          v78,
          HIDWORD(v160),
          *(_QWORD *)bAlertable,
          v77);
      }
      v138 = v85;
      dword_1800A3E90 = dword_1800A3E8C;
      dword_1800A3E8C = v85;
      if ( v86 < 0 )
      {
        v86 = -v86;
        v138 = v86;
      }
      v87 = qword_1800A3CD0;
      v137 = qword_1800A3CD0;
      if ( qword_1800A3CD0 < 0 )
      {
        v87 = -qword_1800A3CD0;
        v137 = -qword_1800A3CD0;
      }
      v88 = v87 / 10000000;
      v137 = v87 / 10000000;
      if ( ((unsigned __int64)v86 > *((_QWORD *)qword_1800A42F0 + 4) >> 1 || (unsigned int)v88 >= v163.m128i_i32[3])
        && v133 == 1 )
      {
        v148 = 0;
        AccurateGetSystemTime(&v148);
        v148 += qword_1800A3CD0;
        AccurateSetSystemTimeWrapper(v148);
        v131 = asint64::getValue((asint64 *)&dword_1800A3820) + qword_1800A3CD0;
        dword_1800A3820 = HIDWORD(v131);
        qword_1800A3824 = v131;
        qword_1800A3AB0 = qword_1800A3CD0;
        if ( (unsigned __int8)FileLogAllowEntry(107) )
        {
          v89 = asint64::getValue((asint64 *)&dword_1800A3820);
          FileLogAdd(L"ClockDispln Discipline: *SET*TIME* - KPho:%I64d spO:%I64d\n", qword_1800A3CD0, v89);
        }
        qword_1800A3CD0 = 0;
        dword_1800A3820 = 0;
        qword_1800A3824 = 0;
        xmmword_1800A3E98 = 0u;
        LODWORD(v85) = 0;
        dword_1800A3E8C = 0;
        dword_1800A3E94 = 0;
        v129 = 1;
        byte_1800A3AAC = 1;
        if ( (_DWORD)v164 != -1 && (unsigned int)v88 > (unsigned int)v164 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(107) )
            FileLogAdd(L" (AUDIT) Time Jump of %I64d seconds.\n", v88);
          Priveleges = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIME_JUMP_AUDIT, L"I", v88);
          v135 = Priveleges;
          if ( Priveleges < 0 )
            return (unsigned int)Priveleges;
          LODWORD(v85) = dword_1800A3E8C;
        }
      }
      v90 = (int)v85;
      v91 = dword_1800A3E90;
      v138 = dword_1800A3E90;
      v92 = qword_1800A3CF0;
      v141 = 0;
      if ( qword_1800A3CF0 < 0 )
      {
        v93 = (float)(qword_1800A3CF0 & 1 | (unsigned int)((unsigned __int64)qword_1800A3CF0 >> 1))
            + (float)(qword_1800A3CF0 & 1 | (unsigned int)((unsigned __int64)qword_1800A3CF0 >> 1));
        v91 = v138;
      }
      else
      {
        v93 = (float)(int)qword_1800A3CF0;
      }
      if ( qword_1800A3CF0 )
      {
        v94 = (unsigned int)(int)(float)((float)(int)v85 / (float)(10000000.0 / v93));
        v95 = (unsigned int)(int)(float)((float)v91 / (float)(10000000.0 / v93));
      }
      else
      {
        v95 = 0;
        v94 = 0;
      }
      v136 = v94;
      v145 = v95;
      v96 = 0;
      v146 = 0;
      v97 = 0;
      v178 = 0;
      if ( !qword_1800A3CF0 )
        goto LABEL_354;
      v98 = qword_1800A3CF0 - v94;
      v99 = (int)v85 <= 0;
      if ( (int)v85 < 0 )
      {
        if ( v98 < qword_1800A3CF0 )
        {
LABEL_354:
          if ( (_DWORD)v85 && (_DWORD)v85 != dword_1800A3E90 && (unsigned __int8)FileLogAllowEntry(107) )
          {
            bAlertable[0] = HIDWORD(v160);
            FileLogAppend(
              L" (PhCRRL:%d CRL:%u phcTL:%I64u) UI:%d KPhO:%I64d\n",
              (unsigned int)dword_1800A3E8C,
              *(unsigned int *)&Data,
              v156,
              *(_QWORD *)bAlertable,
              qword_1800A3CD0);
          }
          v2 = 1;
          v127 = 1;
          byte_1800A45A2 = 1;
          if ( v128 )
            SaveLastGoodSampleInfo(&Str);
          if ( bStartedAsTask )
          {
            if ( (unsigned __int8)FileLogAllowEntry(73) )
              FileLogAdd(L"Service was started as a task.  Synchronization complete, shutting down now.\n");
            if ( !SetEvent(qword_1800A3748) )
            {
              v120 = GetLastError();
              Priveleges = v120;
              if ( v120 > 0 )
                return (unsigned __int16)v120 | 0x80070000;
              return (unsigned int)Priveleges;
            }
          }
          v76 = v126;
          v33 = v133;
          Priveleges = v135;
          goto LABEL_367;
        }
        v99 = (int)v85 <= 0;
      }
      if ( v99 || v98 <= qword_1800A3CF0 )
      {
        v132 = *((_DWORD *)qword_1800A42F0 + 33);
        v100 = qword_1800A3EA8;
        LODWORD(v155) = *(_DWORD *)&Data;
        v137 = qword_1800A3CF0 - v95;
        EnterCriticalSection(&stru_1800A4610);
        v101 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        v181 = (unsigned int)v101;
        v102 = dword_1800A5284;
        if ( (unsigned int)v101 < dword_1800A5278 )
          v102 = ++dword_1800A5284;
        dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        v103 = (unsigned int)v101 + ((unsigned __int64)v102 << 32);
        LeaveCriticalSection(&stru_1800A4610);
        qword_1800A3EA8 = v100;
        if ( v100 && v100 + 60000 < v103 )
        {
          SystemInformation = 0;
          v188 = 0;
          v104 = NtQuerySystemInformation(SystemTimeAdjustmentInformation, &SystemInformation, 0x18u, 0);
          if ( v104 >= 0 )
          {
            v97 = SystemInformation;
            v178 = SystemInformation;
            v105 = 0;
          }
          else
          {
            v105 = v104 | 0x10000000;
          }
          v141 = v105;
          v106 = v137;
          if ( v97 != v137 )
            v96 = 1;
          v146 = v96;
        }
        else
        {
          v106 = v137;
        }
        if ( v138 != v90 || v96 )
        {
          SystemInformation = v98;
          v107 = NtSetSystemInformation(SystemTimeAdjustmentInformation, &SystemInformation, 0x10u);
          if ( v107 >= 0 )
            v108 = 0;
          else
            v108 = v107 | 0x10000000;
          v141 = v108;
          v109 = (float)((float)(int)v136 / v93) * 1000000.0;
          v110 = v90 / -64;
          if ( v110 < 0 )
            v110 = v90 / 64;
          g_dwClockFreqAdjustment = v110;
          v111 = -(int)(float)(v109 * 1000.0);
          if ( (int)(float)(v109 * 1000.0) > 0 )
            v111 = (int)(float)(v109 * 1000.0);
          g_dwClockFreqAdjustmentPPB = v111;
          if ( COERCE_FLOAT(LODWORD(v109) & v25) > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)v132) & v25) )
          {
            v112 = (float)(int)v155;
            if ( v106 < 0 )
              v113 = (float)(v106 & 1 | (unsigned int)((unsigned __int64)v106 >> 1))
                   + (float)(v106 & 1 | (unsigned int)((unsigned __int64)v106 >> 1));
            else
              v113 = (float)(int)v106;
            v114 = (float)(v113 / v93) * v112;
            v115 = 0;
            if ( v114 >= 9.223372e18 )
            {
              v114 = v114 - 9.223372e18;
              if ( v114 < 9.223372e18 )
                v115 = 0x8000000000000000uLL;
            }
            v116 = v115 + (unsigned int)(int)v114;
            if ( (v98 & 0x8000000000000000uLL) != 0LL )
              v117 = (float)(int)(v98 & 1 | (v98 >> 1)) + (float)(int)(v98 & 1 | (v98 >> 1));
            else
              v117 = (float)(int)v98;
            v118 = (float)(v117 / v93) * v112;
            v119 = 0;
            if ( v118 >= 9.223372e18 )
            {
              v118 = v118 - 9.223372e18;
              if ( v118 < 9.223372e18 )
                v119 = 0x8000000000000000uLL;
            }
            v125 = v103;
            HIDWORD(v124) = HIDWORD(v116);
            *(_QWORD *)bAlertable = v119 + (unsigned int)(int)v118;
            LogEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_SET_TIME_ADJUSTMENT, L"fiiif", v109);
          }
          qword_1800A3EA8 = v103;
          if ( (unsigned __int8)FileLogAllowEntry(107) )
            FileLogAdd(
              L"ClockDispln Discipline: *SKEW*TIME* - PhCRR:%I64d CRD:%I64d PhCRR_:%I64d CRD_:%I64d CR:%I64u ",
              v90,
              v136,
              v138,
              v145,
              v92);
          if ( v96 && (unsigned __int8)FileLogAllowEntry(0) )
            FileLogAdd(
              L"\nThe system time adjustment was set to an *unexpected* value. expected:%I64u actual:%I64u.\n",
              v106,
              v97);
        }
        LODWORD(v85) = dword_1800A3E8C;
      }
      goto LABEL_354;
    }
LABEL_367:
    if ( v76 )
      Priveleges = AcquireControlOfSystemClock(0, 0, 0);
LABEL_369:
    if ( v129 )
      SetEvent(qword_1800A36F8);
  }
  while ( v33 != 1 || SetEvent(qword_1800A36D8) );
  v121 = GetLastError();
  Priveleges = v121;
  if ( v121 > 0 )
    return (unsigned __int16)v121 | 0x80070000;
  return (unsigned int)Priveleges;
}

```

## disassembly

```asm
0x18001da40  mov     rax, rsp
0x18001da43  push    rbx
0x18001da44  push    rsi
0x18001da45  push    rdi
0x18001da46  push    r12
0x18001da48  push    r13
0x18001da4a  push    r14
0x18001da4c  push    r15
0x18001da4e  sub     rsp, 380h
0x18001da55  movaps  xmmword ptr [rax-48h], xmm6
0x18001da59  movaps  xmmword ptr [rax-58h], xmm7
0x18001da5d  movaps  xmmword ptr [rax-68h], xmm8
0x18001da62  movaps  xmmword ptr [rax-78h], xmm9
0x18001da67  movaps  xmmword ptr [rax-88h], xmm10
0x18001da6f  movaps  xmmword ptr [rax-98h], xmm11
0x18001da77  movaps  xmmword ptr [rax-0A8h], xmm12
0x18001da7f  movaps  xmmword ptr [rax-0B8h], xmm13
0x18001da87  movaps  xmmword ptr [rax-0C8h], xmm14
0x18001da8f  movaps  xmmword ptr [rax-0D8h], xmm15
0x18001da97  mov     rax, cs:__security_cookie
0x18001da9e  xor     rax, rsp
0x18001daa1  mov     [rsp+3B8h+var_E8], rax
0x18001daa9  mov     rax, cs:hEvent
0x18001dab0  mov     [rsp+3B8h+Handles], rax
0x18001dab8  mov     rax, cs:qword_1800A36D0
0x18001dabf  mov     [rsp+3B8h+var_160], rax
0x18001dac7  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18001dace  call    cs:__imp__set_se_translator
0x18001dad5  nop     dword ptr [rax+rax+00h]
0x18001dada  mov     [rsp+3B8h+var_178], rax
0x18001dae2  lea     rcx, qword_1800A3CD8; unsigned __int64 *
0x18001dae9  call    ?AccurateGetInterruptCount@@YAXPEA_K@Z; AccurateGetInterruptCount(unsigned __int64 *)
0x18001daee  lea     rcx, qword_1800A3CE0; unsigned __int64 *
0x18001daf5  call    ?AccurateGetInterruptCount@@YAXPEA_K@Z; AccurateGetInterruptCount(unsigned __int64 *)
0x18001dafa  xor     esi, esi
0x18001dafc  mov     cs:qword_1800A3CD0, rsi
0x18001db03  mov     cs:dword_1800A3820, esi
0x18001db09  mov     dword ptr cs:qword_1800A3824, esi
0x18001db0f  mov     dword ptr cs:qword_1800A3824+4, esi
0x18001db15  xorps   xmm9, xmm9
0x18001db19  movsd   qword ptr cs:xmmword_1800A3E98, xmm9
0x18001db22  movsd   qword ptr cs:xmmword_1800A3E98+8, xmm9
0x18001db2b  mov     cs:dword_1800A3E8C, esi
0x18001db31  mov     cs:dword_1800A3E94, esi
0x18001db37  mov     cs:dword_1800A3E90, esi
0x18001db3d  mov     rcx, cs:qword_1800A42F0
0x18001db44  mov     eax, [rcx+10h]
0x18001db47  mov     cs:Data, eax
0x18001db4d  mov     rax, [rcx+20h]
0x18001db51  mov     cs:qword_1800A3CF0, rax
0x18001db58  mov     cs:dword_1800A3EB4, esi
0x18001db5e  mov     ecx, esi
0x18001db60  lea     rdx, ?g_state@@3UStateInfo@@A; StateInfo g_state
0x18001db67  mov     [rsp+3B8h+var_34C], ecx
0x18001db6b  cmp     ecx, 4
0x18001db6e  jnb     short loc_18001DB7E
0x18001db70  mov     eax, ecx
0x18001db72  mov     [rdx+rax*8+828h], rsi
0x18001db7a  inc     ecx
0x18001db7c  jmp     short loc_18001DB67
0x18001db7e  mov     cs:dword_1800A3ED8, esi
0x18001db84  mov     cs:dword_1800A3EDC, esi
0x18001db8a  xor     r15b, r15b
0x18001db8d  mov     [rsp+3B8h+var_35F], r15b
0x18001db92  mov     ecx, 7FFFFFFEh
0x18001db97  mov     r8d, ecx
0x18001db9a  mov     [rsp+3B8h+var_1C0], rcx
0x18001dba2  lea     rdx, aLocalCmosClock; "Local CMOS Clock"
0x18001dba9  mov     r10, rdx
0x18001dbac  mov     [rsp+3B8h+var_180], rdx
0x18001dbb4  mov     r9d, 100h
0x18001dbba  mov     [rsp+3B8h+var_1C8], r9
0x18001dbc2  lea     rax, qword_1800A3AC8
0x18001dbc9  mov     [rsp+3B8h+var_2D8], rax
0x18001dbd1  mov     r11, rsi
0x18001dbd4  mov     [rsp+3B8h+var_2D0], rsi
0x18001dbdc  test    r9, r9
0x18001dbdf  jz      short loc_18001DC2D
0x18001dbe1  test    r8, r8
0x18001dbe4  jz      short loc_18001DC44
0x18001dbe6  movzx   ebx, word ptr [r10]
0x18001dbea  test    bx, bx
0x18001dbed  jz      short loc_18001DC44
0x18001dbef  add     r10, 2
0x18001dbf3  mov     [rsp+3B8h+var_180], r10
0x18001dbfb  mov     [rax], bx
0x18001dbfe  add     rax, 2
0x18001dc02  mov     [rsp+3B8h+var_2D8], rax
0x18001dc0a  dec     r9
0x18001dc0d  mov     [rsp+3B8h+var_1C8], r9
0x18001dc15  dec     r8
0x18001dc18  mov     [rsp+3B8h+var_1C0], r8
0x18001dc20  inc     r11
0x18001dc23  mov     [rsp+3B8h+var_2D0], r11
0x18001dc2b  jmp     short loc_18001DBDC
0x18001dc2d  sub     rax, 2
0x18001dc31  mov     [rsp+3B8h+var_2D8], rax
0x18001dc39  dec     r11
0x18001dc3c  mov     [rsp+3B8h+var_2D0], r11
0x18001dc44  mov     [rax], si
0x18001dc47  mov     r8, rcx
0x18001dc4a  mov     [rsp+3B8h+var_1A8], rcx
0x18001dc52  mov     r10, rdx
0x18001dc55  mov     [rsp+3B8h+var_1B8], rdx
0x18001dc5d  mov     r9d, 100h
0x18001dc63  mov     [rsp+3B8h+var_1B0], r9
0x18001dc6b  lea     rax, Str
0x18001dc72  mov     [rsp+3B8h+var_2C8], rax
0x18001dc7a  mov     r11, rsi
0x18001dc7d  mov     [rsp+3B8h+var_2C0], rsi
0x18001dc85  test    r9, r9
0x18001dc88  jz      short loc_18001DCD6
0x18001dc8a  test    r8, r8
0x18001dc8d  jz      short loc_18001DCED
0x18001dc8f  movzx   ebx, word ptr [r10]
0x18001dc93  test    bx, bx
0x18001dc96  jz      short loc_18001DCED
0x18001dc98  add     r10, 2
0x18001dc9c  mov     [rsp+3B8h+var_1B8], r10
0x18001dca4  mov     [rax], bx
0x18001dca7  add     rax, 2
0x18001dcab  mov     [rsp+3B8h+var_2C8], rax
0x18001dcb3  dec     r9
0x18001dcb6  mov     [rsp+3B8h+var_1B0], r9
0x18001dcbe  dec     r8
0x18001dcc1  mov     [rsp+3B8h+var_1A8], r8
0x18001dcc9  inc     r11
0x18001dccc  mov     [rsp+3B8h+var_2C0], r11
0x18001dcd4  jmp     short loc_18001DC85
0x18001dcd6  sub     rax, 2
0x18001dcda  mov     [rsp+3B8h+var_2C8], rax
0x18001dce2  dec     r11
0x18001dce5  mov     [rsp+3B8h+var_2C0], r11
0x18001dced  mov     [rax], si
0x18001dcf0  mov     [rsp+3B8h+var_190], rcx
0x18001dcf8  mov     [rsp+3B8h+var_1A0], rdx
0x18001dd00  mov     r8d, 100h
0x18001dd06  mov     [rsp+3B8h+var_198], r8
0x18001dd0e  lea     rax, qword_1800A3EF0
0x18001dd15  mov     [rsp+3B8h+var_2B8], rax
0x18001dd1d  mov     r9, rsi
0x18001dd20  mov     [rsp+3B8h+var_2B0], rsi
0x18001dd28  test    r8, r8
0x18001dd2b  jz      short loc_18001DD7B
0x18001dd2d  test    rcx, rcx
0x18001dd30  jz      short loc_18001DD92
0x18001dd32  movzx   r10d, word ptr [rdx]
0x18001dd36  test    r10w, r10w
0x18001dd3a  jz      short loc_18001DD92
0x18001dd3c  add     rdx, 2
0x18001dd40  mov     [rsp+3B8h+var_1A0], rdx
0x18001dd48  mov     [rax], r10w
0x18001dd4c  add     rax, 2
0x18001dd50  mov     [rsp+3B8h+var_2B8], rax
0x18001dd58  dec     r8
0x18001dd5b  mov     [rsp+3B8h+var_198], r8
0x18001dd63  dec     rcx
0x18001dd66  mov     [rsp+3B8h+var_190], rcx
0x18001dd6e  inc     r9
0x18001dd71  mov     [rsp+3B8h+var_2B0], r9
0x18001dd79  jmp     short loc_18001DD28
0x18001dd7b  sub     rax, 2
0x18001dd7f  mov     [rsp+3B8h+var_2B8], rax
0x18001dd87  dec     r9
0x18001dd8a  mov     [rsp+3B8h+var_2B0], r9
0x18001dd92  mov     [rax], si
0x18001dd95  mov     rax, cs:qword_1800A42F0
0x18001dd9c  movups  xmm0, xmmword ptr [rax+10h]
0x18001dda0  movups  [rsp+3B8h+var_298], xmm0
0x18001dda8  movups  xmm1, xmmword ptr [rax+20h]
0x18001ddac  movups  [rsp+3B8h+var_288], xmm1
0x18001ddb4  movups  xmm0, xmmword ptr [rax+30h]
0x18001ddb8  movups  [rsp+3B8h+var_278], xmm0
0x18001ddc0  movups  xmm1, xmmword ptr [rax+40h]
0x18001ddc4  movups  [rsp+3B8h+var_268], xmm1
0x18001ddcc  movups  xmm2, xmmword ptr [rax+50h]
0x18001ddd0  movaps  [rsp+3B8h+var_258], xmm2
0x18001ddd8  movups  xmm0, xmmword ptr [rax+60h]
0x18001dddc  movups  [rsp+3B8h+var_248], xmm0
0x18001dde4  movups  xmm1, xmmword ptr [rax+70h]
0x18001dde8  movups  [rsp+3B8h+var_238], xmm1
0x18001ddf0  movups  xmm0, xmmword ptr [rax+80h]
0x18001ddf7  movups  [rsp+3B8h+var_228], xmm0
0x18001ddff  movups  xmm1, xmmword ptr [rax+90h]
0x18001de06  movups  [rsp+3B8h+var_218], xmm1
0x18001de0e  movups  xmm0, xmmword ptr [rax+0A0h]
0x18001de15  movups  [rsp+3B8h+var_208], xmm0
0x18001de1d  movups  xmm1, xmmword ptr [rax+0B0h]
0x18001de24  movups  [rsp+3B8h+var_1F8], xmm1
0x18001de2c  movups  xmm0, xmmword ptr [rax+0C0h]
0x18001de33  movups  [rsp+3B8h+var_1E8], xmm0
0x18001de3b  mov     rax, [rax+0D0h]
0x18001de42  mov     [rsp+3B8h+var_1D8], rax
0x18001de4a  movd    eax, xmm2
0x18001de4e  mov     [rsp+3B8h+var_31C], eax
0x18001de55  imul    eax, 18E0h
0x18001de5b  mov     cs:dword_1800A3EB0, eax
0x18001de61  call    ?GetPriveleges@@YAJXZ; GetPriveleges(void)
0x18001de66  mov     r12d, eax
0x18001de69  mov     [rsp+3B8h+var_364], eax
0x18001de6d  test    eax, eax
0x18001de6f  jns     short loc_18001DE76
0x18001de71  jmp     loc_18001FC4A
0x18001de76  call    cs:__imp_GetCurrentThread
0x18001de7d  nop     dword ptr [rax+rax+00h]
0x18001de82  mov     rcx, rax; hThread
0x18001de85  mov     edx, 0Fh; nPriority
0x18001de8a  call    cs:__imp_SetThreadPriority
0x18001de91  nop     dword ptr [rax+rax+00h]
0x18001de96  test    eax, eax
0x18001de98  jnz     short loc_18001DEC2
0x18001de9a  call    cs:__imp_GetLastError
0x18001dea1  nop     dword ptr [rax+rax+00h]
0x18001dea6  mov     r12d, eax
0x18001dea9  test    eax, eax
0x18001deab  jle     short loc_18001DEB8
0x18001dead  movzx   r12d, ax
0x18001deb1  or      r12d, 80070000h
0x18001deb8  mov     [rsp+3B8h+var_364], r12d
0x18001debd  jmp     loc_18001FC4A
0x18001dec2  mov     ecx, 3Eh ; '>'
0x18001dec7  call    FileLogAllowEntry
0x18001decc  test    al, al
0x18001dece  jz      short loc_18001DEDC
0x18001ded0  lea     rcx, aClockdisciplin_0; "ClockDisciplineThread: Starting:"
0x18001ded7  call    FileLogAdd
0x18001dedc  lea     rcx, [rsp+3B8h+var_298]; struct LocalClockConfigInfo *
0x18001dee4  call    ?SetClockUnsynchronized@@YAXPEAULocalClockConfigInfo@@@Z; SetClockUnsynchronized(LocalClockConfigInfo *)
0x18001dee9  mov     ecx, cs:dword_1800A468C; unsigned int
0x18001deef  call    ?SetNetlogonServiceBits@@YAJK@Z; SetNetlogonServiceBits(ulong)
0x18001def4  mov     [rsp+3B8h+var_364], eax
0x18001def8  mov     r12d, esi
0x18001defb  mov     [rsp+3B8h+var_364], esi
0x18001deff  mov     ecx, 78h ; 'x'
0x18001df04  call    FileLogAllowEntry
0x18001df09  test    al, al
0x18001df0b  jz      short loc_18001DF20
0x18001df0d  mov     rdx, cs:qword_1800A3CE0
0x18001df14  lea     rcx, aLastutcI64u; " LastUTC:%I64u"
0x18001df1b  call    FileLogAppend
0x18001df20  mov     ecx, 3Eh ; '>'
0x18001df25  call    FileLogAllowEntry
0x18001df2a  test    al, al
0x18001df2c  jz      short loc_18001DF3A
0x18001df2e  lea     rcx, asc_18007145C; "\n"
0x18001df35  call    FileLogAppend
0x18001df3a  mov     rcx, cs:qword_1800A36D8; hEvent
0x18001df41  call    cs:__imp_SetEvent
0x18001df48  nop     dword ptr [rax+rax+00h]
0x18001df4d  test    eax, eax
0x18001df4f  jnz     short loc_18001DF79
0x18001df51  call    cs:__imp_GetLastError
0x18001df58  nop     dword ptr [rax+rax+00h]
0x18001df5d  mov     r12d, eax
0x18001df60  test    eax, eax
0x18001df62  jle     short loc_18001DF6F
0x18001df64  movzx   r12d, ax
0x18001df68  or      r12d, 80070000h
0x18001df6f  mov     [rsp+3B8h+var_364], r12d
0x18001df74  jmp     loc_18001FC4A
0x18001df79  movdqa  xmm13, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18001df82  movsd   xmm8, cs:__real@416312d000000000
0x18001df8b  movsd   xmm10, cs:__real@3f90000000000000
0x18001df94  movsd   xmm11, cs:__real@bfe0000000000000
0x18001df9d  movss   xmm12, cs:__real@42800000
0x18001dfa6  movss   xmm7, cs:__real@4b189680
0x18001dfae  movss   xmm14, cs:__real@49742400
0x18001dfb7  movss   xmm15, cs:__real@447a0000
0x18001dfc0  mov     r13d, 19999999h
0x18001dfc6  mov     r14d, 1
0x18001dfcc  mov     eax, 7FFE0320h
0x18001dfd1  mov     [rsp+3B8h+var_310], rsi
0x18001dfd9  mov     [rsp+3B8h+var_367], 0
0x18001dfde  mov     edi, cs:dword_1800A381C
0x18001dfe4  mov     dword ptr [rsp+3B8h+var_340], edi
0x18001dfe8  mov     [rsp+3B8h+var_35C], 0
0x18001dfed  mov     [rsp+3B8h+var_35D], 0
0x18001dff2  mov     [rsp+3B8h+var_2F8], rsi
0x18001dffa  mov     rax, [rax]
0x18001dffd  mov     ecx, ds:7FFE0004h
0x18001e004  imul    rcx, rax
0x18001e008  shr     rcx, 18h
0x18001e00c  mov     eax, ecx
0x18001e00e  mov     [rsp+3B8h+var_2F8], rax
0x18001e016  cmp     ecx, cs:dword_1800A5280
0x18001e01c  mov     ecx, cs:dword_1800A526C
0x18001e022  jnb     short loc_18001E02C
0x18001e024  inc     ecx
0x18001e026  mov     cs:dword_1800A526C, ecx
0x18001e02c  mov     cs:dword_1800A5280, eax
0x18001e032  mov     ebx, ecx
0x18001e034  shl     rbx, 20h
0x18001e038  add     rbx, rax
0x18001e03b  mov     [rsp+3B8h+var_310], rbx
0x18001e043  mov     ecx, 3EBh
0x18001e048  call    FileLogAllowEntry
0x18001e04d  test    al, al
0x18001e04f  jz      short loc_18001E05D
0x18001e051  lea     rcx, aClockdisplnDis_2; "ClockDispln Discipline: Check and set s"...
0x18001e058  call    FileLogAdd
  ... truncated ...
```
