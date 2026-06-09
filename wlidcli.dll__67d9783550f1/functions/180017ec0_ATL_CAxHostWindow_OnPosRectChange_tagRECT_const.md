# ATL::CAxHostWindow::OnPosRectChange(tagRECT const *)

- ea: `0x180017ec0`
- end: `0x180017f90`
- name: `?OnPosRectChange@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002da0`
- `0x180017ec0`

## import_xrefs

- `USER32!ClientToScreen` at `0x180017efd`
- `USER32!ClientToScreen` at `0x180017f10`
- `USER32!ClientToScreen` at `0x180017efd`
- `USER32!ClientToScreen` at `0x180017f10`
- `USER32!GetParent` at `0x180017f1a`
- `USER32!GetParent` at `0x180017f1a`
- `USER32!ScreenToClient` at `0x180017f30`
- `USER32!ScreenToClient` at `0x180017f42`
- `USER32!ScreenToClient` at `0x180017f30`
- `USER32!ScreenToClient` at `0x180017f42`
- `USER32!MoveWindow` at `0x180017f70`
- `USER32!MoveWindow` at `0x180017f70`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPosRectChange(ATL::CAxHostWindow *this, const struct tagRECT *a2)
{
  HWND v4; // rcx
  HWND Parent; // rax
  HWND v6; // rbx
  tagPOINT Point[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (HWND)*((_QWORD *)this - 10);
  *(struct tagRECT *)&Point[0].x = *a2;
  if ( ClientToScreen(v4, Point) )
    ClientToScreen(*((HWND *)this - 10), &Point[1]);
  Parent = GetParent(*((HWND *)this - 10));
  v6 = Parent;
  if ( Parent )
  {
    if ( ScreenToClient(Parent, Point) )
      ScreenToClient(v6, &Point[1]);
  }
  MoveWindow(*((HWND *)this - 10), Point[0].x, Point[0].y, Point[1].x - Point[0].x, Point[1].y - Point[0].y, 1);
  return 0;
}

```

## disassembly

```asm
0x180017ec0  mov     [rsp+arg_10], rbx
0x180017ec5  push    rdi
0x180017ec6  sub     rsp, 50h
0x180017eca  mov     rax, cs:__security_cookie
0x180017ed1  xor     rax, rsp
0x180017ed4  mov     [rsp+58h+var_18], rax
0x180017ed9  mov     rdi, rcx
0x180017edc  test    rdx, rdx
0x180017edf  jnz     short loc_180017EEB
0x180017ee1  mov     eax, 80004003h
0x180017ee6  jmp     loc_180017F78
0x180017eeb  movups  xmm0, xmmword ptr [rdx]
0x180017eee  mov     rcx, [rcx-50h]; hWnd
0x180017ef2  lea     rdx, [rsp+58h+Point]; lpPoint
0x180017ef7  movdqu  xmmword ptr [rsp+58h+Point.x], xmm0
0x180017efd  call    cs:__imp_ClientToScreen
0x180017f03  test    eax, eax
0x180017f05  jz      short loc_180017F16
0x180017f07  mov     rcx, [rdi-50h]; hWnd
0x180017f0b  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x180017f10  call    cs:__imp_ClientToScreen
0x180017f16  mov     rcx, [rdi-50h]; hWnd
0x180017f1a  call    cs:__imp_GetParent
0x180017f20  mov     rbx, rax
0x180017f23  test    rax, rax
0x180017f26  jz      short loc_180017F48
0x180017f28  lea     rdx, [rsp+58h+Point]; lpPoint
0x180017f2d  mov     rcx, rax; hWnd
0x180017f30  call    cs:__imp_ScreenToClient
0x180017f36  test    eax, eax
0x180017f38  jz      short loc_180017F48
0x180017f3a  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x180017f3f  mov     rcx, rbx; hWnd
0x180017f42  call    cs:__imp_ScreenToClient
0x180017f48  mov     eax, [rsp+58h+Point.y+8]
0x180017f4c  mov     r8d, [rsp+58h+Point.y]; Y
0x180017f51  sub     eax, r8d
0x180017f54  mov     r9d, [rsp+58h+Point.x+8]
0x180017f59  mov     edx, [rsp+58h+Point.x]; X
0x180017f5d  sub     r9d, edx; nWidth
0x180017f60  mov     rcx, [rdi-50h]; hWnd
0x180017f64  mov     [rsp+58h+bRepaint], 1; bRepaint
0x180017f6c  mov     [rsp+58h+nHeight], eax; nHeight
0x180017f70  call    cs:__imp_MoveWindow
0x180017f76  xor     eax, eax
0x180017f78  mov     rcx, [rsp+58h+var_18]
0x180017f7d  xor     rcx, rsp; StackCookie
0x180017f80  call    __security_check_cookie
0x180017f85  mov     rbx, [rsp+58h+arg_10]
0x180017f8a  add     rsp, 50h
0x180017f8e  pop     rdi
0x180017f8f  retn
```
