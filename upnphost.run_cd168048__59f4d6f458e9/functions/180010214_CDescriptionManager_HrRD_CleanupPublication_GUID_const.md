# CDescriptionManager::HrRD_CleanupPublication(_GUID const &)

- ea: `0x180010214`
- end: `0x1800105a9`
- name: `?HrRD_CleanupPublication@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18000fdc0`
- `0x1800112b0`

## callees

- `0x18000e478`
- `0x18000e4b0`
- `0x180010214`
- `0x18001252c`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001024b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001024b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001028a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001028a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800102c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001031b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001038e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001041b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001031b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001038e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001041b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800103d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800103d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001046e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180010547`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001046e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180010547`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001042a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001042a`
- `SSDPAPI!DeregisterService` at `0x18001034e`
- `SSDPAPI!DeregisterService` at `0x18001034e`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrRD_CleanupPublication(CDescriptionManager *this, const struct _GUID *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rsi
  signed int v6; // ebp
  int i; // ecx
  PTP_WORK *v8; // rbx
  int j; // ecx
  _QWORD *v10; // rdx
  __int64 v11; // rax
  void **v12; // r14
  CDescriptionManager *v13; // rcx
  struct _TP_WORK *ThreadpoolWork; // r12
  __int64 v15; // rdi
  int v16; // ebp
  struct _GUID v17; // xmm0
  __int64 v18; // rax
  _QWORD *v20; // rdx
  __int64 v21; // rax
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  v4 = malloc(0x50u);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    v4[1] = v4;
    v4[2] = 0;
    v4[3] = 0;
    v4[5] = 0;
    v4[4] = 0;
    v4[9] = 0;
    *v4 = v4;
  }
  else
  {
    v6 = -2147024882;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 82) )
    {
      v8 = 0;
      goto LABEL_7;
    }
    v20 = (_QWORD *)(*((_QWORD *)this + 40) + 16LL * i);
    v21 = *(_QWORD *)&a2->Data1 - *v20;
    if ( *(_QWORD *)&a2->Data1 == *v20 )
      v21 = *(_QWORD *)a2->Data4 - v20[1];
    if ( !v21 )
      break;
  }
  v8 = (PTP_WORK *)(*((_QWORD *)this + 42) + 8LL * i);
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  if ( v8 )
    WaitForThreadpoolWorkCallbacks(*v8, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  for ( j = 0; j < *((_DWORD *)this + 74); ++j )
  {
    v10 = (_QWORD *)(*((_QWORD *)this + 36) + 16LL * j);
    v11 = *(_QWORD *)&a2->Data1 - *v10;
    if ( *(_QWORD *)&a2->Data1 == *v10 )
      v11 = *(_QWORD *)a2->Data4 - v10[1];
    if ( !v11 )
    {
      v12 = (void **)(*((_QWORD *)this + 38) + 8LL * j);
      goto LABEL_16;
    }
  }
  v12 = 0;
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  if ( v12 )
  {
    ThreadpoolWork = 0;
    if ( v6 < 0 )
      goto LABEL_18;
    v5[4] = *v12;
    v17 = *a2;
    v5[9] = this;
    *(struct _GUID *)((char *)v5 + 52) = v17;
    ThreadpoolWork = CreateThreadpoolWork(
                       CDescriptionManager::BeginRegistration,
                       v5,
                       (PTP_CALLBACK_ENVIRON)((char *)this + 392));
    if ( ThreadpoolWork )
      goto LABEL_26;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
        (unsigned int)v6);
    if ( v6 >= 0 )
    {
LABEL_26:
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
      v18 = *((_QWORD *)this + 76);
      v5[1] = (char *)this + 608;
      *v5 = v18;
      *(_QWORD *)(v18 + 8) = v5;
      *((_QWORD *)this + 76) = v5;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
      SubmitThreadpoolWork(ThreadpoolWork);
      v5 = 0;
    }
    else
    {
LABEL_18:
      v15 = 0;
      v16 = *((_DWORD *)*v12 + 2);
      if ( v16 > 0 )
      {
        do
        {
          DeregisterService(*(_QWORD *)(*(_QWORD *)*v12 + 8 * v15), 1);
          v15 = (unsigned int)(v15 + 1);
        }
        while ( (int)v15 < v16 );
      }
      if ( *v12 )
        CUArray<void *>::`scalar deleting destructor'(*v12);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
      v6 = CTable<_GUID,_TP_WORK *>::HrErase((char *)this + 288, a2);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
    }
    if ( ThreadpoolWork )
      WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v5 )
  {
    CDescriptionManager::PurgeRegistrationParams(v13, (struct SSDP_SERVICE_REGISTRATION_PARAMS *)v5);
    operator delete(v5, 0x50u);
  }
  if ( v6 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010214  mov     [rsp+arg_8], rdx
0x180010219  push    rbx
0x18001021a  push    rbp
0x18001021b  push    rsi
0x18001021c  push    rdi
0x18001021d  push    r12
0x18001021f  push    r13
0x180010221  push    r14
0x180010223  push    r15
0x180010225  sub     rsp, 28h
0x180010229  mov     r14, rdx
0x18001022c  mov     r15, rcx
0x18001022f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010236  lea     r12, WPP_GLOBAL_Control
0x18001023d  cmp     rcx, r12
0x180010240  jnz     loc_180010514
0x180010246  mov     ecx, 50h ; 'P'; Size
0x18001024b  call    cs:__imp_malloc
0x180010252  nop     dword ptr [rax+rax+00h]
0x180010257  mov     rsi, rax
0x18001025a  test    rax, rax
0x18001025d  jz      loc_180010538
0x180010263  xor     ebp, ebp
0x180010265  mov     [rax+8], rax
0x180010269  mov     [rax+10h], rbp
0x18001026d  mov     [rax+18h], rbp
0x180010271  mov     [rax+28h], rbp
0x180010275  mov     [rax+20h], rbp
0x180010279  mov     [rax+48h], rbp
0x18001027d  mov     [rax], rax
0x180010280  lea     rdi, [r15+1E8h]
0x180010287  mov     rcx, rdi; lpCriticalSection
0x18001028a  call    cs:__imp_EnterCriticalSection
0x180010291  nop     dword ptr [rax+rax+00h]
0x180010296  xor     ecx, ecx
0x180010298  cmp     ecx, [r15+148h]
0x18001029f  jl      loc_18001047C
0x1800102a5  xor     ebx, ebx
0x1800102a7  mov     rcx, rdi; lpCriticalSection
0x1800102aa  call    cs:__imp_LeaveCriticalSection
0x1800102b1  nop     dword ptr [rax+rax+00h]
0x1800102b6  test    rbx, rbx
0x1800102b9  jnz     loc_180010542
0x1800102bf  lea     rbx, [r15+210h]
0x1800102c6  mov     rcx, rbx; lpCriticalSection
0x1800102c9  call    cs:__imp_EnterCriticalSection
0x1800102d0  nop     dword ptr [rax+rax+00h]
0x1800102d5  xor     ecx, ecx
0x1800102d7  lea     r13, [r15+120h]
0x1800102de  cmp     ecx, [r13+8]
0x1800102e2  jge     short loc_180010315
0x1800102e4  mov     rax, [r14]
0x1800102e7  movsxd  r8, ecx
0x1800102ea  mov     rdx, r8
0x1800102ed  shl     rdx, 4
0x1800102f1  add     rdx, [r13+0]
0x1800102f5  sub     rax, [rdx]
0x1800102f8  jnz     short loc_180010302
0x1800102fa  mov     rax, [r14+8]
0x1800102fe  sub     rax, [rdx+8]
0x180010302  test    rax, rax
0x180010305  jnz     loc_18001039F
0x18001030b  mov     rax, [r13+10h]
0x18001030f  lea     r14, [rax+r8*8]
0x180010313  jmp     short loc_180010318
0x180010315  xor     r14d, r14d
0x180010318  mov     rcx, rbx; lpCriticalSection
0x18001031b  call    cs:__imp_LeaveCriticalSection
0x180010322  nop     dword ptr [rax+rax+00h]
0x180010327  test    r14, r14
0x18001032a  jz      short loc_1800103A6
0x18001032c  xor     r12d, r12d
0x18001032f  test    ebp, ebp
0x180010331  jns     short loc_1800103B0
0x180010333  mov     rax, [r14]
0x180010336  xor     edi, edi
0x180010338  mov     ebp, [rax+8]
0x18001033b  test    ebp, ebp
0x18001033d  jle     short loc_180010360
0x18001033f  mov     rax, [r14]
0x180010342  mov     edx, 1
0x180010347  mov     rcx, [rax]
0x18001034a  mov     rcx, [rcx+rdi*8]
0x18001034e  call    cs:__imp_DeregisterService
0x180010355  nop     dword ptr [rax+rax+00h]
0x18001035a  inc     edi
0x18001035c  cmp     edi, ebp
0x18001035e  jl      short loc_18001033F
0x180010360  mov     rcx, [r14]; void *
0x180010363  test    rcx, rcx
0x180010366  jz      short loc_18001036D
0x180010368  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18001036d  mov     rcx, rbx; lpCriticalSection
0x180010370  call    cs:__imp_EnterCriticalSection
0x180010377  nop     dword ptr [rax+rax+00h]
0x18001037c  mov     rdx, [rsp+68h+arg_8]
0x180010381  mov     rcx, r13
0x180010384  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x180010389  mov     rcx, rbx; lpCriticalSection
0x18001038c  mov     ebp, eax
0x18001038e  call    cs:__imp_LeaveCriticalSection
0x180010395  nop     dword ptr [rax+rax+00h]
0x18001039a  jmp     loc_180010438
0x18001039f  inc     ecx
0x1800103a1  jmp     loc_1800102DE
0x1800103a6  mov     ebp, 80070057h
0x1800103ab  jmp     loc_180010444
0x1800103b0  mov     rax, [r14]
0x1800103b3  lea     r8, [r15+188h]; pcbe
0x1800103ba  mov     [rsi+20h], rax
0x1800103be  lea     rcx, ?BeginRegistration@CDescriptionManager@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800103c5  mov     rax, [rsp+68h+arg_8]
0x1800103ca  mov     rdx, rsi; pv
0x1800103cd  movups  xmm0, xmmword ptr [rax]
0x1800103d0  mov     [rsi+48h], r15
0x1800103d4  movdqu  xmmword ptr [rsi+34h], xmm0
0x1800103d9  call    cs:__imp_CreateThreadpoolWork
0x1800103e0  nop     dword ptr [rax+rax+00h]
0x1800103e5  mov     r12, rax
0x1800103e8  test    rax, rax
0x1800103eb  jz      loc_1800104C6
0x1800103f1  mov     rcx, rdi; lpCriticalSection
0x1800103f4  call    cs:__imp_EnterCriticalSection
0x1800103fb  nop     dword ptr [rax+rax+00h]
0x180010400  lea     rcx, [r15+260h]
0x180010407  mov     rax, [rcx]
0x18001040a  mov     [rsi+8], rcx
0x18001040e  mov     [rsi], rax
0x180010411  mov     [rax+8], rsi
0x180010415  mov     [rcx], rsi
0x180010418  mov     rcx, rdi; lpCriticalSection
0x18001041b  call    cs:__imp_LeaveCriticalSection
0x180010422  nop     dword ptr [rax+rax+00h]
0x180010427  mov     rcx, r12; pwk
0x18001042a  call    cs:__imp_SubmitThreadpoolWork
0x180010431  nop     dword ptr [rax+rax+00h]
0x180010436  xor     esi, esi
0x180010438  test    r12, r12
0x18001043b  jnz     short loc_180010469
0x18001043d  lea     r12, WPP_GLOBAL_Control
0x180010444  test    rsi, rsi
0x180010447  jnz     loc_180010558
0x18001044d  test    ebp, ebp
0x18001044f  jnz     loc_180010572
0x180010455  mov     eax, ebp
0x180010457  add     rsp, 28h
0x18001045b  pop     r15
0x18001045d  pop     r14
0x18001045f  pop     r13
0x180010461  pop     r12
0x180010463  pop     rdi
0x180010464  pop     rsi
0x180010465  pop     rbp
0x180010466  pop     rbx
0x180010467  retn
0x180010469  xor     edx, edx; fCancelPendingCallbacks
0x18001046b  mov     rcx, r12; pwk
0x18001046e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180010475  nop     dword ptr [rax+rax+00h]
0x18001047a  jmp     short loc_18001043D
0x18001047c  mov     rax, [r14]
0x18001047f  movsxd  r8, ecx
0x180010482  mov     rdx, r8
0x180010485  shl     rdx, 4
0x180010489  add     rdx, [r15+140h]
0x180010490  sub     rax, [rdx]
0x180010493  jnz     short loc_18001049D
0x180010495  mov     rax, [r14+8]
0x180010499  sub     rax, [rdx+8]
0x18001049d  test    rax, rax
0x1800104a0  jz      short loc_1800104A9
0x1800104a2  inc     ecx
0x1800104a4  jmp     loc_180010298
0x1800104a9  mov     rax, [r15+150h]
0x1800104b0  lea     rbx, [rax+r8*8]
0x1800104b4  jmp     loc_1800102A7
0x1800104b9  test    ebp, ebp
0x1800104bb  jns     loc_1800103F1
0x1800104c1  jmp     loc_180010333
0x1800104c6  call    cs:__imp_GetLastError
0x1800104cd  nop     dword ptr [rax+rax+00h]
0x1800104d2  mov     ebp, eax
0x1800104d4  test    eax, eax
0x1800104d6  jle     short loc_1800104E1
0x1800104d8  movzx   ebp, ax
0x1800104db  or      ebp, 80070000h
0x1800104e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104e8  lea     rax, WPP_GLOBAL_Control
0x1800104ef  cmp     rcx, rax
0x1800104f2  jz      short loc_1800104B9
0x1800104f4  test    byte ptr [rcx+1Ch], 40h
0x1800104f8  jz      short loc_1800104B9
0x1800104fa  mov     rcx, [rcx+10h]
0x1800104fe  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180010505  mov     edx, 60h ; '`'
0x18001050a  mov     r9d, ebp
0x18001050d  call    WPP_SF_d
0x180010512  jmp     short loc_1800104B9
0x180010514  test    byte ptr [rcx+1Ch], 40h
0x180010518  jz      loc_180010246
0x18001051e  mov     rcx, [rcx+10h]
0x180010522  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180010529  mov     edx, 5Fh ; '_'
0x18001052e  call    WPP_SF_
0x180010533  jmp     loc_180010246
0x180010538  mov     ebp, 8007000Eh
0x18001053d  jmp     loc_180010280
0x180010542  mov     rcx, [rbx]; pwk
0x180010545  xor     edx, edx; fCancelPendingCallbacks
0x180010547  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001054e  nop     dword ptr [rax+rax+00h]
0x180010553  jmp     loc_1800102BF
0x180010558  mov     rdx, rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001055b  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x180010560  mov     edx, 50h ; 'P'; unsigned __int64
0x180010565  mov     rcx, rsi; void *
0x180010568  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001056d  jmp     loc_18001044D
0x180010572  mov     rcx, cs:WPP_GLOBAL_Control
0x180010579  cmp     rcx, r12
0x18001057c  jz      loc_180010455
0x180010582  test    byte ptr [rcx+1Ch], 1
0x180010586  jz      loc_180010455
0x18001058c  mov     rcx, [rcx+10h]
0x180010590  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180010597  mov     edx, 61h ; 'a'
0x18001059c  mov     r9d, ebp
0x18001059f  call    WPP_SF_d
0x1800105a4  jmp     loc_180010455
```
