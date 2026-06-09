# UpdateTimerQueue1(void)

- ea: `0x180011120`
- end: `0x1800118b7`
- name: `?UpdateTimerQueue1@@YAJXZ`
- size: `1943`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ee90`
- `0x18000f150`
- `0x180012110`
- `0x1800125c0`
- `0x180032ff0`
- `0x180039100`

## callees

- `0x180011120`
- `0x1800118c0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002a6e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001113b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800112fb`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18001113b`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800112fb`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800113c9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800113c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001140a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001140a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001143b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001143b`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800112ae`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800112ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800113f5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800113f5`
- `ntdll!RtlReleaseResource` at `0x1800114d3`
- `ntdll!RtlReleaseResource` at `0x180011647`
- `ntdll!RtlReleaseResource` at `0x180011801`
- `ntdll!RtlReleaseResource` at `0x1800114d3`
- `ntdll!RtlReleaseResource` at `0x180011647`
- `ntdll!RtlReleaseResource` at `0x180011801`
- `ntdll!RtlAcquireResourceShared` at `0x180011494`
- `ntdll!RtlAcquireResourceShared` at `0x18001160c`
- `ntdll!RtlAcquireResourceShared` at `0x1800117c2`
- `ntdll!RtlAcquireResourceShared` at `0x180011494`
- `ntdll!RtlAcquireResourceShared` at `0x18001160c`
- `ntdll!RtlAcquireResourceShared` at `0x1800117c2`

## string_xrefs

