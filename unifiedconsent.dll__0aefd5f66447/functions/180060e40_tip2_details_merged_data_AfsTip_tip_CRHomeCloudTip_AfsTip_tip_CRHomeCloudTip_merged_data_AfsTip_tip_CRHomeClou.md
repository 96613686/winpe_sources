# tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(void)

- ea: `0x180060e40`
- end: `0x180060ed1`
- name: `??1?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060ed8`
- `0x180060f60`
- `0x180060fb0`
- `0x180061d10`
- `0x180067ca8`
- `0x1800685c8`

## callees

- `0x1800139fc`
- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180060e40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060ec0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180060e8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180060e8b`

## pseudocode

```c
void __fastcall tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::~merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
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
0x180060e40  mov     [rsp+arg_0], rbx
0x180060e45  push    rdi
0x180060e46  sub     rsp, 20h
0x180060e4a  lea     rax, ??_7?$merged_data@U_tip_CRHomeCloudTip@AfsTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AfsTip::_tip_CRHomeCloudTip,AfsTip::_tip_CRHomeCloudTip>::`vftable'
0x180060e51  mov     rbx, rcx
0x180060e54  mov     [rcx], rax
0x180060e57  add     rcx, 8
0x180060e5b  lea     rdi, [rcx+0F0h]
0x180060e62  cmp     qword ptr [rdi], 0
0x180060e66  jz      short loc_180060E78
0x180060e68  test    byte ptr [rcx+14h], 1
0x180060e6c  jnz     short loc_180060E78
0x180060e6e  mov     edx, 4
0x180060e73  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180060e78  lea     rcx, [rbx+110h]
0x180060e7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180060e84  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180060e8b  call    cs:__imp_DeleteCriticalSection
0x180060e91  mov     rcx, rdi
0x180060e94  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180060e99  lea     rcx, [rbx+80h]
0x180060ea0  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180060ea5  lea     rcx, [rbx+68h]
0x180060ea9  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180060eae  lea     rcx, [rbx+50h]
0x180060eb2  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180060eb7  mov     rcx, [rbx+10h]; pv
0x180060ebb  test    rcx, rcx
0x180060ebe  jz      short loc_180060EC6
0x180060ec0  call    cs:__imp_CoTaskMemFree
0x180060ec6  mov     rbx, [rsp+28h+arg_0]
0x180060ecb  add     rsp, 20h
0x180060ecf  pop     rdi
0x180060ed0  retn
```
