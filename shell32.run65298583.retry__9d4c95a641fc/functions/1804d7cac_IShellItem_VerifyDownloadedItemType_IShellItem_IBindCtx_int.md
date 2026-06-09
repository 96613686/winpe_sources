# IShellItem_VerifyDownloadedItemType(IShellItem *,IBindCtx *,int *)

- ea: `0x1804d7cac`
- end: `0x1804d7fac`
- name: `?IShellItem_VerifyDownloadedItemType@@YAJPEAUIShellItem@@PEAUIBindCtx@@PEAH@Z`
- size: `768`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IBindCtx *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1803a9db8`

## callees

- `0x1800cb730`
- `0x180233280`
- `0x1804d7cac`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7dd4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7e17`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7e7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7eb4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7f33`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7dd4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7e17`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7e7f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7eb4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1804d7f33`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1804d7e71`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1804d7e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7e24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7e24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804d7f76`
- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x1804d7ea1`
- `SHLWAPI!__imp_MIME_GetExtensionW` at `0x1804d7ea1`
- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x1804d7ef8`
- `api-ms-win-shell-associations-l1-1-0!AssocCreateForClasses` at `0x1804d7ef8`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804d7d47`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804d7d98`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804d7d47`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804d7d98`

## pseudocode

```c
__int64 __fastcall IShellItem_VerifyDownloadedItemType(struct IShellItem *a1, struct IBindCtx *a2, int *a3)
{
  struct IShellItemVtbl *lpVtbl; // rax
  unsigned int v6; // edi
  int v7; // eax
  int v8; // ebx
  const WCHAR *ExtensionW; // rax
  PWSTR v11; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR value; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  ASSOCIATIONELEMENT rgClasses; // [rsp+58h] [rbp-A8h] BYREF
  IPropertyBag *propBag[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszStr2[264]; // [rsp+80h] [rbp-80h] BYREF

  *a3 = 0;
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v6 = -2147023267;
  if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
         &v13) >= 0 )
  {
    v11 = 0;
    value = 0;
    propBag[0] = 0;
    if ( (int)GetObjectFromBindCtx(
                a2,
                L"SHBindCtxPropertyBag",
                &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                (void **)propBag) >= 0 )
    {
      PSPropertyBag_ReadStrAlloc(propBag[0], L"ServerFileName", &value);
      ((void (__fastcall *)(IPropertyBag *))propBag[0]->lpVtbl->Release)(propBag[0]);
    }
    v11 = 0;
    propBag[0] = 0;
    if ( (int)GetObjectFromBindCtx(
                a2,
                L"SHBindCtxPropertyBag",
                &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                (void **)propBag) >= 0 )
    {
      PSPropertyBag_ReadStrAlloc(propBag[0], L"MimeType", &v11);
      ((void (__fastcall *)(IPropertyBag *))propBag[0]->lpVtbl->Release)(propBag[0]);
    }
    if ( value )
    {
      if ( !v11 )
        goto LABEL_12;
    }
    else if ( !v11 )
    {
      v6 = 0;
LABEL_24:
      CoTaskMemFree(value);
      CoTaskMemFree(v11);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return v6;
    }
    v7 = StrCmpICW(L"text/html", v11);
    propBag[0] = 0;
    *a3 = v7 == 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, IPropertyBag **))(*(_QWORD *)v13 + 136LL))(
           v13,
           &PKEY_MIMEType,
           propBag) >= 0 )
    {
      v8 = StrCmpICW((LPCWSTR)propBag[0], v11);
      CoTaskMemFree(propBag[0]);
      v6 = v8 != 0 ? 0x8007065D : 0;
      if ( !v8 )
        goto LABEL_24;
    }
