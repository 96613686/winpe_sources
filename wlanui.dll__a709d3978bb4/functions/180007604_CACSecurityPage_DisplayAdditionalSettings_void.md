# CACSecurityPage::DisplayAdditionalSettings(void)

- ea: `0x180007604`
- end: `0x1800078ee`
- name: `?DisplayAdditionalSettings@CACSecurityPage@@AEAAJXZ`
- size: `746`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x1800011d0`
- `0x1800060a0`
- `0x1800068e8`
- `0x180007604`
- `0x18000833c`
- `0x180008388`
- `0x18000901c`
- `0x180014e90`
- `0x18001bf0a`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800078a0`
- `KERNEL32!GetLastError` at `0x1800078a0`
- `USER32!GetDlgItem` at `0x18000769a`
- `USER32!GetDlgItem` at `0x1800076be`
- `USER32!GetDlgItem` at `0x18000769a`
- `USER32!GetDlgItem` at `0x1800076be`
- `USER32!SendMessageW` at `0x1800076ae`
- `USER32!SendMessageW` at `0x1800076ae`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::DisplayAdditionalSettings(CACSecurityPage *this)
{
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rdi
  struct _AUI_CIPHER_INFO *CurrentlySelectedCipher; // r14
  HWND DlgItem; // rax
  int v5; // ebx
  HWND v6; // rax
  void *ItemDataPtr; // rax
  __int64 v8; // r8
  const unsigned __int16 *v9; // r9
  const WCHAR *v10; // rbx
  void *v11; // r15
  UINT v12; // r14d
  _QWORD *v13; // rax
  __int64 v14; // r11
  int v15; // r10d
  __int64 v16; // rcx
  int v17; // edx
  unsigned int v18; // edi
  int v19; // ecx
  _QWORD *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // ecx
  struct _PSP *Page; // rax
  signed int LastError; // eax
  const unsigned __int16 *v27; // [rsp+20h] [rbp-69h]
  const unsigned __int16 *v28; // [rsp+28h] [rbp-61h]
  HINSTANCE v29; // [rsp+30h] [rbp-59h]
  unsigned int (*v30)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+38h] [rbp-51h]
  __int128 v31; // [rsp+40h] [rbp-49h] BYREF
  PROPSHEETHEADERW_V2 v32; // [rsp+50h] [rbp-39h] BYREF
  __int64 v33; // [rsp+F8h] [rbp+6Fh] BYREF

  memset_0(&v32, 0, sizeof(v32));
  v31 = 0;
  v33 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  memset_0(&v32, 0, sizeof(v32));
  *(_QWORD *)&v31 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
    &v33,
    17320);
  CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth(this);
  CurrentlySelectedCipher = CACSecurityPage::GetCurrentlySelectedCipher(this);
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1119);
  v5 = SendMessageW(DlgItem, 0x147u, 0, 0);
  v6 = GetDlgItem(*((HWND *)this + 1), 1119);
  ItemDataPtr = ComboBox_GetItemDataPtr(v6, v5);
  v10 = (const WCHAR *)v33;
  v11 = ItemDataPtr;
  if ( !CurrentlySelectedAuth || !CurrentlySelectedCipher )
  {
    v18 = -2147467261;
    goto LABEL_24;
  }
  v12 = 0;
  if ( *((_DWORD *)CurrentlySelectedAuth + 2) )
  {
    v13 = (_QWORD *)*((_QWORD *)this + 169);
    if ( !v13 )
    {
      v13 = operator new(0x68u);
      if ( v13 )
      {
        v14 = *((_QWORD *)this + 156);
        v15 = *((_DWORD *)this + 311);
        v9 = (const unsigned __int16 *)*((_QWORD *)this + 2);
        v8 = *((_QWORD *)this + 5);
        v16 = *((_QWORD *)this + 1);
        v17 = *((_DWORD *)this + 23);
        v13[1] = 0;
        *v13 = &CACDot1XPage::`vftable';
        *((_DWORD *)v13 + 10) = 1;
        *(_QWORD *)((char *)v13 + 60) = 1;
        v13[6] = v16;
        *((_DWORD *)v13 + 14) = v17;
        v13[9] = v8;
        v13[2] = 0;
        v13[3] = 0;
        v13[4] = v9;
        *((_DWORD *)v13 + 20) = v15;
        v13[12] = v14;
      }
      *((_QWORD *)this + 169) = v13;
      if ( !v13 )
        goto LABEL_8;
    }
    v13[11] = v11;
    *(_QWORD *)&v31 = CPropSheetPage::CreatePage(*((CPropSheetPage **)this + 169), 0x69u, v8, v9, v27, v28, v29, v30);
    if ( !(_QWORD)v31 )
      goto LABEL_8;
    v12 = 1;
  }
  v19 = *((_DWORD *)CurrentlySelectedAuth + 1);
  if ( (unsigned int)(v19 - 6) <= 3 || v19 == 11 )
  {
    v20 = (_QWORD *)*((_QWORD *)this + 168);
    if ( v20 )
      goto LABEL_29;
    v20 = operator new(0x108u);
    if ( v20 )
    {
      v21 = *((_QWORD *)this + 5);
      v9 = (const unsigned __int16 *)&CACDot11Page::`vftable';
      v22 = *((_QWORD *)this + 1);
      v23 = *((_DWORD *)this + 23);
      *v20 = &CACDot11Page::`vftable';
      v20[3] = v22;
      v20[5] = v21;
      v20[1] = 0;
      *((_DWORD *)v20 + 4) = 1;
      *((_DWORD *)v20 + 8) = v23;
      v20[31] = 0;
      v20[32] = this;
      v20[7] = 0;
    }
    else
    {
      v20 = 0;
    }
    *((_QWORD *)this + 168) = v20;
    if ( v20 )
    {
LABEL_29:
      Page = CPropSheetPage::CreatePage((CPropSheetPage *)v20, 0x68u, (unsigned int)v20, v9, v27, v28, v29, v30);
      *((_QWORD *)&v31 + v12) = Page;
      if ( Page )
      {
        ++v12;
        goto LABEL_20;
      }
    }
LABEL_8:
    v18 = -2147024882;
    goto LABEL_24;
  }
LABEL_20:
  v32.hwndParent = (HWND)*((_QWORD *)this + 1);
  v18 = 0;
  v32.hInstance = hInstance;
  v32.ppsp = (LPCPROPSHEETPAGEW)&v31;
  v32.dwSize = 72;
  v32.dwFlags = 33554560;
  v32.nPages = v12;
  v32.pszCaption = v10;
  if ( (unsigned int)PropertySheetW(&v32) == -1 )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_24:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  return v18;
}

```

## disassembly

```asm
0x180007604  push    rbp
0x180007606  push    rbx
0x180007607  push    rsi
0x180007608  push    rdi
0x180007609  push    r14
0x18000760b  push    r15
0x18000760d  lea     rbp, [rsp-2Fh]
0x180007612  sub     rsp, 0B8h
0x180007619  mov     rsi, rcx
0x18000761c  mov     ebx, 60h ; '`'
0x180007621  mov     r8d, ebx; Size
0x180007624  lea     rcx, [rbp+57h+var_90]; void *
0x180007628  xor     edx, edx; Val
0x18000762a  call    memset_0
0x18000762f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007636  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000763d  xorps   xmm0, xmm0
0x180007640  movups  [rbp+57h+var_A0], xmm0
0x180007644  mov     rax, [rax+18h]
0x180007648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000764d  add     rax, 18h
0x180007651  lea     rcx, [rbp+57h+var_90]; void *
0x180007655  mov     r8d, ebx; Size
0x180007658  mov     [rbp+57h+arg_8], rax
0x18000765c  xor     edx, edx; Val
0x18000765e  call    memset_0
0x180007663  xor     eax, eax
0x180007665  lea     rcx, [rbp+57h+arg_8]
0x180007669  mov     edx, 43A8h
0x18000766e  mov     qword ptr [rbp+57h+var_A0], rax
0x180007672  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180007677  mov     rcx, rsi; this
0x18000767a  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000767f  mov     rcx, rsi; this
0x180007682  mov     rdi, rax
0x180007685  call    ?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedCipher(void)
0x18000768a  mov     rcx, [rsi+8]; hDlg
0x18000768e  mov     r15d, 45Fh
0x180007694  mov     edx, r15d; nIDDlgItem
0x180007697  mov     r14, rax
0x18000769a  call    cs:__imp_GetDlgItem
0x1800076a0  xor     r9d, r9d; lParam
0x1800076a3  xor     r8d, r8d; wParam
0x1800076a6  mov     rcx, rax; hWnd
0x1800076a9  mov     edx, 147h; Msg
0x1800076ae  call    cs:__imp_SendMessageW
0x1800076b4  mov     rcx, [rsi+8]; hDlg
0x1800076b8  mov     edx, r15d; nIDDlgItem
0x1800076bb  mov     rbx, rax
0x1800076be  call    cs:__imp_GetDlgItem
0x1800076c4  mov     rcx, rax; HWND
0x1800076c7  mov     edx, ebx; int
0x1800076c9  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x1800076ce  mov     rbx, [rbp+57h+arg_8]
0x1800076d2  mov     r15, rax
0x1800076d5  test    rdi, rdi
0x1800076d8  jz      loc_1800078B7
0x1800076de  test    r14, r14
0x1800076e1  jz      loc_1800078B7
0x1800076e7  xor     r14d, r14d
0x1800076ea  cmp     [rdi+8], r14d
0x1800076ee  jz      loc_1800077AC
0x1800076f4  mov     rax, [rsi+548h]
0x1800076fb  test    rax, rax
0x1800076fe  jnz     loc_180007788
0x180007704  lea     ecx, [rax+68h]; Size
0x180007707  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000770c  test    rax, rax
0x18000770f  jz      short loc_180007772
0x180007711  mov     r11, [rsi+4E0h]
0x180007718  mov     r10d, [rsi+4DCh]
0x18000771f  mov     r9, [rsi+10h]
0x180007723  mov     r8, [rsi+28h]
0x180007727  mov     rcx, [rsi+8]
0x18000772b  mov     edx, [rsi+5Ch]
0x18000772e  mov     [rax+8], r14
0x180007732  lea     r14, ??_7CACDot1XPage@@6B@; const CACDot1XPage::`vftable'
0x180007739  mov     [rax], r14
0x18000773c  mov     dword ptr [rax+28h], 1
0x180007743  mov     qword ptr [rax+3Ch], 1
0x18000774b  mov     [rax+30h], rcx
0x18000774f  mov     [rax+38h], edx
0x180007752  mov     [rax+48h], r8
0x180007756  mov     qword ptr [rax+10h], 0
0x18000775e  mov     qword ptr [rax+18h], 0
0x180007766  mov     [rax+20h], r9
0x18000776a  mov     [rax+50h], r10d
0x18000776e  mov     [rax+60h], r11
0x180007772  mov     [rsi+548h], rax
0x180007779  test    rax, rax
0x18000777c  jnz     short loc_180007788
0x18000777e  mov     edi, 8007000Eh
0x180007783  jmp     loc_1800078BC
0x180007788  mov     [rax+58h], r15
0x18000778c  mov     edx, 69h ; 'i'; unsigned int
0x180007791  mov     rcx, [rsi+548h]; this
0x180007798  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@P6AIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *,uint (*)(HWND__ *,uint,_PROPSHEETPAGEW *))
0x18000779d  mov     qword ptr [rbp+57h+var_A0], rax
0x1800077a1  test    rax, rax
0x1800077a4  jz      short loc_18000777E
0x1800077a6  mov     r14d, 1
0x1800077ac  mov     ecx, [rdi+4]
0x1800077af  lea     eax, [rcx-6]
0x1800077b2  cmp     eax, 3
0x1800077b5  jbe     short loc_1800077C0
0x1800077b7  cmp     ecx, 0Bh
0x1800077ba  jnz     loc_18000785F
0x1800077c0  mov     r8, [rsi+540h]
0x1800077c7  test    r8, r8
0x1800077ca  jnz     short loc_18000783E
0x1800077cc  mov     ecx, 108h; Size
0x1800077d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077d6  mov     r8, rax
0x1800077d9  test    rax, rax
0x1800077dc  jz      short loc_18000782B
0x1800077de  mov     rdx, [rsi+28h]
0x1800077e2  lea     r9, ??_7CACDot11Page@@6B@; const CACDot11Page::`vftable'
0x1800077e9  mov     rax, [rsi+8]
0x1800077ed  mov     ecx, [rsi+5Ch]
0x1800077f0  mov     [r8], r9
0x1800077f3  mov     [r8+18h], rax
0x1800077f7  mov     [r8+28h], rdx
0x1800077fb  mov     qword ptr [r8+8], 0
0x180007803  mov     dword ptr [r8+10h], 1
0x18000780b  mov     [r8+20h], ecx
0x18000780f  mov     qword ptr [r8+0F8h], 0
0x18000781a  mov     [r8+100h], rsi
0x180007821  mov     qword ptr [r8+38h], 0
0x180007829  jmp     short loc_18000782E
0x18000782b  xor     r8d, r8d; unsigned int
0x18000782e  mov     [rsi+540h], r8
0x180007835  test    r8, r8
0x180007838  jz      loc_18000777E
0x18000783e  mov     edx, 68h ; 'h'; unsigned int
0x180007843  mov     rcx, r8; this
0x180007846  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@P6AIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *,uint (*)(HWND__ *,uint,_PROPSHEETPAGEW *))
0x18000784b  mov     ecx, r14d
0x18000784e  mov     qword ptr [rbp+rcx*8+57h+var_A0], rax
0x180007853  test    rax, rax
0x180007856  jz      loc_18000777E
0x18000785c  inc     r14d
0x18000785f  mov     rax, [rsi+8]
0x180007863  lea     rcx, [rbp+57h+var_90]; LPCPROPSHEETHEADERW
0x180007867  mov     [rbp+57h+var_90.hwndParent], rax
0x18000786b  xor     edi, edi
0x18000786d  mov     rax, cs:hInstance
0x180007874  mov     [rbp+57h+var_90.hInstance], rax
0x180007878  lea     rax, [rbp+57h+var_A0]
0x18000787c  mov     qword ptr [rbp+57h+var_90.38h], rax
0x180007880  mov     [rbp+57h+var_90.dwSize], 48h ; 'H'
0x180007887  mov     [rbp+57h+var_90.dwFlags], 2000080h
0x18000788e  mov     [rbp+57h+var_90.nPages], r14d
0x180007892  mov     [rbp+57h+var_90.pszCaption], rbx
0x180007896  call    PropertySheetW
0x18000789b  cmp     eax, 0FFFFFFFFh
0x18000789e  jnz     short loc_1800078BC
0x1800078a0  call    cs:__imp_GetLastError
0x1800078a6  mov     edi, eax
0x1800078a8  test    eax, eax
0x1800078aa  jle     short loc_1800078BC
0x1800078ac  movzx   edi, ax
0x1800078af  or      edi, 80070000h
0x1800078b5  jmp     short loc_1800078BC
0x1800078b7  mov     edi, 80004003h
0x1800078bc  lea     rdx, [rbx-18h]
0x1800078c0  or      ecx, 0FFFFFFFFh
0x1800078c3  lock xadd [rdx+10h], ecx
0x1800078c8  sub     ecx, 1
0x1800078cb  jg      short loc_1800078DC
0x1800078cd  mov     rcx, [rdx]
0x1800078d0  mov     r8, [rcx]
0x1800078d3  mov     rax, [r8+8]
0x1800078d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078dc  mov     eax, edi
0x1800078de  add     rsp, 0B8h
0x1800078e5  pop     r15
0x1800078e7  pop     r14
0x1800078e9  pop     rdi
0x1800078ea  pop     rsi
0x1800078eb  pop     rbx
0x1800078ec  pop     rbp
0x1800078ed  retn
```
