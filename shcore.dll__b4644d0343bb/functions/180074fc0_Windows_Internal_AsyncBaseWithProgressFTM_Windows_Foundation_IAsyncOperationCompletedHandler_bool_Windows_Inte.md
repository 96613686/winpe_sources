# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x180074fc0`
- end: `0x1800751bc`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800797c0`

## callees

- `0x18000ddd4`
- `0x18001415c`
- `0x18001db74`
- `0x18001e800`
- `0x18004ccac`
- `0x180074838`
- `0x180074fc0`
- `0x180079aa8`
- `0x180079c84`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800750de`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800750de`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007510a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18007510a`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075140`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180075140`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        int (__fastcall ***a1)(_QWORD, GUID *, LPUNKNOWN *),
        unsigned int a2)
{
  unsigned int v4; // esi
  int (__fastcall *v5)(_QWORD, GUID *, LPUNKNOWN *); // rbx
  __int64 v6; // rdx
  bool v7; // dl
  IUnknown *v8; // rbx
  int v9; // eax
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v13; // [rsp+50h] [rbp-20h]
  GUID v14; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v15; // [rsp+A0h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+B0h] [rbp+40h] BYREF
  struct IRpcOptions *v17; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v11);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1) )
  {
    v5 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(a1 + 18, v6, &v15) >= 0 )
      {
        if ( Microsoft::WRL::gCausality )
        {
          v14 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
          (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, int (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *), int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
            Microsoft::WRL::gCausality,
            1,
            2,
            &v14,
            a1,
            1);
        }
        v17 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v17);
        RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
        ppstm = 0;
        v13 = 0;
        if ( v17 && v15 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppstm);
          v13 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v13 >= 0 )
            v13 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v8, 0, 0, 1u);
        }
        else
        {
          v13 = -2147467262;
        }
        v9 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v15->lpVtbl[1].QueryInterface)(
               v15,
               pUnk,
               a2);
        v4 = v9;
        if ( v9 < 0 )
        {
          RoTransformError((unsigned int)v9, 0, 0);
          v4 = 0;
        }
        if ( Microsoft::WRL::gCausality )
          (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
            Microsoft::WRL::gCausality,
            1,
            2,
            1);
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v17);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v15);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v11);
  return v4;
}

