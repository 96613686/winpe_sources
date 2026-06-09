# CFolderTypeDescription::_LoadFolderTypeInfo(ushort const *,int)

- ea: `0x180295e24`
- end: `0x1802963c4`
- name: `?_LoadFolderTypeInfo@CFolderTypeDescription@@AEAAJPEBGH@Z`
- size: `1440`
- prototype: `__int64 __fastcall(CFolderTypeDescription *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180295da0`
- `0x180295e24`

## callees

- `0x1800143b0`
- `0x180045bd0`
- `0x18011a17c`
- `0x180133f50`
- `0x180231670`
- `0x180295e24`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802961de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802962e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180296331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802961de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802962e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180296331`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180295e88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180296143`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180296199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180295e88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180296143`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180296199`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180296234`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1802962cd`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180296234`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1802962cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180295f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802960dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180296349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180296377`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180295f66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802960dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180296349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180296377`
- `SHCORE!__imp_GUIDFromStringW` at `0x180295f40`
- `SHCORE!__imp_GUIDFromStringW` at `0x180295f40`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295f18`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295f92`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295fd3`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295f18`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295f92`
- `PROPSYS!PSPropertyBag_ReadStr` at `0x180295fd3`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180295fb1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180295ff2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180296011`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180296030`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18029604f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180295fb1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180295ff2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180296011`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180296030`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18029604f`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180296167`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802963a3`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180296167`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x1802963a3`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180296071`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18029609b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1802960c5`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180296071`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18029609b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1802960c5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x180295eec`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x18029631c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x180295eec`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHCreatePropertyBagOnRegKey` at `0x18029631c`

## pseudocode

```c
__int64 __fastcall CFolderTypeDescription::_LoadFolderTypeInfo(
        CFolderTypeDescription *this,
        const unsigned __int16 *a2,
        int a3)
{
  int v6; // edi
  void *v8; // rcx
  IPropertyBag *v9; // rcx
  int TopViews; // eax
  IPropertyBag *v11; // rcx
  DWORD v12; // edi
  DWORD i; // edx
  unsigned int v14; // eax
  unsigned __int64 v15; // rcx
  _QWORD *v16; // rsi
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // kr00_8
  int v19; // eax
  DWORD v20; // edi
  __int64 v21; // r11
  IPropertyBag *propBag; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR v25; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR v26; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY v28; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cbData[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR value[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Data[40]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SubKey; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v35[526]; // [rsp+132h] [rbp+32h] BYREF
  WCHAR ValueName[264]; // [rsp+340h] [rbp+240h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes",
         0,
         0x20019u,
         &hKey) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    propBag = 0;
    v6 = SHCreatePropertyBagOnRegKey(hKey, a2, 0, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &propBag);
    if ( v6 >= 0 )
    {
      if ( PSPropertyBag_ReadStr(propBag, L"Parent", value, 39) >= 0 )
      {
        if ( !a3 )
        {
          *((GUID *)this + 3) = GUID_NULL;
          GUIDFromStringW(value);
        }
        CFolderTypeDescription::_LoadFolderTypeInfo(this, value, 1);
        v8 = (void *)*((_QWORD *)this + 9);
        *((_DWORD *)this + 16) = 0;
        CoTaskMemFree(v8);
        *((_QWORD *)this + 9) = 0;
      }
      v9 = propBag;
      *((_WORD *)this + 48) = 0;
      PSPropertyBag_ReadStr(v9, L"CanonicalName", (LPWSTR)this + 48, 260);
      PSPropertyBag_ReadDWORD(propBag, L"PerceivedType", (DWORD *)this + 154);
      PSPropertyBag_ReadStr(propBag, L"Theme", (LPWSTR)this + 310, 260);
      PSPropertyBag_ReadDWORD(propBag, L"LayoutType", (DWORD *)this + 285);
      PSPropertyBag_ReadDWORD(propBag, L"TopViewPersistence", (DWORD *)this + 292);
      PSPropertyBag_ReadDWORD(propBag, L"ViewSettingsPersistence", (DWORD *)this + 293);
      PSPropertyBag_ReadDWORD(propBag, L"Mode", (DWORD *)this + 294);
      v25 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"HelpTopic", &v25) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 143));
        *((_QWORD *)this + 143) = v25;
      }
      v26 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"Class", &v26) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 144));
        *((_QWORD *)this + 144) = v26;
      }
      v27 = 0;
      if ( PSPropertyBag_ReadStrAlloc(propBag, L"MostRelevant", &v27) >= 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 145));
        *((_QWORD *)this + 145) = v27;
      }
      SubKey = 0;
      memset_0(v35, 0, 0x206u);
      StringCchPrintfW(
        &SubKey,
        0x104u,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes\\%s\\Modifiers",
        a2);
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20019u, &phkResult) )
      {
        *((_DWORD *)this + 16) = 0;
        v12 = 0;
        Type = 0;
        for ( i = 0; ; i = v12 )
        {
          cchValueName = 260;
          if ( RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, &Type, 0, 0) )
            break;
          ++*((_DWORD *)this + 16);
          ++v12;
        }
        v14 = *((_DWORD *)this + 16);
        if ( v14
          && ((v15 = v14,
               *(_QWORD *)cbData = 0,
               v16 = (_QWORD *)((char *)this + 72),
               v18 = v14,
               v17 = 536LL * v14,
               *((_QWORD *)this + 9) = 0,
               !is_mul_ok(v18, 0x218u))
            ? (v19 = -2147024362)
            : (v19 = CTCoAllocPolicy::Alloc((void *)v15, 1u, v17, (void **)this + 9)),
              v19 >= 0) )
        {
          v20 = 0;
          cchValueName = 260;
          for ( cbData[0] = 78; v20 < *((_DWORD *)this + 16); cbData[0] = 78 )
          {
            if ( RegEnumValueW(phkResult, v20, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, cbData) )
              break;
            StringCchCopyW((unsigned __int16 *)(536LL * v20 + *v16 + 16LL), 0x104u, ValueName);
            SHCLSIDFromString(Data, (CLSID *)(v21 + *v16));
            ++v20;
            cchValueName = 260;
          }
        }
        else
        {
          *((_DWORD *)this + 16) = 0;
        }
        RegCloseKey(phkResult);
      }
      PSPropertyBag_ReadGUID(propBag, L"DefaultView", (GUID *)this + 5);
      v28 = 0;
      if ( !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FolderTypes",
              0,
              0x20019u,
              &v28) )
      {
        *(_QWORD *)cbData = 0;
        if ( (int)SHCreatePropertyBagOnRegKey(hKey, a2, 0, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, cbData) >= 0 )
        {
          PSPropertyBag_ReadGUID(*(IPropertyBag **)cbData, L"DefaultView", (GUID *)this + 5);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)cbData + 16LL))(*(_QWORD *)cbData);
        }
        RegCloseKey(v28);
      }
      TopViews = CFolderTypeDescription::_LoadTopViews(this, a2, a3);
      v11 = propBag;
      v6 = TopViews;
      *((_BYTE *)this + 1192) = TopViews >= 0;
      ((void (__fastcall *)(IPropertyBag *))v11->lpVtbl->Release)(v11);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180295e24  mov     [rsp-8+arg_10], rbx
