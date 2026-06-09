# CEdgeUiInput::Position(tagRECT const *,EDGEUI_LAYOUT_REASON,bool)

- ea: `0x180012650`
- end: `0x180012bce`
- name: `?Position@CEdgeUiInput@@UEAAJPEBUtagRECT@@W4EDGEUI_LAYOUT_REASON@@_N@Z`
- size: `1406`
- prototype: `int __high(const struct tagRECT *, enum EDGEUI_LAYOUT_REASON, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x1800118dc`
- `0x180012650`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `USER32!SetWindowRgn` at `0x180012a2f`
- `USER32!SetWindowRgn` at `0x180012b40`
- `USER32!SetWindowRgn` at `0x180012a2f`
- `USER32!SetWindowRgn` at `0x180012b40`
- `GDI32!DeleteObject` at `0x180012b52`
- `GDI32!DeleteObject` at `0x180012b52`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180012a5f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180012a5f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180012a92`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180012a92`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800127bf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800127bf`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800128d2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800128d2`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800126f5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180012b8d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180012ba1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800126f5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180012b8d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180012ba1`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800127d5`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800127d5`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180012a7f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180012a7f`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800128a0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800129fa`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180012abd`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800128a0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800129fa`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180012abd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEdgeUiInput::Position(__int64 a1, struct tagRECT *a2, __int64 a3, char a4)
{
  CEdgeUiInput *v7; // rdi
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  LONG v17; // r15d
  LONG top; // r13d
  LONG v19; // esi
  __int64 (__fastcall ***v20)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v21)(_QWORD, GUID *, void **); // rbx
  int v22; // eax
  int v23; // edx
  void *v24; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, void **); // rbx
  int v28; // eax
  int v29; // edx
  int v30; // r9d
  void *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v33)(_QWORD, GUID *, void **); // rbx
  int v34; // eax
  int left; // edx
  int right; // r9d
  _DWORD *v37; // r9
  BOOL v38; // eax
  int v39; // r8d
  int v40; // r9d
  int v41; // edx
  int yBottom; // [rsp+20h] [rbp-49h]
  int v43; // [rsp+40h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-21h] BYREF
  int v45; // [rsp+50h] [rbp-19h] BYREF
  int v46; // [rsp+54h] [rbp-15h] BYREF
  int v47; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp+7h] BYREF

  rc = 0;
  v7 = (CEdgeUiInput *)(a1 - 24);
  v8 = *(_DWORD *)(a1 - 24 + 136);
  v9 = 0;
  if ( !v8 )
    goto LABEL_18;
  v10 = v8 - 1;
  if ( !v10 )
    goto LABEL_18;
  v11 = v10 - 1;
  if ( !v11 )
  {
    *(_DWORD *)(a1 + 144) = (a2->bottom - a2->top) / 3;
    goto LABEL_10;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( !v13 )
    {
      ppvOut = 0;
      v46 = 0;
      v45 = 0;
      v47 = 0;
      v43 = 0;
      v32 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
      v33 = **v32;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      v34 = v33(v32, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
      v9 = 0;
      if ( v34 >= 0
        && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             &v46,
             &v45,
             &v47,
             &v43) >= 0 )
      {
        if ( a4 )
        {
          right = a2->right;
          left = right - v47 - v46;
        }
        else
        {
          left = a2->left;
          right = v46 + a2->left + v47;
        }
        SetRect(&rc, left, a2->top, right, v45 + a2->top + v43);
      }
      goto LABEL_15;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      ppvOut = 0;
      v43 = 0;
      v47 = 0;
      v45 = 0;
      v46 = 0;
      v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
      v27 = **v26;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      v28 = v27(v26, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
      v9 = 0;
      if ( v28 >= 0
        && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             &v43,
             &v47,
             &v45,
             &v46) >= 0 )
      {
        if ( a4 )
        {
          v29 = a2->left;
          v30 = v43 + a2->left + v45;
        }
        else
        {
          v30 = a2->right;
          v29 = v30 - v45 - v43;
        }
        SetRect(&rc, v29, a2->top, v30, v47 + a2->top + v46);
      }
      goto LABEL_15;
    }
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_18;
    v16 = v15 - 1;
    if ( !v16 )
    {
      v39 = a2->bottom - 20;
      yBottom = a2->bottom;
      if ( a4 )
      {
        v41 = a2->left;
        v40 = v41 + 20;
      }
      else
      {
        v40 = a2->right;
        v41 = v40 - 20;
      }
      SetRect(&rc, v41, v39, v40, yBottom);
      goto LABEL_18;
    }
    if ( v16 != 1 )
    {
      SetRectEmpty(&rc);
      return (unsigned int)-2147418113;
    }
LABEL_10:
    SetRectEmpty(&rc);
    v17 = a2->left;
    top = a2->top;
    v19 = a2->right;
    ppvOut = 0;
    v43 = 0;
    v46 = 0;
    v45 = 0;
    v47 = 0;
    v20 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
    v21 = **v20;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
    v22 = v21(v20, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
    v9 = 0;
    if ( v22 >= 0
      && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           &v43,
           &v46,
           &v45,
           &v47) >= 0 )
    {
      v23 = v43 + v45;
      if ( a4 )
        v19 -= v23;
      else
        v17 += v23;
    }
    rc.left = v17;
    rc.top = top;
    rc.right = v19;
    rc.bottom = top + 4;
LABEL_15:
    v24 = ppvOut;
    if ( ppvOut )
    {
      ppvOut = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v7 = (CEdgeUiInput *)(a1 - 24);
    goto LABEL_18;
  }
  ppvOut = 0;
  v43 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         *(IUnknown **)(a1 - 8),
         (const GUID *const)&SID_EdgeUi,
         &GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e,
         &ppvOut) >= 0
    && (*(int (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 80LL))(ppvOut, &v43) >= 0 )
  {
    Rect = *a2;
    if ( v43 )
    {
      switch ( v43 )
      {
        case 1:
          Rect.bottom = Rect.top + 1;
          break;
        case 2:
          Rect.left = Rect.right - 1;
          break;
        case 3:
          Rect.top = Rect.bottom - 1;
          break;
        default:
          SetRectEmpty(&Rect);
          break;
      }
    }
    else
    {
      Rect.right = Rect.left + 1;
    }
    rc = Rect;
  }
  v31 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
  }
LABEL_18:
  Rect = 0;
  if ( GetWindowRect(*(HWND *)(a1 + 120), &Rect) && EqualRect(&Rect, &rc) )
    return v9;
  SetWindowRgn(*(HWND *)(a1 + 120), 0, 0);
  SetWindowPos(*(HWND *)(a1 + 120), 0, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0x14u);
  if ( rc.left >= rc.right || rc.top >= rc.bottom )
  {
    v37 = (_DWORD *)(a1 + 112);
  }
  else
  {
    v37 = (_DWORD *)(a1 + 112);
    if ( (unsigned int)(*(_DWORD *)(a1 + 112) - 4) <= 3 )
    {
      ppvOut = 0;
      v9 = CEdgeUiInput::_ComputeCornerRegion(v7, rc.right - rc.left, rc.bottom - rc.top, a4, (HRGN *)&ppvOut);
      if ( (v9 & 0x80000000) == 0 && !SetWindowRgn(*(HWND *)(a1 + 120), (HRGN)ppvOut, 0) )
        DeleteObject(ppvOut);
      return v9;
    }
  }
  if ( *v37 == 8 || *v37 == 2 )
  {
    v38 = IsRectEmpty(&rc);
    ShowWindow(*(HWND *)(a1 + 120), !v38 ? 4 : 0);
  }
  return v9;
}

```

