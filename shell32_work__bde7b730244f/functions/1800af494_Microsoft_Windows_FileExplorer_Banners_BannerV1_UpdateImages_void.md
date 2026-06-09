# Microsoft::Windows::FileExplorer::Banners::BannerV1::UpdateImages(void)

- ea: `0x1800af494`
- end: `0x1800af6e4`
- name: `?UpdateImages@BannerV1@Banners@FileExplorer@Windows@Microsoft@@AEAAXXZ`
- size: `592`
- prototype: `void __fastcall(Microsoft::Windows::FileExplorer::Banners::BannerV1 *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800af240`
- `0x18022c310`

## callees

- `0x180061090`
- `0x1800af494`
- `0x1800af6ec`
- `0x1800af998`
- `0x1800d4564`
- `0x18053059c`
- `0x1805305cc`
- `0x180571010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800af5c3`
- `GDI32!DeleteObject` at `0x1800af6d5`
- `GDI32!DeleteObject` at `0x1800af5c3`
- `GDI32!DeleteObject` at `0x1800af6d5`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800af4d6`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800af5a0`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800af5ee`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800af6b2`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800af4f4`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800af60f`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800af4f4`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800af60f`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800af4e0`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800af5f8`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800af4e0`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800af5f8`
- `DUI70!StrToID` at `0x1800af4b8`
- `DUI70!StrToID` at `0x1800af5d0`
- `DUI70!StrToID` at `0x1800af4b8`
- `DUI70!StrToID` at `0x1800af5d0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800af4c4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800af5dc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800af4c4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800af5dc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800af5aa`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800af6bc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800af5aa`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800af6bc`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800af578`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800af696`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800af578`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800af696`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Windows::FileExplorer::Banners::BannerV1::UpdateImages(
        Microsoft::Windows::FileExplorer::Banners::BannerData **this)
{
  unsigned __int16 v2; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v4; // rsi
  struct DirectUI::Element *Root; // rax
  __int64 v6; // rax
  HWND v7; // rax
  Microsoft::Windows::FileExplorer::Banners::BannerData *v8; // rbx
  HBITMAP v9; // rbx
  bool v10; // zf
  struct DirectUI::Value *Graphic; // rax
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rax
  DirectUI::Element *v14; // rsi
  struct DirectUI::Element *v15; // rax
  __int64 v16; // rax
  HWND v17; // rax
  Microsoft::Windows::FileExplorer::Banners::BannerData *v18; // rdi
  Microsoft::Windows::FileExplorer::Banners::BannerData *v19; // rcx
  HGDIOBJ v20; // rbx
  HBITMAP v21; // rdx
  struct DirectUI::Value *v22; // rax
  struct tagSIZE v23; // [rsp+30h] [rbp-18h] BYREF
  HGDIOBJ ho[2]; // [rsp+38h] [rbp-10h] BYREF

  if ( this[26] )
  {
    v2 = StrToID(L"BannerLogo");
    Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
    v4 = Descendent;
    if ( Descendent )
    {
      DirectUI::Element::RemoveLocalValue(Descendent, DirectUI::Element::ContentProp);
      v23 = (struct tagSIZE)0x3A0000003ALL;
      Root = DirectUI::Element::GetRoot((DirectUI::Element *)this);
      v6 = element_cast<DirectUI::HWNDElement>(Root);
      v7 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 360LL))(v6);
      SHLogicalToPhysicalDPI(v7, &v23);
      ho[0] = 0;
      v8 = this[26];
      wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
        ho,
        0);
      Microsoft::Windows::FileExplorer::Banners::BannerData::GetLogoBitmap(v8, v23, (HBITMAP *)ho);
      v9 = (HBITMAP)ho[0];
      v10 = ho[0] == 0;
      *((_BYTE *)this + 256) = ho[0] != 0;
      if ( !v10 )
      {
        Graphic = DirectUI::Value::CreateGraphic(v9, 2u, 0xFFFFFFFF, 0, 0, 0);
        v23 = (struct tagSIZE)Graphic;
        *((_BYTE *)this + 256) = Graphic != 0;
        if ( Graphic )
        {
          v9 = 0;
          ho[0] = 0;
          DirectUI::Element::SetValue(v4, DirectUI::Element::ContentProp, 1, Graphic);
        }
        ValueRef::~ValueRef((ValueRef *)&v23);
      }
      if ( v9 )
        DeleteObject(v9);
    }
    v12 = StrToID(L"BannerBackground");
    v13 = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v12);
    v14 = v13;
    if ( v13 )
    {
      DirectUI::Element::RemoveLocalValue(v13, DirectUI::Element::ContentProp);
      v23.cx = 146;
      v23.cy = 132;
      v15 = DirectUI::Element::GetRoot((DirectUI::Element *)this);
      v16 = element_cast<DirectUI::HWNDElement>(v15);
      v17 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 360LL))(v16);
      SHLogicalToPhysicalDPI(v17, &v23);
      ho[0] = 0;
      v18 = this[26];
      wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(
        ho,
        0);
      v20 = 0;
      ho[0] = 0;
      v21 = (HBITMAP)*((_QWORD *)v18 + 24);
      if ( v21 )
      {
        Microsoft::Windows::FileExplorer::Banners::BannerData::GetScaledHBitmap(v19, v21, v23, (HBITMAP *)ho);
        v20 = ho[0];
        if ( ho[0] )
        {
          v22 = DirectUI::Value::CreateGraphic((HBITMAP)ho[0], 2u, 0xFFFFFFFF, 0, 0, 0);
          v23 = (struct tagSIZE)v22;
          if ( v22 )
          {
            v20 = 0;
            ho[0] = 0;
            DirectUI::Element::SetValue(v14, DirectUI::Element::ContentProp, 1, v22);
          }
          ValueRef::~ValueRef((ValueRef *)&v23);
        }
      }
      if ( v20 )
        DeleteObject(v20);
    }
  }
}

