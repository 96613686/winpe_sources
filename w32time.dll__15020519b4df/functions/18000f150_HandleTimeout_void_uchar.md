# HandleTimeout(void *,uchar)

- ea: `0x18000f150`
- end: `0x18000f3f5`
- name: `?HandleTimeout@@YAXPEAXE@Z`
- size: `677`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d464`
- `0x18000dfd4`
- `0x18000e758`
- `0x18000f150`
- `0x18000f400`
- `0x18000fae0`
- `0x180010e24`
- `0x180011120`
- `0x180018138`
- `0x18001d9a0`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f171`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f2a8`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f171`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000f2a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f2f7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f2f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f233`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f233`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f18c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f18c`
- `ntdll!RtlReleaseResource` at `0x18000f35b`
- `ntdll!RtlReleaseResource` at `0x18000f35b`
- `ntdll!RtlAcquireResourceShared` at `0x18000f320`
- `ntdll!RtlAcquireResourceShared` at `0x18000f320`

## string_xrefs

- `0x18000f370`: `W32TmServiceMain: timeout\n`
- `0x18000f391`: `Triggering re-read of configuration\n`
- `0x18000f3dd`: `Failed in handling timeout, restart service async`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HandleTimeout(void *a1)
{
  int v1; // ebx
  char v2; // di
  signed int updated; // edi
  char v4; // cl
  __int64 i; // rdx
  unsigned int v6; // [rsp+2Ch] [rbp-4Ch]
  __int64 v7; // [rsp+90h] [rbp+18h]

  v1 = 0;
  v7 = _set_se_translator(SeTransFunc);
  EnterCriticalSection(&CriticalSection);
  v6 = dword_1800A468C;
  v2 = 0;
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
          v2 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v2 )
      FileLogAdd(L"W32TmServiceMain: timeout\n");
  }
  updated = UpdateTimerQueue2();
  if ( updated >= 0 )
  {
    if ( dword_1800A45B0 == 2 )
    {
      updated = HandleManagerGoUnsyncd();
      if ( updated < 0 )
        goto LABEL_7;
    }
    else
    {
      v4 = qword_1800A4320 && !dword_1800A45AC;
      updated = HandleManagerGetSamples(v4);
      if ( updated < 0 )
        goto LABEL_7;
    }
    updated = UpdateTimerQueue1();
    if ( updated >= 0 )
    {
      if ( (unsigned int)ShouldConfigBeUpdated(qword_1800A4308) )
      {
        if ( (unsigned __int8)FileLogAllowEntry(62) )
          FileLogAdd(L"Triggering re-read of configuration\n");
        _InterlockedIncrement(&s_lUpdateConfigCount);
        SetEvent(qword_1800A36F0);
      }
      PeriodicallyLogConfigAndStatus((struct StateInfo *)&g_state);
      _set_se_translator(v7);
      updated = 0;
    }
  }
LABEL_7:
  if ( !updated && (dword_1800A468C != v6 || !_InterlockedCompareExchange(&s_bNetlogonSuccessfullyChecked, 0, 0)) )
    v1 = 1;
  LeaveCriticalSection(&CriticalSection);
  if ( v1 )
  {
    if ( !updated )
    {
      SetNetlogonServiceBits(dword_1800A468C);
      return;
    }
  }
  else if ( !updated )
  {
    return;
  }
  if ( (unsigned __int8)FileLogAllowEntry(73) )
    FileLogAdd(L"Failed in handling timeout, restart service async");
  NotifyShutdown(updated);
}

```

## disassembly

