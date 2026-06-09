# Windows::Internal::CPopupWindowImpl::SetAppItem(IShellItem *)

- ea: `0x180094690`
- end: `0x180094a17`
- name: `?SetAppItem@CPopupWindowImpl@Internal@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `903`
- prototype: `int(Windows::Internal::CPopupWindowImpl *__hidden this, struct IShellItem *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000af00`
- `0x18003a074`
- `0x180054130`
- `0x18009080c`
- `0x180090820`
- `0x1800908e8`
- `0x18009224c`
- `0x1800933c4`
- `0x180094690`
- `0x1800e4f74`
- `0x1800e5034`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800948fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009497c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800948fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009497c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180094704`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800949c8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180094704`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800949c8`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800946c0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180094937`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800946c0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180094937`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800949d9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800949d9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800946e8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800946e8`
- `DUI70!StrToID` at `0x1800946d6`
- `DUI70!StrToID` at `0x1800946d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::CPopupWindowImpl::SetAppItem(
        Windows::Internal::CPopupWindowImpl *this,
        struct IShellItem *a2)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v7; // r8
  DirectUI::Element *v8; // rsi
  int As; // ebx
  unsigned int v10; // eax
  struct DirectUI::Element *v11; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // edx
  CShellItemThumbnailElement *v15; // r14
  unsigned int v17; // [rsp+30h] [rbp-99h] BYREF
  int v18; // [rsp+34h] [rbp-95h] BYREF
  __int64 v19; // [rsp+38h] [rbp-91h] BYREF
  PROPERTYKEY v20; // [rsp+40h] [rbp-89h] BYREF
  __int64 v21; // [rsp+60h] [rbp-69h] BYREF
  __int64 v22; // [rsp+68h] [rbp-61h]
  __int64 v23; // [rsp+70h] [rbp-59h]
  LPVOID pv; // [rsp+78h] [rbp-51h] BYREF
  __int128 v25; // [rsp+80h] [rbp-49h] BYREF
  int v26; // [rsp+90h] [rbp-39h]
  __int128 v27; // [rsp+94h] [rbp-35h]
  int v28; // [rsp+A4h] [rbp-25h]
  __int128 v29; // [rsp+A8h] [rbp-21h]
  int v30; // [rsp+B8h] [rbp-11h]
  __int128 v31; // [rsp+BCh] [rbp-Dh]
  int v32; // [rsp+CCh] [rbp+3h]
  PROPERTYKEY v33; // [rsp+D0h] [rbp+7h]

  Element = DirectUI::NativeHWNDHost::GetElement((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
  v5 = StrToID(L"AppIconContainer");
  Descendent = DirectUI::Element::FindDescendent(Element, v5);
  v8 = Descendent;
  if ( a2 )
  {
    v25 = PKEY_Tile_Background;
    v26 = 4;
    v27 = PKEY_Tile_DisplayNameLanguage;
    v28 = 18;
    v29 = PKEY_Tile_Foreground;
    v30 = 5;
    v31 = PKEY_Tile_LongDisplayName;
    v32 = 11;
    v33 = PKEY_ItemNameDisplay;
    v19 = 0;
    As = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v19, a2, v7, &v25);
    if ( As >= 0 )
    {
      v18 = 0;
      v20.fmtid = (GUID)PKEY_Tile_Foreground;
      v20.pid = 5;
      As = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v19, &v20, &v18);
      if ( As >= 0 )
      {
        v18 |= 0xFF000000;
        v17 = 0;
        v20.fmtid = (GUID)PKEY_Tile_Background;
        v20.pid = 4;
        As = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v19, &v20, &v17);
        if ( As >= 0 )
        {
          v10 = v17 | 0xFF000000;
          v17 |= 0xFF000000;
          if ( (*((_DWORD *)this + 21) & 0x8000000) == 0 )
          {
            v21 = 0;
            v22 = 0;
            v23 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
            v22 = -1;
            v23 = -1;
            v20.fmtid = (GUID)PKEY_Tile_LongDisplayName;
            v20.pid = 11;
            if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &v21) >= 0
              || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21),
                  v22 = -1,
                  v23 = -1,
                  v20 = PKEY_ItemNameDisplay,
                  As = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &v21),
                  As >= 0) )
            {
              As = (*(__int64 (__fastcall **)(Windows::Internal::CPopupWindowImpl *, __int64))(*(_QWORD *)this + 176LL))(
                     this,
                     v21);
              if ( As >= 0 )
              {
                pv = 0;
                CoTaskMemFree(0);
                v20.fmtid = (GUID)PKEY_Tile_DisplayNameLanguage;
                v20.pid = 18;
                if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &pv) >= 0 )
                {
                  v11 = DirectUI::NativeHWNDHost::GetElement((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
                  DUI_SetDescendentElementPreferredFont(v11, v12, (const unsigned __int16 *)pv);
                }
                v13 = FindDescendentElement<CShellItemThumbnailElement>(v8);
                v15 = (CShellItemThumbnailElement *)v13;
                if ( v13 )
                {
                  shell::TaskScheduler::RemoveTasks(*(shell::TaskScheduler **)(v13 + 216), v14);
                  As = CShellItemThumbnailElement::_AsyncPopulateListIcon(v15, a2);
                }
                CoTaskMemFree(pv);
              }
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
            if ( As < 0 )
              goto LABEL_19;
            v10 = v17;
          }
          *((_DWORD *)this + 71) = v10;
          *((_DWORD *)this + 66) = v10;
          *((_DWORD *)this + 67) = v18;
          *((_DWORD *)this + 72) = 7;
          if ( v8 )
          {
            DirectUI::Element::SetLayoutPos(v8, *((_DWORD *)this + 84));
            DirectUI::Element::SetVisible(v8, 1);
          }
        }
      }
    }
