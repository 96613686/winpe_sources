# LiteCryptUtilities::ComputeHash(uchar const *,ulong,uchar const *,ulong,ulong,uchar * *,ulong *,ushort const *)

- ea: `0x180009858`
- end: `0x180009b5e`
- name: `?ComputeHash@LiteCryptUtilities@@YAJPEBEK0KKPEAPEAEPEAKPEBG@Z`
- size: `774`
- prototype: `int(LiteCryptUtilities *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 **, unsigned int *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800765e0`
- `0x18009ace8`
- `0x1800cbe70`
- `0x180108258`

## callees

- `0x180009858`
- `0x180009f00`
- `0x18000a354`
- `0x18000a36c`
- `0x18000a45c`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180112304`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800099a0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180009937`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180009937`
- `bcrypt!BCryptGetProperty` at `0x18000997d`
- `bcrypt!BCryptGetProperty` at `0x18000997d`
- `bcrypt!BCryptCreateHash` at `0x1800099d6`
- `bcrypt!BCryptCreateHash` at `0x1800099d6`
- `bcrypt!BCryptHashData` at `0x180009a06`
- `bcrypt!BCryptHashData` at `0x180009a06`
- `bcrypt!BCryptFinishHash` at `0x180009a30`
- `bcrypt!BCryptFinishHash` at `0x180009a30`

## string_xrefs

- `0x1800098ae`: `LiteCryptUtilities::ComputeHash`
- `0x180009a74`: `LiteCryptUtilities::ComputeHash`
- `0x180009ad3`: `LiteCryptUtilities::ComputeHash`
- `0x180009abe`: `hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spAlgorithm, pAlgId, nullptr, providerFlags))`
- `0x180009aff`: `hr = HRESULT_FROM_WIN32(::BCryptCreateHash( spAlgorithm, &spHash, nullptr, 0, static_cast<PUCHAR>(const_cast<BYTE*>(pKey)), static_cast<ULONG>(keySizeBytes), 0))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LiteCryptUtilities::ComputeHash(
        UCHAR *this,
        const unsigned __int8 *a2,
        UCHAR *a3,
        const unsigned __int8 *a4,
        ULONG dwFlags,
        UCHAR **a6,
        unsigned __int8 **a7,
        const WCHAR *pszAlgId)
{
  ULONG cbSecret; // r15d
  ULONG v10; // r13d
  unsigned __int64 v11; // r14
  PPTraceStatus *v12; // rcx
  PPTraceStatus *v13; // rcx
  bool v14; // bl
  int Property; // eax
  UCHAR *v16; // rbx
  unsigned int v17; // ebx
  unsigned int v19; // r8d
  ULONG *pcbResult; // [rsp+20h] [rbp-A1h]
  const char *pcbResulta; // [rsp+20h] [rbp-A1h]
  int v22; // [rsp+40h] [rbp-81h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-7Dh] BYREF
  ULONG v24; // [rsp+48h] [rbp-79h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm[3]; // [rsp+50h] [rbp-71h] BYREF
  BCRYPT_HASH_HANDLE phHash[3]; // [rsp+68h] [rbp-59h] BYREF
  UCHAR *v27; // [rsp+80h] [rbp-41h] BYREF
  __int64 v28; // [rsp+88h] [rbp-39h]
  __int64 v29; // [rsp+90h] [rbp-31h]
  _QWORD v30[13]; // [rsp+98h] [rbp-29h] BYREF

  cbSecret = (unsigned int)a4;
  v10 = (unsigned int)a2;
  v22 = 0;
  v24 = 0;
  *(_DWORD *)pbOutput = 0;
  v27 = 0;
  v29 = 0;
  v28 = 0;
  memset(phHash, 0, sizeof(phHash));
  memset(phAlgorithm, 0, sizeof(phAlgorithm));
  v30[0] = "LiteCryptUtilities::ComputeHash";
  v30[1] = &v22;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::ComputeHash",
    (const char *)0x52B,
    0,
    (const unsigned __int16 *)pcbResult);
  v11 = 10;
  v14 = 1;
  if ( PPTraceStatus::GetAssertFlag(v12) != 1 )
    v14 = PPTraceStatus::GetAssertFlag(v13) == 2;
  if ( !v14 )
    v11 = -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0) & 0xA;
  *a6 = 0;
  *(_DWORD *)a7 = 0;
  Property = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, dwFlags);
  if ( Property > 0 )
    Property = (unsigned __int16)Property | 0x80070000;
  v22 = Property;
  if ( Property < 0 )
  {
    pcbResulta = "hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spAlgorithm, pAlgId, nullptr, providerFlags))";
    v19 = 1342;
LABEL_24:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::ComputeHash",
      v19,
      Property,
      pcbResulta);
    goto LABEL_22;
  }
  Property = BCryptGetProperty(phAlgorithm[0], L"HashDigestLength", pbOutput, 4u, &v24, 0);
  if ( Property > 0 )
    Property = (unsigned __int16)Property | 0x80070000;
  v22 = Property;
  if ( Property < 0 )
  {
    pcbResulta = "hr = HRESULT_FROM_WIN32(::BCryptGetProperty( spAlgorithm, BCRYPT_HASH_LENGTH, reinterpret_cast<PUCHAR>("
                 "&hashBlobSizeBytes), sizeof(hashBlobSizeBytes), &resultSizeBytes, 0))";
    v19 = 1350;
    goto LABEL_24;
  }
  v16 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
  v27 = v16;
  if ( !v16 )
  {
    v22 = -2147024882;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::ComputeHash",
      0x54Bu,
      -2147024882,
      "hr = E_OUTOFMEMORY");
    goto LABEL_22;
  }
  Property = BCryptCreateHash(phAlgorithm[0], phHash, 0, 0, a3, cbSecret, 0);
  if ( Property > 0 )
    Property = (unsigned __int16)Property | 0x80070000;
  v22 = Property;
  if ( Property < 0 )
  {
    pcbResulta = "hr = HRESULT_FROM_WIN32(::BCryptCreateHash( spAlgorithm, &spHash, nullptr, 0, static_cast<PUCHAR>(const"
                 "_cast<BYTE*>(pKey)), static_cast<ULONG>(keySizeBytes), 0))";
    v19 = 1365;
    goto LABEL_24;
  }
  Property = BCryptHashData(phHash[0], this, v10, 0);
  if ( Property > 0 )
    Property = (unsigned __int16)Property | 0x80070000;
  v22 = Property;
  if ( Property < 0 )
  {
    pcbResulta = "hr = HRESULT_FROM_WIN32(::BCryptHashData( spHash, static_cast<PUCHAR>(const_cast<BYTE*>(pMessage)), mes"
                 "sageSizeBytes, 0))";
    v19 = 1371;
    goto LABEL_24;
  }
  Property = BCryptFinishHash(phHash[0], v16, *(ULONG *)pbOutput, 0);
  if ( Property > 0 )
    Property = (unsigned __int16)Property | 0x80070000;
  v22 = Property;
  if ( Property < 0 )
  {
    pcbResulta = "hr = HRESULT_FROM_WIN32(::BCryptFinishHash( spHash, reinterpret_cast<PUCHAR>(static_cast<BYTE*>(spHashB"
                 "lob)), hashBlobSizeBytes, 0))";
    v19 = 1377;
    goto LABEL_24;
  }
  v27 = 0;
  v28 = 0;
  *a6 = v16;
  *(_DWORD *)a7 = *(_DWORD *)pbOutput;
