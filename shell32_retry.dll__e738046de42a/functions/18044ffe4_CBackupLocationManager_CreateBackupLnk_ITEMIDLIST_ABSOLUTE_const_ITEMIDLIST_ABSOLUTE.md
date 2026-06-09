# CBackupLocationManager::CreateBackupLnk(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18044ffe4`
- end: `0x1804502ec`
- name: `?CreateBackupLnk@CBackupLocationManager@@QEBAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z`
- size: `776`
- prototype: `__int64 __fastcall(CBackupLocationManager *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801a0164`

## callees

- `0x18001bf10`
- `0x18001dc64`
- `0x180073b60`
- `0x18012cf30`
- `0x180233280`
- `0x18044ffe4`
- `0x180450600`
- `0x18045517c`
- `0x180455410`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18045022b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18045024d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18045022b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18045024d`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18045026d`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18045026d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1804501fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1804501fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18045023c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18045023c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804500dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804502ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804502c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804500dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804502ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804502c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180450088`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180450088`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180450114`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180450114`
- `SHLWAPI!AssocQueryStringW` at `0x1804501ec`
- `SHLWAPI!AssocQueryStringW` at `0x1804501ec`
- `api-ms-win-shell-shellfolders-l1-1-0!PathCleanupSpec` at `0x180450213`
- `api-ms-win-shell-shellfolders-l1-1-0!PathCleanupSpec` at `0x180450213`
- `Windows.Storage!ILIsParentByPath` at `0x18045013e`
- `Windows.Storage!ILIsParentByPath` at `0x18045013e`
- `Windows.Storage!ILIsParent` at `0x180450129`
- `Windows.Storage!ILIsParent` at `0x180450129`
- `Windows.Storage!ILFree` at `0x180450155`
- `Windows.Storage!ILFree` at `0x180450155`

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
0x18044ffe4  push    rbp
0x18044ffe6  push    rbx
0x18044ffe7  push    rsi
0x18044ffe8  push    rdi
0x18044ffe9  push    r12
0x18044ffeb  push    r13
0x18044ffed  push    r14
0x18044ffef  lea     rbp, [rsp-5B0h]
0x18044fff7  sub     rsp, 6B0h
0x18044fffe  mov     rax, cs:__security_cookie
0x180450005  xor     rax, rsp
0x180450008  mov     [rbp+5E0h+var_40], rax
0x18045000f  mov     rdi, rdx
0x180450012  mov     [rsp+6E0h+var_6A0], 60410000h
0x18045001a  mov     rsi, r8
0x18045001d  lea     rax, [rsp+6E0h+var_6A0]
0x180450022  mov     r12, rcx
0x180450025  mov     [rsp+6E0h+ppv], rax; unsigned int *
0x18045002a  xor     r13d, r13d
0x18045002d  mov     r9d, 104h; unsigned int
0x180450033  mov     [r8], r13
0x180450036  mov     edx, 8000h; unsigned int
0x18045003b  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x180450042  mov     rcx, rdi; pidl
0x180450045  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x18045004a  mov     ebx, eax
0x18045004c  test    eax, eax
0x18045004e  js      loc_1804502C9
0x180450054  test    [rsp+6E0h+var_6A0], 40000000h
0x18045005c  mov     r14d, r13d
0x18045005f  jz      loc_1804502B3
0x180450065  lea     rax, [rsp+6E0h+var_688]
0x18045006a  mov     [rsp+6E0h+var_688], r13
0x18045006f  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180450076  mov     [rsp+6E0h+ppv], rax; ppv
0x18045007b  xor     edx, edx; pUnkOuter
0x18045007d  lea     r8d, [r13+3]; dwClsContext
0x180450081  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180450088  call    cs:__imp_CoCreateInstance
0x18045008e  test    eax, eax
0x180450090  js      loc_1804502B3
0x180450096  mov     rcx, [rsp+6E0h+var_688]
0x18045009b  lea     r9, [rsp+6E0h+ppidl]
0x1804500a0  lea     r8, [rsp+6E0h+pv]
0x1804500a5  mov     [rsp+6E0h+pv], r13
0x1804500aa  mov     rdx, rdi
0x1804500ad  mov     dword ptr [rsp+6E0h+ppidl], r13d
0x1804500b2  mov     ebx, r13d
0x1804500b5  call    _GetAppIDFromIDList
0x1804500ba  test    eax, eax
0x1804500bc  js      short loc_1804500E2
0x1804500be  mov     rcx, [rsp+6E0h+pv]; pv
0x1804500c3  cmp     [rcx], r13w
0x1804500c7  setnz   bl
0x1804500ca  cmp     dword ptr [rsp+6E0h+ppidl], r13d
0x1804500cf  jz      short loc_1804500DC
0x1804500d1  cmp     [rcx], r13w
0x1804500d5  jz      short loc_1804500DC
0x1804500d7  mov     r14, rcx
0x1804500da  jmp     short loc_1804500E2
0x1804500dc  call    cs:__imp_CoTaskMemFree
0x1804500e2  mov     rcx, [rsp+6E0h+var_688]
0x1804500e7  mov     rax, [rcx]
0x1804500ea  mov     rax, [rax+10h]
0x1804500ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804500f3  test    ebx, ebx
0x1804500f5  jz      loc_1804502B3
0x1804500fb  lea     r9, [rsp+6E0h+ppidl]; ppidl
0x180450100  mov     [rsp+6E0h+ppidl], r13
0x180450105  xor     r8d, r8d; hToken
0x180450108  lea     rcx, FOLDERID_ImplicitAppShortcuts; rfid
0x18045010f  mov     edx, 9000h; dwFlags
0x180450114  call    cs:__imp_SHGetKnownFolderIDList
0x18045011a  test    eax, eax
0x18045011c  js      short loc_180450163
0x18045011e  mov     rcx, [rsp+6E0h+ppidl]; pidl1
0x180450123  xor     r8d, r8d; fImmediate
0x180450126  mov     rdx, rdi; pidl2
0x180450129  call    cs:__imp_ILIsParent
0x18045012f  test    eax, eax
0x180450131  jnz     short loc_18045014D
0x180450133  mov     rcx, [rsp+6E0h+ppidl]
0x180450138  xor     r8d, r8d
0x18045013b  mov     rdx, rdi
0x18045013e  call    cs:__imp_ILIsParentByPath
0x180450144  mov     ebx, 1
0x180450149  test    eax, eax
0x18045014b  jz      short loc_180450150
0x18045014d  mov     ebx, r13d
0x180450150  mov     rcx, [rsp+6E0h+ppidl]; pidl
0x180450155  call    cs:__imp_ILFree
0x18045015b  test    ebx, ebx
0x18045015d  jz      loc_1804502B3
0x180450163  lea     rdx, [rsp+6E0h+var_690]; unsigned __int16 **
0x180450168  mov     [rsp+6E0h+var_690], r13
0x18045016d  mov     rcx, r12; this
0x180450170  call    ?GetBackupPath@CBackupLocationManager@@QEBAJPEAPEAG@Z; CBackupLocationManager::GetBackupPath(ushort * *)
0x180450175  test    eax, eax
0x180450177  js      loc_1804502B3
0x18045017d  test    [rsp+6E0h+var_6A0], 10000h
0x180450185  mov     r8, [rsp+6E0h+var_690]; unsigned __int16 *
0x18045018a  jz      short loc_1804501A3
0x18045018c  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE **
0x18045018f  lea     rdx, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x180450196  mov     rcx, r12; this
0x180450199  call    ?_DuplicateShortcut@CBackupLocationManager@@AEBAJPEBG0PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CBackupLocationManager::_DuplicateShortcut(ushort const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x18045019e  jmp     loc_1804502A4
0x1804501a3  mov     edx, 104h; unsigned __int64
0x1804501a8  lea     rcx, [rsp+6E0h+pszDir]; unsigned __int16 *
0x1804501ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804501b2  mov     ebx, eax
0x1804501b4  test    eax, eax
0x1804501b6  js      loc_1804502A6
0x1804501bc  xor     r9d, r9d; pszExtra
0x1804501bf  lea     rax, [rsp+6E0h+ppidl]
0x1804501c4  mov     [rsp+6E0h+pcchOut], rax; pcchOut
0x1804501c9  lea     r8, [rbp+5E0h+pszAssoc]; pszAssoc
0x1804501d0  lea     rax, [rbp+5E0h+pszOut]
0x1804501d7  mov     ebx, 104h
0x1804501dc  mov     dword ptr [rsp+6E0h+ppidl], ebx
0x1804501e0  lea     edx, [r9+4]; str
0x1804501e4  mov     [rsp+6E0h+ppv], rax; pszOut
0x1804501e9  lea     ecx, [rdx+3Eh]; flags
0x1804501ec  call    cs:__imp_AssocQueryStringW
0x1804501f2  test    eax, eax
0x1804501f4  js      short loc_180450235
0x1804501f6  lea     rcx, [rbp+5E0h+pszOut]; pszPath
0x1804501fd  call    cs:__imp_PathIsFileSpecW
0x180450203  test    eax, eax
0x180450205  jz      short loc_180450235
0x180450207  lea     rdx, [rbp+5E0h+pszOut]; pszSpec
0x18045020e  lea     rcx, [rsp+6E0h+pszDir]; pszDir
0x180450213  call    cs:__imp_PathCleanupSpec
0x180450219  test    eax, eax
0x18045021b  js      short loc_180450235
0x18045021d  lea     r8, [rbp+5E0h+pszOut]; pszMore
0x180450224  mov     edx, ebx; cchPath
0x180450226  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18045022b  call    cs:__imp_PathCchAppend
0x180450231  test    eax, eax
0x180450233  jns     short loc_18045025E
0x180450235  lea     rcx, [rbp+5E0h+pszAssoc]; pszPath
0x18045023c  call    cs:__imp_PathFindFileNameW
0x180450242  mov     rdx, rbx; cchPath
0x180450245  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18045024a  mov     r8, rax; pszMore
0x18045024d  call    cs:__imp_PathCchAppend
0x180450253  mov     ebx, eax
0x180450255  test    eax, eax
0x180450257  js      short loc_1804502A6
0x180450259  mov     ebx, 104h
0x18045025e  lea     r8, aLnk; ".lnk"
0x180450265  mov     rdx, rbx; cchPath
0x180450268  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18045026d  call    cs:__imp_PathCchRenameExtension
0x180450273  mov     ebx, eax
0x180450275  test    eax, eax
0x180450277  js      short loc_1804502A6
0x180450279  mov     r9d, [rsp+6E0h+var_6A0]; unsigned int
0x18045027e  lea     rax, [rsp+6E0h+pszDir]
0x180450283  mov     [rsp+6E0h+var_6B0], rsi; struct _ITEMIDLIST_ABSOLUTE **
0x180450288  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x18045028f  mov     [rsp+6E0h+pcchOut], r14; unsigned __int16 *
0x180450294  mov     rdx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x180450297  mov     rcx, r12; this
0x18045029a  mov     [rsp+6E0h+ppv], rax; unsigned __int16 *
0x18045029f  call    ?_CreateNewShortcut@CBackupLocationManager@@AEBAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGK11PEAPEAU2@@Z; CBackupLocationManager::_CreateNewShortcut(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,ushort const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x1804502a4  mov     ebx, eax
0x1804502a6  mov     rcx, [rsp+6E0h+var_690]; pv
0x1804502ab  call    cs:__imp_CoTaskMemFree
0x1804502b1  jmp     short loc_1804502C0
0x1804502b3  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x1804502b6  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x1804502b9  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1804502be  mov     ebx, eax
0x1804502c0  mov     rcx, r14; pv
0x1804502c3  call    cs:__imp_CoTaskMemFree
0x1804502c9  mov     eax, ebx
0x1804502cb  mov     rcx, [rbp+5E0h+var_40]
0x1804502d2  xor     rcx, rsp; StackCookie
0x1804502d5  call    __security_check_cookie
0x1804502da  add     rsp, 6B0h
0x1804502e1  pop     r14
0x1804502e3  pop     r13
0x1804502e5  pop     r12
0x1804502e7  pop     rdi
0x1804502e8  pop     rsi
0x1804502e9  pop     rbx
0x1804502ea  pop     rbp
0x1804502eb  retn
```
