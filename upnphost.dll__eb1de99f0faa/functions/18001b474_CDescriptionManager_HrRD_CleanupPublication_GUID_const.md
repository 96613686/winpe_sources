# CDescriptionManager::HrRD_CleanupPublication(_GUID const &)

- ea: `0x18001b474`
- end: `0x18001b7a4`
- name: `?HrRD_CleanupPublication@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18001b060`
- `0x18001c410`

## callees

- `0x180019970`
- `0x1800199a4`
- `0x18001b474`
- `0x18001da24`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a584`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b4ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b4ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b4e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b614`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b4e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b517`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b614`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b55f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b635`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b55f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b5ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b5ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001b67b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001b748`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001b67b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001b748`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b63e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b63e`
- `SSDPAPI!DeregisterService` at `0x18001b58c`
- `SSDPAPI!DeregisterService` at `0x18001b58c`

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
    operator delete(v5);
  }
  if ( v6 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b474  mov     [rsp+arg_8], rdx
0x18001b479  push    rbx
0x18001b47a  push    rbp
0x18001b47b  push    rsi
0x18001b47c  push    rdi
0x18001b47d  push    r12
0x18001b47f  push    r13
0x18001b481  push    r14
0x18001b483  push    r15
0x18001b485  sub     rsp, 28h
0x18001b489  mov     r14, rdx
0x18001b48c  mov     r15, rcx
0x18001b48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b496  lea     r12, WPP_GLOBAL_Control
0x18001b49d  cmp     rcx, r12
0x18001b4a0  jnz     loc_18001B715
0x18001b4a6  mov     ecx, 50h ; 'P'; Size
0x18001b4ab  call    cs:__imp_malloc
0x18001b4b1  mov     rsi, rax
0x18001b4b4  test    rax, rax
0x18001b4b7  jz      loc_18001B739
0x18001b4bd  xor     ebp, ebp
0x18001b4bf  mov     [rax+8], rax
0x18001b4c3  mov     [rax+10h], rbp
0x18001b4c7  mov     [rax+18h], rbp
0x18001b4cb  mov     [rax+28h], rbp
0x18001b4cf  mov     [rax+20h], rbp
0x18001b4d3  mov     [rax+48h], rbp
0x18001b4d7  mov     [rax], rax
0x18001b4da  lea     rdi, [r15+1E8h]
0x18001b4e1  mov     rcx, rdi; lpCriticalSection
0x18001b4e4  call    cs:__imp_EnterCriticalSection
0x18001b4ea  xor     ecx, ecx
0x18001b4ec  cmp     ecx, [r15+148h]
0x18001b4f3  jl      loc_18001B683
0x18001b4f9  xor     ebx, ebx
0x18001b4fb  mov     rcx, rdi; lpCriticalSection
0x18001b4fe  call    cs:__imp_LeaveCriticalSection
0x18001b504  test    rbx, rbx
0x18001b507  jnz     loc_18001B743
0x18001b50d  lea     rbx, [r15+210h]
0x18001b514  mov     rcx, rbx; lpCriticalSection
0x18001b517  call    cs:__imp_EnterCriticalSection
0x18001b51d  xor     ecx, ecx
0x18001b51f  lea     r13, [r15+120h]
0x18001b526  cmp     ecx, [r13+8]
0x18001b52a  jge     short loc_18001B559
0x18001b52c  mov     rax, [r14]
0x18001b52f  movsxd  r8, ecx
0x18001b532  mov     rdx, r8
0x18001b535  shl     rdx, 4
0x18001b539  add     rdx, [r13+0]
0x18001b53d  sub     rax, [rdx]
0x18001b540  jnz     short loc_18001B54A
0x18001b542  mov     rax, [r14+8]
0x18001b546  sub     rax, [rdx+8]
0x18001b54a  test    rax, rax
0x18001b54d  jnz     short loc_18001B5C8
0x18001b54f  mov     rax, [r13+10h]
0x18001b553  lea     r14, [rax+r8*8]
0x18001b557  jmp     short loc_18001B55C
0x18001b559  xor     r14d, r14d
0x18001b55c  mov     rcx, rbx; lpCriticalSection
0x18001b55f  call    cs:__imp_LeaveCriticalSection
0x18001b565  test    r14, r14
0x18001b568  jz      short loc_18001B5CF
0x18001b56a  xor     r12d, r12d
0x18001b56d  test    ebp, ebp
0x18001b56f  jns     short loc_18001B5D6
0x18001b571  mov     rax, [r14]
0x18001b574  xor     edi, edi
0x18001b576  mov     ebp, [rax+8]
0x18001b579  test    ebp, ebp
0x18001b57b  jle     short loc_18001B598
0x18001b57d  mov     rax, [r14]
0x18001b580  mov     edx, 1
0x18001b585  mov     rcx, [rax]
0x18001b588  mov     rcx, [rcx+rdi*8]
0x18001b58c  call    cs:__imp_DeregisterService
0x18001b592  inc     edi
0x18001b594  cmp     edi, ebp
0x18001b596  jl      short loc_18001B57D
0x18001b598  mov     rcx, [r14]; void *
0x18001b59b  test    rcx, rcx
0x18001b59e  jz      short loc_18001B5A5
0x18001b5a0  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18001b5a5  mov     rcx, rbx; lpCriticalSection
0x18001b5a8  call    cs:__imp_EnterCriticalSection
0x18001b5ae  mov     rdx, [rsp+68h+arg_8]
0x18001b5b3  mov     rcx, r13
0x18001b5b6  call    ?HrErase@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAJAEBU_GUID@@@Z; CTable<_GUID,_TP_WORK *>::HrErase(_GUID const &)
0x18001b5bb  mov     rcx, rbx; lpCriticalSection
0x18001b5be  mov     ebp, eax
0x18001b5c0  call    cs:__imp_LeaveCriticalSection
0x18001b5c6  jmp     short loc_18001B646
0x18001b5c8  inc     ecx
0x18001b5ca  jmp     loc_18001B526
0x18001b5cf  mov     ebp, 80070057h
0x18001b5d4  jmp     short loc_18001B652
0x18001b5d6  mov     rax, [r14]
0x18001b5d9  lea     r8, [r15+188h]; pcbe
0x18001b5e0  mov     [rsi+20h], rax
0x18001b5e4  lea     rcx, ?BeginRegistration@CDescriptionManager@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b5eb  mov     rax, [rsp+68h+arg_8]
0x18001b5f0  mov     rdx, rsi; pv
0x18001b5f3  movups  xmm0, xmmword ptr [rax]
0x18001b5f6  mov     [rsi+48h], r15
0x18001b5fa  movdqu  xmmword ptr [rsi+34h], xmm0
0x18001b5ff  call    cs:__imp_CreateThreadpoolWork
0x18001b605  mov     r12, rax
0x18001b608  test    rax, rax
0x18001b60b  jz      loc_18001B6CD
0x18001b611  mov     rcx, rdi; lpCriticalSection
0x18001b614  call    cs:__imp_EnterCriticalSection
0x18001b61a  lea     rcx, [r15+260h]
0x18001b621  mov     rax, [rcx]
0x18001b624  mov     [rsi+8], rcx
0x18001b628  mov     [rsi], rax
0x18001b62b  mov     [rax+8], rsi
0x18001b62f  mov     [rcx], rsi
0x18001b632  mov     rcx, rdi; lpCriticalSection
0x18001b635  call    cs:__imp_LeaveCriticalSection
0x18001b63b  mov     rcx, r12; pwk
0x18001b63e  call    cs:__imp_SubmitThreadpoolWork
0x18001b644  xor     esi, esi
0x18001b646  test    r12, r12
0x18001b649  jnz     short loc_18001B676
0x18001b64b  lea     r12, WPP_GLOBAL_Control
0x18001b652  test    rsi, rsi
0x18001b655  jnz     loc_18001B753
0x18001b65b  test    ebp, ebp
0x18001b65d  jnz     loc_18001B76D
0x18001b663  mov     eax, ebp
0x18001b665  add     rsp, 28h
0x18001b669  pop     r15
0x18001b66b  pop     r14
0x18001b66d  pop     r13
0x18001b66f  pop     r12
0x18001b671  pop     rdi
0x18001b672  pop     rsi
0x18001b673  pop     rbp
0x18001b674  pop     rbx
0x18001b675  retn
0x18001b676  xor     edx, edx; fCancelPendingCallbacks
0x18001b678  mov     rcx, r12; pwk
0x18001b67b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001b681  jmp     short loc_18001B64B
0x18001b683  mov     rax, [r14]
0x18001b686  movsxd  r8, ecx
0x18001b689  mov     rdx, r8
0x18001b68c  shl     rdx, 4
0x18001b690  add     rdx, [r15+140h]
0x18001b697  sub     rax, [rdx]
0x18001b69a  jnz     short loc_18001B6A4
0x18001b69c  mov     rax, [r14+8]
0x18001b6a0  sub     rax, [rdx+8]
0x18001b6a4  test    rax, rax
0x18001b6a7  jz      short loc_18001B6B0
0x18001b6a9  inc     ecx
0x18001b6ab  jmp     loc_18001B4EC
0x18001b6b0  mov     rax, [r15+150h]
0x18001b6b7  lea     rbx, [rax+r8*8]
0x18001b6bb  jmp     loc_18001B4FB
0x18001b6c0  test    ebp, ebp
0x18001b6c2  jns     loc_18001B611
0x18001b6c8  jmp     loc_18001B571
0x18001b6cd  call    cs:__imp_GetLastError
0x18001b6d3  mov     ebp, eax
0x18001b6d5  test    eax, eax
0x18001b6d7  jle     short loc_18001B6E2
0x18001b6d9  movzx   ebp, ax
0x18001b6dc  or      ebp, 80070000h
0x18001b6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6e9  lea     rax, WPP_GLOBAL_Control
0x18001b6f0  cmp     rcx, rax
0x18001b6f3  jz      short loc_18001B6C0
0x18001b6f5  test    byte ptr [rcx+1Ch], 40h
0x18001b6f9  jz      short loc_18001B6C0
0x18001b6fb  mov     rcx, [rcx+10h]
0x18001b6ff  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001b706  mov     edx, 60h ; '`'
0x18001b70b  mov     r9d, ebp
0x18001b70e  call    WPP_SF_d
0x18001b713  jmp     short loc_18001B6C0
0x18001b715  test    byte ptr [rcx+1Ch], 40h
0x18001b719  jz      loc_18001B4A6
0x18001b71f  mov     rcx, [rcx+10h]
0x18001b723  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001b72a  mov     edx, 5Fh ; '_'
0x18001b72f  call    WPP_SF_
0x18001b734  jmp     loc_18001B4A6
0x18001b739  mov     ebp, 8007000Eh
0x18001b73e  jmp     loc_18001B4DA
0x18001b743  mov     rcx, [rbx]; pwk
0x18001b746  xor     edx, edx; fCancelPendingCallbacks
0x18001b748  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001b74e  jmp     loc_18001B50D
0x18001b753  mov     rdx, rsi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18001b756  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18001b75b  mov     edx, 50h ; 'P'; unsigned __int64
0x18001b760  mov     rcx, rsi; void *
0x18001b763  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b768  jmp     loc_18001B65B
0x18001b76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b774  cmp     rcx, r12
0x18001b777  jz      loc_18001B663
0x18001b77d  test    byte ptr [rcx+1Ch], 1
0x18001b781  jz      loc_18001B663
0x18001b787  mov     rcx, [rcx+10h]
0x18001b78b  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001b792  mov     edx, 61h ; 'a'
0x18001b797  mov     r9d, ebp
0x18001b79a  call    WPP_SF_d
0x18001b79f  jmp     loc_18001B663
```
