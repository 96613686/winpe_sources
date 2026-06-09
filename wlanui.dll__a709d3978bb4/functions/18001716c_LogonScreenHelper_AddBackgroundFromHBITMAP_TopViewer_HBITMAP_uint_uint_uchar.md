# LogonScreenHelper::AddBackgroundFromHBITMAP(TopViewer *,HBITMAP__ *,uint,uint,uchar)

- ea: `0x18001716c`
- end: `0x18001728f`
- name: `?AddBackgroundFromHBITMAP@LogonScreenHelper@@QEAAPEAVValue@DirectUI@@PEAVTopViewer@@PEAUHBITMAP__@@IIE@Z`
- size: `291`
- prototype: `struct DirectUI::Value *__fastcall(LogonScreenHelper *__hidden this, struct TopViewer *, HBITMAP, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800176d0`

## callees

- `0x18001716c`
- `0x180017bc0`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `USER32!GetWindowInfo` at `0x1800171cc`
- `USER32!GetWindowInfo` at `0x1800171cc`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180017216`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180017216`
- `gdiplus!GdipAlloc` at `0x1800171f1`
- `gdiplus!GdipAlloc` at `0x1800171f1`

## pseudocode

```c
struct DirectUI::Value *__fastcall LogonScreenHelper::AddBackgroundFromHBITMAP(
        LogonScreenHelper *this,
        struct TopViewer *a2,
        HBITMAP a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rcx
  LONG top; // esi
  struct DirectUI::Value *v9; // rdi
  LONG left; // r14d
  LONG bottom; // r15d
  LONG right; // r12d
  __int64 v13; // rbx
  int v14; // eax
  LogonScreenHelper *v15; // rcx
  struct tagRECT v17; // [rsp+50h] [rbp-49h] BYREF
  struct tagWINDOWINFO pwi; // [rsp+60h] [rbp-39h] BYREF

  v5 = *((_QWORD *)a2 + 35);
  memset(&pwi, 0, sizeof(pwi));
  pwi.cbSize = 60;
  if ( !GetWindowInfo(*(HWND *)(v5 + 8), &pwi) )
    return 0;
  top = pwi.rcClient.top;
  v9 = 0;
  left = pwi.rcClient.left;
  bottom = pwi.rcClient.bottom;
  right = pwi.rcClient.right;
  v13 = GdipAlloc(24);
  if ( v13 )
  {
    *(_QWORD *)&v17.left = 0;
    *(_QWORD *)v13 = &Gdiplus::Image::`vftable';
    v14 = GdipCreateBitmapFromHBITMAP(a3, 0, &v17);
    v15 = *(LogonScreenHelper **)&v17.left;
    *(_DWORD *)(v13 + 16) = v14;
    *(_QWORD *)(v13 + 8) = v15;
    v17.left = left;
    v17.top = top;
    v17.right = right;
    v17.bottom = bottom;
    v9 = LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(v15, (struct Gdiplus::Bitmap *)v13, a4, a5, &v17);
    (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
  }
  return v9;
}