0x180295e29  mov     [rsp-8+arg_18], rsi
0x180295e2e  push    rbp
0x180295e2f  push    rdi
0x180295e30  push    r12
0x180295e32  push    r14
0x180295e34  push    r15
0x180295e36  lea     rbp, [rsp-460h]
0x180295e3e  sub     rsp, 560h
0x180295e45  mov     rax, cs:__security_cookie
0x180295e4c  xor     rax, rsp
0x180295e4f  mov     [rbp+480h+var_30], rax
0x180295e56  mov     r15d, r8d
0x180295e59  lea     rax, [rsp+580h+hKey]
0x180295e5e  mov     r14, rdx
0x180295e61  mov     [rsp+580h+phkResult], rax; phkResult
0x180295e66  mov     rbx, rcx
0x180295e69  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180295e70  xor     r12d, r12d
0x180295e73  xor     r8d, r8d; ulOptions
0x180295e76  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180295e7d  mov     [rsp+580h+hKey], r12
0x180295e82  mov     r9d, 20019h; samDesired
0x180295e88  call    cs:__imp_RegOpenKeyExW
0x180295e8f  nop     dword ptr [rax+rax+00h]
0x180295e94  test    eax, eax
0x180295e96  jz      short loc_180295ECB
0x180295e98  mov     edi, 80004005h
0x180295e9d  mov     eax, edi
0x180295e9f  mov     rcx, [rbp+480h+var_30]
0x180295ea6  xor     rcx, rsp; StackCookie
0x180295ea9  call    __security_check_cookie
0x180295eae  lea     r11, [rsp+580h+var_20]
0x180295eb6  mov     rbx, [r11+40h]
0x180295eba  mov     rsi, [r11+48h]
0x180295ebe  mov     rsp, r11
0x180295ec1  pop     r15
0x180295ec3  pop     r14
0x180295ec5  pop     r12
0x180295ec7  pop     rdi
0x180295ec8  pop     rbp
0x180295ec9  retn
0x180295ecb  mov     rcx, [rsp+580h+hKey]
0x180295ed0  lea     rax, [rsp+580h+propBag]
0x180295ed5  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x180295edc  mov     [rsp+580h+phkResult], rax
0x180295ee1  xor     r8d, r8d
0x180295ee4  mov     [rsp+580h+propBag], r12
0x180295ee9  mov     rdx, r14
0x180295eec  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x180295ef3  nop     dword ptr [rax+rax+00h]
0x180295ef8  mov     edi, eax
0x180295efa  test    eax, eax
0x180295efc  js      loc_1802961D9
0x180295f02  mov     rcx, [rsp+580h+propBag]; propBag
0x180295f07  lea     r8, [rbp+480h+value]; value
0x180295f0b  mov     r9d, 27h ; '''; characterCount
0x180295f11  lea     rdx, aParent_0; "Parent"
0x180295f18  call    cs:__imp_PSPropertyBag_ReadStr
0x180295f1f  nop     dword ptr [rax+rax+00h]
0x180295f24  test    eax, eax
0x180295f26  js      short loc_180295F76
0x180295f28  test    r15d, r15d
0x180295f2b  jnz     short loc_180295F4C
0x180295f2d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180295f34  lea     rdx, [rbx+30h]
0x180295f38  lea     rcx, [rbp+480h+value]
0x180295f3c  movdqu  xmmword ptr [rdx], xmm0
0x180295f40  call    cs:__imp_GUIDFromStringW
0x180295f47  nop     dword ptr [rax+rax+00h]
0x180295f4c  mov     r8d, 1; int
0x180295f52  lea     rdx, [rbp+480h+value]; unsigned __int16 *
0x180295f56  mov     rcx, rbx; this
0x180295f59  call    ?_LoadFolderTypeInfo@CFolderTypeDescription@@AEAAJPEBGH@Z; CFolderTypeDescription::_LoadFolderTypeInfo(ushort const *,int)
0x180295f5e  mov     rcx, [rbx+48h]; pv
0x180295f62  mov     [rbx+40h], r12d
0x180295f66  call    cs:__imp_CoTaskMemFree
0x180295f6d  nop     dword ptr [rax+rax+00h]
0x180295f72  mov     [rbx+48h], r12
0x180295f76  mov     rcx, [rsp+580h+propBag]; propBag
0x180295f7b  lea     r8, [rbx+60h]; value
0x180295f7f  mov     esi, 104h
0x180295f84  mov     [r8], r12w
0x180295f88  mov     r9d, esi; characterCount
0x180295f8b  lea     rdx, aCanonicalname; "CanonicalName"
0x180295f92  call    cs:__imp_PSPropertyBag_ReadStr
0x180295f99  nop     dword ptr [rax+rax+00h]
0x180295f9e  mov     rcx, [rsp+580h+propBag]; propBag
0x180295fa3  lea     r8, [rbx+268h]; value
0x180295faa  lea     rdx, aPerceivedtype; "PerceivedType"
0x180295fb1  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180295fb8  nop     dword ptr [rax+rax+00h]
0x180295fbd  mov     rcx, [rsp+580h+propBag]; propBag
0x180295fc2  lea     r8, [rbx+26Ch]; value
0x180295fc9  mov     r9d, esi; characterCount
0x180295fcc  lea     rdx, aTheme; "Theme"
0x180295fd3  call    cs:__imp_PSPropertyBag_ReadStr
0x180295fda  nop     dword ptr [rax+rax+00h]
0x180295fdf  mov     rcx, [rsp+580h+propBag]; propBag
0x180295fe4  lea     r8, [rbx+474h]; value
0x180295feb  lea     rdx, aLayouttype; "LayoutType"
0x180295ff2  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180295ff9  nop     dword ptr [rax+rax+00h]
0x180295ffe  mov     rcx, [rsp+580h+propBag]; propBag
0x180296003  lea     r8, [rbx+490h]; value
0x18029600a  lea     rdx, aTopviewpersist; "TopViewPersistence"
0x180296011  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180296018  nop     dword ptr [rax+rax+00h]
0x18029601d  mov     rcx, [rsp+580h+propBag]; propBag
0x180296022  lea     r8, [rbx+494h]; value
0x180296029  lea     rdx, aViewsettingspe; "ViewSettingsPersistence"
0x180296030  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180296037  nop     dword ptr [rax+rax+00h]
0x18029603c  mov     rcx, [rsp+580h+propBag]; propBag
0x180296041  lea     r8, [rbx+498h]; value
0x180296048  lea     rdx, aMode_0; "Mode"
0x18029604f  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180296056  nop     dword ptr [rax+rax+00h]
0x18029605b  mov     rcx, [rsp+580h+propBag]; propBag
0x180296060  lea     r8, [rsp+580h+var_528]; value
0x180296065  lea     rdx, aHelptopic; "HelpTopic"
0x18029606c  mov     [rsp+580h+var_528], r12
0x180296071  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x180296078  nop     dword ptr [rax+rax+00h]
0x18029607d  test    eax, eax
0x18029607f  jns     loc_180296370
0x180296085  mov     rcx, [rsp+580h+propBag]; propBag
0x18029608a  lea     r8, [rsp+580h+var_520]; value
0x18029608f  lea     rdx, aClass; "Class"
0x180296096  mov     [rsp+580h+var_520], r12
0x18029609b  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1802960a2  nop     dword ptr [rax+rax+00h]
0x1802960a7  test    eax, eax
0x1802960a9  jns     loc_180296342
0x1802960af  mov     rcx, [rsp+580h+propBag]; propBag
0x1802960b4  lea     r8, [rsp+580h+var_518]; value
0x1802960b9  lea     rdx, aMostrelevant; "MostRelevant"
0x1802960c0  mov     [rsp+580h+var_518], r12
0x1802960c5  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1802960cc  nop     dword ptr [rax+rax+00h]
0x1802960d1  test    eax, eax
0x1802960d3  js      short loc_1802960F4
0x1802960d5  mov     rcx, [rbx+488h]; pv
0x1802960dc  call    cs:__imp_CoTaskMemFree
0x1802960e3  nop     dword ptr [rax+rax+00h]
0x1802960e8  mov     rax, [rsp+580h+var_518]
0x1802960ed  mov     [rbx+488h], rax
0x1802960f4  xor     edx, edx; Val
0x1802960f6  mov     [rbp+480h+SubKey], r12w
0x1802960fb  mov     r8d, 206h; Size
0x180296101  lea     rcx, [rbp+480h+var_44E]; void *
0x180296105  call    memset_0
0x18029610a  mov     r9, r14
0x18029610d  lea     r8, aSoftwareMicros_94; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180296114  mov     rdx, rsi; unsigned __int64
0x180296117  lea     rcx, [rbp+480h+SubKey]; unsigned __int16 *
0x18029611b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180296120  lea     rax, [rsp+580h+var_538]
0x180296125  mov     [rsp+580h+var_538], r12
0x18029612a  mov     r9d, 20019h; samDesired
0x180296130  mov     [rsp+580h+phkResult], rax; phkResult
0x180296135  xor     r8d, r8d; ulOptions
0x180296138  lea     rdx, [rbp+480h+SubKey]; lpSubKey
0x18029613c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180296143  call    cs:__imp_RegOpenKeyExW
0x18029614a  nop     dword ptr [rax+rax+00h]
0x18029614f  test    eax, eax
0x180296151  jz      loc_1802961EF
0x180296157  mov     rcx, [rsp+580h+propBag]; propBag
0x18029615c  lea     r8, [rbx+50h]; value
0x180296160  lea     rdx, aDefaultview; "DefaultView"
0x180296167  call    cs:__imp_PSPropertyBag_ReadGUID
0x18029616e  nop     dword ptr [rax+rax+00h]
0x180296173  lea     rax, [rsp+580h+var_510]
0x180296178  mov     [rsp+580h+var_510], r12
0x18029617d  mov     r9d, 20019h; samDesired
0x180296183  mov     [rsp+580h+phkResult], rax; phkResult
0x180296188  xor     r8d, r8d; ulOptions
0x18029618b  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180296192  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180296199  call    cs:__imp_RegOpenKeyExW
0x1802961a0  nop     dword ptr [rax+rax+00h]
0x1802961a5  test    eax, eax
0x1802961a7  jz      loc_1802962FD
0x1802961ad  mov     r8d, r15d; int
0x1802961b0  mov     rdx, r14; unsigned __int16 *
0x1802961b3  mov     rcx, rbx; this
0x1802961b6  call    ?_LoadTopViews@CFolderTypeDescription@@AEAAJPEBGH@Z; CFolderTypeDescription::_LoadTopViews(ushort const *,int)
0x1802961bb  mov     rcx, [rsp+580h+propBag]
0x1802961c0  mov     edi, eax
0x1802961c2  shr     eax, 1Fh
0x1802961c5  xor     al, 1
0x1802961c7  mov     [rbx+4A8h], al
0x1802961cd  mov     rax, [rcx]
0x1802961d0  mov     rax, [rax+10h]
0x1802961d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802961d9  mov     rcx, [rsp+580h+hKey]; hKey
0x1802961de  call    cs:__imp_RegCloseKey
0x1802961e5  nop     dword ptr [rax+rax+00h]
0x1802961ea  jmp     loc_180295E9D
0x1802961ef  mov     [rbx+40h], r12d
0x1802961f3  mov     edi, r12d
0x1802961f6  mov     [rsp+580h+Type], r12d
0x1802961fb  xor     edx, edx
0x1802961fd  jmp     short loc_180296206
0x1802961ff  inc     dword ptr [rbx+40h]
0x180296202  inc     edi
0x180296204  mov     edx, edi; dwIndex
0x180296206  mov     rcx, [rsp+580h+var_538]; hKey
0x18029620b  lea     rax, [rsp+580h+Type]
0x180296210  mov     [rsp+580h+lpcbData], r12; lpcbData
0x180296215  lea     r9, [rsp+580h+cchValueName]; lpcchValueName
0x18029621a  mov     [rsp+580h+lpData], r12; lpData
0x18029621f  lea     r8, [rbp+480h+ValueName]; lpValueName
0x180296226  mov     [rsp+580h+lpType], rax; lpType
0x18029622b  mov     [rsp+580h+phkResult], r12; lpReserved
0x180296230  mov     [rsp+580h+cchValueName], esi
0x180296234  call    cs:__imp_RegEnumValueW
0x18029623b  nop     dword ptr [rax+rax+00h]
0x180296240  test    eax, eax
0x180296242  jz      short loc_1802961FF
0x180296244  mov     eax, [rbx+40h]
0x180296247  test    eax, eax
0x180296249  jz      loc_1802962F7
0x18029624f  mov     ecx, eax; void *
0x180296251  mov     qword ptr [rbp+480h+cbData], r12
0x180296255  mov     eax, 218h
0x18029625a  lea     rsi, [rbx+48h]
0x18029625e  mul     rcx
0x180296261  mov     [rsi], r12
0x180296264  test    rdx, rdx
0x180296267  jnz     loc_180296366
0x18029626d  mov     r9, rsi; void **
0x180296270  mov     r8, rax; unsigned __int64
0x180296273  mov     edx, 1; unsigned int
0x180296278  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18029627d  test    eax, eax
0x18029627f  js      short loc_1802962F7
0x180296281  mov     edi, r12d
0x180296284  mov     [rsp+580h+cchValueName], 104h
0x18029628c  mov     [rbp+480h+cbData], 4Eh ; 'N'
0x180296293  cmp     [rbx+40h], r12d
0x180296297  jbe     short loc_1802962E1
0x180296299  mov     rcx, [rsp+580h+var_538]; hKey
0x18029629e  lea     rax, [rbp+480h+cbData]
0x1802962a2  mov     [rsp+580h+lpcbData], rax; lpcbData
0x1802962a7  lea     r9, [rsp+580h+cchValueName]; lpcchValueName
0x1802962ac  lea     rax, [rbp+480h+Data]
0x1802962b0  mov     edx, edi; dwIndex
0x1802962b2  mov     [rsp+580h+lpData], rax; lpData
0x1802962b7  lea     r8, [rbp+480h+ValueName]; lpValueName
0x1802962be  lea     rax, [rsp+580h+Type]
0x1802962c3  mov     [rsp+580h+lpType], rax; lpType
0x1802962c8  mov     [rsp+580h+phkResult], r12; lpReserved
0x1802962cd  call    cs:__imp_RegEnumValueW
0x1802962d4  nop     dword ptr [rax+rax+00h]
0x1802962d9  test    eax, eax
0x1802962db  jz      loc_1806781B0
0x1802962e1  mov     rcx, [rsp+580h+var_538]; hKey
0x1802962e6  call    cs:__imp_RegCloseKey
0x1802962ed  nop     dword ptr [rax+rax+00h]
0x1802962f2  jmp     loc_180296157
0x1802962f7  mov     [rbx+40h], r12d
0x1802962fb  jmp     short loc_1802962E1
0x1802962fd  mov     rcx, [rsp+580h+hKey]
0x180296302  lea     rax, [rbp+480h+cbData]
0x180296306  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18029630d  mov     [rsp+580h+phkResult], rax
0x180296312  xor     r8d, r8d
0x180296315  mov     qword ptr [rbp+480h+cbData], r12
0x180296319  mov     rdx, r14
0x18029631c  call    cs:__imp_SHCreatePropertyBagOnRegKey
0x180296323  nop     dword ptr [rax+rax+00h]
0x180296328  test    eax, eax
0x18029632a  jns     short loc_180296394
0x18029632c  mov     rcx, [rsp+580h+var_510]; hKey
0x180296331  call    cs:__imp_RegCloseKey
0x180296338  nop     dword ptr [rax+rax+00h]
0x18029633d  jmp     loc_1802961AD
0x180296342  mov     rcx, [rbx+480h]; pv
0x180296349  call    cs:__imp_CoTaskMemFree
0x180296350  nop     dword ptr [rax+rax+00h]
0x180296355  mov     rax, [rsp+580h+var_520]
0x18029635a  mov     [rbx+480h], rax
0x180296361  jmp     loc_1802960AF
0x180296366  mov     eax, 80070216h
0x18029636b  jmp     loc_18029627D
0x180296370  mov     rcx, [rbx+478h]; pv
0x180296377  call    cs:__imp_CoTaskMemFree
0x18029637e  nop     dword ptr [rax+rax+00h]
0x180296383  mov     rax, [rsp+580h+var_528]
0x180296388  mov     [rbx+478h], rax
0x18029638f  jmp     loc_180296085
0x180296394  mov     rcx, qword ptr [rbp+480h+cbData]; propBag
0x180296398  lea     r8, [rbx+50h]; value
0x18029639c  lea     rdx, aDefaultview; "DefaultView"
0x1802963a3  call    cs:__imp_PSPropertyBag_ReadGUID
0x1802963aa  nop     dword ptr [rax+rax+00h]
0x1802963af  mov     rcx, qword ptr [rbp+480h+cbData]
0x1802963b3  mov     rax, [rcx]
  ... truncated ...
```
