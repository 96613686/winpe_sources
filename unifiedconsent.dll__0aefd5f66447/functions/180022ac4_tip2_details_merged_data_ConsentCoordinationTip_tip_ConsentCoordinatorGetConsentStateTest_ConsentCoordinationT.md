# tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(void)

- ea: `0x180022ac4`
- end: `0x180022b49`
- name: `??1?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022d88`
- `0x180022f70`
- `0x18002304c`
- `0x180024678`
- `0x1800254a8`
- `0x18002e38c`

## callees

- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180022ac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b38`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b03`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022b03`

## pseudocode

```c
void __fastcall tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::~merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::`vftable';
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
0x180022ac4  mov     [rsp+arg_0], rbx
0x180022ac9  push    rdi
0x180022aca  sub     rsp, 20h
0x180022ace  lea     rax, ??_7?$merged_data@U_tip_ConsentCoordinatorGetConsentStateTest@ConsentCoordinationTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest,ConsentCoordinationTip::_tip_ConsentCoordinatorGetConsentStateTest>::`vftable'
0x180022ad5  mov     rbx, rcx
0x180022ad8  mov     [rcx], rax
0x180022adb  add     rcx, 8
0x180022adf  lea     rdi, [rcx+0F0h]
0x180022ae6  cmp     qword ptr [rdi], 0
0x180022aea  jz      short loc_180022AFC
0x180022aec  test    byte ptr [rcx+14h], 1
0x180022af0  jnz     short loc_180022AFC
0x180022af2  mov     edx, 4
0x180022af7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180022afc  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180022b03  call    cs:__imp_DeleteCriticalSection
0x180022b09  mov     rcx, rdi
0x180022b0c  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180022b11  lea     rcx, [rbx+80h]
0x180022b18  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180022b1d  lea     rcx, [rbx+68h]
0x180022b21  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180022b26  lea     rcx, [rbx+50h]
0x180022b2a  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180022b2f  mov     rcx, [rbx+10h]; pv
0x180022b33  test    rcx, rcx
0x180022b36  jz      short loc_180022B3E
0x180022b38  call    cs:__imp_CoTaskMemFree
0x180022b3e  mov     rbx, [rsp+28h+arg_0]
0x180022b43  add     rsp, 20h
0x180022b47  pop     rdi
0x180022b48  retn
```
