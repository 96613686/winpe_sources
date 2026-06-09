# tip2::test_data_control<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>::~test_data_control<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>(void)

- ea: `0x14000ce38`
- end: `0x14000ceba`
- name: `??1?$test_data_control@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000ecbc`

## callees

- `0x14000cd58`
- `0x14000ce38`
- `0x14001ca70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ce80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000cea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ce80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000cea9`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>::~test_data_control<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x14000ce38  mov     [rsp+arg_8], rbx
0x14000ce3d  push    rdi
0x14000ce3e  sub     rsp, 20h
0x14000ce42  mov     rdi, rcx
0x14000ce45  mov     rcx, [rcx]
0x14000ce48  test    rcx, rcx
0x14000ce4b  jz      short loc_14000CE86
0x14000ce4d  add     rcx, 8
0x14000ce51  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x14000ce56  mov     rbx, [rdi]
0x14000ce59  mov     qword ptr [rdi], 0
0x14000ce60  test    rbx, rbx
0x14000ce63  jz      short loc_14000CE86
0x14000ce65  or      eax, 0FFFFFFFFh
0x14000ce68  lock xadd [rbx+120h], eax
0x14000ce70  cmp     eax, 1
0x14000ce73  jnz     short loc_14000CE86
0x14000ce75  mov     rcx, rbx
0x14000ce78  call    ??1?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(void)
0x14000ce7d  mov     rcx, rbx; pv
0x14000ce80  call    cs:__imp_CoTaskMemFree
0x14000ce86  mov     rbx, [rdi]
0x14000ce89  test    rbx, rbx
0x14000ce8c  jz      short loc_14000CEAF
0x14000ce8e  or      eax, 0FFFFFFFFh
0x14000ce91  lock xadd [rbx+120h], eax
0x14000ce99  cmp     eax, 1
0x14000ce9c  jnz     short loc_14000CEAF
0x14000ce9e  mov     rcx, rbx
0x14000cea1  call    ??1?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(void)
0x14000cea6  mov     rcx, rbx; pv
0x14000cea9  call    cs:__imp_CoTaskMemFree
0x14000ceaf  mov     rbx, [rsp+28h+arg_8]
0x14000ceb4  add     rsp, 20h
0x14000ceb8  pop     rdi
0x14000ceb9  retn
```
