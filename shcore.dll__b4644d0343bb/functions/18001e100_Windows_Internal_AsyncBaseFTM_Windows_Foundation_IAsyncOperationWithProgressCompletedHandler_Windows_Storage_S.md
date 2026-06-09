# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18001e100`
- end: `0x18001e35c`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e0d0`

## callees

- `0x18000ddd4`
- `0x18001db24`
- `0x18001db74`
- `0x18001dc58`
- `0x18001dc88`
- `0x18001e100`
- `0x18001e364`
- `0x18001e39c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001e309`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001e309`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001e338`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001e338`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001e267`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18001e267`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18001e34d`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18001e34d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  int (__fastcall *v4)(__int64, GUID *, LPUNKNOWN *); // rbx
  __int64 v5; // rcx
  bool v6; // dl
  int v7; // eax
  struct IRpcOptions *v8; // rcx
  struct IUnknown *v9; // rcx
  LPUNKNOWN v10; // rcx
  IUnknown *v12; // rbx
  LPSTREAM pStm; // [rsp+38h] [rbp-18h] BYREF
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
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v4 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pUnk);
    if ( v4(a1, &GUID_d26b2819_897f_5c7d_84d6_56d796561431, &pUnk) >= 0 )
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
               &GUID_06386a7a_e009_5b0b_ab68_a8e48b516647,
               &v16) >= 0 )
        {
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
          v18 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v18);
          RpcOptionsHelper::GetRpcOptions(v16, v6, &v18);
          pStm = 0;
          v14 = 0;
          if ( v18 && v16 )
          {
            v12 = pUnk;
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pStm);
            v14 = CreateStreamOnHGlobal(0, 1, &pStm);
            if ( v14 >= 0 )
              v14 = CoMarshalInterface(pStm, &GUID_00000000_0000_0000_c000_000000000046, v12, 0, 0, 1u);
          }
          else
          {
            v14 = -2147467262;
          }
          v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v16->lpVtbl[1].QueryInterface)(
                 v16,
                 pUnk,
                 v15);
          v2 = v7;
          if ( v7 < 0 )
          {
            RoTransformError((unsigned int)v7, 0, 0);
            v2 = 0;
          }
          Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
          if ( v14 >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)pStm + 40LL))(pStm, 0, 0, 0);
            CoReleaseMarshalData(pStm);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&pStm);
          v8 = v18;
          if ( v18 )
          {
            v18 = 0;
            ((void (__fastcall *)(struct IRpcOptions *))v8->lpVtbl->Release)(v8);
          }
        }
        v9 = v16;
      }
      else
      {
        v9 = 0;
      }
      if ( v9 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
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
0x18001e100  push    rbp
0x18001e102  push    rbx
0x18001e103  push    rsi
0x18001e104  push    rdi
0x18001e105  push    r14
0x18001e107  mov     rbp, rsp
0x18001e10a  sub     rsp, 50h
0x18001e10e  mov     rdi, rcx
0x18001e111  xor     r14d, r14d
0x18001e114  mov     esi, r14d
0x18001e117  call    ?TryTransitionToCompleted@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NW4CancelTransitionPolicy@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(Microsoft::WRL::CancelTransitionPolicy)
0x18001e11c  cmp     [rcx+88h], r14d
0x18001e123  jle     loc_18001E2D5
0x18001e129  lea     eax, [r14+1]
0x18001e12d  lock xadd [rcx+10h], eax
0x18001e132  inc     eax
0x18001e134  cmp     eax, 1
0x18001e137  jnz     loc_18001E2D5
0x18001e13d  mov     [rbp+var_20], rcx
0x18001e141  mov     rax, [rcx]
0x18001e144  mov     rax, [rax+8]
0x18001e148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e14d  nop
0x18001e14e  mov     [rbp+pUnk], r14
0x18001e152  mov     rcx, rdi
0x18001e155  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18001e15a  nop
0x18001e15b  mov     rax, [rdi]
0x18001e15e  mov     rbx, [rax]
0x18001e161  lea     rcx, [rbp+pUnk]
0x18001e165  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18001e16a  lea     r8, [rbp+pUnk]
0x18001e16e  lea     rdx, _GUID_d26b2819_897f_5c7d_84d6_56d796561431
0x18001e175  mov     rcx, rdi
0x18001e178  mov     rax, rbx
0x18001e17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e180  nop
0x18001e181  test    eax, eax
0x18001e183  js      loc_18001E2AB
0x18001e189  mov     [rbp+arg_0], 0FFFFFFFEh
0x18001e190  mov     ecx, [rdi+38h]
0x18001e193  mov     eax, [rbp+arg_0]
0x18001e196  lock cmpxchg [rbp+arg_0], ecx
0x18001e19b  mov     [rbp+arg_8], r14
0x18001e19f  lea     rcx, [rbp+arg_8]
0x18001e1a3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18001e1a8  mov     rcx, [rdi+78h]
0x18001e1ac  test    rcx, rcx
0x18001e1af  jz      loc_18001E2E2
0x18001e1b5  mov     [rbp+arg_8], r14
0x18001e1b9  mov     rax, [rcx]
0x18001e1bc  lea     r8, [rbp+arg_8]
0x18001e1c0  lea     rdx, _GUID_06386a7a_e009_5b0b_ab68_a8e48b516647
0x18001e1c7  mov     rax, [rax+18h]
0x18001e1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d0  nop
0x18001e1d1  test    eax, eax
0x18001e1d3  js      loc_18001E291
0x18001e1d9  mov     rcx, rdi
0x18001e1dc  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18001e1e1  mov     [rbp+arg_18], r14
0x18001e1e5  lea     rcx, [rbp+arg_18]
0x18001e1e9  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18001e1ee  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x18001e1f2  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18001e1f6  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18001e1fb  mov     [rbp+pStm], r14
0x18001e1ff  mov     [rbp+var_10], r14d
0x18001e203  cmp     [rbp+arg_18], r14
0x18001e207  jnz     loc_18001E2E7
0x18001e20d  mov     [rbp+var_10], 80004002h
0x18001e214  mov     rcx, [rbp+arg_8]
0x18001e218  mov     rax, [rcx]
0x18001e21b  mov     r8d, [rbp+arg_0]
0x18001e21f  mov     rdx, [rbp+pUnk]
0x18001e223  mov     rax, [rax+18h]
0x18001e227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e22c  mov     esi, eax
0x18001e22e  test    eax, eax
0x18001e230  js      loc_18001E346
0x18001e236  mov     rcx, rdi
0x18001e239  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18001e23e  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$01$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<2,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18001e243  nop
0x18001e244  cmp     [rbp+var_10], r14d
0x18001e248  jl      short loc_18001E26D
0x18001e24a  mov     rcx, [rbp+pStm]
0x18001e24e  mov     rdx, r14
0x18001e251  mov     rax, [rcx]
0x18001e254  xor     r9d, r9d
0x18001e257  xor     r8d, r8d
0x18001e25a  mov     rax, [rax+28h]
0x18001e25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e263  mov     rcx, [rbp+pStm]; pStm
0x18001e267  call    cs:__imp_CoReleaseMarshalData
0x18001e26d  lea     rcx, [rbp+pStm]
0x18001e271  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18001e276  nop
0x18001e277  mov     rcx, [rbp+arg_18]
0x18001e27b  test    rcx, rcx
0x18001e27e  jz      short loc_18001E291
0x18001e280  mov     [rbp+arg_18], r14
0x18001e284  mov     rax, [rcx]
0x18001e287  mov     rax, [rax+10h]
0x18001e28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e290  nop
0x18001e291  mov     rcx, [rbp+arg_8]
0x18001e295  test    rcx, rcx
0x18001e298  jz      short loc_18001E2AB
0x18001e29a  mov     [rbp+arg_8], r14
0x18001e29e  mov     rax, [rcx]
0x18001e2a1  mov     rax, [rax+10h]
0x18001e2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2aa  nop
0x18001e2ab  mov     rcx, [rbp+pUnk]
0x18001e2af  test    rcx, rcx
0x18001e2b2  jz      short loc_18001E2C5
0x18001e2b4  mov     [rbp+pUnk], r14
0x18001e2b8  mov     rax, [rcx]
0x18001e2bb  mov     rax, [rax+10h]
0x18001e2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c4  nop
0x18001e2c5  mov     rcx, [rdi]
0x18001e2c8  mov     rax, [rcx+10h]
0x18001e2cc  mov     rcx, rdi
0x18001e2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2d4  nop
0x18001e2d5  mov     eax, esi
0x18001e2d7  add     rsp, 50h
0x18001e2db  pop     r14
0x18001e2dd  pop     rdi
0x18001e2de  pop     rsi
0x18001e2df  pop     rbx
0x18001e2e0  pop     rbp
0x18001e2e1  retn
0x18001e2e2  mov     rcx, r14
0x18001e2e5  jmp     short loc_18001E295
0x18001e2e7  cmp     [rbp+arg_8], r14
0x18001e2eb  jz      loc_18001E20D
0x18001e2f1  mov     rbx, [rbp+pUnk]
0x18001e2f5  lea     rcx, [rbp+pStm]
0x18001e2f9  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18001e2fe  lea     r8, [rbp+pStm]; ppstm
0x18001e302  mov     edx, 1; fDeleteOnRelease
0x18001e307  xor     ecx, ecx; hGlobal
0x18001e309  call    cs:__imp_CreateStreamOnHGlobal
0x18001e30f  mov     [rbp+var_10], eax
0x18001e312  test    eax, eax
0x18001e314  js      loc_18001E214
0x18001e31a  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18001e322  mov     [rsp+50h+pvDestContext], r14; pvDestContext
0x18001e327  xor     r9d, r9d; dwDestContext
0x18001e32a  mov     r8, rbx; pUnk
0x18001e32d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001e334  mov     rcx, [rbp+pStm]; pStm
0x18001e338  call    cs:__imp_CoMarshalInterface
0x18001e33e  mov     [rbp+var_10], eax
0x18001e341  jmp     loc_18001E214
0x18001e346  xor     r8d, r8d
0x18001e349  xor     edx, edx
0x18001e34b  mov     ecx, eax
0x18001e34d  call    cs:__imp_RoTransformError
0x18001e353  mov     esi, r14d
0x18001e356  jmp     loc_18001E236
```
