# Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)

- ea: `0x180038ce0`
- end: `0x180038cf6`
- name: `??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001fa2c`
- `0x180041c08`
- `0x180041d48`

## callees

- `0x180038ce0`
- `0x18003b524`

## pseudocode

```c
void __fastcall __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180038ce0  sub     rsp, 28h
0x180038ce4  mov     rcx, [rcx]; Block
0x180038ce7  test    rcx, rcx
0x180038cea  jz      short loc_180038CF1
0x180038cec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038cf1  add     rsp, 28h
0x180038cf5  retn
```