- `0x18001169f`: `UpdateTimerQueue1: TN:%I64u::: LRT:%I64u  LUT:%I64u LAFLTNS:%I64u TSLGT:%I64u LTNS:%I64u\n`
- `0x18001186d`: `W32TmServiceMain: waiting %u.%03us\n`
- `0x180011780`: `W32TmServiceMain: waiting ltns%u.%03us (%u.%03us)\n`
- `0x18001158c`: `W32TmServiceMain: waiting i%u.%03us (%u.%03us)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 UpdateTimerQueue1(void)
{
  unsigned int v0; // esi
  __int64 v1; // rax
  unsigned int v2; // ecx
  __int64 v3; // rdi
  __int64 v4; // rdx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // r14
  char v7; // r12
  unsigned __int64 v8; // r14
  char v9; // di
  LPCRITICAL_SECTION v10; // rdi
  __int64 v12; // rcx
  unsigned __int64 v13; // rsi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  signed int LastError; // eax
  char v16; // di
  __int64 k; // rdx
  __int64 v18; // rdx
  unsigned __int64 v19; // r10
  __int64 v20; // rdx
  __int64 i; // rdx
  __int64 Value; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // r10
  __int64 v25; // rdx
  __int64 j; // rdx
  __int64 v27; // rdx
  __int64 v28; // [rsp+20h] [rbp-88h]
  __int64 v29; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+10h]
  __int64 v31; // [rsp+C0h] [rbp+18h]

  v31 = _set_se_translator(SeTransFunc);
  v0 = 0;
  qword_1800A4338 = qword_1800A4310;
  dword_1800A45B0 = 0;
  if ( qword_1800A4320 )
  {
    qword_1800A4338 = qword_1800A4320;
    dword_1800A45B0 = 1;
  }
  v1 = (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24);
  v30 = v1;
  v2 = dword_1800A526C;
  if ( (unsigned int)v1 < dword_1800A5280 )
    v2 = ++dword_1800A526C;
  dword_1800A5280 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  v3 = v1 + ((unsigned __int64)v2 << 32);
  while ( dword_1800A45C8 != dword_1800A45D0 )
    ;
  if ( (unsigned int)dword_1800A45CC + ((unsigned __int64)dword_1800A45C8 << 32) )
    goto LABEL_22;
  do
    v4 = (unsigned int)dword_1800A45D8;
  while ( dword_1800A45D4 != dword_1800A45DC );
  if ( (unsigned int)dword_1800A45D8 + ((unsigned __int64)dword_1800A45D4 << 32) )
  {
LABEL_22:
    while ( dword_1800A45C8 != dword_1800A45D0 )
      ;
    while ( dword_1800A45D4 != dword_1800A45DC )
      ;
    if ( (unsigned int)dword_1800A45CC + ((unsigned __int64)dword_1800A45C8 << 32) <= (unsigned int)dword_1800A45D8
                                                                                    + ((unsigned __int64)dword_1800A45D4 << 32) )
    {
      do
      {
        v12 = dword_1800A45D4;
        v4 = (unsigned int)dword_1800A45D8;
      }
      while ( dword_1800A45D4 != dword_1800A45DC );
    }
    else
    {
      do
      {
        v12 = dword_1800A45C8;
        v4 = (unsigned int)dword_1800A45CC;
      }
      while ( dword_1800A45C8 != dword_1800A45D0 );
    }
    v5 = 10000 * (v3 - (v4 + (v12 << 32)));
    if ( v5 >= qword_1800A4330 )
      v5 = qword_1800A4330;
  }
  else
  {
    v5 = qword_1800A4330;
  }
  if ( !byte_1800A45A1 || (v6 = 10000000LL * *((unsigned int *)qword_1800A42F0 + 27), v6 > 0xC92A69C000LL) )
    v6 = 864000000000LL;
  v7 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x40u; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x40 )
        {
          v7 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v7 )
    {
      asint64::getValue((asint64 *)&dword_1800A45D4);
      Value = asint64::getValue((asint64 *)&dword_1800A45C8);
      HIDWORD(v28) = HIDWORD(v5);
      FileLogAdd(
        L"UpdateTimerQueue1: TN:%I64u::: LRT:%I64u  LUT:%I64u LAFLTNS:%I64u TSLGT:%I64u LTNS:%I64u\n",
        10000 * v3,
        10000 * Value);
    }
  }
  if ( v6 < v5 )
  {
    qword_1800A4338 = 0;
    dword_1800A45B0 = 2;
    goto LABEL_66;
  }
  v8 = v6 - v5;
  if ( v8 < qword_1800A4338 )
  {
    qword_1800A4338 = v8;
    dword_1800A45B0 = 2;
    goto LABEL_66;
  }
  if ( !dword_1800A45B0 )
  {
    v9 = 0;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
    {
      if ( _pflstate
        && *((_BYTE *)_pflstate + 315)
        && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        for ( j = *((_QWORD *)_pflstate + 3); j && *(_DWORD *)j <= 0x40u; j = *(_QWORD *)(j + 8) )
        {
          if ( (unsigned int)(*(_DWORD *)(j + 4) + *(_DWORD *)j) > 0x40 )
          {
            v9 = 1;
            break;
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      }
      if ( v9 )
      {
        v27 = (qword_1800A4310 / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
        FileLogAdd(
          L"W32TmServiceMain: waiting %u.%03us\n",
          qword_1800A4310 / 0x989680uLL,
          qword_1800A4310 / 0x2710uLL - 1000 * ((v27 + ((qword_1800A4310 / 0x2710uLL - v27) >> 1)) >> 9));
      }
    }
    goto LABEL_18;
  }
  if ( dword_1800A45B0 == 2 )
  {
LABEL_66:
    if ( (unsigned __int8)FileLogAllowEntry(64) )
    {
      v23 = (qword_1800A4310 / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      v24 = qword_1800A4310 / 0x2710uLL - 1000 * ((v23 + ((qword_1800A4310 / 0x2710uLL - v23) >> 1)) >> 9);
      v25 = (qword_1800A4338 / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      LODWORD(v28) = v24;
      FileLogAdd(
        L"W32TmServiceMain: waiting ltns%u.%03us (%u.%03us)\n",
        qword_1800A4338 / 0x989680uLL,
        qword_1800A4338 / 0x2710uLL - 1000 * ((v25 + ((qword_1800A4338 / 0x2710uLL - v25) >> 1)) >> 9),
        qword_1800A4310 / 0x989680uLL,
        v28);
    }
    goto LABEL_18;
  }
  v16 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( k = *((_QWORD *)_pflstate + 3); k && *(_DWORD *)k <= 0x40u; k = *(_QWORD *)(k + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(k + 4) + *(_DWORD *)k) > 0x40 )
        {
          v16 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v16 )
    {
      v18 = (qword_1800A4310 / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      v19 = qword_1800A4310 / 0x2710uLL - 1000 * ((v18 + ((qword_1800A4310 / 0x2710uLL - v18) >> 1)) >> 9);
      v20 = (qword_1800A4320 / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      LODWORD(v28) = v19;
      FileLogAdd(
        L"W32TmServiceMain: waiting i%u.%03us (%u.%03us)\n",
        qword_1800A4320 / 0x989680uLL,
        qword_1800A4320 / 0x2710uLL - 1000 * ((v20 + ((qword_1800A4320 / 0x2710uLL - v20) >> 1)) >> 9),
        qword_1800A4310 / 0x989680uLL,
        v28);
    }
  }
LABEL_18:
  v29 = 0;
  GetSystemTimePreciseAsFileTime(&v29, v4);
  qword_1800A4318 = (unsigned int)v29 + ((unsigned __int64)HIDWORD(v29) << 32);
  v10 = lpCriticalSection;
  if ( !lpCriticalSection )
    goto LABEL_19;
  v13 = qword_1800A4338 / 0x2710uLL;
  if ( !TryEnterCriticalSection(lpCriticalSection) )
  {
    v0 = -2147024890;
LABEL_19:
    TakeLSActions((struct StateInfo *)&g_state);
    _set_se_translator(v31);
    if ( (v0 & 0x80000000) == 0 )
      return 0;
    return v0;
  }
  DebugInfo = v10[1].DebugInfo;
  if ( DebugInfo )
  {
    if ( ChangeTimerQueueTimer(0, DebugInfo, v13, 0xFFFFFFu) )
    {
      v0 = 0;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v0 = -2147024890;
  }
  LeaveCriticalSection(v10);
  if ( (int)(v0 + 0x80000000) < 0 || v0 == -2147024890 )
    goto LABEL_19;
  return v0;
}

```

