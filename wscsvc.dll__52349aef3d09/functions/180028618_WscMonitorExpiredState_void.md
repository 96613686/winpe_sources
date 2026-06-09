# WscMonitorExpiredState(void)

- ea: `0x180028618`
- end: `0x1800287a9`
- name: `?WscMonitorExpiredState@@YAJXZ`
- size: `401`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d9e0`
- `0x180025520`

## callees

- `0x1800088b0`
- `0x180008e48`
- `0x1800196e0`
- `0x18001b7f0`
- `0x18001fa14`
- `0x180028618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028662`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002878a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028662`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002878a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002863b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002863b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028737`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028725`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028701`

## pseudocode

```c
__int64 WscMonitorExpiredState(void)
{
  unsigned int v0; // edi
  CThirdPartyManager *v1; // r15
  unsigned int v2; // r14d
  int v3; // ebp
  unsigned int i; // esi
  unsigned int v5; // ebx
  signed int LastError; // eax
  unsigned int v8; // [rsp+60h] [rbp+8h] BYREF

  v0 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
  v1 = WscServiceUtils::g_pAntiVirusManager;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
  v2 = *(_DWORD *)(*((_QWORD *)v1 + 7) + 48LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  v3 = 0;
  if ( v2 > 0x20 )
    v2 = 32;
  for ( i = 0; i < v2; ++i )
  {
    CThirdPartyManager::GetProductBitField(v1, i, &v8);
    v5 = v8;
    if ( (v8 & 0x40000) != 0 )
    {
      if ( (unsigned int)ExtractProductOwner(v8) != 256 && (unsigned int)ExtractProductState(v5) == 4096 )
        goto LABEL_23;
      if ( (unsigned int)ExtractProductState(v5) == 0x4000 || (unsigned int)ExtractProductNotification(v5) == 3145728 )
        v3 = 1;
    }
  }
  if ( v3 && !_InterlockedCompareExchange(&g_lExpiredStateMonitored, 1, 0) )
  {
    if ( g_hThreadExpiredStateMonitor )
    {
      CloseHandle(g_hThreadExpiredStateMonitor);
      g_hThreadExpiredStateMonitor = 0;
    }
    g_hThreadExpiredStateMonitor = CreateThread(
                                     0,
                                     0,
                                     (LPTHREAD_START_ROUTINE)AntivirusExpiredMonitoringThreadProc,
                                     0,
                                     0,
                                     0);
    if ( !g_hThreadExpiredStateMonitor )
    {
      LastError = GetLastError();
      v0 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
          (unsigned int)LastError);
      }
    }
  }
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)WscServiceUtils::g_pAntiVirusManager + 16));
  return v0;
}

