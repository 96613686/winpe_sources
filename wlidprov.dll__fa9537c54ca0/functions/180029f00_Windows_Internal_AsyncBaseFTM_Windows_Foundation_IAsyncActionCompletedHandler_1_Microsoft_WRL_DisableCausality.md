# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::FireCompletion(void)

- ea: `0x180029f00`
- end: `0x18002a086`
- name: `?FireCompletion@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a090`

## callees

- `0x1800272c8`
- `0x18002826c`
- `0x180029aa8`
- `0x180029f00`
- `0x18002a100`
- `0x18002a908`
- `0x18002ae44`
- `0x18002ae68`
- `0x18002f1cc`
- `0x18002f2d4`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002a004`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002a004`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180029fd5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180029fd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    pUnk = 0;
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncAction>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncActionCompletedHandler>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        v14 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::UnlockCompleteDelegate(a1);
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x180029f00  push    rbp
0x180029f02  push    rbx
0x180029f03  push    rdi
0x180029f04  mov     rbp, rsp
0x180029f07  sub     rsp, 50h
0x180029f0b  mov     rbx, rcx
0x180029f0e  xor     edi, edi
0x180029f10  lea     edx, [rdi+1]
0x180029f13  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00UDisableCausality@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180029f18  cmp     [rbx+88h], edi
0x180029f1e  jle     loc_18002A07C
0x180029f24  mov     eax, edx
0x180029f26  lock xadd [rbx+10h], eax
0x180029f2b  inc     eax
0x180029f2d  cmp     eax, edx
0x180029f2f  jnz     loc_18002A07C
0x180029f35  mov     [rbp+var_20], rbx
0x180029f39  lea     rcx, [rbp+var_20]
0x180029f3d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180029f42  nop
0x180029f43  mov     [rbp+pUnk], rdi
0x180029f47  lea     rdx, [rbp+pUnk]
0x180029f4b  lea     rcx, [rbp+var_20]
0x180029f4f  call    ??$As@UIAsyncAction@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncAction>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>>)
0x180029f54  test    eax, eax
0x180029f56  js      loc_18002A069
0x180029f5c  mov     [rbp+arg_0], 0FFFFFFFEh
0x180029f63  mov     ecx, [rbx+38h]
0x180029f66  mov     eax, [rbp+arg_0]
0x180029f69  lock cmpxchg [rbp+arg_0], ecx
0x180029f6e  mov     [rbp+arg_8], rdi
0x180029f72  lea     rcx, [rbp+arg_8]
0x180029f76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029f7b  lea     rcx, [rbx+78h]
0x180029f7f  lea     r8, [rbp+arg_8]
0x180029f83  call    ?CopyLocal@?$GitPtrSupportsAgile@UIAsyncActionCompletedHandler@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncActionCompletedHandler>::CopyLocal(_GUID const &,void * *)
0x180029f88  test    eax, eax
0x180029f8a  js      loc_18002A05F
0x180029f90  mov     [rbp+arg_10], rdi
0x180029f94  lea     rcx, [rbp+arg_10]
0x180029f98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029f9d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180029fa1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180029fa5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180029faa  mov     [rbp+ppstm], rdi
0x180029fae  mov     [rbp+var_10], edi
0x180029fb1  cmp     [rbp+arg_10], rdi
0x180029fb5  jz      short loc_18002A00F
0x180029fb7  cmp     [rbp+arg_8], rdi
0x180029fbb  jz      short loc_18002A00F
0x180029fbd  mov     rdi, [rbp+pUnk]
0x180029fc1  lea     rcx, [rbp+ppstm]
0x180029fc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029fca  lea     r8, [rbp+ppstm]; ppstm
0x180029fce  mov     edx, 1; fDeleteOnRelease
0x180029fd3  xor     ecx, ecx; hGlobal
0x180029fd5  call    cs:__imp_CreateStreamOnHGlobal
0x180029fdb  mov     [rbp+var_10], eax
0x180029fde  test    eax, eax
0x180029fe0  js      short loc_18002A016
0x180029fe2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x180029fea  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180029ff3  xor     r9d, r9d; dwDestContext
0x180029ff6  mov     r8, rdi; pUnk
0x180029ff9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002a000  mov     rcx, [rbp+ppstm]; pStm
0x18002a004  call    cs:__imp_CoMarshalInterface
0x18002a00a  mov     [rbp+var_10], eax
0x18002a00d  jmp     short loc_18002A016
0x18002a00f  mov     [rbp+var_10], 80004002h
0x18002a016  mov     rcx, [rbp+arg_8]
0x18002a01a  mov     rax, [rcx]
0x18002a01d  mov     r8d, [rbp+arg_0]
0x18002a021  mov     rdx, [rbp+pUnk]
0x18002a025  mov     rax, [rax+18h]
0x18002a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a02e  mov     r8, [rbx+80h]
0x18002a035  mov     rdx, [rbp+arg_8]
0x18002a039  mov     ecx, eax
0x18002a03b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002a040  mov     edi, eax
0x18002a042  mov     rcx, rbx
0x18002a045  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::DisableCausality>::UnlockCompleteDelegate(void)
0x18002a04a  nop
0x18002a04b  lea     rcx, [rbp+ppstm]
0x18002a04f  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x18002a054  nop
0x18002a055  lea     rcx, [rbp+arg_10]
0x18002a059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a05e  nop
0x18002a05f  lea     rcx, [rbp+arg_8]
0x18002a063  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a068  nop
0x18002a069  lea     rcx, [rbp+pUnk]
0x18002a06d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a072  nop
0x18002a073  lea     rcx, [rbp+var_20]
0x18002a077  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a07c  mov     eax, edi
0x18002a07e  add     rsp, 50h
0x18002a082  pop     rdi
0x18002a083  pop     rbx
0x18002a084  pop     rbp
0x18002a085  retn
```
