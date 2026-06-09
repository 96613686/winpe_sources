# CListenerEx::GetRedirectAuthInfo(_GUID *,uchar * *,ulong *,ushort * *,uchar * *,ulong *)

- ea: `0x180089040`
- end: `0x180089437`
- name: `?GetRedirectAuthInfo@CListenerEx@@UEAAJPEAU_GUID@@PEAPEAEPEAKPEAPEAG12@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CListenerEx *this, struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000ef50`
- `0x180011f80`
- `0x1800127b0`
- `0x180013150`
- `0x180014a2c`
- `0x1800241f0`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x1800330c4`
- `0x180089040`
- `0x1800c3440`
- `0x1800c3504`
- `0x1800c3598`
- `0x1800c37a4`
- `0x1800c3a94`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008916d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18008916d`
- `CRYPT32!CertFreeCertificateContext` at `0x1800893c3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800893c3`
- `REGAPI!RegWinstationQuerySecurityConfig_Merged` at `0x18008922c`
- `REGAPI!RegWinstationQuerySecurityConfig_Merged` at `0x18008922c`

## string_xrefs

- `0x180089204`: `StringCchCopy failed: 0x%x in %s`
- `0x18008914d`: `NULL == pProtocolListener failed: 0x%x in %s`
- `0x18008917c`: `CoCreateGuid failed: 0x%x in %s`
- `0x18008924b`: `RegWinstationQuerySecurityConfig_Merged failed: 0x%x in %s`
- `0x180089347`: `pProtocolListener->QueryInterface failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180089040  push    rbp
0x180089042  push    rbx
0x180089043  push    rsi
0x180089044  push    rdi
0x180089045  push    r12
0x180089047  push    r13
0x180089049  push    r14
0x18008904b  push    r15
0x18008904d  lea     rbp, [rsp-118h]
0x180089055  sub     rsp, 218h
0x18008905c  mov     rax, cs:__security_cookie
0x180089063  xor     rax, rsp
0x180089066  mov     [rbp+150h+var_50], rax
0x18008906d  mov     rbx, r9
0x180089070  mov     [rsp+250h+var_1E0], rbx
0x180089075  mov     r13, r8
0x180089078  mov     r12, rdx
0x18008907b  mov     r15, rcx
0x18008907e  mov     rdi, [rbp+150h+arg_20]
0x180089085  mov     [rsp+250h+var_1D8], rdi
0x18008908a  mov     r14, [rbp+150h+arg_28]
0x180089091  mov     [rbp+150h+var_1D0], r14
0x180089095  mov     rax, [rbp+150h+arg_30]
0x18008909c  mov     [rsp+250h+var_1E8], rax
0x1800890a1  xor     eax, eax
0x1800890a3  mov     [rsp+250h+var_1F8], rax
0x1800890a8  mov     [rsp+250h+Block], rax
0x1800890ad  mov     [rsp+250h+var_21C], eax
0x1800890b1  mov     esi, eax
0x1800890b3  mov     [rsp+250h+var_218], rax
0x1800890b8  mov     [rsp+250h+var_220], eax
0x1800890bc  xor     edx, edx; Val
0x1800890be  mov     r8d, 120h; Size
0x1800890c4  lea     rcx, [rbp+150h+var_170]; void *
0x1800890c8  call    memset_0
0x1800890cd  xor     ecx, ecx
0x1800890cf  mov     [rsp+250h+pCertContext], rcx
0x1800890d4  xorps   xmm0, xmm0
0x1800890d7  movups  [rbp+150h+var_1C8], xmm0
0x1800890db  mov     [rbp+150h+phKey], rcx
0x1800890df  mov     [rbp+150h+var_1B0], rcx
0x1800890e3  mov     [rbp+150h+var_1A8], rcx
0x1800890e7  mov     [rbp+150h+var_1A0], ecx
0x1800890ea  mov     [rbp+150h+var_198], rcx
0x1800890ee  mov     [rbp+150h+var_190], ecx
0x1800890f1  mov     [rsp+250h+var_200], rcx
0x1800890f6  mov     [rsp+250h+var_208], rcx
0x1800890fb  mov     [r13+0], rcx
0x1800890ff  mov     [rbx], ecx
0x180089101  mov     [rdi], rcx
0x180089104  mov     [r14], rcx
0x180089107  mov     rax, [rsp+250h+var_1E8]
0x18008910c  mov     [rax], ecx
0x18008910e  lea     rdx, [r15+638h]; struct CResource *
0x180089115  lea     rcx, [rbp+150h+var_188]; this
0x180089119  call    ??0CAutoSharedLock@@QEAA@AEAVCResource@@@Z; CAutoSharedLock::CAutoSharedLock(CResource &)
0x18008911e  nop
0x18008911f  mov     rdx, [r15+0C30h]
0x180089126  lea     rcx, [rsp+250h+var_208]
0x18008912b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180089130  nop
0x180089131  lea     rcx, [rbp+150h+var_188]; this
0x180089135  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008913a  nop
0x18008913b  mov     rbx, [rsp+250h+var_208]
0x180089140  test    rbx, rbx
0x180089143  jnz     short loc_18008916A
0x180089145  mov     edi, 800708CAh
0x18008914a  mov     r8d, edi
0x18008914d  lea     rdx, aNullPprotocoll; "NULL == pProtocolListener failed: 0x%x "...
0x180089154  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x18008915b  mov     ecx, 8; int
0x180089160  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180089165  jmp     loc_1800893F3
0x18008916a  mov     rcx, r12; pguid
0x18008916d  call    cs:__imp_CoCreateGuid
0x180089173  mov     edi, eax
0x180089175  test    eax, eax
0x180089177  jns     short loc_180089185
0x180089179  mov     r8d, eax
0x18008917c  lea     rdx, aCocreateguidFa; "CoCreateGuid failed: 0x%x in %s"
0x180089183  jmp     short loc_180089154
0x180089185  lea     r8, [rsp+250h+var_1F8]; unsigned __int64 *
0x18008918a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18008918f  lea     rcx, pszAlgId; "AES"
0x180089196  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008919b  mov     edi, eax
0x18008919d  test    eax, eax
0x18008919f  jns     short loc_1800891AD
0x1800891a1  mov     r8d, eax
0x1800891a4  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x1800891ab  jmp     short loc_180089154
0x1800891ad  mov     rdi, [rsp+250h+var_1F8]
0x1800891b2  inc     rdi
0x1800891b5  mov     eax, 2
0x1800891ba  mul     rdi
0x1800891bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800891c4  cmovb   rax, rcx
0x1800891c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800891cf  mov     rcx, rax; unsigned __int64
0x1800891d2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800891d7  mov     r14, rax
0x1800891da  test    rax, rax
0x1800891dd  jnz     short loc_1800891E9
0x1800891df  mov     edi, 8007000Eh
0x1800891e4  jmp     loc_1800893F3
0x1800891e9  lea     r8, pszAlgId; "AES"
0x1800891f0  mov     rdx, rdi; unsigned __int64
0x1800891f3  mov     rcx, r14; unsigned __int16 *
0x1800891f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800891fb  mov     edi, eax
0x1800891fd  test    eax, eax
0x1800891ff  jns     short loc_180089221
0x180089201  mov     r8d, eax
0x180089204  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18008920b  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x180089212  mov     ecx, 8; int
0x180089217  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008921c  jmp     loc_1800893DD
0x180089221  lea     rcx, [r15+0BD8h]
0x180089228  lea     rdx, [rbp+150h+var_170]
0x18008922c  call    cs:__imp_RegWinstationQuerySecurityConfig_Merged
0x180089232  mov     edi, eax
0x180089234  xor     r15d, r15d
0x180089237  test    eax, eax
0x180089239  jle     short loc_180089244
0x18008923b  movzx   edi, ax
0x18008923e  or      edi, 80070000h
0x180089244  test    edi, edi
0x180089246  jns     short loc_180089254
0x180089248  mov     r8d, edi
0x18008924b  lea     rdx, aRegwinstationq_2; "RegWinstationQuerySecurityConfig_Merged"...
0x180089252  jmp     short loc_18008920B
0x180089254  lea     rax, [rbp+150h+var_16E]
0x180089258  mov     qword ptr [rbp+150h+var_1C8+8], rax
0x18008925c  mov     dword ptr [rbp+150h+var_1C8], 14h
0x180089263  lea     rdx, [rbp+150h+var_154]
0x180089267  lea     rax, aMy; "My"
0x18008926e  cmp     [rbp+150h+var_154], r15w
0x180089273  cmovz   rdx, rax
0x180089277  lea     r9, [rbp+150h+var_1C8]
0x18008927b  lea     rcx, [rsp+250h+pCertContext]
0x180089280  call    TsCryptGetCertContext
0x180089285  mov     edi, eax
0x180089287  mov     r15, [rsp+250h+pCertContext]
0x18008928c  test    eax, eax
0x18008928e  jns     short loc_1800892B0
0x180089290  lea     rdx, aTscryptgetcert; "TsCryptGetCertContext failed: 0x%x in %"...
0x180089297  mov     r8d, eax
0x18008929a  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x1800892a1  mov     ecx, 8; int
0x1800892a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800892ab  jmp     loc_1800893BB
0x1800892b0  lea     r8, [rsp+250h+var_21C]; unsigned int *
0x1800892b5  lea     rdx, [rsp+250h+Block]; unsigned __int8 **
0x1800892ba  mov     rcx, r15; pCertContext
0x1800892bd  call    ?SerializeCertificate@CTSCryptUtils@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; CTSCryptUtils::SerializeCertificate(_CERT_CONTEXT const *,uchar * *,ulong *)
0x1800892c2  mov     edi, eax
0x1800892c4  test    eax, eax
0x1800892c6  jns     short loc_1800892D1
0x1800892c8  lea     rdx, aCryptutilsSeri; "CryptUtils.SerializeCertificate failed:"...
0x1800892cf  jmp     short loc_180089297
0x1800892d1  lea     rcx, [rbp+150h+phKey]; phKey
0x1800892d5  call    ?GenerateSymmetricKey@CTSCryptUtils@@QEAAJPEBG@Z; CTSCryptUtils::GenerateSymmetricKey(ushort const *)
0x1800892da  mov     edi, eax
0x1800892dc  test    eax, eax
0x1800892de  jns     short loc_1800892E9
0x1800892e0  lea     rdx, aCryptutilsGene; "CryptUtils.GenerateSymmetricKey failed:"...
0x1800892e7  jmp     short loc_180089297
0x1800892e9  lea     r8, [rsp+250h+var_220]; unsigned int *
0x1800892ee  lea     rdx, [rsp+250h+var_218]; unsigned __int8 **
0x1800892f3  lea     rcx, [rbp+150h+phKey]; this
0x1800892f7  call    ?ExportSymmetrictKey@CTSCryptUtils@@QEAAJPEAPEAEPEAK@Z; CTSCryptUtils::ExportSymmetrictKey(uchar * *,ulong *)
0x1800892fc  mov     edi, eax
0x1800892fe  test    eax, eax
0x180089300  jns     short loc_180089327
0x180089302  lea     rdx, aCryptutilsExpo; "CryptUtils.ExportSymmetrictKey failed: "...
0x180089309  mov     r8d, eax
0x18008930c  lea     r9, aClistenerexGet; "CListenerEx::GetRedirectAuthInfo"
0x180089313  mov     ecx, 8; int
0x180089318  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008931d  mov     rsi, [rsp+250h+var_218]
0x180089322  jmp     loc_1800893BB
0x180089327  mov     rax, [rbx]
0x18008932a  lea     r8, [rsp+250h+var_200]
0x18008932f  lea     rdx, IID_IWTSRedirectedAuthenticationKeyList
0x180089336  mov     rcx, rbx
0x180089339  mov     rax, [rax]
0x18008933c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089341  mov     edi, eax
0x180089343  test    eax, eax
0x180089345  jns     short loc_180089350
0x180089347  lea     rdx, aPprotocolliste; "pProtocolListener->QueryInterface faile"...
0x18008934e  jmp     short loc_180089309
0x180089350  mov     rcx, [rsp+250h+var_200]
0x180089355  mov     rax, [rcx]
0x180089358  mov     ebx, [rsp+250h+var_220]
0x18008935c  mov     r9d, ebx
0x18008935f  mov     rsi, [rsp+250h+var_218]
0x180089364  mov     r8, rsi
0x180089367  mov     rdx, r12
0x18008936a  mov     rax, [rax+18h]
0x18008936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089373  mov     edi, eax
0x180089375  test    eax, eax
0x180089377  jns     short loc_180089385
0x180089379  lea     rdx, aPtrredirauthke; "ptrRedirAuthKeyList->AddKey failed: 0x%"...
0x180089380  jmp     loc_180089297
0x180089385  mov     rax, [rsp+250h+Block]
0x18008938a  mov     [r13+0], rax
0x18008938e  mov     eax, [rsp+250h+var_21C]
0x180089392  mov     rcx, [rsp+250h+var_1E0]
0x180089397  mov     [rcx], eax
0x180089399  mov     rax, [rsp+250h+var_1D8]
0x18008939e  mov     [rax], r14
0x1800893a1  mov     rax, [rbp+150h+var_1D0]
0x1800893a5  mov     [rax], rsi
0x1800893a8  mov     rax, [rsp+250h+var_1E8]
0x1800893ad  mov     [rax], ebx
0x1800893af  xor     edi, edi
0x1800893b1  mov     [rsp+250h+Block], rdi
0x1800893b6  mov     r14d, edi
0x1800893b9  mov     esi, edi
0x1800893bb  test    r15, r15
0x1800893be  jz      short loc_1800893C9
0x1800893c0  mov     rcx, r15; pCertContext
0x1800893c3  call    cs:__imp_CertFreeCertificateContext
0x1800893c9  mov     rcx, [rsp+250h+Block]; Block
0x1800893ce  test    rcx, rcx
0x1800893d1  jz      short loc_1800893D8
0x1800893d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800893d8  test    r14, r14
0x1800893db  jz      short loc_1800893E5
0x1800893dd  mov     rcx, r14; Block
0x1800893e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800893e5  test    rsi, rsi
0x1800893e8  jz      short loc_1800893F3
0x1800893ea  mov     rcx, rsi; Block
0x1800893ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800893f2  nop
0x1800893f3  lea     rcx, [rsp+250h+var_208]; void *
0x1800893f8  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800893fd  nop
0x1800893fe  lea     rcx, [rsp+250h+var_200]; void *
0x180089403  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180089408  nop
0x180089409  lea     rcx, [rbp+150h+phKey]; this
0x18008940d  call    ?Clear@CTSCryptUtils@@QEAAXXZ; CTSCryptUtils::Clear(void)
0x180089412  mov     eax, edi
0x180089414  mov     rcx, [rbp+150h+var_50]
0x18008941b  xor     rcx, rsp; StackCookie
0x18008941e  call    __security_check_cookie
0x180089423  add     rsp, 218h
0x18008942a  pop     r15
0x18008942c  pop     r14
0x18008942e  pop     r13
0x180089430  pop     r12
0x180089432  pop     rdi
0x180089433  pop     rsi
0x180089434  pop     rbx
0x180089435  pop     rbp
0x180089436  retn
```
