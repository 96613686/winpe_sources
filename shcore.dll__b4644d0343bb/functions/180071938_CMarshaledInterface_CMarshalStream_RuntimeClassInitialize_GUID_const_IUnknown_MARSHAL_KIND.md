# CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(_GUID const &,IUnknown *,MARSHAL_KIND)

- ea: `0x180071938`
- end: `0x1800719e2`
- name: `?RuntimeClassInitialize@CMarshalStream@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z`
- size: `170`
- prototype: `int __high(const struct _GUID *, struct IUnknown *, enum MARSHAL_KIND)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005c430`

## callees

- `0x18000ddd4`
- `0x180071938`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007194d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007194d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800719cf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1800719cf`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071983`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180071983`

## pseudocode

```c
__int64 __fastcall CMarshaledInterface::CMarshalStream::RuntimeClassInitialize(
        __int64 a1,
        const IID *a2,
        IUnknown *a3,
        int a4)
{
  DWORD CurrentThreadId; // eax
  __int64 v9; // rax
  unsigned int AgileReference; // ebx
  _QWORD v12[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 24) = a4;
  *(_DWORD *)(a1 + 40) = CurrentThreadId;
  if ( a4 == 2 )
  {
    v9 = 0;
    AgileReference = 0;
    v13 = 0;
    if ( a3 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
      AgileReference = RoGetAgileReference(0, a2, a3, &v13);
      v9 = v13;
    }
    v12[0] = *(_QWORD *)(a1 + 32);
    v13 = 0;
    *(_QWORD *)(a1 + 32) = v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v13);
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 16);
    return (unsigned int)CoMarshalInterThreadInterfaceInStream(a2, a3, (LPSTREAM *)(a1 + 16));
  }
  return AgileReference;
}

```

## disassembly

```asm
0x180071938  push    rbx
0x18007193a  push    rbp
0x18007193b  push    rsi
0x18007193c  push    rdi
0x18007193d  sub     rsp, 38h
0x180071941  mov     ebx, r9d
0x180071944  mov     rsi, r8
0x180071947  mov     rbp, rdx
0x18007194a  mov     rdi, rcx
0x18007194d  call    cs:__imp_GetCurrentThreadId
0x180071953  mov     [rdi+18h], ebx
0x180071956  mov     [rdi+28h], eax
0x180071959  cmp     ebx, 2
0x18007195c  jnz     short loc_1800719BC
0x18007195e  xor     eax, eax
0x180071960  xor     ebx, ebx
0x180071962  mov     [rsp+58h+arg_0], rax
0x180071967  test    rsi, rsi
0x18007196a  jz      short loc_180071990
0x18007196c  lea     rcx, [rsp+58h+arg_0]
0x180071971  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180071976  lea     r9, [rsp+58h+arg_0]
0x18007197b  mov     r8, rsi
0x18007197e  mov     rdx, rbp
0x180071981  xor     ecx, ecx
0x180071983  call    cs:__imp_RoGetAgileReference
0x180071989  mov     ebx, eax
0x18007198b  mov     rax, [rsp+58h+arg_0]
0x180071990  mov     rcx, [rdi+20h]
0x180071994  mov     [rsp+58h+var_38], rcx
0x180071999  lea     rcx, [rsp+58h+var_38]
0x18007199e  mov     [rsp+58h+arg_0], 0
0x1800719a7  mov     [rdi+20h], rax
0x1800719ab  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800719b0  lea     rcx, [rsp+58h+arg_0]
0x1800719b5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800719ba  jmp     short loc_1800719D7
0x1800719bc  lea     rcx, [rdi+10h]
0x1800719c0  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800719c5  lea     r8, [rdi+10h]; ppStm
0x1800719c9  mov     rdx, rsi; pUnk
0x1800719cc  mov     rcx, rbp; riid
0x1800719cf  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1800719d5  mov     ebx, eax
0x1800719d7  mov     eax, ebx
0x1800719d9  add     rsp, 38h
0x1800719dd  pop     rdi
0x1800719de  pop     rsi
0x1800719df  pop     rbp
0x1800719e0  pop     rbx
0x1800719e1  retn
```
