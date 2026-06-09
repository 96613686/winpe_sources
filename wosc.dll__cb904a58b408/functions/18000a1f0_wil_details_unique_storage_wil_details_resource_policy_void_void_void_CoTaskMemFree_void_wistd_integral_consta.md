# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000a1f0`
- end: `0x18000a207`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a170`
- `0x18000a810`
- `0x180010818`
- `0x1800109dc`
- `0x180011024`
- `0x18001247c`
- `0x1800156e4`
- `0x18003cd38`
- `0x180049ec4`
- `0x18004a05c`
- `0x18004f22c`
- `0x18004f580`

## callees

- `0x18000a1f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18000a1f0  sub     rsp, 28h
0x18000a1f4  mov     rcx, [rcx]; pv
0x18000a1f7  test    rcx, rcx
0x18000a1fa  jz      short loc_18000A202
0x18000a1fc  call    cs:__imp_CoTaskMemFree
0x18000a202  add     rsp, 28h
0x18000a206  retn
```
