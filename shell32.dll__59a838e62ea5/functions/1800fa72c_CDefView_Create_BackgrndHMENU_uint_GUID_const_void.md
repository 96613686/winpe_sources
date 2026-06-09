# CDefView::_Create_BackgrndHMENU(uint,_GUID const &,void * *)

- ea: `0x1800fa72c`
- end: `0x1800faa6c`
- name: `?_Create_BackgrndHMENU@CDefView@@AEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `832`
- prototype: `__int64 __fastcall(CDefView *__hidden this, UINT uPosition, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fa434`
- `0x18013d640`

## callees

- `0x18000db34`
- `0x18000e01c`
- `0x180075dfc`
- `0x1800e7fb0`
- `0x1800fa72c`
- `0x1800fad08`
- `0x1801513c8`
- `0x1801e0ed8`
- `0x180233280`
- `0x1802342fc`
- `0x18041c658`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa8bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa90a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa8bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fa90a`
- `USER32!CheckMenuItem` at `0x1800fa975`
- `USER32!CheckMenuItem` at `0x1800fa975`
- `USER32!ModifyMenuW` at `0x1800fa8b6`
- `USER32!ModifyMenuW` at `0x1800fa901`
- `USER32!ModifyMenuW` at `0x1800fa8b6`
- `USER32!ModifyMenuW` at `0x1800fa901`
- `USER32!GetMenuItemInfoW` at `0x1800fa7ff`
- `USER32!GetMenuItemInfoW` at `0x1800faa00`
- `USER32!GetMenuItemInfoW` at `0x1800fa7ff`
- `USER32!GetMenuItemInfoW` at `0x1800faa00`
- `USER32!RemoveMenu` at `0x1800faa14`
- `USER32!RemoveMenu` at `0x1800faa14`
- `USER32!DeleteMenu` at `0x1800fa7cc`
- `USER32!DeleteMenu` at `0x1800fa81d`
- `USER32!DeleteMenu` at `0x1800fa82e`
- `USER32!DeleteMenu` at `0x1800fa83f`
- `USER32!DeleteMenu` at `0x1800fa850`
- `USER32!DeleteMenu` at `0x1800fa861`
- `USER32!DeleteMenu` at `0x1800fa9a6`
- `USER32!DeleteMenu` at `0x1800fa7cc`
- `USER32!DeleteMenu` at `0x1800fa81d`
- `USER32!DeleteMenu` at `0x1800fa82e`
- `USER32!DeleteMenu` at `0x1800fa83f`
- `USER32!DeleteMenu` at `0x1800fa850`
- `USER32!DeleteMenu` at `0x1800fa861`
- `USER32!DeleteMenu` at `0x1800fa9a6`
- `USER32!DestroyMenu` at `0x1800fa99e`
- `USER32!DestroyMenu` at `0x1800faa1e`
- `USER32!DestroyMenu` at `0x1800fa99e`
- `USER32!DestroyMenu` at `0x1800faa1e`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x1800fa92f`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x1800fa92f`
- `Windows.Storage!Shell_MergeMenus` at `0x1800fa995`
- `Windows.Storage!Shell_MergeMenus` at `0x1800fa995`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x1800fa958`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x1800fa958`
- `Windows.Storage!__imp_SHRestricted` at `0x1800fa915`
- `Windows.Storage!__imp_SHRestricted` at `0x1800fa915`

## pseudocode

```c
__int64 __fastcall CDefView::_Create_BackgrndHMENU(CDefView *this, UINT uPosition, const struct _GUID *a3, void **a4)
{
  unsigned int v7; // ebx
  HMENU hSubMenu; // rsi
  void *v9; // rbx
  void *v10; // rbx
  HMENU v11; // rbx
  __int64 v12; // rax
  const struct _GUID *v13; // r9
  HMENU v14; // rbx
  int lpNewItem; // [rsp+20h] [rbp-69h]
  HMENU hMenu[2]; // [rsp+30h] [rbp-59h] BYREF
  struct tagMENUITEMINFOW mii; // [rsp+40h] [rbp-49h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v19; // [rsp+90h] [rbp+7h] BYREF

  *a4 = 0;
  v7 = -2147024882;
  hMenu[0] = SHLoadPopupMenu(g_hinst, 0xD7u);
  if ( hMenu[0] )
  {
    Def_InitEditCommands(0, hMenu[0], 28672, *((_QWORD *)this + 100));
    if ( (*((_DWORD *)this + 222) & 0x10000000) != 0 )
    {
      DeleteMenu(hMenu[0], 0x7033u, 0);
      mii.cbSize = 80;
      mii.fMask = 4;
      memset_0(&mii.fType, 0, 0x48u);
      GetMenuItemInfoW(hMenu[0], 0x7002u, 0, &mii);
      hSubMenu = mii.hSubMenu;
      if ( mii.hSubMenu )
      {
        DeleteMenu(mii.hSubMenu, 0x704Bu, 0);
        DeleteMenu(hSubMenu, 0x704Cu, 0);
        DeleteMenu(hSubMenu, 0x704Du, 0);
        DeleteMenu(hSubMenu, 0x7051u, 0);
        DeleteMenu(hSubMenu, 0x7052u, 0);
        CDefView::_CheckCurrentViewMenuItem(this, hSubMenu);
        *(_QWORD *)&v19 = 0;
        if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hinst, 1, &v19) >= 0 )
        {
          v9 = (void *)v19;
          ModifyMenuW(hSubMenu, 0x7071u, 0, 0x7071u, *(LPCWSTR *)&v19);
          LocalFree(v9);
        }
        if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hinst, lpNewItem, &v19) >= 0 )
        {
          v10 = (void *)v19;
          ModifyMenuW(hSubMenu, 0x7074u, 0, 0x7074u, *(LPCWSTR *)&v19);
          LocalFree(v10);
        }
        if ( !SHRestricted(REST_CLASSICSHELL) )
        {
          v11 = (HMENU)SHLoadMenuPopup(g_hinst, 218);
          if ( v11 )
          {
            memset(&v19, 0, sizeof(v19));
            SHGetSetSettings(&v19, 0x4000u, 0);
            if ( (*(_WORD *)&v19 & 0x1000) == 0 )
              CheckMenuItem(v11, 0x7402u, 8u);
            Shell_MergeMenus(hSubMenu, v11, 0xFFFFFFFF, 0, 0xFFFFFFFF, 3u);
            DestroyMenu(v11);
          }
        }
      }
    }
    else
    {
      DeleteMenu(hMenu[0], 0x7033u, 0);
      v12 = _lambda_24bd8fc070818ccaf49523ad64560b1b_::_lambda_24bd8fc070818ccaf49523ad64560b1b_(&v19, hMenu, this);
      lambda_16c53df8719282c89666fc44e0c1c168_::operator()(v12);
    }
    CDefView::_InitViewMenu(this, hMenu[0]);
    if ( uPosition )
    {
      mii.cbSize = 80;
      mii.fMask = 4;
      memset_0(&mii.fType, 0, 0x48u);
      GetMenuItemInfoW(hMenu[0], uPosition, 0, &mii);
      v14 = mii.hSubMenu;
      RemoveMenu(hMenu[0], uPosition, 0);
      DestroyMenu(hMenu[0]);
      hMenu[0] = v14;
    }
    else
    {
      v14 = hMenu[0];
    }
    return (unsigned int)Create_CDVBackgroundHMENU(v14, *((HWND *)this + 90), this, v13, a4);
  }
  return v7;
}

```

## disassembly

```asm
0x1800fa72c  mov     [rsp-8+arg_10], rbx
0x1800fa731  push    rbp
0x1800fa732  push    rsi
0x1800fa733  push    rdi
0x1800fa734  push    r14
0x1800fa736  push    r15
0x1800fa738  lea     rbp, [rsp-37h]
0x1800fa73d  sub     rsp, 0C0h
0x1800fa744  mov     rax, cs:__security_cookie
0x1800fa74b  xor     rax, rsp
0x1800fa74e  mov     [rbp+57h+var_30], rax
0x1800fa752  mov     r14d, edx
0x1800fa755  mov     qword ptr [r9], 0
0x1800fa75c  mov     rdi, rcx
0x1800fa75f  mov     edx, 0D7h; unsigned int
0x1800fa764  mov     rcx, cs:g_hinst; HINSTANCE
0x1800fa76b  mov     r15, r9
0x1800fa76e  mov     ebx, 8007000Eh
0x1800fa773  call    ?SHLoadPopupMenu@@YAPEAUHMENU__@@PEAUHINSTANCE__@@I@Z; SHLoadPopupMenu(HINSTANCE__ *,uint)
0x1800fa778  mov     [rbp+57h+hMenu], rax
0x1800fa77c  mov     rdx, rax
0x1800fa77f  test    rax, rax
0x1800fa782  jz      loc_1800FAA47
0x1800fa788  mov     rax, [rdi+280h]
0x1800fa78f  xor     ecx, ecx
0x1800fa791  mov     r9, [rdi+320h]
0x1800fa798  mov     r8d, 7000h
0x1800fa79e  mov     qword ptr [rsp+0E0h+uFlags], rax
0x1800fa7a3  mov     dword ptr [rsp+0E0h+lpNewItem], 1; int
0x1800fa7ab  call    Def_InitEditCommands
0x1800fa7b0  mov     rcx, [rbp+57h+hMenu]; hMenu
0x1800fa7b4  xor     r8d, r8d; uFlags
0x1800fa7b7  test    dword ptr [rdi+378h], 10000000h
0x1800fa7c1  mov     edx, 7033h; uPosition
0x1800fa7c6  jz      loc_1800FA9A6
0x1800fa7cc  call    cs:__imp_DeleteMenu
0x1800fa7d2  xor     edx, edx; Val
0x1800fa7d4  mov     [rbp+57h+mii.cbSize], 50h ; 'P'
0x1800fa7db  lea     rcx, [rbp+57h+mii.fType]; void *
0x1800fa7df  mov     [rbp+57h+mii.fMask], 4
0x1800fa7e6  lea     r8d, [rdx+48h]; Size
0x1800fa7ea  call    memset_0
0x1800fa7ef  mov     rcx, [rbp+57h+hMenu]; hmenu
0x1800fa7f3  lea     r9, [rbp+57h+mii]; lpmii
0x1800fa7f7  xor     r8d, r8d; fByPosition
0x1800fa7fa  mov     edx, 7002h; item
0x1800fa7ff  call    cs:__imp_GetMenuItemInfoW
0x1800fa805  mov     rsi, [rbp+57h+mii.hSubMenu]
0x1800fa809  test    rsi, rsi
0x1800fa80c  jz      loc_1800FA9C4
0x1800fa812  xor     r8d, r8d; uFlags
0x1800fa815  mov     edx, 704Bh; uPosition
0x1800fa81a  mov     rcx, rsi; hMenu
0x1800fa81d  call    cs:__imp_DeleteMenu
0x1800fa823  xor     r8d, r8d; uFlags
0x1800fa826  mov     edx, 704Ch; uPosition
0x1800fa82b  mov     rcx, rsi; hMenu
0x1800fa82e  call    cs:__imp_DeleteMenu
0x1800fa834  xor     r8d, r8d; uFlags
0x1800fa837  mov     edx, 704Dh; uPosition
0x1800fa83c  mov     rcx, rsi; hMenu
0x1800fa83f  call    cs:__imp_DeleteMenu
0x1800fa845  xor     r8d, r8d; uFlags
0x1800fa848  mov     edx, 7051h; uPosition
0x1800fa84d  mov     rcx, rsi; hMenu
0x1800fa850  call    cs:__imp_DeleteMenu
0x1800fa856  xor     r8d, r8d; uFlags
0x1800fa859  mov     edx, 7052h; uPosition
0x1800fa85e  mov     rcx, rsi; hMenu
0x1800fa861  call    cs:__imp_DeleteMenu
0x1800fa867  mov     rdx, rsi; hmenu
0x1800fa86a  mov     rcx, rdi; this
0x1800fa86d  call    ?_CheckCurrentViewMenuItem@CDefView@@AEAAIPEAUHMENU__@@@Z; CDefView::_CheckCurrentViewMenuItem(HMENU__ *)
0x1800fa872  mov     rcx, cs:g_hinst; hModule
0x1800fa879  lea     rax, [rbp+57h+var_50]
0x1800fa87d  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x1800fa884  mov     qword ptr [rsp+0E0h+uFlags], rax; void *
0x1800fa889  mov     edx, 79B5h
0x1800fa88e  mov     [rbp+57h+var_50], 0
0x1800fa896  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800fa89b  test    eax, eax
0x1800fa89d  js      short loc_1800FA8C5
0x1800fa89f  mov     rbx, [rbp+57h+var_50]
0x1800fa8a3  mov     edx, 7071h; uPosition
0x1800fa8a8  mov     r9d, edx; uIDNewItem
0x1800fa8ab  mov     [rsp+0E0h+lpNewItem], rbx; int
0x1800fa8b0  xor     r8d, r8d; uFlags
0x1800fa8b3  mov     rcx, rsi; hMnu
0x1800fa8b6  call    cs:__imp_ModifyMenuW
0x1800fa8bc  mov     rcx, rbx; hMem
0x1800fa8bf  call    cs:__imp_LocalFree
0x1800fa8c5  mov     rcx, cs:g_hinst; hModule
0x1800fa8cc  lea     rax, [rbp+57h+var_50]
0x1800fa8d0  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x1800fa8d7  mov     qword ptr [rsp+0E0h+uFlags], rax; void *
0x1800fa8dc  mov     edx, 79B6h
0x1800fa8e1  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800fa8e6  test    eax, eax
0x1800fa8e8  js      short loc_1800FA910
0x1800fa8ea  mov     rbx, [rbp+57h+var_50]
0x1800fa8ee  mov     edx, 7074h; uPosition
0x1800fa8f3  mov     r9d, edx; uIDNewItem
0x1800fa8f6  mov     [rsp+0E0h+lpNewItem], rbx; lpNewItem
0x1800fa8fb  xor     r8d, r8d; uFlags
0x1800fa8fe  mov     rcx, rsi; hMnu
0x1800fa901  call    cs:__imp_ModifyMenuW
0x1800fa907  mov     rcx, rbx; hMem
0x1800fa90a  call    cs:__imp_LocalFree
0x1800fa910  mov     ecx, 40000008h; rest
0x1800fa915  call    cs:__imp_SHRestricted
0x1800fa91b  test    eax, eax
0x1800fa91d  jnz     loc_1800FA9C4
0x1800fa923  mov     rcx, cs:g_hinst
0x1800fa92a  mov     edx, 0DAh
0x1800fa92f  call    cs:__imp_SHLoadMenuPopup
0x1800fa935  mov     rbx, rax
0x1800fa938  test    rax, rax
0x1800fa93b  jz      loc_1800FA9C4
0x1800fa941  xorps   xmm0, xmm0
0x1800fa944  lea     rcx, [rbp+57h+var_50]; lpss
0x1800fa948  xor     r8d, r8d; bSet
0x1800fa94b  mov     edx, 4000h; dwMask
0x1800fa950  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800fa954  movups  [rbp+57h+var_40], xmm0
0x1800fa958  call    cs:__imp_SHGetSetSettings
0x1800fa95e  test    dword ptr [rbp+57h+var_50], 1000h
0x1800fa965  jnz     short loc_1800FA97B
0x1800fa967  mov     edx, 7402h; uIDCheckItem
0x1800fa96c  mov     r8d, 8; uCheck
0x1800fa972  mov     rcx, rbx; hMenu
0x1800fa975  call    cs:__imp_CheckMenuItem
0x1800fa97b  or      r8d, 0FFFFFFFFh; uInsert
0x1800fa97f  mov     [rsp+0E0h+uFlags], 3; uFlags
0x1800fa987  xor     r9d, r9d; uIDAdjust
0x1800fa98a  mov     dword ptr [rsp+0E0h+lpNewItem], r8d; uIDAdjustMax
0x1800fa98f  mov     rdx, rbx; hmSrc
0x1800fa992  mov     rcx, rsi; hmDst
0x1800fa995  call    cs:__imp_Shell_MergeMenus
0x1800fa99b  mov     rcx, rbx; hMenu
0x1800fa99e  call    cs:__imp_DestroyMenu
0x1800fa9a4  jmp     short loc_1800FA9C4
0x1800fa9a6  call    cs:__imp_DeleteMenu
0x1800fa9ac  mov     r8, rdi
0x1800fa9af  lea     rdx, [rbp+57h+hMenu]
0x1800fa9b3  lea     rcx, [rbp+57h+var_50]
0x1800fa9b7  call    ??0_lambda_24bd8fc070818ccaf49523ad64560b1b_@@QEAA@AEBUhstring@winrt@@PEBU?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@2@@Z; _lambda_24bd8fc070818ccaf49523ad64560b1b_::_lambda_24bd8fc070818ccaf49523ad64560b1b_(winrt::hstring const &,winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version> const *)
0x1800fa9bc  mov     rcx, rax
0x1800fa9bf  call    _lambda_16c53df8719282c89666fc44e0c1c168___operator__
0x1800fa9c4  mov     rdx, [rbp+57h+hMenu]; hMenu
0x1800fa9c8  mov     rcx, rdi; this
0x1800fa9cb  call    ?_InitViewMenu@CDefView@@AEAAXPEAUHMENU__@@@Z; CDefView::_InitViewMenu(HMENU__ *)
0x1800fa9d0  test    r14d, r14d
0x1800fa9d3  jz      short loc_1800FAA2A
0x1800fa9d5  xor     edx, edx; Val
0x1800fa9d7  mov     [rbp+57h+mii.cbSize], 50h ; 'P'
0x1800fa9de  lea     rcx, [rbp+57h+mii.fType]; void *
0x1800fa9e2  mov     [rbp+57h+mii.fMask], 4
0x1800fa9e9  lea     r8d, [rdx+48h]; Size
0x1800fa9ed  call    memset_0
0x1800fa9f2  mov     rcx, [rbp+57h+hMenu]; hmenu
0x1800fa9f6  lea     r9, [rbp+57h+mii]; lpmii
0x1800fa9fa  xor     r8d, r8d; fByPosition
0x1800fa9fd  mov     edx, r14d; item
0x1800faa00  call    cs:__imp_GetMenuItemInfoW
0x1800faa06  mov     rcx, [rbp+57h+hMenu]; hMenu
0x1800faa0a  xor     r8d, r8d; uFlags
0x1800faa0d  mov     rbx, [rbp+57h+mii.hSubMenu]
0x1800faa11  mov     edx, r14d; uPosition
0x1800faa14  call    cs:__imp_RemoveMenu
0x1800faa1a  mov     rcx, [rbp+57h+hMenu]; hMenu
0x1800faa1e  call    cs:__imp_DestroyMenu
0x1800faa24  mov     [rbp+57h+hMenu], rbx
0x1800faa28  jmp     short loc_1800FAA2E
0x1800faa2a  mov     rbx, [rbp+57h+hMenu]
0x1800faa2e  mov     rdx, [rdi+2D0h]; HWND
0x1800faa35  mov     r8, rdi; struct CDefView *
0x1800faa38  mov     rcx, rbx; HMENU
0x1800faa3b  mov     [rsp+0E0h+lpNewItem], r15; void **
0x1800faa40  call    ?Create_CDVBackgroundHMENU@@YAJPEAUHMENU__@@PEAUHWND__@@PEAVCDefView@@AEBU_GUID@@PEAPEAX@Z; Create_CDVBackgroundHMENU(HMENU__ *,HWND__ *,CDefView *,_GUID const &,void * *)
0x1800faa45  mov     ebx, eax
0x1800faa47  mov     eax, ebx
0x1800faa49  mov     rcx, [rbp+57h+var_30]
0x1800faa4d  xor     rcx, rsp; StackCookie
0x1800faa50  call    __security_check_cookie
0x1800faa55  mov     rbx, [rsp+0E0h+arg_10]
0x1800faa5d  add     rsp, 0C0h
0x1800faa64  pop     r15
0x1800faa66  pop     r14
0x1800faa68  pop     rdi
0x1800faa69  pop     rsi
0x1800faa6a  pop     rbp
0x1800faa6b  retn
```
