# tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)

- ea: `0x18000fcd4`
- end: `0x18000fd59`
- name: `??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eb50`
- `0x18000fe3c`
- `0x18000ff14`
- `0x180010f28`
- `0x180011994`
- `0x180015fc0`

## callees

- `0x18000fcd4`
- `0x18000ffd0`
- `0x1800100e8`
- `0x18001016c`
- `0x1800101ec`
- `0x180015820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd13`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd48`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<1,0,0>::complete_helper(p_LockCount, 4);
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
0x18000fcd4  mov     [rsp+arg_0], rbx
0x18000fcd9  push    rdi
0x18000fcda  sub     rsp, 20h
0x18000fcde  lea     rax, ??_7?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::`vftable'
0x18000fce5  mov     rbx, rcx
0x18000fce8  mov     [rcx], rax
0x18000fceb  add     rcx, 8
0x18000fcef  lea     rdi, [rcx+0F0h]
0x18000fcf6  cmp     qword ptr [rdi], 0
0x18000fcfa  jz      short loc_18000FD0C
0x18000fcfc  test    byte ptr [rcx+14h], 1
0x18000fd00  jnz     short loc_18000FD0C
0x18000fd02  mov     edx, 4
0x18000fd07  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18000fd0c  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000fd13  call    cs:__imp_DeleteCriticalSection
0x18000fd19  mov     rcx, rdi
0x18000fd1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18000fd21  lea     rcx, [rbx+80h]
0x18000fd28  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x18000fd2d  lea     rcx, [rbx+68h]
0x18000fd31  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18000fd36  lea     rcx, [rbx+50h]
0x18000fd3a  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18000fd3f  mov     rcx, [rbx+10h]; pv
0x18000fd43  test    rcx, rcx
0x18000fd46  jz      short loc_18000FD4E
0x18000fd48  call    cs:__imp_CoTaskMemFree
0x18000fd4e  mov     rbx, [rsp+28h+arg_0]
0x18000fd53  add     rsp, 20h
0x18000fd57  pop     rdi
0x18000fd58  retn
```
