# EvaluateZipEdpPolicyIfNeeded(HWND__ *,ushort const *,ushort const *,uint,ulong,ushort const *,ushort * *)

- ea: `0x1800143cc`
- end: `0x180014953`
- name: `?EvaluateZipEdpPolicyIfNeeded@@YAJPEAUHWND__@@PEBG1IK1PEAPEAG@Z`
- size: `1415`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, const unsigned __int16 *lpString1, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b430`

## callees

- `0x180010c30`
- `0x18001367c`
- `0x1800143cc`
- `0x180031e94`
- `0x180032480`
- `0x1800324b8`
- `0x180035728`
- `0x180036f50`
- `0x18003c918`
- `0x18003c990`
- `0x180040e78`
- `0x180041528`
- `0x180071010`

## import_xrefs

- `PROPSYS!PropVariantGetElementCount` at `0x180014712`
- `PROPSYS!PropVariantGetElementCount` at `0x180014712`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014459`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800144db`
- `SHELL32!SHCreateItemFromParsingName` at `0x180014459`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800144db`
- `SHLWAPI!PathFindFileNameW` at `0x18001463f`
- `SHLWAPI!PathFindFileNameW` at `0x180014734`
- `SHLWAPI!PathFindFileNameW` at `0x18001463f`
- `SHLWAPI!PathFindFileNameW` at `0x180014734`
- `SHLWAPI!PathFileExistsW` at `0x180014723`
- `SHLWAPI!PathFileExistsW` at `0x180014890`
- `SHLWAPI!PathFileExistsW` at `0x180014723`
- `SHLWAPI!PathFileExistsW` at `0x180014890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800147df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014602`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001460c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014817`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014821`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001483f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014849`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014933`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001493d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014602`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001460c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014817`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014821`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001483f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014849`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014933`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001493d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180014495`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180014495`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001441f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18001441f`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccess` at `0x1800145db`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccess` at `0x1800146ec`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccess` at `0x1800145db`
- `ext-ms-win-edputil-policy-l1-1-0!EdpRequestAccess` at `0x1800146ec`
- `ext-ms-win-security-efs-l1-1-0!EdpPlatform_ShowDialog` at `0x18001479d`
- `ext-ms-win-security-efs-l1-1-0!EdpPlatform_ShowDialog` at `0x18001479d`

## pseudocode

```c
__int64 __fastcall EvaluateZipEdpPolicyIfNeeded(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        const unsigned __int16 *lpString1,
        unsigned __int16 **a7)
{
  unsigned __int16 *v10; // rbx
  HRESULT v11; // eax
  unsigned int v12; // edi
  size_t v13; // r10
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  const struct tagPROPVARIANT *v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  const struct wil::PropVariant *v20; // r8
  __int64 v21; // rax
  int v22; // eax
  LPWSTR FileNameW; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  LPWSTR v27; // rax
  const unsigned __int16 **v29; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v30; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int128 v33; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v37; // [rsp+88h] [rbp-78h] BYREF
  void *ppv; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h] BYREF
  PROPVARIANT propvar[3]; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT pvar[3]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h]
  __int128 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  WCHAR pszPath[264]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  LODWORD(pv) = a4;
  *a7 = 0;
  if ( !(unsigned int)EdpGetIsManaged(a1, a2) )
    return 0;
  v10 = 0;
  v37 = 0;
  if ( !lpString1 )
    return 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v11 = SHCreateItemFromParsingName(a2, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  v12 = v11;
  if ( v11 != -2147024894 )
  {
    if ( v11 < 0 )
    {
      v14 = 763;
      goto LABEL_8;
    }
    goto LABEL_13;
  }
  v11 = StringCchCopyW(pszPath, 0x104u, a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v11 = PathCchRemoveFileSpec(pszPath, v13);
    v12 = v11;
    if ( v11 < 0 )
    {
      v14 = 758;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v11 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    v12 = v11;
    if ( v11 < 0 )
    {
      v14 = 759;
      goto LABEL_8;
    }
LABEL_13:
    LOWORD(propvar[0]) = 0;
    v15 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
            ppv,
            &PKEY_Security_EncryptionOwners,
            propvar);
    v12 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x300,
        (unsigned int)"shell\\ext\\zip\\dropin.cpp",
        (const char *)(unsigned int)v15,
        (int)v29);
LABEL_61:
      PropVariantClear(propvar);
      goto LABEL_62;
    }
    LOWORD(pvar[0]) = 0;
    v16 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 104LL))(
            ppv,
            &PKEY_Security_AllowedEnterpriseDataProtectionIdentities,
            pvar);
    v12 = v16;
    if ( v16 < 0 )
    {
      v18 = (unsigned int)v16;
      v19 = 770;
LABEL_59:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\ext\\zip\\dropin.cpp",
        (const char *)v18,
        (int)v29);
      goto LABEL_60;
    }
    if ( EdpHelpers::IsUnencryptedEID((EdpHelpers *)pvar, v17) )
    {
      v30 = a3;
      v31 = a2;
      v44 = 0;
      v43 = 0;
      HIDWORD(v43) = 5;
      LODWORD(v37) = 0;
      v42 = 0;
      v21 = lambda_010d7eb079e259750a4bdadd95cf3b0b_::operator_long____cdecl___void_const___AUDIT_CALLBACK_INFO___();
      v29 = &v30;
      v22 = EdpRequestAccess(a1, lpString1, 0, v21);
      v12 = v22;
      if ( v22 < 0 )
      {
        v18 = (unsigned int)v22;
        v19 = 807;
        goto LABEL_59;
      }
      if ( (_DWORD)v37 != 1 )
      {
LABEL_21:
        PropVariantClear(pvar);
        PropVariantClear(propvar);
        v12 = -2147024891;
        goto LABEL_62;
      }
      goto LABEL_46;
    }
    if ( !EdpHelpers::IsEnterpriseIdAllowed(lpString1, (const unsigned __int16 *)pvar, v20) )
    {
      if ( a5 != -1 )
        goto LABEL_21;
      FileNameW = PathFindFileNameW(a2);
      v35 = 0;
      LODWORD(pv) = 0;
      v30 = 0;
      v31 = 0;
      v33 = 0;
      v32 = 0;
      v34 = 0;
      v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              &v30,
              g_hmodThisDll,
              10606,
              FileNameW);
      v12 = v24;
      if ( v24 >= 0 )
      {
        *((_QWORD *)&v33 + 1) = v30;
        DWORD2(v34) = 1;
        LODWORD(v29) = 0;
        v24 = EdpRequestAccess(a1, lpString1, lpString1, 0);
        v12 = v24;
        if ( v24 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
          goto LABEL_21;
        }
        v25 = 827;
      }
      else
      {
        v25 = 822;
      }
      goto LABEL_26;
    }
    if ( PropVariantGetElementCount(propvar) || !PathFileExistsW(a2) )
    {
      if ( PathFileExistsW(a2) )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          *(_QWORD *)propvar[2],
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v37,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        v10 = v37;
        if ( v37 )
          goto LABEL_46;
        v19 = 872;
      }
      else
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          lpString1,
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v37,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        v10 = v37;
        if ( v37 )
          goto LABEL_46;
        v19 = 866;
      }
      v12 = -2147024882;
      v18 = 2147942414LL;
      goto LABEL_59;
    }
    v27 = PathFindFileNameW(a2);
    v39 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v30,
            g_hmodThisDll,
            (unsigned int)((_DWORD)pv != 1) + 10603,
            v27);
    v12 = v24;
    if ( v24 < 0 )
    {
      v25 = 845;
LABEL_26:
      v26 = (unsigned int)v24;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shell\\ext\\zip\\dropin.cpp",
        (const char *)v26,
        (int)v29);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
