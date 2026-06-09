# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)

- ea: `0x14001d934`
- end: `0x14001d9b9`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d930`
- `0x14001b410`
- `0x14001b760`
- `0x140033b30`

## callees

- `0x140005e4c`
- `0x14001d934`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001d999`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001d999`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001d96b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001d96b`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(
        LPSTREAM *ppstm,
        __int64 a2,
        IUnknown *a3,
        __int64 a4)
{
  HRESULT StreamOnHGlobal; // eax

  *ppstm = 0;
  *((_DWORD *)ppstm + 2) = 0;
  if ( a2 && a4 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppstm);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
    *((_DWORD *)ppstm + 2) = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      *((_DWORD *)ppstm + 2) = CoMarshalInterface(*ppstm, &GUID_00000000_0000_0000_c000_000000000046, a3, 0, 0, 1u);
  }
  else
  {
    *((_DWORD *)ppstm + 2) = -2147467262;
  }
  return ppstm;
}

```

## disassembly

```asm
0x14001d934  mov     [rsp+arg_0], rbx
0x14001d939  push    rdi
0x14001d93a  sub     rsp, 30h
0x14001d93e  mov     qword ptr [rcx], 0
0x14001d945  mov     rdi, r8
0x14001d948  mov     dword ptr [rcx+8], 0
0x14001d94f  mov     rbx, rcx
0x14001d952  test    rdx, rdx
0x14001d955  jz      short loc_14001D9A4
0x14001d957  test    r9, r9
0x14001d95a  jz      short loc_14001D9A4
0x14001d95c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d961  mov     r8, rbx; ppstm
0x14001d964  mov     edx, 1; fDeleteOnRelease
0x14001d969  xor     ecx, ecx; hGlobal
0x14001d96b  call    cs:__imp_CreateStreamOnHGlobal
0x14001d971  mov     [rbx+8], eax
0x14001d974  test    eax, eax
0x14001d976  js      short loc_14001D9AB
0x14001d978  mov     rcx, [rbx]; pStm
0x14001d97b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14001d982  mov     [rsp+38h+mshlflags], 1; mshlflags
0x14001d98a  xor     r9d, r9d; dwDestContext
0x14001d98d  mov     r8, rdi; pUnk
0x14001d990  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x14001d999  call    cs:__imp_CoMarshalInterface
0x14001d99f  mov     [rbx+8], eax
0x14001d9a2  jmp     short loc_14001D9AB
0x14001d9a4  mov     dword ptr [rcx+8], 80004002h
0x14001d9ab  mov     rax, rbx
0x14001d9ae  mov     rbx, [rsp+38h+arg_0]
0x14001d9b3  add     rsp, 30h
0x14001d9b7  pop     rdi
0x14001d9b8  retn
```
