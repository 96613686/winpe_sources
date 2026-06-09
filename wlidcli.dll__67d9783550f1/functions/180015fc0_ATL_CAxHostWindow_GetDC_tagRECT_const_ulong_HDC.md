# ATL::CAxHostWindow::GetDC(tagRECT const *,ulong,HDC__ * *)

- ea: `0x180015fc0`
- end: `0x1800160f3`
- name: `?GetDC@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@KPEAPEAUHDC__@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct tagRECT *, unsigned int, HDC *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002da0`
- `0x180015fc0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180016095`
- `GDI32!DeleteDC` at `0x180016095`
- `GDI32!SelectObject` at `0x18001607e`
- `GDI32!SelectObject` at `0x18001607e`
- `GDI32!CreateCompatibleBitmap` at `0x18001606a`
- `GDI32!CreateCompatibleBitmap` at `0x18001606a`
- `GDI32!CreateCompatibleDC` at `0x180016047`
- `GDI32!CreateCompatibleDC` at `0x180016047`
- `GDI32!DeleteObject` at `0x18001608c`
- `GDI32!DeleteObject` at `0x1800160a0`
- `GDI32!DeleteObject` at `0x18001608c`
- `GDI32!DeleteObject` at `0x1800160a0`
- `USER32!FillRect` at `0x1800160c4`
- `USER32!FillRect` at `0x1800160c4`
- `USER32!GetClientRect` at `0x180016038`
- `USER32!GetClientRect` at `0x180016038`
- `USER32!GetDC` at `0x180016007`
- `USER32!GetDC` at `0x180016007`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetDC(HWND *this, const struct tagRECT *a2, char a3, HDC *a4)
{
  HDC DC; // rax
  HWND v9; // rcx
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v12; // r14
  HDC v13; // rcx
  HGDIOBJ v14; // rax
  tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF

  if ( !a4 )
    return 2147500035LL;
  if ( *((_BYTE *)this + 96) )
  {
    DC = GetDC(*(this - 10));
    *a4 = DC;
    if ( DC )
    {
      *((_BYTE *)this + 96) = 0;
      if ( (a3 & 1) != 0 )
        return 0;
      v9 = *(this - 10);
      Rect = 0;
      GetClientRect(v9, &Rect);
      if ( (a3 & 4) != 0 )
      {
        CompatibleDC = CreateCompatibleDC(*a4);
        if ( CompatibleDC )
        {
          CompatibleBitmap = CreateCompatibleBitmap(*a4, Rect.right - Rect.left, Rect.bottom - Rect.top);
          v12 = CompatibleBitmap;
          v13 = CompatibleDC;
          if ( !CompatibleBitmap )
          {
LABEL_11:
            DeleteDC(v13);
            goto LABEL_13;
          }
          v14 = SelectObject(CompatibleDC, CompatibleBitmap);
          if ( !v14 )
          {
            DeleteObject(v12);
            v13 = CompatibleDC;
            goto LABEL_11;
          }
          DeleteObject(v14);
          this[11] = (HWND)*a4;
          *a4 = CompatibleDC;
        }
      }
LABEL_13:
      if ( (a3 & 2) != 0 )
        FillRect(*a4, &Rect, (HBRUSH)6);
      return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180015fc0  mov     [rsp+arg_8], rbx
0x180015fc5  mov     [rsp+arg_10], rbp
0x180015fca  push    rsi
0x180015fcb  push    rdi
0x180015fcc  push    r14
0x180015fce  sub     rsp, 40h
0x180015fd2  mov     rax, cs:__security_cookie
0x180015fd9  xor     rax, rsp
0x180015fdc  mov     [rsp+58h+var_28], rax
0x180015fe1  mov     rbx, r9
0x180015fe4  mov     ebp, r8d
0x180015fe7  mov     rsi, rcx
0x180015fea  test    r9, r9
0x180015fed  jnz     short loc_180015FF9
0x180015fef  mov     eax, 80004003h
0x180015ff4  jmp     loc_1800160D3
0x180015ff9  cmp     byte ptr [rcx+60h], 0
0x180015ffd  jz      loc_1800160CE
0x180016003  mov     rcx, [rcx-50h]; hWnd
0x180016007  call    cs:__imp_GetDC
0x18001600d  mov     [rbx], rax
0x180016010  test    rax, rax
0x180016013  jz      loc_1800160CE
0x180016019  mov     byte ptr [rsi+60h], 0
0x18001601d  test    bpl, 1
0x180016021  jnz     loc_1800160CA
0x180016027  mov     rcx, [rsi-50h]; hWnd
0x18001602b  lea     rdx, [rsp+58h+Rect]; lpRect
0x180016030  xorps   xmm0, xmm0
0x180016033  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x180016038  call    cs:__imp_GetClientRect
0x18001603e  test    bpl, 4
0x180016042  jz      short loc_1800160B0
0x180016044  mov     rcx, [rbx]; hdc
0x180016047  call    cs:__imp_CreateCompatibleDC
0x18001604d  mov     rdi, rax
0x180016050  test    rax, rax
0x180016053  jz      short loc_1800160B0
0x180016055  mov     r8d, [rsp+58h+Rect.bottom]
0x18001605a  mov     edx, [rsp+58h+Rect.right]
0x18001605e  sub     r8d, [rsp+58h+Rect.top]; cy
0x180016063  sub     edx, [rsp+58h+Rect.left]; cx
0x180016067  mov     rcx, [rbx]; hdc
0x18001606a  call    cs:__imp_CreateCompatibleBitmap
0x180016070  mov     r14, rax
0x180016073  mov     rcx, rdi; hdc
0x180016076  test    rax, rax
0x180016079  jz      short loc_180016095
0x18001607b  mov     rdx, rax; h
0x18001607e  call    cs:__imp_SelectObject
0x180016084  test    rax, rax
0x180016087  jnz     short loc_18001609D
0x180016089  mov     rcx, r14; ho
0x18001608c  call    cs:__imp_DeleteObject
0x180016092  mov     rcx, rdi; hdc
0x180016095  call    cs:__imp_DeleteDC
0x18001609b  jmp     short loc_1800160B0
0x18001609d  mov     rcx, rax; ho
0x1800160a0  call    cs:__imp_DeleteObject
0x1800160a6  mov     rax, [rbx]
0x1800160a9  mov     [rsi+58h], rax
0x1800160ad  mov     [rbx], rdi
0x1800160b0  test    bpl, 2
0x1800160b4  jz      short loc_1800160CA
0x1800160b6  mov     rcx, [rbx]; hDC
0x1800160b9  lea     rdx, [rsp+58h+Rect]; lprc
0x1800160be  mov     r8d, 6; hbr
0x1800160c4  call    cs:__imp_FillRect
0x1800160ca  xor     eax, eax
0x1800160cc  jmp     short loc_1800160D3
0x1800160ce  mov     eax, 80004005h
0x1800160d3  mov     rcx, [rsp+58h+var_28]
0x1800160d8  xor     rcx, rsp; StackCookie
0x1800160db  call    __security_check_cookie
0x1800160e0  mov     rbx, [rsp+58h+arg_8]
0x1800160e5  mov     rbp, [rsp+58h+arg_10]
0x1800160ea  add     rsp, 40h
0x1800160ee  pop     r14
0x1800160f0  pop     rdi
0x1800160f1  pop     rsi
0x1800160f2  retn
```
