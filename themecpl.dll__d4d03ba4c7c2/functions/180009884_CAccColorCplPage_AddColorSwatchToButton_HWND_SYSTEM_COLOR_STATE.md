# CAccColorCplPage::_AddColorSwatchToButton(HWND__ *,SYSTEM_COLOR_STATE *)

- ea: `0x180009884`
- end: `0x180009a90`
- name: `?_AddColorSwatchToButton@CAccColorCplPage@@AEAAXPEAUHWND__@@PEAUSYSTEM_COLOR_STATE@@@Z`
- size: `524`
- prototype: `void(CAccColorCplPage *__hidden this, HWND, struct SYSTEM_COLOR_STATE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009ba8`
- `0x18000a20c`
- `0x18000a754`

## callees

- `0x180002280`
- `0x180002f10`
- `0x180008d9c`
- `0x180009884`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800098ba`
- `GDI32!CreateCompatibleDC` at `0x1800098ba`
- `GDI32!SelectObject` at `0x180009957`
- `GDI32!SelectObject` at `0x180009a27`
- `GDI32!SelectObject` at `0x180009957`
- `GDI32!SelectObject` at `0x180009a27`
- `GDI32!DeleteDC` at `0x180009a61`
- `GDI32!DeleteDC` at `0x180009a61`
- `GDI32!DeleteObject` at `0x1800099ee`
- `GDI32!DeleteObject` at `0x180009a52`
- `GDI32!DeleteObject` at `0x1800099ee`
- `GDI32!DeleteObject` at `0x180009a52`
- `GDI32!CreateSolidBrush` at `0x1800099c1`
- `GDI32!CreateSolidBrush` at `0x1800099c1`
- `USER32!SendMessageW` at `0x180009a42`
- `USER32!SendMessageW` at `0x180009a42`
- `USER32!FillRect` at `0x1800099df`
- `USER32!FillRect` at `0x1800099df`
- `USER32!FrameRect` at `0x180009a15`
- `USER32!FrameRect` at `0x180009a15`
- `USER32!GetSysColorBrush` at `0x1800099ff`
- `USER32!GetSysColorBrush` at `0x1800099ff`
- `DUI70!GetScaleFactor` at `0x1800098da`
- `DUI70!GetScaleFactor` at `0x180009902`
- `DUI70!GetScaleFactor` at `0x18000996e`
- `DUI70!GetScaleFactor` at `0x180009996`
- `DUI70!GetScaleFactor` at `0x1800098da`
- `DUI70!GetScaleFactor` at `0x180009902`
- `DUI70!GetScaleFactor` at `0x18000996e`
- `DUI70!GetScaleFactor` at `0x180009996`

## pseudocode

```c
void __fastcall CAccColorCplPage::_AddColorSwatchToButton(
        CAccColorCplPage *this,
        HWND a2,
        struct SYSTEM_COLOR_STATE *a3)
{
  __int64 v5; // rcx
  HDC CompatibleDC; // rbx
  float ScaleFactor; // xmm0_4
  __int64 v8; // rcx
  float v9; // xmm0_4
  HGDIOBJ v10; // r15
  __int64 v11; // rcx
  float v12; // xmm0_4
  float v13; // xmm0_4
  float v14; // xmm0_4
  COLORREF v15; // ecx
  HBRUSH SolidBrush; // rax
  HBRUSH v17; // rdi
  HBRUSH SysColorBrush; // rax
  HGDIOBJ h; // [rsp+20h] [rbp-30h] BYREF
  void *v20; // [rsp+28h] [rbp-28h] BYREF
  RECT rc; // [rsp+30h] [rbp-20h] BYREF

