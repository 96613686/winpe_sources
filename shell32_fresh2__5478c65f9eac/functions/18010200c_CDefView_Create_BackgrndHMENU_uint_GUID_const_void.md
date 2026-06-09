# CDefView::_Create_BackgrndHMENU(uint,_GUID const &,void * *)

- ea: `0x18010200c`
- end: `0x1801023cb`
- name: `?_Create_BackgrndHMENU@CDefView@@AEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `959`
- prototype: `__int64 __fastcall(CDefView *__hidden this, UINT uPosition, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180101ce8`
- `0x18014dd74`

## callees

- `0x18000de54`
- `0x18000e38c`
- `0x18002857c`
- `0x180057334`
- `0x1800e8e90`
- `0x18010200c`
- `0x1801613dc`
- `0x1801f8b54`
- `0x180249490`
- `0x18024a53c`
- `0x18044bf80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801021cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102226`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801021cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102226`
- `USER32!CheckMenuItem` at `0x1801022a9`
- `USER32!CheckMenuItem` at `0x1801022a9`
- `USER32!ModifyMenuW` at `0x1801021c0`
- `USER32!ModifyMenuW` at `0x180102217`
- `USER32!ModifyMenuW` at `0x1801021c0`
- `USER32!ModifyMenuW` at `0x180102217`
- `USER32!GetMenuItemInfoW` at `0x1801020e5`
- `USER32!GetMenuItemInfoW` at `0x18010234c`
- `USER32!GetMenuItemInfoW` at `0x1801020e5`
- `USER32!GetMenuItemInfoW` at `0x18010234c`
- `USER32!RemoveMenu` at `0x180102366`
- `USER32!RemoveMenu` at `0x180102366`
- `USER32!DeleteMenu` at `0x1801020ac`
- `USER32!DeleteMenu` at `0x180102109`
- `USER32!DeleteMenu` at `0x180102120`
- `USER32!DeleteMenu` at `0x180102137`
- `USER32!DeleteMenu` at `0x18010214e`
- `USER32!DeleteMenu` at `0x180102165`
- `USER32!DeleteMenu` at `0x1801022ec`
- `USER32!DeleteMenu` at `0x1801020ac`
- `USER32!DeleteMenu` at `0x180102109`
- `USER32!DeleteMenu` at `0x180102120`
- `USER32!DeleteMenu` at `0x180102137`
- `USER32!DeleteMenu` at `0x18010214e`
- `USER32!DeleteMenu` at `0x180102165`
- `USER32!DeleteMenu` at `0x1801022ec`
- `USER32!DestroyMenu` at `0x1801022de`
- `USER32!DestroyMenu` at `0x180102376`
- `USER32!DestroyMenu` at `0x1801022de`
- `USER32!DestroyMenu` at `0x180102376`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x180102257`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x180102257`
- `Windows.Storage!Shell_MergeMenus` at `0x1801022cf`
- `Windows.Storage!Shell_MergeMenus` at `0x1801022cf`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x180102286`
- `Windows.Storage!__imp_SHGetSetSettings` at `0x180102286`
- `Windows.Storage!__imp_SHRestricted` at `0x180102237`
- `Windows.Storage!__imp_SHRestricted` at `0x180102237`

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
0x18010200c  mov     [rsp-8+arg_10], rbx
0x180102011  push    rbp
0x180102012  push    rsi
0x180102013  push    rdi
0x180102014  push    r14
0x180102016  push    r15
0x180102018  lea     rbp, [rsp-37h]
0x18010201d  sub     rsp, 0C0h
0x180102024  mov     rax, cs:__security_cookie
0x18010202b  xor     rax, rsp
0x18010202e  mov     [rbp+57h+var_30], rax
0x180102032  mov     r14d, edx
0x180102035  mov     qword ptr [r9], 0
0x18010203c  mov     rdi, rcx
0x18010203f  mov     edx, 0D7h; unsigned int
0x180102044  mov     rcx, cs:g_hinst; HINSTANCE
0x18010204b  mov     r15, r9
0x18010204e  mov     ebx, 8007000Eh
0x180102053  call    ?SHLoadPopupMenu@@YAPEAUHMENU__@@PEAUHINSTANCE__@@I@Z; SHLoadPopupMenu(HINSTANCE__ *,uint)
0x180102058  mov     [rbp+57h+hMenu], rax
0x18010205c  mov     rdx, rax
0x18010205f  test    rax, rax
0x180102062  jz      loc_1801023A5
0x180102068  mov     rax, [rdi+280h]
0x18010206f  xor     ecx, ecx
0x180102071  mov     r9, [rdi+320h]
0x180102078  mov     r8d, 7000h
0x18010207e  mov     qword ptr [rsp+0E0h+uFlags], rax
0x180102083  mov     dword ptr [rsp+0E0h+lpNewItem], 1; int
0x18010208b  call    Def_InitEditCommands
0x180102090  mov     rcx, [rbp+57h+hMenu]; hMenu
0x180102094  xor     r8d, r8d; uFlags
0x180102097  test    dword ptr [rdi+378h], 10000000h
0x1801020a1  mov     edx, 7033h; uPosition
0x1801020a6  jz      loc_1801022EC
0x1801020ac  call    cs:__imp_DeleteMenu
0x1801020b3  nop     dword ptr [rax+rax+00h]
0x1801020b8  xor     edx, edx; Val
0x1801020ba  mov     [rbp+57h+mii.cbSize], 50h ; 'P'
0x1801020c1  lea     rcx, [rbp+57h+mii.fType]; void *
0x1801020c5  mov     [rbp+57h+mii.fMask], 4
0x1801020cc  lea     r8d, [rdx+48h]; Size
0x1801020d0  call    memset_0
0x1801020d5  mov     rcx, [rbp+57h+hMenu]; hmenu
0x1801020d9  lea     r9, [rbp+57h+mii]; lpmii
0x1801020dd  xor     r8d, r8d; fByPosition
0x1801020e0  mov     edx, 7002h; item
0x1801020e5  call    cs:__imp_GetMenuItemInfoW
0x1801020ec  nop     dword ptr [rax+rax+00h]
0x1801020f1  mov     rsi, [rbp+57h+mii.hSubMenu]
0x1801020f5  test    rsi, rsi
0x1801020f8  jz      loc_180102310
0x1801020fe  xor     r8d, r8d; uFlags
0x180102101  mov     edx, 704Bh; uPosition
0x180102106  mov     rcx, rsi; hMenu
0x180102109  call    cs:__imp_DeleteMenu
0x180102110  nop     dword ptr [rax+rax+00h]
0x180102115  xor     r8d, r8d; uFlags
0x180102118  mov     edx, 704Ch; uPosition
0x18010211d  mov     rcx, rsi; hMenu
0x180102120  call    cs:__imp_DeleteMenu
0x180102127  nop     dword ptr [rax+rax+00h]
0x18010212c  xor     r8d, r8d; uFlags
0x18010212f  mov     edx, 704Dh; uPosition
0x180102134  mov     rcx, rsi; hMenu
0x180102137  call    cs:__imp_DeleteMenu
0x18010213e  nop     dword ptr [rax+rax+00h]
0x180102143  xor     r8d, r8d; uFlags
0x180102146  mov     edx, 7051h; uPosition
0x18010214b  mov     rcx, rsi; hMenu
0x18010214e  call    cs:__imp_DeleteMenu
0x180102155  nop     dword ptr [rax+rax+00h]
0x18010215a  xor     r8d, r8d; uFlags
0x18010215d  mov     edx, 7052h; uPosition
0x180102162  mov     rcx, rsi; hMenu
0x180102165  call    cs:__imp_DeleteMenu
0x18010216c  nop     dword ptr [rax+rax+00h]
0x180102171  mov     rdx, rsi; hmenu
0x180102174  mov     rcx, rdi; this
0x180102177  call    ?_CheckCurrentViewMenuItem@CDefView@@AEAAIPEAUHMENU__@@@Z; CDefView::_CheckCurrentViewMenuItem(HMENU__ *)
0x18010217c  mov     rcx, cs:g_hinst; hModule
0x180102183  lea     rax, [rbp+57h+var_50]
0x180102187  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x18010218e  mov     qword ptr [rsp+0E0h+uFlags], rax; void *
0x180102193  mov     edx, 79B5h
0x180102198  mov     [rbp+57h+var_50], 0
0x1801021a0  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1801021a5  test    eax, eax
0x1801021a7  js      short loc_1801021DB
0x1801021a9  mov     rbx, [rbp+57h+var_50]
0x1801021ad  mov     edx, 7071h; uPosition
0x1801021b2  mov     r9d, edx; uIDNewItem
0x1801021b5  mov     [rsp+0E0h+lpNewItem], rbx; int
0x1801021ba  xor     r8d, r8d; uFlags
0x1801021bd  mov     rcx, rsi; hMnu
0x1801021c0  call    cs:__imp_ModifyMenuW
0x1801021c7  nop     dword ptr [rax+rax+00h]
0x1801021cc  mov     rcx, rbx; hMem
0x1801021cf  call    cs:__imp_LocalFree
0x1801021d6  nop     dword ptr [rax+rax+00h]
0x1801021db  mov     rcx, cs:g_hinst; hModule
0x1801021e2  lea     rax, [rbp+57h+var_50]
0x1801021e6  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x1801021ed  mov     qword ptr [rsp+0E0h+uFlags], rax; void *
0x1801021f2  mov     edx, 79B6h
0x1801021f7  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1801021fc  test    eax, eax
0x1801021fe  js      short loc_180102232
0x180102200  mov     rbx, [rbp+57h+var_50]
0x180102204  mov     edx, 7074h; uPosition
0x180102209  mov     r9d, edx; uIDNewItem
0x18010220c  mov     [rsp+0E0h+lpNewItem], rbx; lpNewItem
0x180102211  xor     r8d, r8d; uFlags
0x180102214  mov     rcx, rsi; hMnu
0x180102217  call    cs:__imp_ModifyMenuW
0x18010221e  nop     dword ptr [rax+rax+00h]
0x180102223  mov     rcx, rbx; hMem
0x180102226  call    cs:__imp_LocalFree
0x18010222d  nop     dword ptr [rax+rax+00h]
0x180102232  mov     ecx, 40000008h; rest
0x180102237  call    cs:__imp_SHRestricted
0x18010223e  nop     dword ptr [rax+rax+00h]
0x180102243  test    eax, eax
0x180102245  jnz     loc_180102310
0x18010224b  mov     rcx, cs:g_hinst
0x180102252  mov     edx, 0DAh
0x180102257  call    cs:__imp_SHLoadMenuPopup
0x18010225e  nop     dword ptr [rax+rax+00h]
0x180102263  mov     rbx, rax
0x180102266  test    rax, rax
0x180102269  jz      loc_180102310
0x18010226f  xorps   xmm0, xmm0
0x180102272  lea     rcx, [rbp+57h+var_50]; lpss
0x180102276  xor     r8d, r8d; bSet
0x180102279  mov     edx, 4000h; dwMask
0x18010227e  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180102282  movups  [rbp+57h+var_40], xmm0
0x180102286  call    cs:__imp_SHGetSetSettings
0x18010228d  nop     dword ptr [rax+rax+00h]
0x180102292  test    dword ptr [rbp+57h+var_50], 1000h
0x180102299  jnz     short loc_1801022B5
0x18010229b  mov     edx, 7402h; uIDCheckItem
0x1801022a0  mov     r8d, 8; uCheck
0x1801022a6  mov     rcx, rbx; hMenu
0x1801022a9  call    cs:__imp_CheckMenuItem
0x1801022b0  nop     dword ptr [rax+rax+00h]
0x1801022b5  or      r8d, 0FFFFFFFFh; uInsert
0x1801022b9  mov     [rsp+0E0h+uFlags], 3; uFlags
0x1801022c1  xor     r9d, r9d; uIDAdjust
0x1801022c4  mov     dword ptr [rsp+0E0h+lpNewItem], r8d; uIDAdjustMax
0x1801022c9  mov     rdx, rbx; hmSrc
0x1801022cc  mov     rcx, rsi; hmDst
0x1801022cf  call    cs:__imp_Shell_MergeMenus
0x1801022d6  nop     dword ptr [rax+rax+00h]
0x1801022db  mov     rcx, rbx; hMenu
0x1801022de  call    cs:__imp_DestroyMenu
0x1801022e5  nop     dword ptr [rax+rax+00h]
0x1801022ea  jmp     short loc_180102310
0x1801022ec  call    cs:__imp_DeleteMenu
0x1801022f3  nop     dword ptr [rax+rax+00h]
0x1801022f8  mov     r8, rdi
0x1801022fb  lea     rdx, [rbp+57h+hMenu]
0x1801022ff  lea     rcx, [rbp+57h+var_50]
0x180102303  call    ??0_lambda_24bd8fc070818ccaf49523ad64560b1b_@@QEAA@AEBUhstring@winrt@@PEBU?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@2@@Z; _lambda_24bd8fc070818ccaf49523ad64560b1b_::_lambda_24bd8fc070818ccaf49523ad64560b1b_(winrt::hstring const &,winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version> const *)
0x180102308  mov     rcx, rax
0x18010230b  call    _lambda_16c53df8719282c89666fc44e0c1c168___operator__
0x180102310  mov     rdx, [rbp+57h+hMenu]; hMenu
0x180102314  mov     rcx, rdi; this
0x180102317  call    ?_InitViewMenu@CDefView@@AEAAXPEAUHMENU__@@@Z; CDefView::_InitViewMenu(HMENU__ *)
0x18010231c  test    r14d, r14d
0x18010231f  jz      short loc_180102388
0x180102321  xor     edx, edx; Val
0x180102323  mov     [rbp+57h+mii.cbSize], 50h ; 'P'
0x18010232a  lea     rcx, [rbp+57h+mii.fType]; void *
0x18010232e  mov     [rbp+57h+mii.fMask], 4
0x180102335  lea     r8d, [rdx+48h]; Size
0x180102339  call    memset_0
0x18010233e  mov     rcx, [rbp+57h+hMenu]; hmenu
0x180102342  lea     r9, [rbp+57h+mii]; lpmii
0x180102346  xor     r8d, r8d; fByPosition
0x180102349  mov     edx, r14d; item
0x18010234c  call    cs:__imp_GetMenuItemInfoW
0x180102353  nop     dword ptr [rax+rax+00h]
0x180102358  mov     rcx, [rbp+57h+hMenu]; hMenu
0x18010235c  xor     r8d, r8d; uFlags
0x18010235f  mov     rbx, [rbp+57h+mii.hSubMenu]
0x180102363  mov     edx, r14d; uPosition
0x180102366  call    cs:__imp_RemoveMenu
0x18010236d  nop     dword ptr [rax+rax+00h]
0x180102372  mov     rcx, [rbp+57h+hMenu]; hMenu
0x180102376  call    cs:__imp_DestroyMenu
0x18010237d  nop     dword ptr [rax+rax+00h]
0x180102382  mov     [rbp+57h+hMenu], rbx
0x180102386  jmp     short loc_18010238C
0x180102388  mov     rbx, [rbp+57h+hMenu]
0x18010238c  mov     rdx, [rdi+2D0h]; HWND
0x180102393  mov     r8, rdi; struct CDefView *
0x180102396  mov     rcx, rbx; HMENU
0x180102399  mov     [rsp+0E0h+lpNewItem], r15; void **
0x18010239e  call    ?Create_CDVBackgroundHMENU@@YAJPEAUHMENU__@@PEAUHWND__@@PEAVCDefView@@AEBU_GUID@@PEAPEAX@Z; Create_CDVBackgroundHMENU(HMENU__ *,HWND__ *,CDefView *,_GUID const &,void * *)
0x1801023a3  mov     ebx, eax
0x1801023a5  mov     eax, ebx
0x1801023a7  mov     rcx, [rbp+57h+var_30]
0x1801023ab  xor     rcx, rsp; StackCookie
0x1801023ae  call    __security_check_cookie
0x1801023b3  mov     rbx, [rsp+0E0h+arg_10]
0x1801023bb  add     rsp, 0C0h
0x1801023c2  pop     r15
0x1801023c4  pop     r14
0x1801023c6  pop     rdi
0x1801023c7  pop     rsi
0x1801023c8  pop     rbp
0x1801023c9  retn
```
