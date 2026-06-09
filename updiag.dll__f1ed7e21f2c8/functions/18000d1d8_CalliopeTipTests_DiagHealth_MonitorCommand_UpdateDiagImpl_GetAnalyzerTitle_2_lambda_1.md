# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerTitle_::_2_::_lambda_1___

- ea: `0x18000d1d8`
- end: `0x18000d35f`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerTitle_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c8c0`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000d1d8`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x18003a8a8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d32c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d32c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d301`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d301`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d2d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d2d4`

## pseudocode

```c
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerTitle_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int AnalyzerTitle; // edi
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
  v3[68] = 6;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  AnalyzerTitle = UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerTitle(**(HSTRING **)a2, **(HSTRING ***)(a2 + 8));
  v5 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = AnalyzerTitle;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v6 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v6 + 2));
  v6[69] = ((AnalyzerTitle >> 31) & 1) + 2;
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
  return (unsigned int)AnalyzerTitle;
}

```

## disassembly

```asm
0x18000d1d8  mov     [rsp-8+arg_0], rbx
0x18000d1dd  mov     [rsp-8+arg_10], rsi
0x18000d1e2  mov     [rsp-8+arg_18], rdi
0x18000d1e7  push    rbp
0x18000d1e8  mov     rbp, rsp
0x18000d1eb  sub     rsp, 70h
0x18000d1ef  mov     rax, cs:__security_cookie
0x18000d1f6  xor     rax, rsp
0x18000d1f9  mov     [rbp+var_10], rax
0x18000d1fd  mov     rdi, rdx
0x18000d200  xorps   xmm0, xmm0
0x18000d203  xor     eax, eax
0x18000d205  movups  [rbp+var_48], xmm0
0x18000d209  movups  [rbp+var_38], xmm0
0x18000d20d  movups  [rbp+var_28], xmm0
0x18000d211  mov     [rbp+pv], rax
0x18000d215  lea     rcx, [rbp+var_48]
0x18000d219  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000d21e  nop
0x18000d21f  mov     rbx, [rbp+pv]
0x18000d223  mov     [rbp+var_50], rbx
0x18000d227  test    rbx, rbx
0x18000d22a  jz      short loc_18000D233
0x18000d22c  lock inc dword ptr [rbx+120h]
0x18000d233  lea     rcx, [rbx+8]
0x18000d237  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d23c  mov     dword ptr [rbx+110h], 6
0x18000d246  lea     rcx, [rbp+var_50]
0x18000d24a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d24f  mov     rdx, [rdi+8]
0x18000d253  mov     rcx, [rdi]
0x18000d256  mov     rdx, [rdx]; HSTRING *
0x18000d259  mov     rcx, [rcx]; HSTRING
0x18000d25c  call    ?GetAnalyzerTitle@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAUHSTRING__@@PEAPEAU3@@Z; UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerTitle(HSTRING__ *,HSTRING__ * *)
0x18000d261  mov     edi, eax
0x18000d263  mov     rbx, [rbp+pv]
0x18000d267  mov     [rbp+var_50], rbx
0x18000d26b  test    rbx, rbx
0x18000d26e  jz      short loc_18000D277
0x18000d270  lock inc dword ptr [rbx+120h]
0x18000d277  lea     rcx, [rbx+8]
0x18000d27b  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d280  mov     [rbx+118h], edi
0x18000d286  lea     rcx, [rbp+var_50]
0x18000d28a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d28f  mov     rbx, [rbp+pv]
0x18000d293  mov     [rbp+var_50], rbx
0x18000d297  test    rbx, rbx
0x18000d29a  jz      short loc_18000D2A3
0x18000d29c  lock inc dword ptr [rbx+120h]
0x18000d2a3  lea     rcx, [rbx+8]
0x18000d2a7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d2ac  mov     eax, edi
0x18000d2ae  sar     eax, 1Fh
0x18000d2b1  and     eax, 1
0x18000d2b4  add     eax, 2
0x18000d2b7  mov     [rbx+114h], eax
0x18000d2bd  lea     rcx, [rbp+var_50]
0x18000d2c1  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d2c6  mov     rsi, [rbp+pv]
0x18000d2ca  lea     rbx, [rsi+0C8h]
0x18000d2d1  mov     rcx, rbx; lpCriticalSection
0x18000d2d4  call    cs:__imp_EnterCriticalSection
0x18000d2da  or      dword ptr [rsi+48h], 300h
0x18000d2e1  cmp     qword ptr [rsi+0F8h], 0
0x18000d2e9  jz      short loc_18000D2F9
0x18000d2eb  mov     edx, 2
0x18000d2f0  lea     rcx, [rsi+8]
0x18000d2f4  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000d2f9  test    rbx, rbx
0x18000d2fc  jz      short loc_18000D308
0x18000d2fe  mov     rcx, rbx; lpCriticalSection
0x18000d301  call    cs:__imp_LeaveCriticalSection
0x18000d307  nop
0x18000d308  mov     rbx, [rbp+pv]
0x18000d30c  test    rbx, rbx
0x18000d30f  jz      short loc_18000D332
0x18000d311  or      eax, 0FFFFFFFFh
0x18000d314  lock xadd [rbx+120h], eax
0x18000d31c  cmp     eax, 1
0x18000d31f  jnz     short loc_18000D332
0x18000d321  mov     rcx, rbx
0x18000d324  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d329  mov     rcx, rbx; pv
0x18000d32c  call    cs:__imp_CoTaskMemFree
0x18000d332  lea     rcx, [rbp+var_48+8]; this
0x18000d336  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d33b  mov     eax, edi
0x18000d33d  mov     rcx, [rbp+var_10]
0x18000d341  xor     rcx, rsp; StackCookie
0x18000d344  call    __security_check_cookie
0x18000d349  lea     r11, [rsp+70h+var_s0]
0x18000d34e  mov     rbx, [r11+10h]
0x18000d352  mov     rsi, [r11+20h]
0x18000d356  mov     rdi, [r11+28h]
0x18000d35a  mov     rsp, r11
0x18000d35d  pop     rbp
0x18000d35e  retn
```
