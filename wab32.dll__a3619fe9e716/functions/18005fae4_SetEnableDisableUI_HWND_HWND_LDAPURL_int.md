# SetEnableDisableUI(HWND__ *,HWND__ *,_LDAPURL *,int)

- ea: `0x18005fae4`
- end: `0x18005ff68`
- name: `?SetEnableDisableUI@@YAXPEAUHWND__@@0PEAU_LDAPURL@@H@Z`
- size: `1156`
- prototype: `void __fastcall(HWND hDlg, HWND, struct _LDAPURL *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005e0cc`
- `0x180060430`
- `0x180060850`

## callees

- `0x1800270d4`
- `0x1800277e4`
- `0x18005d2a8`
- `0x18005e6d8`
- `0x18005fae4`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005ff0b`
- `KERNEL32!LocalFree` at `0x18005ff0b`
- `KERNEL32!GetFileAttributesW` at `0x18005fdf2`
- `KERNEL32!GetFileAttributesW` at `0x18005fdf2`
- `KERNEL32!CompareStringW` at `0x18005fe86`
- `KERNEL32!CompareStringW` at `0x18005fe86`
- `USER32!EnableWindow` at `0x18005fc5f`
- `USER32!EnableWindow` at `0x18005fc78`
- `USER32!EnableWindow` at `0x18005fc91`
- `USER32!EnableWindow` at `0x18005fcaa`
- `USER32!EnableWindow` at `0x18005fcc3`
- `USER32!EnableWindow` at `0x18005fcdc`
- `USER32!EnableWindow` at `0x18005feb7`
- `USER32!EnableWindow` at `0x18005ff26`
- `USER32!EnableWindow` at `0x18005fc5f`
- `USER32!EnableWindow` at `0x18005fc78`
- `USER32!EnableWindow` at `0x18005fc91`
- `USER32!EnableWindow` at `0x18005fcaa`
- `USER32!EnableWindow` at `0x18005fcc3`
- `USER32!EnableWindow` at `0x18005fcdc`
- `USER32!EnableWindow` at `0x18005feb7`
- `USER32!EnableWindow` at `0x18005ff26`
- `USER32!GetDlgItem` at `0x18005fb50`
- `USER32!GetDlgItem` at `0x18005fb6a`
- `USER32!GetDlgItem` at `0x18005fb84`
- `USER32!GetDlgItem` at `0x18005fb9e`
- `USER32!GetDlgItem` at `0x18005fbb8`
- `USER32!GetDlgItem` at `0x18005fbd2`
- `USER32!GetDlgItem` at `0x18005fbec`
- `USER32!GetDlgItem` at `0x18005fc06`
- `USER32!GetDlgItem` at `0x18005fc20`
- `USER32!GetDlgItem` at `0x18005fc3a`
- `USER32!GetDlgItem` at `0x18005fc54`
- `USER32!GetDlgItem` at `0x18005fc6d`
- `USER32!GetDlgItem` at `0x18005fc86`
- `USER32!GetDlgItem` at `0x18005fc9f`
- `USER32!GetDlgItem` at `0x18005fcb8`
- `USER32!GetDlgItem` at `0x18005fcd1`
- `USER32!GetDlgItem` at `0x18005fcea`
- `USER32!GetDlgItem` at `0x18005fd03`
- `USER32!GetDlgItem` at `0x18005fd1c`
- `USER32!GetDlgItem` at `0x18005fd35`
- `USER32!GetDlgItem` at `0x18005fd4e`
- `USER32!GetDlgItem` at `0x18005fd67`
- `USER32!GetDlgItem` at `0x18005fd80`
- `USER32!GetDlgItem` at `0x18005fe97`
- `USER32!GetDlgItem` at `0x18005feac`
- `USER32!GetDlgItem` at `0x18005ff1b`
- `USER32!GetDlgItem` at `0x18005ff3c`
- `USER32!GetDlgItem` at `0x18005fb50`
- `USER32!GetDlgItem` at `0x18005fb6a`
- `USER32!GetDlgItem` at `0x18005fb84`
- `USER32!GetDlgItem` at `0x18005fb9e`
- `USER32!GetDlgItem` at `0x18005fbb8`
- `USER32!GetDlgItem` at `0x18005fbd2`
- `USER32!GetDlgItem` at `0x18005fbec`
- `USER32!GetDlgItem` at `0x18005fc06`
- `USER32!GetDlgItem` at `0x18005fc20`
- `USER32!GetDlgItem` at `0x18005fc3a`
- `USER32!GetDlgItem` at `0x18005fc54`
- `USER32!GetDlgItem` at `0x18005fc6d`
- `USER32!GetDlgItem` at `0x18005fc86`
- `USER32!GetDlgItem` at `0x18005fc9f`
- `USER32!GetDlgItem` at `0x18005fcb8`
- `USER32!GetDlgItem` at `0x18005fcd1`
- `USER32!GetDlgItem` at `0x18005fcea`
- `USER32!GetDlgItem` at `0x18005fd03`
- `USER32!GetDlgItem` at `0x18005fd1c`
- `USER32!GetDlgItem` at `0x18005fd35`
- `USER32!GetDlgItem` at `0x18005fd4e`
- `USER32!GetDlgItem` at `0x18005fd67`
- `USER32!GetDlgItem` at `0x18005fd80`
- `USER32!GetDlgItem` at `0x18005fe97`
- `USER32!GetDlgItem` at `0x18005feac`
- `USER32!GetDlgItem` at `0x18005ff1b`
- `USER32!GetDlgItem` at `0x18005ff3c`
- `USER32!SendDlgItemMessageW` at `0x18005fe42`
- `USER32!SendDlgItemMessageW` at `0x18005fe42`
- `USER32!ShowWindow` at `0x18005fb5c`
- `USER32!ShowWindow` at `0x18005fb76`
- `USER32!ShowWindow` at `0x18005fb90`
- `USER32!ShowWindow` at `0x18005fbaa`
- `USER32!ShowWindow` at `0x18005fbc4`
- `USER32!ShowWindow` at `0x18005fbde`
- `USER32!ShowWindow` at `0x18005fbf8`
- `USER32!ShowWindow` at `0x18005fc12`
- `USER32!ShowWindow` at `0x18005fc2c`
- `USER32!ShowWindow` at `0x18005fc46`
- `USER32!ShowWindow` at `0x18005fcf5`
- `USER32!ShowWindow` at `0x18005fd0e`
- `USER32!ShowWindow` at `0x18005fd27`
- `USER32!ShowWindow` at `0x18005fd40`
- `USER32!ShowWindow` at `0x18005fd59`
- `USER32!ShowWindow` at `0x18005fd72`
- `USER32!ShowWindow` at `0x18005fd8b`
- `USER32!ShowWindow` at `0x18005fb5c`
- `USER32!ShowWindow` at `0x18005fb76`
- `USER32!ShowWindow` at `0x18005fb90`
- `USER32!ShowWindow` at `0x18005fbaa`
- `USER32!ShowWindow` at `0x18005fbc4`
- `USER32!ShowWindow` at `0x18005fbde`
- `USER32!ShowWindow` at `0x18005fbf8`
- `USER32!ShowWindow` at `0x18005fc12`
- `USER32!ShowWindow` at `0x18005fc2c`
- `USER32!ShowWindow` at `0x18005fc46`
- `USER32!ShowWindow` at `0x18005fcf5`
- `USER32!ShowWindow` at `0x18005fd0e`
- `USER32!ShowWindow` at `0x18005fd27`
- `USER32!ShowWindow` at `0x18005fd40`
- `USER32!ShowWindow` at `0x18005fd59`
- `USER32!ShowWindow` at `0x18005fd72`
- `USER32!ShowWindow` at `0x18005fd8b`
- `USER32!ShowWindow` at `0x18005ff61`
- `USER32!LoadImageW` at `0x18005fe22`
- `USER32!LoadImageW` at `0x18005fe22`

## pseudocode

```c
void __fastcall SetEnableDisableUI(HWND hDlg, HWND a2, struct _LDAPURL *a3, int a4)
{
  int v4; // ebx
  BOOL v8; // esi
  int v9; // r15d
  int v10; // r13d
  HWND DlgItem; // rax
  HWND v12; // rax
  HWND v13; // rax
  HWND v14; // rax
  HWND v15; // rax
  HWND v16; // rax
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  HWND v20; // rax
  HWND v21; // rax
  HWND v22; // rax
  HWND v23; // rax
  HWND v24; // rax
  HWND v25; // rax
  HWND v26; // rax
  HWND v27; // rax
  HWND v28; // rax
  HWND v29; // rax
  HWND v30; // rax
  HWND v31; // rax
  HWND v32; // rax
  HWND v33; // rax
  HLOCAL v34; // rsi
  unsigned __int64 v35; // rbx
  __int64 v36; // rax
  HANDLE ImageW; // rax
  HWND v38; // rax
  BOOL v39; // edx
  HWND v40; // rax
  HWND v41; // rax
  _OWORD v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h]
  __int128 v44; // [rsp+60h] [rbp-A0h]
  __int128 v45; // [rsp+70h] [rbp-90h]
  __int128 v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+90h] [rbp-70h]
  _OWORD v48[10]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+160h] [rbp+60h] BYREF
  int nCmdShow; // [rsp+168h] [rbp+68h]

  v4 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a3 )
    v8 = CurrentContainerIsPAB(a2) != 0;
  nCmdShow = a4 == 0;
  if ( a4 || (v10 = 1, !v8) )
    v10 = 0;
  LOBYTE(v4) = a4 == 1;
  DlgItem = GetDlgItem(hDlg, 1152);
  ShowWindow(DlgItem, nCmdShow);
  v12 = GetDlgItem(hDlg, 1151);
  ShowWindow(v12, nCmdShow);
  v13 = GetDlgItem(hDlg, 1154);
  ShowWindow(v13, nCmdShow);
  v14 = GetDlgItem(hDlg, 1153);
  ShowWindow(v14, nCmdShow);
  v15 = GetDlgItem(hDlg, 1157);
  ShowWindow(v15, v10);
  v16 = GetDlgItem(hDlg, 1156);
  ShowWindow(v16, v10);
  v17 = GetDlgItem(hDlg, 1159);
  ShowWindow(v17, v10);
  v18 = GetDlgItem(hDlg, 1158);
  ShowWindow(v18, v10);
  v19 = GetDlgItem(hDlg, 1167);
  ShowWindow(v19, v10);
  v20 = GetDlgItem(hDlg, 1166);
  ShowWindow(v20, v10);
  v21 = GetDlgItem(hDlg, 1157);
  EnableWindow(v21, v8);
  v22 = GetDlgItem(hDlg, 1156);
  EnableWindow(v22, v8);
  v23 = GetDlgItem(hDlg, 1159);
  EnableWindow(v23, v8);
  v24 = GetDlgItem(hDlg, 1158);
  EnableWindow(v24, v8);
  v25 = GetDlgItem(hDlg, 1167);
  EnableWindow(v25, v8);
  v26 = GetDlgItem(hDlg, 1166);
  EnableWindow(v26, v8);
  v27 = GetDlgItem(hDlg, 2789);
  ShowWindow(v27, v4);
  v28 = GetDlgItem(hDlg, 2790);
  ShowWindow(v28, v4);
  v29 = GetDlgItem(hDlg, 2791);
  ShowWindow(v29, v4);
  v30 = GetDlgItem(hDlg, 2792);
  ShowWindow(v30, v4);
  v31 = GetDlgItem(hDlg, 2793);
  ShowWindow(v31, v4);
  v32 = GetDlgItem(hDlg, 2794);
  ShowWindow(v32, v4);
  v33 = GetDlgItem(hDlg, 2795);
  ShowWindow(v33, v4);
  if ( v8 )
  {
    v40 = GetDlgItem(hDlg, 11);
    EnableWindow(v40, 0);
  }
  else
  {
    memset_0(v42, 0, 0x70u);
    hMem = 0;
    GetSelectedText(a2, (unsigned __int16 **)&hMem);
    v34 = hMem;
    GetLDAPServerParams((unsigned __int16 *)hMem, (struct _LDAPSERVERPARAMS *)v42);
    v35 = -1;
    if ( !a4 )
    {
      if ( lpFileName[1] )
      {
        v36 = -1;
        do
          ++v36;
        while ( lpFileName[1][v36] );
        if ( v36 )
        {
          if ( GetFileAttributesW(lpFileName[1]) != -1 )
          {
            ImageW = LoadImageW(hinstMapiX, lpFileName[1], 0, 134, 38, 0x1010u);
            if ( ImageW )
            {
              SendDlgItemMessageW(hDlg, 102, 0x172u, 0, (LPARAM)ImageW);
              v9 = 1;
            }
          }
        }
      }
    }
    if ( !lpFileName[0] )
      goto LABEL_21;
    do
      ++v35;
    while ( lpFileName[0][v35] );
    if ( v35 > 7 )
      LODWORD(v35) = 7;
    if ( CompareStringW(0x7Fu, 1u, L"http://", 7, lpFileName[0], v35) == 2 )
    {
      v38 = GetDlgItem(hDlg, 11);
      v39 = 1;
    }
    else
    {
LABEL_21:
      v38 = GetDlgItem(hDlg, 11);
      v39 = 0;
    }
    EnableWindow(v38, v39);
    v48[0] = v42[0];
    v48[2] = *(_OWORD *)lpFileName;
    v48[1] = v42[1];
    v48[4] = v45;
    v48[3] = v44;
    v48[6] = v47;
    v48[5] = v46;
    FreeLDAPServerParams(v48);
    if ( v34 )
      LocalFree(v34);
  }
  v41 = GetDlgItem(hDlg, 102);
  ShowWindow(v41, v9 != 0 ? 5 : 0);
}

