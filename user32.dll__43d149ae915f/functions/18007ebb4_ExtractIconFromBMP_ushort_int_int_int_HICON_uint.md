# ExtractIconFromBMP(ushort *,int,int,int,HICON__ * *,uint)

- ea: `0x18007ebb4`
- end: `0x18007edc0`
- name: `?ExtractIconFromBMP@@YAIPEAGHHHPEAPEAUHICON__@@I@Z`
- size: `524`
- prototype: `unsigned int __usercall@<eax>(PCWSTR SourceString@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, HICON *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031a30`

## callees

- `0x180005950`
- `0x18002d750`
- `0x18007ebb4`

## import_xrefs

- `GDI32!SelectObject` at `0x18007ec69`
- `GDI32!SelectObject` at `0x18007ec80`
- `GDI32!SelectObject` at `0x18007ec69`
- `GDI32!SelectObject` at `0x18007ec80`
- `GDI32!SetBkColor` at `0x18007ec99`
- `GDI32!SetBkColor` at `0x18007ec99`
- `GDI32!GetPixel` at `0x18007ec8e`
- `GDI32!GetPixel` at `0x18007ec8e`
- `GDI32!CreateBitmap` at `0x18007ec4f`
- `GDI32!CreateBitmap` at `0x18007ec4f`
- `GDI32!BitBlt` at `0x18007ecd0`
- `GDI32!BitBlt` at `0x18007ed07`
- `GDI32!BitBlt` at `0x18007ecd0`
- `GDI32!BitBlt` at `0x18007ed07`
- `GDI32!CreateCompatibleDC` at `0x18007ec5a`
- `GDI32!CreateCompatibleDC` at `0x18007ec71`
- `GDI32!CreateCompatibleDC` at `0x18007ec5a`
- `GDI32!CreateCompatibleDC` at `0x18007ec71`
- `GDI32!DeleteObject` at `0x18007ed38`
- `GDI32!DeleteObject` at `0x18007ed41`
- `GDI32!DeleteObject` at `0x18007ed4a`
- `GDI32!DeleteObject` at `0x18007ed53`
- `GDI32!DeleteObject` at `0x18007ed99`
- `GDI32!DeleteObject` at `0x18007ed38`
- `GDI32!DeleteObject` at `0x18007ed41`
- `GDI32!DeleteObject` at `0x18007ed4a`
- `GDI32!DeleteObject` at `0x18007ed53`
- `GDI32!DeleteObject` at `0x18007ed99`

## pseudocode

