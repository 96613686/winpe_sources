# CScriptedDiag::VerifyPackageTrust(ushort const *)

- ea: `0x180011ba4`
- end: `0x180011fd6`
- name: `?VerifyPackageTrust@CScriptedDiag@@AEAAJPEBG@Z`
- size: `1074`
- prototype: `__int64 __fastcall(CScriptedDiag *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800101cc`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x18000680c`
- `0x180006ca0`
- `0x180007184`
- `0x1800073a0`
- `0x1800077a0`
- `0x180007bc0`
- `0x180011ba4`
- `0x18001e6c0`
- `0x18001eaf0`
- `0x18001eb94`
- `0x180026fa0`
- `0x1800278d4`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180011fa4`
- `CRYPT32!CertFreeCertificateContext` at `0x180011fb6`
- `CRYPT32!CertFreeCertificateContext` at `0x180011fa4`
- `CRYPT32!CertFreeCertificateContext` at `0x180011fb6`
- `CRYPT32!CertCompareCertificate` at `0x180011ebc`
- `CRYPT32!CertCompareCertificate` at `0x180011ebc`

## string_xrefs

- `0x180011ed3`: `SdpCompareCertificate`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::VerifyPackageTrust(CScriptedDiag *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // r12
  WCHAR *v6; // r13
  PCCERT_CONTEXT v7; // r14
  unsigned int v8; // ebx
  int v9; // r8d
  int SubjectName; // eax
  int v11; // r8d
  int Certificate; // eax
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // r9d
  int Locale; // eax
  int v18; // eax
  int v19; // r8d
  int v20; // eax
  int v21; // r8d
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // r8
  int v25; // [rsp+20h] [rbp-50h] BYREF
  int v26; // [rsp+24h] [rbp-4Ch] BYREF
  unsigned __int16 *v27; // [rsp+28h] [rbp-48h] BYREF
  void *Block; // [rsp+30h] [rbp-40h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v30; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v33; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp-10h] BYREF
  PCCERT_CONTEXT v35; // [rsp+68h] [rbp-8h] BYREF
  int v37; // [rsp+C0h] [rbp+50h] BYREF
  int v38; // [rsp+C8h] [rbp+58h] BYREF

  Block = 0;
  v30 = 0;
  v4 = 0;
  v27 = 0;
  v5 = 0;
  v32 = 0;
  v6 = 0;
  lpFileName = 0;
  v7 = 0;
  v33 = 0;
  pCertContext = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  v25 = 0;
  v26 = 0;
  v34 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 1440;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", v9, v8);
    return v8;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v8 = -2147467261;
    v9 = 1442;
    goto LABEL_3;
  }
  SubjectName = SdpBuildPath(a2, L"DiagPackage.cat", (unsigned __int16 **)&Block);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1449;
LABEL_52:
    v16 = SubjectName;
    goto LABEL_53;
  }
  SubjectName = SdpVerifyDirectoryTrust(a2, (const unsigned __int16 *)Block);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1452;
    goto LABEL_52;
  }
  Certificate = SdpGetCertificate((LPCWSTR)Block, &pCertContext, &v37, &v38);
  v8 = Certificate;
  if ( Certificate < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", 1458, Certificate);
    v7 = pCertContext;
    goto LABEL_54;
  }
  if ( v37 )
    *((_DWORD *)this + 12) |= 1u;
  v13 = *((_QWORD *)this + 3);
  v14 = *(_DWORD *)(v13 + 56);
  if ( v38 )
    v15 = v14 | 0x400;
  else
    v15 = v14 & 0xFFFFFBFF;
  v7 = pCertContext;
  *(_DWORD *)(v13 + 56) = v15;
  SubjectName = SdpGetSubjectName(v7, &v34);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1468;
    goto LABEL_52;
  }
  Settings::set_PackagePublisher(*((Settings **)this + 3), v34);
  SubjectName = SdpShouldValidateTrust(&v25);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1478;
    goto LABEL_52;
  }
  if ( v25 )
  {
    SubjectName = SdpIsTrusted(v7, &v26);
    v8 = SubjectName;
    if ( SubjectName < 0 )
    {
      v11 = 1482;
      goto LABEL_52;
    }
    if ( !v26 )
    {
      v8 = -2143551225;
      v11 = 1486;
LABEL_26:
      v16 = v8;
LABEL_53:
      SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", v11, v16);
      goto LABEL_54;
    }
  }
  Locale = Settings::get_Locale(*((Settings **)this + 3), &v30);
  v8 = Locale;
  if ( Locale < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", 1495, Locale);
    v4 = v30;
    goto LABEL_54;
  }
  v4 = v30;
  if ( !v30 )
    goto LABEL_54;
  v18 = SdpBuildPath(a2, v30, &v27);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1507;
