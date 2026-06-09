# CFinishPageAero::SetWizInfo(void)

- ea: `0x1800112a0`
- end: `0x18001154a`
- name: `?SetWizInfo@CFinishPageAero@@MEAAJXZ`
- size: `682`
- prototype: `__int64 __fastcall(CFinishPageAero *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800112a0`
- `0x18001247c`
- `0x1800124c4`
- `0x1800126bc`
- `0x180024c3c`
- `0x18006088c`
- `0x1800608f0`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180011334`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800113c8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180011334`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800113c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001144f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001146f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001144f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001146f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001141d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001142d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001141d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001142d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011523`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800113f9`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800114a8`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800113f9`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800114a8`
- `DUI70!StrToID` at `0x1800113df`
- `DUI70!StrToID` at `0x18001148e`
- `DUI70!StrToID` at `0x1800114b9`
- `DUI70!StrToID` at `0x1800113df`
- `DUI70!StrToID` at `0x18001148e`
- `DUI70!StrToID` at `0x1800114b9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800113eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001149a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800114c5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800113eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001149a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800114c5`

## pseudocode

```c
__int64 __fastcall CFinishPageAero::SetWizInfo(CFinishPageAero *this, __int64 a2, __int64 a3, int a4)
{
  int v4; // edx
  UINT v6; // r14d
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  UINT v12; // esi
  HRESULT DomainAndName; // eax
  HRESULT CurrentLoggedInInfo; // ebx
  int v15; // r9d
  int v16; // r9d
  CUserAccountWizardBase *v17; // rcx
  const WCHAR *v18; // rcx
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  DirectUI::Element *Descendent; // rax
  int v22; // r9d
  LPWSTR v23; // rcx
  void *v24; // rcx
  DirectUI::Element *v25; // rbx
  unsigned __int16 v26; // ax
  DirectUI::Element *v27; // rax
  DirectUI::Element *v28; // rbx
  unsigned __int16 v29; // ax
  UserTile *v30; // rsi
  const unsigned __int16 *v31; // rdx
  HRESULT v32; // eax
  LPWSTR v33; // rcx
  LPWSTR ppwsz; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR v36; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v38[264]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = *((_DWORD *)this + 22);
  ppwsz = 0;
  v6 = 160;
  v7 = v4 - 1;
  if ( !v7 )
  {
    v17 = (CUserAccountWizardBase *)*((_QWORD *)this + 12);
    pv = 0;
    v12 = 193;
    CurrentLoggedInInfo = CUserAccountWizardBase::GetCurrentLoggedInInfo(v17, &ppwsz, (unsigned __int16 **)&pv);
    if ( CurrentLoggedInInfo >= 0 )
    {
      v18 = (const WCHAR *)(*((_QWORD *)this + 12) + 728LL);
      v36 = 0;
      CurrentLoggedInInfo = SHStrDupW(v18, &v36);
      if ( CurrentLoggedInInfo >= 0 )
      {
        v19 = (DirectUI::Element *)*((_QWORD *)this + 8);
        v20 = StrToID(L"connectedinfosubtitle");
        Descendent = DirectUI::Element::FindDescendent(v19, v20);
        CurrentLoggedInInfo = DirectUI::Element::SetContentString(Descendent, v36);
        CWizardPageBase::CollapseExpand(this, L"connectedinfosubtitle", 1, v22);
      }
      v23 = v36;
      v36 = 0;
      CoTaskMemFree(v23);
    }
    v24 = pv;
    pv = 0;
    CoTaskMemFree(v24);
LABEL_20:
    if ( CurrentLoggedInInfo < 0 )
      goto LABEL_32;
    goto LABEL_21;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
    {
      v12 = 199;
      goto LABEL_9;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 != 2 )
        {
LABEL_23:
          CurrentLoggedInInfo = -2147467259;
          goto LABEL_32;
        }
        v12 = 161;
        DomainAndName = CUserAccountWizardBase::GetDomainAndName(*((CUserAccountWizardBase **)this + 12), &ppwsz);
        goto LABEL_10;
      }
      v12 = 161;
LABEL_9:
      DomainAndName = SHStrDupW((LPCWSTR)(*((_QWORD *)this + 12) + 728LL), &ppwsz);
LABEL_10:
      CurrentLoggedInInfo = DomainAndName;
      goto LABEL_20;
    }
    v12 = 198;
    v6 = 197;
  }
  else
  {
    v12 = 194;
  }
  CWizardPageBase::CollapseExpand(this, L"UserTileControlElement", 0, a4);
  CWizardPageBase::CollapseExpand(this, L"username", 0, v15);
  CWizardPageBase::CollapseExpand(this, L"connectedinfosubtitle", 0, v16);
