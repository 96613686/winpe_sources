# CAppListTileElement::InitializeElement(IShellItem *,IPropertyStore *)

- ea: `0x180261e7c`
- end: `0x180262367`
- name: `?InitializeElement@CAppListTileElement@@QEAAJPEAUIShellItem@@PEAUIPropertyStore@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(CAppListTileElement *__hidden this, struct IShellItem *, struct IPropertyStore *)`
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802605b0`
- `0x180261170`

## callees

- `0x180011884`
- `0x18002cd00`
- `0x18008e9d4`
- `0x18009cfa8`
- `0x18009d6fc`
- `0x1800a6a98`
- `0x1800bb114`
- `0x18013d330`
- `0x1801dd34c`
- `0x180261660`
- `0x1802618f4`
- `0x180261e34`
- `0x180261e7c`
- `0x180262b5c`
- `0x180262e78`
- `0x180262f5c`
- `0x180265d00`
- `0x18036d624`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026202e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180262067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802620aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180262106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026214c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026216a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802621b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802621c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026220a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026202e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180262067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802620aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180262106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026214c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026216a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802621b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802621c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026220a`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802621ff`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802621ff`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180261fba`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180262227`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180261fba`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180262227`
- `DUI70!StrToID` at `0x180261fae`
- `DUI70!StrToID` at `0x18026221b`
- `DUI70!StrToID` at `0x180261fae`
- `DUI70!StrToID` at `0x18026221b`
- `DUI70!?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x1802622fd`
- `DUI70!?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x1802622fd`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802620f5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802620f5`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180262013`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180262013`

## pseudocode

```c
__int64 __fastcall CAppListTileElement::InitializeElement(
        CAppListTileElement *this,
        struct IShellItem *a2,
        struct IPropertyStore *a3)
{
  struct IShellItem **v6; // r15
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rbx
  __int64 v8; // rax
  int inited; // ebx
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned int Color; // eax
  struct IShellItem *v13; // rdi
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  const unsigned __int16 *v15; // rdx
  int v16; // r9d
  HINSTANCE v17; // r8
  const unsigned __int16 *v18; // rdx
  unsigned __int16 v19; // ax
  struct DirectUI::Element *v20; // rax
  int TileStyle; // eax
  int v22; // ecx
  char *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  CShellItemThumbnailElement *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  bool *v31; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  CShellItemThumbnailElement *v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  PROPERTYKEY v35; // [rsp+50h] [rbp-B0h] BYREF
  char v36; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+94h] [rbp-6Ch]
  int v40; // [rsp+A4h] [rbp-5Ch]
  __int128 v41; // [rsp+A8h] [rbp-58h]
  int v42; // [rsp+B8h] [rbp-48h]
  PROPERTYKEY v43; // [rsp+BCh] [rbp-44h]
  PROPERTYKEY v44; // [rsp+D0h] [rbp-30h]
  __int128 v45; // [rsp+E4h] [rbp-1Ch]
  int v46; // [rsp+F4h] [rbp-Ch]

  if ( a2 )
  {
    v6 = (struct IShellItem **)((char *)this + 424);
    QueryInterface = a2->lpVtbl->QueryInterface;
    v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>((char *)this + 424);
    inited = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64))QueryInterface)(
               a2,
               &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
               v8);
    if ( inited < 0 )
      return (unsigned int)inited;
    v34[0] = (__int64)a3;
    if ( a3 )
    {
      ((void (__fastcall *)(struct IPropertyStore *))a3->lpVtbl->AddRef)(a3);
    }
    else
    {
      v38 = 4;
      v37 = PKEY_Tile_Background;
      v40 = 11;
      v39 = PKEY_Tile_LongDisplayName;
      v42 = 18;
      v43 = PKEY_ItemNameDisplay;
      v41 = PKEY_Tile_DisplayNameLanguage;
      v44 = PKEY_AppUserModel_ID;
      v46 = 2;
      v45 = PKEY_ShareTarget_Description;
      inited = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(
                 (unsigned int)v34,
                 (_DWORD)a2,
                 8,
                 (unsigned int)&v37,
                 6);
      if ( inited < 0 )
        goto LABEL_25;
    }
    v10 = StrToID(L"IconBackground");
    LODWORD(pv) = 0;
    Descendent = DirectUI::Element::FindDescendent(this, v10);
    Color = CImmersiveColor::GetColor(10);
    v35.pid = 4;
    v35.fmtid = (GUID)PKEY_Tile_Background;
    if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(v34, &v35, Color, &pv) < 0
      || (inited = DirectUI::Element::SetBackgroundColor(Descendent, (unsigned int)pv | 0xFF000000), inited >= 0) )
    {
      pv = 0;
      CoTaskMemFree(0);
      v35.pid = 11;
      v35.fmtid = (GUID)PKEY_Tile_LongDisplayName;
      if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(
                  v34,
                  (__int128 *)&v35,
                  (unsigned __int16 **)&pv) >= 0
        || (CoTaskMemFree(pv),
            v35 = PKEY_ItemNameDisplay,
            (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(
                   v34,
                   (__int128 *)&v35,
                   (unsigned __int16 **)&pv) >= 0)
        || (v13 = *v6,
            GetDisplayName = (*v6)->lpVtbl->GetDisplayName,
            CoTaskMemFree(pv),
            inited = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))GetDisplayName)(v13, 0, &pv),
            inited >= 0) )
      {
        inited = DUI_SetDescendentElementText(this, L"DisplayName", (const unsigned __int16 *)pv, 0);
        if ( inited >= 0 )
        {
          DirectUI::Element::SetAccName(this, (const unsigned __int16 *)pv);
          v33 = 0;
          CoTaskMemFree(0);
          v35.pid = 18;
          v35.fmtid = (GUID)PKEY_Tile_DisplayNameLanguage;
          if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(
                      v34,
                      (__int128 *)&v35,
                      (unsigned __int16 **)&v33) >= 0 )
            DUI_SetDescendentElementPreferredFontWithMinimumHeight(this, v15, (const unsigned __int16 *)v33, v16, v31);
          CoTaskMemFree(v33);
          if ( (unsigned int)CAppListTileElement::GetTileStyle(this) == 8 )
          {
            v33 = 0;
            CoTaskMemFree(0);
            v35.pid = 2;
            v35.fmtid = (GUID)PKEY_ShareTarget_Description;
            if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(
                        v34,
                        (__int128 *)&v35,
                        (unsigned __int16 **)&v33) >= 0 )
              CAppListTileElement::SetDescription(this, (const unsigned __int16 *)v33, v17);
            CoTaskMemFree(v33);
          }
          CoTaskMemFree(*((LPVOID *)this + 55));
          v35 = PKEY_AppUserModel_ID;
          if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(
                      v34,
                      (__int128 *)&v35,
                      (unsigned __int16 **)this + 55) < 0 )
            v18 = (const unsigned __int16 *)pv;
          else
            v18 = (const unsigned __int16 *)*((_QWORD *)this + 55);
          DirectUI::Element::SetID(this, v18);
        }
      }
      CoTaskMemFree(pv);
      if ( inited >= 0 )
      {
        v19 = StrToID(L"Icon");
        v20 = DirectUI::Element::FindDescendent(this, v19);
        v33 = 0;
        inited = ElementCast<CShellItemThumbnailElement>(v20, &v33);
        if ( inited >= 0 )
          inited = CShellItemThumbnailElement::SetShellItem(v33, *v6);
      }
    }
