# winrt::Windows::Internal::Shell::ConsentUx::implementation::GetCacheUnavailableConsentState(tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>)

- ea: `0x180024678`
- end: `0x18002478e`
- name: `?GetCacheUnavailableConsentState@implementation@ConsentUx@Shell@Internal@Windows@winrt@@YA?AUUnifiedConsentState@23456@V?$tip_test@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800254a8`

## callees

- `0x18001962c`
- `0x18001c9e4`
- `0x180022ac4`
- `0x180022d88`
- `0x180024678`
- `0x18002e38c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002477b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002477b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024710`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Internal::Shell::ConsentUx::implementation::GetCacheUnavailableConsentState(
        __int64 a1,
        volatile signed __int32 **a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  char v8; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+70h] [rbp+8h] BYREF
  volatile signed __int32 **v10; // [rsp+78h] [rbp+10h]
  char v11; // [rsp+80h] [rbp+18h] BYREF
  char v12; // [rsp+88h] [rbp+20h] BYREF

  v10 = a2;
  v9 = a1;
  v4 = *tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::ensure_data(a2);
  v9 = (__int64)v4;
  if ( v4 )
    _InterlockedIncrement(v4 + 70);
  EnterCriticalSection((LPCRITICAL_SECTION)v4 + 5);
  ++*((_DWORD *)v4 + 60);
  *((_BYTE *)v4 + 278) = 1;
  tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>(&v9);
  v5 = *a2;
  if ( *a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v5 + 5);
    *((_DWORD *)v5 + 18) |= 0x300u;
    if ( *((_QWORD *)v5 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(v5 + 2), 2u);
    if ( v5 != (volatile signed __int32 *)-200LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v5 + 5);
  }
  LOBYTE(v9) = 1;
  v11 = 0;
  v12 = 0;
  v8 = 0;
  winrt::make<winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentState,bool,bool,bool,bool>(
    a1,
    (unsigned int)&v8,
    (unsigned int)&v12,
    (unsigned int)&v11,
    (__int64)&v9);
  v6 = *a2;
  if ( *a2 && _InterlockedExchangeAdd(v6 + 70, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>((struct _RTL_CRITICAL_SECTION *)v6);
    CoTaskMemFree((LPVOID)v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180024678  mov     [rsp+arg_8], rdx
0x18002467d  mov     [rsp+arg_0], rcx
0x180024682  push    rbx
0x180024683  push    rsi
0x180024684  push    rdi
0x180024685  push    r14
0x180024687  sub     rsp, 48h
0x18002468b  mov     r14, rdx
0x18002468e  mov     rsi, rcx
0x180024691  mov     rcx, rdx
0x180024694  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::ensure_data(void)
0x180024699  mov     rbx, [rax]
0x18002469c  mov     [rsp+68h+arg_0], rbx
0x1800246a1  test    rbx, rbx
0x1800246a4  jz      short loc_1800246AD
0x1800246a6  lock inc dword ptr [rbx+118h]
0x1800246ad  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800246b4  call    cs:__imp_EnterCriticalSection
0x1800246ba  inc     dword ptr [rbx+0F0h]
0x1800246c0  mov     byte ptr [rbx+116h], 1
0x1800246c7  lea     rcx, [rsp+68h+arg_0]
0x1800246cc  call    ??1?$test_data_control@V?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>>(void)
0x1800246d1  mov     rbx, [r14]
0x1800246d4  test    rbx, rbx
0x1800246d7  jz      short loc_180024716
0x1800246d9  lea     rdi, [rbx+0C8h]
0x1800246e0  mov     rcx, rdi; lpCriticalSection
0x1800246e3  call    cs:__imp_EnterCriticalSection
0x1800246e9  or      dword ptr [rbx+48h], 300h
0x1800246f0  cmp     qword ptr [rbx+0F8h], 0
0x1800246f8  jz      short loc_180024708
0x1800246fa  mov     edx, 2
0x1800246ff  lea     rcx, [rbx+8]
0x180024703  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180024708  test    rdi, rdi
0x18002470b  jz      short loc_180024716
0x18002470d  mov     rcx, rdi; lpCriticalSection
0x180024710  call    cs:__imp_LeaveCriticalSection
0x180024716  mov     byte ptr [rsp+68h+arg_0], 1
0x18002471b  mov     [rsp+68h+arg_10], 0
0x180024723  mov     [rsp+68h+arg_18], 0
0x18002472b  mov     [rsp+68h+var_38], 0
0x180024730  lea     rax, [rsp+68h+arg_0]
0x180024735  mov     [rsp+68h+var_48], rax
0x18002473a  lea     r9, [rsp+68h+arg_10]
0x180024742  lea     r8, [rsp+68h+arg_18]
0x18002474a  lea     rdx, [rsp+68h+var_38]
0x18002474f  mov     rcx, rsi
0x180024752  call    ??$make@UUnifiedConsentState@implementation@ConsentUx@Shell@Internal@Windows@winrt@@_N_N_N_N@winrt@@YA?A_P$$QEA_N000@Z
0x180024757  nop
0x180024758  mov     rbx, [r14]
0x18002475b  test    rbx, rbx
0x18002475e  jz      short loc_180024781
0x180024760  or      eax, 0FFFFFFFFh
0x180024763  lock xadd [rbx+118h], eax
0x18002476b  cmp     eax, 1
0x18002476e  jnz     short loc_180024781
0x180024770  mov     rcx, rbx
0x180024773  call    ??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)
0x180024778  mov     rcx, rbx; pv
0x18002477b  call    cs:__imp_CoTaskMemFree
0x180024781  mov     rax, rsi
0x180024784  add     rsp, 48h
0x180024788  pop     r14
0x18002478a  pop     rdi
0x18002478b  pop     rsi
0x18002478c  pop     rbx
0x18002478d  retn
```
