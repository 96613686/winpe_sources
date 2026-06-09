# CArchiveIDList::EvaluateExtractEdpPolicyIfNeeded(HWND__ *,ushort const *,ushort const *,bool,ulong,ushort const *,ushort * *)

- ea: `0x18001495c`
- end: `0x180014be8`
- name: `?EvaluateExtractEdpPolicyIfNeeded@CArchiveIDList@@AEBAJPEAUHWND__@@PEBG1_NK1PEAPEAG@Z`
- size: `652`
- prototype: `__int64 __fastcall(CArchiveIDList *this, HWND, const unsigned __int16 *, const unsigned __int16 *, bool, char, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f284`

## callees

- `0x18001367c`
- `0x18001495c`
- `0x180024a24`
- `0x180031e94`
- `0x180036f50`
- `0x18003c824`
- `0x18003c918`
- `0x18003c990`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180014a06`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014adc`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014a06`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014adc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aa7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aa7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a63`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014b68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a37`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a63`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014a8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014b68`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180014990`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180014990`

## pseudocode

```c
__int64 __fastcall CArchiveIDList::EvaluateExtractEdpPolicyIfNeeded(
        CArchiveIDList *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        char a6,
        const unsigned __int16 *a7,
        unsigned __int16 **a8)
{
  HRESULT v11; // eax
  unsigned int v12; // ebx
  HRESULT v13; // eax
  int EnterpriseId; // eax
  int v15; // eax
  const struct tagPROPVARIANT *v16; // rdx
  const struct wil::PropVariant *v17; // r8
  LPVOID pv; // [rsp+20h] [rbp-40h] BYREF
  void *ppv; // [rsp+28h] [rbp-38h] BYREF
  struct IShellItem *v20; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar[3]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a8 = 0;
  if ( (a6 & 0x20) != 0 || !(unsigned int)EdpGetIsManaged(this, a2) )
    return 0;
  v20 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v13 = SHCreateItemFromParsingName(a3, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v20);
  v12 = v13;
  if ( v13 >= 0 )
  {
    pv = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    EnterpriseId = IShellItem_GetEnterpriseId(v20, (unsigned __int16 **)&pv);
    v12 = EnterpriseId;
    if ( EnterpriseId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"shell\\ext\\zip\\arcentry.cpp",
        (const char *)(unsigned int)EnterpriseId,
        (int)pv);
      goto LABEL_5;
    }
    if ( pv )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      v11 = SHCreateItemFromParsingName(a4, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"shell\\ext\\zip\\arcentry.cpp",
          (const char *)(unsigned int)v11,
          (int)pv);
LABEL_24:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
LABEL_5:
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_4;
      }
      LOWORD(pvar[0]) = 0;
      v15 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
              ppv,
              &PKEY_Security_AllowedEnterpriseDataProtectionIdentities,
              pvar);
      v12 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"shell\\ext\\zip\\arcentry.cpp",
          (const char *)(unsigned int)v15,
          (int)pv);
        PropVariantClear(pvar);
        goto LABEL_24;
      }
      if ( EdpHelpers::IsUnencryptedEID((EdpHelpers *)pvar, v16) )
      {
        if ( (a6 & 0x10) == 0 )
        {
          PropVariantClear(pvar);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          if ( pv )
            CoTaskMemFree(pv);
          v12 = -2147024540;
          goto LABEL_4;
        }
      }
      else
      {
        if ( !EdpHelpers::IsEnterpriseIdAllowed((LPCWCH)pv, (const unsigned __int16 *)pvar, v17) )
        {
          PropVariantClear(pvar);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
          if ( pv )
            CoTaskMemFree(pv);
          v12 = -2144927672;
          goto LABEL_4;
        }
        *a8 = (unsigned __int16 *)pv;
        pv = 0;
      }
      PropVariantClear(pvar);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      if ( pv )
        CoTaskMemFree(pv);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBB,
    (unsigned int)"shell\\ext\\zip\\arcentry.cpp",
    (const char *)(unsigned int)v13,
    (int)pv);
LABEL_4:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  return v12;
}

