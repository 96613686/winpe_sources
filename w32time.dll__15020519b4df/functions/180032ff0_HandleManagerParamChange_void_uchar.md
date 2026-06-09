# HandleManagerParamChange(void *,uchar)

- ea: `0x180032ff0`
- end: `0x180033969`
- name: `?HandleManagerParamChange@@YAXPEAXE@Z`
- size: `2425`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800123b0`
- `0x180037540`

## callees

- `0x180008930`
- `0x180009204`
- `0x180009238`
- `0x18000a7e0`
- `0x18000c91c`
- `0x18000ca10`
- `0x18000e758`
- `0x18000f400`
- `0x18000f5f0`
- `0x180010b74`
- `0x180011120`
- `0x180018138`
- `0x180019400`
- `0x18001a780`
- `0x18001b850`
- `0x18001d9a0`
- `0x180021170`
- `0x18002aca4`
- `0x18002ca84`
- `0x18002dca4`
- `0x180032ff0`
- `0x18003f485`
- `0x18004c3b8`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003303c`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800338a5`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003303c`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800338a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800338cd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180033402`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180033402`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800333b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800333b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033070`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033412`
- `ntdll!RtlInitUnicodeString` at `0x18003311f`
- `ntdll!RtlInitUnicodeString` at `0x18003311f`

## string_xrefs

- `0x1800336d8`: `Logging error: The time service has been configured to use one or more input providers, however, none of the input providers could be started. THE TIME SERVICE HAS NO SOURCE OF ACCURATE TIME.\n`
- `0x18003305d`: `W32TmServiceMain: Param change notification\n`
- `0x180033101`: `Logging warning: The time service encountered an error while reading its configuration from the registry, and will continue running with its previous configuration. The error was: %s\n`
- `0x180033468`: `Parameter change before list is updated`
- `0x18003348e`: `Parameter change before list is updated`
- `0x18003369e`: `Parameter change after list is updated`
- `0x180033938`: `Failed in handling parameter change, restart service async`

## pseudocode

