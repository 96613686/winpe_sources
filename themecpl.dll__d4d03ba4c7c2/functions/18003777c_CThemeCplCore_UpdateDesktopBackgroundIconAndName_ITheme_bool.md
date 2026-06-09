# CThemeCplCore::_UpdateDesktopBackgroundIconAndName(ITheme *,bool)

- ea: `0x18003777c`
- end: `0x180037b84`
- name: `?_UpdateDesktopBackgroundIconAndName@CThemeCplCore@@AEAAJPEAUITheme@@_N@Z`
- size: `1032`
- prototype: `__int64 __fastcall(CThemeCplCore *this, struct ITheme *, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180037f18`

## callees

- `0x18000268c`
- `0x18002033c`
- `0x180035a44`
- `0x18003605c`
- `0x180036134`
- `0x18003621c`
- `0x18003777c`
- `0x180044cc0`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x1800377ab`
- `SHELL32!__imp_SHRestricted` at `0x1800377ab`
- `SHLWAPI!PathRemoveExtensionW` at `0x180037908`
- `SHLWAPI!PathRemoveExtensionW` at `0x180037908`
- `SHLWAPI!PathFindFileNameW` at `0x1800378f1`
- `SHLWAPI!PathFindFileNameW` at `0x1800378f1`
- `SHLWAPI!__imp_IsOS` at `0x180037893`
- `SHLWAPI!__imp_IsOS` at `0x1800378c3`
- `SHLWAPI!__imp_IsOS` at `0x180037893`
- `SHLWAPI!__imp_IsOS` at `0x1800378c3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180037a10`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180037a10`
- `OLEAUT32!__imp_SysAllocString` at `0x180037925`
- `OLEAUT32!__imp_SysAllocString` at `0x180037925`
- `OLEAUT32!__imp_SysFreeString` at `0x180037871`
- `OLEAUT32!__imp_SysFreeString` at `0x180037916`
- `OLEAUT32!__imp_SysFreeString` at `0x18003794f`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b45`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b56`
- `OLEAUT32!__imp_SysFreeString` at `0x180037871`
- `OLEAUT32!__imp_SysFreeString` at `0x180037916`
- `OLEAUT32!__imp_SysFreeString` at `0x18003794f`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b45`
- `OLEAUT32!__imp_SysFreeString` at `0x180037b56`
- `OLEAUT32!__imp_SysStringLen` at `0x18003785b`
- `OLEAUT32!__imp_SysStringLen` at `0x18003785b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800379a5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180037b14`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800379a5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180037b14`
- `DUI70!StrToID` at `0x180037993`
- `DUI70!StrToID` at `0x180037b02`
- `DUI70!StrToID` at `0x180037993`
- `DUI70!StrToID` at `0x180037b02`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180037b33`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180037b33`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800379c6`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800379c6`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180037a63`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180037a63`

## pseudocode