```

## disassembly

```asm
0x1800af494  push    rbp
0x1800af496  push    rbx
0x1800af497  push    rsi
0x1800af498  push    rdi
0x1800af499  mov     rbp, rsp
0x1800af49c  sub     rsp, 48h
0x1800af4a0  mov     rdi, rcx
0x1800af4a3  cmp     qword ptr [rcx+0D0h], 0
0x1800af4ab  jz      loc_1800AF6DB
0x1800af4b1  lea     rcx, aBannerlogo; "BannerLogo"
0x1800af4b8  call    cs:__imp_StrToID
0x1800af4be  movzx   edx, ax
0x1800af4c1  mov     rcx, rdi
0x1800af4c4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800af4ca  mov     rsi, rax
0x1800af4cd  test    rax, rax
0x1800af4d0  jz      loc_1800AF5C9
0x1800af4d6  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800af4dd  mov     rcx, rax
0x1800af4e0  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800af4e6  mov     eax, 3Ah ; ':'
0x1800af4eb  mov     [rbp+var_18.cx], eax
0x1800af4ee  mov     [rbp+var_18.cy], eax
0x1800af4f1  mov     rcx, rdi
0x1800af4f4  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x1800af4fa  mov     rcx, rax
0x1800af4fd  call    ??$element_cast@VHWNDElement@DirectUI@@@@YAPEAVHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::HWNDElement>(DirectUI::Element *)
0x1800af502  mov     rdx, rax
0x1800af505  mov     rcx, [rax]
0x1800af508  mov     rax, [rcx+168h]
0x1800af50f  mov     rcx, rdx
0x1800af512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af517  mov     rcx, rax; HWND
0x1800af51a  lea     rdx, [rbp+var_18]; struct tagSIZE *
0x1800af51e  call    ?SHLogicalToPhysicalDPI@@YAXPEAUHWND__@@PEAUtagSIZE@@@Z; SHLogicalToPhysicalDPI(HWND__ *,tagSIZE *)
0x1800af523  mov     [rbp+ho], 0
0x1800af52b  mov     rbx, [rdi+0D0h]
0x1800af532  xor     edx, edx
0x1800af534  lea     rcx, [rbp+ho]
0x1800af538  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(HBITMAP__ *)
0x1800af53d  lea     r8, [rbp+ho]; HBITMAP *
0x1800af541  mov     rdx, qword ptr [rbp+var_18.cx]; struct tagSIZE
0x1800af545  mov     rcx, rbx; this
0x1800af548  call    ?GetLogoBitmap@BannerData@Banners@FileExplorer@Windows@Microsoft@@QEBAJUtagSIZE@@PEAPEAUHBITMAP__@@@Z; Microsoft::Windows::FileExplorer::Banners::BannerData::GetLogoBitmap(tagSIZE,HBITMAP__ * *)
0x1800af54d  mov     rbx, [rbp+ho]
0x1800af551  test    rbx, rbx
0x1800af554  setnz   al
0x1800af557  mov     [rdi+100h], al
0x1800af55d  test    rbx, rbx
0x1800af560  jz      short loc_1800AF5BB
0x1800af562  mov     [rsp+48h+var_20], 0
0x1800af567  mov     [rsp+48h+var_28], 0
0x1800af56c  xor     r9d, r9d
0x1800af56f  or      r8d, 0FFFFFFFFh
0x1800af573  mov     dl, 2
0x1800af575  mov     rcx, rbx
0x1800af578  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800af57e  mov     qword ptr [rbp+var_18.cx], rax
0x1800af582  test    rax, rax
0x1800af585  setnz   cl
0x1800af588  mov     [rdi+100h], cl
0x1800af58e  test    rax, rax
0x1800af591  jz      short loc_1800AF5B1
0x1800af593  xor     ebx, ebx
0x1800af595  mov     [rbp+ho], rbx
0x1800af599  mov     r9, rax
0x1800af59c  lea     r8d, [rbx+1]
0x1800af5a0  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800af5a7  mov     rcx, rsi
0x1800af5aa  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800af5b0  nop
0x1800af5b1  lea     rcx, [rbp+var_18]; this
0x1800af5b5  call    ??1ValueRef@@QEAA@XZ; ValueRef::~ValueRef(void)
0x1800af5ba  nop
0x1800af5bb  test    rbx, rbx
0x1800af5be  jz      short loc_1800AF5C9
0x1800af5c0  mov     rcx, rbx; ho
0x1800af5c3  call    cs:__imp_DeleteObject
0x1800af5c9  lea     rcx, aBannerbackgrou_0; "BannerBackground"
0x1800af5d0  call    cs:__imp_StrToID
0x1800af5d6  movzx   edx, ax
0x1800af5d9  mov     rcx, rdi
0x1800af5dc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800af5e2  mov     rsi, rax
0x1800af5e5  test    rax, rax
0x1800af5e8  jz      loc_1800AF6DB
0x1800af5ee  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800af5f5  mov     rcx, rax
0x1800af5f8  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800af5fe  mov     [rbp+var_18.cx], 92h
0x1800af605  mov     [rbp+var_18.cy], 84h
0x1800af60c  mov     rcx, rdi
0x1800af60f  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x1800af615  mov     rcx, rax
0x1800af618  call    ??$element_cast@VHWNDElement@DirectUI@@@@YAPEAVHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::HWNDElement>(DirectUI::Element *)
0x1800af61d  mov     rdx, rax
0x1800af620  mov     rcx, [rax]
0x1800af623  mov     rax, [rcx+168h]
0x1800af62a  mov     rcx, rdx
0x1800af62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af632  mov     rcx, rax; HWND
0x1800af635  lea     rdx, [rbp+var_18]; struct tagSIZE *
0x1800af639  call    ?SHLogicalToPhysicalDPI@@YAXPEAUHWND__@@PEAUtagSIZE@@@Z; SHLogicalToPhysicalDPI(HWND__ *,tagSIZE *)
0x1800af63e  mov     [rbp+ho], 0
0x1800af646  mov     rdi, [rdi+0D0h]
0x1800af64d  xor     edx, edx
0x1800af64f  lea     rcx, [rbp+ho]
0x1800af653  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHBITMAP__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::reset(HBITMAP__ *)
0x1800af658  xor     ebx, ebx
0x1800af65a  mov     [rbp+ho], rbx
0x1800af65e  mov     rdx, [rdi+0C0h]; HBITMAP
0x1800af665  test    rdx, rdx
0x1800af668  jz      short loc_1800AF6CD
0x1800af66a  lea     r9, [rbp+ho]; HBITMAP *
0x1800af66e  mov     r8, qword ptr [rbp+var_18.cx]; struct tagSIZE
0x1800af672  call    ?GetScaledHBitmap@BannerData@Banners@FileExplorer@Windows@Microsoft@@AEBAJPEAUHBITMAP__@@UtagSIZE@@PEAPEAU6@@Z; Microsoft::Windows::FileExplorer::Banners::BannerData::GetScaledHBitmap(HBITMAP__ *,tagSIZE,HBITMAP__ * *)
0x1800af677  mov     rbx, [rbp+ho]
0x1800af67b  test    rbx, rbx
0x1800af67e  jz      short loc_1800AF6CD
0x1800af680  mov     [rsp+48h+var_20], 0
0x1800af685  mov     [rsp+48h+var_28], 0
0x1800af68a  xor     r9d, r9d
0x1800af68d  or      r8d, 0FFFFFFFFh
0x1800af691  mov     dl, 2
0x1800af693  mov     rcx, rbx
0x1800af696  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800af69c  mov     qword ptr [rbp+var_18.cx], rax
0x1800af6a0  test    rax, rax
0x1800af6a3  jz      short loc_1800AF6C3
0x1800af6a5  xor     ebx, ebx
0x1800af6a7  mov     [rbp+ho], rbx
0x1800af6ab  mov     r9, rax
0x1800af6ae  lea     r8d, [rbx+1]
0x1800af6b2  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800af6b9  mov     rcx, rsi
0x1800af6bc  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800af6c2  nop
0x1800af6c3  lea     rcx, [rbp+var_18]; this
0x1800af6c7  call    ??1ValueRef@@QEAA@XZ; ValueRef::~ValueRef(void)
0x1800af6cc  nop
0x1800af6cd  test    rbx, rbx
0x1800af6d0  jz      short loc_1800AF6DB
0x1800af6d2  mov     rcx, rbx; ho
0x1800af6d5  call    cs:__imp_DeleteObject
0x1800af6db  add     rsp, 48h
0x1800af6df  pop     rdi
0x1800af6e0  pop     rsi
0x1800af6e1  pop     rbx
0x1800af6e2  pop     rbp
0x1800af6e3  retn
```
