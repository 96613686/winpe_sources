# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18005a1c0`
- end: `0x18005a247`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057e84`
- `0x180064140`

## callees

- `0x1800297f4`
- `0x18005a1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a205`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a1fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a21f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a1fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a21f`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        void **a1,
        __int64 a2,
        __int64 a3)
{
  void **v4; // rax
  void **v5; // rsi
  void *v6; // rbp
  void *v7; // r14
  DWORD LastError; // ebx
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pv,
                  a2,
                  a3);
  v5 = v4;
  if ( a1 != v4 )
  {
    v6 = *a1;
    v7 = *v4;
    if ( *a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *a1 = v7;
    *v5 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return *a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18005a1c0  mov     [rsp+arg_8], rbx
0x18005a1c5  mov     [rsp+arg_10], rbp
0x18005a1ca  push    rsi
0x18005a1cb  push    rdi
0x18005a1cc  push    r14
0x18005a1ce  sub     rsp, 20h
0x18005a1d2  mov     rdi, rcx
0x18005a1d5  lea     rcx, [rsp+38h+pv]
0x18005a1da  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005a1df  mov     rsi, rax
0x18005a1e2  cmp     rdi, rax
0x18005a1e5  jz      short loc_18005A215
0x18005a1e7  mov     rbp, [rdi]
0x18005a1ea  mov     r14, [rax]
0x18005a1ed  test    rbp, rbp
0x18005a1f0  jz      short loc_18005A20B
0x18005a1f2  call    cs:__imp_GetLastError
0x18005a1f8  mov     rcx, rbp; pv
0x18005a1fb  mov     ebx, eax
0x18005a1fd  call    cs:__imp_CoTaskMemFree
0x18005a203  mov     ecx, ebx; dwErrCode
0x18005a205  call    cs:__imp_SetLastError
0x18005a20b  mov     [rdi], r14
0x18005a20e  mov     qword ptr [rsi], 0
0x18005a215  mov     rcx, [rsp+38h+pv]; pv
0x18005a21a  test    rcx, rcx
0x18005a21d  jz      short loc_18005A225
0x18005a21f  call    cs:__imp_CoTaskMemFree
0x18005a225  mov     rax, [rdi]
0x18005a228  mov     rbx, [rsp+38h+arg_8]
0x18005a22d  neg     rax
0x18005a230  mov     rbp, [rsp+38h+arg_10]
0x18005a235  sbb     eax, eax
0x18005a237  not     eax
0x18005a239  and     eax, 8007000Eh
0x18005a23e  add     rsp, 20h
0x18005a242  pop     r14
0x18005a244  pop     rdi
0x18005a245  pop     rsi
0x18005a246  retn
```