```c
__int64 __fastcall CThemeCplCore::_UpdateDesktopBackgroundIconAndName(CThemeCplCore *this, struct ITheme *a2, char a3)
{
  signed int v5; // esi
  HINSTANCE v6; // rdx
  unsigned int v7; // r8d
  HINSTANCE v8; // rdx
  HINSTANCE v9; // rdx
  unsigned int v10; // r8d
  WCHAR *FileNameW; // rax
  const OLECHAR *v12; // rbx
  int v13; // ecx
  OLECHAR *v14; // rbx
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v16; // rbx
  unsigned __int16 v17; // ax
  char *v18; // rdi
  __int64 v19; // rbx
  DirectUI::Element *v20; // rcx
  const struct _GUID *v21; // rdx
  const struct _GUID *v22; // r8
  const struct _GUID *v23; // r9
  DirectUI::Element *v24; // rax
  DirectUI::Element *v25; // rbx
  unsigned __int16 v26; // ax
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-18h] BYREF
  void *v30; // [rsp+40h] [rbp-10h] BYREF
  int v31; // [rsp+90h] [rbp+40h] BYREF
  int v32; // [rsp+98h] [rbp+48h] BYREF

  if ( !a3 )
  {
    v5 = 0;
    if ( SHRestricted(REST_NOCHANGINGWALLPAPER) )
      return (unsigned int)v5;
  }
  pbstr = 0;
  bstrString = 0;
  v31 = 0;
  v32 = 0;
  if ( !(unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow()
    && (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 264LL))(a2, &v31) >= 0
    && v31 )
  {
    v7 = 21;
LABEL_10:
    ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, v6, v7);
    v5 = 0;
    goto LABEL_24;
  }
  if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 432LL))(a2, &v32) >= 0 && v32 )
  {
    v7 = 27;
    goto LABEL_10;
  }
  v5 = (*(__int64 (__fastcall **)(struct ITheme *, BSTR *))(*(_QWORD *)a2 + 168LL))(a2, &pbstr);
  if ( v5 >= 0 && SysStringLen(pbstr) )
  {
    SysFreeString(0);
    bstrString = 0;
    if ( IsDefaultBackground(pbstr) )
    {
      v10 = IsOS(0x1Du) ? 632 : 635;
    }
    else
    {
      if ( !IsDefaultBackgroundDark(pbstr) )
      {
        FileNameW = PathFindFileNameW(pbstr);
        v12 = FileNameW;
        if ( FileNameW )
        {
          PathRemoveExtensionW(FileNameW);
          SysFreeString(0);
          bstrString = SysAllocString(v12);
          if ( !bstrString )
            ATL::AtlThrowImpl(v13);
        }
        else
        {
          v14 = pbstr;
          pbstr = 0;
          if ( v14 )
          {
            SysFreeString(0);
            bstrString = v14;
          }
        }
        goto LABEL_24;
      }
      v10 = IsOS(0x1Du) ? 632 : 636;
    }
    ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, v9, v10);
  }
  else
  {
    v5 = !ATL::CComBSTR::LoadStringW((ATL::CComBSTR *)&bstrString, v8, 0x16u) ? 0x80004005 : 0;
  }
LABEL_24:
  Descendent = (DirectUI::Element *)*((_QWORD *)this + 22);
  if ( Descendent
    || (v16 = (DirectUI::Element *)*((_QWORD *)this + 3),
        v17 = StrToID(L"DesktopBackgroundIcon"),
        Descendent = DirectUI::Element::FindDescendent(v16, v17),
        (*((_QWORD *)this + 22) = Descendent) != 0) )
  {
    DirectUI::Element::SetBackgroundColor(Descendent, 0);
    v18 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v18;
    if ( v18 )
    {
      v19 = *((_QWORD *)this + 22);
      *(_QWORD *)v18 = &CFrameWorkItem::`vftable';
      *((_QWORD *)v18 + 1) = 1;
      *((_DWORD *)v18 + 4) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
      *(_QWORD *)v18 = &CThemeCplBackgroundIconWorkItem::`vftable'{for `CFrameWorkItem'};
      *((_QWORD *)v18 + 8) = &CThemeCplBackgroundIconWorkItem::`vftable'{for `DirectUI::IElementListener'};
      *((_QWORD *)v18 + 9) = v19;
      *((_QWORD *)v18 + 10) = 0;
      *((_QWORD *)v18 + 11) = 0;
      v18[96] = 0;
      _InterlockedIncrement(&g_cLocks);
    }
    else
    {
      v18 = 0;
    }
    if ( v18 )
    {
      v20 = (DirectUI::Element *)*((_QWORD *)v18 + 9);
      if ( v20 )
      {
        if ( (int)DirectUI::Element::AddListener(v20, (struct DirectUI::IElementListener *)(v18 + 64)) >= 0 )
        {
          v18[96] = 1;
          if ( (*(int (__fastcall **)(struct ITheme *, char *))(*(_QWORD *)a2 + 584LL))(a2, v18 + 80) >= 0 )
          {
            v30 = 0;
            v5 = IUnknown_QueryServiceObject(*((struct IUnknown **)this + 5), v21, v22, v23, &v30);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(void *, char *, GUID *, _QWORD))(*(_QWORD *)v30 + 24LL))(
                     v30,
                     v18,
                     &GUID_8f2751df_00b1_4860_8199_890906187fe4,
                     0);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
            }
          }
        }
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  v24 = (DirectUI::Element *)*((_QWORD *)this + 23);
  if ( v24
    || (v25 = (DirectUI::Element *)*((_QWORD *)this + 3),
        v26 = StrToID(L"DesktopBackgroundName"),
        v24 = DirectUI::Element::FindDescendent(v25, v26),
        (*((_QWORD *)this + 23) = v24) != 0) )
  {
    v5 = DirectUI::Element::SetContentString(v24, bstrString);
  }
  SysFreeString(bstrString);
  SysFreeString(pbstr);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003777c  mov     [rsp-28h+arg_0], rbx
