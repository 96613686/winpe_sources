# _TryRenameContact

- ea: `0x1800121f0`
- end: `0x1800123d1`
- name: `_TryRenameContact`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18000eef0`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x180006f7c`
- `0x180008f74`
- `0x180008fa0`
- `0x1800121f0`
- `0x1800127fc`
- `0x180012d08`
- `0x180013950`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `msvcrt!_wrename` at `0x18001231e`
- `msvcrt!_wrename` at `0x18001231e`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800122bc`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800122bc`
- `SHLWAPI!PathFindExtensionW` at `0x1800122d0`
- `SHLWAPI!PathFindExtensionW` at `0x1800122d0`
- `SHELL32!SHChangeNotify` at `0x18001237b`
- `SHELL32!SHChangeNotify` at `0x18001237b`

## pseudocode

```c
__int64 __fastcall TryRenameContact(struct IContact **a1)
{
  struct IContact *v2; // r12
  int FileNameForStorage; // ebx
  LPCWSTR v4; // rdi
  const unsigned __int16 *v5; // r8
  const WCHAR *v6; // rcx
  const unsigned __int16 *ExtensionW; // rax
  int v8; // r12d
  wchar_t *v9; // rdx
  wchar_t *v10; // rbx
  const wchar_t *v11; // rcx
  const unsigned __int16 *v12; // rcx
  const WCHAR *v13; // r9
  struct IContact *v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v17[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *NewFileName; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v21[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v22[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  STRW::STRW((STRW *)&v16, v21, 0x104u);
  STRW::STRW((STRW *)&v18, v22, 0x104u);
  memset_0(pszPath, 0, 0x208u);
  v2 = *a1;
  if ( GetPathFromContact(*a1, (struct STRW *)&v16) < 0 )
  {
    FileNameForStorage = 1;
    goto LABEL_25;
  }
  if ( (unsigned int)ContactHasOriginalName(v2) )
  {
LABEL_24:
    FileNameForStorage = 0;
    goto LABEL_25;
  }
  v4 = &Str;
  v5 = &Str;
  if ( v16 )
    v5 = v17[0];
  FileNameForStorage = StringCchCopyW(pszPath, 0x104u, v5);
  if ( FileNameForStorage >= 0 )
  {
    PathRemoveFileSpecW(pszPath);
    v6 = &Str;
    if ( v16 )
      v6 = v17[0];
    ExtensionW = PathFindExtensionW(v6);
    FileNameForStorage = GenerateFileNameForStorage(v2, pszPath, ExtensionW, 0, (struct STRW *)&v18);
    if ( FileNameForStorage >= 0 )
    {
      v8 = v18;
      v9 = (wchar_t *)&Str;
      v10 = NewFileName;
      v11 = &Str;
      if ( v18 )
        v9 = NewFileName;
      if ( v16 )
        v11 = v17[0];
      if ( !_wrename(v11, v9) )
      {
        v15 = 0;
        v12 = &Str;
        if ( v8 )
          v12 = v10;
        if ( (int)CreateContactFromFile(v12, &v15) >= 0 )
        {
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(a1);
          *a1 = v15;
        }
        v13 = &Str;
        if ( v8 )
          v13 = v10;
        if ( v16 )
          v4 = v17[0];
        SHChangeNotify(1, 0x3005u, v4, v13);
      }
      goto LABEL_24;
    }
  }
LABEL_25:
  v18 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&NewFileName);
  v16 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v17);
  return (unsigned int)FileNameForStorage;
}

```

## disassembly

