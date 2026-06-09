# FirewallManager::InternalUpdateCapabilityAccess(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18002a38c`
- end: `0x18002a70f`
- name: `?InternalUpdateCapabilityAccess@FirewallManager@@AEAAJPEBG00H@Z`
- size: `899`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180070204`

## callees

- `0x180010080`
- `0x180012440`
- `0x180013afc`
- `0x18002a38c`
- `0x18002abb0`
- `0x1800664ec`
- `0x180072664`
- `0x1800c59d4`
- `0x1800c5a70`
- `0x1800c7548`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a48f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a5c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a48f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a5c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a6df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a6df`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a62d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a62d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall FirewallManager::InternalUpdateCapabilityAccess(
        LPCRITICAL_SECTION lpCriticalSection,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v5; // r13
  const unsigned __int16 *v6; // r15
  LPCRITICAL_SECTION v7; // rsi
  const unsigned __int16 *v8; // r12
  __int64 *v9; // rax
  const char *v10; // r9
  __int64 v11; // rcx
  volatile signed __int32 *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // r8
  std::_Ref_count_base *v16; // r15
  const char *v17; // r9
  __int64 result; // rax
  const unsigned __int16 *v19; // [rsp+30h] [rbp-178h]
  __int64 v20; // [rsp+38h] [rbp-170h]
  __int64 v24; // [rsp+50h] [rbp-158h]
  volatile signed __int32 *v26; // [rsp+58h] [rbp-150h]
  std::_Ref_count_base *v35[2]; // [rsp+88h] [rbp-120h] BYREF
  __int128 v36; // [rsp+98h] [rbp-110h]
  __int128 v37; // [rsp+A8h] [rbp-100h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-F0h]
  __int128 v39; // [rsp+C8h] [rbp-E0h] BYREF
  __int128 v40; // [rsp+D8h] [rbp-D0h]
  int v41; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v42[32]; // [rsp+F8h] [rbp-B0h] BYREF
  _BYTE v43[32]; // [rsp+118h] [rbp-90h] BYREF
  _BYTE v44[32]; // [rsp+138h] [rbp-70h] BYREF
  int DebugInfo; // [rsp+158h] [rbp-50h]
  __int64 v46; // [rsp+160h] [rbp-48h]
  std::_Ref_count_base *v47; // [rsp+168h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v19 = a4;
  v5 = a3;
  v6 = a2;
  v7 = lpCriticalSection;
  v8 = a2;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_SSc(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)a3, a5 != 0);
  }
  try
  {
    try
    {
      v9 = (__int64 *)std::make_shared<WcmTimerTracking,char const (&)[40]>((__int64)v35);
      v20 = *v9;
      v11 = *v9;
      v12 = (volatile signed __int32 *)v9[1];
      *v9 = 0;
      v9[1] = 0;
      v24 = v11;
      v26 = v12;
      if ( v35[1] )
        std::_Ref_count_base::_Decref(v35[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanager.cpp",
        v10);
      v12 = v26;
      v20 = v24;
      v7 = lpCriticalSection;
      v8 = a2;
      v19 = a4;
      v6 = a2;
      v5 = a3;
    }
    EnterCriticalSection(v7);
    v39 = 0;
    v40 = 0;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v6[v14] );
    std::wstring::_Construct<1,unsigned short const *>(&v39, v8);
    v37 = 0;
    v38 = 0;
    v15 = -1;
    do
      ++v15;
    while ( v5[v15] );
    std::wstring::_Construct<1,unsigned short const *>(&v37, a3);
    *(_OWORD *)v35 = 0;
    v36 = 0;
    do
      ++v13;
    while ( v19[v13] );
    std::wstring::_Construct<1,unsigned short const *>(v35, a4);
    v41 = a5;
    std::wstring::wstring(v42, &v39);
    std::wstring::wstring(v43, &v37);
    std::wstring::wstring(v44, v35);
    DebugInfo = (int)v7[1].DebugInfo;
    if ( v12 )
      _InterlockedIncrement(v12 + 2);
    v46 = v20;
    v16 = (std::_Ref_count_base *)v12;
    v47 = (std::_Ref_count_base *)v12;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 56));
    if ( LOBYTE(v7[8].DebugInfo) )
    {
      if ( v7 != (LPCRITICAL_SECTION)-56LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 56));
    }
    else
    {
      if ( v7[1].LockCount == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__FirewallManager::InternalUpdateCapabilityAccess_::_3_::_lambda_1___(
          &v7[5],
          &v41);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__FirewallManager::InternalUpdateCapabilityAccess_::_3_::_lambda_1___(
          &v7[7],
          &v41);
      if ( v7 != (LPCRITICAL_SECTION)-56LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 56));
      _InterlockedIncrement64((volatile signed __int64 *)&v7[4].LockSemaphore);
      SubmitThreadpoolWork((PTP_WORK)v7[4].OwningThread);
      v16 = v47;
    }
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v44);
    ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v43);
    ProfileRoutePolicyData::~ProfileRoutePolicyData((ProfileRoutePolicyData *)v42);
    if ( *((_QWORD *)&v36 + 1) > 7u )
      std::_Deallocate<16>(v35[0], (struct std::nothrow_t *)(2LL * *((_QWORD *)&v36 + 1) + 2));
    if ( *((_QWORD *)&v38 + 1) > 7u )
      std::_Deallocate<16>((void *)v37, (struct std::nothrow_t *)(2LL * *((_QWORD *)&v38 + 1) + 2));
    if ( *((_QWORD *)&v40 + 1) > 7u )
      std::_Deallocate<16>((void *)v39, (struct std::nothrow_t *)(2LL * *((_QWORD *)&v40 + 1) + 2));
    LeaveCriticalSection(v7);
    if ( v12 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x139,
                           (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanager.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18002a38c  push    rbx
0x18002a38e  push    rsi
0x18002a38f  push    rdi
0x18002a390  push    r12
0x18002a392  push    r13
0x18002a394  push    r14
0x18002a396  push    r15
0x18002a398  sub     rsp, 170h
0x18002a39f  mov     rax, r9
0x18002a3a2  mov     [rsp+1A8h+var_178], rax
0x18002a3a7  mov     r13, r8
0x18002a3aa  mov     r15, rdx
0x18002a3ad  mov     rsi, rcx
0x18002a3b0  mov     [rsp+1A8h+var_138], rax
0x18002a3b5  mov     [rsp+1A8h+var_168], r8
0x18002a3ba  mov     [rsp+1A8h+var_148], rcx
0x18002a3bf  mov     r12, rdx
0x18002a3c2  mov     [rsp+1A8h+var_140], rdx
0x18002a3c7  mov     rdx, r8
0x18002a3ca  mov     [rsp+1A8h+var_128], rdx
0x18002a3d2  mov     [rsp+1A8h+var_160], rax
0x18002a3d7  lea     rax, WPP_GLOBAL_Control
0x18002a3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3e5  xor     edi, edi
0x18002a3e7  cmp     rcx, rax
0x18002a3ea  jz      short loc_18002A417
0x18002a3ec  cmp     byte ptr [rcx+19h], 4
0x18002a3f0  jb      short loc_18002A417
0x18002a3f2  test    byte ptr [rcx+1Ch], 1
0x18002a3f6  jz      short loc_18002A417
0x18002a3f8  cmp     [rsp+1A8h+arg_20], edi
0x18002a3ff  setnz   al
0x18002a402  mov     [rsp+1A8h+var_180], al; char
0x18002a406  mov     [rsp+1A8h+var_188], rdx; __int64
0x18002a40b  mov     r9, r12
0x18002a40e  mov     rcx, [rcx+10h]; LoggerHandle
0x18002a412  call    WPP_SF_SSc
0x18002a417  xorps   xmm1, xmm1
0x18002a41a  movdqu  [rsp+1A8h+var_158], xmm1
0x18002a420  lea     rcx, [rsp+1A8h+var_120]
0x18002a428  call    ??$make_shared@VWcmTimerTracking@@AEAY0CI@$$CBD@std@@YA?AV?$shared_ptr@VWcmTimerTracking@@@0@AEAY0CI@$$CBD@Z; std::make_shared<WcmTimerTracking,char const (&)[40]>(char const (&)[40])
0x18002a42d  mov     rcx, [rax]
0x18002a430  mov     [rsp+1A8h+var_170], rcx
0x18002a435  mov     r14, [rax+8]
0x18002a439  mov     [rax], rdi
0x18002a43c  mov     [rax+8], rdi
0x18002a440  mov     qword ptr [rsp+1A8h+var_158], rcx
0x18002a445  mov     qword ptr [rsp+1A8h+var_158+8], r14
0x18002a44a  mov     rcx, [rsp+1A8h+var_120+8]; this
0x18002a452  test    rcx, rcx
0x18002a455  jz      short loc_18002A45D
0x18002a457  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a45c  nop
0x18002a45d  jmp     short loc_18002A48C
0x18002a45f  xor     edi, edi
0x18002a461  mov     r14, qword ptr [rsp+1A8h+var_158+8]
0x18002a466  mov     rax, qword ptr [rsp+1A8h+var_158]
0x18002a46b  mov     [rsp+1A8h+var_170], rax
0x18002a470  mov     rsi, [rsp+1A8h+var_148]
0x18002a475  mov     r12, [rsp+1A8h+var_140]
0x18002a47a  mov     rax, [rsp+1A8h+var_138]
0x18002a47f  mov     [rsp+1A8h+var_178], rax
0x18002a484  mov     r15, r12
0x18002a487  mov     r13, [rsp+1A8h+var_168]
0x18002a48c  mov     rcx, rsi; lpCriticalSection
0x18002a48f  call    cs:__imp_EnterCriticalSection
0x18002a495  mov     [rsp+1A8h+var_168], rsi
0x18002a49a  xorps   xmm0, xmm0
0x18002a49d  movups  [rsp+1A8h+var_E0], xmm0
0x18002a4a5  xorps   xmm1, xmm1
0x18002a4a8  movdqu  [rsp+1A8h+var_D0], xmm1
0x18002a4b1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a4b5  mov     r8, rbx
0x18002a4b8  inc     r8
0x18002a4bb  cmp     [r15+r8*2], di
0x18002a4c0  jnz     short loc_18002A4B8
0x18002a4c2  mov     rdx, r12
0x18002a4c5  lea     rcx, [rsp+1A8h+var_E0]
0x18002a4cd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a4d2  nop
0x18002a4d3  xorps   xmm0, xmm0
0x18002a4d6  movups  [rsp+1A8h+var_100], xmm0
0x18002a4de  xorps   xmm1, xmm1
0x18002a4e1  movdqu  [rsp+1A8h+var_F0], xmm1
0x18002a4ea  mov     r8, rbx
0x18002a4ed  inc     r8
0x18002a4f0  cmp     [r13+r8*2+0], di
0x18002a4f6  jnz     short loc_18002A4ED
0x18002a4f8  mov     rdx, [rsp+1A8h+var_128]
0x18002a500  lea     rcx, [rsp+1A8h+var_100]
0x18002a508  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a50d  nop
0x18002a50e  xorps   xmm0, xmm0
0x18002a511  movups  xmmword ptr [rsp+1A8h+var_120], xmm0
0x18002a519  xorps   xmm1, xmm1
0x18002a51c  movdqu  [rsp+1A8h+var_110], xmm1
0x18002a525  mov     rax, [rsp+1A8h+var_178]
0x18002a52a  inc     rbx
0x18002a52d  cmp     [rax+rbx*2], di
0x18002a531  jnz     short loc_18002A52A
0x18002a533  mov     r8, rbx
0x18002a536  mov     rdx, [rsp+1A8h+var_160]
0x18002a53b  lea     rcx, [rsp+1A8h+var_120]
0x18002a543  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a548  nop
0x18002a549  mov     eax, [rsp+1A8h+arg_20]
0x18002a550  mov     [rsp+1A8h+var_B8], eax
0x18002a557  lea     rdx, [rsp+1A8h+var_E0]
0x18002a55f  lea     rcx, [rsp+1A8h+var_B0]
0x18002a567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002a56c  lea     rdx, [rsp+1A8h+var_100]
0x18002a574  lea     rcx, [rsp+1A8h+var_90]
0x18002a57c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002a581  lea     rdx, [rsp+1A8h+var_120]
0x18002a589  lea     rcx, [rsp+1A8h+var_70]
0x18002a591  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18002a596  mov     ecx, [rsi+28h]
0x18002a599  mov     [rsp+1A8h+var_50], ecx
0x18002a5a0  test    r14, r14
0x18002a5a3  jz      short loc_18002A5AA
0x18002a5a5  lock inc dword ptr [r14+8]
0x18002a5aa  mov     rax, [rsp+1A8h+var_170]
0x18002a5af  mov     [rsp+1A8h+var_48], rax
0x18002a5b7  mov     r15, r14
0x18002a5ba  mov     [rsp+1A8h+var_40], r14
0x18002a5c2  lea     rbx, [rsi+38h]
0x18002a5c6  mov     rcx, rbx; lpCriticalSection
0x18002a5c9  call    cs:__imp_EnterCriticalSection
0x18002a5cf  mov     [rsp+1A8h+var_160], rbx
0x18002a5d4  lea     rcx, [rsi+0C8h]
0x18002a5db  cmp     [rcx+78h], dil
0x18002a5df  jz      short loc_18002A5F1
0x18002a5e1  test    rbx, rbx
0x18002a5e4  jz      short loc_18002A63B
0x18002a5e6  mov     rcx, rbx; lpCriticalSection
0x18002a5e9  call    cs:__imp_LeaveCriticalSection
0x18002a5ef  jmp     short loc_18002A63B
0x18002a5f1  lea     rdx, [rsp+1A8h+var_B8]
0x18002a5f9  cmp     dword ptr [rsi+30h], 1
0x18002a5fd  jnz     short loc_18002A606
0x18002a5ff  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__FirewallManager__InternalUpdateCapabilityAccess____3____lambda_1___
0x18002a604  jmp     short loc_18002A610
0x18002a606  add     rcx, 50h ; 'P'
0x18002a60a  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__FirewallManager__InternalUpdateCapabilityAccess____3____lambda_1___
0x18002a60f  nop
0x18002a610  test    rbx, rbx
0x18002a613  jz      short loc_18002A61E
0x18002a615  mov     rcx, rbx; lpCriticalSection
0x18002a618  call    cs:__imp_LeaveCriticalSection
0x18002a61e  lock inc qword ptr [rsi+0B8h]
0x18002a626  mov     rcx, [rsi+0B0h]; pwk
0x18002a62d  call    cs:__imp_SubmitThreadpoolWork
0x18002a633  mov     r15, [rsp+1A8h+var_40]
0x18002a63b  test    r15, r15
0x18002a63e  jz      short loc_18002A648
0x18002a640  mov     rcx, r15; this
0x18002a643  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a648  lea     rcx, [rsp+1A8h+var_70]; this
0x18002a650  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18002a655  lea     rcx, [rsp+1A8h+var_90]; this
0x18002a65d  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18002a662  lea     rcx, [rsp+1A8h+var_B0]; this
0x18002a66a  call    ??1ProfileRoutePolicyData@@QEAA@XZ; ProfileRoutePolicyData::~ProfileRoutePolicyData(void)
0x18002a66f  nop
0x18002a670  mov     rdx, qword ptr [rsp+1A8h+var_110+8]
0x18002a678  cmp     rdx, 7
0x18002a67c  jbe     short loc_18002A694
0x18002a67e  lea     rdx, ds:2[rdx*2]
0x18002a686  mov     rcx, [rsp+1A8h+var_120]
0x18002a68e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a693  nop
0x18002a694  mov     rdx, qword ptr [rsp+1A8h+var_F0+8]
0x18002a69c  cmp     rdx, 7
0x18002a6a0  jbe     short loc_18002A6B8
0x18002a6a2  lea     rdx, ds:2[rdx*2]
0x18002a6aa  mov     rcx, qword ptr [rsp+1A8h+var_100]
0x18002a6b2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a6b7  nop
0x18002a6b8  mov     rdx, qword ptr [rsp+1A8h+var_D0+8]
0x18002a6c0  cmp     rdx, 7
0x18002a6c4  jbe     short loc_18002A6DC
0x18002a6c6  lea     rdx, ds:2[rdx*2]
0x18002a6ce  mov     rcx, qword ptr [rsp+1A8h+var_E0]
0x18002a6d6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a6db  nop
0x18002a6dc  mov     rcx, rsi; lpCriticalSection
0x18002a6df  call    cs:__imp_LeaveCriticalSection
0x18002a6e5  nop
0x18002a6e6  test    r14, r14
0x18002a6e9  jz      short loc_18002A6F3
0x18002a6eb  mov     rcx, r14; this
0x18002a6ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002a6f3  xor     eax, eax
0x18002a6f5  jmp     short loc_18002A6FB
0x18002a6f7  mov     eax, dword ptr [rsp+1A8h+var_178]
0x18002a6fb  add     rsp, 170h
0x18002a702  pop     r15
0x18002a704  pop     r14
0x18002a706  pop     r13
0x18002a708  pop     r12
0x18002a70a  pop     rdi
0x18002a70b  pop     rsi
0x18002a70c  pop     rbx
0x18002a70d  retn
```
