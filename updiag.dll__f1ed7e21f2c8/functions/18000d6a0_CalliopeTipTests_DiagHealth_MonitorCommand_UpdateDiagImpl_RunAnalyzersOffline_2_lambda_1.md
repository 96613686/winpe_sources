# CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzersOffline_::_2_::_lambda_1___

- ea: `0x18000d6a0`
- end: `0x18000d846`
- name: `CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzersOffline_::_2_::_lambda_1___`
- size: `422`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c9a0`

## callees

- `0x180005950`
- `0x180005d48`
- `0x18000c4a0`
- `0x18000d6a0`
- `0x18000d900`
- `0x18000ddc4`
- `0x18000e12c`
- `0x180039e64`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d7e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d7e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d7b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CalliopeTipTests::DiagHealth::MonitorCommand__UpdateDiagImpl::RunAnalyzersOffline_::_2_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v3; // rbx
  int v4; // esi
  _DWORD *v5; // rbx
  _DWORD *v6; // rbx
  _DWORD *v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  void *v9; // rbx
  HSTRING v11; // [rsp+20h] [rbp-60h]
  LPVOID v12; // [rsp+30h] [rbp-50h] BYREF
  _OWORD v13[3]; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-18h]

  memset(v13, 0, sizeof(v13));
  pv = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>>(v13);
  v3 = pv;
  v12 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update(v3 + 2);
  v3[68] = 9;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v4 = UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(
         **(HSTRING ***)a2,
         **(_DWORD **)(a2 + 8),
         **(HSTRING **)(a2 + 16),
         **(HSTRING **)(a2 + 24),
         v11,
         **(HSTRING ***)(a2 + 40));
  v5 = pv;
  v12 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update(v5 + 2);
  v5[70] = v4;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v6 = pv;
  v12 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  tip2::details::shared_data<1,0,0>::begin_update(v6 + 2);
  v6[69] = ((v4 >> 31) & 1) + 2;
  tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(&v12);
  v7 = pv;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v7[18] |= 0x300u;
  if ( *((_QWORD *)v7 + 31) )
    tip2::details::shared_data<1,0,0>::complete_helper(v7 + 2, 2);
  if ( v8 )
    LeaveCriticalSection(v8);
  v9 = pv;
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
0x18000d6a0  mov     [rsp-8+arg_0], rbx
0x18000d6a5  mov     [rsp-8+arg_10], rsi
0x18000d6aa  mov     [rsp-8+arg_18], rdi
0x18000d6af  push    rbp
0x18000d6b0  mov     rbp, rsp
0x18000d6b3  sub     rsp, 80h
0x18000d6ba  mov     rax, cs:__security_cookie
0x18000d6c1  xor     rax, rsp
0x18000d6c4  mov     [rbp+var_10], rax
0x18000d6c8  mov     rdi, rdx
0x18000d6cb  xorps   xmm0, xmm0
0x18000d6ce  xor     eax, eax
0x18000d6d0  movups  [rbp+var_48], xmm0
0x18000d6d4  movups  [rbp+var_38], xmm0
0x18000d6d8  movups  [rbp+var_28], xmm0
0x18000d6dc  mov     [rbp+pv], rax
0x18000d6e0  lea     rcx, [rbp+var_48]
0x18000d6e4  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18000d6e9  nop
0x18000d6ea  mov     rbx, [rbp+pv]
0x18000d6ee  mov     [rbp+var_50], rbx
0x18000d6f2  test    rbx, rbx
0x18000d6f5  jz      short loc_18000D6FE
0x18000d6f7  lock inc dword ptr [rbx+120h]
0x18000d6fe  lea     rcx, [rbx+8]
0x18000d702  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d707  mov     dword ptr [rbx+110h], 9
0x18000d711  lea     rcx, [rbp+var_50]
0x18000d715  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d71a  mov     rax, [rdi+28h]
0x18000d71e  mov     r9, [rdi+18h]
0x18000d722  mov     r8, [rdi+10h]
0x18000d726  mov     rdx, [rdi+8]
0x18000d72a  mov     rcx, [rdi]
0x18000d72d  mov     rax, [rax]
0x18000d730  mov     [rsp+80h+var_58], rax; HSTRING *
0x18000d735  mov     r9, [r9]; HSTRING
0x18000d738  mov     r8, [r8]; HSTRING
0x18000d73b  mov     edx, [rdx]; unsigned int
0x18000d73d  mov     rcx, [rcx]; HSTRING *
0x18000d740  call    ?RunAnalyzers@DiagDeepDive@UpdateDiagnosticsInternal@@SAJPEAPEAUHSTRING__@@IPEAU3@110@Z; UpdateDiagnosticsInternal::DiagDeepDive::RunAnalyzers(HSTRING__ * *,uint,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18000d745  mov     esi, eax
0x18000d747  mov     rbx, [rbp+pv]
0x18000d74b  mov     [rbp+var_50], rbx
0x18000d74f  test    rbx, rbx
0x18000d752  jz      short loc_18000D75B
0x18000d754  lock inc dword ptr [rbx+120h]
0x18000d75b  lea     rcx, [rbx+8]
0x18000d75f  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d764  mov     [rbx+118h], esi
0x18000d76a  lea     rcx, [rbp+var_50]
0x18000d76e  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d773  mov     rbx, [rbp+pv]
0x18000d777  mov     [rbp+var_50], rbx
0x18000d77b  test    rbx, rbx
0x18000d77e  jz      short loc_18000D787
0x18000d780  lock inc dword ptr [rbx+120h]
0x18000d787  lea     rcx, [rbx+8]
0x18000d78b  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18000d790  mov     eax, esi
0x18000d792  sar     eax, 1Fh
0x18000d795  and     eax, 1
0x18000d798  add     eax, 2
0x18000d79b  mov     [rbx+114h], eax
0x18000d7a1  lea     rcx, [rbp+var_50]
0x18000d7a5  call    ??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)
0x18000d7aa  mov     rdi, [rbp+pv]
0x18000d7ae  lea     rbx, [rdi+0C8h]
0x18000d7b5  mov     rcx, rbx; lpCriticalSection
0x18000d7b8  call    cs:__imp_EnterCriticalSection
0x18000d7be  or      dword ptr [rdi+48h], 300h
0x18000d7c5  cmp     qword ptr [rdi+0F8h], 0
0x18000d7cd  jz      short loc_18000D7DD
0x18000d7cf  mov     edx, 2
0x18000d7d4  lea     rcx, [rdi+8]
0x18000d7d8  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000d7dd  test    rbx, rbx
0x18000d7e0  jz      short loc_18000D7EC
0x18000d7e2  mov     rcx, rbx; lpCriticalSection
0x18000d7e5  call    cs:__imp_LeaveCriticalSection
0x18000d7eb  nop
0x18000d7ec  mov     rbx, [rbp+pv]
0x18000d7f0  test    rbx, rbx
0x18000d7f3  jz      short loc_18000D816
0x18000d7f5  or      eax, 0FFFFFFFFh
0x18000d7f8  lock xadd [rbx+120h], eax
0x18000d800  cmp     eax, 1
0x18000d803  jnz     short loc_18000D816
0x18000d805  mov     rcx, rbx
0x18000d808  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d80d  mov     rcx, rbx; pv
0x18000d810  call    cs:__imp_CoTaskMemFree
0x18000d816  lea     rcx, [rbp+var_48+8]; this
0x18000d81a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000d81f  mov     eax, esi
0x18000d821  mov     rcx, [rbp+var_10]
0x18000d825  xor     rcx, rsp; StackCookie
0x18000d828  call    __security_check_cookie
0x18000d82d  lea     r11, [rsp+80h+var_s0]
0x18000d835  mov     rbx, [r11+10h]
0x18000d839  mov     rsi, [r11+20h]
0x18000d83d  mov     rdi, [r11+28h]
0x18000d841  mov     rsp, r11
0x18000d844  pop     rbp
0x18000d845  retn
```