```asm
0x1800121f0  mov     [rsp-8+arg_8], rbx
0x1800121f5  mov     [rsp-8+arg_10], rdi
0x1800121fa  push    rbp
0x1800121fb  push    r12
0x1800121fd  push    r15
0x1800121ff  lea     rbp, [rsp-5C0h]
0x180012207  sub     rsp, 6C0h
0x18001220e  mov     rax, cs:__security_cookie
0x180012215  xor     rax, rsp
0x180012218  mov     [rbp+5D0h+var_20], rax
0x18001221f  mov     r15, rcx
0x180012222  lea     rdx, [rbp+5D0h+var_440]; unsigned __int16 *
0x180012229  mov     ebx, 104h
0x18001222e  lea     rcx, [rsp+6D0h+var_698]; this
0x180012233  mov     r8d, ebx; unsigned int
0x180012236  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18001223b  mov     r8d, ebx; unsigned int
0x18001223e  lea     rcx, [rsp+6D0h+var_678]; this
0x180012243  lea     rdx, [rbp+5D0h+var_230]; unsigned __int16 *
0x18001224a  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18001224f  mov     r8d, 208h; Size
0x180012255  lea     rcx, [rbp+5D0h+pszPath]; void *
0x180012259  xor     edx, edx; Val
0x18001225b  call    memset_0
0x180012260  mov     r12, [r15]
0x180012263  lea     rdx, [rsp+6D0h+var_698]; struct STRW *
0x180012268  mov     rcx, r12; struct IContact *
0x18001226b  call    ?GetPathFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetPathFromContact(IContact *,STRW *)
0x180012270  test    eax, eax
0x180012272  jns     short loc_18001227E
0x180012274  mov     ebx, 1
0x180012279  jmp     loc_180012383
0x18001227e  mov     rcx, r12; struct IContact *
0x180012281  call    ?ContactHasOriginalName@@YAHPEAUIContact@@@Z; ContactHasOriginalName(IContact *)
0x180012286  test    eax, eax
0x180012288  jnz     loc_180012381
0x18001228e  cmp     [rsp+6D0h+var_698], eax
0x180012292  lea     rdi, Str
0x180012299  mov     r8, rdi
0x18001229c  lea     rcx, [rbp+5D0h+pszPath]; unsigned __int16 *
0x1800122a0  cmovnz  r8, [rsp+6D0h+var_690]; unsigned __int16 *
0x1800122a6  mov     rdx, rbx; unsigned __int64
0x1800122a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122ae  mov     ebx, eax
0x1800122b0  test    eax, eax
0x1800122b2  js      loc_180012383
0x1800122b8  lea     rcx, [rbp+5D0h+pszPath]; pszPath
0x1800122bc  call    cs:__imp_PathRemoveFileSpecW
0x1800122c2  cmp     [rsp+6D0h+var_698], 0
0x1800122c7  mov     rcx, rdi
0x1800122ca  cmovnz  rcx, [rsp+6D0h+var_690]; pszPath
0x1800122d0  call    cs:__imp_PathFindExtensionW
0x1800122d6  lea     rcx, [rsp+6D0h+var_678]
0x1800122db  xor     r9d, r9d; struct IStream **
0x1800122de  mov     [rsp+6D0h+var_6B0], rcx; struct STRW *
0x1800122e3  lea     rdx, [rbp+5D0h+pszPath]; unsigned __int16 *
0x1800122e7  mov     rcx, r12; struct IContact *
0x1800122ea  mov     r8, rax; unsigned __int16 *
0x1800122ed  call    ?GenerateFileNameForStorage@@YAJPEAUIContact@@PEBG1PEAPEAUIStream@@PEAVSTRW@@@Z; GenerateFileNameForStorage(IContact *,ushort const *,ushort const *,IStream * *,STRW *)
0x1800122f2  mov     ebx, eax
0x1800122f4  test    eax, eax
0x1800122f6  js      loc_180012383
0x1800122fc  mov     r12d, [rsp+6D0h+var_678]
0x180012301  mov     rdx, rdi
0x180012304  mov     rbx, [rsp+6D0h+NewFileName]
0x180012309  test    r12d, r12d
0x18001230c  mov     rcx, rdi
0x18001230f  cmovnz  rdx, rbx; NewFileName
0x180012313  cmp     [rsp+6D0h+var_698], 0
0x180012318  cmovnz  rcx, [rsp+6D0h+var_690]; OldFileName
0x18001231e  call    cs:__imp__wrename
0x180012324  test    eax, eax
0x180012326  jnz     short loc_180012381
0x180012328  test    r12d, r12d
0x18001232b  mov     [rsp+6D0h+var_6A0], 0
0x180012334  mov     rcx, rdi
0x180012337  lea     rdx, [rsp+6D0h+var_6A0]; struct IContact **
0x18001233c  cmovnz  rcx, rbx; unsigned __int16 *
0x180012340  call    ?CreateContactFromFile@@YAJPEBGPEAPEAUIContact@@@Z; CreateContactFromFile(ushort const *,IContact * *)
0x180012345  test    eax, eax
0x180012347  js      short loc_180012359
0x180012349  mov     rcx, r15
0x18001234c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180012351  mov     rax, [rsp+6D0h+var_6A0]
0x180012356  mov     [r15], rax
0x180012359  test    r12d, r12d
0x18001235c  mov     r9, rdi
0x18001235f  mov     edx, 3005h; uFlags
0x180012364  mov     ecx, 1; wEventId
0x180012369  cmovnz  r9, rbx; dwItem2
0x18001236d  cmp     [rsp+6D0h+var_698], 0
0x180012372  cmovnz  rdi, [rsp+6D0h+var_690]
0x180012378  mov     r8, rdi; dwItem1
0x18001237b  call    cs:__imp_SHChangeNotify
0x180012381  xor     ebx, ebx
0x180012383  lea     rcx, [rsp+6D0h+NewFileName]; this
0x180012388  mov     [rsp+6D0h+var_678], 0
0x180012390  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180012395  lea     rcx, [rsp+6D0h+var_690]; this
0x18001239a  mov     [rsp+6D0h+var_698], 0
0x1800123a2  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800123a7  mov     eax, ebx
0x1800123a9  mov     rcx, [rbp+5D0h+var_20]
0x1800123b0  xor     rcx, rsp; StackCookie
0x1800123b3  call    __security_check_cookie
0x1800123b8  lea     r11, [rsp+6D0h+var_10]
0x1800123c0  mov     rbx, [r11+28h]
0x1800123c4  mov     rdi, [r11+30h]
0x1800123c8  mov     rsp, r11
0x1800123cb  pop     r15
0x1800123cd  pop     r12
0x1800123cf  pop     rbp
0x1800123d0  retn
```
