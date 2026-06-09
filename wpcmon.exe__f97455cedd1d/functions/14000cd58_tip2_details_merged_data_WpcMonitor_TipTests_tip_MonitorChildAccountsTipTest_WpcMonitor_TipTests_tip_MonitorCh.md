# tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(void)

- ea: `0x14000cd58`
- end: `0x14000cddd`
- name: `??1?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ce38`
- `0x14000ecbc`
- `0x14001ccec`

## callees

- `0x14000cd58`
- `0x14000cf40`
- `0x14000d1b8`
- `0x14000d23c`
- `0x14000d2bc`
- `0x14001c818`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000cd97`
- `KERNEL32!DeleteCriticalSection` at `0x14000cd97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000cdcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000cdcc`

## pseudocode

```c
void __fastcall tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::~merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
  DeleteCriticalSection(a1 + 5);
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(v3);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[3].LockCount);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&a1[2].LockSemaphore);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(&a1[2]);
  OwningThread = a1->OwningThread;
  if ( OwningThread )
    CoTaskMemFree(OwningThread);
}

```

## disassembly

```asm
0x14000cd58  mov     [rsp+arg_0], rbx
0x14000cd5d  push    rdi
0x14000cd5e  sub     rsp, 20h
0x14000cd62  lea     rax, ??_7?$merged_data@U_tip_MonitorChildAccountsTipTest@TipTests@WpcMonitor@@U123@@details@tip2@@6B@; const tip2::details::merged_data<WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest,WpcMonitor::TipTests::_tip_MonitorChildAccountsTipTest>::`vftable'
0x14000cd69  mov     rbx, rcx
0x14000cd6c  mov     [rcx], rax
0x14000cd6f  add     rcx, 8
0x14000cd73  lea     rdi, [rcx+0F0h]
0x14000cd7a  cmp     qword ptr [rdi], 0
0x14000cd7e  jz      short loc_14000CD90
0x14000cd80  test    byte ptr [rcx+14h], 1
0x14000cd84  jnz     short loc_14000CD90
0x14000cd86  mov     edx, 4
0x14000cd8b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x14000cd90  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000cd97  call    cs:__imp_DeleteCriticalSection
0x14000cd9d  mov     rcx, rdi
0x14000cda0  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x14000cda5  lea     rcx, [rbx+80h]
0x14000cdac  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x14000cdb1  lea     rcx, [rbx+68h]
0x14000cdb5  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x14000cdba  lea     rcx, [rbx+50h]
0x14000cdbe  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x14000cdc3  mov     rcx, [rbx+10h]; pv
0x14000cdc7  test    rcx, rcx
0x14000cdca  jz      short loc_14000CDD2
0x14000cdcc  call    cs:__imp_CoTaskMemFree
0x14000cdd2  mov     rbx, [rsp+28h+arg_0]
0x14000cdd7  add     rsp, 20h
0x14000cddb  pop     rdi
0x14000cddc  retn
```
