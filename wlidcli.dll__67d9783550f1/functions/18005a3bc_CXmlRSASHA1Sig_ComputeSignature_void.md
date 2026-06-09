# CXmlRSASHA1Sig::ComputeSignature(void)

- ea: `0x18005a3bc`
- end: `0x18005a7ad`
- name: `?ComputeSignature@CXmlRSASHA1Sig@@QEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(CXmlRSASHA1Sig *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005733c`

## callees

- `0x180005a7c`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000d1c8`
- `0x18000d438`
- `0x18000dff0`
- `0x18000e69c`
- `0x18000e728`
- `0x18000fa44`
- `0x1800103d0`
- `0x1800114b0`
- `0x18001b710`
- `0x18001d310`
- `0x180053890`
- `0x180059f90`
- `0x180059ff8`
- `0x18005a3bc`
- `0x18005a7b4`
- `0x18005a8c0`
- `0x18005a8fc`

## string_xrefs

- `0x18005a49e`: `<SignedInfo xmlns="http://www.w3.org/2000/09/xmldsig#">`
- `0x18005a633`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig.cpp`
- `0x18005a74d`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig.cpp`
- `0x18005a62c`: `CXmlRSASHA1Sig::ComputeSignature`
- `0x18005a746`: `CXmlRSASHA1Sig::ComputeSignature`
- `0x18005a461`: `m_strSigXmlText.GetLength() > (int)m_cchCanonicalizationStartIndex`
- `0x18005a4e4`: `hr = cryptSHA1SignedInfoHash.AddData( (const PBYTE)(pcszRemainingSignedInfoText), m_strSigXmlText.GetLength() - m_cchCanonicalizationStartIndex)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CXmlRSASHA1Sig::ComputeSignature(CXmlRSASHA1Sig *this)
{
  __int64 *v2; // r14
  int CertProperty; // edi
  const unsigned __int16 *v4; // r8
  const char *v5; // rax
  unsigned int v6; // r8d
  __int64 v7; // rbx
  __int64 v8; // r15
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // ebx
  unsigned __int8 *v13; // rbx
  unsigned int v14; // r9d
  int v15; // r10d
  int v16; // r15d
  int i; // r9d
  unsigned __int8 v18; // dl
  char *BufferSetLength; // rax
  int v20; // ebx
  unsigned int v21; // edx
  bool v22; // r8
  unsigned int v23; // edx
  char *v24; // rax
  const char *v25; // rdx
  __int64 v26; // r8
  unsigned int v28; // [rsp+20h] [rbp-50h]
  __int64 v29; // [rsp+30h] [rbp-40h] BYREF
  __int64 v30; // [rsp+38h] [rbp-38h] BYREF
  int v31; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v32; // [rsp+48h] [rbp-28h]
  int v33; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 *v34; // [rsp+60h] [rbp-10h]
  int v35; // [rsp+68h] [rbp-8h]
  int RequiredLength; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v37; // [rsp+B8h] [rbp+48h] BYREF
  HCRYPTHASH phHash; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v39; // [rsp+C8h] [rbp+58h] BYREF

  phHash = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v37 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v29);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v39);
  v30 = 0;
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 8) || !*((_QWORD *)this + 10) )
  {
    CertProperty = -2147216615;
    v5 = "m_RefList.GetCount() != 0 && m_cryptProv.GetHandle() != 0 && m_pCertContext != nullptr";
    v6 = 156;
    goto LABEL_30;
  }
  v2 = (__int64 *)((char *)this + 56);
  ATL::CSimpleStringT<char,0>::PrepareWrite((char *)this + 56, 2000);
  CertProperty = CXmlRSASHA1Sig::BuildDigestedReferences(this);
  if ( CertProperty < 0 )
  {
    v5 = "hr = BuildDigestedReferences()";
    v6 = 162;
LABEL_30:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig.cpp",
      "CXmlRSASHA1Sig::ComputeSignature",
      v6,
      CertProperty,
      v5);
    goto LABEL_31;
  }
  v7 = *((int *)this + 18);
  v8 = *v2;
  if ( *(_DWORD *)(*v2 - 16) <= (int)v7 )
  {
    CertProperty = -2147216614;
    v5 = "m_strSigXmlText.GetLength() > (int)m_cchCanonicalizationStartIndex";
    v6 = 165;
    goto LABEL_30;
  }
  CertProperty = ATL::CCryptSHAHash::Initialize(&phHash, (CXmlRSASHA1Sig *)((char *)this + 88), v4);
  if ( CertProperty < 0 )
  {
    v5 = "hr = cryptSHA1SignedInfoHash.Initialize(m_cCryptProv)";
    v6 = 169;
    goto LABEL_30;
  }
  CertProperty = ATL::CCryptHash::AddData(
                   (ATL::CCryptHash *)&phHash,
                   "<SignedInfo xmlns=\"http://www.w3.org/2000/09/xmldsig#\">",
                   0x37u,
                   v9);
  if ( CertProperty < 0 )
  {
    v5 = "hr = cryptSHA1SignedInfoHash.AddData( (const PBYTE)(k_pcszSignedInfoStart), (DWORD)strlen(k_pcszSignedInfoStart))";
    v6 = 174;
    goto LABEL_30;
  }
  CertProperty = ATL::CCryptHash::AddData(
                   (ATL::CCryptHash *)&phHash,
                   (const unsigned __int8 *)(v8 + v7),
                   *(_DWORD *)(*v2 - 16) - *((_DWORD *)this + 18),
                   v10);
  if ( CertProperty < 0 )
  {
    v5 = "hr = cryptSHA1SignedInfoHash.AddData( (const PBYTE)(pcszRemainingSignedInfoText), m_strSigXmlText.GetLength() -"
         " m_cchCanonicalizationStartIndex)";
    v6 = 179;
    goto LABEL_30;
  }
  CertProperty = ATL::CCryptHash::Sign((ATL::CCryptHash *)&phHash, 0, &v37, v11, *((_DWORD *)this + 24));
  if ( CertProperty < 0 )
  {
    v5 = "hr = cryptSHA1SignedInfoHash.Sign(nullptr, &dwSigValueLen, 0, m_dwKeySpecification)";
    v6 = 182;
    goto LABEL_30;
  }
  v12 = *((_DWORD *)this + 24);
  CBytePtr::SetLength((CBytePtr *)&v33, v37, 0);
  v28 = v12;
  v13 = v34;
  CertProperty = ATL::CCryptHash::Sign((ATL::CCryptHash *)&phHash, v34, &v37, v14, v28);
  if ( CertProperty < 0 )
  {
    v5 = "hr = cryptSHA1SignedInfoHash.Sign( bpSigValue.GetBufferSetLength(dwSigValueLen, FALSE), &dwSigValueLen, 0, m_dw"
         "KeySpecification)";
    v6 = 191;
    goto LABEL_30;
  }
  v15 = 0;
  v16 = v33;
  for ( i = v33 - 1; v15 < i; --i )
  {
    v18 = v13[v15];
    v13[v15] = v13[i];
    v13[i] = v18;
    ++v15;
  }
  RequiredLength = ATL::Base64EncodeGetRequiredLength(v16, 0);
  BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v29, (unsigned int)RequiredLength);
  v20 = ATL::Base64Encode(v13, v16, BufferSetLength, &RequiredLength, 0);
  ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v29, (unsigned int)RequiredLength);
  if ( !v20 )
  {
    CertProperty = -2147197938;
    v5 = "bRet";
    v6 = 220;
    goto LABEL_30;
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 6) - 16LL) )
  {
    CBytePtr::CBytePtr((CBytePtr *)&v31, v21, v22);
    CertProperty = CXmlRSASHA1Sig::GetCertProperty(this, v23, (struct CBytePtr *)&v31);
    if ( CertProperty < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig.cpp",
        "CXmlRSASHA1Sig::ComputeSignature",
        0xE2u,
        CertProperty,
        "hr = GetCertProperty(CERT_KEY_IDENTIFIER_PROP_ID, bpSKI)");
      CBytePtr::Empty((CBytePtr *)&v31);
      goto LABEL_31;
    }
    RequiredLength = ATL::Base64EncodeGetRequiredLength(v31, 0);
    v24 = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v39, (unsigned int)RequiredLength);
    ATL::Base64Encode(v32, v31, v24, &RequiredLength, 0);
    ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v39, (unsigned int)RequiredLength);
    CBytePtr::Empty((CBytePtr *)&v31);
  }
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "<SignatureValue>", 16);
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, v29, *(unsigned int *)(v29 - 16));
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "</SignatureValue><KeyInfo>", 26);
  v25 = (const char *)*((_QWORD *)this + 6);
  v26 = *((unsigned int *)v25 - 4);
  if ( !(_DWORD)v26 )
  {
    ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "<X509Data><X509SKI>", 19);
    ATL::CSimpleStringT<char,0>::Append((char *)this + 56, v39, *(unsigned int *)(v39 - 16));
    v25 = "</X509SKI></X509Data>";
    v26 = 21;
  }
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, v25, v26);
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "</KeyInfo></Signature>", 22);
LABEL_31:
  ATL::CCryptHash::Destroy((ATL::CCryptHash *)&phHash);
  ATL::CCryptProv::Release((ATL::CCryptProv *)&v30);
  ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
  CBytePtr::Empty((CBytePtr *)&v33);
  ATL::CCryptHash::Destroy((ATL::CCryptHash *)&phHash);
  return (unsigned int)CertProperty;
}

