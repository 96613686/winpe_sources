# NtpTimeProvCommand(void *,TimeProvCmd,void *)

- ea: `0x180023510`
- end: `0x180023818`
- name: `?NtpTimeProvCommand@@YAJPEAXW4TimeProvCmd@@0@Z`
- size: `776`
- prototype: `__int64 __fastcall(void *, enum TimeProvCmd, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b760`

## callees

- `0x180014560`
- `0x180018138`
- `0x18001d9a0`
- `0x180022060`
- `0x180023510`
- `0x180023820`
- `0x1800239c4`
- `0x18002439c`
- `0x180024bbc`
- `0x18002522c`
- `0x18003748c`
- `0x1800386d4`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18002375c`
- `ntdll!RtlReleaseResource` at `0x18002375c`
- `ntdll!RtlAcquireResourceShared` at `0x180023714`
- `ntdll!RtlAcquireResourceShared` at `0x180023714`

## string_xrefs

- `0x18002364f`: `TPC_UpdateConfig`
- `0x1800236c8`: `(unknown command)`
- `0x180023779`: `TimeProvCommand([%s], %s) called.\n`
- `0x1800237ab`: `  Bad Command: 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NtpTimeProvCommand(void *a1, unsigned int a2, char *a3)
{
  int updated; // ebx
  const wchar_t *v7; // r12
  __int64 result; // rax
  const wchar_t *v9; // r14
  char v10; // r15
  __int64 i; // rdx

  if ( a2 == 3 )
  {
    if ( a1 != (void *)1 )
    {
      updated = PrepareSamples((struct TpcGetSamplesArgs *)a3);
      if ( updated >= 0 )
        goto LABEL_17;
      return (unsigned int)updated;
    }
    *(_QWORD *)(a3 + 12) = 0;
LABEL_17:
    PeriodicallyLogNtpClientStatus();
    return 0;
  }
  switch ( a2 )
  {
    case 0u:
      v7 = L"TPC_TimeJumped";
      break;
    case 1u:
      v7 = L"TPC_UpdateConfig";
      break;
    case 2u:
      v7 = L"TPC_PollIntervalChanged";
      break;
    case 4u:
      v7 = L"TPC_NetTopoChange";
      break;
    case 5u:
      v7 = L"TPC_Query";
      break;
    case 6u:
      v7 = L"TPC_Shutdown";
      break;
    default:
      v7 = L"(unknown command)";
      break;
  }
  if ( a1 == (void *)1 )
  {
    if ( !*((_BYTE *)g_pnpstate + 48) )
      return (unsigned int)-2147024890;
    v9 = L"NtpServer";
  }
  else
  {
    if ( a1 != (void *)2 || !*((_BYTE *)g_pnpstate + 49) )
      return (unsigned int)-2147024890;
    v9 = L"NtpClient";
  }
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
    && _pflstate
    && *((_BYTE *)_pflstate + 315)
    && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    v10 = 0;
    for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x3Bu; i = *(_QWORD *)(i + 8) )
    {
      if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x3B )
      {
        v10 = 1;
        break;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    if ( v10 )
      FileLogAdd(L"TimeProvCommand([%s], %s) called.\n", v9, v7);
  }
  if ( a2 == 4 )
  {
    if ( a1 == (void *)2 || !*((_BYTE *)g_pnpstate + 49) )
    {
      updated = HandleNetTopoChange((struct TpcNetTopoChangeArgs *)a3);
      if ( updated < 0 )
        return (unsigned int)updated;
    }
    goto LABEL_17;
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      if ( a2 == 2 )
      {
        if ( a1 == (void *)2 )
        {
          updated = HandleNtpClientPollIntervalChange();
          if ( updated < 0 )
            return (unsigned int)updated;
        }
        goto LABEL_17;
      }
      if ( a2 == 5 )
      {
        updated = HandleNtpProvQuery(a1, (struct _W32TIME_PROVIDER_QUERY *)a3);
        if ( updated < 0 )
          return (unsigned int)updated;
        goto LABEL_17;
      }
      if ( a2 != 6 )
      {
        updated = -2147024874;
        if ( (unsigned __int8)FileLogAllowEntry(59) )
          FileLogAdd(L"  Bad Command: 0x%08X\n", a2);
        return (unsigned int)updated;
      }
      updated = HandleNtpProvShutdown();
      if ( updated < 0 )
        return (unsigned int)updated;
      goto LABEL_17;
    }
    if ( a1 == (void *)1 )
    {
      updated = UpdateNtpServer();
      if ( updated < 0 )
        return (unsigned int)updated;
      goto LABEL_17;
    }
    result = UpdateNtpClient();
    if ( (int)result >= 0 )
      goto LABEL_17;
  }
  else
  {
    if ( a1 != (void *)2 )
      goto LABEL_17;
    result = HandleNtpClientTimeJump((struct TpcTimeJumpedArgs *)a3);
    if ( (int)result >= 0 )
      goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x180023510  push    rbx
0x180023512  push    rbp
0x180023513  push    rsi
0x180023514  push    rdi
0x180023515  push    r12
0x180023517  push    r14
0x180023519  sub     rsp, 28h
0x18002351d  movsxd  rdi, edx
0x180023520  mov     rsi, r8
0x180023523  mov     rbx, rcx
0x180023526  cmp     edi, 3
0x180023529  jnz     short loc_18002354A
0x18002352b  cmp     rcx, 1
0x18002352f  jz      loc_1800237EE
0x180023535  mov     rcx, r8; struct TpcGetSamplesArgs *
0x180023538  call    ?PrepareSamples@@YAJPEAUTpcGetSamplesArgs@@@Z; PrepareSamples(TpcGetSamplesArgs *)
0x18002353d  mov     ebx, eax
0x18002353f  test    eax, eax
0x180023541  js      short loc_180023593
0x180023543  xor     ebp, ebp
0x180023545  jmp     loc_1800235D9
0x18002354a  cmp     edi, 6; switch 7 cases
0x18002354d  ja      def_180023564; jumptable 0000000180023564 default case, case 3
0x180023553  lea     rdx, __ImageBase
0x18002355a  mov     ecx, ds:(jpt_180023564 - 180000000h)[rdx+rdi*4]
0x180023561  add     rcx, rdx
0x180023564  jmp     rcx; switch jump
0x18002356a  lea     r12, aTpcNettopochan; jumptable 0000000180023564 case 4
0x180023571  cmp     rbx, 1
0x180023575  jz      loc_1800236D4
0x18002357b  cmp     rbx, 2
0x18002357f  jnz     short loc_18002358E
0x180023581  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180023588  cmp     byte ptr [rax+31h], 0
0x18002358c  jnz     short loc_1800235A3
0x18002358e  mov     ebx, 80070006h
0x180023593  mov     eax, ebx
0x180023595  add     rsp, 28h
0x180023599  pop     r14
0x18002359b  pop     r12
0x18002359d  pop     rdi
0x18002359e  pop     rsi
0x18002359f  pop     rbp
0x1800235a0  pop     rbx
0x1800235a1  retn
0x1800235a3  lea     r14, aNtpclient; "NtpClient"
0x1800235aa  xor     ebp, ebp
0x1800235ac  xor     eax, eax
0x1800235ae  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ebp; long volatile _lLoggingEnabled
0x1800235b6  jnz     loc_1800236F1
0x1800235bc  cmp     edi, 4
0x1800235bf  jnz     short loc_1800235E2
0x1800235c1  cmp     rbx, 2
0x1800235c5  jnz     loc_180023667
0x1800235cb  mov     rcx, rsi; struct TpcNetTopoChangeArgs *
0x1800235ce  call    ?HandleNetTopoChange@@YAJPEAUTpcNetTopoChangeArgs@@@Z; HandleNetTopoChange(TpcNetTopoChangeArgs *)
0x1800235d3  mov     ebx, eax
0x1800235d5  test    eax, eax
0x1800235d7  js      short loc_180023593
0x1800235d9  call    ?PeriodicallyLogNtpClientStatus@@YAXXZ; PeriodicallyLogNtpClientStatus(void)
0x1800235de  mov     ebx, ebp
0x1800235e0  jmp     short loc_180023593
0x1800235e2  mov     ecx, edi
0x1800235e4  test    edi, edi
0x1800235e6  jz      short loc_180023604
0x1800235e8  sub     ecx, 1
0x1800235eb  jnz     short loc_180023626
0x1800235ed  cmp     rbx, 1
0x1800235f1  jnz     loc_180023687
0x1800235f7  call    ?UpdateNtpServer@@YAJXZ; UpdateNtpServer(void)
0x1800235fc  mov     ebx, eax
0x1800235fe  test    eax, eax
0x180023600  js      short loc_180023593
0x180023602  jmp     short loc_1800235D9
0x180023604  cmp     rbx, 2
0x180023608  jnz     short loc_1800235D9
0x18002360a  mov     rcx, rsi; struct TpcTimeJumpedArgs *
0x18002360d  call    ?HandleNtpClientTimeJump@@YAJPEAUTpcTimeJumpedArgs@@@Z; HandleNtpClientTimeJump(TpcTimeJumpedArgs *)
0x180023612  mov     ebx, eax
0x180023614  test    eax, eax
0x180023616  jns     short loc_1800235D9
0x180023618  add     rsp, 28h
0x18002361c  pop     r14
0x18002361e  pop     r12
0x180023620  pop     rdi
0x180023621  pop     rsi
0x180023622  pop     rbp
0x180023623  pop     rbx
0x180023624  retn
0x180023626  sub     ecx, 1
0x180023629  jz      loc_1800237D0
0x18002362f  sub     ecx, 3
0x180023632  jnz     loc_18002378D
0x180023638  mov     rdx, rsi; struct _W32TIME_PROVIDER_QUERY *
0x18002363b  mov     rcx, rbx; void *
0x18002363e  call    ?HandleNtpProvQuery@@YAJPEAXPEAU_W32TIME_PROVIDER_QUERY@@@Z; HandleNtpProvQuery(void *,_W32TIME_PROVIDER_QUERY *)
0x180023643  mov     ebx, eax
0x180023645  test    eax, eax
0x180023647  js      loc_180023593
0x18002364d  jmp     short loc_1800235D9
0x18002364f  lea     r12, aTpcUpdateconfi; jumptable 0000000180023564 case 1
0x180023656  jmp     loc_180023571
0x18002365b  lea     r12, aTpcQuery; jumptable 0000000180023564 case 5
0x180023662  jmp     loc_180023571
0x180023667  cmp     rbx, 1
0x18002366b  jnz     loc_1800235D9
0x180023671  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180023678  cmp     [rax+31h], bpl
0x18002367c  jnz     loc_1800235D9
0x180023682  jmp     loc_1800235CB
0x180023687  call    ?UpdateNtpClient@@YAJXZ; UpdateNtpClient(void)
0x18002368c  mov     ebx, eax
0x18002368e  test    eax, eax
0x180023690  jns     loc_1800235D9
0x180023696  add     rsp, 28h
0x18002369a  pop     r14
0x18002369c  pop     r12
0x18002369e  pop     rdi
0x18002369f  pop     rsi
0x1800236a0  pop     rbp
0x1800236a1  pop     rbx
0x1800236a2  retn
0x1800236a4  lea     r12, aTpcTimejumped; jumptable 0000000180023564 case 0
0x1800236ab  jmp     loc_180023571
0x1800236b0  lea     r12, aTpcPollinterva; jumptable 0000000180023564 case 2
0x1800236b7  jmp     loc_180023571
0x1800236bc  lea     r12, aTpcShutdown; jumptable 0000000180023564 case 6
0x1800236c3  jmp     loc_180023571
0x1800236c8  lea     r12, aUnknownCommand; jumptable 0000000180023564 default case, case 3
0x1800236cf  jmp     loc_180023571
0x1800236d4  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800236db  cmp     byte ptr [rax+30h], 0
0x1800236df  jz      loc_18002358E
0x1800236e5  lea     r14, aNtpserver; "NtpServer"
0x1800236ec  jmp     loc_1800235AA
0x1800236f1  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800236f8  test    rcx, rcx
0x1800236fb  jz      loc_1800235BC
0x180023701  cmp     [rcx+13Bh], bpl
0x180023708  jz      loc_1800235BC
0x18002370e  add     rcx, 50h ; 'P'; Resource
0x180023712  mov     dl, 1; Wait
0x180023714  call    cs:__imp_RtlAcquireResourceShared
0x18002371b  nop     dword ptr [rax+rax+00h]
0x180023720  test    al, al
0x180023722  jz      loc_1800235BC
0x180023728  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18002372f  mov     [rsp+58h+arg_0], r15
0x180023734  xor     r15b, r15b
0x180023737  mov     rdx, [r8+18h]
0x18002373b  test    rdx, rdx
0x18002373e  jz      short loc_180023758
0x180023740  mov     ecx, [rdx]
0x180023742  cmp     ecx, 3Bh ; ';'
0x180023745  ja      short loc_180023758
0x180023747  add     ecx, [rdx+4]
0x18002374a  cmp     ecx, 3Bh ; ';'
0x18002374d  ja      short loc_180023755
0x18002374f  mov     rdx, [rdx+8]
0x180023753  jmp     short loc_18002373B
0x180023755  mov     r15b, 1
0x180023758  lea     rcx, [r8+50h]; Resource
0x18002375c  call    cs:__imp_RtlReleaseResource
0x180023763  nop     dword ptr [rax+rax+00h]
0x180023768  test    r15b, r15b
0x18002376b  mov     r15, [rsp+58h+arg_0]
0x180023770  jz      loc_1800235BC
0x180023776  mov     r8, r12
0x180023779  lea     rcx, aTimeprovcomman_1; "TimeProvCommand([%s], %s) called.\n"
0x180023780  mov     rdx, r14
0x180023783  call    FileLogAdd
0x180023788  jmp     loc_1800235BC
0x18002378d  cmp     ecx, 1
0x180023790  jz      short loc_1800237BC
0x180023792  mov     ecx, 3Bh ; ';'
0x180023797  mov     ebx, 80070016h
0x18002379c  call    FileLogAllowEntry
0x1800237a1  test    al, al
0x1800237a3  jz      loc_180023593
0x1800237a9  mov     edx, edi
0x1800237ab  lea     rcx, aBadCommand0x08; "  Bad Command: 0x%08X\n"
0x1800237b2  call    FileLogAdd
0x1800237b7  jmp     loc_180023593
0x1800237bc  call    ?HandleNtpProvShutdown@@YAJXZ; HandleNtpProvShutdown(void)
0x1800237c1  mov     ebx, eax
0x1800237c3  test    eax, eax
0x1800237c5  js      loc_180023593
0x1800237cb  jmp     loc_1800235D9
0x1800237d0  cmp     rbx, 2
0x1800237d4  jnz     loc_1800235D9
0x1800237da  call    ?HandleNtpClientPollIntervalChange@@YAJXZ; HandleNtpClientPollIntervalChange(void)
0x1800237df  mov     ebx, eax
0x1800237e1  test    eax, eax
0x1800237e3  js      loc_180023593
0x1800237e9  jmp     loc_1800235D9
0x1800237ee  xor     ebp, ebp
0x1800237f0  mov     [r8+0Ch], rbp
0x1800237f4  jmp     loc_1800235D9
```