```asm
0x18000f150  mov     [rsp+arg_0], rbx
0x18000f155  push    rdi
0x18000f156  sub     rsp, 70h
0x18000f15a  xor     ebx, ebx
0x18000f15c  mov     [rsp+78h+var_50], ebx
0x18000f160  mov     eax, cs:dword_1800A468C
0x18000f166  mov     [rsp+78h+var_4C], eax
0x18000f16a  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000f171  call    cs:__imp__set_se_translator
0x18000f178  nop     dword ptr [rax+rax+00h]
0x18000f17d  mov     [rsp+78h+arg_10], rax
0x18000f185  lea     rcx, CriticalSection; lpCriticalSection
0x18000f18c  call    cs:__imp_EnterCriticalSection
0x18000f193  nop     dword ptr [rax+rax+00h]
0x18000f198  mov     [rsp+78h+var_54], ebx
0x18000f19c  mov     [rsp+78h+var_50], 1
0x18000f1a4  mov     eax, cs:dword_1800A468C
0x18000f1aa  mov     [rsp+78h+var_4C], eax
0x18000f1ae  xor     dil, dil
0x18000f1b1  mov     [rsp+78h+var_58], dil
0x18000f1b6  xor     eax, eax
0x18000f1b8  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebx; long volatile _lLoggingEnabled
0x18000f1c0  jnz     loc_18000F305
0x18000f1c6  call    ?UpdateTimerQueue2@@YAJXZ; UpdateTimerQueue2(void)
0x18000f1cb  mov     edi, eax
0x18000f1cd  mov     [rsp+78h+var_54], eax
0x18000f1d1  test    eax, eax
0x18000f1d3  js      loc_18000F387
0x18000f1d9  cmp     cs:dword_1800A45B0, 2
0x18000f1e0  jz      short loc_18000F25E
0x18000f1e2  cmp     cs:qword_1800A4320, 0
0x18000f1ea  jnz     loc_18000F2C3
0x18000f1f0  xor     ecx, ecx; bool
0x18000f1f2  call    ?HandleManagerGetSamples@@YAJ_N@Z; HandleManagerGetSamples(bool)
0x18000f1f7  mov     edi, eax
0x18000f1f9  mov     [rsp+78h+var_54], eax
0x18000f1fd  test    eax, eax
0x18000f1ff  jns     short loc_18000F270
0x18000f201  cmp     [rsp+78h+var_50], 0
0x18000f206  jz      short loc_18000F247
0x18000f208  test    edi, edi
0x18000f20a  jnz     short loc_18000F22C
0x18000f20c  mov     eax, cs:dword_1800A468C
0x18000f212  cmp     eax, [rsp+78h+var_4C]
0x18000f216  jnz     loc_18000F3B1
0x18000f21c  xor     eax, eax
0x18000f21e  lock cmpxchg cs:?s_bNetlogonSuccessfullyChecked@@3HC, ebx; int volatile s_bNetlogonSuccessfullyChecked
0x18000f226  jz      loc_18000F3B1
0x18000f22c  lea     rcx, CriticalSection; lpCriticalSection
0x18000f233  call    cs:__imp_LeaveCriticalSection
0x18000f23a  nop     dword ptr [rax+rax+00h]
0x18000f23f  test    ebx, ebx
0x18000f241  jnz     loc_18000F3BB
0x18000f247  test    edi, edi
0x18000f249  jnz     loc_18000F3CF
0x18000f24f  mov     rbx, [rsp+78h+arg_0]
0x18000f257  add     rsp, 70h
0x18000f25b  pop     rdi
0x18000f25c  retn
0x18000f25e  call    ?HandleManagerGoUnsyncd@@YAJXZ; HandleManagerGoUnsyncd(void)
0x18000f263  nop
0x18000f264  mov     edi, eax
0x18000f266  mov     [rsp+78h+var_54], eax
0x18000f26a  test    eax, eax
0x18000f26c  jns     short loc_18000F270
0x18000f26e  jmp     short loc_18000F201
0x18000f270  call    ?UpdateTimerQueue1@@YAJXZ; UpdateTimerQueue1(void)
0x18000f275  mov     edi, eax
0x18000f277  mov     [rsp+78h+var_54], eax
0x18000f27b  test    eax, eax
0x18000f27d  js      loc_18000F38C
0x18000f283  mov     rcx, cs:qword_1800A4308; unsigned __int64
0x18000f28a  call    ?ShouldConfigBeUpdated@@YAH_K@Z; ShouldConfigBeUpdated(unsigned __int64)
0x18000f28f  test    eax, eax
0x18000f291  jnz     short loc_18000F2D7
0x18000f293  lea     rcx, ?g_state@@3UStateInfo@@A; struct StateInfo *
0x18000f29a  call    ?PeriodicallyLogConfigAndStatus@@YAXPEAUStateInfo@@@Z; PeriodicallyLogConfigAndStatus(StateInfo *)
0x18000f29f  nop
0x18000f2a0  mov     rcx, [rsp+78h+arg_10]
0x18000f2a8  call    cs:__imp__set_se_translator
0x18000f2af  nop     dword ptr [rax+rax+00h]
0x18000f2b4  test    edi, edi
0x18000f2b6  js      loc_18000F201
0x18000f2bc  mov     edi, ebx
0x18000f2be  jmp     loc_18000F201
0x18000f2c3  cmp     cs:dword_1800A45AC, 0
0x18000f2ca  jnz     loc_18000F1F0
0x18000f2d0  mov     cl, 1
0x18000f2d2  jmp     loc_18000F1F2
0x18000f2d7  mov     ecx, 3Eh ; '>'
0x18000f2dc  call    FileLogAllowEntry
0x18000f2e1  test    al, al
0x18000f2e3  jnz     loc_18000F391
0x18000f2e9  lock inc cs:?s_lUpdateConfigCount@@3JC; long volatile s_lUpdateConfigCount
0x18000f2f0  mov     rcx, cs:qword_1800A36F0; hEvent
0x18000f2f7  call    cs:__imp_SetEvent
0x18000f2fe  nop     dword ptr [rax+rax+00h]
0x18000f303  jmp     short loc_18000F293
0x18000f305  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000f30c  test    rcx, rcx
0x18000f30f  jz      short loc_18000F367
0x18000f311  cmp     [rcx+13Bh], dil
0x18000f318  jz      short loc_18000F367
0x18000f31a  add     rcx, 50h ; 'P'; Resource
0x18000f31e  mov     dl, 1; Wait
0x18000f320  call    cs:__imp_RtlAcquireResourceShared
0x18000f327  nop     dword ptr [rax+rax+00h]
0x18000f32c  test    al, al
0x18000f32e  jz      short loc_18000F367
0x18000f330  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000f337  mov     rdx, [r8+18h]
0x18000f33b  test    rdx, rdx
0x18000f33e  jz      short loc_18000F357
0x18000f340  mov     ecx, [rdx]
0x18000f342  cmp     ecx, 40h ; '@'
0x18000f345  ja      short loc_18000F357
0x18000f347  add     ecx, [rdx+4]
0x18000f34a  cmp     ecx, 40h ; '@'
0x18000f34d  jbe     short loc_18000F381
0x18000f34f  mov     dil, 1
0x18000f352  mov     [rsp+78h+var_58], dil
0x18000f357  lea     rcx, [r8+50h]; Resource
0x18000f35b  call    cs:__imp_RtlReleaseResource
0x18000f362  nop     dword ptr [rax+rax+00h]
0x18000f367  test    dil, dil
0x18000f36a  jz      loc_18000F1C6
0x18000f370  lea     rcx, aW32tmservicema_6; "W32TmServiceMain: timeout\n"
0x18000f377  call    FileLogAdd
0x18000f37c  jmp     loc_18000F1C6
0x18000f381  mov     rdx, [rdx+8]
0x18000f385  jmp     short loc_18000F33B
0x18000f387  jmp     loc_18000F201
0x18000f38c  jmp     loc_18000F201
0x18000f391  lea     rcx, aTriggeringReRe; "Triggering re-read of configuration\n"
0x18000f398  call    FileLogAdd
0x18000f39d  jmp     loc_18000F2E9
0x18000f3a2  jmp     short loc_18000F3A6
0x18000f3a4  jmp     short $+2
0x18000f3a6  xor     ebx, ebx
0x18000f3a8  mov     edi, [rsp+78h+var_54]
0x18000f3ac  jmp     loc_18000F2A0
0x18000f3b1  mov     ebx, 1
0x18000f3b6  jmp     loc_18000F22C
0x18000f3bb  test    edi, edi
0x18000f3bd  jnz     short loc_18000F3CF
0x18000f3bf  mov     ecx, cs:dword_1800A468C; unsigned int
0x18000f3c5  call    ?SetNetlogonServiceBits@@YAJK@Z; SetNetlogonServiceBits(ulong)
0x18000f3ca  jmp     loc_18000F24F
0x18000f3cf  mov     ecx, 49h ; 'I'
0x18000f3d4  call    FileLogAllowEntry
0x18000f3d9  test    al, al
0x18000f3db  jz      short loc_18000F3E9
0x18000f3dd  lea     rcx, aFailedInHandli; "Failed in handling timeout, restart ser"...
0x18000f3e4  call    FileLogAdd
0x18000f3e9  mov     ecx, edi; unsigned int
0x18000f3eb  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x18000f3f0  jmp     loc_18000F24F
```
