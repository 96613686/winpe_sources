# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationProgressHandler<unsigned __int64,unsigned __int64>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(unsigned __int64)

- ea: `0x1800819a0`
- end: `0x180081b75`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_K_K@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJ_K@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180082350`

## callees

- `0x18000ddd4`
- `0x18001415c`
- `0x18001db74`
- `0x18003233c`
- `0x18004ba14`
- `0x180079aa8`
- `0x180079c84`
- `0x180081828`
- `0x1800819a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180081aa0`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180081aa0`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180081acc`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180081acc`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180081b02`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180081b02`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationProgressHandler<unsigned __int64,unsigned __int64>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rbx
  int v8; // eax
  __int64 v10; // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v12; // [rsp+50h] [rbp-20h]
  GUID v13; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+A0h] [rbp+30h] BYREF
  struct IRpcOptions *v15; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v10 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v10);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(
              &v10,
              &pUnk) >= 0 )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<unsigned __int64,unsigned __int64>>::CopyLocal(
                a1 + 144,
                v5,
                &v14) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          &v13,
          a1,
          1);
      }
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
      RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
      ppstm = 0;
      v12 = 0;
      if ( v15 && v14 )
      {
        v7 = pUnk;
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppstm);
        v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
        if ( v12 >= 0 )
          v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
      }
      else
      {
        v12 = -2147467262;
      }
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, __int64))v14->lpVtbl[1].QueryInterface)(v14, pUnk, a2);
      v4 = v8;
      if ( v8 < 0 )
      {
        RoTransformError((unsigned int)v8, 0, 0);
        v4 = 0;
      }
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          1);
      AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800819a0  push    rbp
0x1800819a2  push    rbx
0x1800819a3  push    rsi
0x1800819a4  push    rdi
0x1800819a5  push    r15
0x1800819a7  mov     rbp, rsp
0x1800819aa  sub     rsp, 70h
0x1800819ae  mov     rsi, rdx
0x1800819b1  mov     rdi, rcx
0x1800819b4  xor     ebx, ebx
0x1800819b6  mov     [rbp+var_30], rcx
0x1800819ba  lea     rcx, [rbp+var_30]
0x1800819be  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800819c3  nop
0x1800819c4  mov     [rbp+pUnk], rbx
0x1800819c8  mov     rcx, rdi
0x1800819cb  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x1800819d0  test    al, al
0x1800819d2  jz      loc_180081B55
0x1800819d8  lea     rdx, [rbp+pUnk]
0x1800819dc  lea     rcx, [rbp+var_30]
0x1800819e0  call    ??$As@U?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>>)
0x1800819e5  test    eax, eax
0x1800819e7  js      loc_180081B55
0x1800819ed  mov     [rbp+arg_0], rbx
0x1800819f1  lea     rcx, [rbp+arg_0]
0x1800819f5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800819fa  lea     rcx, [rdi+90h]
0x180081a01  lea     r8, [rbp+arg_0]
0x180081a05  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationProgressHandler@_K_K@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<unsigned __int64,unsigned __int64>>::CopyLocal(_GUID const &,void * *)
0x180081a0a  test    eax, eax
0x180081a0c  js      loc_180081B42
0x180081a12  lea     r15d, [rbx+1]
0x180081a16  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180081a1d  test    rcx, rcx
0x180081a20  jz      short loc_180081A4F
0x180081a22  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180081a29  movdqu  [rbp+var_10], xmm0
0x180081a2e  mov     rax, [rcx]
0x180081a31  mov     [rsp+70h+mshlflags], r15d
0x180081a36  mov     [rsp+70h+pvDestContext], rdi
0x180081a3b  lea     r9, [rbp+var_10]
0x180081a3f  lea     r8d, [rbx+2]
0x180081a43  mov     edx, r15d
0x180081a46  mov     rax, [rax+48h]
0x180081a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a4f  mov     [rbp+arg_10], 0
0x180081a57  lea     rcx, [rbp+arg_10]
0x180081a5b  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081a60  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180081a64  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180081a68  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180081a6d  mov     [rbp+ppstm], 0
0x180081a75  mov     [rbp+var_20], 0
0x180081a7c  cmp     [rbp+arg_10], 0
0x180081a81  jz      short loc_180081AD7
0x180081a83  cmp     [rbp+arg_0], 0
0x180081a88  jz      short loc_180081AD7
0x180081a8a  mov     rbx, [rbp+pUnk]
0x180081a8e  lea     rcx, [rbp+ppstm]
0x180081a92  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081a97  lea     r8, [rbp+ppstm]; ppstm
0x180081a9b  mov     edx, r15d; fDeleteOnRelease
0x180081a9e  xor     ecx, ecx; hGlobal
0x180081aa0  call    cs:__imp_CreateStreamOnHGlobal
0x180081aa6  mov     [rbp+var_20], eax
0x180081aa9  test    eax, eax
0x180081aab  js      short loc_180081ADE
0x180081aad  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x180081ab2  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x180081abb  xor     r9d, r9d; dwDestContext
0x180081abe  mov     r8, rbx; pUnk
0x180081ac1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180081ac8  mov     rcx, [rbp+ppstm]; pStm
0x180081acc  call    cs:__imp_CoMarshalInterface
0x180081ad2  mov     [rbp+var_20], eax
0x180081ad5  jmp     short loc_180081ADE
0x180081ad7  mov     [rbp+var_20], 80004002h
0x180081ade  mov     rcx, [rbp+arg_0]
0x180081ae2  mov     rax, [rcx]
0x180081ae5  mov     r8, rsi
0x180081ae8  mov     rdx, [rbp+pUnk]
0x180081aec  mov     rax, [rax+18h]
0x180081af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081af5  mov     ebx, eax
0x180081af7  test    eax, eax
0x180081af9  jns     short loc_180081B0A
0x180081afb  xor     r8d, r8d
0x180081afe  xor     edx, edx
0x180081b00  mov     ecx, eax
0x180081b02  call    cs:__imp_RoTransformError
0x180081b08  xor     ebx, ebx
0x180081b0a  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180081b11  test    rcx, rcx
0x180081b14  jz      short loc_180081B2F
0x180081b16  mov     rax, [rcx]
0x180081b19  mov     r9d, r15d
0x180081b1c  mov     r8d, 2
0x180081b22  mov     edx, r15d
0x180081b25  mov     rax, [rax+50h]
0x180081b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b2e  nop
0x180081b2f  lea     rcx, [rbp+ppstm]
0x180081b33  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x180081b38  nop
0x180081b39  lea     rcx, [rbp+arg_10]
0x180081b3d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081b42  mov     rcx, rdi
0x180081b45  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180081b4a  nop
0x180081b4b  lea     rcx, [rbp+arg_0]
0x180081b4f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081b54  nop
0x180081b55  lea     rcx, [rbp+pUnk]
0x180081b59  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081b5e  nop
0x180081b5f  lea     rcx, [rbp+var_30]
0x180081b63  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180081b68  mov     eax, ebx
0x180081b6a  add     rsp, 70h
0x180081b6e  pop     r15
0x180081b70  pop     rdi
0x180081b71  pop     rsi
0x180081b72  pop     rbx
0x180081b73  pop     rbp
0x180081b74  retn
```
