# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsTree_::_2_::_lambda_1___

- ea: `0x18000cb98`
- end: `0x18000cd1f`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsTree_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c7c0`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000cb98`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180019150`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ccec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc94`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsTree_::_2_::_lambda_1___(
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
  v3[68] = 2;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v4 = UpdateDiagnosticsInternal::DiagReporting::FormatAsTree(**(const wchar_t ***)a2, **(HSTRING ***)(a2 + 8));
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
0x18000cb98  mov     [rsp-8+arg_0], rbx
0x18000cb9d  mov     [rsp-8+arg_10], rsi
0x18000cba2  mov     [rsp-8+arg_18], rdi
0x18000cba7  push    rbp
0x18000cba8  mov     rbp, rsp
0x18000cbab  sub     rsp, 70h
0x18000cbaf  mov     rax, cs:__security_cookie
0x18000cbb6  xor     rax, rsp
0x18000cbb9  mov     [rbp+var_10], rax
0x18000cbbd  mov     rdi, rdx
0x18000cbc0  xorps   xmm0, xmm0
0x18000cbc3  xor     eax, eax
0x18000cbc5  movups  [rbp+var_48], xmm0
0x18000cbc9  movups  [rbp+var_38], xmm0
0x18000cbcd  movups  [rbp+var_28], xmm0
0x18000cbd1  mov     [rbp+pv], rax
0x18000cbd5  lea     rcx, [rbp+var_48]
0x18000cbd9  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000cbde  nop
0x18000cbdf  mov     rbx, [rbp+pv]
0x18000cbe3  mov     [rbp+var_50], rbx
0x18000cbe7  test    rbx, rbx
0x18000cbea  jz      short loc_18000CBF3
0x18000cbec  lock inc dword ptr [rbx+120h]
0x18000cbf3  lea     rcx, [rbx+8]
0x18000cbf7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cbfc  mov     dword ptr [rbx+110h], 2
0x18000cc06  lea     rcx, [rbp+var_50]
0x18000cc0a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cc0f  mov     rdx, [rdi+8]
0x18000cc13  mov     rcx, [rdi]
0x18000cc16  mov     rdx, [rdx]; HSTRING *
0x18000cc19  mov     rcx, [rcx]; wchar_t *
0x18000cc1c  call    ?FormatAsTree@DiagReporting@UpdateDiagnosticsInternal@@SAJPEB_WPEAPEAUHSTRING__@@@Z; UpdateDiagnosticsInternal::DiagReporting::FormatAsTree(wchar_t const *,HSTRING__ * *)
0x18000cc21  mov     esi, eax
0x18000cc23  mov     rbx, [rbp+pv]
0x18000cc27  mov     [rbp+var_50], rbx
0x18000cc2b  test    rbx, rbx
0x18000cc2e  jz      short loc_18000CC37
0x18000cc30  lock inc dword ptr [rbx+120h]
0x18000cc37  lea     rcx, [rbx+8]
0x18000cc3b  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cc40  mov     [rbx+118h], esi
0x18000cc46  lea     rcx, [rbp+var_50]
0x18000cc4a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cc4f  mov     rbx, [rbp+pv]
0x18000cc53  mov     [rbp+var_50], rbx
0x18000cc57  test    rbx, rbx
0x18000cc5a  jz      short loc_18000CC63
0x18000cc5c  lock inc dword ptr [rbx+120h]
0x18000cc63  lea     rcx, [rbx+8]
0x18000cc67  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cc6c  mov     eax, esi
0x18000cc6e  sar     eax, 1Fh
0x18000cc71  and     eax, 1
0x18000cc74  add     eax, 2
0x18000cc77  mov     [rbx+114h], eax
0x18000cc7d  lea     rcx, [rbp+var_50]
0x18000cc81  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cc86  mov     rdi, [rbp+pv]
0x18000cc8a  lea     rbx, [rdi+0C8h]
0x18000cc91  mov     rcx, rbx; lpCriticalSection
0x18000cc94  call    cs:__imp_EnterCriticalSection
0x18000cc9a  or      dword ptr [rdi+48h], 300h
0x18000cca1  cmp     qword ptr [rdi+0F8h], 0
0x18000cca9  jz      short loc_18000CCB9
0x18000ccab  mov     edx, 2
0x18000ccb0  lea     rcx, [rdi+8]
0x18000ccb4  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000ccb9  test    rbx, rbx
0x18000ccbc  jz      short loc_18000CCC8
0x18000ccbe  mov     rcx, rbx; lpCriticalSection
0x18000ccc1  call    cs:__imp_LeaveCriticalSection
0x18000ccc7  nop
0x18000ccc8  mov     rbx, [rbp+pv]
0x18000cccc  test    rbx, rbx
0x18000cccf  jz      short loc_18000CCF2
0x18000ccd1  or      eax, 0FFFFFFFFh
0x18000ccd4  lock xadd [rbx+120h], eax
0x18000ccdc  cmp     eax, 1
0x18000ccdf  jnz     short loc_18000CCF2
0x18000cce1  mov     rcx, rbx
0x18000cce4  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000cce9  mov     rcx, rbx; pv
0x18000ccec  call    cs:__imp_CoTaskMemFree
0x18000ccf2  lea     rcx, [rbp+var_48+8]; this
0x18000ccf6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000ccfb  mov     eax, esi
0x18000ccfd  mov     rcx, [rbp+var_10]
0x18000cd01  xor     rcx, rsp; StackCookie
0x18000cd04  call    __security_check_cookie
0x18000cd09  lea     r11, [rsp+70h+var_s0]
0x18000cd0e  mov     rbx, [r11+10h]
0x18000cd12  mov     rsi, [r11+20h]
0x18000cd16  mov     rdi, [r11+28h]
0x18000cd1a  mov     rsp, r11
0x18000cd1d  pop     rbp
0x18000cd1e  retn
```
