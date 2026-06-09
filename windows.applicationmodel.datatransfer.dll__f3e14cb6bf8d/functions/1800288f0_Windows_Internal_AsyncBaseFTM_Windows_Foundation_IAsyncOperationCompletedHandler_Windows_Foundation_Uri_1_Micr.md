# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Uri *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800288f0`
- end: `0x180028c14`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUri@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029130`
- `0x18003a100`
- `0x1800514c4`

## callees

- `0x1800288f0`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180028acf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180028acf`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028b81`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028b81`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028aa7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028aa7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Uri *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_641cb9dd_a28d_59e2_b8db_a227eda6cf2e, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_ad46f1cc_2bb0_585c_9885_03c2780d4d58,
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
0x1800288f0  push    rbp
0x1800288f2  push    rbx
0x1800288f3  push    rsi
0x1800288f4  push    rdi
0x1800288f5  push    r14
0x1800288f7  push    r15
0x1800288f9  mov     rbp, rsp
0x1800288fc  sub     rsp, 78h
0x180028900  mov     rbx, rcx
0x180028903  xor     r14d, r14d
0x180028906  mov     esi, r14d
0x180028909  mov     [rbp+arg_0], 0FFFFFFFEh
0x180028910  mov     edx, [rcx+38h]
0x180028913  mov     eax, [rbp+arg_0]
0x180028916  lock cmpxchg [rbp+arg_0], edx
0x18002891b  lea     r15d, [r14+1]
0x18002891f  cmp     [rbp+arg_0], r14d
0x180028923  jnz     short loc_18002892D
0x180028925  xor     eax, eax
0x180028927  lock cmpxchg [rcx+38h], r15d
0x18002892d  cmp     [rcx+88h], r14d
0x180028934  jle     loc_180028C05
0x18002893a  mov     eax, r15d
0x18002893d  lock xadd [rcx+10h], eax
0x180028942  add     eax, r15d
0x180028945  cmp     eax, r15d
0x180028948  jnz     loc_180028C05
0x18002894e  mov     [rbp+var_38], rbx
0x180028952  test    rbx, rbx
0x180028955  jz      short loc_180028964
0x180028957  mov     rax, [rcx]
0x18002895a  mov     rax, [rax+8]
0x18002895e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028963  nop
0x180028964  mov     rcx, r14
0x180028967  mov     [rbp+pUnk], rcx
0x18002896b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028972  jz      short loc_1800289BF
0x180028974  mov     [rbp+arg_0], r14d
0x180028978  mov     ecx, [rbx+38h]
0x18002897b  mov     eax, [rbp+arg_0]
0x18002897e  lock cmpxchg [rbp+arg_0], ecx
0x180028983  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002898a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18002898f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028996  mov     rax, [rcx]
0x180028999  mov     r10, [rax+38h]
0x18002899d  mov     eax, [rbp+arg_0]
0x1800289a0  mov     [rsp+78h+mshlflags], eax
0x1800289a4  mov     [rsp+78h+pvDestContext], rbx
0x1800289a9  lea     r9, [rbp+ppstm]
0x1800289ad  xor     edx, edx
0x1800289af  lea     r8d, [rdx+2]
0x1800289b3  mov     rax, r10
0x1800289b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289bb  mov     rcx, [rbp+pUnk]
0x1800289bf  mov     rax, [rbx]
0x1800289c2  mov     rdi, [rax]
0x1800289c5  test    rcx, rcx
0x1800289c8  jz      short loc_1800289DB
0x1800289ca  mov     [rbp+pUnk], r14
0x1800289ce  mov     rax, [rcx]
0x1800289d1  mov     rax, [rax+10h]
0x1800289d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289da  nop
0x1800289db  lea     r8, [rbp+pUnk]
0x1800289df  lea     rdx, _GUID_641cb9dd_a28d_59e2_b8db_a227eda6cf2e
0x1800289e6  mov     rcx, rbx
0x1800289e9  mov     rax, rdi
0x1800289ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f1  nop
0x1800289f2  test    eax, eax
0x1800289f4  js      loc_180028BDB
0x1800289fa  mov     [rbp+arg_0], 0FFFFFFFEh
0x180028a01  mov     ecx, [rbx+38h]
0x180028a04  mov     eax, [rbp+arg_0]
0x180028a07  lock cmpxchg [rbp+arg_0], ecx
0x180028a0c  mov     rcx, [rbx+78h]
0x180028a10  test    rcx, rcx
0x180028a13  jz      loc_180028BC2
0x180028a19  mov     [rbp+arg_8], r14
0x180028a1d  mov     rax, [rcx]
0x180028a20  lea     r8, [rbp+arg_8]
0x180028a24  lea     rdx, _GUID_ad46f1cc_2bb0_585c_9885_03c2780d4d58
0x180028a2b  mov     rax, [rax+18h]
0x180028a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a34  nop
0x180028a35  test    eax, eax
0x180028a37  js      loc_180028BBC
0x180028a3d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028a44  test    rcx, rcx
0x180028a47  jz      short loc_180028A75
0x180028a49  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180028a50  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180028a55  mov     rax, [rcx]
0x180028a58  mov     [rsp+78h+mshlflags], r14d
0x180028a5d  mov     [rsp+78h+pvDestContext], rbx
0x180028a62  lea     r9, [rbp+var_18]
0x180028a66  xor     edx, edx
0x180028a68  lea     r8d, [rdx+2]
0x180028a6c  mov     rax, [rax+48h]
0x180028a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a75  mov     [rbp+arg_18], r14
0x180028a79  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180028a7d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180028a81  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180028a86  mov     [rbp+ppstm], r14
0x180028a8a  mov     dword ptr [rbp+ppstm+8], r14d
0x180028a8e  cmp     [rbp+arg_18], r14
0x180028a92  jz      short loc_180028ADA
0x180028a94  cmp     [rbp+arg_8], r14
0x180028a98  jz      short loc_180028ADA
0x180028a9a  mov     rdi, [rbp+pUnk]
0x180028a9e  lea     r8, [rbp+ppstm]; ppstm
0x180028aa2  mov     edx, r15d; fDeleteOnRelease
0x180028aa5  xor     ecx, ecx; hGlobal
0x180028aa7  call    cs:__imp_CreateStreamOnHGlobal
0x180028aad  mov     dword ptr [rbp+ppstm+8], eax
0x180028ab0  test    eax, eax
0x180028ab2  js      short loc_180028AE1
0x180028ab4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180028ab9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x180028abe  xor     r9d, r9d; dwDestContext
0x180028ac1  mov     r8, rdi; pUnk
0x180028ac4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180028acb  mov     rcx, [rbp+ppstm]; pStm
0x180028acf  call    cs:__imp_CoMarshalInterface
0x180028ad5  mov     dword ptr [rbp+ppstm+8], eax
0x180028ad8  jmp     short loc_180028AE1
0x180028ada  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180028ae1  mov     rcx, [rbp+arg_8]
0x180028ae5  mov     rax, [rcx]
0x180028ae8  mov     r8d, [rbp+arg_0]
0x180028aec  mov     rdx, [rbp+pUnk]
0x180028af0  mov     rax, [rax+18h]
0x180028af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028af9  mov     r8, [rbx+80h]
0x180028b00  mov     rdx, [rbp+arg_8]
0x180028b04  mov     ecx, eax
0x180028b06  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180028b0b  mov     esi, eax
0x180028b0d  or      ecx, 0FFFFFFFFh
0x180028b10  lock xadd [rbx+88h], ecx
0x180028b18  cmp     ecx, 1
0x180028b1b  jnz     short loc_180028B3C
0x180028b1d  lock or [rsp+78h+var_78], r14d
0x180028b22  mov     rcx, [rbx+78h]
0x180028b26  mov     [rbx+78h], r14
0x180028b2a  test    rcx, rcx
0x180028b2d  jz      short loc_180028B3C
0x180028b2f  mov     rax, [rcx]
0x180028b32  mov     rax, [rax+10h]
0x180028b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b3b  nop
0x180028b3c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028b43  test    rcx, rcx
0x180028b46  jz      short loc_180028B5E
0x180028b48  mov     rax, [rcx]
0x180028b4b  xor     r9d, r9d
0x180028b4e  xor     edx, edx
0x180028b50  lea     r8d, [r9+2]
0x180028b54  mov     rax, [rax+50h]
0x180028b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b5d  nop
0x180028b5e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180028b62  jl      short loc_180028B88
0x180028b64  mov     rcx, [rbp+ppstm]
0x180028b68  mov     rdx, r14
0x180028b6b  mov     rax, [rcx]
0x180028b6e  xor     r9d, r9d
0x180028b71  xor     r8d, r8d
0x180028b74  mov     rax, [rax+28h]
0x180028b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b7d  mov     rcx, [rbp+ppstm]; pStm
0x180028b81  call    cs:__imp_CoReleaseMarshalData
0x180028b87  nop
0x180028b88  mov     rcx, [rbp+ppstm]
0x180028b8c  test    rcx, rcx
0x180028b8f  jz      short loc_180028BA2
0x180028b91  mov     [rbp+ppstm], r14
0x180028b95  mov     rax, [rcx]
0x180028b98  mov     rax, [rax+10h]
0x180028b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ba1  nop
0x180028ba2  mov     rcx, [rbp+arg_18]
0x180028ba6  test    rcx, rcx
0x180028ba9  jz      short loc_180028BBC
0x180028bab  mov     [rbp+arg_18], r14
0x180028baf  mov     rax, [rcx]
0x180028bb2  mov     rax, [rax+10h]
0x180028bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bbb  nop
0x180028bbc  mov     rcx, [rbp+arg_8]
0x180028bc0  jmp     short loc_180028BC5
0x180028bc2  mov     rcx, r14
0x180028bc5  test    rcx, rcx
0x180028bc8  jz      short loc_180028BDB
0x180028bca  mov     [rbp+arg_8], r14
0x180028bce  mov     rax, [rcx]
0x180028bd1  mov     rax, [rax+10h]
0x180028bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bda  nop
0x180028bdb  mov     rcx, [rbp+pUnk]
0x180028bdf  test    rcx, rcx
0x180028be2  jz      short loc_180028BF5
0x180028be4  mov     [rbp+pUnk], r14
0x180028be8  mov     rax, [rcx]
0x180028beb  mov     rax, [rax+10h]
0x180028bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bf4  nop
0x180028bf5  mov     rax, [rbx]
0x180028bf8  mov     rcx, rbx
0x180028bfb  mov     rax, [rax+10h]
0x180028bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c04  nop
0x180028c05  mov     eax, esi
0x180028c07  add     rsp, 78h
0x180028c0b  pop     r15
0x180028c0d  pop     r14
0x180028c0f  pop     rdi
0x180028c10  pop     rsi
0x180028c11  pop     rbx
0x180028c12  pop     rbp
0x180028c13  retn
```
