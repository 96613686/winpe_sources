# CFSFolder::_GetFolderIconPath(_ITEMIDLIST_RELATIVE const *,int,ushort *,int,int *)

- ea: `0x180134360`
- end: `0x1801347e5`
- name: `?_GetFolderIconPath@CFSFolder@@IEAAHPEFBU_ITEMIDLIST_RELATIVE@@HPEAGHPEAH@Z`
- size: `1157`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, int, unsigned __int16 *, int, int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180041f50`
- `0x180096370`
- `0x18052c5d0`

## callees

- `0x180009fc0`
- `0x180063050`
- `0x1800ffce0`
- `0x180106480`
- `0x180133f50`
- `0x180134360`
- `0x1801357fc`
- `0x180202c40`
- `0x1802ba988`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180134718`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180134718`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180134581`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180134581`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801347bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801347bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180134543`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1801347d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180134543`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1801347d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013452c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801345f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013452c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801345f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134700`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180134730`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180134730`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1801345cf`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1801345cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFSFolder::_GetFolderIconPath(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        int a3,
        unsigned __int16 *a4,
        int a5,
        int *a6)
{
  unsigned int v8; // r13d
  char *v9; // rdi
  int (__fastcall *v10)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, __int64); // rbx
  __int64 v11; // rax
  int v12; // r12d
  int v13; // r14d
  int v14; // eax
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, PCWSTR, _QWORD, LPVOID *); // rbx
  LPVOID v17; // rcx
  int v18; // ebx
  int v19; // eax
  struct IUnknown *v20; // rdx
  int v22; // ebx
  int v23; // ebx
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct ICachedPrivateProfile *v27; // [rsp+58h] [rbp-A8h] BYREF
  KNOWNFOLDER_DEFINITION pKFD; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v29; // [rsp+D0h] [rbp-30h] BYREF
  PCWSTR pszPathIn; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v31[16]; // [rsp+E0h] [rbp-20h] BYREF

  LODWORD(pv) = a3;
  *a4 = 0;
  v8 = 0;
  pszPathIn = 0;
  v9 = (char *)this + 312;
  v10 = *(int (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, __int64))(*((_QWORD *)this + 39)
                                                                                            + 112LL);
  v11 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPathIn);
  if ( v10(v9, a2, 1, v11) < 0 )
    goto LABEL_11;
  v12 = 0;
  v13 = 0;
  v29 = 0;
  v27 = 0;
  if ( (_DWORD)pv )
    goto LABEL_6;
  v14 = a2
      ? (*(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, _QWORD, GUID *, struct ICachedPrivateProfile **))(*((_QWORD *)this + 6) + 40LL))(
          (char *)this + 48,
          a2,
          0,
          &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
          &v27)
      : CFSFolder::_GetDesktopIni(this, &v27);
  if ( v14 < 0 )
    goto LABEL_6;
  pv = 0;
  if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, const wchar_t *, _QWORD, int, LPVOID *))(*(_QWORD *)v27 + 48LL))(
         v27,
         L".ShellClassInfo",
         L"IconResource",
         0,
         2,
         &pv) >= 0 )
  {
    v18 = StringCchCopyW(a4, 0x104u, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    if ( v18 >= 0 )
    {
      v19 = PathParseIconLocationW(a4);
LABEL_16:
      v12 = v19;
LABEL_17:
      v13 = 1;
      goto LABEL_18;
    }
  }
  pv = 0;
  if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, const wchar_t *, _QWORD, int, LPVOID *))(*(_QWORD *)v27 + 48LL))(
         v27,
         L".ShellClassInfo",
         L"IconFile",
         0,
         2,
         &pv) >= 0 )
  {
    v22 = StringCchCopyW(a4, 0x104u, (const unsigned __int16 *)pv);
    CoTaskMemFree(pv);
    if ( v22 >= 0 )
    {
      if ( !a6 )
        goto LABEL_17;
      pv = 0;
      if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, const wchar_t *, _QWORD, int, LPVOID *))(*(_QWORD *)v27 + 48LL))(
             v27,
             L".ShellClassInfo",
             L"IconIndex",
             0,
             2,
             &pv) >= 0 )
      {
        v23 = StringCchCopyW(v31, 0x10u, (const unsigned __int16 *)pv);
        CoTaskMemFree(pv);
        if ( v23 >= 0 )
        {
          v19 = _o__wtoi(v31);
          goto LABEL_16;
        }
      }
    }
  }
LABEL_18:
  (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( !v13 )
  {
LABEL_6:
    if ( (int)CFSFolder::_EnsureKnownFolderManager(this) < 0 )
      goto LABEL_11;
    pv = 0;
    v15 = *((_QWORD *)this + 82);
    v16 = *(int (__fastcall **)(__int64, PCWSTR, _QWORD, LPVOID *))(*(_QWORD *)v15 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    if ( v16(v15, pszPathIn, 0, &pv) >= 0 )
    {
      v29 = 1;
      memset_0(&pKFD, 0, sizeof(pKFD));
      if ( (*(int (__fastcall **)(LPVOID, KNOWNFOLDER_DEFINITION *))(*(_QWORD *)pv + 88LL))(pv, &pKFD) >= 0 )
      {
        if ( pKFD.pszIcon && (unsigned int)SHExpandEnvironmentStringsW(pKFD.pszIcon, a4, 260) )
        {
          v12 = PathParseIconLocationW(a4);
          v13 = 1;
        }
        FreeKnownFolderDefinitionFields(&pKFD);
      }
    }
    v17 = pv;
    if ( pv )
    {
      pv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( !v13 )
      goto LABEL_11;
  }
  if ( PathCchCombine(a4, 0x104u, pszPathIn, a4) < 0 )
    goto LABEL_11;
  if ( v29 )
  {
    v8 = 1;
    goto LABEL_24;
  }
  if ( ((v29 = 0, (int)SHMapUrlToZone(a4, v20, 1u, &v29) < 0) || v29)
    && !(unsigned int)SHWindowsPolicy(POLID_EnableShellShortcutIconRemotePath)
    || (v8 = PathFileExistsAndAttributesW(a4, 0)) == 0 )
  {
LABEL_11:
    if ( a6 )
      GetShellIconLocationParts(SIID_FOLDER, a4, 0x104u, a6);
    goto LABEL_26;
  }
LABEL_24:
  if ( a6 )
    *a6 = v12;
LABEL_26:
  if ( pszPathIn )
    CoTaskMemFree((LPVOID)pszPathIn);
  return v8;
}

```

