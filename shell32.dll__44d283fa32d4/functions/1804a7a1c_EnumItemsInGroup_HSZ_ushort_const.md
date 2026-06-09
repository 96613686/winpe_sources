# EnumItemsInGroup(HSZ__ *,ushort const *)

- ea: `0x1804a7a1c`
- end: `0x1804a7f56`
- name: `?EnumItemsInGroup@@YAPEAUHDDEDATA__@@PEAUHSZ__@@PEBG@Z`
- size: `1338`
- prototype: `HDDEDATA(HSZ, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1804a712c`

## callees

- `0x18001aae0`
- `0x18001b9a0`
- `0x18003a3e0`
- `0x18003e1e8`
- `0x18003ef10`
- `0x18003f7bc`
- `0x1800585dc`
- `0x180249490`
- `0x18024a53c`
- `0x1804a7a1c`
- `0x1804a8720`
- `0x1804a97f8`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804a7dbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804a7ecc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804a7dbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804a7ecc`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1804a7eb9`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1804a7eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804a7f0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804a7f0a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1804a7ad1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1804a7ad1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1804a7b56`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1804a7b56`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804a7a90`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804a7b27`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804a7a90`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804a7b27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a7da2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a7e94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a7da2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a7e94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804a7c18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804a7c18`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1804a7a73`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1804a7a73`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1804a7b0e`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1804a7b0e`
- `Windows.Storage!ILCreateFromPathW` at `0x1804a7b7f`
- `Windows.Storage!ILCreateFromPathW` at `0x1804a7b7f`
- `Windows.Storage!ILFree` at `0x1804a7cdb`
- `Windows.Storage!ILFree` at `0x1804a7d31`
- `Windows.Storage!ILFree` at `0x1804a7cdb`
- `Windows.Storage!ILFree` at `0x1804a7d31`
- `Windows.Storage!SHBindToObject` at `0x1804a7bba`
- `Windows.Storage!SHBindToObject` at `0x1804a7bba`
- `Windows.Storage!PathGetShortPath` at `0x1804a7d4d`
- `Windows.Storage!PathGetShortPath` at `0x1804a7d4d`
- `Windows.Storage!__imp_SHRestricted` at `0x1804a7aee`
- `Windows.Storage!__imp_SHRestricted` at `0x1804a7aee`

## pseudocode

