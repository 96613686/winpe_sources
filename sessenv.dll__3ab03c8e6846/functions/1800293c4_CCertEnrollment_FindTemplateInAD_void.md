# CCertEnrollment::FindTemplateInAD(void)

- ea: `0x1800293c4`
- end: `0x1800297da`
- name: `?FindTemplateInAD@CCertEnrollment@@AEAAJXZ`
- size: `1046`
- prototype: `__int64 __fastcall(CCertEnrollment *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ad30`

## callees

- `0x180001b38`
- `0x180003f30`
- `0x180019cec`
- `0x180028b30`
- `0x1800291c0`
- `0x1800293c4`
- `0x180029e8c`
- `0x18002ae80`
- `0x18005d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800294a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002965a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294a2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002965a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800297bb`
- `OLEAUT32!__imp_SysStringLen` at `0x180029472`
- `OLEAUT32!__imp_SysStringLen` at `0x180029472`
- `OLEAUT32!__imp_VarBstrCat` at `0x180029493`
- `OLEAUT32!__imp_VarBstrCat` at `0x180029493`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800294be`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800294be`

## string_xrefs

- `0x18002941b`: `CCertEnrollment::FindTemplateInAD`
- `0x18002944a`: `CCertEnrollment::FindTemplateInAD`
- `0x18002958d`: `CCertEnrollment::FindTemplateInAD`
- `0x180029729`: `CCertEnrollment::FindTemplateInAD`
- `0x180029414`: `this->GetConfigurationNamingContext failed: 0x%x in %s`
- `0x180029434`: `LDAP://CN=Certificate Templates,CN=Public Key Services,CN=Services,`
- `0x180029578`: `msPKI-Cert-Template-OID`
- `0x180029636`: `msPKI-Cert-Template-OID`
- `0x180029597`: `this->FindTemplateByNameType failed: 0x%x in %s`
- `0x180029608`: `m_bstrTemplateCN.Assign failed: 0x%x in %s`
- `0x180029693`: `m_bstrTemplateOID.Assign failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertEnrollment::FindTemplateInAD(BSTR *this)
{
  OLECHAR *v2; // rbx
  void *v3; // r15
  int ConfigurationNamingContext; // eax
  int TemplateByNameType; // edi
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  UINT v9; // eax
  HRESULT v10; // eax
  HRESULT Object; // eax
  int v12; // eax
  int v13; // eax
  unsigned __int16 v14; // dx
  CCertEnrollment *v15; // rcx
  int v16; // eax
  const char *v17; // rdx
  unsigned int v18; // r14d
  unsigned __int16 v19; // dx
  CCertEnrollment *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  BSTR bstrLeft; // [rsp+30h] [rbp-59h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v26[4]; // [rsp+40h] [rbp-49h] BYREF
  __int128 v27; // [rsp+50h] [rbp-39h]
  __int64 v28; // [rsp+60h] [rbp-29h]
  _DWORD v29[28]; // [rsp+70h] [rbp-19h] BYREF
  void *v30; // [rsp+F8h] [rbp+6Fh] BYREF
  BSTR pbstrResult; // [rsp+100h] [rbp+77h] BYREF
  void *ppObject; // [rsp+108h] [rbp+7Fh] BYREF

  v2 = 0;
  bstrLeft = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  ppObject = 0;
  v3 = 0;
  v30 = 0;
  pbstr = 0;
  ConfigurationNamingContext = CCertEnrollment::GetConfigurationNamingContext((CCertEnrollment *)this, &pbstr);
  TemplateByNameType = ConfigurationNamingContext;
  if ( ConfigurationNamingContext < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->GetConfigurationNamingContext failed: 0x%x in %s",
      (unsigned int)ConfigurationNamingContext,
      "CCertEnrollment::FindTemplateInAD");
LABEL_32:
    if ( (unsigned int)dword_180084250 > 5 )
    {
      LODWORD(v30) = -1;
      LODWORD(pbstrResult) = TemplateByNameType;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180084250,
        (unsigned int)byte_18007933D,
        v6,
        v7,
        (__int64)&pbstrResult,
        (__int64)&v30);
    }
    goto LABEL_40;
  }
  v8 = CComBSTREx::Assign(
         (CComBSTREx *)&bstrLeft,
         L"LDAP://CN=Certificate Templates,CN=Public Key Services,CN=Services,");
  TemplateByNameType = v8;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "bstrBindingString.Assign failed: 0x%x in %s", v8, "CCertEnrollment::FindTemplateInAD");
    v2 = bstrLeft;
    goto LABEL_32;
  }
  v9 = SysStringLen(pbstr);
  v2 = bstrLeft;
  if ( v9 )
  {
    pbstrResult = 0;
    v10 = VarBstrCat(bstrLeft, pbstr, &pbstrResult);
    TemplateByNameType = v10;
    if ( v10 < 0 )
    {
      _DbgPrintMessage(
        8,
        "bstrBindingString.Append failed: 0x%x in %s",
        (unsigned int)v10,
        "CCertEnrollment::FindTemplateInAD");
      goto LABEL_32;
    }
    SysFreeString(v2);
    v2 = pbstrResult;
    bstrLeft = pbstrResult;
  }
  Object = ADsGetObject(v2, &IID_IDirectorySearch, &ppObject);
  TemplateByNameType = Object;
  if ( Object < 0 )
  {
    _DbgPrintMessage(8, "ADsGetObject failed: 0x%x in %s", (unsigned int)Object, "CCertEnrollment::FindTemplateInAD");
    goto LABEL_32;
  }
  v29[0] = 2;
  v29[2] = 7;
  v29[4] = 1;
  v29[10] = 5;
  v29[12] = 7;
  v29[14] = 2;
  v12 = (*(__int64 (__fastcall **)(void *, _DWORD *))(*(_QWORD *)ppObject + 24LL))(ppObject, v29);
  TemplateByNameType = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(
      8,
      "pDSSearch->SetSearchPreference failed: 0x%x in %s",
      (unsigned int)v12,
      "CCertEnrollment::FindTemplateInAD");
    goto LABEL_32;
  }
  TemplateByNameType = CCertEnrollment::FindTemplateByNameType(
                         (CCertEnrollment *)this,
                         L"displayName",
                         (struct IDirectorySearch *)ppObject,
                         &v30);
  if ( TemplateByNameType == -2147024894 )
  {
    TemplateByNameType = CCertEnrollment::FindTemplateByNameType(
                           (CCertEnrollment *)this,
                           L"cn",
                           (struct IDirectorySearch *)ppObject,
                           &v30);
    if ( TemplateByNameType == -2147024894 )
      TemplateByNameType = CCertEnrollment::FindTemplateByNameType(
                             (CCertEnrollment *)this,
                             L"msPKI-Cert-Template-OID",
                             (struct IDirectorySearch *)ppObject,
                             &v30);
  }
  if ( TemplateByNameType < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->FindTemplateByNameType failed: 0x%x in %s",
      TemplateByNameType,
      "CCertEnrollment::FindTemplateInAD");
    v3 = v30;
    goto LABEL_32;
  }
  v3 = v30;
  v13 = (*(__int64 (__fastcall **)(void *, void *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)ppObject + 80LL))(
          ppObject,
          v30,
          L"cn",
          v26);
  TemplateByNameType = v13;
  if ( v13 < 0 )
  {
LABEL_20:
    _DbgPrintMessage(
      8,
      "spDSSearch->GetColumn failed: 0x%x in %s",
      (unsigned int)v13,
      "CCertEnrollment::FindTemplateInAD");
    goto LABEL_32;
  }
  if ( v26[2] != 3 )
  {
    CCertEnrollment::SecLogColumnTypeFailure(v15, v14, 0xC0000430, *this, v26[2]);
    v18 = -2147463152;
    goto LABEL_36;
  }
  v16 = CComBSTREx::Assign((CComBSTREx *)(this + 1), *(const unsigned __int16 **)(v27 + 8));
  TemplateByNameType = v16;
  if ( v16 >= 0 )
  {
    (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppObject + 88LL))(ppObject, v26);
    v13 = (*(__int64 (__fastcall **)(void *, void *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)ppObject
                                                                                              + 80LL))(
            ppObject,
            v3,
            L"msPKI-Cert-Template-OID",
            v26);
    TemplateByNameType = v13;
    v18 = -2147463152;
    if ( v13 == -2147463152 )
    {
      SysFreeString(this[2]);
      this[2] = 0;
      TemplateByNameType = 0;
      goto LABEL_32;
    }
    if ( v13 < 0 )
      goto LABEL_20;
    if ( v26[2] == 3 )
    {
      v16 = CComBSTREx::Assign((CComBSTREx *)(this + 2), *(const unsigned __int16 **)(v27 + 8));
      TemplateByNameType = v16;
      if ( v16 >= 0 )
      {
        (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppObject + 88LL))(ppObject, v26);
        goto LABEL_32;
      }
      v17 = "m_bstrTemplateOID.Assign failed: 0x%x in %s";
      goto LABEL_24;
    }
    CCertEnrollment::SecLogColumnTypeFailure(v20, v19, 0xC0000431, *this, v26[2]);
LABEL_36:
    v17 = "spDSSearch->GetColumn failed: 0x%x in %s";
    goto LABEL_37;
  }
  v17 = "m_bstrTemplateCN.Assign failed: 0x%x in %s";
LABEL_24:
  v18 = v16;
LABEL_37:
  _DbgPrintMessage(8, v17, v18, "CCertEnrollment::FindTemplateInAD");
  if ( (unsigned int)dword_180084250 > 5 )
  {
    LODWORD(v30) = v26[2];
    LODWORD(pbstrResult) = TemplateByNameType;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180084250,
      (unsigned int)byte_180079369,
      v21,
      v22,
      (__int64)&pbstrResult,
      (__int64)&v30);
  }
  (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppObject + 88LL))(ppObject, v26);
LABEL_40:
  if ( v3 )
    (*(void (__fastcall **)(void *, void *))(*(_QWORD *)ppObject + 96LL))(ppObject, v3);
  SysFreeString(pbstr);
  ATL::CComPtrBase<IDirectorySearch>::~CComPtrBase<IDirectorySearch>(&ppObject);
  SysFreeString(v2);
  return (unsigned int)TemplateByNameType;
}

```

