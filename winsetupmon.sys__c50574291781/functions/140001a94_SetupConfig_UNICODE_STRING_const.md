# SetupConfig(_UNICODE_STRING const *)

- ea: `0x140001a94`
- end: `0x1400022e8`
- name: `?SetupConfig@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `2132`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x14001f6c0`

## callees

- `0x140001a94`
- `0x1400022f0`
- `0x140002428`
- `0x140002f00`
- `0x140002ffc`
- `0x1400030b8`
- `0x140003944`
- `0x140005910`
- `0x140005de4`
- `0x140006924`
- `0x140008a18`
- `0x140008a8c`
- `0x140009394`
- `0x14000eb0c`
- `0x14000eb68`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001dc7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001f7e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000208a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001dc7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001f7e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000208a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400022a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400022a0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001d4e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001d4e`
- `ntoskrnl!KeReleaseMutex` at `0x140001cfd`
- `ntoskrnl!KeReleaseMutex` at `0x14000219e`
- `ntoskrnl!KeReleaseMutex` at `0x1400022be`
- `ntoskrnl!KeReleaseMutex` at `0x140001cfd`
- `ntoskrnl!KeReleaseMutex` at `0x14000219e`
- `ntoskrnl!KeReleaseMutex` at `0x1400022be`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001ae6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001ae6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001db0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ea7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ec0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001f67`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002051`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002066`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001db0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ea7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ec0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001f67`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002051`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002066`
- `ntoskrnl!_wcsicmp` at `0x140001b76`
- `ntoskrnl!_wcsicmp` at `0x140001b76`

## string_xrefs

- `0x140001ba8`: `Done setting up load-time log config`
- `0x140001ca1`: `Done setting up load-time tracking config`
- `0x1400021cd`: `AddOrUpdateTrackedPath [%wZ] for tracking table failed (0x%08X)`
- `0x1400021c0`: `AddTrackedStablePath [%s] for tracking config failed (0x%08X)`
- `0x140002276`: `IsTrackedPath failed (0x%08X)`
- `0x1400021ef`: `GetVolumeInStablePath for [%wZ] failed (0x%08X)`
- `0x140002265`: `AddOrUpdateTrackedPathOverride [%wZ] [%wZ] [%wZ] for tracking table failed (0x%08X)`
- `0x140002215`: `AddOrUpdateTrackedStablePathOverride [%s] [%s] [%s] for tracking config failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall SetupConfig(PCUNICODE_STRING String2)
{
  char v2; // di
  __int64 (__fastcall ***v3)(_QWORD); // rcx
  int StablePathWithFallback; // ebx
  __int64 (__fastcall ***v5)(_QWORD); // rsi
  __int64 v6; // rbx
  const wchar_t **v7; // rax
  const wchar_t **v8; // rsi
  bool v9; // zf
  char v10; // al
  __int64 (__fastcall ***v11)(_QWORD); // rbx
  __int64 (__fastcall ***v12)(_QWORD); // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  char v15; // al
  char *PoolWithTag; // rax
  PCWSTR *v17; // rax
  PCWSTR *v18; // rsi
  unsigned __int64 v19; // rcx
  const WCHAR **v20; // rax
  const WCHAR **v21; // rsi
  const WCHAR *v22; // rdx
  const WCHAR *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // r14
  __int64 v27; // rsi
  int updated; // eax
  int v29; // eax
  int v30; // eax
  unsigned int i; // r13d
  __int64 v32; // r12
  __int64 v33; // r9
  struct _UNICODE_STRING *p_DestinationString; // r8
  UNICODE_STRING *v35; // rdx
  int v36; // eax
  int Timeout; // [rsp+20h] [rbp-69h]
  __int64 v39; // [rsp+28h] [rbp-61h]
  __int64 v40; // [rsp+40h] [rbp-49h]
  UNICODE_STRING v41; // [rsp+48h] [rbp-41h] BYREF
  UNICODE_STRING String2a; // [rsp+58h] [rbp-31h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp-21h] BYREF
  UNICODE_STRING v44; // [rsp+78h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-1h] BYREF
  struct _UNICODE_STRING v46; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v47; // [rsp+F8h] [rbp+6Fh] BYREF
  char v48; // [rsp+100h] [rbp+77h]
  int v49; // [rsp+108h] [rbp+7Fh]

  String1 = 0;
  DestinationString = 0;
  if ( !byte_140019370 )
  {
    v2 = 0;
    goto LABEL_101;
  }
  KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
  v2 = 1;
  if ( !qword_140019348 )
    goto LABEL_21;
  v3 = (__int64 (__fastcall ***)(_QWORD))qword_140019350;
  if ( !qword_140019350 )
  {
    utl::make_unique<CWsmLogConfig,,0>(&v47);
    v3 = (__int64 (__fastcall ***)(_QWORD))v47;
    if ( !v47 )
    {
LABEL_5:
      StablePathWithFallback = -1073741670;
      goto LABEL_102;
    }
    qword_140019350 = v47;
  }
  v5 = (__int64 (__fastcall ***)(_QWORD))qword_140019348;
  if ( qword_140019348 )
  {
    if ( v3 )
    {
      v6 = (**v3)(v3);
      v7 = (const wchar_t **)(**v5)(v5);
      v8 = v7;
      if ( v7 )
      {
        if ( !v6 || _wcsicmp(*v7, *(const wchar_t **)v6) )
          goto LABEL_15;
        v9 = v8[1] == *(const wchar_t **)(v6 + 8);
      }
      else
      {
        v9 = v6 == 0;
      }
      if ( v9 )
      {
        v10 = 1;
LABEL_17:
        if ( !v10 )
          goto LABEL_21;
        goto LABEL_20;
      }
LABEL_15:
      v10 = 0;
      goto LABEL_17;
    }
  }
  else if ( !v3 )
  {
LABEL_20:
    WriteLogMessage(1, L"Done setting up load-time log config");
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019350 + 8LL))(qword_140019350);
    qword_140019350 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019348 + 8LL))(qword_140019348);
    qword_140019348 = 0;
  }