```c
HDDEDATA __fastcall EnumItemsInGroup(HSZ a1, const unsigned __int16 *a2)
{
  HDDEDATA DataHandleFromUnicode; // r13
  HANDLE FirstFileW; // rax
  BOOL v5; // ebx
  struct _DSA *v6; // r14
  LPITEMIDLIST v7; // rsi
  int v8; // edi
  int v9; // r12d
  __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  _DWORD *ItemPtr; // rax
  SIZE_T v14; // rdx
  unsigned __int16 *v15; // rax
  struct IPersistFile *v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  __int64 v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  HSZ hszItem; // [rsp+60h] [rbp-A0h]
  struct IShellLinkW *v24; // [rsp+68h] [rbp-98h] BYREF
  struct IShellFolder *ppv; // [rsp+70h] [rbp-90h] BYREF
  LPITEMIDLIST pidl; // [rsp+78h] [rbp-88h] BYREF
  struct IPersistFile *v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+90h] [rbp-70h] BYREF
  _OWORD pitem[3]; // [rsp+98h] [rbp-68h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR String[1040]; // [rsp+530h] [rbp+430h] BYREF

  hszItem = a1;
  DataHandleFromUnicode = 0;
  if ( (int)SHGetFolderPathEx(&FOLDERID_Programs, 0, 0, pszPath, 260) < 0 )
    return DataHandleFromUnicode;
  PathCchAddBackslash(pszPath, 0x104u);
  if ( (int)StringCchCatW(pszPath, 0x104u, a2) < 0 )
    return DataHandleFromUnicode;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(pszPath, &FindFileData);
  v5 = 0;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( !SHRestricted(REST_NOCOMMONGROUPS) && SHGetSpecialFolderPathW(0, pszPath, 23, 0) )
    {
      PathCchAddBackslash(pszPath, 0x104u);
      v5 = (int)StringCchCatW(pszPath, 0x104u, a2) >= 0;
    }
    if ( !v5 )
      return DataHandleFromUnicode;
  }
  else
  {
    FindClose(FirstFileW);
  }
  v6 = DSA_Create(48, 0);
  if ( v6 )
  {
    v7 = ILCreateFromPathW(pszPath);
    if ( v7 )
    {
      v8 = 0;
      ppv = 0;
      v9 = 0;
      if ( SHBindToObject(0, v7, 0, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&ppv) >= 0 )
      {
        v28 = 0;
        if ( !((unsigned int (__fastcall *)(struct IShellFolder *, _QWORD, __int64, __int64 *))ppv->lpVtbl->EnumObjects)(
                ppv,
                0,
                64,
                &v28) )
        {
          v24 = 0;
          if ( CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, (LPVOID *)&v24) >= 0 )
          {
            v27 = 0;
            if ( ((__int64 (__fastcall *)(struct IShellLinkW *, GUID *, struct IPersistFile **))v24->lpVtbl->QueryInterface)(
                   v24,
                   &GUID_0000010b_0000_0000_c000_000000000046,
                   &v27) >= 0 )
            {
              pidl = 0;
              v9 = 1;
              v29 = 0;
              while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPITEMIDLIST *, int *))(*(_QWORD *)v28 + 24LL))(
                         v28,
                         1,
                         &pidl,
                         &v29)
                   && v29 == 1 )
              {
                memset(pitem, 0, sizeof(pitem));
                if ( (unsigned int)GroupItem_GetLinkInfo(
                                     pszPath,
                                     (struct GROUPITEM *)pitem,
                                     (const struct _ITEMID_CHILD *)pidl,
                                     ppv,
                                     v24,
                                     v27) )
                  DSA_InsertItem(v6, v8++, pitem);
                ILFree(pidl);
              }
              ((void (__fastcall *)(struct IPersistFile *))v27->lpVtbl->Release)(v27);
            }
            ((void (__fastcall *)(struct IShellLinkW *))v24->lpVtbl->Release)(v24);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        ((void (__fastcall *)(struct IShellFolder *))ppv->lpVtbl->Release)(ppv);
      }
      ILFree(v7);
      if ( v9 )
      {
        PathGetShortPath(pszPath);
        LODWORD(v17) = v8;
        if ( (int)StringCchPrintfW(String, 0x410u, L"\"%s\",%s,%d,%d,%d\r\n", a2, pszPath, v17, 1, v5) >= 0 )
        {
          v10 = (unsigned int)(lstrlenW(String) + 1);
          v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v10);
          v12 = v11;
          if ( v11 )
          {
            StringCchCopyW(v11, (unsigned int)v10, String);
            while ( --v8 >= 0 )
            {
              ItemPtr = DSA_GetItemPtr(v6, v8);
              LODWORD(v22) = ItemPtr[9];
              LODWORD(v21) = *((unsigned __int16 *)ItemPtr + 20);
              LODWORD(v20) = ItemPtr[8];
              LODWORD(v19) = ((v8 / 7) << 6) + 32;
              LODWORD(v18) = ((v8 % 7) << 6) + 32;
              if ( (int)StringCchPrintfW(
                          String,
                          0x410u,
                          L"\"%s\",\"%s\",%s,%s,%d,%d,%d,%d,%d\r\n",
                          *(_QWORD *)ItemPtr,
                          *((_QWORD *)ItemPtr + 1),
                          *((_QWORD *)ItemPtr + 2),
                          *((_QWORD *)ItemPtr + 3),
                          v18,
                          v19,
                          v20,
                          v21,
                          v22,
                          hszItem) < 0 )
                goto LABEL_38;
              v10 = (unsigned int)(lstrlenW(String) + 1 + v10);
              v14 = 2 * v10;
              v15 = (unsigned __int16 *)(v12 ? LocalReAlloc(v12, v14, 0x42u) : LocalAlloc(0x40u, v14));
              if ( !v15 )
                goto LABEL_38;
              v12 = v15;
              StringCchCatW(v15, (unsigned int)v10, String);
            }
            DataHandleFromUnicode = _DdeCreateDataHandleFromUnicode(v12, hszItem);
LABEL_38:
            LocalFree(v12);
          }
        }
      }
    }
    DSA_DestroyCallback(v6, DSA_DestroyGroupCallback, 0);
  }
  return DataHandleFromUnicode;
}

```