## disassembly

```asm
0x180134360  mov     [rsp-8+arg_10], rbx
0x180134365  push    rbp
0x180134366  push    rsi
0x180134367  push    rdi
0x180134368  push    r12
0x18013436a  push    r13
0x18013436c  push    r14
0x18013436e  push    r15
0x180134370  lea     rbp, [rsp-10h]
0x180134375  sub     rsp, 110h
0x18013437c  mov     rax, cs:__security_cookie
0x180134383  xor     rax, rsp
0x180134386  mov     [rbp+40h+var_40], rax
0x18013438a  mov     rsi, r9
0x18013438d  mov     dword ptr [rsp+140h+pv], r8d
0x180134392  mov     r14, rdx
0x180134395  mov     [rsp+140h+var_F8], rdx
0x18013439a  mov     [rsp+140h+var_100], rcx
0x18013439f  mov     r15, [rbp+40h+arg_28]
0x1801343a3  xor     eax, eax
0x1801343a5  mov     [r9], ax
0x1801343a9  xor     r13d, r13d
0x1801343ac  mov     [rbp+40h+pszPathIn], rax
0x1801343b0  lea     rdi, [rcx+138h]
0x1801343b7  mov     rax, [rdi]
0x1801343ba  mov     rbx, [rax+70h]
0x1801343be  lea     rcx, [rbp+40h+pszPathIn]
0x1801343c2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801343c7  mov     r9, rax
0x1801343ca  lea     r8d, [r13+1]
0x1801343ce  mov     rdx, r14
0x1801343d1  mov     rcx, rdi
0x1801343d4  mov     rax, rbx
0x1801343d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801343dc  test    eax, eax
0x1801343de  js      loc_1801344AE
0x1801343e4  xor     r12d, r12d
0x1801343e7  xor     r14d, r14d
0x1801343ea  mov     [rbp+40h+var_70], r12d
0x1801343ee  mov     [rsp+140h+var_E8], r12
0x1801343f3  mov     rdi, [rsp+140h+var_100]
0x1801343f8  cmp     dword ptr [rsp+140h+pv], r12d
0x1801343fd  jnz     short loc_180134439
0x1801343ff  mov     rdx, [rsp+140h+var_F8]
0x180134404  test    rdx, rdx
0x180134407  jz      loc_1801347A2
0x18013440d  lea     rcx, [rdi+30h]
0x180134411  mov     rax, [rcx]
0x180134414  lea     r8, [rsp+140h+var_E8]
0x180134419  mov     [rsp+140h+var_120], r8
0x18013441e  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf
0x180134425  xor     r8d, r8d
0x180134428  mov     rax, [rax+28h]
0x18013442c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134431  test    eax, eax
0x180134433  jns     loc_1801344D2
0x180134439  mov     rcx, rdi; this
0x18013443c  call    ?_EnsureKnownFolderManager@CFSFolder@@IEAAJXZ; CFSFolder::_EnsureKnownFolderManager(void)
0x180134441  test    eax, eax
0x180134443  js      short loc_1801344AE
0x180134445  mov     [rsp+140h+pv], 0
0x18013444e  mov     rdi, [rdi+290h]
0x180134455  mov     rax, [rdi]
0x180134458  mov     rbx, [rax+50h]
0x18013445c  lea     rcx, [rsp+140h+pv]
0x180134461  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180134466  lea     r9, [rsp+140h+pv]
0x18013446b  xor     r8d, r8d
0x18013446e  mov     rdx, [rbp+40h+pszPathIn]
0x180134472  mov     rcx, rdi
0x180134475  mov     rax, rbx
0x180134478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013447d  test    eax, eax
0x18013447f  jns     loc_180134754
0x180134485  mov     rcx, [rsp+140h+pv]
0x18013448a  test    rcx, rcx
0x18013448d  jz      short loc_1801344A5
0x18013448f  mov     [rsp+140h+pv], 0
0x180134498  mov     rax, [rcx]
0x18013449b  mov     rax, [rax+10h]
0x18013449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801344a4  nop
0x1801344a5  test    r14d, r14d
0x1801344a8  jnz     loc_180134572
0x1801344ae  test    r15, r15
0x1801344b1  jz      loc_1801345EE
0x1801344b7  mov     r9, r15; int *
0x1801344ba  mov     r8d, 104h; unsigned int
0x1801344c0  mov     rdx, rsi; unsigned __int16 *
0x1801344c3  mov     ecx, 3; enum SHSTOCKICONID
0x1801344c8  call    ?GetShellIconLocationParts@@YAJW4SHSTOCKICONID@@PEAGIPEAH@Z; GetShellIconLocationParts(SHSTOCKICONID,ushort *,uint,int *)
0x1801344cd  jmp     loc_1801345EE
0x1801344d2  mov     rcx, [rsp+140h+var_E8]
0x1801344d7  mov     [rsp+140h+pv], r12
0x1801344dc  mov     rax, [rcx]
0x1801344df  lea     rdx, [rsp+140h+pv]
0x1801344e4  mov     [rsp+140h+var_118], rdx
0x1801344e9  mov     dword ptr [rsp+140h+var_120], 2
0x1801344f1  xor     r9d, r9d
0x1801344f4  lea     r8, aIconresource; "IconResource"
0x1801344fb  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x180134502  mov     rax, [rax+30h]
0x180134506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013450b  test    eax, eax
0x18013450d  js      loc_18013462E
0x180134513  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x180134518  mov     edx, 104h; unsigned __int64
0x18013451d  mov     rcx, rsi; unsigned __int16 *
0x180134520  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180134525  mov     ebx, eax
0x180134527  mov     rcx, [rsp+140h+pv]; pv
0x18013452c  call    cs:__imp_CoTaskMemFree
0x180134533  nop     dword ptr [rax+rax+00h]
0x180134538  test    ebx, ebx
0x18013453a  js      loc_18013462E
0x180134540  mov     rcx, rsi; pszIconFile
0x180134543  call    cs:__imp_PathParseIconLocationW
0x18013454a  nop     dword ptr [rax+rax+00h]
0x18013454f  mov     r12d, eax
0x180134552  mov     r14d, 1
0x180134558  mov     rcx, [rsp+140h+var_E8]
0x18013455d  mov     rax, [rcx]
0x180134560  mov     rax, [rax+10h]
0x180134564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134569  test    r14d, r14d
0x18013456c  jz      loc_180134439
0x180134572  mov     r9, rsi; pszMore
0x180134575  mov     r8, [rbp+40h+pszPathIn]; pszPathIn
0x180134579  mov     edx, 104h; cchPathOut
0x18013457e  mov     rcx, rsi; pszPathOut
0x180134581  call    cs:__imp_PathCchCombine
0x180134588  nop     dword ptr [rax+rax+00h]
0x18013458d  test    eax, eax
0x18013458f  js      loc_1801344AE
0x180134595  cmp     [rbp+40h+var_70], 0
0x180134599  jnz     loc_180134749
0x18013459f  mov     [rbp+40h+var_70], 0
0x1801345a6  lea     r9, [rbp+40h+var_70]; unsigned int *
0x1801345aa  mov     r8d, 1; unsigned int
0x1801345b0  mov     rcx, rsi; unsigned __int16 *
0x1801345b3  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x1801345b8  test    eax, eax
0x1801345ba  js      loc_180134729
0x1801345c0  cmp     [rbp+40h+var_70], 0
0x1801345c4  jnz     loc_180134729
0x1801345ca  xor     edx, edx
0x1801345cc  mov     rcx, rsi
0x1801345cf  call    cs:__imp_PathFileExistsAndAttributesW
0x1801345d6  nop     dword ptr [rax+rax+00h]
0x1801345db  mov     r13d, eax
0x1801345de  test    eax, eax
0x1801345e0  jz      loc_1801344AE
0x1801345e6  test    r15, r15
0x1801345e9  jz      short loc_1801345EE
0x1801345eb  mov     [r15], r12d
0x1801345ee  mov     rcx, [rbp+40h+pszPathIn]; pv
0x1801345f2  test    rcx, rcx
0x1801345f5  jz      short loc_180134603
0x1801345f7  call    cs:__imp_CoTaskMemFree
0x1801345fe  nop     dword ptr [rax+rax+00h]
0x180134603  mov     eax, r13d
0x180134606  mov     rcx, [rbp+40h+var_40]
0x18013460a  xor     rcx, rsp; StackCookie
0x18013460d  call    __security_check_cookie
0x180134612  mov     rbx, [rsp+140h+arg_10]
0x18013461a  add     rsp, 110h
0x180134621  pop     r15
0x180134623  pop     r14
0x180134625  pop     r13
0x180134627  pop     r12
0x180134629  pop     rdi
0x18013462a  pop     rsi
0x18013462b  pop     rbp
0x18013462c  retn
0x18013462e  mov     rcx, [rsp+140h+var_E8]
0x180134633  mov     [rsp+140h+pv], r12
0x180134638  mov     rax, [rcx]
0x18013463b  lea     rdx, [rsp+140h+pv]
0x180134640  mov     [rsp+140h+var_118], rdx
0x180134645  mov     dword ptr [rsp+140h+var_120], 2
0x18013464d  xor     r9d, r9d
0x180134650  lea     r8, aIconfile; "IconFile"
0x180134657  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x18013465e  mov     rax, [rax+30h]
0x180134662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134667  test    eax, eax
0x180134669  js      loc_180134558
0x18013466f  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x180134674  mov     edx, 104h; unsigned __int64
0x180134679  mov     rcx, rsi; unsigned __int16 *
0x18013467c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180134681  mov     ebx, eax
0x180134683  mov     rcx, [rsp+140h+pv]; pv
0x180134688  call    cs:__imp_CoTaskMemFree
0x18013468f  nop     dword ptr [rax+rax+00h]
0x180134694  test    ebx, ebx
0x180134696  js      loc_180134558
0x18013469c  test    r15, r15
0x18013469f  jz      loc_180134552
0x1801346a5  mov     rcx, [rsp+140h+var_E8]
0x1801346aa  mov     [rsp+140h+pv], r12
0x1801346af  mov     rax, [rcx]
0x1801346b2  lea     r8, [rsp+140h+pv]
0x1801346b7  mov     [rsp+140h+var_118], r8
0x1801346bc  mov     dword ptr [rsp+140h+var_120], 2
0x1801346c4  xor     r9d, r9d
0x1801346c7  lea     r8, aIconindex; "IconIndex"
0x1801346ce  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x1801346d5  mov     rax, [rax+30h]
0x1801346d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801346de  test    eax, eax
0x1801346e0  js      loc_180134558
0x1801346e6  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x1801346eb  mov     edx, 10h; unsigned __int64
0x1801346f0  lea     rcx, [rbp+40h+var_60]; unsigned __int16 *
0x1801346f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801346f9  mov     ebx, eax
0x1801346fb  mov     rcx, [rsp+140h+pv]; pv
0x180134700  call    cs:__imp_CoTaskMemFree
0x180134707  nop     dword ptr [rax+rax+00h]
0x18013470c  test    ebx, ebx
0x18013470e  js      loc_180134558
0x180134714  lea     rcx, [rbp+40h+var_60]
0x180134718  call    cs:__imp__o__wtoi
0x18013471f  nop     dword ptr [rax+rax+00h]
0x180134724  jmp     loc_18013454F
0x180134729  lea     rcx, POLID_EnableShellShortcutIconRemotePath
0x180134730  call    cs:__imp_SHWindowsPolicy
0x180134737  nop     dword ptr [rax+rax+00h]
0x18013473c  test    eax, eax
0x18013473e  jz      loc_1801344AE
0x180134744  jmp     loc_1801345CA
0x180134749  mov     r13d, 1
0x18013474f  jmp     loc_1801345E6
0x180134754  mov     ebx, 1
0x180134759  mov     [rbp+40h+var_70], ebx
0x18013475c  xor     edx, edx; Val
0x18013475e  lea     r8d, [rbx+6Fh]; Size
0x180134762  lea     rcx, [rsp+140h+pKFD]; void *
0x180134767  call    memset_0
0x18013476c  mov     rcx, [rsp+140h+pv]
0x180134771  mov     rax, [rcx]
0x180134774  lea     rdx, [rsp+140h+pKFD]
0x180134779  mov     rax, [rax+58h]
0x18013477d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134782  test    eax, eax
0x180134784  js      loc_180134485
0x18013478a  mov     rcx, [rbp+40h+pKFD.pszIcon]
0x18013478e  test    rcx, rcx
0x180134791  jnz     short loc_1801347B4
0x180134793  lea     rcx, [rsp+140h+pKFD]; pKFD
0x180134798  call    FreeKnownFolderDefinitionFields
0x18013479d  jmp     loc_180134485
0x1801347a2  lea     rdx, [rsp+140h+var_E8]; struct ICachedPrivateProfile **
0x1801347a7  mov     rcx, rdi; this
0x1801347aa  call    ?_GetDesktopIni@CFSFolder@@IEAAJPEAPEAUICachedPrivateProfile@@@Z; CFSFolder::_GetDesktopIni(ICachedPrivateProfile * *)
0x1801347af  jmp     loc_180134431
0x1801347b4  mov     r8d, 104h
0x1801347ba  mov     rdx, rsi
0x1801347bd  call    cs:__imp_SHExpandEnvironmentStringsW
0x1801347c4  nop     dword ptr [rax+rax+00h]
0x1801347c9  test    eax, eax
0x1801347cb  jz      short loc_180134793
0x1801347cd  mov     rcx, rsi; pszIconFile
0x1801347d0  call    cs:__imp_PathParseIconLocationW
0x1801347d7  nop     dword ptr [rax+rax+00h]
0x1801347dc  mov     r12d, eax
0x1801347df  mov     r14d, ebx
0x1801347e2  jmp     short loc_180134793
```
