# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180028c20`
- end: `0x180028f44`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029190`
- `0x18003a160`
- `0x180051570`

## callees

- `0x180028c20`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180028dff`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180028dff`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028eb1`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028eb1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028dd7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028dd7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_e8d81715_c56c_5a6b_b738_5df6c2775b7b, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_2833ba54_a4e1_5c2d_8a7a_136e8510c78b,
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
0x180028c20  push    rbp
0x180028c22  push    rbx
0x180028c23  push    rsi
0x180028c24  push    rdi
0x180028c25  push    r14
0x180028c27  push    r15
0x180028c29  mov     rbp, rsp
0x180028c2c  sub     rsp, 78h
0x180028c30  mov     rbx, rcx
0x180028c33  xor     r14d, r14d
0x180028c36  mov     esi, r14d
0x180028c39  mov     [rbp+arg_0], 0FFFFFFFEh
0x180028c40  mov     edx, [rcx+38h]
0x180028c43  mov     eax, [rbp+arg_0]
0x180028c46  lock cmpxchg [rbp+arg_0], edx
0x180028c4b  lea     r15d, [r14+1]
0x180028c4f  cmp     [rbp+arg_0], r14d
0x180028c53  jnz     short loc_180028C5D
0x180028c55  xor     eax, eax
0x180028c57  lock cmpxchg [rcx+38h], r15d
0x180028c5d  cmp     [rcx+88h], r14d
0x180028c64  jle     loc_180028F35
0x180028c6a  mov     eax, r15d
0x180028c6d  lock xadd [rcx+10h], eax
0x180028c72  add     eax, r15d
0x180028c75  cmp     eax, r15d
0x180028c78  jnz     loc_180028F35
0x180028c7e  mov     [rbp+var_38], rbx
0x180028c82  test    rbx, rbx
0x180028c85  jz      short loc_180028C94
0x180028c87  mov     rax, [rcx]
0x180028c8a  mov     rax, [rax+8]
0x180028c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c93  nop
0x180028c94  mov     rcx, r14
0x180028c97  mov     [rbp+pUnk], rcx
0x180028c9b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028ca2  jz      short loc_180028CEF
0x180028ca4  mov     [rbp+arg_0], r14d
0x180028ca8  mov     ecx, [rbx+38h]
0x180028cab  mov     eax, [rbp+arg_0]
0x180028cae  lock cmpxchg [rbp+arg_0], ecx
0x180028cb3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180028cba  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x180028cbf  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028cc6  mov     rax, [rcx]
0x180028cc9  mov     r10, [rax+38h]
0x180028ccd  mov     eax, [rbp+arg_0]
0x180028cd0  mov     [rsp+78h+mshlflags], eax
0x180028cd4  mov     [rsp+78h+pvDestContext], rbx
0x180028cd9  lea     r9, [rbp+ppstm]
0x180028cdd  xor     edx, edx
0x180028cdf  lea     r8d, [rdx+2]
0x180028ce3  mov     rax, r10
0x180028ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ceb  mov     rcx, [rbp+pUnk]
0x180028cef  mov     rax, [rbx]
0x180028cf2  mov     rdi, [rax]
0x180028cf5  test    rcx, rcx
0x180028cf8  jz      short loc_180028D0B
0x180028cfa  mov     [rbp+pUnk], r14
0x180028cfe  mov     rax, [rcx]
0x180028d01  mov     rax, [rax+10h]
0x180028d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d0a  nop
0x180028d0b  lea     r8, [rbp+pUnk]
0x180028d0f  lea     rdx, _GUID_e8d81715_c56c_5a6b_b738_5df6c2775b7b
0x180028d16  mov     rcx, rbx
0x180028d19  mov     rax, rdi
0x180028d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d21  nop
0x180028d22  test    eax, eax
0x180028d24  js      loc_180028F0B
0x180028d2a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180028d31  mov     ecx, [rbx+38h]
0x180028d34  mov     eax, [rbp+arg_0]
0x180028d37  lock cmpxchg [rbp+arg_0], ecx
0x180028d3c  mov     rcx, [rbx+78h]
0x180028d40  test    rcx, rcx
0x180028d43  jz      loc_180028EF2
0x180028d49  mov     [rbp+arg_8], r14
0x180028d4d  mov     rax, [rcx]
0x180028d50  lea     r8, [rbp+arg_8]
0x180028d54  lea     rdx, _GUID_2833ba54_a4e1_5c2d_8a7a_136e8510c78b
0x180028d5b  mov     rax, [rax+18h]
0x180028d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d64  nop
0x180028d65  test    eax, eax
0x180028d67  js      loc_180028EEC
0x180028d6d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028d74  test    rcx, rcx
0x180028d77  jz      short loc_180028DA5
0x180028d79  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180028d80  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180028d85  mov     rax, [rcx]
0x180028d88  mov     [rsp+78h+mshlflags], r14d
0x180028d8d  mov     [rsp+78h+pvDestContext], rbx
0x180028d92  lea     r9, [rbp+var_18]
0x180028d96  xor     edx, edx
0x180028d98  lea     r8d, [rdx+2]
0x180028d9c  mov     rax, [rax+48h]
0x180028da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028da5  mov     [rbp+arg_18], r14
0x180028da9  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180028dad  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180028db1  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180028db6  mov     [rbp+ppstm], r14
0x180028dba  mov     dword ptr [rbp+ppstm+8], r14d
0x180028dbe  cmp     [rbp+arg_18], r14
0x180028dc2  jz      short loc_180028E0A
0x180028dc4  cmp     [rbp+arg_8], r14
0x180028dc8  jz      short loc_180028E0A
0x180028dca  mov     rdi, [rbp+pUnk]
0x180028dce  lea     r8, [rbp+ppstm]; ppstm
0x180028dd2  mov     edx, r15d; fDeleteOnRelease
0x180028dd5  xor     ecx, ecx; hGlobal
0x180028dd7  call    cs:__imp_CreateStreamOnHGlobal
0x180028ddd  mov     dword ptr [rbp+ppstm+8], eax
0x180028de0  test    eax, eax
0x180028de2  js      short loc_180028E11
0x180028de4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180028de9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x180028dee  xor     r9d, r9d; dwDestContext
0x180028df1  mov     r8, rdi; pUnk
0x180028df4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180028dfb  mov     rcx, [rbp+ppstm]; pStm
0x180028dff  call    cs:__imp_CoMarshalInterface
0x180028e05  mov     dword ptr [rbp+ppstm+8], eax
0x180028e08  jmp     short loc_180028E11
0x180028e0a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180028e11  mov     rcx, [rbp+arg_8]
0x180028e15  mov     rax, [rcx]
0x180028e18  mov     r8d, [rbp+arg_0]
0x180028e1c  mov     rdx, [rbp+pUnk]
0x180028e20  mov     rax, [rax+18h]
0x180028e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e29  mov     r8, [rbx+80h]
0x180028e30  mov     rdx, [rbp+arg_8]
0x180028e34  mov     ecx, eax
0x180028e36  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180028e3b  mov     esi, eax
0x180028e3d  or      ecx, 0FFFFFFFFh
0x180028e40  lock xadd [rbx+88h], ecx
0x180028e48  cmp     ecx, 1
0x180028e4b  jnz     short loc_180028E6C
0x180028e4d  lock or [rsp+78h+var_78], r14d
0x180028e52  mov     rcx, [rbx+78h]
0x180028e56  mov     [rbx+78h], r14
0x180028e5a  test    rcx, rcx
0x180028e5d  jz      short loc_180028E6C
0x180028e5f  mov     rax, [rcx]
0x180028e62  mov     rax, [rax+10h]
0x180028e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e6b  nop
0x180028e6c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028e73  test    rcx, rcx
0x180028e76  jz      short loc_180028E8E
0x180028e78  mov     rax, [rcx]
0x180028e7b  xor     r9d, r9d
0x180028e7e  xor     edx, edx
0x180028e80  lea     r8d, [r9+2]
0x180028e84  mov     rax, [rax+50h]
0x180028e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e8d  nop
0x180028e8e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180028e92  jl      short loc_180028EB8
0x180028e94  mov     rcx, [rbp+ppstm]
0x180028e98  mov     rdx, r14
0x180028e9b  mov     rax, [rcx]
0x180028e9e  xor     r9d, r9d
0x180028ea1  xor     r8d, r8d
0x180028ea4  mov     rax, [rax+28h]
0x180028ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ead  mov     rcx, [rbp+ppstm]; pStm
0x180028eb1  call    cs:__imp_CoReleaseMarshalData
0x180028eb7  nop
0x180028eb8  mov     rcx, [rbp+ppstm]
0x180028ebc  test    rcx, rcx
0x180028ebf  jz      short loc_180028ED2
0x180028ec1  mov     [rbp+ppstm], r14
0x180028ec5  mov     rax, [rcx]
0x180028ec8  mov     rax, [rax+10h]
0x180028ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ed1  nop
0x180028ed2  mov     rcx, [rbp+arg_18]
0x180028ed6  test    rcx, rcx
0x180028ed9  jz      short loc_180028EEC
0x180028edb  mov     [rbp+arg_18], r14
0x180028edf  mov     rax, [rcx]
0x180028ee2  mov     rax, [rax+10h]
0x180028ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eeb  nop
0x180028eec  mov     rcx, [rbp+arg_8]
0x180028ef0  jmp     short loc_180028EF5
0x180028ef2  mov     rcx, r14
0x180028ef5  test    rcx, rcx
0x180028ef8  jz      short loc_180028F0B
0x180028efa  mov     [rbp+arg_8], r14
0x180028efe  mov     rax, [rcx]
0x180028f01  mov     rax, [rax+10h]
0x180028f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f0a  nop
0x180028f0b  mov     rcx, [rbp+pUnk]
0x180028f0f  test    rcx, rcx
0x180028f12  jz      short loc_180028F25
0x180028f14  mov     [rbp+pUnk], r14
0x180028f18  mov     rax, [rcx]
0x180028f1b  mov     rax, [rax+10h]
0x180028f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f24  nop
0x180028f25  mov     rax, [rbx]
0x180028f28  mov     rcx, rbx
0x180028f2b  mov     rax, [rax+10h]
0x180028f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f34  nop
0x180028f35  mov     eax, esi
0x180028f37  add     rsp, 78h
0x180028f3b  pop     r15
0x180028f3d  pop     r14
0x180028f3f  pop     rdi
0x180028f40  pop     rsi
0x180028f41  pop     rbx
0x180028f42  pop     rbp
0x180028f43  retn
```