LABEL_21:
  if ( !LoadStringW(g_hinst, v6, (LPWSTR)this + 52, 256) || !LoadStringW(g_hinst, v12, (LPWSTR)this + 308, 512) )
    goto LABEL_23;
  v25 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v26 = StrToID(L"username");
  v27 = DirectUI::Element::FindDescendent(v25, v26);
  DirectUI::Element::SetContentString(v27, ppwsz);
  v28 = (DirectUI::Element *)*((_QWORD *)this + 8);
  v29 = StrToID(L"UserTileControl");
  v30 = DirectUI::Element::FindDescendent(v28, v29);
  if ( v30 )
  {
    v31 = *(const unsigned __int16 **)(*((_QWORD *)this + 12) + 6688LL);
    if ( v31 && *v31 )
    {
      v32 = UserTile::SetImageURL(v30, v31);
    }
    else
    {
      CurrentLoggedInInfo = _GetDefaultUserPicturePath(v38);
      if ( CurrentLoggedInInfo < 0 )
        goto LABEL_32;
      v32 = UserTile::SetImagePath(v30, v38);
    }
    CurrentLoggedInInfo = v32;
    goto LABEL_32;
  }
  CurrentLoggedInInfo = -2147418113;
LABEL_32:
  v33 = ppwsz;
  ppwsz = 0;
  CoTaskMemFree(v33);
  return (unsigned int)CurrentLoggedInInfo;
}