```

## disassembly

```asm
0x18005a3bc  push    rbp
0x18005a3be  push    rbx
0x18005a3bf  push    rsi
0x18005a3c0  push    rdi
0x18005a3c1  push    r12
0x18005a3c3  push    r14
0x18005a3c5  push    r15
0x18005a3c7  mov     rbp, rsp
0x18005a3ca  sub     rsp, 70h
0x18005a3ce  mov     rsi, rcx
0x18005a3d1  xor     r12d, r12d
0x18005a3d4  mov     [rbp+phHash], r12
0x18005a3d8  mov     [rbp+var_10], r12
0x18005a3dc  mov     [rbp+var_18], r12d
0x18005a3e0  mov     [rbp+var_8], r12d
0x18005a3e4  mov     [rbp+arg_8], r12d
0x18005a3e8  lea     rcx, [rbp+var_40]
0x18005a3ec  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005a3f1  nop
0x18005a3f2  lea     rcx, [rbp+arg_18]
0x18005a3f6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005a3fb  nop
0x18005a3fc  mov     [rbp+var_38], r12
0x18005a400  cmp     [rsi+10h], r12
0x18005a404  jz      loc_18005A72C
0x18005a40a  cmp     [rsi+40h], r12
0x18005a40e  jz      loc_18005A72C
0x18005a414  cmp     [rsi+50h], r12
0x18005a418  jz      loc_18005A72C
0x18005a41e  lea     r14, [rsi+38h]
0x18005a422  mov     edx, 7D0h
0x18005a427  mov     rcx, r14
0x18005a42a  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x18005a42f  mov     rcx, rsi; this
0x18005a432  call    ?BuildDigestedReferences@CXmlRSASHA1Sig@@AEAAJXZ; CXmlRSASHA1Sig::BuildDigestedReferences(void)
0x18005a437  mov     edi, eax
0x18005a439  test    eax, eax
0x18005a43b  jns     short loc_18005A44F
0x18005a43d  lea     rax, aHrBuilddigeste; "hr = BuildDigestedReferences()"
0x18005a444  mov     r8d, 0A2h
0x18005a44a  jmp     loc_18005A73E
0x18005a44f  movsxd  rbx, dword ptr [rsi+48h]
0x18005a453  mov     r15, [r14]
0x18005a456  cmp     [r15-10h], ebx
0x18005a45a  jg      short loc_18005A473
0x18005a45c  mov     edi, 8004131Ah
0x18005a461  lea     rax, aMStrsigxmltext; "m_strSigXmlText.GetLength() > (int)m_cc"...
0x18005a468  mov     r8d, 0A5h
0x18005a46e  jmp     loc_18005A73E
0x18005a473  lea     rdx, [rsi+58h]; struct ATL::CCryptProv *
0x18005a477  lea     rcx, [rbp+phHash]; phHash
0x18005a47b  call    ?Initialize@CCryptSHAHash@ATL@@QEAAJAEAVCCryptProv@2@PEBG@Z; ATL::CCryptSHAHash::Initialize(ATL::CCryptProv &,ushort const *)
0x18005a480  mov     edi, eax
0x18005a482  test    eax, eax
0x18005a484  jns     short loc_18005A498
0x18005a486  lea     rax, aHrCryptsha1sig_3; "hr = cryptSHA1SignedInfoHash.Initialize"...
0x18005a48d  mov     r8d, 0A9h
0x18005a493  jmp     loc_18005A73E
0x18005a498  mov     r8d, 37h ; '7'; unsigned int
0x18005a49e  lea     rdx, aSignedinfoXmln; "<SignedInfo xmlns=\"http://www.w3.org/2"...
0x18005a4a5  lea     rcx, [rbp+phHash]; this
0x18005a4a9  call    ?AddData@CCryptHash@ATL@@QEAAJPEBEKK@Z; ATL::CCryptHash::AddData(uchar const *,ulong,ulong)
0x18005a4ae  mov     edi, eax
0x18005a4b0  test    eax, eax
0x18005a4b2  jns     short loc_18005A4C6
0x18005a4b4  lea     rax, aHrCryptsha1sig; "hr = cryptSHA1SignedInfoHash.AddData( ("...
0x18005a4bb  mov     r8d, 0AEh
0x18005a4c1  jmp     loc_18005A73E
0x18005a4c6  mov     rax, [r14]
0x18005a4c9  mov     r8d, [rax-10h]
0x18005a4cd  sub     r8d, [rsi+48h]; unsigned int
0x18005a4d1  lea     rdx, [r15+rbx]; unsigned __int8 *
0x18005a4d5  lea     rcx, [rbp+phHash]; this
0x18005a4d9  call    ?AddData@CCryptHash@ATL@@QEAAJPEBEKK@Z; ATL::CCryptHash::AddData(uchar const *,ulong,ulong)
0x18005a4de  mov     edi, eax
0x18005a4e0  test    eax, eax
0x18005a4e2  jns     short loc_18005A4F6
0x18005a4e4  lea     rax, aHrCryptsha1sig_1; "hr = cryptSHA1SignedInfoHash.AddData( ("...
0x18005a4eb  mov     r8d, 0B3h
0x18005a4f1  jmp     loc_18005A73E
0x18005a4f6  mov     eax, [rsi+60h]
0x18005a4f9  mov     [rsp+70h+var_50], eax; unsigned int
0x18005a4fd  lea     r8, [rbp+arg_8]; unsigned int *
0x18005a501  xor     edx, edx; unsigned __int8 *
0x18005a503  lea     rcx, [rbp+phHash]; this
0x18005a507  call    ?Sign@CCryptHash@ATL@@QEAAJPEAEPEAKKK@Z; ATL::CCryptHash::Sign(uchar *,ulong *,ulong,ulong)
0x18005a50c  mov     edi, eax
0x18005a50e  test    eax, eax
0x18005a510  jns     short loc_18005A524
0x18005a512  lea     rax, aHrCryptsha1sig_0; "hr = cryptSHA1SignedInfoHash.Sign(nullp"...
0x18005a519  mov     r8d, 0B6h
0x18005a51f  jmp     loc_18005A73E
0x18005a524  mov     ebx, [rsi+60h]
0x18005a527  xor     r8d, r8d; bool
0x18005a52a  mov     edx, [rbp+arg_8]; unsigned int
0x18005a52d  lea     rcx, [rbp+var_18]; this
0x18005a531  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x18005a536  mov     [rsp+70h+var_50], ebx; unsigned int
0x18005a53a  lea     r8, [rbp+arg_8]; unsigned int *
0x18005a53e  mov     rbx, [rbp+var_10]
0x18005a542  mov     rdx, rbx; unsigned __int8 *
0x18005a545  lea     rcx, [rbp+phHash]; this
0x18005a549  call    ?Sign@CCryptHash@ATL@@QEAAJPEAEPEAKKK@Z; ATL::CCryptHash::Sign(uchar *,ulong *,ulong,ulong)
0x18005a54e  mov     edi, eax
0x18005a550  test    eax, eax
0x18005a552  jns     short loc_18005A566
0x18005a554  lea     rax, aHrCryptsha1sig_2; "hr = cryptSHA1SignedInfoHash.Sign( bpSi"...
0x18005a55b  mov     r8d, 0BFh
0x18005a561  jmp     loc_18005A73E
0x18005a566  mov     r10d, r12d
0x18005a569  mov     r15d, [rbp+var_18]
0x18005a56d  lea     r9d, [r15-1]
0x18005a571  test    r9d, r9d
0x18005a574  jle     short loc_18005A595
0x18005a576  movsxd  r8, r10d
0x18005a579  mov     dl, [r8+rbx]
0x18005a57d  movsxd  rcx, r9d
0x18005a580  mov     al, [rcx+rbx]
0x18005a583  mov     [r8+rbx], al
0x18005a587  mov     [rcx+rbx], dl
0x18005a58a  inc     r10d
0x18005a58d  dec     r9d
0x18005a590  cmp     r10d, r9d
0x18005a593  jl      short loc_18005A576
0x18005a595  xor     edx, edx; unsigned int
0x18005a597  mov     ecx, r15d; int
0x18005a59a  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18005a59f  mov     [rbp+arg_0], eax
0x18005a5a2  mov     edx, eax
0x18005a5a4  lea     rcx, [rbp+var_40]
0x18005a5a8  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18005a5ad  mov     [rsp+70h+var_50], r12d; unsigned int
0x18005a5b2  lea     r9, [rbp+arg_0]; int *
0x18005a5b6  mov     r8, rax; char *
0x18005a5b9  mov     edx, r15d; int
0x18005a5bc  mov     rcx, rbx; unsigned __int8 *
0x18005a5bf  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18005a5c4  mov     ebx, eax
0x18005a5c6  mov     edx, [rbp+arg_0]
0x18005a5c9  lea     rcx, [rbp+var_40]
0x18005a5cd  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18005a5d2  test    ebx, ebx
0x18005a5d4  jnz     short loc_18005A5ED
0x18005a5d6  mov     edi, 80045C0Eh
0x18005a5db  lea     rax, aBret; "bRet"
0x18005a5e2  mov     r8d, 0DCh
0x18005a5e8  jmp     loc_18005A73E
0x18005a5ed  mov     rax, [rsi+30h]
0x18005a5f1  cmp     [rax-10h], r12d
0x18005a5f5  jnz     loc_18005A694
0x18005a5fb  lea     rcx, [rbp+var_30]; this
0x18005a5ff  call    ??0CBytePtr@@QEAA@K_N@Z; CBytePtr::CBytePtr(ulong,bool)
0x18005a604  nop
0x18005a605  lea     r8, [rbp+var_30]; struct CBytePtr *
0x18005a609  mov     rcx, rsi; this
0x18005a60c  call    ?GetCertProperty@CXmlRSASHA1Sig@@AEAAJKAEAVCBytePtr@@@Z; CXmlRSASHA1Sig::GetCertProperty(ulong,CBytePtr &)
0x18005a611  mov     edi, eax
0x18005a613  test    eax, eax
0x18005a615  jns     short loc_18005A64E
0x18005a617  lea     rax, aHrGetcertprope; "hr = GetCertProperty(CERT_KEY_IDENTIFIE"...
0x18005a61e  mov     qword ptr [rsp+70h+var_50], rax; char *
0x18005a623  mov     r9d, edi; int
0x18005a626  mov     r8d, 0E2h; unsigned int
0x18005a62c  lea     rdx, aCxmlrsasha1sig_0; "CXmlRSASHA1Sig::ComputeSignature"
0x18005a633  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18005a63a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005a63f  nop
0x18005a640  lea     rcx, [rbp+var_30]; this
0x18005a644  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18005a649  jmp     loc_18005A759
0x18005a64e  xor     edx, edx; unsigned int
0x18005a650  mov     ecx, [rbp+var_30]; int
0x18005a653  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18005a658  mov     [rbp+arg_0], eax
0x18005a65b  mov     edx, eax
0x18005a65d  lea     rcx, [rbp+arg_18]
0x18005a661  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18005a666  mov     [rsp+70h+var_50], r12d; unsigned int
0x18005a66b  lea     r9, [rbp+arg_0]; int *
0x18005a66f  mov     r8, rax; char *
0x18005a672  mov     edx, [rbp+var_30]; int
0x18005a675  mov     rcx, [rbp+var_28]; unsigned __int8 *
0x18005a679  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18005a67e  mov     edx, [rbp+arg_0]
0x18005a681  lea     rcx, [rbp+arg_18]
0x18005a685  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18005a68a  nop
0x18005a68b  lea     rcx, [rbp+var_30]; this
0x18005a68f  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18005a694  mov     r8d, 10h
0x18005a69a  lea     rdx, aSignaturevalue; "<SignatureValue>"
0x18005a6a1  mov     rcx, r14
0x18005a6a4  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a6a9  mov     rdx, [rbp+var_40]
0x18005a6ad  mov     r8d, [rdx-10h]
0x18005a6b1  mov     rcx, r14
0x18005a6b4  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a6b9  mov     r8d, 1Ah
0x18005a6bf  lea     rdx, aSignaturevalue_0; "</SignatureValue><KeyInfo>"
0x18005a6c6  mov     rcx, r14
0x18005a6c9  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a6ce  mov     rdx, [rsi+30h]
0x18005a6d2  mov     r8d, [rdx-10h]
0x18005a6d6  test    r8d, r8d
0x18005a6d9  jnz     short loc_18005A70D
0x18005a6db  mov     r8d, 13h
0x18005a6e1  lea     rdx, aX509dataX509sk; "<X509Data><X509SKI>"
0x18005a6e8  mov     rcx, r14
0x18005a6eb  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a6f0  mov     rdx, [rbp+arg_18]
0x18005a6f4  mov     r8d, [rdx-10h]
0x18005a6f8  mov     rcx, r14
0x18005a6fb  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a700  lea     rdx, aX509skiX509dat; "</X509SKI></X509Data>"
0x18005a707  mov     r8d, 15h
0x18005a70d  mov     rcx, r14
0x18005a710  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a715  mov     r8d, 16h
0x18005a71b  lea     rdx, aKeyinfoSignatu; "</KeyInfo></Signature>"
0x18005a722  mov     rcx, r14
0x18005a725  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a72a  jmp     short loc_18005A759
0x18005a72c  mov     edi, 80041319h
0x18005a731  lea     rax, aMReflistGetcou; "m_RefList.GetCount() != 0 && m_cryptPro"...
0x18005a738  mov     r8d, 9Ch; unsigned int
0x18005a73e  mov     qword ptr [rsp+70h+var_50], rax; char *
0x18005a743  mov     r9d, edi; int
0x18005a746  lea     rdx, aCxmlrsasha1sig_0; "CXmlRSASHA1Sig::ComputeSignature"
0x18005a74d  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18005a754  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005a759  lea     rcx, [rbp+phHash]; this
0x18005a75d  call    ?Destroy@CCryptHash@ATL@@QEAAXXZ; ATL::CCryptHash::Destroy(void)
0x18005a762  nop
0x18005a763  lea     rcx, [rbp+var_38]; this
0x18005a767  call    ?Release@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::Release(void)
0x18005a76c  nop
0x18005a76d  mov     rcx, [rbp+arg_18]
0x18005a771  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005a775  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005a77a  nop
0x18005a77b  mov     rcx, [rbp+var_40]
0x18005a77f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005a783  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005a788  nop
0x18005a789  lea     rcx, [rbp+var_18]; this
0x18005a78d  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18005a792  nop
0x18005a793  lea     rcx, [rbp+phHash]; this
0x18005a797  call    ?Destroy@CCryptHash@ATL@@QEAAXXZ; ATL::CCryptHash::Destroy(void)
0x18005a79c  mov     eax, edi
0x18005a79e  add     rsp, 70h
0x18005a7a2  pop     r15
0x18005a7a4  pop     r14
0x18005a7a6  pop     r12
0x18005a7a8  pop     rdi
0x18005a7a9  pop     rsi
0x18005a7aa  pop     rbx
0x18005a7ab  pop     rbp
0x18005a7ac  retn
```
