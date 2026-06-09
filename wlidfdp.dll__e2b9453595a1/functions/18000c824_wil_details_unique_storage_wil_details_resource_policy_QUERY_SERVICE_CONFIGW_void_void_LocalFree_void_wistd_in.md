# wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)

- ea: `0x18000c824`
- end: `0x18000c842`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000cec8`

## callees

- `0x18000c824`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c830`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return ((__int64 (*)(void))LocalFree)();
  return result;
}

```

## disassembly

```asm
0x18000c824  sub     rsp, 28h
0x18000c828  mov     rcx, [rcx]
0x18000c82b  test    rcx, rcx
0x18000c82e  jz      short loc_18000C83D
0x18000c830  mov     rax, cs:__imp_LocalFree
0x18000c837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c83c  nop
0x18000c83d  add     rsp, 28h
0x18000c841  retn
```
