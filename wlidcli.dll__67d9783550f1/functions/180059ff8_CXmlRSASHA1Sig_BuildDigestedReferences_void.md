# CXmlRSASHA1Sig::BuildDigestedReferences(void)

- ea: `0x180059ff8`
- end: `0x18005a1ff`
- name: `?BuildDigestedReferences@CXmlRSASHA1Sig@@AEAAJXZ`
- size: `519`
- prototype: `__int64 __fastcall(CXmlRSASHA1Sig *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a3bc`

## callees

- `0x18000a914`
- `0x18000ade0`
- `0x18000ba8c`
- `0x180012da8`
- `0x18001b00c`
- `0x18001d310`
- `0x180053890`
- `0x180057e4c`
- `0x180059ff8`
- `0x18005a208`

## string_xrefs

- `0x18005a01f`: `<Signature xmlns="http://www.w3.org/2000/09/xmldsig#"><SignedInfo>`
- `0x18005a050`: `http://www.w3.org/2000/09/xmldsig#rsa-sha1`
- `0x18005a03d`: `<CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"></CanonicalizationMethod><SignatureMethod Algorithm="`
- `0x18005a188`: `CXmlRSASHA1Sig::BuildDigestedReferences`
- `0x18005a173`: `!xmlRef.IsEmpty()`
- `0x18005a18f`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig.cpp`
- `0x18005a15f`: `hr = ComputeReferenceDigest(xmlRef, strEncodedDigest)`
- `0x18005a0ea`: `<Transforms><Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"></Transform><Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"></Transform></Transforms><DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"></DigestMethod><DigestValue>`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CXmlRSASHA1Sig::BuildDigestedReferences(CXmlRSASHA1Sig *this)
{
  int v2; // ebx
  __int64 *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // r8
  const char *v6; // rax
  unsigned int v7; // r8d
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v10);
  ATL::CSimpleStringT<char,0>::SetString(
    (char *)this + 56,
    "<Signature xmlns=\"http://www.w3.org/2000/09/xmldsig#\"><SignedInfo>",
    66);
  *((_DWORD *)this + 18) = *(_DWORD *)(*((_QWORD *)this + 7) - 16LL);
  ATL::CSimpleStringT<char,0>::Append(
    (char *)this + 56,
    "<CanonicalizationMethod Algorithm=\"http://www.w3.org/2001/10/xml-exc-c14n#\"></CanonicalizationMethod><SignatureMet"
    "hod Algorithm=\"",
    129);
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "http://www.w3.org/2000/09/xmldsig#rsa-sha1", 42);
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "\"></SignatureMethod>", 20);
  while ( *((_QWORD *)this + 2) )
  {
    v3 = *(__int64 **)this;
    if ( !*(_QWORD *)this )
      ATL::AtlThrowImpl(-2147467259);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
      &v9,
      v3 + 2);
    v4 = *v3;
    *(_QWORD *)this = *v3;
    if ( v4 )
      *(_QWORD *)(v4 + 8) = 0;
    else
      *((_QWORD *)this + 1) = 0;
    ATL::CAtlList<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CElementTraits<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>>>::FreeNode(
      this,
      v3);
    if ( !*(_DWORD *)(v9 - 16) )
    {
      v2 = -2147216615;
      v6 = "!xmlRef.IsEmpty()";
      v7 = 56;
      goto LABEL_16;
    }
    ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "<Reference>", 11);
    ATL::CSimpleStringT<char,0>::Append(
      (char *)this + 56,
      "<Transforms><Transform Algorithm=\"http://www.w3.org/2000/09/xmldsig#enveloped-signature\"></Transform><Transform "
      "Algorithm=\"http://www.w3.org/2001/10/xml-exc-c14n#\"></Transform></Transforms><DigestMethod Algorithm=\"http://ww"
      "w.w3.org/2000/09/xmldsig#sha1\"></DigestMethod><DigestValue>",
      282);
    v2 = CXmlRSASHA1Sig::ComputeReferenceDigest(this, &v9, &v10);
    if ( v2 < 0 )
    {
      v6 = "hr = ComputeReferenceDigest(xmlRef, strEncodedDigest)";
      v7 = 68;
LABEL_16:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig.cpp",
        "CXmlRSASHA1Sig::BuildDigestedReferences",
        v7,
        v2,
        v6);
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
      ATL::CSimpleStringT<char,0>::SetString((char *)this + 56, MultiByteStr, 0);
      goto LABEL_18;
    }
    if ( v10 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_BYTE *)(v10 + v5) );
    }
    else
    {
      v5 = 0;
    }
    ATL::CSimpleStringT<char,0>::Append((char *)this + 56, v10, v5);
    ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "</DigestValue></Reference>", 26);
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
  }
  ATL::CSimpleStringT<char,0>::Append((char *)this + 56, "</SignedInfo>", 13);
