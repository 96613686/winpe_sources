# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)

- ea: `0x180033910`
- end: `0x180033927`
- name: `??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033890`
- `0x1800339ac`
- `0x1800437dc`
- `0x18005097c`
- `0x1800556f0`
- `0x1800559fc`
- `0x180056538`
- `0x180058894`
- `0x18006e2b0`
- `0x18007e840`
- `0x180084cf0`
- `0x18008548c`

## callees

- `0x180033910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003391c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003391c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(
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
0x180033910  sub     rsp, 28h
0x180033914  mov     rcx, [rcx]; pv
0x180033917  test    rcx, rcx
0x18003391a  jz      short loc_180033922
0x18003391c  call    cs:__imp_CoTaskMemFree
0x180033922  add     rsp, 28h
0x180033926  retn
```
