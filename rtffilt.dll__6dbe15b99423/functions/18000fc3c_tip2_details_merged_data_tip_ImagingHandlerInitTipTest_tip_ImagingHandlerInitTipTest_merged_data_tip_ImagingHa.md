# tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(void)

- ea: `0x18000fc3c`
- end: `0x18000fccd`
- name: `??1?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fdb4`
- `0x18000fec4`
- `0x180010b80`

## callees

- `0x1800041b8`
- `0x18000fc3c`
- `0x18000ffd0`
- `0x1800100e8`
- `0x18001016c`
- `0x1800101ec`
- `0x180015820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcbc`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::~merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<1,0,0>::complete_helper(p_LockCount, 4);
  std::wstring::~wstring(&a1[6].SpinCount);
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
0x18000fc3c  mov     [rsp+arg_0], rbx
0x18000fc41  push    rdi
0x18000fc42  sub     rsp, 20h
0x18000fc46  lea     rax, ??_7?$merged_data@U_tip_ImagingHandlerInitTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_ImagingHandlerInitTipTest,_tip_ImagingHandlerInitTipTest>::`vftable'
0x18000fc4d  mov     rbx, rcx
0x18000fc50  mov     [rcx], rax
0x18000fc53  add     rcx, 8
0x18000fc57  lea     rdi, [rcx+0F0h]
0x18000fc5e  cmp     qword ptr [rdi], 0
0x18000fc62  jz      short loc_18000FC74
0x18000fc64  test    byte ptr [rcx+14h], 1
0x18000fc68  jnz     short loc_18000FC74
0x18000fc6a  mov     edx, 4
0x18000fc6f  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000fc74  lea     rcx, [rbx+110h]
0x18000fc7b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fc80  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000fc87  call    cs:__imp_DeleteCriticalSection
0x18000fc8d  mov     rcx, rdi
0x18000fc90  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18000fc95  lea     rcx, [rbx+80h]
0x18000fc9c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x18000fca1  lea     rcx, [rbx+68h]
0x18000fca5  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18000fcaa  lea     rcx, [rbx+50h]
0x18000fcae  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18000fcb3  mov     rcx, [rbx+10h]; pv
0x18000fcb7  test    rcx, rcx
0x18000fcba  jz      short loc_18000FCC2
0x18000fcbc  call    cs:__imp_CoTaskMemFree
0x18000fcc2  mov     rbx, [rsp+28h+arg_0]
0x18000fcc7  add     rsp, 20h
0x18000fccb  pop     rdi
0x18000fccc  retn
```
