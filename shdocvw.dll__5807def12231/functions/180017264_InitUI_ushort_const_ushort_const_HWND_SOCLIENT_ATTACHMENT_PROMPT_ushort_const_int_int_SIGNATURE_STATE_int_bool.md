# InitUI(ushort const *,ushort const *,HWND__ *,SOCLIENT,ATTACHMENT_PROMPT,ushort const *,int,int,SIGNATURE_STATE,int,bool,ushort const * *,HICON__ * *,HFONT__ * *,ulong)

- ea: `0x180017264`
- end: `0x1800178e8`
- name: `?InitUI@@YAHPEBG0PEAUHWND__@@W4SOCLIENT@@W4ATTACHMENT_PROMPT@@0HHW4SIGNATURE_STATE@@H_NPEAPEBGPEAPEAUHICON__@@PEAPEAUHFONT__@@K@Z`
- size: `1668`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180019170`

## callees

- `0x180008320`
- `0x180009018`
- `0x18000bf78`
- `0x180017264`
- `0x180017f38`
- `0x180018114`
- `0x18001d4d4`
- `0x180026538`
- `0x180027354`

## import_xrefs

- `SHELL32!SHGetFileInfoW` at `0x1800174b5`
- `SHELL32!SHGetFileInfoW` at `0x1800174fb`
- `SHELL32!SHGetFileInfoW` at `0x1800174b5`
- `SHELL32!SHGetFileInfoW` at `0x1800174fb`
- `SHELL32!ExtractIconExW` at `0x180017469`
- `SHELL32!ExtractIconExW` at `0x180017469`
- `SHLWAPI!AssocQueryStringW` at `0x180017435`
- `SHLWAPI!AssocQueryStringW` at `0x180017435`
- `SHLWAPI!PathParseIconLocationW` at `0x18001744c`
- `SHLWAPI!PathParseIconLocationW` at `0x18001744c`
- `SHLWAPI!AssocGetPerceivedType` at `0x180017542`
- `SHLWAPI!AssocGetPerceivedType` at `0x180017542`
- `SHLWAPI!PathFindExtensionW` at `0x180017402`
- `SHLWAPI!PathFindExtensionW` at `0x180017402`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017604`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001762e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800176de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017729`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800177ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001784a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017604`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001762e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800176de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017729`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800177ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001784a`
- `USER32!DestroyIcon` at `0x180017828`
- `USER32!DestroyIcon` at `0x180017891`
- `USER32!DestroyIcon` at `0x180017828`
- `USER32!DestroyIcon` at `0x180017891`
- `USER32!SendDlgItemMessageW` at `0x18001781a`
- `USER32!SendDlgItemMessageW` at `0x180017883`
- `USER32!SendDlgItemMessageW` at `0x18001781a`
- `USER32!SendDlgItemMessageW` at `0x180017883`
- `USER32!LoadIconW` at `0x1800177fe`
- `USER32!LoadIconW` at `0x1800177fe`
- `USER32!SetWindowTextW` at `0x1800177e0`
- `USER32!SetWindowTextW` at `0x1800177e0`
- `USER32!SetFocus` at `0x180017300`
- `USER32!SetFocus` at `0x180017300`
- `USER32!SetWindowPos` at `0x1800173bf`
- `USER32!SetWindowPos` at `0x1800173bf`
- `USER32!MapWindowPoints` at `0x180017380`
- `USER32!MapWindowPoints` at `0x180017380`
- `USER32!GetWindowRect` at `0x18001736b`
- `USER32!GetWindowRect` at `0x18001736b`
- `USER32!GetDlgItem` at `0x1800172f7`
- `USER32!GetDlgItem` at `0x18001731f`
- `USER32!GetDlgItem` at `0x180017338`
- `USER32!GetDlgItem` at `0x18001735b`
- `USER32!GetDlgItem` at `0x18001738e`
- `USER32!GetDlgItem` at `0x1800173d5`
- `USER32!GetDlgItem` at `0x1800173ee`
- `USER32!GetDlgItem` at `0x1800175c4`
- `USER32!GetDlgItem` at `0x1800175da`
- `USER32!GetDlgItem` at `0x180017743`
- `USER32!GetDlgItem` at `0x180017752`
- `USER32!GetDlgItem` at `0x18001789f`
- `USER32!GetDlgItem` at `0x1800172f7`
- `USER32!GetDlgItem` at `0x18001731f`
- `USER32!GetDlgItem` at `0x180017338`
- `USER32!GetDlgItem` at `0x18001735b`
- `USER32!GetDlgItem` at `0x18001738e`
- `USER32!GetDlgItem` at `0x1800173d5`
- `USER32!GetDlgItem` at `0x1800173ee`
- `USER32!GetDlgItem` at `0x1800175c4`
- `USER32!GetDlgItem` at `0x1800175da`
- `USER32!GetDlgItem` at `0x180017743`
- `USER32!GetDlgItem` at `0x180017752`
- `USER32!GetDlgItem` at `0x18001789f`
- `USER32!EnableWindow` at `0x18001732a`
- `USER32!EnableWindow` at `0x1800173e0`
- `USER32!EnableWindow` at `0x1800175cf`
- `USER32!EnableWindow` at `0x18001732a`
- `USER32!EnableWindow` at `0x1800173e0`
- `USER32!EnableWindow` at `0x1800175cf`
- `USER32!ShowWindow` at `0x180017343`
- `USER32!ShowWindow` at `0x1800173f9`
- `USER32!ShowWindow` at `0x1800175e5`
- `USER32!ShowWindow` at `0x180017343`
- `USER32!ShowWindow` at `0x1800173f9`
- `USER32!ShowWindow` at `0x1800175e5`
- `USER32!SetDlgItemTextW` at `0x180017649`
- `USER32!SetDlgItemTextW` at `0x1800176fd`
- `USER32!SetDlgItemTextW` at `0x180017779`
- `USER32!SetDlgItemTextW` at `0x180017860`
- `USER32!SetDlgItemTextW` at `0x180017649`
- `USER32!SetDlgItemTextW` at `0x1800176fd`
- `USER32!SetDlgItemTextW` at `0x180017779`
- `USER32!SetDlgItemTextW` at `0x180017860`

