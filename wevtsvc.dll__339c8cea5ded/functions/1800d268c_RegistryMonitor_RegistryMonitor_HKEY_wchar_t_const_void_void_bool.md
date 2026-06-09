# RegistryMonitor::RegistryMonitor(HKEY__ *,wchar_t const *,void (*)(void *,bool),...)

- ea: `0x1800d268c`
- end: `0x1800d294a`
- name: `??0RegistryMonitor@@QEAA@PEAUHKEY__@@PEB_WP6AXPEAX_N@_E2KK@Z`
- size: `702`
- prototype: `char *__fastcall(char *pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180080d50`

## callees

- `0x180006770`
- `0x18005ff90`
- `0x180092008`
- `0x1800d268c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d281c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800d281c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2790`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2790`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800d2933`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800d2933`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800d28a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800d28a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d26dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d26dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d26f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d28b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d26f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d28b6`

## string_xrefs

- `0x1800d2782`: `SYSTEM\CurrentControlSet\Services\Eventlog`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall RegistryMonitor::RegistryMonitor(char *pv)
{
  HANDLE *v2; // rsi
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  HKEY *phkResult; // rax
  unsigned int v6; // eax
  unsigned int v7; // edi
  DWORD v8; // ebx
  struct _TP_WAIT *ThreadpoolWait; // rax
  DWORD v10; // ebx
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-28h]
  DWORD v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+4Ch] [rbp-1Ch]
  int v16; // [rsp+50h] [rbp-18h]

  *(_QWORD *)pv = 0;
  v2 = (HANDLE *)(pv + 8);
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 2) = ElfRegistryMonitor;
  *((_QWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 4) = 0;
  *((_DWORD *)pv + 10) = 5;
  *((_DWORD *)pv + 11) = -1;
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(v2, EventW);
  if ( *v2 == (HANDLE)-1LL || (char *)*v2 + 1 == HANDLE_FLAG_INHERIT )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = LastError;
    v15 = -1;
    v16 = 45;
    throw (EvtException *)&pExceptionObject;
  }
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>((HKEY *)pv);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\Eventlog", 0, 0x10u, phkResult);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids, v6);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = v7;
    v15 = -1;
    v16 = 52;
    throw (EvtException *)&pExceptionObject;
  }
  *((_DWORD *)pv + 10) |= 0x10000000u;
  if ( RegNotifyChangeKeyValue(*(HKEY *)pv, 1, *((_DWORD *)pv + 10), *v2, 1) )
  {
    v8 = GetLastError();
    if ( !v8 )
      v8 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids, v8);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = v8;
    v15 = -1;
    v16 = 69;
    throw (EvtException *)&pExceptionObject;
  }
  ThreadpoolWait = CreateThreadpoolWait(RegistryMonitor::WaitCallback, pv, 0);
  *((_QWORD *)pv + 4) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v10 = GetLastError();
    if ( !v10 )
      v10 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids, v10);
    }
    pExceptionObject = 0;
    v13 = 0;
    v14 = v10;
    v15 = -1;
    v16 = 79;
    throw (EvtException *)&pExceptionObject;
  }
  SetThreadpoolWait(ThreadpoolWait, *v2, 0);
  return pv;
}

