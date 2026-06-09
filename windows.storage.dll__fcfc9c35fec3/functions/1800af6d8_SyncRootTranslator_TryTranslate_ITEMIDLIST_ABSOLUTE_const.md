# SyncRootTranslator::TryTranslate(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1800af6d8`
- end: `0x1800afde7`
- name: `?TryTranslate@SyncRootTranslator@@SA?AV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `1807`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b06e0`

## callees

- `0x18003e0a0`
- `0x18005de30`
- `0x18005ee50`
- `0x180063050`
- `0x180079ccc`
- `0x1800ae930`
- `0x1800af6d8`
- `0x1800b03d0`
- `0x1800b1760`
- `0x1800c4ae0`
- `0x1800d2690`
- `0x1800dafcc`
- `0x1800db6f4`
- `0x1801ae280`
- `0x180276be8`
- `0x18028040c`
- `0x180297410`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x1800af736`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x1800af736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afb26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afb85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afbe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afc02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afc1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afd16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afb26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afb85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afbe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afc02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afc1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afcde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afd16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af80d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af80d`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
void **__fastcall SyncRootTranslator::TryTranslate(Windows::Internal::SyncRootHelpers *a1, ITEMIDLIST *a2)
{
  ITEMIDLIST *v2; // r12
  void **v3; // r15
  HRESULT v5; // eax
  void *v6; // rdi
  int (__fastcall *v7)(void *, __int64, __int64); // rbx
  __int64 v8; // r8
  const char *v9; // r9
  HRESULT v10; // eax
  int (__fastcall *v11)(__int64, LPVOID, __int64, __int64 *); // rdi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64); // rbx
  __int64 v14; // rdx
  int v15; // eax
  __int64 *v16; // rdi
  struct IShellItem2 *v17; // rbx
  LPVOID v18; // r14
  int (__fastcall *v19)(LPVOID, LPVOID, _QWORD, __int64); // rsi
  __int64 v20; // r9
  __int64 **ItemFromParsingNameAndAttributes; // rax
  __int64 *v22; // rsi
  IUnknown *v23; // rcx
  struct IShellItem2 **FolderOnRootDesktop; // rax
  __int64 v25; // rax
  int v26; // eax
  _QWORD *v27; // rax
  struct IShellItem2 **v28; // rax
  struct IBindCtx *v29; // rdx
  HRESULT v30; // eax
  void *v31; // rcx
  const ITEMIDLIST *v32; // rax
  LPITEMIDLIST v33; // rax
  void *v34; // rcx
  void *v35; // rcx
  ITEMIDLIST *v36; // rcx
  ITEMIDLIST *v37; // rcx
  LPCITEMIDLIST v38; // rdx
  int v39; // [rsp+20h] [rbp-E8h]
  int v40; // [rsp+20h] [rbp-E8h]
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp-A8h] BYREF
  char v42; // [rsp+68h] [rbp-A0h]
  Windows::Internal::SyncRootHelpers *v43; // [rsp+70h] [rbp-98h]
  IUnknown *punk; // [rsp+78h] [rbp-90h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+80h] [rbp-88h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+88h] [rbp-80h] BYREF
  __int64 v47; // [rsp+90h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-70h]
  LPVOID v49; // [rsp+A0h] [rbp-68h] BYREF
  void *ppv; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v51; // [rsp+B0h] [rbp-58h] BYREF
  LPVOID v52; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID v53; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = a2;
  v3 = (void **)a1;
  v43 = a1;
  *(_QWORD *)a1 = 0;
  if ( a2
    && a2->mkid.cb
    && Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(a1)
    && !RtlIsThreadWithinLoaderCallout() )
  {
    ppv = 0;
    v5 = SHCreateItemFromIDList(v2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    try
    {
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
          (const char *)(unsigned int)v5,
          v39);
      v53 = 0;
      v6 = ppv;
      v7 = *(int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppv + 40LL);
      v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v53);
      if ( v7(v6, 2147844096LL, v8) >= 0 )
      {
        v49 = 0;
        v10 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v49);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBB,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
            (const char *)(unsigned int)v10,
            v40);
        v47 = 0;
        wil::com_ptr_t<ISyncRootManager,wil::err_exception_policy>::query<ISyncRootManager4>(&v49, &v54);
        v11 = *(int (__fastcall **)(__int64, LPVOID, __int64, __int64 *))(*(_QWORD *)v54 + 32LL);
        v47 = 0;
        if ( v11(v54, v53, 1, &v47) >= 0 )
        {
          v52 = 0;
          v12 = v47;
          v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 24LL);
          v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v52);
          v15 = v13(v12, v14);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xC3,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
              (const char *)(unsigned int)v15,
              0);
          v16 = 0;
          v17 = 0;
          v51 = 0;
          v18 = v49;
          v19 = *(int (__fastcall **)(LPVOID, LPVOID, _QWORD, __int64))(*(_QWORD *)v49 + 136LL);
          v20 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v51);
          if ( v19(v18, v52, 0, v20) >= 0 )
          {
            ItemFromParsingNameAndAttributes = (__int64 **)wil::GetItemFromParsingNameAndAttributes(&punk, v51);
            v22 = *ItemFromParsingNameAndAttributes;
            *ItemFromParsingNameAndAttributes = 0;
            v16 = v22;
            v23 = punk;
            if ( punk )
            {
              punk = 0;
              ((void (__fastcall *)(IUnknown *))v23->lpVtbl->Release)(v23);
            }
            FolderOnRootDesktop = (struct IShellItem2 **)SyncRootTranslator::TryFindFolderOnRootDesktop(&punk, v22);
            v17 = *FolderOnRootDesktop;
            *FolderOnRootDesktop = 0;
            if ( punk )
              ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
            if ( v17 )
              goto LABEL_83;
            pidl1 = 0;
            v25 = *v22;
            pidl1 = 0;
            v26 = (*(__int64 (__fastcall **)(__int64 *, LPCITEMIDLIST *))(v25 + 32))(v22, &pidl1);
            if ( v26 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xD8,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
                (const char *)(unsigned int)v26,
                0);
            v27 = (_QWORD *)wil::com_ptr_t<IShellItem,wil::err_exception_policy>::query<IShellItem2>(&pidl1, &pidl2);
            v28 = (struct IShellItem2 **)SyncRootTranslator::TryFindFolderOnRootDesktop(&punk, *v27);
            v17 = *v28;
            *v28 = 0;
            if ( punk )
              ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
            if ( pidl2 )
              (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl2->mkid.cb + 16LL))(pidl2);
            if ( v17 )
            {
              v16 = *(__int64 **)wil::com_ptr_t<IShellItem,wil::err_exception_policy>::query<IShellItem2>(&pidl1, &punk);
              if ( v16 )
                (*(void (__fastcall **)(__int64 *))(*v16 + 8))(v16);
              (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
              if ( punk )
                ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
            }
            if ( pidl1 )
              (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl1->mkid.cb + 16LL))(pidl1);
            if ( v17 )
            {
LABEL_83:
              if ( SyncRootTranslator::IsFileSystemFolder(v17) )
              {
                wil::GetAbsoluteIdList(&pidl2, v16);
                wil::GetAbsoluteIdList(&pidl1, v17);
                pv = 0;
                punk = 0;
                if ( (int)GetUnaliasedItem(
                            (struct IShellItem *)ppv,
                            v29,
                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                            (void **)&punk) >= 0 )
                {
                  ppidl = 0;
                  v42 = 1;
                  v30 = SHGetIDListFromObject(punk, &ppidl);
                  if ( v30 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0xF1,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
                      (const char *)(unsigned int)v30,
                      0);
                  if ( v42 )
                  {
                    v31 = pv;
                    pv = ppidl;
                    if ( v31 )
                      CoTaskMemFree(v31);
                  }
                  v2 = (ITEMIDLIST *)pv;
                }
                if ( ILIsEqual(v2, pidl2) )
                {
                  v38 = pidl1;
                  pidl1 = 0;
                  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                    v3,
                    v38);
                }
                else
                {
                  v32 = (const ITEMIDLIST *)ILIsParent((void *)pidl2, (struct _ITEMIDLIST_RELATIVE *)v2);
                  if ( v32 )
                  {
                    v33 = ILCombine(pidl1, v32);
                    v34 = *v3;
                    *v3 = v33;
                    if ( v34 )
                      CoTaskMemFree(v34);
                  }
                }
                v35 = pv;
                pv = 0;
                if ( v35 )
                  CoTaskMemFree(v35);
                if ( punk )
                  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
                v36 = (ITEMIDLIST *)pidl1;
                pidl1 = 0;
                if ( v36 )
                  CoTaskMemFree(v36);
                v37 = (ITEMIDLIST *)pidl2;
                pidl2 = 0;
                if ( v37 )
                  CoTaskMemFree(v37);
              }
            }
          }
          if ( v51 )
            CoTaskMemFree(v51);
          if ( v17 )
            ((void (__fastcall *)(struct IShellItem2 *))v17->lpVtbl->Release)(v17);
          if ( v16 )
            (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
          if ( v52 )
            CoTaskMemFree(v52);
        }
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        if ( v49 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
      }
      if ( v53 )
        CoTaskMemFree(v53);
      if ( ppv )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\folder.cpp",
        v9);
      return (void **)v43;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800af6d8  mov     [rsp+arg_10], rbx
