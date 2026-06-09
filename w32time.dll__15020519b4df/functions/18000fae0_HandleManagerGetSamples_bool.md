# HandleManagerGetSamples(bool)

- ea: `0x18000fae0`
- end: `0x180010398`
- name: `?HandleManagerGetSamples@@YAJ_N@Z`
- size: `2232`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f150`

## callees

- `0x180003ac0`
- `0x18000a41c`
- `0x18000a7e0`
- `0x18000f5f0`
- `0x18000fae0`
- `0x1800103a0`
- `0x180010b74`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x18002aca4`
- `0x18002e044`
- `0x18003d270`
- `0x18004c890`
- `0x18004efac`
- `0x18004f058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000fd63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000fd63`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fbd5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fca3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fbd5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fca3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fc55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fccc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fd38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fc55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fccc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fd38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fb84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcdc`
- `ntdll!RtlReleaseResource` at `0x180010127`
- `ntdll!RtlReleaseResource` at `0x180010127`
- `ntdll!RtlAcquireResourceShared` at `0x1800100e6`
- `ntdll!RtlAcquireResourceShared` at `0x1800100e6`
- `ntdll!RtlInitUnicodeString` at `0x18000fea2`
- `ntdll!RtlInitUnicodeString` at `0x180010300`
- `ntdll!RtlInitUnicodeString` at `0x18000fea2`
- `ntdll!RtlInitUnicodeString` at `0x180010300`

## string_xrefs

- `0x1800102e5`: `Logging warning: The time service has jumped the local system clock by %s seconds. This occurs when the time source and local system time are far enough apart that clock rate adjustments cannot be made to reach the time specified by the time source.\n`
- `0x180010340`: `Logging warning: The time service detected a time difference of greater than %ld milliseconds for %ld seconds.  The system clock is unsynchronized.  This is usually caused by synchronizing from low-accuracy time sources, or by poor network conditions.\n`
- `0x180010371`: `Logging error: The time service has detected that the system time need to be changed by -%I64u seconds. For security reasons, the time service will not change the system time by more than -%u seconds. Verify that your time and time zone are correct, and that the time source %s is working properly.\n`
- `0x18001037a`: `Logging error: The time service has detected that the system time need to be changed by +%I64u seconds. For security reasons, the time service will not change the system time by more than +%u seconds. Verify that your time and time zone are correct, and that the time source %s is working properly.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HandleManagerGetSamples(char a1)
{
  bool v2; // si
  int TimeSamples; // ebx
  unsigned int v4; // r15d
  signed int LastError; // eax
  signed int v7; // eax
  DWORD v8; // eax
  char v9; // cl
  __int64 v10; // rbx
  unsigned int v11; // esi
  __int64 k; // rsi
  __int64 v13; // r15
  char v14; // r9
  __int64 v15; // rdx
  BYTE *pbSampleBuf; // rax
  char *v17; // rcx
  __int64 v18; // rdx
  __int128 v19; // xmm0
  char v20; // bl
  __int64 i; // rdx
  __int64 v22; // rcx
  unsigned int j; // r12d
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  const unsigned __int16 *v29; // r8
  unsigned int v30; // esi
  __int64 bAlertable; // [rsp+20h] [rbp-79h]
  bool v32; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v33; // [rsp+34h] [rbp-65h] BYREF
  struct TpcGetMetaDataSamplesArgs DestinationString; // [rsp+38h] [rbp-61h] BYREF
  struct TpcGetSamplesArgs Handles; // [rsp+50h] [rbp-49h] BYREF
  WCHAR SourceString[40]; // [rsp+70h] [rbp-29h] BYREF

  memset(&Handles, 0, sizeof(Handles));
  v33 = 0;
  v2 = 1;
  memset(&DestinationString, 0, sizeof(DestinationString));
  EnterCriticalSection(&CriticalSection);
  if ( !byte_1800A45A0 )
  {
    TimeSamples = GetTimeSamples(&Handles, &v33);
    if ( TimeSamples >= 0 )
    {
      v4 = v33;
      v2 = 0;
      v32 = 0;
      if ( !v33 )
        goto LABEL_4;
      TimeSamples = SelectBestSample(v33, &v32);
      if ( TimeSamples >= 0 )
      {
        v2 = v32;
        goto LABEL_4;
      }
    }
LABEL_12:
    LeaveCriticalSection(&CriticalSection);
    return (unsigned int)TimeSamples;
  }
  TimeSamples = GetMetaDataSamples(&DestinationString, &v33);
  if ( TimeSamples < 0 )
    goto LABEL_12;
  if ( DestinationString.dwSamplesReturned == 1 )
  {
    pbSampleBuf = DestinationString.pbSampleBuf;
    v17 = byte_1800A4380;
    v18 = 4;
    do
    {
      v17 += 128;
      v19 = *(_OWORD *)pbSampleBuf;
      pbSampleBuf += 128;
      *((_OWORD *)v17 - 8) = v19;
      *((_OWORD *)v17 - 7) = *((_OWORD *)pbSampleBuf - 7);
      *((_OWORD *)v17 - 6) = *((_OWORD *)pbSampleBuf - 6);
      *((_OWORD *)v17 - 5) = *((_OWORD *)pbSampleBuf - 5);
      *((_OWORD *)v17 - 4) = *((_OWORD *)pbSampleBuf - 4);
      *((_OWORD *)v17 - 3) = *((_OWORD *)pbSampleBuf - 3);
      *((_OWORD *)v17 - 2) = *((_OWORD *)pbSampleBuf - 2);
      *((_OWORD *)v17 - 1) = *((_OWORD *)pbSampleBuf - 1);
      --v18;
    }
    while ( v18 );
    *(_OWORD *)v17 = *(_OWORD *)pbSampleBuf;
    *((_OWORD *)v17 + 1) = *((_OWORD *)pbSampleBuf + 1);
  }
  v4 = v33;
LABEL_4:
  LeaveCriticalSection(&CriticalSection);
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
    && _pflstate
    && *((_BYTE *)_pflstate + 315)
    && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    v20 = 0;
    for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x6Eu; i = *(_QWORD *)(i + 8) )
    {
      if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x6E )
      {
        v20 = 1;
        break;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    if ( v20 )
    {
      if ( byte_1800A45A0 )
      {
        FileLogAdd(L"Metadata sample stratum:%d dispersion:", (unsigned __int8)byte_1800A4399);
        FileLogNtTimePeriodEx(v22, qword_1800A4388);
        FileLogAppend(L"\n");
      }
      else
      {
        for ( j = 0; j < v4; ++j )
        {
          if ( j >= dword_1800A45A4 )
            break;
          v24 = 568LL * j;
          v25 = *(_QWORD *)((char *)Src + v24 + 8);
          FileLogAdd(L"Sample %d offset:", j);
          FileLogNtTimeOffsetEx(v26, v25);
          FileLogAppend(L" delay:");
          FileLogNtTimeOffsetEx(v27, *(_QWORD *)((char *)Src + v24 + 16));
          FileLogAppend(L" dispersion:");
          FileLogNtTimePeriodEx(v28, *(_QWORD *)((char *)Src + v24 + 24));
          FileLogAppend(L"\n");
        }
      }
    }
  }
  if ( v2 )
  {
    Handles.pbSampleBuf = (BYTE *)qword_1800A36D8;
    *(_QWORD *)&Handles.cbSampleBuf = hThread;
    if ( !hThread )
      return (unsigned int)-2147467260;
    dword_1800A3AA8 = (a1 != 0) + 2;
    if ( !SetEvent(qword_1800A36D0) )
      goto LABEL_9;
    v8 = WaitForMultipleObjectsEx(2u, (const HANDLE *)&Handles.pbSampleBuf, 0, 0xFFFFFFFF, 0);
    if ( v8 == -1 )
      goto LABEL_9;
    if ( !v8 )
    {
      TimeSamples = UpdateNetlogonServiceBits(1);
      if ( TimeSamples < 0 )
        return (unsigned int)TimeSamples;
      if ( byte_1800A3AB9 == 1 )
      {
        dword_1800A4690 = 2;
      }
      else if ( byte_1800A3ABA == 1 )
      {
        dword_1800A4690 = 4;
      }
      else
      {
        dword_1800A4690 = 0;
        qword_1800A4330 = 0;
      }
      if ( byte_1800A3CC8 )
        MyLogSourceChangeEvent(&qword_1800A3AC8, dword_1800A3818, dword_1800A3814, dword_1800A45B8);
      if ( byte_1800A3AAC && (dword_1800A45B8 & 1) != 0 )
      {
        if ( qword_1800A3AB0 < gc_toZero )
        {
          v14 = 1;
          v15 = ((unsigned __int128)(qword_1800A3AB0 * (__int128)0x29406B2A1A85BD43LL) >> 64) - qword_1800A3AB0;
        }
        else
        {
          v14 = 0;
          v15 = qword_1800A3AB0
              + ((unsigned __int128)(qword_1800A3AB0 * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64);
        }
        v29 = L"-%I64u";
        if ( !v14 )
          v29 = L"+%I64u";
        StringCchPrintfW(SourceString, 0x23u, v29, ((unsigned __int64)v15 >> 63) + (v15 >> 23));
        if ( (unsigned __int8)FileLogAllowEntry(16) )
          FileLogAdd(
            L"Logging warning: The time service has jumped the local system clock by %s seconds. This occurs when the time"
             " source and local system time are far enough apart that clock rate adjustments cannot be made to reach the "
             "time specified by the time source.\n",
            SourceString);
        *(_OWORD *)&DestinationString.pbSampleBuf = 0;
        RtlInitUnicodeString((PUNICODE_STRING)&DestinationString, SourceString);
        TimeSamples = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIME_JUMPED, L"u", &DestinationString);
        if ( TimeSamples < 0 )
          return (unsigned int)TimeSamples;
      }
      if ( byte_1800A3CCA )
      {
        if ( (unsigned __int8)FileLogAllowEntry(16) )
          FileLogAdd(
            L"Logging warning: The time service detected a time difference of greater than %ld milliseconds for %ld second"
             "s.  The system clock is unsynchronized.  This is usually caused by synchronizing from low-accuracy time sou"
             "rces, or by poor network conditions.\n",
            *((_DWORD *)qword_1800A42F0 + 22) / 0x2710u,
            *((unsigned int *)qword_1800A42F0 + 23));
        LODWORD(bAlertable) = *((_DWORD *)qword_1800A42F0 + 23);
        TimeSamples = LogEvent(&_W32TimeRegistrationHandle, "2", L"dd", *((_DWORD *)qword_1800A42F0 + 22) / 0x2710u);
        if ( TimeSamples < 0 )
          return (unsigned int)TimeSamples;
        if ( byte_1800A3CCA )
          goto LABEL_36;
      }
      if ( byte_1800A3CCB )
      {
LABEL_36:
        qword_1800A4328 = 0;
        qword_1800A4310 = 10000000 * (1LL << dword_1800A381C);
        qword_1800A4330 = 0;
        qword_1800A4320 = 160000000;
      }
      v9 = byte_1800A45B4;
      if ( byte_1800A3ABA == 1 && !byte_1800A45B4 )
      {
        *(_OWORD *)&DestinationString.pbSampleBuf = 0;
        RtlInitUnicodeString((PUNICODE_STRING)&DestinationString, &::SourceString);
        v10 = qword_1800A3AC0 / 10000000;
        if ( qword_1800A3AC0 < gc_toZero )
        {
          v30 = *((_DWORD *)qword_1800A42F0 + 29);
          if ( (unsigned __int8)FileLogAllowEntry(16) )
            FileLogAdd(
              L"Logging error: The time service has detected that the system time need to be changed by -%I64u seconds. Fo"
               "r security reasons, the time service will not change the system time by more than -%u seconds. Verify tha"
               "t your time and time zone are correct, and that the time source %s is working properly.\n",
              v10,
              v30,
              &::SourceString,
              bAlertable);
        }
        else
        {
          v11 = *((_DWORD *)qword_1800A42F0 + 30);
          if ( (unsigned __int8)FileLogAllowEntry(16) )
            FileLogAdd(
              L"Logging error: The time service has detected that the system time need to be changed by +%I64u seconds. Fo"
               "r security reasons, the time service will not change the system time by more than +%u seconds. Verify tha"
               "t your time and time zone are correct, and that the time source %s is working properly.\n",
              v10,
              v11,
              &::SourceString,
              bAlertable);
        }
        TimeSamples = LogEvent(&_W32TimeRegistrationHandle, "\"", L"Idu", v10);
        if ( TimeSamples < 0 )
          return (unsigned int)TimeSamples;
        v9 = 1;
        byte_1800A45B4 = 1;
      }
      if ( !byte_1800A3AB9 && !byte_1800A3ABA && v9 == 1 )
        byte_1800A45B4 = 0;
      if ( byte_1800A3AB8 || byte_1800A3AAC )
      {
        TimeSamples = 0;
        for ( k = *(_QWORD *)qword_1800A42F0; k; k = v13 )
        {
          if ( byte_1800A3AAC )
          {
            v33 = 0;
            TimeSamples = SendNotificationToProvider((struct TimeProvider *)k, TPC_TimeJumped, &v33);
          }
          if ( TimeSamples >= 0 && byte_1800A3AB8 )
            TimeSamples = SendNotificationToProvider((struct TimeProvider *)k, TPC_PollIntervalChanged, 0);
          v13 = *(_QWORD *)(k + 24);
          if ( TimeSamples < 0 || *(_BYTE *)(k + 68) == 1 && !*(_DWORD *)(k + 72) )
          {
            TimeSamples = RemoveProviderFromList((struct TimeProvider *)k, 1, 0);
            if ( TimeSamples < 0 )
              return (unsigned int)TimeSamples;
          }
        }
      }
    }
  }
  else
  {
    dword_1800A4690 = 1;
  }
  if ( hHandle == qword_1800A3700 )
  {
    if ( ResetEvent(qword_1800A3708) )
    {
      hHandle = qword_1800A3708;
      if ( SetEvent(qword_1800A3700) )
        goto LABEL_14;
    }
    goto LABEL_9;
  }
  if ( !ResetEvent(qword_1800A3700) )
  {
LABEL_9:
    LastError = GetLastError();
    TimeSamples = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)TimeSamples;
  }
  hHandle = qword_1800A3700;
  if ( SetEvent(qword_1800A3708) )
  {
LABEL_14:
    if ( !a1 )
    {
      qword_1800A4310 = 10000000 * (1LL << dword_1800A381C);
      dword_1800A45AC = dword_1800A4690;
    }
    qword_1800A4320 = 0;
    TimeSamples = 0;
    qword_1800A4328 = 0;
    return (unsigned int)TimeSamples;
  }
  v7 = GetLastError();
  TimeSamples = v7;
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)TimeSamples;
}

