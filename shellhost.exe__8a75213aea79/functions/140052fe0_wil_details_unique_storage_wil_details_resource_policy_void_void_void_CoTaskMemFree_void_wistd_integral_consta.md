# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140052fe0`
- end: `0x140052ff7`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140051114`
- `0x140052f3c`
- `0x140053744`
- `0x140056db0`
- `0x140057044`
- `0x14005d9cc`
- `0x14005dd48`
- `0x14005e4f4`
- `0x14005f760`

## callees

- `0x140052fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052fec`

## pseudocode

```c
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
0x140052fe0  sub     rsp, 28h
0x140052fe4  mov     rcx, [rcx]; pv
0x140052fe7  test    rcx, rcx
0x140052fea  jz      short loc_140052FF2
0x140052fec  call    cs:__imp_CoTaskMemFree
0x140052ff2  add     rsp, 28h
0x140052ff6  retn
```