LABEL_21:
  v11 = (__int64 (__fastcall ***)(_QWORD))qword_140019358;
  if ( qword_140019358 )
  {
    if ( !(**(__int64 (__fastcall ***)(__int64))qword_140019358)(qword_140019358) )
    {
LABEL_38:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019358 + 8LL))(qword_140019358);
      v11 = 0;
      qword_140019358 = 0;
      goto LABEL_39;
    }
    v12 = (__int64 (__fastcall ***)(_QWORD))qword_140019360;
    if ( !qword_140019360 )
    {
      utl::make_unique<CWsmTrackingConfig,,0>(&v47);
      v12 = (__int64 (__fastcall ***)(_QWORD))v47;
      if ( !v47 )
        goto LABEL_5;
      qword_140019360 = v47;
    }
    v11 = (__int64 (__fastcall ***)(_QWORD))qword_140019358;
    if ( !qword_140019358 )
    {
      if ( v12 )
        goto LABEL_39;
LABEL_37:
      WriteLogMessage(1, L"Done setting up load-time tracking config");
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019360 + 8LL))(qword_140019360);
      qword_140019360 = 0;
      goto LABEL_38;
    }
    if ( v12 )
    {
      v13 = (**v12)(v12);
      v14 = (**v11)(v11);
      if ( v14 )
      {
        if ( v13 )
        {
          v15 = operator__(v14, v13);
          goto LABEL_34;
        }
      }
      else if ( !v13 )
      {
        v15 = 1;
LABEL_34:
        if ( !v15 )
        {
          v11 = (__int64 (__fastcall ***)(_QWORD))qword_140019358;
          goto LABEL_39;
        }
        goto LABEL_37;
      }
      v15 = 0;
      goto LABEL_34;
    }
  }
