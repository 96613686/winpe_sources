# CWMPRichPreviewExt::SetWindow(HWND__ *,tagRECT const *)

- ea: `0x140008600`
- end: `0x1400087cd`
- name: `?SetWindow@CWMPRichPreviewExt@@UEAAJPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `461`
- prototype: `int(CWMPRichPreviewExt *__hidden this, HWND, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140006164`
- `0x140008600`
- `0x1400099e0`
- `0x140009a4c`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400086fa`
- `KERNEL32!GetLastError` at `0x1400086fa`
- `USER32!GetWindowLongW` at `0x14000872f`
- `USER32!GetWindowLongW` at `0x140008741`
- `USER32!GetWindowLongW` at `0x14000872f`
- `USER32!GetWindowLongW` at `0x140008741`
- `USER32!CreateWindowExW` at `0x1400086eb`
- `USER32!CreateWindowExW` at `0x1400086eb`
- `USER32!SetWindowLongW` at `0x140008754`
- `USER32!SetWindowLongW` at `0x140008754`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewExt::SetWindow(CWMPRichPreviewExt *this, HWND a2, const struct tagRECT *a3)
{
  CWMPRichPreviewExt *v6; // rcx
  unsigned int v7; // edi
  LONG X; // r9d
  int nHeight; // edx
  int nWidth; // ecx
  HWND Window; // rax
  signed int LastError; // eax
  LONG WindowLongW; // eax
  struct tagRECT v15; // [rsp+60h] [rbp-38h] BYREF

  if ( !a3 || !a2 )
    return 2147500035LL;
  v6 = (CWMPRichPreviewExt *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dqdddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)a2,
      a3,
      a3->left,
      a3->top,
      a3->right,
      a3->bottom);
  }
  v7 = 0;
  if ( !*((_QWORD *)this + 12) || a2 != *((HWND *)this + 11) )
  {
    *((_QWORD *)this + 11) = a2;
    X = a3->left;
    nHeight = a3->bottom - a3->top;
    if ( nHeight < 0 )
      nHeight = a3->top - a3->bottom;
    nWidth = X - a3->right;
    if ( a3->right - X > 0 )
      nWidth = a3->right - X;
    Window = CreateWindowExW(
               0x8000000u,
               L"RPHInnerParent",
               &WindowName,
               0x56000000u,
               X,
               a3->top,
               nWidth,
               nHeight,
               a2,
               0,
               0,
               0);
    *((_QWORD *)this + 12) = Window;
    if ( Window )
    {
      (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 3) + 24LL))(
        (char *)this + 24,
        *((unsigned int *)this + 18));
      if ( (GetWindowLongW(*((HWND *)this + 12), -20) & 0x400000) != 0 )
      {
        WindowLongW = GetWindowLongW(*((HWND *)this + 12), -20);
        SetWindowLongW(*((HWND *)this + 12), -20, WindowLongW & 0xFFBFFFFF);
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    v6 = (CWMPRichPreviewExt *)*((_QWORD *)this + 6);
    if ( v6 )
    {
      *((_QWORD *)this + 6) = 0;
      (*(void (__fastcall **)(CWMPRichPreviewExt *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  *(struct tagRECT *)((char *)this + 104) = *CWMPRichPreviewExt::MaintainAspect(v6, &v15, a3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x140008600  push    rbx
0x140008602  push    rbp
0x140008603  push    rsi
0x140008604  push    rdi
0x140008605  push    r15
0x140008607  sub     rsp, 70h
0x14000860b  mov     rsi, r8
0x14000860e  mov     rbp, rdx
0x140008611  mov     rbx, rcx
0x140008614  test    r8, r8
0x140008617  jz      loc_1400087BD
0x14000861d  test    rdx, rdx
0x140008620  jz      loc_1400087BD
0x140008626  mov     rcx, cs:WPP_GLOBAL_Control
0x14000862d  lea     r15, WPP_GLOBAL_Control
0x140008634  cmp     rcx, r15
0x140008637  jz      short loc_140008675
0x140008639  test    byte ptr [rcx+1Ch], 1
0x14000863d  jz      short loc_140008675
0x14000863f  cmp     byte ptr [rcx+19h], 5
0x140008643  jb      short loc_140008675
0x140008645  mov     eax, [r8+0Ch]
0x140008649  mov     r9d, ebp
0x14000864c  mov     rcx, [rcx+10h]
0x140008650  mov     dword ptr [rsp+98h+hWndParent], eax
0x140008654  mov     eax, [r8+8]
0x140008658  mov     [rsp+98h+nHeight], eax
0x14000865c  mov     eax, [r8+4]
0x140008660  mov     [rsp+98h+nWidth], eax
0x140008664  mov     eax, [r8]
0x140008667  mov     [rsp+98h+Y], eax
0x14000866b  mov     qword ptr [rsp+98h+X], r8
0x140008670  call    WPP_SF_Dqdddd
0x140008675  xor     edi, edi
0x140008677  cmp     [rbx+60h], rdi
0x14000867b  jz      short loc_140008687
0x14000867d  cmp     rbp, [rbx+58h]
0x140008681  jz      loc_140008777
0x140008687  mov     [rsp+98h+lpParam], rdi; lpParam
0x14000868c  mov     [rsp+98h+hInstance], rdi; hInstance
0x140008691  mov     [rbx+58h], rbp
0x140008695  mov     r8d, [rsi+4]
0x140008699  mov     eax, r8d
0x14000869c  sub     eax, [rsi+0Ch]
0x14000869f  mov     r9d, [rsi]
0x1400086a2  mov     edx, eax
0x1400086a4  mov     [rsp+98h+hMenu], rdi; hMenu
0x1400086a9  neg     edx
0x1400086ab  mov     [rsp+98h+hWndParent], rbp; hWndParent
0x1400086b0  cmovs   edx, eax
0x1400086b3  mov     eax, [rsi+8]
0x1400086b6  sub     eax, r9d
0x1400086b9  mov     [rsp+98h+nHeight], edx; nHeight
0x1400086bd  mov     ecx, eax
0x1400086bf  lea     rdx, szClass; "RPHInnerParent"
0x1400086c6  neg     ecx
0x1400086c8  cmovs   ecx, eax
0x1400086cb  mov     [rsp+98h+nWidth], ecx; nWidth
0x1400086cf  mov     ecx, 8000000h; dwExStyle
0x1400086d4  mov     [rsp+98h+Y], r8d; Y
0x1400086d9  lea     r8, WindowName; lpWindowName
0x1400086e0  mov     [rsp+98h+X], r9d; X
0x1400086e5  mov     r9d, 56000000h; dwStyle
0x1400086eb  call    cs:__imp_CreateWindowExW
0x1400086f1  mov     [rbx+60h], rax
0x1400086f5  test    rax, rax
0x1400086f8  jnz     short loc_140008711
0x1400086fa  call    cs:__imp_GetLastError
0x140008700  mov     edi, eax
0x140008702  test    eax, eax
0x140008704  jle     short loc_14000875A
0x140008706  movzx   edi, ax
0x140008709  or      edi, 80070000h
0x14000870f  jmp     short loc_14000875A
0x140008711  mov     edx, [rbx+48h]
0x140008714  lea     rcx, [rbx+18h]
0x140008718  mov     rax, [rcx]
0x14000871b  mov     rax, [rax+18h]
0x14000871f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008724  mov     rcx, [rbx+60h]; hWnd
0x140008728  mov     ebp, 0FFFFFFECh
0x14000872d  mov     edx, ebp; nIndex
0x14000872f  call    cs:__imp_GetWindowLongW
0x140008735  bt      eax, 16h
0x140008739  jnb     short loc_14000875A
0x14000873b  mov     rcx, [rbx+60h]; hWnd
0x14000873f  mov     edx, ebp; nIndex
0x140008741  call    cs:__imp_GetWindowLongW
0x140008747  mov     rcx, [rbx+60h]; hWnd
0x14000874b  mov     edx, ebp; nIndex
0x14000874d  btr     eax, 16h
0x140008751  mov     r8d, eax; dwNewLong
0x140008754  call    cs:__imp_SetWindowLongW
0x14000875a  mov     rcx, [rbx+30h]
0x14000875e  test    rcx, rcx
0x140008761  jz      short loc_140008777
0x140008763  mov     qword ptr [rbx+30h], 0
0x14000876b  mov     rax, [rcx]
0x14000876e  mov     rax, [rax+10h]
0x140008772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008777  mov     r8, rsi; struct tagRECT *
0x14000877a  lea     rdx, [rsp+98h+var_38]; retstr
0x14000877f  call    ?MaintainAspect@CWMPRichPreviewExt@@AEAA?AUtagRECT@@PEBU2@@Z; CWMPRichPreviewExt::MaintainAspect(tagRECT const *)
0x140008784  movups  xmm3, xmmword ptr [rax]
0x140008787  movdqu  xmmword ptr [rbx+68h], xmm3
0x14000878c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008793  cmp     rcx, r15
0x140008796  jz      short loc_1400087B9
0x140008798  test    byte ptr [rcx+1Ch], 1
0x14000879c  jz      short loc_1400087B9
0x14000879e  cmp     byte ptr [rcx+19h], 5
0x1400087a2  jb      short loc_1400087B9
0x1400087a4  mov     rcx, [rcx+10h]
0x1400087a8  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400087af  mov     edx, 15h
0x1400087b4  call    WPP_SF_
0x1400087b9  mov     eax, edi
0x1400087bb  jmp     short loc_1400087C2
0x1400087bd  mov     eax, 80004003h
0x1400087c2  add     rsp, 70h
0x1400087c6  pop     r15
0x1400087c8  pop     rdi
0x1400087c9  pop     rsi
0x1400087ca  pop     rbp
0x1400087cb  pop     rbx
0x1400087cc  retn
```
