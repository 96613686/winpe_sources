# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerDescription_::_2_::_lambda_1___

- ea: `0x18000d368`
- end: `0x18000d4ef`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerDescription_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c900`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000d368`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x18003ab5c`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d491`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d491`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d464`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d464`

## pseudocode

```c
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerDescription_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int AnalyzerDescription; // edi
  _DWORD *v5; // rbx
  _DWORD *v6; // rbx
  _DWORD *v7; // rsi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v12[3]; // [rsp+28h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-18h]

  memset(v12, 0, sizeof(v12));
  pv = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>>((__int64)v12);
  v3 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v3 + 2));
  v3[68] = 7;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  AnalyzerDescription = UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerDescription(
                          **(HSTRING **)a2,
                          **(HSTRING ***)(a2 + 8));
  v5 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = AnalyzerDescription;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v6 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v6 + 2));
  v6[69] = ((AnalyzerDescription >> 31) & 1) + 2;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
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
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)((char *)v12 + 8));
  return (unsigned int)AnalyzerDescription;
}

```

## disassembly

```asm
0x18000d368  mov     [rsp-8+arg_0], rbx
0x18000d36d  mov     [rsp-8+arg_10], rsi
0x18000d372  mov     [rsp-8+arg_18], rdi
0x18000d377  push    rbp
0x18000d378  mov     rbp, rsp
0x18000d37b  sub     rsp, 70h
0x18000d37f  mov     rax, cs:__security_cookie
0x18000d386  xor     rax, rsp
0x18000d389  mov     [rbp+var_10], rax
0x18000d38d  mov     rdi, rdx
0x18000d390  xorps   xmm0, xmm0
0x18000d393  xor     eax, eax
0x18000d395  movups  [rbp+var_48], xmm0
0x18000d399  movups  [rbp+var_38], xmm0
0x18000d39d  movups  [rbp+var_28], xmm0
0x18000d3a1  mov     [rbp+pv], rax
0x18000d3a5  lea     rcx, [rbp+var_48]
0x18000d3a9  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000d3ae  nop
0x18000d3af  mov     rbx, [rbp+pv]
0x18000d3b3  mov     [rbp+var_50], rbx
0x18000d3b7  test    rbx, rbx
0x18000d3ba  jz      short loc_18000D3C3
0x18000d3bc  lock inc dword ptr [rbx+120h]
0x18000d3c3  lea     rcx, [rbx+8]
0x18000d3c7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d3cc  mov     dword ptr [rbx+110h], 7
0x18000d3d6  lea     rcx, [rbp+var_50]
0x18000d3da  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d3df  mov     rdx, [rdi+8]
0x18000d3e3  mov     rcx, [rdi]
0x18000d3e6  mov     rdx, [rdx]; HSTRING *
0x18000d3e9  mov     rcx, [rcx]; HSTRING
0x18000d3ec  call    ?GetAnalyzerDescription@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAUHSTRING__@@PEAPEAU3@@Z; UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerDescription(HSTRING__ *,HSTRING__ * *)
0x18000d3f1  mov     edi, eax
0x18000d3f3  mov     rbx, [rbp+pv]
0x18000d3f7  mov     [rbp+var_50], rbx
0x18000d3fb  test    rbx, rbx
0x18000d3fe  jz      short loc_18000D407
0x18000d400  lock inc dword ptr [rbx+120h]
0x18000d407  lea     rcx, [rbx+8]
0x18000d40b  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d410  mov     [rbx+118h], edi
0x18000d416  lea     rcx, [rbp+var_50]
0x18000d41a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d41f  mov     rbx, [rbp+pv]
0x18000d423  mov     [rbp+var_50], rbx
0x18000d427  test    rbx, rbx
0x18000d42a  jz      short loc_18000D433
0x18000d42c  lock inc dword ptr [rbx+120h]
0x18000d433  lea     rcx, [rbx+8]
0x18000d437  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d43c  mov     eax, edi
0x18000d43e  sar     eax, 1Fh
0x18000d441  and     eax, 1
0x18000d444  add     eax, 2
0x18000d447  mov     [rbx+114h], eax
0x18000d44d  lea     rcx, [rbp+var_50]
0x18000d451  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d456  mov     rsi, [rbp+pv]
0x18000d45a  lea     rbx, [rsi+0C8h]
0x18000d461  mov     rcx, rbx; lpCriticalSection
0x18000d464  call    cs:__imp_EnterCriticalSection
0x18000d46a  or      dword ptr [rsi+48h], 300h
0x18000d471  cmp     qword ptr [rsi+0F8h], 0
0x18000d479  jz      short loc_18000D489
0x18000d47b  mov     edx, 2
0x18000d480  lea     rcx, [rsi+8]
0x18000d484  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000d489  test    rbx, rbx
0x18000d48c  jz      short loc_18000D498
0x18000d48e  mov     rcx, rbx; lpCriticalSection
0x18000d491  call    cs:__imp_LeaveCriticalSection
0x18000d497  nop
0x18000d498  mov     rbx, [rbp+pv]
0x18000d49c  test    rbx, rbx
0x18000d49f  jz      short loc_18000D4C2
0x18000d4a1  or      eax, 0FFFFFFFFh
0x18000d4a4  lock xadd [rbx+120h], eax
0x18000d4ac  cmp     eax, 1
0x18000d4af  jnz     short loc_18000D4C2
0x18000d4b1  mov     rcx, rbx
0x18000d4b4  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d4b9  mov     rcx, rbx; pv
0x18000d4bc  call    cs:__imp_CoTaskMemFree
0x18000d4c2  lea     rcx, [rbp+var_48+8]; this
0x18000d4c6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d4cb  mov     eax, edi
0x18000d4cd  mov     rcx, [rbp+var_10]
0x18000d4d1  xor     rcx, rsp; StackCookie
0x18000d4d4  call    __security_check_cookie
0x18000d4d9  lea     r11, [rsp+70h+var_s0]
0x18000d4de  mov     rbx, [r11+10h]
0x18000d4e2  mov     rsi, [r11+20h]
0x18000d4e6  mov     rdi, [r11+28h]
0x18000d4ea  mov     rsp, r11
0x18000d4ed  pop     rbp
0x18000d4ee  retn
```
