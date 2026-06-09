# MSACredentialManagerImplementation::GetAuthBufferInternal(IAuthBufferExecutionContext *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,uchar * *,ulong *)

- ea: `0x1800332a0`
- end: `0x18003388a`
- name: `?GetAuthBufferInternal@MSACredentialManagerImplementation@@EEAAJPEAVIAuthBufferExecutionContext@@PEBG111111HKPEAPEAEPEAK@Z`
- size: `1514`
- prototype: `int(MSACredentialManagerImplementation *__hidden this, struct IAuthBufferExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x180005458`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180010b80`
- `0x180015238`
- `0x1800189f4`
- `0x180018a0c`
- `0x1800332a0`
- `0x1800343d4`
- `0x180034fb4`
- `0x18004c46c`
- `0x18004c704`
- `0x180058010`

## string_xrefs

- `0x180033627`: `IsNullOrEmpty(daToken)`
- `0x180033652`: `IsNullOrEmpty(daTokenCreationTime)`
- `0x18003366c`: `IsNullOrEmpty(daTokenExpiryTime)`
- `0x1800336ae`: `IsNullOrEmpty(flowToken)`
- `0x180033414`: `hr = GetStringLengthCharacters(daToken, daTokenLength)`
- `0x18003344f`: `hr = GetStringLengthCharacters(daTokenCreationTime, daTokenCreationTimeLength)`
- `0x180033471`: `hr = GetStringLengthCharacters(daTokenExpiryTime, daTokenExpiryTimeLength)`
- `0x1800334d6`: `hr = GetStringLengthCharacters(flowToken, flowTokenLength)`
- `0x1800335f7`: `hr = CredSerializationHelper::SerializeDATokenCredentials( &execContextLite, daToken, daTokenLength, daTokenExpiryTime, daTokenExpiryTimeLength, daTokenCreationTime, daTokenCreationTimeLength, encodedSessionKey, encodedSessionKeyLength, flowToken, flowTokenLength, false , &spEncoded, &encodedLengthBytes)`
- `0x180033589`: `hr = CredSerializationHelper::SerializePasswordAndDATokenCredentials( &execContextLite, password, passwordLength, daToken, daTokenLength, daTokenExpiryTime, daTokenExpiryTimeLength, daTokenCreationTime, daTokenCreationTimeLength, encodedSessionKey, encodedSessionKeyLength, flowToken, flowTokenLength, false , &spEncoded, &encodedLengthBytes)`
- `0x1800337cf`: `hr = pAuthBufferFunctions->CreateAuthBuffer( pContext, &memoryManager, spEncoded, encodedLengthBytes, userNameLocal, requestFlags, encryptAuthIdentity, &spAuthBuffer, &authBufferSizeBytes)`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::GetAuthBufferInternal(
        MSACredentialManagerImplementation *this,
        struct IAuthBufferExecutionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        int a10,
        unsigned int a11,
        unsigned __int8 **a12,
        unsigned int *a13)
{
  unsigned int v15; // r13d
  unsigned __int8 **v16; // r12
  const char *v17; // rax
  unsigned int v18; // r8d
  unsigned int *v19; // r15
  int StringLengthCharacters; // eax
  const char *v21; // rcx
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // ebx
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  char *v30; // [rsp+20h] [rbp-E0h]
  bool v31; // [rsp+58h] [rbp-A8h]
  bool v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v34; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v35; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v36; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v37; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v38; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v39; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h]
  unsigned int *v44; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v45; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  _QWORD v48[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v49[128]; // [rsp+100h] [rbp+0h] BYREF

  v48[2] = 11;
  v48[1] = &v33;
  v48[0] = "MSACredentialManagerImplementation::GetAuthBufferInternal";
  v48[3] = qword_18006B5A8;
  v15 = 0;
  v33 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::GetAuthBufferInternal",
    (const char *)0xFE,
    0,
    (const unsigned __int16 *)v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v41);
  v16 = a12;
  v45 = 0;
  v47 = 0;
  v46 = 0;
  v35 = 0;
  if ( !a12 )
  {
    v17 = "ppAuthBuffer != nullptr";
    v18 = 261;
LABEL_63:
    v33 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::GetAuthBufferInternal",
      v18,
      -2147024809,
      v17);
    goto LABEL_64;
  }
  v19 = a13;
  *a12 = 0;
  if ( !v19 )
  {
    v17 = "pAuthBufferSizeBytes != nullptr";
    v18 = 263;
    goto LABEL_63;
  }
  *v19 = 0;
  if ( !a3 || !*a3 )
  {
    v17 = "IsNullOrEmpty(userName) == false";
    v18 = 266;
    goto LABEL_63;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v41, a3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v41);
  ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v49);
  v34 = 0;
  if ( a5 && *a5 && a6 && *a6 && a7 && *a7 )
  {
    v39 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v40[0] = 0;
    StringLengthCharacters = GetStringLengthCharacters(a5, &v39);
    v33 = StringLengthCharacters;
    if ( StringLengthCharacters < 0 )
    {
      v21 = "hr = GetStringLengthCharacters(daToken, daTokenLength)";
      v22 = 310;
LABEL_15:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::GetAuthBufferInternal",
        v22,
        StringLengthCharacters,
        v21);
      goto LABEL_64;
    }
    StringLengthCharacters = GetStringLengthCharacters(a6, &v37);
    v33 = StringLengthCharacters;
    if ( StringLengthCharacters < 0 )
    {
      v21 = "hr = GetStringLengthCharacters(daTokenCreationTime, daTokenCreationTimeLength)";
      v22 = 311;
      goto LABEL_15;
    }
    StringLengthCharacters = GetStringLengthCharacters(a7, &v38);
    v33 = StringLengthCharacters;
    if ( StringLengthCharacters < 0 )
    {
      v21 = "hr = GetStringLengthCharacters(daTokenExpiryTime, daTokenExpiryTimeLength)";
      v22 = 312;
      goto LABEL_15;
    }
    if ( a8 )
    {
      StringLengthCharacters = GetStringLengthCharacters(a8, v40);
      v33 = StringLengthCharacters;
      if ( StringLengthCharacters < 0 )
      {
        v21 = "hr = GetStringLengthCharacters(encodedSessionKey, encodedSessionKeyLength)";
        v22 = 315;
        goto LABEL_15;
      }
      v15 = v40[0];
    }
    if ( a9 )
    {
      StringLengthCharacters = GetStringLengthCharacters(a9, &v36);
      v33 = StringLengthCharacters;
      if ( StringLengthCharacters < 0 )
      {
        v21 = "hr = GetStringLengthCharacters(flowToken, flowTokenLength)";
        v22 = 319;
        goto LABEL_15;
      }
    }
    if ( a4 && *a4 )
    {
      StringLengthCharacters = GetStringLengthCharacters(a4, &v34);
      v33 = StringLengthCharacters;
      if ( StringLengthCharacters < 0 )
      {
        v21 = "hr = GetStringLengthCharacters(password, passwordLength)";
        v22 = 343;
        goto LABEL_15;
      }
      StringLengthCharacters = CredSerializationHelper::SerializePasswordAndDATokenCredentials(
                                 (struct IExecutionContextLite *)v49,
                                 a4,
                                 v34,
                                 a5,
                                 v39,
                                 a7,
                                 v38,
                                 a6,
                                 v37,
                                 a8,
                                 v15,
                                 a9,
                                 v36,
                                 v32,
                                 &v45,
                                 &v35);
      v33 = StringLengthCharacters;
      if ( StringLengthCharacters < 0 )
      {
        v21 = "hr = CredSerializationHelper::SerializePasswordAndDATokenCredentials( &execContextLite, password, password"
              "Length, daToken, daTokenLength, daTokenExpiryTime, daTokenExpiryTimeLength, daTokenCreationTime, daTokenCr"
              "eationTimeLength, encodedSessionKey, encodedSessionKeyLength, flowToken, flowTokenLength, false , &spEncod"
              "ed, &encodedLengthBytes)";
        v22 = 361;
        goto LABEL_15;
      }
    }
    else
    {
      StringLengthCharacters = CredSerializationHelper::SerializeDATokenCredentials(
                                 (struct IExecutionContextLite *)v49,
                                 a5,
                                 v39,
                                 a7,
                                 v38,
                                 a6,
                                 v37,
                                 a8,
                                 v15,
                                 a9,
                                 v36,
                                 v31,
                                 &v45,
                                 &v35);
      v33 = StringLengthCharacters;
      if ( StringLengthCharacters < 0 )
      {
        v21 = "hr = CredSerializationHelper::SerializeDATokenCredentials( &execContextLite, daToken, daTokenLength, daTok"
              "enExpiryTime, daTokenExpiryTimeLength, daTokenCreationTime, daTokenCreationTimeLength, encodedSessionKey, "
              "encodedSessionKeyLength, flowToken, flowTokenLength, false , &spEncoded, &encodedLengthBytes)";
        v22 = 339;
        goto LABEL_15;
      }
    }
    v16 = a12;
    v19 = a13;
  }
  else
  {
    if ( !a4 || !*a4 )
    {
      v17 = "IsNullOrEmpty(password) == false";
      v18 = 280;
      goto LABEL_63;
    }
    if ( a5 && *a5 )
    {
      v17 = "IsNullOrEmpty(daToken)";
      v18 = 283;
      goto LABEL_63;
    }
    if ( a6 && *a6 )
    {
      v17 = "IsNullOrEmpty(daTokenCreationTime)";
      v18 = 284;
      goto LABEL_63;
    }
    if ( a7 && *a7 )
    {
      v17 = "IsNullOrEmpty(daTokenExpiryTime)";
      v18 = 285;
      goto LABEL_63;
    }
    if ( a8 && *a8 )
    {
      v17 = "IsNullOrEmpty(encodedSessionKey)";
      v18 = 286;
      goto LABEL_63;
    }
    if ( a9 && *a9 )
    {
      v17 = "IsNullOrEmpty(flowToken)";
      v18 = 287;
      goto LABEL_63;
    }
    StringLengthCharacters = GetStringLengthCharacters(a4, &v34);
    v33 = StringLengthCharacters;
    if ( StringLengthCharacters < 0 )
    {
      v21 = "hr = GetStringLengthCharacters(password, passwordLength)";
      v22 = 289;
      goto LABEL_15;
    }
    StringLengthCharacters = CredSerializationHelper::SerializeCredentials(v49, v23, v24, a4, v34);
    v33 = StringLengthCharacters;
    if ( StringLengthCharacters < 0 )
    {
      v21 = "hr = CredSerializationHelper::SerializePasswordCredentials( &execContextLite, password, passwordLength, fals"
            "e , &spEncoded, &encodedLengthBytes)";
      v22 = 297;
      goto LABEL_15;
    }
  }
  v25 = v35;
  v46 = v35;
  v26 = (*(__int64 (__fastcall **)(struct IAuthBufferExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v42 = 0;
  v43 = 0;
  *(_QWORD *)v40 = &CoTaskMemoryManager::`vftable';
  LODWORD(a12) = 0;
  v44 = v40;
  v27 = (*(__int64 (__fastcall **)(__int64, struct IAuthBufferExecutionContext *, unsigned int *, unsigned __int8 *, unsigned int, __int64, unsigned int, int, unsigned __int8 **, unsigned __int8 ***))(*(_QWORD *)v26 + 8LL))(
          v26,
          a2,
          v40,
          v45,
          v25,
          v41,
          a11,
          a10,
          &v42,
          &a12);
  v33 = v27;
  if ( v27 >= 0 )
  {
    *v16 = v42;
    *v19 = (unsigned int)a12;
    v42 = 0;
    v43 = 0;
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::GetAuthBufferInternal",
      0x17Fu,
      v27,
      "hr = pAuthBufferFunctions->CreateAuthBuffer( pContext, &memoryManager, spEncoded, encodedLengthBytes, userNameLoca"
      "l, requestFlags, encryptAuthIdentity, &spAuthBuffer, &authBufferSizeBytes)");
  }
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v42);
LABEL_64:
  v28 = v33;
  Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>(&v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  CTraceFuncW<long>::~CTraceFuncW<long>(v48);
  return v28;
}

