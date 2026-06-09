# _InitMultipleFilePropSheet(FILEPROPINFO *)

- ea: `0x18004d8e4`
- end: `0x18004df0a`
- name: `?_InitMultipleFilePropSheet@@YAXPEAUFILEPROPINFO@@@Z`
- size: `1574`
- prototype: `void __fastcall(struct FILEPROPINFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004ac30`

## callees

- `0x180004110`
- `0x180019270`
- `0x180033d04`
- `0x180035590`
- `0x1800361ba`
- `0x1800499e8`
- `0x18004d124`
- `0x18004d8e4`
- `0x18004f2cc`
- `0x1800506b8`
- `0x1800628cc`
- `0x18006d310`
- `0x18006ef2c`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004db7d`
- `KERNEL32!LocalFree` at `0x18004dbd4`
- `KERNEL32!LocalFree` at `0x18004db7d`
- `KERNEL32!LocalFree` at `0x18004dbd4`
- `KERNEL32!lstrcmpiW` at `0x18004da72`
- `KERNEL32!lstrcmpiW` at `0x18004da72`
- `KERNEL32!lstrcmpW` at `0x18004da08`
- `KERNEL32!lstrcmpW` at `0x18004da08`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004da43`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004da43`
- `USER32!LoadStringW` at `0x18004db24`
- `USER32!LoadStringW` at `0x18004db47`
- `USER32!LoadStringW` at `0x18004db9e`
- `USER32!LoadStringW` at `0x18004dbe1`
- `USER32!LoadStringW` at `0x18004ddb3`
- `USER32!LoadStringW` at `0x18004de08`
- `USER32!LoadStringW` at `0x18004de54`
- `USER32!LoadStringW` at `0x18004db24`
- `USER32!LoadStringW` at `0x18004db47`
- `USER32!LoadStringW` at `0x18004db9e`
- `USER32!LoadStringW` at `0x18004dbe1`
- `USER32!LoadStringW` at `0x18004ddb3`
- `USER32!LoadStringW` at `0x18004de08`
- `USER32!LoadStringW` at `0x18004de54`
- `USER32!SetDlgItemTextW` at `0x18004db3a`
- `USER32!SetDlgItemTextW` at `0x18004db74`
- `USER32!SetDlgItemTextW` at `0x18004dbcb`
- `USER32!SetDlgItemTextW` at `0x18004dbf7`
- `USER32!SetDlgItemTextW` at `0x18004ddc9`
- `USER32!SetDlgItemTextW` at `0x18004de6f`
- `USER32!SetDlgItemTextW` at `0x18004db3a`
- `USER32!SetDlgItemTextW` at `0x18004db74`
- `USER32!SetDlgItemTextW` at `0x18004dbcb`
- `USER32!SetDlgItemTextW` at `0x18004dbf7`
- `USER32!SetDlgItemTextW` at `0x18004ddc9`
- `USER32!SetDlgItemTextW` at `0x18004de6f`
- `USER32!GetWindowLongW` at `0x18004dc3e`
- `USER32!GetWindowLongW` at `0x18004dd04`
- `USER32!GetWindowLongW` at `0x18004dc3e`
- `USER32!GetWindowLongW` at `0x18004dd04`
- `USER32!GetDlgItem` at `0x18004dadb`
- `USER32!GetDlgItem` at `0x18004daf8`
- `USER32!GetDlgItem` at `0x18004dc2a`
- `USER32!GetDlgItem` at `0x18004dcee`
- `USER32!GetDlgItem` at `0x18004dea3`
- `USER32!GetDlgItem` at `0x18004dece`
- `USER32!GetDlgItem` at `0x18004dadb`
- `USER32!GetDlgItem` at `0x18004daf8`
- `USER32!GetDlgItem` at `0x18004dc2a`
- `USER32!GetDlgItem` at `0x18004dcee`
- `USER32!GetDlgItem` at `0x18004dea3`
- `USER32!GetDlgItem` at `0x18004dece`
- `USER32!CheckDlgButton` at `0x18004dc72`
- `USER32!CheckDlgButton` at `0x18004dcb8`
- `USER32!CheckDlgButton` at `0x18004dd3a`
- `USER32!CheckDlgButton` at `0x18004dc72`
- `USER32!CheckDlgButton` at `0x18004dcb8`
- `USER32!CheckDlgButton` at `0x18004dd3a`
- `USER32!EnableWindow` at `0x18004deae`
- `USER32!EnableWindow` at `0x18004ded9`
- `USER32!EnableWindow` at `0x18004deae`
- `USER32!EnableWindow` at `0x18004ded9`
- `USER32!ShowWindow` at `0x18004dae9`
- `USER32!ShowWindow` at `0x18004db03`
- `USER32!ShowWindow` at `0x18004dae9`
- `USER32!ShowWindow` at `0x18004db03`
- `USER32!SetWindowLongW` at `0x18004dc53`
- `USER32!SetWindowLongW` at `0x18004dd1b`
- `USER32!SetWindowLongW` at `0x18004dc53`
- `USER32!SetWindowLongW` at `0x18004dd1b`
- `SHELL32!ExtractIconExW` at `0x18004dab5`
- `SHELL32!ExtractIconExW` at `0x18004dab5`
- `SHELL32!SHGetFileInfoW` at `0x18004d9d9`
- `SHELL32!SHGetFileInfoW` at `0x18004d9d9`
- `SHELL32!__imp_ILFree` at `0x18004da84`
- `SHELL32!__imp_ILFree` at `0x18004dcc1`
- `SHELL32!__imp_ILFree` at `0x18004da84`
- `SHELL32!__imp_ILFree` at `0x18004dcc1`

## string_xrefs

- `0x18004daae`: `wpdshext.dll`

## pseudocode

```c
void __fastcall _InitMultipleFilePropSheet(struct FILEPROPINFO *a1)
{
  unsigned int *v2; // rax
  int v3; // esi
  BOOL v4; // r15d
  BOOL v5; // r14d
  unsigned int v6; // edi
  const WCHAR *v7; // rax
  ITEMIDLIST *v8; // rsi
  HWND DlgItem; // rax
  HWND v10; // rax
  const WCHAR *v11; // rax
  WCHAR *v12; // rdi
  const WCHAR *v13; // rax
  WCHAR *v14; // rdi
  struct PROPKEYINFO *CommonProperty; // rax
  HWND v16; // rax
  HWND v17; // rdi
  LONG WindowLongW; // eax
  UINT v19; // r8d
  __int64 v20; // rax
  ITEMIDLIST *v21; // rdi
  struct PROPKEYINFO *v22; // rax
  HWND v23; // rax
  HWND v24; // rdi
  LONG v25; // eax
  UINT v26; // r8d
  struct PROPKEYINFO *v27; // rax
  UINT v28; // edx
  const struct tagPROPVARIANT *v29; // rdx
  struct PROPKEYINFO *v30; // rax
  int v31; // edi
  const struct tagPROPVARIANT *v32; // rdx
  HWND v33; // rax
  HWND v34; // rax
  HICON phiconLarge; // [rsp+30h] [rbp-D0h] BYREF
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR pszPath[264]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR String1[264]; // [rsp+720h] [rbp+620h] BYREF
  WCHAR v40[264]; // [rsp+930h] [rbp+830h] BYREF

  memset_0(&psfi, 0, sizeof(psfi));
  phiconLarge = 0;
  memset_0(pszPath, 0, 0x208u);
  memset_0(v40, 0, 0x208u);
  memset_0(String1, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v2 = (unsigned int *)*((_QWORD *)a1 + 7);
  v3 = 1;
  v4 = 0;
  v5 = 1;
  if ( *v2 )
  {
    v6 = 0;
    do
    {
      if ( v4 && !v5 )
        break;
      v7 = (const WCHAR *)IDA_ILClone(v2, v6);
      v8 = (ITEMIDLIST *)v7;
      if ( v7 )
      {
        if ( !v4 )
        {
          SHGetFileInfoW(v7, 0, &psfi, 0x2B8u, 0x408u);
          if ( String1[0] )
            v4 = lstrcmpW(String1, psfi.szTypeName) != 0;
          else
            StringCchCopyW(String1, 0x104u, psfi.szTypeName);
        }
        if ( v5 && (int)SHGetNameAndFlagsW(v8, 0) >= 0 )
        {
          PathRemoveFileSpecW(pszPath);
          if ( v40[0] )
            v5 = lstrcmpiW(v40, pszPath) == 0;
          else
            StringCchCopyW(v40, 0x104u, pszPath);
        }
        ILFree(v8);
      }
      v2 = (unsigned int *)*((_QWORD *)a1 + 7);
      v3 = 1;
      ++v6;
    }
    while ( v6 < *v2 );
  }
  if ( ExtractIconExW(L"wpdshext.dll", -740, &phiconLarge, 0, 1u) )
    ReplaceDlgIcon(*((_QWORD *)a1 + 3), 311, phiconLarge);
  DlgItem = GetDlgItem(*((HWND *)a1 + 3), 332);
  ShowWindow(DlgItem, 5);
  v10 = GetDlgItem(*((HWND *)a1 + 3), 312);
  ShowWindow(v10, 0);
  if ( v4 )
  {
    LoadStringW(g_hInst, 0x145u, Buffer, 260);
    SetDlgItemTextW(*((HWND *)a1 + 3), 315, Buffer);
  }
  else
  {
    LoadStringW(g_hInst, 0x147u, Buffer, 260);
    v11 = FormatString(Buffer, String1);
    v12 = (WCHAR *)v11;
    if ( v11 )
    {
      SetDlgItemTextW(*((HWND *)a1 + 3), 315, v11);
      LocalFree(v12);
    }
  }
  if ( v5 )
  {
    LoadStringW(g_hInst, 0x146u, Buffer, 260);
    v13 = FormatString(Buffer, v40);
    v14 = (WCHAR *)v13;
    if ( v13 )
    {
      SetDlgItemTextW(*((HWND *)a1 + 3), 318, v13);
      LocalFree(v14);
    }
  }
  else
  {
    LoadStringW(g_hInst, 0x148u, Buffer, 260);
    SetDlgItemTextW(*((HWND *)a1 + 3), 318, Buffer);
  }
  CommonProperty = _RetrieveCommonProperty(a1, &WPD_OBJECT_CAN_DELETE);
  if ( CommonProperty )
  {
    if ( *((_DWORD *)CommonProperty + 15) )
    {
      v16 = GetDlgItem(*((HWND *)a1 + 3), 341);
      v17 = v16;
      if ( v16 )
      {
        WindowLongW = GetWindowLongW(v16, -16);
        SetWindowLongW(v17, -16, WindowLongW & 0xFFFFFFF8 | 6);
      }
      v19 = 2;
    }
    else
    {
      if ( *((_WORD *)CommonProperty + 16) )
        goto LABEL_39;
      v19 = 1;
    }
    CheckDlgButton(*((HWND *)a1 + 3), 341, v19);
  }
  else
  {
    v20 = IDA_ILClone(*((_QWORD *)a1 + 7), 0);
    v21 = (ITEMIDLIST *)v20;
    if ( v20 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, const PROPERTYKEY *))(**((_QWORD **)a1 + 1) + 72LL))(
              *((_QWORD *)a1 + 1),
              v20,
              &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS) )
        CheckDlgButton(*((HWND *)a1 + 3), 341, 1u);
      ILFree(v21);
    }
  }
