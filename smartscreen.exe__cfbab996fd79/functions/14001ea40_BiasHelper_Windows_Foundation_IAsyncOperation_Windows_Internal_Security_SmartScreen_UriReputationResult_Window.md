# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)

- ea: `0x14001ea40`
- end: `0x14001ead2`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z`
- size: `146`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e050`
- `0x14001c370`
- `0x14001c780`
- `0x140034fb4`

## callees

- `0x1400061cc`
- `0x14001ea40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001eaab`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001eaab`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001ea77`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001ea77`

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
0x14001ea40  mov     [rsp+arg_0], rbx
0x14001ea45  push    rdi
0x14001ea46  sub     rsp, 30h
0x14001ea4a  mov     qword ptr [rcx], 0
0x14001ea51  mov     rdi, r8
0x14001ea54  mov     dword ptr [rcx+8], 0
0x14001ea5b  mov     rbx, rcx
0x14001ea5e  test    rdx, rdx
0x14001ea61  jz      short loc_14001EABC
0x14001ea63  test    r9, r9
0x14001ea66  jz      short loc_14001EABC
0x14001ea68  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001ea6d  mov     r8, rbx; ppstm
0x14001ea70  mov     edx, 1; fDeleteOnRelease
0x14001ea75  xor     ecx, ecx; hGlobal
0x14001ea77  call    cs:__imp_CreateStreamOnHGlobal
0x14001ea7e  nop     dword ptr [rax+rax+00h]
0x14001ea83  mov     [rbx+8], eax
0x14001ea86  test    eax, eax
0x14001ea88  js      short loc_14001EAC3
0x14001ea8a  mov     rcx, [rbx]; pStm
0x14001ea8d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14001ea94  mov     [rsp+38h+mshlflags], 1; mshlflags
0x14001ea9c  xor     r9d, r9d; dwDestContext
0x14001ea9f  mov     r8, rdi; pUnk
0x14001eaa2  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x14001eaab  call    cs:__imp_CoMarshalInterface
0x14001eab2  nop     dword ptr [rax+rax+00h]
0x14001eab7  mov     [rbx+8], eax
0x14001eaba  jmp     short loc_14001EAC3
0x14001eabc  mov     dword ptr [rcx+8], 80004002h
0x14001eac3  mov     rax, rbx
0x14001eac6  mov     rbx, [rsp+38h+arg_0]
0x14001eacb  add     rsp, 30h
0x14001eacf  pop     rdi
0x14001ead0  retn
```
