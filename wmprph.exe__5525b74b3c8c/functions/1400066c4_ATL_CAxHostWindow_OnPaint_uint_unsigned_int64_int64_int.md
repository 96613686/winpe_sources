# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x1400066c4`
- end: `0x14000692b`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006cf0`

## callees

- `0x140001390`
- `0x140001d26`
- `0x1400066c4`
- `0x14000f010`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x140006761`
- `GDI32!CreateCompatibleBitmap` at `0x140006761`
- `GDI32!SelectObject` at `0x14000678e`
- `GDI32!SelectObject` at `0x140006865`
- `GDI32!SelectObject` at `0x14000678e`
- `GDI32!SelectObject` at `0x140006865`
- `GDI32!CreateCompatibleDC` at `0x140006776`
- `GDI32!CreateCompatibleDC` at `0x140006776`
- `GDI32!DeleteDC` at `0x14000686e`
- `GDI32!DeleteDC` at `0x14000686e`
- `GDI32!DeleteObject` at `0x1400067cb`
- `GDI32!DeleteObject` at `0x14000690d`
- `GDI32!DeleteObject` at `0x1400067cb`
- `GDI32!DeleteObject` at `0x14000690d`
- `GDI32!CreateSolidBrush` at `0x1400067a6`
- `GDI32!CreateSolidBrush` at `0x1400068ec`
- `GDI32!CreateSolidBrush` at `0x1400067a6`
- `GDI32!CreateSolidBrush` at `0x1400068ec`
- `GDI32!BitBlt` at `0x140006859`
- `GDI32!BitBlt` at `0x140006859`
- `USER32!EndPaint` at `0x14000691b`
- `USER32!EndPaint` at `0x14000691b`
- `USER32!BeginPaint` at `0x140006729`
- `USER32!BeginPaint` at `0x1400068c3`
- `USER32!BeginPaint` at `0x140006729`
- `USER32!BeginPaint` at `0x1400068c3`
- `USER32!FillRect` at `0x1400067c2`
- `USER32!FillRect` at `0x140006904`
- `USER32!FillRect` at `0x1400067c2`
- `USER32!FillRect` at `0x140006904`
- `USER32!GetClientRect` at `0x14000674a`
- `USER32!GetClientRect` at `0x1400068e0`
- `USER32!GetClientRect` at `0x14000674a`
- `USER32!GetClientRect` at `0x1400068e0`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPaint(ATL::CAxHostWindow *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HDC v6; // rsi
  HWND v7; // rcx
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // r15
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // r12
  HBITMAP v14; // rcx
  HDC v16; // rsi
  HWND v17; // rcx
  HBRUSH v18; // rax
  HBRUSH v19; // rdi
  struct tagRECT Rect; // [rsp+60h] [rbp-41h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+70h] [rbp-31h] BYREF

  if ( *((_QWORD *)this + 24) )
  {
    if ( (*((_BYTE *)this + 248) & 8) != 0 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      v6 = BeginPaint(*((HWND *)this + 1), &Paint);
      if ( v6 )
      {
        v7 = (HWND)*((_QWORD *)this + 1);
        Rect = 0;
        GetClientRect(v7, &Rect);
        CompatibleBitmap = CreateCompatibleBitmap(v6, Rect.right - Rect.left, Rect.bottom - Rect.top);
        if ( CompatibleBitmap )
        {
          CompatibleDC = CreateCompatibleDC(v6);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            v11 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( v11 )
            {
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 74));
              v13 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v13);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 24) + 24LL))(
                  *((_QWORD *)this + 24),
                  1,
                  0xFFFFFFFFLL);
                BitBlt(v6, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u);
              }
              SelectObject(hdcSrc, v11);
            }
            DeleteDC(hdcSrc);
          }
          v14 = CompatibleBitmap;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 0;
  }
  memset_0(&Paint, 0, sizeof(Paint));
  v16 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( !v16 )
    return 0;
  v17 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  GetClientRect(v17, &Rect);
  v18 = CreateSolidBrush(*((_DWORD *)this + 74));
  v19 = v18;
  if ( v18 )
  {
    FillRect(v16, &Rect, v18);
    v14 = (HBITMAP)v19;
LABEL_17:
    DeleteObject(v14);
  }