LABEL_18:
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180059ff8  mov     [rsp+arg_10], rbx
0x180059ffd  mov     [rsp+arg_18], rsi
0x18005a002  push    rdi
0x18005a003  sub     rsp, 30h
0x18005a007  mov     rdi, rcx
0x18005a00a  xor     ebx, ebx
0x18005a00c  lea     rcx, [rsp+38h+arg_8]
0x18005a011  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005a016  nop
0x18005a017  lea     rsi, [rdi+38h]
0x18005a01b  lea     r8d, [rbx+42h]
0x18005a01f  lea     rdx, aSignatureXmlns; "<Signature xmlns=\"http://www.w3.org/20"...
0x18005a026  mov     rcx, rsi
0x18005a029  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x18005a02e  mov     rax, [rsi]
0x18005a031  mov     ecx, [rax-10h]
0x18005a034  mov     [rdi+48h], ecx
0x18005a037  mov     r8d, 81h
0x18005a03d  lea     rdx, aCanonicalizati; "<CanonicalizationMethod Algorithm=\"htt"...
0x18005a044  mov     rcx, rsi
0x18005a047  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a04c  lea     r8d, [rbx+2Ah]
0x18005a050  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x18005a057  mov     rcx, rsi
0x18005a05a  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a05f  lea     r8d, [rbx+14h]
0x18005a063  lea     rdx, aSignaturemetho; "\"></SignatureMethod>"
0x18005a06a  mov     rcx, rsi
0x18005a06d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a072  cmp     qword ptr [rdi+10h], 0
0x18005a077  jz      loc_18005A1BE
0x18005a07d  mov     rbx, [rdi]
0x18005a080  test    rbx, rbx
0x18005a083  jz      loc_18005A1F4
0x18005a089  lea     rdx, [rbx+10h]
0x18005a08d  lea     rcx, [rsp+38h+arg_0]
0x18005a092  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18005a097  mov     rax, [rbx]
0x18005a09a  mov     [rdi], rax
0x18005a09d  test    rax, rax
0x18005a0a0  jz      short loc_18005A0AC
0x18005a0a2  mov     qword ptr [rax+8], 0
0x18005a0aa  jmp     short loc_18005A0B4
0x18005a0ac  mov     qword ptr [rdi+8], 0
0x18005a0b4  mov     rdx, rbx
0x18005a0b7  mov     rcx, rdi
0x18005a0ba  call    ?FreeNode@?$CAtlList@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CElementTraits<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>>>::FreeNode(ATL::CAtlList<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CElementTraits<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>>>::CNode *)
0x18005a0bf  nop
0x18005a0c0  mov     rax, [rsp+38h+arg_0]
0x18005a0c5  cmp     dword ptr [rax-10h], 0
0x18005a0c9  jz      loc_18005A16E
0x18005a0cf  mov     r8d, 0Bh
0x18005a0d5  lea     rdx, aReference; "<Reference>"
0x18005a0dc  mov     rcx, rsi
0x18005a0df  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a0e4  mov     r8d, 11Ah
0x18005a0ea  lea     rdx, aTransformsTran; "<Transforms><Transform Algorithm=\"http"...
0x18005a0f1  mov     rcx, rsi
0x18005a0f4  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a0f9  lea     r8, [rsp+38h+arg_8]
0x18005a0fe  lea     rdx, [rsp+38h+arg_0]
0x18005a103  mov     rcx, rdi
0x18005a106  call    ?ComputeReferenceDigest@CXmlRSASHA1Sig@@AEAAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV23@@Z; CXmlRSASHA1Sig::ComputeReferenceDigest(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18005a10b  mov     ebx, eax
0x18005a10d  test    eax, eax
0x18005a10f  js      short loc_18005A15F
0x18005a111  mov     rdx, [rsp+38h+arg_8]
0x18005a116  test    rdx, rdx
0x18005a119  jnz     short loc_18005A120
0x18005a11b  xor     r8d, r8d
0x18005a11e  jmp     short loc_18005A12E
0x18005a120  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005a124  inc     r8
0x18005a127  cmp     byte ptr [rdx+r8], 0
0x18005a12c  jnz     short loc_18005A124
0x18005a12e  mov     rcx, rsi
0x18005a131  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a136  mov     r8d, 1Ah
0x18005a13c  lea     rdx, aDigestvalueRef; "</DigestValue></Reference>"
0x18005a143  mov     rcx, rsi
0x18005a146  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a14b  nop
0x18005a14c  mov     rcx, [rsp+38h+arg_0]
0x18005a151  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005a155  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005a15a  jmp     loc_18005A072
0x18005a15f  lea     rax, aHrComputerefer; "hr = ComputeReferenceDigest(xmlRef, str"...
0x18005a166  mov     r8d, 44h ; 'D'
0x18005a16c  jmp     short loc_18005A180
0x18005a16e  mov     ebx, 80041319h
0x18005a173  lea     rax, aXmlrefIsempty; "!xmlRef.IsEmpty()"
0x18005a17a  mov     r8d, 38h ; '8'; unsigned int
0x18005a180  mov     [rsp+38h+var_18], rax; char *
0x18005a185  mov     r9d, ebx; int
0x18005a188  lea     rdx, aCxmlrsasha1sig; "CXmlRSASHA1Sig::BuildDigestedReferences"
0x18005a18f  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18005a196  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005a19b  nop
0x18005a19c  mov     rcx, [rsp+38h+arg_0]
0x18005a1a1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005a1a5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005a1aa  xor     r8d, r8d
0x18005a1ad  lea     rdx, MultiByteStr
0x18005a1b4  mov     rcx, rsi
0x18005a1b7  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x18005a1bc  jmp     short loc_18005A1D4
0x18005a1be  mov     r8d, 0Dh
0x18005a1c4  lea     rdx, aSignedinfo; "</SignedInfo>"
0x18005a1cb  mov     rcx, rsi
0x18005a1ce  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005a1d3  nop
0x18005a1d4  mov     rcx, [rsp+38h+arg_8]
0x18005a1d9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005a1dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005a1e2  mov     eax, ebx
0x18005a1e4  mov     rbx, [rsp+38h+arg_10]
0x18005a1e9  mov     rsi, [rsp+38h+arg_18]
0x18005a1ee  add     rsp, 30h
0x18005a1f2  pop     rdi
0x18005a1f3  retn
0x18005a1f4  mov     ecx, 80004005h; int
0x18005a1f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
