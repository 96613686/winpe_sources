# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180010e64`
- end: `0x180010e9f`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010904`
- `0x180010dc0`
- `0x1800172d0`

## callees

- `0x180010e64`
- `0x1800171a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e7b`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180010e64  push    rbx
0x180010e66  push    rbp
0x180010e67  push    rsi
0x180010e68  push    rdi
0x180010e69  sub     rsp, 28h
0x180010e6d  mov     rsi, [rcx]
0x180010e70  mov     rbp, rdx
0x180010e73  mov     rdi, rcx
0x180010e76  test    rsi, rsi
0x180010e79  jz      short loc_180010E93
0x180010e7b  call    cs:__imp_GetLastError
0x180010e81  mov     rcx, rsi; pti
0x180010e84  mov     ebx, eax
0x180010e86  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180010e8b  mov     ecx, ebx; dwErrCode
0x180010e8d  call    cs:__imp_SetLastError
0x180010e93  mov     [rdi], rbp
0x180010e96  add     rsp, 28h
0x180010e9a  pop     rdi
0x180010e9b  pop     rsi
0x180010e9c  pop     rbp
0x180010e9d  pop     rbx
0x180010e9e  retn
```
