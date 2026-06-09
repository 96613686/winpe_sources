# GetBitmapFromSBEProperty

- ea: `0x18002ab64`
- end: `0x18002ae8d`
- name: `GetBitmapFromSBEProperty`
- size: `809`
- prototype: `__int64 __fastcall(int nNumber, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002a9e0`

## callees

- `0x180001c00`
- `0x18002a53c`
- `0x18002a5c0`
- `0x18002aa88`
- `0x18002ab64`
- `0x18002b2c4`
- `0x18002b3cc`
- `0x1800b33f9`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18002accf`
- `KERNEL32!MulDiv` at `0x18002ad24`
- `KERNEL32!MulDiv` at `0x18002ad41`
- `KERNEL32!MulDiv` at `0x18002accf`
- `KERNEL32!MulDiv` at `0x18002ad24`
- `KERNEL32!MulDiv` at `0x18002ad41`
- `KERNEL32!GlobalUnlock` at `0x18002ac57`
- `KERNEL32!GlobalUnlock` at `0x18002ac57`
- `KERNEL32!GlobalLock` at `0x18002ac39`
- `KERNEL32!GlobalLock` at `0x18002ac39`
- `KERNEL32!GlobalFree` at `0x18002ae0e`
- `KERNEL32!GlobalFree` at `0x18002ae0e`
- `KERNEL32!GlobalAlloc` at `0x18002ac1e`
- `KERNEL32!GlobalAlloc` at `0x18002ac1e`
- `ole32!CreateStreamOnHGlobal` at `0x18002ac66`
- `ole32!CreateStreamOnHGlobal` at `0x18002ac66`
- `gdiplus!GdipFree` at `0x18002ae25`
- `gdiplus!GdipFree` at `0x18002ae25`
- `gdiplus!GdipDrawImageRectI` at `0x18002adb3`
- `gdiplus!GdipDrawImageRectI` at `0x18002adb3`
- `gdiplus!GdipAlloc` at `0x18002ad5b`
- `gdiplus!GdipAlloc` at `0x18002ad7b`
- `gdiplus!GdipAlloc` at `0x18002ad5b`
- `gdiplus!GdipAlloc` at `0x18002ad7b`
- `gdiplus!GdiplusShutdown` at `0x18002ae65`
- `gdiplus!GdiplusShutdown` at `0x18002ae65`
- `gdiplus!GdiplusStartup` at `0x18002ac02`
- `gdiplus!GdiplusStartup` at `0x18002ac02`
- `gdiplus!GdipDeleteGraphics` at `0x18002ae1c`
- `gdiplus!GdipDeleteGraphics` at `0x18002ae1c`

## pseudocode

```c
__int64 __fastcall GetBitmapFromSBEProperty(int nNumber, int a2, __int64 a3, __int64 a4)
{
  bool v5; // zf
  struct Gdiplus::Bitmap *v7; // r12
  struct Image *v8; // r15
  _QWORD *v9; // r14
  void *v10; // r13
  __int64 v11; // rbx
  HRESULT v12; // ebx
  HGLOBAL v13; // rax
  void *v14; // rax
  int v15; // edx
  struct Gdiplus::Bitmap *v16; // rax
  int v17; // edx
  int v18; // eax
  Gdiplus::Bitmap *v19; // rax
  int v20; // r9d
  Gdiplus::Graphics *v21; // rax
  _QWORD *v22; // rax
  int v23; // eax
  struct Image *v24; // rcx
  __int64 v26; // [rsp+30h] [rbp-39h] BYREF
  int v27; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  int v31; // [rsp+58h] [rbp-11h] BYREF
  __int64 v32; // [rsp+60h] [rbp-9h]
  __int64 v33; // [rsp+68h] [rbp-1h]

  v28 = a4;
  v31 = 1;
  v5 = *(_WORD *)a3 == 65;
  v32 = 0;
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  v26 = 0;
  v10 = 0;
  ppstm = 0;
  v27 = -16777216;
  if ( !v5 || *(_DWORD *)(a3 + 8) < 0x1Du )
    goto LABEL_38;
  v11 = *(_QWORD *)(a3 + 16);
  if ( *(unsigned int *)(a3 + 8) < (unsigned __int64)*(unsigned int *)(v11 + 17) + 29 )
    return (unsigned int)-2147024809;
  if ( (unsigned int)GdiplusStartup(&v30, &v31, 0) )
    goto LABEL_6;
  v13 = GlobalAlloc(0x22u, *(unsigned int *)(v11 + 17));
  v10 = v13;
  if ( !v13 )
  {
    v12 = -2147024882;
    goto LABEL_39;
  }
  v14 = GlobalLock(v13);
  if ( !v14 )
    goto LABEL_6;
  memcpy_0(v14, *(const void **)(v11 + 21), *(unsigned int *)(v11 + 17));
  GlobalUnlock(v10);
  v12 = CreateStreamOnHGlobal(v10, 0, &ppstm);
  if ( v12 < 0 )
    goto LABEL_39;
  v16 = Gdiplus::Bitmap::FromStream(ppstm, v15);
  v7 = v16;
  if ( !v16 )
  {
LABEL_38:
    v12 = -2147024809;
    goto LABEL_39;
  }
  Gdiplus::Image::GetPhysicalDimension(v16, &v26);
  if ( !nNumber
    || !a2
    || (v17 = (int)*(float *)&v26, v18 = (int)*((float *)&v26 + 1), (int)*(float *)&v26 <= nNumber) && v18 <= a2 )
  {
    v24 = v7;
    goto LABEL_36;
  }
  if ( nNumber == 0x7FFFFFFF && v18 > a2 )
  {
    nNumber = MulDiv(a2, v17, v18);
    if ( nNumber < 1 )
      nNumber = 1;
  }
  else if ( a2 == 0x7FFFFFFF && v17 > nNumber || (double)v17 / (double)v18 > (double)nNumber / (double)a2 )
  {
    a2 = MulDiv(nNumber, v18, v17);
    if ( a2 < 1 )
      a2 = 1;
  }
  else
  {
    nNumber = MulDiv(a2, v17, v18);
    if ( nNumber < 1 )
      nNumber = 1;
  }
  v19 = (Gdiplus::Bitmap *)GdipAlloc(24);
  if ( v19 )
    v8 = (struct Image *)Gdiplus::Bitmap::Bitmap(v19, nNumber, a2, v20);
  v21 = (Gdiplus::Graphics *)GdipAlloc(16);
  if ( !v21 )
  {
    v9 = 0;
    goto LABEL_6;
  }
  v22 = (_QWORD *)Gdiplus::Graphics::Graphics(v21, v8);
  v9 = v22;
  if ( v22 )
  {
    v23 = GdipDrawImageRectI(*v22, *((_QWORD *)v7 + 1), 0, 0, nNumber, a2);
    if ( v23 )
    {
      *((_DWORD *)v9 + 2) = v23;
      goto LABEL_6;
    }
    v24 = v8;
LABEL_36:
    if ( !(unsigned int)Gdiplus::Bitmap::GetHBITMAP(v24, &v27, v28) )
      goto LABEL_39;
  }
LABEL_6:
  v12 = -2147467259;
LABEL_39:
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  if ( v10 )
    GlobalFree(v10);
  if ( v9 )
  {
    GdipDeleteGraphics(*v9);
    GdipFree(v9);
  }
  if ( v8 )
    (**(void (__fastcall ***)(struct Image *, __int64))v8)(v8, 1);
  if ( v7 )
    (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))v7)(v7, 1);
  if ( v30 )
    GdiplusShutdown();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002ab64  push    rbp
