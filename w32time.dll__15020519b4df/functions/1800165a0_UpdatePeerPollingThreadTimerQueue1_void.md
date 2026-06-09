# UpdatePeerPollingThreadTimerQueue1(void)

- ea: `0x1800165a0`
- end: `0x180016958`
- name: `?UpdatePeerPollingThreadTimerQueue1@@YAJXZ`
- size: `952`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014f30`
- `0x180015620`
- `0x1800164f0`

## callees

- `0x1800165a0`
- `0x180018138`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800165d0`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800167f1`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800165d0`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800167f1`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800166b4`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016794`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800166b4`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180016794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001681a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016947`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001681a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016947`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800165f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800165f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016845`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800167c0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800167c0`
- `ntdll!RtlReleaseResource` at `0x1800168d1`
- `ntdll!RtlReleaseResource` at `0x1800168d1`
- `ntdll!RtlAcquireResourceShared` at `0x180016896`
- `ntdll!RtlAcquireResourceShared` at `0x180016896`

## string_xrefs

- `0x18001686a`: `PeerPollingThread: waiting forever\n`
- `0x1800168fc`: `PeerPollingThread: waiting %u.%03us\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 UpdatePeerPollingThreadTimerQueue1(void)
{
  char *v0; // r8
  __int64 *v1; // rdx
  unsigned __int64 v2; // rdi
  int i; // r12d
  __int64 *v4; // r13
  __int64 j; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // r15
  __int64 v7; // rcx
  unsigned __int64 v8; // rbx
  char v9; // di
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  signed int v12; // ebx
  signed int LastError; // eax
  __int64 k; // rdx
  char v16; // [rsp+20h] [rbp-A8h]
  char *v17; // [rsp+D0h] [rbp+8h]
  char *v18; // [rsp+D8h] [rbp+10h]
  __int64 v19; // [rsp+E0h] [rbp+18h]

  v19 = _set_se_translator(SeTransFunc);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  v0 = (char *)g_pnpstate + 408;
  v18 = (char *)g_pnpstate + 408;
  v1 = (__int64 *)((char *)g_pnpstate + 432);
  v17 = (char *)g_pnpstate + 432;
  if ( *((_QWORD *)g_pnpstate + 51) == *((_QWORD *)g_pnpstate + 52) && *v1 == *((_QWORD *)g_pnpstate + 55)
    || *((_DWORD *)g_pnpstate + 19) == *((_DWORD *)g_pnpstate + 18) )
  {
    goto LABEL_46;
  }
  v16 = 1;
  v2 = -1;
  for ( i = 0; i < 2; ++i )
  {
    v4 = v1;
    if ( !i )
      v4 = (__int64 *)v0;
    for ( j = *v4; j != v4[1]; j += 8 )
    {
      v6 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(*(_QWORD *)j + 8LL) + 8LL);
      if ( TryEnterCriticalSection(v6) )
      {
        v7 = *(_QWORD *)(*(_QWORD *)j + 8LL);
        if ( *(_QWORD *)(v7 + 280) < v2 )
        {
          v2 = *(_QWORD *)(v7 + 280);
          v16 = 0;
        }
        LeaveCriticalSection(v6);
      }
    }
    v1 = (__int64 *)v17;
    v0 = v18;
  }
  if ( v16 )
  {
LABEL_46:
    if ( (unsigned __int8)FileLogAllowEntry(103) )
      FileLogAdd(L"PeerPollingThread: waiting forever\n");
    LODWORD(v8) = -1;
  }
  else
  {
    v8 = (v2 + 9999) / 0x2710;
    v9 = 0;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
    {
      if ( _pflstate
        && *((_BYTE *)_pflstate + 315)
        && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        for ( k = *((_QWORD *)_pflstate + 3); k && *(_DWORD *)k <= 0x67u; k = *(_QWORD *)(k + 8) )
        {
          if ( (unsigned int)(*(_DWORD *)(k + 4) + *(_DWORD *)k) > 0x67 )
          {
            v9 = 1;
            break;
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      }
      if ( v9 )
        FileLogAdd(L"PeerPollingThread: waiting %u.%03us\n", (unsigned int)v8 / 0x3E8, (unsigned int)v8 % 0x3E8);
    }
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)g_pnpstate + 17);
  if ( TryEnterCriticalSection(v10) )
  {
    DebugInfo = v10[1].DebugInfo;
    if ( DebugInfo )
    {
      if ( ChangeTimerQueueTimer(0, DebugInfo, v8, 0xFFFFFFFE) )
      {
        v12 = 0;
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v12 = -2147024890;
    }
    LeaveCriticalSection(v10);
    if ( v12 >= 0 )
    {
      _set_se_translator(v19);
      v12 = 0;
    }
  }
  else
  {
    v12 = -2147024890;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pnpstate + 328));
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800165a0  push    rbx
0x1800165a2  push    rsi
0x1800165a3  push    rdi
0x1800165a4  push    r12
0x1800165a6  push    r13
0x1800165a8  push    r14
0x1800165aa  push    r15
0x1800165ac  sub     rsp, 90h
0x1800165b3  mov     [rsp+0C8h+var_A7], 0
0x1800165b8  xor     esi, esi
0x1800165ba  mov     r14d, esi
0x1800165bd  mov     [rsp+0C8h+var_9C], esi
0x1800165c1  mov     r15d, esi
0x1800165c4  mov     [rsp+0C8h+var_98], rsi
0x1800165c9  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x1800165d0  call    cs:__imp__set_se_translator
0x1800165d7  nop     dword ptr [rax+rax+00h]
0x1800165dc  mov     [rsp+0C8h+arg_10], rax
0x1800165e4  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800165eb  add     rcx, 148h; lpCriticalSection
0x1800165f2  call    cs:__imp_EnterCriticalSection
0x1800165f9  nop     dword ptr [rax+rax+00h]
0x1800165fe  mov     [rsp+0C8h+var_A7], 1
0x180016603  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001660a  lea     r8, [rcx+198h]
0x180016611  mov     [rsp+0C8h+arg_8], r8
0x180016619  lea     rdx, [rcx+1B0h]
0x180016620  mov     [rsp+0C8h+arg_0], rdx
0x180016628  mov     rax, [r8+8]
0x18001662c  cmp     [r8], rax
0x18001662f  jz      loc_180016716
0x180016635  mov     eax, [rcx+48h]
0x180016638  cmp     [rcx+4Ch], eax
0x18001663b  jz      loc_180016723
0x180016641  mov     [rsp+0C8h+var_A8], 1
0x180016646  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001664d  mov     [rsp+0C8h+var_88], rdi
0x180016652  mov     r12d, esi
0x180016655  mov     [rsp+0C8h+var_90], esi
0x180016659  cmp     r12d, 2
0x18001665d  jge     loc_180016745
0x180016663  mov     r13, rdx
0x180016666  test    r12d, r12d
0x180016669  cmovz   r13, r8
0x18001666d  mov     rbx, [r13+0]
0x180016671  mov     [rsp+0C8h+var_80], rbx
0x180016676  mov     rax, [r13+8]
0x18001667a  mov     [rsp+0C8h+arg_18], rax
0x180016682  cmp     rbx, rax
0x180016685  jnz     short loc_1800166A1
0x180016687  inc     r12d
0x18001668a  mov     [rsp+0C8h+var_90], r12d
0x18001668f  mov     rdx, [rsp+0C8h+arg_0]
0x180016697  mov     r8, [rsp+0C8h+arg_8]
0x18001669f  jmp     short loc_180016659
0x1800166a1  mov     rax, [rbx]
0x1800166a4  mov     r15, [rax+8]
0x1800166a8  add     r15, 8
0x1800166ac  mov     [rsp+0C8h+var_98], r15
0x1800166b1  mov     rcx, r15; lpCriticalSection
0x1800166b4  call    cs:__imp_TryEnterCriticalSection
0x1800166bb  nop     dword ptr [rax+rax+00h]
0x1800166c0  mov     r14d, eax
0x1800166c3  mov     [rsp+0C8h+var_9C], eax
0x1800166c7  mov     [rsp+0C8h+var_A4], esi
0x1800166cb  test    eax, eax
0x1800166cd  jz      short loc_180016705
0x1800166cf  mov     rax, [rbx]
0x1800166d2  mov     rcx, [rax+8]
0x1800166d6  mov     rax, [rcx+118h]
0x1800166dd  cmp     rax, rdi
0x1800166e0  jnb     short loc_1800166EF
0x1800166e2  mov     rdi, rax
0x1800166e5  mov     [rsp+0C8h+var_88], rax
0x1800166ea  mov     [rsp+0C8h+var_A8], 0
0x1800166ef  mov     rcx, r15; lpCriticalSection
0x1800166f2  call    cs:__imp_LeaveCriticalSection
0x1800166f9  nop     dword ptr [rax+rax+00h]
0x1800166fe  mov     r14d, esi
0x180016701  mov     [rsp+0C8h+var_9C], esi
0x180016705  mov     [rsp+0C8h+arg_18], rbx
0x18001670d  add     rbx, 8
0x180016711  jmp     loc_180016671
0x180016716  mov     rax, [rdx+8]
0x18001671a  cmp     [rdx], rax
0x18001671d  jnz     loc_180016635
0x180016723  mov     [rsp+0C8h+var_A8], 1
0x180016728  mov     ecx, 67h ; 'g'
0x18001672d  call    FileLogAllowEntry
0x180016732  test    al, al
0x180016734  jnz     loc_18001686A
0x18001673a  mov     ebx, 0FFFFFFFFh
0x18001673f  mov     [rsp+0C8h+var_8C], ebx
0x180016743  jmp     short loc_180016783
0x180016745  cmp     [rsp+0C8h+var_A8], 0
0x18001674a  jnz     short loc_180016728
0x18001674c  add     rdi, 270Fh
0x180016753  mov     rax, 346DC5D63886594Bh
0x18001675d  mul     rdi
0x180016760  mov     rbx, rdx
0x180016763  shr     rbx, 0Bh
0x180016767  mov     [rsp+0C8h+var_8C], ebx
0x18001676b  xor     dil, dil
0x18001676e  mov     [rsp+0C8h+var_A0], dil
0x180016773  xor     eax, eax
0x180016775  lock cmpxchg cs:?_lLoggingEnabled@@3JC, esi; long volatile _lLoggingEnabled
0x18001677d  jnz     loc_18001687B
0x180016783  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18001678a  mov     rdi, [rax+88h]
0x180016791  mov     rcx, rdi; lpCriticalSection
0x180016794  call    cs:__imp_TryEnterCriticalSection
0x18001679b  nop     dword ptr [rax+rax+00h]
0x1800167a0  test    eax, eax
0x1800167a2  jz      loc_180016913
0x1800167a8  mov     rdx, [rdi+28h]; Timer
0x1800167ac  test    rdx, rdx
0x1800167af  jz      loc_180016921
0x1800167b5  mov     r9d, 0FFFFFFFEh; Period
0x1800167bb  mov     r8d, ebx; DueTime
0x1800167be  xor     ecx, ecx; TimerQueue
0x1800167c0  call    cs:__imp_ChangeTimerQueueTimer
0x1800167c7  nop     dword ptr [rax+rax+00h]
0x1800167cc  test    eax, eax
0x1800167ce  jz      short loc_180016845
0x1800167d0  mov     ebx, esi
0x1800167d2  mov     rcx, rdi; lpCriticalSection
0x1800167d5  call    cs:__imp_LeaveCriticalSection
0x1800167dc  nop     dword ptr [rax+rax+00h]
0x1800167e1  mov     [rsp+0C8h+var_A4], ebx
0x1800167e5  test    ebx, ebx
0x1800167e7  js      short loc_180016805
0x1800167e9  mov     rcx, [rsp+0C8h+arg_10]
0x1800167f1  call    cs:__imp__set_se_translator
0x1800167f8  nop     dword ptr [rax+rax+00h]
0x1800167fd  test    ebx, ebx
0x1800167ff  js      short loc_180016805
0x180016801  mov     ebx, esi
0x180016803  jmp     short $+2
0x180016805  cmp     [rsp+0C8h+var_A7], 0
0x18001680a  jz      short loc_180016826
0x18001680c  mov     rcx, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180016813  add     rcx, 148h; lpCriticalSection
0x18001681a  call    cs:__imp_LeaveCriticalSection
0x180016821  nop     dword ptr [rax+rax+00h]
0x180016826  test    r14d, r14d
0x180016829  jnz     loc_180016944
0x18001682f  mov     eax, ebx
0x180016831  add     rsp, 90h
0x180016838  pop     r15
0x18001683a  pop     r14
0x18001683c  pop     r13
0x18001683e  pop     r12
0x180016840  pop     rdi
0x180016841  pop     rsi
0x180016842  pop     rbx
0x180016843  retn
0x180016845  call    cs:__imp_GetLastError
0x18001684c  nop     dword ptr [rax+rax+00h]
0x180016851  nop
0x180016852  mov     ebx, eax
0x180016854  test    eax, eax
0x180016856  jle     loc_1800167D2
0x18001685c  movzx   ebx, ax
0x18001685f  or      ebx, 80070000h
0x180016865  jmp     loc_1800167D2
0x18001686a  lea     rcx, aPeerpollingthr_0; "PeerPollingThread: waiting forever\n"
0x180016871  call    FileLogAdd
0x180016876  jmp     loc_18001673A
0x18001687b  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180016882  test    rcx, rcx
0x180016885  jz      short loc_1800168DD
0x180016887  cmp     [rcx+13Bh], dil
0x18001688e  jz      short loc_1800168DD
0x180016890  add     rcx, 50h ; 'P'; Resource
0x180016894  mov     dl, 1; Wait
0x180016896  call    cs:__imp_RtlAcquireResourceShared
0x18001689d  nop     dword ptr [rax+rax+00h]
0x1800168a2  test    al, al
0x1800168a4  jz      short loc_1800168DD
0x1800168a6  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800168ad  mov     rdx, [r8+18h]
0x1800168b1  test    rdx, rdx
0x1800168b4  jz      short loc_1800168CD
0x1800168b6  mov     ecx, [rdx]
0x1800168b8  cmp     ecx, 67h ; 'g'
0x1800168bb  ja      short loc_1800168CD
0x1800168bd  add     ecx, [rdx+4]
0x1800168c0  cmp     ecx, 67h ; 'g'
0x1800168c3  jbe     short loc_18001690D
0x1800168c5  mov     dil, 1
0x1800168c8  mov     [rsp+0C8h+var_A0], dil
0x1800168cd  lea     rcx, [r8+50h]; Resource
0x1800168d1  call    cs:__imp_RtlReleaseResource
0x1800168d8  nop     dword ptr [rax+rax+00h]
0x1800168dd  test    dil, dil
0x1800168e0  jz      loc_180016783
0x1800168e6  mov     eax, 10624DD3h
0x1800168eb  mul     ebx
0x1800168ed  shr     edx, 6
0x1800168f0  imul    eax, edx, 3E8h
0x1800168f6  mov     r8d, ebx
0x1800168f9  sub     r8d, eax
0x1800168fc  lea     rcx, aPeerpollingthr_4; "PeerPollingThread: waiting %u.%03us\n"
0x180016903  call    FileLogAdd
0x180016908  jmp     loc_180016783
0x18001690d  mov     rdx, [rdx+8]
0x180016911  jmp     short loc_1800168B1
0x180016913  mov     ebx, 80070006h
0x180016918  mov     [rsp+0C8h+var_A4], ebx
0x18001691c  jmp     loc_180016805
0x180016921  mov     ebx, 80070006h
0x180016926  jmp     loc_1800167D2
0x18001692b  jmp     short loc_18001692F
0x18001692d  jmp     short $+2
0x18001692f  xor     esi, esi
0x180016931  mov     r14d, [rsp+0C8h+var_9C]
0x180016936  mov     r15, [rsp+0C8h+var_98]
0x18001693b  mov     ebx, [rsp+0C8h+var_A4]
0x18001693f  jmp     loc_1800167E9
0x180016944  mov     rcx, r15; lpCriticalSection
0x180016947  call    cs:__imp_LeaveCriticalSection
0x18001694e  nop     dword ptr [rax+rax+00h]
0x180016953  jmp     loc_18001682F
```
