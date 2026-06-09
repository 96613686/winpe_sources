# _InitSingleFilePropSheet(FILEPROPINFO *)

- ea: `0x18004ee88`
- end: `0x18004f2c6`
- name: `?_InitSingleFilePropSheet@@YAXPEAUFILEPROPINFO@@@Z`
- size: `1086`
- prototype: `void __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004ac30`

## callees

- `0x180004110`
- `0x180019270`
- `0x1800285c8`
- `0x180033d04`
- `0x180035590`
- `0x1800361ba`
- `0x1800499e8`
- `0x18004d124`
- `0x18004ee88`
- `0x18004f2cc`
- `0x1800506b8`
- `0x1800628cc`
- `0x18006ef2c`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x18004f08c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004f08c`
- `USER32!LoadStringW` at `0x18004f178`
- `USER32!LoadStringW` at `0x18004f1e8`
- `USER32!LoadStringW` at `0x18004f178`
- `USER32!LoadStringW` at `0x18004f1e8`
- `USER32!SendMessageW` at `0x18004f04c`
- `USER32!SendMessageW` at `0x18004f04c`
- `USER32!SetDlgItemTextW` at `0x18004ef6a`
- `USER32!SetDlgItemTextW` at `0x18004efa0`
- `USER32!SetDlgItemTextW` at `0x18004f0a2`
- `USER32!SetDlgItemTextW` at `0x18004f191`
- `USER32!SetDlgItemTextW` at `0x18004f201`
- `USER32!SetDlgItemTextW` at `0x18004ef6a`
- `USER32!SetDlgItemTextW` at `0x18004efa0`
- `USER32!SetDlgItemTextW` at `0x18004f0a2`
- `USER32!SetDlgItemTextW` at `0x18004f191`
- `USER32!SetDlgItemTextW` at `0x18004f201`
- `USER32!GetDlgItem` at `0x18004f022`
- `USER32!GetDlgItem` at `0x18004f23e`
- `USER32!GetDlgItem` at `0x18004f26b`
- `USER32!GetDlgItem` at `0x18004f022`
- `USER32!GetDlgItem` at `0x18004f23e`
- `USER32!GetDlgItem` at `0x18004f26b`
- `USER32!SendDlgItemMessageW` at `0x18004efbf`
- `USER32!SendDlgItemMessageW` at `0x18004efbf`
- `USER32!CheckDlgButton` at `0x18004f0ef`
- `USER32!CheckDlgButton` at `0x18004f11c`
- `USER32!CheckDlgButton` at `0x18004f0ef`
- `USER32!CheckDlgButton` at `0x18004f11c`
- `USER32!EnableWindow` at `0x18004f249`
- `USER32!EnableWindow` at `0x18004f276`
- `USER32!EnableWindow` at `0x18004f249`
- `USER32!EnableWindow` at `0x18004f276`
- `SHELL32!SHGetFileInfoW` at `0x18004ef42`
- `SHELL32!SHGetFileInfoW` at `0x18004ef42`
- `SHELL32!SHBindToParent` at `0x18004efd7`
- `SHELL32!SHBindToParent` at `0x18004efd7`
- `SHELL32!__imp_ILFree` at `0x18004f287`
- `SHELL32!__imp_ILFree` at `0x18004f287`
- `SHELL32!__imp_SHLimitInputEdit` at `0x18004f05a`
- `SHELL32!__imp_SHLimitInputEdit` at `0x18004f05a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _InitSingleFilePropSheet(struct FILEPROPINFO *a1)
{
  const WCHAR *v2; // rax
  ITEMIDLIST *v3; // rsi
  HWND DlgItem; // rax
  HWND v5; // rdi
  int v6; // edx
  struct PROPKEYINFO *CommonProperty; // rax
  bool v8; // zf
  struct PROPKEYINFO *v9; // rax
  struct PROPKEYINFO *v10; // rax
  int v11; // r14d
  const struct tagPROPVARIANT *v12; // rdx
  struct PROPKEYINFO *v13; // rax
  int v14; // edi
  const struct tagPROPVARIANT *v15; // rdx
  HWND v16; // rax
  HWND v17; // rax
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v19[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  SHFILEINFOW psfi; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR pszPath[264]; // [rsp+520h] [rbp+420h] BYREF

  *(_QWORD *)&v19[1] = 0;
  v20[0] = 0;
  memset_0(&psfi, 0, sizeof(psfi));
  memset_0(Buffer, 0, 0x208u);
  memset_0(pszPath, 0, 0x208u);
  v19[0] = 0x20000000;
  v18 = 0;
  v2 = (const WCHAR *)IDA_ILClone(*((_QWORD *)a1 + 7), 0);
  v3 = (ITEMIDLIST *)v2;
  if ( v2 )
  {
    psfi.dwAttributes = 16;
    if ( SHGetFileInfoW(v2, 0, &psfi, 0x2B8u, 0x20F28u) )
    {
      SetDlgItemTextW(*((HWND *)a1 + 3), 312, psfi.szDisplayName);
      StringCchCopyW((unsigned __int16 *)a1 + 48, 0x104u, psfi.szDisplayName);
      ReplaceDlgIcon(*((_QWORD *)a1 + 3), 311, psfi.hIcon);
      SetDlgItemTextW(*((HWND *)a1 + 3), 315, psfi.szTypeName);
      if ( (psfi.dwAttributes & 0x10) == 0 )
        SendDlgItemMessageW(*((HWND *)a1 + 3), 312, 0xCFu, 1u, 0);
      if ( SHBindToParent(v3, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v19[1], 0) >= 0 )
      {
        if ( (***(int (__fastcall ****)(_QWORD, GUID *, _QWORD *))&v19[1])(
               *(_QWORD *)&v19[1],
               &GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4,
               v20) >= 0 )
          (*(void (__fastcall **)(_QWORD, WCHAR *, int *))(*(_QWORD *)v20[0] + 32LL))(v20[0], psfi.szDisplayName, &v18);
        DlgItem = GetDlgItem(*((HWND *)a1 + 3), 312);
        v5 = DlgItem;
        if ( DlgItem )
        {
          v6 = 128;
          if ( v18 )
            v6 = v18;
          SendMessageW(DlgItem, 0xC5u, v6, 0);
          SHLimitInputEdit(v5, *(IShellFolder **)&v19[1]);
        }
      }
    }
    if ( (int)SHGetNameAndFlagsW(v3, (__int64)v19) >= 0 )
    {
      PathRemoveFileSpecW(pszPath);
      SetDlgItemTextW(*((HWND *)a1 + 3), 318, pszPath);
    }
    CommonProperty = _RetrieveCommonProperty(a1, &WPD_OBJECT_CAN_DELETE);
    if ( CommonProperty )
      v8 = *((_WORD *)CommonProperty + 16) == 0;
    else
      v8 = (*(unsigned int (__fastcall **)(_QWORD, ITEMIDLIST *, const PROPERTYKEY *))(**((_QWORD **)a1 + 1) + 72LL))(
             *((_QWORD *)a1 + 1),
             v3,
             &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS) == 0;
    if ( v8 )
      CheckDlgButton(*((HWND *)a1 + 3), 341, 1u);
    v9 = _RetrieveCommonProperty(a1, &WPD_OBJECT_ISHIDDEN);
    if ( v9 && *((_WORD *)v9 + 16) == 0xFFFF )
      CheckDlgButton(*((HWND *)a1 + 3), 342, 1u);
    v10 = _RetrieveCommonProperty(a1, &WPD_OBJECT_DATE_CREATED);
    if ( v10 )
    {
      v11 = 0;
      v12 = (const struct tagPROPVARIANT *)((char *)v10 + 24);
      if ( *((_QWORD *)v10 + 6) )
        (*((void (__fastcall **)(struct PROPKEYINFO *, const struct tagPROPVARIANT *, WCHAR *, __int64))v10 + 6))(
          v10,
          v12,
          Buffer,
          260);
      else
        PropVariantToDisplayString((const struct _tagpropertykey *)v10, v12, Buffer, 0x104u, 3u);
    }
    else
    {
      LoadStringW(g_hInst, 0x2402u, Buffer, 260);
      v11 = 1;
    }
    SetDlgItemTextW(*((HWND *)a1 + 3), 337, Buffer);
    v13 = _RetrieveCommonProperty(a1, &WPD_OBJECT_DATE_MODIFIED);
    if ( v13 )
    {
      v14 = 0;
      v15 = (const struct tagPROPVARIANT *)((char *)v13 + 24);
      if ( *((_QWORD *)v13 + 6) )
        (*((void (__fastcall **)(struct PROPKEYINFO *, const struct tagPROPVARIANT *, WCHAR *, __int64))v13 + 6))(
          v13,
          v15,
          Buffer,
          260);
      else
        PropVariantToDisplayString((const struct _tagpropertykey *)v13, v15, Buffer, 0x104u, 3u);
    }
    else
    {
      LoadStringW(g_hInst, 0x2402u, Buffer, 260);
      v14 = 1;
    }
    SetDlgItemTextW(*((HWND *)a1 + 3), 339, Buffer);
    _HideUnusedWindows(*((HWND *)a1 + 3), ((v19[0] >> 29) & 1) == 0, v11, v14);
    if ( !(unsigned int)_IsPropertyWritable(a1, &WPD_OBJECT_CAN_DELETE) )
    {
      v16 = GetDlgItem(*((HWND *)a1 + 3), 341);
      EnableWindow(v16, 0);
    }
    if ( !(unsigned int)_IsPropertyWritable(a1, &WPD_OBJECT_ISHIDDEN) )
    {
      v17 = GetDlgItem(*((HWND *)a1 + 3), 342);
      EnableWindow(v17, 0);
    }
    CreateSizeThread(a1);
    ILFree(v3);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19[1]);
}

```

## disassembly

```asm
0x18004ee88  push    rbp
0x18004ee8a  push    rbx
0x18004ee8b  push    rsi
0x18004ee8c  push    rdi
0x18004ee8d  push    r12
0x18004ee8f  push    r13
0x18004ee91  push    r14
0x18004ee93  push    r15
0x18004ee95  lea     rbp, [rsp-648h]
0x18004ee9d  sub     rsp, 748h
0x18004eea4  mov     rax, cs:__security_cookie
0x18004eeab  xor     rax, rsp
0x18004eeae  mov     [rbp+680h+var_50], rax
0x18004eeb5  mov     rbx, rcx
0x18004eeb8  xor     r15d, r15d
0x18004eebb  mov     qword ptr [rsp+780h+var_74C+4], r15
0x18004eec0  mov     [rsp+780h+var_740], r15
0x18004eec5  mov     r14d, 2B8h
0x18004eecb  mov     r8d, r14d; Size
0x18004eece  xor     edx, edx; Val
0x18004eed0  lea     rcx, [rsp+780h+psfi]; void *
0x18004eed5  call    memset_0
0x18004eeda  mov     edi, 208h
0x18004eedf  mov     r8d, edi; Size
0x18004eee2  xor     edx, edx; Val
0x18004eee4  lea     rcx, [rbp+680h+Buffer]; void *
0x18004eeeb  call    memset_0
0x18004eef0  mov     r8d, edi; Size
0x18004eef3  xor     edx, edx; Val
0x18004eef5  lea     rcx, [rbp+680h+pszPath]; void *
0x18004eefc  call    memset_0
0x18004ef01  mov     dword ptr [rsp+780h+var_74C], 20000000h
0x18004ef09  mov     [rsp+780h+var_750], r15d
0x18004ef0e  xor     edx, edx
0x18004ef10  mov     rcx, [rbx+38h]
0x18004ef14  call    IDA_ILClone
0x18004ef19  mov     rsi, rax
0x18004ef1c  test    rax, rax
0x18004ef1f  jz      loc_18004F28E
0x18004ef25  mov     [rsp+780h+psfi.dwAttributes], 10h
0x18004ef2d  mov     [rsp+780h+uFlags], 20F28h; uFlags
0x18004ef35  mov     r9d, r14d; cbFileInfo
0x18004ef38  lea     r8, [rsp+780h+psfi]; psfi
0x18004ef3d  xor     edx, edx; dwFileAttributes
0x18004ef3f  mov     rcx, rax; pszPath
0x18004ef42  call    cs:__imp_SHGetFileInfoW
0x18004ef48  mov     r13d, 104h
0x18004ef4e  lea     r12d, [r15+1]
0x18004ef52  test    rax, rax
0x18004ef55  jz      loc_18004F060
0x18004ef5b  lea     r8, [rsp+780h+psfi.szDisplayName]; lpString
0x18004ef60  lea     edi, [r13+34h]
0x18004ef64  mov     edx, edi; nIDDlgItem
0x18004ef66  mov     rcx, [rbx+18h]; hDlg
0x18004ef6a  call    cs:__imp_SetDlgItemTextW
0x18004ef70  lea     rcx, [rbx+60h]; unsigned __int16 *
0x18004ef74  lea     r8, [rsp+780h+psfi.szDisplayName]; unsigned __int16 *
0x18004ef79  mov     edx, r13d; unsigned __int64
0x18004ef7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ef81  mov     r8, [rsp+780h+psfi.hIcon]
0x18004ef86  lea     edx, [rdi-1]
0x18004ef89  mov     rcx, [rbx+18h]
0x18004ef8d  call    ReplaceDlgIcon
0x18004ef92  lea     r8, [rbp+680h+psfi.szTypeName]; lpString
0x18004ef99  lea     edx, [rdi+3]; nIDDlgItem
0x18004ef9c  mov     rcx, [rbx+18h]; hDlg
0x18004efa0  call    cs:__imp_SetDlgItemTextW
0x18004efa6  test    byte ptr [rsp+780h+psfi.dwAttributes], 10h
0x18004efab  jnz     short loc_18004EFC5
0x18004efad  mov     qword ptr [rsp+780h+uFlags], r15; lParam
0x18004efb2  mov     r9d, r12d; wParam
0x18004efb5  lea     r8d, [r13-35h]; Msg
0x18004efb9  mov     edx, edi; nIDDlgItem
0x18004efbb  mov     rcx, [rbx+18h]; hDlg
0x18004efbf  call    cs:__imp_SendDlgItemMessageW
0x18004efc5  xor     r9d, r9d; ppidlLast
0x18004efc8  lea     r8, [rsp+780h+var_74C+4]; ppv
0x18004efcd  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18004efd4  mov     rcx, rsi; pidl
0x18004efd7  call    cs:__imp_SHBindToParent
0x18004efdd  test    eax, eax
0x18004efdf  js      short loc_18004F060
0x18004efe1  mov     rcx, qword ptr [rsp+780h+var_74C+4]
0x18004efe6  mov     rax, [rcx]
0x18004efe9  lea     r8, [rsp+780h+var_740]
0x18004efee  lea     rdx, _GUID_1df0d7f1_b267_4d28_8b10_12e23202a5c4
0x18004eff5  mov     rax, [rax]
0x18004eff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004effd  test    eax, eax
0x18004efff  js      short loc_18004F01C
0x18004f001  mov     rcx, [rsp+780h+var_740]
0x18004f006  mov     rax, [rcx]
0x18004f009  lea     r8, [rsp+780h+var_750]
0x18004f00e  lea     rdx, [rsp+780h+psfi.szDisplayName]
0x18004f013  mov     rax, [rax+20h]
0x18004f017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f01c  mov     edx, edi; nIDDlgItem
0x18004f01e  mov     rcx, [rbx+18h]; hDlg
0x18004f022  call    cs:__imp_GetDlgItem
0x18004f028  mov     rdi, rax
0x18004f02b  test    rax, rax
0x18004f02e  jz      short loc_18004F060
0x18004f030  mov     edx, 80h
0x18004f035  mov     ecx, [rsp+780h+var_750]
0x18004f039  test    ecx, ecx
0x18004f03b  cmovnz  edx, ecx
0x18004f03e  movsxd  r8, edx; wParam
0x18004f041  xor     r9d, r9d; lParam
0x18004f044  mov     edx, 0C5h; Msg
0x18004f049  mov     rcx, rax; hWnd
0x18004f04c  call    cs:__imp_SendMessageW
0x18004f052  mov     rdx, qword ptr [rsp+780h+var_74C+4]; psf
0x18004f057  mov     rcx, rdi; hwndEdit
0x18004f05a  call    cs:__imp_SHLimitInputEdit
0x18004f060  lea     rax, [rsp+780h+var_74C]
0x18004f065  mov     qword ptr [rsp+780h+uFlags], rax; __int64
0x18004f06a  mov     r9d, r13d
0x18004f06d  lea     r8, [rbp+680h+pszPath]
0x18004f074  mov     edx, 0C000h
0x18004f079  mov     rcx, rsi; pidl
0x18004f07c  call    SHGetNameAndFlagsW
0x18004f081  test    eax, eax
0x18004f083  js      short loc_18004F0A8
0x18004f085  lea     rcx, [rbp+680h+pszPath]; pszPath
0x18004f08c  call    cs:__imp_PathRemoveFileSpecW
0x18004f092  lea     r8, [rbp+680h+pszPath]; lpString
0x18004f099  mov     edx, 13Eh; nIDDlgItem
0x18004f09e  mov     rcx, [rbx+18h]; hDlg
0x18004f0a2  call    cs:__imp_SetDlgItemTextW
0x18004f0a8  lea     rdx, WPD_OBJECT_CAN_DELETE; struct _tagpropertykey *
0x18004f0af  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f0b2  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004f0b7  mov     edi, 155h
0x18004f0bc  test    rax, rax
0x18004f0bf  jz      short loc_18004F0C8
0x18004f0c1  cmp     [rax+20h], r15w
0x18004f0c6  jmp     short loc_18004F0E4
0x18004f0c8  mov     rcx, [rbx+8]
0x18004f0cc  mov     rax, [rcx]
0x18004f0cf  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS
0x18004f0d6  mov     rdx, rsi
0x18004f0d9  mov     rax, [rax+48h]
0x18004f0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0e2  test    eax, eax
0x18004f0e4  jnz     short loc_18004F0F5
0x18004f0e6  mov     r8d, r12d; uCheck
0x18004f0e9  mov     edx, edi; nIDButton
0x18004f0eb  mov     rcx, [rbx+18h]; hDlg
0x18004f0ef  call    cs:__imp_CheckDlgButton
0x18004f0f5  lea     rdx, WPD_OBJECT_ISHIDDEN; struct _tagpropertykey *
0x18004f0fc  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f0ff  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004f104  test    rax, rax
0x18004f107  jz      short loc_18004F122
0x18004f109  cmp     word ptr [rax+20h], 0FFFFh
0x18004f10e  jnz     short loc_18004F122
0x18004f110  mov     r8d, r12d; uCheck
0x18004f113  mov     edx, 156h; nIDButton
0x18004f118  mov     rcx, [rbx+18h]; hDlg
0x18004f11c  call    cs:__imp_CheckDlgButton
0x18004f122  lea     rdx, WPD_OBJECT_DATE_CREATED; struct _tagpropertykey *
0x18004f129  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f12c  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004f131  mov     edi, 2402h
0x18004f136  mov     r9d, r13d; unsigned int
0x18004f139  lea     r8, [rbp+680h+Buffer]; unsigned __int16 *
0x18004f140  test    rax, rax
0x18004f143  jz      short loc_18004F16F
0x18004f145  mov     r14d, r15d
0x18004f148  lea     rdx, [rax+18h]; struct tagPROPVARIANT *
0x18004f14c  mov     rcx, rax; struct _tagpropertykey *
0x18004f14f  cmp     [rax+30h], r15
0x18004f153  jz      short loc_18004F160
0x18004f155  mov     rax, [rax+30h]
0x18004f159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f15e  jmp     short loc_18004F181
0x18004f160  mov     [rsp+780h+uFlags], 3; unsigned int
0x18004f168  call    ?PropVariantToDisplayString@@YAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAGIK@Z; PropVariantToDisplayString(_tagpropertykey const &,tagPROPVARIANT const &,ushort *,uint,ulong)
0x18004f16d  jmp     short loc_18004F181
0x18004f16f  mov     edx, edi; uID
0x18004f171  mov     rcx, cs:g_hInst; hInstance
0x18004f178  call    cs:__imp_LoadStringW
0x18004f17e  mov     r14d, r12d
0x18004f181  lea     r8, [rbp+680h+Buffer]; lpString
0x18004f188  mov     edx, 151h; nIDDlgItem
0x18004f18d  mov     rcx, [rbx+18h]; hDlg
0x18004f191  call    cs:__imp_SetDlgItemTextW
0x18004f197  lea     rdx, WPD_OBJECT_DATE_MODIFIED; struct _tagpropertykey *
0x18004f19e  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f1a1  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004f1a6  mov     r9d, r13d; unsigned int
0x18004f1a9  lea     r8, [rbp+680h+Buffer]; unsigned __int16 *
0x18004f1b0  test    rax, rax
0x18004f1b3  jz      short loc_18004F1DF
0x18004f1b5  mov     edi, r15d
0x18004f1b8  lea     rdx, [rax+18h]; struct tagPROPVARIANT *
0x18004f1bc  mov     rcx, rax; struct _tagpropertykey *
0x18004f1bf  cmp     [rax+30h], r15
0x18004f1c3  jz      short loc_18004F1D0
0x18004f1c5  mov     rax, [rax+30h]
0x18004f1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1ce  jmp     short loc_18004F1F1
0x18004f1d0  mov     [rsp+780h+uFlags], 3; unsigned int
0x18004f1d8  call    ?PropVariantToDisplayString@@YAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAGIK@Z; PropVariantToDisplayString(_tagpropertykey const &,tagPROPVARIANT const &,ushort *,uint,ulong)
0x18004f1dd  jmp     short loc_18004F1F1
0x18004f1df  mov     edx, edi; uID
0x18004f1e1  mov     rcx, cs:g_hInst; hInstance
0x18004f1e8  call    cs:__imp_LoadStringW
0x18004f1ee  mov     edi, r12d
0x18004f1f1  lea     r8, [rbp+680h+Buffer]; lpString
0x18004f1f8  mov     edx, 153h; nIDDlgItem
0x18004f1fd  mov     rcx, [rbx+18h]; hDlg
0x18004f201  call    cs:__imp_SetDlgItemTextW
0x18004f207  mov     edx, dword ptr [rsp+780h+var_74C]
0x18004f20b  shr     edx, 1Dh
0x18004f20e  not     edx
0x18004f210  and     edx, r12d; int
0x18004f213  mov     r9d, edi; int
0x18004f216  mov     r8d, r14d; int
0x18004f219  mov     rcx, [rbx+18h]; hWnd
0x18004f21d  call    ?_HideUnusedWindows@@YAXPEAUHWND__@@HHH@Z; _HideUnusedWindows(HWND__ *,int,int,int)
0x18004f222  lea     rdx, WPD_OBJECT_CAN_DELETE; struct _tagpropertykey *
0x18004f229  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f22c  call    ?_IsPropertyWritable@@YAHPEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _IsPropertyWritable(FILEPROPINFO *,_tagpropertykey const &)
0x18004f231  test    eax, eax
0x18004f233  jnz     short loc_18004F24F
0x18004f235  mov     edx, 155h; nIDDlgItem
0x18004f23a  mov     rcx, [rbx+18h]; hDlg
0x18004f23e  call    cs:__imp_GetDlgItem
0x18004f244  mov     rcx, rax; hWnd
0x18004f247  xor     edx, edx; bEnable
0x18004f249  call    cs:__imp_EnableWindow
0x18004f24f  lea     rdx, WPD_OBJECT_ISHIDDEN; struct _tagpropertykey *
0x18004f256  mov     rcx, rbx; struct FILEPROPINFO *
0x18004f259  call    ?_IsPropertyWritable@@YAHPEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _IsPropertyWritable(FILEPROPINFO *,_tagpropertykey const &)
0x18004f25e  test    eax, eax
0x18004f260  jnz     short loc_18004F27C
0x18004f262  mov     edx, 156h; nIDDlgItem
0x18004f267  mov     rcx, [rbx+18h]; hDlg
0x18004f26b  call    cs:__imp_GetDlgItem
0x18004f271  mov     rcx, rax; hWnd
0x18004f274  xor     edx, edx; bEnable
0x18004f276  call    cs:__imp_EnableWindow
0x18004f27c  mov     rcx, rbx; pData
0x18004f27f  call    ?CreateSizeThread@@YAXPEAUFILEPROPINFO@@@Z; CreateSizeThread(FILEPROPINFO *)
0x18004f284  mov     rcx, rsi; pidl
0x18004f287  call    cs:__imp_ILFree
0x18004f28d  nop
0x18004f28e  lea     rcx, [rsp+780h+var_740]
0x18004f293  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f298  nop
0x18004f299  lea     rcx, [rsp+780h+var_74C+4]
0x18004f29e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f2a3  mov     rcx, [rbp+680h+var_50]
0x18004f2aa  xor     rcx, rsp; StackCookie
0x18004f2ad  call    __security_check_cookie
0x18004f2b2  add     rsp, 748h
0x18004f2b9  pop     r15
0x18004f2bb  pop     r14
0x18004f2bd  pop     r13
0x18004f2bf  pop     r12
0x18004f2c1  pop     rdi
0x18004f2c2  pop     rsi
0x18004f2c3  pop     rbx
0x18004f2c4  pop     rbp
0x18004f2c5  retn
```
