# ShowLVContextMenu(int,HWND__ *,HWND__ *,__int64,void *,IAddrBook *,HWND__ *)

- ea: `0x18006973c`
- end: `0x180069e1d`
- name: `?ShowLVContextMenu@@YAHHPEAUHWND__@@0_JPEAXPEAUIAddrBook@@0@Z`
- size: `1761`
- prototype: `int(int, HWND, HWND, __int64, void *, struct IAddrBook *, HWND)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180047e90`
- `0x18005abf0`
- `0x18005ca00`
- `0x180060850`

## callees

- `0x180007ff8`
- `0x18001d778`
- `0x18001dc44`
- `0x18002ba38`
- `0x180033ae0`
- `0x180064760`
- `0x1800648b0`
- `0x18006973c`
- `0x180091ef0`

## import_xrefs

- `USER32!LoadStringW` at `0x180069dd4`
- `USER32!LoadStringW` at `0x180069dd4`
- `USER32!SendMessageW` at `0x1800698ab`
- `USER32!SendMessageW` at `0x180069b43`
- `USER32!SendMessageW` at `0x1800698ab`
- `USER32!SendMessageW` at `0x180069b43`
- `USER32!GetParent` at `0x180069cb8`
- `USER32!GetParent` at `0x180069cb8`
- `USER32!InsertMenuW` at `0x180069e12`
- `USER32!InsertMenuW` at `0x180069e12`
- `USER32!DestroyMenu` at `0x180069d01`
- `USER32!DestroyMenu` at `0x180069d01`
- `USER32!EnableMenuItem` at `0x1800698ce`
- `USER32!EnableMenuItem` at `0x1800698df`
- `USER32!EnableMenuItem` at `0x1800698f8`
- `USER32!EnableMenuItem` at `0x180069909`
- `USER32!EnableMenuItem` at `0x180069ae4`
- `USER32!EnableMenuItem` at `0x180069afb`
- `USER32!EnableMenuItem` at `0x180069b13`
- `USER32!EnableMenuItem` at `0x180069b80`
- `USER32!EnableMenuItem` at `0x180069b91`
- `USER32!EnableMenuItem` at `0x180069d3f`
- `USER32!EnableMenuItem` at `0x180069d98`
- `USER32!EnableMenuItem` at `0x1800698ce`
- `USER32!EnableMenuItem` at `0x1800698df`
- `USER32!EnableMenuItem` at `0x1800698f8`
- `USER32!EnableMenuItem` at `0x180069909`
- `USER32!EnableMenuItem` at `0x180069ae4`
- `USER32!EnableMenuItem` at `0x180069afb`
- `USER32!EnableMenuItem` at `0x180069b13`
- `USER32!EnableMenuItem` at `0x180069b80`
- `USER32!EnableMenuItem` at `0x180069b91`
- `USER32!EnableMenuItem` at `0x180069d3f`
- `USER32!EnableMenuItem` at `0x180069d98`
- `USER32!LoadMenuW` at `0x1800697dd`
- `USER32!LoadMenuW` at `0x1800697dd`
- `USER32!GetSubMenu` at `0x1800697ed`
- `USER32!GetSubMenu` at `0x180069819`
- `USER32!GetSubMenu` at `0x18006982c`
- `USER32!GetSubMenu` at `0x1800697ed`
- `USER32!GetSubMenu` at `0x180069819`
- `USER32!GetSubMenu` at `0x18006982c`
- `USER32!TrackPopupMenu` at `0x180069cf3`
- `USER32!TrackPopupMenu` at `0x180069cf3`
- `USER32!RemoveMenu` at `0x180069990`
- `USER32!RemoveMenu` at `0x1800699bf`
- `USER32!RemoveMenu` at `0x1800699d0`
- `USER32!RemoveMenu` at `0x1800699e1`
- `USER32!RemoveMenu` at `0x1800699f2`
- `USER32!RemoveMenu` at `0x180069c1f`
- `USER32!RemoveMenu` at `0x180069caf`
- `USER32!RemoveMenu` at `0x180069990`
- `USER32!RemoveMenu` at `0x1800699bf`
- `USER32!RemoveMenu` at `0x1800699d0`
- `USER32!RemoveMenu` at `0x1800699e1`
- `USER32!RemoveMenu` at `0x1800699f2`
- `USER32!RemoveMenu` at `0x180069c1f`
- `USER32!RemoveMenu` at `0x180069caf`
- `USER32!ModifyMenuW` at `0x180069acb`
- `USER32!ModifyMenuW` at `0x180069df2`
- `USER32!ModifyMenuW` at `0x180069acb`
- `USER32!ModifyMenuW` at `0x180069df2`
- `USER32!CheckMenuRadioItem` at `0x180069c66`
- `USER32!CheckMenuRadioItem` at `0x180069c66`

