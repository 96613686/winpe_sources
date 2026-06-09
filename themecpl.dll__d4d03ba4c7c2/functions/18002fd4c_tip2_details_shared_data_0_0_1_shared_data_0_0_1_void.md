# tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(void)

- ea: `0x18002fd4c`
- end: `0x18002fdb0`
- name: `??1?$shared_data@$0A@$0A@$00@details@tip2@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fc48`

## callees

- `0x18002fd4c`
- `0x18002fddc`
- `0x18002fe70`
- `0x180031c14`
- `0x180034df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fd5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fd5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fd9d`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(__int64 a1)
{
  void *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  if ( *(_QWORD *)(a1 + 240) )
    TestClose();
  tip2::vector_nothrow<tip2::test_flag>::clear(a1 + 120);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(a1 + 96);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(a1 + 72);
  v2 = *(void **)(a1 + 8);
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18002fd4c  push    rbx
0x18002fd4e  sub     rsp, 20h
0x18002fd52  mov     rbx, rcx
0x18002fd55  add     rcx, 0C0h; lpCriticalSection
0x18002fd5c  call    cs:__imp_DeleteCriticalSection
0x18002fd63  nop     dword ptr [rax+rax+00h]
0x18002fd68  mov     rcx, [rbx+0F0h]
0x18002fd6f  test    rcx, rcx
0x18002fd72  jz      short loc_18002FD79
0x18002fd74  call    TestClose
0x18002fd79  lea     rcx, [rbx+78h]
0x18002fd7d  call    ?clear@?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAAXXZ; tip2::vector_nothrow<tip2::test_flag>::clear(void)
0x18002fd82  lea     rcx, [rbx+60h]
0x18002fd86  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18002fd8b  lea     rcx, [rbx+48h]
0x18002fd8f  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18002fd94  mov     rcx, [rbx+8]; pv
0x18002fd98  test    rcx, rcx
0x18002fd9b  jz      short loc_18002FDA9
0x18002fd9d  call    cs:__imp_CoTaskMemFree
0x18002fda4  nop     dword ptr [rax+rax+00h]
0x18002fda9  add     rsp, 20h
0x18002fdad  pop     rbx
0x18002fdae  retn
```
