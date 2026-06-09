# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(void)

- ea: `0x14000b774`
- end: `0x14000b78b`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400215c7`
- `0x140021713`
- `0x14002188b`
- `0x140021909`
- `0x14002191b`
- `0x140021963`
- `0x140021aef`

## callees

- `0x14000b774`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000b780`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(
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
0x14000b774  sub     rsp, 28h
0x14000b778  mov     rcx, [rcx]; pv
0x14000b77b  test    rcx, rcx
0x14000b77e  jz      short loc_14000B786
0x14000b780  call    cs:__imp_CoTaskMemFree
0x14000b786  add     rsp, 28h
0x14000b78a  retn
```
