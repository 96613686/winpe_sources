# RefreshAndEnforceSecureTime(int)

- ea: `0x18001fcc0`
- end: `0x1800205c9`
- name: `?RefreshAndEnforceSecureTime@@YAHH@Z`
- size: `2313`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001da40`
- `0x180039100`

## callees

- `0x18000a7e0`
- `0x18000bff4`
- `0x180018138`
- `0x18001d9a0`
- `0x18001fcc0`
- `0x1800205d0`
- `0x18002d0e4`
- `0x18003d270`
- `0x18004f360`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fefe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ff54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fefe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ff54`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020546`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020546`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001fe28`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001fe28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020533`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fd61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020533`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdaa`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001feb8`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18001feb8`
- `ntdll!RtlReleaseResource` at `0x1800202a7`
- `ntdll!RtlReleaseResource` at `0x1800202e8`
- `ntdll!RtlReleaseResource` at `0x18002037c`
- `ntdll!RtlReleaseResource` at `0x1800202a7`
- `ntdll!RtlReleaseResource` at `0x1800202e8`
- `ntdll!RtlReleaseResource` at `0x18002037c`
- `ntdll!RtlAcquireResourceShared` at `0x1800200e0`
- `ntdll!RtlAcquireResourceShared` at `0x180020337`
- `ntdll!RtlAcquireResourceShared` at `0x180020579`
- `ntdll!RtlAcquireResourceShared` at `0x1800200e0`
- `ntdll!RtlAcquireResourceShared` at `0x180020337`
- `ntdll!RtlAcquireResourceShared` at `0x180020579`

## string_xrefs

- `0x180020177`: `Failed to read secure time from the registry. Assuming secure time is disabled and continuing. Error: 0x%08X\n`
- `0x18002044b`: `Setting the system time because it is outside the secure time limits.\n`
- `0x180020152`: `Secure Time value is invalid.  Not using it for time comparisons.\n`
- `0x1800203e6`: `Secure Time value is of low confidence and cannot be used for time comparisons.\n`

## pseudocode

