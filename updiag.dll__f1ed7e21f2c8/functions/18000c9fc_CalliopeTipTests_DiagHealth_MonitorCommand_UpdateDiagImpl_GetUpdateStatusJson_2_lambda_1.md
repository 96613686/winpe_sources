# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetUpdateStatusJson_::_2_::_lambda_1___

- ea: `0x18000c9fc`
- end: `0x18000cb91`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetUpdateStatusJson_::_2_::_lambda_1___`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c790`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000c9fc`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180039e64`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cb30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cb03`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::GetUpdateStatusJson_::_2_::_lambda_1___(
        __int64 a1,
        HSTRING ***a2)
{
  _DWORD *v3; // rbx
  int v4; // edi
  _DWORD *v5; // rbx
  _DWORD *v6; // rbx
  _DWORD *v7; // rsi
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
    _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v3 + 2));
  v3[68] = 1;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v4 = UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(0, 0, 0, 0, v11, **a2);
  v5 = pv;
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
  v5[70] = v4;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v6 = pv;
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
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
0x18000c9fc  mov     [rsp-8+arg_0], rbx
0x18000ca01  mov     [rsp-8+arg_10], rsi
0x18000ca06  mov     [rsp-8+arg_18], rdi
0x18000ca0b  push    rbp
0x18000ca0c  mov     rbp, rsp
0x18000ca0f  sub     rsp, 80h
0x18000ca16  mov     rax, cs:__security_cookie
0x18000ca1d  xor     rax, rsp
0x18000ca20  mov     [rbp+var_10], rax
0x18000ca24  mov     rdi, rdx
0x18000ca27  xorps   xmm0, xmm0
0x18000ca2a  xor     eax, eax
0x18000ca2c  movups  [rbp+var_48], xmm0
0x18000ca30  movups  [rbp+var_38], xmm0
0x18000ca34  movups  [rbp+var_28], xmm0
0x18000ca38  mov     [rbp+pv], rax
0x18000ca3c  lea     rcx, [rbp+var_48]
0x18000ca40  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000ca45  nop
0x18000ca46  mov     rbx, [rbp+pv]
0x18000ca4a  mov     [rbp+var_50], rbx
0x18000ca4e  mov     esi, 1
0x18000ca53  test    rbx, rbx
0x18000ca56  jz      short loc_18000CA5F
0x18000ca58  lock add [rbx+120h], esi
0x18000ca5f  lea     rcx, [rbx+8]
0x18000ca63  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000ca68  mov     [rbx+110h], esi
0x18000ca6e  lea     rcx, [rbp+var_50]
0x18000ca72  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000ca77  mov     rax, [rdi]
0x18000ca7a  mov     rcx, [rax]
0x18000ca7d  mov     [rsp+80h+var_58], rcx; HSTRING *
0x18000ca82  xor     r9d, r9d; HSTRING
0x18000ca85  xor     r8d, r8d; HSTRING
0x18000ca88  xor     edx, edx; unsigned int
0x18000ca8a  xor     ecx, ecx; HSTRING *
0x18000ca8c  call    ?RunAnalyzers@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAUHSTRING__@@IPEAU3@110@Z; UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(HSTRING__ * *,uint,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18000ca91  mov     edi, eax
0x18000ca93  mov     rbx, [rbp+pv]
0x18000ca97  mov     [rbp+var_50], rbx
0x18000ca9b  test    rbx, rbx
0x18000ca9e  jz      short loc_18000CAA7
0x18000caa0  lock add [rbx+120h], esi
0x18000caa7  lea     rcx, [rbx+8]
0x18000caab  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cab0  mov     [rbx+118h], edi
0x18000cab6  lea     rcx, [rbp+var_50]
0x18000caba  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000cabf  mov     rbx, [rbp+pv]
0x18000cac3  mov     [rbp+var_50], rbx
0x18000cac7  test    rbx, rbx
0x18000caca  jz      short loc_18000CAD3
0x18000cacc  lock add [rbx+120h], esi
0x18000cad3  lea     rcx, [rbx+8]
0x18000cad7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000cadc  mov     eax, edi
0x18000cade  sar     eax, 1Fh
0x18000cae1  and     eax, esi
0x18000cae3  add     eax, 2
0x18000cae6  mov     [rbx+114h], eax
0x18000caec  lea     rcx, [rbp+var_50]
0x18000caf0  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000caf5  mov     rsi, [rbp+pv]
0x18000caf9  lea     rbx, [rsi+0C8h]
0x18000cb00  mov     rcx, rbx; lpCriticalSection
0x18000cb03  call    cs:__imp_EnterCriticalSection
0x18000cb09  or      dword ptr [rsi+48h], 300h
0x18000cb10  cmp     qword ptr [rsi+0F8h], 0
0x18000cb18  jz      short loc_18000CB28
0x18000cb1a  mov     edx, 2
0x18000cb1f  lea     rcx, [rsi+8]
0x18000cb23  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000cb28  test    rbx, rbx
0x18000cb2b  jz      short loc_18000CB37
0x18000cb2d  mov     rcx, rbx; lpCriticalSection
0x18000cb30  call    cs:__imp_LeaveCriticalSection
0x18000cb36  nop
0x18000cb37  mov     rbx, [rbp+pv]
0x18000cb3b  test    rbx, rbx
0x18000cb3e  jz      short loc_18000CB61
0x18000cb40  or      eax, 0FFFFFFFFh
0x18000cb43  lock xadd [rbx+120h], eax
0x18000cb4b  cmp     eax, 1
0x18000cb4e  jnz     short loc_18000CB61
0x18000cb50  mov     rcx, rbx
0x18000cb53  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000cb58  mov     rcx, rbx; pv
0x18000cb5b  call    cs:__imp_CoTaskMemFree
0x18000cb61  lea     rcx, [rbp+var_48+8]; this
0x18000cb65  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000cb6a  mov     eax, edi
0x18000cb6c  mov     rcx, [rbp+var_10]
0x18000cb70  xor     rcx, rsp; StackCookie
0x18000cb73  call    __security_check_cookie
0x18000cb78  lea     r11, [rsp+80h+var_s0]
0x18000cb80  mov     rbx, [r11+10h]
0x18000cb84  mov     rsi, [r11+20h]
0x18000cb88  mov     rdi, [r11+28h]
0x18000cb8c  mov     rsp, r11
0x18000cb8f  pop     rbp
0x18000cb90  retn
```
