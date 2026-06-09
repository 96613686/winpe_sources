# SaveTopView(IUnknown *,IShellItem *,ushort const *)

- ea: `0x1801f02a8`
- end: `0x1801f0758`
- name: `?SaveTopView@@YAJPEAUIUnknown@@PEAUIShellItem@@PEBG@Z`
- size: `1200`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801eba70`

## callees

- `0x180176d54`
- `0x1801f02a8`
- `0x180249490`
- `0x1802cf154`
- `0x180310170`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801f0631`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801f064a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801f0631`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801f064a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f06b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f06c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f06b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f06c2`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801f050b`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801f0522`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801f050b`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x1801f0522`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1801f0492`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x1801f0492`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801f053e`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801f0564`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801f053e`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x1801f0564`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801f04d2`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801f04ef`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801f04d2`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1801f04ef`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801f05e1`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1801f05e1`
- `Windows.Storage!ILFree` at `0x1801f06e4`
- `Windows.Storage!ILFree` at `0x1801f06e4`
- `Windows.Storage!SHGetIDListFromObject` at `0x1801f0453`
- `Windows.Storage!SHGetIDListFromObject` at `0x1801f0453`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801f066e`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801f0687`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801f066e`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x1801f0687`
- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1801f036d`
- `Windows.Storage!__imp_SHGetFolderTypeDescription` at `0x1801f036d`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x1801f0593`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x1801f0593`

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
0x1801f02a8  push    rbp
0x1801f02aa  push    rbx
0x1801f02ab  push    rsi
0x1801f02ac  push    rdi
0x1801f02ad  push    r14
0x1801f02af  lea     rbp, [rsp-90h]
0x1801f02b7  sub     rsp, 190h
0x1801f02be  mov     rax, cs:__security_cookie
0x1801f02c5  xor     rax, rsp
0x1801f02c8  mov     [rbp+0B0h+var_30], rax
0x1801f02cf  mov     r14, rcx
0x1801f02d2  mov     [rsp+1B0h+var_160], 0
0x1801f02db  mov     rcx, rdx; struct IShellItem *
0x1801f02de  mov     rsi, r8
0x1801f02e1  mov     rbx, rdx
0x1801f02e4  call    ?IsFilteredSet@@YAHPEAUIShellItem@@@Z; IsFilteredSet(IShellItem *)
0x1801f02e9  test    eax, eax
0x1801f02eb  jz      short loc_1801F02F7
0x1801f02ed  mov     ebx, 80004005h
0x1801f02f2  jmp     loc_1801F0738
0x1801f02f7  mov     rax, [rbx]
0x1801f02fa  lea     rcx, [rsp+1B0h+var_160]
0x1801f02ff  mov     [rsp+1B0h+ppv], rcx
0x1801f0304  lea     r9, _GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb
0x1801f030b  lea     r8, BHID_SFViewObject
0x1801f0312  xor     edx, edx
0x1801f0314  mov     rcx, rbx
0x1801f0317  mov     rax, [rax+18h]
0x1801f031b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0320  mov     ebx, eax
0x1801f0322  test    eax, eax
0x1801f0324  js      loc_1801F0738
0x1801f032a  mov     rcx, [rsp+1B0h+var_160]
0x1801f032f  lea     rdx, [rbp+0B0h+var_130]
0x1801f0333  xorps   xmm0, xmm0
0x1801f0336  movups  [rbp+0B0h+var_130], xmm0
0x1801f033a  movups  [rbp+0B0h+var_120], xmm0
0x1801f033e  mov     rax, [rcx]
0x1801f0341  mov     rax, [rax+18h]
0x1801f0345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f034a  mov     ebx, eax
0x1801f034c  test    eax, eax
0x1801f034e  js      loc_1801F0727
0x1801f0354  lea     r8, [rsp+1B0h+var_168]
0x1801f0359  mov     [rsp+1B0h+var_168], 0
0x1801f0362  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x1801f0369  lea     rcx, [rbp+0B0h+var_130]
0x1801f036d  call    cs:__imp_SHGetFolderTypeDescription
0x1801f0374  nop     dword ptr [rax+rax+00h]
0x1801f0379  mov     ebx, eax
0x1801f037b  test    eax, eax
0x1801f037d  js      loc_1801F0727
0x1801f0383  movups  xmm0, [rbp+0B0h+var_130]
0x1801f0387  mov     rcx, [rsp+1B0h+var_168]
0x1801f038c  xor     edi, edi
0x1801f038e  movups  xmm1, [rbp+0B0h+var_120]
0x1801f0392  mov     [rsp+1B0h+var_13C], edi
0x1801f0396  lea     rdx, [rsp+1B0h+var_13C]
0x1801f039b  movups  [rbp+0B0h+var_F0], xmm0
0x1801f039f  mov     [rsp+1B0h+var_140], edi
0x1801f03a3  movups  [rbp+0B0h+var_E0], xmm1
0x1801f03a7  mov     rax, [rcx]
0x1801f03aa  mov     rax, [rax+68h]
0x1801f03ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f03b3  test    eax, eax
0x1801f03b5  js      short loc_1801F03CF
0x1801f03b7  cmp     [rsp+1B0h+var_13C], 1
0x1801f03bc  jnz     short loc_1801F03CF
0x1801f03be  lea     rdx, [rsp+1B0h+var_140]
0x1801f03c3  mov     rcx, r14; struct IUnknown *
0x1801f03c6  call    SaveTopViewSettings
0x1801f03cb  mov     edi, [rsp+1B0h+var_140]
0x1801f03cf  mov     rcx, [rsp+1B0h+var_168]
0x1801f03d4  lea     rdx, [rsp+1B0h+var_138]
0x1801f03d9  mov     [rsp+1B0h+var_138], 0
0x1801f03e1  mov     rax, [rcx]
0x1801f03e4  mov     rax, [rax+60h]
0x1801f03e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f03ed  test    eax, eax
0x1801f03ef  js      short loc_1801F0417
0x1801f03f1  cmp     [rsp+1B0h+var_138], 1
0x1801f03f6  jnz     short loc_1801F0417
0x1801f03f8  mov     rcx, [rsp+1B0h+var_168]
0x1801f03fd  lea     rdx, [rbp+0B0h+var_120]
0x1801f0401  mov     rax, [rcx]
0x1801f0404  mov     rax, [rax+0A8h]
0x1801f040b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0410  mov     ebx, eax
0x1801f0412  jmp     loc_1801F0701
0x1801f0417  mov     rcx, [rsp+1B0h+var_160]
0x1801f041c  lea     rdx, [rsp+1B0h+punk]
0x1801f0421  mov     [rsp+1B0h+punk], 0
0x1801f042a  mov     rax, [rcx]
0x1801f042d  mov     rax, [rax+30h]
0x1801f0431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0436  mov     ebx, eax
0x1801f0438  test    eax, eax
0x1801f043a  js      loc_1801F0701
0x1801f0440  mov     rcx, [rsp+1B0h+punk]; punk
0x1801f0445  lea     rdx, [rsp+1B0h+ppidl]; ppidl
0x1801f044a  mov     [rsp+1B0h+ppidl], 0
0x1801f0453  call    cs:__imp_SHGetIDListFromObject
0x1801f045a  nop     dword ptr [rax+rax+00h]
0x1801f045f  mov     ebx, eax
0x1801f0461  test    eax, eax
0x1801f0463  js      loc_1801F06F0
0x1801f0469  xor     ecx, ecx; propBag
0x1801f046b  mov     [rsp+1B0h+propBag], rcx
0x1801f0470  test    rsi, rsi
0x1801f0473  jz      short loc_1801F04A7
0x1801f0475  lea     rax, [rsp+1B0h+propBag]
0x1801f047a  mov     rdx, rsi; pszBagName
0x1801f047d  lea     r8d, [rcx+5]; dwFlags
0x1801f0481  mov     [rsp+1B0h+ppv], rax; ppv
0x1801f0486  mov     rcx, [rsp+1B0h+ppidl]; pidl
0x1801f048b  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1801f0492  call    cs:__imp_SHGetViewStatePropertyBag
0x1801f0499  nop     dword ptr [rax+rax+00h]
0x1801f049e  mov     rcx, [rsp+1B0h+propBag]
0x1801f04a3  mov     ebx, eax
0x1801f04a5  jmp     short loc_1801F04AC
0x1801f04a7  mov     ebx, 80004005h
0x1801f04ac  test    ebx, ebx
0x1801f04ae  js      loc_1801F06DF
0x1801f04b4  lea     r8, [rsp+1B0h+value]; value
0x1801f04b9  mov     [rsp+1B0h+value], 0
0x1801f04c2  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1801f04c9  mov     [rsp+1B0h+var_170], 0
0x1801f04d2  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801f04d9  nop     dword ptr [rax+rax+00h]
0x1801f04de  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801f04e3  lea     r8, [rsp+1B0h+var_170]; value
0x1801f04e8  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1801f04ef  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1801f04f6  nop     dword ptr [rax+rax+00h]
0x1801f04fb  mov     ebx, 27h ; '''
0x1801f0500  lea     rdx, [rbp+0B0h+pszStr2]
0x1801f0504  mov     r8d, ebx
0x1801f0507  lea     rcx, [rbp+0B0h+var_130]
0x1801f050b  call    cs:__imp_SHStringFromGUIDW
0x1801f0512  nop     dword ptr [rax+rax+00h]
0x1801f0517  mov     r8d, ebx
0x1801f051a  lea     rdx, [rbp+0B0h+var_80]
0x1801f051e  lea     rcx, [rbp+0B0h+var_120]
0x1801f0522  call    cs:__imp_SHStringFromGUIDW
0x1801f0529  nop     dword ptr [rax+rax+00h]
0x1801f052e  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801f0533  lea     r8, [rbp+0B0h+pszStr2]; value
0x1801f0537  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1801f053e  call    cs:__imp_PSPropertyBag_WriteStr
0x1801f0545  nop     dword ptr [rax+rax+00h]
0x1801f054a  mov     ebx, eax
0x1801f054c  test    eax, eax
0x1801f054e  js      loc_1801F06AC
0x1801f0554  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801f0559  lea     r8, [rbp+0B0h+var_80]; value
0x1801f055d  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1801f0564  call    cs:__imp_PSPropertyBag_WriteStr
0x1801f056b  nop     dword ptr [rax+rax+00h]
0x1801f0570  mov     ebx, eax
0x1801f0572  test    eax, eax
0x1801f0574  js      loc_1801F06AC
0x1801f057a  lea     r8, [rsp+1B0h+var_158]
0x1801f057f  mov     [rsp+1B0h+var_158], 0
0x1801f0588  lea     rdx, _GUID_fe812157_522c_46cb_8d53_6efe3dce2c46
0x1801f058f  lea     rcx, [rbp+0B0h+var_130]
0x1801f0593  call    cs:__imp_SHGetTopViewDescription
0x1801f059a  nop     dword ptr [rax+rax+00h]
0x1801f059f  mov     ebx, eax
0x1801f05a1  test    eax, eax
0x1801f05a3  js      loc_1801F06AC
0x1801f05a9  mov     rcx, [rsp+1B0h+var_158]
0x1801f05ae  lea     rdx, [rsp+1B0h+var_140]
0x1801f05b3  mov     [rsp+1B0h+var_140], 0
0x1801f05bb  mov     rax, [rcx]
0x1801f05be  mov     rax, [rax+0B0h]
0x1801f05c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f05ca  mov     ebx, eax
0x1801f05cc  test    eax, eax
0x1801f05ce  js      short loc_1801F05EF
0x1801f05d0  mov     r8d, [rsp+1B0h+var_140]; value
0x1801f05d5  lea     rdx, aTvTopviewversi; "TV_TopViewVersion"
0x1801f05dc  mov     rcx, [rsp+1B0h+propBag]; propBag
0x1801f05e1  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1801f05e8  nop     dword ptr [rax+rax+00h]
0x1801f05ed  mov     ebx, eax
0x1801f05ef  mov     rcx, [rsp+1B0h+var_158]
0x1801f05f4  mov     rax, [rcx]
0x1801f05f7  mov     rax, [rax+10h]
0x1801f05fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0600  test    ebx, ebx
0x1801f0602  js      loc_1801F06AC
0x1801f0608  cmp     [rsp+1B0h+var_13C], 1
0x1801f060d  jnz     loc_1801F06AC
0x1801f0613  mov     rcx, [rsp+1B0h+value]; pszStr1
0x1801f0618  test    rcx, rcx
0x1801f061b  jz      loc_1801F06B1
0x1801f0621  cmp     [rsp+1B0h+var_170], 0
0x1801f0627  jz      loc_1801F06B1
0x1801f062d  lea     rdx, [rbp+0B0h+pszStr2]; pszStr2
0x1801f0631  call    cs:__imp_StrCmpICW
0x1801f0638  nop     dword ptr [rax+rax+00h]
0x1801f063d  test    eax, eax
0x1801f063f  jnz     short loc_1801F065A
0x1801f0641  mov     rcx, [rsp+1B0h+var_170]; pszStr1
0x1801f0646  lea     rdx, [rbp+0B0h+var_80]; pszStr2
0x1801f064a  call    cs:__imp_StrCmpICW
0x1801f0651  nop     dword ptr [rax+rax+00h]
0x1801f0656  test    eax, eax
0x1801f0658  jz      short loc_1801F06AC
0x1801f065a  mov     rcx, [rsp+1B0h+value]; psz
0x1801f065f  lea     rdx, [rbp+0B0h+pclsid]; pclsid
0x1801f0663  xorps   xmm0, xmm0
0x1801f0666  movups  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x1801f066a  movups  xmmword ptr [rbp+0B0h+var_100.Data1], xmm0
0x1801f066e  call    cs:__imp_SHCLSIDFromString
0x1801f0675  nop     dword ptr [rax+rax+00h]
0x1801f067a  test    eax, eax
0x1801f067c  js      short loc_1801F06AC
0x1801f067e  mov     rcx, [rsp+1B0h+var_170]; psz
0x1801f0683  lea     rdx, [rbp+0B0h+var_100]; pclsid
0x1801f0687  call    cs:__imp_SHCLSIDFromString
0x1801f068e  nop     dword ptr [rax+rax+00h]
0x1801f0693  test    eax, eax
0x1801f0695  js      short loc_1801F06AC
0x1801f0697  movups  xmm0, xmmword ptr [rbp+0B0h+pclsid.Data1]
0x1801f069b  mov     edi, 1
0x1801f06a0  movups  xmm1, xmmword ptr [rbp+0B0h+var_100.Data1]
0x1801f06a4  movups  [rbp+0B0h+var_F0], xmm0
0x1801f06a8  movups  [rbp+0B0h+var_E0], xmm1
0x1801f06ac  mov     rcx, [rsp+1B0h+value]; pv
0x1801f06b1  call    cs:__imp_CoTaskMemFree
0x1801f06b8  nop     dword ptr [rax+rax+00h]
0x1801f06bd  mov     rcx, [rsp+1B0h+var_170]; pv
0x1801f06c2  call    cs:__imp_CoTaskMemFree
0x1801f06c9  nop     dword ptr [rax+rax+00h]
0x1801f06ce  mov     rcx, [rsp+1B0h+propBag]
0x1801f06d3  mov     rax, [rcx]
0x1801f06d6  mov     rax, [rax+10h]
0x1801f06da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f06df  mov     rcx, [rsp+1B0h+ppidl]; pidl
0x1801f06e4  call    cs:__imp_ILFree
0x1801f06eb  nop     dword ptr [rax+rax+00h]
0x1801f06f0  mov     rcx, [rsp+1B0h+punk]
0x1801f06f5  mov     rax, [rcx]
0x1801f06f8  mov     rax, [rax+10h]
0x1801f06fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0701  mov     rcx, [rsp+1B0h+var_168]
0x1801f0706  mov     rax, [rcx]
0x1801f0709  mov     rax, [rax+10h]
0x1801f070d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0712  test    edi, edi
0x1801f0714  jz      short loc_1801F0727
0x1801f0716  mov     rcx, [rsp+1B0h+var_160]; struct ITopViewAwareItem *
0x1801f071b  lea     r8, [rbp+0B0h+var_F0]; struct TOPVIEWKEY *
0x1801f071f  mov     rdx, rsi; unsigned __int16 *
0x1801f0722  call    ?ClearViewSettingsForTopView@@YAXPEAUITopViewAwareItem@@PEBGAEBUTOPVIEWKEY@@@Z; ClearViewSettingsForTopView(ITopViewAwareItem *,ushort const *,TOPVIEWKEY const &)
0x1801f0727  mov     rcx, [rsp+1B0h+var_160]
0x1801f072c  mov     rax, [rcx]
0x1801f072f  mov     rax, [rax+10h]
0x1801f0733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0738  mov     eax, ebx
0x1801f073a  mov     rcx, [rbp+0B0h+var_30]
0x1801f0741  xor     rcx, rsp; StackCookie
0x1801f0744  call    __security_check_cookie
0x1801f0749  add     rsp, 190h
0x1801f0750  pop     r14
0x1801f0752  pop     rdi
0x1801f0753  pop     rsi
0x1801f0754  pop     rbx
0x1801f0755  pop     rbp
0x1801f0756  retn
```
