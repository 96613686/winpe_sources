# tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(void)

- ea: `0x180040674`
- end: `0x180040705`
- name: `??1?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004070c`
- `0x180040794`
- `0x1800407e4`
- `0x180041410`
- `0x180047bd8`

## callees

- `0x1800139fc`
- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x180040674`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800406f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800406f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800406bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800406bf`

## pseudocode

```c
void __fastcall tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::~merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::`vftable';
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
0x180040674  mov     [rsp+arg_0], rbx
0x180040679  push    rdi
0x18004067a  sub     rsp, 20h
0x18004067e  lea     rax, ??_7?$merged_data@U_tip_CRFixAccountTip@CloudRequestorTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudRequestorTip::_tip_CRFixAccountTip,CloudRequestorTip::_tip_CRFixAccountTip>::`vftable'
0x180040685  mov     rbx, rcx
0x180040688  mov     [rcx], rax
0x18004068b  add     rcx, 8
0x18004068f  lea     rdi, [rcx+0F0h]
0x180040696  cmp     qword ptr [rdi], 0
0x18004069a  jz      short loc_1800406AC
0x18004069c  test    byte ptr [rcx+14h], 1
0x1800406a0  jnz     short loc_1800406AC
0x1800406a2  mov     edx, 4
0x1800406a7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800406ac  lea     rcx, [rbx+110h]
0x1800406b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800406b8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800406bf  call    cs:__imp_DeleteCriticalSection
0x1800406c5  mov     rcx, rdi
0x1800406c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800406cd  lea     rcx, [rbx+80h]
0x1800406d4  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x1800406d9  lea     rcx, [rbx+68h]
0x1800406dd  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x1800406e2  lea     rcx, [rbx+50h]
0x1800406e6  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x1800406eb  mov     rcx, [rbx+10h]; pv
0x1800406ef  test    rcx, rcx
0x1800406f2  jz      short loc_1800406FA
0x1800406f4  call    cs:__imp_CoTaskMemFree
0x1800406fa  mov     rbx, [rsp+28h+arg_0]
0x1800406ff  add     rsp, 20h
0x180040703  pop     rdi
0x180040704  retn
```
