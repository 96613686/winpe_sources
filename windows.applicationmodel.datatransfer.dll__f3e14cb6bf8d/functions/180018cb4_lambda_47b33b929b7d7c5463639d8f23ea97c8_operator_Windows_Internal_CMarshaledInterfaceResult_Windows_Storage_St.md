# _lambda_47b33b929b7d7c5463639d8f23ea97c8_::operator()(Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStreamReference> &)

- ea: `0x180018cb4`
- end: `0x18001911d`
- name: `??R_lambda_47b33b929b7d7c5463639d8f23ea97c8_@@QEBAJAEAV?$CMarshaledInterfaceResult@UIRandomAccessStreamReference@Streams@Storage@Windows@@@Internal@Windows@@@Z`
- size: `1129`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800492a0`

## callees

- `0x180002ad0`
- `0x180008b68`
- `0x180018cb4`
- `0x180048954`
- `0x180081010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x180018d47`
- `SHCORE!SHCreateMemStream` at `0x180018d47`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180018db2`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180018db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018e25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018e3e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018e3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018e70`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018e70`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180018fe4`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180018fe4`

## string_xrefs

- `0x180018e1e`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
__int64 __fastcall _lambda_47b33b929b7d7c5463639d8f23ea97c8_::operator()(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v5; // rax
  int RandomAccessStreamOverStream; // eax
  __int64 v7; // rcx
  int ActivationFactory; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int AgileReference; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  IStream *v26; // [rsp+20h] [rbp-59h]
  __int64 v27; // [rsp+20h] [rbp-59h]
  __int64 v28; // [rsp+20h] [rbp-59h]
  __int64 v29; // [rsp+20h] [rbp-59h]
  __int64 v30; // [rsp+20h] [rbp-59h]
  __int64 v31; // [rsp+20h] [rbp-59h]
  __int64 v32; // [rsp+28h] [rbp-51h] BYREF
  __int64 v33; // [rsp+30h] [rbp-49h] BYREF
  __int64 v34; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-31h] BYREF
  BYTE pInit[8]; // [rsp+60h] [rbp-19h] BYREF
  int v38; // [rsp+68h] [rbp-11h]
  int v39; // [rsp+6Ch] [rbp-Dh]
  int v40; // [rsp+70h] [rbp-9h]
  int v41; // [rsp+74h] [rbp-5h]
  int v42; // [rsp+78h] [rbp-1h]
  int v43; // [rsp+7Ch] [rbp+3h]
  __int64 v44; // [rsp+80h] [rbp+7h]
  __int64 v45; // [rsp+88h] [rbp+Fh]
  __int64 v46; // [rsp+90h] [rbp+17h]
  int v47; // [rsp+98h] [rbp+1Fh]
  int v48; // [rsp+9Ch] [rbp+23h]
  __int16 v49; // [rsp+A0h] [rbp+27h]
  char v50; // [rsp+A2h] [rbp+29h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)pInit = 4345154;
  v38 = 4063232;
  v39 = 2621440;
  v40 = 0x10000;
  v41 = 0x10000;
  v42 = 0x10000;
  v43 = 1;
  v44 = 0x40000;
  v45 = 0;
  v46 = 0;
  v47 = -65536;
  v48 = 8388863;
  v49 = 0;
  v50 = 0;
  v26 = SHCreateMemStream(pInit, 0x43u);
  if ( !v26 )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1515,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)0x8007000ELL,
      0);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    return v3;
  }
  v33 = 0;
  v5 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v33);
  RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                   v26,
                                   0,
                                   &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                   v5);
  v3 = RandomAccessStreamOverStream;
  if ( RandomAccessStreamOverStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1518,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)RandomAccessStreamOverStream,
      (int)v26);
    v7 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    return v3;
  }
  v32 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Storage.Streams.RandomAccessStreamReference",
         0x33u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v32);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x151B,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v26);
    v9 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    return v3;
  }
  v34 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v32 + 64LL))(v32, v33, &v34);
  v3 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x151E,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)v11,
      (int)v26);
    v12 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    return v3;
  }
  v15 = v34;
  v16 = (__int64 *)(a2 + 16);
  v17 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = *v16;
  if ( v15 )
  {
    if ( v18 )
    {
      *v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    AgileReference = RoGetAgileReference(0, &GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b, v15, a2 + 16);
    v3 = AgileReference;
    if ( AgileReference < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1520,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)AgileReference,
        (int)v26);
      v20 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      return v3;
    }
  }
  else
  {
    *v16 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v23 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x180018cb4  mov     [rsp-8+arg_0], rbx
0x180018cb9  mov     [rsp-8+arg_10], rsi
0x180018cbe  push    rbp
0x180018cbf  push    rdi
0x180018cc0  push    r14
0x180018cc2  lea     rbp, [rsp-47h]
0x180018cc7  sub     rsp, 0C0h
0x180018cce  mov     rax, cs:__security_cookie
0x180018cd5  xor     rax, rsp
0x180018cd8  mov     [rbp+57h+var_20], rax
0x180018cdc  mov     rsi, rdx
0x180018cdf  mov     qword ptr [rbp+57h+pInit], 424D42h
0x180018ce7  xor     r14d, r14d
0x180018cea  mov     [rbp+57h+var_68], 3E0000h
0x180018cf1  mov     [rbp+57h+var_64], 280000h
0x180018cf8  mov     [rbp+57h+var_60], 10000h
0x180018cff  mov     [rbp+57h+var_5C], 10000h
0x180018d06  mov     [rbp+57h+var_58], 10000h
0x180018d0d  mov     [rbp+57h+var_54], 1
0x180018d14  mov     [rbp+57h+var_50], 40000h
0x180018d1c  mov     [rbp+57h+var_48], r14
0x180018d20  mov     [rbp+57h+var_40], r14
0x180018d24  mov     [rbp+57h+var_38], 0FFFF0000h
0x180018d2b  mov     [rbp+57h+var_34], 8000FFh
0x180018d32  mov     [rbp+57h+var_30], r14w
0x180018d37  mov     [rbp+57h+var_2E], r14b
0x180018d3b  mov     [rbp+57h+var_B0], r14
0x180018d3f  lea     edx, [r14+43h]; cbInit
0x180018d43  lea     rcx, [rbp+57h+pInit]; pInit
0x180018d47  call    cs:__imp_SHCreateMemStream
0x180018d4d  mov     [rbp+57h+var_B0], rax
0x180018d51  test    rax, rax
0x180018d54  jnz     short loc_180018D95
0x180018d56  mov     rcx, [rbp+5Fh]; this
0x180018d5a  mov     ebx, 8007000Eh
0x180018d5f  mov     r9d, ebx; char *
0x180018d62  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180018d69  mov     edx, 1515h; void *
0x180018d6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d73  nop
0x180018d74  mov     rcx, [rbp+57h+var_B0]
0x180018d78  test    rcx, rcx
0x180018d7b  jz      short loc_180018D8E
0x180018d7d  mov     [rbp+57h+var_B0], r14
0x180018d81  mov     rdx, [rcx]
0x180018d84  mov     rax, [rdx+10h]
0x180018d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d8d  nop
0x180018d8e  mov     eax, ebx
0x180018d90  jmp     loc_1800190F9
0x180018d95  mov     [rbp+57h+var_A0], r14
0x180018d99  lea     rcx, [rbp+57h+var_A0]
0x180018d9d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180018da2  mov     r9, rax
0x180018da5  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180018dac  xor     edx, edx
0x180018dae  mov     rcx, [rbp+57h+var_B0]
0x180018db2  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180018db8  mov     ebx, eax
0x180018dba  test    eax, eax
0x180018dbc  jns     short loc_180018E0D
0x180018dbe  mov     rcx, [rbp+5Fh]; this
0x180018dc2  mov     r9d, eax; char *
0x180018dc5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180018dcc  mov     edx, 1518h; void *
0x180018dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018dd6  nop
0x180018dd7  mov     rcx, [rbp+57h+var_A0]
0x180018ddb  test    rcx, rcx
0x180018dde  jz      short loc_180018DF1
0x180018de0  mov     [rbp+57h+var_A0], r14
0x180018de4  mov     rax, [rcx]
0x180018de7  mov     rax, [rax+10h]
0x180018deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018df0  nop
0x180018df1  mov     rcx, [rbp+57h+var_B0]
0x180018df5  test    rcx, rcx
0x180018df8  jz      short loc_180018E0B
0x180018dfa  mov     [rbp+57h+var_B0], r14
0x180018dfe  mov     rax, [rcx]
0x180018e01  mov     rax, [rax+10h]
0x180018e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e0a  nop
0x180018e0b  jmp     short loc_180018D8E
0x180018e0d  mov     [rbp+57h+var_A8], r14
0x180018e11  lea     r9, [rbp+57h+string]; string
0x180018e15  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180018e19  mov     edx, 33h ; '3'; length
0x180018e1e  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStreamReference@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180018e25  call    cs:__imp_WindowsCreateStringReference
0x180018e2b  test    eax, eax
0x180018e2d  jns     short loc_180018E44
0x180018e2f  xor     r9d, r9d; lpArguments
0x180018e32  xor     r8d, r8d; nNumberOfArguments
0x180018e35  lea     edx, [r9+1]; dwExceptionFlags
0x180018e39  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018e3e  call    cs:__imp_RaiseException
0x180018e44  mov     rbx, [rbp+57h+string]
0x180018e48  mov     rcx, [rbp+57h+var_A8]
0x180018e4c  test    rcx, rcx
0x180018e4f  jz      short loc_180018E62
0x180018e51  mov     [rbp+57h+var_A8], r14
0x180018e55  mov     rax, [rcx]
0x180018e58  mov     rax, [rax+10h]
0x180018e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e61  nop
0x180018e62  lea     r8, [rbp+57h+var_A8]
0x180018e66  lea     rdx, _GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964
0x180018e6d  mov     rcx, rbx
0x180018e70  call    cs:__imp_RoGetActivationFactory
0x180018e76  mov     ebx, eax
0x180018e78  test    eax, eax
0x180018e7a  jns     short loc_180018EE8
0x180018e7c  mov     rcx, [rbp+5Fh]; this
0x180018e80  mov     r9d, eax; char *
0x180018e83  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180018e8a  mov     edx, 151Bh; void *
0x180018e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e94  nop
0x180018e95  mov     rcx, [rbp+57h+var_A8]
0x180018e99  test    rcx, rcx
0x180018e9c  jz      short loc_180018EAF
0x180018e9e  mov     [rbp+57h+var_A8], r14
0x180018ea2  mov     rax, [rcx]
0x180018ea5  mov     rax, [rax+10h]
0x180018ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eae  nop
0x180018eaf  mov     rcx, [rbp+57h+var_A0]
0x180018eb3  test    rcx, rcx
0x180018eb6  jz      short loc_180018EC9
0x180018eb8  mov     [rbp+57h+var_A0], r14
0x180018ebc  mov     rax, [rcx]
0x180018ebf  mov     rax, [rax+10h]
0x180018ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ec8  nop
0x180018ec9  mov     rcx, [rbp+57h+var_B0]
0x180018ecd  test    rcx, rcx
0x180018ed0  jz      short loc_180018EE3
0x180018ed2  mov     [rbp+57h+var_B0], r14
0x180018ed6  mov     rax, [rcx]
0x180018ed9  mov     rax, [rax+10h]
0x180018edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ee2  nop
0x180018ee3  jmp     loc_180018D8E
0x180018ee8  mov     [rbp+57h+var_98], r14
0x180018eec  mov     rcx, [rbp+57h+var_A8]
0x180018ef0  mov     rax, [rcx]
0x180018ef3  lea     r8, [rbp+57h+var_98]
0x180018ef7  mov     rdx, [rbp+57h+var_A0]
0x180018efb  mov     rax, [rax+40h]
0x180018eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f04  mov     ebx, eax
0x180018f06  test    eax, eax
0x180018f08  jns     loc_180018F94
0x180018f0e  mov     rcx, [rbp+5Fh]; this
0x180018f12  mov     r9d, eax; char *
0x180018f15  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180018f1c  mov     edx, 151Eh; void *
0x180018f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f26  nop
0x180018f27  mov     rcx, [rbp+57h+var_98]
0x180018f2b  test    rcx, rcx
0x180018f2e  jz      short loc_180018F41
0x180018f30  mov     [rbp+57h+var_98], r14
0x180018f34  mov     rax, [rcx]
0x180018f37  mov     rax, [rax+10h]
0x180018f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f40  nop
0x180018f41  mov     rcx, [rbp+57h+var_A8]
0x180018f45  test    rcx, rcx
0x180018f48  jz      short loc_180018F5B
0x180018f4a  mov     [rbp+57h+var_A8], r14
0x180018f4e  mov     rax, [rcx]
0x180018f51  mov     rax, [rax+10h]
0x180018f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f5a  nop
0x180018f5b  mov     rcx, [rbp+57h+var_A0]
0x180018f5f  test    rcx, rcx
0x180018f62  jz      short loc_180018F75
0x180018f64  mov     [rbp+57h+var_A0], r14
0x180018f68  mov     rax, [rcx]
0x180018f6b  mov     rax, [rax+10h]
0x180018f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f74  nop
0x180018f75  mov     rcx, [rbp+57h+var_B0]
0x180018f79  test    rcx, rcx
0x180018f7c  jz      short loc_180018F8F
0x180018f7e  mov     [rbp+57h+var_B0], r14
0x180018f82  mov     rax, [rcx]
0x180018f85  mov     rax, [rax+10h]
0x180018f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f8e  nop
0x180018f8f  jmp     loc_180018D8E
0x180018f94  mov     rdi, [rbp+57h+var_98]
0x180018f98  lea     rbx, [rsi+10h]
0x180018f9c  mov     rcx, [rbx]
0x180018f9f  mov     [rbx], r14
0x180018fa2  test    rcx, rcx
0x180018fa5  jz      short loc_180018FB4
0x180018fa7  mov     rax, [rcx]
0x180018faa  mov     rax, [rax+10h]
0x180018fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb3  nop
0x180018fb4  mov     rcx, [rbx]
0x180018fb7  test    rdi, rdi
0x180018fba  jz      loc_18001907A
0x180018fc0  test    rcx, rcx
0x180018fc3  jz      short loc_180018FD5
0x180018fc5  mov     [rbx], r14
0x180018fc8  mov     rax, [rcx]
0x180018fcb  mov     rax, [rax+10h]
0x180018fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fd4  nop
0x180018fd5  mov     r9, rbx
0x180018fd8  mov     r8, rdi
0x180018fdb  lea     rdx, _GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b
0x180018fe2  xor     ecx, ecx
0x180018fe4  call    cs:__imp_RoGetAgileReference
0x180018fea  mov     ebx, eax
0x180018fec  test    eax, eax
0x180018fee  jns     loc_18001908F
0x180018ff4  mov     rcx, [rbp+5Fh]; this
0x180018ff8  mov     r9d, eax; char *
0x180018ffb  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180019002  mov     edx, 1520h; void *
0x180019007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001900c  nop
0x18001900d  mov     rcx, [rbp+57h+var_98]
0x180019011  test    rcx, rcx
0x180019014  jz      short loc_180019027
0x180019016  mov     [rbp+57h+var_98], r14
0x18001901a  mov     rax, [rcx]
0x18001901d  mov     rax, [rax+10h]
0x180019021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019026  nop
0x180019027  mov     rcx, [rbp+57h+var_A8]
0x18001902b  test    rcx, rcx
0x18001902e  jz      short loc_180019041
0x180019030  mov     [rbp+57h+var_A8], r14
0x180019034  mov     rax, [rcx]
0x180019037  mov     rax, [rax+10h]
0x18001903b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019040  nop
0x180019041  mov     rcx, [rbp+57h+var_A0]
0x180019045  test    rcx, rcx
0x180019048  jz      short loc_18001905B
0x18001904a  mov     [rbp+57h+var_A0], r14
0x18001904e  mov     rax, [rcx]
0x180019051  mov     rax, [rax+10h]
0x180019055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001905a  nop
0x18001905b  mov     rcx, [rbp+57h+var_B0]
0x18001905f  test    rcx, rcx
0x180019062  jz      short loc_180019075
0x180019064  mov     [rbp+57h+var_B0], r14
0x180019068  mov     rax, [rcx]
0x18001906b  mov     rax, [rax+10h]
0x18001906f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019074  nop
0x180019075  jmp     loc_180018D8E
0x18001907a  mov     [rbx], r14
0x18001907d  test    rcx, rcx
0x180019080  jz      short loc_18001908F
0x180019082  mov     rax, [rcx]
0x180019085  mov     rax, [rax+10h]
0x180019089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001908e  nop
0x18001908f  mov     rcx, [rbp+57h+var_98]
0x180019093  test    rcx, rcx
0x180019096  jz      short loc_1800190A9
0x180019098  mov     [rbp+57h+var_98], r14
0x18001909c  mov     rax, [rcx]
0x18001909f  mov     rax, [rax+10h]
0x1800190a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190a8  nop
0x1800190a9  mov     rcx, [rbp+57h+var_A8]
0x1800190ad  test    rcx, rcx
0x1800190b0  jz      short loc_1800190C3
0x1800190b2  mov     [rbp+57h+var_A8], r14
0x1800190b6  mov     rax, [rcx]
0x1800190b9  mov     rax, [rax+10h]
0x1800190bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c2  nop
0x1800190c3  mov     rcx, [rbp+57h+var_A0]
0x1800190c7  test    rcx, rcx
0x1800190ca  jz      short loc_1800190DD
0x1800190cc  mov     [rbp+57h+var_A0], r14
0x1800190d0  mov     rax, [rcx]
0x1800190d3  mov     rax, [rax+10h]
0x1800190d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190dc  nop
0x1800190dd  mov     rcx, [rbp+57h+var_B0]
0x1800190e1  test    rcx, rcx
0x1800190e4  jz      short loc_1800190F7
0x1800190e6  mov     [rbp+57h+var_B0], r14
0x1800190ea  mov     rax, [rcx]
0x1800190ed  mov     rax, [rax+10h]
0x1800190f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f6  nop
0x1800190f7  xor     eax, eax
  ... truncated ...
```
