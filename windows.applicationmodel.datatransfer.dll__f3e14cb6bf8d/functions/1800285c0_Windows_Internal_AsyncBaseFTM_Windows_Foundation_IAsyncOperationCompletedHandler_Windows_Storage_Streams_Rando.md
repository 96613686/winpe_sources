# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::RandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800285c0`
- end: `0x1800288e4`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVRandomAccessStreamReference@Streams@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800290d0`
- `0x18003a0a0`
- `0x180051418`

## callees

- `0x1800285c0`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002879f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002879f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028851`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028851`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028777`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028777`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::RandomAccessStreamReference *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_d90442ca_543c_504b_9eb9_294bcad8a283, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_3d203732_ded7_5d32_87e6_c179781f791f,
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
0x1800285c0  push    rbp
0x1800285c2  push    rbx
0x1800285c3  push    rsi
0x1800285c4  push    rdi
0x1800285c5  push    r14
0x1800285c7  push    r15
0x1800285c9  mov     rbp, rsp
0x1800285cc  sub     rsp, 78h
0x1800285d0  mov     rbx, rcx
0x1800285d3  xor     r14d, r14d
0x1800285d6  mov     esi, r14d
0x1800285d9  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800285e0  mov     edx, [rcx+38h]
0x1800285e3  mov     eax, [rbp+arg_0]
0x1800285e6  lock cmpxchg [rbp+arg_0], edx
0x1800285eb  lea     r15d, [r14+1]
0x1800285ef  cmp     [rbp+arg_0], r14d
0x1800285f3  jnz     short loc_1800285FD
0x1800285f5  xor     eax, eax
0x1800285f7  lock cmpxchg [rcx+38h], r15d
0x1800285fd  cmp     [rcx+88h], r14d
0x180028604  jle     loc_1800288D5
0x18002860a  mov     eax, r15d
0x18002860d  lock xadd [rcx+10h], eax
0x180028612  add     eax, r15d
0x180028615  cmp     eax, r15d
0x180028618  jnz     loc_1800288D5
0x18002861e  mov     [rbp+var_38], rbx
0x180028622  test    rbx, rbx
0x180028625  jz      short loc_180028634
0x180028627  mov     rax, [rcx]
0x18002862a  mov     rax, [rax+8]
0x18002862e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028633  nop
0x180028634  mov     rcx, r14
0x180028637  mov     [rbp+pUnk], rcx
0x18002863b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028642  jz      short loc_18002868F
0x180028644  mov     [rbp+arg_0], r14d
0x180028648  mov     ecx, [rbx+38h]
0x18002864b  mov     eax, [rbp+arg_0]
0x18002864e  lock cmpxchg [rbp+arg_0], ecx
0x180028653  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002865a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18002865f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028666  mov     rax, [rcx]
0x180028669  mov     r10, [rax+38h]
0x18002866d  mov     eax, [rbp+arg_0]
0x180028670  mov     [rsp+78h+mshlflags], eax
0x180028674  mov     [rsp+78h+pvDestContext], rbx
0x180028679  lea     r9, [rbp+ppstm]
0x18002867d  xor     edx, edx
0x18002867f  lea     r8d, [rdx+2]
0x180028683  mov     rax, r10
0x180028686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868b  mov     rcx, [rbp+pUnk]
0x18002868f  mov     rax, [rbx]
0x180028692  mov     rdi, [rax]
0x180028695  test    rcx, rcx
0x180028698  jz      short loc_1800286AB
0x18002869a  mov     [rbp+pUnk], r14
0x18002869e  mov     rax, [rcx]
0x1800286a1  mov     rax, [rax+10h]
0x1800286a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286aa  nop
0x1800286ab  lea     r8, [rbp+pUnk]
0x1800286af  lea     rdx, _GUID_d90442ca_543c_504b_9eb9_294bcad8a283
0x1800286b6  mov     rcx, rbx
0x1800286b9  mov     rax, rdi
0x1800286bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286c1  nop
0x1800286c2  test    eax, eax
0x1800286c4  js      loc_1800288AB
0x1800286ca  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800286d1  mov     ecx, [rbx+38h]
0x1800286d4  mov     eax, [rbp+arg_0]
0x1800286d7  lock cmpxchg [rbp+arg_0], ecx
0x1800286dc  mov     rcx, [rbx+78h]
0x1800286e0  test    rcx, rcx
0x1800286e3  jz      loc_180028892
0x1800286e9  mov     [rbp+arg_8], r14
0x1800286ed  mov     rax, [rcx]
0x1800286f0  lea     r8, [rbp+arg_8]
0x1800286f4  lea     rdx, _GUID_3d203732_ded7_5d32_87e6_c179781f791f
0x1800286fb  mov     rax, [rax+18h]
0x1800286ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028704  nop
0x180028705  test    eax, eax
0x180028707  js      loc_18002888C
0x18002870d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028714  test    rcx, rcx
0x180028717  jz      short loc_180028745
0x180028719  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180028720  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180028725  mov     rax, [rcx]
0x180028728  mov     [rsp+78h+mshlflags], r14d
0x18002872d  mov     [rsp+78h+pvDestContext], rbx
0x180028732  lea     r9, [rbp+var_18]
0x180028736  xor     edx, edx
0x180028738  lea     r8d, [rdx+2]
0x18002873c  mov     rax, [rax+48h]
0x180028740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028745  mov     [rbp+arg_18], r14
0x180028749  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18002874d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180028751  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180028756  mov     [rbp+ppstm], r14
0x18002875a  mov     dword ptr [rbp+ppstm+8], r14d
0x18002875e  cmp     [rbp+arg_18], r14
0x180028762  jz      short loc_1800287AA
0x180028764  cmp     [rbp+arg_8], r14
0x180028768  jz      short loc_1800287AA
0x18002876a  mov     rdi, [rbp+pUnk]
0x18002876e  lea     r8, [rbp+ppstm]; ppstm
0x180028772  mov     edx, r15d; fDeleteOnRelease
0x180028775  xor     ecx, ecx; hGlobal
0x180028777  call    cs:__imp_CreateStreamOnHGlobal
0x18002877d  mov     dword ptr [rbp+ppstm+8], eax
0x180028780  test    eax, eax
0x180028782  js      short loc_1800287B1
0x180028784  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180028789  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18002878e  xor     r9d, r9d; dwDestContext
0x180028791  mov     r8, rdi; pUnk
0x180028794  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002879b  mov     rcx, [rbp+ppstm]; pStm
0x18002879f  call    cs:__imp_CoMarshalInterface
0x1800287a5  mov     dword ptr [rbp+ppstm+8], eax
0x1800287a8  jmp     short loc_1800287B1
0x1800287aa  mov     dword ptr [rbp+ppstm+8], 80004002h
0x1800287b1  mov     rcx, [rbp+arg_8]
0x1800287b5  mov     rax, [rcx]
0x1800287b8  mov     r8d, [rbp+arg_0]
0x1800287bc  mov     rdx, [rbp+pUnk]
0x1800287c0  mov     rax, [rax+18h]
0x1800287c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287c9  mov     r8, [rbx+80h]
0x1800287d0  mov     rdx, [rbp+arg_8]
0x1800287d4  mov     ecx, eax
0x1800287d6  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800287db  mov     esi, eax
0x1800287dd  or      ecx, 0FFFFFFFFh
0x1800287e0  lock xadd [rbx+88h], ecx
0x1800287e8  cmp     ecx, 1
0x1800287eb  jnz     short loc_18002880C
0x1800287ed  lock or [rsp+78h+var_78], r14d
0x1800287f2  mov     rcx, [rbx+78h]
0x1800287f6  mov     [rbx+78h], r14
0x1800287fa  test    rcx, rcx
0x1800287fd  jz      short loc_18002880C
0x1800287ff  mov     rax, [rcx]
0x180028802  mov     rax, [rax+10h]
0x180028806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002880b  nop
0x18002880c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028813  test    rcx, rcx
0x180028816  jz      short loc_18002882E
0x180028818  mov     rax, [rcx]
0x18002881b  xor     r9d, r9d
0x18002881e  xor     edx, edx
0x180028820  lea     r8d, [r9+2]
0x180028824  mov     rax, [rax+50h]
0x180028828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882d  nop
0x18002882e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180028832  jl      short loc_180028858
0x180028834  mov     rcx, [rbp+ppstm]
0x180028838  mov     rdx, r14
0x18002883b  mov     rax, [rcx]
0x18002883e  xor     r9d, r9d
0x180028841  xor     r8d, r8d
0x180028844  mov     rax, [rax+28h]
0x180028848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002884d  mov     rcx, [rbp+ppstm]; pStm
0x180028851  call    cs:__imp_CoReleaseMarshalData
0x180028857  nop
0x180028858  mov     rcx, [rbp+ppstm]
0x18002885c  test    rcx, rcx
0x18002885f  jz      short loc_180028872
0x180028861  mov     [rbp+ppstm], r14
0x180028865  mov     rax, [rcx]
0x180028868  mov     rax, [rax+10h]
0x18002886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028871  nop
0x180028872  mov     rcx, [rbp+arg_18]
0x180028876  test    rcx, rcx
0x180028879  jz      short loc_18002888C
0x18002887b  mov     [rbp+arg_18], r14
0x18002887f  mov     rax, [rcx]
0x180028882  mov     rax, [rax+10h]
0x180028886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002888b  nop
0x18002888c  mov     rcx, [rbp+arg_8]
0x180028890  jmp     short loc_180028895
0x180028892  mov     rcx, r14
0x180028895  test    rcx, rcx
0x180028898  jz      short loc_1800288AB
0x18002889a  mov     [rbp+arg_8], r14
0x18002889e  mov     rax, [rcx]
0x1800288a1  mov     rax, [rax+10h]
0x1800288a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288aa  nop
0x1800288ab  mov     rcx, [rbp+pUnk]
0x1800288af  test    rcx, rcx
0x1800288b2  jz      short loc_1800288C5
0x1800288b4  mov     [rbp+pUnk], r14
0x1800288b8  mov     rax, [rcx]
0x1800288bb  mov     rax, [rax+10h]
0x1800288bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c4  nop
0x1800288c5  mov     rax, [rbx]
0x1800288c8  mov     rcx, rbx
0x1800288cb  mov     rax, [rax+10h]
0x1800288cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288d4  nop
0x1800288d5  mov     eax, esi
0x1800288d7  add     rsp, 78h
0x1800288db  pop     r15
0x1800288dd  pop     r14
0x1800288df  pop     rdi
0x1800288e0  pop     rsi
0x1800288e1  pop     rbx
0x1800288e2  pop     rbp
0x1800288e3  retn
```