## pseudocode

```c
__int64 __fastcall InitUI(
        const WCHAR *a1,
        const WCHAR *a2,
        HWND a3,
        unsigned int a4,
        UINT cPoints,
        LPCWSTR lpString,
        unsigned int a7,
        int a8,
        int a9,
        unsigned int a10,
        char a11,
        _QWORD *a12,
        HICON *phiconLarge,
        __int64 *a14)
{
  HWND DlgItem; // rax
  HWND v18; // rax
  HWND v19; // rax
  HWND v20; // rax
  HWND v21; // rax
  HWND v22; // rax
  HWND v23; // rax
  LPWSTR ExtensionW; // rbx
  HRESULT v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // r12d
  HWND v29; // rax
  HWND v30; // rax
  int v31; // edx
  UINT v32; // r15d
  HWND v33; // rbx
  HWND v34; // rax
  unsigned __int16 *v35; // rdx
  HICON IconW; // rax
  HICON v37; // rax
  HICON v38; // rax
  HWND v39; // rax
  __int64 v40; // rax
  int pszOut; // [rsp+20h] [rbp-E0h]
  UINT uID; // [rsp+60h] [rbp-A0h] BYREF
  UINT v44; // [rsp+64h] [rbp-9Ch] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  PERCEIVED ptype; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v47; // [rsp+70h] [rbp-90h]
  UINT v48; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD pcchOut; // [rsp+78h] [rbp-88h] BYREF
  PERCEIVEDFLAG pflag; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 *v51; // [rsp+80h] [rbp-80h]
  SHFILEINFOW psfi; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+350h] [rbp+250h] BYREF
  WCHAR Buffer; // [rsp+360h] [rbp+260h] BYREF
  char v55[510]; // [rsp+362h] [rbp+262h] BYREF
  unsigned __int16 v56[96]; // [rsp+560h] [rbp+460h] BYREF
  WCHAR pszIconFile[264]; // [rsp+620h] [rbp+520h] BYREF

  v51 = a14;
  v47 = a4;
  uID = 0;
  v44 = 0;
  v48 = 0;
  v45 = 0;
  Buffer = 0;
  memset_0(v55, 0, sizeof(v55));
  DlgItem = GetDlgItem(a3, 2);
  SetFocus(DlgItem);
  if ( cPoints == 2 )
  {
    v18 = GetDlgItem(a3, 4427);
    EnableWindow(v18, 0);
    v19 = GetDlgItem(a3, 4427);
    ShowWindow(v19, 0);
    Rect = 0;
    v20 = GetDlgItem(a3, 4427);
    GetWindowRect(v20, &Rect);
    MapWindowPoints(0, a3, (LPPOINT)&Rect, 2u);
    v21 = GetDlgItem(a3, 4426);
    SetWindowPos(v21, 0, Rect.left, Rect.top, 0, 0, 5u);
  }
  else if ( cPoints == 1 )
  {
    v22 = GetDlgItem(a3, 4426);
    EnableWindow(v22, 0);
    v23 = GetDlgItem(a3, 4426);
    ShowWindow(v23, 0);
  }
  pcchOut = 260;
  ExtensionW = PathFindExtensionW(a1);
  v25 = AssocQueryStringW(0, ASSOCSTR_DEFAULTICON, a2, 0, pszIconFile, &pcchOut);
  v26 = 0;
  if ( v25 >= 0 )
  {
    v27 = PathParseIconLocationW(pszIconFile);
    ExtractIconExW(pszIconFile, v27, phiconLarge, 0, 1u);
    if ( *phiconLarge )
      goto LABEL_15;
    if ( !a8 )
    {
      memset_0(&psfi, 0, sizeof(psfi));
      if ( ExtensionW )
      {
        if ( *ExtensionW && SHGetFileInfoW(ExtensionW, 0x80u, &psfi, 0x2B8u, 0x110u) )
          *phiconLarge = psfi.hIcon;
      }
    }
  }
  if ( !*phiconLarge )
  {
    memset_0(&psfi, 0, sizeof(psfi));
    if ( SHGetFileInfoW(L"filename", 0x80u, &psfi, 0x2B8u, 0x110u) )
      *phiconLarge = psfi.hIcon;
  }
LABEL_15:
  ptype = PERCEIVED_TYPE_UNKNOWN;
  *a12 = L"mshelp://windows/?id=6b046ae9-1434-4423-9303-400ff6fe686b";
  if ( ExtensionW )
  {
    if ( *ExtensionW )
    {
      pflag = 0;
      if ( AssocGetPerceivedType(ExtensionW, &ptype, &pflag, 0) >= 0 && ptype == PERCEIVED_TYPE_APPLICATION )
      {
        v28 = v47;
        LoadDialogExecHeaderFooterIcon(v47, cPoints, a7);
        if ( a9 == 7 )
        {
          v29 = GetDlgItem(a3, 4426);
          EnableWindow(v29, 0);
          v30 = GetDlgItem(a3, 4426);
          ShowWindow(v30, 0);
          if ( !LoadStringW(g_hinst, 0x8506u, &Buffer, 256) )
            goto LABEL_25;
          v31 = 2;
        }
        else
        {
          if ( !LoadStringW(g_hinst, 0x8505u, &Buffer, 256) )
            goto LABEL_25;
          v31 = 4426;
        }
        v26 = SetDlgItemTextW(a3, v31, &Buffer);
LABEL_25:
        v32 = 34098;
        if ( !v26 )
          goto LABEL_46;
        goto LABEL_28;
      }
    }
  }
  v26 = 1;
  v28 = v47;
  LOBYTE(pszOut) = a11;
  LoadDialogOpenHeaderFooterIcon(v47, cPoints, a7, a10, pszOut, &v48, &uID, &v44, &v45, a12);
  v32 = v48;
LABEL_28:
  if ( !uID || (v26 = LoadStringW(g_hinst, uID, &Buffer, 256)) != 0 && (v26 = SetDlgItemTextW(a3, 4417, &Buffer)) != 0 )
  {
    if ( !v44
      || (v26 = LoadStringW(g_hinst, v44, &Buffer, 256)) != 0
      && (v33 = GetDlgItem(a3, 4431),
          v34 = GetDlgItem(a3, 4430),
          FormatFooterSection(a3, v34, v33, &Buffer),
          (v26 = SetDlgItemTextW(a3, 4431, &Buffer)) != 0) )
    {
      if ( !lpString
        || (!v32 || !LoadStringW(g_hinst, v32, &Buffer, 256)
          ? (v35 = (unsigned __int16 *)lpString)
          : (StringCchPrintfW(v56, 0x60u, &Buffer, lpString), v35 = v56),
            (v26 = SetWindowTextW(a3, v35)) != 0) )
      {
        if ( v45 )
        {
          IconW = LoadIconW(g_hinst, (LPCWSTR)(unsigned __int16)v45);
          v37 = (HICON)SendDlgItemMessageW(a3, 4430, 0x170u, (WPARAM)IconW, 0);
          if ( v37 )
            DestroyIcon(v37);
        }
        if ( v28 == 1 && LoadStringW(g_hinst, 0x8533u, (LPWSTR)&psfi, 260) )
          v26 = SetDlgItemTextW(a3, 4428, (LPCWSTR)&psfi);
      }
    }
  }
LABEL_46:
  if ( *phiconLarge )
  {
    v38 = (HICON)SendDlgItemMessageW(a3, 4418, 0x170u, (WPARAM)*phiconLarge, 0);
    if ( v38 )
      DestroyIcon(v38);
  }
  v39 = GetDlgItem(a3, 4417);
  v40 = SetBoldFontOnControl(v39);
  *v51 = v40;
  SHCenterWindow(a3);
  return v26;
}

```

