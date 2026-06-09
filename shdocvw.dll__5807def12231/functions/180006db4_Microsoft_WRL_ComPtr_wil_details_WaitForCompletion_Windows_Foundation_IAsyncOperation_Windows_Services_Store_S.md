# Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)

- ea: `0x180006db4`
- end: `0x180006dda`
- name: `?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b34`
- `0x180006d78`
- `0x180014884`
- `0x180014ae0`
- `0x180020aa0`
- `0x180020c48`
- `0x180023438`

## callees

- `0x180006db4`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180006db4  sub     rsp, 28h
0x180006db8  mov     rdx, rcx
0x180006dbb  xor     eax, eax
0x180006dbd  mov     rcx, [rcx]
0x180006dc0  test    rcx, rcx
0x180006dc3  jz      short loc_180006DD5
0x180006dc5  mov     [rdx], rax
0x180006dc8  mov     rax, [rcx]
0x180006dcb  mov     rax, [rax+10h]
0x180006dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd4  nop
0x180006dd5  add     rsp, 28h
0x180006dd9  retn
```
