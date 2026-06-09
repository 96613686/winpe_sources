# tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(void)

- ea: `0x1800583f0`
- end: `0x180058481`
- name: `??1?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800585f4`
- `0x18005878c`
- `0x18005887c`
- `0x180059840`
- `0x18005eac4`
- `0x18005fe6c`

## callees

- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x1800583f0`
- `0x180058b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058470`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005843b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005843b`

## pseudocode

```c
void __fastcall tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::~merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
  CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::~_tip_CNCreateOrUpdateSubscriptionTip((CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip *)&a1[6].OwningThread);
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
0x1800583f0  mov     [rsp+arg_0], rbx
0x1800583f5  push    rdi
0x1800583f6  sub     rsp, 20h
0x1800583fa  lea     rax, ??_7?$merged_data@U_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip,CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip>::`vftable'
0x180058401  mov     rbx, rcx
0x180058404  mov     [rcx], rax
0x180058407  add     rcx, 8
0x18005840b  lea     rdi, [rcx+0F0h]
0x180058412  cmp     qword ptr [rdi], 0
0x180058416  jz      short loc_180058428
0x180058418  test    byte ptr [rcx+14h], 1
0x18005841c  jnz     short loc_180058428
0x18005841e  mov     edx, 4
0x180058423  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180058428  lea     rcx, [rbx+100h]; this
0x18005842f  call    ??1_tip_CNCreateOrUpdateSubscriptionTip@CloudNotificationsTip@@QEAA@XZ; CloudNotificationsTip::_tip_CNCreateOrUpdateSubscriptionTip::~_tip_CNCreateOrUpdateSubscriptionTip(void)
0x180058434  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18005843b  call    cs:__imp_DeleteCriticalSection
0x180058441  mov     rcx, rdi
0x180058444  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180058449  lea     rcx, [rbx+80h]
0x180058450  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180058455  lea     rcx, [rbx+68h]
0x180058459  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18005845e  lea     rcx, [rbx+50h]
0x180058462  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180058467  mov     rcx, [rbx+10h]; pv
0x18005846b  test    rcx, rcx
0x18005846e  jz      short loc_180058476
0x180058470  call    cs:__imp_CoTaskMemFree
0x180058476  mov     rbx, [rsp+28h+arg_0]
0x18005847b  add     rsp, 20h
0x18005847f  pop     rdi
0x180058480  retn
```