LABEL_39:
  v22 = _RetrieveCommonProperty(a1, &WPD_OBJECT_ISHIDDEN);
  if ( !v22 )
    goto LABEL_47;
  if ( *((_DWORD *)v22 + 15) )
  {
    v23 = GetDlgItem(*((HWND *)a1 + 3), 342);
    v24 = v23;
    if ( v23 )
    {
      v25 = GetWindowLongW(v23, -16);
      SetWindowLongW(v24, -16, v25 & 0xFFFFFFF8 | 6);
    }
    v26 = 2;
  }
  else
  {
    if ( *((_WORD *)v22 + 16) != 0xFFFF )
      goto LABEL_47;
    v26 = 1;
  }
  CheckDlgButton(*((HWND *)a1 + 3), 342, v26);
LABEL_47:
  v27 = _RetrieveCommonProperty(a1, &WPD_OBJECT_DATE_CREATED);
  if ( !v27 )
  {
    v28 = 9218;
    goto LABEL_55;
  }
  v3 = 0;
  if ( *((_DWORD *)v27 + 15) && !*((_DWORD *)v27 + 14) )
  {
    v28 = 852;
LABEL_55:
    LoadStringW(g_hInst, v28, Buffer, 260);
    goto LABEL_56;
  }
  v29 = (const struct tagPROPVARIANT *)((char *)v27 + 24);
  if ( *((_QWORD *)v27 + 6) )
    (*((void (__fastcall **)(struct PROPKEYINFO *, const struct tagPROPVARIANT *, WCHAR *, __int64))v27 + 6))(
      v27,
      v29,
      Buffer,
      260);
  else
    PropVariantToDisplayString((const struct _tagpropertykey *)v27, v29, Buffer, 0x104u, 2u);
