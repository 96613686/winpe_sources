# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180027c30`
- end: `0x180027f54`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028fb0`
- `0x180039f80`
- `0x180051214`

## callees

- `0x180027c30`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027e0f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027e0f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180027ec1`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180027ec1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027de7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027de7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        signed __int32 *a1)
{
  unsigned int v2; // esi
  LPUNKNOWN v3; // rcx
  int (__fastcall *v4)(signed __int32 *, GUID *, LPUNKNOWN *); // rdi
  __int64 v5; // rcx
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v8; // rcx
  LPSTREAM v9; // rcx
  struct IRpcOptions *v10; // rcx
  struct IUnknown *v11; // rcx
  LPUNKNOWN v12; // rcx
  signed __int32 v14[8]; // [rsp+0h] [rbp-78h] BYREF
  signed __int32 *v15; // [rsp+40h] [rbp-38h]
  LPSTREAM ppstm[2]; // [rsp+50h] [rbp-28h] BYREF
  GUID v17; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+B0h] [rbp+38h] BYREF
  struct IUnknown *v19; // [rsp+B8h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+C0h] [rbp+48h] BYREF
  struct IRpcOptions *v21; // [rsp+C8h] [rbp+50h] BYREF

  v2 = 0;
  v18 = -2;
  _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
  if ( !v18 )
    _InterlockedCompareExchange(a1 + 14, 1, 0);
  if ( a1[34] > 0 && _InterlockedIncrement(a1 + 4) == 1 )
  {
    v15 = a1;
    if ( a1 )
      (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
    v3 = 0;
    pUnk = 0;
    if ( Microsoft::WRL::gCausality )
    {
      v18 = 0;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], 0);
      *(GUID *)ppstm = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, LPSTREAM *, signed __int32 *, unsigned int))(*(_QWORD *)Microsoft::WRL::gCausality + 56LL))(
        Microsoft::WRL::gCausality,
        0,
        2,
        ppstm,
        a1,
        v18);
      v3 = pUnk;
    }
    v4 = **(int (__fastcall ***)(signed __int32 *, GUID *, LPUNKNOWN *))a1;
    if ( v3 )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v3->lpVtbl->Release)(v3);
    }
    if ( v4(a1, &GUID_4b1c0fd7_7a01_5e7a_a6fe_be4500283f23, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_51436e75_ace1_5a68_b260_f843b846f0db,
               &v19) >= 0 )
        {
          if ( Microsoft::WRL::gCausality )
          {
            v17 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, signed __int32 *, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
              Microsoft::WRL::gCausality,
              0,
              2,
              &v17,
              a1,
              0);
          }
          v21 = 0;
          RpcOptionsHelper::GetRpcOptions(v19, &v21);
          ppstm[0] = 0;
          LODWORD(ppstm[1]) = 0;
          if ( v21 && v19 )
          {
            v6 = pUnk;
            LODWORD(ppstm[1]) = CreateStreamOnHGlobal(0, 1, ppstm);
            if ( SLODWORD(ppstm[1]) >= 0 )
              LODWORD(ppstm[1]) = CoMarshalInterface(ppstm[0], &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
          }
          else
          {
            LODWORD(ppstm[1]) = -2147467262;
          }
          v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v19->lpVtbl[1].QueryInterface)(
                 v19,
                 pUnk,
                 v18);
          v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
                 v7,
                 v19,
                 *((_QWORD *)a1 + 16));
          if ( _InterlockedExchangeAdd(a1 + 34, 0xFFFFFFFF) == 1 )
          {
            _InterlockedOr(v14, 0);
            v8 = *((_QWORD *)a1 + 15);
            *((_QWORD *)a1 + 15) = 0;
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          if ( Microsoft::WRL::gCausality )
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
              Microsoft::WRL::gCausality,
              0,
              2);
          if ( SLODWORD(ppstm[1]) >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm[0] + 40LL))(ppstm[0], 0, 0, 0);
            CoReleaseMarshalData(ppstm[0]);
          }
          v9 = ppstm[0];
          if ( ppstm[0] )
          {
            ppstm[0] = 0;
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v9 + 16LL))(v9);
          }
          v10 = v21;
          if ( v21 )
          {
            v21 = 0;
            ((void (__fastcall *)(struct IRpcOptions *))v10->lpVtbl->Release)(v10);
          }
        }
        v11 = v19;
      }
      else
      {
        v11 = 0;
      }
      if ( v11 )
      {
        v19 = 0;
        ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
      }
    }
    v12 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
    }
    (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180027c30  push    rbp
0x180027c32  push    rbx
0x180027c33  push    rsi
0x180027c34  push    rdi
0x180027c35  push    r14
0x180027c37  push    r15
0x180027c39  mov     rbp, rsp
0x180027c3c  sub     rsp, 78h
0x180027c40  mov     rbx, rcx
0x180027c43  xor     r14d, r14d
0x180027c46  mov     esi, r14d
0x180027c49  mov     [rbp+arg_0], 0FFFFFFFEh
0x180027c50  mov     edx, [rcx+38h]
0x180027c53  mov     eax, [rbp+arg_0]
0x180027c56  lock cmpxchg [rbp+arg_0], edx
0x180027c5b  lea     r15d, [r14+1]
0x180027c5f  cmp     [rbp+arg_0], r14d
0x180027c63  jnz     short loc_180027C6D
0x180027c65  xor     eax, eax
0x180027c67  lock cmpxchg [rcx+38h], r15d
0x180027c6d  cmp     [rcx+88h], r14d
0x180027c74  jle     loc_180027F45
0x180027c7a  mov     eax, r15d
0x180027c7d  lock xadd [rcx+10h], eax
0x180027c82  add     eax, r15d
0x180027c85  cmp     eax, r15d
0x180027c88  jnz     loc_180027F45
0x180027c8e  mov     [rbp+var_38], rbx
0x180027c92  test    rbx, rbx
0x180027c95  jz      short loc_180027CA4
0x180027c97  mov     rax, [rcx]
0x180027c9a  mov     rax, [rax+8]
0x180027c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca3  nop
0x180027ca4  mov     rcx, r14
0x180027ca7  mov     [rbp+pUnk], rcx
0x180027cab  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027cb2  jz      short loc_180027CFF
0x180027cb4  mov     [rbp+arg_0], r14d
0x180027cb8  mov     ecx, [rbx+38h]
0x180027cbb  mov     eax, [rbp+arg_0]
0x180027cbe  lock cmpxchg [rbp+arg_0], ecx
0x180027cc3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180027cca  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x180027ccf  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027cd6  mov     rax, [rcx]
0x180027cd9  mov     r10, [rax+38h]
0x180027cdd  mov     eax, [rbp+arg_0]
0x180027ce0  mov     [rsp+78h+mshlflags], eax
0x180027ce4  mov     [rsp+78h+pvDestContext], rbx
0x180027ce9  lea     r9, [rbp+ppstm]
0x180027ced  xor     edx, edx
0x180027cef  lea     r8d, [rdx+2]
0x180027cf3  mov     rax, r10
0x180027cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cfb  mov     rcx, [rbp+pUnk]
0x180027cff  mov     rax, [rbx]
0x180027d02  mov     rdi, [rax]
0x180027d05  test    rcx, rcx
0x180027d08  jz      short loc_180027D1B
0x180027d0a  mov     [rbp+pUnk], r14
0x180027d0e  mov     rax, [rcx]
0x180027d11  mov     rax, [rax+10h]
0x180027d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d1a  nop
0x180027d1b  lea     r8, [rbp+pUnk]
0x180027d1f  lea     rdx, _GUID_4b1c0fd7_7a01_5e7a_a6fe_be4500283f23
0x180027d26  mov     rcx, rbx
0x180027d29  mov     rax, rdi
0x180027d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d31  nop
0x180027d32  test    eax, eax
0x180027d34  js      loc_180027F1B
0x180027d3a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180027d41  mov     ecx, [rbx+38h]
0x180027d44  mov     eax, [rbp+arg_0]
0x180027d47  lock cmpxchg [rbp+arg_0], ecx
0x180027d4c  mov     rcx, [rbx+78h]
0x180027d50  test    rcx, rcx
0x180027d53  jz      loc_180027F02
0x180027d59  mov     [rbp+arg_8], r14
0x180027d5d  mov     rax, [rcx]
0x180027d60  lea     r8, [rbp+arg_8]
0x180027d64  lea     rdx, _GUID_51436e75_ace1_5a68_b260_f843b846f0db
0x180027d6b  mov     rax, [rax+18h]
0x180027d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d74  nop
0x180027d75  test    eax, eax
0x180027d77  js      loc_180027EFC
0x180027d7d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027d84  test    rcx, rcx
0x180027d87  jz      short loc_180027DB5
0x180027d89  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180027d90  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180027d95  mov     rax, [rcx]
0x180027d98  mov     [rsp+78h+mshlflags], r14d
0x180027d9d  mov     [rsp+78h+pvDestContext], rbx
0x180027da2  lea     r9, [rbp+var_18]
0x180027da6  xor     edx, edx
0x180027da8  lea     r8d, [rdx+2]
0x180027dac  mov     rax, [rax+48h]
0x180027db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027db5  mov     [rbp+arg_18], r14
0x180027db9  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180027dbd  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180027dc1  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180027dc6  mov     [rbp+ppstm], r14
0x180027dca  mov     dword ptr [rbp+ppstm+8], r14d
0x180027dce  cmp     [rbp+arg_18], r14
0x180027dd2  jz      short loc_180027E1A
0x180027dd4  cmp     [rbp+arg_8], r14
0x180027dd8  jz      short loc_180027E1A
0x180027dda  mov     rdi, [rbp+pUnk]
0x180027dde  lea     r8, [rbp+ppstm]; ppstm
0x180027de2  mov     edx, r15d; fDeleteOnRelease
0x180027de5  xor     ecx, ecx; hGlobal
0x180027de7  call    cs:__imp_CreateStreamOnHGlobal
0x180027ded  mov     dword ptr [rbp+ppstm+8], eax
0x180027df0  test    eax, eax
0x180027df2  js      short loc_180027E21
0x180027df4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180027df9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x180027dfe  xor     r9d, r9d; dwDestContext
0x180027e01  mov     r8, rdi; pUnk
0x180027e04  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180027e0b  mov     rcx, [rbp+ppstm]; pStm
0x180027e0f  call    cs:__imp_CoMarshalInterface
0x180027e15  mov     dword ptr [rbp+ppstm+8], eax
0x180027e18  jmp     short loc_180027E21
0x180027e1a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180027e21  mov     rcx, [rbp+arg_8]
0x180027e25  mov     rax, [rcx]
0x180027e28  mov     r8d, [rbp+arg_0]
0x180027e2c  mov     rdx, [rbp+pUnk]
0x180027e30  mov     rax, [rax+18h]
0x180027e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e39  mov     r8, [rbx+80h]
0x180027e40  mov     rdx, [rbp+arg_8]
0x180027e44  mov     ecx, eax
0x180027e46  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180027e4b  mov     esi, eax
0x180027e4d  or      ecx, 0FFFFFFFFh
0x180027e50  lock xadd [rbx+88h], ecx
0x180027e58  cmp     ecx, 1
0x180027e5b  jnz     short loc_180027E7C
0x180027e5d  lock or [rsp+78h+var_78], r14d
0x180027e62  mov     rcx, [rbx+78h]
0x180027e66  mov     [rbx+78h], r14
0x180027e6a  test    rcx, rcx
0x180027e6d  jz      short loc_180027E7C
0x180027e6f  mov     rax, [rcx]
0x180027e72  mov     rax, [rax+10h]
0x180027e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e7b  nop
0x180027e7c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027e83  test    rcx, rcx
0x180027e86  jz      short loc_180027E9E
0x180027e88  mov     rax, [rcx]
0x180027e8b  xor     r9d, r9d
0x180027e8e  xor     edx, edx
0x180027e90  lea     r8d, [r9+2]
0x180027e94  mov     rax, [rax+50h]
0x180027e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e9d  nop
0x180027e9e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180027ea2  jl      short loc_180027EC8
0x180027ea4  mov     rcx, [rbp+ppstm]
0x180027ea8  mov     rdx, r14
0x180027eab  mov     rax, [rcx]
0x180027eae  xor     r9d, r9d
0x180027eb1  xor     r8d, r8d
0x180027eb4  mov     rax, [rax+28h]
0x180027eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ebd  mov     rcx, [rbp+ppstm]; pStm
0x180027ec1  call    cs:__imp_CoReleaseMarshalData
0x180027ec7  nop
0x180027ec8  mov     rcx, [rbp+ppstm]
0x180027ecc  test    rcx, rcx
0x180027ecf  jz      short loc_180027EE2
0x180027ed1  mov     [rbp+ppstm], r14
0x180027ed5  mov     rax, [rcx]
0x180027ed8  mov     rax, [rax+10h]
0x180027edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ee1  nop
0x180027ee2  mov     rcx, [rbp+arg_18]
0x180027ee6  test    rcx, rcx
0x180027ee9  jz      short loc_180027EFC
0x180027eeb  mov     [rbp+arg_18], r14
0x180027eef  mov     rax, [rcx]
0x180027ef2  mov     rax, [rax+10h]
0x180027ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027efb  nop
0x180027efc  mov     rcx, [rbp+arg_8]
0x180027f00  jmp     short loc_180027F05
0x180027f02  mov     rcx, r14
0x180027f05  test    rcx, rcx
0x180027f08  jz      short loc_180027F1B
0x180027f0a  mov     [rbp+arg_8], r14
0x180027f0e  mov     rax, [rcx]
0x180027f11  mov     rax, [rax+10h]
0x180027f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f1a  nop
0x180027f1b  mov     rcx, [rbp+pUnk]
0x180027f1f  test    rcx, rcx
0x180027f22  jz      short loc_180027F35
0x180027f24  mov     [rbp+pUnk], r14
0x180027f28  mov     rax, [rcx]
0x180027f2b  mov     rax, [rax+10h]
0x180027f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f34  nop
0x180027f35  mov     rax, [rbx]
0x180027f38  mov     rcx, rbx
0x180027f3b  mov     rax, [rax+10h]
0x180027f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f44  nop
0x180027f45  mov     eax, esi
0x180027f47  add     rsp, 78h
0x180027f4b  pop     r15
0x180027f4d  pop     r14
0x180027f4f  pop     rdi
0x180027f50  pop     rsi
0x180027f51  pop     rbx
0x180027f52  pop     rbp
0x180027f53  retn
```
