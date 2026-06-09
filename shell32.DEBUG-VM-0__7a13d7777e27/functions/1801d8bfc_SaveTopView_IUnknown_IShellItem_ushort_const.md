# SaveTopView(IUnknown *,IShellItem *,ushort const *)

- ea: `0x1801d8bfc`
- end: `0x1801d9033`
- name: `?SaveTopView@@YAJPEAUIUnknown@@PEAUIShellItem@@PEBG@Z`
- size: `1079`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801d4a14`

## callees

- `0x18010fc64`
- `0x1801d8bfc`
- `0x180233280`
- `0x1802b3408`
- `0x1802f0ab0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801d8f37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801d8f4a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801d8f37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801d8f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8faa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d8faa`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801d8e41`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801d8e52`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801d8e41`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801d8e52`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1801d8dda`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1801d8dda`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801d8e68`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801d8e88`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801d8e68`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801d8e88`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801d8e14`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801d8e2b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801d8e14`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801d8e2b`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801d8ef9`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801d8ef9`
- `Windows.Storage!ILFree` at `0x1801d8fc6`
- `Windows.Storage!ILFree` at `0x1801d8fc6`
- `Windows.Storage!SHGetIDListFromObject` at `0x1801d8da1`
- `Windows.Storage!SHGetIDListFromObject` at `0x1801d8da1`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801d8f68`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801d8f7b`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801d8f68`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801d8f7b`
- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1801d8cc1`
- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1801d8cc1`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x1801d8eb1`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x1801d8eb1`

## pseudocode

