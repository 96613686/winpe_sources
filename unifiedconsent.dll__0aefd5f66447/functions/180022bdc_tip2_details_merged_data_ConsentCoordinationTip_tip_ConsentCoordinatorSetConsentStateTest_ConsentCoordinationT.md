# tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>(void)

- ea: `0x180022bdc`
- end: `0x180022c61`
- name: `??1?$merged_data@U_tip_ConsentCoordinatorSetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022e98`
- `0x180022fc0`
- `0x180029504`

## callees

- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180022bdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022c1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022c1b`

## pseudocode

```c
void __fastcall tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::`vftable';
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
0x180022bdc  mov     [rsp+arg_0], rbx
0x180022be1  push    rdi
0x180022be2  sub     rsp, 20h
0x180022be6  lea     rax, ??_7?$merged_data@U_tip_ConsentCoordinatorSetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorSetConsentStateTest>::`vftable'
0x180022bed  mov     rbx, rcx
0x180022bf0  mov     [rcx], rax
0x180022bf3  add     rcx, 8
0x180022bf7  lea     rdi, [rcx+0F0h]
0x180022bfe  cmp     qword ptr [rdi], 0
0x180022c02  jz      short loc_180022C14
0x180022c04  test    byte ptr [rcx+14h], 1
0x180022c08  jnz     short loc_180022C14
0x180022c0a  mov     edx, 4
0x180022c0f  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180022c14  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180022c1b  call    cs:__imp_DeleteCriticalSection
0x180022c21  mov     rcx, rdi
0x180022c24  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180022c29  lea     rcx, [rbx+80h]
0x180022c30  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180022c35  lea     rcx, [rbx+68h]
0x180022c39  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180022c3e  lea     rcx, [rbx+50h]
0x180022c42  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180022c47  mov     rcx, [rbx+10h]; pv
0x180022c4b  test    rcx, rcx
0x180022c4e  jz      short loc_180022C56
0x180022c50  call    cs:__imp_CoTaskMemFree
0x180022c56  mov     rbx, [rsp+28h+arg_0]
0x180022c5b  add     rsp, 20h
0x180022c5f  pop     rdi
0x180022c60  retn
```