```c
__int64 __fastcall ExtractIconFromBMP(PCWSTR SourceString, int a2, int a3, int a4, HICON *a5, unsigned int a6)
{
  const WCHAR *v7; // rax
  int v9; // edi
  HBITMAP ImageInternal; // rax
  HBITMAP v11; // r13
  HBITMAP Bitmap; // rbp
  HDC hdcSrc; // rsi
  HDC CompatibleDC; // rdi
  COLORREF Pixel; // eax
  HICON v16; // rbx
  ICONINFO piconinfo; // [rsp+50h] [rbp-58h] BYREF
  int v20; // [rsp+B8h] [rbp+10h]
  int v21; // [rsp+C0h] [rbp+18h]

  HIWORD(v21) = HIWORD(a3);
  *(&piconinfo.yHotspot + 1) = 0;
  v7 = SourceString;
  if ( a2 < 1 )
  {
    while ( 1 )
    {
      v9 = (unsigned __int16)a3;
      v20 = (unsigned __int16)a3;
      ImageInternal = (HBITMAP)LoadImageInternal(
                                 0,
                                 v7,
                                 0,
                                 (unsigned __int16)a3,
                                 (unsigned __int16)a4,
                                 a6 & 0xFFFDFFEF | 0x10);
      v11 = ImageInternal;
      if ( !ImageInternal )
        break;
      if ( !a5 )
      {
        DeleteObject(ImageInternal);
        return 1;
      }
      Bitmap = CreateBitmap(v9, (unsigned __int16)a4, 1u, 1u, 0);
      hdcSrc = CreateCompatibleDC(0);
      SelectObject(hdcSrc, v11);
      CompatibleDC = CreateCompatibleDC(0);
      SelectObject(CompatibleDC, Bitmap);
      Pixel = GetPixel(hdcSrc, 0, 0);
      SetBkColor(hdcSrc, Pixel);
      BitBlt(CompatibleDC, 0, 0, v20, (unsigned __int16)a4, hdcSrc, 0, 0, 0xCC0020u);
      BitBlt(hdcSrc, 0, 0, v20, (unsigned __int16)a4, CompatibleDC, 0, 0, 0x220326u);
      *(_QWORD *)&piconinfo.fIcon = 1;
      piconinfo.yHotspot = 0;
      piconinfo.hbmColor = v11;
      piconinfo.hbmMask = Bitmap;
      v16 = CreateIconIndirect(&piconinfo);
      DeleteObject(hdcSrc);
      DeleteObject(v11);
      DeleteObject(CompatibleDC);
      DeleteObject(Bitmap);
      *a5 = v16;
      if ( !HIWORD(v21) )
        return 1;
      LOWORD(a3) = HIWORD(v21);
      LOWORD(a4) = HIWORD(a4);
      ++a5;
      v7 = SourceString;
      v21 = HIWORD(v21);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007ebb4  mov     [rsp+arg_18], rbx
0x18007ebb9  mov     [rsp+arg_10], r8d
0x18007ebbe  mov     [rsp+arg_0], rcx
0x18007ebc3  push    rbp
0x18007ebc4  push    rsi
0x18007ebc5  push    rdi
0x18007ebc6  push    r12
0x18007ebc8  push    r13
0x18007ebca  push    r14
0x18007ebcc  push    r15
0x18007ebce  sub     rsp, 70h
0x18007ebd2  xor     esi, esi
0x18007ebd4  mov     r12d, r9d
0x18007ebd7  mov     dword ptr [rsp+0A8h+piconinfo+0Ch], esi
0x18007ebdb  mov     rax, rcx
0x18007ebde  cmp     edx, 1
0x18007ebe1  jge     loc_18007EDA6
0x18007ebe7  mov     r14d, [rsp+0A8h+arg_28]
0x18007ebef  mov     r15, [rsp+0A8h+arg_20]
0x18007ebf7  btr     r14d, 11h
0x18007ebfc  or      r14d, 10h
0x18007ec00  movzx   edi, r8w
0x18007ec04  mov     rdx, rax; SourceString
0x18007ec07  movzx   ebx, r12w
0x18007ec0b  mov     r9d, edi; int
0x18007ec0e  mov     dword ptr [rsp+0A8h+hdcSrc], r14d; unsigned int
0x18007ec13  xor     r8d, r8d; unsigned int
0x18007ec16  xor     ecx, ecx; hModule
0x18007ec18  mov     [rsp+0A8h+arg_8], edi
0x18007ec1f  mov     dword ptr [rsp+0A8h+lpBits], ebx; int
0x18007ec23  call    ?LoadImageInternal@@YAPEAXPEAUHINSTANCE__@@PEBGIHHI@Z; LoadImageInternal(HINSTANCE__ *,ushort const *,uint,int,int,uint)
0x18007ec28  mov     r13, rax
0x18007ec2b  test    rax, rax
0x18007ec2e  jz      loc_18007EDA6
0x18007ec34  test    r15, r15
0x18007ec37  jz      loc_18007ED96
0x18007ec3d  mov     r9d, 1; nBitCount
0x18007ec43  mov     [rsp+0A8h+lpBits], rsi; lpBits
0x18007ec48  mov     r8d, r9d; nPlanes
0x18007ec4b  mov     edx, ebx; nHeight
0x18007ec4d  mov     ecx, edi; nWidth
0x18007ec4f  call    cs:__imp_CreateBitmap
0x18007ec55  xor     ecx, ecx; hdc
0x18007ec57  mov     rbp, rax
0x18007ec5a  call    cs:__imp_CreateCompatibleDC
0x18007ec60  mov     rcx, rax; hdc
0x18007ec63  mov     rdx, r13; h
0x18007ec66  mov     rsi, rax
0x18007ec69  call    cs:__imp_SelectObject
0x18007ec6f  xor     ecx, ecx; hdc
0x18007ec71  call    cs:__imp_CreateCompatibleDC
0x18007ec77  mov     rcx, rax; hdc
0x18007ec7a  mov     rdx, rbp; h
0x18007ec7d  mov     rdi, rax
0x18007ec80  call    cs:__imp_SelectObject
0x18007ec86  xor     r8d, r8d; y
0x18007ec89  xor     edx, edx; x
0x18007ec8b  mov     rcx, rsi; hdc
0x18007ec8e  call    cs:__imp_GetPixel
0x18007ec94  mov     edx, eax; color
0x18007ec96  mov     rcx, rsi; hdc
0x18007ec99  call    cs:__imp_SetBkColor
0x18007ec9f  mov     r9d, [rsp+0A8h+arg_8]; cx
0x18007eca7  xor     r8d, r8d; y
0x18007ecaa  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x18007ecb2  xor     edx, edx; x
0x18007ecb4  mov     [rsp+0A8h+y1], 0; y1
0x18007ecbc  mov     rcx, rdi; hdc
0x18007ecbf  mov     [rsp+0A8h+x1], 0; x1
0x18007ecc7  mov     [rsp+0A8h+hdcSrc], rsi; hdcSrc
0x18007eccc  mov     dword ptr [rsp+0A8h+lpBits], ebx; cy
0x18007ecd0  call    cs:__imp_BitBlt
0x18007ecd6  mov     r9d, [rsp+0A8h+arg_8]; cx
0x18007ecde  xor     r8d, r8d; y
0x18007ece1  mov     [rsp+0A8h+rop], 220326h; rop
0x18007ece9  xor     edx, edx; x
0x18007eceb  mov     [rsp+0A8h+y1], 0; y1
0x18007ecf3  mov     rcx, rsi; hdc
0x18007ecf6  mov     [rsp+0A8h+x1], 0; x1
0x18007ecfe  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x18007ed03  mov     dword ptr [rsp+0A8h+lpBits], ebx; cy
0x18007ed07  call    cs:__imp_BitBlt
0x18007ed0d  lea     rcx, [rsp+0A8h+piconinfo]; piconinfo
0x18007ed12  mov     qword ptr [rsp+0A8h+piconinfo.fIcon], 1
0x18007ed1b  mov     [rsp+0A8h+piconinfo.yHotspot], 0
0x18007ed23  mov     [rsp+0A8h+piconinfo.hbmColor], r13
0x18007ed28  mov     [rsp+0A8h+piconinfo.hbmMask], rbp
0x18007ed2d  call    CreateIconIndirect
0x18007ed32  mov     rcx, rsi; ho
0x18007ed35  mov     rbx, rax
0x18007ed38  call    cs:__imp_DeleteObject
0x18007ed3e  mov     rcx, r13; ho
0x18007ed41  call    cs:__imp_DeleteObject
0x18007ed47  mov     rcx, rdi; ho
0x18007ed4a  call    cs:__imp_DeleteObject
0x18007ed50  mov     rcx, rbp; ho
0x18007ed53  call    cs:__imp_DeleteObject
0x18007ed59  mov     eax, [rsp+0A8h+arg_10]
0x18007ed60  xor     esi, esi
0x18007ed62  shr     rax, 10h
0x18007ed66  mov     [r15], rbx
0x18007ed69  test    ax, ax
0x18007ed6c  jz      short loc_18007ED9F
0x18007ed6e  movzx   r8d, ax
0x18007ed72  mov     eax, r12d
0x18007ed75  shr     rax, 10h
0x18007ed79  movzx   r12d, ax
0x18007ed7d  add     r15, 8
0x18007ed81  mov     rax, [rsp+0A8h+arg_0]
0x18007ed89  mov     [rsp+0A8h+arg_10], r8d
0x18007ed91  jmp     loc_18007EC00
0x18007ed96  mov     rcx, r13; ho
0x18007ed99  call    cs:__imp_DeleteObject
0x18007ed9f  mov     eax, 1
0x18007eda4  jmp     short loc_18007EDA8
0x18007eda6  xor     eax, eax
0x18007eda8  mov     rbx, [rsp+0A8h+arg_18]
0x18007edb0  add     rsp, 70h
0x18007edb4  pop     r15
0x18007edb6  pop     r14
0x18007edb8  pop     r13
0x18007edba  pop     r12
0x18007edbc  pop     rdi
0x18007edbd  pop     rsi
0x18007edbe  pop     rbp
0x18007edbf  retn
```
