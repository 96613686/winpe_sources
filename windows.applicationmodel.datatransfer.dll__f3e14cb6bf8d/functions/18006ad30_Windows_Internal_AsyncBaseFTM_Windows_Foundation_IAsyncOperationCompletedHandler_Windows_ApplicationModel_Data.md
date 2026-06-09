# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryItemsResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18006ad30`
- end: `0x18006b054`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVClipboardHistoryItemsResult@DataTransfer@ApplicationModel@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006b060`
- `0x18006d3d0`
- `0x180070d78`

## callees

- `0x1800293d8`
- `0x18003350c`
- `0x18006ad30`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18006af0f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18006af0f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18006afc1`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18006afc1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006aee7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006aee7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::DataTransfer::ClipboardHistoryItemsResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_677b06b8_0134_5692_b487_4c8e2408ca01, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_841da82d_a32c_5997_8450_f54af1d5477e,
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
0x18006ad30  push    rbp
0x18006ad32  push    rbx
0x18006ad33  push    rsi
0x18006ad34  push    rdi
0x18006ad35  push    r14
0x18006ad37  push    r15
0x18006ad39  mov     rbp, rsp
0x18006ad3c  sub     rsp, 78h
0x18006ad40  mov     rbx, rcx
0x18006ad43  xor     r14d, r14d
0x18006ad46  mov     esi, r14d
0x18006ad49  mov     [rbp+arg_0], 0FFFFFFFEh
0x18006ad50  mov     edx, [rcx+38h]
0x18006ad53  mov     eax, [rbp+arg_0]
0x18006ad56  lock cmpxchg [rbp+arg_0], edx
0x18006ad5b  lea     r15d, [r14+1]
0x18006ad5f  cmp     [rbp+arg_0], r14d
0x18006ad63  jnz     short loc_18006AD6D
0x18006ad65  xor     eax, eax
0x18006ad67  lock cmpxchg [rcx+38h], r15d
0x18006ad6d  cmp     [rcx+88h], r14d
0x18006ad74  jle     loc_18006B045
0x18006ad7a  mov     eax, r15d
0x18006ad7d  lock xadd [rcx+10h], eax
0x18006ad82  add     eax, r15d
0x18006ad85  cmp     eax, r15d
0x18006ad88  jnz     loc_18006B045
0x18006ad8e  mov     [rbp+var_38], rbx
0x18006ad92  test    rbx, rbx
0x18006ad95  jz      short loc_18006ADA4
0x18006ad97  mov     rax, [rcx]
0x18006ad9a  mov     rax, [rax+8]
0x18006ad9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ada3  nop
0x18006ada4  mov     rcx, r14
0x18006ada7  mov     [rbp+pUnk], rcx
0x18006adab  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18006adb2  jz      short loc_18006ADFF
0x18006adb4  mov     [rbp+arg_0], r14d
0x18006adb8  mov     ecx, [rbx+38h]
0x18006adbb  mov     eax, [rbp+arg_0]
0x18006adbe  lock cmpxchg [rbp+arg_0], ecx
0x18006adc3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18006adca  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18006adcf  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18006add6  mov     rax, [rcx]
0x18006add9  mov     r10, [rax+38h]
0x18006addd  mov     eax, [rbp+arg_0]
0x18006ade0  mov     [rsp+78h+mshlflags], eax
0x18006ade4  mov     [rsp+78h+pvDestContext], rbx
0x18006ade9  lea     r9, [rbp+ppstm]
0x18006aded  xor     edx, edx
0x18006adef  lea     r8d, [rdx+2]
0x18006adf3  mov     rax, r10
0x18006adf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adfb  mov     rcx, [rbp+pUnk]
0x18006adff  mov     rax, [rbx]
0x18006ae02  mov     rdi, [rax]
0x18006ae05  test    rcx, rcx
0x18006ae08  jz      short loc_18006AE1B
0x18006ae0a  mov     [rbp+pUnk], r14
0x18006ae0e  mov     rax, [rcx]
0x18006ae11  mov     rax, [rax+10h]
0x18006ae15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae1a  nop
0x18006ae1b  lea     r8, [rbp+pUnk]
0x18006ae1f  lea     rdx, _GUID_677b06b8_0134_5692_b487_4c8e2408ca01
0x18006ae26  mov     rcx, rbx
0x18006ae29  mov     rax, rdi
0x18006ae2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae31  nop
0x18006ae32  test    eax, eax
0x18006ae34  js      loc_18006B01B
0x18006ae3a  mov     [rbp+arg_0], 0FFFFFFFEh
0x18006ae41  mov     ecx, [rbx+38h]
0x18006ae44  mov     eax, [rbp+arg_0]
0x18006ae47  lock cmpxchg [rbp+arg_0], ecx
0x18006ae4c  mov     rcx, [rbx+78h]
0x18006ae50  test    rcx, rcx
0x18006ae53  jz      loc_18006B002
0x18006ae59  mov     [rbp+arg_8], r14
0x18006ae5d  mov     rax, [rcx]
0x18006ae60  lea     r8, [rbp+arg_8]
0x18006ae64  lea     rdx, _GUID_841da82d_a32c_5997_8450_f54af1d5477e
0x18006ae6b  mov     rax, [rax+18h]
0x18006ae6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae74  nop
0x18006ae75  test    eax, eax
0x18006ae77  js      loc_18006AFFC
0x18006ae7d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18006ae84  test    rcx, rcx
0x18006ae87  jz      short loc_18006AEB5
0x18006ae89  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18006ae90  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18006ae95  mov     rax, [rcx]
0x18006ae98  mov     [rsp+78h+mshlflags], r14d
0x18006ae9d  mov     [rsp+78h+pvDestContext], rbx
0x18006aea2  lea     r9, [rbp+var_18]
0x18006aea6  xor     edx, edx
0x18006aea8  lea     r8d, [rdx+2]
0x18006aeac  mov     rax, [rax+48h]
0x18006aeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aeb5  mov     [rbp+arg_18], r14
0x18006aeb9  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18006aebd  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18006aec1  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x18006aec6  mov     [rbp+ppstm], r14
0x18006aeca  mov     dword ptr [rbp+ppstm+8], r14d
0x18006aece  cmp     [rbp+arg_18], r14
0x18006aed2  jz      short loc_18006AF1A
0x18006aed4  cmp     [rbp+arg_8], r14
0x18006aed8  jz      short loc_18006AF1A
0x18006aeda  mov     rdi, [rbp+pUnk]
0x18006aede  lea     r8, [rbp+ppstm]; ppstm
0x18006aee2  mov     edx, r15d; fDeleteOnRelease
0x18006aee5  xor     ecx, ecx; hGlobal
0x18006aee7  call    cs:__imp_CreateStreamOnHGlobal
0x18006aeed  mov     dword ptr [rbp+ppstm+8], eax
0x18006aef0  test    eax, eax
0x18006aef2  js      short loc_18006AF21
0x18006aef4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x18006aef9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18006aefe  xor     r9d, r9d; dwDestContext
0x18006af01  mov     r8, rdi; pUnk
0x18006af04  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18006af0b  mov     rcx, [rbp+ppstm]; pStm
0x18006af0f  call    cs:__imp_CoMarshalInterface
0x18006af15  mov     dword ptr [rbp+ppstm+8], eax
0x18006af18  jmp     short loc_18006AF21
0x18006af1a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x18006af21  mov     rcx, [rbp+arg_8]
0x18006af25  mov     rax, [rcx]
0x18006af28  mov     r8d, [rbp+arg_0]
0x18006af2c  mov     rdx, [rbp+pUnk]
0x18006af30  mov     rax, [rax+18h]
0x18006af34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af39  mov     r8, [rbx+80h]
0x18006af40  mov     rdx, [rbp+arg_8]
0x18006af44  mov     ecx, eax
0x18006af46  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18006af4b  mov     esi, eax
0x18006af4d  or      ecx, 0FFFFFFFFh
0x18006af50  lock xadd [rbx+88h], ecx
0x18006af58  cmp     ecx, 1
0x18006af5b  jnz     short loc_18006AF7C
0x18006af5d  lock or [rsp+78h+var_78], r14d
0x18006af62  mov     rcx, [rbx+78h]
0x18006af66  mov     [rbx+78h], r14
0x18006af6a  test    rcx, rcx
0x18006af6d  jz      short loc_18006AF7C
0x18006af6f  mov     rax, [rcx]
0x18006af72  mov     rax, [rax+10h]
0x18006af76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af7b  nop
0x18006af7c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18006af83  test    rcx, rcx
0x18006af86  jz      short loc_18006AF9E
0x18006af88  mov     rax, [rcx]
0x18006af8b  xor     r9d, r9d
0x18006af8e  xor     edx, edx
0x18006af90  lea     r8d, [r9+2]
0x18006af94  mov     rax, [rax+50h]
0x18006af98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af9d  nop
0x18006af9e  cmp     dword ptr [rbp+ppstm+8], r14d
0x18006afa2  jl      short loc_18006AFC8
0x18006afa4  mov     rcx, [rbp+ppstm]
0x18006afa8  mov     rdx, r14
0x18006afab  mov     rax, [rcx]
0x18006afae  xor     r9d, r9d
0x18006afb1  xor     r8d, r8d
0x18006afb4  mov     rax, [rax+28h]
0x18006afb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afbd  mov     rcx, [rbp+ppstm]; pStm
0x18006afc1  call    cs:__imp_CoReleaseMarshalData
0x18006afc7  nop
0x18006afc8  mov     rcx, [rbp+ppstm]
0x18006afcc  test    rcx, rcx
0x18006afcf  jz      short loc_18006AFE2
0x18006afd1  mov     [rbp+ppstm], r14
0x18006afd5  mov     rax, [rcx]
0x18006afd8  mov     rax, [rax+10h]
0x18006afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe1  nop
0x18006afe2  mov     rcx, [rbp+arg_18]
0x18006afe6  test    rcx, rcx
0x18006afe9  jz      short loc_18006AFFC
0x18006afeb  mov     [rbp+arg_18], r14
0x18006afef  mov     rax, [rcx]
0x18006aff2  mov     rax, [rax+10h]
0x18006aff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006affb  nop
0x18006affc  mov     rcx, [rbp+arg_8]
0x18006b000  jmp     short loc_18006B005
0x18006b002  mov     rcx, r14
0x18006b005  test    rcx, rcx
0x18006b008  jz      short loc_18006B01B
0x18006b00a  mov     [rbp+arg_8], r14
0x18006b00e  mov     rax, [rcx]
0x18006b011  mov     rax, [rax+10h]
0x18006b015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b01a  nop
0x18006b01b  mov     rcx, [rbp+pUnk]
0x18006b01f  test    rcx, rcx
0x18006b022  jz      short loc_18006B035
0x18006b024  mov     [rbp+pUnk], r14
0x18006b028  mov     rax, [rcx]
0x18006b02b  mov     rax, [rax+10h]
0x18006b02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b034  nop
0x18006b035  mov     rax, [rbx]
0x18006b038  mov     rcx, rbx
0x18006b03b  mov     rax, [rax+10h]
0x18006b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b044  nop
0x18006b045  mov     eax, esi
0x18006b047  add     rsp, 78h
0x18006b04b  pop     r15
0x18006b04d  pop     r14
0x18006b04f  pop     rdi
0x18006b050  pop     rsi
0x18006b051  pop     rbx
0x18006b052  pop     rbp
0x18006b053  retn
```
