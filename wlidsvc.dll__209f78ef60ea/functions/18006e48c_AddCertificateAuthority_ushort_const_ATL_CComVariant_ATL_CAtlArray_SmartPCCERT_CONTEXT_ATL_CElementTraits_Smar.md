# AddCertificateAuthority(ushort const *,ATL::CComVariant &,ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>> &)

- ea: `0x18006e48c`
- end: `0x18006e6e8`
- name: `?AddCertificateAuthority@@YAJPEBGAEAVCComVariant@ATL@@AEAV?$CAtlArray@VSmartPCCERT_CONTEXT@@V?$CElementTraits@VSmartPCCERT_CONTEXT@@@ATL@@@2@@Z`
- size: `604`
- prototype: `__int64 __fastcall(void *pvPara)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e8b0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180016938`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180033218`
- `0x180034908`
- `0x1800451d0`
- `0x18004f970`
- `0x18004ff98`
- `0x18006e48c`
- `0x18007c408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e55d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e55d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e63a`
- `OLEAUT32!__imp_SysStringLen` at `0x18006e59c`
- `OLEAUT32!__imp_SysStringLen` at `0x18006e59c`
- `CRYPT32!CertOpenStore` at `0x18006e53f`
- `CRYPT32!CertOpenStore` at `0x18006e53f`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18006e630`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18006e630`
- `CRYPT32!CertCreateCertificateContext` at `0x18006e5d9`
- `CRYPT32!CertCreateCertificateContext` at `0x18006e5d9`

## string_xrefs

- `0x18006e4df`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AddCertificateAuthority(void *pvPara, __int64 a2, __int64 a3)
{
  HCERTSTORE v6; // rax
  signed int LastError; // eax
  int v8; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  PCCERT_CONTEXT v15; // rdx
  unsigned int v16; // ebx
  const unsigned __int16 *pvParaa; // [rsp+20h] [rbp-60h]
  void **v19; // [rsp+30h] [rbp-50h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-48h]
  void **v21; // [rsp+40h] [rbp-40h] BYREF
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-38h]
  int v23; // [rsp+50h] [rbp-30h]
  _QWORD v24[5]; // [rsp+58h] [rbp-28h] BYREF
  signed int v25; // [rsp+B8h] [rbp+38h] BYREF
  BYTE *pbCertEncoded; // [rsp+C8h] [rbp+48h] BYREF

  v25 = 0;
  v24[0] = "AddCertificateAuthority";
  v24[1] = &v25;
  v24[2] = 0;
  v24[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
    "AddCertificateAuthority",
    (const char *)0x37,
    0,
    pvParaa);
  hCertStore = 0;
  v21 = &SmartHCERTSTORE::`vftable';
  v23 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pbCertEncoded);
  pCertContext = 0;
  v19 = &SmartPCCERT_CONTEXT::`vftable';
  if ( *(_WORD *)a2 == 8 )
  {
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, pvPara);
    SmartPtr<void *>::Attach(&v21, v6);
    if ( !hCertStore )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v25 = LastError;
      if ( LastError < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
          "AddCertificateAuthority",
          0x48u,
          LastError,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
        goto LABEL_23;
      }
    }
    SysStringLen(*(BSTR *)(a2 + 8));
    v8 = PassportEncode::Base64Decode(*(void **)(a2 + 8));
    v25 = v8;
    if ( v8 >= 0 )
    {
      CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, *((_DWORD *)pbCertEncoded - 4));
      SmartPtr<void *>::Attach(&v19, CertificateContext);
      v10 = pCertContext;
      if ( !pCertContext )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        v25 = v11;
        if ( v11 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
            "AddCertificateAuthority",
            0x51u,
            v11,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
          goto LABEL_23;
        }
        v10 = pCertContext;
      }
      if ( CertAddCertificateContextToStore(hCertStore, v10, 3u, 0) )
        goto LABEL_21;
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v25 = v12;
      if ( v12 >= 0 )
      {
LABEL_21:
        v13 = *(_QWORD *)(a3 + 8);
        if ( !(unsigned __int8)ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::SetCount(
                                 a3,
                                 v13 + 1) )
          ATL::AtlThrowImpl(-2147024882);
        v14 = ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::operator[](a3, v13);
        v15 = pCertContext;
        pCertContext = 0;
        SmartPtr<void *>::Attach(v14, v15);
      }
      else
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
          "AddCertificateAuthority",
          0x56u,
          v12,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\configuration.cpp",
        "AddCertificateAuthority",
        0x4Cu,
        v8,
        "hr = PassportEncode::Base64Decode(varValue.bstrVal, SysStringLen(varValue.bstrVal), strCertificate)");
    }
  }
LABEL_23:
  v16 = v25;
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v19);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pbCertEncoded);
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v21);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v24);
  return v16;
}

```