## disassembly

```asm
0x180017264  mov     [rsp-8+arg_18], rbx
0x180017269  push    rbp
0x18001726a  push    rsi
0x18001726b  push    rdi
0x18001726c  push    r12
0x18001726e  push    r13
0x180017270  push    r14
0x180017272  push    r15
0x180017274  lea     rbp, [rsp-740h]
0x18001727c  sub     rsp, 840h
0x180017283  mov     rax, cs:__security_cookie
0x18001728a  xor     rax, rsp
0x18001728d  mov     [rbp+770h+var_40], rax
0x180017294  mov     rax, [rbp+770h+arg_68]
0x18001729b  mov     rsi, r8
0x18001729e  mov     r13, [rbp+770h+lpString]
0x1800172a5  mov     rdi, rdx
0x1800172a8  mov     r12, [rbp+770h+arg_58]
0x1800172af  mov     rbx, rcx
0x1800172b2  mov     r14, [rbp+770h+phiconLarge]
0x1800172b9  lea     rcx, [rbp+770h+var_50E]; void *
0x1800172c0  mov     [rbp+770h+var_7F0], rax
0x1800172c4  xor     edx, edx; Val
0x1800172c6  xor     eax, eax
0x1800172c8  mov     [rsp+870h+var_800], r9d
0x1800172cd  mov     r8d, 1FEh; Size
0x1800172d3  mov     [rsp+870h+uID], eax
0x1800172d7  mov     [rsp+870h+var_80C], eax
0x1800172db  mov     [rsp+870h+var_7FC], eax
0x1800172df  mov     [rsp+870h+var_808], eax
0x1800172e3  mov     [rbp+770h+Buffer], ax
0x1800172ea  call    memset_0
0x1800172ef  mov     edx, 2; nIDDlgItem
0x1800172f4  mov     rcx, rsi; hDlg
0x1800172f7  call    cs:__imp_GetDlgItem
0x1800172fd  mov     rcx, rax; hWnd
0x180017300  call    cs:__imp_SetFocus
0x180017306  mov     r15d, [rbp+770h+cPoints]
0x18001730d  cmp     r15d, 2
0x180017311  jnz     loc_1800173C7
0x180017317  mov     edx, 114Bh; nIDDlgItem
0x18001731c  mov     rcx, rsi; hDlg
0x18001731f  call    cs:__imp_GetDlgItem
0x180017325  mov     rcx, rax; hWnd
0x180017328  xor     edx, edx; bEnable
0x18001732a  call    cs:__imp_EnableWindow
0x180017330  mov     edx, 114Bh; nIDDlgItem
0x180017335  mov     rcx, rsi; hDlg
0x180017338  call    cs:__imp_GetDlgItem
0x18001733e  mov     rcx, rax; hWnd
0x180017341  xor     edx, edx; nCmdShow
0x180017343  call    cs:__imp_ShowWindow
0x180017349  xorps   xmm0, xmm0
0x18001734c  mov     edx, 114Bh; nIDDlgItem
0x180017351  mov     rcx, rsi; hDlg
0x180017354  movups  xmmword ptr [rbp+770h+Rect.left], xmm0
0x18001735b  call    cs:__imp_GetDlgItem
0x180017361  mov     rcx, rax; hWnd
0x180017364  lea     rdx, [rbp+770h+Rect]; lpRect
0x18001736b  call    cs:__imp_GetWindowRect
0x180017371  mov     r9d, r15d; cPoints
0x180017374  lea     r8, [rbp+770h+Rect]; lpPoints
0x18001737b  mov     rdx, rsi; hWndTo
0x18001737e  xor     ecx, ecx; hWndFrom
0x180017380  call    cs:__imp_MapWindowPoints
0x180017386  mov     edx, 114Ah; nIDDlgItem
0x18001738b  mov     rcx, rsi; hDlg
0x18001738e  call    cs:__imp_GetDlgItem
0x180017394  mov     r9d, [rbp+770h+Rect.top]; Y
0x18001739b  xor     edx, edx; hWndInsertAfter
0x18001739d  mov     r8d, [rbp+770h+Rect.left]; X
0x1800173a4  mov     rcx, rax; hWnd
0x1800173a7  mov     [rsp+870h+uFlags], 5; uFlags
0x1800173af  mov     [rsp+870h+cy], 0; cy
0x1800173b7  mov     dword ptr [rsp+870h+pszOut], 0; cx
0x1800173bf  call    cs:__imp_SetWindowPos
0x1800173c5  jmp     short loc_1800173FF
0x1800173c7  cmp     r15d, 1
0x1800173cb  jnz     short loc_1800173FF
0x1800173cd  mov     edx, 114Ah; nIDDlgItem
0x1800173d2  mov     rcx, rsi; hDlg
0x1800173d5  call    cs:__imp_GetDlgItem
0x1800173db  mov     rcx, rax; hWnd
0x1800173de  xor     edx, edx; bEnable
0x1800173e0  call    cs:__imp_EnableWindow
0x1800173e6  mov     edx, 114Ah; nIDDlgItem
0x1800173eb  mov     rcx, rsi; hDlg
0x1800173ee  call    cs:__imp_GetDlgItem
0x1800173f4  mov     rcx, rax; hWnd
0x1800173f7  xor     edx, edx; nCmdShow
0x1800173f9  call    cs:__imp_ShowWindow
0x1800173ff  mov     rcx, rbx; pszPath
0x180017402  call    cs:__imp_PathFindExtensionW
0x180017408  xor     r9d, r9d; pszExtra
0x18001740b  mov     [rsp+870h+pcchOut], 104h
0x180017413  mov     rbx, rax
0x180017416  mov     r8, rdi; pszAssoc
0x180017419  lea     rax, [rsp+870h+pcchOut]
0x18001741e  xor     ecx, ecx; flags
0x180017420  mov     qword ptr [rsp+870h+cy], rax; pcchOut
0x180017425  lea     rax, [rbp+770h+pszIconFile]
0x18001742c  lea     edx, [r9+0Fh]; str
0x180017430  mov     [rsp+870h+pszOut], rax; pszOut
0x180017435  call    cs:__imp_AssocQueryStringW
0x18001743b  xor     edi, edi
0x18001743d  test    eax, eax
0x18001743f  js      loc_1800174C7
0x180017445  lea     rcx, [rbp+770h+pszIconFile]; pszIconFile
0x18001744c  call    cs:__imp_PathParseIconLocationW
0x180017452  xor     r9d, r9d; phiconSmall
0x180017455  mov     dword ptr [rsp+870h+pszOut], 1; nIcons
0x18001745d  mov     edx, eax; nIconIndex
0x18001745f  lea     rcx, [rbp+770h+pszIconFile]; lpszFile
0x180017466  mov     r8, r14; phiconLarge
0x180017469  call    cs:__imp_ExtractIconExW
0x18001746f  cmp     [r14], rdi
0x180017472  jnz     loc_18001750D
0x180017478  cmp     [rbp+770h+arg_38], edi
0x18001747e  jnz     short loc_1800174C7
0x180017480  xor     edx, edx; Val
0x180017482  lea     rcx, [rbp+770h+psfi]; void *
0x180017486  mov     r8d, 2B8h; Size
0x18001748c  call    memset_0
0x180017491  test    rbx, rbx
0x180017494  jz      short loc_1800174C7
0x180017496  cmp     [rbx], di
0x180017499  jz      short loc_1800174C7
0x18001749b  mov     r9d, 2B8h; cbFileInfo
0x1800174a1  mov     dword ptr [rsp+870h+pszOut], 110h; uFlags
0x1800174a9  lea     r8, [rbp+770h+psfi]; psfi
0x1800174ad  mov     edx, 80h; dwFileAttributes
0x1800174b2  mov     rcx, rbx; pszPath
0x1800174b5  call    cs:__imp_SHGetFileInfoW
0x1800174bb  test    rax, rax
0x1800174be  jz      short loc_1800174C7
0x1800174c0  mov     rax, [rbp+770h+psfi.hIcon]
0x1800174c4  mov     [r14], rax
0x1800174c7  cmp     [r14], rdi
0x1800174ca  jnz     short loc_18001750D
0x1800174cc  xor     edx, edx; Val
0x1800174ce  lea     rcx, [rbp+770h+psfi]; void *
0x1800174d2  mov     r8d, 2B8h; Size
0x1800174d8  call    memset_0
0x1800174dd  mov     r9d, 2B8h; cbFileInfo
0x1800174e3  mov     dword ptr [rsp+870h+pszOut], 110h; uFlags
0x1800174eb  lea     r8, [rbp+770h+psfi]; psfi
0x1800174ef  mov     edx, 80h; dwFileAttributes
0x1800174f4  lea     rcx, pszPath; "filename"
0x1800174fb  call    cs:__imp_SHGetFileInfoW
0x180017501  test    rax, rax
0x180017504  jz      short loc_18001750D
0x180017506  mov     rax, [rbp+770h+psfi.hIcon]
0x18001750a  mov     [r14], rax
0x18001750d  mov     [rsp+870h+ptype], edi
0x180017511  lea     rax, aMshelpWindowsI_0; "mshelp://windows/?id=6b046ae9-1434-4423"...
0x180017518  mov     [r12], rax
0x18001751c  test    rbx, rbx
0x18001751f  jz      loc_180017661
0x180017525  cmp     [rbx], di
0x180017528  jz      loc_180017661
0x18001752e  xor     r9d, r9d; ppszType
0x180017531  mov     [rsp+870h+pflag], edi
0x180017535  lea     r8, [rsp+870h+pflag]; pflag
0x18001753a  mov     rcx, rbx; pszExt
0x18001753d  lea     rdx, [rsp+870h+ptype]; ptype
0x180017542  call    cs:__imp_AssocGetPerceivedType
0x180017548  xor     ebx, ebx
0x18001754a  test    eax, eax
0x18001754c  js      loc_180017663
0x180017552  cmp     [rsp+870h+ptype], 8
0x180017557  jnz     loc_180017663
0x18001755d  mov     ebx, [rbp+770h+arg_40]
0x180017563  lea     rax, [rsp+870h+var_808]
0x180017568  mov     r8d, [rbp+770h+arg_30]
0x18001756f  mov     edx, r15d
0x180017572  mov     [rsp+870h+var_820], r12
0x180017577  mov     r12d, [rsp+870h+var_800]
0x18001757c  mov     ecx, r12d
0x18001757f  mov     [rsp+870h+var_828], rax
0x180017584  lea     rax, [rsp+870h+var_80C]
0x180017589  mov     [rsp+870h+var_830], rax
0x18001758e  lea     rax, [rsp+870h+uID]
0x180017593  mov     [rsp+870h+var_838], rax
0x180017598  mov     al, [rbp+770h+arg_50]
0x18001759e  mov     byte ptr [rsp+870h+uFlags], al
0x1800175a2  mov     eax, [rbp+770h+arg_48]
0x1800175a8  mov     [rsp+870h+cy], eax
0x1800175ac  mov     dword ptr [rsp+870h+pszOut], ebx
0x1800175b0  call    ?LoadDialogExecHeaderFooterIcon@@YAXW4SOCLIENT@@W4ATTACHMENT_PROMPT@@HPEBGW4SIGNATURE_STATE@@H_NPEAI55PEAPEBG@Z; LoadDialogExecHeaderFooterIcon(SOCLIENT,ATTACHMENT_PROMPT,int,ushort const *,SIGNATURE_STATE,int,bool,uint *,uint *,uint *,ushort const * *)
0x1800175b5  cmp     ebx, 7
0x1800175b8  jnz     short loc_180017615
0x1800175ba  mov     ebx, 114Ah
0x1800175bf  mov     rcx, rsi; hDlg
0x1800175c2  mov     edx, ebx; nIDDlgItem
0x1800175c4  call    cs:__imp_GetDlgItem
0x1800175ca  mov     rcx, rax; hWnd
0x1800175cd  xor     edx, edx; bEnable
0x1800175cf  call    cs:__imp_EnableWindow
0x1800175d5  mov     edx, ebx; nIDDlgItem
0x1800175d7  mov     rcx, rsi; hDlg
0x1800175da  call    cs:__imp_GetDlgItem
0x1800175e0  mov     rcx, rax; hWnd
0x1800175e3  xor     edx, edx; nCmdShow
0x1800175e5  call    cs:__imp_ShowWindow
0x1800175eb  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800175f2  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x1800175f9  mov     r9d, 100h; cchBufferMax
0x1800175ff  mov     edx, 8506h; uID
0x180017604  call    cs:__imp_LoadStringW
0x18001760a  xor     ebx, ebx
0x18001760c  test    eax, eax
0x18001760e  jz      short loc_180017651
0x180017610  lea     edx, [rbx+2]
0x180017613  jmp     short loc_18001763F
0x180017615  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001761c  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x180017623  mov     r9d, 100h; cchBufferMax
0x180017629  mov     edx, 8505h; uID
0x18001762e  call    cs:__imp_LoadStringW
0x180017634  xor     ebx, ebx
0x180017636  test    eax, eax
0x180017638  jz      short loc_180017651
0x18001763a  mov     edx, 114Ah; nIDDlgItem
0x18001763f  lea     r8, [rbp+770h+Buffer]; lpString
0x180017646  mov     rcx, rsi; hDlg
0x180017649  call    cs:__imp_SetDlgItemTextW
0x18001764f  mov     edi, eax
0x180017651  mov     r15d, 8532h
0x180017657  test    edi, edi
0x180017659  jz      loc_180017868
0x18001765f  jmp     short loc_1800176C2
0x180017661  xor     ebx, ebx
0x180017663  mov     r9d, [rbp+770h+arg_48]
0x18001766a  lea     rax, [rsp+870h+var_808]
0x18001766f  mov     r8d, [rbp+770h+arg_30]
0x180017676  mov     edx, r15d
0x180017679  mov     [rsp+870h+var_828], r12
0x18001767e  mov     edi, 1
0x180017683  mov     r12d, [rsp+870h+var_800]
0x180017688  mov     ecx, r12d
0x18001768b  mov     [rsp+870h+var_830], rax
0x180017690  lea     rax, [rsp+870h+var_80C]
0x180017695  mov     [rsp+870h+var_838], rax
0x18001769a  lea     rax, [rsp+870h+uID]
0x18001769f  mov     qword ptr [rsp+870h+uFlags], rax
0x1800176a4  lea     rax, [rsp+870h+var_7FC]
0x1800176a9  mov     qword ptr [rsp+870h+cy], rax
0x1800176ae  mov     al, [rbp+770h+arg_50]
0x1800176b4  mov     byte ptr [rsp+870h+pszOut], al
0x1800176b8  call    ?LoadDialogOpenHeaderFooterIcon@@YAXW4SOCLIENT@@W4ATTACHMENT_PROMPT@@HH_NPEAI333PEAPEBG@Z; LoadDialogOpenHeaderFooterIcon(SOCLIENT,ATTACHMENT_PROMPT,int,int,bool,uint *,uint *,uint *,uint *,ushort const * *)
0x1800176bd  mov     r15d, [rsp+870h+var_7FC]
0x1800176c2  mov     edx, [rsp+870h+uID]; uID
0x1800176c6  test    edx, edx
0x1800176c8  jz      short loc_18001770D
0x1800176ca  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800176d1  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x1800176d8  mov     r9d, 100h; cchBufferMax
0x1800176de  call    cs:__imp_LoadStringW
0x1800176e4  mov     edi, eax
0x1800176e6  test    eax, eax
0x1800176e8  jz      loc_180017868
0x1800176ee  lea     r8, [rbp+770h+Buffer]; lpString
0x1800176f5  mov     edx, 1141h; nIDDlgItem
0x1800176fa  mov     rcx, rsi; hDlg
0x1800176fd  call    cs:__imp_SetDlgItemTextW
0x180017703  mov     edi, eax
0x180017705  test    eax, eax
0x180017707  jz      loc_180017868
0x18001770d  mov     edx, [rsp+870h+var_80C]; uID
0x180017711  test    edx, edx
0x180017713  jz      short loc_18001778B
0x180017715  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001771c  lea     r8, [rbp+770h+Buffer]; lpBuffer
0x180017723  mov     r9d, 100h; cchBufferMax
0x180017729  call    cs:__imp_LoadStringW
0x18001772f  mov     edi, eax
0x180017731  test    eax, eax
0x180017733  jz      loc_180017868
0x180017739  mov     edi, 114Fh
0x18001773e  mov     rcx, rsi; hDlg
0x180017741  mov     edx, edi; nIDDlgItem
0x180017743  call    cs:__imp_GetDlgItem
0x180017749  lea     edx, [rdi-1]; nIDDlgItem
0x18001774c  mov     rcx, rsi; hDlg
0x18001774f  mov     rbx, rax
0x180017752  call    cs:__imp_GetDlgItem
0x180017758  lea     r9, [rbp+770h+Buffer]; pszStr1
0x18001775f  mov     r8, rbx; HWND
0x180017762  mov     rdx, rax; HWND
0x180017765  mov     rcx, rsi; hWnd
0x180017768  call    ?FormatFooterSection@@YAXPEAUHWND__@@00PEBG@Z; FormatFooterSection(HWND__ *,HWND__ *,HWND__ *,ushort const *)
0x18001776d  lea     r8, [rbp+770h+Buffer]; lpString
0x180017774  mov     edx, edi; nIDDlgItem
0x180017776  mov     rcx, rsi; hDlg
0x180017779  call    cs:__imp_SetDlgItemTextW
0x18001777f  xor     ebx, ebx
0x180017781  mov     edi, eax
0x180017783  test    eax, eax
0x180017785  jz      loc_180017868
0x18001778b  test    r13, r13
  ... truncated ...
```
