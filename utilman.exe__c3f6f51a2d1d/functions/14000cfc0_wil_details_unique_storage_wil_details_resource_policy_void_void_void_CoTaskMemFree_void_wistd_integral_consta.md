# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000cfc0`
- end: `0x14000cfde`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14000b4a0`
- `0x14000d2b0`
- `0x14000f9c4`
- `0x14000fe7c`
- `0x1400100c8`
- `0x140010954`
- `0x14001156c`
- `0x1400121cc`

## callees

- `0x14000cfc0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000cfcc`
- `ole32!CoTaskMemFree` at `0x14000cfcc`

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
0x14000cfc0  sub     rsp, 28h
0x14000cfc4  mov     rcx, [rcx]; pv
0x14000cfc7  test    rcx, rcx
0x14000cfca  jz      short loc_14000CFD8
0x14000cfcc  call    cs:__imp_CoTaskMemFree
0x14000cfd3  nop     dword ptr [rax+rax+00h]
0x14000cfd8  add     rsp, 28h
0x14000cfdc  retn
```
