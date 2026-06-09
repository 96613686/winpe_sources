# tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(void)

- ea: `0x1800515bc`
- end: `0x18005164d`
- name: `??1?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800516bc`
- `0x180051744`
- `0x180052980`
- `0x1800555ac`

## callees

- `0x1800139fc`
- `0x180013c40`
- `0x180013cbc`
- `0x180013d40`
- `0x180013dc0`
- `0x18001962c`
- `0x1800515bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005163c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005163c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051607`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051607`

## pseudocode

```c
void __fastcall tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::~merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::`vftable';
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
0x1800515bc  mov     [rsp+arg_0], rbx
0x1800515c1  push    rdi
0x1800515c2  sub     rsp, 20h
0x1800515c6  lea     rax, ??_7?$merged_data@U_tip_CRHttpInterfaceTip@CloudRequestorTip@@U12@@details@tip2@@6B@; const tip2::details::merged_data<CloudRequestorTip::_tip_CRHttpInterfaceTip,CloudRequestorTip::_tip_CRHttpInterfaceTip>::`vftable'
0x1800515cd  mov     rbx, rcx
0x1800515d0  mov     [rcx], rax
0x1800515d3  add     rcx, 8
0x1800515d7  lea     rdi, [rcx+0F0h]
0x1800515de  cmp     qword ptr [rdi], 0
0x1800515e2  jz      short loc_1800515F4
0x1800515e4  test    byte ptr [rcx+14h], 1
0x1800515e8  jnz     short loc_1800515F4
0x1800515ea  mov     edx, 4
0x1800515ef  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800515f4  lea     rcx, [rbx+110h]
0x1800515fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051600  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180051607  call    cs:__imp_DeleteCriticalSection
0x18005160d  mov     rcx, rdi
0x180051610  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180051615  lea     rcx, [rbx+80h]
0x18005161c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180051621  lea     rcx, [rbx+68h]
0x180051625  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18005162a  lea     rcx, [rbx+50h]
0x18005162e  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180051633  mov     rcx, [rbx+10h]; pv
0x180051637  test    rcx, rcx
0x18005163a  jz      short loc_180051642
0x18005163c  call    cs:__imp_CoTaskMemFree
0x180051642  mov     rbx, [rsp+28h+arg_0]
0x180051647  add     rsp, 20h
0x18005164b  pop     rdi
0x18005164c  retn
```
