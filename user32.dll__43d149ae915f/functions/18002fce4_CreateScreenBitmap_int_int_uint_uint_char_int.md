# CreateScreenBitmap(int,int,uint,uint,char *,int *)

- ea: `0x18002fce4`
- end: `0x18002ff0b`
- name: `?CreateScreenBitmap@@YAPEAUHBITMAP__@@HHIIPEADPEAH@Z`
- size: `551`
- prototype: `HBITMAP __usercall@<rax>(int cx@<ecx>, int cy@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, char *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002f198`

## callees

- `0x18002fce4`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserReleaseDC` at `0x18002fdd2`
- `win32u!NtUserReleaseDC` at `0x18002fdd2`
- `win32u!NtUserGetDC` at `0x18002fd2b`
- `win32u!NtUserGetDC` at `0x18002fd2b`
- `GDI32!GdiReleaseDC` at `0x18002fdc9`
- `GDI32!GdiReleaseDC` at `0x18002fdc9`
- `GDI32!CreateCompatibleBitmap` at `0x18002fe4a`
- `GDI32!CreateCompatibleBitmap` at `0x18002fe4a`
- `GDI32!CreateDIBitmap` at `0x18002fd9f`
- `GDI32!CreateDIBitmap` at `0x18002fee1`
- `GDI32!CreateDIBitmap` at `0x18002fd9f`
- `GDI32!CreateDIBitmap` at `0x18002fee1`
- `GDI32!CreateDCW` at `0x18002fe0f`
- `GDI32!CreateDCW` at `0x18002fe0f`
- `GDI32!DeleteDC` at `0x18002fe58`
- `GDI32!DeleteDC` at `0x18002fe58`

## pseudocode

```c
HBITMAP __fastcall CreateScreenBitmap(unsigned int cx, unsigned int cy, int a3, int a4, char *a5, int *a6)
{
  HBITMAP v6; // rsi
  HDC DC; // rax
  HDC v12; // rbx
  HBITMAP DIBitmap; // rax
  int v15; // edi
  BITMAPINFO pbmi; // [rsp+30h] [rbp-A9h] BYREF
  int v17; // [rsp+5Ch] [rbp-7Dh]
  _OWORD v18[6]; // [rsp+60h] [rbp-79h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-19h]

  v6 = 0;
  if ( gfSystemInitialized )
    DC = (HDC)NtUserGetDC(0);
  else
    DC = CreateDCW(L"DISPLAY", &pszFormat, 0, 0);
  v12 = DC;
  if ( DC )
  {
    if ( a4 == 1 && a3 == 1 )
    {
      v17 = 0xFFFFFF;
      pbmi.bmiHeader.biSize = 40;
      *(_OWORD *)&pbmi.bmiHeader.biPlanes = xmmword_1800A818C;
      pbmi.bmiHeader.biWidth = cx;
      *(_OWORD *)&pbmi.bmiHeader.biYPelsPerMeter = xmmword_1800A819C;
      pbmi.bmiHeader.biHeight = cy;
      DIBitmap = CreateDIBitmap(DC, &pbmi.bmiHeader, 2u, 0, &pbmi, 0);
      *a6 = 1;
    }
    else if ( a3 && a3 != *(unsigned __int8 *)(gpsi + 7002) || a4 && a4 != *(unsigned __int8 *)(gpsi + 7003) )
    {
      v18[0] = xmmword_1800A8AB0;
      v18[2] = xmmword_1800A8AD0;
      v18[1] = xmmword_1800A8AC0;
      v15 = a3 * a4;
      v18[4] = xmmword_1800A8AF0;
      v18[3] = xmmword_1800A8AE0;
      v19 = 0xFFFFFF0000FFFFLL;
      v18[5] = xmmword_1800A8B00;
      if ( v15 )
        HIWORD(v18[0]) = v15;
      else
        HIWORD(v18[0]) = *(_WORD *)(gpsi + 6996);
      *(_QWORD *)((char *)v18 + 4) = __PAIR64__(cy, cx);
      DIBitmap = CreateDIBitmap(DC, (const BITMAPINFOHEADER *)v18, 2u, 0, (const BITMAPINFO *)v18, 0);
    }
    else
    {
      DIBitmap = CreateCompatibleBitmap(DC, cx, cy);
    }
    v6 = DIBitmap;
    if ( gfSystemInitialized )
    {
      if ( g_systemCallFilterId != 5 || v12 != (HDC)-589410304LL )
      {
        GdiReleaseDC(v12);
        NtUserReleaseDC(v12);
      }
    }
    else
    {
      DeleteDC(v12);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002fce4  push    rbp
0x18002fce6  push    rbx
0x18002fce7  push    rsi
0x18002fce8  push    rdi
0x18002fce9  push    r12
0x18002fceb  push    r13
0x18002fced  push    r14
0x18002fcef  push    r15
0x18002fcf1  lea     rbp, [rsp-0Fh]
0x18002fcf6  sub     rsp, 0E8h
0x18002fcfd  mov     rax, cs:__security_cookie
0x18002fd04  xor     rax, rsp
0x18002fd07  mov     [rbp+47h+var_50], rax
0x18002fd0b  mov     r13, [rbp+47h+arg_28]
0x18002fd0f  xor     esi, esi
0x18002fd11  cmp     cs:?gfSystemInitialized@@3HA, esi; int gfSystemInitialized
0x18002fd17  mov     edi, r9d
0x18002fd1a  mov     r14d, r8d
0x18002fd1d  mov     r12d, edx
0x18002fd20  mov     r15d, ecx
0x18002fd23  jz      loc_18002FDFB
0x18002fd29  xor     ecx, ecx
0x18002fd2b  call    cs:__imp_NtUserGetDC
0x18002fd31  mov     rbx, rax
0x18002fd34  test    rax, rax
0x18002fd37  jz      loc_18002FDD8
0x18002fd3d  cmp     edi, 1
0x18002fd40  jnz     loc_18002FE1A
0x18002fd46  cmp     r14d, edi
0x18002fd49  jnz     loc_18002FE1A
0x18002fd4f  mov     eax, cs:dword_1800A81AC
0x18002fd55  lea     r8d, [rdi+1]; flInit
0x18002fd59  movups  xmm0, cs:xmmword_1800A818C
0x18002fd60  mov     [rbp+47h+var_C4], eax
0x18002fd63  lea     rax, [rsp+120h+var_F0]
0x18002fd68  movups  xmm1, cs:xmmword_1800A819C
0x18002fd6f  mov     [rsp+120h+iUsage], esi; iUsage
0x18002fd73  lea     rdx, [rsp+120h+var_F0]; pbmih
0x18002fd78  xor     r9d, r9d; pjBits
0x18002fd7b  mov     [rsp+120h+pbmi], rax; pbmi
0x18002fd80  mov     rcx, rbx; hdc
0x18002fd83  mov     [rsp+120h+var_F0.bmiHeader.biSize], 28h ; '('
0x18002fd8b  movups  xmmword ptr [rsp+120h+var_F0.bmiHeader.biPlanes], xmm0
0x18002fd90  mov     [rsp+120h+var_F0.bmiHeader.biWidth], r15d
0x18002fd95  movups  xmmword ptr [rsp+120h+var_F0.bmiHeader.biYPelsPerMeter], xmm1
0x18002fd9a  mov     [rsp+120h+var_F0.bmiHeader.biHeight], r12d
0x18002fd9f  call    cs:__imp_CreateDIBitmap
0x18002fda5  mov     [r13+0], edi
0x18002fda9  cmp     cs:?gfSystemInitialized@@3HA, 0; int gfSystemInitialized
0x18002fdb0  mov     rsi, rax
0x18002fdb3  jz      loc_18002FE55
0x18002fdb9  cmp     cs:?g_systemCallFilterId@@3KA, 5; ulong g_systemCallFilterId
0x18002fdc0  jz      loc_18002FEF9
0x18002fdc6  mov     rcx, rbx
0x18002fdc9  call    cs:__imp_GdiReleaseDC
0x18002fdcf  mov     rcx, rbx
0x18002fdd2  call    cs:__imp_NtUserReleaseDC
0x18002fdd8  mov     rax, rsi
0x18002fddb  mov     rcx, [rbp+47h+var_50]
0x18002fddf  xor     rcx, rsp; StackCookie
0x18002fde2  call    __security_check_cookie
0x18002fde7  add     rsp, 0E8h
0x18002fdee  pop     r15
0x18002fdf0  pop     r14
0x18002fdf2  pop     r13
0x18002fdf4  pop     r12
0x18002fdf6  pop     rdi
0x18002fdf7  pop     rsi
0x18002fdf8  pop     rbx
0x18002fdf9  pop     rbp
0x18002fdfa  retn
0x18002fdfb  xor     r9d, r9d; pdm
0x18002fdfe  lea     rdx, pszFormat; pwszDevice
0x18002fe05  xor     r8d, r8d; pszPort
0x18002fe08  lea     rcx, pwszDriver; "DISPLAY"
0x18002fe0f  call    cs:__imp_CreateDCW
0x18002fe15  jmp     loc_18002FD31
0x18002fe1a  mov     rcx, cs:gpsi
0x18002fe21  test    r14d, r14d
0x18002fe24  jz      short loc_18002FE32
0x18002fe26  movzx   eax, byte ptr [rcx+1B5Ah]
0x18002fe2d  cmp     r14d, eax
0x18002fe30  jnz     short loc_18002FE63
0x18002fe32  test    edi, edi
0x18002fe34  jz      short loc_18002FE41
0x18002fe36  movzx   eax, byte ptr [rcx+1B5Bh]
0x18002fe3d  cmp     edi, eax
0x18002fe3f  jnz     short loc_18002FE63
0x18002fe41  mov     r8d, r12d; cy
0x18002fe44  mov     edx, r15d; cx
0x18002fe47  mov     rcx, rbx; hdc
0x18002fe4a  call    cs:__imp_CreateCompatibleBitmap
0x18002fe50  jmp     loc_18002FDA9
0x18002fe55  mov     rcx, rbx; hdc
0x18002fe58  call    cs:__imp_DeleteDC
0x18002fe5e  jmp     loc_18002FDD8
0x18002fe63  movaps  xmm0, cs:xmmword_1800A8AB0
0x18002fe6a  movaps  xmm1, cs:xmmword_1800A8AC0
0x18002fe71  movaps  xmmword ptr [rbp+47h+var_C0.bmiHeader.biSize], xmm0
0x18002fe75  movaps  xmm0, cs:xmmword_1800A8AD0
0x18002fe7c  movaps  xmmword ptr [rbp+47h+var_C0.bmiHeader.biClrUsed], xmm0
0x18002fe80  movaps  xmm0, cs:xmmword_1800A8AF0
0x18002fe87  movaps  xmmword ptr [rbp+47h+var_C0.bmiHeader.biCompression], xmm1
0x18002fe8b  movaps  xmm1, cs:xmmword_1800A8AE0
0x18002fe92  imul    edi, r14d
0x18002fe96  movaps  [rbp+47h+var_80], xmm0
0x18002fe9a  movsd   xmm0, cs:qword_1800A8B10
0x18002fea2  movaps  [rbp+47h+var_90], xmm1
0x18002fea6  movaps  xmm1, cs:xmmword_1800A8B00
0x18002fead  movsd   [rbp+47h+var_60], xmm0
0x18002feb2  movaps  [rbp+47h+var_70], xmm1
0x18002feb6  test    edi, edi
0x18002feb8  jz      short loc_18002FEEC
0x18002feba  mov     [rbp+47h+var_C0.bmiHeader.biBitCount], di
0x18002febe  xor     r9d, r9d; pjBits
0x18002fec1  mov     [rsp+120h+iUsage], esi; iUsage
0x18002fec5  lea     rax, [rbp+47h+var_C0]
0x18002fec9  mov     [rbp+47h+var_C0.bmiHeader.biWidth], r15d
0x18002fecd  lea     rdx, [rbp+47h+var_C0]; pbmih
0x18002fed1  mov     [rbp+47h+var_C0.bmiHeader.biHeight], r12d
0x18002fed5  mov     rcx, rbx; hdc
0x18002fed8  mov     [rsp+120h+pbmi], rax; pbmi
0x18002fedd  lea     r8d, [r9+2]; flInit
0x18002fee1  call    cs:__imp_CreateDIBitmap
0x18002fee7  jmp     loc_18002FDA9
0x18002feec  movzx   eax, word ptr [rcx+1B54h]
0x18002fef3  mov     [rbp+47h+var_C0.bmiHeader.biBitCount], ax
0x18002fef7  jmp     short loc_18002FEBE
0x18002fef9  cmp     rbx, 0FFFFFFFFDCDE5000h
0x18002ff00  jz      loc_18002FDD8
0x18002ff06  jmp     loc_18002FDC6
```