## disassembly

```asm
0x180012650  mov     [rsp-8+arg_10], rbx
0x180012655  push    rbp
0x180012656  push    rsi
0x180012657  push    rdi
0x180012658  push    r12
0x18001265a  push    r13
0x18001265c  push    r14
0x18001265e  push    r15
0x180012660  lea     rbp, [rsp-27h]
0x180012665  sub     rsp, 90h
0x18001266c  mov     rax, cs:__security_cookie
0x180012673  xor     rax, rsp
0x180012676  mov     [rbp+57h+var_40], rax
0x18001267a  mov     r12b, r9b
0x18001267d  mov     rsi, rdx
0x180012680  mov     r14, rcx
0x180012683  xorps   xmm0, xmm0
0x180012686  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x18001268b  lea     rdi, [rcx-18h]
0x18001268f  mov     r8d, [rdi+88h]
0x180012696  xor     ebx, ebx
0x180012698  test    r8d, r8d
0x18001269b  jz      loc_1800127B0
0x1800126a1  sub     r8d, 1
0x1800126a5  jz      loc_1800127B0
0x1800126ab  sub     r8d, 1
0x1800126af  jz      loc_180012A06
0x1800126b5  sub     r8d, 1
0x1800126b9  jz      loc_1800128AC
0x1800126bf  sub     r8d, 1
0x1800126c3  jz      loc_180012966
0x1800126c9  sub     r8d, 1
0x1800126cd  jz      loc_18001280C
0x1800126d3  sub     r8d, 1
0x1800126d7  jz      loc_1800127B0
0x1800126dd  sub     r8d, 1
0x1800126e1  jz      loc_180012A9D
0x1800126e7  cmp     r8d, 1
0x1800126eb  jnz     loc_180012B89
0x1800126f1  lea     rcx, [rbp+57h+rc]; lprc
0x1800126f5  call    cs:__imp_SetRectEmpty
0x1800126fb  mov     r15d, [rsi]
0x1800126fe  mov     r13d, [rsi+4]
0x180012702  mov     esi, [rsi+8]
0x180012705  mov     [rbp+57h+ppvOut], rbx
0x180012709  mov     [rbp+57h+var_80], ebx
0x18001270c  mov     [rbp+57h+var_6C], ebx
0x18001270f  mov     [rbp+57h+var_70], ebx
0x180012712  mov     [rbp+57h+var_68], ebx
0x180012715  mov     rdi, [r14-8]
0x180012719  mov     rax, [rdi]
0x18001271c  mov     rbx, [rax]
0x18001271f  lea     rcx, [rbp+57h+ppvOut]
0x180012723  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012728  lea     r8, [rbp+57h+ppvOut]
0x18001272c  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180012733  mov     rcx, rdi
0x180012736  mov     rax, rbx
0x180012739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001273e  nop
0x18001273f  xor     ebx, ebx
0x180012741  test    eax, eax
0x180012743  js      short loc_180012780
0x180012745  mov     rcx, [rbp+57h+ppvOut]
0x180012749  mov     rax, [rcx]
0x18001274c  lea     rdx, [rbp+57h+var_68]
0x180012750  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x180012755  lea     r9, [rbp+57h+var_70]
0x180012759  lea     r8, [rbp+57h+var_6C]
0x18001275d  lea     rdx, [rbp+57h+var_80]
0x180012761  mov     rax, [rax+18h]
0x180012765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001276a  test    eax, eax
0x18001276c  js      short loc_180012780
0x18001276e  mov     edx, [rbp+57h+var_70]
0x180012771  add     edx, [rbp+57h+var_80]
0x180012774  test    r12b, r12b
0x180012777  jnz     loc_180012BC6
0x18001277d  add     r15d, edx
0x180012780  mov     [rbp+57h+rc.left], r15d
0x180012784  mov     [rbp+57h+rc.top], r13d
0x180012788  mov     [rbp+57h+rc.right], esi
0x18001278b  lea     eax, [r13+4]
0x18001278f  mov     [rbp+57h+rc.bottom], eax
0x180012792  mov     rcx, [rbp+57h+ppvOut]
0x180012796  test    rcx, rcx
0x180012799  jz      short loc_1800127AC
0x18001279b  mov     [rbp+57h+ppvOut], rbx
0x18001279f  mov     rax, [rcx]
0x1800127a2  mov     rax, [rax+10h]
0x1800127a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ab  nop
0x1800127ac  lea     rdi, [r14-18h]
0x1800127b0  xorps   xmm0, xmm0
0x1800127b3  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800127b7  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800127bb  mov     rcx, [r14+78h]; hWnd
0x1800127bf  call    cs:__imp_GetWindowRect
0x1800127c5  test    eax, eax
0x1800127c7  jz      loc_180012A26
0x1800127cd  lea     rdx, [rbp+57h+rc]; lprc2
0x1800127d1  lea     rcx, [rbp+57h+Rect]; lprc1
0x1800127d5  call    cs:__imp_EqualRect
0x1800127db  test    eax, eax
0x1800127dd  jz      loc_180012A26
0x1800127e3  mov     eax, ebx
0x1800127e5  mov     rcx, [rbp+57h+var_40]
0x1800127e9  xor     rcx, rsp; StackCookie
0x1800127ec  call    __security_check_cookie
0x1800127f1  mov     rbx, [rsp+0C0h+arg_10]
0x1800127f9  add     rsp, 90h
0x180012800  pop     r15
0x180012802  pop     r14
0x180012804  pop     r13
0x180012806  pop     r12
0x180012808  pop     rdi
0x180012809  pop     rsi
0x18001280a  pop     rbp
0x18001280b  retn
0x18001280c  mov     [rbp+57h+ppvOut], rbx
0x180012810  mov     [rbp+57h+var_80], ebx
0x180012813  mov     [rbp+57h+var_68], ebx
0x180012816  mov     [rbp+57h+var_70], ebx
0x180012819  mov     [rbp+57h+var_6C], ebx
0x18001281c  mov     rdi, [rcx-8]
0x180012820  mov     rax, [rdi]
0x180012823  mov     rbx, [rax]
0x180012826  lea     rcx, [rbp+57h+ppvOut]
0x18001282a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001282f  lea     r8, [rbp+57h+ppvOut]
0x180012833  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x18001283a  mov     rcx, rdi
0x18001283d  mov     rax, rbx
0x180012840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012845  nop
0x180012846  xor     ebx, ebx
0x180012848  test    eax, eax
0x18001284a  js      short loc_1800128A7
0x18001284c  mov     rcx, [rbp+57h+ppvOut]
0x180012850  mov     rax, [rcx]
0x180012853  lea     rdx, [rbp+57h+var_6C]
0x180012857  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x18001285c  lea     r9, [rbp+57h+var_70]
0x180012860  lea     r8, [rbp+57h+var_68]
0x180012864  lea     rdx, [rbp+57h+var_80]
0x180012868  mov     rax, [rax+18h]
0x18001286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012871  test    eax, eax
0x180012873  js      short loc_1800128A7
0x180012875  mov     r8d, [rsi+4]; yTop
0x180012879  mov     ecx, [rbp+57h+var_6C]
0x18001287c  add     ecx, r8d
0x18001287f  add     ecx, [rbp+57h+var_68]
0x180012882  mov     [rsp+0C0h+yBottom], ecx; yBottom
0x180012886  lea     rcx, [rbp+57h+rc]; lprc
0x18001288a  test    r12b, r12b
0x18001288d  jz      loc_180012AC8
0x180012893  mov     edx, [rsi]; xLeft
0x180012895  mov     r9d, [rbp+57h+var_70]
0x180012899  add     r9d, edx
0x18001289c  add     r9d, [rbp+57h+var_80]; xRight
0x1800128a0  call    cs:__imp_SetRect
0x1800128a6  nop
0x1800128a7  jmp     loc_180012792
0x1800128ac  mov     [rbp+57h+ppvOut], rbx
0x1800128b0  mov     [rbp+57h+var_80], ebx
0x1800128b3  lea     rcx, [rbp+57h+ppvOut]
0x1800128b7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800128bc  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800128c0  lea     r8, _GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e; riid
0x1800128c7  lea     rdx, SID_EdgeUi; guidService
0x1800128ce  mov     rcx, [r14-8]; punk
0x1800128d2  call    cs:__imp_IUnknown_QueryService
0x1800128d8  test    eax, eax
0x1800128da  js      short loc_180012944
0x1800128dc  mov     rcx, [rbp+57h+ppvOut]
0x1800128e0  mov     rax, [rcx]
0x1800128e3  lea     rdx, [rbp+57h+var_80]
0x1800128e7  mov     rax, [rax+50h]
0x1800128eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128f0  test    eax, eax
0x1800128f2  js      short loc_180012944
0x1800128f4  movups  xmm0, xmmword ptr [rsi]
0x1800128f7  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800128fc  mov     ecx, [rbp+57h+var_80]
0x1800128ff  test    ecx, ecx
0x180012901  jz      loc_180012ADA
0x180012907  sub     ecx, 1
0x18001290a  jz      loc_180012BB9
0x180012910  sub     ecx, 1
0x180012913  jz      loc_180012BAC
0x180012919  cmp     ecx, 1
0x18001291c  jnz     loc_180012B9D
0x180012922  mov     eax, [rbp+57h+Rect.bottom]
0x180012925  dec     eax
0x180012927  mov     [rbp+57h+Rect.top], eax
0x18001292a  mov     eax, [rbp+57h+Rect.left]
0x18001292d  mov     ecx, [rbp+57h+Rect.top]
0x180012930  mov     edx, [rbp+57h+Rect.right]
0x180012933  mov     r8d, [rbp+57h+Rect.bottom]
0x180012937  mov     [rbp+57h+rc.left], eax
0x18001293a  mov     [rbp+57h+rc.top], ecx
0x18001293d  mov     [rbp+57h+rc.right], edx
0x180012940  mov     [rbp+57h+rc.bottom], r8d
0x180012944  mov     rcx, [rbp+57h+ppvOut]
0x180012948  test    rcx, rcx
0x18001294b  jz      loc_1800127B0
0x180012951  mov     [rbp+57h+ppvOut], rbx
0x180012955  mov     rax, [rcx]
0x180012958  mov     rax, [rax+10h]
0x18001295c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012961  jmp     loc_1800127B0
0x180012966  mov     [rbp+57h+ppvOut], rbx
0x18001296a  mov     [rbp+57h+var_6C], ebx
0x18001296d  mov     [rbp+57h+var_70], ebx
0x180012970  mov     [rbp+57h+var_68], ebx
0x180012973  mov     [rbp+57h+var_80], ebx
0x180012976  mov     rdi, [rcx-8]
0x18001297a  mov     rax, [rdi]
0x18001297d  mov     rbx, [rax]
0x180012980  lea     rcx, [rbp+57h+ppvOut]
0x180012984  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012989  lea     r8, [rbp+57h+ppvOut]
0x18001298d  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180012994  mov     rcx, rdi
0x180012997  mov     rax, rbx
0x18001299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299f  nop
0x1800129a0  xor     ebx, ebx
0x1800129a2  test    eax, eax
0x1800129a4  js      short loc_180012A01
0x1800129a6  mov     rcx, [rbp+57h+ppvOut]
0x1800129aa  mov     rax, [rcx]
0x1800129ad  lea     rdx, [rbp+57h+var_80]
0x1800129b1  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x1800129b6  lea     r9, [rbp+57h+var_68]
0x1800129ba  lea     r8, [rbp+57h+var_70]
0x1800129be  lea     rdx, [rbp+57h+var_6C]
0x1800129c2  mov     rax, [rax+18h]
0x1800129c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129cb  test    eax, eax
0x1800129cd  js      short loc_180012A01
0x1800129cf  mov     r8d, [rsi+4]; yTop
0x1800129d3  mov     ecx, [rbp+57h+var_80]
0x1800129d6  add     ecx, r8d
0x1800129d9  add     ecx, [rbp+57h+var_70]
0x1800129dc  mov     [rsp+0C0h+yBottom], ecx; yBottom
0x1800129e0  lea     rcx, [rbp+57h+rc]; lprc
0x1800129e4  test    r12b, r12b
0x1800129e7  jnz     loc_180012B77
0x1800129ed  mov     edx, [rsi]; xLeft
0x1800129ef  mov     r9d, [rbp+57h+var_68]
0x1800129f3  add     r9d, edx
0x1800129f6  add     r9d, [rbp+57h+var_6C]; xRight
0x1800129fa  call    cs:__imp_SetRect
0x180012a00  nop
0x180012a01  jmp     loc_180012792
0x180012a06  mov     ecx, [rdx+0Ch]
0x180012a09  sub     ecx, [rdx+4]
0x180012a0c  mov     eax, 55555556h
0x180012a11  imul    ecx
0x180012a13  mov     eax, edx
0x180012a15  shr     eax, 1Fh
0x180012a18  add     edx, eax
0x180012a1a  mov     [r14+90h], edx
0x180012a21  jmp     loc_1800126F1
0x180012a26  xor     r8d, r8d; bRedraw
0x180012a29  xor     edx, edx; hRgn
0x180012a2b  mov     rcx, [r14+78h]; hWnd
0x180012a2f  call    cs:__imp_SetWindowRgn
0x180012a35  mov     ecx, [rbp+57h+rc.bottom]
0x180012a38  mov     r9d, [rbp+57h+rc.top]; Y
0x180012a3c  sub     ecx, r9d
0x180012a3f  mov     eax, [rbp+57h+rc.right]
0x180012a42  mov     r8d, [rbp+57h+rc.left]; X
0x180012a46  sub     eax, r8d
0x180012a49  mov     [rsp+0C0h+uFlags], 14h; uFlags
0x180012a51  mov     [rsp+0C0h+cy], ecx; cy
0x180012a55  mov     [rsp+0C0h+yBottom], eax; cx
0x180012a59  xor     edx, edx; hWndInsertAfter
0x180012a5b  mov     rcx, [r14+78h]; hWnd
0x180012a5f  call    cs:__imp_SetWindowPos
0x180012a65  mov     edx, [rbp+57h+rc.right]
0x180012a68  cmp     [rbp+57h+rc.left], edx
0x180012a6b  jl      short loc_180012AE7
0x180012a6d  lea     r9, [r14+70h]
0x180012a71  cmp     dword ptr [r9], 8
0x180012a75  jnz     loc_180012B5D
0x180012a7b  lea     rcx, [rbp+57h+rc]; lprc
0x180012a7f  call    cs:__imp_IsRectEmpty
0x180012a85  neg     eax
0x180012a87  sbb     edx, edx
0x180012a89  not     edx
0x180012a8b  and     edx, 4; nCmdShow
0x180012a8e  mov     rcx, [r14+78h]; hWnd
0x180012a92  call    cs:__imp_ShowWindow
0x180012a98  jmp     loc_1800127E3
0x180012a9d  mov     eax, [rdx+0Ch]
0x180012aa0  lea     r8d, [rax-14h]; yTop
0x180012aa4  mov     [rsp+0C0h+yBottom], eax; yBottom
  ... truncated ...
```
