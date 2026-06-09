# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsHtml_::_2_::_lambda_1___

- ea: `0x18000ceb8`
- end: `0x18000d03f`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsHtml_::_2_::_lambda_1___`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c840`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000ceb8`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180019390`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d00c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cfe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfb4`

## pseudocode

```c
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::FormatAsHtml_::_2_::_lambda_1___(
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
  v3[68] = 4;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v11);
  v4 = UpdateDiagnosticsInternal::DiagReporting::FormatAsHtml(**(const wchar_t ***)a2, **(HSTRING ***)(a2 + 8));
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
0x18000ceb8  mov     [rsp-8+arg_0], rbx
0x18000cebd  mov     [rsp-8+arg_10], rsi
0x18000cec2  mov     [rsp-8+arg_18], rdi
0x18000cec7  push    rbp
0x18000cec8  mov     rbp, rsp
0x18000cecb  sub     rsp, 70h
0x18000cecf  mov     rax, cs:__security_cookie
0x18000ced6  xor     rax, rsp
0x18000ced9  mov     [rbp+var_10], rax
0x18000cedd  mov     rdi, rdx
0x18000cee0  xorps   xmm0, xmm0
0x18000cee3  xor     eax, eax
0x18000cee5  movups  [rbp+var_48], xmm0
0x18000cee9  movups  [rbp+var_38], xmm0
0x18000ceed  movups  [rbp+var_28], xmm0
0x18000cef1  mov     [rbp+pv], rax
0x18000cef5  lea     rcx, [rbp+var_48]
0x18000cef9  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000cefe  nop
0x18000ceff  mov     rbx, [rbp+pv]
0x18000cf03  mov     [rbp+var_50], rbx
0x18000cf07  test    rbx, rbx
0x18000cf0a  jz      short loc_18000CF13
0x18000cf0c  lock inc dword ptr [rbx+120h]
0x18000cf13  lea     rcx, [rbx+8]
0x18000cf17  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cf1c  mov     dword ptr [rbx+110h], 4
0x18000cf26  lea     rcx, [rbp+var_50]
0x18000cf2a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cf2f  mov     rdx, [rdi+8]
0x18000cf33  mov     rcx, [rdi]
0x18000cf36  mov     rdx, [rdx]; HSTRING *
0x18000cf39  mov     rcx, [rcx]; wchar_t *
0x18000cf3c  call    ?FormatAsHtml@DiagReporting@UpdateDiagnosticsInternal@@SAJPEB_WPEAPEAUHSTRING__@@@Z; UpdateDiagnosticsInternal::DiagReporting::FormatAsHtml(wchar_t const *,HSTRING__ * *)
0x18000cf41  mov     edi, eax
0x18000cf43  mov     rbx, [rbp+pv]
0x18000cf47  mov     [rbp+var_50], rbx
0x18000cf4b  test    rbx, rbx
0x18000cf4e  jz      short loc_18000CF57
0x18000cf50  lock inc dword ptr [rbx+120h]
0x18000cf57  lea     rcx, [rbx+8]
0x18000cf5b  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cf60  mov     [rbx+118h], edi
0x18000cf66  lea     rcx, [rbp+var_50]
0x18000cf6a  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cf6f  mov     rbx, [rbp+pv]
0x18000cf73  mov     [rbp+var_50], rbx
0x18000cf77  test    rbx, rbx
0x18000cf7a  jz      short loc_18000CF83
0x18000cf7c  lock inc dword ptr [rbx+120h]
0x18000cf83  lea     rcx, [rbx+8]
0x18000cf87  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cf8c  mov     eax, edi
0x18000cf8e  sar     eax, 1Fh
0x18000cf91  and     eax, 1
0x18000cf94  add     eax, 2
0x18000cf97  mov     [rbx+114h], eax
0x18000cf9d  lea     rcx, [rbp+var_50]
0x18000cfa1  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cfa6  mov     rsi, [rbp+pv]
0x18000cfaa  lea     rbx, [rsi+0C8h]
0x18000cfb1  mov     rcx, rbx; lpCriticalSection
0x18000cfb4  call    cs:__imp_EnterCriticalSection
0x18000cfba  or      dword ptr [rsi+48h], 300h
0x18000cfc1  cmp     qword ptr [rsi+0F8h], 0
0x18000cfc9  jz      short loc_18000CFD9
0x18000cfcb  mov     edx, 2
0x18000cfd0  lea     rcx, [rsi+8]
0x18000cfd4  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000cfd9  test    rbx, rbx
0x18000cfdc  jz      short loc_18000CFE8
0x18000cfde  mov     rcx, rbx; lpCriticalSection
0x18000cfe1  call    cs:__imp_LeaveCriticalSection
0x18000cfe7  nop
0x18000cfe8  mov     rbx, [rbp+pv]
0x18000cfec  test    rbx, rbx
0x18000cfef  jz      short loc_18000D012
0x18000cff1  or      eax, 0FFFFFFFFh
0x18000cff4  lock xadd [rbx+120h], eax
0x18000cffc  cmp     eax, 1
0x18000cfff  jnz     short loc_18000D012
0x18000d001  mov     rcx, rbx
0x18000d004  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d009  mov     rcx, rbx; pv
0x18000d00c  call    cs:__imp_CoTaskMemFree
0x18000d012  lea     rcx, [rbp+var_48+8]; this
0x18000d016  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d01b  mov     eax, edi
0x18000d01d  mov     rcx, [rbp+var_10]
0x18000d021  xor     rcx, rsp; StackCookie
0x18000d024  call    __security_check_cookie
0x18000d029  lea     r11, [rsp+70h+var_s0]
0x18000d02e  mov     rbx, [r11+10h]
0x18000d032  mov     rsi, [r11+20h]
0x18000d036  mov     rdi, [r11+28h]
0x18000d03a  mov     rsp, r11
0x18000d03d  pop     rbp
0x18000d03e  retn
```
