# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::FireProgress(int)

- ea: `0x18002a1dc`
- end: `0x18002a35c`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002dd20`

## callees

- `0x18002826c`
- `0x180029af0`
- `0x18002a100`
- `0x18002a1dc`
- `0x18002a908`
- `0x18002ae44`
- `0x18002ae68`
- `0x18002f234`
- `0x18002f320`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002a2d9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002a2d9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a2ae`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a2ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // esi
  int (__fastcall *v5)(__int64, GUID *, LPUNKNOWN *); // rbx
  __int64 v6; // rdx
  bool v7; // dl
  IUnknown *v8; // rbx
  unsigned int v9; // eax
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v13; // [rsp+40h] [rbp-10h]
  struct IUnknown *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+90h] [rbp+40h] BYREF
  struct IRpcOptions *v16; // [rsp+98h] [rbp+48h] BYREF

  v4 = 0;
  v11 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v11);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::TryLockProgressDelegate(a1) )
  {
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v14 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(a1 + 144, v6, &v14) >= 0 )
      {
        v16 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        RpcOptionsHelper::GetRpcOptions(v14, v7, &v16);
        ppstm = 0;
        v13 = 0;
        if ( v16 && v14 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v13 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v13 >= 0 )
            v13 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v8, 0, 0, 1u);
        }
        else
        {
          v13 = -2147467262;
        }
        v9 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               pUnk,
               a2);
        v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v9,
               v14,
               *(_QWORD *)(a1 + 152));
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  return v4;
}

```

## disassembly

```asm
0x18002a1dc  push    rbp
0x18002a1de  push    rbx
0x18002a1df  push    rsi
0x18002a1e0  push    rdi
0x18002a1e1  push    r14
0x18002a1e3  mov     rbp, rsp
0x18002a1e6  sub     rsp, 50h
0x18002a1ea  mov     r14d, edx
0x18002a1ed  mov     rdi, rcx
0x18002a1f0  xor     esi, esi
0x18002a1f2  mov     [rbp+var_20], rcx
0x18002a1f6  lea     rcx, [rbp+var_20]
0x18002a1fa  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002a1ff  nop
0x18002a200  mov     [rbp+pUnk], rsi
0x18002a204  mov     rcx, rdi
0x18002a207  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::TryLockProgressDelegate(void)
0x18002a20c  test    al, al
0x18002a20e  jz      loc_18002A33C
0x18002a214  mov     rax, [rdi]
0x18002a217  mov     rbx, [rax]
0x18002a21a  lea     rcx, [rbp+pUnk]
0x18002a21e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a223  lea     r8, [rbp+pUnk]
0x18002a227  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002a22e  mov     rcx, rdi
0x18002a231  mov     rax, rbx
0x18002a234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a239  nop
0x18002a23a  test    eax, eax
0x18002a23c  js      loc_18002A33C
0x18002a242  mov     [rbp+arg_0], rsi
0x18002a246  lea     rcx, [rbp+arg_0]
0x18002a24a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a24f  lea     rcx, [rdi+90h]
0x18002a256  lea     r8, [rbp+arg_0]
0x18002a25a  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x18002a25f  test    eax, eax
0x18002a261  js      loc_18002A329
0x18002a267  mov     [rbp+arg_18], rsi
0x18002a26b  lea     rcx, [rbp+arg_18]
0x18002a26f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a274  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x18002a278  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002a27c  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002a281  mov     [rbp+ppstm], rsi
0x18002a285  mov     [rbp+var_10], esi
0x18002a288  cmp     [rbp+arg_18], rsi
0x18002a28c  jz      short loc_18002A2E4
0x18002a28e  cmp     [rbp+arg_0], rsi
0x18002a292  jz      short loc_18002A2E4
0x18002a294  mov     rbx, [rbp+pUnk]
0x18002a298  lea     rcx, [rbp+ppstm]
0x18002a29c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a2a1  lea     r8, [rbp+ppstm]; ppstm
0x18002a2a5  mov     esi, 1
0x18002a2aa  mov     edx, esi; fDeleteOnRelease
0x18002a2ac  xor     ecx, ecx; hGlobal
0x18002a2ae  call    cs:__imp_CreateStreamOnHGlobal
0x18002a2b4  mov     [rbp+var_10], eax
0x18002a2b7  test    eax, eax
0x18002a2b9  js      short loc_18002A2EB
0x18002a2bb  mov     [rsp+50h+mshlflags], esi; mshlflags
0x18002a2bf  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002a2c8  xor     r9d, r9d; dwDestContext
0x18002a2cb  mov     r8, rbx; pUnk
0x18002a2ce  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002a2d5  mov     rcx, [rbp+ppstm]; pStm
0x18002a2d9  call    cs:__imp_CoMarshalInterface
0x18002a2df  mov     [rbp+var_10], eax
0x18002a2e2  jmp     short loc_18002A2EB
0x18002a2e4  mov     [rbp+var_10], 80004002h
0x18002a2eb  mov     rcx, [rbp+arg_0]
0x18002a2ef  mov     rax, [rcx]
0x18002a2f2  mov     r8d, r14d
0x18002a2f5  mov     rdx, [rbp+pUnk]
0x18002a2f9  mov     rax, [rax+18h]
0x18002a2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a302  mov     r8, [rdi+98h]
0x18002a309  mov     rdx, [rbp+arg_0]
0x18002a30d  mov     ecx, eax
0x18002a30f  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002a314  mov     esi, eax
0x18002a316  lea     rcx, [rbp+ppstm]
0x18002a31a  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x18002a31f  nop
0x18002a320  lea     rcx, [rbp+arg_18]
0x18002a324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a329  mov     rcx, rdi
0x18002a32c  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00UDisableCausality@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::DisableCausality>::UnlockProgressDelegate(void)
0x18002a331  nop
0x18002a332  lea     rcx, [rbp+arg_0]
0x18002a336  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a33b  nop
0x18002a33c  lea     rcx, [rbp+pUnk]
0x18002a340  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a345  nop
0x18002a346  lea     rcx, [rbp+var_20]
0x18002a34a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002a34f  mov     eax, esi
0x18002a351  add     rsp, 50h
0x18002a355  pop     r14
0x18002a357  pop     rdi
0x18002a358  pop     rsi
0x18002a359  pop     rbx
0x18002a35a  pop     rbp
0x18002a35b  retn
```