0x180037781  mov     [rsp-28h+arg_8], rsi
0x180037786  push    rbp
0x180037787  push    rdi
0x180037788  push    r12
0x18003778a  push    r14
0x18003778c  push    r15
0x18003778e  mov     rbp, rsp
0x180037791  sub     rsp, 50h
0x180037795  mov     r15, rdx
0x180037798  mov     r14, rcx
0x18003779b  xor     r12d, r12d
0x18003779e  test    r8b, r8b
0x1800377a1  jnz     short loc_1800377BF
0x1800377a3  mov     esi, r12d
0x1800377a6  mov     ecx, 40000011h; rest
0x1800377ab  call    cs:__imp_SHRestricted
0x1800377b2  nop     dword ptr [rax+rax+00h]
0x1800377b7  test    eax, eax
0x1800377b9  jnz     loc_180037B62
0x1800377bf  mov     [rbp+pbstr], r12
0x1800377c3  mov     [rbp+bstrString], r12
0x1800377c7  mov     [rbp+arg_10], r12d
0x1800377cb  mov     [rbp+arg_18], r12d
0x1800377cf  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x1800377d4  test    eax, eax
0x1800377d6  jnz     short loc_180037800
0x1800377d8  mov     rax, [r15]
0x1800377db  lea     rdx, [rbp+arg_10]
0x1800377df  mov     rcx, r15
0x1800377e2  mov     rax, [rax+108h]
0x1800377e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377ee  test    eax, eax
0x1800377f0  js      short loc_180037800
0x1800377f2  cmp     [rbp+arg_10], r12d
0x1800377f6  jz      short loc_180037800
0x1800377f8  mov     r8d, 15h
0x1800377fe  jmp     short loc_180037826
0x180037800  mov     rax, [r15]
0x180037803  lea     rdx, [rbp+arg_18]
0x180037807  mov     rcx, r15
0x18003780a  mov     rax, [rax+1B0h]
0x180037811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037816  test    eax, eax
0x180037818  js      short loc_180037837
0x18003781a  cmp     [rbp+arg_18], r12d
0x18003781e  jz      short loc_180037837
0x180037820  mov     r8d, 1Bh; unsigned int
0x180037826  lea     rcx, [rbp+bstrString]; this
0x18003782a  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18003782f  mov     esi, r12d
0x180037832  jmp     loc_18003797C
0x180037837  mov     rax, [r15]
0x18003783a  lea     rdx, [rbp+pbstr]
0x18003783e  mov     rcx, r15
0x180037841  mov     rax, [rax+0A8h]
0x180037848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003784d  mov     esi, eax
0x18003784f  test    eax, eax
0x180037851  js      loc_180037961
0x180037857  mov     rcx, [rbp+pbstr]; pbstr
0x18003785b  call    cs:__imp_SysStringLen
0x180037862  nop     dword ptr [rax+rax+00h]
0x180037867  test    eax, eax
0x180037869  jz      loc_180037961
0x18003786f  xor     ecx, ecx; bstrString
0x180037871  call    cs:__imp_SysFreeString
0x180037878  nop     dword ptr [rax+rax+00h]
0x18003787d  mov     [rbp+bstrString], r12
0x180037881  mov     rcx, [rbp+pbstr]; lpString1
0x180037885  call    ?IsDefaultBackground@@YA_NPEBG@Z; IsDefaultBackground(ushort const *)
0x18003788a  test    al, al
0x18003788c  jz      short loc_1800378B1
0x18003788e  mov     ecx, 1Dh; dwOS
0x180037893  call    cs:__imp_IsOS
0x18003789a  nop     dword ptr [rax+rax+00h]
0x18003789f  neg     eax
0x1800378a1  sbb     r8d, r8d
0x1800378a4  and     r8d, 0FFFFFFFDh
0x1800378a8  add     r8d, 27Bh
0x1800378af  jmp     short loc_1800378DF
0x1800378b1  mov     rcx, [rbp+pbstr]; lpString1
0x1800378b5  call    ?IsDefaultBackgroundDark@@YA_NPEBG@Z; IsDefaultBackgroundDark(ushort const *)
0x1800378ba  test    al, al
0x1800378bc  jz      short loc_1800378ED
0x1800378be  mov     ecx, 1Dh; dwOS
0x1800378c3  call    cs:__imp_IsOS
0x1800378ca  nop     dword ptr [rax+rax+00h]
0x1800378cf  neg     eax
0x1800378d1  sbb     r8d, r8d
0x1800378d4  and     r8d, 0FFFFFFFCh
0x1800378d8  add     r8d, 27Ch; unsigned int
0x1800378df  lea     rcx, [rbp+bstrString]; this
0x1800378e3  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x1800378e8  jmp     loc_18003797C
0x1800378ed  mov     rcx, [rbp+pbstr]; pszPath
0x1800378f1  call    cs:__imp_PathFindFileNameW
0x1800378f8  nop     dword ptr [rax+rax+00h]
0x1800378fd  mov     rbx, rax
0x180037900  test    rax, rax
0x180037903  jz      short loc_180037940
0x180037905  mov     rcx, rax; pszPath
0x180037908  call    cs:__imp_PathRemoveExtensionW
0x18003790f  nop     dword ptr [rax+rax+00h]
0x180037914  xor     ecx, ecx; bstrString
0x180037916  call    cs:__imp_SysFreeString
0x18003791d  nop     dword ptr [rax+rax+00h]
0x180037922  mov     rcx, rbx; psz
0x180037925  call    cs:__imp_SysAllocString
0x18003792c  nop     dword ptr [rax+rax+00h]
0x180037931  mov     [rbp+bstrString], rax
0x180037935  test    rax, rax
0x180037938  jz      loc_180037B7E
0x18003793e  jmp     short loc_18003797C
0x180037940  mov     rbx, [rbp+pbstr]
0x180037944  mov     [rbp+pbstr], r12
0x180037948  test    rbx, rbx
0x18003794b  jz      short loc_18003797C
0x18003794d  xor     ecx, ecx; bstrString
0x18003794f  call    cs:__imp_SysFreeString
0x180037956  nop     dword ptr [rax+rax+00h]
0x18003795b  mov     [rbp+bstrString], rbx
0x18003795f  jmp     short loc_18003797C
0x180037961  mov     r8d, 16h; unsigned int
0x180037967  lea     rcx, [rbp+bstrString]; this
0x18003796b  call    ?LoadStringW@CComBSTR@ATL@@QEAA_NPEAUHINSTANCE__@@I@Z; ATL::CComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x180037970  neg     al
0x180037972  sbb     esi, esi
0x180037974  not     esi
0x180037976  and     esi, 80004005h
0x18003797c  mov     rax, [r14+0B0h]
0x180037983  test    rax, rax
0x180037986  jnz     short loc_1800379C1
0x180037988  mov     rbx, [r14+18h]
0x18003798c  lea     rcx, aDesktopbackgro_1; "DesktopBackgroundIcon"
0x180037993  call    cs:__imp_StrToID
0x18003799a  nop     dword ptr [rax+rax+00h]
0x18003799f  movzx   edx, ax
0x1800379a2  mov     rcx, rbx
0x1800379a5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800379ac  nop     dword ptr [rax+rax+00h]
0x1800379b1  mov     [r14+0B0h], rax
0x1800379b8  test    rax, rax
0x1800379bb  jz      loc_180037AEB
0x1800379c1  xor     edx, edx
0x1800379c3  mov     rcx, rax
0x1800379c6  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x1800379cd  nop     dword ptr [rax+rax+00h]
0x1800379d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800379d9  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800379de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800379e3  mov     rdi, rax
0x1800379e6  mov     [rbp+var_10], rax
0x1800379ea  test    rax, rax
0x1800379ed  jz      short loc_180037A4A
0x1800379ef  mov     rbx, [r14+0B0h]
0x1800379f6  lea     rax, ??_7CFrameWorkItem@@6B@; const CFrameWorkItem::`vftable'
0x1800379fd  mov     [rdi], rax
0x180037a00  mov     qword ptr [rdi+8], 1
0x180037a08  mov     [rdi+10h], r12d
0x180037a0c  lea     rcx, [rdi+18h]; lpCriticalSection
0x180037a10  call    cs:__imp_InitializeCriticalSection
0x180037a17  nop     dword ptr [rax+rax+00h]
0x180037a1c  lea     rax, ??_7CThemeCplBackgroundIconWorkItem@@6BCFrameWorkItem@@@; const CThemeCplBackgroundIconWorkItem::`vftable'{for `CFrameWorkItem'}
0x180037a23  mov     [rdi], rax
0x180037a26  lea     rax, ??_7CThemeCplBackgroundIconWorkItem@@6BIElementListener@DirectUI@@@; const CThemeCplBackgroundIconWorkItem::`vftable'{for `DirectUI::IElementListener'}
0x180037a2d  mov     [rdi+40h], rax
0x180037a31  mov     [rdi+48h], rbx
0x180037a35  mov     [rdi+50h], r12
0x180037a39  mov     [rdi+58h], r12
0x180037a3d  mov     [rdi+60h], r12b
0x180037a41  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180037a48  jmp     short loc_180037A4D
0x180037a4a  mov     rdi, r12
0x180037a4d  test    rdi, rdi
0x180037a50  jz      loc_180037AEB
0x180037a56  mov     rcx, [rdi+48h]
0x180037a5a  test    rcx, rcx
0x180037a5d  jz      short loc_180037ADC
0x180037a5f  lea     rdx, [rdi+40h]
0x180037a63  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180037a6a  nop     dword ptr [rax+rax+00h]
0x180037a6f  test    eax, eax
0x180037a71  js      short loc_180037ADC
0x180037a73  mov     byte ptr [rdi+60h], 1
0x180037a77  mov     rax, [r15]
0x180037a7a  lea     rdx, [rdi+50h]
0x180037a7e  mov     rcx, r15
0x180037a81  mov     rax, [rax+248h]
0x180037a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a8d  test    eax, eax
0x180037a8f  js      short loc_180037ADC
0x180037a91  mov     [rbp+var_10], r12
0x180037a95  lea     rax, [rbp+var_10]
0x180037a99  mov     [rsp+50h+var_30], rax; void **
0x180037a9e  mov     rcx, [r14+28h]; struct IUnknown *
0x180037aa2  call    ?IUnknown_QueryServiceObject@@YAJPEAUIUnknown@@AEBU_GUID@@11PEAPEAX@Z; IUnknown_QueryServiceObject(IUnknown *,_GUID const &,_GUID const &,_GUID const &,void * *)
0x180037aa7  mov     esi, eax
0x180037aa9  test    eax, eax
0x180037aab  js      short loc_180037ADC
0x180037aad  mov     rcx, [rbp+var_10]
0x180037ab1  mov     rax, [rcx]
0x180037ab4  xor     r9d, r9d
0x180037ab7  lea     r8, _GUID_8f2751df_00b1_4860_8199_890906187fe4
0x180037abe  mov     rdx, rdi
0x180037ac1  mov     rax, [rax+18h]
0x180037ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aca  mov     esi, eax
0x180037acc  mov     rcx, [rbp+var_10]
0x180037ad0  mov     rax, [rcx]
0x180037ad3  mov     rax, [rax+10h]
0x180037ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037adc  mov     rax, [rdi]
0x180037adf  mov     rcx, rdi
0x180037ae2  mov     rax, [rax+10h]
0x180037ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aeb  mov     rax, [r14+0B8h]
0x180037af2  test    rax, rax
0x180037af5  jnz     short loc_180037B2C
0x180037af7  mov     rbx, [r14+18h]
0x180037afb  lea     rcx, aDesktopbackgro_0; "DesktopBackgroundName"
0x180037b02  call    cs:__imp_StrToID
0x180037b09  nop     dword ptr [rax+rax+00h]
0x180037b0e  movzx   edx, ax
0x180037b11  mov     rcx, rbx
0x180037b14  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180037b1b  nop     dword ptr [rax+rax+00h]
0x180037b20  mov     [r14+0B8h], rax
0x180037b27  test    rax, rax
0x180037b2a  jz      short loc_180037B41
0x180037b2c  mov     rdx, [rbp+bstrString]
0x180037b30  mov     rcx, rax
0x180037b33  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180037b3a  nop     dword ptr [rax+rax+00h]
0x180037b3f  mov     esi, eax
0x180037b41  mov     rcx, [rbp+bstrString]; bstrString
0x180037b45  call    cs:__imp_SysFreeString
0x180037b4c  nop     dword ptr [rax+rax+00h]
0x180037b51  nop
0x180037b52  mov     rcx, [rbp+pbstr]; bstrString
0x180037b56  call    cs:__imp_SysFreeString
0x180037b5d  nop     dword ptr [rax+rax+00h]
0x180037b62  mov     eax, esi
0x180037b64  lea     r11, [rsp+50h+var_s0]
0x180037b69  mov     rbx, [r11+30h]
0x180037b6d  mov     rsi, [r11+38h]
0x180037b71  mov     rsp, r11
0x180037b74  pop     r15
0x180037b76  pop     r14
0x180037b78  pop     r12
0x180037b7a  pop     rdi
0x180037b7b  pop     rbp
0x180037b7c  retn
0x180037b7e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
