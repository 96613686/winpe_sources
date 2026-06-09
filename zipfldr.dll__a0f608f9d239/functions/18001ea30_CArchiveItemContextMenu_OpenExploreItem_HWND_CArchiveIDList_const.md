# CArchiveItemContextMenu::_OpenExploreItem(HWND__ *,CArchiveIDList const *)

- ea: `0x18001ea30`
- end: `0x18001f079`
- name: `?_OpenExploreItem@CArchiveItemContextMenu@@AEAAJPEAUHWND__@@PEBVCArchiveIDList@@@Z`
- size: `1609`
- prototype: `__int64 __fastcall(CArchiveItemContextMenu *__hidden this, HWND, LPCITEMIDLIST pidl)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002cc30`

## callees

- `0x18000ed94`
- `0x18000f370`
- `0x18000f5f0`
- `0x180011568`
- `0x1800121ec`
- `0x18001ea30`
- `0x18001f080`
- `0x18001f13c`
- `0x18001f284`
- `0x18001f680`
- `0x18001f724`
- `0x1800200e4`
- `0x1800203b0`
- `0x1800203e0`
- `0x180022ffc`
- `0x180025b70`
- `0x1800278b0`
- `0x180036f50`
- `0x18006da18`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001eab9`
- `SHELL32!__imp_ILFindLastID` at `0x18001eab9`
- `SHELL32!__imp_ILFree` at `0x18001efc8`
- `SHELL32!__imp_ILFree` at `0x18001efc8`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed1d`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed53`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed86`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed1d`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed53`
- `SHLWAPI!PathFindExtensionW` at `0x18001ed86`
- `SHLWAPI!PathFindFileNameW` at `0x18001ecd1`
- `SHLWAPI!PathFindFileNameW` at `0x18001ecf8`
- `SHLWAPI!PathFindFileNameW` at `0x18001ecd1`
- `SHLWAPI!PathFindFileNameW` at `0x18001ecf8`
- `SHLWAPI!PathRemoveExtensionW` at `0x18001ecb6`
- `SHLWAPI!PathRemoveExtensionW` at `0x18001ecb6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001ec2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eecc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ed41`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ed74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001eda7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ed41`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ed74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001eda7`
- `KERNEL32!lstrcmpiW` at `0x18001ece1`
- `KERNEL32!lstrcmpiW` at `0x18001ed08`
- `KERNEL32!lstrcmpiW` at `0x18001ece1`
- `KERNEL32!lstrcmpiW` at `0x18001ed08`
- `USER32!SetCursor` at `0x18001ea7e`
- `USER32!SetCursor` at `0x18001eed6`
- `USER32!SetCursor` at `0x18001ef32`
- `USER32!SetCursor` at `0x18001ea7e`
- `USER32!SetCursor` at `0x18001eed6`
- `USER32!SetCursor` at `0x18001ef32`
- `USER32!LoadCursorW` at `0x18001ea75`
- `USER32!LoadCursorW` at `0x18001ef29`
- `USER32!LoadCursorW` at `0x18001ea75`
- `USER32!LoadCursorW` at `0x18001ef29`
- `USER32!ShowCursor` at `0x18001ea8d`
- `USER32!ShowCursor` at `0x18001ea8d`

## pseudocode