## disassembly

```asm
0x180011120  mov     [rsp+arg_18], rbx
0x180011125  push    rsi
0x180011126  push    rdi
0x180011127  push    r12
0x180011129  push    r14
0x18001112b  push    r15
0x18001112d  sub     rsp, 80h
0x180011134  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18001113b  call    cs:__imp__set_se_translator
0x180011142  nop     dword ptr [rax+rax+00h]
0x180011147  mov     [rsp+0A8h+arg_10], rax
0x18001114f  xor     ebx, ebx
0x180011151  mov     esi, ebx
0x180011153  mov     rax, cs:qword_1800A4310
0x18001115a  mov     cs:qword_1800A4338, rax
0x180011161  mov     cs:dword_1800A45B0, ebx
0x180011167  mov     rax, cs:qword_1800A4320
0x18001116e  test    rax, rax
0x180011171  jnz     loc_1800115BC
0x180011177  mov     [rsp+0A8h+arg_8], rbx
0x18001117f  mov     eax, 7FFE0320h
0x180011184  mov     rax, [rax]
0x180011187  mov     ecx, ds:7FFE0004h
0x18001118e  imul    rcx, rax
0x180011192  shr     rcx, 18h
0x180011196  mov     eax, ecx
0x180011198  mov     [rsp+0A8h+arg_8], rax
0x1800111a0  cmp     ecx, cs:dword_1800A5280
0x1800111a6  mov     ecx, cs:dword_1800A526C
0x1800111ac  jb      loc_1800115D2
0x1800111b2  mov     cs:dword_1800A5280, eax
0x1800111b8  mov     edi, ecx
0x1800111ba  shl     rdi, 20h
0x1800111be  add     rdi, rax
0x1800111c1  mov     ecx, cs:dword_1800A45C8
0x1800111c7  mov     edx, cs:dword_1800A45CC
0x1800111cd  mov     eax, cs:dword_1800A45D0
0x1800111d3  cmp     ecx, eax
0x1800111d5  jnz     short loc_1800111C1
0x1800111d7  shl     rcx, 20h
0x1800111db  add     rcx, rdx
0x1800111de  jnz     loc_180011330
0x1800111e4  mov     ecx, cs:dword_1800A45D4
0x1800111ea  mov     edx, cs:dword_1800A45D8
0x1800111f0  mov     eax, cs:dword_1800A45DC
0x1800111f6  cmp     ecx, eax
0x1800111f8  jnz     short loc_1800111E4
0x1800111fa  shl     rcx, 20h
0x1800111fe  add     rcx, rdx
0x180011201  jnz     loc_180011330
0x180011207  mov     r15, cs:qword_1800A4330
0x18001120e  cmp     cs:byte_1800A45A1, 0
0x180011215  jz      loc_1800115DF
0x18001121b  mov     rax, cs:qword_1800A42F0
0x180011222  mov     ecx, [rax+6Ch]
0x180011225  imul    r14, rcx, 989680h
0x18001122c  mov     rax, 0C92A69C000h
0x180011236  cmp     r14, rax
0x180011239  ja      loc_1800115E9
0x18001123f  xor     r12b, r12b
0x180011242  mov     [rsp+0A8h+var_68], r12b
0x180011247  xor     eax, eax
0x180011249  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x180011251  jnz     loc_1800115F1
0x180011257  cmp     r14, r15
0x18001125a  jb      loc_1800116B9
0x180011260  sub     r14, r15
0x180011263  cmp     r14, cs:qword_1800A4338
0x18001126a  jb      loc_180011791
0x180011270  mov     eax, cs:dword_1800A45B0
0x180011276  test    eax, eax
0x180011278  jnz     loc_180011458
0x18001127e  xor     dil, dil
0x180011281  mov     [rsp+0A8h+var_67], dil
0x180011286  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x18001128e  jnz     loc_1800117A7
0x180011294  mov     r14, 346DC5D63886594Bh
0x18001129e  mov     [rsp+0A8h+arg_0], rbx
0x1800112a6  lea     rcx, [rsp+0A8h+arg_0]
0x1800112ae  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800112b5  nop     dword ptr [rax+rax+00h]
0x1800112ba  mov     edx, dword ptr [rsp+0A8h+arg_0+4]
0x1800112c1  shl     rdx, 20h
0x1800112c5  mov     ecx, dword ptr [rsp+0A8h+arg_0]
0x1800112cc  add     rdx, rcx
0x1800112cf  mov     cs:qword_1800A4318, rdx
0x1800112d6  mov     rdi, cs:lpCriticalSection
0x1800112dd  test    rdi, rdi
0x1800112e0  jnz     loc_1800113B5
0x1800112e6  lea     rcx, ?g_state@@3UStateInfo@@A; struct StateInfo *
0x1800112ed  call    ?TakeLSActions@@YAXPEAUStateInfo@@@Z; TakeLSActions(StateInfo *)
0x1800112f2  nop
0x1800112f3  mov     rcx, [rsp+0A8h+arg_10]
0x1800112fb  call    cs:__imp__set_se_translator
0x180011302  nop     dword ptr [rax+rax+00h]
0x180011307  test    esi, esi
0x180011309  js      short loc_18001130D
0x18001130b  mov     esi, ebx
0x18001130d  mov     eax, esi
0x18001130f  mov     rbx, [rsp+0A8h+arg_18]
0x180011317  add     rsp, 80h
0x18001131e  pop     r15
0x180011320  pop     r14
0x180011322  pop     r12
0x180011324  pop     rdi
0x180011325  pop     rsi
0x180011326  retn
0x180011330  mov     ecx, cs:dword_1800A45C8
0x180011336  mov     r8d, cs:dword_1800A45CC
0x18001133d  mov     eax, cs:dword_1800A45D0
0x180011343  cmp     ecx, eax
0x180011345  jnz     short loc_180011330
0x180011347  mov     edx, ecx
0x180011349  shl     rdx, 20h
0x18001134d  add     rdx, r8
0x180011350  mov     ecx, cs:dword_1800A45D4
0x180011356  mov     r8d, cs:dword_1800A45D8
0x18001135d  mov     eax, cs:dword_1800A45DC
0x180011363  cmp     ecx, eax
0x180011365  jnz     short loc_180011350
0x180011367  shl     rcx, 20h
0x18001136b  add     rcx, r8
0x18001136e  cmp     rdx, rcx
0x180011371  jbe     loc_1800115A0
0x180011377  mov     ecx, cs:dword_1800A45C8
0x18001137d  mov     edx, cs:dword_1800A45CC
0x180011383  mov     eax, cs:dword_1800A45D0
0x180011389  cmp     ecx, eax
0x18001138b  jnz     short loc_180011377
0x18001138d  shl     rcx, 20h
0x180011391  add     rcx, rdx
0x180011394  mov     rax, rdi
0x180011397  sub     rax, rcx
0x18001139a  imul    r15, rax, 2710h
0x1800113a1  cmp     r15, cs:qword_1800A4330
0x1800113a8  cmovnb  r15, cs:qword_1800A4330
0x1800113b0  jmp     loc_18001120E
0x1800113b5  mov     rax, r14
0x1800113b8  mul     cs:qword_1800A4338
0x1800113bf  mov     rsi, rdx
0x1800113c2  shr     rsi, 0Bh
0x1800113c6  mov     rcx, rdi; lpCriticalSection
0x1800113c9  call    cs:__imp_TryEnterCriticalSection
0x1800113d0  nop     dword ptr [rax+rax+00h]
0x1800113d5  test    eax, eax
0x1800113d7  jz      loc_180011890
0x1800113dd  mov     rdx, [rdi+28h]; Timer
0x1800113e1  test    rdx, rdx
0x1800113e4  jz      loc_18001189E
0x1800113ea  mov     r8d, esi; DueTime
0x1800113ed  xor     ecx, ecx; TimerQueue
0x1800113ef  mov     r9d, 0FFFFFFh; Period
0x1800113f5  call    cs:__imp_ChangeTimerQueueTimer
0x1800113fc  nop     dword ptr [rax+rax+00h]
0x180011401  test    eax, eax
0x180011403  jz      short loc_18001143B
0x180011405  mov     esi, ebx
0x180011407  mov     rcx, rdi; lpCriticalSection
0x18001140a  call    cs:__imp_LeaveCriticalSection
0x180011411  nop     dword ptr [rax+rax+00h]
0x180011416  mov     [rsp+0A8h+var_64], esi
0x18001141a  mov     ecx, 80000000h
0x18001141f  lea     eax, [rsi+rcx]
0x180011422  test    ecx, eax
0x180011424  jnz     loc_1800112E6
0x18001142a  cmp     esi, 80070006h
0x180011430  jz      loc_1800112E6
0x180011436  jmp     loc_18001130D
0x18001143b  call    cs:__imp_GetLastError
0x180011442  nop     dword ptr [rax+rax+00h]
0x180011447  mov     esi, eax
0x180011449  test    eax, eax
0x18001144b  jle     short loc_180011407
0x18001144d  movzx   esi, ax
0x180011450  or      esi, 80070000h
0x180011456  jmp     short loc_180011407
0x180011458  cmp     eax, 2
0x18001145b  jz      loc_1800116CA
0x180011461  xor     dil, dil
0x180011464  mov     [rsp+0A8h+var_66], dil
0x180011469  xor     eax, eax
0x18001146b  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x180011473  jz      loc_180011294
0x180011479  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180011480  test    rcx, rcx
0x180011483  jz      short loc_1800114DF
0x180011485  cmp     [rcx+13Bh], dil
0x18001148c  jz      short loc_1800114DF
0x18001148e  add     rcx, 50h ; 'P'; Resource
0x180011492  mov     dl, 1; Wait
0x180011494  call    cs:__imp_RtlAcquireResourceShared
0x18001149b  nop     dword ptr [rax+rax+00h]
0x1800114a0  test    al, al
0x1800114a2  jz      short loc_1800114DF
0x1800114a4  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800114ab  mov     rdx, [r8+18h]
0x1800114af  test    rdx, rdx
0x1800114b2  jz      short loc_1800114CF
0x1800114b4  mov     ecx, [rdx]
0x1800114b6  cmp     ecx, 40h ; '@'
0x1800114b9  ja      short loc_1800114CF
0x1800114bb  add     ecx, [rdx+4]
0x1800114be  cmp     ecx, 40h ; '@'
0x1800114c1  jbe     loc_180011887
0x1800114c7  mov     dil, 1
0x1800114ca  mov     [rsp+0A8h+var_66], dil
0x1800114cf  lea     rcx, [r8+50h]; Resource
0x1800114d3  call    cs:__imp_RtlReleaseResource
0x1800114da  nop     dword ptr [rax+rax+00h]
0x1800114df  test    dil, dil
0x1800114e2  jz      loc_180011294
0x1800114e8  mov     r14, 346DC5D63886594Bh
0x1800114f2  mov     rax, r14
0x1800114f5  mul     cs:qword_1800A4310
0x1800114fc  mov     r10, rdx
0x1800114ff  shr     r10, 0Bh
0x180011503  mov     r11, 624DD2F1A9FBE77h
0x18001150d  mov     rax, r11
0x180011510  mul     r10
0x180011513  mov     rax, r10
0x180011516  sub     rax, rdx
0x180011519  shr     rax, 1
0x18001151c  add     rax, rdx
0x18001151f  shr     rax, 9
0x180011523  imul    rax, 3E8h
0x18001152a  sub     r10, rax
0x18001152d  mov     rdi, 0D6BF94D5E57A42BDh
0x180011537  mov     rax, rdi
0x18001153a  mul     cs:qword_1800A4310
0x180011541  mov     r9, rdx
0x180011544  shr     r9, 17h
0x180011548  mov     rax, r14
0x18001154b  mul     cs:qword_1800A4320
0x180011552  mov     r8, rdx
0x180011555  shr     r8, 0Bh
0x180011559  mov     rax, r11
0x18001155c  mul     r8
0x18001155f  mov     rax, r8
0x180011562  sub     rax, rdx
0x180011565  shr     rax, 1
0x180011568  add     rax, rdx
0x18001156b  shr     rax, 9
0x18001156f  imul    rax, 3E8h
0x180011576  sub     r8, rax
0x180011579  mov     rax, rdi
0x18001157c  mul     cs:qword_1800A4320
0x180011583  shr     rdx, 17h
0x180011587  mov     dword ptr [rsp+0A8h+var_88], r10d
0x18001158c  lea     rcx, aW32tmservicema_0; "W32TmServiceMain: waiting i%u.%03us (%u"...
0x180011593  call    FileLogAdd
0x180011598  jmp     loc_18001129E
0x1800115a0  mov     ecx, cs:dword_1800A45D4
0x1800115a6  mov     edx, cs:dword_1800A45D8
0x1800115ac  mov     eax, cs:dword_1800A45DC
0x1800115b2  cmp     ecx, eax
0x1800115b4  jz      loc_18001138D
0x1800115ba  jmp     short loc_1800115A0
0x1800115bc  mov     cs:qword_1800A4338, rax
0x1800115c3  mov     cs:dword_1800A45B0, 1
0x1800115cd  jmp     loc_180011177
0x1800115d2  inc     ecx
0x1800115d4  mov     cs:dword_1800A526C, ecx
0x1800115da  jmp     loc_1800111B2
0x1800115df  mov     rax, 0C92A69C000h
0x1800115e9  mov     r14, rax
0x1800115ec  jmp     loc_18001123F
0x1800115f1  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800115f8  test    rcx, rcx
0x1800115fb  jz      short loc_180011653
0x1800115fd  cmp     [rcx+13Bh], r12b
0x180011604  jz      short loc_180011653
0x180011606  add     rcx, 50h ; 'P'; Resource
0x18001160a  mov     dl, 1; Wait
0x18001160c  call    cs:__imp_RtlAcquireResourceShared
0x180011613  nop     dword ptr [rax+rax+00h]
0x180011618  test    al, al
0x18001161a  jz      short loc_180011653
0x18001161c  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180011623  mov     rdx, [r8+18h]
0x180011627  test    rdx, rdx
0x18001162a  jz      short loc_180011643
0x18001162c  mov     ecx, [rdx]
0x18001162e  cmp     ecx, 40h ; '@'
0x180011631  ja      short loc_180011643
0x180011633  add     ecx, [rdx+4]
0x180011636  cmp     ecx, 40h ; '@'
0x180011639  jbe     short loc_1800116B0
0x18001163b  mov     r12b, 1
0x18001163e  mov     [rsp+0A8h+var_68], r12b
0x180011643  lea     rcx, [r8+50h]; Resource
0x180011647  call    cs:__imp_RtlReleaseResource
0x18001164e  nop     dword ptr [rax+rax+00h]
0x180011653  test    r12b, r12b
0x180011656  jz      loc_180011257
0x18001165c  mov     r10, cs:qword_1800A4330
0x180011663  lea     rcx, dword_1800A45D4; this
0x18001166a  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x18001166f  imul    r9, rax, 2710h
0x180011676  lea     rcx, dword_1800A45C8; this
0x18001167d  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
  ... truncated ...
```
