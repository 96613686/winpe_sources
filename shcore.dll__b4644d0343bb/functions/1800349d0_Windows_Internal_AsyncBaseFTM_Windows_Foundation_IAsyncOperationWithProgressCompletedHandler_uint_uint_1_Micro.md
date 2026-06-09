# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800349d0`
- end: `0x180034c27`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800349a0`

## callees

- `0x18000ddd4`
- `0x18001db24`
- `0x18001db74`
- `0x18001dc88`
- `0x18001e364`
- `0x18003238c`
- `0x1800349d0`
- `0x180034c30`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180034aaf`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180034aaf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180034ada`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180034ada`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180034b36`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180034b36`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034c18`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x180034c18`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  int (__fastcall *v4)(__int64, GUID *, LPUNKNOWN *); // rbx
  __int64 v5; // rcx
  struct IUnknown *v6; // rcx
  IUnknown *v7; // rbx
  int v8; // eax
  struct IRpcOptions *v9; // rcx
  LPUNKNOWN v10; // rcx
  bool v12; // dl
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v14; // [rsp+40h] [rbp-10h]
  unsigned int v15; // [rsp+80h] [rbp+30h] BYREF
  struct IUnknown *v16; // [rsp+88h] [rbp+38h] BYREF
  LPUNKNOWN pUnk; // [rsp+90h] [rbp+40h] BYREF
  struct IRpcOptions *v18; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted();
  if ( *(int *)(v3 + 136) > 0 && _InterlockedIncrement((volatile signed __int32 *)(v3 + 16)) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v4 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pUnk);
    if ( v4(a1, &GUID_eccb574a_c684_5572_a679_6b0842cfb57f, &pUnk) >= 0 )
    {
      v15 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v15, *(_DWORD *)(a1 + 56), -2);
      v16 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v16);
      v5 = *(_QWORD *)(a1 + 120);
      if ( v5 )
      {
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_1e466dc5_840f_54f9_b877_5e3a9f4b6c74,
               &v16) >= 0 )
        {
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
          v18 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v18);
          RpcOptionsHelper::GetRpcOptions(v16, v12, &v18);
          ppstm = 0;
          v14 = 0;
          if ( v18 && v16 )
          {
            v7 = pUnk;
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppstm);
            v14 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v14 >= 0 )
              v14 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
          }
          else
          {
            v14 = -2147467262;
          }
          v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v16->lpVtbl[1].QueryInterface)(
                 v16,
                 pUnk,
                 v15);
          v2 = v8;
          if ( v8 < 0 )
          {
            RoTransformError((unsigned int)v8, 0, 0);
            v2 = 0;
          }
          Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
          if ( v14 >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
            CoReleaseMarshalData(ppstm);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppstm);
          v9 = v18;
          if ( v18 )
          {
            v18 = 0;
            ((void (__fastcall *)(struct IRpcOptions *))v9->lpVtbl->Release)(v9);
          }
        }
        v6 = v16;
      }
      else
      {
        v6 = 0;
      }
      if ( v6 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
      }
    }
    v10 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v10->lpVtbl->Release)(v10);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x1800349d0  push    rbp
