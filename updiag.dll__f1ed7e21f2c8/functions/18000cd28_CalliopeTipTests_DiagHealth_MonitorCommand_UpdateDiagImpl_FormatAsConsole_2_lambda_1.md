# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsConsole_::_2_::_lambda_1___

- ea: `0x18000cd28`
- end: `0x18000ceaf`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsConsole_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c800`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000cd28`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180019270`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce24`

## pseudocode

```c
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsConsole_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int v4; // edi
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
  v3[68] = 3;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v4 = UpdateDiagnosticsInternal::DiagReporting::FormatAsConsole(**(const wchar_t ***)a2, **(HSTRING ***)(a2 + 8));
  v5 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = v4;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v6 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v6 + 2));
  v6[69] = ((v4 >> 31) & 1) + 2;
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
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000cd28  mov     [rsp-8+arg_0], rbx
0x18000cd2d  mov     [rsp-8+arg_10], rsi
0x18000cd32  mov     [rsp-8+arg_18], rdi
0x18000cd37  push    rbp
0x18000cd38  mov     rbp, rsp
0x18000cd3b  sub     rsp, 70h
0x18000cd3f  mov     rax, cs:__security_cookie
0x18000cd46  xor     rax, rsp
0x18000cd49  mov     [rbp+var_10], rax
0x18000cd4d  mov     rdi, rdx
0x18000cd50  xorps   xmm0, xmm0
0x18000cd53  xor     eax, eax
0x18000cd55  movups  [rbp+var_48], xmm0
0x18000cd59  movups  [rbp+var_38], xmm0
0x18000cd5d  movups  [rbp+var_28], xmm0
0x18000cd61  mov     [rbp+pv], rax
0x18000cd65  lea     rcx, [rbp+var_48]
0x18000cd69  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000cd6e  nop
0x18000cd6f  mov     rbx, [rbp+pv]
0x18000cd73  mov     [rbp+var_50], rbx
0x18000cd77  test    rbx, rbx
0x18000cd7a  jz      short loc_18000CD83
0x18000cd7c  lock inc dword ptr [rbx+120h]
0x18000cd83  lea     rcx, [rbx+8]
0x18000cd87  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cd8c  mov     dword ptr [rbx+110h], 3
0x18000cd96  lea     rcx, [rbp+var_50]
0x18000cd9a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cd9f  mov     rdx, [rdi+8]
0x18000cda3  mov     rcx, [rdi]
0x18000cda6  mov     rdx, [rdx]; HSTRING *
0x18000cda9  mov     rcx, [rcx]; wchar_t *
0x18000cdac  call    ?FormatAsConsole@DiagReporting@UpdateDiagnosticsInternal@@SAJPEB_WPEAPEAUHSTRING__@@@Z; UpdateDiagnosticsInternal::DiagReporting::FormatAsConsole(wchar_t const *,HSTRING__ * *)
0x18000cdb1  mov     edi, eax
0x18000cdb3  mov     rbx, [rbp+pv]
0x18000cdb7  mov     [rbp+var_50], rbx
0x18000cdbb  test    rbx, rbx
0x18000cdbe  jz      short loc_18000CDC7
0x18000cdc0  lock inc dword ptr [rbx+120h]
0x18000cdc7  lea     rcx, [rbx+8]
0x18000cdcb  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cdd0  mov     [rbx+118h], edi
0x18000cdd6  lea     rcx, [rbp+var_50]
0x18000cdda  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cddf  mov     rbx, [rbp+pv]
0x18000cde3  mov     [rbp+var_50], rbx
0x18000cde7  test    rbx, rbx
0x18000cdea  jz      short loc_18000CDF3
0x18000cdec  lock inc dword ptr [rbx+120h]
0x18000cdf3  lea     rcx, [rbx+8]
0x18000cdf7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cdfc  mov     eax, edi
0x18000cdfe  sar     eax, 1Fh
0x18000ce01  and     eax, 1
0x18000ce04  add     eax, 2
0x18000ce07  mov     [rbx+114h], eax
0x18000ce0d  lea     rcx, [rbp+var_50]
0x18000ce11  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000ce16  mov     rsi, [rbp+pv]
0x18000ce1a  lea     rbx, [rsi+0C8h]
0x18000ce21  mov     rcx, rbx; lpCriticalSection
0x18000ce24  call    cs:__imp_EnterCriticalSection
0x18000ce2a  or      dword ptr [rsi+48h], 300h
0x18000ce31  cmp     qword ptr [rsi+0F8h], 0
0x18000ce39  jz      short loc_18000CE49
0x18000ce3b  mov     edx, 2
0x18000ce40  lea     rcx, [rsi+8]
0x18000ce44  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000ce49  test    rbx, rbx
0x18000ce4c  jz      short loc_18000CE58
0x18000ce4e  mov     rcx, rbx; lpCriticalSection
0x18000ce51  call    cs:__imp_LeaveCriticalSection
0x18000ce57  nop
0x18000ce58  mov     rbx, [rbp+pv]
0x18000ce5c  test    rbx, rbx
0x18000ce5f  jz      short loc_18000CE82
0x18000ce61  or      eax, 0FFFFFFFFh
0x18000ce64  lock xadd [rbx+120h], eax
0x18000ce6c  cmp     eax, 1
0x18000ce6f  jnz     short loc_18000CE82
0x18000ce71  mov     rcx, rbx
0x18000ce74  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000ce79  mov     rcx, rbx; pv
0x18000ce7c  call    cs:__imp_CoTaskMemFree
0x18000ce82  lea     rcx, [rbp+var_48+8]; this
0x18000ce86  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000ce8b  mov     eax, edi
0x18000ce8d  mov     rcx, [rbp+var_10]
0x18000ce91  xor     rcx, rsp; StackCookie
0x18000ce94  call    __security_check_cookie
0x18000ce99  lea     r11, [rsp+70h+var_s0]
0x18000ce9e  mov     rbx, [r11+10h]
0x18000cea2  mov     rsi, [r11+20h]
0x18000cea6  mov     rdi, [r11+28h]
0x18000ceaa  mov     rsp, r11
0x18000cead  pop     rbp
0x18000ceae  retn
```
