# EnumItemsInGroup(HSZ__ *,ushort const *)

- ea: `0x180473110`
- end: `0x1804735d7`
- name: `?EnumItemsInGroup@@YAPEAUHDDEDATA__@@PEAUHSZ__@@PEBG@Z`
- size: `1223`
- prototype: `HDDEDATA(HSZ, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180472908`

## callees

- `0x18001bf10`
- `0x18001f630`
- `0x18003eab0`
- `0x1800426e8`
- `0x180043380`
- `0x180043c20`
- `0x180076fdc`
- `0x180233280`
- `0x1802342fc`
- `0x180473110`
- `0x180473cfc`
- `0x180474c54`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18047345e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18047355a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18047345e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18047355a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180473592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180473592`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18047354d`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18047354d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180473226`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180473226`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1804731b9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1804731b9`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18047317e`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804731fd`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18047317e`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1804731fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180473448`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18047352e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180473448`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18047352e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804732d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1804732d6`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x180473167`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x180473167`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1804731ea`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x1804731ea`
- `Windows.Storage!ILCreateFromPathW` at `0x180473249`
- `Windows.Storage!ILCreateFromPathW` at `0x180473249`
- `Windows.Storage!ILFree` at `0x180473393`
- `Windows.Storage!ILFree` at `0x1804733e3`
- `Windows.Storage!ILFree` at `0x180473393`
- `Windows.Storage!ILFree` at `0x1804733e3`
- `Windows.Storage!PathGetShortPath` at `0x1804733f9`
- `Windows.Storage!PathGetShortPath` at `0x1804733f9`
- `Windows.Storage!SHBindToObject` at `0x18047327e`
- `Windows.Storage!SHBindToObject` at `0x18047327e`
- `Windows.Storage!__imp_SHRestricted` at `0x1804731d0`
- `Windows.Storage!__imp_SHRestricted` at `0x1804731d0`

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
0x180473110  mov     [rsp-8+arg_10], rbx
0x180473115  push    rbp
0x180473116  push    rsi
0x180473117  push    rdi
0x180473118  push    r12
0x18047311a  push    r13
0x18047311c  push    r14
0x18047311e  push    r15
0x180473120  lea     rbp, [rsp-0C60h]
0x180473128  sub     rsp, 0D60h
0x18047312f  mov     rax, cs:__security_cookie
0x180473136  xor     rax, rsp
0x180473139  mov     [rbp+0C90h+var_40], rax
0x180473140  mov     r15, rdx
0x180473143  mov     [rsp+0D90h+hszItem], rcx
0x180473148  mov     esi, 104h
0x18047314d  lea     rcx, FOLDERID_Programs
0x180473154  xor     edx, edx
0x180473156  mov     dword ptr [rsp+0D90h+ppv], esi
0x18047315a  lea     r9, [rbp+0C90h+pszPath]
0x180473161  xor     r8d, r8d
0x180473164  xor     r13d, r13d
0x180473167  call    cs:__imp_SHGetFolderPathEx
0x18047316d  test    eax, eax
0x18047316f  js      loc_1804735AA
0x180473175  mov     edx, esi; cchPath
0x180473177  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x18047317e  call    cs:__imp_PathCchAddBackslash
0x180473184  mov     r8, r15; unsigned __int16 *
0x180473187  lea     rcx, [rbp+0C90h+pszPath]; unsigned __int16 *
0x18047318e  mov     edx, esi; unsigned __int64
0x180473190  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180473195  test    eax, eax
0x180473197  js      loc_1804735AA
0x18047319d  xor     edx, edx; Val
0x18047319f  lea     rcx, [rbp+0C90h+FindFileData]; void *
0x1804731a3  mov     r8d, 250h; Size
0x1804731a9  call    memset_0
0x1804731ae  lea     rdx, [rbp+0C90h+FindFileData]; lpFindFileData
0x1804731b2  lea     rcx, [rbp+0C90h+pszPath]; lpFileName
0x1804731b9  call    cs:__imp_FindFirstFileW
0x1804731bf  xor     ebx, ebx
0x1804731c1  lea     edi, [r13+1]
0x1804731c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804731c9  jnz     short loc_180473223
0x1804731cb  mov     ecx, 400000h; rest
0x1804731d0  call    cs:__imp_SHRestricted
0x1804731d6  test    eax, eax
0x1804731d8  jnz     short loc_180473219
0x1804731da  xor     r9d, r9d; fCreate
0x1804731dd  lea     r8d, [r13+17h]; csidl
0x1804731e1  lea     rdx, [rbp+0C90h+pszPath]; pszPath
0x1804731e8  xor     ecx, ecx; hwnd
0x1804731ea  call    cs:__imp_SHGetSpecialFolderPathW
0x1804731f0  test    eax, eax
0x1804731f2  jz      short loc_180473219
0x1804731f4  mov     edx, esi; cchPath
0x1804731f6  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x1804731fd  call    cs:__imp_PathCchAddBackslash
0x180473203  mov     r8, r15; unsigned __int16 *
0x180473206  lea     rcx, [rbp+0C90h+pszPath]; unsigned __int16 *
0x18047320d  mov     edx, esi; unsigned __int64
0x18047320f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180473214  test    eax, eax
0x180473216  cmovns  ebx, edi
0x180473219  test    ebx, ebx
0x18047321b  jz      loc_1804735AA
0x180473221  jmp     short loc_18047322C
0x180473223  mov     rcx, rax; hFindFile
0x180473226  call    cs:__imp_FindClose
0x18047322c  xor     edx, edx; cItemGrow
0x18047322e  lea     ecx, [rdx+30h]; cbItem
0x180473231  call    DSA_Create
0x180473236  mov     r14, rax
0x180473239  test    rax, rax
0x18047323c  jz      loc_1804735AA
0x180473242  lea     rcx, [rbp+0C90h+pszPath]; pszPath
0x180473249  call    cs:__imp_ILCreateFromPathW
0x18047324f  mov     rsi, rax
0x180473252  test    rax, rax
0x180473255  jz      loc_180473598
0x18047325b  lea     rax, [rsp+0D90h+var_D20]
0x180473260  xor     edi, edi
0x180473262  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180473269  mov     [rsp+0D90h+var_D20], rdi
0x18047326e  xor     r8d, r8d; pbc
0x180473271  mov     [rsp+0D90h+ppv], rax; ppv
0x180473276  mov     rdx, rsi; pidl
0x180473279  xor     ecx, ecx; psf
0x18047327b  xor     r12d, r12d
0x18047327e  call    cs:__imp_SHBindToObject
0x180473284  test    eax, eax
0x180473286  js      loc_1804733E0
0x18047328c  mov     rcx, [rsp+0D90h+var_D20]
0x180473291  lea     r9, [rbp+0C90h+var_D08]
0x180473295  mov     [rbp+0C90h+var_D08], rdi
0x180473299  lea     r8d, [rdi+40h]
0x18047329d  xor     edx, edx
0x18047329f  mov     rax, [rcx]
0x1804732a2  mov     rax, [rax+20h]
0x1804732a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804732ab  test    eax, eax
0x1804732ad  jnz     loc_1804733CF
0x1804732b3  lea     rax, [rsp+0D90h+var_D28]
0x1804732b8  mov     [rsp+0D90h+var_D28], rdi
0x1804732bd  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x1804732c4  mov     [rsp+0D90h+ppv], rax; ppv
0x1804732c9  xor     edx, edx; pUnkOuter
0x1804732cb  lea     r8d, [rdi+1]; dwClsContext
0x1804732cf  lea     rcx, CLSID_ShellLink; rclsid
0x1804732d6  call    cs:__imp_CoCreateInstance
0x1804732dc  test    eax, eax
0x1804732de  js      loc_1804733BF
0x1804732e4  mov     rcx, [rsp+0D90h+var_D28]
0x1804732e9  lea     r8, [rbp+0C90h+var_D10]
0x1804732ed  mov     [rbp+0C90h+var_D10], rdi
0x1804732f1  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x1804732f8  mov     rax, [rcx]
0x1804732fb  mov     rax, [rax]
0x1804732fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473303  test    eax, eax
0x180473305  js      loc_1804733AE
0x18047330b  mov     [rsp+0D90h+pidl], rdi
0x180473310  lea     r12d, [rdi+1]
0x180473314  mov     [rbp+0C90h+var_D00], edi
0x180473317  mov     rcx, [rbp+0C90h+var_D08]
0x18047331b  lea     r9, [rbp+0C90h+var_D00]
0x18047331f  lea     r8, [rsp+0D90h+pidl]
0x180473324  mov     edx, r12d
0x180473327  mov     rax, [rcx]
0x18047332a  mov     rax, [rax+18h]
0x18047332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473333  test    eax, eax
0x180473335  jnz     short loc_18047339E
0x180473337  cmp     [rbp+0C90h+var_D00], r12d
0x18047333b  jnz     short loc_18047339E
0x18047333d  mov     rax, [rbp+0C90h+var_D10]
0x180473341  lea     rdx, [rbp+0C90h+pitem]; struct GROUPITEM *
0x180473345  mov     r9, [rsp+0D90h+var_D20]; struct IShellFolder *
0x18047334a  lea     rcx, [rbp+0C90h+pszPath]; pszPathIn
0x180473351  mov     r8, [rsp+0D90h+pidl]; struct _ITEMID_CHILD *
0x180473356  xorps   xmm0, xmm0
0x180473359  mov     [rsp+0D90h+var_D68], rax; struct IPersistFile *
0x18047335e  mov     rax, [rsp+0D90h+var_D28]
0x180473363  mov     [rsp+0D90h+ppv], rax; struct IShellLinkW *
0x180473368  movups  [rbp+0C90h+pitem], xmm0
0x18047336c  movups  [rbp+0C90h+var_CE8], xmm0
0x180473370  movups  [rbp+0C90h+var_CD8], xmm0
0x180473374  call    ?GroupItem_GetLinkInfo@@YAHPEBGPEAUGROUPITEM@@PEFBU_ITEMID_CHILD@@PEAUIShellFolder@@PEAUIShellLinkW@@PEAUIPersistFile@@@Z; GroupItem_GetLinkInfo(ushort const *,GROUPITEM *,_ITEMID_CHILD const *,IShellFolder *,IShellLinkW *,IPersistFile *)
0x180473379  test    eax, eax
0x18047337b  jz      short loc_18047338E
0x18047337d  lea     r8, [rbp+0C90h+pitem]; pitem
0x180473381  mov     edx, edi; i
0x180473383  mov     rcx, r14; hdsa
0x180473386  call    DSA_InsertItem
0x18047338b  add     edi, r12d
0x18047338e  mov     rcx, [rsp+0D90h+pidl]; pidl
0x180473393  call    cs:__imp_ILFree
0x180473399  jmp     loc_180473317
0x18047339e  mov     rcx, [rbp+0C90h+var_D10]
0x1804733a2  mov     rax, [rcx]
0x1804733a5  mov     rax, [rax+10h]
0x1804733a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804733ae  mov     rcx, [rsp+0D90h+var_D28]
0x1804733b3  mov     rax, [rcx]
0x1804733b6  mov     rax, [rax+10h]
0x1804733ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804733bf  mov     rcx, [rbp+0C90h+var_D08]
0x1804733c3  mov     rax, [rcx]
0x1804733c6  mov     rax, [rax+10h]
0x1804733ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804733cf  mov     rcx, [rsp+0D90h+var_D20]
0x1804733d4  mov     rax, [rcx]
0x1804733d7  mov     rax, [rax+10h]
0x1804733db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804733e0  mov     rcx, rsi; pidl
0x1804733e3  call    cs:__imp_ILFree
0x1804733e9  test    r12d, r12d
0x1804733ec  jz      loc_180473598
0x1804733f2  lea     rcx, [rbp+0C90h+pszPath]; pszLongPath
0x1804733f9  call    cs:__imp_PathGetShortPath
0x1804733ff  mov     dword ptr [rsp+0D90h+var_D58], ebx
0x180473403  lea     rax, [rbp+0C90h+pszPath]
0x18047340a  mov     r12d, 1
0x180473410  lea     r8, aSSDDD; "\"%s\",%s,%d,%d,%d\r\n"
0x180473417  mov     dword ptr [rsp+0D90h+var_D60], r12d
0x18047341c  lea     rcx, [rbp+0C90h+String]; unsigned __int16 *
0x180473423  mov     dword ptr [rsp+0D90h+var_D68], edi
0x180473427  mov     r9, r15
0x18047342a  mov     edx, 410h; unsigned __int64
0x18047342f  mov     [rsp+0D90h+ppv], rax
0x180473434  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180473439  test    eax, eax
0x18047343b  js      loc_180473598
0x180473441  lea     rcx, [rbp+0C90h+String]; lpString
0x180473448  call    cs:__imp_lstrlenW
0x18047344e  lea     ecx, [r12+3Fh]; uFlags
0x180473453  lea     esi, [r12+rax]
0x180473457  lea     rdx, [rsi+rsi]; uBytes
0x18047345b  mov     r15d, esi
0x18047345e  call    cs:__imp_LocalAlloc
0x180473464  mov     rbx, rax
0x180473467  test    rax, rax
0x18047346a  jz      loc_180473598
0x180473470  lea     r8, [rbp+0C90h+String]; unsigned __int16 *
0x180473477  mov     edx, r15d; unsigned __int64
0x18047347a  mov     rcx, rax; unsigned __int16 *
0x18047347d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180473482  sub     edi, r12d
0x180473485  test    edi, edi
0x180473487  js      loc_18047357F
0x18047348d  mov     edx, edi; i
0x18047348f  mov     rcx, r14; hdsa
0x180473492  call    DSA_GetItemPtr
0x180473497  mov     r10, rax
0x18047349a  mov     eax, 92492493h
0x18047349f  imul    edi
0x1804734a1  lea     r8d, [rdi+rdx]
0x1804734a5  movzx   edx, word ptr [r10+28h]
0x1804734aa  sar     r8d, 2
0x1804734ae  mov     ecx, r8d
0x1804734b1  shr     ecx, 1Fh
0x1804734b4  add     r8d, ecx
0x1804734b7  mov     ecx, edi
0x1804734b9  imul    eax, r8d, 7
0x1804734bd  mov     r9d, r8d
0x1804734c0  shl     r9d, 6
0x1804734c4  lea     r8, aSSSSDDDDD; "\"%s\",\"%s\",%s,%s,%d,%d,%d,%d,%d\r\n"
0x1804734cb  add     r9d, 20h ; ' '
0x1804734cf  sub     ecx, eax
0x1804734d1  mov     eax, [r10+24h]
0x1804734d5  mov     dword ptr [rsp+0D90h+var_D38], eax
0x1804734d9  mov     eax, [r10+20h]
0x1804734dd  mov     dword ptr [rsp+0D90h+var_D40], edx
0x1804734e1  mov     edx, 410h; unsigned __int64
0x1804734e6  mov     dword ptr [rsp+0D90h+var_D48], eax
0x1804734ea  mov     rax, [r10+18h]
0x1804734ee  mov     dword ptr [rsp+0D90h+var_D50], r9d
0x1804734f3  mov     r9, [r10]
0x1804734f6  shl     ecx, 6
0x1804734f9  add     ecx, 20h ; ' '
0x1804734fc  mov     dword ptr [rsp+0D90h+var_D58], ecx
0x180473500  lea     rcx, [rbp+0C90h+String]; unsigned __int16 *
0x180473507  mov     [rsp+0D90h+var_D60], rax
0x18047350c  mov     rax, [r10+10h]
0x180473510  mov     [rsp+0D90h+var_D68], rax
0x180473515  mov     rax, [r10+8]
0x180473519  mov     [rsp+0D90h+ppv], rax
0x18047351e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180473523  test    eax, eax
0x180473525  js      short loc_18047358F
0x180473527  lea     rcx, [rbp+0C90h+String]; lpString
0x18047352e  call    cs:__imp_lstrlenW
0x180473534  inc     eax
0x180473536  add     esi, eax
0x180473538  mov     r15d, esi
0x18047353b  lea     rdx, [rsi+rsi]; uBytes
0x18047353f  test    rbx, rbx
0x180473542  jz      short loc_180473555
0x180473544  mov     r8d, 42h ; 'B'; uFlags
0x18047354a  mov     rcx, rbx; hMem
0x18047354d  call    cs:__imp_LocalReAlloc
0x180473553  jmp     short loc_180473560
0x180473555  mov     ecx, 40h ; '@'; uFlags
0x18047355a  call    cs:__imp_LocalAlloc
0x180473560  test    rax, rax
0x180473563  jz      short loc_18047358F
0x180473565  lea     r8, [rbp+0C90h+String]; unsigned __int16 *
0x18047356c  mov     rdx, r15; unsigned __int64
0x18047356f  mov     rcx, rax; unsigned __int16 *
0x180473572  mov     rbx, rax
0x180473575  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18047357a  jmp     loc_180473482
0x18047357f  mov     rdx, [rsp+0D90h+hszItem]; hszItem
0x180473584  mov     rcx, rbx; lpWideCharStr
0x180473587  call    ?_DdeCreateDataHandleFromUnicode@@YAPEAUHDDEDATA__@@PEBGPEAUHSZ__@@@Z; _DdeCreateDataHandleFromUnicode(ushort const *,HSZ__ *)
0x18047358c  mov     r13, rax
0x18047358f  mov     rcx, rbx; hMem
0x180473592  call    cs:__imp_LocalFree
0x180473598  xor     r8d, r8d; pData
0x18047359b  lea     rdx, ?DSA_DestroyGroupCallback@@YAHPEAX0@Z; pfnCB
0x1804735a2  mov     rcx, r14; hdsa
0x1804735a5  call    DSA_DestroyCallback
0x1804735aa  mov     rax, r13
0x1804735ad  mov     rcx, [rbp+0C90h+var_40]
0x1804735b4  xor     rcx, rsp; StackCookie
0x1804735b7  call    __security_check_cookie
0x1804735bc  mov     rbx, [rsp+0D90h+arg_10]
0x1804735c4  add     rsp, 0D60h
0x1804735cb  pop     r15
0x1804735cd  pop     r14
0x1804735cf  pop     r13
0x1804735d1  pop     r12
0x1804735d3  pop     rdi
0x1804735d4  pop     rsi
0x1804735d5  pop     rbp
0x1804735d6  retn
```
