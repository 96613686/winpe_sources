# BltColor(HDC__ *,HBRUSH__ *,HDC__ *,int,int,int,int,int,int,uint)

- ea: `0x18003e370`
- end: `0x18003e495`
- name: `?BltColor@@YAXPEAUHDC__@@PEAUHBRUSH__@@0HHHHHHI@Z`
- size: `293`
- prototype: `void __usercall(HDC hdc@<rcx>, HBRUSH h@<rdx>, HDC@<r8>, int@<r9d>, int y, int, int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003c8b0`

## callees

- `0x18003e370`
- `0x18004e6a0`
- `0x180096e00`

## import_xrefs

- `GDI32!SelectObject` at `0x18003e3cc`
- `GDI32!SelectObject` at `0x18003e421`
- `GDI32!SelectObject` at `0x18003e3cc`
- `GDI32!SelectObject` at `0x18003e421`
- `GDI32!SetBkColor` at `0x18003e3be`
- `GDI32!SetBkColor` at `0x18003e437`
- `GDI32!SetBkColor` at `0x18003e3be`
- `GDI32!SetBkColor` at `0x18003e437`
- `GDI32!SetTextColor` at `0x18003e3ae`
- `GDI32!SetTextColor` at `0x18003e42c`
- `GDI32!SetTextColor` at `0x18003e3ae`
- `GDI32!SetTextColor` at `0x18003e42c`
- `GDI32!CreateBrushIndirect` at `0x18003e479`
- `GDI32!CreateBrushIndirect` at `0x18003e479`
- `GDI32!BitBlt` at `0x18003e415`
- `GDI32!BitBlt` at `0x18003e415`
- `GDI32!DeleteObject` at `0x18003e48d`
- `GDI32!DeleteObject` at `0x18003e48d`

## pseudocode

```c
void __fastcall BltColor(HDC hdc, HBRUSH h, HDC a3, int a4, int y, int a6, int cy)
{
  HDC hdcSrc; // r12
  HBRUSH v8; // rbp
  HBRUSH v10; // rbx
  COLORREF v12; // esi
  COLORREF v13; // edi
  HGDIOBJ v14; // rbx
  LOGBRUSH plbrush; // [rsp+50h] [rbp-58h] BYREF

  hdcSrc = ghdcGray;
  v8 = 0;
  v10 = h;
  if ( !h )
  {
    plbrush = 0;
    plbrush.lbColor = GetSysColor(8);
    v10 = CreateBrushIndirect(&plbrush);
    v8 = v10;
  }
  v12 = SetTextColor(hdc, 0);
  v13 = SetBkColor(hdc, 0xFFFFFFu);
  v14 = SelectObject(hdc, v10);
  BitBlt(hdc, a4, y, a6, cy, hdcSrc, 0, 0, 0xB8074Au);
  SelectObject(hdc, v14);
  SetTextColor(hdc, v12);
  SetBkColor(hdc, v13);
  if ( v8 )
    DeleteObject(v8);
}

```

## disassembly

```asm
0x18003e370  push    rbx
0x18003e372  push    rbp
0x18003e373  push    rsi
0x18003e374  push    rdi
0x18003e375  push    r12
0x18003e377  push    r14
0x18003e379  push    r15
0x18003e37b  sub     rsp, 70h
0x18003e37f  mov     rax, cs:__security_cookie
0x18003e386  xor     rax, rsp
0x18003e389  mov     [rsp+0A8h+var_48], rax
0x18003e38e  mov     r12, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x18003e395  xor     ebp, ebp
0x18003e397  mov     r15d, r9d
0x18003e39a  mov     rbx, rdx
0x18003e39d  mov     r14, rcx
0x18003e3a0  test    rdx, rdx
0x18003e3a3  jz      loc_18003E45E
0x18003e3a9  xor     edx, edx; color
0x18003e3ab  mov     rcx, r14; hdc
0x18003e3ae  call    cs:__imp_SetTextColor
0x18003e3b4  mov     edx, 0FFFFFFh; color
0x18003e3b9  mov     rcx, r14; hdc
0x18003e3bc  mov     esi, eax
0x18003e3be  call    cs:__imp_SetBkColor
0x18003e3c4  mov     rdx, rbx; h
0x18003e3c7  mov     rcx, r14; hdc
0x18003e3ca  mov     edi, eax
0x18003e3cc  call    cs:__imp_SelectObject
0x18003e3d2  mov     r8d, [rsp+0A8h+arg_30]
0x18003e3da  mov     edx, r15d; x
0x18003e3dd  mov     r9d, [rsp+0A8h+arg_28]; cx
0x18003e3e5  mov     rcx, r14; hdc
0x18003e3e8  mov     [rsp+0A8h+rop], 0B8074Ah; rop
0x18003e3f0  mov     rbx, rax
0x18003e3f3  mov     [rsp+0A8h+y1], 0; y1
0x18003e3fb  mov     [rsp+0A8h+x1], 0; x1
0x18003e403  mov     [rsp+0A8h+hdcSrc], r12; hdcSrc
0x18003e408  mov     [rsp+0A8h+cy], r8d; cy
0x18003e40d  mov     r8d, [rsp+0A8h+y]; y
0x18003e415  call    cs:__imp_BitBlt
0x18003e41b  mov     rdx, rbx; h
0x18003e41e  mov     rcx, r14; hdc
0x18003e421  call    cs:__imp_SelectObject
0x18003e427  mov     edx, esi; color
0x18003e429  mov     rcx, r14; hdc
0x18003e42c  call    cs:__imp_SetTextColor
0x18003e432  mov     edx, edi; color
0x18003e434  mov     rcx, r14; hdc
0x18003e437  call    cs:__imp_SetBkColor
0x18003e43d  test    rbp, rbp
0x18003e440  jnz     short loc_18003E48A
0x18003e442  mov     rcx, [rsp+0A8h+var_48]
0x18003e447  xor     rcx, rsp; StackCookie
0x18003e44a  call    __security_check_cookie
0x18003e44f  add     rsp, 70h
0x18003e453  pop     r15
0x18003e455  pop     r14
0x18003e457  pop     r12
0x18003e459  pop     rdi
0x18003e45a  pop     rsi
0x18003e45b  pop     rbp
0x18003e45c  pop     rbx
0x18003e45d  retn
0x18003e45e  xorps   xmm0, xmm0
0x18003e461  mov     ecx, 8; nIndex
0x18003e466  movups  xmmword ptr [rsp+0A8h+plbrush.lbStyle], xmm0
0x18003e46b  call    GetSysColor
0x18003e470  lea     rcx, [rsp+0A8h+plbrush]; plbrush
0x18003e475  mov     [rsp+0A8h+plbrush.lbColor], eax
0x18003e479  call    cs:__imp_CreateBrushIndirect
0x18003e47f  mov     rbx, rax
0x18003e482  mov     rbp, rax
0x18003e485  jmp     loc_18003E3A9
0x18003e48a  mov     rcx, rbp; ho
0x18003e48d  call    cs:__imp_DeleteObject
0x18003e493  jmp     short loc_18003E442
```
