# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)

- ea: `0x18002b0cc`
- end: `0x18002b0f4`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180033363`

## callees

- `0x18002b0cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b0e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b0e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b0df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b0df`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<1>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(
        PTP_WORK *a1)
{
  struct _TP_WORK *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    WaitForThreadpoolWorkCallbacks(*a1, 0);
    CloseThreadpoolWork(v1);
  }
}

```

## disassembly

```asm
0x18002b0cc  push    rbx
0x18002b0ce  sub     rsp, 20h
0x18002b0d2  mov     rbx, [rcx]
0x18002b0d5  test    rbx, rbx
0x18002b0d8  jz      short loc_18002B0EE
0x18002b0da  xor     edx, edx; fCancelPendingCallbacks
0x18002b0dc  mov     rcx, rbx; pwk
0x18002b0df  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002b0e5  mov     rcx, rbx; pwk
0x18002b0e8  call    cs:__imp_CloseThreadpoolWork
0x18002b0ee  add     rsp, 20h
0x18002b0f2  pop     rbx
0x18002b0f3  retn
```