```c
__int64 __fastcall CArchiveItemContextMenu::_OpenExploreItem(CArchiveItemContextMenu *this, HWND a2, ITEMIDLIST *pidl)
{
  HCURSOR CursorW; // rax
  CTempFileNameArray *v7; // rcx
  unsigned int v8; // r9d
  signed int TempLocation; // ebx
  LPITEMIDLIST ID; // r14
  __int64 v11; // rsi
  unsigned __int16 *v12; // r9
  __int64 v13; // rdi
  unsigned __int16 *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // rcx
  int v20; // eax
  WCHAR *v21; // r12
  __int64 v22; // rax
  WCHAR *v23; // r8
  WCHAR *v24; // rcx
  __int64 v25; // rdx
  WCHAR *v26; // rcx
  const unsigned __int16 *v27; // rdx
  WCHAR *v28; // rax
  WCHAR *v29; // rdx
  WCHAR *v30; // rcx
  int v31; // esi
  const WCHAR *FileNameW; // rax
  const WCHAR *v33; // rax
  const WCHAR *ExtensionW; // rax
  __int64 v35; // rcx
  const WCHAR *v36; // rax
  const WCHAR *v37; // rax
  __int64 v38; // rax
  int v39; // r8d
  CArchiveIDList *v40; // rdi
  HCURSOR v42; // rax
  struct CEnumArchive *Enumerator; // r14
  struct _DPA *v44; // rsi
  int v45; // edi
  CArchiveIDList *Ptr; // rax
  int v47; // r8d
  __int64 v48; // [rsp+40h] [rbp-C0h]
  HLOCAL hMem[2]; // [rsp+78h] [rbp-88h] BYREF
  HCURSOR hCursor; // [rsp+88h] [rbp-78h]
  void *p[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v53[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v54[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v55[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR pszPath[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  WCHAR Buffer[256]; // [rsp+8E0h] [rbp+7E0h] BYREF
  WCHAR String2[256]; // [rsp+AE0h] [rbp+9E0h] BYREF
  unsigned __int16 v59[264]; // [rsp+CE0h] [rbp+BE0h] BYREF

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F8A);
  hCursor = SetCursor(CursorW);
  ShowCursor(1);
  TempLocation = CTempFileNameArray::GetTempLocation(
                   v7,
                   (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL),
                   v53,
                   v8);
  if ( TempLocation >= 0 )
  {
    TempLocation = -2147467259;
    ID = ILFindLastID(pidl);
    if ( ID )
    {
      v11 = 2147483646;
      v12 = v53;
      v13 = 260;
      v14 = v55;
      v15 = 2147483646;
      v16 = 260;
      do
      {
        if ( !v15 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v15;
        --v16;
      }
      while ( v16 );
      v17 = v14 - 1;
      TempLocation = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
        v17 = v14;
      *v17 = 0;
      if ( v16 )
      {
        TempLocation = CArchiveIDList::AppendRelPathAndName((CArchiveIDList *)ID, 1, v55, (unsigned int)v12);
        if ( TempLocation >= 0 )
        {
          v18 = v55[0];
          if ( v55[0] )
          {
            v19 = v55;
            do
            {
              if ( v18 == 47 )
                *v19 = 92;
              v18 = *++v19;
            }
            while ( *v19 );
          }
          *(_OWORD *)hMem = 0;
          v20 = CTempAlignedString::Set((CTempAlignedString *)hMem, (const unsigned __int16 *)ID[30].mkid.abID);
          v21 = (WCHAR *)hMem[0];
          TempLocation = v20;
          if ( v20 < 0 )
            goto LABEL_46;
          v22 = 2147483646;
          v23 = v54;
          v24 = (WCHAR *)hMem[0];
          v25 = 260;
          do
          {
            if ( !v22 )
              break;
            if ( !*v24 )
              break;
            *v23++ = *v24++;
            --v22;
            --v25;
          }
          while ( v25 );
          v26 = v23 - 1;
          TempLocation = v25 == 0 ? 0x8007007A : 0;
          if ( v25 )
            v26 = v23;
          *v26 = 0;
          if ( !v25 )
            goto LABEL_46;
          LoadStringW(g_hmodThisDll, 0x27C8u, Buffer, 256);
          LoadStringW(g_hmodThisDll, 0x27C9u, String2, 256);
          v27 = (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL);
          LODWORD(p[0]) = 0;
          TempLocation = DZ_GetCountOfZipMembers(a2, v27, (int *)p);
          if ( TempLocation < 0 )
            goto LABEL_46;
          v28 = v54;
          v29 = pszPath;
          do
          {
            if ( !v11 )
              break;
            if ( !*v28 )
              break;
            *v29++ = *v28++;
            --v11;
            --v13;
          }
          while ( v13 );
          v30 = v29 - 1;
          TempLocation = v13 == 0 ? 0x8007007A : 0;
          if ( v13 )
            v30 = v29;
          *v30 = 0;
          if ( !v13 )
            goto LABEL_46;
          PathRemoveExtensionW(pszPath);
          v31 = 1;
          if ( SLODWORD(p[0]) > 1 )
          {
            FileNameW = PathFindFileNameW(pszPath);
            if ( !lstrcmpiW(FileNameW, Buffer) || (v33 = PathFindFileNameW(pszPath), !lstrcmpiW(v33, String2)) )
            {
              CTempFileNameArray::ReferenceDirectory(g_pCTFA, v53);
              v42 = LoadCursorW(0, (LPCWSTR)0x7F8A);
              SetCursor(v42);
              dword_18008BBC0 = 1;
              TempLocation = CZipFolder::BuildMainEnumerator(*((CZipFolder **)this + 5), a2);
              if ( TempLocation >= 0 )
              {
                Enumerator = CZipFolder::GetEnumerator(*((CZipFolder **)this + 5));
                (*(void (__fastcall **)(struct CEnumArchive *))(*(_QWORD *)Enumerator + 40LL))(Enumerator);
                v44 = DPA_Create(4);
                if ( v44 )
                {
                  p[0] = 0;
                  while ( !(*(unsigned int (__fastcall **)(struct CEnumArchive *, __int64, void **))(*(_QWORD *)Enumerator + 24LL))(
                             Enumerator,
                             1,
                             p) )
                  {
                    if ( DPA_InsertPtr(v44, 0x7FFFFFFF, p[0]) == -1 )
                    {
                      TempLocation = -2147467259;
                      ILFree((LPITEMIDLIST)p[0]);
                      goto LABEL_63;
                    }
                  }
                  v45 = 0;
                  do
                  {
                    if ( v45 >= *(_DWORD *)v44 )
                      break;
                    Ptr = (CArchiveIDList *)DPA_GetPtr(v44, v45);
                    v47 = *((_DWORD *)Ptr + 20);
                    if ( v47 != 0xFFFF )
                    {
                      LODWORD(v48) = 2;
                      TempLocation = CArchiveIDList::ExtractFromZipToFile(
                                       Ptr,
                                       (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL),
                                       v47,
                                       0,
                                       v53,
                                       1,
                                       0,
                                       0,
                                       v48,
                                       a2,
                                       0,
                                       0,
                                       0);
                    }
                    ++v45;
                  }
                  while ( TempLocation >= 0 );
                  v21 = (WCHAR *)hMem[0];
LABEL_63:
                  DPA_FreeIDArray(v44);
                }
                else
                {
                  TempLocation = -2147024882;
                }
                (*(void (__fastcall **)(struct CEnumArchive *))(*(_QWORD *)Enumerator + 16LL))(Enumerator);
              }
              dword_18008BBC0 = 0;
              goto LABEL_67;
            }
            ExtensionW = PathFindExtensionW(v54);
            if ( CompareStringW(0x7Fu, 1u, ExtensionW, -1, L".exe", -1) == 2
              || (v36 = PathFindExtensionW(v54), CompareStringW(0x7Fu, 1u, v36, -1, L".bat", -1) == 2)
              || (v37 = PathFindExtensionW(v54), CompareStringW(0x7Fu, 1u, v37, -1, L".com", -1) == 2) )
            {
              v38 = SHFusionDialogBoxParam(v35, 176, a2, PromptDlgProc, 0);
              if ( v38 != 2 )
              {
                if ( v38 == 1131 )
                {
                  TempLocation = ExtractZipFile((const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL), 0);
                  v31 = 0;
                  if ( TempLocation < 0 )
                    goto LABEL_46;
                }
                goto LABEL_41;
              }
              TempLocation = -2147023673;
LABEL_67:
              v40 = (CArchiveIDList *)pidl;
              goto LABEL_42;
            }
          }
LABEL_41:
          v40 = (CArchiveIDList *)pidl;
          LODWORD(v48) = 2;
          dword_18008BBC0 = 1;
          TempLocation = CArchiveIDList::ExtractFromZipToFile(
                           (CArchiveIDList *)pidl,
                           (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL),
                           *(_DWORD *)ID[26].mkid.abID,
                           0,
                           v53,
                           1,
                           0,
                           0,
                           v48,
                           a2,
                           0,
                           0,
                           0);
          dword_18008BBC0 = 0;
          if ( v31 )
          {
LABEL_42:
            if ( !TempLocation )
            {
              TempLocation = CArchiveIDList::GetRelativePathAndName(v40, v59, v39);
              if ( TempLocation >= 0 )
              {
                TempLocation = CheckUnZippedFile(a2, (const unsigned __int16 *)(*((_QWORD *)this + 5) + 72LL), v53, v59);
                if ( TempLocation >= 0 )
                  TempLocation = CArchiveItemContextMenu::_OpenExploreTempFile(this, a2, v53, v55);
              }
            }
          }
LABEL_46:
          if ( v21 != hMem[1] && v21 != &psz )
            LocalFree(v21);
        }
      }
    }
  }
  SetCursor(hCursor);
  return (unsigned int)TempLocation;
}

```