LABEL_39:
  if ( qword_140019348 || v11 )
  {
    StablePathWithFallback = GetStablePathWithFallback(String2, &String1, &DestinationString);
    if ( StablePathWithFallback < 0 )
      goto LABEL_102;
    v48 = 1;
    if ( !(unsigned __int8)WasVolumeSeen(&String1) )
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x18u, 0x6E6D7377u);
      if ( !PoolWithTag )
        goto LABEL_5;
      v48 = 0;
      *(UNICODE_STRING *)(PoolWithTag + 8) = String1;
      *(_QWORD *)PoolWithTag = P;
      P = PoolWithTag;
    }
    if ( !qword_140019348 )
      goto LABEL_109;
    v17 = (PCWSTR *)(**(__int64 (__fastcall ***)(__int64))qword_140019348)(qword_140019348);
    DestinationString = 0;
    v18 = v17;
    RtlInitUnicodeString(&DestinationString, *v17);
    if ( !RtlPrefixUnicodeString(&String1, &DestinationString, 1u)
      || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)qword_140019350 + 16LL))(qword_140019350) )
    {
      goto LABEL_109;
    }
    StablePathWithFallback = SetLogPath(&DestinationString, 0);
    if ( StablePathWithFallback >= 0 )
    {
      StablePathWithFallback = (*(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)qword_140019350 + 24LL))(
                                 qword_140019350,
                                 *v18);
      if ( StablePathWithFallback >= 0 )
      {
        v19 = (unsigned __int64)v18[1];
        if ( !v19
          || (StablePathWithFallback = SetLogMaximumSize(v19, 0), StablePathWithFallback >= 0)
          && (StablePathWithFallback = (*(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)qword_140019350 + 32LL))(
                                         qword_140019350,
                                         v18[1]),
              StablePathWithFallback >= 0) )
        {
          if ( !qword_140019358 )
            goto LABEL_90;
          v20 = (const WCHAR **)(**(__int64 (__fastcall ***)(__int64))qword_140019358)(qword_140019358);
          v21 = v20;
          if ( !v20 )
            goto LABEL_109;
          v22 = *v20;
          String2a = 0;
          v44 = 0;
          if ( v22 )
            RtlInitUnicodeString(&String2a, v22);
          v23 = v21[1];
          if ( v23 )
            RtlInitUnicodeString(&v44, v23);
          if ( !String2a.Length && !v44.Length
            || (StablePathWithFallback = SetLogSessionInfo(&String2a, &v44), StablePathWithFallback >= 0)
            && (StablePathWithFallback = (*(__int64 (__fastcall **)(__int64, const WCHAR *, const WCHAR *))(*(_QWORD *)qword_140019360 + 16LL))(
                                           qword_140019360,
                                           *v21,
                                           v21[1]),
                StablePathWithFallback >= 0) )
          {
LABEL_109:
            if ( qword_140019358 )
            {
              v40 = (**(__int64 (__fastcall ***)(__int64))qword_140019358)(qword_140019358);
              v24 = v40;
              if ( v40 )
              {
                v25 = 0;
                v49 = 0;
                while ( (unsigned int)v25 < *(_DWORD *)(v40 + 16) )
                {
                  v26 = *(_QWORD *)(v24 + 24);
                  v27 = 3 * v25;
                  String2a = 0;
                  RtlInitUnicodeString(&String2a, *(PCWSTR *)(v26 + 24 * v25));
                  if ( RtlPrefixUnicodeString(&String1, &String2a, 1u)
                    && !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_140019360 + 24LL))(
                          qword_140019360,
                          *(_QWORD *)(v26 + 8 * v27)) )
                  {
                    updated = AddOrUpdateTrackedPath(&String2a, *(unsigned int *)(v26 + 8 * v27 + 8), 0, 0);
                    StablePathWithFallback = updated;
                    if ( updated < 0 )
                    {
                      WriteLogMessage(
                        3,
                        L"AddOrUpdateTrackedPath [%wZ] for tracking table failed (0x%08X)",
                        &String2a,
                        (unsigned int)updated);
                      goto LABEL_91;
                    }
                    v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_140019360 + 32LL))(
                            qword_140019360,
                            *(_QWORD *)(v26 + 8 * v27),
                            *(unsigned int *)(v26 + 8 * v27 + 8));
                    StablePathWithFallback = v29;
                    if ( v29 < 0 )
                    {
                      WriteLogMessage(
                        3,
                        L"AddTrackedStablePath [%s] for tracking config failed (0x%08X)",
                        *(_QWORD *)(v26 + 8 * v27),
                        (unsigned int)v29);
                      goto LABEL_91;
                    }
                  }
                  if ( *(_DWORD *)(v26 + 8 * v27 + 12) )
                  {
                    LOBYTE(v47) = 0;
                    v30 = IsTrackedPath(&String2a, (unsigned __int8 *)&v47);
                    StablePathWithFallback = v30;
                    if ( v30 < 0 )
                    {
                      WriteLogMessage(3, L"IsTrackedPath failed (0x%08X)", (unsigned int)v30);
                      goto LABEL_91;
                    }
                    if ( (_BYTE)v47 )
                    {
                      for ( i = 0; i < *(_DWORD *)(v26 + 8 * v27 + 12); ++i )
                      {
                        v32 = *(_QWORD *)(v26 + 8 * v27 + 16);
                        v41 = 0;
                        DestinationString = 0;
                        v44 = 0;
                        RtlInitUnicodeString(&v41, *(PCWSTR *)(v32 + 24LL * i));
                        RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v32 + 24LL * i + 8));
                        if ( v41.Length )
                        {
                          if ( RtlPrefixUnicodeString(&::String1, &v41, 1u) )
                          {
                            if ( v41.Length < 0x60u )
                            {
                              StablePathWithFallback = -1073741767;
LABEL_96:
                              WriteLogMessage(
                                3,
                                L"GetVolumeInStablePath for [%wZ] failed (0x%08X)",
                                &v41,
                                (unsigned int)StablePathWithFallback);
                              goto LABEL_91;
                            }
                            StablePathWithFallback = 0;
                            v44.Buffer = v41.Buffer;
                            *(_DWORD *)&v44.Length = 6291552;
LABEL_81:
                            if ( !(unsigned __int8)WasVolumeSeen(&v44) )
                              continue;
                            goto LABEL_82;
                          }
                          v46 = 0;
                          StablePathWithFallback = GetVolumeDeviceInPath(&v41, &v44, &v46);
                          if ( StablePathWithFallback < 0 )
                            goto LABEL_96;
                        }
                        if ( v44.Length )
                          goto LABEL_81;
LABEL_82:
                        p_DestinationString = &DestinationString;
                        v35 = &v41;
                        if ( !DestinationString.Length )
                          p_DestinationString = 0;
                        if ( !v41.Length )
                          v35 = 0;
                        LOBYTE(v33) = *(_BYTE *)(v32 + 24LL * i + 16);
                        v36 = AddOrUpdateTrackedPathOverride(
                                &String2a,
                                v35,
                                p_DestinationString,
                                v33,
                                *(_DWORD *)(v32 + 24LL * i + 20));
                        StablePathWithFallback = v36;
                        if ( v36 < 0 )
                        {
                          LODWORD(v39) = v36;
                          WriteLogMessage(
                            3,
                            L"AddOrUpdateTrackedPathOverride [%wZ] [%wZ] [%wZ] for tracking table failed (0x%08X)",
                            &String2a,
                            &v41,
                            &DestinationString,
                            v39);
                          goto LABEL_91;
                        }
                        LOBYTE(Timeout) = *(_BYTE *)(v32 + 24LL * i + 16);
                        StablePathWithFallback = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, _DWORD))(*(_QWORD *)qword_140019360 + 40LL))(
                                                   qword_140019360,
                                                   *(_QWORD *)(v26 + 8 * v27),
                                                   *(_QWORD *)(v32 + 24LL * i),
                                                   *(_QWORD *)(v32 + 24LL * i + 8),
                                                   Timeout,
                                                   *(_DWORD *)(v32 + 24LL * i + 20));
                        if ( StablePathWithFallback < 0 )
                        {
                          WriteLogMessage(
                            3,
                            L"AddOrUpdateTrackedStablePathOverride [%s] [%s] [%s] for tracking config failed (0x%08X)",
                            *(_QWORD *)(v26 + 8 * v27));
                          goto LABEL_91;
                        }
                      }
                    }
                  }
                  v24 = v40;
                  v25 = (unsigned int)(v49 + 1);
                  v49 = v25;
                }
              }
            }