LABEL_32:
    SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", v19, v18);
    v5 = v27;
    goto LABEL_54;
  }
  v18 = SdpStrCat(v4, L"cat", 0x2Eu, &v32);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1510;
    goto LABEL_32;
  }
  v5 = v27;
  v20 = SdpBuildPath(v27, v32, (unsigned __int16 **)&lpFileName);
  v8 = v20;
  if ( v20 < 0 )
  {
    SdpDebugTrace(1u, L"CScriptedDiag::VerifyPackageTrust", 1513, v20);
    v6 = (WCHAR *)lpFileName;
    goto LABEL_54;
  }
  v6 = (WCHAR *)lpFileName;
  SubjectName = SdpVerifyDirectoryTrust(v5, lpFileName);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1516;
    goto LABEL_52;
  }
  SubjectName = SdpGetCertificate(v6, &v35, 0, 0);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1526;
    goto LABEL_52;
  }
  if ( !v7 )
  {
    v8 = -2147024809;
    v21 = 974;
LABEL_47:
    SdpDebugTrace(1u, L"SdpCompareCertificate", v21, v8);
    v11 = 1535;
    goto LABEL_26;
  }
  if ( !v35 )
  {
    v8 = -2147024809;
    v21 = 975;
    goto LABEL_47;
  }
  if ( !CertCompareCertificate(v7->dwCertEncodingType, v7->pCertInfo, v35->pCertInfo) )
  {
    v8 = -2147418113;
    v21 = 981;
    goto LABEL_47;
  }
  SubjectName = SdpGetCatalogAttribute(v6, v22, v23, &v33);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1548;
    goto LABEL_52;
  }
  SubjectName = Settings::set_PackageId(*((Settings **)this + 3), v33);
  v8 = SubjectName;
  if ( SubjectName < 0 )
  {
    v11 = 1551;
    goto LABEL_52;
  }
LABEL_54:
  if ( Block )
    operator delete(Block);
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  if ( v32 )
    operator delete(v32);
  if ( v6 )
    operator delete(v6);
  if ( v33 )
    operator delete(v33);
  if ( v34 )
    operator delete(v34);
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( v35 )
    CertFreeCertificateContext(v35);
  return v8;
}