LABEL_18:
  EndPaint(*((HWND *)this + 1), &Paint);
  return 1;
}

```

## disassembly

```asm
0x1400066c4  mov     [rsp-8+arg_8], rbx
0x1400066c9  mov     [rsp-8+arg_10], rsi
0x1400066ce  push    rbp
0x1400066cf  push    rdi
0x1400066d0  push    r12
0x1400066d2  push    r14
0x1400066d4  push    r15
0x1400066d6  lea     rbp, [rsp-2Fh]
0x1400066db  sub     rsp, 0D0h
0x1400066e2  mov     rax, cs:__security_cookie
0x1400066e9  xor     rax, rsp
0x1400066ec  mov     [rbp+4Fh+var_30], rax
0x1400066f0  cmp     qword ptr [rcx+0C0h], 0
0x1400066f8  mov     rbx, rcx
0x1400066fb  mov     rax, [rbp+4Fh+arg_20]
0x1400066ff  jz      loc_1400068AC
0x140006705  test    byte ptr [rcx+0F8h], 8
0x14000670c  jz      loc_14000687C
0x140006712  xor     edx, edx; Val
0x140006714  lea     rcx, [rbp+4Fh+Paint]; void *
0x140006718  lea     r8d, [rdx+48h]; Size
0x14000671c  call    memset_0
0x140006721  mov     rcx, [rbx+8]; hWnd
0x140006725  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x140006729  call    cs:__imp_BeginPaint
0x14000672f  mov     rsi, rax
0x140006732  test    rax, rax
0x140006735  jz      loc_140006882
0x14000673b  mov     rcx, [rbx+8]; hWnd
0x14000673f  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x140006743  xorps   xmm0, xmm0
0x140006746  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x14000674a  call    cs:__imp_GetClientRect
0x140006750  mov     r8d, [rbp+4Fh+Rect.bottom]
0x140006754  mov     rcx, rsi; hdc
0x140006757  mov     edx, [rbp+4Fh+Rect.right]
0x14000675a  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x14000675e  sub     edx, [rbp+4Fh+Rect.left]; cx
0x140006761  call    cs:__imp_CreateCompatibleBitmap
0x140006767  mov     r14, rax
0x14000676a  test    rax, rax
0x14000676d  jz      loc_140006913
0x140006773  mov     rcx, rsi; hdc
0x140006776  call    cs:__imp_CreateCompatibleDC
0x14000677c  mov     rdi, rax
0x14000677f  test    rax, rax
0x140006782  jz      loc_140006874
0x140006788  mov     rdx, r14; h
0x14000678b  mov     rcx, rax; hdc
0x14000678e  call    cs:__imp_SelectObject
0x140006794  mov     r15, rax
0x140006797  test    rax, rax
0x14000679a  jz      loc_14000686B
0x1400067a0  mov     ecx, [rbx+128h]; color
0x1400067a6  call    cs:__imp_CreateSolidBrush
0x1400067ac  mov     r12, rax
0x1400067af  test    rax, rax
0x1400067b2  jz      loc_14000685F
0x1400067b8  mov     r8, rax; hbr
0x1400067bb  lea     rdx, [rbp+4Fh+Rect]; lprc
0x1400067bf  mov     rcx, rdi; hDC
0x1400067c2  call    cs:__imp_FillRect
0x1400067c8  mov     rcx, r12; ho
0x1400067cb  call    cs:__imp_DeleteObject
0x1400067d1  mov     rcx, [rbx+0C0h]
0x1400067d8  lea     rdx, [rbx+114h]
0x1400067df  mov     [rsp+0F0h+var_A0], 0
0x1400067e8  xor     r9d, r9d
0x1400067eb  mov     [rsp+0F0h+var_A8], 0
0x1400067f4  or      r8d, 0FFFFFFFFh
0x1400067f8  mov     qword ptr [rsp+0F0h+rop], rdx
0x1400067fd  mov     rax, [rcx]
0x140006800  mov     qword ptr [rsp+0F0h+y1], rdx
0x140006805  lea     edx, [r9+1]
0x140006809  mov     qword ptr [rsp+0F0h+x1], rdi
0x14000680e  mov     [rsp+0F0h+hdcSrc], 0
0x140006817  mov     rax, [rax+18h]
0x14000681b  mov     qword ptr [rsp+0F0h+cy], 0
0x140006824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006829  mov     eax, [rbp+4Fh+Rect.bottom]
0x14000682c  xor     r8d, r8d; y
0x14000682f  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x140006833  xor     edx, edx; x
0x140006835  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x14000683d  mov     rcx, rsi; hdc
0x140006840  mov     [rsp+0F0h+y1], 0; y1
0x140006848  mov     [rsp+0F0h+x1], 0; x1
0x140006850  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x140006855  mov     [rsp+0F0h+cy], eax; cy
0x140006859  call    cs:__imp_BitBlt
0x14000685f  mov     rdx, r15; h
0x140006862  mov     rcx, rdi; hdc
0x140006865  call    cs:__imp_SelectObject
0x14000686b  mov     rcx, rdi; hdc
0x14000686e  call    cs:__imp_DeleteDC
0x140006874  mov     rcx, r14
0x140006877  jmp     loc_14000690D
0x14000687c  mov     dword ptr [rax], 0
0x140006882  xor     eax, eax
0x140006884  mov     rcx, [rbp+4Fh+var_30]
0x140006888  xor     rcx, rsp; StackCookie
0x14000688b  call    __security_check_cookie
0x140006890  lea     r11, [rsp+0F0h+var_20]
0x140006898  mov     rbx, [r11+38h]
0x14000689c  mov     rsi, [r11+40h]
0x1400068a0  mov     rsp, r11
0x1400068a3  pop     r15
0x1400068a5  pop     r14
0x1400068a7  pop     r12
0x1400068a9  pop     rdi
0x1400068aa  pop     rbp
0x1400068ab  retn
0x1400068ac  xor     edx, edx; Val
0x1400068ae  lea     rcx, [rbp+4Fh+Paint]; void *
0x1400068b2  lea     r8d, [rdx+48h]; Size
0x1400068b6  call    memset_0
0x1400068bb  mov     rcx, [rbx+8]; hWnd
0x1400068bf  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1400068c3  call    cs:__imp_BeginPaint
0x1400068c9  mov     rsi, rax
0x1400068cc  test    rax, rax
0x1400068cf  jz      short loc_140006882
0x1400068d1  mov     rcx, [rbx+8]; hWnd
0x1400068d5  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1400068d9  xorps   xmm0, xmm0
0x1400068dc  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1400068e0  call    cs:__imp_GetClientRect
0x1400068e6  mov     ecx, [rbx+128h]; color
0x1400068ec  call    cs:__imp_CreateSolidBrush
0x1400068f2  mov     rdi, rax
0x1400068f5  test    rax, rax
0x1400068f8  jz      short loc_140006913
0x1400068fa  mov     r8, rax; hbr
0x1400068fd  lea     rdx, [rbp+4Fh+Rect]; lprc
0x140006901  mov     rcx, rsi; hDC
0x140006904  call    cs:__imp_FillRect
0x14000690a  mov     rcx, rdi; ho
0x14000690d  call    cs:__imp_DeleteObject
0x140006913  mov     rcx, [rbx+8]; hWnd
0x140006917  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x14000691b  call    cs:__imp_EndPaint
0x140006921  mov     eax, 1
0x140006926  jmp     loc_140006884
```
