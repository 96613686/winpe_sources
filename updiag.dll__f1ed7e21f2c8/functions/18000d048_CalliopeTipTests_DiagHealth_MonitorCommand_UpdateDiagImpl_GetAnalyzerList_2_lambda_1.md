# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerList_::_2_::_lambda_1___

- ea: `0x18000d048`
- end: `0x18000d1cf`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerList_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c880`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000d048`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x18003a5d8`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d19c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d19c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d171`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d144`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d144`

## pseudocode

```c
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetAnalyzerList_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int AnalyzerList; // edi
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
  v3[68] = 5;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  AnalyzerList = UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerList(
                   **(HSTRING ****)a2,
                   **(unsigned int ***)(a2 + 8));
  v5 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = AnalyzerList;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v6 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v6 + 2));
  v6[69] = ((AnalyzerList >> 31) & 1) + 2;
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
  return (unsigned int)AnalyzerList;
}

```

## disassembly

```asm
0x18000d048  mov     [rsp-8+arg_0], rbx
0x18000d04d  mov     [rsp-8+arg_10], rsi
0x18000d052  mov     [rsp-8+arg_18], rdi
0x18000d057  push    rbp
0x18000d058  mov     rbp, rsp
0x18000d05b  sub     rsp, 70h
0x18000d05f  mov     rax, cs:__security_cookie
0x18000d066  xor     rax, rsp
0x18000d069  mov     [rbp+var_10], rax
0x18000d06d  mov     rdi, rdx
0x18000d070  xorps   xmm0, xmm0
0x18000d073  xor     eax, eax
0x18000d075  movups  [rbp+var_48], xmm0
0x18000d079  movups  [rbp+var_38], xmm0
0x18000d07d  movups  [rbp+var_28], xmm0
0x18000d081  mov     [rbp+pv], rax
0x18000d085  lea     rcx, [rbp+var_48]
0x18000d089  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000d08e  nop
0x18000d08f  mov     rbx, [rbp+pv]
0x18000d093  mov     [rbp+var_50], rbx
0x18000d097  test    rbx, rbx
0x18000d09a  jz      short loc_18000D0A3
0x18000d09c  lock inc dword ptr [rbx+120h]
0x18000d0a3  lea     rcx, [rbx+8]
0x18000d0a7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d0ac  mov     dword ptr [rbx+110h], 5
0x18000d0b6  lea     rcx, [rbp+var_50]
0x18000d0ba  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d0bf  mov     rdx, [rdi+8]
0x18000d0c3  mov     rcx, [rdi]
0x18000d0c6  mov     rdx, [rdx]; unsigned int *
0x18000d0c9  mov     rcx, [rcx]; HSTRING **
0x18000d0cc  call    ?GetAnalyzerList@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAPEAUHSTRING__@@PEAI@Z; UpdateDiagnosticsInternal::DiagDeepDive::GetAnalyzerList(HSTRING__ * * *,uint *)
0x18000d0d1  mov     edi, eax
0x18000d0d3  mov     rbx, [rbp+pv]
0x18000d0d7  mov     [rbp+var_50], rbx
0x18000d0db  test    rbx, rbx
0x18000d0de  jz      short loc_18000D0E7
0x18000d0e0  lock inc dword ptr [rbx+120h]
0x18000d0e7  lea     rcx, [rbx+8]
0x18000d0eb  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d0f0  mov     [rbx+118h], edi
0x18000d0f6  lea     rcx, [rbp+var_50]
0x18000d0fa  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d0ff  mov     rbx, [rbp+pv]
0x18000d103  mov     [rbp+var_50], rbx
0x18000d107  test    rbx, rbx
0x18000d10a  jz      short loc_18000D113
0x18000d10c  lock inc dword ptr [rbx+120h]
0x18000d113  lea     rcx, [rbx+8]
0x18000d117  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d11c  mov     eax, edi
0x18000d11e  sar     eax, 1Fh
0x18000d121  and     eax, 1
0x18000d124  add     eax, 2
0x18000d127  mov     [rbx+114h], eax
0x18000d12d  lea     rcx, [rbp+var_50]
0x18000d131  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d136  mov     rsi, [rbp+pv]
0x18000d13a  lea     rbx, [rsi+0C8h]
0x18000d141  mov     rcx, rbx; lpCriticalSection
0x18000d144  call    cs:__imp_EnterCriticalSection
0x18000d14a  or      dword ptr [rsi+48h], 300h
0x18000d151  cmp     qword ptr [rsi+0F8h], 0
0x18000d159  jz      short loc_18000D169
0x18000d15b  mov     edx, 2
0x18000d160  lea     rcx, [rsi+8]
0x18000d164  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000d169  test    rbx, rbx
0x18000d16c  jz      short loc_18000D178
0x18000d16e  mov     rcx, rbx; lpCriticalSection
0x18000d171  call    cs:__imp_LeaveCriticalSection
0x18000d177  nop
0x18000d178  mov     rbx, [rbp+pv]
0x18000d17c  test    rbx, rbx
0x18000d17f  jz      short loc_18000D1A2
0x18000d181  or      eax, 0FFFFFFFFh
0x18000d184  lock xadd [rbx+120h], eax
0x18000d18c  cmp     eax, 1
0x18000d18f  jnz     short loc_18000D1A2
0x18000d191  mov     rcx, rbx
0x18000d194  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d199  mov     rcx, rbx; pv
0x18000d19c  call    cs:__imp_CoTaskMemFree
0x18000d1a2  lea     rcx, [rbp+var_48+8]; this
0x18000d1a6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d1ab  mov     eax, edi
0x18000d1ad  mov     rcx, [rbp+var_10]
0x18000d1b1  xor     rcx, rsp; StackCookie
0x18000d1b4  call    __security_check_cookie
0x18000d1b9  lea     r11, [rsp+70h+var_s0]
0x18000d1be  mov     rbx, [r11+10h]
0x18000d1c2  mov     rsi, [r11+20h]
0x18000d1c6  mov     rdi, [r11+28h]
0x18000d1ca  mov     rsp, r11
0x18000d1cd  pop     rbp
0x18000d1ce  retn
```