## disassembly

```asm
0x1800293c4  mov     [rsp-8+arg_0], rbx
0x1800293c9  push    rbp
0x1800293ca  push    rsi
0x1800293cb  push    rdi
0x1800293cc  push    r14
0x1800293ce  push    r15
0x1800293d0  lea     rbp, [rsp-37h]
0x1800293d5  sub     rsp, 0C0h
0x1800293dc  mov     rsi, rcx
0x1800293df  xor     ebx, ebx
0x1800293e1  mov     [rbp+57h+bstrLeft], rbx
0x1800293e5  xorps   xmm0, xmm0
0x1800293e8  xor     eax, eax
0x1800293ea  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800293ee  movups  [rbp+57h+var_90], xmm0
0x1800293f2  mov     [rbp+57h+var_80], rax
0x1800293f6  mov     [rbp+57h+ppObject], rax
0x1800293fa  xor     r15d, r15d
0x1800293fd  mov     [rbp+57h+arg_8], r15
0x180029401  mov     [rbp+57h+pbstr], r15
0x180029405  lea     rdx, [rbp+57h+pbstr]; unsigned __int16 **
0x180029409  call    ?GetConfigurationNamingContext@CCertEnrollment@@AEAAJPEAPEAG@Z; CCertEnrollment::GetConfigurationNamingContext(ushort * *)
0x18002940e  mov     edi, eax
0x180029410  test    eax, eax
0x180029412  jns     short loc_180029434
0x180029414  lea     rdx, aThisGetconfigu; "this->GetConfigurationNamingContext fai"...
0x18002941b  lea     r9, aCcertenrollmen_0; "CCertEnrollment::FindTemplateInAD"
0x180029422  mov     r8d, eax
0x180029425  mov     ecx, 8; int
0x18002942a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002942f  jmp     loc_1800296B3
0x180029434  lea     rdx, aLdapCnCertific; "LDAP://CN=Certificate Templates,CN=Publ"...
0x18002943b  lea     rcx, [rbp+57h+bstrLeft]; this
0x18002943f  call    ?Assign@CComBSTREx@@QEAAJPEBG@Z; CComBSTREx::Assign(ushort const *)
0x180029444  mov     edi, eax
0x180029446  test    eax, eax
0x180029448  jns     short loc_18002946E
0x18002944a  lea     r9, aCcertenrollmen_0; "CCertEnrollment::FindTemplateInAD"
0x180029451  mov     r8d, eax
0x180029454  lea     rdx, aBstrbindingstr; "bstrBindingString.Assign failed: 0x%x i"...
0x18002945b  mov     ecx, 8; int
0x180029460  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029465  mov     rbx, [rbp+57h+bstrLeft]
0x180029469  jmp     loc_1800296B3
0x18002946e  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180029472  call    cs:__imp_SysStringLen
0x180029478  mov     rbx, [rbp+57h+bstrLeft]
0x18002947c  test    eax, eax
0x18002947e  jz      short loc_1800294B0
0x180029480  mov     [rbp+57h+pbstrResult], 0
0x180029488  lea     r8, [rbp+57h+pbstrResult]; pbstrResult
0x18002948c  mov     rdx, [rbp+57h+pbstr]; bstrRight
0x180029490  mov     rcx, rbx; bstrLeft
0x180029493  call    cs:__imp_VarBstrCat
0x180029499  mov     edi, eax
0x18002949b  test    eax, eax
0x18002949d  js      short loc_1800294D6
0x18002949f  mov     rcx, rbx; bstrString
0x1800294a2  call    cs:__imp_SysFreeString
0x1800294a8  mov     rbx, [rbp+57h+pbstrResult]
0x1800294ac  mov     [rbp+57h+bstrLeft], rbx
0x1800294b0  lea     r8, [rbp+57h+ppObject]; ppObject
0x1800294b4  lea     rdx, IID_IDirectorySearch; riid
0x1800294bb  mov     rcx, rbx; lpszPathName
0x1800294be  call    cs:__imp_ADsGetObject
0x1800294c4  mov     edi, eax
0x1800294c6  test    eax, eax
0x1800294c8  jns     short loc_1800294E2
0x1800294ca  lea     rdx, aAdsgetobjectFa; "ADsGetObject failed: 0x%x in %s"
0x1800294d1  jmp     loc_18002941B
0x1800294d6  lea     rdx, aBstrbindingstr_0; "bstrBindingString.Append failed: 0x%x i"...
0x1800294dd  jmp     loc_18002941B
0x1800294e2  mov     r8d, 2
0x1800294e8  mov     [rbp+57h+var_70], r8d
0x1800294ec  lea     eax, [r8+5]
0x1800294f0  mov     [rbp+57h+var_68], eax
0x1800294f3  mov     [rbp+57h+var_60], 1
0x1800294fa  mov     [rbp+57h+var_48], 5
0x180029501  mov     [rbp+57h+var_40], eax
0x180029504  mov     [rbp+57h+var_38], r8d
0x180029508  mov     rcx, [rbp+57h+ppObject]
0x18002950c  mov     rax, [rcx]
0x18002950f  lea     rdx, [rbp+57h+var_70]
0x180029513  mov     rax, [rax+18h]
0x180029517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002951c  mov     edi, eax
0x18002951e  test    eax, eax
0x180029520  jns     short loc_18002952E
0x180029522  lea     rdx, aPdssearchSetse; "pDSSearch->SetSearchPreference failed: "...
0x180029529  jmp     loc_18002941B
0x18002952e  lea     r9, [rbp+57h+arg_8]; void **
0x180029532  mov     r8, [rbp+57h+ppObject]; struct IDirectorySearch *
0x180029536  lea     rdx, aDisplayname; "displayName"
0x18002953d  mov     rcx, rsi; this
0x180029540  call    ?FindTemplateByNameType@CCertEnrollment@@AEAAJPEBGPEAUIDirectorySearch@@PEAPEAX@Z; CCertEnrollment::FindTemplateByNameType(ushort const *,IDirectorySearch *,void * *)
0x180029545  mov     edi, eax
0x180029547  mov     r14d, 80070002h
0x18002954d  cmp     eax, r14d
0x180029550  jnz     short loc_180029589
0x180029552  lea     r9, [rbp+57h+arg_8]; void **
0x180029556  mov     r8, [rbp+57h+ppObject]; struct IDirectorySearch *
0x18002955a  lea     rdx, aCn; "cn"
0x180029561  mov     rcx, rsi; this
0x180029564  call    ?FindTemplateByNameType@CCertEnrollment@@AEAAJPEBGPEAUIDirectorySearch@@PEAPEAX@Z; CCertEnrollment::FindTemplateByNameType(ushort const *,IDirectorySearch *,void * *)
0x180029569  mov     edi, eax
0x18002956b  cmp     eax, r14d
0x18002956e  jnz     short loc_180029589
0x180029570  lea     r9, [rbp+57h+arg_8]; void **
0x180029574  mov     r8, [rbp+57h+ppObject]; struct IDirectorySearch *
0x180029578  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002957f  mov     rcx, rsi; this
0x180029582  call    ?FindTemplateByNameType@CCertEnrollment@@AEAAJPEBGPEAUIDirectorySearch@@PEAPEAX@Z; CCertEnrollment::FindTemplateByNameType(ushort const *,IDirectorySearch *,void * *)
0x180029587  mov     edi, eax
0x180029589  test    edi, edi
0x18002958b  jns     short loc_1800295B1
0x18002958d  lea     r9, aCcertenrollmen_0; "CCertEnrollment::FindTemplateInAD"
0x180029594  mov     r8d, edi
0x180029597  lea     rdx, aThisFindtempla; "this->FindTemplateByNameType failed: 0x"...
0x18002959e  mov     ecx, 8; int
0x1800295a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800295a8  mov     r15, [rbp+57h+arg_8]
0x1800295ac  jmp     loc_1800296B3
0x1800295b1  mov     rcx, [rbp+57h+ppObject]
0x1800295b5  mov     rax, [rcx]
0x1800295b8  lea     r9, [rbp+57h+var_A0]
0x1800295bc  lea     r8, aCn; "cn"
0x1800295c3  mov     r15, [rbp+57h+arg_8]
0x1800295c7  mov     rdx, r15
0x1800295ca  mov     rax, [rax+50h]
0x1800295ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295d3  mov     edi, eax
0x1800295d5  test    eax, eax
0x1800295d7  jns     short loc_1800295E5
0x1800295d9  lea     rdx, aSpdssearchGetc; "spDSSearch->GetColumn failed: 0x%x in %"...
0x1800295e0  jmp     loc_18002941B
0x1800295e5  mov     eax, [rbp+57h+var_A0+8]
0x1800295e8  cmp     eax, 3
0x1800295eb  jnz     loc_18002970A
0x1800295f1  lea     rcx, [rsi+8]; this
0x1800295f5  mov     rdx, qword ptr [rbp+57h+var_90]
0x1800295f9  mov     rdx, [rdx+8]; unsigned __int16 *
0x1800295fd  call    ?Assign@CComBSTREx@@QEAAJPEBG@Z; CComBSTREx::Assign(ushort const *)
0x180029602  mov     edi, eax
0x180029604  test    eax, eax
0x180029606  jns     short loc_180029617
0x180029608  lea     rdx, aMBstrtemplatec; "m_bstrTemplateCN.Assign failed: 0x%x in"...
0x18002960f  mov     r14d, eax
0x180029612  jmp     loc_180029729
0x180029617  mov     rcx, [rbp+57h+ppObject]
0x18002961b  mov     rax, [rcx]
0x18002961e  lea     rdx, [rbp+57h+var_A0]
0x180029622  mov     rax, [rax+58h]
0x180029626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002962b  mov     rcx, [rbp+57h+ppObject]
0x18002962f  mov     rax, [rcx]
0x180029632  lea     r9, [rbp+57h+var_A0]
0x180029636  lea     r8, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x18002963d  mov     rdx, r15
0x180029640  mov     rax, [rax+50h]
0x180029644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029649  mov     edi, eax
0x18002964b  mov     r14d, 80005010h
0x180029651  cmp     eax, r14d
0x180029654  jnz     short loc_18002966C
0x180029656  mov     rcx, [rsi+10h]; bstrString
0x18002965a  call    cs:__imp_SysFreeString
0x180029660  mov     qword ptr [rsi+10h], 0
0x180029668  xor     edi, edi
0x18002966a  jmp     short loc_1800296B3
0x18002966c  test    eax, eax
0x18002966e  js      loc_1800295D9
0x180029674  mov     eax, [rbp+57h+var_A0+8]
0x180029677  cmp     eax, 3
0x18002967a  jnz     short loc_1800296F6
0x18002967c  lea     rcx, [rsi+10h]; this
0x180029680  mov     rdx, qword ptr [rbp+57h+var_90]
0x180029684  mov     rdx, [rdx+8]; unsigned __int16 *
0x180029688  call    ?Assign@CComBSTREx@@QEAAJPEBG@Z; CComBSTREx::Assign(ushort const *)
0x18002968d  mov     edi, eax
0x18002968f  test    eax, eax
0x180029691  jns     short loc_18002969F
0x180029693  lea     rdx, aMBstrtemplateo; "m_bstrTemplateOID.Assign failed: 0x%x i"...
0x18002969a  jmp     loc_18002960F
0x18002969f  mov     rcx, [rbp+57h+ppObject]
0x1800296a3  mov     rax, [rcx]
0x1800296a6  lea     rdx, [rbp+57h+var_A0]
0x1800296aa  mov     rax, [rax+58h]
0x1800296ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b3  mov     eax, cs:dword_180084250
0x1800296b9  cmp     eax, 5
0x1800296bc  jbe     loc_18002978A
0x1800296c2  mov     dword ptr [rbp+57h+arg_8], 0FFFFFFFFh
0x1800296c9  mov     dword ptr [rbp+57h+pbstrResult], edi
0x1800296cc  lea     rax, [rbp+57h+arg_8]
0x1800296d0  mov     [rsp+0E0h+var_B8], rax
0x1800296d5  lea     rax, [rbp+57h+pbstrResult]
0x1800296d9  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800296de  lea     rdx, byte_18007933D
0x1800296e5  lea     rcx, dword_180084250
0x1800296ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800296f1  jmp     loc_18002978A
0x1800296f6  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x1800296fa  mov     r9, [rsi]; unsigned __int16 *
0x1800296fd  mov     r8d, 0C0000431h; unsigned int
0x180029703  call    ?SecLogColumnTypeFailure@CCertEnrollment@@AEAAJGIPEBGK@Z; CCertEnrollment::SecLogColumnTypeFailure(ushort,uint,ushort const *,ulong)
0x180029708  jmp     short loc_180029722
0x18002970a  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x18002970e  mov     r9, [rsi]; unsigned __int16 *
0x180029711  mov     r8d, 0C0000430h; unsigned int
0x180029717  call    ?SecLogColumnTypeFailure@CCertEnrollment@@AEAAJGIPEBGK@Z; CCertEnrollment::SecLogColumnTypeFailure(ushort,uint,ushort const *,ulong)
0x18002971c  mov     r14d, 80005010h
0x180029722  lea     rdx, aSpdssearchGetc; "spDSSearch->GetColumn failed: 0x%x in %"...
0x180029729  lea     r9, aCcertenrollmen_0; "CCertEnrollment::FindTemplateInAD"
0x180029730  mov     ecx, 8; int
0x180029735  mov     r8d, r14d
0x180029738  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002973d  mov     eax, cs:dword_180084250
0x180029743  cmp     eax, 5
0x180029746  jbe     short loc_180029776
0x180029748  mov     eax, [rbp+57h+var_A0+8]
0x18002974b  mov     dword ptr [rbp+57h+arg_8], eax
0x18002974e  mov     dword ptr [rbp+57h+pbstrResult], edi
0x180029751  lea     rax, [rbp+57h+arg_8]
0x180029755  mov     [rsp+0E0h+var_B8], rax
0x18002975a  lea     rax, [rbp+57h+pbstrResult]
0x18002975e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180029763  lea     rdx, byte_180079369
0x18002976a  lea     rcx, dword_180084250
0x180029771  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180029776  mov     rcx, [rbp+57h+ppObject]
0x18002977a  mov     rax, [rcx]
0x18002977d  lea     rdx, [rbp+57h+var_A0]
0x180029781  mov     rax, [rax+58h]
0x180029785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002978a  test    r15, r15
0x18002978d  jz      short loc_1800297A3
0x18002978f  mov     rcx, [rbp+57h+ppObject]
0x180029793  mov     rax, [rcx]
0x180029796  mov     rdx, r15
0x180029799  mov     rax, [rax+60h]
0x18002979d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297a2  nop
0x1800297a3  mov     rcx, [rbp+57h+pbstr]; bstrString
0x1800297a7  call    cs:__imp_SysFreeString
0x1800297ad  nop
0x1800297ae  lea     rcx, [rbp+57h+ppObject]
0x1800297b2  call    ??1?$CComPtrBase@UIDirectorySearch@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDirectorySearch>::~CComPtrBase<IDirectorySearch>(void)
0x1800297b7  nop
0x1800297b8  mov     rcx, rbx; bstrString
0x1800297bb  call    cs:__imp_SysFreeString
0x1800297c1  mov     eax, edi
0x1800297c3  mov     rbx, [rsp+0E0h+arg_0]
0x1800297cb  add     rsp, 0C0h
0x1800297d2  pop     r15
0x1800297d4  pop     r14
0x1800297d6  pop     rdi
0x1800297d7  pop     rsi
0x1800297d8  pop     rbp
0x1800297d9  retn
```