```c
__int64 __fastcall RefreshAndEnforceSecureTime(int a1)
{
  __int64 v2; // rsi
  unsigned int v3; // eax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  char v7; // bl
  int SecureTimeFromRegistry; // esi
  unsigned int v9; // eax
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  BOOL v12; // esi
  unsigned int v13; // esi
  ULONGLONG TickCount64; // rax
  int v15; // ecx
  double v16; // xmm0_8
  __int64 v17; // r10
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned __int64 v23; // r9
  unsigned int v24; // r10d
  char v26; // bl
  char v27; // bl
  __int64 k; // rdx
  unsigned __int64 v29; // r10
  __int64 v30; // rax
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rax
  bool v33; // cf
  __int64 i; // rdx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rdi
  __int64 j; // r8
  unsigned __int64 v38; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v40; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v41; // [rsp+38h] [rbp-40h] BYREF
  __int128 v42; // [rsp+40h] [rbp-38h] BYREF
  __int128 v43; // [rsp+50h] [rbp-28h]
  __int64 v44; // [rsp+60h] [rbp-18h]

  v44 = 0;
  v42 = 0;
  v43 = 0;
  if ( *((_DWORD *)qword_1800A42F0 + 58) )
  {
    v2 = qword_1800A46F0;
    EnterCriticalSection(&stru_1800A4610);
    v3 = dword_1800A5284;
    v4 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    if ( (unsigned int)v4 < dword_1800A5278 )
      v3 = ++dword_1800A5284;
    v5 = (unsigned int)v4 + ((unsigned __int64)v3 << 32);
    dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    LeaveCriticalSection(&stru_1800A4610);
    if ( v2 + 120000 >= v5 )
    {
      v26 = 0;
      if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
        && _pflstate
        && *((_BYTE *)_pflstate + 315)
        && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x3EBu; i = *(_QWORD *)(i + 8) )
        {
          if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x3EB )
          {
            v26 = 1;
            break;
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
        if ( v26 )
          FileLogAdd(L"Secure time seeding enforcement skipped this time.\n");
      }
    }
    else
    {
      v6 = *((unsigned int *)qword_1800A42F0 + 32);
      v7 = 0;
      SecureTimeFromRegistry = ReadSecureTimeFromRegistry((__int64)&v42);
      if ( a1 )
      {
        qword_1800A46F0 = 0;
        EnterCriticalSection(&stru_1800A4610);
        v9 = dword_1800A5284;
        v10 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        if ( (unsigned int)v10 < dword_1800A5278 )
          v9 = ++dword_1800A5284;
        dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        qword_1800A46F0 = (unsigned int)v10 + ((unsigned __int64)v9 << 32);
        LeaveCriticalSection(&stru_1800A4610);
      }
      if ( SecureTimeFromRegistry < 0 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(1003) )
          FileLogAdd(
            L"Failed to read secure time from the registry. Assuming secure time is disabled and continuing. Error: 0x%08X\n",
            (unsigned int)SecureTimeFromRegistry);
      }
      else
      {
        if ( !_InterlockedCompareExchange(&dword_1800A460C, 0, 0) )
        {
          v12 = TryEnterCriticalSection(&stru_1800A45E0);
          if ( v12 && _InterlockedCompareExchange(&dword_1800A460C, 0, 0) )
          {
            v12 = 0;
            LeaveCriticalSection(&stru_1800A45E0);
          }
          if ( v12 )
          {
            xmmword_1800A46C8 = v42;
            xmmword_1800A46D8 = v43;
            qword_1800A46E8 = v44;
            v39 = *((_QWORD *)&v42 + 1);
            v38 = 0;
            GetSystemTimePreciseAsFileTime(&v38, v11);
            v13 = 0;
            if ( a1 )
            {
              if ( *((_QWORD *)&xmmword_1800A46C8 + 1) <= 0x1D0CBED024C8000uLL
                || *((_QWORD *)&xmmword_1800A46D8 + 1) <= 0x1D0CBED024C8000uLL
                || (unsigned __int64)xmmword_1800A46D8 <= 0x1D0CBED024C8000LL
                || GetTickCount64() < (unsigned __int64)xmmword_1800A46C8
                || *((_QWORD *)&xmmword_1800A46C8 + 1) > *((_QWORD *)&xmmword_1800A46D8 + 1)
                || *((_QWORD *)&xmmword_1800A46D8 + 1) > (unsigned __int64)xmmword_1800A46D8 )
              {
                if ( (unsigned __int8)FileLogAllowEntry(1003) )
                  FileLogAdd(L"Secure Time value is invalid.  Not using it for time comparisons.\n");
                goto LABEL_38;
              }
              if ( (unsigned int)qword_1800A46E8 < 6 )
              {
                if ( (unsigned __int8)FileLogAllowEntry(1003) )
                  FileLogAdd(L"Secure Time value is of low confidence and cannot be used for time comparisons.\n");
                goto LABEL_38;
              }
              TickCount64 = GetTickCount64();
              v15 = TickCount64 - xmmword_1800A46C8;
              *(_QWORD *)&xmmword_1800A46C8 = TickCount64;
              v16 = (double)v15 * 10000.0;
              v17 = (unsigned int)(int)v16;
              if ( (int)v16 )
              {
                v18 = -1;
                v19 = -1;
                v20 = -1;
                if ( (unsigned __int64)(v17 + *((_QWORD *)&xmmword_1800A46C8 + 1)) >= *((_QWORD *)&xmmword_1800A46C8 + 1) )
                  v19 = v17 + *((_QWORD *)&xmmword_1800A46C8 + 1);
                v21 = -1;
                *((_QWORD *)&xmmword_1800A46C8 + 1) = v19;
                if ( v17 + (__int64)xmmword_1800A46D8 >= (unsigned __int64)xmmword_1800A46D8 )
                  v21 = v17 + xmmword_1800A46D8;
                *(_QWORD *)&xmmword_1800A46D8 = v21;
                if ( (unsigned __int64)(v17 + *((_QWORD *)&xmmword_1800A46D8 + 1)) >= *((_QWORD *)&xmmword_1800A46D8 + 1) )
                  v20 = v17 + *((_QWORD *)&xmmword_1800A46D8 + 1);
              }
              else
              {
                v29 = -v17;
                if ( *((_QWORD *)&xmmword_1800A46C8 + 1) < v29 )
                {
                  v19 = 0;
                  *((_QWORD *)&xmmword_1800A46C8 + 1) = 0;
                }
                else
                {
                  v19 = *((_QWORD *)&xmmword_1800A46C8 + 1) - v29;
                  *((_QWORD *)&xmmword_1800A46C8 + 1) -= v29;
                }
                if ( (unsigned __int64)xmmword_1800A46D8 < v29 )
                {
                  v31 = *((_QWORD *)&xmmword_1800A46D8 + 1);
                  v21 = 0;
                  v30 = *((_QWORD *)&xmmword_1800A46D8 + 1);
                  *(_QWORD *)&xmmword_1800A46D8 = 0;
                }
                else
                {
                  v30 = *((_QWORD *)&xmmword_1800A46D8 + 1);
                  v21 = xmmword_1800A46D8 - v29;
                  *(_QWORD *)&xmmword_1800A46D8 = xmmword_1800A46D8 - v29;
                  v31 = *((_QWORD *)&xmmword_1800A46D8 + 1);
                }
                v32 = v30 - v29;
                v20 = 0;
                v33 = v31 < v29;
                v18 = -1;
                if ( !v33 )
                  v20 = v32;
              }
              *((_QWORD *)&xmmword_1800A46D8 + 1) = v20;
              if ( v19 < 0x7DBA821800LL )
                v22 = 0;
              else
                v22 = v19 + 1165879296;
              v23 = v19 - 540000000000LL;
              v24 = HIDWORD(v38);
              if ( v19 < 0x7DBA821800LL )
                v23 = 0;
              v40 = v23;
              if ( v21 + 540000000000LL >= v21 )
                v18 = v21 + 540000000000LL;
              v41 = v18;
              if ( (v38 >= __PAIR64__(HIDWORD(v23), v22) || (unsigned __int8)FileTimeGreaterThanComparator(&v38, &v40))
                && (__PAIR64__(v24, v38) < v18 || !(unsigned __int8)FileTimeGreaterThanComparator(&v38, &v41)) )
              {
                v20 = v39;
              }
              else
              {
                v39 = v20;
                v13 = 1;
              }
              if ( !v13 )
              {
LABEL_38:
                if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
                  && _pflstate
                  && *((_BYTE *)_pflstate + 315)
                  && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
                {
                  for ( j = *((_QWORD *)_pflstate + 3); j && *(_DWORD *)j <= 0x3EBu; j = *(_QWORD *)(j + 8) )
                  {
                    if ( (unsigned int)(*(_DWORD *)(j + 4) + *(_DWORD *)j) > 0x3EB )
                    {
                      v7 = 1;
                      break;
                    }
                  }
                  RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
                  if ( v7 )
                    FileLogAdd(L"System clock not modified\n");
                }
                LeaveCriticalSection(&stru_1800A45E0);
                return v13;
              }
            }
            else
            {
              if ( !(unsigned __int8)FileTimeGreaterThanComparator((char *)&xmmword_1800A46C8 + 8, &v38) )
                goto LABEL_38;
              v20 = *((_QWORD *)&xmmword_1800A46C8 + 1);
              v13 = 1;
              v39 = *((_QWORD *)&xmmword_1800A46C8 + 1);
            }
            if ( (unsigned __int8)FileLogAllowEntry(16) )
              FileLogAdd(L"Setting the system time because it is outside the secure time limits.\n");
            LogFileTimeAsSystemTime(&v38, L"Current system time:", 16);
            LogFileTimeAsSystemTime(&v39, L"Target system time:", 16);
            AccurateSetSystemTimeWrapper(v20);
            v35 = v38 - v39;
            if ( (__int64)(v38 - v39) < 0 )
              v35 = v39 - v38;
            if ( (_DWORD)v6 != -1 )
            {
              v36 = v35 / 0x989680;
              if ( v35 / 0x989680 > v6 )
              {
                if ( (unsigned __int8)FileLogAllowEntry(16) )
                  FileLogAdd(L" (AUDIT) Time Jump of %I64d seconds.\n", v36);
                LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIME_JUMP_AUDIT, L"I", v36);
              }
            }
            byte_1800A46F8 = 1;
            qword_1800A3CD0 = 0;
            dword_1800A3820 = 0;
            qword_1800A3824 = 0;
            xmmword_1800A3E98 = 0;
            dword_1800A3E8C = 0;
            dword_1800A3E94 = 0;
            LeaveCriticalSection(&stru_1800A45E0);
            SetEvent(qword_1800A36F8);
            return v13;
          }
        }
        if ( (unsigned __int8)FileLogAllowEntry(1003) )
          FileLogAdd(L"Secure time enforcement skipped this time.\n");
      }
    }
  }
  else
  {
    v27 = 0;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
      && _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( k = *((_QWORD *)_pflstate + 3); k && *(_DWORD *)k <= 0x3EBu; k = *(_QWORD *)(k + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(k + 4) + *(_DWORD *)k) > 0x3EB )
        {
          v27 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      if ( v27 )
        FileLogAdd(L"Secure time enforcement is disabled\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001fcc0  push    rbp
0x18001fcc2  push    rbx
0x18001fcc3  push    rsi
0x18001fcc4  push    rdi
0x18001fcc5  push    r14
0x18001fcc7  push    r15
0x18001fcc9  mov     rbp, rsp
0x18001fccc  sub     rsp, 78h
0x18001fcd0  mov     rax, cs:__security_cookie
0x18001fcd7  xor     rax, rsp
0x18001fcda  mov     [rbp+var_10], rax
0x18001fcde  xor     eax, eax
0x18001fce0  xorps   xmm0, xmm0
0x18001fce3  mov     [rbp+var_18], rax
0x18001fce7  mov     edi, ecx
0x18001fce9  mov     rax, cs:qword_1800A42F0
0x18001fcf0  movups  [rbp+var_38], xmm0
0x18001fcf4  movups  [rbp+var_28], xmm0
0x18001fcf8  cmp     dword ptr [rax+0E8h], 0
0x18001fcff  jz      loc_1800200B8
0x18001fd05  mov     rsi, cs:qword_1800A46F0
0x18001fd0c  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001fd13  call    cs:__imp_EnterCriticalSection
0x18001fd1a  nop     dword ptr [rax+rax+00h]
0x18001fd1f  mov     r15d, 7FFE0320h
0x18001fd25  mov     rax, [r15]
0x18001fd28  mov     edx, ds:7FFE0004h
0x18001fd2f  imul    rdx, rax
0x18001fd33  mov     eax, cs:dword_1800A5284
0x18001fd39  shr     rdx, 18h
0x18001fd3d  cmp     edx, cs:dword_1800A5278
0x18001fd43  jb      loc_180020308
0x18001fd49  mov     ebx, eax
0x18001fd4b  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001fd52  mov     eax, edx
0x18001fd54  shl     rbx, 20h
0x18001fd58  add     rbx, rax
0x18001fd5b  mov     cs:dword_1800A5278, edx
0x18001fd61  call    cs:__imp_LeaveCriticalSection
0x18001fd68  nop     dword ptr [rax+rax+00h]
0x18001fd6d  lea     rax, [rsi+1D4C0h]
0x18001fd74  cmp     rax, rbx
0x18001fd77  jnb     loc_18002008A
0x18001fd7d  mov     rax, cs:qword_1800A42F0
0x18001fd84  lea     rcx, [rbp+var_38]
0x18001fd88  mov     r14d, [rax+80h]
0x18001fd8f  call    ReadSecureTimeFromRegistry
0x18001fd94  xor     ebx, ebx
0x18001fd96  mov     esi, eax
0x18001fd98  test    edi, edi
0x18001fd9a  jz      short loc_18001FE09
0x18001fd9c  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001fda3  mov     cs:qword_1800A46F0, rbx
0x18001fdaa  call    cs:__imp_EnterCriticalSection
0x18001fdb1  nop     dword ptr [rax+rax+00h]
0x18001fdb6  mov     rcx, [r15]
0x18001fdb9  mov     r8d, ds:7FFE0004h
0x18001fdc1  mov     eax, cs:dword_1800A5284
0x18001fdc7  imul    r8, rcx
0x18001fdcb  shr     r8, 18h
0x18001fdcf  cmp     r8d, cs:dword_1800A5278
0x18001fdd6  jb      loc_18002039C
0x18001fddc  mov     edx, eax
0x18001fdde  lea     rcx, stru_1800A4610; lpCriticalSection
0x18001fde5  shl     rdx, 20h
0x18001fde9  mov     eax, r8d
0x18001fdec  add     rdx, rax
0x18001fdef  mov     cs:dword_1800A5278, r8d
0x18001fdf6  mov     cs:qword_1800A46F0, rdx
0x18001fdfd  call    cs:__imp_LeaveCriticalSection
0x18001fe04  nop     dword ptr [rax+rax+00h]
0x18001fe09  test    esi, esi
0x18001fe0b  js      loc_180020163
0x18001fe11  xor     eax, eax
0x18001fe13  lock cmpxchg cs:dword_1800A460C, ebx
0x18001fe1b  jnz     loc_1800201A2
0x18001fe21  lea     rcx, stru_1800A45E0; lpCriticalSection
0x18001fe28  call    cs:__imp_TryEnterCriticalSection
0x18001fe2f  nop     dword ptr [rax+rax+00h]
0x18001fe34  mov     esi, eax
0x18001fe36  test    eax, eax
0x18001fe38  jz      short loc_18001FE4A
0x18001fe3a  xor     eax, eax
0x18001fe3c  lock cmpxchg cs:dword_1800A460C, ebx
0x18001fe44  jnz     loc_1800203A9
0x18001fe4a  test    esi, esi
0x18001fe4c  jz      loc_1800201A2
0x18001fe52  mov     rax, qword ptr [rbp+var_38]
0x18001fe56  lea     rcx, [rbp+var_58]
0x18001fe5a  mov     qword ptr cs:xmmword_1800A46C8, rax
0x18001fe61  mov     eax, dword ptr [rbp+var_38+8]
0x18001fe64  mov     dword ptr cs:xmmword_1800A46C8+8, eax
0x18001fe6a  mov     eax, dword ptr [rbp+var_38+0Ch]
0x18001fe6d  mov     dword ptr cs:xmmword_1800A46C8+0Ch, eax
0x18001fe73  mov     eax, dword ptr [rbp+var_28]
0x18001fe76  mov     dword ptr cs:xmmword_1800A46D8, eax
0x18001fe7c  mov     eax, dword ptr [rbp+var_28+4]
0x18001fe7f  mov     dword ptr cs:xmmword_1800A46D8+4, eax
0x18001fe85  mov     eax, dword ptr [rbp+var_28+8]
0x18001fe88  mov     dword ptr cs:xmmword_1800A46D8+8, eax
0x18001fe8e  mov     eax, dword ptr [rbp+var_28+0Ch]
0x18001fe91  mov     dword ptr cs:xmmword_1800A46D8+0Ch, eax
0x18001fe97  mov     eax, dword ptr [rbp+var_18]
0x18001fe9a  mov     dword ptr cs:qword_1800A46E8, eax
0x18001fea0  mov     eax, dword ptr [rbp+var_18+4]
0x18001fea3  mov     dword ptr cs:qword_1800A46E8+4, eax
0x18001fea9  mov     rax, qword ptr cs:xmmword_1800A46C8+8
0x18001feb0  mov     [rbp+var_50], rax
0x18001feb4  mov     [rbp+var_58], rbx
0x18001feb8  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18001febf  nop     dword ptr [rax+rax+00h]
0x18001fec4  mov     esi, ebx
0x18001fec6  test    edi, edi
0x18001fec8  jz      loc_180020415
0x18001fece  cmp     dword ptr cs:xmmword_1800A46C8+0Ch, 1D0CBEDh
0x18001fed8  jbe     loc_180020222
0x18001fede  cmp     dword ptr cs:xmmword_1800A46D8+0Ch, 1D0CBEDh
0x18001fee8  jbe     loc_180020188
0x18001feee  cmp     dword ptr cs:xmmword_1800A46D8+4, 1D0CBEDh
0x18001fef8  jbe     loc_180020127
0x18001fefe  call    cs:__imp_GetTickCount64
0x18001ff05  nop     dword ptr [rax+rax+00h]
0x18001ff0a  cmp     rax, qword ptr cs:xmmword_1800A46C8
0x18001ff11  jb      loc_180020140
0x18001ff17  mov     ecx, dword ptr cs:xmmword_1800A46D8+0Ch
0x18001ff1d  cmp     dword ptr cs:xmmword_1800A46C8+0Ch, ecx
0x18001ff23  ja      loc_180020140
0x18001ff29  mov     edx, dword ptr cs:xmmword_1800A46D8+8
0x18001ff2f  jz      loc_1800202CC
0x18001ff35  cmp     ecx, dword ptr cs:xmmword_1800A46D8+4
0x18001ff3b  ja      loc_180020140
0x18001ff41  jz      loc_1800203C3
0x18001ff47  cmp     dword ptr cs:qword_1800A46E8, 6
0x18001ff4e  jb      loc_1800203D4
0x18001ff54  call    cs:__imp_GetTickCount64
0x18001ff5b  nop     dword ptr [rax+rax+00h]
0x18001ff60  xorps   xmm0, xmm0
0x18001ff63  mov     rcx, rax
0x18001ff66  sub     rcx, qword ptr cs:xmmword_1800A46C8
0x18001ff6d  mov     qword ptr cs:xmmword_1800A46C8, rax
0x18001ff74  cvtsi2sd xmm0, rcx
0x18001ff79  mulsd   xmm0, cs:__real@40c3880000000000
0x18001ff81  cvttsd2si r10, xmm0
0x18001ff86  test    r10, r10
0x18001ff89  jle     loc_1800201C5
0x18001ff8f  mov     rax, qword ptr cs:xmmword_1800A46C8+8
0x18001ff96  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001ff9d  mov     rcx, r8
0x18001ffa0  mov     rdi, r8
0x18001ffa3  lea     rdx, [r10+rax]
0x18001ffa7  cmp     rdx, rax
0x18001ffaa  mov     rax, qword ptr cs:xmmword_1800A46D8
0x18001ffb1  cmovnb  rcx, rdx
0x18001ffb5  mov     rdx, r8
0x18001ffb8  mov     qword ptr cs:xmmword_1800A46C8+8, rcx
0x18001ffbf  lea     r9, [r10+rax]
0x18001ffc3  cmp     r9, rax
0x18001ffc6  mov     rax, qword ptr cs:xmmword_1800A46D8+8
0x18001ffcd  cmovnb  rdx, r9
0x18001ffd1  mov     qword ptr cs:xmmword_1800A46D8, rdx
0x18001ffd8  lea     r9, [r10+rax]
0x18001ffdc  cmp     r9, rax
0x18001ffdf  cmovnb  rdi, r9
0x18001ffe3  mov     r10, 7DBA821800h
0x18001ffed  mov     qword ptr cs:xmmword_1800A46D8+8, rdi
0x18001fff4  mov     r9, 0FFFFFF82457DE800h
0x18001fffe  cmp     rcx, r10
0x180020001  jb      loc_18002029B
0x180020007  lea     rax, [rcx+r9]
0x18002000b  add     r9, rcx
0x18002000e  cmp     rcx, r10
0x180020011  lea     rcx, [rdx+r10]
0x180020015  mov     r10d, dword ptr [rbp+var_58+4]
0x180020019  cmovb   r9, rbx
0x18002001d  cmp     rcx, rdx
0x180020020  mov     [rbp+var_48], r9
0x180020024  cmovnb  r8, rcx
0x180020028  shr     r9, 20h
0x18002002c  mov     [rbp+var_40], r8
0x180020030  cmp     r10d, r9d
0x180020033  jb      loc_1800203FB
0x180020039  jz      loc_1800203F2
0x18002003f  mov     rax, r8
0x180020042  shr     rax, 20h
0x180020046  cmp     r10d, eax
0x180020049  jnb     loc_180020244
0x18002004f  mov     rdi, [rbp+var_50]
0x180020053  test    esi, esi
0x180020055  jnz     loc_18002043D
0x18002005b  xor     eax, eax
0x18002005d  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x180020065  jnz     loc_180020557
0x18002006b  lea     rcx, stru_1800A45E0; lpCriticalSection
0x180020072  call    cs:__imp_LeaveCriticalSection
0x180020079  nop     dword ptr [rax+rax+00h]
0x18002007e  test    esi, esi
0x180020080  jnz     loc_18002053F
0x180020086  mov     eax, esi
0x180020088  jmp     short loc_18002009E
0x18002008a  xor     ebx, ebx
0x18002008c  xor     eax, eax
0x18002008e  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x180020096  jnz     loc_180020315
0x18002009c  xor     eax, eax
0x18002009e  mov     rcx, [rbp+var_10]
0x1800200a2  xor     rcx, rsp; StackCookie
0x1800200a5  call    __security_check_cookie
0x1800200aa  add     rsp, 78h
0x1800200ae  pop     r15
0x1800200b0  pop     r14
0x1800200b2  pop     rdi
0x1800200b3  pop     rsi
0x1800200b4  pop     rbx
0x1800200b5  pop     rbp
0x1800200b6  retn
0x1800200b8  xor     ebx, ebx
0x1800200ba  xor     eax, eax
0x1800200bc  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x1800200c4  jz      short loc_18002009C
0x1800200c6  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800200cd  test    rcx, rcx
0x1800200d0  jz      short loc_18002009C
0x1800200d2  cmp     [rcx+13Bh], bl
0x1800200d8  jz      short loc_18002009C
0x1800200da  add     rcx, 50h ; 'P'; Resource
0x1800200de  mov     dl, 1; Wait
0x1800200e0  call    cs:__imp_RtlAcquireResourceShared
0x1800200e7  nop     dword ptr [rax+rax+00h]
0x1800200ec  test    al, al
0x1800200ee  jz      short loc_18002009C
0x1800200f0  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800200f7  mov     rdx, [r8+18h]
0x1800200fb  test    rdx, rdx
0x1800200fe  jz      loc_1800202E4
0x180020104  mov     ecx, [rdx]
0x180020106  cmp     ecx, 3EBh
0x18002010c  ja      loc_1800202E4
0x180020112  add     ecx, [rdx+4]
0x180020115  cmp     ecx, 3EBh
0x18002011b  ja      loc_1800202E2
0x180020121  mov     rdx, [rdx+8]
0x180020125  jmp     short loc_1800200FB
0x180020127  jnz     short loc_180020140
0x180020129  cmp     dword ptr cs:xmmword_1800A46D8, 24C8000h
0x180020133  mov     eax, ebx
0x180020135  setnbe  al
0x180020138  test    eax, eax
0x18002013a  jnz     loc_18001FEFE
0x180020140  mov     ecx, 3EBh
0x180020145  call    FileLogAllowEntry
0x18002014a  test    al, al
0x18002014c  jz      loc_18002005B
0x180020152  lea     rcx, aSecureTimeValu; "Secure Time value is invalid.  Not usin"...
0x180020159  call    FileLogAdd
0x18002015e  jmp     loc_18002005B
0x180020163  mov     ecx, 3EBh
0x180020168  call    FileLogAllowEntry
0x18002016d  test    al, al
0x18002016f  jz      loc_18002009C
0x180020175  mov     edx, esi
0x180020177  lea     rcx, aFailedToReadSe_1; "Failed to read secure time from the reg"...
0x18002017e  call    FileLogAdd
0x180020183  jmp     loc_18002009C
0x180020188  jnz     short loc_180020140
0x18002018a  cmp     dword ptr cs:xmmword_1800A46D8+8, 24C8000h
0x180020194  mov     eax, ebx
0x180020196  setnbe  al
0x180020199  test    eax, eax
0x18002019b  jz      short loc_180020140
0x18002019d  jmp     loc_18001FEEE
0x1800201a2  mov     ecx, 3EBh
0x1800201a7  call    FileLogAllowEntry
0x1800201ac  test    al, al
0x1800201ae  jz      loc_18002009C
0x1800201b4  lea     rcx, aSecureTimeEnfo_0; "Secure time enforcement skipped this ti"...
0x1800201bb  call    FileLogAdd
0x1800201c0  jmp     loc_18002009C
0x1800201c5  mov     rcx, qword ptr cs:xmmword_1800A46C8+8
0x1800201cc  neg     r10
0x1800201cf  mov     rdx, qword ptr cs:xmmword_1800A46D8
0x1800201d6  mov     rax, rdx
0x1800201d9  cmp     rcx, r10
0x1800201dc  jb      loc_180020273
0x1800201e2  sub     rcx, r10
0x1800201e5  mov     qword ptr cs:xmmword_1800A46C8+8, rcx
0x1800201ec  cmp     rax, r10
0x1800201ef  jb      loc_180020282
0x1800201f5  mov     rax, qword ptr cs:xmmword_1800A46D8+8
0x1800201fc  sub     rdx, r10
0x1800201ff  mov     qword ptr cs:xmmword_1800A46D8, rdx
0x180020206  mov     r8, rax
0x180020209  sub     rax, r10
0x18002020c  mov     rdi, rbx
0x18002020f  cmp     r8, r10
0x180020212  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180020219  cmovnb  rdi, rax
0x18002021d  jmp     loc_18001FFE3
0x180020222  jnz     loc_180020140
0x180020228  cmp     dword ptr cs:xmmword_1800A46C8+8, 24C8000h
0x180020232  mov     eax, ebx
  ... truncated ...
```
