# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180028290`
- end: `0x1800285b4`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029070`
- `0x18003a040`
- `0x18005136c`

## callees

- `0x180028290`
- `0x1800293d8`
- `0x18003350c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002846f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002846f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028521`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180028521`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028447`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180028447`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_abf53c57_ee50_5342_b52a_26e3b8cc024f, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_3f08262e_a2e1_5134_9297_e9211f481a2d,
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
0x180028290  push    rbp
0x180028292  push    rbx
0x180028293  push    rsi
0x180028294  push    rdi
0x180028295  push    r14
0x180028297  push    r15
0x180028299  mov     rbp, rsp
0x18002829c  sub     rsp, 78h
0x1800282a0  mov     rbx, rcx
0x1800282a3  xor     r14d, r14d
0x1800282a6  mov     esi, r14d
0x1800282a9  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800282b0  mov     edx, [rcx+38h]
0x1800282b3  mov     eax, [rbp+arg_0]
0x1800282b6  lock cmpxchg [rbp+arg_0], edx
0x1800282bb  lea     r15d, [r14+1]
0x1800282bf  cmp     [rbp+arg_0], r14d
0x1800282c3  jnz     short loc_1800282CD
0x1800282c5  xor     eax, eax
0x1800282c7  lock cmpxchg [rcx+38h], r15d
0x1800282cd  cmp     [rcx+88h], r14d
0x1800282d4  jle     loc_1800285A5
0x1800282da  mov     eax, r15d
0x1800282dd  lock xadd [rcx+10h], eax
0x1800282e2  add     eax, r15d
0x1800282e5  cmp     eax, r15d
0x1800282e8  jnz     loc_1800285A5
0x1800282ee  mov     [rbp+var_38], rbx
0x1800282f2  test    rbx, rbx
0x1800282f5  jz      short loc_180028304
0x1800282f7  mov     rax, [rcx]
0x1800282fa  mov     rax, [rax+8]
0x1800282fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028303  nop
0x180028304  mov     rcx, r14
0x180028307  mov     [rbp+pUnk], rcx
0x18002830b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028312  jz      short loc_18002835F
0x180028314  mov     [rbp+arg_0], r14d
0x180028318  mov     ecx, [rbx+38h]
0x18002831b  mov     eax, [rbp+arg_0]
0x18002831e  lock cmpxchg [rbp+arg_0], ecx
0x180028323  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002832a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18002832f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180028336  mov     rax, [rcx]
0x180028339  mov     r10, [rax+38h]
0x18002833d  mov     eax, [rbp+arg_0]
0x180028340  mov     [rsp+78h+mshlflags], eax
0x180028344  mov     [rsp+78h+pvDestContext], rbx
0x180028349  lea     r9, [rbp+ppstm]
0x18002834d  xor     edx, edx
0x18002834f  lea     r8d, [rdx+2]
0x180028353  mov     rax, r10
0x180028356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002835b  mov     rcx, [rbp+pUnk]
0x18002835f  mov     rax, [rbx]
0x180028362  mov     rdi, [rax]
0x180028365  test    rcx, rcx
0x180028368  jz      short loc_18002837B
0x18002836a  mov     [rbp+pUnk], r14
0x18002836e  mov     rax, [rcx]
0x180028371  mov     rax, [rax+10h]
0x180028375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002837a  nop
0x18002837b  lea     r8, [rbp+pUnk]
0x18002837f  lea     rdx, _GUID_abf53c57_ee50_5342_b52a_26e3b8cc024f
0x180028386  mov     rcx, rbx
0x180028389  mov     rax, rdi
0x18002838c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028391  nop
0x180028392  test    eax, eax
0x180028394  js      loc_18002857B
0x18002839a  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800283a1  mov     ecx, [rbx+38h]
0x1800283a4  mov     eax, [rbp+arg_0]
0x1800283a7  lock cmpxchg [rbp+arg_0], ecx
0x1800283ac  mov     rcx, [rbx+78h]
0x1800283b0  test    rcx, rcx
0x1800283b3  jz      loc_180028562
0x1800283b9  mov     [rbp+arg_8], r14
0x1800283bd  mov     rax, [rcx]
0x1800283c0  lea     r8, [rbp+arg_8]
0x1800283c4  lea     rdx, _GUID_3f08262e_a2e1_5134_9297_e9211f481a2d
0x1800283cb  mov     rax, [rax+18h]
0x1800283cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283d4  nop
0x1800283d5  test    eax, eax
0x1800283d7  js      loc_18002855C
0x1800283dd  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800283e4  test    rcx, rcx
0x1800283e7  jz      short loc_180028415
0x1800283e9  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800283f0  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x1800283f5  mov     rax, [rcx]
0x1800283f8  mov     [rsp+78h+mshlflags], r14d
0x1800283fd  mov     [rsp+78h+pvDestContext], rbx
0x180028402  lea     r9, [rbp+var_18]
0x180028406  xor     edx, edx
0x180028408  lea     r8d, [rdx+2]
0x18002840c  mov     rax, [rax+48h]
0x180028410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028415  mov     [rbp+arg_18], r14
0x180028419  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18002841d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180028421  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180028426  mov     [rbp+ppstm], r14
0x18002842a  mov     dword ptr [rbp+ppstm+8], r14d
0x18002842e  cmp     [rbp+arg_18], r14
0x180028432  jz      short loc_18002847A
0x180028434  cmp     [rbp+arg_8], r14
0x180028438  jz      short loc_18002847A
0x18002843a  mov     rdi, [rbp+pUnk]
0x18002843e  lea     r8, [rbp+ppstm]; ppstm
0x180028442  mov     edx, r15d; fDeleteOnRelease
0x180028445  xor     ecx, ecx; hGlobal
0x180028447  call    cs:__imp_CreateStreamOnHGlobal
0x18002844d  mov     dword ptr [rbp+ppstm+8], eax
0x180028450  test    eax, eax
0x180028452  js      short loc_180028481
0x180028454  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180028459  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18002845e  xor     r9d, r9d; dwDestContext
0x180028461  mov     r8, rdi; pUnk
0x180028464  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002846b  mov     rcx, [rbp+ppstm]; pStm
0x18002846f  call    cs:__imp_CoMarshalInterface
0x180028475  mov     dword ptr [rbp+ppstm+8], eax
0x180028478  jmp     short loc_180028481
0x18002847a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180028481  mov     rcx, [rbp+arg_8]
0x180028485  mov     rax, [rcx]
0x180028488  mov     r8d, [rbp+arg_0]
0x18002848c  mov     rdx, [rbp+pUnk]
0x180028490  mov     rax, [rax+18h]
0x180028494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028499  mov     r8, [rbx+80h]
0x1800284a0  mov     rdx, [rbp+arg_8]
0x1800284a4  mov     ecx, eax
0x1800284a6  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800284ab  mov     esi, eax
0x1800284ad  or      ecx, 0FFFFFFFFh
0x1800284b0  lock xadd [rbx+88h], ecx
0x1800284b8  cmp     ecx, 1
0x1800284bb  jnz     short loc_1800284DC
0x1800284bd  lock or [rsp+78h+var_78], r14d
0x1800284c2  mov     rcx, [rbx+78h]
0x1800284c6  mov     [rbx+78h], r14
0x1800284ca  test    rcx, rcx
0x1800284cd  jz      short loc_1800284DC
0x1800284cf  mov     rax, [rcx]
0x1800284d2  mov     rax, [rax+10h]
0x1800284d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284db  nop
0x1800284dc  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800284e3  test    rcx, rcx
0x1800284e6  jz      short loc_1800284FE
0x1800284e8  mov     rax, [rcx]
0x1800284eb  xor     r9d, r9d
0x1800284ee  xor     edx, edx
0x1800284f0  lea     r8d, [r9+2]
0x1800284f4  mov     rax, [rax+50h]
0x1800284f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284fd  nop
0x1800284fe  cmp     dword ptr [rbp+ppstm+8], r14d
0x180028502  jl      short loc_180028528
0x180028504  mov     rcx, [rbp+ppstm]
0x180028508  mov     rdx, r14
0x18002850b  mov     rax, [rcx]
0x18002850e  xor     r9d, r9d
0x180028511  xor     r8d, r8d
0x180028514  mov     rax, [rax+28h]
0x180028518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002851d  mov     rcx, [rbp+ppstm]; pStm
0x180028521  call    cs:__imp_CoReleaseMarshalData
0x180028527  nop
0x180028528  mov     rcx, [rbp+ppstm]
0x18002852c  test    rcx, rcx
0x18002852f  jz      short loc_180028542
0x180028531  mov     [rbp+ppstm], r14
0x180028535  mov     rax, [rcx]
0x180028538  mov     rax, [rax+10h]
0x18002853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028541  nop
0x180028542  mov     rcx, [rbp+arg_18]
0x180028546  test    rcx, rcx
0x180028549  jz      short loc_18002855C
0x18002854b  mov     [rbp+arg_18], r14
0x18002854f  mov     rax, [rcx]
0x180028552  mov     rax, [rax+10h]
0x180028556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002855b  nop
0x18002855c  mov     rcx, [rbp+arg_8]
0x180028560  jmp     short loc_180028565
0x180028562  mov     rcx, r14
0x180028565  test    rcx, rcx
0x180028568  jz      short loc_18002857B
0x18002856a  mov     [rbp+arg_8], r14
0x18002856e  mov     rax, [rcx]
0x180028571  mov     rax, [rax+10h]
0x180028575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002857a  nop
0x18002857b  mov     rcx, [rbp+pUnk]
0x18002857f  test    rcx, rcx
0x180028582  jz      short loc_180028595
0x180028584  mov     [rbp+pUnk], r14
0x180028588  mov     rax, [rcx]
0x18002858b  mov     rax, [rax+10h]
0x18002858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028594  nop
0x180028595  mov     rax, [rbx]
0x180028598  mov     rcx, rbx
0x18002859b  mov     rax, [rax+10h]
0x18002859f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285a4  nop
0x1800285a5  mov     eax, esi
0x1800285a7  add     rsp, 78h
0x1800285ab  pop     r15
0x1800285ad  pop     r14
0x1800285af  pop     rdi
0x1800285b0  pop     rsi
0x1800285b1  pop     rbx
0x1800285b2  pop     rbp
0x1800285b3  retn
```