LABEL_56:
  SetDlgItemTextW(*((HWND *)a1 + 3), 337, Buffer);
  v30 = _RetrieveCommonProperty(a1, &WPD_OBJECT_DATE_MODIFIED);
  if ( v30 )
  {
    v31 = 0;
    if ( !*((_DWORD *)v30 + 15) || *((_DWORD *)v30 + 14) )
    {
      v32 = (const struct tagPROPVARIANT *)((char *)v30 + 24);
      if ( *((_QWORD *)v30 + 6) )
        (*((void (__fastcall **)(struct PROPKEYINFO *, const struct tagPROPVARIANT *, WCHAR *, __int64))v30 + 6))(
          v30,
          v32,
          Buffer,
          260);
      else
        PropVariantToDisplayString((const struct _tagpropertykey *)v30, v32, Buffer, 0x104u, 2u);
    }
    else
    {
      LoadStringW(g_hInst, 0x354u, Buffer, 260);
    }
  }
  else
  {
    LoadStringW(g_hInst, 0x2402u, Buffer, 260);
    v31 = 1;
  }
  SetDlgItemTextW(*((HWND *)a1 + 3), 339, Buffer);
  _HideUnusedWindows(*((HWND *)a1 + 3), 1, v3, v31);
  if ( !(unsigned int)_IsPropertyWritable(a1, &WPD_OBJECT_CAN_DELETE) )
  {
    v33 = GetDlgItem(*((HWND *)a1 + 3), 341);
    EnableWindow(v33, 0);
  }
  if ( !(unsigned int)_IsPropertyWritable(a1, &WPD_OBJECT_ISHIDDEN) )
  {
    v34 = GetDlgItem(*((HWND *)a1 + 3), 342);
    EnableWindow(v34, 0);
  }
  CreateSizeThread(a1);
}