```

## disassembly

```asm
0x180028618  mov     [rsp+arg_8], rbx
0x18002861d  mov     [rsp+arg_10], rbp
0x180028622  push    rsi
0x180028623  push    rdi
0x180028624  push    r13
0x180028626  push    r14
0x180028628  push    r15
0x18002862a  sub     rsp, 30h
0x18002862e  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180028635  xor     edi, edi
0x180028637  add     rcx, 10h; lpCriticalSection
0x18002863b  call    cs:__imp_EnterCriticalSection
0x180028641  mov     r15, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180028648  mov     [rsp+58h+arg_0], edi
0x18002864c  lea     rcx, [r15+10h]; lpCriticalSection
0x180028650  call    cs:__imp_EnterCriticalSection
0x180028656  mov     rax, [r15+38h]
0x18002865a  lea     rcx, [r15+10h]; lpCriticalSection
0x18002865e  mov     r14d, [rax+30h]
0x180028662  call    cs:__imp_LeaveCriticalSection
0x180028668  lea     eax, [rdi+20h]
0x18002866b  xor     ebp, ebp
0x18002866d  cmp     r14d, eax
0x180028670  lea     r13d, [rdi+1]
0x180028674  cmova   r14d, eax
0x180028678  xor     esi, esi
0x18002867a  cmp     esi, r14d
0x18002867d  jnb     short loc_1800286DC
0x18002867f  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x180028684  mov     edx, esi; unsigned int
0x180028686  mov     rcx, r15; this
0x180028689  call    ?GetProductBitField@CThirdPartyManager@@QEAAJKAEAK@Z; CThirdPartyManager::GetProductBitField(ulong,ulong &)
0x18002868e  mov     ebx, [rsp+58h+arg_0]
0x180028692  bt      ebx, 12h
0x180028696  jnb     short loc_1800286D7
0x180028698  mov     ecx, ebx
0x18002869a  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x18002869f  cmp     eax, 100h
0x1800286a4  jz      short loc_1800286B8
0x1800286a6  mov     ecx, ebx
0x1800286a8  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x1800286ad  cmp     eax, 1000h
0x1800286b2  jz      loc_18002877F
0x1800286b8  mov     ecx, ebx
0x1800286ba  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x1800286bf  cmp     eax, 4000h
0x1800286c4  jz      short loc_1800286D4
0x1800286c6  mov     ecx, ebx
0x1800286c8  call    ?ExtractProductNotification@@YA?AW4ProductNotification@@K@Z; ExtractProductNotification(ulong)
0x1800286cd  cmp     eax, 300000h
0x1800286d2  jnz     short loc_1800286D7
0x1800286d4  mov     ebp, r13d
0x1800286d7  add     esi, r13d
0x1800286da  jmp     short loc_18002867A
0x1800286dc  test    ebp, ebp
0x1800286de  jz      loc_18002877F
0x1800286e4  xor     eax, eax
0x1800286e6  lock cmpxchg cs:?g_lExpiredStateMonitored@@3JC, r13d; long volatile g_lExpiredStateMonitored
0x1800286ef  jnz     loc_18002877F
0x1800286f5  mov     rcx, cs:?g_hThreadExpiredStateMonitor@@3PEAXEA; hObject
0x1800286fc  test    rcx, rcx
0x1800286ff  jz      short loc_18002870E
0x180028701  call    cs:__imp_CloseHandle
0x180028707  mov     cs:?g_hThreadExpiredStateMonitor@@3PEAXEA, rdi; void * g_hThreadExpiredStateMonitor
0x18002870e  mov     [rsp+58h+lpThreadId], rdi; lpThreadId
0x180028713  lea     r8, ?AntivirusExpiredMonitoringThreadProc@@YAKPEAX@Z; lpStartAddress
0x18002871a  xor     r9d, r9d; lpParameter
0x18002871d  mov     [rsp+58h+dwCreationFlags], edi; dwCreationFlags
0x180028721  xor     edx, edx; dwStackSize
0x180028723  xor     ecx, ecx; lpThreadAttributes
0x180028725  call    cs:__imp_CreateThread
0x18002872b  mov     cs:?g_hThreadExpiredStateMonitor@@3PEAXEA, rax; void * g_hThreadExpiredStateMonitor
0x180028732  test    rax, rax
0x180028735  jnz     short loc_18002877F
0x180028737  call    cs:__imp_GetLastError
0x18002873d  test    eax, eax
0x18002873f  jg      short loc_180028745
0x180028741  mov     edi, eax
0x180028743  jmp     short loc_18002874E
0x180028745  movzx   edi, ax
0x180028748  or      edi, 80070000h
0x18002874e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028755  lea     rdx, WPP_GLOBAL_Control
0x18002875c  cmp     rcx, rdx
0x18002875f  jz      short loc_18002877F
0x180028761  test    [rcx+1Ch], r13b
0x180028765  jz      short loc_18002877F
0x180028767  mov     rcx, [rcx+10h]
0x18002876b  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180028772  mov     edx, 15h
0x180028777  mov     r9d, eax
0x18002877a  call    WPP_SF_d
0x18002877f  mov     rcx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x180028786  add     rcx, 10h; lpCriticalSection
0x18002878a  call    cs:__imp_LeaveCriticalSection
0x180028790  mov     rbx, [rsp+58h+arg_8]
0x180028795  mov     eax, edi
0x180028797  mov     rbp, [rsp+58h+arg_10]
0x18002879c  add     rsp, 30h
0x1800287a0  pop     r15
0x1800287a2  pop     r14
0x1800287a4  pop     r13
0x1800287a6  pop     rdi
0x1800287a7  pop     rsi
0x1800287a8  retn
```