LABEL_60:
      PropVariantClear(pvar);
      goto LABEL_61;
    }
    if ( a5 == -1 )
    {
      v24 = EdpPlatform_ShowDialog(a1, 4, v30, &v39);
      v12 = v24;
      if ( v24 < 0 )
      {
        v25 = 850;
        goto LABEL_26;
      }
      if ( v39 == 1 )
        goto LABEL_39;
    }
    else if ( a5 != 7 )
    {
LABEL_39:
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        lpString1,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v37,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
      v10 = v37;
      if ( !v37 )
      {
        v12 = -2147024882;
        v25 = 860;
        v26 = 2147942414LL;
        goto LABEL_27;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
LABEL_46:
      PropVariantClear(pvar);
      PropVariantClear(propvar);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      if ( v10 )
        *a7 = v10;
      return 0;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
    PropVariantClear(pvar);
    PropVariantClear(propvar);
    v12 = -2147023673;
    goto LABEL_62;
  }
  v14 = 755;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"shell\\ext\\zip\\dropin.cpp",
    (const char *)(unsigned int)v11,
    (int)v29);
LABEL_62:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v12;
}

```

## disassembly

```asm
0x1800143cc  mov     [rsp-8+arg_18], rbx
0x1800143d1  push    rbp
0x1800143d2  push    rsi
0x1800143d3  push    rdi
0x1800143d4  push    r12
0x1800143d6  push    r13
0x1800143d8  push    r14
0x1800143da  push    r15
0x1800143dc  lea     rbp, [rsp-220h]
0x1800143e4  sub     rsp, 320h
0x1800143eb  mov     rax, cs:__security_cookie
0x1800143f2  xor     rax, rsp
0x1800143f5  mov     [rbp+250h+var_40], rax
0x1800143fc  mov     r12, [rbp+250h+arg_30]
0x180014403  mov     r13, r8
0x180014406  mov     rsi, [rbp+250h+lpString1]
0x18001440d  mov     r14, rdx
0x180014410  mov     dword ptr [rbp+250h+pv], r9d
0x180014414  mov     r15, rcx
0x180014417  mov     qword ptr [r12], 0
0x18001441f  call    cs:__imp_EdpGetIsManaged
0x180014425  test    eax, eax
0x180014427  jz      loc_180014861
0x18001442d  xor     ebx, ebx
0x18001442f  mov     [rbp+250h+var_2C8], rbx
0x180014433  test    rsi, rsi
0x180014436  jz      loc_180014861
0x18001443c  lea     rcx, [rbp+250h+ppv]
0x180014440  mov     [rbp+250h+ppv], rbx
0x180014444  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014449  lea     r9, [rbp+250h+ppv]; ppv
0x18001444d  xor     edx, edx; pbc
0x18001444f  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180014456  mov     rcx, r14; pszPath
0x180014459  call    cs:__imp_SHCreateItemFromParsingName
0x18001445f  mov     edi, eax
0x180014461  cmp     eax, 80070002h
0x180014466  jnz     loc_1800144EE
0x18001446c  mov     r10d, 104h
0x180014472  lea     rcx, [rbp+250h+pszPath]; unsigned __int16 *
0x180014476  mov     edx, r10d; unsigned __int64
0x180014479  mov     r8, r14; unsigned __int16 *
0x18001447c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014481  mov     edi, eax
0x180014483  test    eax, eax
0x180014485  jns     short loc_18001448E
0x180014487  mov     edx, 2F3h
0x18001448c  jmp     short loc_1800144A6
0x18001448e  mov     rdx, r10; cchPath
0x180014491  lea     rcx, [rbp+250h+pszPath]; pszPath
0x180014495  call    cs:__imp_PathCchRemoveFileSpec
0x18001449b  mov     edi, eax
0x18001449d  test    eax, eax
0x18001449f  jns     short loc_1800144C1
0x1800144a1  mov     edx, 2F6h; void *
0x1800144a6  mov     rcx, [rbp+258h]; this
0x1800144ad  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x1800144b4  mov     r9d, eax; char *
0x1800144b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800144bc  jmp     loc_180014943
0x1800144c1  lea     rcx, [rbp+250h+ppv]
0x1800144c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800144ca  lea     r9, [rbp+250h+ppv]; ppv
0x1800144ce  xor     edx, edx; pbc
0x1800144d0  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800144d7  lea     rcx, [rbp+250h+pszPath]; pszPath
0x1800144db  call    cs:__imp_SHCreateItemFromParsingName
0x1800144e1  mov     edi, eax
0x1800144e3  test    eax, eax
0x1800144e5  jns     short loc_1800144F9
0x1800144e7  mov     edx, 2F7h
0x1800144ec  jmp     short loc_1800144A6
0x1800144ee  test    eax, eax
0x1800144f0  jns     short loc_1800144F9
0x1800144f2  mov     edx, 2FBh
0x1800144f7  jmp     short loc_1800144A6
0x1800144f9  mov     rcx, [rbp+250h+ppv]
0x1800144fd  lea     r8, [rbp+250h+propvar]
0x180014501  xor     eax, eax
0x180014503  lea     rdx, PKEY_Security_EncryptionOwners
0x18001450a  mov     word ptr [rbp+250h+propvar], ax
0x18001450e  mov     rax, [rcx]
0x180014511  mov     rax, [rax+68h]
0x180014515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001451a  mov     edi, eax
0x18001451c  test    eax, eax
0x18001451e  jns     short loc_180014540
0x180014520  mov     rcx, [rbp+258h]; this
0x180014527  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x18001452e  mov     r9d, eax; char *
0x180014531  mov     edx, 300h; void *
0x180014536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001453b  jmp     loc_180014939
0x180014540  mov     rcx, [rbp+250h+ppv]
0x180014544  lea     r8, [rbp+250h+pvar]
0x180014548  xor     eax, eax
0x18001454a  lea     rdx, PKEY_Security_AllowedEnterpriseDataProtectionIdentities
0x180014551  mov     word ptr [rbp+250h+pvar], ax
0x180014555  mov     rax, [rcx]
0x180014558  mov     rax, [rax+68h]
0x18001455c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014561  mov     edi, eax
0x180014563  test    eax, eax
0x180014565  jns     short loc_180014574
0x180014567  mov     r9d, eax
0x18001456a  mov     edx, 302h
0x18001456f  jmp     loc_18001491C
0x180014574  lea     rcx, [rbp+250h+pvar]; this
0x180014578  call    ?IsUnencryptedEID@EdpHelpers@@YA_NAEBUtagPROPVARIANT@@@Z; EdpHelpers::IsUnencryptedEID(tagPROPVARIANT const &)
0x18001457d  test    al, al
0x18001457f  jz      loc_18001461C
0x180014585  xorps   xmm0, xmm0
0x180014588  mov     [rsp+350h+var_310], r13
0x18001458d  xor     eax, eax
0x18001458f  mov     [rsp+350h+var_308], r14
0x180014594  xor     r13d, r13d
0x180014597  mov     [rbp+250h+var_260], rax
0x18001459b  movups  [rbp+250h+var_270], xmm0
0x18001459f  mov     dword ptr [rbp+250h+var_270+0Ch], 5
0x1800145a6  mov     dword ptr [rbp+250h+var_2C8], r13d
0x1800145aa  movups  [rbp+250h+var_280], xmm0
0x1800145ae  call    _lambda_010d7eb079e259750a4bdadd95cf3b0b___operator_long____cdecl___void_const___AUDIT_CALLBACK_INFO___
0x1800145b3  mov     r9, rax
0x1800145b6  xor     r8d, r8d
0x1800145b9  lea     rax, [rbp+250h+var_2C8]
0x1800145bd  mov     rdx, rsi
0x1800145c0  mov     [rsp+350h+var_320], rax
0x1800145c5  mov     rcx, r15
0x1800145c8  lea     rax, [rbp+250h+var_280]
0x1800145cc  mov     [rsp+350h+var_328], rax
0x1800145d1  lea     rax, [rsp+350h+var_310]
0x1800145d6  mov     [rsp+350h+var_330], rax
0x1800145db  call    cs:__imp_EdpRequestAccess
0x1800145e1  mov     edi, eax
0x1800145e3  test    eax, eax
0x1800145e5  jns     short loc_1800145F4
0x1800145e7  mov     r9d, eax
0x1800145ea  mov     edx, 327h
0x1800145ef  jmp     loc_18001491C
0x1800145f4  cmp     dword ptr [rbp+250h+var_2C8], 1
0x1800145f8  jz      loc_18001483B
0x1800145fe  lea     rcx, [rbp+250h+pvar]; pvar
0x180014602  call    cs:__imp_PropVariantClear
0x180014608  lea     rcx, [rbp+250h+propvar]; pvar
0x18001460c  call    cs:__imp_PropVariantClear
0x180014612  mov     edi, 80070005h
0x180014617  jmp     loc_180014943
0x18001461c  lea     rdx, [rbp+250h+pvar]; unsigned __int16 *
0x180014620  mov     rcx, rsi; lpString1
0x180014623  call    ?IsEnterpriseIdAllowed@EdpHelpers@@YA_NPEBGAEBVPropVariant@wil@@@Z; EdpHelpers::IsEnterpriseIdAllowed(ushort const *,wil::PropVariant const &)
0x180014628  xor     r13d, r13d
0x18001462b  test    al, al
0x18001462d  jnz     loc_18001470E
0x180014633  cmp     [rbp+250h+arg_20], 0FFFFFFFFh
0x18001463a  jnz     short loc_1800145FE
0x18001463c  mov     rcx, r14; pszPath
0x18001463f  call    cs:__imp_PathFindFileNameW
0x180014645  mov     rdx, cs:g_hmodThisDll
0x18001464c  xor     ecx, ecx
0x18001464e  xorps   xmm0, xmm0
0x180014651  mov     [rsp+350h+var_2D8], rcx
0x180014656  lea     rcx, [rsp+350h+var_310]
0x18001465b  mov     dword ptr [rbp+250h+pv], r13d
0x18001465f  mov     r9, rax
0x180014662  mov     [rsp+350h+var_310], r13
0x180014667  mov     r8d, 296Eh
0x18001466d  mov     [rsp+350h+var_308], r13
0x180014672  movups  [rsp+350h+var_2F8], xmm0
0x180014677  mov     [rsp+350h+var_300], r13
0x18001467c  movups  [rsp+350h+var_2E8], xmm0
0x180014681  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180014686  mov     edi, eax
0x180014688  test    eax, eax
0x18001468a  jns     short loc_1800146B6
0x18001468c  mov     edx, 336h; void *
0x180014691  mov     r9d, eax; char *
0x180014694  mov     rcx, [rbp+258h]; this
0x18001469b  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x1800146a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146a7  lea     rcx, [rsp+350h+var_310]
0x1800146ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800146b1  jmp     loc_18001492F
0x1800146b6  mov     rax, [rsp+350h+var_310]
0x1800146bb  xor     r9d, r9d
0x1800146be  mov     qword ptr [rsp+350h+var_2F8+8], rax
0x1800146c3  mov     r8, rsi
0x1800146c6  lea     rax, [rbp+250h+pv]
0x1800146ca  mov     dword ptr [rsp+350h+var_2E8+8], 1
0x1800146d2  mov     [rsp+350h+var_320], rax
0x1800146d7  mov     rdx, rsi
0x1800146da  lea     rax, [rsp+350h+var_2F8]
0x1800146df  mov     rcx, r15
0x1800146e2  mov     [rsp+350h+var_328], rax
0x1800146e7  mov     [rsp+350h+var_330], r13
0x1800146ec  call    cs:__imp_EdpRequestAccess
0x1800146f2  mov     edi, eax
0x1800146f4  test    eax, eax
0x1800146f6  jns     short loc_1800146FF
0x1800146f8  mov     edx, 33Bh
0x1800146fd  jmp     short loc_180014691
0x1800146ff  lea     rcx, [rsp+350h+var_310]
0x180014704  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014709  jmp     loc_1800145FE
0x18001470e  lea     rcx, [rbp+250h+propvar]; propvar
0x180014712  call    cs:__imp_PropVariantGetElementCount
0x180014718  test    eax, eax
0x18001471a  jnz     loc_18001488D
0x180014720  mov     rcx, r14; pszPath
0x180014723  call    cs:__imp_PathFileExistsW
0x180014729  test    eax, eax
0x18001472b  jz      loc_18001488D
0x180014731  mov     rcx, r14; pszPath
0x180014734  call    cs:__imp_PathFindFileNameW
0x18001473a  cmp     dword ptr [rbp+250h+pv], 1
0x18001473e  lea     rcx, [rsp+350h+var_310]
0x180014743  mov     rdx, cs:g_hmodThisDll
0x18001474a  mov     r8d, r13d
0x18001474d  setnz   r8b
0x180014751  mov     [rbp+250h+var_2B8], r13d
0x180014755  add     r8d, 296Bh
0x18001475c  mov     [rsp+350h+var_310], r13
0x180014761  mov     r9, rax
0x180014764  mov     [rsp+350h+var_308], r13
0x180014769  mov     [rsp+350h+var_300], r13
0x18001476e  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180014773  mov     edi, eax
0x180014775  test    eax, eax
0x180014777  jns     short loc_180014783
0x180014779  mov     edx, 34Dh
0x18001477e  jmp     loc_180014691
0x180014783  cmp     [rbp+250h+arg_20], 0FFFFFFFFh
0x18001478a  jnz     short loc_180014800
0x18001478c  mov     r8, [rsp+350h+var_310]
0x180014791  lea     r9, [rbp+250h+var_2B8]
0x180014795  mov     edx, 4
0x18001479a  mov     rcx, r15
0x18001479d  call    cs:__imp_EdpPlatform_ShowDialog
0x1800147a3  mov     edi, eax
0x1800147a5  test    eax, eax
0x1800147a7  jns     short loc_1800147B3
0x1800147a9  mov     edx, 352h
0x1800147ae  jmp     loc_180014691
0x1800147b3  cmp     [rbp+250h+var_2B8], 1
0x1800147b7  jnz     short loc_180014809
0x1800147b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800147bd  lea     rcx, [rbp+250h+pv]
0x1800147c1  mov     rdx, rsi
0x1800147c4  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800147c9  lea     rdx, [rbp+250h+pv]
0x1800147cd  lea     rcx, [rbp+250h+var_2C8]
0x1800147d1  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800147d6  mov     rcx, [rbp+250h+pv]; pv
0x1800147da  test    rcx, rcx
0x1800147dd  jz      short loc_1800147E5
0x1800147df  call    cs:__imp_CoTaskMemFree
0x1800147e5  mov     rbx, [rbp+250h+var_2C8]
0x1800147e9  test    rbx, rbx
0x1800147ec  jnz     short loc_180014831
0x1800147ee  mov     edi, 8007000Eh
0x1800147f3  mov     edx, 35Ch
0x1800147f8  mov     r9d, edi
0x1800147fb  jmp     loc_180014694
0x180014800  cmp     [rbp+250h+arg_20], 7
0x180014807  jnz     short loc_1800147B9
0x180014809  lea     rcx, [rsp+350h+var_310]
0x18001480e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180014813  lea     rcx, [rbp+250h+pvar]; pvar
0x180014817  call    cs:__imp_PropVariantClear
0x18001481d  lea     rcx, [rbp+250h+propvar]; pvar
0x180014821  call    cs:__imp_PropVariantClear
0x180014827  mov     edi, 800704C7h
0x18001482c  jmp     loc_180014943
0x180014831  lea     rcx, [rsp+350h+var_310]
0x180014836  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001483b  lea     rcx, [rbp+250h+pvar]; pvar
0x18001483f  call    cs:__imp_PropVariantClear
0x180014845  lea     rcx, [rbp+250h+propvar]; pvar
0x180014849  call    cs:__imp_PropVariantClear
0x18001484f  lea     rcx, [rbp+250h+ppv]
0x180014853  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014858  test    rbx, rbx
0x18001485b  jz      short loc_180014861
0x18001485d  mov     [r12], rbx
0x180014861  xor     eax, eax
0x180014863  mov     rcx, [rbp+250h+var_40]
0x18001486a  xor     rcx, rsp; StackCookie
0x18001486d  call    __security_check_cookie
0x180014872  mov     rbx, [rsp+350h+arg_18]
0x18001487a  add     rsp, 320h
0x180014881  pop     r15
0x180014883  pop     r14
0x180014885  pop     r13
0x180014887  pop     r12
0x180014889  pop     rdi
0x18001488a  pop     rsi
0x18001488b  pop     rbp
0x18001488c  retn
0x18001488d  mov     rcx, r14; pszPath
0x180014890  call    cs:__imp_PathFileExistsW
0x180014896  or      r8, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
