# CColorCplPage::_Setup(bool)

- ea: `0x18000eaf0`
- end: `0x18000ed79`
- name: `?_Setup@CColorCplPage@@AEAAJ_N@Z`
- size: `649`
- prototype: `__int64 __fastcall(CColorCplPage *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000ddb0`
- `0x18000e4b4`

## callees

- `0x18000e964`
- `0x18000eaf0`
- `0x18000ed80`
- `0x180052f3c`
- `0x180057010`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18000eb39`
- `USER32!SystemParametersInfoW` at `0x18000eb39`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000eb7a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000eba2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000eb7a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000eba2`
- `DUI70!StrToID` at `0x18000eb68`
- `DUI70!StrToID` at `0x18000eb90`
- `DUI70!StrToID` at `0x18000eb68`
- `DUI70!StrToID` at `0x18000eb90`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ebbe`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ec0b`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ebbe`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ec0b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000ebf6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000ec3f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000ebf6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000ec3f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ebd7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ec20`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ebd7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000ec20`

## pseudocode

```c
__int64 __fastcall CColorCplPage::_Setup(CColorCplPage *this, char a2)
{
  char v4; // al
  unsigned __int16 v5; // ax
  struct DirectUI::Element *Descendent; // rdi
  unsigned __int16 v7; // ax
  struct DirectUI::Element *v8; // rbp
  __int64 *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int128 pvParam; // [rsp+40h] [rbp-38h] BYREF

  if ( !a2 )
  {
    CColorCplPage::_RefreshButtonStatus(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 98) + 40LL))(*((_QWORD *)this + 98));
  }
  pvParam = 0;
  LODWORD(pvParam) = 16;
  if ( !SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) || (v4 = 1, (BYTE4(pvParam) & 1) == 0) )
    v4 = 0;
  *((_BYTE *)this + 258) = v4;
  CColorCplPage::_UpdateBannerColors(this);
  v5 = StrToID(L"WindowColorCPL");
  Descendent = DirectUI::Element::FindDescendent(this, v5);
  v7 = StrToID(L"HCColorCPL");
  v8 = DirectUI::Element::FindDescendent(this, v7);
  DirectUI::Element::SetEnabled(Descendent, *((_BYTE *)this + 258) == 0);
  DirectUI::Element::SetVisible(Descendent, *((_BYTE *)this + 258) == 0);
  DirectUI::Element::SetLayoutPos(Descendent, *((_BYTE *)this + 258) != 0 ? -3 : 4);
  DirectUI::Element::SetEnabled(v8, *((_BYTE *)this + 258));
  DirectUI::Element::SetVisible(v8, *((_BYTE *)this + 258));
  DirectUI::Element::SetLayoutPos(v8, *((_BYTE *)this + 258) != 0 ? 4 : -3);
  if ( *((_BYTE *)this + 258) )
  {
    v9 = (__int64 *)(((unsigned __int64)v8 + 200) & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64));
  }
  else if ( Descendent )
  {
    v9 = (__int64 *)((char *)Descendent + 208);
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 98) = v9;
  if ( a2 )
  {
    if ( *((_QWORD *)this + 102) )
    {
      (*(void (__fastcall **)(__int64))(*((_QWORD *)Descendent + 26) + 48LL))((__int64)Descendent + 208);
      v10 = *((_QWORD *)v8 + 25);
    }
    else
    {
      v10 = *v9;
    }
    (*(void (**)(void))(v10 + 48))();
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, bool, char *))(**((_QWORD **)this + 98) + 32LL))(
          *((_QWORD *)this + 98),
          *((_QWORD *)this + 105),
          *((_QWORD *)this + 99),
          *((_QWORD *)this + 100),
          *((_QWORD *)this + 101),
          *((_QWORD *)this + 102) != 0,
          (char *)this + (*((_BYTE *)this + 258) != 0) + 256);
  v12 = v11;
  if ( a2 && v11 >= 0 )
  {
    v13 = *((_QWORD *)this + 102);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 168LL))(v13);
    }
    else if ( !*((_BYTE *)this + 258) )
    {
      return (unsigned int)DUIFramework_SetRegisteredDefaultButton(
                             (struct IObjectWithSite *)(((unsigned __int64)this + 208) & -(__int64)(this != 0)),
                             *((struct DirectUI::Element **)this + 99));
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000eaf0  push    rbx
0x18000eaf2  push    rbp
0x18000eaf3  push    rsi
0x18000eaf4  push    rdi
0x18000eaf5  push    r14
0x18000eaf7  sub     rsp, 50h
0x18000eafb  mov     sil, dl
0x18000eafe  mov     rbx, rcx
0x18000eb01  test    dl, dl
0x18000eb03  jnz     short loc_18000EB1D
0x18000eb05  call    ?_RefreshButtonStatus@CColorCplPage@@AEAAXXZ; CColorCplPage::_RefreshButtonStatus(void)
0x18000eb0a  mov     rcx, [rbx+310h]
0x18000eb11  mov     rax, [rcx]
0x18000eb14  mov     rax, [rax+28h]
0x18000eb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb1d  mov     edx, 10h; uiParam
0x18000eb22  lea     r8, [rsp+78h+pvParam]; pvParam
0x18000eb27  xorps   xmm0, xmm0
0x18000eb2a  xor     r9d, r9d; fWinIni
0x18000eb2d  movups  [rsp+78h+pvParam], xmm0
0x18000eb32  mov     dword ptr [rsp+78h+pvParam], edx
0x18000eb36  lea     ecx, [rdx+32h]; uiAction
0x18000eb39  call    cs:__imp_SystemParametersInfoW
0x18000eb40  nop     dword ptr [rax+rax+00h]
0x18000eb45  test    eax, eax
0x18000eb47  jz      short loc_18000EB51
0x18000eb49  mov     al, 1
0x18000eb4b  test    byte ptr [rsp+78h+pvParam+4], al
0x18000eb4f  jnz     short loc_18000EB53
0x18000eb51  xor     al, al
0x18000eb53  mov     rcx, rbx; this
0x18000eb56  mov     [rbx+102h], al
0x18000eb5c  call    ?_UpdateBannerColors@CColorCplPage@@AEAAXXZ; CColorCplPage::_UpdateBannerColors(void)
0x18000eb61  lea     rcx, aWindowcolorcpl; "WindowColorCPL"
0x18000eb68  call    cs:__imp_StrToID
0x18000eb6f  nop     dword ptr [rax+rax+00h]
0x18000eb74  movzx   edx, ax
0x18000eb77  mov     rcx, rbx
0x18000eb7a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000eb81  nop     dword ptr [rax+rax+00h]
0x18000eb86  lea     rcx, aHccolorcpl; "HCColorCPL"
0x18000eb8d  mov     rdi, rax
0x18000eb90  call    cs:__imp_StrToID
0x18000eb97  nop     dword ptr [rax+rax+00h]
0x18000eb9c  movzx   edx, ax
0x18000eb9f  mov     rcx, rbx
0x18000eba2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000eba9  nop     dword ptr [rax+rax+00h]
0x18000ebae  cmp     byte ptr [rbx+102h], 0
0x18000ebb5  mov     rcx, rdi
0x18000ebb8  mov     rbp, rax
0x18000ebbb  setz    dl
0x18000ebbe  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000ebc5  nop     dword ptr [rax+rax+00h]
0x18000ebca  cmp     byte ptr [rbx+102h], 0
0x18000ebd1  mov     rcx, rdi
0x18000ebd4  setz    dl
0x18000ebd7  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000ebde  nop     dword ptr [rax+rax+00h]
0x18000ebe3  mov     cl, [rbx+102h]
0x18000ebe9  neg     cl
0x18000ebeb  mov     rcx, rdi
0x18000ebee  sbb     edx, edx
0x18000ebf0  and     edx, 0FFFFFFF9h
0x18000ebf3  add     edx, 4
0x18000ebf6  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000ebfd  nop     dword ptr [rax+rax+00h]
0x18000ec02  mov     dl, [rbx+102h]
0x18000ec08  mov     rcx, rbp
0x18000ec0b  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18000ec12  nop     dword ptr [rax+rax+00h]
0x18000ec17  mov     dl, [rbx+102h]
0x18000ec1d  mov     rcx, rbp
0x18000ec20  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000ec27  nop     dword ptr [rax+rax+00h]
0x18000ec2c  mov     al, [rbx+102h]
0x18000ec32  mov     rcx, rbp
0x18000ec35  neg     al
0x18000ec37  sbb     edx, edx
0x18000ec39  and     edx, 7
0x18000ec3c  add     edx, 0FFFFFFFDh
0x18000ec3f  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000ec46  nop     dword ptr [rax+rax+00h]
0x18000ec4b  cmp     byte ptr [rbx+102h], 0
0x18000ec52  jz      short loc_18000EC69
0x18000ec54  mov     rax, rbp
0x18000ec57  lea     rcx, [rbp+0C8h]
0x18000ec5e  neg     rax
0x18000ec61  sbb     rdx, rdx
0x18000ec64  and     rdx, rcx
0x18000ec67  jmp     short loc_18000EC79
0x18000ec69  test    rdi, rdi
0x18000ec6c  jz      short loc_18000EC77
0x18000ec6e  lea     rdx, [rdi+0D0h]
0x18000ec75  jmp     short loc_18000EC79
0x18000ec77  xor     edx, edx
0x18000ec79  mov     [rbx+310h], rdx
0x18000ec80  test    sil, sil
0x18000ec83  jz      short loc_18000ECBD
0x18000ec85  cmp     qword ptr [rbx+330h], 0
0x18000ec8d  jz      short loc_18000ECAE
0x18000ec8f  lea     rcx, [rdi+0D0h]
0x18000ec96  mov     rax, [rcx]
0x18000ec99  mov     rax, [rax+30h]
0x18000ec9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca2  lea     rcx, [rbp+0C8h]
0x18000eca9  mov     rax, [rcx]
0x18000ecac  jmp     short loc_18000ECB4
0x18000ecae  mov     rax, [rdx]
0x18000ecb1  mov     rcx, rdx
0x18000ecb4  mov     rax, [rax+30h]
0x18000ecb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecbd  mov     al, [rbx+102h]
0x18000ecc3  lea     r14, [rbx+318h]
0x18000ecca  mov     rcx, [rbx+310h]
0x18000ecd1  neg     al
0x18000ecd3  sbb     r8, r8
0x18000ecd6  neg     r8
0x18000ecd9  mov     r9, [rcx]
0x18000ecdc  add     r8, 100h
0x18000ece3  add     r8, rbx
0x18000ece6  cmp     qword ptr [rbx+330h], 0
0x18000ecee  mov     [rsp+78h+var_48], r8
0x18000ecf3  mov     rax, [r9+20h]
0x18000ecf7  setnz   dl
0x18000ecfa  mov     r9, [rbx+320h]
0x18000ed01  mov     r8, [r14]
0x18000ed04  mov     [rsp+78h+var_50], dl
0x18000ed08  mov     rdx, [rbx+328h]
0x18000ed0f  mov     [rsp+78h+var_58], rdx
0x18000ed14  mov     rdx, [rbx+348h]
0x18000ed1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed20  mov     edi, eax
0x18000ed22  test    sil, sil
0x18000ed25  jz      short loc_18000ED6B
0x18000ed27  test    eax, eax
0x18000ed29  js      short loc_18000ED6B
0x18000ed2b  mov     rcx, [rbx+330h]
0x18000ed32  test    rcx, rcx
0x18000ed35  jz      short loc_18000ED48
0x18000ed37  mov     rdx, [rcx]
0x18000ed3a  mov     rax, [rdx+0A8h]
0x18000ed41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed46  jmp     short loc_18000ED6B
0x18000ed48  cmp     byte ptr [rbx+102h], 0
0x18000ed4f  jnz     short loc_18000ED6B
0x18000ed51  mov     rdx, [r14]; struct DirectUI::Element *
0x18000ed54  lea     rax, [rbx+0D0h]
0x18000ed5b  neg     rbx
0x18000ed5e  sbb     rcx, rcx
0x18000ed61  and     rcx, rax; struct IObjectWithSite *
0x18000ed64  call    ?DUIFramework_SetRegisteredDefaultButton@@YAJPEAUIObjectWithSite@@PEAVElement@DirectUI@@@Z; DUIFramework_SetRegisteredDefaultButton(IObjectWithSite *,DirectUI::Element *)
0x18000ed69  mov     edi, eax
0x18000ed6b  mov     eax, edi
0x18000ed6d  add     rsp, 50h
0x18000ed71  pop     r14
0x18000ed73  pop     rdi
0x18000ed74  pop     rsi
0x18000ed75  pop     rbp
0x18000ed76  pop     rbx
0x18000ed77  retn
```