```c
__int64 __fastcall SaveTopView(struct IUnknown *a1, struct IShellItem *a2, const unsigned __int16 *a3)
{
  HRESULT v6; // ebx
  DWORD v7; // edi
  IPropertyBag *v8; // rcx
  HRESULT v9; // eax
  PWSTR v10; // rcx
  IPropertyBag *propBag; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR value; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  struct ITopViewAwareItem *v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp-A0h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-98h] BYREF
  DWORD v20; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+74h] [rbp-8Ch] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  CLSID v23; // [rsp+80h] [rbp-80h] BYREF
  CLSID v24; // [rsp+90h] [rbp-70h] BYREF
  CLSID pclsid; // [rsp+A0h] [rbp-60h] BYREF
  CLSID v26; // [rsp+B0h] [rbp-50h] BYREF
  CLSID v27; // [rsp+C0h] [rbp-40h] BYREF
  CLSID v28; // [rsp+D0h] [rbp-30h]
  WCHAR pszStr2[40]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v30[40]; // [rsp+130h] [rbp+30h] BYREF

  v16 = 0;
  if ( !(unsigned int)IsFilteredSet(a2) )
  {
    v6 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, struct ITopViewAwareItem **))a2->lpVtbl->BindToHandler)(
           a2,
           0,
           &BHID_SFViewObject,
           &GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb,
           &v16);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v23 = 0;
    v24 = 0;
    v6 = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, CLSID *))(*(_QWORD *)v16 + 24LL))(v16, &v23);
    if ( v6 < 0
      || (v15 = 0, v6 = SHGetFolderTypeDescription(&v23, &GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80, &v15), v6 < 0) )
    {
LABEL_38:
      (*(void (__fastcall **)(struct ITopViewAwareItem *))(*(_QWORD *)v16 + 16LL))(v16);
      return (unsigned int)v6;
    }
    v7 = 0;
    v21 = 0;
    v27 = v23;
    v20 = 0;
    v28 = v24;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 104LL))(v15, &v21) >= 0 && v21 == 1 )
    {
      SaveTopViewSettings(a1);
      v7 = v20;
    }
    v22 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 96LL))(v15, &v22) >= 0 && v22 == 1 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, CLSID *))(*(_QWORD *)v15 + 168LL))(v15, &v24);
      goto LABEL_36;
    }
    punk = 0;
    v6 = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, IUnknown **))(*(_QWORD *)v16 + 48LL))(v16, &punk);
    if ( v6 < 0 )
    {
LABEL_36:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v7 )
        ClearViewSettingsForTopView(v16, a3, (const struct TOPVIEWKEY *)&v27);
      goto LABEL_38;
    }
    ppidl = 0;
    v6 = SHGetIDListFromObject(punk, &ppidl);
    if ( v6 < 0 )
    {
LABEL_35:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      goto LABEL_36;
    }
    v8 = 0;
    propBag = 0;
    if ( a3 )
    {
      v9 = SHGetViewStatePropertyBag(ppidl, a3, 5u, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&propBag);
      v8 = propBag;
      v6 = v9;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( v6 < 0 )
    {
LABEL_34:
      ILFree(ppidl);
      goto LABEL_35;
    }
    value = 0;
    v14 = 0;
    PSPropertyBag_ReadStrAlloc(v8, L"TV_FolderType", &value);
    PSPropertyBag_ReadStrAlloc(propBag, L"TV_TopViewID", &v14);
    SHStringFromGUIDW(&v23, pszStr2, 39);
    SHStringFromGUIDW(&v24, v30, 39);
    v6 = PSPropertyBag_WriteStr(propBag, L"TV_FolderType", pszStr2);
    if ( v6 >= 0 )
    {
      v6 = PSPropertyBag_WriteStr(propBag, L"TV_TopViewID", v30);
      if ( v6 >= 0 )
      {
        v17 = 0;
        v6 = SHGetTopViewDescription(&v23, &GUID_fe812157_522c_46cb_8d53_6efe3dce2c46, &v17);
        if ( v6 >= 0 )
        {
          v20 = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v17 + 176LL))(v17, &v20);
          if ( v6 >= 0 )
            v6 = PSPropertyBag_WriteDWORD(propBag, L"TV_TopViewVersion", v20);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          if ( v6 >= 0 && v21 == 1 )
          {
            v10 = value;
            if ( !value || !v14 )
              goto LABEL_33;
            if ( StrCmpICW(value, pszStr2) || StrCmpICW(v14, v30) )
            {
              pclsid = 0;
              v26 = 0;
              if ( SHCLSIDFromString(value, &pclsid) >= 0 && SHCLSIDFromString(v14, &v26) >= 0 )
              {
                v7 = 1;
                v27 = pclsid;
                v28 = v26;
              }
            }
          }
        }
      }
    }
    v10 = value;
LABEL_33:
    CoTaskMemFree(v10);
    CoTaskMemFree(v14);
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
    goto LABEL_34;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1801d8bfc  push    rbp
0x1801d8bfe  push    rbx
0x1801d8bff  push    rsi
0x1801d8c00  push    rdi
0x1801d8c01  push    r14
0x1801d8c03  lea     rbp, [rsp-90h]
0x1801d8c0b  sub     rsp, 190h
0x1801d8c12  mov     rax, cs:__security_cookie
0x1801d8c19  xor     rax, rsp
0x1801d8c1c  mov     [rbp+0B0h+var_30], rax
0x1801d8c23  mov     r14, rcx
0x1801d8c26  mov     [rsp+1B0h+var_160], 0
0x1801d8c2f  mov     rcx, rdx; struct IShellItem *
0x1801d8c32  mov     rsi, r8
0x1801d8c35  mov     rbx, rdx
0x1801d8c38  call    ?IsFilteredSet@@YAHPEAUIShellItem@@@Z; IsFilteredSet(IShellItem *)
0x1801d8c3d  test    eax, eax
0x1801d8c3f  jz      short loc_1801D8C4B
0x1801d8c41  mov     ebx, 80004005h
0x1801d8c46  jmp     loc_1801D9014
0x1801d8c4b  mov     rax, [rbx]
0x1801d8c4e  lea     rcx, [rsp+1B0h+var_160]
0x1801d8c53  mov     [rsp+1B0h+ppv], rcx
0x1801d8c58  lea     r9, _GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb
0x1801d8c5f  lea     r8, BHID_SFViewObject
0x1801d8c66  xor     edx, edx
0x1801d8c68  mov     rcx, rbx
0x1801d8c6b  mov     rax, [rax+18h]
0x1801d8c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8c74  mov     ebx, eax
0x1801d8c76  test    eax, eax
0x1801d8c78  js      loc_1801D9014
0x1801d8c7e  mov     rcx, [rsp+1B0h+var_160]
0x1801d8c83  lea     rdx, [rbp+0B0h+var_130]
0x1801d8c87  xorps   xmm0, xmm0
0x1801d8c8a  movups  [rbp+0B0h+var_130], xmm0
0x1801d8c8e  movups  [rbp+0B0h+var_120], xmm0
0x1801d8c92  mov     rax, [rcx]
0x1801d8c95  mov     rax, [rax+18h]
0x1801d8c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8c9e  mov     ebx, eax
0x1801d8ca0  test    eax, eax
0x1801d8ca2  js      loc_1801D9003
0x1801d8ca8  lea     r8, [rsp+1B0h+var_168]
0x1801d8cad  mov     [rsp+1B0h+var_168], 0
0x1801d8cb6  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x1801d8cbd  lea     rcx, [rbp+0B0h+var_130]
0x1801d8cc1  call    cs:__imp_SHGetFolderTypeDescription
0x1801d8cc7  mov     ebx, eax
0x1801d8cc9  test    eax, eax
0x1801d8ccb  js      loc_1801D9003
0x1801d8cd1  movups  xmm0, [rbp+0B0h+var_130]
0x1801d8cd5  mov     rcx, [rsp+1B0h+var_168]
0x1801d8cda  xor     edi, edi
0x1801d8cdc  movups  xmm1, [rbp+0B0h+var_120]
0x1801d8ce0  mov     [rsp+1B0h+var_13C], edi
0x1801d8ce4  lea     rdx, [rsp+1B0h+var_13C]
0x1801d8ce9  movups  [rbp+0B0h+var_F0], xmm0
0x1801d8ced  mov     [rsp+1B0h+var_140], edi
0x1801d8cf1  movups  [rbp+0B0h+var_E0], xmm1
0x1801d8cf5  mov     rax, [rcx]
0x1801d8cf8  mov     rax, [rax+68h]
0x1801d8cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d01  test    eax, eax
0x1801d8d03  js      short loc_1801D8D1D
0x1801d8d05  cmp     [rsp+1B0h+var_13C], 1
0x1801d8d0a  jnz     short loc_1801D8D1D
0x1801d8d0c  lea     rdx, [rsp+1B0h+var_140]
0x1801d8d11  mov     rcx, r14; struct IUnknown *
0x1801d8d14  call    SaveTopViewSettings
0x1801d8d19  mov     edi, [rsp+1B0h+var_140]
0x1801d8d1d  mov     rcx, [rsp+1B0h+var_168]
0x1801d8d22  lea     rdx, [rsp+1B0h+var_138]
0x1801d8d27  mov     [rsp+1B0h+var_138], 0
0x1801d8d2f  mov     rax, [rcx]
0x1801d8d32  mov     rax, [rax+60h]
0x1801d8d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d3b  test    eax, eax
0x1801d8d3d  js      short loc_1801D8D65
0x1801d8d3f  cmp     [rsp+1B0h+var_138], 1
0x1801d8d44  jnz     short loc_1801D8D65
0x1801d8d46  mov     rcx, [rsp+1B0h+var_168]
0x1801d8d4b  lea     rdx, [rbp+0B0h+var_120]
0x1801d8d4f  mov     rax, [rcx]
0x1801d8d52  mov     rax, [rax+0A8h]
0x1801d8d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d5e  mov     ebx, eax
0x1801d8d60  jmp     loc_1801D8FDD
0x1801d8d65  mov     rcx, [rsp+1B0h+var_160]
0x1801d8d6a  lea     rdx, [rsp+1B0h+punk]
0x1801d8d6f  mov     [rsp+1B0h+punk], 0
0x1801d8d78  mov     rax, [rcx]
0x1801d8d7b  mov     rax, [rax+30h]
0x1801d8d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8d84  mov     ebx, eax
0x1801d8d86  test    eax, eax
0x1801d8d88  js      loc_1801D8FDD
0x1801d8d8e  mov     rcx, [rsp+1B0h+punk]; punk
0x1801d8d93  lea     rdx, [rsp+1B0h+ppidl]; ppidl
0x1801d8d98  mov     [rsp+1B0h+ppidl], 0
0x1801d8da1  call    cs:__imp_SHGetIDListFromObject
0x1801d8da7  mov     ebx, eax
0x1801d8da9  test    eax, eax
0x1801d8dab  js      loc_1801D8FCC
0x1801d8db1  xor     ecx, ecx; propBag
0x1801d8db3  mov     [rsp+1B0h+propBag], rcx
0x1801d8db8  test    rsi, rsi
0x1801d8dbb  jz      short loc_1801D8DE9
0x1801d8dbd  lea     rax, [rsp+1B0h+propBag]
0x1801d8dc2  mov     rdx, rsi; pszBagName
0x1801d8dc5  lea     r8d, [rcx+5]; dwFlags
0x1801d8dc9  mov     [rsp+1B0h+ppv], rax; ppv
0x1801d8dce  mov     rcx, [rsp+1B0h+ppidl]; pidl
0x1801d8dd3  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1801d8dda  call    cs:__imp_SHGetViewStatePropertyBag
0x1801d8de0  mov     rcx, [rsp+1B0h+propBag]
0x1801d8de5  mov     ebx, eax
0x1801d8de7  jmp     short loc_1801D8DEE
0x1801d8de9  mov     ebx, 80004005h
0x1801d8dee  test    ebx, ebx
0x1801d8df0  js      loc_1801D8FC1
0x1801d8df6  lea     r8, [rsp+1B0h+value]; value
0x1801d8dfb  mov     [rsp+1B0h+value], 0
0x1801d8e04  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1801d8e0b  mov     [rsp+1B0h+var_170], 0
0x1801d8e14  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801d8e1a  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801d8e1f  lea     r8, [rsp+1B0h+var_170]; value
0x1801d8e24  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1801d8e2b  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801d8e31  mov     ebx, 27h ; '''
0x1801d8e36  lea     rdx, [rbp+0B0h+pszStr2]
0x1801d8e3a  mov     r8d, ebx
0x1801d8e3d  lea     rcx, [rbp+0B0h+var_130]
0x1801d8e41  call    cs:__imp_SHStringFromGUIDW
0x1801d8e47  mov     r8d, ebx
0x1801d8e4a  lea     rdx, [rbp+0B0h+var_80]
0x1801d8e4e  lea     rcx, [rbp+0B0h+var_120]
0x1801d8e52  call    cs:__imp_SHStringFromGUIDW
0x1801d8e58  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801d8e5d  lea     r8, [rbp+0B0h+pszStr2]; value
0x1801d8e61  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1801d8e68  call    cs:__imp_PSPropertyBag_WriteStr
0x1801d8e6e  mov     ebx, eax
0x1801d8e70  test    eax, eax
0x1801d8e72  js      loc_1801D8F9A
0x1801d8e78  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801d8e7d  lea     r8, [rbp+0B0h+var_80]; value
0x1801d8e81  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1801d8e88  call    cs:__imp_PSPropertyBag_WriteStr
0x1801d8e8e  mov     ebx, eax
0x1801d8e90  test    eax, eax
0x1801d8e92  js      loc_1801D8F9A
0x1801d8e98  lea     r8, [rsp+1B0h+var_158]
0x1801d8e9d  mov     [rsp+1B0h+var_158], 0
0x1801d8ea6  lea     rdx, _GUID_fe812157_522c_46cb_8d53_6efe3dce2c46
0x1801d8ead  lea     rcx, [rbp+0B0h+var_130]
0x1801d8eb1  call    cs:__imp_SHGetTopViewDescription
0x1801d8eb7  mov     ebx, eax
0x1801d8eb9  test    eax, eax
0x1801d8ebb  js      loc_1801D8F9A
0x1801d8ec1  mov     rcx, [rsp+1B0h+var_158]
0x1801d8ec6  lea     rdx, [rsp+1B0h+var_140]
0x1801d8ecb  mov     [rsp+1B0h+var_140], 0
0x1801d8ed3  mov     rax, [rcx]
0x1801d8ed6  mov     rax, [rax+0B0h]
0x1801d8edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8ee2  mov     ebx, eax
0x1801d8ee4  test    eax, eax
0x1801d8ee6  js      short loc_1801D8F01
0x1801d8ee8  mov     r8d, [rsp+1B0h+var_140]; value
0x1801d8eed  lea     rdx, aTvTopviewversi; "TV_TopViewVersion"
0x1801d8ef4  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801d8ef9  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801d8eff  mov     ebx, eax
0x1801d8f01  mov     rcx, [rsp+1B0h+var_158]
0x1801d8f06  mov     rax, [rcx]
0x1801d8f09  mov     rax, [rax+10h]
0x1801d8f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8f12  test    ebx, ebx
0x1801d8f14  js      loc_1801D8F9A
0x1801d8f1a  cmp     [rsp+1B0h+var_13C], 1
0x1801d8f1f  jnz     short loc_1801D8F9A
0x1801d8f21  mov     rcx, [rsp+1B0h+value]; pszStr1
0x1801d8f26  test    rcx, rcx
0x1801d8f29  jz      short loc_1801D8F9F
0x1801d8f2b  cmp     [rsp+1B0h+var_170], 0
0x1801d8f31  jz      short loc_1801D8F9F
0x1801d8f33  lea     rdx, [rbp+0B0h+pszStr2]; pszStr2
0x1801d8f37  call    cs:__imp_StrCmpICW
0x1801d8f3d  test    eax, eax
0x1801d8f3f  jnz     short loc_1801D8F54
0x1801d8f41  mov     rcx, [rsp+1B0h+var_170]; pszStr1
0x1801d8f46  lea     rdx, [rbp+0B0h+var_80]; pszStr2
0x1801d8f4a  call    cs:__imp_StrCmpICW
0x1801d8f50  test    eax, eax
0x1801d8f52  jz      short loc_1801D8F9A
0x1801d8f54  mov     rcx, [rsp+1B0h+value]; psz
0x1801d8f59  lea     rdx, [rbp+0B0h+pclsid]; pclsid
0x1801d8f5d  xorps   xmm0, xmm0
0x1801d8f60  movups  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x1801d8f64  movups  xmmword ptr [rbp+0B0h+var_100.Data1], xmm0
0x1801d8f68  call    cs:__imp_SHCLSIDFromString
0x1801d8f6e  test    eax, eax
0x1801d8f70  js      short loc_1801D8F9A
0x1801d8f72  mov     rcx, [rsp+1B0h+var_170]; psz
0x1801d8f77  lea     rdx, [rbp+0B0h+var_100]; pclsid
0x1801d8f7b  call    cs:__imp_SHCLSIDFromString
0x1801d8f81  test    eax, eax
0x1801d8f83  js      short loc_1801D8F9A
0x1801d8f85  movups  xmm0, xmmword ptr [rbp+0B0h+pclsid.Data1]
0x1801d8f89  mov     edi, 1
0x1801d8f8e  movups  xmm1, xmmword ptr [rbp+0B0h+var_100.Data1]
0x1801d8f92  movups  [rbp+0B0h+var_F0], xmm0
0x1801d8f96  movups  [rbp+0B0h+var_E0], xmm1
0x1801d8f9a  mov     rcx, [rsp+1B0h+value]; pv
0x1801d8f9f  call    cs:__imp_CoTaskMemFree
0x1801d8fa5  mov     rcx, [rsp+1B0h+var_170]; pv
0x1801d8faa  call    cs:__imp_CoTaskMemFree
0x1801d8fb0  mov     rcx, [rsp+1B0h+propBag]
0x1801d8fb5  mov     rax, [rcx]
0x1801d8fb8  mov     rax, [rax+10h]
0x1801d8fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8fc1  mov     rcx, [rsp+1B0h+ppidl]; pidl
0x1801d8fc6  call    cs:__imp_ILFree
0x1801d8fcc  mov     rcx, [rsp+1B0h+punk]
0x1801d8fd1  mov     rax, [rcx]
0x1801d8fd4  mov     rax, [rax+10h]
0x1801d8fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8fdd  mov     rcx, [rsp+1B0h+var_168]
0x1801d8fe2  mov     rax, [rcx]
0x1801d8fe5  mov     rax, [rax+10h]
0x1801d8fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8fee  test    edi, edi
0x1801d8ff0  jz      short loc_1801D9003
0x1801d8ff2  mov     rcx, [rsp+1B0h+var_160]; struct ITopViewAwareItem *
0x1801d8ff7  lea     r8, [rbp+0B0h+var_F0]; struct TOPVIEWKEY *
0x1801d8ffb  mov     rdx, rsi; unsigned __int16 *
0x1801d8ffe  call    ?ClearViewSettingsForTopView@@YAXPEAUITopViewAwareItem@@PEBGAEBUTOPVIEWKEY@@@Z; ClearViewSettingsForTopView(ITopViewAwareItem *,ushort const *,TOPVIEWKEY const &)
0x1801d9003  mov     rcx, [rsp+1B0h+var_160]
0x1801d9008  mov     rax, [rcx]
0x1801d900b  mov     rax, [rax+10h]
0x1801d900f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d9014  mov     eax, ebx
0x1801d9016  mov     rcx, [rbp+0B0h+var_30]
0x1801d901d  xor     rcx, rsp; StackCookie
0x1801d9020  call    __security_check_cookie
0x1801d9025  add     rsp, 190h
0x1801d902c  pop     r14
0x1801d902e  pop     rdi
0x1801d902f  pop     rsi
0x1801d9030  pop     rbx
0x1801d9031  pop     rbp
0x1801d9032  retn
```
