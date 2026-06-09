# CreateHBITMAP(HDC__ *,ushort,tagSIZE const *,IWICPalette *,int,tagRGBQUAD,void * *,HBITMAP__ * *)

- ea: `0x180084680`
- end: `0x1800847fc`
- name: `?CreateHBITMAP@@YAJPEAUHDC__@@GPEBUtagSIZE@@PEAUIWICPalette@@HUtagRGBQUAD@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(HDC, WORD, const struct tagSIZE *, struct IWICPalette *, int, struct tagRGBQUAD, void **ppvBits, HBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800849b8`

## callees

- `0x18003a3c0`
- `0x18003b0ac`
- `0x180084680`
- `0x180086010`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x1800847b1`
- `GDI32!CreateDIBSection` at `0x1800847b1`
- `USER32!ReleaseDC` at `0x1800847bf`
- `USER32!ReleaseDC` at `0x1800847bf`
- `USER32!GetDC` at `0x180084784`
- `USER32!GetDC` at `0x180084784`

## pseudocode

```c
__int64 __fastcall CreateHBITMAP(
        HDC a1,
        WORD a2,
        const struct tagSIZE *a3,
        struct IWICPalette *a4,
        int a5,
        struct tagRGBQUAD a6,
        void **ppvBits,
        HBITMAP *a8)
{
  int v11; // ebx
  DWORD v12; // edx
  HDC DC; // rax
  HDC v14; // rdi
  _DWORD v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  BITMAPINFO pbmi; // [rsp+40h] [rbp-C0h] BYREF

  *a8 = 0;
  memset_0(&pbmi.bmiHeader.biSizeImage, 0, 0x414u);
  *(struct tagSIZE *)&pbmi.bmiHeader.biWidth = *a3;
  pbmi.bmiHeader.biPlanes = 1;
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biBitCount = a2;
  pbmi.bmiHeader.biCompression = 0;
  v16[0] = 0;
  if ( a4 && ((int (__fastcall *)(struct IWICPalette *, _DWORD *))a4->lpVtbl->GetColorCount)(a4, v16) >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(struct IWICPalette *, __int64, RGBQUAD *, _DWORD *))a4->lpVtbl->GetColors)(
            a4,
            256,
            pbmi.bmiColors,
            v16);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v12 = v16[0];
    if ( v16[0] > 0x100u )
      return (unsigned int)-2147024809;
    if ( a5 )
      pbmi.bmiColors[v16[0] - 1] = a6;
    pbmi.bmiHeader.biClrImportant = v12;
    pbmi.bmiHeader.biClrUsed = v12;
  }
  v11 = -2147024882;
  DC = GetDC(0);
  v14 = DC;
  if ( DC )
  {
    *a8 = CreateDIBSection(DC, &pbmi, 0, ppvBits, 0, 0);
    ReleaseDC(0, v14);
    if ( *a8 )
      return 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180084680  mov     [rsp-8+arg_0], rbx
0x180084685  push    rbp
0x180084686  push    rsi
0x180084687  push    rdi
0x180084688  push    r14
0x18008468a  push    r15
0x18008468c  lea     rbp, [rsp-380h]
0x180084694  sub     rsp, 480h
0x18008469b  mov     rax, cs:__security_cookie
0x1800846a2  xor     rax, rsp
0x1800846a5  mov     [rbp+3A0h+var_30], rax
0x1800846ac  mov     r14, [rbp+3A0h+arg_38]
0x1800846b3  lea     rcx, [rsp+4A0h+pbmi.bmiHeader.biSizeImage]; void *
0x1800846b8  mov     r15, [rbp+3A0h+ppvBits]
0x1800846bf  mov     rbx, r8
0x1800846c2  movzx   edi, dx
0x1800846c5  mov     r8d, 414h; Size
0x1800846cb  xor     edx, edx; Val
0x1800846cd  mov     rsi, r9
0x1800846d0  mov     qword ptr [r14], 0
0x1800846d7  call    memset_0
0x1800846dc  mov     eax, [rbx]
0x1800846de  mov     [rsp+4A0h+pbmi.bmiHeader.biWidth], eax
0x1800846e2  mov     eax, [rbx+4]
0x1800846e5  mov     [rsp+4A0h+pbmi.bmiHeader.biHeight], eax
0x1800846e9  mov     eax, 1
0x1800846ee  mov     [rsp+4A0h+pbmi.bmiHeader.biPlanes], ax
0x1800846f3  mov     [rsp+4A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800846fb  mov     [rsp+4A0h+pbmi.bmiHeader.biBitCount], di
0x180084700  mov     [rsp+4A0h+pbmi.bmiHeader.biCompression], 0
0x180084708  mov     [rsp+4A0h+var_470], 0
0x180084710  test    rsi, rsi
0x180084713  jz      short loc_18008477D
0x180084715  mov     rax, [rsi]
0x180084718  lea     rdx, [rsp+4A0h+var_470]
0x18008471d  mov     rcx, rsi
0x180084720  mov     rax, [rax+40h]
0x180084724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084729  test    eax, eax
0x18008472b  js      short loc_18008477D
0x18008472d  mov     rax, [rsi]
0x180084730  lea     r9, [rsp+4A0h+var_470]
0x180084735  mov     edi, 100h
0x18008473a  lea     r8, [rsp+4A0h+pbmi.bmiColors]
0x18008473f  mov     edx, edi
0x180084741  mov     rcx, rsi
0x180084744  mov     rax, [rax+48h]
0x180084748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008474d  mov     ebx, eax
0x18008474f  test    eax, eax
0x180084751  js      short loc_1800847CD
0x180084753  mov     edx, [rsp+4A0h+var_470]
0x180084757  cmp     edx, edi
0x180084759  ja      loc_1800847F5
0x18008475f  cmp     [rbp+3A0h+arg_20], 0
0x180084766  jz      short loc_180084775
0x180084768  mov     eax, dword ptr [rbp+3A0h+arg_28.rgbBlue]
0x18008476e  lea     ecx, [rdx-1]
0x180084771  mov     dword ptr [rsp+rcx*4+4A0h+pbmi.bmiColors.rgbBlue], eax
0x180084775  mov     [rsp+4A0h+pbmi.bmiHeader.biClrImportant], edx
0x180084779  mov     [rsp+4A0h+pbmi.bmiHeader.biClrUsed], edx
0x18008477d  xor     ecx, ecx; hWnd
0x18008477f  mov     ebx, 8007000Eh
0x180084784  call    cs:__imp_GetDC
0x18008478a  mov     rdi, rax
0x18008478d  test    rax, rax
0x180084790  jz      short loc_1800847CD
0x180084792  mov     [rsp+4A0h+offset], 0; offset
0x18008479a  lea     rdx, [rsp+4A0h+pbmi]; pbmi
0x18008479f  mov     r9, r15; ppvBits
0x1800847a2  mov     [rsp+4A0h+hSection], 0; hSection
0x1800847ab  xor     r8d, r8d; usage
0x1800847ae  mov     rcx, rax; hdc
0x1800847b1  call    cs:__imp_CreateDIBSection
0x1800847b7  mov     rdx, rdi; hDC
0x1800847ba  xor     ecx, ecx; hWnd
0x1800847bc  mov     [r14], rax
0x1800847bf  call    cs:__imp_ReleaseDC
0x1800847c5  xor     eax, eax
0x1800847c7  cmp     [r14], rax
0x1800847ca  cmovnz  ebx, eax
0x1800847cd  mov     eax, ebx
0x1800847cf  mov     rcx, [rbp+3A0h+var_30]
0x1800847d6  xor     rcx, rsp; StackCookie
0x1800847d9  call    __security_check_cookie
0x1800847de  mov     rbx, [rsp+4A0h+arg_0]
0x1800847e6  add     rsp, 480h
0x1800847ed  pop     r15
0x1800847ef  pop     r14
0x1800847f1  pop     rdi
0x1800847f2  pop     rsi
0x1800847f3  pop     rbp
0x1800847f4  retn
0x1800847f5  mov     ebx, 80070057h
0x1800847fa  jmp     short loc_1800847CD
```
