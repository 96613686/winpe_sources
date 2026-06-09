# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180016ccc`
- end: `0x180016d19`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000420c`
- `0x180005000`
- `0x18001681c`
- `0x180025b24`

## callees

- `0x180003138`
- `0x180003158`
- `0x180016ccc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016cf6`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180016ccc  mov     [rsp+arg_8], rbx
0x180016cd1  mov     [rsp+arg_10], rsi
0x180016cd6  push    rdi
0x180016cd7  sub     rsp, 20h
0x180016cdb  mov     rdi, [rcx]
0x180016cde  mov     rsi, rdx
0x180016ce1  mov     rbx, rcx
0x180016ce4  test    rdi, rdi
0x180016ce7  jz      short loc_180016D06
0x180016ce9  lea     rcx, [rsp+28h+arg_0]; this
0x180016cee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016cf3  mov     rcx, rdi; pv
0x180016cf6  call    cs:__imp_CoTaskMemFree
0x180016cfc  lea     rcx, [rsp+28h+arg_0]; this
0x180016d01  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016d06  mov     [rbx], rsi
0x180016d09  mov     rbx, [rsp+28h+arg_8]
0x180016d0e  mov     rsi, [rsp+28h+arg_10]
0x180016d13  add     rsp, 20h
0x180016d17  pop     rdi
0x180016d18  retn
```
