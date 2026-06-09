# MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds(ushort const *,int *)

- ea: `0x180003f50`
- end: `0x1800041bd`
- name: `?IsIdentityEligibleForTargetedAds@MicrosoftAccountChildInfoImplementation@@UEAAJPEBGPEAH@Z`
- size: `621`
- prototype: `int(MicrosoftAccountChildInfoImplementation *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003f50`
- `0x1800041c4`
- `0x180004a7c`
- `0x180005398`
- `0x180005458`
- `0x1800090c0`
- `0x180009630`
- `0x18000a300`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800040dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800041b1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800040dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800041b1`

## string_xrefs

- `0x180003f90`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds`
- `0x1800040f1`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds`
- `0x18000410d`: `MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds(
        MicrosoftAccountChildInfoImplementation *this,
        const unsigned __int16 *a2,
        int *a3)
{
  unsigned __int64 v5; // rdi
  PPTraceStatus *v6; // rcx
  char v7; // al
  MicrosoftAccountChildInfoImplementation *v8; // rcx
  unsigned int v9; // ebx
  PPTraceStatus *v10; // rcx
  bool v12; // zf
  PPTraceStatus *v13; // rcx
  PPTraceStatus *v14; // rcx
  int *v15; // [rsp+20h] [rbp-168h]
  int v16; // [rsp+30h] [rbp-158h] BYREF
  __int64 *v17; // [rsp+38h] [rbp-150h]
  unsigned __int64 v18; // [rsp+40h] [rbp-148h]
  int *v19; // [rsp+48h] [rbp-140h]
  const char *v20; // [rsp+50h] [rbp-138h]
  _QWORD v21[4]; // [rsp+58h] [rbp-130h] BYREF
  CPassportException *v22; // [rsp+78h] [rbp-110h] BYREF
  ATL::CAtlException *v23; // [rsp+80h] [rbp-108h] BYREF
  void **v24; // [rsp+90h] [rbp-F8h] BYREF
  _BYTE v25[72]; // [rsp+98h] [rbp-F0h] BYREF
  _BYTE v26[144]; // [rsp+E0h] [rbp-A8h] BYREF
  int IsIdentityEligibleForTargetedAdsInternal; // [rsp+1A8h] [rbp+20h] BYREF

  v5 = 0;
  IsIdentityEligibleForTargetedAdsInternal = 0;
  v17 = qword_1800630A0;
  v18 = 5;
  v19 = &IsIdentityEligibleForTargetedAdsInternal;
  v20 = "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds";
  if ( PPTraceStatus::GetAssertFlag(this) == 1 || (v12 = PPTraceStatus::GetAssertFlag(v6) == 2, v7 = 0, v12) )
    v7 = 1;
  if ( !v7 )
    v18 &= -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0);
  IdentityProviderExecutionContext::IdentityProviderExecutionContext((IdentityProviderExecutionContext *)v26);
  v24 = &IdentityStorageFunctions::`vftable';
  ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v25);
  v21[0] = "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds";
  v21[1] = &IsIdentityEligibleForTargetedAdsInternal;
  v21[2] = 0;
  v21[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\microsoftaccountchildinfoimplementation.cpp",
    "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds",
    (const char *)0x44,
    0,
    (const unsigned __int16 *)v15);
  try
  {
    IsIdentityEligibleForTargetedAdsInternal = MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal(
                                                 v8,
                                                 (struct IIdentityProviderExecutionContext *)v26,
                                                 (struct IIdentityStorageFunctions *)&v24,
                                                 a2,
                                                 a3);
    CTraceFuncW<long>::~CTraceFuncW<long>(v21);
  }
  catch ( CPassportException *v22 )
  {
    v14 = (PPTraceStatus *)*((unsigned int *)v22 + 2);
    IsIdentityEligibleForTargetedAdsInternal = (int)v14;
    if ( (int)v14 >= 0 )
      IsIdentityEligibleForTargetedAdsInternal = -2147418113;
    v5 = 0;
  }
  catch ( ATL::CAtlException *v23 )
  {
    v14 = (PPTraceStatus *)*(unsigned int *)v23;
    IsIdentityEligibleForTargetedAdsInternal = (int)v14;
    if ( (int)v14 >= 0 )
      IsIdentityEligibleForTargetedAdsInternal = -2147418113;
    v5 = 0;
  }
  catch ( std::bad_alloc )
  {
    IsIdentityEligibleForTargetedAdsInternal = -2147024882;
    v5 = 0;
    v9 = -2147024882;
    goto LABEL_8;
  }
  catch ( long v16 )
  {
    IsIdentityEligibleForTargetedAdsInternal = v16;
    if ( v16 >= 0 )
      IsIdentityEligibleForTargetedAdsInternal = -2147418113;
    v5 = 0;
  }
  v9 = IsIdentityEligibleForTargetedAdsInternal;
  if ( IsIdentityEligibleForTargetedAdsInternal == -2147024883 )
  {
    v9 = -2147023728;
    IsIdentityEligibleForTargetedAdsInternal = -2147023728;
  }
LABEL_8:
  if ( v9 && v18 )
  {
    if ( PPTraceStatus::GetAssertFlag(v14) == 2
      && (v9 == -2147024890
       || v9 == -2147023834
       || v9 == -2147023179
       || v9 == -2147023174
       || v9 == -2147023173
       || v9 == -2147023170
       || v9 == -2147023143) )
    {
      if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
        McTemplateU0sd_EventWriteTransfer(
          v10,
          Telemetry_ErrorVerifier,
          "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds",
          v9);
      DebugBreak();
    }
    while ( v5 < v18 )
    {
      if ( v9 == *((_DWORD *)qword_1800630A0 + v5) )
        return v9;
      ++v5;
    }
    if ( (Microsoft_Windows_LiveIdEnableBits & 0x20) != 0 )
      McTemplateU0sd_EventWriteTransfer(
        v10,
        Telemetry_ErrorVerifier,
        "MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAds",
        v9);
    if ( PPTraceStatus::GetAssertFlag(v10) == 1 || PPTraceStatus::GetAssertFlag(v13) == 2 )
      DebugBreak();
  }
  return v9;
}

```