```

## disassembly

```asm
0x18000fae0  mov     [rsp-8+arg_8], rbx
0x18000fae5  mov     [rsp-8+arg_10], rsi
0x18000faea  push    rbp
0x18000faeb  push    rdi
0x18000faec  push    r13
0x18000faee  push    r14
0x18000faf0  push    r15
0x18000faf2  lea     rbp, [rsp-37h]
0x18000faf7  sub     rsp, 0D0h
0x18000fafe  mov     rax, cs:__security_cookie
0x18000fb05  xor     rax, rsp
0x18000fb08  mov     [rbp+57h+var_30], rax
0x18000fb0c  xor     eax, eax
0x18000fb0e  movzx   r14d, cl
0x18000fb12  xorps   xmm0, xmm0
0x18000fb15  mov     [rbp+57h+var_90], rax
0x18000fb19  xorps   xmm1, xmm1
0x18000fb1c  mov     [rbp+57h+var_A8], rax
0x18000fb20  xor     r13d, r13d
0x18000fb23  lea     rcx, CriticalSection; lpCriticalSection
0x18000fb2a  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x18000fb2e  mov     [rbp+57h+var_BC], r13d
0x18000fb32  mov     sil, 1
0x18000fb35  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000fb39  call    cs:__imp_EnterCriticalSection
0x18000fb40  nop     dword ptr [rax+rax+00h]
0x18000fb45  cmp     cs:byte_1800A45A0, r13b
0x18000fb4c  lea     rdx, [rbp+57h+var_BC]; unsigned int *
0x18000fb50  jnz     loc_180010011
0x18000fb56  lea     rcx, [rbp+57h+Handles]; struct TpcGetSamplesArgs *
0x18000fb5a  call    ?GetTimeSamples@@YAJPEAUTpcGetSamplesArgs@@PEAI@Z; GetTimeSamples(TpcGetSamplesArgs *,uint *)
0x18000fb5f  mov     ebx, eax
0x18000fb61  test    eax, eax
0x18000fb63  js      loc_18000FC2B
0x18000fb69  mov     r15d, [rbp+57h+var_BC]
0x18000fb6d  xor     sil, sil
0x18000fb70  mov     [rbp+57h+var_C0], sil
0x18000fb74  test    r15d, r15d
0x18000fb77  jnz     loc_1800100A4
0x18000fb7d  lea     rcx, CriticalSection; lpCriticalSection
0x18000fb84  call    cs:__imp_LeaveCriticalSection
0x18000fb8b  nop     dword ptr [rax+rax+00h]
0x18000fb90  mov     ecx, r13d
0x18000fb93  xor     eax, eax
0x18000fb95  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000fb9d  jnz     loc_1800100C3
0x18000fba3  mov     edi, 1
0x18000fba8  test    sil, sil
0x18000fbab  jnz     loc_18000FD00
0x18000fbb1  mov     cs:dword_1800A4690, edi
0x18000fbb7  mov     rax, cs:hHandle
0x18000fbbe  mov     rcx, cs:qword_1800A3700; hEvent
0x18000fbc5  cmp     rax, rcx
0x18000fbc8  jnz     loc_18000FCA3
0x18000fbce  mov     rcx, cs:qword_1800A3708; hEvent
0x18000fbd5  call    cs:__imp_ResetEvent
0x18000fbdc  nop     dword ptr [rax+rax+00h]
0x18000fbe1  test    eax, eax
0x18000fbe3  jnz     short loc_18000FC40
0x18000fbe5  call    cs:__imp_GetLastError
0x18000fbec  nop     dword ptr [rax+rax+00h]
0x18000fbf1  mov     ebx, eax
0x18000fbf3  test    eax, eax
0x18000fbf5  jle     short loc_18000FC00
0x18000fbf7  movzx   ebx, ax
0x18000fbfa  or      ebx, 80070000h
0x18000fc00  mov     eax, ebx
0x18000fc02  mov     rcx, [rbp+57h+var_30]
0x18000fc06  xor     rcx, rsp; StackCookie
0x18000fc09  call    __security_check_cookie
0x18000fc0e  lea     r11, [rsp+0F0h+var_20]
0x18000fc16  mov     rbx, [r11+38h]
0x18000fc1a  mov     rsi, [r11+40h]
0x18000fc1e  mov     rsp, r11
0x18000fc21  pop     r15
0x18000fc23  pop     r14
0x18000fc25  pop     r13
0x18000fc27  pop     rdi
0x18000fc28  pop     rbp
0x18000fc29  retn
0x18000fc2b  lea     rcx, CriticalSection; lpCriticalSection
0x18000fc32  call    cs:__imp_LeaveCriticalSection
0x18000fc39  nop     dword ptr [rax+rax+00h]
0x18000fc3e  jmp     short loc_18000FC00
0x18000fc40  mov     rax, cs:qword_1800A3708
0x18000fc47  mov     rcx, cs:qword_1800A3700; hEvent
0x18000fc4e  mov     cs:hHandle, rax
0x18000fc55  call    cs:__imp_SetEvent
0x18000fc5c  nop     dword ptr [rax+rax+00h]
0x18000fc61  test    eax, eax
0x18000fc63  jz      short loc_18000FBE5
0x18000fc65  test    r14b, r14b
0x18000fc68  jnz     short loc_18000FC8D
0x18000fc6a  mov     ecx, cs:dword_1800A381C
0x18000fc70  shl     rdi, cl
0x18000fc73  imul    rax, rdi, 989680h
0x18000fc7a  mov     cs:qword_1800A4310, rax
0x18000fc81  mov     eax, cs:dword_1800A4690
0x18000fc87  mov     cs:dword_1800A45AC, eax
0x18000fc8d  mov     cs:qword_1800A4320, r13
0x18000fc94  mov     ebx, r13d
0x18000fc97  mov     cs:qword_1800A4328, r13
0x18000fc9e  jmp     loc_18000FC00
0x18000fca3  call    cs:__imp_ResetEvent
0x18000fcaa  nop     dword ptr [rax+rax+00h]
0x18000fcaf  test    eax, eax
0x18000fcb1  jz      loc_18000FBE5
0x18000fcb7  mov     rax, cs:qword_1800A3700
0x18000fcbe  mov     rcx, cs:qword_1800A3708; hEvent
0x18000fcc5  mov     cs:hHandle, rax
0x18000fccc  call    cs:__imp_SetEvent
0x18000fcd3  nop     dword ptr [rax+rax+00h]
0x18000fcd8  test    eax, eax
0x18000fcda  jnz     short loc_18000FC65
0x18000fcdc  call    cs:__imp_GetLastError
0x18000fce3  nop     dword ptr [rax+rax+00h]
0x18000fce8  mov     ebx, eax
0x18000fcea  test    eax, eax
0x18000fcec  jle     loc_18000FC00
0x18000fcf2  movzx   ebx, ax
0x18000fcf5  or      ebx, 80070000h
0x18000fcfb  jmp     loc_18000FC00
0x18000fd00  mov     rax, cs:qword_1800A36D8
0x18000fd07  mov     [rbp+57h+Handles], rax
0x18000fd0b  mov     rax, cs:hThread
0x18000fd12  mov     [rbp+57h+Handles+8], rax
0x18000fd16  test    rax, rax
0x18000fd19  jz      loc_18001021D
0x18000fd1f  mov     rcx, cs:qword_1800A36D0; hEvent
0x18000fd26  mov     eax, r13d
0x18000fd29  test    r14b, r14b
0x18000fd2c  setnz   al
0x18000fd2f  add     eax, 2
0x18000fd32  mov     cs:dword_1800A3AA8, eax
0x18000fd38  call    cs:__imp_SetEvent
0x18000fd3f  nop     dword ptr [rax+rax+00h]
0x18000fd44  test    eax, eax
0x18000fd46  jz      loc_18000FBE5
0x18000fd4c  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000fd52  mov     dword ptr [rsp+0F0h+bAlertable], r13d; bAlertable
0x18000fd57  xor     r8d, r8d; bWaitAll
0x18000fd5a  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000fd5e  mov     ecx, 2; nCount
0x18000fd63  call    cs:__imp_WaitForMultipleObjectsEx
0x18000fd6a  nop     dword ptr [rax+rax+00h]
0x18000fd6f  cmp     eax, 0FFFFFFFFh
0x18000fd72  jz      loc_18000FBE5
0x18000fd78  test    eax, eax
0x18000fd7a  jnz     loc_18000FBB7
0x18000fd80  movzx   ecx, dil; bool
0x18000fd84  call    ?UpdateNetlogonServiceBits@@YAJ_N@Z; UpdateNetlogonServiceBits(bool)
0x18000fd89  mov     ebx, eax
0x18000fd8b  test    eax, eax
0x18000fd8d  js      loc_18000FC00
0x18000fd93  cmp     cs:byte_1800A3AB9, dil
0x18000fd9a  jnz     loc_180010227
0x18000fda0  mov     cs:dword_1800A4690, 2
0x18000fdaa  cmp     cs:byte_1800A3CC8, r13b
0x18000fdb1  jnz     loc_180010252
0x18000fdb7  cmp     cs:byte_1800A3AAC, r13b
0x18000fdbe  mov     rsi, 0D6BF94D5E57A42BDh
0x18000fdc8  jnz     loc_180010277
0x18000fdce  cmp     cs:byte_1800A3CCA, r13b
0x18000fdd5  jz      loc_18000FE6B
0x18000fddb  mov     ecx, 10h
0x18000fde0  call    FileLogAllowEntry
0x18000fde5  test    al, al
0x18000fde7  jnz     loc_180010339
0x18000fded  mov     rcx, cs:qword_1800A42F0
0x18000fdf4  lea     r8, aDd; "dd"
0x18000fdfb  mov     eax, 0D1B71759h
0x18000fe00  mul     dword ptr [rcx+58h]
0x18000fe03  mov     eax, [rcx+5Ch]
0x18000fe06  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000fe0d  shr     edx, 0Dh
0x18000fe10  mov     r9d, edx
0x18000fe13  mov     dword ptr [rsp+0F0h+bAlertable], eax
0x18000fe17  lea     rdx, W32TIME_EVENT_LOCALCLOCK_UNSET; "2"
0x18000fe1e  call    LogEvent
0x18000fe23  mov     ebx, eax
0x18000fe25  test    eax, eax
0x18000fe27  js      loc_18000FC00
0x18000fe2d  cmp     cs:byte_1800A3CCA, r13b
0x18000fe34  jz      short loc_18000FE6B
0x18000fe36  mov     ecx, cs:dword_1800A381C
0x18000fe3c  mov     rax, rdi
0x18000fe3f  shl     rax, cl
0x18000fe42  imul    rax, 989680h
0x18000fe49  mov     cs:qword_1800A4328, r13
0x18000fe50  mov     cs:qword_1800A4310, rax
0x18000fe57  mov     cs:qword_1800A4330, r13
0x18000fe5e  mov     cs:qword_1800A4320, 9896800h
0x18000fe69  jmp     short loc_18000FE74
0x18000fe6b  cmp     cs:byte_1800A3CCB, r13b
0x18000fe72  jnz     short loc_18000FE36
0x18000fe74  cmp     cs:byte_1800A3ABA, dil
0x18000fe7b  movzx   ecx, cs:byte_1800A45B4
0x18000fe82  jnz     loc_18000FF34
0x18000fe88  test    cl, cl
0x18000fe8a  jnz     loc_18000FF34
0x18000fe90  xorps   xmm0, xmm0
0x18000fe93  lea     rdx, SourceString; SourceString
0x18000fe9a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000fe9e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000fea2  call    cs:__imp_RtlInitUnicodeString
0x18000fea9  nop     dword ptr [rax+rax+00h]
0x18000feae  mov     r8, cs:qword_1800A3AC0
0x18000feb5  mov     rax, rsi
0x18000feb8  imul    r8
0x18000febb  mov     ecx, 10h
0x18000fec0  lea     rbx, [r8+rdx]
0x18000fec4  sar     rbx, 17h
0x18000fec8  mov     rax, rbx
0x18000fecb  shr     rax, 3Fh
0x18000fecf  add     rbx, rax
0x18000fed2  mov     rax, cs:qword_1800A42F0
0x18000fed9  cmp     r8, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18000fee0  jl      loc_180010361
0x18000fee6  mov     esi, [rax+78h]
0x18000fee9  call    FileLogAllowEntry
0x18000feee  test    al, al
0x18000fef0  jnz     loc_18001037A
0x18000fef6  lea     rax, [rbp+57h+DestinationString]
0x18000fefa  mov     r9, rbx
0x18000fefd  mov     [rsp+0F0h+var_C8], rax
0x18000ff02  lea     r8, aIdu; "Idu"
0x18000ff09  lea     rdx, W32TIME_EVENT_TIME_CHANGE_TOO_BIG; "\""
0x18000ff10  mov     dword ptr [rsp+0F0h+bAlertable], esi
0x18000ff14  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x18000ff1b  call    LogEvent
0x18000ff20  mov     ebx, eax
0x18000ff22  test    eax, eax
0x18000ff24  js      loc_18000FC00
0x18000ff2a  movzx   ecx, dil
0x18000ff2e  mov     cs:byte_1800A45B4, cl
0x18000ff34  cmp     cs:byte_1800A3AB9, r13b
0x18000ff3b  jnz     short loc_18000FF52
0x18000ff3d  cmp     cs:byte_1800A3ABA, r13b
0x18000ff44  jnz     short loc_18000FF52
0x18000ff46  cmp     cl, dil
0x18000ff49  jnz     short loc_18000FF52
0x18000ff4b  mov     cs:byte_1800A45B4, r13b
0x18000ff52  cmp     cs:byte_1800A3AB8, r13b
0x18000ff59  jnz     short loc_18000FF68
0x18000ff5b  cmp     cs:byte_1800A3AAC, r13b
0x18000ff62  jz      loc_18000FBB7
0x18000ff68  mov     rax, cs:qword_1800A42F0
0x18000ff6f  mov     ebx, r13d
0x18000ff72  mov     rsi, [rax]
0x18000ff75  test    rsi, rsi
0x18000ff78  jz      loc_18000FBB7
0x18000ff7e  cmp     cs:byte_1800A3AAC, r13b
0x18000ff85  jz      short loc_18000FF9B
0x18000ff87  lea     r8, [rbp+57h+var_BC]; void *
0x18000ff8b  mov     [rbp+57h+var_BC], r13d
0x18000ff8f  xor     edx, edx; enum TimeProvCmd
0x18000ff91  mov     rcx, rsi; struct TimeProvider *
0x18000ff94  call    ?SendNotificationToProvider@@YAJPEAUTimeProvider@@W4TimeProvCmd@@PEAX@Z; SendNotificationToProvider(TimeProvider *,TimeProvCmd,void *)
0x18000ff99  mov     ebx, eax
0x18000ff9b  test    ebx, ebx
0x18000ff9d  js      short loc_18000FFBA
0x18000ff9f  cmp     cs:byte_1800A3AB8, r13b
0x18000ffa6  jz      short loc_18000FFBA
0x18000ffa8  xor     r8d, r8d; void *
0x18000ffab  mov     edx, 2; enum TimeProvCmd
0x18000ffb0  mov     rcx, rsi; struct TimeProvider *
0x18000ffb3  call    ?SendNotificationToProvider@@YAJPEAUTimeProvider@@W4TimeProvCmd@@PEAX@Z; SendNotificationToProvider(TimeProvider *,TimeProvCmd,void *)
0x18000ffb8  mov     ebx, eax
0x18000ffba  mov     r15, [rsi+18h]
0x18000ffbe  test    ebx, ebx
0x18000ffc0  js      short loc_18000FFCE
0x18000ffc2  cmp     [rsi+44h], dil
0x18000ffc6  jnz     short loc_18000FFE7
0x18000ffc8  cmp     [rsi+48h], r13d
0x18000ffcc  jnz     short loc_18000FFE7
0x18000ffce  xor     r8d, r8d; bool *
0x18000ffd1  movzx   edx, dil; bool
0x18000ffd5  mov     rcx, rsi; struct TimeProvider *
0x18000ffd8  call    ?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z; RemoveProviderFromList(TimeProvider *,bool,bool *)
0x18000ffdd  mov     ebx, eax
0x18000ffdf  test    eax, eax
0x18000ffe1  js      loc_18000FC00
0x18000ffe7  mov     rsi, r15
0x18000ffea  jmp     short loc_18000FF75
0x18000ffec  mov     rcx, cs:qword_1800A3AB0
0x18000fff3  cmp     rcx, cs:?gc_toZero@@3UNtTimeOffset@@B; NtTimeOffset const gc_toZero
0x18000fffa  jl      loc_18001028B
0x180010000  mov     rax, rsi
0x180010003  xor     r9b, r9b
0x180010006  imul    rcx
0x180010009  add     rdx, rcx
0x18001000c  jmp     loc_18001029F
0x180010011  lea     rcx, [rbp+57h+DestinationString]; struct TpcGetMetaDataSamplesArgs *
0x180010015  call    ?GetMetaDataSamples@@YAJPEAUTpcGetMetaDataSamplesArgs@@PEAI@Z; GetMetaDataSamples(TpcGetMetaDataSamplesArgs *,uint *)
0x18001001a  mov     ebx, eax
0x18001001c  test    eax, eax
0x18001001e  js      loc_18000FC2B
0x180010024  cmp     dword ptr [rbp+57h+DestinationString.Buffer+4], 1
0x180010028  jnz     short loc_18001009B
0x18001002a  mov     rax, qword ptr [rbp+57h+DestinationString.Length]
  ... truncated ...
```
