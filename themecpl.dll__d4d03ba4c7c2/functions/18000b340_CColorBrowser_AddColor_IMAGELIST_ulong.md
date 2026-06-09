# CColorBrowser::AddColor(_IMAGELIST *,ulong)

- ea: `0x18000b340`
- end: `0x18000b499`
- name: `?AddColor@CColorBrowser@@AEAAHPEAU_IMAGELIST@@K@Z`
- size: `345`
- prototype: `int(CColorBrowser *__hidden this, struct _IMAGELIST *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b890`

## callees

- `0x180002280`
- `0x18000b340`
- `0x18005521c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18000b38b`
- `GDI32!CreateCompatibleDC` at `0x18000b38b`
- `GDI32!SelectObject` at `0x18000b3ca`
- `GDI32!SelectObject` at `0x18000b425`
- `GDI32!SelectObject` at `0x18000b3ca`
- `GDI32!SelectObject` at `0x18000b425`
- `GDI32!CreateCompatibleBitmap` at `0x18000b3ac`
- `GDI32!CreateCompatibleBitmap` at `0x18000b3ac`
- `GDI32!DeleteDC` at `0x18000b453`
- `GDI32!DeleteDC` at `0x18000b453`
- `GDI32!DeleteObject` at `0x18000b413`
- `GDI32!DeleteObject` at `0x18000b444`
- `GDI32!DeleteObject` at `0x18000b413`
- `GDI32!DeleteObject` at `0x18000b444`
- `GDI32!CreateSolidBrush` at `0x18000b3ea`
- `GDI32!CreateSolidBrush` at `0x18000b3ea`
- `USER32!GetDC` at `0x18000b370`
- `USER32!GetDC` at `0x18000b370`
- `USER32!ReleaseDC` at `0x18000b464`
- `USER32!ReleaseDC` at `0x18000b464`
- `USER32!FillRect` at `0x18000b404`
- `USER32!FillRect` at `0x18000b404`

## pseudocode

```c
__int64 __fastcall CColorBrowser::AddColor(CColorBrowser *this, struct _IMAGELIST *a2, COLORREF a3)
{
  unsigned int v5; // ebx
  HDC DC; // rax
  HDC v7; // rsi
  HDC CompatibleDC; // rbp
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v10; // r14
  HGDIOBJ v11; // rax
  void *v12; // rdi
  HBRUSH SolidBrush; // rbx
  RECT rc; // [rsp+20h] [rbp-48h] BYREF

  v5 = -1;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      CompatibleBitmap = CreateCompatibleBitmap(v7, 60, 60);
      v10 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v11 = SelectObject(CompatibleDC, CompatibleBitmap);
        rc = (RECT)_mm_load_si128((const __m128i *)&_xmm);
        v12 = v11;
        SolidBrush = CreateSolidBrush(a3);
        FillRect(CompatibleDC, &rc, SolidBrush);
        DeleteObject(SolidBrush);
        SelectObject(CompatibleDC, v12);
        v5 = ImageList_Add(a2, v10, 0);
        DeleteObject(v10);
      }
      DeleteDC(CompatibleDC);
    }
    ReleaseDC(0, v7);
  }
  return v5;
}

```

## disassembly