LABEL_12:
    propBag[0] = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, IPropertyBag **))(*(_QWORD *)v13 + 136LL))(
           v13,
           &PKEY_FileExtension,
           propBag) < 0 )
      goto LABEL_24;
    if ( !value || (ExtensionW = PathFindExtensionW(value), StrCmpICW((LPCWSTR)propBag[0], ExtensionW)) )
    {
      if ( !v11 )
      {
LABEL_23:
        CoTaskMemFree(propBag[0]);
        goto LABEL_24;
      }
      if ( !(unsigned int)MIME_GetExtensionW(v11, pszStr2, 260) || StrCmpICW((LPCWSTR)propBag[0], pszStr2) )
      {
        rgClasses.pszClass = (PCWSTR)propBag[0];
        ppv = 0;
        rgClasses.ac = ASSOCCLASS_PROGID_STR;
        rgClasses.hkClass = 0;
        if ( AssocCreateForClasses(&rgClasses, 1u, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &ppv) >= 0 )
        {
          pszStr1 = 0;
          if ( (*(int (__fastcall **)(void *, __int64, _QWORD, LPCWSTR *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 2147942402LL,
                 0,
                 &pszStr1) >= 0 )
          {
            v6 &= -(StrCmpICW(pszStr1, v11) != 0);
            CoTaskMemFree((LPVOID)pszStr1);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        goto LABEL_23;
      }
    }
    v6 = 0;
    goto LABEL_23;
  }
  return v6;
}

```

## disassembly

```asm
0x1804d7cac  push    rbp
0x1804d7cae  push    rbx
0x1804d7caf  push    rsi
0x1804d7cb0  push    rdi
0x1804d7cb1  push    r14
0x1804d7cb3  lea     rbp, [rsp-1A0h]
0x1804d7cbb  sub     rsp, 2A0h
0x1804d7cc2  mov     rax, cs:__security_cookie
0x1804d7cc9  xor     rax, rsp
0x1804d7ccc  mov     [rbp+1C0h+var_30], rax
0x1804d7cd3  xor     r14d, r14d
0x1804d7cd6  mov     rsi, r8
0x1804d7cd9  mov     [r8], r14d
0x1804d7cdc  mov     rbx, rdx
0x1804d7cdf  mov     rax, [rcx]
0x1804d7ce2  lea     r8, [rsp+2C0h+var_280]
0x1804d7ce7  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1804d7cee  mov     [rsp+2C0h+var_280], r14
0x1804d7cf3  mov     edi, 8007065Dh
0x1804d7cf8  mov     rax, [rax]
0x1804d7cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7d00  test    eax, eax
0x1804d7d02  js      loc_1804D7F8D
0x1804d7d08  lea     r9, [rsp+2C0h+propBag]; void **
0x1804d7d0d  mov     [rsp+2C0h+var_290], r14
0x1804d7d12  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; struct _GUID *
0x1804d7d19  mov     [rsp+2C0h+value], r14
0x1804d7d1e  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x1804d7d25  mov     [rsp+2C0h+propBag], r14
0x1804d7d2a  mov     rcx, rbx; struct IBindCtx *
0x1804d7d2d  call    ?GetObjectFromBindCtx@@YAJPEAUIBindCtx@@PEBGAEBU_GUID@@PEAPEAX@Z; GetObjectFromBindCtx(IBindCtx *,ushort const *,_GUID const &,void * *)
0x1804d7d32  test    eax, eax
0x1804d7d34  js      short loc_1804D7D5E
0x1804d7d36  mov     rcx, [rsp+2C0h+propBag]; propBag
0x1804d7d3b  lea     r8, [rsp+2C0h+value]; value
0x1804d7d40  lea     rdx, aServerfilename; "ServerFileName"
0x1804d7d47  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1804d7d4d  mov     rcx, [rsp+2C0h+propBag]
0x1804d7d52  mov     rax, [rcx]
0x1804d7d55  mov     rax, [rax+10h]
0x1804d7d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7d5e  lea     r9, [rsp+2C0h+propBag]; void **
0x1804d7d63  mov     [rsp+2C0h+var_290], r14
0x1804d7d68  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; struct _GUID *
0x1804d7d6f  mov     [rsp+2C0h+propBag], r14
0x1804d7d74  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x1804d7d7b  mov     rcx, rbx; struct IBindCtx *
0x1804d7d7e  call    ?GetObjectFromBindCtx@@YAJPEAUIBindCtx@@PEBGAEBU_GUID@@PEAPEAX@Z; GetObjectFromBindCtx(IBindCtx *,ushort const *,_GUID const &,void * *)
0x1804d7d83  test    eax, eax
0x1804d7d85  js      short loc_1804D7DAF
0x1804d7d87  mov     rcx, [rsp+2C0h+propBag]; propBag
0x1804d7d8c  lea     r8, [rsp+2C0h+var_290]; value
0x1804d7d91  lea     rdx, aMimetype; "MimeType"
0x1804d7d98  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1804d7d9e  mov     rcx, [rsp+2C0h+propBag]
0x1804d7da3  mov     rax, [rcx]
0x1804d7da6  mov     rax, [rax+10h]
0x1804d7daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7daf  mov     rdx, [rsp+2C0h+var_290]; pszStr2
0x1804d7db4  cmp     [rsp+2C0h+value], r14
0x1804d7db9  jnz     short loc_1804D7DC8
0x1804d7dbb  test    rdx, rdx
0x1804d7dbe  jnz     short loc_1804D7DCD
0x1804d7dc0  mov     edi, r14d
0x1804d7dc3  jmp     loc_1804D7F66
0x1804d7dc8  test    rdx, rdx
0x1804d7dcb  jz      short loc_1804D7E3A
0x1804d7dcd  lea     rcx, pszContentType; "text/html"
0x1804d7dd4  call    cs:__imp_StrCmpICW
0x1804d7dda  mov     ecx, r14d
0x1804d7ddd  mov     [rsp+2C0h+propBag], r14
0x1804d7de2  test    eax, eax
0x1804d7de4  lea     r8, [rsp+2C0h+propBag]
0x1804d7de9  lea     rdx, PKEY_MIMEType
0x1804d7df0  setz    cl
0x1804d7df3  mov     [rsi], ecx
0x1804d7df5  mov     rcx, [rsp+2C0h+var_280]
0x1804d7dfa  mov     rax, [rcx]
0x1804d7dfd  mov     rax, [rax+88h]
0x1804d7e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7e09  test    eax, eax
0x1804d7e0b  js      short loc_1804D7E3A
0x1804d7e0d  mov     rdx, [rsp+2C0h+var_290]; pszStr2
0x1804d7e12  mov     rcx, [rsp+2C0h+propBag]; pszStr1
0x1804d7e17  call    cs:__imp_StrCmpICW
0x1804d7e1d  mov     rcx, [rsp+2C0h+propBag]; pv
0x1804d7e22  mov     ebx, eax
0x1804d7e24  call    cs:__imp_CoTaskMemFree
0x1804d7e2a  mov     eax, ebx
0x1804d7e2c  neg     eax
0x1804d7e2e  sbb     ecx, ecx
0x1804d7e30  and     edi, ecx
0x1804d7e32  test    ebx, ebx
0x1804d7e34  jz      loc_1804D7F66
0x1804d7e3a  mov     rcx, [rsp+2C0h+var_280]
0x1804d7e3f  lea     r8, [rsp+2C0h+propBag]
0x1804d7e44  mov     [rsp+2C0h+propBag], r14
0x1804d7e49  lea     rdx, PKEY_FileExtension
0x1804d7e50  mov     rax, [rcx]
0x1804d7e53  mov     rax, [rax+88h]
0x1804d7e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7e5f  test    eax, eax
0x1804d7e61  js      loc_1804D7F66
0x1804d7e67  mov     rcx, [rsp+2C0h+value]; pszPath
0x1804d7e6c  test    rcx, rcx
0x1804d7e6f  jz      short loc_1804D7E89
0x1804d7e71  call    cs:__imp_PathFindExtensionW
0x1804d7e77  mov     rcx, [rsp+2C0h+propBag]; pszStr1
0x1804d7e7c  mov     rdx, rax; pszStr2
0x1804d7e7f  call    cs:__imp_StrCmpICW
0x1804d7e85  test    eax, eax
0x1804d7e87  jz      short loc_1804D7EBE
0x1804d7e89  mov     rcx, [rsp+2C0h+var_290]
0x1804d7e8e  test    rcx, rcx
0x1804d7e91  jz      loc_1804D7F5B
0x1804d7e97  mov     r8d, 104h
0x1804d7e9d  lea     rdx, [rbp+1C0h+pszStr2]
0x1804d7ea1  call    cs:__imp_MIME_GetExtensionW
0x1804d7ea7  test    eax, eax
0x1804d7ea9  jz      short loc_1804D7EC6
0x1804d7eab  mov     rcx, [rsp+2C0h+propBag]; pszStr1
0x1804d7eb0  lea     rdx, [rbp+1C0h+pszStr2]; pszStr2
0x1804d7eb4  call    cs:__imp_StrCmpICW
0x1804d7eba  test    eax, eax
0x1804d7ebc  jnz     short loc_1804D7EC6
0x1804d7ebe  mov     edi, r14d
0x1804d7ec1  jmp     loc_1804D7F5B
0x1804d7ec6  mov     rax, [rsp+2C0h+propBag]
0x1804d7ecb  lea     r9, [rsp+2C0h+ppv]; ppv
0x1804d7ed0  lea     r8, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f; riid
0x1804d7ed7  mov     [rsp+2C0h+rgClasses.pszClass], rax
0x1804d7edc  mov     edx, 1; cClasses
0x1804d7ee1  mov     [rsp+2C0h+ppv], r14
0x1804d7ee6  lea     rcx, [rsp+2C0h+rgClasses]; rgClasses
0x1804d7eeb  mov     [rsp+2C0h+rgClasses.ac], 2
0x1804d7ef3  mov     [rsp+2C0h+rgClasses.hkClass], r14
0x1804d7ef8  call    cs:__imp_AssocCreateForClasses
0x1804d7efe  test    eax, eax
0x1804d7f00  js      short loc_1804D7F5B
0x1804d7f02  mov     rcx, [rsp+2C0h+ppv]
0x1804d7f07  lea     r9, [rsp+2C0h+pszStr1]
0x1804d7f0c  mov     [rsp+2C0h+pszStr1], r14
0x1804d7f11  xor     r8d, r8d
0x1804d7f14  mov     edx, 80070002h
0x1804d7f19  mov     rax, [rcx]
0x1804d7f1c  mov     rax, [rax+18h]
0x1804d7f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7f25  test    eax, eax
0x1804d7f27  js      short loc_1804D7F4A
0x1804d7f29  mov     rdx, [rsp+2C0h+var_290]; pszStr2
0x1804d7f2e  mov     rcx, [rsp+2C0h+pszStr1]; pszStr1
0x1804d7f33  call    cs:__imp_StrCmpICW
0x1804d7f39  neg     eax
0x1804d7f3b  sbb     ecx, ecx
0x1804d7f3d  and     edi, ecx
0x1804d7f3f  mov     rcx, [rsp+2C0h+pszStr1]; pv
0x1804d7f44  call    cs:__imp_CoTaskMemFree
0x1804d7f4a  mov     rcx, [rsp+2C0h+ppv]
0x1804d7f4f  mov     rax, [rcx]
0x1804d7f52  mov     rax, [rax+10h]
0x1804d7f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7f5b  mov     rcx, [rsp+2C0h+propBag]; pv
0x1804d7f60  call    cs:__imp_CoTaskMemFree
0x1804d7f66  mov     rcx, [rsp+2C0h+value]; pv
0x1804d7f6b  call    cs:__imp_CoTaskMemFree
0x1804d7f71  mov     rcx, [rsp+2C0h+var_290]; pv
0x1804d7f76  call    cs:__imp_CoTaskMemFree
0x1804d7f7c  mov     rcx, [rsp+2C0h+var_280]
0x1804d7f81  mov     rdx, [rcx]
0x1804d7f84  mov     rax, [rdx+10h]
0x1804d7f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804d7f8d  mov     eax, edi
0x1804d7f8f  mov     rcx, [rbp+1C0h+var_30]
0x1804d7f96  xor     rcx, rsp; StackCookie
0x1804d7f99  call    __security_check_cookie
0x1804d7f9e  add     rsp, 2A0h
0x1804d7fa5  pop     r14
0x1804d7fa7  pop     rdi
0x1804d7fa8  pop     rsi
0x1804d7fa9  pop     rbx
0x1804d7faa  pop     rbp
0x1804d7fab  retn
```
