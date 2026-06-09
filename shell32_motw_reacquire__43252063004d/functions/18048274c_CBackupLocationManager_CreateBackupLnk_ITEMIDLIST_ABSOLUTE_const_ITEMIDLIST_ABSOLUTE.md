# CBackupLocationManager::CreateBackupLnk(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18048274c`
- end: `0x180482aaf`
- name: `?CreateBackupLnk@CBackupLocationManager@@QEBAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z`
- size: `867`
- prototype: `__int64 __fastcall(CBackupLocationManager *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b46c8`

## callees

- `0x180016018`
- `0x18001aae0`
- `0x180049790`
- `0x18013d930`
- `0x180249490`
- `0x18048274c`
- `0x180482dd4`
- `0x180487c2c`
- `0x180487ed4`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180482a1d`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x180482a1d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1804829c9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1804829f7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1804829c9`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1804829f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804829e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804829e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18048298f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18048298f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18048284a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180482a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180482a7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18048284a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180482a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180482a7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804827f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804827f0`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180482888`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180482888`
- `SHLWAPI!AssocQueryStringW` at `0x180482978`
- `SHLWAPI!AssocQueryStringW` at `0x180482978`
- `api-ms-win-shell-shellfolders-l1-1-0!PathCleanupSpec` at `0x1804829ab`
- `api-ms-win-shell-shellfolders-l1-1-0!PathCleanupSpec` at `0x1804829ab`
- `Windows.Storage!ILIsParentByPath` at `0x1804828be`
- `Windows.Storage!ILIsParentByPath` at `0x1804828be`
- `Windows.Storage!ILIsParent` at `0x1804828a3`
- `Windows.Storage!ILIsParent` at `0x1804828a3`
- `Windows.Storage!ILFree` at `0x1804828db`
- `Windows.Storage!ILFree` at `0x1804828db`

## pseudocode

```c
__int64 __fastcall CBackupLocationManager::CreateBackupLnk(
        CBackupLocationManager *this,
        const ITEMIDLIST *a2,
        struct _ITEMIDLIST_ABSOLUTE **a3)
{
  HRESULT v6; // ebx
  unsigned __int16 *v7; // r14
  int v8; // ebx
  int v9; // ebx
  HRESULT NewShortcut; // eax
  const WCHAR *FileNameW; // rax
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDir[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszAssoc[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszOut[264]; // [rsp+490h] [rbp+390h] BYREF

  v13 = 1614872576;
  *a3 = 0;
  v6 = SHGetNameAndFlagsW(a2, 0x8000u, pszAssoc, 0x104u, &v13);
  if ( v6 >= 0 )
  {
    v7 = 0;
    if ( (v13 & 0x40000000) == 0 )
      goto LABEL_28;
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv) < 0 )
      goto LABEL_28;
    pv[0] = 0;
    LODWORD(ppidl) = 0;
    v8 = 0;
    if ( (int)GetAppIDFromIDList(ppv, a2, pv, &ppidl) >= 0 )
    {
      LOBYTE(v8) = *(_WORD *)pv[0] != 0;
      if ( (_DWORD)ppidl && *(_WORD *)pv[0] )
        v7 = (unsigned __int16 *)pv[0];
      else
        CoTaskMemFree(pv[0]);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( !v8 )
      goto LABEL_28;
    ppidl = 0;
    if ( SHGetKnownFolderIDList(&FOLDERID_ImplicitAppShortcuts, 0x9000u, 0, &ppidl) >= 0 )
    {
      if ( ILIsParent(ppidl, a2, 0) || (v9 = 1, (unsigned int)ILIsParentByPath(ppidl, a2, 0)) )
        v9 = 0;
      ILFree(ppidl);
      if ( !v9 )
        goto LABEL_28;
    }
    v15 = 0;
    if ( CBackupLocationManager::GetBackupPath(this, &v15) < 0 )
    {
LABEL_28:
      v6 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)a2, a3);
      goto LABEL_29;
    }
    if ( (v13 & 0x10000) != 0 )
    {
      NewShortcut = CBackupLocationManager::_DuplicateShortcut(this, pszAssoc, v15, a3);
    }
    else
    {
      v6 = StringCchCopyW(pszDir, 0x104u, v15);
      if ( v6 < 0 )
        goto LABEL_27;
      LODWORD(ppidl) = 260;
      if ( AssocQueryStringW(0x42u, ASSOCSTR_FRIENDLYAPPNAME, pszAssoc, 0, pszOut, (DWORD *)&ppidl) < 0
        || !PathIsFileSpecW(pszOut)
        || PathCleanupSpec(pszDir, pszOut) < 0
        || PathCchAppend(pszDir, 0x104u, pszOut) < 0 )
      {
        FileNameW = PathFindFileNameW(pszAssoc);
        v6 = PathCchAppend(pszDir, 0x104u, FileNameW);
        if ( v6 < 0 )
          goto LABEL_27;
      }
      v6 = PathCchRenameExtension(pszDir, 0x104u, L".lnk");
      if ( v6 < 0 )
        goto LABEL_27;
      NewShortcut = CBackupLocationManager::_CreateNewShortcut(
                      this,
                      (const struct _ITEMIDLIST_ABSOLUTE *)a2,
                      pszAssoc,
                      v13,
                      pszDir,
                      v7,
                      a3);
    }
    v6 = NewShortcut;
LABEL_27:
    CoTaskMemFree(v15);
LABEL_29:
    CoTaskMemFree(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18048274c  push    rbp
0x18048274e  push    rbx
0x18048274f  push    rsi
0x180482750  push    rdi
0x180482751  push    r12
0x180482753  push    r13
0x180482755  push    r14
0x180482757  lea     rbp, [rsp-5B0h]
0x18048275f  sub     rsp, 6B0h
0x180482766  mov     rax, cs:__security_cookie
0x18048276d  xor     rax, rsp
0x180482770  mov     [rbp+5E0h+var_40], rax
0x180482777  mov     rdi, rdx
0x18048277a  mov     [rsp+6E0h+var_6A0], 60410000h
0x180482782  mov     rsi, r8
0x180482785  lea     rax, [rsp+6E0h+var_6A0]
0x18048278a  mov     r12, rcx
0x18048278d  mov     [rsp+6E0h+ppv], rax; unsigned int *
0x180482792  xor     r13d, r13d
0x180482795  mov     r9d, 104h; unsigned int
0x18048279b  mov     [r8], r13
0x18048279e  mov     edx, 8000h; unsigned int
0x1804827a3  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x1804827aa  mov     rcx, rdi; pidl
0x1804827ad  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x1804827b2  mov     ebx, eax
0x1804827b4  test    eax, eax
0x1804827b6  js      loc_180482A8B
0x1804827bc  test    [rsp+6E0h+var_6A0], 40000000h
0x1804827c4  mov     r14d, r13d
0x1804827c7  jz      loc_180482A6F
0x1804827cd  lea     rax, [rsp+6E0h+var_688]
0x1804827d2  mov     [rsp+6E0h+var_688], r13
0x1804827d7  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x1804827de  mov     [rsp+6E0h+ppv], rax; ppv
0x1804827e3  xor     edx, edx; pUnkOuter
0x1804827e5  lea     r8d, [r13+3]; dwClsContext
0x1804827e9  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x1804827f0  call    cs:__imp_CoCreateInstance
0x1804827f7  nop     dword ptr [rax+rax+00h]
0x1804827fc  test    eax, eax
0x1804827fe  js      loc_180482A6F
0x180482804  mov     rcx, [rsp+6E0h+var_688]
0x180482809  lea     r9, [rsp+6E0h+ppidl]
0x18048280e  lea     r8, [rsp+6E0h+pv]
0x180482813  mov     [rsp+6E0h+pv], r13
0x180482818  mov     rdx, rdi
0x18048281b  mov     dword ptr [rsp+6E0h+ppidl], r13d
0x180482820  mov     ebx, r13d
0x180482823  call    _GetAppIDFromIDList
0x180482828  test    eax, eax
0x18048282a  js      short loc_180482856
0x18048282c  mov     rcx, [rsp+6E0h+pv]; pv
0x180482831  cmp     [rcx], r13w
0x180482835  setnz   bl
0x180482838  cmp     dword ptr [rsp+6E0h+ppidl], r13d
0x18048283d  jz      short loc_18048284A
0x18048283f  cmp     [rcx], r13w
0x180482843  jz      short loc_18048284A
0x180482845  mov     r14, rcx
0x180482848  jmp     short loc_180482856
0x18048284a  call    cs:__imp_CoTaskMemFree
0x180482851  nop     dword ptr [rax+rax+00h]
0x180482856  mov     rcx, [rsp+6E0h+var_688]
0x18048285b  mov     rax, [rcx]
0x18048285e  mov     rax, [rax+10h]
0x180482862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180482867  test    ebx, ebx
0x180482869  jz      loc_180482A6F
0x18048286f  lea     r9, [rsp+6E0h+ppidl]; ppidl
0x180482874  mov     [rsp+6E0h+ppidl], r13
0x180482879  xor     r8d, r8d; hToken
0x18048287c  lea     rcx, FOLDERID_ImplicitAppShortcuts; rfid
0x180482883  mov     edx, 9000h; dwFlags
0x180482888  call    cs:__imp_SHGetKnownFolderIDList
0x18048288f  nop     dword ptr [rax+rax+00h]
0x180482894  test    eax, eax
0x180482896  js      short loc_1804828EF
0x180482898  mov     rcx, [rsp+6E0h+ppidl]; pidl1
0x18048289d  xor     r8d, r8d; fImmediate
0x1804828a0  mov     rdx, rdi; pidl2
0x1804828a3  call    cs:__imp_ILIsParent
0x1804828aa  nop     dword ptr [rax+rax+00h]
0x1804828af  test    eax, eax
0x1804828b1  jnz     short loc_1804828D3
0x1804828b3  mov     rcx, [rsp+6E0h+ppidl]
0x1804828b8  xor     r8d, r8d
0x1804828bb  mov     rdx, rdi
0x1804828be  call    cs:__imp_ILIsParentByPath
0x1804828c5  nop     dword ptr [rax+rax+00h]
0x1804828ca  mov     ebx, 1
0x1804828cf  test    eax, eax
0x1804828d1  jz      short loc_1804828D6
0x1804828d3  mov     ebx, r13d
0x1804828d6  mov     rcx, [rsp+6E0h+ppidl]; pidl
0x1804828db  call    cs:__imp_ILFree
0x1804828e2  nop     dword ptr [rax+rax+00h]
0x1804828e7  test    ebx, ebx
0x1804828e9  jz      loc_180482A6F
0x1804828ef  lea     rdx, [rsp+6E0h+var_690]; unsigned __int16 **
0x1804828f4  mov     [rsp+6E0h+var_690], r13
0x1804828f9  mov     rcx, r12; this
0x1804828fc  call    ?GetBackupPath@CBackupLocationManager@@QEBAJPEAPEAG@Z; CBackupLocationManager::GetBackupPath(ushort * *)
0x180482901  test    eax, eax
0x180482903  js      loc_180482A6F
0x180482909  test    [rsp+6E0h+var_6A0], 10000h
0x180482911  mov     r8, [rsp+6E0h+var_690]; unsigned __int16 *
0x180482916  jz      short loc_18048292F
0x180482918  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE **
0x18048291b  lea     rdx, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x180482922  mov     rcx, r12; this
0x180482925  call    ?_DuplicateShortcut@CBackupLocationManager@@AEBAJPEBG0PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CBackupLocationManager::_DuplicateShortcut(ushort const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x18048292a  jmp     loc_180482A5A
0x18048292f  mov     edx, 104h; unsigned __int64
0x180482934  lea     rcx, [rsp+6E0h+pszDir]; unsigned __int16 *
0x180482939  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18048293e  mov     ebx, eax
0x180482940  test    eax, eax
0x180482942  js      loc_180482A5C
0x180482948  xor     r9d, r9d; pszExtra
0x18048294b  lea     rax, [rsp+6E0h+ppidl]
0x180482950  mov     [rsp+6E0h+pcchOut], rax; pcchOut
0x180482955  lea     r8, [rbp+5E0h+pszAssoc]; pszAssoc
0x18048295c  lea     rax, [rbp+5E0h+pszOut]
0x180482963  mov     ebx, 104h
0x180482968  mov     dword ptr [rsp+6E0h+ppidl], ebx
0x18048296c  lea     edx, [r9+4]; str
0x180482970  mov     [rsp+6E0h+ppv], rax; pszOut
0x180482975  lea     ecx, [rdx+3Eh]; flags
0x180482978  call    cs:__imp_AssocQueryStringW
0x18048297f  nop     dword ptr [rax+rax+00h]
0x180482984  test    eax, eax
0x180482986  js      short loc_1804829D9
0x180482988  lea     rcx, [rbp+5E0h+pszOut]; pszPath
0x18048298f  call    cs:__imp_PathIsFileSpecW
0x180482996  nop     dword ptr [rax+rax+00h]
0x18048299b  test    eax, eax
0x18048299d  jz      short loc_1804829D9
0x18048299f  lea     rdx, [rbp+5E0h+pszOut]; pszSpec
0x1804829a6  lea     rcx, [rsp+6E0h+pszDir]; pszDir
0x1804829ab  call    cs:__imp_PathCleanupSpec
0x1804829b2  nop     dword ptr [rax+rax+00h]
0x1804829b7  test    eax, eax
0x1804829b9  js      short loc_1804829D9
0x1804829bb  lea     r8, [rbp+5E0h+pszOut]; pszMore
0x1804829c2  mov     edx, ebx; cchPath
0x1804829c4  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x1804829c9  call    cs:__imp_PathCchAppend
0x1804829d0  nop     dword ptr [rax+rax+00h]
0x1804829d5  test    eax, eax
0x1804829d7  jns     short loc_180482A0E
0x1804829d9  lea     rcx, [rbp+5E0h+pszAssoc]; pszPath
0x1804829e0  call    cs:__imp_PathFindFileNameW
0x1804829e7  nop     dword ptr [rax+rax+00h]
0x1804829ec  mov     rdx, rbx; cchPath
0x1804829ef  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x1804829f4  mov     r8, rax; pszMore
0x1804829f7  call    cs:__imp_PathCchAppend
0x1804829fe  nop     dword ptr [rax+rax+00h]
0x180482a03  mov     ebx, eax
0x180482a05  test    eax, eax
0x180482a07  js      short loc_180482A5C
0x180482a09  mov     ebx, 104h
0x180482a0e  lea     r8, aLnk; ".lnk"
0x180482a15  mov     rdx, rbx; cchPath
0x180482a18  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x180482a1d  call    cs:__imp_PathCchRenameExtension
0x180482a24  nop     dword ptr [rax+rax+00h]
0x180482a29  mov     ebx, eax
0x180482a2b  test    eax, eax
0x180482a2d  js      short loc_180482A5C
0x180482a2f  mov     r9d, [rsp+6E0h+var_6A0]; unsigned int
0x180482a34  lea     rax, [rsp+6E0h+pszDir]
0x180482a39  mov     [rsp+6E0h+var_6B0], rsi; struct _ITEMIDLIST_ABSOLUTE **
0x180482a3e  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x180482a45  mov     [rsp+6E0h+pcchOut], r14; unsigned __int16 *
0x180482a4a  mov     rdx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x180482a4d  mov     rcx, r12; this
0x180482a50  mov     [rsp+6E0h+ppv], rax; unsigned __int16 *
0x180482a55  call    ?_CreateNewShortcut@CBackupLocationManager@@AEBAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGK11PEAPEAU2@@Z; CBackupLocationManager::_CreateNewShortcut(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,ushort const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x180482a5a  mov     ebx, eax
0x180482a5c  mov     rcx, [rsp+6E0h+var_690]; pv
0x180482a61  call    cs:__imp_CoTaskMemFree
0x180482a68  nop     dword ptr [rax+rax+00h]
0x180482a6d  jmp     short loc_180482A7C
0x180482a6f  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x180482a72  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180482a75  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180482a7a  mov     ebx, eax
0x180482a7c  mov     rcx, r14; pv
0x180482a7f  call    cs:__imp_CoTaskMemFree
0x180482a86  nop     dword ptr [rax+rax+00h]
0x180482a8b  mov     eax, ebx
0x180482a8d  mov     rcx, [rbp+5E0h+var_40]
0x180482a94  xor     rcx, rsp; StackCookie
0x180482a97  call    __security_check_cookie
0x180482a9c  add     rsp, 6B0h
0x180482aa3  pop     r14
0x180482aa5  pop     r13
0x180482aa7  pop     r12
0x180482aa9  pop     rdi
0x180482aaa  pop     rsi
0x180482aab  pop     rbx
0x180482aac  pop     rbp
0x180482aad  retn
```