LABEL_19:
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&v19);
    return (unsigned int)As;
  }
  As = 0;
  DirectUI::Element::SetLayoutPos(Descendent, -3);
  return (unsigned int)As;
}

```

## disassembly

```asm
0x180094690  mov     [rsp-8+arg_10], rbx
0x180094695  push    rbp
0x180094696  push    rsi
0x180094697  push    rdi
0x180094698  push    r14
0x18009469a  push    r15
0x18009469c  lea     rbp, [rsp-37h]
0x1800946a1  sub     rsp, 100h
0x1800946a8  mov     rax, cs:__security_cookie
0x1800946af  xor     rax, rsp
0x1800946b2  mov     [rbp+57h+var_30], rax
0x1800946b6  mov     r15, rdx
0x1800946b9  mov     rdi, rcx
0x1800946bc  add     rcx, 0FFFFFFFFFFFFFFC8h
0x1800946c0  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x1800946c7  nop     dword ptr [rax+rax+00h]
0x1800946cc  mov     rbx, rax
0x1800946cf  lea     rcx, aAppiconcontain; "AppIconContainer"
0x1800946d6  call    cs:__imp_StrToID
0x1800946dd  nop     dword ptr [rax+rax+00h]
0x1800946e2  movzx   edx, ax
0x1800946e5  mov     rcx, rbx
0x1800946e8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800946ef  nop     dword ptr [rax+rax+00h]
0x1800946f4  mov     rsi, rax
0x1800946f7  test    r15, r15
0x1800946fa  jnz     short loc_180094715
0x1800946fc  xor     ebx, ebx
0x1800946fe  lea     edx, [rbx-3]
0x180094701  mov     rcx, rax
0x180094704  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18009470b  nop     dword ptr [rax+rax+00h]
0x180094710  jmp     loc_1800949F1
0x180094715  movups  xmm0, cs:PKEY_Tile_Background
0x18009471c  movaps  [rbp+57h+var_A0], xmm0
0x180094720  mov     eax, cs:dword_180109028
0x180094726  mov     [rbp+57h+var_90], eax
0x180094729  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x180094730  movups  [rbp+57h+var_8C], xmm0
0x180094734  mov     eax, cs:dword_180109040
0x18009473a  mov     [rbp+57h+var_7C], eax
0x18009473d  movups  xmm0, cs:PKEY_Tile_Foreground
0x180094744  movups  [rbp+57h+var_78], xmm0
0x180094748  mov     eax, cs:dword_180109058
0x18009474e  mov     [rbp+57h+var_68], eax
0x180094751  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x180094758  movups  [rbp+57h+var_64], xmm0
0x18009475c  mov     eax, cs:dword_180109070
0x180094762  mov     [rbp+57h+var_54], eax
0x180094765  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18009476c  movaps  [rbp+57h+var_50], xmm0
0x180094770  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x180094776  mov     [rbp+57h+var_40], eax
0x180094779  mov     [rsp+120h+var_E8], 0
0x180094782  lea     r9, [rbp+57h+var_A0]
0x180094786  mov     rdx, r15
0x180094789  lea     rcx, [rsp+120h+var_E8]
0x18009478e  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180094793  mov     ebx, eax
0x180094795  test    eax, eax
0x180094797  js      loc_1800949E6
0x18009479d  mov     [rsp+120h+var_EC], 0
0x1800947a5  movups  xmm0, cs:PKEY_Tile_Foreground
0x1800947ac  movaps  [rsp+120h+var_E0], xmm0
0x1800947b1  mov     eax, cs:dword_180109058
0x1800947b7  mov     [rbp+57h+var_D0], eax
0x1800947ba  lea     r8, [rsp+120h+var_EC]
0x1800947bf  lea     rdx, [rsp+120h+var_E0]
0x1800947c4  lea     rcx, [rsp+120h+var_E8]
0x1800947c9  call    ??$GetAsUInt32@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x1800947ce  mov     ebx, eax
0x1800947d0  test    eax, eax
0x1800947d2  js      loc_1800949E6
0x1800947d8  or      [rsp+120h+var_EC], 0FF000000h
0x1800947e0  mov     [rsp+120h+var_F0], 0
0x1800947e8  movups  xmm0, cs:PKEY_Tile_Background
0x1800947ef  movaps  [rsp+120h+var_E0], xmm0
0x1800947f4  mov     eax, cs:dword_180109028
0x1800947fa  mov     [rbp+57h+var_D0], eax
0x1800947fd  lea     r8, [rsp+120h+var_F0]
0x180094802  lea     rdx, [rsp+120h+var_E0]
0x180094807  lea     rcx, [rsp+120h+var_E8]
0x18009480c  call    ??$GetAsUInt32@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180094811  mov     ebx, eax
0x180094813  test    eax, eax
0x180094815  js      loc_1800949E6
0x18009481b  mov     eax, [rsp+120h+var_F0]
0x18009481f  or      eax, 0FF000000h
0x180094824  mov     [rsp+120h+var_F0], eax
0x180094828  test    dword ptr [rdi+54h], 8000000h
0x18009482f  jnz     loc_18009499A
0x180094835  mov     [rbp+57h+var_C0], 0
0x18009483d  mov     [rbp+57h+var_B8], 0
0x180094845  mov     [rbp+57h+var_B0], 0
0x18009484d  lea     rcx, [rbp+57h+var_C0]
0x180094851  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180094856  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009485a  mov     [rbp+57h+var_B8], rbx
0x18009485e  mov     [rbp+57h+var_B0], rbx
0x180094862  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x180094869  movaps  [rsp+120h+var_E0], xmm0
0x18009486e  mov     eax, cs:dword_180109070
0x180094874  mov     [rbp+57h+var_D0], eax
0x180094877  lea     r8, [rbp+57h+var_C0]
0x18009487b  lea     rdx, [rsp+120h+var_E0]
0x180094880  lea     rcx, [rsp+120h+var_E8]
0x180094885  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18009488a  test    eax, eax
0x18009488c  jns     short loc_1800948D1
0x18009488e  lea     rcx, [rbp+57h+var_C0]
0x180094892  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180094897  mov     [rbp+57h+var_B8], rbx
0x18009489b  mov     [rbp+57h+var_B0], rbx
0x18009489f  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x1800948a6  movaps  [rsp+120h+var_E0], xmm0
0x1800948ab  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x1800948b1  mov     [rbp+57h+var_D0], eax
0x1800948b4  lea     r8, [rbp+57h+var_C0]
0x1800948b8  lea     rdx, [rsp+120h+var_E0]
0x1800948bd  lea     rcx, [rsp+120h+var_E8]
0x1800948c2  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1800948c7  mov     ebx, eax
0x1800948c9  test    eax, eax
0x1800948cb  js      loc_180094989
0x1800948d1  mov     rax, [rdi]
0x1800948d4  mov     rdx, [rbp+57h+var_C0]
0x1800948d8  mov     rcx, rdi
0x1800948db  mov     rax, [rax+0B0h]
0x1800948e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948e7  mov     ebx, eax
0x1800948e9  test    eax, eax
0x1800948eb  js      loc_180094989
0x1800948f1  mov     [rbp+57h+pv], 0
0x1800948f9  xor     ecx, ecx; pv
0x1800948fb  call    cs:__imp_CoTaskMemFree
0x180094902  nop     dword ptr [rax+rax+00h]
0x180094907  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x18009490e  movaps  [rsp+120h+var_E0], xmm0
0x180094913  mov     eax, cs:dword_180109040
0x180094919  mov     [rbp+57h+var_D0], eax
0x18009491c  lea     r8, [rbp+57h+pv]
0x180094920  lea     rdx, [rsp+120h+var_E0]
0x180094925  lea     rcx, [rsp+120h+var_E8]
0x18009492a  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18009492f  test    eax, eax
0x180094931  js      short loc_18009494F
0x180094933  lea     rcx, [rdi-38h]
0x180094937  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009493e  nop     dword ptr [rax+rax+00h]
0x180094943  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x180094947  mov     rcx, rax; struct DirectUI::Element *
0x18009494a  call    ?DUI_SetDescendentElementPreferredFont@@YAJPEAVElement@DirectUI@@PEBG1@Z; DUI_SetDescendentElementPreferredFont(DirectUI::Element *,ushort const *,ushort const *)
0x18009494f  mov     rcx, rsi
0x180094952  call    ??$FindDescendentElement@VCShellItemThumbnailElement@@@@YAPEAVCShellItemThumbnailElement@@PEAVElement@DirectUI@@@Z; FindDescendentElement<CShellItemThumbnailElement>(DirectUI::Element *)
0x180094957  mov     r14, rax
0x18009495a  test    rax, rax
0x18009495d  jz      short loc_180094978
0x18009495f  mov     rcx, [rax+0D8h]; this
0x180094966  call    ?RemoveTasks@TaskScheduler@shell@@QEAAJH@Z; shell::TaskScheduler::RemoveTasks(int)
0x18009496b  mov     rdx, r15; struct IShellItem *
0x18009496e  mov     rcx, r14; this
0x180094971  call    ?_AsyncPopulateListIcon@CShellItemThumbnailElement@@AEAAJPEAUIShellItem@@@Z; CShellItemThumbnailElement::_AsyncPopulateListIcon(IShellItem *)
0x180094976  mov     ebx, eax
0x180094978  mov     rcx, [rbp+57h+pv]; pv
0x18009497c  call    cs:__imp_CoTaskMemFree
0x180094983  nop     dword ptr [rax+rax+00h]
0x180094988  nop
0x180094989  lea     rcx, [rbp+57h+var_C0]
0x18009498d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180094992  test    ebx, ebx
0x180094994  js      short loc_1800949E6
0x180094996  mov     eax, [rsp+120h+var_F0]
0x18009499a  mov     [rdi+11Ch], eax
0x1800949a0  mov     [rdi+108h], eax
0x1800949a6  mov     eax, [rsp+120h+var_EC]
0x1800949aa  mov     [rdi+10Ch], eax
0x1800949b0  mov     dword ptr [rdi+120h], 7
0x1800949ba  test    rsi, rsi
0x1800949bd  jz      short loc_1800949E6
0x1800949bf  mov     edx, [rdi+150h]
0x1800949c5  mov     rcx, rsi
0x1800949c8  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800949cf  nop     dword ptr [rax+rax+00h]
0x1800949d4  mov     dl, 1
0x1800949d6  mov     rcx, rsi
0x1800949d9  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800949e0  nop     dword ptr [rax+rax+00h]
0x1800949e5  nop
0x1800949e6  lea     rcx, [rsp+120h+var_E8]; this
0x1800949eb  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1800949f0  nop
0x1800949f1  mov     eax, ebx
0x1800949f3  mov     rcx, [rbp+57h+var_30]
0x1800949f7  xor     rcx, rsp; StackCookie
0x1800949fa  call    __security_check_cookie
0x1800949ff  mov     rbx, [rsp+120h+arg_10]
0x180094a07  add     rsp, 100h
0x180094a0e  pop     r15
0x180094a10  pop     r14
0x180094a12  pop     rdi
0x180094a13  pop     rsi
0x180094a14  pop     rbp
0x180094a15  retn
```
