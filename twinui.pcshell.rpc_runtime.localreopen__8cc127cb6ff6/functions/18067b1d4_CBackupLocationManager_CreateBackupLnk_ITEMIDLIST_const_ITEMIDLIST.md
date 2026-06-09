# CBackupLocationManager::CreateBackupLnk(_ITEMIDLIST const *,_ITEMIDLIST * *)

- ea: `0x18067b1d4`
- end: `0x18067b4d7`
- name: `?CreateBackupLnk@CBackupLocationManager@@QEBAJPEFBU_ITEMIDLIST@@PEAPEFAU2@@Z`
- size: `771`
- prototype: `__int64 __fastcall(CBackupLocationManager *__hidden this, const struct _ITEMIDLIST *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180354cb4`

## callees

- `0x1800c7bc0`
- `0x180356360`
- `0x1805f6eb0`
- `0x1806780b0`
- `0x18067b1d4`
- `0x18067c478`
- `0x18067f318`
- `0x180683c0c`
- `0x180683ec8`
- `0x180684170`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18067b272`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18067b272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b2c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b4ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b2c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b4ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18067b428`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18067b428`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18067b3e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x18067b3e6`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18067b458`
- `api-ms-win-core-path-l1-1-0!PathCchRenameExtension` at `0x18067b458`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067b417`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067b43b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067b417`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067b43b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x18067b3d5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x18067b3d5`
- `SHELL32!__imp_ILFree` at `0x18067b33e`
- `SHELL32!__imp_ILFree` at `0x18067b33e`
- `Windows.Storage!PathCleanupSpec` at `0x18067b3fc`
- `Windows.Storage!PathCleanupSpec` at `0x18067b3fc`
- `Windows.Storage!ILIsParent` at `0x18067b313`
- `Windows.Storage!ILIsParent` at `0x18067b313`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067b2fe`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067b2fe`

## pseudocode