```

## disassembly

```asm
0x1800112a0  push    rbp
0x1800112a2  push    rbx
0x1800112a3  push    rsi
0x1800112a4  push    rdi
0x1800112a5  push    r14
0x1800112a7  push    r15
0x1800112a9  lea     rbp, [rsp-168h]
0x1800112b1  sub     rsp, 268h
0x1800112b8  mov     rax, cs:__security_cookie
0x1800112bf  xor     rax, rsp
0x1800112c2  mov     [rbp+190h+var_40], rax
0x1800112c9  mov     edx, [rcx+58h]
0x1800112cc  xor     r15d, r15d
0x1800112cf  mov     [rsp+290h+ppwsz], r15
0x1800112d4  mov     rdi, rcx
0x1800112d7  mov     r14d, 0A0h
0x1800112dd  sub     edx, 1
0x1800112e0  jz      loc_180011390
0x1800112e6  sub     edx, 1
0x1800112e9  jz      loc_180011389
0x1800112ef  sub     edx, 1
0x1800112f2  jz      loc_180011382
0x1800112f8  sub     edx, 1
0x1800112fb  jz      short loc_180011341
0x1800112fd  sub     edx, 1
0x180011300  jz      short loc_18001131F
0x180011302  cmp     edx, 2
0x180011305  jnz     loc_180011479
0x18001130b  mov     rcx, [rcx+60h]; this
0x18001130f  lea     rdx, [rsp+290h+ppwsz]; unsigned __int16 **
0x180011314  lea     esi, [r14+1]
0x180011318  call    ?GetDomainAndName@CUserAccountWizardBase@@QEAAJPEAPEAG@Z; CUserAccountWizardBase::GetDomainAndName(ushort * *)
0x18001131d  jmp     short loc_18001133A
0x18001131f  mov     esi, 0A1h
0x180011324  mov     rcx, [rcx+60h]
0x180011328  lea     rdx, [rsp+290h+ppwsz]; ppwsz
0x18001132d  add     rcx, 2D8h; psz
0x180011334  call    cs:__imp_SHStrDupW
0x18001133a  mov     ebx, eax
0x18001133c  jmp     loc_180011433
0x180011341  mov     esi, 0C6h
0x180011346  lea     r14d, [rsi-1]
0x18001134a  xor     r8d, r8d; bool
0x18001134d  lea     rdx, aUsertilecontro; "UserTileControlElement"
0x180011354  call    ?CollapseExpand@CWizardPageBase@@QEAAXPEBG_NH@Z; CWizardPageBase::CollapseExpand(ushort const *,bool,int)
0x180011359  xor     r8d, r8d; bool
0x18001135c  lea     rdx, pszStr2; "username"
0x180011363  mov     rcx, rdi; this
0x180011366  call    ?CollapseExpand@CWizardPageBase@@QEAAXPEBG_NH@Z; CWizardPageBase::CollapseExpand(ushort const *,bool,int)
0x18001136b  xor     r8d, r8d; bool
0x18001136e  lea     rdx, aConnectedinfos_0; "connectedinfosubtitle"
0x180011375  mov     rcx, rdi; this
0x180011378  call    ?CollapseExpand@CWizardPageBase@@QEAAXPEBG_NH@Z; CWizardPageBase::CollapseExpand(ushort const *,bool,int)
0x18001137d  jmp     loc_18001143B
0x180011382  mov     esi, 0C7h
0x180011387  jmp     short loc_180011324
0x180011389  mov     esi, 0C2h
0x18001138e  jmp     short loc_18001134A
0x180011390  mov     rcx, [rcx+60h]; this
0x180011394  lea     r8, [rsp+290h+pv]; unsigned __int16 **
0x180011399  lea     rdx, [rsp+290h+ppwsz]; unsigned __int16 **
0x18001139e  mov     [rsp+290h+pv], r15
0x1800113a3  mov     esi, 0C1h
0x1800113a8  call    ?GetCurrentLoggedInInfo@CUserAccountWizardBase@@QEAAJPEAPEAG0@Z; CUserAccountWizardBase::GetCurrentLoggedInInfo(ushort * *,ushort * *)
0x1800113ad  mov     ebx, eax
0x1800113af  test    eax, eax
0x1800113b1  js      short loc_180011423
0x1800113b3  mov     rcx, [rdi+60h]
0x1800113b7  lea     rdx, [rsp+290h+var_268]; ppwsz
0x1800113bc  add     rcx, 2D8h; psz
0x1800113c3  mov     [rsp+290h+var_268], r15
0x1800113c8  call    cs:__imp_SHStrDupW
0x1800113ce  mov     ebx, eax
0x1800113d0  test    eax, eax
0x1800113d2  js      short loc_180011413
0x1800113d4  mov     rbx, [rdi+40h]
0x1800113d8  lea     rcx, aConnectedinfos_0; "connectedinfosubtitle"
0x1800113df  call    cs:__imp_StrToID
0x1800113e5  movzx   edx, ax
0x1800113e8  mov     rcx, rbx
0x1800113eb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800113f1  mov     rdx, [rsp+290h+var_268]
0x1800113f6  mov     rcx, rax
0x1800113f9  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800113ff  mov     r8b, 1; bool
0x180011402  lea     rdx, aConnectedinfos_0; "connectedinfosubtitle"
0x180011409  mov     rcx, rdi; this
0x18001140c  mov     ebx, eax
0x18001140e  call    ?CollapseExpand@CWizardPageBase@@QEAAXPEBG_NH@Z; CWizardPageBase::CollapseExpand(ushort const *,bool,int)
0x180011413  mov     rcx, [rsp+290h+var_268]; pv
0x180011418  mov     [rsp+290h+var_268], r15
0x18001141d  call    cs:__imp_CoTaskMemFree
0x180011423  mov     rcx, [rsp+290h+pv]; pv
0x180011428  mov     [rsp+290h+pv], r15
0x18001142d  call    cs:__imp_CoTaskMemFree
0x180011433  test    ebx, ebx
0x180011435  js      loc_180011519
0x18001143b  mov     rcx, cs:g_hinst; hInstance
0x180011442  lea     r8, [rdi+68h]; lpBuffer
0x180011446  mov     r9d, 100h; cchBufferMax
0x18001144c  mov     edx, r14d; uID
0x18001144f  call    cs:__imp_LoadStringW
0x180011455  test    eax, eax
0x180011457  jz      short loc_180011479
0x180011459  mov     rcx, cs:g_hinst; hInstance
0x180011460  lea     r8, [rdi+268h]; lpBuffer
0x180011467  mov     r9d, 200h; cchBufferMax
0x18001146d  mov     edx, esi; uID
0x18001146f  call    cs:__imp_LoadStringW
0x180011475  test    eax, eax
0x180011477  jnz     short loc_180011483
0x180011479  mov     ebx, 80004005h
0x18001147e  jmp     loc_180011519
0x180011483  mov     rbx, [rdi+40h]
0x180011487  lea     rcx, pszStr2; "username"
0x18001148e  call    cs:__imp_StrToID
0x180011494  movzx   edx, ax
0x180011497  mov     rcx, rbx
0x18001149a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800114a0  mov     rdx, [rsp+290h+ppwsz]
0x1800114a5  mov     rcx, rax
0x1800114a8  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800114ae  mov     rbx, [rdi+40h]
0x1800114b2  lea     rcx, aUsertilecontro_0; "UserTileControl"
0x1800114b9  call    cs:__imp_StrToID
0x1800114bf  movzx   edx, ax
0x1800114c2  mov     rcx, rbx
0x1800114c5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800114cb  mov     rsi, rax
0x1800114ce  test    rax, rax
0x1800114d1  jnz     short loc_1800114DA
0x1800114d3  mov     ebx, 8000FFFFh
0x1800114d8  jmp     short loc_180011519
0x1800114da  mov     rax, [rdi+60h]
0x1800114de  mov     rdx, [rax+1A20h]; unsigned int
0x1800114e5  test    rdx, rdx
0x1800114e8  jz      short loc_1800114FA
0x1800114ea  cmp     [rdx], r15w
0x1800114ee  jz      short loc_1800114FA
0x1800114f0  mov     rcx, rsi; this
0x1800114f3  call    ?SetImageURL@UserTile@@QEAAJPEBG@Z; UserTile::SetImageURL(ushort const *)
0x1800114f8  jmp     short loc_180011517
0x1800114fa  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x1800114ff  call    ?_GetDefaultUserPicturePath@@YAJPEAGK@Z; _GetDefaultUserPicturePath(ushort *,ulong)
0x180011504  mov     ebx, eax
0x180011506  test    eax, eax
0x180011508  js      short loc_180011519
0x18001150a  lea     rdx, [rsp+290h+var_250]; unsigned __int16 *
0x18001150f  mov     rcx, rsi; this
0x180011512  call    ?SetImagePath@UserTile@@QEAAJPEBG@Z; UserTile::SetImagePath(ushort const *)
0x180011517  mov     ebx, eax
0x180011519  mov     rcx, [rsp+290h+ppwsz]; pv
0x18001151e  mov     [rsp+290h+ppwsz], r15
0x180011523  call    cs:__imp_CoTaskMemFree
0x180011529  mov     eax, ebx
0x18001152b  mov     rcx, [rbp+190h+var_40]
0x180011532  xor     rcx, rsp; StackCookie
0x180011535  call    __security_check_cookie
0x18001153a  add     rsp, 268h
0x180011541  pop     r15
0x180011543  pop     r14
0x180011545  pop     rdi
0x180011546  pop     rsi
0x180011547  pop     rbx
0x180011548  pop     rbp
0x180011549  retn
```