## pseudocode

```c
__int64 __fastcall ShowLVContextMenu(int a1, HWND a2, HWND a3, __int64 a4, _DWORD *a5, struct IAddrBook *a6)
{
  int v7; // edi
  __int64 v8; // rdx
  int v9; // esi
  HMENU v10; // r14
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  HMENU SubMenu; // rax
  HMENU v16; // rbx
  HWND v17; // rsi
  int v18; // edi
  UINT v19; // edx
  UINT v20; // r8d
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  signed int j; // edi
  UINT_PTR v29; // rsi
  int v30; // r14d
  unsigned __int16 *v31; // rax
  UINT v32; // edx
  int v33; // eax
  struct _RecipientInfo *ItemFromLV; // rax
  unsigned int v35; // edi
  unsigned int v36; // eax
  unsigned int v37; // r14d
  __int64 v38; // rsi
  signed int i; // r9d
  struct IAddrBook *v40; // rcx
  __int64 v41; // rax
  HWND Parent; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  HMENU hMenu; // [rsp+50h] [rbp-B0h]
  HMENU MenuW; // [rsp+58h] [rbp-A8h]
  void *v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h]
  int v51[12]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NewItem[200]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = 0;
  v8 = 0;
  v50 = a4;
  v9 = 0;
  v10 = 0;
  if ( a1 > 6 )
  {
    v21 = a1 - 7;
    if ( !v21 )
    {
LABEL_7:
      v8 = 8606;
LABEL_8:
      v9 = -1;
      goto LABEL_9;
    }
    v22 = v21 - 1;
    if ( !v22 )
    {
      v8 = 8608;
      goto LABEL_8;
    }
    v23 = v22 - 1;
    if ( !v23 )
    {
      v7 = -1;
      v8 = 8605;
      goto LABEL_9;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 == 1 )
        {
          v7 = -1;
          v8 = 8700;
        }
        goto LABEL_9;
      }
    }
LABEL_36:
    v7 = 5;
    v8 = 8604;
    goto LABEL_9;
  }
  if ( !a1 )
    goto LABEL_36;
  v12 = a1 - 1;
  if ( !v12 || (v13 = v12 - 1) == 0 )
  {
    v7 = 6;
    v8 = 8607;
    v9 = 4;
    goto LABEL_9;
  }
  v14 = v13 - 1;
  if ( !v14 || (unsigned int)(v14 - 1) <= 1 )
    goto LABEL_7;
LABEL_9:
  MenuW = LoadMenuW(hinstMapiX, (LPCWSTR)v8);
  SubMenu = GetSubMenu(MenuW, 0);
  v16 = SubMenu;
  if ( !MenuW || !SubMenu )
    return (unsigned int)v10;
  hMenu = 0;
  if ( v7 != -1 )
    v10 = GetSubMenu(SubMenu, v7);
  if ( v9 != -1 )
    hMenu = GetSubMenu(v16, v9);
  v17 = a2;
  if ( v10 )
    AddExtendedMenuItems(a6, a2, v10, 1);
  GetCurrentOptionsState(a3, a2, v51);
  if ( a1 > 5 )
  {
    if ( a1 == 7 )
    {
      LoadStringW(hinstMapiX, 0xFAEu, NewItem, 200);
      ModifyMenuW(v16, 0x9CC6u, 0, 0x9CC6u, NewItem);
      InsertMenuW(v16, 0x9CC6u, 0x800u, 0x9CC6u, 0);
      goto LABEL_104;
    }
    if ( a1 != 8 )
    {
      if ( a1 == 9 )
      {
        EnableMenuItem(v16, 0x219Au, 1u);
        v40 = a6;
        if ( a5 )
          goto LABEL_105;
        v44 = (__int64)&a6[48];
        if ( !a6 )
          v44 = 1016;
        if ( !*(_QWORD *)v44 )
          goto LABEL_105;
        v45 = (__int64)&a6[50];
        if ( !a6 )
          v45 = 1032;
        if ( *(_QWORD *)v45 )
          goto LABEL_105;
        EnableMenuItem(v16, 2u, 0x401u);
        v20 = 1025;
        v19 = 3;
        goto LABEL_27;
      }
      if ( a1 != 12 )
        goto LABEL_104;
      v35 = PR_WAB_CUSTOMPROP1;
      if ( !PR_WAB_CUSTOMPROP1 )
      {
        v35 = 973668383;
        PR_WAB_CUSTOMPROP1 = 973668383;
      }
      v36 = PR_WAB_CUSTOMPROP2;
      if ( !PR_WAB_CUSTOMPROP2 )
      {
        v36 = 973602847;
        PR_WAB_CUSTOMPROP2 = 973602847;
      }
      v37 = v36;
      if ( (_DWORD)a5 == 3 )
        v37 = v35;
      if ( v37 == v35 )
        v35 = v36;
      v38 = 0;
      do
      {
        if ( *((_DWORD *)&MenuToPropTagMap + v38) == v35 && RemoveMenu(v16, v38, 0x400u) )
          break;
        v38 = (unsigned int)(v38 + 1);
      }
      while ( (int)v38 < 12 );
      if ( v37 != v35 )
      {
        for ( i = 0; i < 12; ++i )
        {
          if ( v37 == *((_DWORD *)&MenuToPropTagMap + i) )
          {
            if ( i > (int)v38 )
              --i;
            CheckMenuRadioItem(v16, 0, 0xBu, i, 0x400u);
            break;
          }
        }
      }
LABEL_103:
      v17 = a2;
      goto LABEL_104;
    }
    if ( !v51[6] )
    {
      v32 = 40135;
      goto LABEL_71;
    }
LABEL_72:
    if ( v51[2] )
      goto LABEL_104;
    v20 = 1;
    v19 = 40134;
    goto LABEL_27;
  }
  if ( a1 != 5 )
  {
    if ( a1 )
    {
      if ( a1 != 1 && a1 != 2 )
      {
        if ( (unsigned int)(a1 - 3) > 1 )
          goto LABEL_104;
        goto LABEL_23;
      }
      if ( a1 != 2 )
        RemoveMenu(v16, 0x9CC6u, 0);
      if ( !a5 )
        goto LABEL_104;
      v26 = a5[24];
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          if ( v27 != 1 )
          {
LABEL_49:
            if ( !a5[24] || !*((_QWORD *)a5 + 13) )
              goto LABEL_104;
            for ( j = 0; j < a5[24]; ++j )
            {
              v29 = 0;
              if ( j )
              {
                if ( j == 1 )
                {
                  v29 = 40129;
                }
                else if ( j == 2 )
                {
                  v29 = 40130;
                }
              }
              else
              {
                v29 = 40128;
              }
              if ( (int)a5[4] >= 0 )
              {
                v30 = 1;
                v31 = ConvertAtoW(*(LPCCH *)(*((_QWORD *)a5 + 13) + 8LL * j));
              }
              else
              {
                v30 = 0;
                v31 = *(unsigned __int16 **)(*((_QWORD *)a5 + 13) + 8LL * j);
              }
              v49 = v31;
              if ( v31 )
              {
                StringCchCopyNW(NewItem, 0xC8u, v31, 0xC4u);
                StringCchCatW(NewItem, 0xC8u, L" ->");
                if ( v30 )
                  LocalFreeAndNull(&v49);
              }
              else
              {
                NewItem[0] = 0;
              }
              ModifyMenuW(v16, j, 0x400u, v29, NewItem);
            }
            goto LABEL_103;
          }
LABEL_48:
          RemoveMenu(v16, 0x9CC2u, 0);
          goto LABEL_49;
        }
      }
      else
      {
        RemoveMenu(v16, 3u, 0x400u);
        RemoveMenu(v16, 0x9CC0u, 0);
      }
      RemoveMenu(v16, 0x9CC1u, 0);
      goto LABEL_48;
    }
    EnableMenuItem(v16, 0x219Au, 1u);
    if ( !v51[7] )
      EnableMenuItem(v16, 0x9CCAu, 1u);
    if ( !v51[1] )
    {
      v32 = 40133;
LABEL_71:
      EnableMenuItem(v16, v32, 1u);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
LABEL_23:
  v18 = SendMessageW(a2, 0x1032u, 0, 0);
  if ( v18 == 1 )
  {
    v33 = SendMessageW(a2, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
    if ( v33 == -1 )
      goto LABEL_104;
    ItemFromLV = GetItemFromLV(a2, v33);
    if ( !ItemFromLV || *(_DWORD *)ItemFromLV && *((_QWORD *)ItemFromLV + 1) )
      goto LABEL_104;
    EnableMenuItem(v16, 0x9CC5u, 1u);
    EnableMenuItem(v16, 0x9CCAu, 1u);
    v19 = 40139;
    goto LABEL_26;
  }
  EnableMenuItem(v16, 0x9CC5u, 1u);
  EnableMenuItem(v16, 0x9CCBu, 1u);
  if ( v18 <= 0 )
  {
    EnableMenuItem(v16, 0x9CC6u, 1u);
    v19 = 40138;
LABEL_26:
    v20 = 1;
LABEL_27:
    EnableMenuItem(v16, v19, v20);
  }
LABEL_104:
  v40 = a6;
LABEL_105:
  if ( hMenu )
  {
    v41 = (__int64)&v40[59].lpVtbl + 4;
    if ( !v40 )
      v41 = 1108;
    if ( !*(_DWORD *)v41 || (unsigned int)(a1 - 1) <= 4 )
      RemoveMenu(hMenu, 2u, 0x400u);
  }
  Parent = GetParent(v17);
  LODWORD(v10) = TrackPopupMenu(v16, 2u, (unsigned __int16)v50, WORD1(v50), 0, Parent, 0);
  DestroyMenu(MenuW);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006973c  mov     [rsp-8+arg_0], rbx
0x180069741  push    rbp
0x180069742  push    rsi
0x180069743  push    rdi
0x180069744  push    r12
0x180069746  push    r13
0x180069748  push    r14
0x18006974a  push    r15
0x18006974c  lea     rbp, [rsp-140h]
0x180069754  sub     rsp, 240h
0x18006975b  mov     rax, cs:__security_cookie
0x180069762  xor     rax, rsp
0x180069765  mov     [rbp+170h+var_40], rax
0x18006976c  mov     rax, [rbp+170h+arg_28]
0x180069773  mov     r12, r8
0x180069776  mov     r15, [rbp+170h+arg_20]
0x18006977d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180069781  mov     [rsp+270h+hWnd], rdx
0x180069786  xor     edi, edi
0x180069788  xor     edx, edx
0x18006978a  mov     [rsp+270h+var_208], r9
0x18006978f  xor     esi, esi
0x180069791  mov     [rsp+270h+var_230], rax
0x180069796  xor     r14d, r14d
0x180069799  mov     r13d, ecx
0x18006979c  cmp     ecx, 6
0x18006979f  jg      loc_180069926
0x1800697a5  test    ecx, ecx
0x1800697a7  jz      loc_180069959
0x1800697ad  sub     ecx, 1
0x1800697b0  jz      loc_180069914
0x1800697b6  sub     ecx, 1
0x1800697b9  jz      loc_180069914
0x1800697bf  sub     ecx, 1
0x1800697c2  jz      short loc_1800697CE
0x1800697c4  sub     ecx, 1
0x1800697c7  jz      short loc_1800697CE
0x1800697c9  cmp     ecx, 1
0x1800697cc  jnz     short loc_1800697D6
0x1800697ce  mov     edx, 219Eh; lpMenuName
0x1800697d3  mov     esi, r8d
0x1800697d6  mov     rcx, cs:hinstMapiX; hInstance
0x1800697dd  call    cs:__imp_LoadMenuW
0x1800697e3  mov     rcx, rax; hMenu
0x1800697e6  mov     [rsp+270h+var_218], rax
0x1800697eb  xor     edx, edx; nPos
0x1800697ed  call    cs:__imp_GetSubMenu
0x1800697f3  mov     rbx, rax
0x1800697f6  cmp     [rsp+270h+var_218], r14
0x1800697fb  jz      loc_180069D07
0x180069801  test    rax, rax
0x180069804  jz      loc_180069D07
0x18006980a  mov     [rsp+270h+hMenu], r14
0x18006980f  cmp     edi, 0FFFFFFFFh
0x180069812  jz      short loc_180069822
0x180069814  mov     edx, edi; nPos
0x180069816  mov     rcx, rax; hMenu
0x180069819  call    cs:__imp_GetSubMenu
0x18006981f  mov     r14, rax
0x180069822  cmp     esi, 0FFFFFFFFh
0x180069825  jz      short loc_180069837
0x180069827  mov     edx, esi; nPos
0x180069829  mov     rcx, rbx; hMenu
0x18006982c  call    cs:__imp_GetSubMenu
0x180069832  mov     [rsp+270h+hMenu], rax
0x180069837  mov     rsi, [rsp+270h+hWnd]
0x18006983c  mov     edi, 1
0x180069841  test    r14, r14
0x180069844  jz      short loc_180069859
0x180069846  mov     rcx, [rsp+270h+var_230]; struct IAddrBook *
0x18006984b  mov     r9d, edi; int
0x18006984e  mov     r8, r14; hMenu
0x180069851  mov     rdx, rsi; hWnd
0x180069854  call    ?AddExtendedMenuItems@@YAXPEAUIAddrBook@@PEAUHWND__@@PEAUHMENU__@@H@Z; AddExtendedMenuItems(IAddrBook *,HWND__ *,HMENU__ *,int)
0x180069859  lea     r8, [rsp+270h+var_200]; int *
0x18006985e  mov     rdx, rsi; HWND
0x180069861  mov     rcx, r12; hWnd
0x180069864  call    ?GetCurrentOptionsState@@YAXPEAUHWND__@@0PEAH@Z; GetCurrentOptionsState(HWND__ *,HWND__ *,int *)
0x180069869  cmp     r13d, 5
0x18006986d  jg      loc_180069BA1
0x180069873  jz      short loc_18006989D
0x180069875  mov     ecx, r13d
0x180069878  test    r13d, r13d
0x18006987b  jz      loc_180069AD9
0x180069881  sub     ecx, edi
0x180069883  jz      loc_18006997F
0x180069889  sub     ecx, edi
0x18006988b  jz      loc_18006997F
0x180069891  sub     ecx, edi
0x180069893  jz      short loc_18006989D
0x180069895  cmp     ecx, edi
0x180069897  jnz     loc_180069C71
0x18006989d  xor     r9d, r9d; lParam
0x1800698a0  xor     r8d, r8d; wParam
0x1800698a3  mov     edx, 1032h; Msg
0x1800698a8  mov     rcx, rsi; hWnd
0x1800698ab  call    cs:__imp_SendMessageW
0x1800698b1  mov     r12d, 1
0x1800698b7  mov     rdi, rax
0x1800698ba  cmp     eax, r12d
0x1800698bd  jz      loc_180069B31
0x1800698c3  mov     r8d, r12d; uEnable
0x1800698c6  mov     edx, 9CC5h; uIDEnableItem
0x1800698cb  mov     rcx, rbx; hMenu
0x1800698ce  call    cs:__imp_EnableMenuItem
0x1800698d4  mov     r8d, r12d; uEnable
0x1800698d7  mov     edx, 9CCBh; uIDEnableItem
0x1800698dc  mov     rcx, rbx; hMenu
0x1800698df  call    cs:__imp_EnableMenuItem
0x1800698e5  test    edi, edi
0x1800698e7  jg      loc_180069C71
0x1800698ed  mov     r8d, r12d; uEnable
0x1800698f0  mov     edx, 9CC6h; uIDEnableItem
0x1800698f5  mov     rcx, rbx; hMenu
0x1800698f8  call    cs:__imp_EnableMenuItem
0x1800698fe  mov     edx, 9CCAh; uIDEnableItem
0x180069903  mov     r8d, r12d; uEnable
0x180069906  mov     rcx, rbx; hMenu
0x180069909  call    cs:__imp_EnableMenuItem
0x18006990f  jmp     loc_180069C71
0x180069914  mov     edi, 6
0x180069919  mov     edx, 219Fh
0x18006991e  lea     esi, [rdi-2]
0x180069921  jmp     loc_1800697D6
0x180069926  sub     ecx, 7
0x180069929  jz      loc_1800697CE
0x18006992f  sub     ecx, 1
0x180069932  jz      short loc_180069975
0x180069934  sub     ecx, 1
0x180069937  jz      short loc_180069968
0x180069939  sub     ecx, 1
0x18006993c  jz      short loc_180069959
0x18006993e  sub     ecx, 1
0x180069941  jz      short loc_180069959
0x180069943  cmp     ecx, 1
0x180069946  jnz     loc_1800697D6
0x18006994c  mov     edi, r8d
0x18006994f  mov     edx, 21FCh
0x180069954  jmp     loc_1800697D6
0x180069959  mov     edi, 5
0x18006995e  mov     edx, 219Ch
0x180069963  jmp     loc_1800697D6
0x180069968  mov     edi, r8d
0x18006996b  mov     edx, 219Dh
0x180069970  jmp     loc_1800697D6
0x180069975  mov     edx, 21A0h
0x18006997a  jmp     loc_1800697D3
0x18006997f  cmp     r13d, 2
0x180069983  jz      short loc_180069996
0x180069985  xor     r8d, r8d; uFlags
0x180069988  mov     edx, 9CC6h; uPosition
0x18006998d  mov     rcx, rbx; hMenu
0x180069990  call    cs:__imp_RemoveMenu
0x180069996  test    r15, r15
0x180069999  jz      loc_180069C71
0x18006999f  mov     ecx, [r15+60h]
0x1800699a3  test    ecx, ecx
0x1800699a5  jz      short loc_1800699B1
0x1800699a7  sub     ecx, edi
0x1800699a9  jz      short loc_1800699D6
0x1800699ab  cmp     ecx, edi
0x1800699ad  jz      short loc_1800699E7
0x1800699af  jmp     short loc_1800699F8
0x1800699b1  mov     edx, 3; uPosition
0x1800699b6  mov     r8d, 400h; uFlags
0x1800699bc  mov     rcx, rbx; hMenu
0x1800699bf  call    cs:__imp_RemoveMenu
0x1800699c5  xor     r8d, r8d; uFlags
0x1800699c8  mov     edx, 9CC0h; uPosition
0x1800699cd  mov     rcx, rbx; hMenu
0x1800699d0  call    cs:__imp_RemoveMenu
0x1800699d6  xor     r8d, r8d; uFlags
0x1800699d9  mov     edx, 9CC1h; uPosition
0x1800699de  mov     rcx, rbx; hMenu
0x1800699e1  call    cs:__imp_RemoveMenu
0x1800699e7  xor     r8d, r8d; uFlags
0x1800699ea  mov     edx, 9CC2h; uPosition
0x1800699ef  mov     rcx, rbx; hMenu
0x1800699f2  call    cs:__imp_RemoveMenu
0x1800699f8  cmp     dword ptr [r15+60h], 0
0x1800699fd  jbe     loc_180069C71
0x180069a03  cmp     qword ptr [r15+68h], 0
0x180069a08  jz      loc_180069C71
0x180069a0e  xor     edi, edi
0x180069a10  lea     r12d, [rdi+1]
0x180069a14  cmp     edi, [r15+60h]
0x180069a18  jge     loc_180069C6C
0x180069a1e  xor     esi, esi
0x180069a20  mov     ecx, edi
0x180069a22  test    edi, edi
0x180069a24  jz      short loc_180069A3E
0x180069a26  sub     ecx, r12d
0x180069a29  jz      short loc_180069A37
0x180069a2b  cmp     ecx, r12d
0x180069a2e  jnz     short loc_180069A43
0x180069a30  mov     esi, 9CC2h
0x180069a35  jmp     short loc_180069A43
0x180069a37  mov     esi, 9CC1h
0x180069a3c  jmp     short loc_180069A43
0x180069a3e  mov     esi, 9CC0h
0x180069a43  cmp     dword ptr [r15+10h], 0
0x180069a48  movsxd  rdx, edi
0x180069a4b  jge     short loc_180069A5A
0x180069a4d  mov     rax, [r15+68h]
0x180069a51  xor     r14d, r14d
0x180069a54  mov     rax, [rax+rdx*8]
0x180069a58  jmp     short loc_180069A6A
0x180069a5a  mov     rcx, [r15+68h]
0x180069a5e  mov     r14d, r12d
0x180069a61  mov     rcx, [rcx+rdx*8]; lpMultiByteStr
0x180069a65  call    ?ConvertAtoW@@YAPEAGPEBD@Z; ConvertAtoW(char const *)
0x180069a6a  mov     [rsp+270h+var_210], rax
0x180069a6f  test    rax, rax
0x180069a72  jz      short loc_180069AB0
0x180069a74  mov     r9d, 0C4h; unsigned __int64
0x180069a7a  lea     rcx, [rbp+170h+NewItem]; unsigned __int16 *
0x180069a7e  mov     r8, rax; unsigned __int16 *
0x180069a81  lea     edx, [r9+4]; unsigned __int64
0x180069a85  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180069a8a  lea     r8, asc_18009D8B8; " ->"
0x180069a91  mov     edx, 0C8h; unsigned __int64
0x180069a96  lea     rcx, [rbp+170h+NewItem]; unsigned __int16 *
0x180069a9a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180069a9f  test    r14d, r14d
0x180069aa2  jz      short loc_180069AB4
0x180069aa4  lea     rcx, [rsp+270h+var_210]; void **
0x180069aa9  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180069aae  jmp     short loc_180069AB4
0x180069ab0  mov     [rbp+170h+NewItem], ax
0x180069ab4  lea     rax, [rbp+170h+NewItem]
0x180069ab8  mov     r9, rsi; uIDNewItem
0x180069abb  mov     r8d, 400h; uFlags
0x180069ac1  mov     [rsp+270h+lpNewItem], rax; lpNewItem
0x180069ac6  mov     edx, edi; uPosition
0x180069ac8  mov     rcx, rbx; hMnu
0x180069acb  call    cs:__imp_ModifyMenuW
0x180069ad1  add     edi, r12d
0x180069ad4  jmp     loc_180069A14
0x180069ad9  mov     r8d, edi; uEnable
0x180069adc  mov     edx, 219Ah; uIDEnableItem
0x180069ae1  mov     rcx, rbx; hMenu
0x180069ae4  call    cs:__imp_EnableMenuItem
0x180069aea  cmp     [rbp+170h+var_1E4], 0
0x180069aee  jnz     short loc_180069B01
0x180069af0  mov     r8d, edi; uEnable
0x180069af3  mov     edx, 9CCAh; uIDEnableItem
0x180069af8  mov     rcx, rbx; hMenu
0x180069afb  call    cs:__imp_EnableMenuItem
0x180069b01  cmp     [rsp+270h+var_1FC], 0
0x180069b06  jnz     short loc_180069B19
0x180069b08  mov     edx, 9CC5h; uIDEnableItem
0x180069b0d  mov     r8d, edi; uEnable
0x180069b10  mov     rcx, rbx; hMenu
0x180069b13  call    cs:__imp_EnableMenuItem
0x180069b19  cmp     [rsp+270h+var_1F8], 0
0x180069b1e  jnz     loc_180069C71
0x180069b24  mov     r8d, edi
0x180069b27  mov     edx, 9CC6h
0x180069b2c  jmp     loc_180069906
0x180069b31  mov     r9d, 2; lParam
0x180069b37  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180069b3b  mov     edx, 100Ch; Msg
0x180069b40  mov     rcx, rsi; hWnd
0x180069b43  call    cs:__imp_SendMessageW
0x180069b49  cmp     eax, 0FFFFFFFFh
0x180069b4c  jz      loc_180069C71
0x180069b52  mov     edx, eax; int
0x180069b54  mov     rcx, rsi; hWnd
0x180069b57  call    ?GetItemFromLV@@YAPEAU_RecipientInfo@@PEAUHWND__@@H@Z; GetItemFromLV(HWND__ *,int)
0x180069b5c  test    rax, rax
0x180069b5f  jz      loc_180069C71
0x180069b65  cmp     dword ptr [rax], 0
0x180069b68  jz      short loc_180069B75
0x180069b6a  cmp     qword ptr [rax+8], 0
0x180069b6f  jnz     loc_180069C71
0x180069b75  mov     r8d, r12d; uEnable
0x180069b78  mov     edx, 9CC5h; uIDEnableItem
0x180069b7d  mov     rcx, rbx; hMenu
0x180069b80  call    cs:__imp_EnableMenuItem
0x180069b86  mov     r8d, r12d; uEnable
0x180069b89  mov     edx, 9CCAh; uIDEnableItem
0x180069b8e  mov     rcx, rbx; hMenu
0x180069b91  call    cs:__imp_EnableMenuItem
0x180069b97  mov     edx, 9CCBh
0x180069b9c  jmp     loc_180069903
0x180069ba1  mov     ecx, r13d
0x180069ba4  sub     ecx, 7
0x180069ba7  jz      loc_180069DBE
0x180069bad  sub     ecx, edi
0x180069baf  jz      loc_180069DAA
0x180069bb5  sub     ecx, edi
0x180069bb7  jz      loc_180069D34
0x180069bbd  cmp     ecx, 3
0x180069bc0  jnz     loc_180069C71
0x180069bc6  mov     edi, cs:?PR_WAB_CUSTOMPROP1@@3KA; ulong PR_WAB_CUSTOMPROP1
0x180069bcc  test    edi, edi
0x180069bce  jnz     short loc_180069BDB
0x180069bd0  mov     edi, 3A09001Fh
0x180069bd5  mov     cs:?PR_WAB_CUSTOMPROP1@@3KA, edi; ulong PR_WAB_CUSTOMPROP1
0x180069bdb  mov     eax, cs:?PR_WAB_CUSTOMPROP2@@3KA; ulong PR_WAB_CUSTOMPROP2
  ... truncated ...
```
