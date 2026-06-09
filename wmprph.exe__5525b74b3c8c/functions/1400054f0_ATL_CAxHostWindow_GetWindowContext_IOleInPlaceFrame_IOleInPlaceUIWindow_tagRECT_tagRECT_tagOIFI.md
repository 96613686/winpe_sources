# ATL::CAxHostWindow::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x1400054f0`
- end: `0x1400056e2`
- name: `?GetWindowContext@CAxHostWindow@ATL@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `498`
- prototype: `int(ATL::CAxHostWindow *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001014`
- `0x1400054f0`
- `0x14000f010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x140005564`
- `USER32!DefWindowProcW` at `0x1400055d9`
- `USER32!GetParent` at `0x1400056b0`
- `USER32!GetParent` at `0x1400056b0`
- `USER32!GetClientRect` at `0x14000565d`
- `USER32!GetClientRect` at `0x14000566c`
- `USER32!GetClientRect` at `0x14000565d`
- `USER32!GetClientRect` at `0x14000566c`
- `USER32!CreateAcceleratorTableW` at `0x140005689`
- `USER32!CreateAcceleratorTableW` at `0x140005689`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetWindowContext(
        ATL::CAxHostWindow *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lpRect,
        struct tagOIFI *a6)
{
  _QWORD *v10; // rdi
  unsigned int v11; // ebp
  _DWORD *v12; // rax
  _DWORD *v13; // rcx
  _QWORD *v14; // rbx
  void (__fastcall ***v15)(__int64, GUID *, char *); // rax
  void (__fastcall ***v16)(__int64, GUID *, char *); // rcx
  HACCEL v17; // rax
  struct tagOIFI *v18; // rdi
  HACCEL v19; // rbx
  tagACCEL paccel; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 && a3 && a4 && lpRect )
  {
    v10 = (_QWORD *)((char *)this + 96);
    v11 = 0;
    if ( !*((_QWORD *)this + 12) )
    {
      v12 = operator new(0x58u);
      v13 = v12;
      if ( v12 )
      {
        v12[18] = 0;
        *((_QWORD *)v12 + 1) = 0;
        *((_QWORD *)v12 + 5) = 0;
        *((_QWORD *)v12 + 6) = 0;
        *((_QWORD *)v12 + 7) = DefWindowProcW;
        *(_QWORD *)v12 = &ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
        *((_QWORD *)v12 + 8) = &ATL::CComObject<ATL::CAxFrameWindow>::`vftable'{for `IOleInPlaceFrame'};
        *((_QWORD *)v12 + 10) = 0;
        _InterlockedIncrement(&dword_1400153D8);
      }
      else
      {
        v13 = 0;
      }
      (**((void (__fastcall ***)(__int64, GUID *, _QWORD *))v13 + 8))((__int64)(v13 + 16), &IID_IOleInPlaceFrame, v10);
    }
    v14 = (_QWORD *)((char *)this + 104);
    if ( !*((_QWORD *)this + 13) )
    {
      v15 = (void (__fastcall ***)(__int64, GUID *, char *))operator new(0x58u);
      v16 = v15;
      if ( v15 )
      {
        *((_DWORD *)v15 + 18) = 0;
        v15[1] = 0;
        v15[5] = 0;
        v15[6] = 0;
        v15[7] = (void (__fastcall **)(__int64, GUID *, char *))DefWindowProcW;
        *v15 = (void (__fastcall **)(__int64, GUID *, char *))&ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
        v15[8] = (void (__fastcall **)(__int64, GUID *, char *))&ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `IOleInPlaceUIWindow'};
        v15[10] = 0;
        _InterlockedIncrement(&dword_1400153D8);
      }
      else
      {
        v16 = 0;
      }
      (*v16[8])((__int64)(v16 + 8), &IID_IOleInPlaceUIWindow, (char *)this + 104);
    }
    *a2 = (struct IOleInPlaceFrame *)*v10;
    if ( *v10 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
    *a3 = (struct IOleInPlaceUIWindow *)*v14;
    if ( *v14 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    GetClientRect(*((HWND *)this - 9), a4);
    GetClientRect(*((HWND *)this - 9), lpRect);
    *(_DWORD *)&paccel.fVirt = 0;
    paccel.cmd = 0;
    v17 = CreateAcceleratorTableW(&paccel, 1);
    v18 = a6;
    v19 = v17;
    a6->cb = 32;
    v18->fMDIApp = (*((_DWORD *)this + 42) >> 2) & 1;
    v18->hwndFrame = GetParent(*((HWND *)this - 9));
    v18->haccel = v19;
    v18->cAccelEntries = 1;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v11;
}

```

## disassembly

```asm
0x1400054f0  mov     [rsp+arg_0], rbx
0x1400054f5  mov     [rsp+arg_10], rbp
0x1400054fa  push    rsi
0x1400054fb  push    rdi
0x1400054fc  push    r13
0x1400054fe  push    r14
0x140005500  push    r15
0x140005502  sub     rsp, 20h
0x140005506  xor     ebx, ebx
0x140005508  mov     r13, r9
0x14000550b  mov     r14, r8
0x14000550e  mov     r15, rdx
0x140005511  mov     rsi, rcx
0x140005514  test    rdx, rdx
0x140005517  jz      loc_1400056C4
0x14000551d  test    r8, r8
0x140005520  jz      loc_1400056C4
0x140005526  test    r9, r9
0x140005529  jz      loc_1400056C4
0x14000552f  cmp     [rsp+48h+lpRect], rbx
0x140005534  jz      loc_1400056C4
0x14000553a  lea     rdi, [rcx+60h]
0x14000553e  mov     ebp, ebx
0x140005540  cmp     [rdi], rbx
0x140005543  jnz     short loc_1400055AD
0x140005545  lea     ecx, [rbx+58h]; Size
0x140005548  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000554d  mov     rcx, rax
0x140005550  test    rax, rax
0x140005553  jz      short loc_140005591
0x140005555  mov     [rax+48h], ebx
0x140005558  mov     [rax+8], rbx
0x14000555c  mov     [rax+28h], rbx
0x140005560  mov     [rax+30h], rbx
0x140005564  mov     rax, cs:__imp_DefWindowProcW
0x14000556b  mov     [rcx+38h], rax
0x14000556f  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6B?$CWindowImpl@VCAxUIWindow@ATL@@VCWindow@2@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@1@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x140005576  mov     [rcx], rax
0x140005579  lea     rax, ??_7?$CComObject@VCAxFrameWindow@ATL@@@ATL@@6BIOleInPlaceFrame@@@; const ATL::CComObject<ATL::CAxFrameWindow>::`vftable'{for `IOleInPlaceFrame'}
0x140005580  mov     [rcx+40h], rax
0x140005584  mov     [rcx+50h], rbx
0x140005588  lock inc cs:dword_1400153D8
0x14000558f  jmp     short loc_140005594
0x140005591  mov     rcx, rbx
0x140005594  add     rcx, 40h ; '@'
0x140005598  lea     rdx, IID_IOleInPlaceFrame
0x14000559f  mov     r8, rdi
0x1400055a2  mov     rax, [rcx]
0x1400055a5  mov     rax, [rax]
0x1400055a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055ad  lea     rbx, [rsi+68h]
0x1400055b1  cmp     [rbx], rbp
0x1400055b4  jnz     short loc_140005622
0x1400055b6  mov     ecx, 58h ; 'X'; Size
0x1400055bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400055c0  xor     edx, edx
0x1400055c2  mov     rcx, rax
0x1400055c5  test    rax, rax
0x1400055c8  jz      short loc_140005606
0x1400055ca  mov     [rax+48h], edx
0x1400055cd  mov     [rax+8], rdx
0x1400055d1  mov     [rax+28h], rdx
0x1400055d5  mov     [rax+30h], rdx
0x1400055d9  mov     rax, cs:__imp_DefWindowProcW
0x1400055e0  mov     [rcx+38h], rax
0x1400055e4  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6B?$CWindowImpl@VCAxUIWindow@ATL@@VCWindow@2@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@1@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxUIWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x1400055eb  mov     [rcx], rax
0x1400055ee  lea     rax, ??_7?$CComObject@VCAxUIWindow@ATL@@@ATL@@6BIOleInPlaceUIWindow@@@; const ATL::CComObject<ATL::CAxUIWindow>::`vftable'{for `IOleInPlaceUIWindow'}
0x1400055f5  mov     [rcx+40h], rax
0x1400055f9  mov     [rcx+50h], rdx
0x1400055fd  lock inc cs:dword_1400153D8
0x140005604  jmp     short loc_140005609
0x140005606  mov     rcx, rdx
0x140005609  add     rcx, 40h ; '@'
0x14000560d  lea     rdx, IID_IOleInPlaceUIWindow
0x140005614  mov     r8, rbx
0x140005617  mov     rax, [rcx]
0x14000561a  mov     rax, [rax]
0x14000561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005622  mov     rax, [rdi]
0x140005625  mov     [r15], rax
0x140005628  mov     rcx, [rdi]
0x14000562b  test    rcx, rcx
0x14000562e  jz      short loc_14000563C
0x140005630  mov     rax, [rcx]
0x140005633  mov     rax, [rax+8]
0x140005637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000563c  mov     rax, [rbx]
0x14000563f  mov     [r14], rax
0x140005642  mov     rcx, [rbx]
0x140005645  test    rcx, rcx
0x140005648  jz      short loc_140005656
0x14000564a  mov     rax, [rcx]
0x14000564d  mov     rax, [rax+8]
0x140005651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005656  mov     rcx, [rsi-48h]; hWnd
0x14000565a  mov     rdx, r13; lpRect
0x14000565d  call    cs:__imp_GetClientRect
0x140005663  mov     rdx, [rsp+48h+lpRect]; lpRect
0x140005668  mov     rcx, [rsi-48h]; hWnd
0x14000566c  call    cs:__imp_GetClientRect
0x140005672  xor     eax, eax
0x140005674  mov     dword ptr [rsp+48h+paccel.fVirt], ebp
0x140005678  lea     rcx, [rsp+48h+paccel]; paccel
0x14000567d  mov     [rsp+48h+paccel.cmd], ax
0x140005682  lea     r14d, [rax+1]
0x140005686  mov     edx, r14d; cAccel
0x140005689  call    cs:__imp_CreateAcceleratorTableW
0x14000568f  mov     rdi, [rsp+48h+arg_28]
0x140005694  mov     rbx, rax
0x140005697  mov     dword ptr [rdi], 20h ; ' '
0x14000569d  mov     eax, [rsi+0A8h]
0x1400056a3  shr     eax, 2
0x1400056a6  and     eax, r14d
0x1400056a9  mov     [rdi+4], eax
0x1400056ac  mov     rcx, [rsi-48h]; hWnd
0x1400056b0  call    cs:__imp_GetParent
0x1400056b6  mov     [rdi+8], rax
0x1400056ba  mov     [rdi+10h], rbx
0x1400056be  mov     [rdi+18h], r14d
0x1400056c2  jmp     short loc_1400056C9
0x1400056c4  mov     ebp, 80004003h
0x1400056c9  mov     rbx, [rsp+48h+arg_0]
0x1400056ce  mov     eax, ebp
0x1400056d0  mov     rbp, [rsp+48h+arg_10]
0x1400056d5  add     rsp, 20h
0x1400056d9  pop     r15
0x1400056db  pop     r14
0x1400056dd  pop     r13
0x1400056df  pop     rdi
0x1400056e0  pop     rsi
0x1400056e1  retn
```