## disassembly

```asm
0x18001ea30  mov     [rsp-8+arg_18], rbx
0x18001ea35  push    rbp
0x18001ea36  push    rsi
0x18001ea37  push    rdi
0x18001ea38  push    r12
0x18001ea3a  push    r13
0x18001ea3c  push    r14
0x18001ea3e  push    r15
0x18001ea40  lea     rbp, [rsp-0E00h]
0x18001ea48  sub     rsp, 0F00h
0x18001ea4f  mov     rax, cs:__security_cookie
0x18001ea56  xor     rax, rsp
0x18001ea59  mov     [rbp+0E30h+var_40], rax
0x18001ea60  mov     r13, rdx
0x18001ea63  mov     [rsp+0F30h+var_EC0], r8
0x18001ea68  mov     r15, rcx
0x18001ea6b  mov     edx, 7F8Ah; lpCursorName
0x18001ea70  xor     ecx, ecx; hInstance
0x18001ea72  mov     rdi, r8
0x18001ea75  call    cs:__imp_LoadCursorW
0x18001ea7b  mov     rcx, rax; hCursor
0x18001ea7e  call    cs:__imp_SetCursor
0x18001ea84  mov     ecx, 1; bShow
0x18001ea89  mov     [rbp+0E30h+hCursor], rax
0x18001ea8d  call    cs:__imp_ShowCursor
0x18001ea93  mov     rdx, [r15+28h]
0x18001ea97  lea     r8, [rbp+0E30h+var_E90]; unsigned __int16 *
0x18001ea9b  add     rdx, 48h ; 'H'; unsigned __int16 *
0x18001ea9f  call    ?GetTempLocation@CTempFileNameArray@@QEAAJPEBGPEAGI@Z; CTempFileNameArray::GetTempLocation(ushort const *,ushort *,uint)
0x18001eaa4  xor     r12d, r12d
0x18001eaa7  mov     ebx, eax
0x18001eaa9  test    eax, eax
0x18001eaab  js      loc_18001EED2
0x18001eab1  mov     rcx, rdi; pidl
0x18001eab4  mov     ebx, 80004005h
0x18001eab9  call    cs:__imp_ILFindLastID
0x18001eabf  mov     r14, rax
0x18001eac2  test    rax, rax
0x18001eac5  jz      loc_18001EED2
0x18001eacb  mov     esi, 7FFFFFFEh
0x18001ead0  lea     r9, [rbp+0E30h+var_E90]
0x18001ead4  mov     edi, 104h
0x18001ead9  lea     r8, [rbp+0E30h+var_A70]
0x18001eae0  mov     ecx, esi
0x18001eae2  mov     edx, edi
0x18001eae4  test    rcx, rcx
0x18001eae7  jz      short loc_18001EB07
0x18001eae9  movzx   eax, word ptr [r9]
0x18001eaed  test    ax, ax
0x18001eaf0  jz      short loc_18001EB07
0x18001eaf2  mov     [r8], ax
0x18001eaf6  add     r9, 2; unsigned int
0x18001eafa  add     r8, 2
0x18001eafe  dec     rcx
0x18001eb01  sub     rdx, 1
0x18001eb05  jnz     short loc_18001EAE4
0x18001eb07  mov     rax, rdx
0x18001eb0a  lea     rcx, [r8-2]
0x18001eb0e  neg     rax
0x18001eb11  sbb     ebx, ebx
0x18001eb13  not     ebx
0x18001eb15  and     ebx, 8007007Ah
0x18001eb1b  test    rdx, rdx
0x18001eb1e  cmovnz  rcx, r8
0x18001eb22  mov     [rcx], r12w
0x18001eb26  jz      loc_18001EED2
0x18001eb2c  lea     r8, [rbp+0E30h+var_A70]; unsigned __int16 *
0x18001eb33  mov     edx, 1; int
0x18001eb38  mov     rcx, r14; this
0x18001eb3b  call    ?AppendRelPathAndName@CArchiveIDList@@QEBAJHPEAGI@Z; CArchiveIDList::AppendRelPathAndName(int,ushort *,uint)
0x18001eb40  mov     ebx, eax
0x18001eb42  test    eax, eax
0x18001eb44  js      loc_18001EED2
0x18001eb4a  movzx   eax, [rbp+0E30h+var_A70]
0x18001eb51  test    ax, ax
0x18001eb54  jz      short loc_18001EB74
0x18001eb56  lea     rcx, [rbp+0E30h+var_A70]
0x18001eb5d  cmp     ax, 2Fh ; '/'
0x18001eb61  jnz     short loc_18001EB68
0x18001eb63  mov     word ptr [rcx], 5Ch ; '\'
0x18001eb68  add     rcx, 2
0x18001eb6c  movzx   eax, word ptr [rcx]
0x18001eb6f  test    ax, ax
0x18001eb72  jnz     short loc_18001EB5D
0x18001eb74  xorps   xmm0, xmm0
0x18001eb77  lea     rdx, [r14+5Ch]; unsigned __int16 *
0x18001eb7b  lea     rcx, [rsp+0F30h+hMem]; this
0x18001eb80  movdqu  xmmword ptr [rsp+0F30h+hMem], xmm0
0x18001eb86  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x18001eb8b  mov     r12, [rsp+0F30h+hMem]
0x18001eb90  xor     r10d, r10d
0x18001eb93  mov     ebx, eax
0x18001eb95  test    eax, eax
0x18001eb97  js      loc_18001EEB7
0x18001eb9d  mov     rax, rsi
0x18001eba0  lea     r8, [rbp+0E30h+var_C80]
0x18001eba7  mov     rcx, r12
0x18001ebaa  mov     rdx, rdi
0x18001ebad  test    rax, rax
0x18001ebb0  jz      short loc_18001EBD1
0x18001ebb2  movzx   r9d, word ptr [rcx]
0x18001ebb6  test    r9w, r9w
0x18001ebba  jz      short loc_18001EBD1
0x18001ebbc  mov     [r8], r9w
0x18001ebc0  add     rcx, 2
0x18001ebc4  add     r8, 2
0x18001ebc8  dec     rax
0x18001ebcb  sub     rdx, 1
0x18001ebcf  jnz     short loc_18001EBAD
0x18001ebd1  mov     rax, rdx
0x18001ebd4  lea     rcx, [r8-2]
0x18001ebd8  neg     rax
0x18001ebdb  sbb     ebx, ebx
0x18001ebdd  not     ebx
0x18001ebdf  and     ebx, 8007007Ah
0x18001ebe5  test    rdx, rdx
0x18001ebe8  cmovnz  rcx, r8
0x18001ebec  mov     [rcx], r10w
0x18001ebf0  jz      loc_18001EEB7
0x18001ebf6  mov     rcx, cs:g_hmodThisDll; hInstance
0x18001ebfd  lea     r8, [rbp+0E30h+Buffer]; lpBuffer
0x18001ec04  mov     ebx, 100h
0x18001ec09  mov     edx, 27C8h; uID
0x18001ec0e  mov     r9d, ebx; cchBufferMax
0x18001ec11  call    cs:__imp_LoadStringW
0x18001ec17  mov     rcx, cs:g_hmodThisDll; hInstance
0x18001ec1e  lea     r8, [rbp+0E30h+String2]; lpBuffer
0x18001ec25  mov     r9d, ebx; cchBufferMax
0x18001ec28  mov     edx, 27C9h; uID
0x18001ec2d  call    cs:__imp_LoadStringW
0x18001ec33  mov     rdx, [r15+28h]
0x18001ec37  lea     r8, [rbp+0E30h+p]; int *
0x18001ec3b  add     rdx, 48h ; 'H'; unsigned __int16 *
0x18001ec3f  mov     dword ptr [rbp+0E30h+p], 0
0x18001ec46  mov     rcx, r13; HWND
0x18001ec49  call    ?DZ_GetCountOfZipMembers@@YAJPEAUHWND__@@PEBGPEAH@Z; DZ_GetCountOfZipMembers(HWND__ *,ushort const *,int *)
0x18001ec4e  xor     r8d, r8d
0x18001ec51  mov     ebx, eax
0x18001ec53  test    eax, eax
0x18001ec55  js      loc_18001EEB7
0x18001ec5b  lea     rax, [rbp+0E30h+var_C80]
0x18001ec62  lea     rdx, [rbp+0E30h+pszPath]
0x18001ec69  test    rsi, rsi
0x18001ec6c  jz      short loc_18001EC8A
0x18001ec6e  movzx   ecx, word ptr [rax]
0x18001ec71  test    cx, cx
0x18001ec74  jz      short loc_18001EC8A
0x18001ec76  mov     [rdx], cx
0x18001ec79  add     rax, 2
0x18001ec7d  add     rdx, 2
0x18001ec81  dec     rsi
0x18001ec84  sub     rdi, 1
0x18001ec88  jnz     short loc_18001EC69
0x18001ec8a  mov     rax, rdi
0x18001ec8d  lea     rcx, [rdx-2]
0x18001ec91  neg     rax
0x18001ec94  sbb     ebx, ebx
0x18001ec96  not     ebx
0x18001ec98  and     ebx, 8007007Ah
0x18001ec9e  test    rdi, rdi
0x18001eca1  cmovnz  rcx, rdx
0x18001eca5  mov     [rcx], r8w
0x18001eca9  jz      loc_18001EEB7
0x18001ecaf  lea     rcx, [rbp+0E30h+pszPath]; pszPath
0x18001ecb6  call    cs:__imp_PathRemoveExtensionW
0x18001ecbc  mov     esi, 1
0x18001ecc1  cmp     dword ptr [rbp+0E30h+p], esi
0x18001ecc4  jle     loc_18001EDFA
0x18001ecca  lea     rcx, [rbp+0E30h+pszPath]; pszPath
0x18001ecd1  call    cs:__imp_PathFindFileNameW
0x18001ecd7  mov     rcx, rax; lpString1
0x18001ecda  lea     rdx, [rbp+0E30h+Buffer]; lpString2
0x18001ece1  call    cs:__imp_lstrcmpiW
0x18001ece7  xor     ebx, ebx
0x18001ece9  test    eax, eax
0x18001eceb  jz      loc_18001EF12
0x18001ecf1  lea     rcx, [rbp+0E30h+pszPath]; pszPath
0x18001ecf8  call    cs:__imp_PathFindFileNameW
0x18001ecfe  mov     rcx, rax; lpString1
0x18001ed01  lea     rdx, [rbp+0E30h+String2]; lpString2
0x18001ed08  call    cs:__imp_lstrcmpiW
0x18001ed0e  test    eax, eax
0x18001ed10  jz      loc_18001EF12
0x18001ed16  lea     rcx, [rbp+0E30h+var_C80]; pszPath
0x18001ed1d  call    cs:__imp_PathFindExtensionW
0x18001ed23  lea     rcx, aExe; ".exe"
0x18001ed2a  or      edi, 0FFFFFFFFh
0x18001ed2d  mov     [rsp+0F30h+cchCount2], edi; cchCount2
0x18001ed31  mov     r9d, edi; cchCount1
0x18001ed34  mov     [rsp+0F30h+lpString2], rcx; lpString2
0x18001ed39  mov     r8, rax; lpString1
0x18001ed3c  lea     ecx, [rsi+7Eh]; Locale
0x18001ed3f  mov     edx, esi; dwCmpFlags
0x18001ed41  call    cs:__imp_CompareStringW
0x18001ed47  cmp     eax, 2
0x18001ed4a  jz      short loc_18001EDB2
0x18001ed4c  lea     rcx, [rbp+0E30h+var_C80]; pszPath
0x18001ed53  call    cs:__imp_PathFindExtensionW
0x18001ed59  lea     rcx, aBat; ".bat"
0x18001ed60  mov     [rsp+0F30h+cchCount2], edi; cchCount2
0x18001ed64  mov     [rsp+0F30h+lpString2], rcx; lpString2
0x18001ed69  mov     r9d, edi; cchCount1
0x18001ed6c  lea     ecx, [rsi+7Eh]; Locale
0x18001ed6f  mov     r8, rax; lpString1
0x18001ed72  mov     edx, esi; dwCmpFlags
0x18001ed74  call    cs:__imp_CompareStringW
0x18001ed7a  cmp     eax, 2
0x18001ed7d  jz      short loc_18001EDB2
0x18001ed7f  lea     rcx, [rbp+0E30h+var_C80]; pszPath
0x18001ed86  call    cs:__imp_PathFindExtensionW
0x18001ed8c  lea     rdx, aCom; ".com"
0x18001ed93  mov     [rsp+0F30h+cchCount2], edi; cchCount2
0x18001ed97  mov     [rsp+0F30h+lpString2], rdx; lpString2
0x18001ed9c  lea     ecx, [rsi+7Eh]; Locale
0x18001ed9f  mov     edx, esi; dwCmpFlags
0x18001eda1  mov     r9d, edi; cchCount1
0x18001eda4  mov     r8, rax; lpString1
0x18001eda7  call    cs:__imp_CompareStringW
0x18001edad  cmp     eax, 2
0x18001edb0  jnz     short loc_18001EDFC
0x18001edb2  lea     r9, ?PromptDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; PromptDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001edb9  mov     [rsp+0F30h+lpString2], rbx
0x18001edbe  mov     r8, r13
0x18001edc1  mov     edx, 0B0h
0x18001edc6  call    SHFusionDialogBoxParam
0x18001edcb  cmp     rax, 2
0x18001edcf  jz      loc_18001EF08
0x18001edd5  cmp     rax, 46Bh
0x18001eddb  jnz     short loc_18001EDFC
0x18001eddd  mov     rcx, [r15+28h]
0x18001ede1  xor     edx, edx; unsigned __int16 *
0x18001ede3  add     rcx, 48h ; 'H'; unsigned __int16 *
0x18001ede7  call    ?ExtractZipFile@@YAJPEBG0@Z; ExtractZipFile(ushort const *,ushort const *)
0x18001edec  mov     ebx, eax
0x18001edee  xor     eax, eax
0x18001edf0  mov     esi, eax
0x18001edf2  test    ebx, ebx
0x18001edf4  js      loc_18001EEB7
0x18001edfa  xor     ebx, ebx
0x18001edfc  mov     rdi, [rsp+0F30h+var_EC0]
0x18001ee01  lea     rax, [rbp+0E30h+var_E90]
0x18001ee05  mov     [rsp+0F30h+var_ED0], rbx
0x18001ee0a  xor     r9d, r9d
0x18001ee0d  mov     [rsp+0F30h+var_ED8], rbx
0x18001ee12  mov     rcx, rdi
0x18001ee15  mov     [rsp+0F30h+var_EE0], ebx
0x18001ee19  mov     [rsp+0F30h+var_EE8], r13
0x18001ee1e  mov     dword ptr [rsp+0F30h+var_EF0], 2
0x18001ee26  mov     cs:dword_18008BBC0, 1
0x18001ee30  mov     rdx, [r15+28h]
0x18001ee34  mov     r8d, [r14+50h]
0x18001ee38  add     rdx, 48h ; 'H'
0x18001ee3c  mov     [rsp+0F30h+var_EF8], rbx
0x18001ee41  mov     [rsp+0F30h+var_F00], ebx
0x18001ee45  mov     [rsp+0F30h+cchCount2], 1
0x18001ee4d  mov     [rsp+0F30h+lpString2], rax
0x18001ee52  call    ?ExtractFromZipToFile@CArchiveIDList@@QEBAJPEBGK00HK0W4ZIPEXTRACTMODE@@PEAUHWND__@@HP6AH0_K3JPEAX@Z4@Z; CArchiveIDList::ExtractFromZipToFile(ushort const *,ulong,ushort const *,ushort const *,int,ulong,ushort const *,ZIPEXTRACTMODE,HWND__ *,int,int (*)(ushort const *,unsigned __int64,unsigned __int64,long,void *),void *)
0x18001ee57  mov     ebx, eax
0x18001ee59  xor     eax, eax
0x18001ee5b  mov     cs:dword_18008BBC0, eax
0x18001ee61  test    esi, esi
0x18001ee63  jz      short loc_18001EEB7
0x18001ee65  test    ebx, ebx
0x18001ee67  jnz     short loc_18001EEB7
0x18001ee69  lea     rdx, [rbp+0E30h+var_250]; unsigned __int16 *
0x18001ee70  mov     rcx, rdi; this
0x18001ee73  call    ?GetRelativePathAndName@CArchiveIDList@@QEBAJPEAGH@Z; CArchiveIDList::GetRelativePathAndName(ushort *,int)
0x18001ee78  mov     ebx, eax
0x18001ee7a  test    eax, eax
0x18001ee7c  js      short loc_18001EEB7
0x18001ee7e  mov     rdx, [r15+28h]
0x18001ee82  lea     r9, [rbp+0E30h+var_250]; unsigned __int16 *
0x18001ee89  add     rdx, 48h ; 'H'; unsigned __int16 *
0x18001ee8d  lea     r8, [rbp+0E30h+var_E90]; unsigned __int16 *
0x18001ee91  mov     rcx, r13; HWND
0x18001ee94  call    ?CheckUnZippedFile@@YAJPEAUHWND__@@PEBG11@Z; CheckUnZippedFile(HWND__ *,ushort const *,ushort const *,ushort const *)
0x18001ee99  mov     ebx, eax
0x18001ee9b  test    eax, eax
0x18001ee9d  js      short loc_18001EEB7
0x18001ee9f  lea     r9, [rbp+0E30h+var_A70]; unsigned __int16 *
0x18001eea6  mov     rdx, r13; HWND
0x18001eea9  lea     r8, [rbp+0E30h+var_E90]; unsigned __int16 *
0x18001eead  mov     rcx, r15; this
0x18001eeb0  call    ?_OpenExploreTempFile@CArchiveItemContextMenu@@AEAAJPEAUHWND__@@PEBG1@Z; CArchiveItemContextMenu::_OpenExploreTempFile(HWND__ *,ushort const *,ushort const *)
0x18001eeb5  mov     ebx, eax
0x18001eeb7  cmp     r12, [rbp+0E30h+hMem+8]
0x18001eebb  jz      short loc_18001EED2
0x18001eebd  lea     rax, psz
0x18001eec4  cmp     r12, rax
0x18001eec7  jz      short loc_18001EED2
0x18001eec9  mov     rcx, r12; hMem
0x18001eecc  call    cs:__imp_LocalFree
0x18001eed2  mov     rcx, [rbp+0E30h+hCursor]; hCursor
0x18001eed6  call    cs:__imp_SetCursor
0x18001eedc  mov     eax, ebx
0x18001eede  mov     rcx, [rbp+0E30h+var_40]
0x18001eee5  xor     rcx, rsp; StackCookie
0x18001eee8  call    __security_check_cookie
0x18001eeed  mov     rbx, [rsp+0F30h+arg_18]
0x18001eef5  add     rsp, 0F00h
  ... truncated ...
```
