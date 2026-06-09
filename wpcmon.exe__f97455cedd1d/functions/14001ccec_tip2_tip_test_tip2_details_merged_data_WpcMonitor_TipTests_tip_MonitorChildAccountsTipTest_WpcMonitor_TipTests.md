# tip2::tip_test<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>::ensure_data(void)

- ea: `0x14001ccec`
- end: `0x14001cd78`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000ecbc`

## callees

- `0x14000b44c`
- `0x14000cd58`
- `0x14001ccec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cd39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cd64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cd39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001cd64`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14001ccec  mov     [rsp+arg_10], rbx
0x14001ccf1  push    rdi
0x14001ccf2  sub     rsp, 20h
0x14001ccf6  cmp     qword ptr [rcx], 0
0x14001ccfa  mov     rdi, rcx
0x14001ccfd  jnz     short loc_14001CD6A
0x14001ccff  lea     rcx, [rsp+28h+pv]
0x14001cd04  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>,>(void)
0x14001cd09  mov     rdx, [rax]
0x14001cd0c  mov     qword ptr [rax], 0
0x14001cd13  mov     rbx, [rdi]
0x14001cd16  mov     [rdi], rdx
0x14001cd19  test    rbx, rbx
0x14001cd1c  jz      short loc_14001CD3F
0x14001cd1e  or      eax, 0FFFFFFFFh
0x14001cd21  lock xadd [rbx+120h], eax
0x14001cd29  cmp     eax, 1
0x14001cd2c  jnz     short loc_14001CD3F
0x14001cd2e  mov     rcx, rbx
0x14001cd31  call    ??1?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(void)
0x14001cd36  mov     rcx, rbx; pv
0x14001cd39  call    cs:__imp_CoTaskMemFree
0x14001cd3f  mov     rbx, [rsp+28h+pv]
0x14001cd44  test    rbx, rbx
0x14001cd47  jz      short loc_14001CD6A
0x14001cd49  or      eax, 0FFFFFFFFh
0x14001cd4c  lock xadd [rbx+120h], eax
0x14001cd54  cmp     eax, 1
0x14001cd57  jnz     short loc_14001CD6A
0x14001cd59  mov     rcx, rbx
0x14001cd5c  call    ??1?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(void)
0x14001cd61  mov     rcx, rbx; pv
0x14001cd64  call    cs:__imp_CoTaskMemFree
0x14001cd6a  mov     rbx, [rsp+28h+arg_10]
0x14001cd6f  mov     rax, rdi
0x14001cd72  add     rsp, 20h
0x14001cd76  pop     rdi
0x14001cd77  retn
```