0x18002ab66  push    rbx
0x18002ab67  push    rsi
0x18002ab68  push    rdi
0x18002ab69  push    r12
0x18002ab6b  push    r13
0x18002ab6d  push    r14
0x18002ab6f  push    r15
0x18002ab71  lea     rbp, [rsp-1Fh]
0x18002ab76  sub     rsp, 88h
0x18002ab7d  mov     rax, cs:__security_cookie
0x18002ab84  xor     rax, rsp
0x18002ab87  mov     [rbp+57h+var_50], rax
0x18002ab8b  mov     esi, ecx
0x18002ab8d  mov     [rbp+57h+var_80], r9
0x18002ab91  xor     ecx, ecx
0x18002ab93  mov     [rbp+57h+var_68], 1
0x18002ab9a  cmp     word ptr [r8], 41h ; 'A'
0x18002ab9f  mov     edi, edx
0x18002aba1  mov     [rbp+57h+var_60], rcx
0x18002aba5  mov     r12d, ecx
0x18002aba8  mov     [rbp+57h+var_58], rcx
0x18002abac  mov     r15d, ecx
0x18002abaf  mov     [rbp+57h+var_70], rcx
0x18002abb3  mov     r14d, ecx
0x18002abb6  mov     [rbp+57h+var_90], rcx
0x18002abba  mov     r13d, ecx
0x18002abbd  mov     [rbp+57h+ppstm], rcx
0x18002abc1  mov     [rbp+57h+var_88], 0FF000000h
0x18002abc8  jnz     loc_18002ADEC
0x18002abce  cmp     dword ptr [r8+8], 1Dh
0x18002abd3  jb      loc_18002ADEC
0x18002abd9  mov     rbx, [r8+10h]
0x18002abdd  mov     eax, [r8+8]
0x18002abe1  mov     ecx, [rbx+11h]
0x18002abe4  add     rcx, 1Dh
0x18002abe8  cmp     rax, rcx
0x18002abeb  jnb     short loc_18002ABF7
0x18002abed  mov     ebx, 80070057h
0x18002abf2  jmp     loc_18002AE6B
0x18002abf7  xor     r8d, r8d
0x18002abfa  lea     rdx, [rbp+57h+var_68]
0x18002abfe  lea     rcx, [rbp+57h+var_70]
0x18002ac02  call    cs:__imp_GdiplusStartup
0x18002ac08  test    eax, eax
0x18002ac0a  jz      short loc_18002AC16
0x18002ac0c  mov     ebx, 80004005h
0x18002ac11  jmp     loc_18002ADF1
0x18002ac16  mov     edx, [rbx+11h]; dwBytes
0x18002ac19  mov     ecx, 22h ; '"'; uFlags
0x18002ac1e  call    cs:__imp_GlobalAlloc
0x18002ac24  mov     r13, rax
0x18002ac27  test    rax, rax
0x18002ac2a  jnz     short loc_18002AC36
0x18002ac2c  mov     ebx, 8007000Eh
0x18002ac31  jmp     loc_18002ADF1
0x18002ac36  mov     rcx, r13; hMem
0x18002ac39  call    cs:__imp_GlobalLock
0x18002ac3f  test    rax, rax
0x18002ac42  jz      short loc_18002AC0C
0x18002ac44  mov     r8d, [rbx+11h]; Size
0x18002ac48  mov     rcx, rax; void *
0x18002ac4b  mov     rdx, [rbx+15h]; Src
0x18002ac4f  call    memcpy_0
0x18002ac54  mov     rcx, r13; hMem
0x18002ac57  call    cs:__imp_GlobalUnlock
0x18002ac5d  lea     r8, [rbp+57h+ppstm]; ppstm
0x18002ac61  xor     edx, edx; fDeleteOnRelease
0x18002ac63  mov     rcx, r13; hGlobal
0x18002ac66  call    cs:__imp_CreateStreamOnHGlobal
0x18002ac6c  mov     ebx, eax
0x18002ac6e  test    eax, eax
0x18002ac70  js      loc_18002ADF1
0x18002ac76  mov     rcx, [rbp+57h+ppstm]; struct IStream *
0x18002ac7a  call    ?FromStream@Bitmap@Gdiplus@@SAPEAV12@PEAUIStream@@H@Z; Gdiplus::Bitmap::FromStream(IStream *,int)
0x18002ac7f  mov     r12, rax
0x18002ac82  test    rax, rax
0x18002ac85  jz      loc_18002ADEC
0x18002ac8b  lea     rdx, [rbp+57h+var_90]
0x18002ac8f  mov     rcx, rax
0x18002ac92  call    ?GetPhysicalDimension@Image@Gdiplus@@QEAA?AW4Status@2@PEAVSizeF@2@@Z; Gdiplus::Image::GetPhysicalDimension(Gdiplus::SizeF *)
0x18002ac97  test    esi, esi
0x18002ac99  jz      loc_18002ADD3
0x18002ac9f  test    edi, edi
0x18002aca1  jz      loc_18002ADD3
0x18002aca7  cvttss2si edx, dword ptr [rbp+57h+var_90]; nNumerator
0x18002acac  cvttss2si eax, dword ptr [rbp+57h+var_90+4]
0x18002acb1  cmp     edx, esi
0x18002acb3  jg      short loc_18002ACBD
0x18002acb5  cmp     eax, edi
0x18002acb7  jle     loc_18002ADD3
0x18002acbd  mov     ecx, 7FFFFFFFh
0x18002acc2  cmp     esi, ecx
0x18002acc4  jnz     short loc_18002ACE7
0x18002acc6  cmp     eax, edi
0x18002acc8  jle     short loc_18002ACE7
0x18002acca  mov     r8d, eax; nDenominator
0x18002accd  mov     ecx, edi; nNumber
0x18002accf  call    cs:__imp_MulDiv
0x18002acd5  mov     r14d, 1
0x18002acdb  mov     esi, eax
0x18002acdd  cmp     eax, r14d
0x18002ace0  jge     short loc_18002AD56
0x18002ace2  mov     esi, r14d
0x18002ace5  jmp     short loc_18002AD56
0x18002ace7  cmp     edi, ecx
0x18002ace9  jnz     short loc_18002ACEF
0x18002aceb  cmp     edx, esi
0x18002aced  jg      short loc_18002AD1D
0x18002acef  movd    xmm3, edx
0x18002acf3  movd    xmm0, eax
0x18002acf7  movd    xmm2, esi
0x18002acfb  movd    xmm1, edi
0x18002acff  cvtdq2pd xmm3, xmm3
0x18002ad03  cvtdq2pd xmm0, xmm0
0x18002ad07  cvtdq2pd xmm2, xmm2
0x18002ad0b  cvtdq2pd xmm1, xmm1
0x18002ad0f  divsd   xmm3, xmm0
0x18002ad13  divsd   xmm2, xmm1
0x18002ad17  comisd  xmm3, xmm2
0x18002ad1b  jbe     short loc_18002AD3C
0x18002ad1d  mov     r8d, edx; nDenominator
0x18002ad20  mov     ecx, esi; nNumber
0x18002ad22  mov     edx, eax; nNumerator
0x18002ad24  call    cs:__imp_MulDiv
0x18002ad2a  mov     r14d, 1
0x18002ad30  mov     edi, eax
0x18002ad32  cmp     eax, r14d
0x18002ad35  jge     short loc_18002AD56
0x18002ad37  mov     edi, r14d
0x18002ad3a  jmp     short loc_18002AD56
0x18002ad3c  mov     r8d, eax; nDenominator
0x18002ad3f  mov     ecx, edi; nNumber
0x18002ad41  call    cs:__imp_MulDiv
0x18002ad47  mov     r14d, 1
0x18002ad4d  mov     esi, eax
0x18002ad4f  cmp     eax, r14d
0x18002ad52  cmovl   esi, r14d
0x18002ad56  mov     ecx, 18h
0x18002ad5b  call    cs:__imp_GdipAlloc
0x18002ad61  test    rax, rax
0x18002ad64  jz      short loc_18002AD76
0x18002ad66  mov     r8d, edi; int
0x18002ad69  mov     edx, esi; int
0x18002ad6b  mov     rcx, rax; this
0x18002ad6e  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x18002ad73  mov     r15, rax
0x18002ad76  mov     ecx, 10h
0x18002ad7b  call    cs:__imp_GdipAlloc
0x18002ad81  test    rax, rax
0x18002ad84  jz      short loc_18002ADCB
0x18002ad86  mov     rdx, r15; struct Image *
0x18002ad89  mov     rcx, rax; this
0x18002ad8c  call    ??0Graphics@Gdiplus@@QEAA@PEAVImage@1@@Z; Gdiplus::Graphics::Graphics(Gdiplus::Image *)
0x18002ad91  mov     r14, rax
0x18002ad94  test    rax, rax
0x18002ad97  jz      loc_18002AC0C
0x18002ad9d  mov     rdx, [r12+8]
0x18002ada2  xor     r9d, r9d
0x18002ada5  mov     rcx, [rax]
0x18002ada8  xor     r8d, r8d
0x18002adab  mov     [rsp+0C0h+var_98], edi
0x18002adaf  mov     [rsp+0C0h+var_A0], esi
0x18002adb3  call    cs:__imp_GdipDrawImageRectI
0x18002adb9  test    eax, eax
0x18002adbb  jz      short loc_18002ADC6
0x18002adbd  mov     [r14+8], eax
0x18002adc1  jmp     loc_18002AC0C
0x18002adc6  mov     rcx, r15
0x18002adc9  jmp     short loc_18002ADD6
0x18002adcb  xor     r14d, r14d
0x18002adce  jmp     loc_18002AC0C
0x18002add3  mov     rcx, r12
0x18002add6  mov     r8, [rbp+57h+var_80]
0x18002adda  lea     rdx, [rbp+57h+var_88]
0x18002adde  call    ?GetHBITMAP@Bitmap@Gdiplus@@QEAA?AW4Status@2@AEBVColor@2@PEAPEAUHBITMAP__@@@Z; Gdiplus::Bitmap::GetHBITMAP(Gdiplus::Color const &,HBITMAP__ * *)
0x18002ade3  test    eax, eax
0x18002ade5  jz      short loc_18002ADF1
0x18002ade7  jmp     loc_18002AC0C
0x18002adec  mov     ebx, 80070057h
0x18002adf1  mov     rcx, [rbp+57h+ppstm]
0x18002adf5  test    rcx, rcx
0x18002adf8  jz      short loc_18002AE06
0x18002adfa  mov     rax, [rcx]
0x18002adfd  mov     rax, [rax+10h]
0x18002ae01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae06  test    r13, r13
0x18002ae09  jz      short loc_18002AE14
0x18002ae0b  mov     rcx, r13; hMem
0x18002ae0e  call    cs:__imp_GlobalFree
0x18002ae14  test    r14, r14
0x18002ae17  jz      short loc_18002AE2B
0x18002ae19  mov     rcx, [r14]
0x18002ae1c  call    cs:__imp_GdipDeleteGraphics
0x18002ae22  mov     rcx, r14
0x18002ae25  call    cs:__imp_GdipFree
0x18002ae2b  test    r15, r15
0x18002ae2e  jz      short loc_18002AE43
0x18002ae30  mov     rax, [r15]
0x18002ae33  mov     edx, 1
0x18002ae38  mov     rcx, r15
0x18002ae3b  mov     rax, [rax]
0x18002ae3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae43  test    r12, r12
0x18002ae46  jz      short loc_18002AE5C
0x18002ae48  mov     rax, [r12]
0x18002ae4c  mov     edx, 1
0x18002ae51  mov     rcx, r12
0x18002ae54  mov     rax, [rax]
0x18002ae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae5c  mov     rcx, [rbp+57h+var_70]
0x18002ae60  test    rcx, rcx
0x18002ae63  jz      short loc_18002AE6B
0x18002ae65  call    cs:__imp_GdiplusShutdown
0x18002ae6b  mov     eax, ebx
0x18002ae6d  mov     rcx, [rbp+57h+var_50]
0x18002ae71  xor     rcx, rsp; StackCookie
0x18002ae74  call    __security_check_cookie
0x18002ae79  add     rsp, 88h
0x18002ae80  pop     r15
0x18002ae82  pop     r14
0x18002ae84  pop     r13
0x18002ae86  pop     r12
0x18002ae88  pop     rdi
0x18002ae89  pop     rsi
0x18002ae8a  pop     rbx
0x18002ae8b  pop     rbp
0x18002ae8c  retn
```