```c
void __fastcall HandleManagerParamChange(void *a1)
{
  unsigned int v1; // r12d
  unsigned int v2; // r15d
  signed int updated; // edi
  DWORD v4; // eax
  signed int v5; // eax
  struct ConfigInfo *v6; // rsi
  __int64 i; // rdi
  __int64 v8; // rsi
  struct ConfigInfo *v9; // rcx
  struct ConfigInfo *v10; // rdi
  unsigned __int64 v11; // rcx
  __int64 j; // rdi
  __int64 v13; // r14
  signed int LastError; // eax
  signed int v15; // eax
  unsigned int v16; // r13d
  struct ConfigInfo *v17; // r14
  __int64 k; // rdi
  struct ConfigInfo *v19; // r10
  struct TimeProvider *m; // rcx
  unsigned __int16 *v21; // rax
  int v22; // edx
  int v23; // r8d
  unsigned __int16 *v24; // rax
  __int64 v25; // r9
  int v26; // edx
  int v27; // r8d
  __int64 n; // rdi
  struct ConfigInfo *v29; // rdx
  __int64 v30; // r9
  struct ConfigInfo *v31; // rcx
  int v32; // eax
  struct ConfigInfo *v33; // rdx
  int v34; // ecx
  int v35; // [rsp+30h] [rbp-B8h]
  int v36; // [rsp+30h] [rbp-B8h]
  struct ConfigInfo *v37; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-A8h]
  PCWSTR SourceString; // [rsp+48h] [rbp-A0h] BYREF
  struct ConfigInfo *v40; // [rsp+50h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-90h] BYREF
  int v42; // [rsp+68h] [rbp-80h]
  int v43; // [rsp+6Ch] [rbp-7Ch]
  int v44; // [rsp+70h] [rbp-78h]
  __int64 v45; // [rsp+78h] [rbp-70h]
  unsigned int v46; // [rsp+100h] [rbp+18h]
  BOOL v47; // [rsp+108h] [rbp+20h]

  v1 = 0;
  v2 = 0;
  v46 = 0;
  v47 = 0;
  v38 = dword_1800A468C;
  v37 = 0;
  SourceString = 0;
  v45 = _set_se_translator(SeTransFunc);
  if ( (unsigned __int8)FileLogAllowEntry(65) )
    FileLogAdd(L"W32TmServiceMain: Param change notification\n");
  EnterCriticalSection(&CriticalSection);
  v38 = dword_1800A468C;
  updated = UpdateTimerQueue2();
  if ( updated >= 0 )
  {
    v4 = UpdateFileLogConfig();
    LogFileLogOpenErrorEvent(v4);
    v5 = ReadConfig((struct StateInfo *)&g_state, &v37);
    if ( v5 < 0 )
    {
      updated = GetSystemErrorString(v5, (unsigned __int16 **)&SourceString);
      if ( updated < 0 )
      {
        v6 = v37;
LABEL_113:
        if ( v6 )
          FreeConfigInfo((HLOCAL *)v6);
        if ( SourceString )
          LocalFree((HLOCAL)SourceString);
        goto LABEL_117;
      }
      if ( (unsigned __int8)FileLogAllowEntry(11) )
        FileLogAdd(
          L"Logging warning: The time service encountered an error while reading its configuration from the registry, and "
           "will continue running with its previous configuration. The error was: %s\n",
          SourceString);
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      updated = LogEvent(
                  &_W32TimeRegistrationHandle,
                  W32TIME_EVENT_CONFIG_READ_FAILED_WARNING,
                  L"u",
                  &DestinationString);
      if ( updated < 0 )
      {
        v6 = v37;
        goto LABEL_113;
      }
      for ( i = *(_QWORD *)qword_1800A42F0; i; i = v8 )
      {
        v35 = SendNotificationToProvider((struct TimeProvider *)i, TPC_UpdateConfig, 0);
        v8 = *(_QWORD *)(i + 24);
        if ( v35 < 0 || *(_BYTE *)(i + 68) == 1 && !*(_DWORD *)(i + 72) )
        {
          updated = RemoveProviderFromList((struct TimeProvider *)i, 1, 0);
          if ( updated < 0 )
          {
            v6 = v37;
            goto LABEL_113;
          }
        }
      }
      v6 = v37;
LABEL_111:
      updated = UpdateTimerQueue1();
      if ( updated >= 0 )
      {
        _set_se_translator(v45);
        updated = 0;
      }
      goto LABEL_113;
    }
    AccurateGetTickCountSafe(&qword_1800A4308, 0);
    v6 = v37;
    if ( !memcmp_0((char *)qword_1800A42F0 + 16, (char *)v37 + 16, 0xC8u) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(65) )
        FileLogAdd(L"  No params changed for local clock.\n");
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(65) )
        FileLogAdd(L"  Updating params for local clock.\n");
      v9 = qword_1800A42F0;
      *((_OWORD *)qword_1800A42F0 + 1) = *((_OWORD *)v6 + 1);
      *((_OWORD *)v9 + 2) = *((_OWORD *)v6 + 2);
      *((_OWORD *)v9 + 3) = *((_OWORD *)v6 + 3);
      *((_OWORD *)v9 + 4) = *((_OWORD *)v6 + 4);
      *((_OWORD *)v9 + 5) = *((_OWORD *)v6 + 5);
      *((_OWORD *)v9 + 6) = *((_OWORD *)v6 + 6);
      *((_OWORD *)v9 + 7) = *((_OWORD *)v6 + 7);
      *((_OWORD *)v9 + 8) = *((_OWORD *)v6 + 8);
      *((_OWORD *)v9 + 9) = *((_OWORD *)v6 + 9);
      *((_OWORD *)v9 + 10) = *((_OWORD *)v6 + 10);
      *((_OWORD *)v9 + 11) = *((_OWORD *)v6 + 11);
      *((_OWORD *)v9 + 12) = *((_OWORD *)v6 + 12);
      *((_QWORD *)v9 + 26) = *((_QWORD *)v6 + 26);
      if ( dword_1800A381C < *((_DWORD *)qword_1800A42F0 + 25) || dword_1800A381C > *((_DWORD *)qword_1800A42F0 + 26) )
      {
        if ( dword_1800A381C >= *((_DWORD *)qword_1800A42F0 + 25) )
        {
          v11 = 10000000 * (1LL << dword_1800A381C);
          v10 = qword_1800A42F0;
          dword_1800A381C = *((_DWORD *)qword_1800A42F0 + 26);
          if ( qword_1800A4310 > v11 )
            qword_1800A4310 = v11;
        }
        else
        {
          v10 = qword_1800A42F0;
          dword_1800A381C = *((_DWORD *)qword_1800A42F0 + 25);
        }
        for ( j = *(_QWORD *)v10; j; j = v13 )
        {
          v36 = SendNotificationToProvider((struct TimeProvider *)j, TPC_PollIntervalChanged, 0);
          v13 = *(_QWORD *)(j + 24);
          if ( v36 < 0 || *(_BYTE *)(j + 68) == 1 && !*(_DWORD *)(j + 72) )
          {
            updated = RemoveProviderFromList((struct TimeProvider *)j, 1, 0);
            if ( updated < 0 )
              goto LABEL_113;
          }
        }
      }
      *(_QWORD *)&DestinationString.Length = qword_1800A36D8;
      DestinationString.Buffer = (PWSTR)hThread;
      if ( !hThread )
      {
        updated = -2147467260;
        goto LABEL_113;
      }
      dword_1800A3AA8 = 0;
      if ( !SetEvent(qword_1800A36D0) )
      {
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_113;
      }
      if ( WaitForMultipleObjectsEx(2u, (const HANDLE *)&DestinationString, 0, 0xFFFFFFFF, 0) == -1 )
      {
        v15 = GetLastError();
        updated = v15;
        if ( v15 > 0 )
          updated = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_113;
      }
    }
    if ( (unsigned __int8)FileLogAllowEntry(121) )
    {
      FileLogTimeProviderList(*(struct TimeProvider **)v6, L"new enabled provider list");
      FileLogTimeProviderList(*(struct TimeProvider **)qword_1800A42F0, L"Parameter change before list is updated");
      FileLogTimeProviderList(*((struct TimeProvider **)v6 + 1), L"new disabled provider list");
      FileLogTimeProviderList(
        *((struct TimeProvider **)qword_1800A42F0 + 1),
        L"Parameter change before list is updated");
    }
    FreeTimeProviderList(*((HLOCAL *)qword_1800A42F0 + 1));
    *((_QWORD *)qword_1800A42F0 + 1) = *((_QWORD *)v6 + 1);
    *((_QWORD *)v6 + 1) = 0;
    v16 = CountInputProvidersInList(*(struct TimeProvider **)v6);
    v17 = qword_1800A42F0;
    v40 = qword_1800A42F0;
    for ( k = *(_QWORD *)qword_1800A42F0; k; k = *(_QWORD *)v17 )
    {
      v19 = v6;
      for ( m = *(struct TimeProvider **)v6; ; m = (struct TimeProvider *)*((_QWORD *)m + 3) )
      {
        if ( !m )
        {
          v43 = ++v1;
          *(_QWORD *)v17 = *(_QWORD *)(k + 24);
          RemoveProviderFromList((struct TimeProvider *)k, 0, 0);
          goto LABEL_71;
        }
        v21 = *(unsigned __int16 **)m;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v21 + *(_QWORD *)k - *(_QWORD *)m);
          v23 = *v21 - v22;
          if ( v23 )
            break;
          ++v21;
        }
        while ( v22 );
        if ( !v23 )
        {
          v24 = (unsigned __int16 *)*((_QWORD *)m + 1);
          v25 = *(_QWORD *)(k + 8) - (_QWORD)v24;
          do
          {
            v26 = *(unsigned __int16 *)((char *)v24 + v25);
            v27 = *v24 - v26;
            if ( v27 )
              break;
            ++v24;
          }
          while ( v26 );
          if ( !v27 && *((_BYTE *)m + 16) == *(_BYTE *)(k + 16) )
            break;
        }
        v19 = (struct TimeProvider *)((char *)m + 24);
      }
      v42 = ++v46;
      *(_QWORD *)v19 = *((_QWORD *)m + 3);
      *((_QWORD *)m + 3) = 0;
      FreeTimeProviderList(m);
      if ( (int)SendNotificationToProvider((struct TimeProvider *)k, TPC_UpdateConfig, 0) < 0
        || *(_BYTE *)(k + 68) == 1 && !*(_DWORD *)(k + 72) )
      {
        *(_QWORD *)v17 = *(_QWORD *)(k + 24);
        updated = RemoveProviderFromList((struct TimeProvider *)k, 0, 0);
        if ( updated < 0 )
          goto LABEL_113;
      }
      else
      {
        v17 = (struct ConfigInfo *)(k + 24);
        v40 = (struct ConfigInfo *)(k + 24);
      }
LABEL_71:
      ;
    }
    *(_QWORD *)v17 = *(_QWORD *)v6;
    *(_QWORD *)v6 = 0;
    for ( n = *(_QWORD *)v17; n; n = *(_QWORD *)v17 )
    {
      if ( (int)StartProvider((struct TimeProvider *)n) >= 0 )
      {
        v44 = ++v2;
        v17 = (struct ConfigInfo *)(n + 24);
        v40 = (struct ConfigInfo *)(n + 24);
      }
      else
      {
        if ( (unsigned __int8)FileLogAllowEntry(65) )
          FileLogAdd(L"Discarding provider '%s'.\n", *(_QWORD *)(n + 8));
        *(_QWORD *)v17 = *(_QWORD *)(n + 24);
        RemoveProviderFromList((struct TimeProvider *)n, 0, 0);
      }
    }
    if ( (unsigned __int8)FileLogAllowEntry(65) )
      FileLogAdd(L"  Provider list: %u stopped, %u started, %u not changed.\n", v1, v2, v46);
    if ( (unsigned __int8)FileLogAllowEntry(121) )
      FileLogTimeProviderList(*(struct TimeProvider **)qword_1800A42F0, L"Parameter change after list is updated");
    if ( CountInputProvidersInList(*(struct TimeProvider **)qword_1800A42F0) )
    {
      byte_1800A45A1 = 1;
    }
    else
    {
      if ( v16 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(11) )
          FileLogAdd(
            L"Logging error: The time service has been configured to use one or more input providers, however, none of the"
             " input providers could be started. THE TIME SERVICE HAS NO SOURCE OF ACCURATE TIME.\n");
        LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_NO_INPUT_PROVIDERS_STARTED, 0, v30);
        v29 = qword_1800A42F0;
      }
      byte_1800A45A1 = 0;
    }
    *((_DWORD *)v29 + 56) = *((_DWORD *)v6 + 56);
    v31 = qword_1800A42F0;
    v32 = *((_DWORD *)qword_1800A42F0 + 54);
    if ( v32 == *((_DWORD *)v6 + 54) )
    {
      if ( !v1 && !v2 || (v32 & 3) != 2 )
        goto LABEL_103;
      if ( (unsigned __int8)FileLogAllowEntry(65) )
        FileLogAdd(L"  AnnounceFlags are auto. Updating announcement to match new provider list.\n");
      updated = UpdateNetlogonServiceBits(1);
      if ( updated < 0 )
        goto LABEL_113;
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(65) )
        FileLogAdd(
          L"  AnnounceFlags changed from 0x%08X to 0x%08X.\n",
          *((unsigned int *)qword_1800A42F0 + 54),
          *((unsigned int *)v6 + 54));
      *((_DWORD *)qword_1800A42F0 + 54) = *((_DWORD *)v6 + 54);
      updated = UpdateNetlogonServiceBits(1);
      if ( updated < 0 )
        goto LABEL_113;
    }
    v31 = qword_1800A42F0;
LABEL_103:
    *((_DWORD *)v31 + 57) = *((_DWORD *)v6 + 57);
    v33 = qword_1800A42F0;
    if ( *((_DWORD *)qword_1800A42F0 + 55) != *((_DWORD *)v6 + 55) )
    {
      if ( (unsigned __int8)FileLogAllowEntry(65) )
        FileLogAdd(L"  EventLogFlags changed from 0x%08X to 0x%08X.\n", dword_1800A45B8, *((unsigned int *)v6 + 55));
      *((_DWORD *)qword_1800A42F0 + 55) = *((_DWORD *)v6 + 55);
      dword_1800A45B8 = *((_DWORD *)v6 + 55);
      v33 = qword_1800A42F0;
    }
    v34 = *((_DWORD *)v6 + 58);
    if ( *((_DWORD *)v33 + 58) != v34 || *((_DWORD *)v33 + 59) != *((_DWORD *)v6 + 59) )
    {
      *((_DWORD *)v33 + 58) = v34;
      *((_DWORD *)qword_1800A42F0 + 59) = *((_DWORD *)v6 + 59);
    }
    byte_1800A45B4 = 0;
    LogSettingsChange();
    goto LABEL_111;
  }
LABEL_117:
  if ( !updated )
    v47 = DidNetlogonServiceBitsChange(dword_1800A468C, v38);
  LeaveCriticalSection(&CriticalSection);
  if ( !v47 )
  {
LABEL_122:
    if ( !updated )
      return;
    goto LABEL_123;
  }
  if ( !updated )
  {
    SetNetlogonServiceBits(dword_1800A468C);
    updated = 0;
    goto LABEL_122;
  }
LABEL_123:
  if ( (unsigned __int8)FileLogAllowEntry(73) )
    FileLogAdd(L"Failed in handling parameter change, restart service async");
  NotifyShutdown(updated);
}

```