0x1800349d2  push    rbx
0x1800349d3  push    rsi
0x1800349d4  push    rdi
0x1800349d5  push    r14
0x1800349d7  mov     rbp, rsp
0x1800349da  sub     rsp, 50h
0x1800349de  mov     rdi, rcx
0x1800349e1  xor     r14d, r14d
0x1800349e4  mov     esi, r14d
0x1800349e7  call    ?TryTransitionToCompleted@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NW4CancelTransitionPolicy@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(Microsoft::WRL::CancelTransitionPolicy)
0x1800349ec  cmp     [rcx+88h], r14d
0x1800349f3  jle     loc_180034BA4
0x1800349f9  lea     eax, [r14+1]
0x1800349fd  lock xadd [rcx+10h], eax
0x180034a02  inc     eax
0x180034a04  cmp     eax, 1
0x180034a07  jnz     loc_180034BA4
0x180034a0d  mov     [rbp+var_20], rcx
0x180034a11  mov     rax, [rcx]
0x180034a14  mov     rax, [rax+8]
0x180034a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a1d  nop
0x180034a1e  mov     [rbp+pUnk], r14
0x180034a22  mov     rcx, rdi
0x180034a25  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180034a2a  nop
0x180034a2b  mov     rax, [rdi]
0x180034a2e  mov     rbx, [rax]
0x180034a31  lea     rcx, [rbp+pUnk]
0x180034a35  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180034a3a  lea     r8, [rbp+pUnk]
0x180034a3e  lea     rdx, _GUID_eccb574a_c684_5572_a679_6b0842cfb57f
0x180034a45  mov     rcx, rdi
0x180034a48  mov     rax, rbx
0x180034a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a50  nop
0x180034a51  test    eax, eax
0x180034a53  js      loc_180034B7A
0x180034a59  mov     [rbp+arg_0], 0FFFFFFFEh
0x180034a60  mov     ecx, [rdi+38h]
0x180034a63  mov     eax, [rbp+arg_0]
0x180034a66  lock cmpxchg [rbp+arg_0], ecx
0x180034a6b  mov     [rbp+arg_8], r14
0x180034a6f  lea     rcx, [rbp+arg_8]
0x180034a73  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180034a78  mov     rcx, [rdi+78h]
0x180034a7c  test    rcx, rcx
0x180034a7f  jnz     loc_180034BB1
0x180034a85  mov     ecx, r14d
0x180034a88  jmp     loc_180034B64
0x180034a8d  cmp     [rbp+arg_8], r14
0x180034a91  jz      loc_180034C05
0x180034a97  mov     rbx, [rbp+pUnk]
0x180034a9b  lea     rcx, [rbp+ppstm]
0x180034a9f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180034aa4  lea     r8, [rbp+ppstm]; ppstm
0x180034aa8  mov     edx, 1; fDeleteOnRelease
0x180034aad  xor     ecx, ecx; hGlobal
0x180034aaf  call    cs:__imp_CreateStreamOnHGlobal
0x180034ab5  mov     [rbp+var_10], eax
0x180034ab8  test    eax, eax
0x180034aba  js      short loc_180034AE3
0x180034abc  mov     [rsp+50h+mshlflags], 1; mshlflags
0x180034ac4  mov     [rsp+50h+pvDestContext], r14; pvDestContext
0x180034ac9  xor     r9d, r9d; dwDestContext
0x180034acc  mov     r8, rbx; pUnk
0x180034acf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180034ad6  mov     rcx, [rbp+ppstm]; pStm
0x180034ada  call    cs:__imp_CoMarshalInterface
0x180034ae0  mov     [rbp+var_10], eax
0x180034ae3  mov     rcx, [rbp+arg_8]
0x180034ae7  mov     rax, [rcx]
0x180034aea  mov     r8d, [rbp+arg_0]
0x180034aee  mov     rdx, [rbp+pUnk]
0x180034af2  mov     rax, [rax+18h]
0x180034af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034afb  mov     esi, eax
0x180034afd  test    eax, eax
0x180034aff  js      loc_180034C11
0x180034b05  mov     rcx, rdi
0x180034b08  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180034b0d  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x180034b12  nop
0x180034b13  cmp     [rbp+var_10], r14d
0x180034b17  jl      short loc_180034B3C
0x180034b19  mov     rcx, [rbp+ppstm]
0x180034b1d  mov     rdx, r14
0x180034b20  mov     rax, [rcx]
0x180034b23  xor     r9d, r9d
0x180034b26  xor     r8d, r8d
0x180034b29  mov     rax, [rax+28h]
0x180034b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b32  mov     rcx, [rbp+ppstm]; pStm
0x180034b36  call    cs:__imp_CoReleaseMarshalData
0x180034b3c  lea     rcx, [rbp+ppstm]
0x180034b40  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180034b45  nop
0x180034b46  mov     rcx, [rbp+arg_18]
0x180034b4a  test    rcx, rcx
0x180034b4d  jz      short loc_180034B60
0x180034b4f  mov     [rbp+arg_18], r14
0x180034b53  mov     rax, [rcx]
0x180034b56  mov     rax, [rax+10h]
0x180034b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b5f  nop
0x180034b60  mov     rcx, [rbp+arg_8]
0x180034b64  test    rcx, rcx
0x180034b67  jz      short loc_180034B7A
0x180034b69  mov     [rbp+arg_8], r14
0x180034b6d  mov     rax, [rcx]
0x180034b70  mov     rax, [rax+10h]
0x180034b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b79  nop
0x180034b7a  mov     rcx, [rbp+pUnk]
0x180034b7e  test    rcx, rcx
0x180034b81  jz      short loc_180034B94
0x180034b83  mov     [rbp+pUnk], r14
0x180034b87  mov     rax, [rcx]
0x180034b8a  mov     rax, [rax+10h]
0x180034b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b93  nop
0x180034b94  mov     rcx, [rdi]
0x180034b97  mov     rax, [rcx+10h]
0x180034b9b  mov     rcx, rdi
0x180034b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ba3  nop
0x180034ba4  mov     eax, esi
0x180034ba6  add     rsp, 50h
0x180034baa  pop     r14
0x180034bac  pop     rdi
0x180034bad  pop     rsi
0x180034bae  pop     rbx
0x180034baf  pop     rbp
0x180034bb0  retn
0x180034bb1  mov     [rbp+arg_8], r14
0x180034bb5  mov     rax, [rcx]
0x180034bb8  lea     r8, [rbp+arg_8]
0x180034bbc  lea     rdx, _GUID_1e466dc5_840f_54f9_b877_5e3a9f4b6c74
0x180034bc3  mov     rax, [rax+18h]
0x180034bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bcc  nop
0x180034bcd  test    eax, eax
0x180034bcf  js      short loc_180034B60
0x180034bd1  mov     rcx, rdi
0x180034bd4  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180034bd9  mov     [rbp+arg_18], r14
0x180034bdd  lea     rcx, [rbp+arg_18]
0x180034be1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180034be6  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x180034bea  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180034bee  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180034bf3  mov     [rbp+ppstm], r14
0x180034bf7  mov     [rbp+var_10], r14d
0x180034bfb  cmp     [rbp+arg_18], r14
0x180034bff  jnz     loc_180034A8D
0x180034c05  mov     [rbp+var_10], 80004002h
0x180034c0c  jmp     loc_180034AE3
0x180034c11  xor     r8d, r8d
0x180034c14  xor     edx, edx
0x180034c16  mov     ecx, eax
0x180034c18  call    cs:__imp_RoTransformError
0x180034c1e  mov     esi, r14d
0x180034c21  jmp     loc_180034B05
```
