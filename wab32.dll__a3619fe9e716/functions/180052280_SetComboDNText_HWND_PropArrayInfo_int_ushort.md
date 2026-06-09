# SetComboDNText(HWND__ *,_PropArrayInfo *,int,ushort *)

- ea: `0x180052280`
- end: `0x18005278c`
- name: `?SetComboDNText@@YAXPEAUHWND__@@PEAU_PropArrayInfo@@HPEAG@Z`
- size: `1292`
- prototype: `void(HWND, struct _PropArrayInfo *, int, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004b418`
- `0x18004d9a0`
- `0x180052de4`
- `0x180056080`
- `0x180057370`

## callees

- `0x1800045e4`
- `0x18002fe40`
- `0x180033ae0`
- `0x180052280`
- `0x1800691e4`
- `0x18006a678`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18005233a`
- `KERNEL32!LocalAlloc` at `0x18005234d`
- `KERNEL32!LocalAlloc` at `0x180052360`
- `KERNEL32!LocalAlloc` at `0x180052373`
- `KERNEL32!LocalAlloc` at `0x180052463`
- `KERNEL32!LocalAlloc` at `0x18005233a`
- `KERNEL32!LocalAlloc` at `0x18005234d`
- `KERNEL32!LocalAlloc` at `0x180052360`
- `KERNEL32!LocalAlloc` at `0x180052373`
- `KERNEL32!LocalAlloc` at `0x180052463`
- `KERNEL32!lstrcmpW` at `0x1800524dd`
- `KERNEL32!lstrcmpW` at `0x180052569`
- `KERNEL32!lstrcmpW` at `0x1800525ec`
- `KERNEL32!lstrcmpW` at `0x180052652`
- `KERNEL32!lstrcmpW` at `0x1800526fc`
- `KERNEL32!lstrcmpW` at `0x1800524dd`
- `KERNEL32!lstrcmpW` at `0x180052569`
- `KERNEL32!lstrcmpW` at `0x1800525ec`
- `KERNEL32!lstrcmpW` at `0x180052652`
- `KERNEL32!lstrcmpW` at `0x1800526fc`
- `USER32!SendMessageW` at `0x1800522e9`
- `USER32!SendMessageW` at `0x1800522fd`
- `USER32!SendMessageW` at `0x180052311`
- `USER32!SendMessageW` at `0x1800523d5`
- `USER32!SendMessageW` at `0x18005240b`
- `USER32!SendMessageW` at `0x1800524f3`
- `USER32!SendMessageW` at `0x180052581`
- `USER32!SendMessageW` at `0x180052602`
- `USER32!SendMessageW` at `0x180052668`
- `USER32!SendMessageW` at `0x180052712`
- `USER32!SendMessageW` at `0x180052726`
- `USER32!SendMessageW` at `0x1800522e9`
- `USER32!SendMessageW` at `0x1800522fd`
- `USER32!SendMessageW` at `0x180052311`
- `USER32!SendMessageW` at `0x1800523d5`
- `USER32!SendMessageW` at `0x18005240b`
- `USER32!SendMessageW` at `0x1800524f3`
- `USER32!SendMessageW` at `0x180052581`
- `USER32!SendMessageW` at `0x180052602`
- `USER32!SendMessageW` at `0x180052668`
- `USER32!SendMessageW` at `0x180052712`
- `USER32!SendMessageW` at `0x180052726`
- `USER32!GetDlgItem` at `0x1800522bd`
- `USER32!GetDlgItem` at `0x1800522bd`
- `USER32!UpdateWindow` at `0x18005275f`
- `USER32!UpdateWindow` at `0x18005275f`
- `USER32!GetWindowTextW` at `0x1800523c1`
- `USER32!GetWindowTextW` at `0x1800523c1`
- `USER32!SetWindowTextW` at `0x18005231d`
- `USER32!SetWindowTextW` at `0x180052732`
- `USER32!SetWindowTextW` at `0x18005231d`
- `USER32!SetWindowTextW` at `0x180052732`
- `USER32!GetDlgItemTextW` at `0x180052423`
- `USER32!GetDlgItemTextW` at `0x18005243b`
- `USER32!GetDlgItemTextW` at `0x180052453`
- `USER32!GetDlgItemTextW` at `0x18005262c`
- `USER32!GetDlgItemTextW` at `0x180052423`
- `USER32!GetDlgItemTextW` at `0x18005243b`
- `USER32!GetDlgItemTextW` at `0x180052453`
- `USER32!GetDlgItemTextW` at `0x18005262c`

## pseudocode

```c
void __fastcall SetComboDNText(HWND a1, struct _PropArrayInfo *a2, int a3, unsigned __int16 *a4)
{
  HWND DlgItem; // rax
  HWND v7; // rdi
  const WCHAR *v8; // rbx
  _WORD *v9; // rbx
  unsigned __int16 *v10; // rsi
  _WORD *v11; // r13
  _WORD *v12; // rax
  unsigned __int16 *v13; // r14
  __int64 v14; // r15
  __int64 v15; // rax
  _WORD *v16; // rax
  const WCHAR *v17; // rsi
  unsigned __int16 *v18; // r8
  __int64 v19; // rax
  unsigned __int16 *v20; // rcx
  __int64 v21; // rax
  unsigned __int16 *v22; // r8
  __int64 v23; // rax
  HWND v24; // rcx
  __int64 v25; // rax
  struct _PropArrayInfo *v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  void *v29; // rcx
  BOOL v30; // [rsp+38h] [rbp-41h]
  LPVOID pv; // [rsp+50h] [rbp-29h] BYREF
  HWND hDlg; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v33; // [rsp+60h] [rbp-19h] BYREF
  struct _PropArrayInfo *v34; // [rsp+68h] [rbp-11h]
  void *v35; // [rsp+70h] [rbp-9h] BYREF
  void *v36; // [rsp+78h] [rbp-1h] BYREF
  void *v37; // [rsp+80h] [rbp+7h] BYREF
  void *v38; // [rsp+88h] [rbp+Fh] BYREF

  v34 = a2;
  hDlg = a1;
  DlgItem = GetDlgItem(a1, 67);
  v7 = DlgItem;
  if ( a3 )
  {
    v9 = LocalAlloc(0x40u, 0x320u);
    v35 = v9;
    v10 = (unsigned __int16 *)LocalAlloc(0x40u, 0x320u);
    v33 = v10;
    v11 = LocalAlloc(0x40u, 0x320u);
    v36 = v11;
    v12 = LocalAlloc(0x40u, 0x320u);
    v37 = v12;
    v13 = v12;
    if ( v9 && v10 && v11 && v12 )
    {
      *v12 = 0;
      *v11 = 0;
      *v10 = 0;
      *v9 = 0;
      GetWindowTextW(v7, v12, 400);
      SendMessageW(v7, 0x14Bu, 0, 0);
      TrimSpaces(v13);
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( v13[v15] );
      if ( v15 )
        SendMessageW(v7, 0x143u, 0, (LPARAM)v13);
      GetDlgItemTextW(hDlg, 2765, v9, 400);
      GetDlgItemTextW(hDlg, 2766, v10, 400);
      GetDlgItemTextW(hDlg, 2769, v11, 400);
      v16 = LocalAlloc(0x40u, 0x640u);
      v38 = v16;
      pv = v16;
      v17 = v16;
      if ( v16 )
      {
        v18 = v33;
        *v16 = 0;
        if ( SetLocalizedDisplayName(v9, v11, v18, 0, 0, (unsigned __int16 **)&pv, 0x320u, bDNisByLN, 0, 0) )
        {
          v19 = -1;
          do
            ++v19;
          while ( v17[v19] );
          if ( v19 && lstrcmpW(v17, v13) )
            SendMessageW(v7, 0x143u, 0, (LPARAM)v17);
        }
        v20 = (unsigned __int16 *)szResourceDNByCommaLN;
        if ( !bDNisByLN )
          v20 = &szResourceDNByLN;
        if ( SetLocalizedDisplayName(v9, v11, v33, 0, 0, (unsigned __int16 **)&pv, 0x320u, bDNisByLN, v20, 0) )
        {
          v21 = -1;
          do
            ++v21;
          while ( v17[v21] );
          if ( v21 && lstrcmpW(v17, v13) )
            SendMessageW(v7, 0x143u, 0, (LPARAM)v17);
        }
        v22 = v33;
        v30 = bDNisByLN == 0;
        *v17 = 0;
        if ( SetLocalizedDisplayName(v9, v11, v22, 0, 0, (unsigned __int16 **)&pv, 0x320u, v30, 0, 0) )
        {
          v23 = -1;
          do
            ++v23;
          while ( v17[v23] );
          if ( v23 && lstrcmpW(v17, v13) )
            SendMessageW(v7, 0x143u, 0, (LPARAM)v17);
        }
        LocalFreeAndNull(&v38);
      }
      v24 = hDlg;
      *v9 = 0;
      GetDlgItemTextW(v24, 2770, v9, 400);
      TrimSpaces(v9);
      v25 = -1;
      do
        ++v25;
      while ( v9[v25] );
      if ( v25 && lstrcmpW(v9, v13) )
        SendMessageW(v7, 0x143u, 0, (LPARAM)v9);
      v26 = v34;
      *v9 = 0;
      LODWORD(hDlg) = 0;
      pv = 0;
      v27 = *((_QWORD *)v26 + 3);
      v38 = (void *)0x3A16001F00000001LL;
      v28 = (*(__int64 (__fastcall **)(__int64, void **, __int64, HWND *, LPVOID *))(*(_QWORD *)v27 + 40LL))(
              v27,
              &v38,
              0x80000000LL,
              &hDlg,
              &pv);
      v29 = pv;
      if ( v28 >= 0 && *(_DWORD *)pv == 974520351 )
      {
        StringCchCopyW(v9, 0x190u, *((const unsigned __int16 **)pv + 1));
        v29 = pv;
      }
      if ( v29 )
        MAPIFreeBuffer(v29);
      TrimSpaces(v9);
      do
        ++v14;
      while ( v9[v14] );
      if ( v14 && lstrcmpW(v9, v13) )
        SendMessageW(v7, 0x143u, 0, (LPARAM)v9);
      SendMessageW(v7, 0x14Eu, 0, 0);
      SetWindowTextW(v7, v13);
    }
    LocalFreeAndNull(&v35);
    LocalFreeAndNull((void **)&v33);
    LocalFreeAndNull(&v36);
    LocalFreeAndNull(&v37);
  }
  else
  {
    v8 = &szNULL;
    if ( a4 )
      v8 = a4;
    SendMessageW(DlgItem, 0x14Bu, 0, 0);
    SendMessageW(v7, 0x143u, 0, (LPARAM)v8);
    SendMessageW(v7, 0x14Eu, 0, 0);
    SetWindowTextW(v7, v8);
  }
  UpdateWindow(v7);
}