LABEL_25:
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v34);
    if ( inited < 0 )
      return (unsigned int)inited;
  }
  TileStyle = CAppListTileElement::GetTileStyle(this);
  v22 = 27;
  if ( TileStyle != 6 )
    v22 = 3;
  LODWORD(pv) = v22;
  v23 = (char *)Microsoft::WRL::Details::Make<CTileActivateBehavior,enum ACTIVATION_TRIGGER_FLAGS &>(&v33, &pv);
  v24 = 0;
  if ( &v36 != v23 )
  {
    v24 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
  }
  v25 = *((_QWORD *)this + 49);
  *((_QWORD *)this + 49) = v24;
  if ( v25 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(v25);
  v26 = v33;
  if ( v33 )
  {
    v33 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(v26);
  }
  v27 = *((_QWORD *)this + 49);
  if ( v27 )
  {
    *(_BYTE *)(v27 + 28) = 1;
    inited = DirectUI::Element::AddBehavior(this, *((struct IDuiBehavior **)this + 49));
    if ( inited >= 0 )
    {
      inited = CAppListTileElement::_InitializeRearrange(this);
      if ( inited >= 0 )
      {
        if ( (v28 = CAppListTileElement::GetTileStyle(this)) != 0 && (v29 = v28 - 1) != 0 && v29 != 7
          || (inited = CAppListTileElement::_InitContextMenu(this), inited >= 0) )
        {
          *((_BYTE *)this + 456) = 1;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180261e7c  mov     [rsp-8+arg_10], rbx
0x180261e81  push    rbp
0x180261e82  push    rsi
0x180261e83  push    rdi
0x180261e84  push    r14
0x180261e86  push    r15
0x180261e88  lea     rbp, [rsp-10h]
0x180261e8d  sub     rsp, 110h
0x180261e94  mov     rax, cs:__security_cookie
0x180261e9b  xor     rax, rsp
0x180261e9e  mov     [rbp+30h+var_30], rax
0x180261ea2  mov     rdi, r8
0x180261ea5  mov     r14, rdx
0x180261ea8  mov     rsi, rcx
0x180261eab  test    rdx, rdx
0x180261eae  jz      loc_18026226A
0x180261eb4  mov     rax, [rdx]
0x180261eb7  lea     r15, [rcx+1A8h]
0x180261ebe  mov     rcx, r15
0x180261ec1  mov     rbx, [rax]
0x180261ec4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x180261ec9  mov     r8, rax
0x180261ecc  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180261ed3  mov     rax, rbx
0x180261ed6  mov     rcx, r14
0x180261ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180261ede  mov     ebx, eax
0x180261ee0  test    eax, eax
0x180261ee2  js      loc_180262342
0x180261ee8  mov     [rsp+130h+var_F0], rdi
0x180261eed  test    rdi, rdi
0x180261ef0  jz      short loc_180261F06
0x180261ef2  mov     rax, [rdi]
0x180261ef5  mov     rcx, rdi
0x180261ef8  mov     rax, [rax+8]
0x180261efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180261f01  jmp     loc_180261FA7
0x180261f06  movups  xmm0, cs:PKEY_Tile_Background
0x180261f0d  mov     eax, cs:dword_1803F8E88
0x180261f13  lea     r9, [rbp+30h+var_B0]
0x180261f17  mov     [rbp+30h+var_A0], eax
0x180261f1a  lea     rcx, [rsp+130h+var_F0]
0x180261f1f  mov     eax, cs:dword_180409FC0
0x180261f25  mov     r8d, 8
0x180261f2b  movaps  [rbp+30h+var_B0], xmm0
0x180261f2f  mov     rdx, r14
0x180261f32  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x180261f39  mov     [rbp+30h+var_8C], eax
0x180261f3c  mov     eax, cs:dword_18040A088
0x180261f42  movups  [rbp+30h+var_9C], xmm0
0x180261f46  mov     [rbp+30h+var_78], eax
0x180261f49  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x180261f50  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x180261f56  mov     [rbp+30h+var_64], eax
0x180261f59  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x180261f5f  movups  [rbp+30h+var_88], xmm0
0x180261f63  mov     [rbp+30h+var_50], eax
0x180261f66  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180261f6d  mov     eax, cs:dword_18040A010
0x180261f73  mov     [rbp+30h+var_3C], eax
0x180261f76  movups  [rbp+30h+var_74], xmm0
0x180261f7a  mov     dword ptr [rsp+130h+var_110], 6; bool *
0x180261f82  movups  xmm0, xmmword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x180261f89  movaps  [rbp+30h+var_60], xmm0
0x180261f8d  movups  xmm0, cs:PKEY_ShareTarget_Description
0x180261f94  movups  [rbp+30h+var_4C], xmm0
0x180261f98  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180261f9d  mov     ebx, eax
0x180261f9f  test    eax, eax
0x180261fa1  js      loc_180262258
0x180261fa7  lea     rcx, aIconbackground; "IconBackground"
0x180261fae  call    cs:__imp_StrToID
0x180261fb4  movzx   edx, ax
0x180261fb7  mov     rcx, rsi
0x180261fba  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180261fc0  mov     ecx, 0Ah
0x180261fc5  mov     dword ptr [rsp+130h+pv], 0
0x180261fcd  mov     rbx, rax
0x180261fd0  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x180261fd5  mov     ecx, cs:dword_1803F8E88
0x180261fdb  lea     r9, [rsp+130h+pv]
0x180261fe0  movups  xmm0, cs:PKEY_Tile_Background
0x180261fe7  mov     [rsp+130h+var_D0], ecx
0x180261feb  lea     rdx, [rsp+130h+var_E0]
0x180261ff0  mov     r8d, eax
0x180261ff3  lea     rcx, [rsp+130h+var_F0]
0x180261ff8  movaps  [rsp+130h+var_E0], xmm0
0x180261ffd  call    ??$GetAsUInt32WithDefault@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@KPEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(_tagpropertykey,ulong,ulong *)
0x180262002  test    eax, eax
0x180262004  js      short loc_180262023
0x180262006  mov     edx, dword ptr [rsp+130h+pv]
0x18026200a  mov     rcx, rbx
0x18026200d  or      edx, 0FF000000h
0x180262013  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x180262019  mov     ebx, eax
0x18026201b  test    eax, eax
0x18026201d  js      loc_180262258
0x180262023  xor     ecx, ecx; pv
0x180262025  mov     [rsp+130h+pv], 0
0x18026202e  call    cs:__imp_CoTaskMemFree
0x180262034  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x18026203b  mov     eax, cs:dword_180409FC0
0x180262041  lea     r8, [rsp+130h+pv]
0x180262046  lea     rdx, [rsp+130h+var_E0]
0x18026204b  mov     [rsp+130h+var_D0], eax
0x18026204f  lea     rcx, [rsp+130h+var_F0]
0x180262054  movaps  [rsp+130h+var_E0], xmm0
0x180262059  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18026205e  test    eax, eax
0x180262060  jns     short loc_1802620CC
0x180262062  mov     rcx, [rsp+130h+pv]; pv
0x180262067  call    cs:__imp_CoTaskMemFree
0x18026206d  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180262074  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18026207a  lea     r8, [rsp+130h+pv]
0x18026207f  lea     rdx, [rsp+130h+var_E0]
0x180262084  mov     [rsp+130h+var_D0], eax
0x180262088  lea     rcx, [rsp+130h+var_F0]
0x18026208d  movaps  [rsp+130h+var_E0], xmm0
0x180262092  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180262097  test    eax, eax
0x180262099  jns     short loc_1802620CC
0x18026209b  mov     rdi, [r15]
0x18026209e  mov     rcx, [rsp+130h+pv]; pv
0x1802620a3  mov     rax, [rdi]
0x1802620a6  mov     rbx, [rax+28h]
0x1802620aa  call    cs:__imp_CoTaskMemFree
0x1802620b0  lea     r8, [rsp+130h+pv]
0x1802620b5  xor     edx, edx
0x1802620b7  mov     rcx, rdi
0x1802620ba  mov     rax, rbx
0x1802620bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802620c2  mov     ebx, eax
0x1802620c4  test    eax, eax
0x1802620c6  js      loc_180262205
0x1802620cc  mov     r8, [rsp+130h+pv]; unsigned __int16 *
0x1802620d1  lea     rdx, aDisplayname; "DisplayName"
0x1802620d8  xor     r9d, r9d; HINSTANCE
0x1802620db  mov     rcx, rsi; struct DirectUI::Element *
0x1802620de  call    ?DUI_SetDescendentElementText@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementText(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x1802620e3  mov     ebx, eax
0x1802620e5  test    eax, eax
0x1802620e7  js      loc_180262205
0x1802620ed  mov     rdx, [rsp+130h+pv]
0x1802620f2  mov     rcx, rsi
0x1802620f5  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1802620fb  xor     ecx, ecx; pv
0x1802620fd  mov     [rsp+130h+var_F8], 0
0x180262106  call    cs:__imp_CoTaskMemFree
0x18026210c  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x180262113  mov     eax, cs:dword_18040A088
0x180262119  lea     r8, [rsp+130h+var_F8]
0x18026211e  lea     rdx, [rsp+130h+var_E0]
0x180262123  mov     [rsp+130h+var_D0], eax
0x180262127  lea     rcx, [rsp+130h+var_F0]
0x18026212c  movaps  [rsp+130h+var_E0], xmm0
0x180262131  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180262136  test    eax, eax
0x180262138  js      short loc_180262147
0x18026213a  mov     r8, [rsp+130h+var_F8]; unsigned __int16 *
0x18026213f  mov     rcx, rsi; struct DirectUI::Element *
0x180262142  call    ?DUI_SetDescendentElementPreferredFontWithMinimumHeight@@YAJPEAVElement@DirectUI@@PEBG1HPEA_N@Z; DUI_SetDescendentElementPreferredFontWithMinimumHeight(DirectUI::Element *,ushort const *,ushort const *,int,bool *)
0x180262147  mov     rcx, [rsp+130h+var_F8]; pv
0x18026214c  call    cs:__imp_CoTaskMemFree
0x180262152  mov     rcx, rsi
0x180262155  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x18026215a  cmp     eax, 8
0x18026215d  jnz     short loc_1802621B6
0x18026215f  xor     ecx, ecx; pv
0x180262161  mov     [rsp+130h+var_F8], 0
0x18026216a  call    cs:__imp_CoTaskMemFree
0x180262170  movups  xmm0, cs:PKEY_ShareTarget_Description
0x180262177  mov     eax, cs:dword_18040A010
0x18026217d  lea     r8, [rsp+130h+var_F8]
0x180262182  lea     rdx, [rsp+130h+var_E0]
0x180262187  mov     [rsp+130h+var_D0], eax
0x18026218b  lea     rcx, [rsp+130h+var_F0]
0x180262190  movaps  [rsp+130h+var_E0], xmm0
0x180262195  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18026219a  test    eax, eax
0x18026219c  js      short loc_1802621AB
0x18026219e  mov     rdx, [rsp+130h+var_F8]; unsigned __int16 *
0x1802621a3  mov     rcx, rsi; this
0x1802621a6  call    ?SetDescription@CAppListTileElement@@QEAAJPEBGPEAUHINSTANCE__@@@Z; CAppListTileElement::SetDescription(ushort const *,HINSTANCE__ *)
0x1802621ab  mov     rcx, [rsp+130h+var_F8]; pv
0x1802621b0  call    cs:__imp_CoTaskMemFree
0x1802621b6  lea     rdi, [rsi+1B8h]
0x1802621bd  mov     rcx, [rdi]; pv
0x1802621c0  call    cs:__imp_CoTaskMemFree
0x1802621c6  movups  xmm0, xmmword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x1802621cd  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x1802621d3  lea     rdx, [rsp+130h+var_E0]
0x1802621d8  mov     r8, rdi
0x1802621db  mov     [rsp+130h+var_D0], eax
0x1802621df  lea     rcx, [rsp+130h+var_F0]
0x1802621e4  movaps  [rsp+130h+var_E0], xmm0
0x1802621e9  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1802621ee  mov     rcx, rsi
0x1802621f1  test    eax, eax
0x1802621f3  js      short loc_1802621FA
0x1802621f5  mov     rdx, [rdi]
0x1802621f8  jmp     short loc_1802621FF
0x1802621fa  mov     rdx, [rsp+130h+pv]
0x1802621ff  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180262205  mov     rcx, [rsp+130h+pv]; pv
0x18026220a  call    cs:__imp_CoTaskMemFree
0x180262210  test    ebx, ebx
0x180262212  js      short loc_180262258
0x180262214  lea     rcx, aIcon; "Icon"
0x18026221b  call    cs:__imp_StrToID
0x180262221  movzx   edx, ax
0x180262224  mov     rcx, rsi
0x180262227  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18026222d  lea     rdx, [rsp+130h+var_F8]
0x180262232  mov     [rsp+130h+var_F8], 0
0x18026223b  mov     rcx, rax
0x18026223e  call    ??$ElementCast@VCShellItemThumbnailElement@@@@YAJPEAVElement@DirectUI@@PEAPEAVCShellItemThumbnailElement@@@Z; ElementCast<CShellItemThumbnailElement>(DirectUI::Element *,CShellItemThumbnailElement * *)
0x180262243  mov     ebx, eax
0x180262245  test    eax, eax
0x180262247  js      short loc_180262258
0x180262249  mov     rdx, [r15]; struct IShellItem *
0x18026224c  mov     rcx, [rsp+130h+var_F8]; this
0x180262251  call    ?SetShellItem@CShellItemThumbnailElement@@QEAAJPEAUIShellItem@@@Z; CShellItemThumbnailElement::SetShellItem(IShellItem *)
0x180262256  mov     ebx, eax
0x180262258  lea     rcx, [rsp+130h+var_F0]; this
0x18026225d  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x180262262  test    ebx, ebx
0x180262264  js      loc_180262342
0x18026226a  mov     rcx, rsi
0x18026226d  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x180262272  mov     ecx, 1Bh
0x180262277  cmp     eax, 6
0x18026227a  lea     edx, [rcx-18h]
0x18026227d  cmovnz  ecx, edx
0x180262280  lea     rdx, [rsp+130h+pv]
0x180262285  mov     dword ptr [rsp+130h+pv], ecx
0x180262289  lea     rcx, [rsp+130h+var_F8]
0x18026228e  call    ??$Make@VCTileActivateBehavior@@AEAW4ACTIVATION_TRIGGER_FLAGS@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCTileActivateBehavior@@@12@AEAW4ACTIVATION_TRIGGER_FLAGS@@@Z; Microsoft::WRL::Details::Make<CTileActivateBehavior,ACTIVATION_TRIGGER_FLAGS &>(ACTIVATION_TRIGGER_FLAGS &)
0x180262293  xor     ecx, ecx
0x180262295  lea     rdx, [rsp+130h+var_C0]
0x18026229a  cmp     rdx, rax
0x18026229d  jz      short loc_1802622A9
0x18026229f  mov     rcx, [rax]
0x1802622a2  mov     qword ptr [rax], 0
0x1802622a9  mov     rax, [rsi+188h]
0x1802622b0  mov     [rsi+188h], rcx
0x1802622b7  test    rax, rax
0x1802622ba  jz      short loc_1802622C4
0x1802622bc  mov     rcx, rax
0x1802622bf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehavior@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(void)
0x1802622c4  mov     rcx, [rsp+130h+var_F8]
0x1802622c9  test    rcx, rcx
0x1802622cc  jz      short loc_1802622DC
0x1802622ce  mov     [rsp+130h+var_F8], 0
0x1802622d7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehavior@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(void)
0x1802622dc  mov     rax, [rsi+188h]
0x1802622e3  test    rax, rax
0x1802622e6  jnz     short loc_1802622EF
0x1802622e8  mov     ebx, 8007000Eh
0x1802622ed  jmp     short loc_180262342
0x1802622ef  mov     byte ptr [rax+1Ch], 1
0x1802622f3  mov     rcx, rsi
0x1802622f6  mov     rdx, [rsi+188h]
0x1802622fd  call    cs:__imp_?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z; DirectUI::Element::AddBehavior(IDuiBehavior *)
0x180262303  mov     ebx, eax
0x180262305  test    eax, eax
0x180262307  js      short loc_180262342
0x180262309  mov     rcx, rsi; this
0x18026230c  call    ?_InitializeRearrange@CAppListTileElement@@AEAAJXZ; CAppListTileElement::_InitializeRearrange(void)
0x180262311  mov     ebx, eax
0x180262313  test    eax, eax
0x180262315  js      short loc_180262342
0x180262317  mov     rcx, rsi
0x18026231a  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x18026231f  test    eax, eax
0x180262321  jz      short loc_18026232D
0x180262323  sub     eax, 1
0x180262326  jz      short loc_18026232D
0x180262328  cmp     eax, 7
0x18026232b  jnz     short loc_18026233B
0x18026232d  mov     rcx, rsi; this
0x180262330  call    ?_InitContextMenu@CAppListTileElement@@AEAAJXZ; CAppListTileElement::_InitContextMenu(void)
0x180262335  mov     ebx, eax
0x180262337  test    eax, eax
0x180262339  js      short loc_180262342
0x18026233b  mov     byte ptr [rsi+1C8h], 1
0x180262342  mov     eax, ebx
0x180262344  mov     rcx, [rbp+30h+var_30]
0x180262348  xor     rcx, rsp; StackCookie
0x18026234b  call    __security_check_cookie
0x180262350  mov     rbx, [rsp+130h+arg_10]
0x180262358  add     rsp, 110h
0x18026235f  pop     r15
0x180262361  pop     r14
0x180262363  pop     rdi
0x180262364  pop     rsi
0x180262365  pop     rbp
0x180262366  retn
```