## disassembly

```asm
0x1804a7a1c  mov     [rsp-8+arg_10], rbx
0x1804a7a21  push    rbp
0x1804a7a22  push    rsi
0x1804a7a23  push    rdi
0x1804a7a24  push    r12
0x1804a7a26  push    r13
0x1804a7a28  push    r14
0x1804a7a2a  push    r15
0x1804a7a2c  lea     rbp, [rsp-0C60h]
0x1804a7a34  sub     rsp, 0D60h
0x1804a7a3b  mov     rax, cs:__security_cookie
0x1804a7a42  xor     rax, rsp
0x1804a7a45  mov     [rbp+0C90h+var_40], rax
0x1804a7a4c  mov     r15, rdx
0x1804a7a4f  mov     [rsp+0D90h+hszItem], rcx
0x1804a7a54  mov     esi, 104h
0x1804a7a59  lea     rcx, FOLDERID_Programs
0x1804a7a60  xor     edx, edx
0x1804a7a62  mov     dword ptr [rsp+0D90h+ppv], esi
0x1804a7a66  lea     r9, [rbp+0C90h+pszPath]
0x1804a7a6d  xor     r8d, r8d
0x1804a7a70  xor     r13d, r13d
0x1804a7a73  call    cs:__imp_SHGetFolderPathEx
0x1804a7a7a  nop     dword ptr [rax+rax+00h]
0x1804a7a7f  test    eax, eax
0x1804a7a81  js      loc_1804A7F28
0x1804a7a87  mov     edx, esi; cchPath
0x1804a7a89  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x1804a7a90  call    cs:__imp_PathCchAddBackslash
0x1804a7a97  nop     dword ptr [rax+rax+00h]
0x1804a7a9c  mov     r8, r15; unsigned __int16 *
0x1804a7a9f  lea     rcx, [rbp+0C90h+pszPath]; unsigned __int16 *
0x1804a7aa6  mov     edx, esi; unsigned __int64
0x1804a7aa8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1804a7aad  test    eax, eax
0x1804a7aaf  js      loc_1804A7F28
0x1804a7ab5  xor     edx, edx; Val
0x1804a7ab7  lea     rcx, [rbp+0C90h+FindFileData]; void *
0x1804a7abb  mov     r8d, 250h; Size
0x1804a7ac1  call    memset_0
0x1804a7ac6  lea     rdx, [rbp+0C90h+FindFileData]; lpFindFileData
0x1804a7aca  lea     rcx, [rbp+0C90h+pszPath]; lpFileName
0x1804a7ad1  call    cs:__imp_FindFirstFileW
0x1804a7ad8  nop     dword ptr [rax+rax+00h]
0x1804a7add  xor     ebx, ebx
0x1804a7adf  lea     edi, [r13+1]
0x1804a7ae3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804a7ae7  jnz     short loc_1804A7B53
0x1804a7ae9  mov     ecx, 400000h; rest
0x1804a7aee  call    cs:__imp_SHRestricted
0x1804a7af5  nop     dword ptr [rax+rax+00h]
0x1804a7afa  test    eax, eax
0x1804a7afc  jnz     short loc_1804A7B49
0x1804a7afe  xor     r9d, r9d; fCreate
0x1804a7b01  lea     r8d, [r13+17h]; csidl
0x1804a7b05  lea     rdx, [rbp+0C90h+pszPath]; pszPath
0x1804a7b0c  xor     ecx, ecx; hwnd
0x1804a7b0e  call    cs:__imp_SHGetSpecialFolderPathW
0x1804a7b15  nop     dword ptr [rax+rax+00h]
0x1804a7b1a  test    eax, eax
0x1804a7b1c  jz      short loc_1804A7B49
0x1804a7b1e  mov     edx, esi; cchPath
0x1804a7b20  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x1804a7b27  call    cs:__imp_PathCchAddBackslash
0x1804a7b2e  nop     dword ptr [rax+rax+00h]
0x1804a7b33  mov     r8, r15; unsigned __int16 *
0x1804a7b36  lea     rcx, [rbp+0C90h+pszPath]; unsigned __int16 *
0x1804a7b3d  mov     edx, esi; unsigned __int64
0x1804a7b3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1804a7b44  test    eax, eax
0x1804a7b46  cmovns  ebx, edi
0x1804a7b49  test    ebx, ebx
0x1804a7b4b  jz      loc_1804A7F28
0x1804a7b51  jmp     short loc_1804A7B62
0x1804a7b53  mov     rcx, rax; hFindFile
0x1804a7b56  call    cs:__imp_FindClose
0x1804a7b5d  nop     dword ptr [rax+rax+00h]
0x1804a7b62  xor     edx, edx; cItemGrow
0x1804a7b64  lea     ecx, [rdx+30h]; cbItem
0x1804a7b67  call    DSA_Create
0x1804a7b6c  mov     r14, rax
0x1804a7b6f  test    rax, rax
0x1804a7b72  jz      loc_1804A7F28
0x1804a7b78  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x1804a7b7f  call    cs:__imp_ILCreateFromPathW
0x1804a7b86  nop     dword ptr [rax+rax+00h]
0x1804a7b8b  mov     rsi, rax
0x1804a7b8e  test    rax, rax
0x1804a7b91  jz      loc_1804A7F16
0x1804a7b97  lea     rax, [rsp+0D90h+var_D20]
0x1804a7b9c  xor     edi, edi
0x1804a7b9e  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1804a7ba5  mov     [rsp+0D90h+var_D20], rdi
0x1804a7baa  xor     r8d, r8d; pbc
0x1804a7bad  mov     [rsp+0D90h+ppv], rax; ppv
0x1804a7bb2  mov     rdx, rsi; pidl
0x1804a7bb5  xor     ecx, ecx; psf
0x1804a7bb7  xor     r12d, r12d
0x1804a7bba  call    cs:__imp_SHBindToObject
0x1804a7bc1  nop     dword ptr [rax+rax+00h]
0x1804a7bc6  test    eax, eax
0x1804a7bc8  js      loc_1804A7D2E
0x1804a7bce  mov     rcx, [rsp+0D90h+var_D20]
0x1804a7bd3  lea     r9, [rbp+0C90h+var_D08]
0x1804a7bd7  mov     [rbp+0C90h+var_D08], rdi
0x1804a7bdb  lea     r8d, [rdi+40h]
0x1804a7bdf  xor     edx, edx
0x1804a7be1  mov     rax, [rcx]
0x1804a7be4  mov     rax, [rax+20h]
0x1804a7be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7bed  test    eax, eax
0x1804a7bef  jnz     loc_1804A7D1D
0x1804a7bf5  lea     rax, [rsp+0D90h+var_D28]
0x1804a7bfa  mov     [rsp+0D90h+var_D28], rdi
0x1804a7bff  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x1804a7c06  mov     [rsp+0D90h+ppv], rax; ppv
0x1804a7c0b  xor     edx, edx; pUnkOuter
0x1804a7c0d  lea     r8d, [rdi+1]; dwClsContext
0x1804a7c11  lea     rcx, CLSID_ShellLink; rclsid
0x1804a7c18  call    cs:__imp_CoCreateInstance
0x1804a7c1f  nop     dword ptr [rax+rax+00h]
0x1804a7c24  test    eax, eax
0x1804a7c26  js      loc_1804A7D0D
0x1804a7c2c  mov     rcx, [rsp+0D90h+var_D28]
0x1804a7c31  lea     r8, [rbp+0C90h+var_D10]
0x1804a7c35  mov     [rbp+0C90h+var_D10], rdi
0x1804a7c39  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x1804a7c40  mov     rax, [rcx]
0x1804a7c43  mov     rax, [rax]
0x1804a7c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7c4b  test    eax, eax
0x1804a7c4d  js      loc_1804A7CFC
0x1804a7c53  mov     [rsp+0D90h+pidl], rdi
0x1804a7c58  lea     r12d, [rdi+1]
0x1804a7c5c  mov     [rbp+0C90h+var_D00], edi
0x1804a7c5f  mov     rcx, [rbp+0C90h+var_D08]
0x1804a7c63  lea     r9, [rbp+0C90h+var_D00]
0x1804a7c67  lea     r8, [rsp+0D90h+pidl]
0x1804a7c6c  mov     edx, r12d
0x1804a7c6f  mov     rax, [rcx]
0x1804a7c72  mov     rax, [rax+18h]
0x1804a7c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7c7b  test    eax, eax
0x1804a7c7d  jnz     short loc_1804A7CEC
0x1804a7c7f  cmp     [rbp+0C90h+var_D00], r12d
0x1804a7c83  jnz     short loc_1804A7CEC
0x1804a7c85  mov     rax, [rbp+0C90h+var_D10]
0x1804a7c89  lea     rdx, [rbp+0C90h+pitem]; struct GROUPITEM *
0x1804a7c8d  mov     r9, [rsp+0D90h+var_D20]; struct IShellFolder *
0x1804a7c92  lea     rcx, [rbp+0C90h+pszPath]; pszPathIn
0x1804a7c99  mov     r8, [rsp+0D90h+pidl]; struct _ITEMID_CHILD *
0x1804a7c9e  xorps   xmm0, xmm0
0x1804a7ca1  mov     [rsp+0D90h+var_D68], rax; struct IPersistFile *
0x1804a7ca6  mov     rax, [rsp+0D90h+var_D28]
0x1804a7cab  mov     [rsp+0D90h+ppv], rax; struct IShellLinkW *
0x1804a7cb0  movups  [rbp+0C90h+pitem], xmm0
0x1804a7cb4  movups  [rbp+0C90h+var_CE8], xmm0
0x1804a7cb8  movups  [rbp+0C90h+var_CD8], xmm0
0x1804a7cbc  call    ?GroupItem_GetLinkInfo@@YAHPEBGPEAUGROUPITEM@@PEFBU_ITEMID_CHILD@@PEAUIShellFolder@@PEAUIShellLinkW@@PEAUIPersistFile@@@Z; GroupItem_GetLinkInfo(ushort const *,GROUPITEM *,_ITEMID_CHILD const *,IShellFolder *,IShellLinkW *,IPersistFile *)
0x1804a7cc1  test    eax, eax
0x1804a7cc3  jz      short loc_1804A7CD6
0x1804a7cc5  lea     r8, [rbp+0C90h+pitem]; pitem
0x1804a7cc9  mov     edx, edi; i
0x1804a7ccb  mov     rcx, r14; hdsa
0x1804a7cce  call    DSA_InsertItem
0x1804a7cd3  add     edi, r12d
0x1804a7cd6  mov     rcx, [rsp+0D90h+pidl]; pidl
0x1804a7cdb  call    cs:__imp_ILFree
0x1804a7ce2  nop     dword ptr [rax+rax+00h]
0x1804a7ce7  jmp     loc_1804A7C5F
0x1804a7cec  mov     rcx, [rbp+0C90h+var_D10]
0x1804a7cf0  mov     rax, [rcx]
0x1804a7cf3  mov     rax, [rax+10h]
0x1804a7cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7cfc  mov     rcx, [rsp+0D90h+var_D28]
0x1804a7d01  mov     rax, [rcx]
0x1804a7d04  mov     rax, [rax+10h]
0x1804a7d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7d0d  mov     rcx, [rbp+0C90h+var_D08]
0x1804a7d11  mov     rax, [rcx]
0x1804a7d14  mov     rax, [rax+10h]
0x1804a7d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7d1d  mov     rcx, [rsp+0D90h+var_D20]
0x1804a7d22  mov     rax, [rcx]
0x1804a7d25  mov     rax, [rax+10h]
0x1804a7d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a7d2e  mov     rcx, rsi; pidl
0x1804a7d31  call    cs:__imp_ILFree
0x1804a7d38  nop     dword ptr [rax+rax+00h]
0x1804a7d3d  test    r12d, r12d
0x1804a7d40  jz      loc_1804A7F16
0x1804a7d46  lea     rcx, [rbp+0C90h+pszPath]; pszLongPath
0x1804a7d4d  call    cs:__imp_PathGetShortPath
0x1804a7d54  nop     dword ptr [rax+rax+00h]
0x1804a7d59  mov     dword ptr [rsp+0D90h+var_D58], ebx
0x1804a7d5d  lea     rax, [rbp+0C90h+pszPath]
0x1804a7d64  mov     r12d, 1
0x1804a7d6a  lea     r8, aSSDDD; "\"%s\",%s,%d,%d,%d\r\n"
0x1804a7d71  mov     dword ptr [rsp+0D90h+var_D60], r12d
0x1804a7d76  lea     rcx, [rbp+0C90h+String]; unsigned __int16 *
0x1804a7d7d  mov     dword ptr [rsp+0D90h+var_D68], edi
0x1804a7d81  mov     r9, r15
0x1804a7d84  mov     edx, 410h; unsigned __int64
0x1804a7d89  mov     [rsp+0D90h+ppv], rax
0x1804a7d8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1804a7d93  test    eax, eax
0x1804a7d95  js      loc_1804A7F16
0x1804a7d9b  lea     rcx, [rbp+0C90h+String]; lpString
0x1804a7da2  call    cs:__imp_lstrlenW
0x1804a7da9  nop     dword ptr [rax+rax+00h]
0x1804a7dae  lea     ecx, [r12+3Fh]; uFlags
0x1804a7db3  lea     esi, [r12+rax]
0x1804a7db7  lea     rdx, [rsi+rsi]; uBytes
0x1804a7dbb  mov     r15d, esi
0x1804a7dbe  call    cs:__imp_LocalAlloc
0x1804a7dc5  nop     dword ptr [rax+rax+00h]
0x1804a7dca  mov     rbx, rax
0x1804a7dcd  test    rax, rax
0x1804a7dd0  jz      loc_1804A7F16
0x1804a7dd6  lea     r8, [rbp+0C90h+String]; unsigned __int16 *
0x1804a7ddd  mov     edx, r15d; unsigned __int64
0x1804a7de0  mov     rcx, rax; unsigned __int16 *
0x1804a7de3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804a7de8  sub     edi, r12d
0x1804a7deb  test    edi, edi
0x1804a7ded  js      loc_1804A7EF7
0x1804a7df3  mov     edx, edi; i
0x1804a7df5  mov     rcx, r14; hdsa
0x1804a7df8  call    DSA_GetItemPtr
0x1804a7dfd  mov     r10, rax
0x1804a7e00  mov     eax, 92492493h
0x1804a7e05  imul    edi
0x1804a7e07  lea     r8d, [rdi+rdx]
0x1804a7e0b  movzx   edx, word ptr [r10+28h]
0x1804a7e10  sar     r8d, 2
0x1804a7e14  mov     ecx, r8d
0x1804a7e17  shr     ecx, 1Fh
0x1804a7e1a  add     r8d, ecx
0x1804a7e1d  mov     ecx, edi
0x1804a7e1f  imul    eax, r8d, 7
0x1804a7e23  mov     r9d, r8d
0x1804a7e26  shl     r9d, 6
0x1804a7e2a  lea     r8, aSSSSDDDDD; "\"%s\",\"%s\",%s,%s,%d,%d,%d,%d,%d\r\n"
0x1804a7e31  add     r9d, 20h ; ' '
0x1804a7e35  sub     ecx, eax
0x1804a7e37  mov     eax, [r10+24h]
0x1804a7e3b  mov     dword ptr [rsp+0D90h+var_D38], eax
0x1804a7e3f  mov     eax, [r10+20h]
0x1804a7e43  mov     dword ptr [rsp+0D90h+var_D40], edx
0x1804a7e47  mov     edx, 410h; unsigned __int64
0x1804a7e4c  mov     dword ptr [rsp+0D90h+var_D48], eax
0x1804a7e50  mov     rax, [r10+18h]
0x1804a7e54  mov     dword ptr [rsp+0D90h+var_D50], r9d
0x1804a7e59  mov     r9, [r10]
0x1804a7e5c  shl     ecx, 6
0x1804a7e5f  add     ecx, 20h ; ' '
0x1804a7e62  mov     dword ptr [rsp+0D90h+var_D58], ecx
0x1804a7e66  lea     rcx, [rbp+0C90h+String]; unsigned __int16 *
0x1804a7e6d  mov     [rsp+0D90h+var_D60], rax
0x1804a7e72  mov     rax, [r10+10h]
0x1804a7e76  mov     [rsp+0D90h+var_D68], rax
0x1804a7e7b  mov     rax, [r10+8]
0x1804a7e7f  mov     [rsp+0D90h+ppv], rax
0x1804a7e84  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1804a7e89  test    eax, eax
0x1804a7e8b  js      short loc_1804A7F07
0x1804a7e8d  lea     rcx, [rbp+0C90h+String]; lpString
0x1804a7e94  call    cs:__imp_lstrlenW
0x1804a7e9b  nop     dword ptr [rax+rax+00h]
0x1804a7ea0  inc     eax
0x1804a7ea2  add     esi, eax
0x1804a7ea4  mov     r15d, esi
0x1804a7ea7  lea     rdx, [rsi+rsi]; uBytes
0x1804a7eab  test    rbx, rbx
0x1804a7eae  jz      short loc_1804A7EC7
0x1804a7eb0  mov     r8d, 42h ; 'B'; uFlags
0x1804a7eb6  mov     rcx, rbx; hMem
0x1804a7eb9  call    cs:__imp_LocalReAlloc
0x1804a7ec0  nop     dword ptr [rax+rax+00h]
0x1804a7ec5  jmp     short loc_1804A7ED8
0x1804a7ec7  mov     ecx, 40h ; '@'; uFlags
0x1804a7ecc  call    cs:__imp_LocalAlloc
0x1804a7ed3  nop     dword ptr [rax+rax+00h]
0x1804a7ed8  test    rax, rax
0x1804a7edb  jz      short loc_1804A7F07
0x1804a7edd  lea     r8, [rbp+0C90h+String]; unsigned __int16 *
0x1804a7ee4  mov     rdx, r15; unsigned __int64
0x1804a7ee7  mov     rcx, rax; unsigned __int16 *
0x1804a7eea  mov     rbx, rax
0x1804a7eed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1804a7ef2  jmp     loc_1804A7DE8
0x1804a7ef7  mov     rdx, [rsp+0D90h+hszItem]; hszItem
0x1804a7efc  mov     rcx, rbx; lpWideCharStr
0x1804a7eff  call    ?_DdeCreateDataHandleFromUnicode@@YAPEAUHDDEDATA__@@PEBGPEAUHSZ__@@@Z; _DdeCreateDataHandleFromUnicode(ushort const *,HSZ__ *)
0x1804a7f04  mov     r13, rax
0x1804a7f07  mov     rcx, rbx; hMem
0x1804a7f0a  call    cs:__imp_LocalFree
0x1804a7f11  nop     dword ptr [rax+rax+00h]
0x1804a7f16  xor     r8d, r8d; pData
0x1804a7f19  lea     rdx, ?DSA_DestroyGroupCallback@@YAHPEAX0@Z; pfnCB
  ... truncated ...
```
