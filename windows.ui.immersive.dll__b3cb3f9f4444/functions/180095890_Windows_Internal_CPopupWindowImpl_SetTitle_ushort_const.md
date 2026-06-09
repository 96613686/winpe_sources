# Windows::Internal::CPopupWindowImpl::SetTitle(ushort const *)

- ea: `0x180095890`
- end: `0x180095c91`
- name: `?SetTitle@CPopupWindowImpl@Internal@Windows@@UEAAJPEBG@Z`
- size: `1025`
- prototype: `int(Windows::Internal::CPopupWindowImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b5b8`
- `0x1800295a0`
- `0x180046e7c`
- `0x18004ec6c`
- `0x1800934f4`
- `0x180095890`
- `0x180096a00`
- `0x180098dc4`
- `0x1800ed010`

## import_xrefs

- `USER32!SetWindowTextW` at `0x1800958c1`
- `USER32!SetWindowTextW` at `0x180095917`
- `USER32!SetWindowTextW` at `0x1800958c1`
- `USER32!SetWindowTextW` at `0x180095917`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009592d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009592d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095943`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095ab1`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095bd5`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095bec`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095ab1`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095bd5`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180095bec`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095bbf`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095bbf`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800958af`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800958af`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180095967`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180095b85`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180095967`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180095b85`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x180095ae7`
- `DUI70!?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z` at `0x180095ae7`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180095a14`
- `DUI70!?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z` at `0x180095a14`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180095ad1`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180095ad1`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095b01`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095b01`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095b6c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095c21`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095b6c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180095c21`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180095ac0`
- `DUI70!?GetIndex@Element@DirectUI@@QEAAHXZ` at `0x180095ac0`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180095b4f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180095c04`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180095b4f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180095c04`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009598f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180095bad`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009598f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180095bad`
- `DUI70!StrToID` at `0x18009597d`
- `DUI70!StrToID` at `0x180095b9b`
- `DUI70!StrToID` at `0x18009597d`
- `DUI70!StrToID` at `0x180095b9b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CPopupWindowImpl::SetTitle(
        Windows::Internal::CPopupWindowImpl *this,
        const unsigned __int16 *a2)
{
  DirectUI::NativeHWNDHost *v2; // r15
  HWND HWND; // rax
  HWND v6; // rax
  const unsigned __int16 **v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // esi
  DirectUI::Element *Element; // rbx
  unsigned __int16 v12; // ax
  struct DirectUI::Element *Descendent; // rax
  __int64 v14; // rcx
  DirectUI::Element *v15; // rsi
  _DWORD *v16; // rcx
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  struct DirectUI::Element *v19; // rbx
  unsigned int Index; // ebx
  DirectUI::Element *Parent; // rax
  DirectUI::Element *v22; // rbx
  unsigned __int16 v23; // ax
  DirectUI::Element *v24; // rax
  struct DirectUI::Element **savedregs; // [rsp+20h] [rbp+0h]
  struct DirectUI::Element *v27; // [rsp+60h] [rbp+40h] BYREF
  struct DirectUI::Element *v28; // [rsp+68h] [rbp+48h] BYREF
  DirectUI::Element **v29; // [rsp+70h] [rbp+50h] BYREF

  v2 = (Windows::Internal::CPopupWindowImpl *)((char *)this - 56);
  HWND = DirectUI::NativeHWNDHost::GetHWND((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
  SetWindowTextW(HWND, a2);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) == 1 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 120LL))(*((_QWORD *)this + 5)) )
    {
      v6 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 128LL))(*((_QWORD *)this + 5));
      if ( v6 )
        SetWindowTextW(v6, a2);
    }
  }
  v7 = (const unsigned __int16 **)((char *)this + 432);
  CoTaskMemFree(*((LPVOID *)this + 54));
  *((_QWORD *)this + 54) = 0;
  if ( !a2 || (CoTaskMemFree(0), v10 = _AllocString<CTCoAllocPolicy>(v9, v8, a2, (_QWORD *)this + 54), v10 >= 0) )
  {
    Element = DirectUI::NativeHWNDHost::GetElement(v2);
    v12 = StrToID(L"Title");
    Descendent = DirectUI::Element::FindDescendent(Element, v12);
    v14 = *((_QWORD *)this + 5);
    v27 = Descendent;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 88LL))(v14) != 2
      && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 3 )
    {
      Windows::Internal::CPopupWindowImpl::_SetUpTransitionAnimation(v2);
      if ( (*(unsigned __int8 (__fastcall **)(Windows::Internal::CPopupWindowImpl *))(*(_QWORD *)this + 400LL))(this) )
      {
        if ( !*((_DWORD *)this + 38) )
        {
          v15 = v27;
          v27 = 0;
          v28 = 0;
          if ( (int)DirectUI::RichText::Create(0, 0, &v28) >= 0
            && (int)Windows::Internal::CreateNamedElementFromDUIFile(
                      (Windows::Internal *)L"title",
                      (const unsigned __int16 *)0x220F,
                      (int)v28,
                      (struct DirectUI::Element *)&v27,
                      savedregs) >= 0 )
          {
            v16 = (_DWORD *)*((_QWORD *)this + 18);
            if ( v16 && *((_QWORD *)this + 17) )
            {
              v17 = *v16 & 0xFFFFFFF;
              v29 = 0;
              if ( (int)DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(
                          v16,
                          v17,
                          &v29) >= 0 )
                *v29 = v15;
              v18 = (_DWORD *)*((_QWORD *)this + 17);
              v19 = v27;
              v29 = 0;
              if ( (int)DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(
                          v18,
                          *v18 & 0xFFFFFFF,
                          &v29) >= 0 )
                *v29 = v19;
              DirectUI::Element::SetLayoutPos(v15, -2);
            }
            Index = DirectUI::Element::GetIndex(v15);
            Parent = DirectUI::Element::GetParent(v15);
            if ( (int)DirectUI::Element::Insert(Parent, v27, Index) >= 0 )
              DirectUI::Element::SetID(v15, &Class);
          }
        }
      }
    }
    if ( !*v7
      || !**v7
      || (*((_DWORD *)this + 21) & 0x8000000) != 0
      || (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) == 2 )
    {
      v10 = DirectUI::Element::SetLayoutPos(v27, -3);
      if ( v10 >= 0 )
      {
        v10 = DirectUI::Element::SetVisible(v27, 0);
        if ( v10 >= 0 )
        {
          v10 = DirectUI::Element::SetContentString(v27, &Class);
          if ( v10 >= 0 )
          {
LABEL_32:
            if ( *((_QWORD *)this + 7) )
              v10 = Windows::Internal::CPopupWindowImpl::_EnsureProxy(v2, 1);
          }
        }
      }
    }
    else
    {
      v10 = DirectUI::Element::SetVisible(v27, 1);
      if ( v10 >= 0 )
      {
        v10 = DirectUI::Element::SetContentString(v27, *v7);
        if ( v10 >= 0 )
        {
          v22 = DirectUI::NativeHWNDHost::GetElement(v2);
          v23 = StrToID(L"TitleBar");
          v24 = DirectUI::Element::FindDescendent(v22, v23);
          DirectUI::Element::SetAccName(v24, *v7);
          DirectUI::Element::SetLayoutPos(v27, *((_DWORD *)this + 86));
          goto LABEL_32;
        }
      }
    }
    Windows::Internal::CPopupWindowImpl::_SetTitleBarLayout(v2);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 2
      && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5)) != 3 )
    {
      Windows::Internal::CPopupWindowImpl::_DoTransitionAnimation(v2);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180095890  push    rbp
0x180095892  push    rbx
0x180095893  push    rsi
0x180095894  push    rdi
0x180095895  push    r12
0x180095897  push    r14
0x180095899  push    r15; struct DirectUI::Element **
0x18009589b  mov     rbp, rsp
0x18009589e  sub     rsp, 20h
0x1800958a2  lea     r15, [rcx-38h]
0x1800958a6  mov     rdi, rcx
0x1800958a9  mov     rcx, r15
0x1800958ac  mov     rbx, rdx
0x1800958af  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800958b6  nop     dword ptr [rax+rax+00h]
0x1800958bb  mov     rcx, rax; hWnd
0x1800958be  mov     rdx, rbx; lpString
0x1800958c1  call    cs:__imp_SetWindowTextW
0x1800958c8  nop     dword ptr [rax+rax+00h]
0x1800958cd  mov     rcx, [rdi+28h]
0x1800958d1  mov     rax, [rcx]
0x1800958d4  mov     rax, [rax+58h]
0x1800958d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800958dd  xor     r12d, r12d
0x1800958e0  cmp     eax, 1
0x1800958e3  jnz     short loc_180095923
0x1800958e5  mov     rcx, [rdi+28h]
0x1800958e9  mov     rax, [rcx]
0x1800958ec  mov     rax, [rax+78h]
0x1800958f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800958f5  test    al, al
0x1800958f7  jz      short loc_180095923
0x1800958f9  mov     rcx, [rdi+28h]
0x1800958fd  mov     rax, [rcx]
0x180095900  mov     rax, [rax+80h]
0x180095907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009590c  test    rax, rax
0x18009590f  jz      short loc_180095923
0x180095911  mov     rdx, rbx; lpString
0x180095914  mov     rcx, rax; hWnd
0x180095917  call    cs:__imp_SetWindowTextW
0x18009591e  nop     dword ptr [rax+rax+00h]
0x180095923  lea     r14, [rdi+1B0h]
0x18009592a  mov     rcx, [r14]; pv
0x18009592d  call    cs:__imp_CoTaskMemFree
0x180095934  nop     dword ptr [rax+rax+00h]
0x180095939  mov     [r14], r12
0x18009593c  test    rbx, rbx
0x18009593f  jz      short loc_180095964
0x180095941  xor     ecx, ecx; pv
0x180095943  call    cs:__imp_CoTaskMemFree
0x18009594a  nop     dword ptr [rax+rax+00h]
0x18009594f  mov     r9, r14
0x180095952  mov     r8, rbx
0x180095955  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18009595a  mov     esi, eax
0x18009595c  test    eax, eax
0x18009595e  js      loc_180095C7F
0x180095964  mov     rcx, r15
0x180095967  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18009596e  nop     dword ptr [rax+rax+00h]
0x180095973  lea     rcx, aTitle_0; "Title"
0x18009597a  mov     rbx, rax
0x18009597d  call    cs:__imp_StrToID
0x180095984  nop     dword ptr [rax+rax+00h]
0x180095989  movzx   edx, ax
0x18009598c  mov     rcx, rbx
0x18009598f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180095996  nop     dword ptr [rax+rax+00h]
0x18009599b  mov     rcx, [rdi+28h]
0x18009599f  mov     [rbp+arg_0], rax
0x1800959a3  mov     rax, [rcx]
0x1800959a6  mov     rax, [rax+58h]
0x1800959aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959af  cmp     eax, 2
0x1800959b2  jz      loc_180095B0D
0x1800959b8  mov     rcx, [rdi+28h]
0x1800959bc  mov     rax, [rcx]
0x1800959bf  mov     rax, [rax+58h]
0x1800959c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959c8  cmp     eax, 3
0x1800959cb  jz      loc_180095B0D
0x1800959d1  mov     rcx, r15; this
0x1800959d4  call    ?_SetUpTransitionAnimation@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_SetUpTransitionAnimation(void)
0x1800959d9  mov     rax, [rdi]
0x1800959dc  mov     rcx, rdi
0x1800959df  mov     rax, [rax+190h]
0x1800959e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959eb  test    al, al
0x1800959ed  jz      loc_180095B0D
0x1800959f3  cmp     [rdi+98h], r12d
0x1800959fa  jnz     loc_180095B0D
0x180095a00  mov     rsi, [rbp+arg_0]
0x180095a04  lea     r8, [rbp+arg_8]
0x180095a08  xor     edx, edx
0x180095a0a  mov     [rbp+arg_0], r12
0x180095a0e  xor     ecx, ecx
0x180095a10  mov     [rbp+arg_8], r12
0x180095a14  call    cs:__imp_?Create@RichText@DirectUI@@SAJPEAVElement@2@PEAKPEAPEAV32@@Z; DirectUI::RichText::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180095a1b  nop     dword ptr [rax+rax+00h]
0x180095a20  test    eax, eax
0x180095a22  js      loc_180095B0D
0x180095a28  mov     r8, [rbp+arg_8]; int
0x180095a2c  lea     r9, [rbp+arg_0]; struct DirectUI::Element *
0x180095a30  mov     edx, 220Fh; unsigned __int16 *
0x180095a35  lea     rcx, aTitle; "title"
0x180095a3c  call    ?CreateNamedElementFromDUIFile@Internal@Windows@@YAJPEBGHPEAVElement@DirectUI@@PEAPEAV34@@Z; Windows::Internal::CreateNamedElementFromDUIFile(ushort const *,int,DirectUI::Element *,DirectUI::Element * *)
0x180095a41  test    eax, eax
0x180095a43  js      loc_180095B0D
0x180095a49  mov     rcx, [rdi+90h]
0x180095a50  test    rcx, rcx
0x180095a53  jz      short loc_180095ABD
0x180095a55  cmp     [rdi+88h], r12
0x180095a5c  jz      short loc_180095ABD
0x180095a5e  mov     edx, [rcx]
0x180095a60  lea     r8, [rbp+arg_10]
0x180095a64  and     edx, 0FFFFFFFh
0x180095a6a  mov     [rbp+arg_10], r12
0x180095a6e  call    ?InsertPtr@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEAAJIPEAPEAPEAVElement@2@@Z; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(uint,DirectUI::Element * * *)
0x180095a73  test    eax, eax
0x180095a75  js      short loc_180095A7E
0x180095a77  mov     rax, [rbp+arg_10]
0x180095a7b  mov     [rax], rsi
0x180095a7e  mov     rcx, [rdi+88h]
0x180095a85  lea     r8, [rbp+arg_10]
0x180095a89  mov     rbx, [rbp+arg_0]
0x180095a8d  mov     [rbp+arg_10], r12
0x180095a91  mov     edx, [rcx]
0x180095a93  and     edx, 0FFFFFFFh
0x180095a99  call    ?InsertPtr@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEAAJIPEAPEAPEAVElement@2@@Z; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::InsertPtr(uint,DirectUI::Element * * *)
0x180095a9e  test    eax, eax
0x180095aa0  js      short loc_180095AA9
0x180095aa2  mov     rax, [rbp+arg_10]
0x180095aa6  mov     [rax], rbx
0x180095aa9  mov     edx, 0FFFFFFFEh
0x180095aae  mov     rcx, rsi
0x180095ab1  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180095ab8  nop     dword ptr [rax+rax+00h]
0x180095abd  mov     rcx, rsi
0x180095ac0  call    cs:__imp_?GetIndex@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetIndex(void)
0x180095ac7  nop     dword ptr [rax+rax+00h]
0x180095acc  mov     rcx, rsi
0x180095acf  mov     ebx, eax
0x180095ad1  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180095ad8  nop     dword ptr [rax+rax+00h]
0x180095add  mov     rdx, [rbp+arg_0]
0x180095ae1  mov     r8d, ebx
0x180095ae4  mov     rcx, rax
0x180095ae7  call    cs:__imp_?Insert@Element@DirectUI@@QEAAJPEAV12@I@Z; DirectUI::Element::Insert(DirectUI::Element *,uint)
0x180095aee  nop     dword ptr [rax+rax+00h]
0x180095af3  test    eax, eax
0x180095af5  js      short loc_180095B0D
0x180095af7  lea     rdx, Class
0x180095afe  mov     rcx, rsi
0x180095b01  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180095b08  nop     dword ptr [rax+rax+00h]
0x180095b0d  mov     rax, [r14]
0x180095b10  test    rax, rax
0x180095b13  jz      loc_180095BE3
0x180095b19  cmp     [rax], r12w
0x180095b1d  jz      loc_180095BE3
0x180095b23  test    dword ptr [rdi+54h], 8000000h
0x180095b2a  jnz     loc_180095BE3
0x180095b30  mov     rcx, [rdi+28h]
0x180095b34  mov     rax, [rcx]
0x180095b37  mov     rax, [rax+58h]
0x180095b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b40  cmp     eax, 2
0x180095b43  jz      loc_180095BE3
0x180095b49  mov     rcx, [rbp+arg_0]
0x180095b4d  mov     dl, 1
0x180095b4f  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180095b56  nop     dword ptr [rax+rax+00h]
0x180095b5b  mov     esi, eax
0x180095b5d  test    eax, eax
0x180095b5f  js      loc_180095C45
0x180095b65  mov     rdx, [r14]
0x180095b68  mov     rcx, [rbp+arg_0]
0x180095b6c  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180095b73  nop     dword ptr [rax+rax+00h]
0x180095b78  mov     esi, eax
0x180095b7a  test    eax, eax
0x180095b7c  js      loc_180095C45
0x180095b82  mov     rcx, r15
0x180095b85  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180095b8c  nop     dword ptr [rax+rax+00h]
0x180095b91  lea     rcx, aTitlebar; "TitleBar"
0x180095b98  mov     rbx, rax
0x180095b9b  call    cs:__imp_StrToID
0x180095ba2  nop     dword ptr [rax+rax+00h]
0x180095ba7  movzx   edx, ax
0x180095baa  mov     rcx, rbx
0x180095bad  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180095bb4  nop     dword ptr [rax+rax+00h]
0x180095bb9  mov     rdx, [r14]
0x180095bbc  mov     rcx, rax
0x180095bbf  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180095bc6  nop     dword ptr [rax+rax+00h]
0x180095bcb  mov     edx, [rdi+158h]
0x180095bd1  mov     rcx, [rbp+arg_0]
0x180095bd5  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180095bdc  nop     dword ptr [rax+rax+00h]
0x180095be1  jmp     short loc_180095C33
0x180095be3  mov     rcx, [rbp+arg_0]
0x180095be7  mov     edx, 0FFFFFFFDh
0x180095bec  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180095bf3  nop     dword ptr [rax+rax+00h]
0x180095bf8  mov     esi, eax
0x180095bfa  test    eax, eax
0x180095bfc  js      short loc_180095C45
0x180095bfe  mov     rcx, [rbp+arg_0]
0x180095c02  xor     edx, edx
0x180095c04  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180095c0b  nop     dword ptr [rax+rax+00h]
0x180095c10  mov     esi, eax
0x180095c12  test    eax, eax
0x180095c14  js      short loc_180095C45
0x180095c16  mov     rcx, [rbp+arg_0]
0x180095c1a  lea     rdx, Class
0x180095c21  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180095c28  nop     dword ptr [rax+rax+00h]
0x180095c2d  mov     esi, eax
0x180095c2f  test    eax, eax
0x180095c31  js      short loc_180095C45
0x180095c33  cmp     [rdi+38h], r12
0x180095c37  jz      short loc_180095C45
0x180095c39  mov     dl, 1; bool
0x180095c3b  mov     rcx, r15; this
0x180095c3e  call    ?_EnsureProxy@CPopupWindowImpl@Internal@Windows@@AEAAJ_N@Z; Windows::Internal::CPopupWindowImpl::_EnsureProxy(bool)
0x180095c43  mov     esi, eax
0x180095c45  mov     rcx, r15; this
0x180095c48  call    ?_SetTitleBarLayout@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_SetTitleBarLayout(void)
0x180095c4d  mov     rcx, [rdi+28h]
0x180095c51  mov     rax, [rcx]
0x180095c54  mov     rax, [rax+58h]
0x180095c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c5d  cmp     eax, 2
0x180095c60  jz      short loc_180095C7F
0x180095c62  mov     rcx, [rdi+28h]
0x180095c66  mov     rax, [rcx]
0x180095c69  mov     rax, [rax+58h]
0x180095c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c72  cmp     eax, 3
0x180095c75  jz      short loc_180095C7F
0x180095c77  mov     rcx, r15; this
0x180095c7a  call    ?_DoTransitionAnimation@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_DoTransitionAnimation(void)
0x180095c7f  mov     eax, esi
0x180095c81  add     rsp, 20h
0x180095c85  pop     r15
0x180095c87  pop     r14
0x180095c89  pop     r12
0x180095c8b  pop     rdi
0x180095c8c  pop     rsi
0x180095c8d  pop     rbx
0x180095c8e  pop     rbp
0x180095c8f  retn
```
