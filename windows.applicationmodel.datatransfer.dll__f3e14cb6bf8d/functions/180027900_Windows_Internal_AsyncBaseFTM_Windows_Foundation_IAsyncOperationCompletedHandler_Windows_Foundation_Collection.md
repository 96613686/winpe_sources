# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180027900`
- end: `0x180027c24`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IMapView@PEAUHSTRING__@@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028f50`
- `0x180039f20`
- `0x180051168`

## callees

- `0x180027900`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027adf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180027adf`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180027b91`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180027b91`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027ab7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180027ab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::Streams::RandomAccessStreamReference *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_fc012d44_2dcf_5162_be9a_7668675aa590, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_d4cb6b80_821a_5a7b_898d_d58917b31a36,
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
0x180027900  push    rbp
0x180027902  push    rbx
0x180027903  push    rsi
0x180027904  push    rdi
0x180027905  push    r14
0x180027907  push    r15
0x180027909  mov     rbp, rsp
0x18002790c  sub     rsp, 78h
0x180027910  mov     rbx, rcx
0x180027913  xor     r14d, r14d
0x180027916  mov     esi, r14d
0x180027919  mov     [rbp+arg_0], 0FFFFFFFEh
0x180027920  mov     edx, [rcx+38h]
0x180027923  mov     eax, [rbp+arg_0]
0x180027926  lock cmpxchg [rbp+arg_0], edx
0x18002792b  lea     r15d, [r14+1]
0x18002792f  cmp     [rbp+arg_0], r14d
0x180027933  jnz     short loc_18002793D
0x180027935  xor     eax, eax
0x180027937  lock cmpxchg [rcx+38h], r15d
0x18002793d  cmp     [rcx+88h], r14d
0x180027944  jle     loc_180027C15
0x18002794a  mov     eax, r15d
0x18002794d  lock xadd [rcx+10h], eax
0x180027952  add     eax, r15d
0x180027955  cmp     eax, r15d
0x180027958  jnz     loc_180027C15
0x18002795e  mov     [rbp+var_38], rbx
0x180027962  test    rbx, rbx
0x180027965  jz      short loc_180027974
0x180027967  mov     rax, [rcx]
0x18002796a  mov     rax, [rax+8]
0x18002796e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027973  nop
0x180027974  mov     rcx, r14
0x180027977  mov     [rbp+pUnk], rcx
0x18002797b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027982  jz      short loc_1800279CF
0x180027984  mov     [rbp+arg_0], r14d
0x180027988  mov     ecx, [rbx+38h]
0x18002798b  mov     eax, [rbp+arg_0]
0x18002798e  lock cmpxchg [rbp+arg_0], ecx
0x180027993  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002799a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18002799f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800279a6  mov     rax, [rcx]
0x1800279a9  mov     r10, [rax+38h]
0x1800279ad  mov     eax, [rbp+arg_0]
0x1800279b0  mov     [rsp+78h+mshlflags], eax
0x1800279b4  mov     [rsp+78h+pvDestContext], rbx
0x1800279b9  lea     r9, [rbp+ppstm]
0x1800279bd  xor     edx, edx
0x1800279bf  lea     r8d, [rdx+2]
0x1800279c3  mov     rax, r10
0x1800279c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279cb  mov     rcx, [rbp+pUnk]
0x1800279cf  mov     rax, [rbx]
0x1800279d2  mov     rdi, [rax]
0x1800279d5  test    rcx, rcx
0x1800279d8  jz      short loc_1800279EB
0x1800279da  mov     [rbp+pUnk], r14
0x1800279de  mov     rax, [rcx]
0x1800279e1  mov     rax, [rax+10h]
0x1800279e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ea  nop
0x1800279eb  lea     r8, [rbp+pUnk]
0x1800279ef  lea     rdx, _GUID_fc012d44_2dcf_5162_be9a_7668675aa590
0x1800279f6  mov     rcx, rbx
0x1800279f9  mov     rax, rdi
0x1800279fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a01  nop
0x180027a02  test    eax, eax
0x180027a04  js      loc_180027BEB
0x180027a0a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180027a11  mov     ecx, [rbx+38h]
0x180027a14  mov     eax, [rbp+arg_0]
0x180027a17  lock cmpxchg [rbp+arg_0], ecx
0x180027a1c  mov     rcx, [rbx+78h]
0x180027a20  test    rcx, rcx
0x180027a23  jz      loc_180027BD2
0x180027a29  mov     [rbp+arg_8], r14
0x180027a2d  mov     rax, [rcx]
0x180027a30  lea     r8, [rbp+arg_8]
0x180027a34  lea     rdx, _GUID_d4cb6b80_821a_5a7b_898d_d58917b31a36
0x180027a3b  mov     rax, [rax+18h]
0x180027a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a44  nop
0x180027a45  test    eax, eax
0x180027a47  js      loc_180027BCC
0x180027a4d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027a54  test    rcx, rcx
0x180027a57  jz      short loc_180027A85
0x180027a59  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180027a60  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180027a65  mov     rax, [rcx]
0x180027a68  mov     [rsp+78h+mshlflags], r14d
0x180027a6d  mov     [rsp+78h+pvDestContext], rbx
0x180027a72  lea     r9, [rbp+var_18]
0x180027a76  xor     edx, edx
0x180027a78  lea     r8d, [rdx+2]
0x180027a7c  mov     rax, [rax+48h]
0x180027a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a85  mov     [rbp+arg_18], r14
0x180027a89  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180027a8d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180027a91  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180027a96  mov     [rbp+ppstm], r14
0x180027a9a  mov     dword ptr [rbp+ppstm+8], r14d
0x180027a9e  cmp     [rbp+arg_18], r14
0x180027aa2  jz      short loc_180027AEA
0x180027aa4  cmp     [rbp+arg_8], r14
0x180027aa8  jz      short loc_180027AEA
0x180027aaa  mov     rdi, [rbp+pUnk]
0x180027aae  lea     r8, [rbp+ppstm]; ppstm
0x180027ab2  mov     edx, r15d; fDeleteOnRelease
0x180027ab5  xor     ecx, ecx; hGlobal
0x180027ab7  call    cs:__imp_CreateStreamOnHGlobal
0x180027abd  mov     dword ptr [rbp+ppstm+8], eax
0x180027ac0  test    eax, eax
0x180027ac2  js      short loc_180027AF1
0x180027ac4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180027ac9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x180027ace  xor     r9d, r9d; dwDestContext
0x180027ad1  mov     r8, rdi; pUnk
0x180027ad4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180027adb  mov     rcx, [rbp+ppstm]; pStm
0x180027adf  call    cs:__imp_CoMarshalInterface
0x180027ae5  mov     dword ptr [rbp+ppstm+8], eax
0x180027ae8  jmp     short loc_180027AF1
0x180027aea  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180027af1  mov     rcx, [rbp+arg_8]
0x180027af5  mov     rax, [rcx]
0x180027af8  mov     r8d, [rbp+arg_0]
0x180027afc  mov     rdx, [rbp+pUnk]
0x180027b00  mov     rax, [rax+18h]
0x180027b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b09  mov     r8, [rbx+80h]
0x180027b10  mov     rdx, [rbp+arg_8]
0x180027b14  mov     ecx, eax
0x180027b16  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180027b1b  mov     esi, eax
0x180027b1d  or      ecx, 0FFFFFFFFh
0x180027b20  lock xadd [rbx+88h], ecx
0x180027b28  cmp     ecx, 1
0x180027b2b  jnz     short loc_180027B4C
0x180027b2d  lock or [rsp+78h+var_78], r14d
0x180027b32  mov     rcx, [rbx+78h]
0x180027b36  mov     [rbx+78h], r14
0x180027b3a  test    rcx, rcx
0x180027b3d  jz      short loc_180027B4C
0x180027b3f  mov     rax, [rcx]
0x180027b42  mov     rax, [rax+10h]
0x180027b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4b  nop
0x180027b4c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027b53  test    rcx, rcx
0x180027b56  jz      short loc_180027B6E
0x180027b58  mov     rax, [rcx]
0x180027b5b  xor     r9d, r9d
0x180027b5e  xor     edx, edx
0x180027b60  lea     r8d, [r9+2]
0x180027b64  mov     rax, [rax+50h]
0x180027b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b6d  nop
0x180027b6e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180027b72  jl      short loc_180027B98
0x180027b74  mov     rcx, [rbp+ppstm]
0x180027b78  mov     rdx, r14
0x180027b7b  mov     rax, [rcx]
0x180027b7e  xor     r9d, r9d
0x180027b81  xor     r8d, r8d
0x180027b84  mov     rax, [rax+28h]
0x180027b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b8d  mov     rcx, [rbp+ppstm]; pStm
0x180027b91  call    cs:__imp_CoReleaseMarshalData
0x180027b97  nop
0x180027b98  mov     rcx, [rbp+ppstm]
0x180027b9c  test    rcx, rcx
0x180027b9f  jz      short loc_180027BB2
0x180027ba1  mov     [rbp+ppstm], r14
0x180027ba5  mov     rax, [rcx]
0x180027ba8  mov     rax, [rax+10h]
0x180027bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bb1  nop
0x180027bb2  mov     rcx, [rbp+arg_18]
0x180027bb6  test    rcx, rcx
0x180027bb9  jz      short loc_180027BCC
0x180027bbb  mov     [rbp+arg_18], r14
0x180027bbf  mov     rax, [rcx]
0x180027bc2  mov     rax, [rax+10h]
0x180027bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bcb  nop
0x180027bcc  mov     rcx, [rbp+arg_8]
0x180027bd0  jmp     short loc_180027BD5
0x180027bd2  mov     rcx, r14
0x180027bd5  test    rcx, rcx
0x180027bd8  jz      short loc_180027BEB
0x180027bda  mov     [rbp+arg_8], r14
0x180027bde  mov     rax, [rcx]
0x180027be1  mov     rax, [rax+10h]
0x180027be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bea  nop
0x180027beb  mov     rcx, [rbp+pUnk]
0x180027bef  test    rcx, rcx
0x180027bf2  jz      short loc_180027C05
0x180027bf4  mov     [rbp+pUnk], r14
0x180027bf8  mov     rax, [rcx]
0x180027bfb  mov     rax, [rax+10h]
0x180027bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c04  nop
0x180027c05  mov     rax, [rbx]
0x180027c08  mov     rcx, rbx
0x180027c0b  mov     rax, [rax+10h]
0x180027c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c14  nop
0x180027c15  mov     eax, esi
0x180027c17  add     rsp, 78h
0x180027c1b  pop     r15
0x180027c1d  pop     r14
0x180027c1f  pop     rdi
0x180027c20  pop     rsi
0x180027c21  pop     rbx
0x180027c22  pop     rbp
0x180027c23  retn
```
