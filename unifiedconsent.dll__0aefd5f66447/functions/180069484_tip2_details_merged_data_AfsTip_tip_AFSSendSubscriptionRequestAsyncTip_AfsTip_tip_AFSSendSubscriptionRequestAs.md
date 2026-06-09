# tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(void)

- ea: `0x180069484`
- end: `0x18006955d`
- name: `??1?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@QEAA@XZ`
- size: `217`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069564`
- `0x1800695ec`
- `0x18006963c`
- `0x18006a080`
- `0x18006c260`
- `0x18006cad0`

## callees

- `0x1800139fc`
- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180069484`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006954c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006954c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069517`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069517`

## pseudocode

```c
void __fastcall tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::~merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
  std::wstring::_Tidy_deallocate(&a1[11].LockSemaphore);
  std::wstring::_Tidy_deallocate(&a1[10].SpinCount);
  std::wstring::_Tidy_deallocate(&a1[10]);
  std::wstring::_Tidy_deallocate(&a1[9].LockCount);
  std::wstring::_Tidy_deallocate(&a1[8].OwningThread);
  std::wstring::_Tidy_deallocate(&a1[7].LockSemaphore);
  std::wstring::_Tidy_deallocate(&a1[6].SpinCount);
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
0x180069484  mov     [rsp+arg_0], rbx
0x180069489  push    rdi
0x18006948a  sub     rsp, 20h
0x18006948e  lea     rax, ??_7?$merged_data@U_tip_AFSSendSubscriptionRequestAsyncTip@AfsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip,AfsTip::_tip_AFSSendSubscriptionRequestAsyncTip>::`vftable'
0x180069495  mov     rbx, rcx
0x180069498  mov     [rcx], rax
0x18006949b  add     rcx, 8
0x18006949f  lea     rdi, [rcx+0F0h]
0x1800694a6  cmp     qword ptr [rdi], 0
0x1800694aa  jz      short loc_1800694BC
0x1800694ac  test    byte ptr [rcx+14h], 1
0x1800694b0  jnz     short loc_1800694BC
0x1800694b2  mov     edx, 4
0x1800694b7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800694bc  lea     rcx, [rbx+1D0h]
0x1800694c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800694c8  lea     rcx, [rbx+1B0h]
0x1800694cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800694d4  lea     rcx, [rbx+190h]
0x1800694db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800694e0  lea     rcx, [rbx+170h]
0x1800694e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800694ec  lea     rcx, [rbx+150h]
0x1800694f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800694f8  lea     rcx, [rbx+130h]
0x1800694ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069504  lea     rcx, [rbx+110h]
0x18006950b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069510  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180069517  call    cs:__imp_DeleteCriticalSection
0x18006951d  mov     rcx, rdi
0x180069520  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180069525  lea     rcx, [rbx+80h]
0x18006952c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180069531  lea     rcx, [rbx+68h]
0x180069535  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18006953a  lea     rcx, [rbx+50h]
0x18006953e  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180069543  mov     rcx, [rbx+10h]; pv
0x180069547  test    rcx, rcx
0x18006954a  jz      short loc_180069552
0x18006954c  call    cs:__imp_CoTaskMemFree
0x180069552  mov     rbx, [rsp+28h+arg_0]
0x180069557  add     rsp, 20h
0x18006955b  pop     rdi
0x18006955c  retn
```