```

## disassembly

```asm
0x18001495c  mov     [rsp-18h+arg_0], rbx
0x180014961  push    rbp
0x180014962  push    rsi
0x180014963  push    rdi
0x180014964  mov     rbp, rsp
0x180014967  sub     rsp, 60h
0x18001496b  mov     rax, cs:__security_cookie
0x180014972  xor     rax, rsp
0x180014975  mov     [rbp+var_10], rax
0x180014979  test    [rbp+arg_28], 20h
0x18001497d  mov     rsi, r9
0x180014980  mov     rdi, [rbp+arg_38]
0x180014984  mov     rbx, r8
0x180014987  mov     qword ptr [rdi], 0
0x18001498e  jnz     short loc_18001499E
0x180014990  call    cs:__imp_EdpGetIsManaged
0x180014996  test    eax, eax
0x180014998  jnz     loc_180014ABB
0x18001499e  xor     eax, eax
0x1800149a0  mov     rcx, [rbp+var_10]
0x1800149a4  xor     rcx, rsp; StackCookie
0x1800149a7  call    __security_check_cookie
0x1800149ac  mov     rbx, [rsp+60h+arg_0]
0x1800149b4  add     rsp, 60h
0x1800149b8  pop     rdi
0x1800149b9  pop     rsi
0x1800149ba  pop     rbp
0x1800149bb  retn
0x1800149bc  call    cs:__imp_CoTaskMemFree
0x1800149c2  lea     rcx, [rbp+var_30]
0x1800149c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149cb  mov     eax, ebx
0x1800149cd  jmp     short loc_1800149A0
0x1800149cf  mov     rcx, [rbp+pv]; pv
0x1800149d3  test    rcx, rcx
0x1800149d6  jz      short loc_1800149C2
0x1800149d8  jmp     short loc_1800149BC
0x1800149da  cmp     [rbp+pv], 0
0x1800149df  jz      loc_180014AAD
0x1800149e5  lea     rcx, [rbp+ppv]
0x1800149e9  mov     [rbp+ppv], 0
0x1800149f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149f6  lea     r9, [rbp+ppv]; ppv
0x1800149fa  xor     edx, edx; pbc
0x1800149fc  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180014a03  mov     rcx, rsi; pszPath
0x180014a06  call    cs:__imp_SHCreateItemFromParsingName
0x180014a0c  mov     ebx, eax
0x180014a0e  test    eax, eax
0x180014a10  jns     loc_180014B7C
0x180014a16  mov     rcx, [rbp+18h]; this
0x180014a1a  lea     r8, aShellExtZipArc_2; "shell\\ext\\zip\\arcentry.cpp"
0x180014a21  mov     r9d, eax; char *
0x180014a24  mov     edx, 0C3h; void *
0x180014a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a2e  jmp     loc_180014B6E
0x180014a33  lea     rcx, [rbp+pvar]; pvar
0x180014a37  call    cs:__imp_PropVariantClear
0x180014a3d  lea     rcx, [rbp+ppv]
0x180014a41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a46  mov     rcx, [rbp+pv]; pv
0x180014a4a  test    rcx, rcx
0x180014a4d  jz      short loc_180014A55
0x180014a4f  call    cs:__imp_CoTaskMemFree
0x180014a55  mov     ebx, 80070164h
0x180014a5a  jmp     loc_1800149C2
0x180014a5f  lea     rcx, [rbp+pvar]; pvar
0x180014a63  call    cs:__imp_PropVariantClear
0x180014a69  lea     rcx, [rbp+ppv]
0x180014a6d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a72  mov     rcx, [rbp+pv]; pv
0x180014a76  test    rcx, rcx
0x180014a79  jz      short loc_180014A81
0x180014a7b  call    cs:__imp_CoTaskMemFree
0x180014a81  mov     ebx, 80270048h
0x180014a86  jmp     loc_1800149C2
0x180014a8b  lea     rcx, [rbp+pvar]; pvar
0x180014a8f  call    cs:__imp_PropVariantClear
0x180014a95  lea     rcx, [rbp+ppv]
0x180014a99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014a9e  mov     rcx, [rbp+pv]; pv
0x180014aa2  test    rcx, rcx
0x180014aa5  jz      short loc_180014AAD
0x180014aa7  call    cs:__imp_CoTaskMemFree
0x180014aad  lea     rcx, [rbp+var_30]
0x180014ab1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014ab6  jmp     loc_18001499E
0x180014abb  lea     rcx, [rbp+var_30]
0x180014abf  mov     [rbp+var_30], 0
0x180014ac7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014acc  lea     r9, [rbp+var_30]; ppv
0x180014ad0  xor     edx, edx; pbc
0x180014ad2  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180014ad9  mov     rcx, rbx; pszPath
0x180014adc  call    cs:__imp_SHCreateItemFromParsingName
0x180014ae2  mov     ebx, eax
0x180014ae4  test    eax, eax
0x180014ae6  jns     short loc_180014B05
0x180014ae8  mov     rcx, [rbp+18h]; this
0x180014aec  lea     r8, aShellExtZipArc_2; "shell\\ext\\zip\\arcentry.cpp"
0x180014af3  mov     r9d, eax; char *
0x180014af6  mov     edx, 0BBh; void *
0x180014afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b00  jmp     loc_1800149C2
0x180014b05  xor     edx, edx
0x180014b07  mov     [rbp+pv], 0
0x180014b0f  lea     rcx, [rbp+pv]
0x180014b13  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014b18  mov     rcx, [rbp+var_30]; struct IShellItem *
0x180014b1c  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180014b20  call    ?IShellItem_GetEnterpriseId@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetEnterpriseId(IShellItem *,ushort * *)
0x180014b25  mov     ebx, eax
0x180014b27  test    eax, eax
0x180014b29  jns     loc_1800149DA
0x180014b2f  mov     rcx, [rbp+18h]; this
0x180014b33  lea     r8, aShellExtZipArc_2; "shell\\ext\\zip\\arcentry.cpp"
0x180014b3a  mov     r9d, eax; char *
0x180014b3d  mov     edx, 0BEh; void *
0x180014b42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b47  jmp     loc_1800149CF
0x180014b4c  mov     rcx, [rbp+18h]; this
0x180014b50  lea     r8, aShellExtZipArc_2; "shell\\ext\\zip\\arcentry.cpp"
0x180014b57  mov     r9d, eax; char *
0x180014b5a  mov     edx, 0C5h; void *
0x180014b5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b64  lea     rcx, [rbp+pvar]; pvar
0x180014b68  call    cs:__imp_PropVariantClear
0x180014b6e  lea     rcx, [rbp+ppv]
0x180014b72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014b77  jmp     loc_1800149CF
0x180014b7c  mov     rcx, [rbp+ppv]
0x180014b80  lea     r8, [rbp+pvar]
0x180014b84  xor     eax, eax
0x180014b86  lea     rdx, PKEY_Security_AllowedEnterpriseDataProtectionIdentities
0x180014b8d  mov     word ptr [rbp+pvar], ax
0x180014b91  mov     rax, [rcx]
0x180014b94  mov     rax, [rax+68h]
0x180014b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b9d  mov     ebx, eax
0x180014b9f  test    eax, eax
0x180014ba1  js      short loc_180014B4C
0x180014ba3  lea     rcx, [rbp+pvar]; this
0x180014ba7  call    ?IsUnencryptedEID@EdpHelpers@@YA_NAEBUtagPROPVARIANT@@@Z; EdpHelpers::IsUnencryptedEID(tagPROPVARIANT const &)
0x180014bac  test    al, al
0x180014bae  jz      short loc_180014BBF
0x180014bb0  test    [rbp+arg_28], 10h
0x180014bb4  jnz     loc_180014A8B
0x180014bba  jmp     loc_180014A33
0x180014bbf  mov     rcx, [rbp+pv]; lpString1
0x180014bc3  lea     rdx, [rbp+pvar]; unsigned __int16 *
0x180014bc7  call    ?IsEnterpriseIdAllowed@EdpHelpers@@YA_NPEBGAEBVPropVariant@wil@@@Z; EdpHelpers::IsEnterpriseIdAllowed(ushort const *,wil::PropVariant const &)
0x180014bcc  test    al, al
0x180014bce  jz      loc_180014A5F
0x180014bd4  mov     rax, [rbp+pv]
0x180014bd8  mov     [rdi], rax
0x180014bdb  mov     [rbp+pv], 0
0x180014be3  jmp     loc_180014A8B
```