## disassembly

```asm
0x180032ff0  mov     rax, rsp
0x180032ff3  mov     [rax+8], rbx
0x180032ff7  mov     [rax+10h], rsi
0x180032ffb  push    rdi
0x180032ffc  push    r12
0x180032ffe  push    r13
0x180033000  push    r14
0x180033002  push    r15
0x180033004  sub     rsp, 0C0h
0x18003300b  xor     ebx, ebx
0x18003300d  mov     [rsp+0E8h+var_B4], bl
0x180033011  mov     r12d, ebx
0x180033014  mov     r15d, ebx
0x180033017  mov     [rax+18h], ebx
0x18003301a  mov     [rsp+0E8h+arg_18], ebx
0x180033021  mov     eax, cs:dword_1800A468C
0x180033027  mov     [rsp+0E8h+var_A8], eax
0x18003302b  mov     [rsp+0E8h+var_B0], rbx
0x180033030  mov     [rsp+0E8h+SourceString], rbx
0x180033035  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18003303c  call    cs:__imp__set_se_translator
0x180033043  nop     dword ptr [rax+rax+00h]
0x180033048  mov     [rsp+0E8h+var_70], rax
0x18003304d  lea     r14d, [rbx+41h]
0x180033051  mov     ecx, r14d
0x180033054  call    FileLogAllowEntry
0x180033059  test    al, al
0x18003305b  jz      short loc_180033069
0x18003305d  lea     rcx, aW32tmservicema_7; "W32TmServiceMain: Param change notifica"...
0x180033064  call    FileLogAdd
0x180033069  lea     rcx, CriticalSection; lpCriticalSection
0x180033070  call    cs:__imp_EnterCriticalSection
0x180033077  nop     dword ptr [rax+rax+00h]
0x18003307c  mov     [rsp+0E8h+var_B8], ebx
0x180033080  mov     r13d, 1
0x180033086  mov     [rsp+0E8h+var_B4], r13b
0x18003308b  mov     eax, cs:dword_1800A468C
0x180033091  mov     [rsp+0E8h+var_A8], eax
0x180033095  call    ?UpdateTimerQueue2@@YAJXZ; UpdateTimerQueue2(void)
0x18003309a  mov     edi, eax
0x18003309c  mov     [rsp+0E8h+var_B8], eax
0x1800330a0  test    eax, eax
0x1800330a2  jns     short loc_1800330A9
0x1800330a4  jmp     loc_1800338DF
0x1800330a9  call    UpdateFileLogConfig
0x1800330ae  mov     ecx, eax; dwMessageId
0x1800330b0  call    ?LogFileLogOpenErrorEvent@@YAXJ@Z; LogFileLogOpenErrorEvent(long)
0x1800330b5  lea     rdx, [rsp+0E8h+var_B0]; struct ConfigInfo **
0x1800330ba  lea     rcx, ?g_state@@3UStateInfo@@A; struct StateInfo *
0x1800330c1  call    ?ReadConfig@@YAJPEAUStateInfo@@PEAPEAUConfigInfo@@@Z; ReadConfig(StateInfo *,ConfigInfo * *)
0x1800330c6  test    eax, eax
0x1800330c8  jns     loc_1800331C7
0x1800330ce  lea     rdx, [rsp+0E8h+SourceString]; unsigned __int16 **
0x1800330d3  mov     ecx, eax; dwMessageId
0x1800330d5  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x1800330da  mov     edi, eax
0x1800330dc  mov     [rsp+0E8h+var_B8], eax
0x1800330e0  test    eax, eax
0x1800330e2  jns     short loc_1800330EE
0x1800330e4  mov     rsi, [rsp+0E8h+var_B0]
0x1800330e9  jmp     loc_1800338B6
0x1800330ee  mov     ecx, 0Bh
0x1800330f3  call    FileLogAllowEntry
0x1800330f8  test    al, al
0x1800330fa  jz      short loc_18003310D
0x1800330fc  mov     rdx, [rsp+0E8h+SourceString]
0x180033101  lea     rcx, aLoggingWarning_31; "Logging warning: The time service encou"...
0x180033108  call    FileLogAdd
0x18003310d  xorps   xmm0, xmm0
0x180033110  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x180033115  mov     rdx, [rsp+0E8h+SourceString]; SourceString
0x18003311a  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18003311f  call    cs:__imp_RtlInitUnicodeString
0x180033126  nop     dword ptr [rax+rax+00h]
0x18003312b  lea     r9, [rsp+0E8h+DestinationString]
0x180033130  lea     r8, aU; "u"
0x180033137  lea     rdx, W32TIME_EVENT_CONFIG_READ_FAILED_WARNING
0x18003313e  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180033145  call    LogEvent
0x18003314a  mov     edi, eax
0x18003314c  mov     [rsp+0E8h+var_B8], eax
0x180033150  test    eax, eax
0x180033152  jns     short loc_18003315E
0x180033154  mov     rsi, [rsp+0E8h+var_B0]
0x180033159  jmp     loc_1800338B6
0x18003315e  mov     [rsp+0E8h+var_B8], ebx
0x180033162  mov     rax, cs:qword_1800A42F0
0x180033169  mov     rdi, [rax]
0x18003316c  test    rdi, rdi
0x18003316f  jz      short loc_1800331BD
0x180033171  xor     r8d, r8d; void *
0x180033174  mov     edx, r13d; enum TimeProvCmd
0x180033177  mov     rcx, rdi; struct TimeProvider *
0x18003317a  call    ?SendNotificationToProvider@@YAJPEAUTimeProvider@@W4TimeProvCmd@@PEAX@Z; SendNotificationToProvider(TimeProvider *,TimeProvCmd,void *)
0x18003317f  mov     [rsp+0E8h+var_B8], eax
0x180033183  mov     rsi, [rdi+18h]
0x180033187  test    eax, eax
0x180033189  js      short loc_180033196
0x18003318b  cmp     [rdi+44h], r13b
0x18003318f  jnz     short loc_1800331B8
0x180033191  cmp     [rdi+48h], ebx
0x180033194  jnz     short loc_1800331B8
0x180033196  xor     r8d, r8d; bool *
0x180033199  mov     dl, r13b; bool
0x18003319c  mov     rcx, rdi; struct TimeProvider *
0x18003319f  call    ?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z; RemoveProviderFromList(TimeProvider *,bool,bool *)
0x1800331a4  mov     edi, eax
0x1800331a6  mov     [rsp+0E8h+var_B8], eax
0x1800331aa  test    eax, eax
0x1800331ac  jns     short loc_1800331B8
0x1800331ae  mov     rsi, [rsp+0E8h+var_B0]
0x1800331b3  jmp     loc_1800338B6
0x1800331b8  mov     rdi, rsi
0x1800331bb  jmp     short loc_18003316C
0x1800331bd  mov     rsi, [rsp+0E8h+var_B0]
0x1800331c2  jmp     loc_18003387E
0x1800331c7  xor     edx, edx; bool
0x1800331c9  lea     rcx, qword_1800A4308; unsigned __int64 *
0x1800331d0  call    ?AccurateGetTickCountSafe@@YAJPEA_K_N@Z; AccurateGetTickCountSafe(unsigned __int64 *,bool)
0x1800331d5  mov     rsi, [rsp+0E8h+var_B0]
0x1800331da  mov     rcx, cs:qword_1800A42F0
0x1800331e1  add     rcx, 10h; Buf1
0x1800331e5  mov     r8d, 0C8h; Size
0x1800331eb  lea     rdx, [rsi+10h]; Buf2
0x1800331ef  call    memcmp_0
0x1800331f4  mov     ecx, r14d
0x1800331f7  test    eax, eax
0x1800331f9  jz      loc_180033436
0x1800331ff  call    FileLogAllowEntry
0x180033204  test    al, al
0x180033206  jz      short loc_180033214
0x180033208  lea     rcx, aUpdatingParams; "  Updating params for local clock.\n"
0x18003320f  call    FileLogAdd
0x180033214  mov     rcx, cs:qword_1800A42F0
0x18003321b  movups  xmm0, xmmword ptr [rsi+10h]
0x18003321f  movups  xmmword ptr [rcx+10h], xmm0
0x180033223  movups  xmm1, xmmword ptr [rsi+20h]
0x180033227  movups  xmmword ptr [rcx+20h], xmm1
0x18003322b  movups  xmm0, xmmword ptr [rsi+30h]
0x18003322f  movups  xmmword ptr [rcx+30h], xmm0
0x180033233  movups  xmm1, xmmword ptr [rsi+40h]
0x180033237  movups  xmmword ptr [rcx+40h], xmm1
0x18003323b  movups  xmm0, xmmword ptr [rsi+50h]
0x18003323f  movups  xmmword ptr [rcx+50h], xmm0
0x180033243  movups  xmm1, xmmword ptr [rsi+60h]
0x180033247  movups  xmmword ptr [rcx+60h], xmm1
0x18003324b  movups  xmm0, xmmword ptr [rsi+70h]
0x18003324f  movups  xmmword ptr [rcx+70h], xmm0
0x180033253  movups  xmm1, xmmword ptr [rsi+80h]
0x18003325a  movups  xmmword ptr [rcx+80h], xmm1
0x180033261  movups  xmm0, xmmword ptr [rsi+90h]
0x180033268  movups  xmmword ptr [rcx+90h], xmm0
0x18003326f  movups  xmm1, xmmword ptr [rsi+0A0h]
0x180033276  movups  xmmword ptr [rcx+0A0h], xmm1
0x18003327d  movups  xmm0, xmmword ptr [rsi+0B0h]
0x180033284  movups  xmmword ptr [rcx+0B0h], xmm0
0x18003328b  movups  xmm1, xmmword ptr [rsi+0C0h]
0x180033292  movups  xmmword ptr [rcx+0C0h], xmm1
0x180033299  mov     rax, [rsi+0D0h]
0x1800332a0  mov     [rcx+0D0h], rax
0x1800332a7  mov     rax, cs:qword_1800A42F0
0x1800332ae  mov     ecx, [rax+64h]
0x1800332b1  mov     eax, cs:dword_1800A381C
0x1800332b7  cmp     eax, ecx
0x1800332b9  jl      short loc_1800332D3
0x1800332bb  mov     rax, cs:qword_1800A42F0
0x1800332c2  mov     ecx, [rax+68h]
0x1800332c5  mov     eax, cs:dword_1800A381C
0x1800332cb  cmp     eax, ecx
0x1800332cd  jle     loc_180033380
0x1800332d3  mov     rax, cs:qword_1800A42F0
0x1800332da  mov     ecx, [rax+64h]
0x1800332dd  mov     eax, cs:dword_1800A381C
0x1800332e3  cmp     eax, ecx
0x1800332e5  jge     short loc_1800332F9
0x1800332e7  mov     rdi, cs:qword_1800A42F0
0x1800332ee  mov     eax, [rdi+64h]
0x1800332f1  mov     cs:dword_1800A381C, eax
0x1800332f7  jmp     short loc_18003332C
0x1800332f9  mov     ecx, cs:dword_1800A381C
0x1800332ff  mov     rax, r13
0x180033302  shl     rax, cl
0x180033305  imul    rcx, rax, 989680h
0x18003330c  mov     rdi, cs:qword_1800A42F0
0x180033313  mov     eax, [rdi+68h]
0x180033316  mov     cs:dword_1800A381C, eax
0x18003331c  cmp     cs:qword_1800A4310, rcx
0x180033323  jbe     short loc_18003332C
0x180033325  mov     cs:qword_1800A4310, rcx
0x18003332c  mov     [rsp+0E8h+var_B8], ebx
0x180033330  mov     rdi, [rdi]
0x180033333  test    rdi, rdi
0x180033336  jz      short loc_180033380
0x180033338  xor     r8d, r8d; void *
0x18003333b  lea     edx, [r8+2]; enum TimeProvCmd
0x18003333f  mov     rcx, rdi; struct TimeProvider *
0x180033342  call    ?SendNotificationToProvider@@YAJPEAUTimeProvider@@W4TimeProvCmd@@PEAX@Z; SendNotificationToProvider(TimeProvider *,TimeProvCmd,void *)
0x180033347  mov     [rsp+0E8h+var_B8], eax
0x18003334b  mov     r14, [rdi+18h]
0x18003334f  test    eax, eax
0x180033351  js      short loc_18003335E
0x180033353  cmp     [rdi+44h], r13b
0x180033357  jnz     short loc_18003337B
0x180033359  cmp     [rdi+48h], ebx
0x18003335c  jnz     short loc_18003337B
0x18003335e  xor     r8d, r8d; bool *
0x180033361  mov     dl, r13b; bool
0x180033364  mov     rcx, rdi; struct TimeProvider *
0x180033367  call    ?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z; RemoveProviderFromList(TimeProvider *,bool,bool *)
0x18003336c  mov     edi, eax
0x18003336e  mov     [rsp+0E8h+var_B8], eax
0x180033372  test    eax, eax
0x180033374  jns     short loc_18003337B
0x180033376  jmp     loc_1800338B6
0x18003337b  mov     rdi, r14
0x18003337e  jmp     short loc_180033333
0x180033380  mov     rax, cs:qword_1800A36D8
0x180033387  mov     qword ptr [rsp+0E8h+DestinationString.Length], rax
0x18003338c  mov     rax, cs:hThread
0x180033393  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x180033398  test    rax, rax
0x18003339b  jnz     short loc_1800333AB
0x18003339d  mov     edi, 80004004h
0x1800333a2  mov     [rsp+0E8h+var_B8], edi
0x1800333a6  jmp     loc_1800338B6
0x1800333ab  mov     cs:dword_1800A3AA8, ebx
0x1800333b1  mov     rcx, cs:qword_1800A36D0; hEvent
0x1800333b8  call    cs:__imp_SetEvent
0x1800333bf  nop     dword ptr [rax+rax+00h]
0x1800333c4  test    eax, eax
0x1800333c6  jnz     short loc_1800333EC
0x1800333c8  call    cs:__imp_GetLastError
0x1800333cf  nop     dword ptr [rax+rax+00h]
0x1800333d4  mov     edi, eax
0x1800333d6  test    eax, eax
0x1800333d8  jle     short loc_1800333E3
0x1800333da  movzx   edi, ax
0x1800333dd  or      edi, 80070000h
0x1800333e3  mov     [rsp+0E8h+var_B8], edi
0x1800333e7  jmp     loc_1800338B6
0x1800333ec  mov     [rsp+0E8h+bAlertable], ebx; bAlertable
0x1800333f0  or      edi, 0FFFFFFFFh
0x1800333f3  mov     r9d, edi; dwMilliseconds
0x1800333f6  xor     r8d, r8d; bWaitAll
0x1800333f9  lea     rdx, [rsp+0E8h+DestinationString]; lpHandles
0x1800333fe  lea     ecx, [r8+2]; nCount
0x180033402  call    cs:__imp_WaitForMultipleObjectsEx
0x180033409  nop     dword ptr [rax+rax+00h]
0x18003340e  cmp     eax, edi
0x180033410  jnz     short loc_18003344B
0x180033412  call    cs:__imp_GetLastError
0x180033419  nop     dword ptr [rax+rax+00h]
0x18003341e  mov     edi, eax
0x180033420  test    eax, eax
0x180033422  jle     short loc_18003342D
0x180033424  movzx   edi, ax
0x180033427  or      edi, 80070000h
0x18003342d  mov     [rsp+0E8h+var_B8], edi
0x180033431  jmp     loc_1800338B6
0x180033436  call    FileLogAllowEntry
0x18003343b  test    al, al
0x18003343d  jz      short loc_18003344B
0x18003343f  lea     rcx, aNoParamsChange; "  No params changed for local clock.\n"
0x180033446  call    FileLogAdd
0x18003344b  mov     ecx, 79h ; 'y'
0x180033450  call    FileLogAllowEntry
0x180033455  test    al, al
0x180033457  jz      short loc_1800334A5
0x180033459  lea     rdx, aNewEnabledProv; "new enabled provider list"
0x180033460  mov     rcx, [rsi]; struct TimeProvider *
0x180033463  call    ?FileLogTimeProviderList@@YAXPEAUTimeProvider@@PEBG@Z; FileLogTimeProviderList(TimeProvider *,ushort const *)
0x180033468  lea     rdx, aParameterChang; "Parameter change before list is updated"
0x18003346f  mov     rcx, cs:qword_1800A42F0
0x180033476  mov     rcx, [rcx]; struct TimeProvider *
0x180033479  call    ?FileLogTimeProviderList@@YAXPEAUTimeProvider@@PEBG@Z; FileLogTimeProviderList(TimeProvider *,ushort const *)
0x18003347e  lea     rdx, aNewDisabledPro; "new disabled provider list"
0x180033485  mov     rcx, [rsi+8]; struct TimeProvider *
0x180033489  call    ?FileLogTimeProviderList@@YAXPEAUTimeProvider@@PEBG@Z; FileLogTimeProviderList(TimeProvider *,ushort const *)
0x18003348e  lea     rdx, aParameterChang; "Parameter change before list is updated"
0x180033495  mov     rcx, cs:qword_1800A42F0
0x18003349c  mov     rcx, [rcx+8]; struct TimeProvider *
0x1800334a0  call    ?FileLogTimeProviderList@@YAXPEAUTimeProvider@@PEBG@Z; FileLogTimeProviderList(TimeProvider *,ushort const *)
0x1800334a5  mov     rcx, cs:qword_1800A42F0
0x1800334ac  mov     rcx, [rcx+8]; hMem
0x1800334b0  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800334b5  mov     rcx, [rsi+8]
0x1800334b9  mov     rax, cs:qword_1800A42F0
0x1800334c0  mov     [rax+8], rcx
0x1800334c4  mov     [rsi+8], rbx
0x1800334c8  mov     rcx, [rsi]; struct TimeProvider *
0x1800334cb  call    ?CountInputProvidersInList@@YAIPEAUTimeProvider@@@Z; CountInputProvidersInList(TimeProvider *)
0x1800334d0  mov     r13d, eax
0x1800334d3  mov     r14, cs:qword_1800A42F0
0x1800334da  mov     [rsp+0E8h+var_98], r14
0x1800334df  mov     rdi, [r14]
0x1800334e2  mov     [rsp+0E8h+var_B8], ebx
0x1800334e6  test    rdi, rdi
0x1800334e9  jz      loc_1800335FB
0x1800334ef  mov     r10, rsi
0x1800334f2  mov     rcx, [rsi]; hMem
  ... truncated ...
```
