# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180027f60`
- end: `0x180028284`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029010`
- `0x180039fe0`
- `0x1800512c0`

## callees

- `0x180027f60`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002813f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002813f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800281f1`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800281f1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028117`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028117`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_3e1fe603_f897_5263_b328_0806426b8a79, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41,
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
0x180027f60  push    rbp
0x180027f62  push    rbx
0x180027f63  push    rsi
0x180027f64  push    rdi
0x180027f65  push    r14
0x180027f67  push    r15
0x180027f69  mov     rbp, rsp
0x180027f6c  sub     rsp, 78h
0x180027f70  mov     rbx, rcx
0x180027f73  xor     r14d, r14d
0x180027f76  mov     esi, r14d
0x180027f79  mov     [rbp+arg_0], 0FFFFFFFEh
0x180027f80  mov     edx, [rcx+38h]
0x180027f83  mov     eax, [rbp+arg_0]
0x180027f86  lock cmpxchg [rbp+arg_0], edx
0x180027f8b  lea     r15d, [r14+1]
0x180027f8f  cmp     [rbp+arg_0], r14d
0x180027f93  jnz     short loc_180027F9D
0x180027f95  xor     eax, eax
0x180027f97  lock cmpxchg [rcx+38h], r15d
0x180027f9d  cmp     [rcx+88h], r14d
0x180027fa4  jle     loc_180028275
0x180027faa  mov     eax, r15d
0x180027fad  lock xadd [rcx+10h], eax
0x180027fb2  add     eax, r15d
0x180027fb5  cmp     eax, r15d
0x180027fb8  jnz     loc_180028275
0x180027fbe  mov     [rbp+var_38], rbx
0x180027fc2  test    rbx, rbx
0x180027fc5  jz      short loc_180027FD4
0x180027fc7  mov     rax, [rcx]
0x180027fca  mov     rax, [rax+8]
0x180027fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fd3  nop
0x180027fd4  mov     rcx, r14
0x180027fd7  mov     [rbp+pUnk], rcx
0x180027fdb  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180027fe2  jz      short loc_18002802F
0x180027fe4  mov     [rbp+arg_0], r14d
0x180027fe8  mov     ecx, [rbx+38h]
0x180027feb  mov     eax, [rbp+arg_0]
0x180027fee  lock cmpxchg [rbp+arg_0], ecx
0x180027ff3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180027ffa  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x180027fff  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028006  mov     rax, [rcx]
0x180028009  mov     r10, [rax+38h]
0x18002800d  mov     eax, [rbp+arg_0]
0x180028010  mov     [rsp+78h+mshlflags], eax
0x180028014  mov     [rsp+78h+pvDestContext], rbx
0x180028019  lea     r9, [rbp+ppstm]
0x18002801d  xor     edx, edx
0x18002801f  lea     r8d, [rdx+2]
0x180028023  mov     rax, r10
0x180028026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002802b  mov     rcx, [rbp+pUnk]
0x18002802f  mov     rax, [rbx]
0x180028032  mov     rdi, [rax]
0x180028035  test    rcx, rcx
0x180028038  jz      short loc_18002804B
0x18002803a  mov     [rbp+pUnk], r14
0x18002803e  mov     rax, [rcx]
0x180028041  mov     rax, [rax+10h]
0x180028045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002804a  nop
0x18002804b  lea     r8, [rbp+pUnk]
0x18002804f  lea     rdx, _GUID_3e1fe603_f897_5263_b328_0806426b8a79
0x180028056  mov     rcx, rbx
0x180028059  mov     rax, rdi
0x18002805c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028061  nop
0x180028062  test    eax, eax
0x180028064  js      loc_18002824B
0x18002806a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180028071  mov     ecx, [rbx+38h]
0x180028074  mov     eax, [rbp+arg_0]
0x180028077  lock cmpxchg [rbp+arg_0], ecx
0x18002807c  mov     rcx, [rbx+78h]
0x180028080  test    rcx, rcx
0x180028083  jz      loc_180028232
0x180028089  mov     [rbp+arg_8], r14
0x18002808d  mov     rax, [rcx]
0x180028090  lea     r8, [rbp+arg_8]
0x180028094  lea     rdx, _GUID_b79a741f_7fb5_50ae_9e99_911201ec3d41
0x18002809b  mov     rax, [rax+18h]
0x18002809f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280a4  nop
0x1800280a5  test    eax, eax
0x1800280a7  js      loc_18002822C
0x1800280ad  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800280b4  test    rcx, rcx
0x1800280b7  jz      short loc_1800280E5
0x1800280b9  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800280c0  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x1800280c5  mov     rax, [rcx]
0x1800280c8  mov     [rsp+78h+mshlflags], r14d
0x1800280cd  mov     [rsp+78h+pvDestContext], rbx
0x1800280d2  lea     r9, [rbp+var_18]
0x1800280d6  xor     edx, edx
0x1800280d8  lea     r8d, [rdx+2]
0x1800280dc  mov     rax, [rax+48h]
0x1800280e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e5  mov     [rbp+arg_18], r14
0x1800280e9  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x1800280ed  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800280f1  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x1800280f6  mov     [rbp+ppstm], r14
0x1800280fa  mov     dword ptr [rbp+ppstm+8], r14d
0x1800280fe  cmp     [rbp+arg_18], r14
0x180028102  jz      short loc_18002814A
0x180028104  cmp     [rbp+arg_8], r14
0x180028108  jz      short loc_18002814A
0x18002810a  mov     rdi, [rbp+pUnk]
0x18002810e  lea     r8, [rbp+ppstm]; ppstm
0x180028112  mov     edx, r15d; fDeleteOnRelease
0x180028115  xor     ecx, ecx; hGlobal
0x180028117  call    cs:__imp_CreateStreamOnHGlobal
0x18002811d  mov     dword ptr [rbp+ppstm+8], eax
0x180028120  test    eax, eax
0x180028122  js      short loc_180028151
0x180028124  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180028129  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18002812e  xor     r9d, r9d; dwDestContext
0x180028131  mov     r8, rdi; pUnk
0x180028134  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002813b  mov     rcx, [rbp+ppstm]; pStm
0x18002813f  call    cs:__imp_CoMarshalInterface
0x180028145  mov     dword ptr [rbp+ppstm+8], eax
0x180028148  jmp     short loc_180028151
0x18002814a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180028151  mov     rcx, [rbp+arg_8]
0x180028155  mov     rax, [rcx]
0x180028158  mov     r8d, [rbp+arg_0]
0x18002815c  mov     rdx, [rbp+pUnk]
0x180028160  mov     rax, [rax+18h]
0x180028164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028169  mov     r8, [rbx+80h]
0x180028170  mov     rdx, [rbp+arg_8]
0x180028174  mov     ecx, eax
0x180028176  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002817b  mov     esi, eax
0x18002817d  or      ecx, 0FFFFFFFFh
0x180028180  lock xadd [rbx+88h], ecx
0x180028188  cmp     ecx, 1
0x18002818b  jnz     short loc_1800281AC
0x18002818d  lock or [rsp+78h+var_78], r14d
0x180028192  mov     rcx, [rbx+78h]
0x180028196  mov     [rbx+78h], r14
0x18002819a  test    rcx, rcx
0x18002819d  jz      short loc_1800281AC
0x18002819f  mov     rax, [rcx]
0x1800281a2  mov     rax, [rax+10h]
0x1800281a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ab  nop
0x1800281ac  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800281b3  test    rcx, rcx
0x1800281b6  jz      short loc_1800281CE
0x1800281b8  mov     rax, [rcx]
0x1800281bb  xor     r9d, r9d
0x1800281be  xor     edx, edx
0x1800281c0  lea     r8d, [r9+2]
0x1800281c4  mov     rax, [rax+50h]
0x1800281c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281cd  nop
0x1800281ce  cmp     dword ptr [rbp+ppstm+8], r14d
0x1800281d2  jl      short loc_1800281F8
0x1800281d4  mov     rcx, [rbp+ppstm]
0x1800281d8  mov     rdx, r14
0x1800281db  mov     rax, [rcx]
0x1800281de  xor     r9d, r9d
0x1800281e1  xor     r8d, r8d
0x1800281e4  mov     rax, [rax+28h]
0x1800281e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ed  mov     rcx, [rbp+ppstm]; pStm
0x1800281f1  call    cs:__imp_CoReleaseMarshalData
0x1800281f7  nop
0x1800281f8  mov     rcx, [rbp+ppstm]
0x1800281fc  test    rcx, rcx
0x1800281ff  jz      short loc_180028212
0x180028201  mov     [rbp+ppstm], r14
0x180028205  mov     rax, [rcx]
0x180028208  mov     rax, [rax+10h]
0x18002820c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028211  nop
0x180028212  mov     rcx, [rbp+arg_18]
0x180028216  test    rcx, rcx
0x180028219  jz      short loc_18002822C
0x18002821b  mov     [rbp+arg_18], r14
0x18002821f  mov     rax, [rcx]
0x180028222  mov     rax, [rax+10h]
0x180028226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002822b  nop
0x18002822c  mov     rcx, [rbp+arg_8]
0x180028230  jmp     short loc_180028235
0x180028232  mov     rcx, r14
0x180028235  test    rcx, rcx
0x180028238  jz      short loc_18002824B
0x18002823a  mov     [rbp+arg_8], r14
0x18002823e  mov     rax, [rcx]
0x180028241  mov     rax, [rax+10h]
0x180028245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002824a  nop
0x18002824b  mov     rcx, [rbp+pUnk]
0x18002824f  test    rcx, rcx
0x180028252  jz      short loc_180028265
0x180028254  mov     [rbp+pUnk], r14
0x180028258  mov     rax, [rcx]
0x18002825b  mov     rax, [rax+10h]
0x18002825f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028264  nop
0x180028265  mov     rax, [rbx]
0x180028268  mov     rcx, rbx
0x18002826b  mov     rax, [rax+10h]
0x18002826f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028274  nop
0x180028275  mov     eax, esi
0x180028277  add     rsp, 78h
0x18002827b  pop     r15
0x18002827d  pop     r14
0x18002827f  pop     rdi
0x180028280  pop     rsi
0x180028281  pop     rbx
0x180028282  pop     rbp
0x180028283  retn
```