```

## disassembly

```asm
0x18001716c  mov     [rsp-8+arg_0], rbx
0x180017171  push    rbp
0x180017172  push    rsi
0x180017173  push    rdi
0x180017174  push    r12
0x180017176  push    r13
0x180017178  push    r14
0x18001717a  push    r15
0x18001717c  lea     rbp, [rsp-17h]
0x180017181  sub     rsp, 0B0h
0x180017188  mov     rax, cs:__security_cookie
0x18001718f  xor     rax, rsp
0x180017192  mov     [rbp+47h+var_40], rax
0x180017196  mov     rcx, [rdx+118h]
0x18001719d  xorps   xmm0, xmm0
0x1800171a0  mov     eax, [rbp+47h+arg_20]
0x1800171a3  lea     rdx, [rbp+47h+pwi]; pwi
0x1800171a7  movups  xmmword ptr [rbp+47h+pwi.cbSize], xmm0
0x1800171ab  mov     [rbp+47h+pwi.cbSize], 3Ch ; '<'
0x1800171b2  mov     r13, r8
0x1800171b5  movups  xmmword ptr [rbp+47h+pwi.rcClient.bottom], xmm0
0x1800171b9  mov     [rbp+47h+var_9C], r9d
0x1800171bd  movups  xmmword ptr [rbp+47h+pwi.rcWindow.bottom], xmm0
0x1800171c1  mov     [rbp+47h+var_A0], eax
0x1800171c4  movups  xmmword ptr [rbp+47h+pwi.dwWindowStatus], xmm0
0x1800171c8  mov     rcx, [rcx+8]; hwnd
0x1800171cc  call    cs:__imp_GetWindowInfo
0x1800171d2  test    eax, eax
0x1800171d4  jnz     short loc_1800171DD
0x1800171d6  xor     eax, eax
0x1800171d8  jmp     loc_180017268
0x1800171dd  mov     esi, [rbp+47h+pwi.rcClient.top]
0x1800171e0  xor     edi, edi
0x1800171e2  mov     r14d, [rbp+47h+pwi.rcClient.left]
0x1800171e6  mov     r15d, [rbp+47h+pwi.rcClient.bottom]
0x1800171ea  mov     r12d, [rbp+47h+pwi.rcClient.right]
0x1800171ee  lea     ecx, [rdi+18h]
0x1800171f1  call    cs:__imp_GdipAlloc
0x1800171f7  mov     rbx, rax
0x1800171fa  test    rax, rax
0x1800171fd  jz      short loc_180017265
0x1800171ff  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180017206  mov     qword ptr [rbp+47h+var_90.left], rdi
0x18001720a  lea     r8, [rbp+47h+var_90]
0x18001720e  mov     [rbx], rax
0x180017211  xor     edx, edx
0x180017213  mov     rcx, r13
0x180017216  call    cs:__imp_GdipCreateBitmapFromHBITMAP
0x18001721c  mov     rcx, qword ptr [rbp+47h+var_90.left]; this
0x180017220  mov     rdx, rbx; struct Gdiplus::Bitmap *
0x180017223  mov     r9d, [rbp+47h+var_A0]; unsigned int
0x180017227  mov     r8d, [rbp+47h+var_9C]; unsigned int
0x18001722b  mov     [rbx+10h], eax
0x18001722e  lea     rax, [rbp+47h+var_90]
0x180017232  mov     [rsp+0E0h+var_C0], rax; struct tagRECT *
0x180017237  mov     [rbx+8], rcx
0x18001723b  mov     [rbp+47h+var_90.left], r14d
0x18001723f  mov     [rbp+47h+var_90.top], esi
0x180017242  mov     [rbp+47h+var_90.right], r12d
0x180017246  mov     [rbp+47h+var_90.bottom], r15d
0x18001724a  call    ?CreateDuiBitmapFromGDIPlusBitmap@LogonScreenHelper@@QEAAPEAVValue@DirectUI@@PEAVBitmap@Gdiplus@@IIUtagRECT@@E_N@Z; LogonScreenHelper::CreateDuiBitmapFromGDIPlusBitmap(Gdiplus::Bitmap *,uint,uint,tagRECT,uchar,bool)
0x18001724f  mov     rcx, [rbx]
0x180017252  mov     rdi, rax
0x180017255  mov     edx, 1
0x18001725a  mov     rax, [rcx]
0x18001725d  mov     rcx, rbx
0x180017260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017265  mov     rax, rdi
0x180017268  mov     rcx, [rbp+47h+var_40]
0x18001726c  xor     rcx, rsp; StackCookie
0x18001726f  call    __security_check_cookie
0x180017274  mov     rbx, [rsp+0E0h+arg_0]
0x18001727c  add     rsp, 0B0h
0x180017283  pop     r15
0x180017285  pop     r14
0x180017287  pop     r13
0x180017289  pop     r12
0x18001728b  pop     rdi
0x18001728c  pop     rsi
0x18001728d  pop     rbp
0x18001728e  retn
```