  if ( *(_QWORD *)a3 )
  {
    CompatibleDC = CreateCompatibleDC(0);
    if ( CompatibleDC )
    {
      h = 0;
      ScaleFactor = GetScaleFactor(v5);
      rc.left = (int)floorf((float)(ScaleFactor * 16.0) + 0.5);
      v9 = GetScaleFactor(v8);
      v20 = 0;
      rc.top = -(int)floorf((float)(v9 * 16.0) + 0.5);
      if ( (int)Create32BitHBITMAP(CompatibleDC, (const struct tagSIZE *)&rc, &v20, (HBITMAP *)&h) >= 0 )
      {
        v10 = SelectObject(CompatibleDC, h);
        *(_QWORD *)&rc.left = 0;
        v12 = GetScaleFactor(v11);
        rc.right = (int)floorf((float)(v12 * 16.0) + 0.5);
        v13 = GetScaleFactor((unsigned int)rc.right);
        v14 = floorf((float)(v13 * 16.0) + 0.5);
        v15 = *((_DWORD *)a3 + 3);
        rc.bottom = (int)v14;
        SolidBrush = CreateSolidBrush(v15);
        v17 = SolidBrush;
        if ( SolidBrush )
        {
          FillRect(CompatibleDC, &rc, SolidBrush);
          DeleteObject(v17);
        }
        SysColorBrush = GetSysColorBrush(18);
        FrameRect(CompatibleDC, &rc, SysColorBrush);
        SelectObject(CompatibleDC, v10);
        SendMessageW(a2, 0xF7u, 0, (LPARAM)h);
        DeleteObject(h);
      }
      DeleteDC(CompatibleDC);
    }
  }
}

