# CXmlRSASHA1Sig::ComputeReferenceDigest(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18005a208`
- end: `0x18005a3b3`
- name: `?ComputeReferenceDigest@CXmlRSASHA1Sig@@AEAAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `427`
- prototype: `__int64 __fastcall(__int64, const unsigned __int8 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059ff8`

## callees

- `0x180005a7c`
- `0x18000d1c8`
- `0x18000d438`
- `0x18000dff0`
- `0x18000e728`
- `0x18000fa44`
- `0x18000fa9c`
- `0x1800114b0`
- `0x18001b710`
- `0x180053890`
- `0x18005a208`
- `0x18005a8c0`

## import_xrefs

- `CRYPTSP!CryptGetHashParam` at `0x18005a2ab`
- `CRYPTSP!CryptGetHashParam` at `0x18005a2fa`
- `CRYPTSP!CryptGetHashParam` at `0x18005a2ab`
- `CRYPTSP!CryptGetHashParam` at `0x18005a2fa`

## string_xrefs

- `0x18005a384`: `onecoreuap\ds\ext\live\identity\passport\lib\xmlsig\xmlsig.cpp`
- `0x18005a37d`: `CXmlRSASHA1Sig::ComputeReferenceDigest`
- `0x18005a27d`: `hr = cryptSHA1ReferenceHash.AddData( (const PBYTE)((LPCSTR)xmlRef), xmlRef.GetLength())`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CXmlRSASHA1Sig::ComputeReferenceDigest(
        __int64 a1,
        const unsigned __int8 **a2,
        const unsigned __int16 *a3)
{
  signed int Error; // edi
  unsigned int v6; // r9d
  const char *v7; // rax
  unsigned int v8; // r8d
  char *BufferSetLength; // rax
  int v10; // ebx
  HCRYPTHASH hHash; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+38h] [rbp-18h] BYREF
  BYTE *v14; // [rsp+40h] [rbp-10h]
  int v15; // [rsp+48h] [rbp-8h]
  DWORD pbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD pdwDataLen; // [rsp+88h] [rbp+38h] BYREF

  hHash = 0;
  pbData = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  Error = ATL::CCryptSHAHash::Initialize(&hHash, (struct ATL::CCryptProv *)(a1 + 64), a3);
  if ( Error < 0 )
  {
    v7 = "hr = cryptSHA1ReferenceHash.Initialize(m_cryptProv)";
    v8 = 108;
LABEL_14:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\passport\\lib\\xmlsig\\xmlsig.cpp",
      "CXmlRSASHA1Sig::ComputeReferenceDigest",
      v8,
      Error,
      v7);
    goto LABEL_15;
  }
  Error = ATL::CCryptHash::AddData((ATL::CCryptHash *)&hHash, *a2, *((_DWORD *)*a2 - 4), v6);
  if ( Error < 0 )
  {
    v7 = "hr = cryptSHA1ReferenceHash.AddData( (const PBYTE)((LPCSTR)xmlRef), xmlRef.GetLength())";
    v8 = 112;
    goto LABEL_14;
  }
  pdwDataLen = 4;
  if ( !CryptGetHashParam(hHash, 4u, (BYTE *)&pbData, &pdwDataLen, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
    {
      v7 = "hr = cryptSHA1ReferenceHash.GetSize(&dwSize)";
      v8 = 115;
      goto LABEL_14;
    }
  }
  CBytePtr::SetLength((CBytePtr *)&v13, pbData, 0);
  if ( CryptGetHashParam(hHash, 2u, v14, &pbData, 0) )
  {
    Error = 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error < 0 )
    {
      v7 = "hr = cryptSHA1ReferenceHash.GetValue( bpDigest.GetBufferSetLength(dwSize, FALSE), &dwSize)";
      v8 = 120;
      goto LABEL_14;
    }
  }
  pdwDataLen = ATL::Base64EncodeGetRequiredLength(v13, 0);
  BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(a3, pdwDataLen);
  v10 = ATL::Base64Encode(v14, v13, BufferSetLength, (int *)&pdwDataLen, 0);
  ATL::CSimpleStringT<char,0>::ReleaseBuffer(a3, pdwDataLen);
  if ( !v10 )
  {
    Error = -2147197938;
    v7 = "bRet";
    v8 = 135;
    goto LABEL_14;
  }
LABEL_15:
  CBytePtr::Empty((CBytePtr *)&v13);
  ATL::CCryptHash::Destroy((ATL::CCryptHash *)&hHash);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005a208  mov     [rsp-18h+arg_8], rbx
0x18005a20d  push    rbp
0x18005a20e  push    rsi
0x18005a20f  push    rdi
0x18005a210  mov     rbp, rsp
0x18005a213  sub     rsp, 50h
0x18005a217  mov     rsi, r8
0x18005a21a  mov     rbx, rdx
0x18005a21d  mov     [rbp+hHash], 0
0x18005a225  mov     [rbp+pbData], 0
0x18005a22c  mov     [rbp+var_10], 0
0x18005a234  mov     [rbp+var_18], 0
0x18005a23b  mov     [rbp+var_8], 0
0x18005a242  lea     rdx, [rcx+40h]; struct ATL::CCryptProv *
0x18005a246  lea     rcx, [rbp+hHash]; phHash
0x18005a24a  call    ?Initialize@CCryptSHAHash@ATL@@QEAAJAEAVCCryptProv@2@PEBG@Z; ATL::CCryptSHAHash::Initialize(ATL::CCryptProv &,ushort const *)
0x18005a24f  mov     edi, eax
0x18005a251  test    eax, eax
0x18005a253  jns     short loc_18005A267
0x18005a255  lea     rax, aHrCryptsha1ref; "hr = cryptSHA1ReferenceHash.Initialize("...
0x18005a25c  mov     r8d, 6Ch ; 'l'
0x18005a262  jmp     loc_18005A375
0x18005a267  mov     rdx, [rbx]; unsigned __int8 *
0x18005a26a  mov     r8d, [rdx-10h]; unsigned int
0x18005a26e  lea     rcx, [rbp+hHash]; this
0x18005a272  call    ?AddData@CCryptHash@ATL@@QEAAJPEBEKK@Z; ATL::CCryptHash::AddData(uchar const *,ulong,ulong)
0x18005a277  mov     edi, eax
0x18005a279  test    eax, eax
0x18005a27b  jns     short loc_18005A28F
0x18005a27d  lea     rax, aHrCryptsha1ref_0; "hr = cryptSHA1ReferenceHash.AddData( (c"...
0x18005a284  mov     r8d, 70h ; 'p'
0x18005a28a  jmp     loc_18005A375
0x18005a28f  mov     edx, 4; dwParam
0x18005a294  mov     [rbp+pdwDataLen], edx
0x18005a297  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18005a29f  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18005a2a3  lea     r8, [rbp+pbData]; pbData
0x18005a2a7  mov     rcx, [rbp+hHash]; hHash
0x18005a2ab  call    cs:__imp_CryptGetHashParam
0x18005a2b1  test    eax, eax
0x18005a2b3  jnz     short loc_18005A2D2
0x18005a2b5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005a2ba  mov     edi, eax
0x18005a2bc  test    eax, eax
0x18005a2be  jns     short loc_18005A2D2
0x18005a2c0  lea     rax, aHrCryptsha1ref_1; "hr = cryptSHA1ReferenceHash.GetSize(&dw"...
0x18005a2c7  mov     r8d, 73h ; 's'
0x18005a2cd  jmp     loc_18005A375
0x18005a2d2  xor     r8d, r8d; bool
0x18005a2d5  mov     edx, [rbp+pbData]; unsigned int
0x18005a2d8  lea     rcx, [rbp+var_18]; this
0x18005a2dc  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x18005a2e1  mov     [rsp+50h+dwFlags], 0; dwFlags
0x18005a2e9  lea     r9, [rbp+pbData]; pdwDataLen
0x18005a2ed  mov     r8, [rbp+var_10]; pbData
0x18005a2f1  mov     edx, 2; dwParam
0x18005a2f6  mov     rcx, [rbp+hHash]; hHash
0x18005a2fa  call    cs:__imp_CryptGetHashParam
0x18005a300  test    eax, eax
0x18005a302  jnz     short loc_18005A31E
0x18005a304  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005a309  mov     edi, eax
0x18005a30b  test    eax, eax
0x18005a30d  jns     short loc_18005A320
0x18005a30f  lea     rax, aHrCryptsha1ref_2; "hr = cryptSHA1ReferenceHash.GetValue( b"...
0x18005a316  mov     r8d, 78h ; 'x'
0x18005a31c  jmp     short loc_18005A375
0x18005a31e  xor     edi, edi
0x18005a320  xor     edx, edx; unsigned int
0x18005a322  mov     ecx, [rbp+var_18]; int
0x18005a325  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18005a32a  mov     [rbp+pdwDataLen], eax
0x18005a32d  mov     edx, eax
0x18005a32f  mov     rcx, rsi
0x18005a332  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18005a337  mov     [rsp+50h+dwFlags], 0; unsigned int
0x18005a33f  lea     r9, [rbp+pdwDataLen]; int *
0x18005a343  mov     r8, rax; char *
0x18005a346  mov     edx, [rbp+var_18]; int
0x18005a349  mov     rcx, [rbp+var_10]; unsigned __int8 *
0x18005a34d  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x18005a352  mov     ebx, eax
0x18005a354  mov     edx, [rbp+pdwDataLen]
0x18005a357  mov     rcx, rsi
0x18005a35a  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18005a35f  test    ebx, ebx
0x18005a361  jnz     short loc_18005A391
0x18005a363  mov     edi, 80045C0Eh
0x18005a368  lea     rax, aBret; "bRet"
0x18005a36f  mov     r8d, 87h; unsigned int
0x18005a375  mov     qword ptr [rsp+50h+dwFlags], rax; char *
0x18005a37a  mov     r9d, edi; int
0x18005a37d  lea     rdx, aCxmlrsasha1sig_2; "CXmlRSASHA1Sig::ComputeReferenceDigest"
0x18005a384  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\pa"...
0x18005a38b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005a390  nop
0x18005a391  lea     rcx, [rbp+var_18]; this
0x18005a395  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x18005a39a  nop
0x18005a39b  lea     rcx, [rbp+hHash]; this
0x18005a39f  call    ?Destroy@CCryptHash@ATL@@QEAAXXZ; ATL::CCryptHash::Destroy(void)
0x18005a3a4  mov     eax, edi
0x18005a3a6  mov     rbx, [rsp+50h+arg_8]
0x18005a3ab  add     rsp, 50h
0x18005a3af  pop     rdi
0x18005a3b0  pop     rsi
0x18005a3b1  pop     rbp
0x18005a3b2  retn
```