```

## disassembly

```asm
0x1800332a0  mov     [rsp-8+arg_8], rdx
0x1800332a5  push    rbp
0x1800332a6  push    rbx
0x1800332a7  push    rsi
0x1800332a8  push    rdi
0x1800332a9  push    r12
0x1800332ab  push    r13
0x1800332ad  push    r14
0x1800332af  push    r15
0x1800332b1  lea     rbp, [rsp-48h]
0x1800332b6  sub     rsp, 148h
0x1800332bd  lea     rax, [rbp+80h+var_100]
0x1800332c1  mov     [rbp+80h+var_90], 0Bh
0x1800332c9  mov     [rbp+80h+var_98], rax
0x1800332cd  lea     rsi, aMsacredentialm_8; "MSACredentialManagerImplementation::Get"...
0x1800332d4  lea     rax, qword_18006B5A8
0x1800332db  mov     [rbp+80h+var_A0], rsi
0x1800332df  mov     rbx, r9
0x1800332e2  mov     [rbp+80h+var_88], rax
0x1800332e6  mov     rdi, r8
0x1800332e9  lea     r14, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800332f0  xor     r13d, r13d
0x1800332f3  xor     r9d, r9d; unsigned int
0x1800332f6  mov     r8d, 0FEh; char *
0x1800332fc  mov     [rbp+80h+var_100], r13d
0x180033300  mov     rdx, rsi; char *
0x180033303  mov     rcx, r14; this
0x180033306  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003330b  lea     rcx, [rbp+80h+var_D8]; void *
0x18003330f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033314  mov     r12, [rbp+80h+arg_58]
0x18003331b  mov     [rbp+80h+var_B8], r13
0x18003331f  mov     [rbp+80h+var_A8], r13
0x180033323  mov     [rbp+80h+var_B0], r13
0x180033327  mov     [rbp+80h+var_F8], r13d
0x18003332b  test    r12, r12
0x18003332e  jnz     short loc_180033342
0x180033330  lea     rax, aPpauthbufferNu; "ppAuthBuffer != nullptr"
0x180033337  mov     r8d, 105h
0x18003333d  jmp     loc_18003383C
0x180033342  mov     r15, [rbp+80h+arg_60]
0x180033349  mov     [r12], r13
0x18003334d  test    r15, r15
0x180033350  jnz     short loc_180033364
0x180033352  lea     rax, aPauthbuffersiz; "pAuthBufferSizeBytes != nullptr"
0x180033359  mov     r8d, 107h
0x18003335f  jmp     loc_18003383C
0x180033364  mov     [r15], r13d
0x180033367  test    rdi, rdi
0x18003336a  jz      loc_18003382F
0x180033370  cmp     [rdi], r13w
0x180033374  jz      loc_18003382F
0x18003337a  mov     rdx, rdi
0x18003337d  lea     rcx, [rbp+80h+var_D8]
0x180033381  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180033386  lea     rcx, [rbp+80h+var_D8]
0x18003338a  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x18003338f  lea     rcx, [rbp+80h+var_80]; this
0x180033393  call    ??0ExecutionContextLite@@QEAA@XZ; ExecutionContextLite::ExecutionContextLite(void)
0x180033398  mov     r14, [rbp+80h+arg_20]
0x18003339f  mov     rsi, [rbp+80h+arg_30]
0x1800333a6  mov     rdi, [rbp+80h+arg_28]
0x1800333ad  mov     [rbp+80h+var_FC], r13d
0x1800333b1  test    r14, r14
0x1800333b4  jz      loc_180033609
0x1800333ba  cmp     [r14], r13w
0x1800333be  jz      loc_180033609
0x1800333c4  test    rdi, rdi
0x1800333c7  jz      loc_180033609
0x1800333cd  cmp     [rdi], r13w
0x1800333d1  jz      loc_180033609
0x1800333d7  test    rsi, rsi
0x1800333da  jz      loc_180033609
0x1800333e0  cmp     [rsi], r13w
0x1800333e4  jz      loc_180033609
0x1800333ea  xor     r15d, r15d
0x1800333ed  mov     [rbp+80h+var_E8], r13d
0x1800333f1  lea     rdx, [rbp+80h+var_E8]; unsigned int *
0x1800333f5  mov     [rbp+80h+var_F4], r15d
0x1800333f9  mov     rcx, r14; unsigned __int16 *
0x1800333fc  mov     [rbp+80h+var_F0], r13d
0x180033400  mov     [rbp+80h+var_EC], r13d
0x180033404  mov     [rbp+80h+var_E0], r13d
0x180033408  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x18003340d  mov     [rbp+80h+var_100], eax
0x180033410  test    eax, eax
0x180033412  jns     short loc_18003343C
0x180033414  lea     rcx, aHrGetstringlen_3; "hr = GetStringLengthCharacters(daToken,"...
0x18003341b  mov     r8d, 136h
0x180033421  mov     [rsp+180h+var_160], rcx
0x180033426  lea     rdx, aMsacredentialm_8; "MSACredentialManagerImplementation::Get"...
0x18003342d  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180033434  mov     r9d, eax
0x180033437  jmp     loc_180033851
0x18003343c  lea     rdx, [rbp+80h+var_F0]; unsigned int *
0x180033440  mov     rcx, rdi; unsigned __int16 *
0x180033443  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x180033448  mov     [rbp+80h+var_100], eax
0x18003344b  test    eax, eax
0x18003344d  jns     short loc_18003345E
0x18003344f  lea     rcx, aHrGetstringlen_4; "hr = GetStringLengthCharacters(daTokenC"...
0x180033456  mov     r8d, 137h
0x18003345c  jmp     short loc_180033421
0x18003345e  lea     rdx, [rbp+80h+var_EC]; unsigned int *
0x180033462  mov     rcx, rsi; unsigned __int16 *
0x180033465  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x18003346a  mov     [rbp+80h+var_100], eax
0x18003346d  test    eax, eax
0x18003346f  jns     short loc_180033480
0x180033471  lea     rcx, aHrGetstringlen_0; "hr = GetStringLengthCharacters(daTokenE"...
0x180033478  mov     r8d, 138h
0x18003347e  jmp     short loc_180033421
0x180033480  mov     r12, [rbp+80h+arg_38]
0x180033487  test    r12, r12
0x18003348a  jz      short loc_1800334B5
0x18003348c  lea     rdx, [rbp+80h+var_E0]; unsigned int *
0x180033490  mov     rcx, r12; unsigned __int16 *
0x180033493  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x180033498  mov     [rbp+80h+var_100], eax
0x18003349b  test    eax, eax
0x18003349d  jns     short loc_1800334B1
0x18003349f  lea     rcx, aHrGetstringlen_2; "hr = GetStringLengthCharacters(encodedS"...
0x1800334a6  mov     r8d, 13Bh
0x1800334ac  jmp     loc_180033421
0x1800334b1  mov     r13d, [rbp+80h+var_E0]
0x1800334b5  mov     r15, [rbp+80h+arg_40]
0x1800334bc  xor     eax, eax
0x1800334be  test    r15, r15
0x1800334c1  jz      short loc_1800334EA
0x1800334c3  lea     rdx, [rbp+80h+var_F4]; unsigned int *
0x1800334c7  mov     rcx, r15; unsigned __int16 *
0x1800334ca  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x1800334cf  mov     [rbp+80h+var_100], eax
0x1800334d2  test    eax, eax
0x1800334d4  jns     short loc_1800334E8
0x1800334d6  lea     rcx, aHrGetstringlen_1; "hr = GetStringLengthCharacters(flowToke"...
0x1800334dd  mov     r8d, 13Fh
0x1800334e3  jmp     loc_180033421
0x1800334e8  xor     eax, eax
0x1800334ea  test    rbx, rbx
0x1800334ed  jz      loc_18003359B
0x1800334f3  cmp     [rbx], ax
0x1800334f6  jz      loc_18003359B
0x1800334fc  lea     rdx, [rbp+80h+var_FC]; unsigned int *
0x180033500  mov     rcx, rbx; unsigned __int16 *
0x180033503  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x180033508  mov     [rbp+80h+var_100], eax
0x18003350b  test    eax, eax
0x18003350d  jns     short loc_180033521
0x18003350f  lea     rcx, aHrGetstringlen; "hr = GetStringLengthCharacters(password"...
0x180033516  mov     r8d, 157h
0x18003351c  jmp     loc_180033421
0x180033521  mov     r8d, [rbp+80h+var_FC]; unsigned int
0x180033525  lea     rax, [rbp+80h+var_F8]
0x180033529  mov     [rsp+180h+var_108], rax; unsigned int *
0x18003352e  lea     rcx, [rbp+80h+var_80]; struct IExecutionContextLite *
0x180033532  lea     rax, [rbp+80h+var_B8]
0x180033536  mov     r9, r14; unsigned __int16 *
0x180033539  mov     [rsp+180h+var_110], rax; unsigned __int8 **
0x18003353e  mov     rdx, rbx; unsigned __int16 *
0x180033541  mov     eax, [rbp+80h+var_F4]
0x180033544  mov     dword ptr [rsp+180h+var_120], eax; unsigned int
0x180033548  mov     eax, [rbp+80h+var_F0]
0x18003354b  mov     [rsp+180h+var_128], r15; unsigned __int16 *
0x180033550  mov     [rsp+180h+var_130], r13d; unsigned int
0x180033555  mov     [rsp+180h+var_138], r12; unsigned __int16 *
0x18003355a  mov     [rsp+180h+var_140], eax; unsigned int
0x18003355e  mov     eax, [rbp+80h+var_EC]
0x180033561  mov     [rsp+180h+var_148], rdi; unsigned __int16 *
0x180033566  mov     [rsp+180h+var_150], eax; unsigned int
0x18003356a  mov     eax, [rbp+80h+var_E8]
0x18003356d  mov     [rsp+180h+var_158], rsi; unsigned __int16 *
0x180033572  mov     dword ptr [rsp+180h+var_160], eax; unsigned int
0x180033576  call    ?SerializePasswordAndDATokenCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEBGK1K1K1K1K1K_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializePasswordAndDATokenCredentials(IExecutionContextLite *,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,bool,uchar * *,ulong *)
0x18003357b  xor     r13d, r13d
0x18003357e  mov     [rbp+80h+var_100], eax
0x180033581  test    eax, eax
0x180033583  jns     loc_180033728
0x180033589  lea     rcx, aHrCredserializ_2; "hr = CredSerializationHelper::Serialize"...
0x180033590  mov     r8d, 169h
0x180033596  jmp     loc_180033421
0x18003359b  mov     r8d, [rbp+80h+var_E8]; unsigned int
0x18003359f  lea     rax, [rbp+80h+var_F8]
0x1800335a3  mov     [rsp+180h+var_118], rax; unsigned int *
0x1800335a8  lea     rcx, [rbp+80h+var_80]; struct IExecutionContextLite *
0x1800335ac  lea     rax, [rbp+80h+var_B8]
0x1800335b0  mov     r9, rsi; unsigned __int16 *
0x1800335b3  mov     [rsp+180h+var_120], rax; unsigned __int8 **
0x1800335b8  mov     rdx, r14; unsigned __int16 *
0x1800335bb  mov     eax, [rbp+80h+var_F4]
0x1800335be  mov     [rsp+180h+var_130], eax; unsigned int
0x1800335c2  mov     eax, [rbp+80h+var_F0]
0x1800335c5  mov     [rsp+180h+var_138], r15; unsigned __int16 *
0x1800335ca  mov     [rsp+180h+var_140], r13d; unsigned int
0x1800335cf  mov     [rsp+180h+var_148], r12; unsigned __int16 *
0x1800335d4  mov     [rsp+180h+var_150], eax; unsigned int
0x1800335d8  mov     eax, [rbp+80h+var_EC]
0x1800335db  mov     [rsp+180h+var_158], rdi; unsigned __int16 *
0x1800335e0  mov     dword ptr [rsp+180h+var_160], eax; unsigned int
0x1800335e4  call    ?SerializeDATokenCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEBGK1K1K1K1K_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeDATokenCredentials(IExecutionContextLite *,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,bool,uchar * *,ulong *)
0x1800335e9  xor     r13d, r13d
0x1800335ec  mov     [rbp+80h+var_100], eax
0x1800335ef  test    eax, eax
0x1800335f1  jns     loc_180033728
0x1800335f7  lea     rcx, aHrCredserializ; "hr = CredSerializationHelper::Serialize"...
0x1800335fe  mov     r8d, 153h
0x180033604  jmp     loc_180033421
0x180033609  test    rbx, rbx
0x18003360c  jz      loc_18003381D
0x180033612  cmp     [rbx], r13w
0x180033616  jz      loc_18003381D
0x18003361c  test    r14, r14
0x18003361f  jz      short loc_180033647
0x180033621  cmp     [r14], r13w
0x180033625  jz      short loc_180033647
0x180033627  lea     rax, aIsnulloremptyD_4; "IsNullOrEmpty(daToken)"
0x18003362e  mov     r8d, 11Bh
0x180033634  lea     rdx, aMsacredentialm_8; "MSACredentialManagerImplementation::Get"...
0x18003363b  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180033642  jmp     loc_180033842
0x180033647  test    rdi, rdi
0x18003364a  jz      short loc_180033661
0x18003364c  cmp     [rdi], r13w
0x180033650  jz      short loc_180033661
0x180033652  lea     rax, aIsnulloremptyD_0; "IsNullOrEmpty(daTokenCreationTime)"
0x180033659  mov     r8d, 11Ch
0x18003365f  jmp     short loc_180033634
0x180033661  test    rsi, rsi
0x180033664  jz      short loc_18003367B
0x180033666  cmp     [rsi], r13w
0x18003366a  jz      short loc_18003367B
0x18003366c  lea     rax, aIsnulloremptyD; "IsNullOrEmpty(daTokenExpiryTime)"
0x180033673  mov     r8d, 11Dh
0x180033679  jmp     short loc_180033634
0x18003367b  mov     rax, [rbp+80h+arg_38]
0x180033682  test    rax, rax
0x180033685  jz      short loc_18003369C
0x180033687  cmp     [rax], r13w
0x18003368b  jz      short loc_18003369C
0x18003368d  lea     rax, aIsnulloremptyE; "IsNullOrEmpty(encodedSessionKey)"
0x180033694  mov     r8d, 11Eh
0x18003369a  jmp     short loc_180033634
0x18003369c  mov     rax, [rbp+80h+arg_40]
0x1800336a3  test    rax, rax
0x1800336a6  jz      short loc_1800336C0
0x1800336a8  cmp     [rax], r13w
0x1800336ac  jz      short loc_1800336C0
0x1800336ae  lea     rax, aIsnulloremptyF; "IsNullOrEmpty(flowToken)"
0x1800336b5  mov     r8d, 11Fh
0x1800336bb  jmp     loc_180033634
0x1800336c0  lea     rdx, [rbp+80h+var_FC]; unsigned int *
0x1800336c4  mov     rcx, rbx; unsigned __int16 *
0x1800336c7  call    ?GetStringLengthCharacters@@YAJPEBGAEAK@Z; GetStringLengthCharacters(ushort const *,ulong &)
0x1800336cc  mov     [rbp+80h+var_100], eax
0x1800336cf  test    eax, eax
0x1800336d1  jns     short loc_1800336E5
0x1800336d3  lea     rcx, aHrGetstringlen; "hr = GetStringLengthCharacters(password"...
0x1800336da  mov     r8d, 121h
0x1800336e0  jmp     loc_180033421
0x1800336e5  lea     rax, [rbp+80h+var_F8]
0x1800336e9  mov     r9, rbx
0x1800336ec  mov     qword ptr [rsp+180h+var_130], rax
0x1800336f1  lea     rcx, [rbp+80h+var_80]
0x1800336f5  lea     rax, [rbp+80h+var_B8]
0x1800336f9  mov     [rsp+180h+var_138], rax
0x1800336fe  mov     eax, [rbp+80h+var_FC]
0x180033701  mov     byte ptr [rsp+180h+var_140], r13b
0x180033706  mov     dword ptr [rsp+180h+var_160], eax
0x18003370a  call    ?SerializeCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@W4_WLIDCredentialsType@@W4_WLIDCredentialAttribute@@PEBGK23K_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeCredentials(IExecutionContextLite *,_WLIDCredentialsType,_WLIDCredentialAttribute,ushort const *,ulong,_WLIDCredentialAttribute,ushort const *,ulong,bool,uchar * *,ulong *)
0x18003370f  mov     [rbp+80h+var_100], eax
0x180033712  test    eax, eax
0x180033714  jns     short loc_180033736
0x180033716  lea     rcx, aHrCredserializ_0; "hr = CredSerializationHelper::Serialize"...
0x18003371d  mov     r8d, 129h
0x180033723  jmp     loc_180033421
0x180033728  mov     r12, [rbp+80h+arg_58]
0x18003372f  mov     r15, [rbp+80h+arg_60]
0x180033736  mov     rdi, [rbp+80h+arg_8]
0x18003373d  mov     ebx, [rbp+80h+var_F8]
0x180033740  mov     rcx, rdi
0x180033743  mov     [rbp+80h+var_B0], rbx
0x180033747  mov     rax, [rdi]
0x18003374a  mov     rax, [rax+8]
0x18003374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033753  mov     r9, [rbp+80h+var_B8]
0x180033757  lea     r8, [rbp+80h+var_E0]
0x18003375b  mov     r10, rax
0x18003375e  mov     [rbp+80h+var_D0], r13
0x180033762  lea     rax, ??_7CoTaskMemoryManager@@6B@; const CoTaskMemoryManager::`vftable'
0x180033769  mov     [rbp+80h+var_C8], r13
0x18003376d  mov     qword ptr [rbp+80h+var_E0], rax
0x180033771  mov     rdx, rdi
0x180033774  lea     rax, [rbp+80h+var_E0]
0x180033778  mov     dword ptr [rbp+80h+arg_58], r13d
0x18003377f  mov     [rbp+80h+var_C0], rax
0x180033783  mov     rcx, [r10]
0x180033786  mov     rax, [rcx+8]
0x18003378a  lea     rcx, [rbp+80h+arg_58]
0x180033791  mov     [rsp+180h+var_138], rcx
0x180033796  lea     rcx, [rbp+80h+var_D0]
  ... truncated ...
```
