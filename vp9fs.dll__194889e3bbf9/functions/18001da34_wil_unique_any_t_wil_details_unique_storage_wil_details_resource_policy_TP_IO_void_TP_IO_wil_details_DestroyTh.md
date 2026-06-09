# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>(void)

- ea: `0x18001da34`
- end: `0x18001da5c`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolIo@$00@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800326a4`
- `0x180032d9b`

## callees

- `0x18001da34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001da50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001da50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001da47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001da47`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&public: static void wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&public: static void wil::details::DestroyThreadPoolIo<1>::Destroy(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>(
        PTP_IO *a1)
{
  struct _TP_IO *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    WaitForThreadpoolIoCallbacks(*a1, 0);
    CloseThreadpoolIo(v1);
  }
}

```

## disassembly

```asm
0x18001da34  push    rbx
0x18001da36  sub     rsp, 20h
0x18001da3a  mov     rbx, [rcx]
0x18001da3d  test    rbx, rbx
0x18001da40  jz      short loc_18001DA56
0x18001da42  xor     edx, edx; fCancelPendingCallbacks
0x18001da44  mov     rcx, rbx; pio
0x18001da47  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18001da4d  mov     rcx, rbx; pio
0x18001da50  call    cs:__imp_CloseThreadpoolIo
0x18001da56  add     rsp, 20h
0x18001da5a  pop     rbx
0x18001da5b  retn
```