```

## disassembly

```asm
0x18005fae4  mov     [rsp-8+arg_0], rbx
0x18005fae9  push    rbp
0x18005faea  push    rsi
0x18005faeb  push    rdi
0x18005faec  push    r12
0x18005faee  push    r13
0x18005faf0  push    r14
0x18005faf2  push    r15
0x18005faf4  lea     rbp, [rsp-10h]
0x18005faf9  sub     rsp, 110h
0x18005fb00  xor     ebx, ebx
0x18005fb02  mov     rdi, rcx
0x18005fb05  mov     r14d, r9d
0x18005fb08  mov     r12, rdx
0x18005fb0b  mov     esi, ebx
0x18005fb0d  mov     r15d, ebx
0x18005fb10  lea     ecx, [rbx+1]
0x18005fb13  test    r8, r8
0x18005fb16  jnz     short loc_18005FB28
0x18005fb18  mov     rcx, rdx; HWND
0x18005fb1b  call    ?CurrentContainerIsPAB@@YAHPEAUHWND__@@@Z; CurrentContainerIsPAB(HWND__ *)
0x18005fb20  test    eax, eax
0x18005fb22  lea     ecx, [rbx+1]
0x18005fb25  cmovnz  esi, ecx
0x18005fb28  test    r14d, r14d
0x18005fb2b  mov     eax, ebx
0x18005fb2d  setz    al
0x18005fb30  mov     [rbp+40h+nCmdShow], eax
0x18005fb33  test    r14d, r14d
0x18005fb36  jnz     short loc_18005FB3F
0x18005fb38  mov     r13d, ecx
0x18005fb3b  test    esi, esi
0x18005fb3d  jnz     short loc_18005FB42
0x18005fb3f  mov     r13d, ebx
0x18005fb42  cmp     r14d, ecx
0x18005fb45  mov     edx, 480h; nIDDlgItem
0x18005fb4a  mov     rcx, rdi; hDlg
0x18005fb4d  setz    bl
0x18005fb50  call    cs:__imp_GetDlgItem
0x18005fb56  mov     edx, [rbp+40h+nCmdShow]; nCmdShow
0x18005fb59  mov     rcx, rax; hWnd
0x18005fb5c  call    cs:__imp_ShowWindow
0x18005fb62  mov     edx, 47Fh; nIDDlgItem
0x18005fb67  mov     rcx, rdi; hDlg
0x18005fb6a  call    cs:__imp_GetDlgItem
0x18005fb70  mov     edx, [rbp+40h+nCmdShow]; nCmdShow
0x18005fb73  mov     rcx, rax; hWnd
0x18005fb76  call    cs:__imp_ShowWindow
0x18005fb7c  mov     edx, 482h; nIDDlgItem
0x18005fb81  mov     rcx, rdi; hDlg
0x18005fb84  call    cs:__imp_GetDlgItem
0x18005fb8a  mov     edx, [rbp+40h+nCmdShow]; nCmdShow
0x18005fb8d  mov     rcx, rax; hWnd
0x18005fb90  call    cs:__imp_ShowWindow
0x18005fb96  mov     edx, 481h; nIDDlgItem
0x18005fb9b  mov     rcx, rdi; hDlg
0x18005fb9e  call    cs:__imp_GetDlgItem
0x18005fba4  mov     edx, [rbp+40h+nCmdShow]; nCmdShow
0x18005fba7  mov     rcx, rax; hWnd
0x18005fbaa  call    cs:__imp_ShowWindow
0x18005fbb0  mov     edx, 485h; nIDDlgItem
0x18005fbb5  mov     rcx, rdi; hDlg
0x18005fbb8  call    cs:__imp_GetDlgItem
0x18005fbbe  mov     rcx, rax; hWnd
0x18005fbc1  mov     edx, r13d; nCmdShow
0x18005fbc4  call    cs:__imp_ShowWindow
0x18005fbca  mov     edx, 484h; nIDDlgItem
0x18005fbcf  mov     rcx, rdi; hDlg
0x18005fbd2  call    cs:__imp_GetDlgItem
0x18005fbd8  mov     rcx, rax; hWnd
0x18005fbdb  mov     edx, r13d; nCmdShow
0x18005fbde  call    cs:__imp_ShowWindow
0x18005fbe4  mov     edx, 487h; nIDDlgItem
0x18005fbe9  mov     rcx, rdi; hDlg
0x18005fbec  call    cs:__imp_GetDlgItem
0x18005fbf2  mov     rcx, rax; hWnd
0x18005fbf5  mov     edx, r13d; nCmdShow
0x18005fbf8  call    cs:__imp_ShowWindow
0x18005fbfe  mov     edx, 486h; nIDDlgItem
0x18005fc03  mov     rcx, rdi; hDlg
0x18005fc06  call    cs:__imp_GetDlgItem
0x18005fc0c  mov     rcx, rax; hWnd
0x18005fc0f  mov     edx, r13d; nCmdShow
0x18005fc12  call    cs:__imp_ShowWindow
0x18005fc18  mov     edx, 48Fh; nIDDlgItem
0x18005fc1d  mov     rcx, rdi; hDlg
0x18005fc20  call    cs:__imp_GetDlgItem
0x18005fc26  mov     rcx, rax; hWnd
0x18005fc29  mov     edx, r13d; nCmdShow
0x18005fc2c  call    cs:__imp_ShowWindow
0x18005fc32  mov     edx, 48Eh; nIDDlgItem
0x18005fc37  mov     rcx, rdi; hDlg
0x18005fc3a  call    cs:__imp_GetDlgItem
0x18005fc40  mov     rcx, rax; hWnd
0x18005fc43  mov     edx, r13d; nCmdShow
0x18005fc46  call    cs:__imp_ShowWindow
0x18005fc4c  mov     edx, 485h; nIDDlgItem
0x18005fc51  mov     rcx, rdi; hDlg
0x18005fc54  call    cs:__imp_GetDlgItem
0x18005fc5a  mov     rcx, rax; hWnd
0x18005fc5d  mov     edx, esi; bEnable
0x18005fc5f  call    cs:__imp_EnableWindow
0x18005fc65  mov     edx, 484h; nIDDlgItem
0x18005fc6a  mov     rcx, rdi; hDlg
0x18005fc6d  call    cs:__imp_GetDlgItem
0x18005fc73  mov     rcx, rax; hWnd
0x18005fc76  mov     edx, esi; bEnable
0x18005fc78  call    cs:__imp_EnableWindow
0x18005fc7e  mov     edx, 487h; nIDDlgItem
0x18005fc83  mov     rcx, rdi; hDlg
0x18005fc86  call    cs:__imp_GetDlgItem
0x18005fc8c  mov     rcx, rax; hWnd
0x18005fc8f  mov     edx, esi; bEnable
0x18005fc91  call    cs:__imp_EnableWindow
0x18005fc97  mov     edx, 486h; nIDDlgItem
0x18005fc9c  mov     rcx, rdi; hDlg
0x18005fc9f  call    cs:__imp_GetDlgItem
0x18005fca5  mov     rcx, rax; hWnd
0x18005fca8  mov     edx, esi; bEnable
0x18005fcaa  call    cs:__imp_EnableWindow
0x18005fcb0  mov     edx, 48Fh; nIDDlgItem
0x18005fcb5  mov     rcx, rdi; hDlg
0x18005fcb8  call    cs:__imp_GetDlgItem
0x18005fcbe  mov     rcx, rax; hWnd
0x18005fcc1  mov     edx, esi; bEnable
0x18005fcc3  call    cs:__imp_EnableWindow
0x18005fcc9  mov     edx, 48Eh; nIDDlgItem
0x18005fcce  mov     rcx, rdi; hDlg
0x18005fcd1  call    cs:__imp_GetDlgItem
0x18005fcd7  mov     rcx, rax; hWnd
0x18005fcda  mov     edx, esi; bEnable
0x18005fcdc  call    cs:__imp_EnableWindow
0x18005fce2  mov     edx, 0AE5h; nIDDlgItem
0x18005fce7  mov     rcx, rdi; hDlg
0x18005fcea  call    cs:__imp_GetDlgItem
0x18005fcf0  mov     rcx, rax; hWnd
0x18005fcf3  mov     edx, ebx; nCmdShow
0x18005fcf5  call    cs:__imp_ShowWindow
0x18005fcfb  mov     edx, 0AE6h; nIDDlgItem
0x18005fd00  mov     rcx, rdi; hDlg
0x18005fd03  call    cs:__imp_GetDlgItem
0x18005fd09  mov     rcx, rax; hWnd
0x18005fd0c  mov     edx, ebx; nCmdShow
0x18005fd0e  call    cs:__imp_ShowWindow
0x18005fd14  mov     edx, 0AE7h; nIDDlgItem
0x18005fd19  mov     rcx, rdi; hDlg
0x18005fd1c  call    cs:__imp_GetDlgItem
0x18005fd22  mov     rcx, rax; hWnd
0x18005fd25  mov     edx, ebx; nCmdShow
0x18005fd27  call    cs:__imp_ShowWindow
0x18005fd2d  mov     edx, 0AE8h; nIDDlgItem
0x18005fd32  mov     rcx, rdi; hDlg
0x18005fd35  call    cs:__imp_GetDlgItem
0x18005fd3b  mov     rcx, rax; hWnd
0x18005fd3e  mov     edx, ebx; nCmdShow
0x18005fd40  call    cs:__imp_ShowWindow
0x18005fd46  mov     edx, 0AE9h; nIDDlgItem
0x18005fd4b  mov     rcx, rdi; hDlg
0x18005fd4e  call    cs:__imp_GetDlgItem
0x18005fd54  mov     rcx, rax; hWnd
0x18005fd57  mov     edx, ebx; nCmdShow
0x18005fd59  call    cs:__imp_ShowWindow
0x18005fd5f  mov     edx, 0AEAh; nIDDlgItem
0x18005fd64  mov     rcx, rdi; hDlg
0x18005fd67  call    cs:__imp_GetDlgItem
0x18005fd6d  mov     rcx, rax; hWnd
0x18005fd70  mov     edx, ebx; nCmdShow
0x18005fd72  call    cs:__imp_ShowWindow
0x18005fd78  mov     edx, 0AEBh; nIDDlgItem
0x18005fd7d  mov     rcx, rdi; hDlg
0x18005fd80  call    cs:__imp_GetDlgItem
0x18005fd86  mov     rcx, rax; hWnd
0x18005fd89  mov     edx, ebx; nCmdShow
0x18005fd8b  call    cs:__imp_ShowWindow
0x18005fd91  xor     r13d, r13d
0x18005fd94  test    esi, esi
0x18005fd96  jnz     loc_18005FF13
0x18005fd9c  xor     edx, edx; Val
0x18005fd9e  lea     r8d, [r13+70h]; Size
0x18005fda2  lea     rcx, [rsp+140h+var_110]; void *
0x18005fda7  call    memset_0
0x18005fdac  lea     rdx, [rbp+40h+hMem]; unsigned __int16 **
0x18005fdb0  mov     [rbp+40h+hMem], r13
0x18005fdb4  mov     rcx, r12; hWnd
0x18005fdb7  call    ?GetSelectedText@@YAXPEAUHWND__@@PEAPEAG@Z; GetSelectedText(HWND__ *,ushort * *)
0x18005fdbc  mov     rsi, [rbp+40h+hMem]
0x18005fdc0  lea     rdx, [rsp+140h+var_110]; struct _LDAPSERVERPARAMS *
0x18005fdc5  mov     rcx, rsi; unsigned __int16 *
0x18005fdc8  call    ?GetLDAPServerParams@@YAHPEAGPEAU_LDAPSERVERPARAMS@@@Z; GetLDAPServerParams(ushort *,_LDAPSERVERPARAMS *)
0x18005fdcd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005fdd1  test    r14d, r14d
0x18005fdd4  jnz     short loc_18005FE4E
0x18005fdd6  mov     rcx, [rsp+140h+lpFileName+8]; lpFileName
0x18005fddb  test    rcx, rcx
0x18005fdde  jz      short loc_18005FE4E
0x18005fde0  mov     rax, rbx
0x18005fde3  inc     rax
0x18005fde6  cmp     [rcx+rax*2], r13w
0x18005fdeb  jnz     short loc_18005FDE3
0x18005fded  test    rax, rax
0x18005fdf0  jz      short loc_18005FE4E
0x18005fdf2  call    cs:__imp_GetFileAttributesW
0x18005fdf8  cmp     eax, 0FFFFFFFFh
0x18005fdfb  jz      short loc_18005FE4E
0x18005fdfd  mov     rdx, [rsp+140h+lpFileName+8]; name
0x18005fe02  mov     r9d, 86h; cx
0x18005fe08  mov     rcx, cs:hinstMapiX; hInst
0x18005fe0f  xor     r8d, r8d; type
0x18005fe12  mov     [rsp+140h+fuLoad], 1010h; fuLoad
0x18005fe1a  mov     [rsp+140h+cy], 26h ; '&'; cy
0x18005fe22  call    cs:__imp_LoadImageW
0x18005fe28  test    rax, rax
0x18005fe2b  jz      short loc_18005FE4E
0x18005fe2d  xor     r9d, r9d; wParam
0x18005fe30  mov     qword ptr [rsp+140h+cy], rax; lParam
0x18005fe35  mov     r8d, 172h; Msg
0x18005fe3b  mov     rcx, rdi; hDlg
0x18005fe3e  lea     edx, [r9+66h]; nIDDlgItem
0x18005fe42  call    cs:__imp_SendDlgItemMessageW
0x18005fe48  mov     r15d, 1
0x18005fe4e  mov     rax, [rsp+140h+lpFileName]
0x18005fe53  test    rax, rax
0x18005fe56  jz      short loc_18005FEA4
0x18005fe58  inc     rbx
0x18005fe5b  cmp     [rax+rbx*2], r13w
0x18005fe60  jnz     short loc_18005FE58
0x18005fe62  mov     r9d, 7; cchCount1
0x18005fe68  lea     r8, aHttp_2; "http://"
0x18005fe6f  cmp     rbx, r9
0x18005fe72  cmova   rbx, r9
0x18005fe76  lea     edx, [r9-6]; dwCmpFlags
0x18005fe7a  mov     [rsp+140h+fuLoad], ebx; cchCount2
0x18005fe7e  lea     ecx, [rdx+7Eh]; Locale
0x18005fe81  mov     qword ptr [rsp+140h+cy], rax; lpString2
0x18005fe86  call    cs:__imp_CompareStringW
0x18005fe8c  cmp     eax, 2
0x18005fe8f  jnz     short loc_18005FEA4
0x18005fe91  lea     edx, [rax+9]; nIDDlgItem
0x18005fe94  mov     rcx, rdi; hDlg
0x18005fe97  call    cs:__imp_GetDlgItem
0x18005fe9d  mov     edx, 1
0x18005fea2  jmp     short loc_18005FEB4
0x18005fea4  mov     edx, 0Bh; nIDDlgItem
0x18005fea9  mov     rcx, rdi; hDlg
0x18005feac  call    cs:__imp_GetDlgItem
0x18005feb2  xor     edx, edx; bEnable
0x18005feb4  mov     rcx, rax; hWnd
0x18005feb7  call    cs:__imp_EnableWindow
0x18005febd  movaps  xmm0, [rsp+140h+var_110]
0x18005fec2  lea     rcx, [rbp+40h+var_A0]
0x18005fec6  movaps  xmm1, [rsp+140h+var_100]
0x18005fecb  movaps  [rbp+40h+var_A0], xmm0
0x18005fecf  movaps  xmm0, xmmword ptr [rsp+140h+lpFileName]
0x18005fed4  movaps  [rbp+40h+var_80], xmm0
0x18005fed8  movaps  xmm0, [rsp+140h+var_D0]
0x18005fedd  movaps  [rbp+40h+var_90], xmm1
0x18005fee1  movaps  xmm1, [rsp+140h+var_E0]
0x18005fee6  movaps  [rbp+40h+var_60], xmm0
0x18005feea  movaps  xmm0, [rbp+40h+var_B0]
0x18005feee  movaps  [rbp+40h+var_70], xmm1
0x18005fef2  movaps  xmm1, [rbp+40h+var_C0]
0x18005fef6  movaps  [rbp+40h+var_40], xmm0
0x18005fefa  movaps  [rbp+40h+var_50], xmm1
0x18005fefe  call    ?FreeLDAPServerParams@@YAXU_LDAPSERVERPARAMS@@@Z; FreeLDAPServerParams(_LDAPSERVERPARAMS)
0x18005ff03  test    rsi, rsi
0x18005ff06  jz      short loc_18005FF2C
0x18005ff08  mov     rcx, rsi; hMem
0x18005ff0b  call    cs:__imp_LocalFree
0x18005ff11  jmp     short loc_18005FF2C
0x18005ff13  mov     edx, 0Bh; nIDDlgItem
0x18005ff18  mov     rcx, rdi; hDlg
0x18005ff1b  call    cs:__imp_GetDlgItem
0x18005ff21  mov     rcx, rax; hWnd
0x18005ff24  xor     edx, edx; bEnable
0x18005ff26  call    cs:__imp_EnableWindow
0x18005ff2c  neg     r15d
0x18005ff2f  mov     edx, 66h ; 'f'; nIDDlgItem
0x18005ff34  mov     rcx, rdi; hDlg
0x18005ff37  sbb     ebx, ebx
0x18005ff39  and     ebx, 5
0x18005ff3c  call    cs:__imp_GetDlgItem
0x18005ff42  mov     rcx, rax
0x18005ff45  mov     edx, ebx
0x18005ff47  mov     rbx, [rsp+140h+arg_0]
0x18005ff4f  add     rsp, 110h
0x18005ff56  pop     r15
0x18005ff58  pop     r14
0x18005ff5a  pop     r13
0x18005ff5c  pop     r12
0x18005ff5e  pop     rdi
0x18005ff5f  pop     rsi
0x18005ff60  pop     rbp
0x18005ff61  jmp     cs:__imp_ShowWindow
```