## disassembly

```asm
0x180003f50  mov     rax, rsp
0x180003f53  mov     [rax+8], rbx
0x180003f57  mov     [rax+10h], rsi
0x180003f5b  push    rdi
0x180003f5c  push    r14
0x180003f5e  push    r15
0x180003f60  sub     rsp, 170h
0x180003f67  mov     rbx, r8
0x180003f6a  mov     r15, rdx
0x180003f6d  xor     edi, edi
0x180003f6f  mov     [rax+20h], edi
0x180003f72  lea     r14, qword_1800630A0
0x180003f79  mov     [rsp+188h+var_150], r14
0x180003f7e  mov     [rsp+188h+var_148], 5
0x180003f87  lea     rax, [rax+20h]
0x180003f8b  mov     [rsp+188h+var_140], rax
0x180003f90  lea     rsi, aMicrosoftaccou; "MicrosoftAccountChildInfoImplementation"...
0x180003f97  mov     [rsp+188h+var_138], rsi
0x180003f9c  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x180003fa1  cmp     eax, 1
0x180003fa4  jnz     loc_18000409A
0x180003faa  mov     al, 1
0x180003fac  test    al, al
0x180003fae  jz      loc_1800040B0
0x180003fb4  lea     rcx, [rsp+188h+var_A8]; this
0x180003fbc  call    ??0IdentityProviderExecutionContext@@QEAA@XZ; IdentityProviderExecutionContext::IdentityProviderExecutionContext(void)
0x180003fc1  nop
0x180003fc2  lea     rax, ??_7IdentityStorageFunctions@@6B@; const IdentityStorageFunctions::`vftable'
0x180003fc9  mov     [rsp+188h+var_F8], rax
0x180003fd1  lea     rcx, [rsp+188h+var_F0]; this
0x180003fd9  call    ??0ExecutionContextLite@@QEAA@XZ; ExecutionContextLite::ExecutionContextLite(void)
0x180003fde  nop
0x180003fdf  mov     [rsp+188h+var_130], rsi
0x180003fe4  lea     rax, [rsp+188h+arg_18]
0x180003fec  mov     [rsp+188h+var_128], rax
0x180003ff1  mov     [rsp+188h+var_120], rdi
0x180003ff6  mov     [rsp+188h+var_118], rdi
0x180003ffb  xor     r9d, r9d; unsigned int
0x180003ffe  lea     r8d, [r9+44h]; char *
0x180004002  mov     rdx, rsi; char *
0x180004005  lea     rcx, aOnecoreuapDsEx_27; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000400c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180004011  nop
0x180004012  mov     [rsp+188h+var_168], rbx; int *
0x180004017  mov     r9, r15; unsigned __int16 *
0x18000401a  lea     r8, [rsp+188h+var_F8]; struct IIdentityStorageFunctions *
0x180004022  lea     rdx, [rsp+188h+var_A8]; struct IIdentityProviderExecutionContext *
0x18000402a  call    ?IsIdentityEligibleForTargetedAdsInternal@MicrosoftAccountChildInfoImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEAVIIdentityStorageFunctions@@PEBGPEAH@Z; MicrosoftAccountChildInfoImplementation::IsIdentityEligibleForTargetedAdsInternal(IIdentityProviderExecutionContext *,IIdentityStorageFunctions *,ushort const *,int *)
0x18000402f  mov     [rsp+188h+arg_18], eax
0x180004036  lea     rcx, [rsp+188h+var_130]
0x18000403b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180004040  nop
0x180004041  mov     ebx, [rsp+188h+arg_18]
0x180004048  cmp     ebx, 8007000Dh
0x18000404e  jz      loc_180004119
0x180004054  test    ebx, ebx
0x180004056  jz      short loc_18000407F
0x180004058  cmp     [rsp+188h+var_148], rdi
0x18000405d  jz      short loc_18000407F
0x18000405f  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x180004064  cmp     eax, 2
0x180004067  jz      short loc_1800040C7
0x180004069  cmp     rdi, [rsp+188h+var_148]
0x18000406e  jnb     loc_18000417E
0x180004074  cmp     ebx, [r14+rdi*4]
0x180004078  jz      short loc_18000407F
0x18000407a  inc     rdi
0x18000407d  jmp     short loc_180004069
0x18000407f  mov     eax, ebx
0x180004081  lea     r11, [rsp+188h+var_18]
0x180004089  mov     rbx, [r11+20h]
0x18000408d  mov     rsi, [r11+28h]
0x180004091  mov     rsp, r11
0x180004094  pop     r15
0x180004096  pop     r14
0x180004098  pop     rdi
0x180004099  retn
0x18000409a  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x18000409f  cmp     eax, 2
0x1800040a2  mov     al, dil
0x1800040a5  jnz     loc_180003FAC
0x1800040ab  jmp     loc_180003FAA
0x1800040b0  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x1800040b6  and     al, 20h
0x1800040b8  neg     al
0x1800040ba  sbb     rax, rax
0x1800040bd  and     [rsp+188h+var_148], rax
0x1800040c2  jmp     loc_180003FB4
0x1800040c7  cmp     ebx, 80070006h
0x1800040cd  jnz     short loc_18000412A
0x1800040cf  test    cs:Microsoft_Windows_LiveIdEnableBits, 20h
0x1800040d6  jnz     loc_180004167
0x1800040dc  call    cs:__imp_DebugBreak
0x1800040e2  jmp     short loc_180004069
0x1800040e4  jmp     short loc_180004104
0x1800040e6  jmp     short loc_180004104
0x1800040e8  xor     edi, edi
0x1800040ea  lea     r14, qword_1800630A0
0x1800040f1  lea     rsi, aMicrosoftaccou; "MicrosoftAccountChildInfoImplementation"...
0x1800040f8  mov     ebx, [rsp+188h+arg_18]
0x1800040ff  jmp     loc_180004054
0x180004104  xor     edi, edi
0x180004106  lea     r14, qword_1800630A0
0x18000410d  lea     rsi, aMicrosoftaccou; "MicrosoftAccountChildInfoImplementation"...
0x180004114  jmp     loc_180004041
0x180004119  mov     ebx, 80070490h
0x18000411e  mov     [rsp+188h+arg_18], ebx
0x180004125  jmp     loc_180004054
0x18000412a  cmp     ebx, 80070426h
0x180004130  jz      short loc_1800040CF
0x180004132  cmp     ebx, 800706B5h
0x180004138  jz      short loc_1800040CF
0x18000413a  cmp     ebx, 800706BAh
0x180004140  jz      short loc_1800040CF
0x180004142  cmp     ebx, 800706BBh
0x180004148  jz      short loc_1800040CF
0x18000414a  cmp     ebx, 800706BEh
0x180004150  jz      loc_1800040CF
0x180004156  cmp     ebx, 800706D9h
0x18000415c  jnz     loc_180004069
0x180004162  jmp     loc_1800040CF
0x180004167  mov     r9d, ebx
0x18000416a  mov     r8, rsi
0x18000416d  lea     rdx, Telemetry_ErrorVerifier
0x180004174  call    McTemplateU0sd_EventWriteTransfer
0x180004179  jmp     loc_1800040DC
0x18000417e  test    cs:Microsoft_Windows_LiveIdEnableBits, 20h
0x180004185  jz      short loc_180004199
0x180004187  mov     r9d, ebx
0x18000418a  mov     r8, rsi
0x18000418d  lea     rdx, Telemetry_ErrorVerifier
0x180004194  call    McTemplateU0sd_EventWriteTransfer
0x180004199  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x18000419e  cmp     eax, 1
0x1800041a1  jz      short loc_1800041B1
0x1800041a3  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800041a8  cmp     eax, 2
0x1800041ab  jnz     loc_18000407F
0x1800041b1  call    cs:__imp_DebugBreak
0x1800041b7  jmp     loc_18000407F
```