```

## disassembly

```asm
0x180011ba4  mov     [rsp-38h+arg_0], rbx
0x180011ba9  mov     [rsp-38h+arg_8], rdx
0x180011bae  push    rbp
0x180011baf  push    rsi
0x180011bb0  push    rdi
0x180011bb1  push    r12
0x180011bb3  push    r13
0x180011bb5  push    r14
0x180011bb7  push    r15
0x180011bb9  mov     rbp, rsp
0x180011bbc  sub     rsp, 70h
0x180011bc0  xor     eax, eax
0x180011bc2  mov     rdi, rdx
0x180011bc5  mov     [rbp+Block], rax
0x180011bc9  mov     rsi, rcx
0x180011bcc  mov     [rbp+var_30], rax
0x180011bd0  mov     r15d, eax
0x180011bd3  mov     [rbp+var_48], rax
0x180011bd7  mov     r12d, eax
0x180011bda  mov     [rbp+var_20], rax
0x180011bde  mov     r13d, eax
0x180011be1  mov     [rbp+lpFileName], rax
0x180011be5  mov     r14d, eax
0x180011be8  mov     [rbp+var_18], rax
0x180011bec  mov     [rbp+pCertContext], rax
0x180011bf0  mov     [rbp+var_8], rax
0x180011bf4  mov     [rbp+arg_10], eax
0x180011bf7  mov     [rbp+arg_18], eax
0x180011bfa  mov     [rbp+var_50], eax
0x180011bfd  mov     [rbp+var_4C], eax
0x180011c00  mov     [rbp+var_10], rax
0x180011c04  test    rdx, rdx
0x180011c07  jnz     short loc_180011C2D
0x180011c09  mov     ebx, 80070057h
0x180011c0e  mov     r8d, 5A0h; int
0x180011c14  mov     r9d, ebx; int
0x180011c17  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011c1e  mov     ecx, 1; Level
0x180011c23  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011c28  jmp     loc_180011FBC
0x180011c2d  cmp     [rcx+18h], rax
0x180011c31  jnz     short loc_180011C40
0x180011c33  mov     ebx, 80004003h
0x180011c38  mov     r8d, 5A2h
0x180011c3e  jmp     short loc_180011C14
0x180011c40  lea     r8, [rbp+Block]; unsigned __int16 **
0x180011c44  mov     rcx, rdi; unsigned __int16 *
0x180011c47  lea     rdx, aDiagpackageCat; "DiagPackage.cat"
0x180011c4e  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180011c53  mov     ebx, eax
0x180011c55  test    eax, eax
0x180011c57  jns     short loc_180011C69
0x180011c59  mov     r8d, 5A9h
0x180011c5f  mov     ecx, 1
0x180011c64  jmp     loc_180011F22
0x180011c69  mov     rdx, [rbp+Block]; unsigned __int16 *
0x180011c6d  mov     rcx, rdi; unsigned __int16 *
0x180011c70  call    ?SdpVerifyDirectoryTrust@@YAJPEBG0@Z; SdpVerifyDirectoryTrust(ushort const *,ushort const *)
0x180011c75  mov     ebx, eax
0x180011c77  test    eax, eax
0x180011c79  jns     short loc_180011C83
0x180011c7b  mov     r8d, 5ACh
0x180011c81  jmp     short loc_180011C5F
0x180011c83  mov     rcx, [rbp+Block]; lpFileName
0x180011c87  lea     r9, [rbp+arg_18]; int *
0x180011c8b  lea     r8, [rbp+arg_10]; int *
0x180011c8f  lea     rdx, [rbp+pCertContext]; struct _CERT_CONTEXT **
0x180011c93  call    ?SdpGetCertificate@@YAJPEBGPEAPEBU_CERT_CONTEXT@@PEAH2@Z; SdpGetCertificate(ushort const *,_CERT_CONTEXT const * *,int *,int *)
0x180011c98  mov     ebx, eax
0x180011c9a  test    eax, eax
0x180011c9c  jns     short loc_180011CC1
0x180011c9e  mov     r9d, eax; int
0x180011ca1  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011ca8  mov     r8d, 5B2h; int
0x180011cae  mov     ecx, 1; Level
0x180011cb3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011cb8  mov     r14, [rbp+pCertContext]
0x180011cbc  jmp     loc_180011F31
0x180011cc1  mov     edi, 1
0x180011cc6  cmp     [rbp+arg_10], r12d
0x180011cca  jz      short loc_180011CCF
0x180011ccc  or      [rsi+30h], edi
0x180011ccf  mov     rcx, [rsi+18h]
0x180011cd3  mov     eax, [rcx+38h]
0x180011cd6  cmp     [rbp+arg_18], r12d
0x180011cda  jz      short loc_180011CE2
0x180011cdc  bts     eax, 0Ah
0x180011ce0  jmp     short loc_180011CE6
0x180011ce2  btr     eax, 0Ah
0x180011ce6  mov     r14, [rbp+pCertContext]
0x180011cea  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x180011cee  mov     [rcx+38h], eax
0x180011cf1  mov     rcx, r14; pCertContext
0x180011cf4  call    ?SdpGetSubjectName@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; SdpGetSubjectName(_CERT_CONTEXT const *,ushort * *)
0x180011cf9  mov     ebx, eax
0x180011cfb  test    eax, eax
0x180011cfd  jns     short loc_180011D0A
0x180011cff  mov     r8d, 5BCh
0x180011d05  jmp     loc_180011F20
0x180011d0a  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180011d0e  mov     rcx, [rsi+18h]; this
0x180011d12  call    ?set_PackagePublisher@Settings@@QEAAJPEBG@Z; Settings::set_PackagePublisher(ushort const *)
0x180011d17  lea     rcx, [rbp+var_50]; int *
0x180011d1b  call    ?SdpShouldValidateTrust@@YAJPEAH@Z; SdpShouldValidateTrust(int *)
0x180011d20  mov     ebx, eax
0x180011d22  test    eax, eax
0x180011d24  jns     short loc_180011D31
0x180011d26  mov     r8d, 5C6h
0x180011d2c  jmp     loc_180011F20
0x180011d31  cmp     [rbp+var_50], r12d
0x180011d35  jz      short loc_180011D6F
0x180011d37  lea     rdx, [rbp+var_4C]; int *
0x180011d3b  mov     rcx, r14; struct _CERT_CONTEXT *
0x180011d3e  call    ?SdpIsTrusted@@YAJPEBU_CERT_CONTEXT@@PEAH@Z; SdpIsTrusted(_CERT_CONTEXT const *,int *)
0x180011d43  mov     ebx, eax
0x180011d45  test    eax, eax
0x180011d47  jns     short loc_180011D54
0x180011d49  mov     r8d, 5CAh
0x180011d4f  jmp     loc_180011F20
0x180011d54  cmp     [rbp+var_4C], r12d
0x180011d58  jnz     short loc_180011D6F
0x180011d5a  mov     ebx, 803C0107h
0x180011d5f  mov     r8d, 5CEh
0x180011d65  mov     r9d, ebx
0x180011d68  mov     ecx, edi
0x180011d6a  jmp     loc_180011F25
0x180011d6f  mov     rcx, [rsi+18h]; this
0x180011d73  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x180011d77  call    ?get_Locale@Settings@@QEAAJPEAPEAG@Z; Settings::get_Locale(ushort * *)
0x180011d7c  mov     ebx, eax
0x180011d7e  test    eax, eax
0x180011d80  jns     short loc_180011DA2
0x180011d82  mov     r9d, eax; int
0x180011d85  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011d8c  mov     r8d, 5D7h; int
0x180011d92  mov     ecx, edi; Level
0x180011d94  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011d99  mov     r15, [rbp+var_30]
0x180011d9d  jmp     loc_180011F31
0x180011da2  mov     r15, [rbp+var_30]
0x180011da6  test    r15, r15
0x180011da9  jz      loc_180011F31
0x180011daf  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x180011db3  lea     r8, [rbp+var_48]; unsigned __int16 **
0x180011db7  mov     rdx, r15; unsigned __int16 *
0x180011dba  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180011dbf  mov     ebx, eax
0x180011dc1  test    eax, eax
0x180011dc3  jns     short loc_180011DE5
0x180011dc5  mov     r8d, 5E3h; int
0x180011dcb  mov     r9d, eax; int
0x180011dce  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011dd5  mov     ecx, edi; Level
0x180011dd7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011ddc  mov     r12, [rbp+var_48]
0x180011de0  jmp     loc_180011F31
0x180011de5  mov     r8d, 2Eh ; '.'; unsigned __int16
0x180011deb  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180011def  lea     rdx, aCat; "cat"
0x180011df6  mov     rcx, r15; unsigned __int16 *
0x180011df9  call    ?SdpStrCat@@YAJPEBG0GPEAPEAG@Z; SdpStrCat(ushort const *,ushort const *,ushort,ushort * *)
0x180011dfe  mov     ebx, eax
0x180011e00  test    eax, eax
0x180011e02  jns     short loc_180011E0C
0x180011e04  mov     r8d, 5E6h
0x180011e0a  jmp     short loc_180011DCB
0x180011e0c  mov     r12, [rbp+var_48]
0x180011e10  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x180011e14  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180011e18  mov     rcx, r12; unsigned __int16 *
0x180011e1b  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180011e20  mov     ebx, eax
0x180011e22  test    eax, eax
0x180011e24  jns     short loc_180011E46
0x180011e26  mov     r9d, eax; int
0x180011e29  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011e30  mov     r8d, 5E9h; int
0x180011e36  mov     ecx, edi; Level
0x180011e38  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011e3d  mov     r13, [rbp+lpFileName]
0x180011e41  jmp     loc_180011F31
0x180011e46  mov     r13, [rbp+lpFileName]
0x180011e4a  mov     rcx, r12; unsigned __int16 *
0x180011e4d  mov     rdx, r13; unsigned __int16 *
0x180011e50  call    ?SdpVerifyDirectoryTrust@@YAJPEBG0@Z; SdpVerifyDirectoryTrust(ushort const *,ushort const *)
0x180011e55  mov     ebx, eax
0x180011e57  test    eax, eax
0x180011e59  jns     short loc_180011E66
0x180011e5b  mov     r8d, 5ECh
0x180011e61  jmp     loc_180011F20
0x180011e66  xor     r9d, r9d; int *
0x180011e69  lea     rdx, [rbp+var_8]; struct _CERT_CONTEXT **
0x180011e6d  xor     r8d, r8d; int *
0x180011e70  mov     rcx, r13; lpFileName
0x180011e73  call    ?SdpGetCertificate@@YAJPEBGPEAPEBU_CERT_CONTEXT@@PEAH2@Z; SdpGetCertificate(ushort const *,_CERT_CONTEXT const * *,int *,int *)
0x180011e78  mov     ebx, eax
0x180011e7a  test    eax, eax
0x180011e7c  jns     short loc_180011E89
0x180011e7e  mov     r8d, 5F6h
0x180011e84  jmp     loc_180011F20
0x180011e89  test    r14, r14
0x180011e8c  jnz     short loc_180011E9B
0x180011e8e  mov     ebx, 80070057h
0x180011e93  mov     r8d, 3CEh
0x180011e99  jmp     short loc_180011ED1
0x180011e9b  mov     r8, [rbp+var_8]
0x180011e9f  test    r8, r8
0x180011ea2  jnz     short loc_180011EB1
0x180011ea4  mov     ebx, 80070057h
0x180011ea9  mov     r8d, 3CFh
0x180011eaf  jmp     short loc_180011ED1
0x180011eb1  mov     r8, [r8+18h]; pCertId2
0x180011eb5  mov     rdx, [r14+18h]; pCertId1
0x180011eb9  mov     ecx, [r14]; dwCertEncodingType
0x180011ebc  call    cs:__imp_CertCompareCertificate
0x180011ec2  test    eax, eax
0x180011ec4  jnz     short loc_180011EED
0x180011ec6  mov     ebx, 8000FFFFh
0x180011ecb  mov     r8d, 3D5h; int
0x180011ed1  mov     ecx, edi; Level
0x180011ed3  lea     rdx, aSdpcomparecert; "SdpCompareCertificate"
0x180011eda  mov     r9d, ebx; int
0x180011edd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011ee2  mov     r8d, 5FFh
0x180011ee8  jmp     loc_180011D65
0x180011eed  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180011ef1  mov     rcx, r13; unsigned __int16 *
0x180011ef4  call    ?SdpGetCatalogAttribute@@YAJPEBG00PEAPEAG@Z; SdpGetCatalogAttribute(ushort const *,ushort const *,ushort const *,ushort * *)
0x180011ef9  mov     ebx, eax
0x180011efb  test    eax, eax
0x180011efd  jns     short loc_180011F07
0x180011eff  mov     r8d, 60Ch
0x180011f05  jmp     short loc_180011F20
0x180011f07  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x180011f0b  mov     rcx, [rsi+18h]; this
0x180011f0f  call    ?set_PackageId@Settings@@QEAAJPEBG@Z; Settings::set_PackageId(ushort const *)
0x180011f14  mov     ebx, eax
0x180011f16  test    eax, eax
0x180011f18  jns     short loc_180011F31
0x180011f1a  mov     r8d, 60Fh; int
0x180011f20  mov     ecx, edi; Level
0x180011f22  mov     r9d, eax; int
0x180011f25  lea     rdx, aCscripteddiagV_0; "CScriptedDiag::VerifyPackageTrust"
0x180011f2c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180011f31  mov     rax, [rbp+Block]
0x180011f35  test    rax, rax
0x180011f38  jz      short loc_180011F42
0x180011f3a  mov     rcx, rax; Block
0x180011f3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f42  test    r15, r15
0x180011f45  jz      short loc_180011F4F
0x180011f47  mov     rcx, r15; Block
0x180011f4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f4f  test    r12, r12
0x180011f52  jz      short loc_180011F5C
0x180011f54  mov     rcx, r12; Block
0x180011f57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f5c  mov     rax, [rbp+var_20]
0x180011f60  test    rax, rax
0x180011f63  jz      short loc_180011F6D
0x180011f65  mov     rcx, rax; Block
0x180011f68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f6d  test    r13, r13
0x180011f70  jz      short loc_180011F7A
0x180011f72  mov     rcx, r13; Block
0x180011f75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f7a  mov     rax, [rbp+var_18]
0x180011f7e  test    rax, rax
0x180011f81  jz      short loc_180011F8B
0x180011f83  mov     rcx, rax; Block
0x180011f86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f8b  mov     rax, [rbp+var_10]
0x180011f8f  test    rax, rax
0x180011f92  jz      short loc_180011F9C
0x180011f94  mov     rcx, rax; Block
0x180011f97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011f9c  test    r14, r14
0x180011f9f  jz      short loc_180011FAA
0x180011fa1  mov     rcx, r14; pCertContext
0x180011fa4  call    cs:__imp_CertFreeCertificateContext
0x180011faa  mov     rax, [rbp+var_8]
0x180011fae  test    rax, rax
0x180011fb1  jz      short loc_180011FBC
0x180011fb3  mov     rcx, rax; pCertContext
0x180011fb6  call    cs:__imp_CertFreeCertificateContext
0x180011fbc  mov     eax, ebx
0x180011fbe  mov     rbx, [rsp+70h+arg_0]
0x180011fc6  add     rsp, 70h
0x180011fca  pop     r15
0x180011fcc  pop     r14
0x180011fce  pop     r13
0x180011fd0  pop     r12
0x180011fd2  pop     rdi
0x180011fd3  pop     rsi
0x180011fd4  pop     rbp
0x180011fd5  retn
```
