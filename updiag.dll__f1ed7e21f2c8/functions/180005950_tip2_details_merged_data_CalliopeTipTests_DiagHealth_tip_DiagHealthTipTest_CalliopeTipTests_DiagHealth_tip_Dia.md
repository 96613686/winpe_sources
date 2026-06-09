# tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)

- ea: `0x180005950`
- end: `0x1800059d5`
- name: `??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004d9c`
- `0x18000c4a0`
- `0x18000c578`
- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`
- `0x18000d900`
- `0x18000d988`

## callees

- `0x180005950`
- `0x180005d48`
- `0x180006680`
- `0x180006e74`
- `0x180006f04`
- `0x1800076bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000598f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000598f`

## pseudocode

```c
void __fastcall tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<1,0,0>::complete_helper(p_LockCount, 4);
  DeleteCriticalSection(a1 + 5);
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(v3);
  tip2::vector_nothrow<tip2::test_flag>::clear(&a1[3].LockCount);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&a1[2].LockSemaphore);
  tip2::vector_nothrow<wil::StoredFailureInfo>::clear(&a1[2]);
  OwningThread = a1->OwningThread;
  if ( OwningThread )
    CoTaskMemFree(OwningThread);
}

```

## disassembly

```asm
0x180005950  mov     [rsp+arg_0], rbx
0x180005955  push    rdi
0x180005956  sub     rsp, 20h
0x18000595a  lea     rax, ??_7?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@6B@; const tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::`vftable'
0x180005961  mov     rbx, rcx
0x180005964  mov     [rcx], rax
0x180005967  add     rcx, 8
0x18000596b  lea     rdi, [rcx+0F0h]
0x180005972  cmp     qword ptr [rdi], 0
0x180005976  jz      short loc_180005988
0x180005978  test    byte ptr [rcx+14h], 1
0x18000597c  jnz     short loc_180005988
0x18000597e  mov     edx, 4
0x180005983  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180005988  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000598f  call    cs:__imp_DeleteCriticalSection
0x180005995  mov     rcx, rdi
0x180005998  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18000599d  lea     rcx, [rbx+80h]
0x1800059a4  call    ?clear@?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAAXXZ; tip2::vector_nothrow<tip2::test_flag>::clear(void)
0x1800059a9  lea     rcx, [rbx+68h]
0x1800059ad  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800059b2  lea     rcx, [rbx+50h]
0x1800059b6  call    ?clear@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::StoredFailureInfo>::clear(void)
0x1800059bb  mov     rcx, [rbx+10h]; pv
0x1800059bf  test    rcx, rcx
0x1800059c2  jz      short loc_1800059CA
0x1800059c4  call    cs:__imp_CoTaskMemFree
0x1800059ca  mov     rbx, [rsp+28h+arg_0]
0x1800059cf  add     rsp, 20h
0x1800059d3  pop     rdi
0x1800059d4  retn
```
