# tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(void)

- ea: `0x180058544`
- end: `0x1800585ed`
- name: `??1?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ`
- size: `169`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058704`
- `0x18005882c`
- `0x1800588f4`
- `0x18005d2e8`
- `0x18005ebec`
- `0x18006006c`

## callees

- `0x1800139fc`
- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180058544`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800585a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800585a7`

## pseudocode

```c
void __fastcall tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::~merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
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
0x180058544  mov     [rsp+arg_0], rbx
0x180058549  push    rdi
0x18005854a  sub     rsp, 20h
0x18005854e  lea     rax, ??_7?$merged_data@U_tip_CNRegisterWnpEndpointTip@CloudNotificationsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip,CloudNotificationsTip::_tip_CNRegisterWnpEndpointTip>::`vftable'
0x180058555  mov     rbx, rcx
0x180058558  mov     [rcx], rax
0x18005855b  add     rcx, 8
0x18005855f  lea     rdi, [rcx+0F0h]
0x180058566  cmp     qword ptr [rdi], 0
0x18005856a  jz      short loc_18005857C
0x18005856c  test    byte ptr [rcx+14h], 1
0x180058570  jnz     short loc_18005857C
0x180058572  mov     edx, 4
0x180058577  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18005857c  lea     rcx, [rbx+150h]
0x180058583  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058588  lea     rcx, [rbx+130h]
0x18005858f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058594  lea     rcx, [rbx+110h]
0x18005859b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800585a0  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800585a7  call    cs:__imp_DeleteCriticalSection
0x1800585ad  mov     rcx, rdi
0x1800585b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800585b5  lea     rcx, [rbx+80h]
0x1800585bc  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800585c1  lea     rcx, [rbx+68h]
0x1800585c5  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800585ca  lea     rcx, [rbx+50h]
0x1800585ce  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x1800585d3  mov     rcx, [rbx+10h]; pv
0x1800585d7  test    rcx, rcx
0x1800585da  jz      short loc_1800585E2
0x1800585dc  call    cs:__imp_CoTaskMemFree
0x1800585e2  mov     rbx, [rsp+28h+arg_0]
0x1800585e7  add     rsp, 20h
0x1800585eb  pop     rdi
0x1800585ec  retn
```
