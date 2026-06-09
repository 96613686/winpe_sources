# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationProgressHandler<uint,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(uint)

- ea: `0x1800751c4`
- end: `0x180075398`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@U?$IAsyncOperationProgressHandler@II@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJI@Z`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800797e0`

## callees

- `0x18000ddd4`
- `0x18001415c`
- `0x18001db74`
- `0x180034254`
- `0x18005d590`
- `0x1800747d8`
- `0x1800751c4`
- `0x180079aa8`
- `0x180079c84`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800752c3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800752c3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800752ef`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800752ef`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075325`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075325`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<unsigned int,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
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
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>>(
              &v10,
              &pUnk) >= 0 )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v14);
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<unsigned int,unsigned int>>::CopyLocal(
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
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(v14, pUnk, a2);
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
      AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<unsigned int,unsigned int>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<unsigned int,unsigned int>>(&ppstm);
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
0x1800751c4  push    rbp
0x1800751c6  push    rbx
0x1800751c7  push    rsi
0x1800751c8  push    rdi
0x1800751c9  push    r15
0x1800751cb  mov     rbp, rsp
0x1800751ce  sub     rsp, 70h
0x1800751d2  mov     esi, edx
0x1800751d4  mov     rdi, rcx
0x1800751d7  xor     ebx, ebx
0x1800751d9  mov     [rbp+var_30], rcx
0x1800751dd  lea     rcx, [rbp+var_30]
0x1800751e1  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800751e6  nop
0x1800751e7  mov     [rbp+pUnk], rbx
0x1800751eb  mov     rcx, rdi
0x1800751ee  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x1800751f3  test    al, al
0x1800751f5  jz      loc_180075378
0x1800751fb  lea     rdx, [rbp+pUnk]
0x1800751ff  lea     rcx, [rbp+var_30]
0x180075203  call    ??$As@U?$IAsyncOperationWithProgress@II@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@II@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<uint,uint>>>)
0x180075208  test    eax, eax
0x18007520a  js      loc_180075378
0x180075210  mov     [rbp+arg_0], rbx
0x180075214  lea     rcx, [rbp+arg_0]
0x180075218  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007521d  lea     rcx, [rdi+90h]
0x180075224  lea     r8, [rbp+arg_0]
0x180075228  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationProgressHandler@II@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationProgressHandler<uint,uint>>::CopyLocal(_GUID const &,void * *)
0x18007522d  test    eax, eax
0x18007522f  js      loc_180075365
0x180075235  lea     r15d, [rbx+1]
0x180075239  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180075240  test    rcx, rcx
0x180075243  jz      short loc_180075272
0x180075245  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18007524c  movdqu  [rbp+var_10], xmm0
0x180075251  mov     rax, [rcx]
0x180075254  mov     [rsp+70h+mshlflags], r15d
0x180075259  mov     [rsp+70h+pvDestContext], rdi
0x18007525e  lea     r9, [rbp+var_10]
0x180075262  lea     r8d, [rbx+2]
0x180075266  mov     edx, r15d
0x180075269  mov     rax, [rax+48h]
0x18007526d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075272  mov     [rbp+arg_10], 0
0x18007527a  lea     rcx, [rbp+arg_10]
0x18007527e  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075283  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180075287  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18007528b  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180075290  mov     [rbp+ppstm], 0
0x180075298  mov     [rbp+var_20], 0
0x18007529f  cmp     [rbp+arg_10], 0
0x1800752a4  jz      short loc_1800752FA
0x1800752a6  cmp     [rbp+arg_0], 0
0x1800752ab  jz      short loc_1800752FA
0x1800752ad  mov     rbx, [rbp+pUnk]
0x1800752b1  lea     rcx, [rbp+ppstm]
0x1800752b5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800752ba  lea     r8, [rbp+ppstm]; ppstm
0x1800752be  mov     edx, r15d; fDeleteOnRelease
0x1800752c1  xor     ecx, ecx; hGlobal
0x1800752c3  call    cs:__imp_CreateStreamOnHGlobal
0x1800752c9  mov     [rbp+var_20], eax
0x1800752cc  test    eax, eax
0x1800752ce  js      short loc_180075301
0x1800752d0  mov     [rsp+70h+mshlflags], r15d; mshlflags
0x1800752d5  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x1800752de  xor     r9d, r9d; dwDestContext
0x1800752e1  mov     r8, rbx; pUnk
0x1800752e4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800752eb  mov     rcx, [rbp+ppstm]; pStm
0x1800752ef  call    cs:__imp_CoMarshalInterface
0x1800752f5  mov     [rbp+var_20], eax
0x1800752f8  jmp     short loc_180075301
0x1800752fa  mov     [rbp+var_20], 80004002h
0x180075301  mov     rcx, [rbp+arg_0]
0x180075305  mov     rax, [rcx]
0x180075308  mov     r8d, esi
0x18007530b  mov     rdx, [rbp+pUnk]
0x18007530f  mov     rax, [rax+18h]
0x180075313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075318  mov     ebx, eax
0x18007531a  test    eax, eax
0x18007531c  jns     short loc_18007532D
0x18007531e  xor     r8d, r8d
0x180075321  xor     edx, edx
0x180075323  mov     ecx, eax
0x180075325  call    cs:__imp_RoTransformError
0x18007532b  xor     ebx, ebx
0x18007532d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180075334  test    rcx, rcx
0x180075337  jz      short loc_180075352
0x180075339  mov     rax, [rcx]
0x18007533c  mov     r9d, r15d
0x18007533f  mov     r8d, 2
0x180075345  mov     edx, r15d
0x180075348  mov     rax, [rax+50h]
0x18007534c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075351  nop
0x180075352  lea     rcx, [rbp+ppstm]
0x180075356  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@II@Foundation@Windows@@U?$IAsyncOperationProgressHandler@II@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<uint,uint>,Windows::Foundation::IAsyncOperationProgressHandler<uint,uint>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<uint,uint>,Windows::Foundation::IAsyncOperationProgressHandler<uint,uint>>(void)
0x18007535b  nop
0x18007535c  lea     rcx, [rbp+arg_10]
0x180075360  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075365  mov     rcx, rdi
0x180075368  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x18007536d  nop
0x18007536e  lea     rcx, [rbp+arg_0]
0x180075372  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075377  nop
0x180075378  lea     rcx, [rbp+pUnk]
0x18007537c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075381  nop
0x180075382  lea     rcx, [rbp+var_30]
0x180075386  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007538b  mov     eax, ebx
0x18007538d  add     rsp, 70h
0x180075391  pop     r15
0x180075393  pop     rdi
0x180075394  pop     rsi
0x180075395  pop     rbx
0x180075396  pop     rbp
0x180075397  retn
```
