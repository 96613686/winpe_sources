# Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::_)(Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___

- ea: `0x18000c8f4`
- end: `0x18000c9d5`
- name: `Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::_)(Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cafc`

## callees

- `0x180003ffc`
- `0x180008e80`
- `0x18000c8f4`
- `0x18000d0d4`
- `0x18001f010`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::___Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___(
        __int64 *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v6; // rcx
  volatile int *v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v10; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = Microsoft::WRL::Details::ModuleBase::module_;
    *v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::`vftable';
    *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::`vftable';
    *((_DWORD *)v4 + 3) = 1;
    if ( v6 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
    v7 = (volatile int *)(v5 + 4);
    v5[2] = *a2;
    v8 = a2 + 2;
    v5[3] = a2[1];
    v5[4] = 0;
    if ( v5 + 4 != a2 + 2 )
    {
      *(_QWORD *)v7 = *v8;
      *v8 = 0;
    }
    *v5 = &off_180020760;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::Release(
        *a1,
        v7);
    *a1 = (__int64)v5;
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::___Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___::_MakeAllocator_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::___Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___(&v10);
  return a1;
}

```

## disassembly

```asm
0x18000c8f4  mov     [rsp+arg_8], rbx
0x18000c8f9  mov     [rsp+arg_10], rsi
0x18000c8fe  push    rdi
0x18000c8ff  sub     rsp, 20h
0x18000c903  mov     rsi, rdx
0x18000c906  mov     qword ptr [rcx], 0
0x18000c90d  mov     rdi, rcx
0x18000c910  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c917  mov     ecx, 28h ; '('; unsigned __int64
0x18000c91c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c921  mov     [rsp+28h+arg_0], rax
0x18000c926  mov     rbx, rax
0x18000c929  test    rax, rax
0x18000c92c  jz      loc_18000C9B8
0x18000c932  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c939  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::`vftable'
0x18000c940  mov     [rbx], rax
0x18000c943  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::`vftable'
0x18000c94a  mov     [rbx], rax
0x18000c94d  mov     dword ptr [rbx+0Ch], 1
0x18000c954  test    rcx, rcx
0x18000c957  jz      short loc_18000C965
0x18000c959  mov     rdx, [rcx]
0x18000c95c  mov     rax, [rdx+8]
0x18000c960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c965  mov     rax, [rsi]
0x18000c968  lea     rdx, [rbx+20h]
0x18000c96c  mov     [rbx+10h], rax
0x18000c970  lea     rcx, [rsi+10h]
0x18000c974  mov     rax, [rsi+8]
0x18000c978  mov     [rbx+18h], rax
0x18000c97c  mov     qword ptr [rdx], 0
0x18000c983  cmp     rdx, rcx
0x18000c986  jz      short loc_18000C995
0x18000c988  mov     rax, [rcx]
0x18000c98b  mov     [rdx], rax
0x18000c98e  mov     qword ptr [rcx], 0
0x18000c995  lea     rax, off_180020760
0x18000c99c  mov     [rbx], rax
0x18000c99f  mov     rcx, [rdi]
0x18000c9a2  test    rcx, rcx
0x18000c9a5  jz      short loc_18000C9AC
0x18000c9a7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::Release(void)
0x18000c9ac  mov     [rdi], rbx
0x18000c9af  mov     [rsp+28h+arg_0], 0
0x18000c9b8  lea     rcx, [rsp+28h+arg_0]
0x18000c9bd  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Storage__StorageFile___Windows__Storage__IStorageFile__________Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus______MakeAllocator_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Storage__StorageFile___Windows__Storage__IStorageFile__________Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus___
0x18000c9c2  mov     rbx, [rsp+28h+arg_8]
0x18000c9c7  mov     rax, rdi
0x18000c9ca  mov     rsi, [rsp+28h+arg_10]
0x18000c9cf  add     rsp, 20h
0x18000c9d3  pop     rdi
0x18000c9d4  retn
```