```

## disassembly

```asm
0x180052280  mov     [rsp-8+arg_10], rbx
0x180052285  push    rbp
0x180052286  push    rsi
0x180052287  push    rdi
0x180052288  push    r12
0x18005228a  push    r13
0x18005228c  push    r14
0x18005228e  push    r15
0x180052290  lea     rbp, [rsp-27h]
0x180052295  sub     rsp, 0A0h
0x18005229c  mov     rax, cs:__security_cookie
0x1800522a3  xor     rax, rsp
0x1800522a6  mov     [rbp+57h+var_40], rax
0x1800522aa  mov     [rbp+57h+var_68], rdx
0x1800522ae  mov     rsi, r9
0x1800522b1  mov     edx, 43h ; 'C'; nIDDlgItem
0x1800522b6  mov     [rbp+57h+hDlg], rcx
0x1800522ba  mov     ebx, r8d
0x1800522bd  call    cs:__imp_GetDlgItem
0x1800522c3  xor     r12d, r12d
0x1800522c6  mov     rdi, rax
0x1800522c9  test    ebx, ebx
0x1800522cb  jnz     short loc_180052328
0x1800522cd  test    rsi, rsi
0x1800522d0  lea     rbx, ?szNULL@@3QBGB; ushort const near * const szNULL
0x1800522d7  mov     edx, 14Bh; Msg
0x1800522dc  mov     rcx, rax; hWnd
0x1800522df  cmovnz  rbx, rsi
0x1800522e3  xor     r9d, r9d; lParam
0x1800522e6  xor     r8d, r8d; wParam
0x1800522e9  call    cs:__imp_SendMessageW
0x1800522ef  mov     r9, rbx; lParam
0x1800522f2  xor     r8d, r8d; wParam
0x1800522f5  mov     edx, 143h; Msg
0x1800522fa  mov     rcx, rdi; hWnd
0x1800522fd  call    cs:__imp_SendMessageW
0x180052303  xor     r9d, r9d; lParam
0x180052306  xor     r8d, r8d; wParam
0x180052309  mov     edx, 14Eh; Msg
0x18005230e  mov     rcx, rdi; hWnd
0x180052311  call    cs:__imp_SendMessageW
0x180052317  mov     rdx, rbx; lpString
0x18005231a  mov     rcx, rdi; hWnd
0x18005231d  call    cs:__imp_SetWindowTextW
0x180052323  jmp     loc_18005275C
0x180052328  mov     r15d, 320h
0x18005232e  mov     r14d, 40h ; '@'
0x180052334  mov     edx, r15d; uBytes
0x180052337  mov     ecx, r14d; uFlags
0x18005233a  call    cs:__imp_LocalAlloc
0x180052340  mov     edx, r15d; uBytes
0x180052343  mov     ecx, r14d; uFlags
0x180052346  mov     rbx, rax
0x180052349  mov     [rbp+57h+var_60], rax
0x18005234d  call    cs:__imp_LocalAlloc
0x180052353  mov     edx, r15d; uBytes
0x180052356  mov     ecx, r14d; uFlags
0x180052359  mov     rsi, rax
0x18005235c  mov     [rbp+57h+var_70], rax
0x180052360  call    cs:__imp_LocalAlloc
0x180052366  mov     edx, r15d; uBytes
0x180052369  mov     ecx, r14d; uFlags
0x18005236c  mov     r13, rax
0x18005236f  mov     [rbp+57h+var_58], rax
0x180052373  call    cs:__imp_LocalAlloc
0x180052379  mov     [rbp+57h+var_50], rax
0x18005237d  mov     r14, rax
0x180052380  test    rbx, rbx
0x180052383  jz      loc_180052738
0x180052389  test    rsi, rsi
0x18005238c  jz      loc_180052738
0x180052392  test    r13, r13
0x180052395  jz      loc_180052738
0x18005239b  test    rax, rax
0x18005239e  jz      loc_180052738
0x1800523a4  mov     [rax], r12w
0x1800523a8  mov     r8d, 190h; nMaxCount
0x1800523ae  mov     [r13+0], r12w
0x1800523b3  mov     rdx, rax; lpString
0x1800523b6  mov     [rsi], r12w
0x1800523ba  mov     rcx, rdi; hWnd
0x1800523bd  mov     [rbx], r12w
0x1800523c1  call    cs:__imp_GetWindowTextW
0x1800523c7  xor     r9d, r9d; lParam
0x1800523ca  xor     r8d, r8d; wParam
0x1800523cd  mov     edx, 14Bh; Msg
0x1800523d2  mov     rcx, rdi; hWnd
0x1800523d5  call    cs:__imp_SendMessageW
0x1800523db  mov     rcx, r14; unsigned __int16 *
0x1800523de  call    ?TrimSpaces@@YAHPEAG@Z; TrimSpaces(ushort *)
0x1800523e3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800523e7  mov     rax, r15
0x1800523ea  inc     rax
0x1800523ed  cmp     [r14+rax*2], r12w
0x1800523f2  jnz     short loc_1800523EA
0x1800523f4  mov     r12d, 143h
0x1800523fa  test    rax, rax
0x1800523fd  jz      short loc_180052411
0x1800523ff  mov     r9, r14; lParam
0x180052402  xor     r8d, r8d; wParam
0x180052405  mov     edx, r12d; Msg
0x180052408  mov     rcx, rdi; hWnd
0x18005240b  call    cs:__imp_SendMessageW
0x180052411  mov     rcx, [rbp+57h+hDlg]; hDlg
0x180052415  mov     r9d, 190h; cchMax
0x18005241b  mov     r8, rbx; lpString
0x18005241e  mov     edx, 0ACDh; nIDDlgItem
0x180052423  call    cs:__imp_GetDlgItemTextW
0x180052429  mov     rcx, [rbp+57h+hDlg]; hDlg
0x18005242d  mov     r9d, 190h; cchMax
0x180052433  mov     r8, rsi; lpString
0x180052436  mov     edx, 0ACEh; nIDDlgItem
0x18005243b  call    cs:__imp_GetDlgItemTextW
0x180052441  mov     rcx, [rbp+57h+hDlg]; hDlg
0x180052445  mov     r9d, 190h; cchMax
0x18005244b  mov     r8, r13; lpString
0x18005244e  mov     edx, 0AD1h; nIDDlgItem
0x180052453  call    cs:__imp_GetDlgItemTextW
0x180052459  mov     edx, 640h; uBytes
0x18005245e  mov     ecx, 40h ; '@'; uFlags
0x180052463  call    cs:__imp_LocalAlloc
0x180052469  xor     ecx, ecx
0x18005246b  mov     [rbp+57h+var_48], rax
0x18005246f  mov     [rbp+57h+pv], rax
0x180052473  mov     rsi, rax
0x180052476  test    rax, rax
0x180052479  jz      loc_180052613
0x18005247f  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x180052483  xor     r9d, r9d; unsigned __int16 *
0x180052486  mov     [rsp+0D0h+var_88], rcx; unsigned __int16 **
0x18005248b  mov     rdx, r13; unsigned __int16 *
0x18005248e  mov     [rsp+0D0h+var_90], rcx; unsigned __int16 *
0x180052493  mov     [rax], cx
0x180052496  mov     eax, cs:bDNisByLN
0x18005249c  mov     [rsp+0D0h+var_98], eax; int
0x1800524a0  lea     rax, [rbp+57h+pv]
0x1800524a4  mov     [rsp+0D0h+var_A0], 320h; unsigned int
0x1800524ac  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x1800524b1  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 *
0x1800524b6  mov     rcx, rbx; unsigned __int16 *
0x1800524b9  call    ?SetLocalizedDisplayName@@YAHPEAG0000PEAPEAGKH01@Z; SetLocalizedDisplayName(ushort *,ushort *,ushort *,ushort *,ushort *,ushort * *,ulong,int,ushort *,ushort * *)
0x1800524be  xor     r8d, r8d
0x1800524c1  test    eax, eax
0x1800524c3  jz      short loc_1800524FC
0x1800524c5  mov     rax, r15
0x1800524c8  inc     rax
0x1800524cb  cmp     [rsi+rax*2], r8w
0x1800524d0  jnz     short loc_1800524C8
0x1800524d2  test    rax, rax
0x1800524d5  jz      short loc_1800524FC
0x1800524d7  mov     rdx, r14; lpString2
0x1800524da  mov     rcx, rsi; lpString1
0x1800524dd  call    cs:__imp_lstrcmpW
0x1800524e3  xor     r8d, r8d; wParam
0x1800524e6  test    eax, eax
0x1800524e8  jz      short loc_1800524FC
0x1800524ea  mov     r9, rsi; lParam
0x1800524ed  mov     edx, r12d; Msg
0x1800524f0  mov     rcx, rdi; hWnd
0x1800524f3  call    cs:__imp_SendMessageW
0x1800524f9  xor     r8d, r8d
0x1800524fc  mov     eax, cs:bDNisByLN
0x180052502  lea     rdx, szResourceDNByLN
0x180052509  mov     [rsp+0D0h+var_88], r8; unsigned __int16 **
0x18005250e  lea     rcx, szResourceDNByCommaLN
0x180052515  test    eax, eax
0x180052517  cmovz   rcx, rdx
0x18005251b  xor     r9d, r9d; unsigned __int16 *
0x18005251e  mov     [rsp+0D0h+var_90], rcx; unsigned __int16 *
0x180052523  mov     rdx, r13; unsigned __int16 *
0x180052526  mov     [rsp+0D0h+var_98], eax; int
0x18005252a  mov     rcx, rbx; unsigned __int16 *
0x18005252d  lea     rax, [rbp+57h+pv]
0x180052531  mov     [rsp+0D0h+var_A0], 320h; unsigned int
0x180052539  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x18005253e  mov     [rsp+0D0h+var_B0], r8; unsigned __int16 *
0x180052543  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x180052547  call    ?SetLocalizedDisplayName@@YAHPEAG0000PEAPEAGKH01@Z; SetLocalizedDisplayName(ushort *,ushort *,ushort *,ushort *,ushort *,ushort * *,ulong,int,ushort *,ushort * *)
0x18005254c  xor     ecx, ecx
0x18005254e  test    eax, eax
0x180052550  jz      short loc_180052589
0x180052552  mov     rax, r15
0x180052555  inc     rax
0x180052558  cmp     [rsi+rax*2], cx
0x18005255c  jnz     short loc_180052555
0x18005255e  test    rax, rax
0x180052561  jz      short loc_180052589
0x180052563  mov     rdx, r14; lpString2
0x180052566  mov     rcx, rsi; lpString1
0x180052569  call    cs:__imp_lstrcmpW
0x18005256f  xor     ecx, ecx
0x180052571  test    eax, eax
0x180052573  jz      short loc_180052589
0x180052575  mov     r9, rsi; lParam
0x180052578  xor     r8d, r8d; wParam
0x18005257b  mov     edx, r12d; Msg
0x18005257e  mov     rcx, rdi; hWnd
0x180052581  call    cs:__imp_SendMessageW
0x180052587  xor     ecx, ecx
0x180052589  cmp     cs:bDNisByLN, ecx
0x18005258f  mov     eax, ecx
0x180052591  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x180052595  mov     rdx, r13; unsigned __int16 *
0x180052598  mov     [rsp+0D0h+var_88], rcx; unsigned __int16 **
0x18005259d  setz    al
0x1800525a0  mov     [rsp+0D0h+var_90], rcx; unsigned __int16 *
0x1800525a5  xor     r9d, r9d; unsigned __int16 *
0x1800525a8  mov     [rsp+0D0h+var_98], eax; int
0x1800525ac  lea     rax, [rbp+57h+pv]
0x1800525b0  mov     [rsp+0D0h+var_A0], 320h; unsigned int
0x1800525b8  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x1800525bd  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 *
0x1800525c2  mov     [rsi], cx
0x1800525c5  mov     rcx, rbx; unsigned __int16 *
0x1800525c8  call    ?SetLocalizedDisplayName@@YAHPEAG0000PEAPEAGKH01@Z; SetLocalizedDisplayName(ushort *,ushort *,ushort *,ushort *,ushort *,ushort * *,ulong,int,ushort *,ushort * *)
0x1800525cd  xor     r13d, r13d
0x1800525d0  test    eax, eax
0x1800525d2  jz      short loc_180052608
0x1800525d4  mov     rax, r15
0x1800525d7  inc     rax
0x1800525da  cmp     [rsi+rax*2], r13w
0x1800525df  jnz     short loc_1800525D7
0x1800525e1  test    rax, rax
0x1800525e4  jz      short loc_180052608
0x1800525e6  mov     rdx, r14; lpString2
0x1800525e9  mov     rcx, rsi; lpString1
0x1800525ec  call    cs:__imp_lstrcmpW
0x1800525f2  test    eax, eax
0x1800525f4  jz      short loc_180052608
0x1800525f6  mov     r9, rsi; lParam
0x1800525f9  xor     r8d, r8d; wParam
0x1800525fc  mov     edx, r12d; Msg
0x1800525ff  mov     rcx, rdi; hWnd
0x180052602  call    cs:__imp_SendMessageW
0x180052608  lea     rcx, [rbp+57h+var_48]; void **
0x18005260c  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x180052611  jmp     short loc_180052616
0x180052613  xor     r13d, r13d
0x180052616  mov     rcx, [rbp+57h+hDlg]; hDlg
0x18005261a  mov     r9d, 190h; cchMax
0x180052620  mov     r8, rbx; lpString
0x180052623  mov     [rbx], r13w
0x180052627  mov     edx, 0AD2h; nIDDlgItem
0x18005262c  call    cs:__imp_GetDlgItemTextW
0x180052632  mov     rcx, rbx; unsigned __int16 *
0x180052635  call    ?TrimSpaces@@YAHPEAG@Z; TrimSpaces(ushort *)
0x18005263a  mov     rax, r15
0x18005263d  inc     rax
0x180052640  cmp     [rbx+rax*2], r13w
0x180052645  jnz     short loc_18005263D
0x180052647  test    rax, rax
0x18005264a  jz      short loc_18005266E
0x18005264c  mov     rdx, r14; lpString2
0x18005264f  mov     rcx, rbx; lpString1
0x180052652  call    cs:__imp_lstrcmpW
0x180052658  test    eax, eax
0x18005265a  jz      short loc_18005266E
0x18005265c  mov     r9, rbx; lParam
0x18005265f  xor     r8d, r8d; wParam
0x180052662  mov     edx, r12d; Msg
0x180052665  mov     rcx, rdi; hWnd
0x180052668  call    cs:__imp_SendMessageW
0x18005266e  mov     rcx, [rbp+57h+var_68]
0x180052672  lea     rdx, [rbp+57h+pv]
0x180052676  mov     [rbx], r13w
0x18005267a  lea     r9, [rbp+57h+hDlg]
0x18005267e  mov     dword ptr [rbp+57h+hDlg], r13d
0x180052682  mov     esi, 3A16001Fh
0x180052687  mov     [rbp+57h+pv], r13
0x18005268b  mov     r8d, 80000000h
0x180052691  mov     rcx, [rcx+18h]
0x180052695  mov     dword ptr [rbp+57h+var_48], 1
0x18005269c  mov     dword ptr [rbp+57h+var_48+4], esi
0x18005269f  mov     [rsp+0D0h+var_B0], rdx
0x1800526a4  lea     rdx, [rbp+57h+var_48]
0x1800526a8  mov     rax, [rcx]
0x1800526ab  mov     rax, [rax+28h]
0x1800526af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526b4  mov     rcx, [rbp+57h+pv]
0x1800526b8  test    eax, eax
0x1800526ba  js      short loc_1800526D5
0x1800526bc  cmp     [rcx], esi
0x1800526be  jnz     short loc_1800526D5
0x1800526c0  mov     r8, [rcx+8]; unsigned __int16 *
0x1800526c4  mov     edx, 190h; unsigned __int64
0x1800526c9  mov     rcx, rbx; unsigned __int16 *
0x1800526cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800526d1  mov     rcx, [rbp+57h+pv]; pv
0x1800526d5  test    rcx, rcx
0x1800526d8  jz      short loc_1800526DF
0x1800526da  call    MAPIFreeBuffer
0x1800526df  mov     rcx, rbx; unsigned __int16 *
0x1800526e2  call    ?TrimSpaces@@YAHPEAG@Z; TrimSpaces(ushort *)
0x1800526e7  inc     r15
0x1800526ea  cmp     [rbx+r15*2], r13w
0x1800526ef  jnz     short loc_1800526E7
0x1800526f1  test    r15, r15
0x1800526f4  jz      short loc_180052718
0x1800526f6  mov     rdx, r14; lpString2
0x1800526f9  mov     rcx, rbx; lpString1
  ... truncated ...
```