LABEL_22:
  v17 = v22;
  ErrorVerifier::CheckAgainstList("LiteCryptUtilities::ComputeHash", v22, v11, &qword_180135B48);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v30);
  Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(phAlgorithm);
  Auto<void *,BCryptHashFunctor<void *>,DummyContext>::~Auto<void *,BCryptHashFunctor<void *>,DummyContext>(phHash);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v27);
  return v17;
}

```

## disassembly

```asm
0x180009858  mov     [rsp-8+pbInput], rcx
0x18000985d  push    rbp
0x18000985e  push    rbx
0x18000985f  push    rsi
0x180009860  push    rdi
0x180009861  push    r12
0x180009863  push    r13
0x180009865  push    r14
0x180009867  push    r15
0x180009869  lea     rbp, [rsp-7]
0x18000986e  sub     rsp, 0C8h
0x180009875  mov     r15d, r9d
0x180009878  mov     r12, r8
0x18000987b  mov     r13d, edx
0x18000987e  xor     esi, esi
0x180009880  mov     [rsp+100h+var_C0], esi
0x180009884  mov     [rbp+3Fh+var_B8], esi
0x180009887  mov     dword ptr [rbp+3Fh+pbOutput], esi
0x18000988a  mov     [rbp+3Fh+var_80], rsi
0x18000988e  mov     [rbp+3Fh+var_70], rsi
0x180009892  mov     [rbp+3Fh+var_78], rsi
0x180009896  mov     [rbp+3Fh+phHash], rsi
0x18000989a  mov     [rbp+3Fh+var_88], rsi
0x18000989e  mov     [rbp+3Fh+var_90], rsi
0x1800098a2  mov     [rbp+3Fh+phAlgorithm], rsi
0x1800098a6  mov     [rbp+3Fh+var_A0], rsi
0x1800098aa  mov     [rbp+3Fh+var_A8], rsi
0x1800098ae  lea     rcx, aLitecryptutili_9; "LiteCryptUtilities::ComputeHash"
0x1800098b5  mov     [rbp+3Fh+var_68], rcx
0x1800098b9  lea     rax, [rsp+100h+var_C0]
0x1800098be  mov     [rbp+3Fh+var_60], rax
0x1800098c2  mov     [rbp+3Fh+var_58], rsi
0x1800098c6  mov     [rbp+3Fh+var_50], rsi
0x1800098ca  xor     r9d, r9d; unsigned int
0x1800098cd  mov     r8d, 52Bh; char *
0x1800098d3  mov     rdx, rcx; char *
0x1800098d6  lea     rcx, aOnecoreuapDsEx_59; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800098dd  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800098e2  nop
0x1800098e3  lea     r14d, [rsi+0Ah]
0x1800098e7  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800098ec  lea     ebx, [rsi+1]
0x1800098ef  cmp     eax, ebx
0x1800098f1  jz      short loc_180009900
0x1800098f3  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800098f8  cmp     eax, 2
0x1800098fb  jz      short loc_180009900
0x1800098fd  mov     bl, sil
0x180009900  test    bl, bl
0x180009902  jnz     short loc_180009914
0x180009904  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x18000990a  and     al, 20h
0x18000990c  neg     al
0x18000990e  sbb     rax, rax
0x180009911  and     r14, rax
0x180009914  mov     rdi, [rbp+3Fh+arg_28]
0x180009918  mov     [rdi], rsi
0x18000991b  mov     rsi, [rbp+3Fh+arg_30]
0x18000991f  mov     dword ptr [rsi], 0
0x180009925  mov     r9d, [rbp+3Fh+dwFlags]; dwFlags
0x180009929  xor     r8d, r8d; pszImplementation
0x18000992c  mov     rdx, [rbp+3Fh+pszAlgId]; pszAlgId
0x180009933  lea     rcx, [rbp+3Fh+phAlgorithm]; phAlgorithm
0x180009937  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000993d  mov     ebx, 80070000h
0x180009942  test    eax, eax
0x180009944  jle     short loc_18000994B
0x180009946  movzx   eax, ax
0x180009949  or      eax, ebx
0x18000994b  mov     [rsp+100h+var_C0], eax
0x18000994f  test    eax, eax
0x180009951  js      loc_180009ABE
0x180009957  mov     [rsp+100h+cbSecret], 0; dwFlags
0x18000995f  lea     rax, [rbp+3Fh+var_B8]
0x180009963  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180009968  mov     r9d, 4; cbOutput
0x18000996e  lea     r8, [rbp+3Fh+pbOutput]; pbOutput
0x180009972  lea     rdx, pszProperty; "HashDigestLength"
0x180009979  mov     rcx, [rbp+3Fh+phAlgorithm]; hObject
0x18000997d  call    cs:__imp_BCryptGetProperty
0x180009983  test    eax, eax
0x180009985  jle     short loc_18000998C
0x180009987  movzx   eax, ax
0x18000998a  or      eax, ebx
0x18000998c  mov     [rsp+100h+var_C0], eax
0x180009990  test    eax, eax
0x180009992  js      loc_180009AEB
0x180009998  mov     edx, dword ptr [rbp+3Fh+pbOutput]; uBytes
0x18000999b  mov     ecx, 40h ; '@'; uFlags
0x1800099a0  call    cs:__imp_LocalAlloc
0x1800099a6  mov     rbx, rax
0x1800099a9  mov     [rbp+3Fh+var_80], rax
0x1800099ad  test    rax, rax
0x1800099b0  jz      loc_180009B13
0x1800099b6  mov     [rsp+100h+var_D0], 0; dwFlags
0x1800099be  mov     [rsp+100h+cbSecret], r15d; cbSecret
0x1800099c3  mov     [rsp+100h+pcbResult], r12; pbSecret
0x1800099c8  xor     r9d, r9d; cbHashObject
0x1800099cb  xor     r8d, r8d; pbHashObject
0x1800099ce  lea     rdx, [rbp+3Fh+phHash]; phHash
0x1800099d2  mov     rcx, [rbp+3Fh+phAlgorithm]; hAlgorithm
0x1800099d6  call    cs:__imp_BCryptCreateHash
0x1800099dc  mov     r15d, 80070000h
0x1800099e2  test    eax, eax
0x1800099e4  jle     short loc_1800099EC
0x1800099e6  movzx   eax, ax
0x1800099e9  or      eax, r15d
0x1800099ec  mov     [rsp+100h+var_C0], eax
0x1800099f0  test    eax, eax
0x1800099f2  js      loc_180009AFF
0x1800099f8  xor     r9d, r9d; dwFlags
0x1800099fb  mov     r8d, r13d; cbInput
0x1800099fe  mov     rdx, [rbp+3Fh+pbInput]; pbInput
0x180009a02  mov     rcx, [rbp+3Fh+phHash]; hHash
0x180009a06  call    cs:__imp_BCryptHashData
0x180009a0c  test    eax, eax
0x180009a0e  jle     short loc_180009A16
0x180009a10  movzx   eax, ax
0x180009a13  or      eax, r15d
0x180009a16  mov     [rsp+100h+var_C0], eax
0x180009a1a  test    eax, eax
0x180009a1c  js      loc_180009B32
0x180009a22  xor     r9d, r9d; dwFlags
0x180009a25  mov     r8d, dword ptr [rbp+3Fh+pbOutput]; cbOutput
0x180009a29  mov     rdx, rbx; pbOutput
0x180009a2c  mov     rcx, [rbp+3Fh+phHash]; hHash
0x180009a30  call    cs:__imp_BCryptFinishHash
0x180009a36  test    eax, eax
0x180009a38  jle     short loc_180009A40
0x180009a3a  movzx   eax, ax
0x180009a3d  or      eax, r15d
0x180009a40  mov     [rsp+100h+var_C0], eax
0x180009a44  test    eax, eax
0x180009a46  js      loc_180009B46
0x180009a4c  mov     [rbp+3Fh+var_80], 0
0x180009a54  mov     [rbp+3Fh+var_78], 0
0x180009a5c  mov     [rdi], rbx
0x180009a5f  mov     eax, dword ptr [rbp+3Fh+pbOutput]
0x180009a62  mov     [rsi], eax
0x180009a64  mov     ebx, [rsp+100h+var_C0]
0x180009a68  lea     r9, qword_180135B48; int *
0x180009a6f  mov     r8, r14; unsigned __int64
0x180009a72  mov     edx, ebx; int
0x180009a74  lea     rcx, aLitecryptutili_9; "LiteCryptUtilities::ComputeHash"
0x180009a7b  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180009a80  nop
0x180009a81  lea     rcx, [rbp+3Fh+var_68]
0x180009a85  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180009a8a  nop
0x180009a8b  lea     rcx, [rbp+3Fh+phAlgorithm]
0x180009a8f  call    ??1?$Auto@PEAXV?$BCryptAlgFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(void)
0x180009a94  nop
0x180009a95  lea     rcx, [rbp+3Fh+phHash]
0x180009a99  call    ??1?$Auto@PEAXV?$BCryptHashFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptHashFunctor<void *>,DummyContext>::~Auto<void *,BCryptHashFunctor<void *>,DummyContext>(void)
0x180009a9e  nop
0x180009a9f  lea     rcx, [rbp+3Fh+var_80]
0x180009aa3  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180009aa8  mov     eax, ebx
0x180009aaa  add     rsp, 0C8h
0x180009ab1  pop     r15
0x180009ab3  pop     r14
0x180009ab5  pop     r13
0x180009ab7  pop     r12
0x180009ab9  pop     rdi
0x180009aba  pop     rsi
0x180009abb  pop     rbx
0x180009abc  pop     rbp
0x180009abd  retn
0x180009abe  lea     rdx, aHrHresultFromW_3; "hr = HRESULT_FROM_WIN32(::BCryptOpenAlg"...
0x180009ac5  mov     [rsp+100h+pcbResult], rdx; char *
0x180009aca  mov     r8d, 53Eh; unsigned int
0x180009ad0  mov     r9d, eax; int
0x180009ad3  lea     rdx, aLitecryptutili_9; "LiteCryptUtilities::ComputeHash"
0x180009ada  lea     rcx, aOnecoreuapDsEx_59; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180009ae1  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180009ae6  jmp     loc_180009A64
0x180009aeb  lea     rcx, aHrHresultFromW_29; "hr = HRESULT_FROM_WIN32(::BCryptGetProp"...
0x180009af2  mov     [rsp+100h+pcbResult], rcx
0x180009af7  mov     r8d, 546h
0x180009afd  jmp     short loc_180009AD0
0x180009aff  lea     rcx, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(::BCryptCreateH"...
0x180009b06  mov     [rsp+100h+pcbResult], rcx
0x180009b0b  mov     r8d, 555h
0x180009b11  jmp     short loc_180009AD0
0x180009b13  mov     r9d, 8007000Eh
0x180009b19  mov     [rsp+100h+var_C0], r9d
0x180009b1e  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180009b25  mov     [rsp+100h+pcbResult], rax
0x180009b2a  mov     r8d, 54Bh
0x180009b30  jmp     short loc_180009AD3
0x180009b32  lea     rcx, aHrHresultFromW_6; "hr = HRESULT_FROM_WIN32(::BCryptHashDat"...
0x180009b39  mov     [rsp+100h+pcbResult], rcx
0x180009b3e  mov     r8d, 55Bh
0x180009b44  jmp     short loc_180009AD0
0x180009b46  lea     rcx, aHrHresultFromW_16; "hr = HRESULT_FROM_WIN32(::BCryptFinishH"...
0x180009b4d  mov     [rsp+100h+pcbResult], rcx
0x180009b52  mov     r8d, 561h
0x180009b58  jmp     loc_180009AD0
```