```

## disassembly

```asm
0x180009884  mov     [rsp-18h+arg_0], rbx
0x180009889  mov     [rsp-18h+arg_18], rdi
0x18000988e  push    rbp
0x18000988f  push    r14
0x180009891  push    r15
0x180009893  mov     rbp, rsp
0x180009896  sub     rsp, 50h
0x18000989a  mov     rax, cs:__security_cookie
0x1800098a1  xor     rax, rsp
0x1800098a4  mov     [rbp+var_10], rax
0x1800098a8  cmp     qword ptr [r8], 0
0x1800098ac  mov     rdi, r8
0x1800098af  mov     r14, rdx
0x1800098b2  jz      loc_180009A6D
0x1800098b8  xor     ecx, ecx; hdc
0x1800098ba  call    cs:__imp_CreateCompatibleDC
0x1800098c1  nop     dword ptr [rax+rax+00h]
0x1800098c6  mov     rbx, rax
0x1800098c9  test    rax, rax
0x1800098cc  jz      loc_180009A6D
0x1800098d2  mov     [rbp+h], 0
0x1800098da  call    cs:__imp_GetScaleFactor
0x1800098e1  nop     dword ptr [rax+rax+00h]
0x1800098e6  mulss   xmm0, cs:__real@41800000
0x1800098ee  addss   xmm0, cs:__real@3f000000; X
0x1800098f6  call    floorf
0x1800098fb  cvttss2si eax, xmm0
0x1800098ff  mov     [rbp+rc.left], eax
0x180009902  call    cs:__imp_GetScaleFactor
0x180009909  nop     dword ptr [rax+rax+00h]
0x18000990e  mulss   xmm0, cs:__real@41800000
0x180009916  addss   xmm0, cs:__real@3f000000; X
0x18000991e  call    floorf
0x180009923  cvttss2si eax, xmm0
0x180009927  lea     r9, [rbp+h]; HBITMAP *
0x18000992b  mov     [rbp+var_28], 0
0x180009933  lea     r8, [rbp+var_28]; void **
0x180009937  mov     rcx, rbx; hDC
0x18000993a  lea     rdx, [rbp+rc]; struct tagSIZE *
0x18000993e  neg     eax
0x180009940  mov     [rbp+rc.top], eax
0x180009943  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180009948  test    eax, eax
0x18000994a  js      loc_180009A5E
0x180009950  mov     rdx, [rbp+h]; h
0x180009954  mov     rcx, rbx; hdc
0x180009957  call    cs:__imp_SelectObject
0x18000995e  nop     dword ptr [rax+rax+00h]
0x180009963  mov     r15, rax
0x180009966  mov     qword ptr [rbp+rc.left], 0
0x18000996e  call    cs:__imp_GetScaleFactor
0x180009975  nop     dword ptr [rax+rax+00h]
0x18000997a  mulss   xmm0, cs:__real@41800000
0x180009982  addss   xmm0, cs:__real@3f000000; X
0x18000998a  call    floorf
0x18000998f  cvttss2si ecx, xmm0
0x180009993  mov     [rbp+rc.right], ecx
0x180009996  call    cs:__imp_GetScaleFactor
0x18000999d  nop     dword ptr [rax+rax+00h]
0x1800099a2  mulss   xmm0, cs:__real@41800000
0x1800099aa  addss   xmm0, cs:__real@3f000000; X
0x1800099b2  call    floorf
0x1800099b7  mov     ecx, [rdi+0Ch]; color
0x1800099ba  cvttss2si eax, xmm0
0x1800099be  mov     [rbp+rc.bottom], eax
0x1800099c1  call    cs:__imp_CreateSolidBrush
0x1800099c8  nop     dword ptr [rax+rax+00h]
0x1800099cd  mov     rdi, rax
0x1800099d0  test    rax, rax
0x1800099d3  jz      short loc_1800099FA
0x1800099d5  mov     r8, rax; hbr
0x1800099d8  lea     rdx, [rbp+rc]; lprc
0x1800099dc  mov     rcx, rbx; hDC
0x1800099df  call    cs:__imp_FillRect
0x1800099e6  nop     dword ptr [rax+rax+00h]
0x1800099eb  mov     rcx, rdi; ho
0x1800099ee  call    cs:__imp_DeleteObject
0x1800099f5  nop     dword ptr [rax+rax+00h]
0x1800099fa  mov     ecx, 12h; nIndex
0x1800099ff  call    cs:__imp_GetSysColorBrush
0x180009a06  nop     dword ptr [rax+rax+00h]
0x180009a0b  lea     rdx, [rbp+rc]; lprc
0x180009a0f  mov     rcx, rbx; hDC
0x180009a12  mov     r8, rax; hbr
0x180009a15  call    cs:__imp_FrameRect
0x180009a1c  nop     dword ptr [rax+rax+00h]
0x180009a21  mov     rdx, r15; h
0x180009a24  mov     rcx, rbx; hdc
0x180009a27  call    cs:__imp_SelectObject
0x180009a2e  nop     dword ptr [rax+rax+00h]
0x180009a33  mov     r9, [rbp+h]; lParam
0x180009a37  xor     r8d, r8d; wParam
0x180009a3a  mov     edx, 0F7h; Msg
0x180009a3f  mov     rcx, r14; hWnd
0x180009a42  call    cs:__imp_SendMessageW
0x180009a49  nop     dword ptr [rax+rax+00h]
0x180009a4e  mov     rcx, [rbp+h]; ho
0x180009a52  call    cs:__imp_DeleteObject
0x180009a59  nop     dword ptr [rax+rax+00h]
0x180009a5e  mov     rcx, rbx; hdc
0x180009a61  call    cs:__imp_DeleteDC
0x180009a68  nop     dword ptr [rax+rax+00h]
0x180009a6d  mov     rcx, [rbp+var_10]
0x180009a71  xor     rcx, rsp; StackCookie
0x180009a74  call    __security_check_cookie
0x180009a79  lea     r11, [rsp+50h+var_s0]
0x180009a7e  mov     rbx, [r11+20h]
0x180009a82  mov     rdi, [r11+38h]
0x180009a86  mov     rsp, r11
0x180009a89  pop     r15
0x180009a8b  pop     r14
0x180009a8d  pop     rbp
0x180009a8e  retn
```