```c
__int64 __fastcall CBackupLocationManager::CreateBackupLnk(
        CBackupLocationManager *this,
        const struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST **a3,
        unsigned int a4)
{
  HRESULT v7; // ebx
  unsigned __int16 *v8; // r15
  int v9; // ebx
  int v10; // ebx
  HRESULT NewShortcut; // eax
  int v12; // r10d
  const WCHAR *FileNameW; // rax
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v17; // [rsp+50h] [rbp-B0h] BYREF
  struct IApplicationResolver *ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDir[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszAssoc[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszOut[264]; // [rsp+490h] [rbp+390h] BYREF

  v15 = 1614872576;
  *a3 = 0;
  v7 = SHGetNameAndFlagsW(a2, 0x8000u, pszAssoc, a4, &v15);
  if ( v7 >= 0 )
  {
    v8 = 0;
    if ( (v15 & 0x40000000) == 0 )
      goto LABEL_28;
    ppv = 0;
    if ( CoCreateInstance(
           &CLSID_StartMenuCacheAndAppResolver,
           0,
           3u,
           &GUID_de25675a_72de_44b4_9373_05170450c140,
           (LPVOID *)&ppv) < 0 )
      goto LABEL_28;
    pv = 0;
    LODWORD(ppidl) = 0;
    v9 = 0;
    if ( _GetAppIDFromIDList(ppv, a2, (unsigned __int16 **)&pv, (int *)&ppidl) >= 0 )
    {
      LOBYTE(v9) = *(_WORD *)pv != 0;
      if ( (_DWORD)ppidl && *(_WORD *)pv )
        v8 = (unsigned __int16 *)pv;
      else
        CoTaskMemFree(pv);
    }
    (*(void (__fastcall **)(struct IApplicationResolver *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( !v9 )
      goto LABEL_28;
    ppidl = 0;
    if ( SHGetKnownFolderIDList(&FOLDERID_ImplicitAppShortcuts, 0x9000u, 0, &ppidl) >= 0 )
    {
      if ( ILIsParent(ppidl, a2, 0) || (v10 = 1, CPinnedList::ILIsParentByPath(ppidl, a2, 0)) )
        v10 = 0;
      ILFree(ppidl);
      if ( !v10 )
        goto LABEL_28;
    }
    v17 = 0;
    if ( CBackupLocationManager::GetBackupPath(this, &v17) < 0 )
    {
LABEL_28:
      v7 = SHILClone(a2, a3);
      goto LABEL_29;
    }
    if ( (v15 & 0x10000) != 0 )
    {
      NewShortcut = CBackupLocationManager::_DuplicateShortcut(this, pszAssoc, v17, a3);
    }
    else
    {
      v7 = StringCchCopyW(pszDir, 0x104u, v17);
      if ( v7 < 0 )
        goto LABEL_27;
      LODWORD(ppidl) = v12;
      if ( AssocQueryStringW(0x42u, ASSOCSTR_FRIENDLYAPPNAME, pszAssoc, 0, pszOut, (DWORD *)&ppidl) < 0
        || !PathIsFileSpecW(pszOut)
        || PathCleanupSpec(pszDir, pszOut) < 0
        || PathCchAppend(pszDir, 0x104u, pszOut) < 0 )
      {
        FileNameW = PathFindFileNameW(pszAssoc);
        v7 = PathCchAppend(pszDir, 0x104u, FileNameW);
        if ( v7 < 0 )
          goto LABEL_27;
      }
      v7 = PathCchRenameExtension(pszDir, 0x104u, L".lnk");
      if ( v7 < 0 )
        goto LABEL_27;
      NewShortcut = CBackupLocationManager::_CreateNewShortcut(this, a2, pszAssoc, v15, pszDir, v8, a3);
    }
    v7 = NewShortcut;
LABEL_27:
    CoTaskMemFree(v17);
LABEL_29:
    CoTaskMemFree(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18067b1d4  push    rbp
0x18067b1d6  push    rbx
0x18067b1d7  push    rsi
0x18067b1d8  push    rdi
0x18067b1d9  push    r12
0x18067b1db  push    r13
0x18067b1dd  push    r15
0x18067b1df  lea     rbp, [rsp-5B0h]
0x18067b1e7  sub     rsp, 6B0h
0x18067b1ee  mov     rax, cs:__security_cookie
0x18067b1f5  xor     rax, rsp
0x18067b1f8  mov     [rbp+5E0h+var_40], rax
0x18067b1ff  mov     rdi, rdx
0x18067b202  mov     [rsp+6E0h+var_6A0], 60410000h
0x18067b20a  mov     rsi, r8
0x18067b20d  lea     rax, [rsp+6E0h+var_6A0]
0x18067b212  mov     r12, rcx
0x18067b215  mov     [rsp+6E0h+ppv], rax; unsigned int *
0x18067b21a  xor     r13d, r13d
0x18067b21d  mov     edx, 8000h; unsigned int
0x18067b222  mov     [r8], r13
0x18067b225  mov     rcx, rdi; pidl
0x18067b228  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x18067b22f  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18067b234  mov     ebx, eax
0x18067b236  test    eax, eax
0x18067b238  js      loc_18067B4B4
0x18067b23e  test    [rsp+6E0h+var_6A0], 40000000h
0x18067b246  mov     r15d, r13d
0x18067b249  jz      loc_18067B49E
0x18067b24f  lea     rax, [rsp+6E0h+var_688]
0x18067b254  mov     [rsp+6E0h+var_688], r13
0x18067b259  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x18067b260  mov     [rsp+6E0h+ppv], rax; ppv
0x18067b265  xor     edx, edx; pUnkOuter
0x18067b267  lea     r8d, [r13+3]; dwClsContext
0x18067b26b  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x18067b272  call    cs:__imp_CoCreateInstance
0x18067b278  test    eax, eax
0x18067b27a  js      loc_18067B49E
0x18067b280  mov     rcx, [rsp+6E0h+var_688]; struct IApplicationResolver *
0x18067b285  lea     r9, [rsp+6E0h+ppidl]; int *
0x18067b28a  lea     r8, [rsp+6E0h+pv]; unsigned __int16 **
0x18067b28f  mov     [rsp+6E0h+pv], r13
0x18067b294  mov     rdx, rdi; struct _ITEMIDLIST *
0x18067b297  mov     dword ptr [rsp+6E0h+ppidl], r13d
0x18067b29c  mov     ebx, r13d
0x18067b29f  call    ?_GetAppIDFromIDList@@YAJPEAUIApplicationResolver@@PEFBU_ITEMIDLIST@@PEAPEAGPEAH@Z; _GetAppIDFromIDList(IApplicationResolver *,_ITEMIDLIST const *,ushort * *,int *)
0x18067b2a4  test    eax, eax
0x18067b2a6  js      short loc_18067B2CC
0x18067b2a8  mov     rcx, [rsp+6E0h+pv]; pv
0x18067b2ad  cmp     [rcx], r13w
0x18067b2b1  setnz   bl
0x18067b2b4  cmp     dword ptr [rsp+6E0h+ppidl], r13d
0x18067b2b9  jz      short loc_18067B2C6
0x18067b2bb  cmp     [rcx], r13w
0x18067b2bf  jz      short loc_18067B2C6
0x18067b2c1  mov     r15, rcx
0x18067b2c4  jmp     short loc_18067B2CC
0x18067b2c6  call    cs:__imp_CoTaskMemFree
0x18067b2cc  mov     rcx, [rsp+6E0h+var_688]
0x18067b2d1  mov     rax, [rcx]
0x18067b2d4  mov     rax, [rax+10h]
0x18067b2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067b2dd  test    ebx, ebx
0x18067b2df  jz      loc_18067B49E
0x18067b2e5  lea     r9, [rsp+6E0h+ppidl]; ppidl
0x18067b2ea  mov     [rsp+6E0h+ppidl], r13
0x18067b2ef  xor     r8d, r8d; hToken
0x18067b2f2  lea     rcx, FOLDERID_ImplicitAppShortcuts; rfid
0x18067b2f9  mov     edx, 9000h; dwFlags
0x18067b2fe  call    cs:__imp_SHGetKnownFolderIDList
0x18067b304  test    eax, eax
0x18067b306  js      short loc_18067B34C
0x18067b308  mov     rcx, [rsp+6E0h+ppidl]; pidl1
0x18067b30d  xor     r8d, r8d; fImmediate
0x18067b310  mov     rdx, rdi; pidl2
0x18067b313  call    cs:__imp_ILIsParent
0x18067b319  test    eax, eax
0x18067b31b  jnz     short loc_18067B336
0x18067b31d  mov     rcx, [rsp+6E0h+ppidl]; struct _ITEMIDLIST *
0x18067b322  xor     r8d, r8d; int
0x18067b325  mov     rdx, rdi; struct _ITEMIDLIST *
0x18067b328  call    ?ILIsParentByPath@CPinnedList@@SAHPEFBU_ITEMIDLIST@@0H@Z; CPinnedList::ILIsParentByPath(_ITEMIDLIST const *,_ITEMIDLIST const *,int)
0x18067b32d  mov     ebx, 1
0x18067b332  test    eax, eax
0x18067b334  jz      short loc_18067B339
0x18067b336  mov     ebx, r13d
0x18067b339  mov     rcx, [rsp+6E0h+ppidl]; pidl
0x18067b33e  call    cs:__imp_ILFree
0x18067b344  test    ebx, ebx
0x18067b346  jz      loc_18067B49E
0x18067b34c  lea     rdx, [rsp+6E0h+var_690]; unsigned __int16 **
0x18067b351  mov     [rsp+6E0h+var_690], r13
0x18067b356  mov     rcx, r12; this
0x18067b359  call    ?GetBackupPath@CBackupLocationManager@@QEBAJPEAPEAG@Z; CBackupLocationManager::GetBackupPath(ushort * *)
0x18067b35e  test    eax, eax
0x18067b360  js      loc_18067B49E
0x18067b366  test    [rsp+6E0h+var_6A0], 10000h
0x18067b36e  mov     r8, [rsp+6E0h+var_690]; unsigned __int16 *
0x18067b373  jz      short loc_18067B38C
0x18067b375  mov     r9, rsi; struct _ITEMIDLIST **
0x18067b378  lea     rdx, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x18067b37f  mov     rcx, r12; this
0x18067b382  call    ?_DuplicateShortcut@CBackupLocationManager@@AEBAJPEBG0PEAPEFAU_ITEMIDLIST@@@Z; CBackupLocationManager::_DuplicateShortcut(ushort const *,ushort const *,_ITEMIDLIST * *)
0x18067b387  jmp     loc_18067B48F
0x18067b38c  mov     r10d, 104h
0x18067b392  lea     rcx, [rsp+6E0h+pszDir]; unsigned __int16 *
0x18067b397  mov     edx, r10d; unsigned __int64
0x18067b39a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18067b39f  mov     ebx, eax
0x18067b3a1  test    eax, eax
0x18067b3a3  js      loc_18067B491
0x18067b3a9  xor     r9d, r9d; pszExtra
0x18067b3ac  mov     dword ptr [rsp+6E0h+ppidl], r10d
0x18067b3b1  lea     rax, [rsp+6E0h+ppidl]
0x18067b3b6  mov     [rsp+6E0h+pcchOut], rax; pcchOut
0x18067b3bb  lea     r8, [rbp+5E0h+pszAssoc]; pszAssoc
0x18067b3c2  lea     rax, [rbp+5E0h+pszOut]
0x18067b3c9  lea     edx, [r9+4]; str
0x18067b3cd  mov     [rsp+6E0h+ppv], rax; pszOut
0x18067b3d2  lea     ecx, [rdx+3Eh]; flags
0x18067b3d5  call    cs:__imp_AssocQueryStringW
0x18067b3db  test    eax, eax
0x18067b3dd  js      short loc_18067B421
0x18067b3df  lea     rcx, [rbp+5E0h+pszOut]; pszPath
0x18067b3e6  call    cs:__imp_PathIsFileSpecW
0x18067b3ec  test    eax, eax
0x18067b3ee  jz      short loc_18067B421
0x18067b3f0  lea     rdx, [rbp+5E0h+pszOut]; pszSpec
0x18067b3f7  lea     rcx, [rsp+6E0h+pszDir]; pszDir
0x18067b3fc  call    cs:__imp_PathCleanupSpec
0x18067b402  test    eax, eax
0x18067b404  js      short loc_18067B421
0x18067b406  lea     r8, [rbp+5E0h+pszOut]; pszMore
0x18067b40d  mov     edx, 104h; cchPath
0x18067b412  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18067b417  call    cs:__imp_PathCchAppend
0x18067b41d  test    eax, eax
0x18067b41f  jns     short loc_18067B447
0x18067b421  lea     rcx, [rbp+5E0h+pszAssoc]; pszPath
0x18067b428  call    cs:__imp_PathFindFileNameW
0x18067b42e  mov     edx, 104h; cchPath
0x18067b433  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18067b438  mov     r8, rax; pszMore
0x18067b43b  call    cs:__imp_PathCchAppend
0x18067b441  mov     ebx, eax
0x18067b443  test    eax, eax
0x18067b445  js      short loc_18067B491
0x18067b447  lea     r8, pszExt; ".lnk"
0x18067b44e  mov     edx, 104h; cchPath
0x18067b453  lea     rcx, [rsp+6E0h+pszDir]; pszPath
0x18067b458  call    cs:__imp_PathCchRenameExtension
0x18067b45e  mov     ebx, eax
0x18067b460  test    eax, eax
0x18067b462  js      short loc_18067B491
0x18067b464  mov     r9d, [rsp+6E0h+var_6A0]; unsigned int
0x18067b469  lea     rax, [rsp+6E0h+pszDir]
0x18067b46e  mov     [rsp+6E0h+var_6B0], rsi; struct _ITEMIDLIST **
0x18067b473  lea     r8, [rbp+5E0h+pszAssoc]; unsigned __int16 *
0x18067b47a  mov     [rsp+6E0h+pcchOut], r15; unsigned __int16 *
0x18067b47f  mov     rdx, rdi; struct _ITEMIDLIST *
0x18067b482  mov     rcx, r12; this
0x18067b485  mov     [rsp+6E0h+ppv], rax; unsigned __int16 *
0x18067b48a  call    ?_CreateNewShortcut@CBackupLocationManager@@AEBAJPEFBU_ITEMIDLIST@@PEBGK11PEAPEFAU2@@Z; CBackupLocationManager::_CreateNewShortcut(_ITEMIDLIST const *,ushort const *,ulong,ushort const *,ushort const *,_ITEMIDLIST * *)
0x18067b48f  mov     ebx, eax
0x18067b491  mov     rcx, [rsp+6E0h+var_690]; pv
0x18067b496  call    cs:__imp_CoTaskMemFree
0x18067b49c  jmp     short loc_18067B4AB
0x18067b49e  mov     rdx, rsi; struct _ITEMIDLIST **
0x18067b4a1  mov     rcx, rdi; struct _ITEMIDLIST *
0x18067b4a4  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILClone(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18067b4a9  mov     ebx, eax
0x18067b4ab  mov     rcx, r15; pv
0x18067b4ae  call    cs:__imp_CoTaskMemFree
0x18067b4b4  mov     eax, ebx
0x18067b4b6  mov     rcx, [rbp+5E0h+var_40]
0x18067b4bd  xor     rcx, rsp; StackCookie
0x18067b4c0  call    __security_check_cookie
0x18067b4c5  add     rsp, 6B0h
0x18067b4cc  pop     r15
0x18067b4ce  pop     r13
0x18067b4d0  pop     r12
0x18067b4d2  pop     rdi
0x18067b4d3  pop     rsi
0x18067b4d4  pop     rbx
0x18067b4d5  pop     rbp
0x18067b4d6  retn
```