## disassembly

```asm
0x18006e48c  mov     [rsp-28h+arg_0], rbx
0x18006e491  push    rbp
0x18006e492  push    rsi
0x18006e493  push    rdi
0x18006e494  push    r12
0x18006e496  push    r15
0x18006e498  mov     rbp, rsp
0x18006e49b  sub     rsp, 80h
0x18006e4a2  mov     rdi, r8
0x18006e4a5  mov     rbx, rdx
0x18006e4a8  mov     rsi, rcx
0x18006e4ab  mov     [rbp+arg_8], 0
0x18006e4b2  lea     r15, aAddcertificate_0; "AddCertificateAuthority"
0x18006e4b9  mov     [rbp+var_28], r15
0x18006e4bd  lea     rax, [rbp+arg_8]
0x18006e4c1  mov     [rbp+var_20], rax
0x18006e4c5  mov     [rbp+var_18], 0
0x18006e4cd  mov     [rbp+var_10], 0
0x18006e4d5  xor     r9d, r9d; unsigned int
0x18006e4d8  lea     r8d, [r9+37h]; char *
0x18006e4dc  mov     rdx, r15; char *
0x18006e4df  lea     r12, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006e4e6  mov     rcx, r12; this
0x18006e4e9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006e4ee  nop
0x18006e4ef  xor     eax, eax
0x18006e4f1  mov     [rbp+hCertStore], rax
0x18006e4f5  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x18006e4fc  mov     [rbp+var_40], rax
0x18006e500  mov     [rbp+var_30], 0
0x18006e507  lea     rcx, [rbp+pbCertEncoded]
0x18006e50b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006e510  nop
0x18006e511  xor     eax, eax
0x18006e513  mov     [rbp+pCertContext], rax
0x18006e517  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18006e51e  mov     [rbp+var_50], rax
0x18006e522  cmp     word ptr [rbx], 8
0x18006e526  jnz     loc_18006E69A
0x18006e52c  mov     [rsp+80h+pvPara], rsi; pvPara
0x18006e531  mov     r9d, 20000h; dwFlags
0x18006e537  xor     r8d, r8d; hCryptProv
0x18006e53a  xor     edx, edx; dwEncodingType
0x18006e53c  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18006e53f  call    cs:__imp_CertOpenStore
0x18006e545  mov     rdx, rax
0x18006e548  lea     rcx, [rbp+var_40]
0x18006e54c  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18006e551  mov     esi, 80070000h
0x18006e556  cmp     [rbp+hCertStore], 0
0x18006e55b  jnz     short loc_18006E598
0x18006e55d  call    cs:__imp_GetLastError
0x18006e563  test    eax, eax
0x18006e565  jle     short loc_18006E56C
0x18006e567  movzx   eax, ax
0x18006e56a  or      eax, esi
0x18006e56c  mov     [rbp+arg_8], eax
0x18006e56f  test    eax, eax
0x18006e571  jns     short loc_18006E598
0x18006e573  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006e57a  mov     [rsp+80h+pvPara], r8; char *
0x18006e57f  mov     r8d, 48h ; 'H'; unsigned int
0x18006e585  mov     r9d, eax; int
0x18006e588  mov     rdx, r15; char *
0x18006e58b  mov     rcx, r12; char *
0x18006e58e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006e593  jmp     loc_18006E69A
0x18006e598  mov     rcx, [rbx+8]; pbstr
0x18006e59c  call    cs:__imp_SysStringLen
0x18006e5a2  lea     r8, [rbp+pbCertEncoded]
0x18006e5a6  mov     edx, eax
0x18006e5a8  mov     rcx, [rbx+8]; Src
0x18006e5ac  call    ?Base64Decode@PassportEncode@@YAJPEBGKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Decode(ushort const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18006e5b1  mov     [rbp+arg_8], eax
0x18006e5b4  test    eax, eax
0x18006e5b6  jns     short loc_18006E5CC
0x18006e5b8  lea     rcx, aHrPassportenco_37; "hr = PassportEncode::Base64Decode(varVa"...
0x18006e5bf  mov     [rsp+80h+pvPara], rcx
0x18006e5c4  mov     r8d, 4Ch ; 'L'
0x18006e5ca  jmp     short loc_18006E585
0x18006e5cc  mov     rdx, [rbp+pbCertEncoded]; pbCertEncoded
0x18006e5d0  mov     r8d, [rdx-10h]; cbCertEncoded
0x18006e5d4  mov     ecx, 10001h; dwCertEncodingType
0x18006e5d9  call    cs:__imp_CertCreateCertificateContext
0x18006e5df  mov     rdx, rax
0x18006e5e2  lea     rcx, [rbp+var_50]
0x18006e5e6  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18006e5eb  mov     rdx, [rbp+pCertContext]
0x18006e5ef  test    rdx, rdx
0x18006e5f2  jnz     short loc_18006E625
0x18006e5f4  call    cs:__imp_GetLastError
0x18006e5fa  test    eax, eax
0x18006e5fc  jle     short loc_18006E603
0x18006e5fe  movzx   eax, ax
0x18006e601  or      eax, esi
0x18006e603  mov     [rbp+arg_8], eax
0x18006e606  test    eax, eax
0x18006e608  jns     short loc_18006E621
0x18006e60a  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006e611  mov     [rsp+80h+pvPara], r8
0x18006e616  mov     r8d, 51h ; 'Q'
0x18006e61c  jmp     loc_18006E585
0x18006e621  mov     rdx, [rbp+pCertContext]; pCertContext
0x18006e625  xor     r9d, r9d; ppStoreContext
0x18006e628  lea     r8d, [r9+3]; dwAddDisposition
0x18006e62c  mov     rcx, [rbp+hCertStore]; hCertStore
0x18006e630  call    cs:__imp_CertAddCertificateContextToStore
0x18006e636  test    eax, eax
0x18006e638  jnz     short loc_18006E667
0x18006e63a  call    cs:__imp_GetLastError
0x18006e640  test    eax, eax
0x18006e642  jle     short loc_18006E649
0x18006e644  movzx   eax, ax
0x18006e647  or      eax, esi
0x18006e649  mov     [rbp+arg_8], eax
0x18006e64c  test    eax, eax
0x18006e64e  jns     short loc_18006E667
0x18006e650  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18006e657  mov     [rsp+80h+pvPara], r8
0x18006e65c  mov     r8d, 56h ; 'V'
0x18006e662  jmp     loc_18006E585
0x18006e667  mov     rbx, [rdi+8]
0x18006e66b  lea     rdx, [rbx+1]
0x18006e66f  mov     rcx, rdi
0x18006e672  call    ?SetCount@?$CAtlArray@VSmartPCCERT_CONTEXT@@V?$CElementTraits@VSmartPCCERT_CONTEXT@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::SetCount(unsigned __int64,int)
0x18006e677  test    al, al
0x18006e679  jz      short loc_18006E6DD
0x18006e67b  mov     rdx, rbx
0x18006e67e  mov     rcx, rdi
0x18006e681  call    ??A?$CAtlArray@VSmartPCCERT_CONTEXT@@V?$CElementTraits@VSmartPCCERT_CONTEXT@@@ATL@@@ATL@@QEAAAEAVSmartPCCERT_CONTEXT@@_K@Z; ATL::CAtlArray<SmartPCCERT_CONTEXT,ATL::CElementTraits<SmartPCCERT_CONTEXT>>::operator[](unsigned __int64)
0x18006e686  mov     rdx, [rbp+pCertContext]
0x18006e68a  mov     [rbp+pCertContext], 0
0x18006e692  mov     rcx, rax
0x18006e695  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18006e69a  mov     ebx, [rbp+arg_8]
0x18006e69d  lea     rcx, [rbp+var_50]; this
0x18006e6a1  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18006e6a6  nop
0x18006e6a7  lea     rcx, [rbp+pbCertEncoded]
0x18006e6ab  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006e6b0  nop
0x18006e6b1  lea     rcx, [rbp+var_40]; this
0x18006e6b5  call    ??1SmartHCERTSTORE@@UEAA@XZ; SmartHCERTSTORE::~SmartHCERTSTORE(void)
0x18006e6ba  nop
0x18006e6bb  lea     rcx, [rbp+var_28]
0x18006e6bf  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006e6c4  mov     eax, ebx
0x18006e6c6  mov     rbx, [rsp+80h+arg_0]
0x18006e6ce  add     rsp, 80h
0x18006e6d5  pop     r15
0x18006e6d7  pop     r12
0x18006e6d9  pop     rdi
0x18006e6da  pop     rsi
0x18006e6db  pop     rbp
0x18006e6dc  retn
0x18006e6dd  mov     ecx, 8007000Eh; int
0x18006e6e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
