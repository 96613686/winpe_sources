# StartOperationAndThen_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_e6df34189ced74daa6b0c48db56ac83e___

- ea: `0x18000cafc`
- end: `0x18000cba7`
- name: `StartOperationAndThen_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_e6df34189ced74daa6b0c48db56ac83e___`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011b74`

## callees

- `0x180008e80`
- `0x18000c8f4`
- `0x18000cafc`
- `0x180010cd0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall StartOperationAndThen_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile____Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile_____lambda_e6df34189ced74daa6b0c48db56ac83e___(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int32 *v3; // rax
  __int64 *v4; // rax
  volatile int *v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-28h] BYREF
  CSafeElementProxy *v11; // [rsp+30h] [rbp-18h]
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v10[0] = *a2;
  v10[1] = a2[1];
  v3 = (volatile signed __int32 *)a2[2];
  v11 = (CSafeElementProxy *)v3;
  if ( v3 )
    _InterlockedIncrement(v3 + 8);
  v4 = Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::StorageFile___Windows::Storage::IStorageFile_____::___Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows::Foundation::IAsyncOperation_Windows::Storage::StorageFile______enum_ABI::Windows::Foundation::AsyncStatus___lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___(
         &v12,
         v10);
  v6 = *v4;
  *v4 = 0;
  v7 = v12;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::Release(
      v7,
      v5);
  }
  if ( v11 )
    CSafeElementProxy::Release(v11);
  if ( v6 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 48LL))(a1, v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x18000cafc  mov     r11, rsp
0x18000caff  mov     [r11+8], rbx
0x18000cb03  push    rdi
0x18000cb04  sub     rsp, 40h
0x18000cb08  mov     rax, [rdx]
0x18000cb0b  mov     rbx, rcx
0x18000cb0e  mov     [r11-28h], rax
0x18000cb12  mov     rax, [rdx+8]
0x18000cb16  mov     [r11-20h], rax
0x18000cb1a  mov     rax, [rdx+10h]
0x18000cb1e  mov     [r11-18h], rax
0x18000cb22  test    rax, rax
0x18000cb25  jz      short loc_18000CB2B
0x18000cb27  lock inc dword ptr [rax+20h]
0x18000cb2b  lea     rdx, [rsp+48h+var_28]
0x18000cb30  lea     rcx, [rsp+48h+arg_8]
0x18000cb35  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Storage__StorageFile___Windows__Storage__IStorageFile__________Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__StorageFile_____lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___1_Windows__Foundation__IAsyncOperation_Windows__Storage__StorageFile______enum_ABI__Windows__Foundation__AsyncStatus___lambda_6d2141bf2f1c315b8b4e45cbbadd4f9e___
0x18000cb3a  mov     rdi, [rax]
0x18000cb3d  mov     qword ptr [rax], 0
0x18000cb44  mov     rcx, [rsp+48h+arg_8]
0x18000cb49  test    rcx, rcx
0x18000cb4c  jz      short loc_18000CB5C
0x18000cb4e  mov     [rsp+48h+arg_8], 0
0x18000cb57  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>>::Release(void)
0x18000cb5c  mov     rcx, [rsp+48h+var_18]; this
0x18000cb61  test    rcx, rcx
0x18000cb64  jz      short loc_18000CB6B
0x18000cb66  call    ?Release@CSafeElementProxy@@QEAAKXZ; CSafeElementProxy::Release(void)
0x18000cb6b  test    rdi, rdi
0x18000cb6e  jz      short loc_18000CB95
0x18000cb70  mov     rax, [rbx]
0x18000cb73  mov     rdx, rdi
0x18000cb76  mov     rcx, rbx
0x18000cb79  mov     rax, [rax+30h]
0x18000cb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb82  mov     ebx, eax
0x18000cb84  mov     rcx, rdi
0x18000cb87  mov     rax, [rdi]
0x18000cb8a  mov     rax, [rax+10h]
0x18000cb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb93  jmp     short loc_18000CB9A
0x18000cb95  mov     ebx, 8007000Eh
0x18000cb9a  mov     eax, ebx
0x18000cb9c  mov     rbx, [rsp+48h+arg_0]
0x18000cba1  add     rsp, 40h
0x18000cba5  pop     rdi
0x18000cba6  retn
```