LABEL_90:
            KeReleaseMutex(&Mutex, 0);
            v2 = 0;
          }
        }
      }
    }
LABEL_91:
    if ( !v48 )
      goto LABEL_104;
    goto LABEL_102;
  }
  KeReleaseMutex(&Mutex, 0);
  v2 = 0;
  UnloadConfig();
LABEL_101:
  StablePathWithFallback = 0;
LABEL_102:
  if ( String1.Buffer )
  {
    ExFreePoolWithTag(String1.Buffer, 0x6E6D7377u);
    String1.Buffer = 0;
  }
LABEL_104:
  if ( v2 )
    KeReleaseMutex(&Mutex, 0);
  return (unsigned int)StablePathWithFallback;
}

```

## disassembly

```asm
0x140001a94  mov     [rsp-8+arg_0], rbx
0x140001a99  push    rbp
0x140001a9a  push    rsi
0x140001a9b  push    rdi
0x140001a9c  push    r12
0x140001a9e  push    r13
0x140001aa0  push    r14
0x140001aa2  push    r15
0x140001aa4  lea     rbp, [rsp-27h]
0x140001aa9  sub     rsp, 0B0h
0x140001ab0  mov     al, cs:byte_140019370
0x140001ab6  xor     r15d, r15d
0x140001ab9  xorps   xmm0, xmm0
0x140001abc  xorps   xmm1, xmm1
0x140001abf  mov     r14, rcx
0x140001ac2  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140001ac6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140001aca  test    al, al
0x140001acc  jz      loc_14000228C
0x140001ad2  xor     r9d, r9d; Alertable
0x140001ad5  mov     [rsp+0E0h+Timeout], r15; Timeout
0x140001ada  xor     r8d, r8d; WaitMode
0x140001add  lea     rcx, Mutex; Object
0x140001ae4  xor     edx, edx; WaitReason
0x140001ae6  call    cs:__imp_KeWaitForSingleObject
0x140001aed  nop     dword ptr [rax+rax+00h]
0x140001af2  cmp     cs:qword_140019348, r15
0x140001af9  lea     edi, [r15+1]
0x140001afd  jz      loc_140001BEA
0x140001b03  mov     rcx, cs:qword_140019350
0x140001b0a  test    rcx, rcx
0x140001b0d  jnz     short loc_140001B32
0x140001b0f  lea     rcx, [rbp+57h+arg_8]
0x140001b13  call    ??$make_unique@VCWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmLogConfig@@U?$default_delete@VCWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig,,0>(void)
0x140001b18  mov     rcx, [rbp+57h+arg_8]
0x140001b1c  test    rcx, rcx
0x140001b1f  jnz     short loc_140001B2B
0x140001b21  mov     ebx, 0C000009Ah
0x140001b26  jmp     loc_140002292
0x140001b2b  mov     cs:qword_140019350, rcx
0x140001b32  mov     rsi, cs:qword_140019348
0x140001b39  test    rsi, rsi
0x140001b3c  jz      short loc_140001BA3
0x140001b3e  test    rcx, rcx
0x140001b41  jz      loc_140001BEA
0x140001b47  mov     rax, [rcx]
0x140001b4a  mov     rax, [rax]
0x140001b4d  call    _guard_dispatch_icall
0x140001b52  mov     rbx, rax
0x140001b55  mov     rcx, rsi
0x140001b58  mov     rax, [rsi]
0x140001b5b  mov     rax, [rax]
0x140001b5e  call    _guard_dispatch_icall
0x140001b63  mov     rsi, rax
0x140001b66  test    rax, rax
0x140001b69  jz      short loc_140001B90
0x140001b6b  test    rbx, rbx
0x140001b6e  jz      short loc_140001B95
0x140001b70  mov     rdx, [rbx]; Str2
0x140001b73  mov     rcx, [rax]; Str1
0x140001b76  call    cs:__imp__wcsicmp
0x140001b7d  nop     dword ptr [rax+rax+00h]
0x140001b82  test    eax, eax
0x140001b84  jnz     short loc_140001B95
0x140001b86  mov     rax, [rbx+8]
0x140001b8a  cmp     [rsi+8], rax
0x140001b8e  jmp     short loc_140001B93
0x140001b90  test    rbx, rbx
0x140001b93  jz      short loc_140001B9A
0x140001b95  mov     al, r15b
0x140001b98  jmp     short loc_140001B9D
0x140001b9a  mov     al, dil
0x140001b9d  test    al, al
0x140001b9f  jnz     short loc_140001BA8
0x140001ba1  jmp     short loc_140001BEA
0x140001ba3  test    rcx, rcx
0x140001ba6  jnz     short loc_140001BEA
0x140001ba8  lea     rdx, aDoneSettingUpL; "Done setting up load-time log config"
0x140001baf  mov     ecx, edi
0x140001bb1  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140001bb6  mov     rcx, cs:qword_140019350
0x140001bbd  mov     rax, [rcx]
0x140001bc0  mov     rax, [rax+8]
0x140001bc4  call    _guard_dispatch_icall
0x140001bc9  mov     rcx, cs:qword_140019348
0x140001bd0  mov     cs:qword_140019350, r15
0x140001bd7  mov     rax, [rcx]
0x140001bda  mov     rax, [rax+8]
0x140001bde  call    _guard_dispatch_icall
0x140001be3  mov     cs:qword_140019348, r15
0x140001bea  mov     rbx, cs:qword_140019358
0x140001bf1  test    rbx, rbx
0x140001bf4  jz      loc_140001CE6
0x140001bfa  mov     rax, [rbx]
0x140001bfd  mov     rcx, rbx
0x140001c00  mov     rax, [rax]
0x140001c03  call    _guard_dispatch_icall
0x140001c08  test    rax, rax
0x140001c0b  jz      loc_140001CC9
0x140001c11  mov     rcx, cs:qword_140019360
0x140001c18  test    rcx, rcx
0x140001c1b  jnz     short loc_140001C3A
0x140001c1d  lea     rcx, [rbp+57h+arg_8]
0x140001c21  call    ??$make_unique@VCWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmTrackingConfig@@U?$default_delete@VCWsmTrackingConfig@@@utl@@@0@XZ; utl::make_unique<CWsmTrackingConfig,,0>(void)
0x140001c26  mov     rcx, [rbp+57h+arg_8]
0x140001c2a  test    rcx, rcx
0x140001c2d  jz      loc_140001B21
0x140001c33  mov     cs:qword_140019360, rcx
0x140001c3a  mov     rbx, cs:qword_140019358
0x140001c41  test    rbx, rbx
0x140001c44  jz      short loc_140001C9C
0x140001c46  test    rcx, rcx
0x140001c49  jz      loc_140001CE6
0x140001c4f  mov     rax, [rcx]
0x140001c52  mov     rax, [rax]
0x140001c55  call    _guard_dispatch_icall
0x140001c5a  mov     rsi, rax
0x140001c5d  mov     rcx, rbx
0x140001c60  mov     rax, [rbx]
0x140001c63  mov     rax, [rax]
0x140001c66  call    _guard_dispatch_icall
0x140001c6b  test    rax, rax
0x140001c6e  jz      short loc_140001C82
0x140001c70  test    rsi, rsi
0x140001c73  jz      short loc_140001C87
0x140001c75  mov     rdx, rsi
0x140001c78  mov     rcx, rax
0x140001c7b  call    operator__
0x140001c80  jmp     short loc_140001C8F
0x140001c82  test    rsi, rsi
0x140001c85  jz      short loc_140001C8C
0x140001c87  mov     al, r15b
0x140001c8a  jmp     short loc_140001C8F
0x140001c8c  mov     al, dil
0x140001c8f  test    al, al
0x140001c91  jnz     short loc_140001CA1
0x140001c93  mov     rbx, cs:qword_140019358
0x140001c9a  jmp     short loc_140001CE6
0x140001c9c  test    rcx, rcx
0x140001c9f  jnz     short loc_140001CE6
0x140001ca1  lea     rdx, aDoneSettingUpL_0; "Done setting up load-time tracking conf"...
0x140001ca8  mov     ecx, edi
0x140001caa  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140001caf  mov     rcx, cs:qword_140019360
0x140001cb6  mov     rax, [rcx]
0x140001cb9  mov     rax, [rax+8]
0x140001cbd  call    _guard_dispatch_icall
0x140001cc2  mov     cs:qword_140019360, r15
0x140001cc9  mov     rcx, cs:qword_140019358
0x140001cd0  mov     rax, [rcx]
0x140001cd3  mov     rax, [rax+8]
0x140001cd7  call    _guard_dispatch_icall
0x140001cdc  mov     rbx, r15
0x140001cdf  mov     cs:qword_140019358, rbx
0x140001ce6  cmp     cs:qword_140019348, r15
0x140001ced  jnz     short loc_140001D16
0x140001cef  test    rbx, rbx
0x140001cf2  jnz     short loc_140001D16
0x140001cf4  xor     edx, edx; Wait
0x140001cf6  lea     rcx, Mutex; Mutex
0x140001cfd  call    cs:__imp_KeReleaseMutex
0x140001d04  nop     dword ptr [rax+rax+00h]
0x140001d09  mov     dil, r15b
0x140001d0c  call    ?UnloadConfig@@YAXXZ; UnloadConfig(void)
0x140001d11  jmp     loc_14000228F
0x140001d16  lea     r8, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140001d1a  mov     rcx, r14; String2
0x140001d1d  lea     rdx, [rbp+57h+String1]; DestinationString
0x140001d21  call    ?GetStablePathWithFallback@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetStablePathWithFallback(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140001d26  mov     ebx, eax
0x140001d28  test    eax, eax
0x140001d2a  js      loc_140002292
0x140001d30  lea     rcx, [rbp+57h+String1]; String1
0x140001d34  mov     [rbp+57h+arg_10], dil
0x140001d38  call    WasVolumeSeen
0x140001d3d  test    al, al
0x140001d3f  jnz     short loc_140001D84
0x140001d41  mov     edx, 18h; NumberOfBytes
0x140001d46  mov     r8d, 6E6D7377h; Tag
0x140001d4c  mov     ecx, edi; PoolType
0x140001d4e  call    cs:__imp_ExAllocatePoolWithTag
0x140001d55  nop     dword ptr [rax+rax+00h]
0x140001d5a  mov     rcx, rax
0x140001d5d  test    rax, rax
0x140001d60  jz      loc_140001B21
0x140001d66  movups  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x140001d6a  mov     [rbp+57h+arg_10], r15b
0x140001d6e  movdqu  xmmword ptr [rax+8], xmm0
0x140001d73  mov     rax, cs:P
0x140001d7a  mov     [rcx], rax
0x140001d7d  mov     cs:P, rcx
0x140001d84  mov     rcx, cs:qword_140019348
0x140001d8b  test    rcx, rcx
0x140001d8e  jz      loc_140001F15
0x140001d94  mov     rax, [rcx]
0x140001d97  mov     rax, [rax]
0x140001d9a  call    _guard_dispatch_icall
0x140001d9f  xorps   xmm0, xmm0
0x140001da2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140001da6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140001daa  mov     rsi, rax
0x140001dad  mov     rdx, [rax]; SourceString
0x140001db0  call    cs:__imp_RtlInitUnicodeString
0x140001db7  nop     dword ptr [rax+rax+00h]
0x140001dbc  mov     r8b, dil; CaseInSensitive
0x140001dbf  lea     rdx, [rbp+57h+DestinationString]; String2
0x140001dc3  lea     rcx, [rbp+57h+String1]; String1
0x140001dc7  call    cs:__imp_RtlPrefixUnicodeString
0x140001dce  nop     dword ptr [rax+rax+00h]
0x140001dd3  test    al, al
0x140001dd5  jz      loc_140001F15
0x140001ddb  mov     rcx, cs:qword_140019350
0x140001de2  mov     rax, [rcx]
0x140001de5  mov     rax, [rax+10h]
0x140001de9  call    _guard_dispatch_icall
0x140001dee  test    al, al
0x140001df0  jnz     loc_140001F15
0x140001df6  xor     edx, edx; bool
0x140001df8  lea     rcx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140001dfc  call    ?SetLogPath@@YAJPEBU_UNICODE_STRING@@_N@Z; SetLogPath(_UNICODE_STRING const *,bool)
0x140001e01  mov     ebx, eax
0x140001e03  test    eax, eax
0x140001e05  js      loc_1400021AD
0x140001e0b  mov     rcx, cs:qword_140019350
0x140001e12  mov     rdx, [rsi]
0x140001e15  mov     rax, [rcx]
0x140001e18  mov     rax, [rax+18h]
0x140001e1c  call    _guard_dispatch_icall
0x140001e21  mov     ebx, eax
0x140001e23  test    eax, eax
0x140001e25  js      loc_1400021AD
0x140001e2b  mov     rcx, [rsi+8]; unsigned __int64
0x140001e2f  test    rcx, rcx
0x140001e32  jz      short loc_140001E66
0x140001e34  xor     edx, edx; bool
0x140001e36  call    ?SetLogMaximumSize@@YAJ_K_N@Z; SetLogMaximumSize(unsigned __int64,bool)
0x140001e3b  mov     ebx, eax
0x140001e3d  test    eax, eax
0x140001e3f  js      loc_1400021AD
0x140001e45  mov     rcx, cs:qword_140019350
0x140001e4c  mov     rdx, [rsi+8]
0x140001e50  mov     rax, [rcx]
0x140001e53  mov     rax, [rax+20h]
0x140001e57  call    _guard_dispatch_icall
0x140001e5c  mov     ebx, eax
0x140001e5e  test    eax, eax
0x140001e60  js      loc_1400021AD
0x140001e66  mov     rcx, cs:qword_140019358
0x140001e6d  test    rcx, rcx
0x140001e70  jz      loc_140002195
0x140001e76  mov     rax, [rcx]
0x140001e79  mov     rax, [rax]
0x140001e7c  call    _guard_dispatch_icall
0x140001e81  mov     rsi, rax
0x140001e84  test    rax, rax
0x140001e87  jz      loc_140001F15
0x140001e8d  mov     rdx, [rax]; SourceString
0x140001e90  xorps   xmm0, xmm0
0x140001e93  xorps   xmm1, xmm1
0x140001e96  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x140001e9a  movups  xmmword ptr [rbp+57h+var_68.Length], xmm1
0x140001e9e  test    rdx, rdx
0x140001ea1  jz      short loc_140001EB3
0x140001ea3  lea     rcx, [rbp+57h+String2]; DestinationString
0x140001ea7  call    cs:__imp_RtlInitUnicodeString
0x140001eae  nop     dword ptr [rax+rax+00h]
0x140001eb3  mov     rdx, [rsi+8]; SourceString
0x140001eb7  test    rdx, rdx
0x140001eba  jz      short loc_140001ECC
0x140001ebc  lea     rcx, [rbp+57h+var_68]; DestinationString
0x140001ec0  call    cs:__imp_RtlInitUnicodeString
0x140001ec7  nop     dword ptr [rax+rax+00h]
0x140001ecc  cmp     [rbp+57h+String2.Length], r15w
0x140001ed1  ja      short loc_140001EDA
0x140001ed3  cmp     [rbp+57h+var_68.Length], r15w
0x140001ed8  jbe     short loc_140001F15
0x140001eda  lea     rdx, [rbp+57h+var_68]; PCUNICODE_STRING
0x140001ede  lea     rcx, [rbp+57h+String2]; SourceString
0x140001ee2  call    ?SetLogSessionInfo@@YAJPEBU_UNICODE_STRING@@0@Z; SetLogSessionInfo(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x140001ee7  mov     ebx, eax
0x140001ee9  test    eax, eax
0x140001eeb  js      loc_1400021AD
0x140001ef1  mov     rcx, cs:qword_140019360
0x140001ef8  mov     r8, [rsi+8]
0x140001efc  mov     rdx, [rsi]
0x140001eff  mov     rax, [rcx]
0x140001f02  mov     rax, [rax+10h]
0x140001f06  call    _guard_dispatch_icall
0x140001f0b  mov     ebx, eax
0x140001f0d  test    eax, eax
0x140001f0f  js      loc_1400021AD
0x140001f15  mov     rcx, cs:qword_140019358
0x140001f1c  test    rcx, rcx
0x140001f1f  jz      loc_140002195
0x140001f25  mov     rax, [rcx]
0x140001f28  mov     rax, [rax]
0x140001f2b  call    _guard_dispatch_icall
0x140001f30  mov     [rbp+57h+var_A0], rax
0x140001f34  mov     rcx, rax
0x140001f37  test    rax, rax
  ... truncated ...
```
