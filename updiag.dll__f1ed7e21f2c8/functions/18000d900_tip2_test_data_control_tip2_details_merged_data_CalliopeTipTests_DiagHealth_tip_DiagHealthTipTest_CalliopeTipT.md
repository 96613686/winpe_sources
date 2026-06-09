# tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(void)

- ea: `0x18000d900`
- end: `0x18000d982`
- name: `??1?$test_data_control@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`

## callees

- `0x180005950`
- `0x18000d900`
- `0x18000dbe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d971`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>::~test_data_control<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<1,0,0>::end_update(&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x18000d900  mov     [rsp+arg_8], rbx
0x18000d905  push    rdi
0x18000d906  sub     rsp, 20h
0x18000d90a  mov     rdi, rcx
0x18000d90d  mov     rcx, [rcx]
0x18000d910  test    rcx, rcx
0x18000d913  jz      short loc_18000D94E
0x18000d915  add     rcx, 8
0x18000d919  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x18000d91e  mov     rbx, [rdi]
0x18000d921  mov     qword ptr [rdi], 0
0x18000d928  test    rbx, rbx
0x18000d92b  jz      short loc_18000D94E
0x18000d92d  or      eax, 0FFFFFFFFh
0x18000d930  lock xadd [rbx+120h], eax
0x18000d938  cmp     eax, 1
0x18000d93b  jnz     short loc_18000D94E
0x18000d93d  mov     rcx, rbx
0x18000d940  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d945  mov     rcx, rbx; pv
0x18000d948  call    cs:__imp_CoTaskMemFree
0x18000d94e  mov     rbx, [rdi]
0x18000d951  test    rbx, rbx
0x18000d954  jz      short loc_18000D977
0x18000d956  or      eax, 0FFFFFFFFh
0x18000d959  lock xadd [rbx+120h], eax
0x18000d961  cmp     eax, 1
0x18000d964  jnz     short loc_18000D977
0x18000d966  mov     rcx, rbx
0x18000d969  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x18000d96e  mov     rcx, rbx; pv
0x18000d971  call    cs:__imp_CoTaskMemFree
0x18000d977  mov     rbx, [rsp+28h+arg_8]
0x18000d97c  add     rsp, 20h
0x18000d980  pop     rdi
0x18000d981  retn
```
