# CListenerEx::GetRedirectAuthInfo(_GUID *,uchar * *,ulong *,ushort * *,uchar * *,ulong *)

- ea: `0x18008cb20`
- end: `0x18008cf2a`
- name: `?GetRedirectAuthInfo@CListenerEx@@UEAAJPEAU_GUID@@PEAPEAEPEAKPEAPEAG12@Z`
- size: `1034`
- prototype: `int(CListenerEx *__hidden this, struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000f0d0`
- `0x180012750`
- `0x180012d10`
- `0x1800139c0`
- `0x180015044`
- `0x18002558c`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x180034e64`
- `0x18008cb20`
- `0x1800c9440`
- `0x1800c9524`
- `0x1800c95cc`
- `0x1800c97e4`
- `0x1800c9af8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008cc4d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008cc4d`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ceaf`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ceaf`
- `REGAPI!RegWinstationQuerySecurityConfig_Merged` at `0x18008cd12`
- `REGAPI!RegWinstationQuerySecurityConfig_Merged` at `0x18008cd12`

## string_xrefs

- `0x18008ccea`: `StringCchCopy failed: 0x%x in %s`
- `0x18008cc2d`: `NULL == pProtocolListener failed: 0x%x in %s`
- `0x18008cc62`: `CoCreateGuid failed: 0x%x in %s`
- `0x18008cd37`: `RegWinstationQuerySecurityConfig_Merged failed: 0x%x in %s`
- `0x18008ce33`: `pProtocolListener->QueryInterface failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CListenerEx::GetRedirectAuthInfo(
        CListenerEx *this,
        struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int16 **a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 *v11; // rsi
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v13; // edi
  HRESULT Guid; // eax
  int v15; // eax
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // r14
  int v20; // eax
  int SecurityConfig_Merged; // eax
  __int64 v22; // r8
  const wchar_t *v23; // rdx
  int CertContext; // eax
  const CERT_CONTEXT *v25; // r15
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  int SymmetricKey; // eax
  int v29; // eax
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 *v36; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v42; // [rsp+68h] [rbp-98h]
  unsigned int *v43; // [rsp+70h] [rbp-90h]
  unsigned __int16 **v44; // [rsp+78h] [rbp-88h]
  unsigned __int8 **v45; // [rsp+80h] [rbp-80h]
  __int128 v46; // [rsp+88h] [rbp-78h] BYREF
  BCRYPT_KEY_HANDLE phKey[3]; // [rsp+98h] [rbp-68h] BYREF
  int v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+C0h] [rbp-40h]
  _BYTE v51[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v52[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v53; // [rsp+E2h] [rbp-1Eh] BYREF
  __int16 v54; // [rsp+FCh] [rbp-4h] BYREF

  v43 = a4;
  v44 = a5;
  v45 = a6;
  v42 = a7;
  v40 = 0;
  Block = 0;
  v35 = 0;
  v11 = 0;
  v36 = 0;
  v34 = 0;
  memset_0(v52, 0, 0x120u);
  pCertContext = 0;
  v46 = 0;
  memset(phKey, 0, sizeof(phKey));
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v39 = 0;
  v38 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *v42 = 0;
  CAutoSharedLock::CAutoSharedLock((CAutoSharedLock *)v51, (CListenerEx *)((char *)this + 1592));
  SmartPtr<ITerminal>::operator=(&v38, *((_QWORD *)this + 390));
  CAutoLock::Unlock((CAutoLock *)v51);
  v12 = v38;
  if ( !v38 )
  {
    v13 = -2147022646;
    _DbgPrintMessage(
      8,
      "NULL == pProtocolListener failed: 0x%x in %s",
      2147944650LL,
      "CListenerEx::GetRedirectAuthInfo");
    goto LABEL_44;
  }
  Guid = CoCreateGuid(a2);
  v13 = Guid;
  if ( Guid < 0 )
  {
    _DbgPrintMessage(8, "CoCreateGuid failed: 0x%x in %s", (unsigned int)Guid, "CListenerEx::GetRedirectAuthInfo");
    goto LABEL_44;
  }
  v15 = StringCchLengthW(L"AES", 0x7FFFFFFFu, &v40);
  v13 = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", (unsigned int)v15, "CListenerEx::GetRedirectAuthInfo");
    goto LABEL_44;
  }
  v16 = v40 + 1;
  v17 = 2 * (v40 + 1);
  if ( !is_mul_ok(v40 + 1, 2u) )
    v17 = -1;
  v18 = (unsigned __int16 *)operator new[](v17, (const struct std::nothrow_t *)std::nothrow);
  v19 = v18;
  if ( !v18 )
  {
    v13 = -2147024882;
    goto LABEL_44;
  }
  v20 = StringCchCopyW(v18, v16, L"AES");
  v13 = v20;
  if ( v20 < 0 )
  {
    _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", (unsigned int)v20, "CListenerEx::GetRedirectAuthInfo");
    goto LABEL_41;
  }
  SecurityConfig_Merged = RegWinstationQuerySecurityConfig_Merged((char *)this + 3032, v52);
  v13 = SecurityConfig_Merged;
  if ( SecurityConfig_Merged > 0 )
    v13 = (unsigned __int16)SecurityConfig_Merged | 0x80070000;
  if ( (v13 & 0x80000000) == 0 )
  {
    *((_QWORD *)&v46 + 1) = &v53;
    LODWORD(v46) = 20;
    v23 = (const wchar_t *)&v54;
    if ( !v54 )
      v23 = L"My";
    CertContext = TsCryptGetCertContext(&pCertContext, v23, v22, &v46);
    v13 = CertContext;
    v25 = pCertContext;
    if ( CertContext < 0 )
    {
      _DbgPrintMessage(
        8,
        "TsCryptGetCertContext failed: 0x%x in %s",
        (unsigned int)CertContext,
        "CListenerEx::GetRedirectAuthInfo");
      goto LABEL_36;
    }
    v26 = CTSCryptUtils::SerializeCertificate(pCertContext, (unsigned __int8 **)&Block, &v35);
    v13 = v26;
    if ( v26 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CryptUtils.SerializeCertificate failed: 0x%x in %s",
        (unsigned int)v26,
        "CListenerEx::GetRedirectAuthInfo");
      goto LABEL_36;
    }
    SymmetricKey = CTSCryptUtils::GenerateSymmetricKey(phKey, v27);
    v13 = SymmetricKey;
    if ( SymmetricKey < 0 )
    {
      _DbgPrintMessage(
        8,
        "CryptUtils.GenerateSymmetricKey failed: 0x%x in %s",
        (unsigned int)SymmetricKey,
        "CListenerEx::GetRedirectAuthInfo");
      goto LABEL_36;
    }
    v29 = CTSCryptUtils::ExportSymmetrictKey((CTSCryptUtils *)phKey, &v36, &v34);
    v13 = v29;
    if ( v29 >= 0 )
    {
      v30 = (**v12)(v12, &IID_IWTSRedirectedAuthenticationKeyList, &v39);
      v13 = v30;
      if ( v30 >= 0 )
      {
        v31 = v34;
        v11 = v36;
        v32 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, unsigned __int8 *, _QWORD))(*(_QWORD *)v39 + 24LL))(
                v39,
                a2,
                v36,
                v34);
        v13 = v32;
        if ( v32 >= 0 )
        {
          *a3 = (unsigned __int8 *)Block;
          *v43 = v35;
          *v44 = v19;
          *v45 = v11;
          *v42 = v31;
          v13 = 0;
          Block = 0;
          v19 = 0;
          v11 = 0;
        }
        else
        {
          _DbgPrintMessage(
            8,
            "ptrRedirAuthKeyList->AddKey failed: 0x%x in %s",
            (unsigned int)v32,
            "CListenerEx::GetRedirectAuthInfo");
        }