```

## disassembly

```asm
0x18004d8e4  push    rbp
0x18004d8e6  push    rbx
0x18004d8e7  push    rsi
0x18004d8e8  push    rdi
0x18004d8e9  push    r12
0x18004d8eb  push    r13
0x18004d8ed  push    r14
0x18004d8ef  push    r15
0x18004d8f1  lea     rbp, [rsp-0A58h]
0x18004d8f9  sub     rsp, 0B58h
0x18004d900  mov     rax, cs:__security_cookie
0x18004d907  xor     rax, rsp
0x18004d90a  mov     [rbp+0A90h+var_50], rax
0x18004d911  mov     rbx, rcx
0x18004d914  xor     edx, edx; Val
0x18004d916  lea     rcx, [rsp+0B90h+psfi]; void *
0x18004d91b  mov     r8d, 2B8h; Size
0x18004d921  call    memset_0
0x18004d926  mov     edi, 208h
0x18004d92b  lea     rcx, [rbp+0A90h+pszPath]; void *
0x18004d932  xor     r12d, r12d
0x18004d935  mov     r8d, edi; Size
0x18004d938  xor     edx, edx; Val
0x18004d93a  mov     [rsp+0B90h+phiconLarge], r12
0x18004d93f  call    memset_0
0x18004d944  mov     r8d, edi; Size
0x18004d947  lea     rcx, [rbp+0A90h+var_260]; void *
0x18004d94e  xor     edx, edx; Val
0x18004d950  call    memset_0
0x18004d955  mov     r8d, edi; Size
0x18004d958  lea     rcx, [rbp+0A90h+String1]; void *
0x18004d95f  xor     edx, edx; Val
0x18004d961  call    memset_0
0x18004d966  mov     r8d, edi; Size
0x18004d969  lea     rcx, [rbp+0A90h+Buffer]; void *
0x18004d970  xor     edx, edx; Val
0x18004d972  call    memset_0
0x18004d977  mov     rax, [rbx+38h]
0x18004d97b  lea     esi, [r12+1]
0x18004d980  mov     r15d, r12d
0x18004d983  mov     r14d, esi
0x18004d986  mov     r13d, 104h
0x18004d98c  cmp     [rax], r12d
0x18004d98f  jbe     loc_18004DA9D
0x18004d995  mov     edi, r12d
0x18004d998  test    r15d, r15d
0x18004d99b  jz      short loc_18004D9A6
0x18004d99d  test    r14d, r14d
0x18004d9a0  jz      loc_18004DA9D
0x18004d9a6  mov     edx, edi
0x18004d9a8  mov     rcx, rax
0x18004d9ab  call    IDA_ILClone
0x18004d9b0  mov     rsi, rax
0x18004d9b3  test    rax, rax
0x18004d9b6  jz      loc_18004DA8A
0x18004d9bc  test    r15d, r15d
0x18004d9bf  jnz     short loc_18004DA17
0x18004d9c1  mov     r9d, 2B8h; cbFileInfo
0x18004d9c7  mov     [rsp+0B90h+uFlags], 408h; uFlags
0x18004d9cf  lea     r8, [rsp+0B90h+psfi]; psfi
0x18004d9d4  xor     edx, edx; dwFileAttributes
0x18004d9d6  mov     rcx, rax; pszPath
0x18004d9d9  call    cs:__imp_SHGetFileInfoW
0x18004d9df  lea     rcx, [rbp+0A90h+String1]; unsigned __int16 *
0x18004d9e6  cmp     [rbp+0A90h+String1], r12w
0x18004d9ee  jnz     short loc_18004DA01
0x18004d9f0  lea     r8, [rbp+0A90h+psfi.szTypeName]; unsigned __int16 *
0x18004d9f7  mov     rdx, r13; unsigned __int64
0x18004d9fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004d9ff  jmp     short loc_18004DA17
0x18004da01  lea     rdx, [rbp+0A90h+psfi.szTypeName]; lpString2
0x18004da08  call    cs:__imp_lstrcmpW
0x18004da0e  test    eax, eax
0x18004da10  mov     r15d, r12d
0x18004da13  setnz   r15b
0x18004da17  test    r14d, r14d
0x18004da1a  jz      short loc_18004DA81
0x18004da1c  mov     r9d, r13d
0x18004da1f  mov     qword ptr [rsp+0B90h+uFlags], r12; __int64
0x18004da24  lea     r8, [rbp+0A90h+pszPath]
0x18004da2b  mov     edx, 0C000h
0x18004da30  mov     rcx, rsi; pidl
0x18004da33  call    SHGetNameAndFlagsW
0x18004da38  test    eax, eax
0x18004da3a  js      short loc_18004DA81
0x18004da3c  lea     rcx, [rbp+0A90h+pszPath]; pszPath
0x18004da43  call    cs:__imp_PathRemoveFileSpecW
0x18004da49  lea     rcx, [rbp+0A90h+var_260]; unsigned __int16 *
0x18004da50  cmp     [rbp+0A90h+var_260], r12w
0x18004da58  jnz     short loc_18004DA6B
0x18004da5a  lea     r8, [rbp+0A90h+pszPath]; unsigned __int16 *
0x18004da61  mov     rdx, r13; unsigned __int64
0x18004da64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004da69  jmp     short loc_18004DA81
0x18004da6b  lea     rdx, [rbp+0A90h+pszPath]; lpString2
0x18004da72  call    cs:__imp_lstrcmpiW
0x18004da78  test    eax, eax
0x18004da7a  mov     r14d, r12d
0x18004da7d  setz    r14b
0x18004da81  mov     rcx, rsi; pidl
0x18004da84  call    cs:__imp_ILFree
0x18004da8a  mov     rax, [rbx+38h]
0x18004da8e  mov     esi, 1
0x18004da93  add     edi, esi
0x18004da95  cmp     edi, [rax]
0x18004da97  jb      loc_18004D998
0x18004da9d  xor     r9d, r9d; phiconSmall
0x18004daa0  mov     [rsp+0B90h+uFlags], esi; nIcons
0x18004daa4  lea     r8, [rsp+0B90h+phiconLarge]; phiconLarge
0x18004daa9  mov     edx, 0FFFFFD1Ch; nIconIndex
0x18004daae  lea     rcx, szFile; "wpdshext.dll"
0x18004dab5  call    cs:__imp_ExtractIconExW
0x18004dabb  test    eax, eax
0x18004dabd  jz      short loc_18004DAD2
0x18004dabf  mov     r8, [rsp+0B90h+phiconLarge]
0x18004dac4  mov     edx, 137h
0x18004dac9  mov     rcx, [rbx+18h]
0x18004dacd  call    ReplaceDlgIcon
0x18004dad2  mov     rcx, [rbx+18h]; hDlg
0x18004dad6  mov     edx, 14Ch; nIDDlgItem
0x18004dadb  call    cs:__imp_GetDlgItem
0x18004dae1  mov     rcx, rax; hWnd
0x18004dae4  mov     edx, 5; nCmdShow
0x18004dae9  call    cs:__imp_ShowWindow
0x18004daef  mov     rcx, [rbx+18h]; hDlg
0x18004daf3  mov     edx, 138h; nIDDlgItem
0x18004daf8  call    cs:__imp_GetDlgItem
0x18004dafe  mov     rcx, rax; hWnd
0x18004db01  xor     edx, edx; nCmdShow
0x18004db03  call    cs:__imp_ShowWindow
0x18004db09  mov     rcx, cs:g_hInst; hInstance
0x18004db10  mov     r9d, r13d; cchBufferMax
0x18004db13  lea     r8, [rbp+0A90h+Buffer]; lpBuffer
0x18004db1a  test    r15d, r15d
0x18004db1d  jz      short loc_18004DB42
0x18004db1f  mov     edx, 145h; uID
0x18004db24  call    cs:__imp_LoadStringW
0x18004db2a  mov     rcx, [rbx+18h]; hDlg
0x18004db2e  lea     r8, [rbp+0A90h+Buffer]; lpString
0x18004db35  mov     edx, 13Bh; nIDDlgItem
0x18004db3a  call    cs:__imp_SetDlgItemTextW
0x18004db40  jmp     short loc_18004DB83
0x18004db42  mov     edx, 147h; uID
0x18004db47  call    cs:__imp_LoadStringW
0x18004db4d  lea     rdx, [rbp+0A90h+String1]
0x18004db54  lea     rcx, [rbp+0A90h+Buffer]; lpSource
0x18004db5b  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x18004db60  mov     rdi, rax
0x18004db63  test    rax, rax
0x18004db66  jz      short loc_18004DB83
0x18004db68  mov     rcx, [rbx+18h]; hDlg
0x18004db6c  mov     r8, rax; lpString
0x18004db6f  mov     edx, 13Bh; nIDDlgItem
0x18004db74  call    cs:__imp_SetDlgItemTextW
0x18004db7a  mov     rcx, rdi; hMem
0x18004db7d  call    cs:__imp_LocalFree
0x18004db83  mov     rcx, cs:g_hInst; hInstance
0x18004db8a  mov     r9d, r13d; cchBufferMax
0x18004db8d  lea     r8, [rbp+0A90h+Buffer]; lpBuffer
0x18004db94  test    r14d, r14d
0x18004db97  jz      short loc_18004DBDC
0x18004db99  mov     edx, 146h; uID
0x18004db9e  call    cs:__imp_LoadStringW
0x18004dba4  lea     rdx, [rbp+0A90h+var_260]
0x18004dbab  lea     rcx, [rbp+0A90h+Buffer]; lpSource
0x18004dbb2  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x18004dbb7  mov     rdi, rax
0x18004dbba  test    rax, rax
0x18004dbbd  jz      short loc_18004DBFD
0x18004dbbf  mov     rcx, [rbx+18h]; hDlg
0x18004dbc3  mov     r8, rax; lpString
0x18004dbc6  mov     edx, 13Eh; nIDDlgItem
0x18004dbcb  call    cs:__imp_SetDlgItemTextW
0x18004dbd1  mov     rcx, rdi; hMem
0x18004dbd4  call    cs:__imp_LocalFree
0x18004dbda  jmp     short loc_18004DBFD
0x18004dbdc  mov     edx, 148h; uID
0x18004dbe1  call    cs:__imp_LoadStringW
0x18004dbe7  mov     rcx, [rbx+18h]; hDlg
0x18004dbeb  lea     r8, [rbp+0A90h+Buffer]; lpString
0x18004dbf2  mov     edx, 13Eh; nIDDlgItem
0x18004dbf7  call    cs:__imp_SetDlgItemTextW
0x18004dbfd  lea     rdx, WPD_OBJECT_CAN_DELETE; struct _tagpropertykey *
0x18004dc04  mov     rcx, rbx; struct FILEPROPINFO *
0x18004dc07  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004dc0c  mov     r14d, 155h
0x18004dc12  mov     r15d, 0FFFFFFF0h
0x18004dc18  test    rax, rax
0x18004dc1b  jz      short loc_18004DC7A
0x18004dc1d  cmp     [rax+3Ch], r12d
0x18004dc21  jz      short loc_18004DC61
0x18004dc23  mov     rcx, [rbx+18h]; hDlg
0x18004dc27  mov     edx, r14d; nIDDlgItem
0x18004dc2a  call    cs:__imp_GetDlgItem
0x18004dc30  mov     rdi, rax
0x18004dc33  test    rax, rax
0x18004dc36  jz      short loc_18004DC59
0x18004dc38  mov     edx, r15d; nIndex
0x18004dc3b  mov     rcx, rax; hWnd
0x18004dc3e  call    cs:__imp_GetWindowLongW
0x18004dc44  mov     edx, r15d; nIndex
0x18004dc47  mov     rcx, rdi; hWnd
0x18004dc4a  and     eax, 0FFFFFFFEh
0x18004dc4d  or      eax, 6
0x18004dc50  mov     r8d, eax; dwNewLong
0x18004dc53  call    cs:__imp_SetWindowLongW
0x18004dc59  mov     r8d, 2
0x18004dc5f  jmp     short loc_18004DC6B
0x18004dc61  cmp     [rax+20h], r12w
0x18004dc66  jnz     short loc_18004DCC7
0x18004dc68  mov     r8d, esi; uCheck
0x18004dc6b  mov     rcx, [rbx+18h]; hDlg
0x18004dc6f  mov     edx, r14d; nIDButton
0x18004dc72  call    cs:__imp_CheckDlgButton
0x18004dc78  jmp     short loc_18004DCC7
0x18004dc7a  mov     rcx, [rbx+38h]
0x18004dc7e  xor     edx, edx
0x18004dc80  call    IDA_ILClone
0x18004dc85  mov     rdi, rax
0x18004dc88  test    rax, rax
0x18004dc8b  jz      short loc_18004DCC7
0x18004dc8d  mov     r9, [rbx+8]
0x18004dc91  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS
0x18004dc98  mov     rdx, rdi
0x18004dc9b  mov     rcx, [r9]
0x18004dc9e  mov     rax, [rcx+48h]
0x18004dca2  mov     rcx, r9
0x18004dca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcaa  test    eax, eax
0x18004dcac  jnz     short loc_18004DCBE
0x18004dcae  mov     rcx, [rbx+18h]; hDlg
0x18004dcb2  mov     r8d, esi; uCheck
0x18004dcb5  mov     edx, r14d; nIDButton
0x18004dcb8  call    cs:__imp_CheckDlgButton
0x18004dcbe  mov     rcx, rdi; pidl
0x18004dcc1  call    cs:__imp_ILFree
0x18004dcc7  lea     rdx, WPD_OBJECT_ISHIDDEN; struct _tagpropertykey *
0x18004dcce  mov     rcx, rbx; struct FILEPROPINFO *
0x18004dcd1  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004dcd6  mov     r15d, 156h
0x18004dcdc  test    rax, rax
0x18004dcdf  jz      short loc_18004DD40
0x18004dce1  cmp     [rax+3Ch], r12d
0x18004dce5  jz      short loc_18004DD29
0x18004dce7  mov     rcx, [rbx+18h]; hDlg
0x18004dceb  mov     edx, r15d; nIDDlgItem
0x18004dcee  call    cs:__imp_GetDlgItem
0x18004dcf4  mov     rdi, rax
0x18004dcf7  test    rax, rax
0x18004dcfa  jz      short loc_18004DD21
0x18004dcfc  mov     edx, 0FFFFFFF0h; nIndex
0x18004dd01  mov     rcx, rax; hWnd
0x18004dd04  call    cs:__imp_GetWindowLongW
0x18004dd0a  mov     edx, 0FFFFFFF0h; nIndex
0x18004dd0f  mov     rcx, rdi; hWnd
0x18004dd12  and     eax, 0FFFFFFFEh
0x18004dd15  or      eax, 6
0x18004dd18  mov     r8d, eax; dwNewLong
0x18004dd1b  call    cs:__imp_SetWindowLongW
0x18004dd21  mov     r8d, 2
0x18004dd27  jmp     short loc_18004DD33
0x18004dd29  cmp     word ptr [rax+20h], 0FFFFh
0x18004dd2e  jnz     short loc_18004DD40
0x18004dd30  mov     r8d, esi; uCheck
0x18004dd33  mov     rcx, [rbx+18h]; hDlg
0x18004dd37  mov     edx, r15d; nIDButton
0x18004dd3a  call    cs:__imp_CheckDlgButton
0x18004dd40  lea     rdx, WPD_OBJECT_DATE_CREATED; struct _tagpropertykey *
0x18004dd47  mov     rcx, rbx; struct FILEPROPINFO *
0x18004dd4a  call    ?_RetrieveCommonProperty@@YAPEAUPROPKEYINFO@@PEAUFILEPROPINFO@@AEBU_tagpropertykey@@@Z; _RetrieveCommonProperty(FILEPROPINFO *,_tagpropertykey const &)
0x18004dd4f  mov     edi, 2402h
0x18004dd54  test    rax, rax
0x18004dd57  jz      short loc_18004DDA0
0x18004dd59  mov     esi, r12d
0x18004dd5c  cmp     [rax+3Ch], r12d
0x18004dd60  jz      short loc_18004DD6F
0x18004dd62  cmp     [rax+38h], r12d
0x18004dd66  jnz     short loc_18004DD6F
0x18004dd68  mov     edx, 354h
0x18004dd6d  jmp     short loc_18004DDA2
0x18004dd6f  lea     rdx, [rax+18h]; struct tagPROPVARIANT *
0x18004dd73  mov     r9d, r13d; unsigned int
0x18004dd76  lea     r8, [rbp+0A90h+Buffer]; unsigned __int16 *
0x18004dd7d  mov     rcx, rax; struct _tagpropertykey *
0x18004dd80  cmp     [rax+30h], r12
0x18004dd84  jz      short loc_18004DD91
0x18004dd86  mov     rax, [rax+30h]
0x18004dd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd8f  jmp     short loc_18004DDB9
0x18004dd91  mov     [rsp+0B90h+uFlags], 2; unsigned int
0x18004dd99  call    ?PropVariantToDisplayString@@YAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAGIK@Z; PropVariantToDisplayString(_tagpropertykey const &,tagPROPVARIANT const &,ushort *,uint,ulong)
0x18004dd9e  jmp     short loc_18004DDB9
0x18004dda0  mov     edx, edi; uID
0x18004dda2  mov     rcx, cs:g_hInst; hInstance
0x18004dda9  lea     r8, [rbp+0A90h+Buffer]; lpBuffer
0x18004ddb0  mov     r9d, r13d; cchBufferMax
0x18004ddb3  call    cs:__imp_LoadStringW
0x18004ddb9  mov     rcx, [rbx+18h]; hDlg
0x18004ddbd  lea     r8, [rbp+0A90h+Buffer]; lpString
0x18004ddc4  mov     edx, 151h; nIDDlgItem
  ... truncated ...
```
