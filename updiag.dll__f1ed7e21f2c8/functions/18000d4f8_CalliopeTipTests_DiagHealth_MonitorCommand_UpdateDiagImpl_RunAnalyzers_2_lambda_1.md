# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzers_::_2_::_lambda_1___

- ea: `0x18000d4f8`
- end: `0x18000d69a`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzers_::_2_::_lambda_1___`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c940`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000d4f8`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180039e64`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d664`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d639`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d60c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d60c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzers_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int v4; // esi
  _DWORD *v5; // rbx
  _DWORD *v6; // rbx
  _DWORD *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  HSTRING v11; // [rsp+20h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+30h] [rbp-50h] BYREF
  _OWORD v13[3]; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-18h]

  memset(v13, 0, sizeof(v13));
  pv = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>>((__int64)v13);
  v3 = pv;
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v3 + 2));
  v3[68] = 8;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v4 = UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(
         **(HSTRING ***)a2,
         **(_DWORD **)(a2 + 8),
         0,
         **(HSTRING **)(a2 + 16),
         v11,
         **(HSTRING ***)(a2 + 32));
  v5 = pv;
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = v4;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v6 = pv;
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v6 + 2));
  v6[69] = ((v4 >> 31) & 1) + 2;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v7 = pv;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v7[18] |= 0x300u;
  if ( *((_QWORD *)v7 + 31) )
    tip2::details::shared_data<1,0,0>::complete_helper((__int64)(v7 + 2), 2);
  if ( v8 )
    LeaveCriticalSection(v8);
  v9 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v9);
    CoTaskMemFree(v9);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)((char *)v13 + 8));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d4f8  mov     [rsp-8+arg_0], rbx
0x18000d4fd  mov     [rsp-8+arg_10], rsi
0x18000d502  mov     [rsp-8+arg_18], rdi
0x18000d507  push    rbp
0x18000d508  mov     rbp, rsp
0x18000d50b  sub     rsp, 80h
0x18000d512  mov     rax, cs:__security_cookie
0x18000d519  xor     rax, rsp
0x18000d51c  mov     [rbp+var_10], rax
0x18000d520  mov     rdi, rdx
0x18000d523  xorps   xmm0, xmm0
0x18000d526  xor     eax, eax
0x18000d528  movups  [rbp+var_48], xmm0
0x18000d52c  movups  [rbp+var_38], xmm0
0x18000d530  movups  [rbp+var_28], xmm0
0x18000d534  mov     [rbp+pv], rax
0x18000d538  lea     rcx, [rbp+var_48]
0x18000d53c  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000d541  nop
0x18000d542  mov     rbx, [rbp+pv]
0x18000d546  mov     [rbp+var_50], rbx
0x18000d54a  test    rbx, rbx
0x18000d54d  jz      short loc_18000D556
0x18000d54f  lock inc dword ptr [rbx+120h]
0x18000d556  lea     rcx, [rbx+8]
0x18000d55a  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d55f  mov     dword ptr [rbx+110h], 8
0x18000d569  lea     rcx, [rbp+var_50]
0x18000d56d  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d572  mov     rax, [rdi+20h]
0x18000d576  mov     r9, [rdi+10h]
0x18000d57a  mov     rdx, [rdi+8]
0x18000d57e  mov     rcx, [rdi]
0x18000d581  mov     rax, [rax]
0x18000d584  mov     [rsp+80h+var_58], rax; HSTRING *
0x18000d589  mov     r9, [r9]; HSTRING
0x18000d58c  xor     r8d, r8d; HSTRING
0x18000d58f  mov     edx, [rdx]; unsigned int
0x18000d591  mov     rcx, [rcx]; HSTRING *
0x18000d594  call    ?RunAnalyzers@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAUHSTRING__@@IPEAU3@110@Z; UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(HSTRING__ * *,uint,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18000d599  mov     esi, eax
0x18000d59b  mov     rbx, [rbp+pv]
0x18000d59f  mov     [rbp+var_50], rbx
0x18000d5a3  test    rbx, rbx
0x18000d5a6  jz      short loc_18000D5AF
0x18000d5a8  lock inc dword ptr [rbx+120h]
0x18000d5af  lea     rcx, [rbx+8]
0x18000d5b3  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d5b8  mov     [rbx+118h], esi
0x18000d5be  lea     rcx, [rbp+var_50]
0x18000d5c2  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d5c7  mov     rbx, [rbp+pv]
0x18000d5cb  mov     [rbp+var_50], rbx
0x18000d5cf  test    rbx, rbx
0x18000d5d2  jz      short loc_18000D5DB
0x18000d5d4  lock inc dword ptr [rbx+120h]
0x18000d5db  lea     rcx, [rbx+8]
0x18000d5df  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d5e4  mov     eax, esi
0x18000d5e6  sar     eax, 1Fh
0x18000d5e9  and     eax, 1
0x18000d5ec  add     eax, 2
0x18000d5ef  mov     [rbx+114h], eax
0x18000d5f5  lea     rcx, [rbp+var_50]
0x18000d5f9  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d5fe  mov     rdi, [rbp+pv]
0x18000d602  lea     rbx, [rdi+0C8h]
0x18000d609  mov     rcx, rbx; lpCriticalSection
0x18000d60c  call    cs:__imp_EnterCriticalSection
0x18000d612  or      dword ptr [rdi+48h], 300h
0x18000d619  cmp     qword ptr [rdi+0F8h], 0
0x18000d621  jz      short loc_18000D631
0x18000d623  mov     edx, 2
0x18000d628  lea     rcx, [rdi+8]
0x18000d62c  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000d631  test    rbx, rbx
0x18000d634  jz      short loc_18000D640
0x18000d636  mov     rcx, rbx; lpCriticalSection
0x18000d639  call    cs:__imp_LeaveCriticalSection
0x18000d63f  nop
0x18000d640  mov     rbx, [rbp+pv]
0x18000d644  test    rbx, rbx
0x18000d647  jz      short loc_18000D66A
0x18000d649  or      eax, 0FFFFFFFFh
0x18000d64c  lock xadd [rbx+120h], eax
0x18000d654  cmp     eax, 1
0x18000d657  jnz     short loc_18000D66A
0x18000d659  mov     rcx, rbx
0x18000d65c  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d661  mov     rcx, rbx; pv
0x18000d664  call    cs:__imp_CoTaskMemFree
0x18000d66a  lea     rcx, [rbp+var_48+8]; this
0x18000d66e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d673  mov     eax, esi
0x18000d675  mov     rcx, [rbp+var_10]
0x18000d679  xor     rcx, rsp; StackCookie
0x18000d67c  call    __security_check_cookie
0x18000d681  lea     r11, [rsp+80h+var_s0]
0x18000d689  mov     rbx, [r11+10h]
0x18000d68d  mov     rsi, [r11+20h]
0x18000d691  mov     rdi, [r11+28h]
0x18000d695  mov     rsp, r11
0x18000d698  pop     rbp
0x18000d699  retn
```