```

## disassembly

```asm
0x1800d268c  mov     [rsp-30h+arg_0], rcx
0x1800d2691  push    rbp
0x1800d2692  push    rbx
0x1800d2693  push    rsi
0x1800d2694  push    rdi
0x1800d2695  push    r12
0x1800d2697  push    r14
0x1800d2699  mov     rbp, rsp
0x1800d269c  sub     rsp, 68h
0x1800d26a0  mov     rbx, rcx
0x1800d26a3  xor     r14d, r14d
0x1800d26a6  mov     [rcx], r14
0x1800d26a9  lea     rsi, [rcx+8]
0x1800d26ad  mov     [rsi], r14
0x1800d26b0  lea     rax, ?ElfRegistryMonitor@@YAXPEAX_N@Z; ElfRegistryMonitor(void *,bool)
0x1800d26b7  mov     [rcx+10h], rax
0x1800d26bb  mov     [rcx+18h], r14
0x1800d26bf  mov     [rcx+20h], r14
0x1800d26c3  mov     dword ptr [rcx+28h], 5
0x1800d26ca  or      r12d, 0FFFFFFFFh
0x1800d26ce  mov     [rcx+2Ch], r12d
0x1800d26d2  xor     r9d, r9d; lpName
0x1800d26d5  xor     r8d, r8d; bInitialState
0x1800d26d8  xor     edx, edx; bManualReset
0x1800d26da  xor     ecx, ecx; lpEventAttributes
0x1800d26dc  call    cs:__imp_CreateEventW
0x1800d26e2  mov     rdx, rax
0x1800d26e5  mov     rcx, rsi
0x1800d26e8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800d26ed  mov     rax, [rsi]
0x1800d26f0  inc     rax
0x1800d26f3  cmp     rax, 1
0x1800d26f7  ja      short loc_1800D276C
0x1800d26f9  call    cs:__imp_GetLastError
0x1800d26ff  mov     ebx, eax
0x1800d2701  mov     eax, 507h
0x1800d2706  test    ebx, ebx
0x1800d2708  cmovz   ebx, eax
0x1800d270b  lea     rcx, WPP_GLOBAL_Control
0x1800d2712  mov     rax, cs:WPP_GLOBAL_Control
0x1800d2719  cmp     rax, rcx
0x1800d271c  jz      short loc_1800D2741
0x1800d271e  test    byte ptr [rax+1Ch], 1
0x1800d2722  jz      short loc_1800D2741
0x1800d2724  cmp     byte ptr [rax+19h], 2
0x1800d2728  jb      short loc_1800D2741
0x1800d272a  lea     edx, [r14+0Dh]
0x1800d272e  mov     r9d, ebx
0x1800d2731  lea     r8, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids
0x1800d2738  mov     rcx, [rax+10h]
0x1800d273c  call    WPP_SF_d
0x1800d2741  xorps   xmm0, xmm0
0x1800d2744  movdqu  [rbp+pExceptionObject], xmm0
0x1800d2749  mov     [rbp+var_28], r14
0x1800d274d  mov     [rbp+var_20], ebx
0x1800d2750  mov     [rbp+var_1C], r12d
0x1800d2754  mov     [rbp+var_18], 2Dh ; '-'
0x1800d275b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d2762  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d2766  call    _CxxThrowException_0
0x1800d276c  mov     rcx, rbx
0x1800d276f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800d2774  mov     [rsp+68h+phkResult], rax; phkResult
0x1800d2779  mov     r9d, 10h; samDesired
0x1800d277f  xor     r8d, r8d; ulOptions
0x1800d2782  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800d2789  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d2790  call    cs:__imp_RegOpenKeyExW
0x1800d2796  mov     edi, eax
0x1800d2798  test    eax, eax
0x1800d279a  jz      short loc_1800D2800
0x1800d279c  lea     rcx, WPP_GLOBAL_Control
0x1800d27a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800d27aa  cmp     r10, rcx
0x1800d27ad  jz      short loc_1800D27D5
0x1800d27af  test    byte ptr [r10+1Ch], 1
0x1800d27b4  jz      short loc_1800D27D5
0x1800d27b6  cmp     byte ptr [r10+19h], 2
0x1800d27bb  jb      short loc_1800D27D5
0x1800d27bd  mov     edx, 0Eh
0x1800d27c2  mov     r9d, eax
0x1800d27c5  lea     r8, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids
0x1800d27cc  mov     rcx, [r10+10h]
0x1800d27d0  call    WPP_SF_d
0x1800d27d5  xorps   xmm0, xmm0
0x1800d27d8  movdqu  [rbp+pExceptionObject], xmm0
0x1800d27dd  mov     [rbp+var_28], r14
0x1800d27e1  mov     [rbp+var_20], edi
0x1800d27e4  mov     [rbp+var_1C], r12d
0x1800d27e8  mov     [rbp+var_18], 34h ; '4'
0x1800d27ef  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d27f6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d27fa  call    _CxxThrowException_0
0x1800d2800  bts     dword ptr [rbx+28h], 1Ch
0x1800d2805  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x1800d280d  mov     r9, [rsi]; hEvent
0x1800d2810  mov     r8d, [rbx+28h]; dwNotifyFilter
0x1800d2814  mov     edx, 1; bWatchSubtree
0x1800d2819  mov     rcx, [rbx]; hKey
0x1800d281c  call    cs:__imp_RegNotifyChangeKeyValue
0x1800d2822  test    eax, eax
0x1800d2824  jz      short loc_1800D289A
0x1800d2826  call    cs:__imp_GetLastError
0x1800d282c  mov     ebx, eax
0x1800d282e  mov     eax, 507h
0x1800d2833  test    ebx, ebx
0x1800d2835  cmovz   ebx, eax
0x1800d2838  lea     rcx, WPP_GLOBAL_Control
0x1800d283f  mov     rax, cs:WPP_GLOBAL_Control
0x1800d2846  cmp     rax, rcx
0x1800d2849  jz      short loc_1800D286F
0x1800d284b  test    byte ptr [rax+1Ch], 1
0x1800d284f  jz      short loc_1800D286F
0x1800d2851  cmp     byte ptr [rax+19h], 2
0x1800d2855  jb      short loc_1800D286F
0x1800d2857  mov     edx, 0Fh
0x1800d285c  mov     r9d, ebx
0x1800d285f  lea     r8, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids
0x1800d2866  mov     rcx, [rax+10h]
0x1800d286a  call    WPP_SF_d
0x1800d286f  xorps   xmm0, xmm0
0x1800d2872  movdqu  [rbp+pExceptionObject], xmm0
0x1800d2877  mov     [rbp+var_28], r14
0x1800d287b  mov     [rbp+var_20], ebx
0x1800d287e  mov     [rbp+var_1C], r12d
0x1800d2882  mov     [rbp+var_18], 45h ; 'E'
0x1800d2889  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d2890  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d2894  call    _CxxThrowException_0
0x1800d289a  xor     r8d, r8d; pcbe
0x1800d289d  mov     rdx, rbx; pv
0x1800d28a0  lea     rcx, ?WaitCallback@RegistryMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800d28a7  call    cs:__imp_CreateThreadpoolWait
0x1800d28ad  mov     [rbx+20h], rax
0x1800d28b1  test    rax, rax
0x1800d28b4  jnz     short loc_1800D292A
0x1800d28b6  call    cs:__imp_GetLastError
0x1800d28bc  mov     ebx, eax
0x1800d28be  mov     eax, 507h
0x1800d28c3  test    ebx, ebx
0x1800d28c5  cmovz   ebx, eax
0x1800d28c8  lea     rcx, WPP_GLOBAL_Control
0x1800d28cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800d28d6  cmp     rax, rcx
0x1800d28d9  jz      short loc_1800D28FF
0x1800d28db  test    byte ptr [rax+1Ch], 1
0x1800d28df  jz      short loc_1800D28FF
0x1800d28e1  cmp     byte ptr [rax+19h], 2
0x1800d28e5  jb      short loc_1800D28FF
0x1800d28e7  mov     edx, 10h
0x1800d28ec  mov     r9d, ebx
0x1800d28ef  lea     r8, WPP_13a5c28b4f7c3afa0eb6ff317d0fb317_Traceguids
0x1800d28f6  mov     rcx, [rax+10h]
0x1800d28fa  call    WPP_SF_d
0x1800d28ff  xorps   xmm0, xmm0
0x1800d2902  movdqu  [rbp+pExceptionObject], xmm0
0x1800d2907  mov     [rbp+var_28], r14
0x1800d290b  mov     [rbp+var_20], ebx
0x1800d290e  mov     [rbp+var_1C], r12d
0x1800d2912  mov     [rbp+var_18], 4Fh ; 'O'
0x1800d2919  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d2920  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800d2924  call    _CxxThrowException_0
0x1800d292a  xor     r8d, r8d; pftTimeout
0x1800d292d  mov     rdx, [rsi]; h
0x1800d2930  mov     rcx, rax; pwa
0x1800d2933  call    cs:__imp_SetThreadpoolWait
0x1800d2939  nop
0x1800d293a  mov     rax, rbx
0x1800d293d  add     rsp, 68h
0x1800d2941  pop     r14
0x1800d2943  pop     r12
0x1800d2945  pop     rdi
0x1800d2946  pop     rsi
0x1800d2947  pop     rbx
0x1800d2948  pop     rbp
0x1800d2949  retn
```
