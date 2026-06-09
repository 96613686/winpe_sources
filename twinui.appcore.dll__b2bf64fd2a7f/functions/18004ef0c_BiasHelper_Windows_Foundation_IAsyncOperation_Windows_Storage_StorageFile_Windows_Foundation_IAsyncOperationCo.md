# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *> *)

- ea: `0x18004ef0c`
- end: `0x18004ef91`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022a50`
- `0x18004fcdc`

## callees

- `0x180003d24`
- `0x18004ef0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004ef43`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004ef43`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18004ef71`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18004ef71`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,1>::CreateBias(
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
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppstm);
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
0x18004ef0c  mov     [rsp+arg_0], rbx
0x18004ef11  push    rdi
0x18004ef12  sub     rsp, 30h
0x18004ef16  mov     qword ptr [rcx], 0
0x18004ef1d  mov     rdi, r8
0x18004ef20  mov     dword ptr [rcx+8], 0
0x18004ef27  mov     rbx, rcx
0x18004ef2a  test    rdx, rdx
0x18004ef2d  jz      short loc_18004EF7C
0x18004ef2f  test    r9, r9
0x18004ef32  jz      short loc_18004EF7C
0x18004ef34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef39  mov     r8, rbx; ppstm
0x18004ef3c  mov     edx, 1; fDeleteOnRelease
0x18004ef41  xor     ecx, ecx; hGlobal
0x18004ef43  call    cs:__imp_CreateStreamOnHGlobal
0x18004ef49  mov     [rbx+8], eax
0x18004ef4c  test    eax, eax
0x18004ef4e  js      short loc_18004EF83
0x18004ef50  mov     rcx, [rbx]; pStm
0x18004ef53  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18004ef5a  mov     [rsp+38h+mshlflags], 1; mshlflags
0x18004ef62  xor     r9d, r9d; dwDestContext
0x18004ef65  mov     r8, rdi; pUnk
0x18004ef68  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x18004ef71  call    cs:__imp_CoMarshalInterface
0x18004ef77  mov     [rbx+8], eax
0x18004ef7a  jmp     short loc_18004EF83
0x18004ef7c  mov     dword ptr [rcx+8], 80004002h
0x18004ef83  mov     rax, rbx
0x18004ef86  mov     rbx, [rsp+38h+arg_0]
0x18004ef8b  add     rsp, 30h
0x18004ef8f  pop     rdi
0x18004ef90  retn
```