```asm
0x18000b340  mov     [rsp+arg_0], rbx
0x18000b345  mov     [rsp+arg_18], rbp
0x18000b34a  push    rsi
0x18000b34b  push    rdi
0x18000b34c  push    r12
0x18000b34e  push    r14
0x18000b350  push    r15
0x18000b352  sub     rsp, 40h
0x18000b356  mov     rax, cs:__security_cookie
0x18000b35d  xor     rax, rsp
0x18000b360  mov     [rsp+68h+var_38], rax
0x18000b365  xor     ecx, ecx; hWnd
0x18000b367  mov     r12d, r8d
0x18000b36a  mov     r15, rdx
0x18000b36d  or      ebx, 0FFFFFFFFh
0x18000b370  call    cs:__imp_GetDC
0x18000b377  nop     dword ptr [rax+rax+00h]
0x18000b37c  mov     rsi, rax
0x18000b37f  test    rax, rax
0x18000b382  jz      loc_18000B470
0x18000b388  mov     rcx, rax; hdc
0x18000b38b  call    cs:__imp_CreateCompatibleDC
0x18000b392  nop     dword ptr [rax+rax+00h]
0x18000b397  mov     rbp, rax
0x18000b39a  test    rax, rax
0x18000b39d  jz      loc_18000B45F
0x18000b3a3  lea     edx, [rbx+3Dh]; cx
0x18000b3a6  mov     rcx, rsi; hdc
0x18000b3a9  mov     r8d, edx; cy
0x18000b3ac  call    cs:__imp_CreateCompatibleBitmap
0x18000b3b3  nop     dword ptr [rax+rax+00h]
0x18000b3b8  mov     r14, rax
0x18000b3bb  test    rax, rax
0x18000b3be  jz      loc_18000B450
0x18000b3c4  mov     rdx, rax; h
0x18000b3c7  mov     rcx, rbp; hdc
0x18000b3ca  call    cs:__imp_SelectObject
0x18000b3d1  nop     dword ptr [rax+rax+00h]
0x18000b3d6  movdqa  xmm0, cs:__xmm@0000003c0000003c0000000000000000
0x18000b3de  mov     ecx, r12d; color
0x18000b3e1  movdqu  xmmword ptr [rsp+68h+rc.left], xmm0
0x18000b3e7  mov     rdi, rax
0x18000b3ea  call    cs:__imp_CreateSolidBrush
0x18000b3f1  nop     dword ptr [rax+rax+00h]
0x18000b3f6  lea     rdx, [rsp+68h+rc]; lprc
0x18000b3fb  mov     rcx, rbp; hDC
0x18000b3fe  mov     r8, rax; hbr
0x18000b401  mov     rbx, rax
0x18000b404  call    cs:__imp_FillRect
0x18000b40b  nop     dword ptr [rax+rax+00h]
0x18000b410  mov     rcx, rbx; ho
0x18000b413  call    cs:__imp_DeleteObject
0x18000b41a  nop     dword ptr [rax+rax+00h]
0x18000b41f  mov     rdx, rdi; h
0x18000b422  mov     rcx, rbp; hdc
0x18000b425  call    cs:__imp_SelectObject
0x18000b42c  nop     dword ptr [rax+rax+00h]
0x18000b431  xor     r8d, r8d; hbmMask
0x18000b434  mov     rdx, r14; hbmImage
0x18000b437  mov     rcx, r15; himl
0x18000b43a  call    ImageList_Add
0x18000b43f  mov     rcx, r14; ho
0x18000b442  mov     ebx, eax
0x18000b444  call    cs:__imp_DeleteObject
0x18000b44b  nop     dword ptr [rax+rax+00h]
0x18000b450  mov     rcx, rbp; hdc
0x18000b453  call    cs:__imp_DeleteDC
0x18000b45a  nop     dword ptr [rax+rax+00h]
0x18000b45f  mov     rdx, rsi; hDC
0x18000b462  xor     ecx, ecx; hWnd
0x18000b464  call    cs:__imp_ReleaseDC
0x18000b46b  nop     dword ptr [rax+rax+00h]
0x18000b470  mov     eax, ebx
0x18000b472  mov     rcx, [rsp+68h+var_38]
0x18000b477  xor     rcx, rsp; StackCookie
0x18000b47a  call    __security_check_cookie
0x18000b47f  lea     r11, [rsp+68h+var_28]
0x18000b484  mov     rbx, [r11+30h]
0x18000b488  mov     rbp, [r11+48h]
0x18000b48c  mov     rsp, r11
0x18000b48f  pop     r15
0x18000b491  pop     r14
0x18000b493  pop     r12
0x18000b495  pop     rdi
0x18000b496  pop     rsi
0x18000b497  retn
```