LABEL_36:
        if ( v25 )
          CertFreeCertificateContext(v25);
        if ( Block )
          operator delete(Block);
        if ( !v19 )
          goto LABEL_42;
        goto LABEL_41;
      }
      _DbgPrintMessage(
        8,
        "pProtocolListener->QueryInterface failed: 0x%x in %s",
        (unsigned int)v30,
        "CListenerEx::GetRedirectAuthInfo");
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CryptUtils.ExportSymmetrictKey failed: 0x%x in %s",
        (unsigned int)v29,
        "CListenerEx::GetRedirectAuthInfo");
    }
    v11 = v36;
    goto LABEL_36;
  }
  _DbgPrintMessage(
    8,
    "RegWinstationQuerySecurityConfig_Merged failed: 0x%x in %s",
    v13,
    "CListenerEx::GetRedirectAuthInfo");
LABEL_41:
  operator delete(v19);
LABEL_42:
  if ( v11 )
    operator delete(v11);
LABEL_44:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v39);
  CTSCryptUtils::Clear((CTSCryptUtils *)phKey);
  return v13;
}

```

## disassembly

```asm
0x18008cb20  push    rbp
0x18008cb22  push    rbx
0x18008cb23  push    rsi
0x18008cb24  push    rdi
0x18008cb25  push    r12
0x18008cb27  push    r13
0x18008cb29  push    r14
0x18008cb2b  push    r15
0x18008cb2d  lea     rbp, [rsp-118h]
0x18008cb35  sub     rsp, 218h
0x18008cb3c  mov     rax, cs:__security_cookie
0x18008cb43  xor     rax, rsp
0x18008cb46  mov     [rbp+150h+var_50], rax
0x18008cb4d  mov     rbx, r9
0x18008cb50  mov     [rsp+250h+var_1E0], rbx
0x18008cb55  mov     r13, r8
0x18008cb58  mov     r12, rdx
0x18008cb5b  mov     r15, rcx
0x18008cb5e  mov     rdi, [rbp+150h+arg_20]
0x18008cb65  mov     [rsp+250h+var_1D8], rdi
0x18008cb6a  mov     r14, [rbp+150h+arg_28]
0x18008cb71  mov     [rbp+150h+var_1D0], r14
0x18008cb75  mov     rax, [rbp+150h+arg_30]
0x18008cb7c  mov     [rsp+250h+var_1E8], rax
0x18008cb81  xor     eax, eax
0x18008cb83  mov     [rsp+250h+var_1F8], rax
0x18008cb88  mov     [rsp+250h+Block], rax
0x18008cb8d  mov     [rsp+250h+var_21C], eax
0x18008cb91  mov     esi, eax
0x18008cb93  mov     [rsp+250h+var_218], rax
0x18008cb98  mov     [rsp+250h+var_220], eax
0x18008cb9c  xor     edx, edx; Val
0x18008cb9e  mov     r8d, 120h; Size
0x18008cba4  lea     rcx, [rbp+150h+var_170]; void *
0x18008cba8  call    memset_0
0x18008cbad  xor     ecx, ecx
0x18008cbaf  mov     [rsp+250h+pCertContext], rcx
0x18008cbb4  xorps   xmm0, xmm0
0x18008cbb7  movups  [rbp+150h+var_1C8], xmm0
0x18008cbbb  mov     [rbp+150h+phKey], rcx
0x18008cbbf  mov     [rbp+150h+var_1B0], rcx
0x18008cbc3  mov     [rbp+150h+var_1A8], rcx
0x18008cbc7  mov     [rbp+150h+var_1A0], ecx
0x18008cbca  mov     [rbp+150h+var_198], rcx
0x18008cbce  mov     [rbp+150h+var_190], ecx
0x18008cbd1  mov     [rsp+250h+var_200], rcx
0x18008cbd6  mov     [rsp+250h+var_208], rcx
0x18008cbdb  mov     [r13+0], rcx
0x18008cbdf  mov     [rbx], ecx
0x18008cbe1  mov     [rdi], rcx
0x18008cbe4  mov     [r14], rcx
0x18008cbe7  mov     rax, [rsp+250h+var_1E8]
0x18008cbec  mov     [rax], ecx
0x18008cbee  lea     rdx, [r15+638h]; struct CResource *
0x18008cbf5  lea     rcx, [rbp+150h+var_188]; this
0x18008cbf9  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x18008cbfe  nop
0x18008cbff  mov     rdx, [r15+0C30h]
0x18008cc06  lea     rcx, [rsp+250h+var_208]
0x18008cc0b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18008cc10  nop
0x18008cc11  lea     rcx, [rbp+150h+var_188]; this
0x18008cc15  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008cc1a  nop
0x18008cc1b  mov     rbx, [rsp+250h+var_208]
0x18008cc20  test    rbx, rbx
0x18008cc23  jnz     short loc_18008CC4A
0x18008cc25  mov     edi, 800708CAh
0x18008cc2a  mov     r8d, edi
0x18008cc2d  lea     rdx, aNullPprotocoll; "NULL == pProtocolListener failed: 0x%x "...
0x18008cc34  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x18008cc3b  mov     ecx, 8; int
0x18008cc40  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008cc45  jmp     loc_18008CEE5
0x18008cc4a  mov     rcx, r12; pguid
0x18008cc4d  call    cs:__imp_CoCreateGuid
0x18008cc54  nop     dword ptr [rax+rax+00h]
0x18008cc59  mov     edi, eax
0x18008cc5b  test    eax, eax
0x18008cc5d  jns     short loc_18008CC6B
0x18008cc5f  mov     r8d, eax
0x18008cc62  lea     rdx, aCocreateguidFa; "CoCreateGuid failed: 0x%x in %s"
0x18008cc69  jmp     short loc_18008CC34
0x18008cc6b  lea     r8, [rsp+250h+var_1F8]; unsigned __int64 *
0x18008cc70  mov     edx, 7FFFFFFFh; unsigned __int64
0x18008cc75  lea     rcx, pszAlgId; "AES"
0x18008cc7c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008cc81  mov     edi, eax
0x18008cc83  test    eax, eax
0x18008cc85  jns     short loc_18008CC93
0x18008cc87  mov     r8d, eax
0x18008cc8a  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18008cc91  jmp     short loc_18008CC34
0x18008cc93  mov     rdi, [rsp+250h+var_1F8]
0x18008cc98  inc     rdi
0x18008cc9b  mov     eax, 2
0x18008cca0  mul     rdi
0x18008cca3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008ccaa  cmovb   rax, rcx
0x18008ccae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008ccb5  mov     rcx, rax; unsigned __int64
0x18008ccb8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008ccbd  mov     r14, rax
0x18008ccc0  test    rax, rax
0x18008ccc3  jnz     short loc_18008CCCF
0x18008ccc5  mov     edi, 8007000Eh
0x18008ccca  jmp     loc_18008CEE5
0x18008cccf  lea     r8, pszAlgId; "AES"
0x18008ccd6  mov     rdx, rdi; unsigned __int64
0x18008ccd9  mov     rcx, r14; unsigned __int16 *
0x18008ccdc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008cce1  mov     edi, eax
0x18008cce3  test    eax, eax
0x18008cce5  jns     short loc_18008CD07
0x18008cce7  mov     r8d, eax
0x18008ccea  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18008ccf1  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x18008ccf8  mov     ecx, 8; int
0x18008ccfd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008cd02  jmp     loc_18008CECF
0x18008cd07  lea     rcx, [r15+0BD8h]
0x18008cd0e  lea     rdx, [rbp+150h+var_170]
0x18008cd12  call    cs:__imp_RegWinstationQuerySecurityConfig_Merged
0x18008cd19  nop     dword ptr [rax+rax+00h]
0x18008cd1e  mov     edi, eax
0x18008cd20  xor     r15d, r15d
0x18008cd23  test    eax, eax
0x18008cd25  jle     short loc_18008CD30
0x18008cd27  movzx   edi, ax
0x18008cd2a  or      edi, 80070000h
0x18008cd30  test    edi, edi
0x18008cd32  jns     short loc_18008CD40
0x18008cd34  mov     r8d, edi
0x18008cd37  lea     rdx, aRegwinstationq_2; "RegWinstationQuerySecurityConfig_Merged"...
0x18008cd3e  jmp     short loc_18008CCF1
0x18008cd40  lea     rax, [rbp+150h+var_16E]
0x18008cd44  mov     qword ptr [rbp+150h+var_1C8+8], rax
0x18008cd48  mov     dword ptr [rbp+150h+var_1C8], 14h
0x18008cd4f  lea     rdx, [rbp+150h+var_154]
0x18008cd53  lea     rax, aMy; "My"
0x18008cd5a  cmp     [rbp+150h+var_154], r15w
0x18008cd5f  cmovz   rdx, rax
0x18008cd63  lea     r9, [rbp+150h+var_1C8]
0x18008cd67  lea     rcx, [rsp+250h+pCertContext]
0x18008cd6c  call    TsCryptGetCertContext
0x18008cd71  mov     edi, eax
0x18008cd73  mov     r15, [rsp+250h+pCertContext]
0x18008cd78  test    eax, eax
0x18008cd7a  jns     short loc_18008CD9C
0x18008cd7c  lea     rdx, aTscryptgetcert; "TsCryptGetCertContext failed: 0x%x in %"...
0x18008cd83  mov     r8d, eax
0x18008cd86  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x18008cd8d  mov     ecx, 8; int
0x18008cd92  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008cd97  jmp     loc_18008CEA7
0x18008cd9c  lea     r8, [rsp+250h+var_21C]; unsigned int *
0x18008cda1  lea     rdx, [rsp+250h+Block]; unsigned __int8 **
0x18008cda6  mov     rcx, r15; pCertContext
0x18008cda9  call    ?SerializeCertificate@CTSCryptUtils@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; CTSCryptUtils::SerializeCertificate(_CERT_CONTEXT const *,uchar * *,ulong *)
0x18008cdae  mov     edi, eax
0x18008cdb0  test    eax, eax
0x18008cdb2  jns     short loc_18008CDBD
0x18008cdb4  lea     rdx, aCryptutilsSeri; "CryptUtils.SerializeCertificate failed:"...
0x18008cdbb  jmp     short loc_18008CD83
0x18008cdbd  lea     rcx, [rbp+150h+phKey]; phKey
0x18008cdc1  call    ?GenerateSymmetricKey@CTSCryptUtils@@QEAAJPEBG@Z; CTSCryptUtils::GenerateSymmetricKey(ushort const *)
0x18008cdc6  mov     edi, eax
0x18008cdc8  test    eax, eax
0x18008cdca  jns     short loc_18008CDD5
0x18008cdcc  lea     rdx, aCryptutilsGene; "CryptUtils.GenerateSymmetricKey failed:"...
0x18008cdd3  jmp     short loc_18008CD83
0x18008cdd5  lea     r8, [rsp+250h+var_220]; unsigned int *
0x18008cdda  lea     rdx, [rsp+250h+var_218]; unsigned __int8 **
0x18008cddf  lea     rcx, [rbp+150h+phKey]; this
0x18008cde3  call    ?ExportSymmetrictKey@CTSCryptUtils@@QEAAJPEAPEAEPEAK@Z; CTSCryptUtils::ExportSymmetrictKey(uchar * *,ulong *)
0x18008cde8  mov     edi, eax
0x18008cdea  test    eax, eax
0x18008cdec  jns     short loc_18008CE13
0x18008cdee  lea     rdx, aCryptutilsExpo; "CryptUtils.ExportSymmetrictKey failed: "...
0x18008cdf5  mov     r8d, eax
0x18008cdf8  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x18008cdff  mov     ecx, 8; int
0x18008ce04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008ce09  mov     rsi, [rsp+250h+var_218]
0x18008ce0e  jmp     loc_18008CEA7
0x18008ce13  mov     rax, [rbx]
0x18008ce16  lea     r8, [rsp+250h+var_200]
0x18008ce1b  lea     rdx, IID_IWTSRedirectedAuthenticationKeyList
0x18008ce22  mov     rcx, rbx
0x18008ce25  mov     rax, [rax]
0x18008ce28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ce2d  mov     edi, eax
0x18008ce2f  test    eax, eax
0x18008ce31  jns     short loc_18008CE3C
0x18008ce33  lea     rdx, aPprotocolliste; "pProtocolListener->QueryInterface faile"...
0x18008ce3a  jmp     short loc_18008CDF5
0x18008ce3c  mov     rcx, [rsp+250h+var_200]
0x18008ce41  mov     rax, [rcx]
0x18008ce44  mov     ebx, [rsp+250h+var_220]
0x18008ce48  mov     r9d, ebx
0x18008ce4b  mov     rsi, [rsp+250h+var_218]
0x18008ce50  mov     r8, rsi
0x18008ce53  mov     rdx, r12
0x18008ce56  mov     rax, [rax+18h]
0x18008ce5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ce5f  mov     edi, eax
0x18008ce61  test    eax, eax
0x18008ce63  jns     short loc_18008CE71
0x18008ce65  lea     rdx, aPtrredirauthke; "ptrRedirAuthKeyList->AddKey failed: 0x%"...
0x18008ce6c  jmp     loc_18008CD83
0x18008ce71  mov     rax, [rsp+250h+Block]
0x18008ce76  mov     [r13+0], rax
0x18008ce7a  mov     eax, [rsp+250h+var_21C]
0x18008ce7e  mov     rcx, [rsp+250h+var_1E0]
0x18008ce83  mov     [rcx], eax
0x18008ce85  mov     rax, [rsp+250h+var_1D8]
0x18008ce8a  mov     [rax], r14
0x18008ce8d  mov     rax, [rbp+150h+var_1D0]
0x18008ce91  mov     [rax], rsi
0x18008ce94  mov     rax, [rsp+250h+var_1E8]
0x18008ce99  mov     [rax], ebx
0x18008ce9b  xor     edi, edi
0x18008ce9d  mov     [rsp+250h+Block], rdi
0x18008cea2  mov     r14d, edi
0x18008cea5  mov     esi, edi
0x18008cea7  test    r15, r15
0x18008ceaa  jz      short loc_18008CEBB
0x18008ceac  mov     rcx, r15; pCertContext
0x18008ceaf  call    cs:__imp_CertFreeCertificateContext
0x18008ceb6  nop     dword ptr [rax+rax+00h]
0x18008cebb  mov     rcx, [rsp+250h+Block]; Block
0x18008cec0  test    rcx, rcx
0x18008cec3  jz      short loc_18008CECA
0x18008cec5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008ceca  test    r14, r14
0x18008cecd  jz      short loc_18008CED7
0x18008cecf  mov     rcx, r14; Block
0x18008ced2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008ced7  test    rsi, rsi
0x18008ceda  jz      short loc_18008CEE5
0x18008cedc  mov     rcx, rsi; Block
0x18008cedf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008cee4  nop
0x18008cee5  lea     rcx, [rsp+250h+var_208]; void *
0x18008ceea  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008ceef  nop
0x18008cef0  lea     rcx, [rsp+250h+var_200]; void *
0x18008cef5  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008cefa  nop
0x18008cefb  lea     rcx, [rbp+150h+phKey]; this
0x18008ceff  call    ?Clear@CTSCryptUtils@@QEAAXXZ; CTSCryptUtils::Clear(void)
0x18008cf04  mov     eax, edi
0x18008cf06  mov     rcx, [rbp+150h+var_50]
0x18008cf0d  xor     rcx, rsp; StackCookie
0x18008cf10  call    __security_check_cookie
0x18008cf15  add     rsp, 218h
0x18008cf1c  pop     r15
0x18008cf1e  pop     r14
0x18008cf20  pop     r13
0x18008cf22  pop     r12
0x18008cf24  pop     rdi
0x18008cf25  pop     rsi
0x18008cf26  pop     rbx
0x18008cf27  pop     rbp
0x18008cf28  retn
```