0x1800af6dd  mov     [rsp+arg_18], rsi
0x1800af6e2  push    rdi
0x1800af6e3  push    r12
0x1800af6e5  push    r13
0x1800af6e7  push    r14
0x1800af6e9  push    r15
0x1800af6eb  sub     rsp, 0E0h
0x1800af6f2  mov     rax, cs:__security_cookie
0x1800af6f9  xor     rax, rsp
0x1800af6fc  mov     [rsp+108h+var_38], rax
0x1800af704  mov     r12, rdx
0x1800af707  mov     r15, rcx
0x1800af70a  mov     [rsp+108h+var_98], rcx
0x1800af70f  xor     r13d, r13d
0x1800af712  mov     [rsp+108h+var_C8], r13d
0x1800af717  mov     [rcx], r13
0x1800af71a  lea     esi, [r13+1]
0x1800af71e  mov     [rsp+108h+var_C8], esi
0x1800af722  test    rdx, rdx
0x1800af725  jz      short loc_1800AF746
0x1800af727  cmp     [rdx], r13w
0x1800af72b  jz      short loc_1800AF746
0x1800af72d  call    ?AreAnyStorageProvidersRegistered@SyncRootHelpers@Internal@Windows@@YA_NXZ; Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(void)
0x1800af732  test    al, al
0x1800af734  jz      short loc_1800AF746
0x1800af736  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x1800af73d  nop     dword ptr [rax+rax+00h]
0x1800af742  test    al, al
0x1800af744  jz      short loc_1800AF777
0x1800af746  mov     rax, r15
0x1800af749  mov     rcx, [rsp+108h+var_38]
0x1800af751  xor     rcx, rsp; StackCookie
0x1800af754  call    __security_check_cookie
0x1800af759  lea     r11, [rsp+108h+var_28]
0x1800af761  mov     rbx, [r11+40h]
0x1800af765  mov     rsi, [r11+48h]
0x1800af769  mov     rsp, r11
0x1800af76c  pop     r15
0x1800af76e  pop     r14
0x1800af770  pop     r13
0x1800af772  pop     r12
0x1800af774  pop     rdi
0x1800af775  retn
0x1800af777  mov     [rsp+108h+ppv], r13
0x1800af77f  lea     r8, [rsp+108h+ppv]; ppv
0x1800af787  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800af78e  mov     rcx, r12; pidl
0x1800af791  call    SHCreateItemFromIDList
0x1800af796  mov     rcx, [rsp+108h]; this
0x1800af79e  test    eax, eax
0x1800af7a0  js      loc_1800AFCEC
0x1800af7a6  mov     [rsp+108h+var_48], r13
0x1800af7ae  mov     rdi, [rsp+108h+ppv]
0x1800af7b6  mov     rax, [rdi]
0x1800af7b9  mov     rbx, [rax+28h]
0x1800af7bd  lea     rcx, [rsp+108h+var_48]
0x1800af7c5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800af7ca  mov     r8, rax
0x1800af7cd  mov     edx, 80058000h
0x1800af7d2  mov     rcx, rdi
0x1800af7d5  mov     rax, rbx
0x1800af7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af7dd  test    eax, eax
0x1800af7df  js      loc_1800AFCB2
0x1800af7e5  mov     [rsp+108h+var_68], r13
0x1800af7ed  lea     rax, [rsp+108h+var_68]
0x1800af7f5  mov     [rsp+108h+var_E8], rax; int
0x1800af7fa  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x1800af801  mov     r8d, esi; dwClsContext
0x1800af804  xor     edx, edx; pUnkOuter
0x1800af806  lea     rcx, CLSID_SyncRootManager; rclsid
0x1800af80d  call    cs:__imp_CoCreateInstance
0x1800af814  nop     dword ptr [rax+rax+00h]
0x1800af819  mov     rcx, [rsp+108h]; this
0x1800af821  test    eax, eax
0x1800af823  js      loc_1800AFD01
0x1800af829  mov     [rsp+108h+var_78], r13
0x1800af831  lea     rdx, [rsp+108h+var_40]
0x1800af839  lea     rcx, [rsp+108h+var_68]
0x1800af841  call    ??$query@UISyncRootManager4@@@?$com_ptr_t@UISyncRootManager@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UISyncRootManager4@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_exception_policy>::query<ISyncRootManager4>(void)
0x1800af846  nop
0x1800af847  mov     rbx, [rsp+108h+var_40]
0x1800af84f  mov     rax, [rbx]
0x1800af852  mov     rdi, [rax+20h]
0x1800af856  mov     rcx, [rsp+108h+var_78]
0x1800af85e  mov     [rsp+108h+var_78], r13
0x1800af866  test    rcx, rcx
0x1800af869  jz      short loc_1800AF878
0x1800af86b  mov     rax, [rcx]
0x1800af86e  mov     rax, [rax+10h]
0x1800af872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af877  nop
0x1800af878  mov     [rsp+108h+var_E0], r13
0x1800af87d  mov     [rsp+108h+var_E8], r13; int
0x1800af882  lea     r9, [rsp+108h+var_78]
0x1800af88a  mov     r8d, esi
0x1800af88d  mov     rdx, [rsp+108h+var_48]
0x1800af895  mov     rcx, rbx
0x1800af898  mov     rax, rdi
0x1800af89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af8a0  test    eax, eax
0x1800af8a2  js      loc_1800AFC64
0x1800af8a8  mov     [rsp+108h+var_50], r13
0x1800af8b0  mov     rdi, [rsp+108h+var_78]
0x1800af8b8  mov     rax, [rdi]
0x1800af8bb  mov     rbx, [rax+18h]
0x1800af8bf  lea     rcx, [rsp+108h+var_50]
0x1800af8c7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800af8cc  mov     rdx, rax
0x1800af8cf  mov     rcx, rdi
0x1800af8d2  mov     rax, rbx
0x1800af8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af8da  mov     rcx, [rsp+108h]; this
0x1800af8e2  test    eax, eax
0x1800af8e4  js      loc_1800AFD27
0x1800af8ea  mov     rdi, r13
0x1800af8ed  mov     [rsp+108h+var_B8], r13
0x1800af8f2  mov     rbx, r13
0x1800af8f5  mov     [rsp+108h+var_C0], rbx
0x1800af8fa  mov     [rsp+108h+var_58], r13
0x1800af902  mov     r14, [rsp+108h+var_68]
0x1800af90a  mov     rax, [r14]
0x1800af90d  mov     rsi, [rax+88h]
0x1800af914  lea     rcx, [rsp+108h+var_58]
0x1800af91c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800af921  mov     r9, rax
0x1800af924  xor     r8d, r8d
0x1800af927  mov     rdx, [rsp+108h+var_50]
0x1800af92f  mov     rcx, r14
0x1800af932  mov     rax, rsi
0x1800af935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af93a  test    eax, eax
0x1800af93c  js      loc_1800AFC0F
0x1800af942  mov     rdx, [rsp+108h+var_58]
0x1800af94a  lea     rcx, [rsp+108h+punk]
0x1800af94f  call    ?GetItemFromParsingNameAndAttributes@wil@@YA?AV?$ComPtr@UIShellItem2@@@WRL@Microsoft@@PEBGK@Z; wil::GetItemFromParsingNameAndAttributes(ushort const *,ulong)
0x1800af954  mov     rsi, [rax]
0x1800af957  mov     [rax], r13
0x1800af95a  mov     rdi, rsi
0x1800af95d  mov     [rsp+108h+var_B8], rsi
0x1800af962  mov     rcx, [rsp+108h+punk]
0x1800af967  test    rcx, rcx
0x1800af96a  jz      short loc_1800AF97E
0x1800af96c  mov     [rsp+108h+punk], r13
0x1800af971  mov     rax, [rcx]
0x1800af974  mov     rax, [rax+10h]
0x1800af978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af97d  nop
0x1800af97e  mov     rdx, rsi
0x1800af981  lea     rcx, [rsp+108h+punk]
0x1800af986  call    ?TryFindFolderOnRootDesktop@SyncRootTranslator@@CA?AV?$com_ptr_t@UIShellItem2@@Uerr_exception_policy@wil@@@wil@@PEAUIShellItem2@@@Z; SyncRootTranslator::TryFindFolderOnRootDesktop(IShellItem2 *)
0x1800af98b  mov     rbx, [rax]
0x1800af98e  mov     [rax], r13
0x1800af991  mov     [rsp+108h+var_C0], rbx
0x1800af996  mov     rcx, [rsp+108h+punk]
0x1800af99b  test    rcx, rcx
0x1800af99e  jz      short loc_1800AF9AD
0x1800af9a0  mov     rax, [rcx]
0x1800af9a3  mov     rax, [rax+10h]
0x1800af9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9ac  nop
0x1800af9ad  test    rbx, rbx
0x1800af9b0  jnz     loc_1800AFA78
0x1800af9b6  mov     [rsp+108h+pidl1], r13
0x1800af9be  mov     rax, [rsi]
0x1800af9c1  mov     [rsp+108h+pidl1], r13
0x1800af9c9  lea     rdx, [rsp+108h+pidl1]
0x1800af9d1  mov     rcx, rsi
0x1800af9d4  mov     rax, [rax+20h]
0x1800af9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9dd  mov     rcx, [rsp+108h]; this
0x1800af9e5  test    eax, eax
0x1800af9e7  js      loc_1800AFD51
0x1800af9ed  lea     rdx, [rsp+108h+pidl2]
0x1800af9f5  lea     rcx, [rsp+108h+pidl1]
0x1800af9fd  call    ??$query@UIShellItem2@@@?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIShellItem2@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IShellItem,wil::err_exception_policy>::query<IShellItem2>(void)
0x1800afa02  nop
0x1800afa03  mov     rdx, [rax]
0x1800afa06  lea     rcx, [rsp+108h+punk]
0x1800afa0b  call    ?TryFindFolderOnRootDesktop@SyncRootTranslator@@CA?AV?$com_ptr_t@UIShellItem2@@Uerr_exception_policy@wil@@@wil@@PEAUIShellItem2@@@Z; SyncRootTranslator::TryFindFolderOnRootDesktop(IShellItem2 *)
0x1800afa10  mov     rbx, [rax]
0x1800afa13  mov     [rax], r13
0x1800afa16  mov     [rsp+108h+var_C0], rbx
0x1800afa1b  mov     rcx, [rsp+108h+punk]
0x1800afa20  test    rcx, rcx
0x1800afa23  jz      short loc_1800AFA32
0x1800afa25  mov     rax, [rcx]
0x1800afa28  mov     rax, [rax+10h]
0x1800afa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa31  nop
0x1800afa32  mov     rcx, [rsp+108h+pidl2]
0x1800afa3a  test    rcx, rcx
0x1800afa3d  jz      short loc_1800AFA4C
0x1800afa3f  mov     rax, [rcx]
0x1800afa42  mov     rax, [rax+10h]
0x1800afa46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa4b  nop
0x1800afa4c  test    rbx, rbx
0x1800afa4f  jnz     loc_1800AFD65
0x1800afa55  mov     rcx, [rsp+108h+pidl1]
0x1800afa5d  test    rcx, rcx
0x1800afa60  jz      short loc_1800AFA6F
0x1800afa62  mov     rax, [rcx]
0x1800afa65  mov     rax, [rax+10h]
0x1800afa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa6e  nop
0x1800afa6f  test    rbx, rbx
0x1800afa72  jz      loc_1800AFC0F
0x1800afa78  mov     rcx, rbx; struct IShellItem2 *
0x1800afa7b  call    ?IsFileSystemFolder@SyncRootTranslator@@CA_NPEAUIShellItem2@@@Z; SyncRootTranslator::IsFileSystemFolder(IShellItem2 *)
0x1800afa80  test    al, al
0x1800afa82  jz      loc_1800AFC0F
0x1800afa88  mov     rdx, rdi
0x1800afa8b  lea     rcx, [rsp+108h+pidl2]
0x1800afa93  call    ?GetAbsoluteIdList@wil@@YA?AV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@PEAUIShellItem@@@Z; wil::GetAbsoluteIdList(IShellItem *)
0x1800afa98  nop
0x1800afa99  mov     rdx, rbx
0x1800afa9c  lea     rcx, [rsp+108h+pidl1]
0x1800afaa4  call    ?GetAbsoluteIdList@wil@@YA?AV?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@PEAUIShellItem@@@Z; wil::GetAbsoluteIdList(IShellItem *)
0x1800afaa9  nop
0x1800afaaa  mov     [rsp+108h+pv], r13
0x1800afab2  mov     [rsp+108h+punk], r13
0x1800afab7  lea     r9, [rsp+108h+punk]; void **
0x1800afabc  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x1800afac3  mov     rcx, [rsp+108h+ppv]; struct IShellItem *
0x1800afacb  call    ?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)
0x1800afad0  test    eax, eax
0x1800afad2  js      short loc_1800AFB3A
0x1800afad4  lea     rax, [rsp+108h+pv]
0x1800afadc  mov     [rsp+108h+var_B0], rax
0x1800afae1  mov     [rsp+108h+ppidl], r13
0x1800afae6  mov     [rsp+108h+var_A0], 1
0x1800afaeb  lea     rdx, [rsp+108h+ppidl]; ppidl
0x1800afaf0  mov     rcx, [rsp+108h+punk]; punk
0x1800afaf5  call    SHGetIDListFromObject
0x1800afafa  mov     rcx, [rsp+108h]; this
0x1800afb02  test    eax, eax
0x1800afb04  js      loc_1800AFD3C
0x1800afb0a  cmp     [rsp+108h+var_A0], r13b
0x1800afb0f  jz      short loc_1800AFB32
0x1800afb11  mov     rdx, [rsp+108h+var_B0]
0x1800afb16  mov     rcx, [rdx]; pv
0x1800afb19  mov     rax, [rsp+108h+ppidl]
0x1800afb1e  mov     [rdx], rax
0x1800afb21  test    rcx, rcx
0x1800afb24  jz      short loc_1800AFB32
0x1800afb26  call    cs:__imp_CoTaskMemFree
0x1800afb2d  nop     dword ptr [rax+rax+00h]
0x1800afb32  mov     r12, [rsp+108h+pv]
0x1800afb3a  mov     rdx, [rsp+108h+pidl2]; pidl2
0x1800afb42  mov     rcx, r12; pidl1
0x1800afb45  call    ILIsEqual
0x1800afb4a  test    eax, eax
0x1800afb4c  jnz     loc_1800AFDBF
0x1800afb52  xor     r8d, r8d
0x1800afb55  mov     rdx, r12; struct _ITEMIDLIST_RELATIVE *
0x1800afb58  mov     rcx, [rsp+108h+pidl2]; Buf2
0x1800afb60  call    _ILIsParent
0x1800afb65  test    rax, rax
0x1800afb68  jz      short loc_1800AFB92
0x1800afb6a  mov     rdx, rax; pidl2
0x1800afb6d  mov     rcx, [rsp+108h+pidl1]; pidl1
0x1800afb75  call    ILCombine
0x1800afb7a  mov     rcx, [r15]; pv
0x1800afb7d  mov     [r15], rax
0x1800afb80  test    rcx, rcx
0x1800afb83  jz      short loc_1800AFB92
0x1800afb85  call    cs:__imp_CoTaskMemFree
0x1800afb8c  nop     dword ptr [rax+rax+00h]
0x1800afb91  nop
0x1800afb92  mov     rcx, [rsp+108h+pv]; pv
0x1800afb9a  mov     [rsp+108h+pv], r13
0x1800afba2  test    rcx, rcx
0x1800afba5  jz      short loc_1800AFBB4
0x1800afba7  call    cs:__imp_CoTaskMemFree
0x1800afbae  nop     dword ptr [rax+rax+00h]
0x1800afbb3  nop
0x1800afbb4  mov     rcx, [rsp+108h+punk]
0x1800afbb9  test    rcx, rcx
0x1800afbbc  jz      short loc_1800AFBCB
0x1800afbbe  mov     rax, [rcx]
0x1800afbc1  mov     rax, [rax+10h]
0x1800afbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afbca  nop
0x1800afbcb  mov     rcx, [rsp+108h+pidl1]; pv
0x1800afbd3  mov     [rsp+108h+pidl1], r13
0x1800afbdb  test    rcx, rcx
0x1800afbde  jz      short loc_1800AFBED
0x1800afbe0  call    cs:__imp_CoTaskMemFree
0x1800afbe7  nop     dword ptr [rax+rax+00h]
0x1800afbec  nop
0x1800afbed  mov     rcx, [rsp+108h+pidl2]; pv
0x1800afbf5  mov     [rsp+108h+pidl2], r13
0x1800afbfd  test    rcx, rcx
0x1800afc00  jz      short loc_1800AFC0F
0x1800afc02  call    cs:__imp_CoTaskMemFree
0x1800afc09  nop     dword ptr [rax+rax+00h]
0x1800afc0e  nop
0x1800afc0f  mov     rcx, [rsp+108h+var_58]; pv
  ... truncated ...
```
