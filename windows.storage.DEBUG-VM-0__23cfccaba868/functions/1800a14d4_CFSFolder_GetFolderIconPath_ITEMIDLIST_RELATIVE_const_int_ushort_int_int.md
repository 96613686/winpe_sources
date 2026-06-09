# CFSFolder::_GetFolderIconPath(_ITEMIDLIST_RELATIVE const *,int,ushort *,int,int *)

- ea: `0x1800a14d4`
- end: `0x1800a1916`
- name: `?_GetFolderIconPath@CFSFolder@@IEAAHPEFBU_ITEMIDLIST_RELATIVE@@HPEAGHPEAH@Z`
- size: `1090`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, int, unsigned __int16 *, int, int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180090dc0`
- `0x18016c090`
- `0x180516000`

## callees

- `0x18000d6cc`
- `0x1800a14d4`
- `0x1800a3080`
- `0x1800a5690`
- `0x1800a8ae0`
- `0x1800d13a0`
- `0x180201a20`
- `0x1802accc0`
- `0x1803148bc`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800a1861`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800a1861`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800a16e9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800a16e9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800a18fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800a18fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a16b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a1907`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a16b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800a1907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a16a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a17dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a184f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a16a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1753`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a17dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a184f`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800a1873`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800a1873`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1800a1731`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1800a1731`

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
0x1800a14d4  mov     [rsp-8+arg_10], rbx
0x1800a14d9  push    rbp
0x1800a14da  push    rsi
0x1800a14db  push    rdi
0x1800a14dc  push    r12
0x1800a14de  push    r13
0x1800a14e0  push    r14
0x1800a14e2  push    r15
0x1800a14e4  lea     rbp, [rsp-10h]
0x1800a14e9  sub     rsp, 110h
0x1800a14f0  mov     rax, cs:__security_cookie
0x1800a14f7  xor     rax, rsp
0x1800a14fa  mov     [rbp+40h+var_40], rax
0x1800a14fe  mov     rsi, r9
0x1800a1501  mov     dword ptr [rsp+140h+pv], r8d
0x1800a1506  mov     r14, rdx
0x1800a1509  mov     [rsp+140h+var_F8], rdx
0x1800a150e  mov     [rsp+140h+var_100], rcx
0x1800a1513  mov     r15, [rbp+40h+arg_28]
0x1800a1517  xor     eax, eax
0x1800a1519  mov     [r9], ax
0x1800a151d  xor     r13d, r13d
0x1800a1520  mov     [rbp+40h+pszPathIn], rax
0x1800a1524  lea     rdi, [rcx+138h]
0x1800a152b  mov     rax, [rdi]
0x1800a152e  mov     rbx, [rax+70h]
0x1800a1532  lea     rcx, [rbp+40h+pszPathIn]
0x1800a1536  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800a153b  mov     r9, rax
0x1800a153e  lea     r8d, [r13+1]
0x1800a1542  mov     rdx, r14
0x1800a1545  mov     rcx, rdi
0x1800a1548  mov     rax, rbx
0x1800a154b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1550  test    eax, eax
0x1800a1552  js      loc_1800A1622
0x1800a1558  xor     r12d, r12d
0x1800a155b  xor     r14d, r14d
0x1800a155e  mov     [rbp+40h+var_70], r12d
0x1800a1562  mov     [rsp+140h+var_E8], r12
0x1800a1567  mov     rdi, [rsp+140h+var_100]
0x1800a156c  cmp     dword ptr [rsp+140h+pv], r12d
0x1800a1571  jnz     short loc_1800A15AD
0x1800a1573  mov     rdx, [rsp+140h+var_F8]
0x1800a1578  test    rdx, rdx
0x1800a157b  jz      loc_1800A18DF
0x1800a1581  lea     rcx, [rdi+30h]
0x1800a1585  mov     rax, [rcx]
0x1800a1588  lea     r8, [rsp+140h+var_E8]
0x1800a158d  mov     [rsp+140h+var_120], r8
0x1800a1592  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf
0x1800a1599  xor     r8d, r8d
0x1800a159c  mov     rax, [rax+28h]
0x1800a15a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a15a5  test    eax, eax
0x1800a15a7  jns     loc_1800A1646
0x1800a15ad  mov     rcx, rdi; this
0x1800a15b0  call    ?_EnsureKnownFolderManager@CFSFolder@@IEAAJXZ; CFSFolder::_EnsureKnownFolderManager(void)
0x1800a15b5  test    eax, eax
0x1800a15b7  js      short loc_1800A1622
0x1800a15b9  mov     [rsp+140h+pv], 0
0x1800a15c2  mov     rdi, [rdi+290h]
0x1800a15c9  mov     rax, [rdi]
0x1800a15cc  mov     rbx, [rax+50h]
0x1800a15d0  lea     rcx, [rsp+140h+pv]
0x1800a15d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a15da  lea     r9, [rsp+140h+pv]
0x1800a15df  xor     r8d, r8d
0x1800a15e2  mov     rdx, [rbp+40h+pszPathIn]
0x1800a15e6  mov     rcx, rdi
0x1800a15e9  mov     rax, rbx
0x1800a15ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a15f1  test    eax, eax
0x1800a15f3  jns     loc_1800A1891
0x1800a15f9  mov     rcx, [rsp+140h+pv]
0x1800a15fe  test    rcx, rcx
0x1800a1601  jz      short loc_1800A1619
0x1800a1603  mov     [rsp+140h+pv], 0
0x1800a160c  mov     rax, [rcx]
0x1800a160f  mov     rax, [rax+10h]
0x1800a1613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1618  nop
0x1800a1619  test    r14d, r14d
0x1800a161c  jnz     loc_1800A16DA
0x1800a1622  test    r15, r15
0x1800a1625  jz      loc_1800A174A
0x1800a162b  mov     r9, r15; int *
0x1800a162e  mov     r8d, 104h; unsigned int
0x1800a1634  mov     rdx, rsi; unsigned __int16 *
0x1800a1637  mov     ecx, 3; enum SHSTOCKICONID
0x1800a163c  call    ?GetShellIconLocationParts@@YAJW4SHSTOCKICONID@@PEAGIPEAH@Z; GetShellIconLocationParts(SHSTOCKICONID,ushort *,uint,int *)
0x1800a1641  jmp     loc_1800A174A
0x1800a1646  mov     rcx, [rsp+140h+var_E8]
0x1800a164b  mov     [rsp+140h+pv], r12
0x1800a1650  mov     rax, [rcx]
0x1800a1653  lea     rdx, [rsp+140h+pv]
0x1800a1658  mov     [rsp+140h+var_118], rdx
0x1800a165d  mov     dword ptr [rsp+140h+var_120], 2
0x1800a1665  xor     r9d, r9d
0x1800a1668  lea     r8, aIconresource; "IconResource"
0x1800a166f  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x1800a1676  mov     rax, [rax+30h]
0x1800a167a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a167f  test    eax, eax
0x1800a1681  js      loc_1800A1783
0x1800a1687  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x1800a168c  mov     edx, 104h; unsigned __int64
0x1800a1691  mov     rcx, rsi; unsigned __int16 *
0x1800a1694  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1699  mov     ebx, eax
0x1800a169b  mov     rcx, [rsp+140h+pv]; pv
0x1800a16a0  call    cs:__imp_CoTaskMemFree
0x1800a16a6  test    ebx, ebx
0x1800a16a8  js      loc_1800A1783
0x1800a16ae  mov     rcx, rsi; pszIconFile
0x1800a16b1  call    cs:__imp_PathParseIconLocationW
0x1800a16b7  mov     r12d, eax
0x1800a16ba  mov     r14d, 1
0x1800a16c0  mov     rcx, [rsp+140h+var_E8]
0x1800a16c5  mov     rax, [rcx]
0x1800a16c8  mov     rax, [rax+10h]
0x1800a16cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a16d1  test    r14d, r14d
0x1800a16d4  jz      loc_1800A15AD
0x1800a16da  mov     r9, rsi; pszMore
0x1800a16dd  mov     r8, [rbp+40h+pszPathIn]; pszPathIn
0x1800a16e1  mov     edx, 104h; cchPathOut
0x1800a16e6  mov     rcx, rsi; pszPathOut
0x1800a16e9  call    cs:__imp_PathCchCombine
0x1800a16ef  test    eax, eax
0x1800a16f1  js      loc_1800A1622
0x1800a16f7  cmp     [rbp+40h+var_70], 0
0x1800a16fb  jnz     loc_1800A1886
0x1800a1701  mov     [rbp+40h+var_70], 0
0x1800a1708  lea     r9, [rbp+40h+var_70]; unsigned int *
0x1800a170c  mov     r8d, 1; unsigned int
0x1800a1712  mov     rcx, rsi; unsigned __int16 *
0x1800a1715  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x1800a171a  test    eax, eax
0x1800a171c  js      loc_1800A186C
0x1800a1722  cmp     [rbp+40h+var_70], 0
0x1800a1726  jnz     loc_1800A186C
0x1800a172c  xor     edx, edx
0x1800a172e  mov     rcx, rsi
0x1800a1731  call    cs:__imp_PathFileExistsAndAttributesW
0x1800a1737  mov     r13d, eax
0x1800a173a  test    eax, eax
0x1800a173c  jz      loc_1800A1622
0x1800a1742  test    r15, r15
0x1800a1745  jz      short loc_1800A174A
0x1800a1747  mov     [r15], r12d
0x1800a174a  mov     rcx, [rbp+40h+pszPathIn]; pv
0x1800a174e  test    rcx, rcx
0x1800a1751  jz      short loc_1800A1759
0x1800a1753  call    cs:__imp_CoTaskMemFree
0x1800a1759  mov     eax, r13d
0x1800a175c  mov     rcx, [rbp+40h+var_40]
0x1800a1760  xor     rcx, rsp; StackCookie
0x1800a1763  call    __security_check_cookie
0x1800a1768  mov     rbx, [rsp+140h+arg_10]
0x1800a1770  add     rsp, 110h
0x1800a1777  pop     r15
0x1800a1779  pop     r14
0x1800a177b  pop     r13
0x1800a177d  pop     r12
0x1800a177f  pop     rdi
0x1800a1780  pop     rsi
0x1800a1781  pop     rbp
0x1800a1782  retn
0x1800a1783  mov     rcx, [rsp+140h+var_E8]
0x1800a1788  mov     [rsp+140h+pv], r12
0x1800a178d  mov     rax, [rcx]
0x1800a1790  lea     rdx, [rsp+140h+pv]
0x1800a1795  mov     [rsp+140h+var_118], rdx
0x1800a179a  mov     dword ptr [rsp+140h+var_120], 2
0x1800a17a2  xor     r9d, r9d
0x1800a17a5  lea     r8, aIconfile; "IconFile"
0x1800a17ac  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x1800a17b3  mov     rax, [rax+30h]
0x1800a17b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a17bc  test    eax, eax
0x1800a17be  js      loc_1800A16C0
0x1800a17c4  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x1800a17c9  mov     edx, 104h; unsigned __int64
0x1800a17ce  mov     rcx, rsi; unsigned __int16 *
0x1800a17d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a17d6  mov     ebx, eax
0x1800a17d8  mov     rcx, [rsp+140h+pv]; pv
0x1800a17dd  call    cs:__imp_CoTaskMemFree
0x1800a17e3  test    ebx, ebx
0x1800a17e5  js      loc_1800A16C0
0x1800a17eb  test    r15, r15
0x1800a17ee  jz      loc_1800A16BA
0x1800a17f4  mov     rcx, [rsp+140h+var_E8]
0x1800a17f9  mov     [rsp+140h+pv], r12
0x1800a17fe  mov     rax, [rcx]
0x1800a1801  lea     r8, [rsp+140h+pv]
0x1800a1806  mov     [rsp+140h+var_118], r8
0x1800a180b  mov     dword ptr [rsp+140h+var_120], 2
0x1800a1813  xor     r9d, r9d
0x1800a1816  lea     r8, aIconindex; "IconIndex"
0x1800a181d  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x1800a1824  mov     rax, [rax+30h]
0x1800a1828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a182d  test    eax, eax
0x1800a182f  js      loc_1800A16C0
0x1800a1835  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x1800a183a  mov     edx, 10h; unsigned __int64
0x1800a183f  lea     rcx, [rbp+40h+var_60]; unsigned __int16 *
0x1800a1843  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1848  mov     ebx, eax
0x1800a184a  mov     rcx, [rsp+140h+pv]; pv
0x1800a184f  call    cs:__imp_CoTaskMemFree
0x1800a1855  test    ebx, ebx
0x1800a1857  js      loc_1800A16C0
0x1800a185d  lea     rcx, [rbp+40h+var_60]
0x1800a1861  call    cs:__imp__o__wtoi
0x1800a1867  jmp     loc_1800A16B7
0x1800a186c  lea     rcx, POLID_EnableShellShortcutIconRemotePath
0x1800a1873  call    cs:__imp_SHWindowsPolicy
0x1800a1879  test    eax, eax
0x1800a187b  jz      loc_1800A1622
0x1800a1881  jmp     loc_1800A172C
0x1800a1886  mov     r13d, 1
0x1800a188c  jmp     loc_1800A1742
0x1800a1891  mov     ebx, 1
0x1800a1896  mov     [rbp+40h+var_70], ebx
0x1800a1899  xor     edx, edx; Val
0x1800a189b  lea     r8d, [rbx+6Fh]; Size
0x1800a189f  lea     rcx, [rsp+140h+pKFD]; void *
0x1800a18a4  call    memset_0
0x1800a18a9  mov     rcx, [rsp+140h+pv]
0x1800a18ae  mov     rax, [rcx]
0x1800a18b1  lea     rdx, [rsp+140h+pKFD]
0x1800a18b6  mov     rax, [rax+58h]
0x1800a18ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18bf  test    eax, eax
0x1800a18c1  js      loc_1800A15F9
0x1800a18c7  mov     rcx, [rbp+40h+pKFD.pszIcon]
0x1800a18cb  test    rcx, rcx
0x1800a18ce  jnz     short loc_1800A18F1
0x1800a18d0  lea     rcx, [rsp+140h+pKFD]; pKFD
0x1800a18d5  call    FreeKnownFolderDefinitionFields
0x1800a18da  jmp     loc_1800A15F9
0x1800a18df  lea     rdx, [rsp+140h+var_E8]; struct ICachedPrivateProfile **
0x1800a18e4  mov     rcx, rdi; this
0x1800a18e7  call    ?_GetDesktopIni@CFSFolder@@IEAAJPEAPEAUICachedPrivateProfile@@@Z; CFSFolder::_GetDesktopIni(ICachedPrivateProfile * *)
0x1800a18ec  jmp     loc_1800A15A5
0x1800a18f1  mov     r8d, 104h
0x1800a18f7  mov     rdx, rsi
0x1800a18fa  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800a1900  test    eax, eax
0x1800a1902  jz      short loc_1800A18D0
0x1800a1904  mov     rcx, rsi; pszIconFile
0x1800a1907  call    cs:__imp_PathParseIconLocationW
0x1800a190d  mov     r12d, eax
0x1800a1910  mov     r14d, ebx
0x1800a1913  jmp     short loc_1800A18D0
```