```

## disassembly

```asm
0x180074fc0  mov     [rsp-28h+arg_8], rbx
0x180074fc5  push    rbp
0x180074fc6  push    rsi
0x180074fc7  push    rdi
0x180074fc8  push    r12
0x180074fca  push    r14
0x180074fcc  mov     rbp, rsp
0x180074fcf  sub     rsp, 70h
0x180074fd3  mov     r14d, edx
0x180074fd6  mov     rdi, rcx
0x180074fd9  xor     esi, esi
0x180074fdb  mov     [rbp+var_30], rcx
0x180074fdf  lea     rcx, [rbp+var_30]
0x180074fe3  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180074fe8  nop
0x180074fe9  mov     [rbp+pUnk], rsi
0x180074fed  mov     rcx, rdi
0x180074ff0  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x180074ff5  test    al, al
0x180074ff7  jz      loc_180075193
0x180074ffd  mov     rax, [rdi]
0x180075000  mov     rbx, [rax]
0x180075003  lea     rcx, [rbp+pUnk]
0x180075007  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007500c  lea     r8, [rbp+pUnk]
0x180075010  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180075017  mov     rcx, rdi
0x18007501a  mov     rax, rbx
0x18007501d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075022  nop
0x180075023  test    eax, eax
0x180075025  js      loc_180075193
0x18007502b  mov     [rbp+arg_0], rsi
0x18007502f  lea     rcx, [rbp+arg_0]
0x180075033  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075038  lea     rcx, [rdi+90h]
0x18007503f  lea     r8, [rbp+arg_0]
0x180075043  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x180075048  test    eax, eax
0x18007504a  js      loc_180075180
0x180075050  lea     r12d, [rsi+1]
0x180075054  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18007505b  test    rcx, rcx
0x18007505e  jz      short loc_18007508D
0x180075060  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180075067  movdqu  [rbp+var_10], xmm0
0x18007506c  mov     rax, [rcx]
0x18007506f  mov     [rsp+70h+mshlflags], r12d
0x180075074  mov     [rsp+70h+pvDestContext], rdi
0x180075079  lea     r9, [rbp+var_10]
0x18007507d  lea     r8d, [rsi+2]
0x180075081  mov     edx, r12d
0x180075084  mov     rax, [rax+48h]
0x180075088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007508d  mov     [rbp+arg_18], 0
0x180075095  lea     rcx, [rbp+arg_18]
0x180075099  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18007509e  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x1800750a2  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x1800750a6  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800750ab  mov     [rbp+ppstm], 0
0x1800750b3  mov     [rbp+var_20], 0
0x1800750ba  cmp     [rbp+arg_18], 0
0x1800750bf  jz      short loc_180075115
0x1800750c1  cmp     [rbp+arg_0], 0
0x1800750c6  jz      short loc_180075115
0x1800750c8  mov     rbx, [rbp+pUnk]
0x1800750cc  lea     rcx, [rbp+ppstm]
0x1800750d0  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800750d5  lea     r8, [rbp+ppstm]; ppstm
0x1800750d9  mov     edx, r12d; fDeleteOnRelease
0x1800750dc  xor     ecx, ecx; hGlobal
0x1800750de  call    cs:__imp_CreateStreamOnHGlobal
0x1800750e4  mov     [rbp+var_20], eax
0x1800750e7  test    eax, eax
0x1800750e9  js      short loc_18007511C
0x1800750eb  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x1800750f0  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x1800750f9  xor     r9d, r9d; dwDestContext
0x1800750fc  mov     r8, rbx; pUnk
0x1800750ff  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180075106  mov     rcx, [rbp+ppstm]; pStm
0x18007510a  call    cs:__imp_CoMarshalInterface
0x180075110  mov     [rbp+var_20], eax
0x180075113  jmp     short loc_18007511C
0x180075115  mov     [rbp+var_20], 80004002h
0x18007511c  mov     rcx, [rbp+arg_0]
0x180075120  mov     rax, [rcx]
0x180075123  mov     r8d, r14d
0x180075126  mov     rdx, [rbp+pUnk]
0x18007512a  mov     rax, [rax+18h]
0x18007512e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075133  mov     esi, eax
0x180075135  test    eax, eax
0x180075137  jns     short loc_180075148
0x180075139  xor     r8d, r8d
0x18007513c  xor     edx, edx
0x18007513e  mov     ecx, eax
0x180075140  call    cs:__imp_RoTransformError
0x180075146  xor     esi, esi
0x180075148  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18007514f  test    rcx, rcx
0x180075152  jz      short loc_18007516D
0x180075154  mov     rax, [rcx]
0x180075157  mov     r9d, r12d
0x18007515a  mov     r8d, 2
0x180075160  mov     edx, r12d
0x180075163  mov     rax, [rax+50h]
0x180075167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007516c  nop
0x18007516d  lea     rcx, [rbp+ppstm]
0x180075171  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x180075176  nop
0x180075177  lea     rcx, [rbp+arg_18]
0x18007517b  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075180  mov     rcx, rdi
0x180075183  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180075188  nop
0x180075189  lea     rcx, [rbp+arg_0]
0x18007518d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180075192  nop
0x180075193  lea     rcx, [rbp+pUnk]
0x180075197  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007519c  nop
0x18007519d  lea     rcx, [rbp+var_30]
0x1800751a1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800751a6  mov     eax, esi
0x1800751a8  mov     rbx, [rsp+70h+arg_8]
0x1800751b0  add     rsp, 70h
0x1800751b4  pop     r14
0x1800751b6  pop     r12
0x1800751b8  pop     rdi
0x1800751b9  pop     rsi
0x1800751ba  pop     rbp
0x1800751bb  retn
```
