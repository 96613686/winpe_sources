# BitmapFromDIB(int,int,ushort,ushort,uint,int,int,char *,ulong,tagBITMAPINFO *,tagBITMAPINFO *,HPALETTE__ *)

- ea: `0x180005280`
- end: `0x180005949`
- name: `?BitmapFromDIB@@YAPEAUHBITMAP__@@HHGGIHHPEADKPEAUtagBITMAPINFO@@1PEAUHPALETTE__@@@Z`
- size: `1737`
- prototype: `HBITMAP __fastcall(int, int, unsigned __int16, unsigned __int16, unsigned int, int, UINT cLines, char *, unsigned int, BITMAPINFO *lpbmi, struct tagBITMAPINFO *, HPALETTE)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000426c`
- `0x180004cd0`

## callees

- `0x180003a08`
- `0x1800048b4`
- `0x180005280`
- `0x180005d48`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserReleaseDC` at `0x18000552e`
- `win32u!NtUserReleaseDC` at `0x18000552e`
- `win32u!NtUserGetDC` at `0x180005458`
- `win32u!NtUserGetDC` at `0x180005458`
- `ntdll!RtlLeaveCriticalSection` at `0x1800056e1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800056e1`
- `GDI32!SelectObject` at `0x180005559`
- `GDI32!SelectObject` at `0x1800056bf`
- `GDI32!SelectObject` at `0x180005559`
- `GDI32!SelectObject` at `0x1800056bf`
- `GDI32!SetBkColor` at `0x180005583`
- `GDI32!SetBkColor` at `0x180005696`
- `GDI32!SetBkColor` at `0x180005583`
- `GDI32!SetBkColor` at `0x180005696`
- `GDI32!SetTextColor` at `0x18000559c`
- `GDI32!SetTextColor` at `0x180005686`
- `GDI32!SetTextColor` at `0x18000559c`
- `GDI32!SetTextColor` at `0x180005686`
- `GDI32!GdiGetBitmapBitsSize` at `0x1800052e8`
- `GDI32!GdiGetBitmapBitsSize` at `0x1800052e8`
- `GDI32!GdiReleaseDC` at `0x180005525`
- `GDI32!GdiReleaseDC` at `0x180005525`
- `GDI32!SetDIBits` at `0x1800055df`
- `GDI32!SetDIBits` at `0x1800055df`
- `GDI32!SetStretchBltMode` at `0x1800056af`
- `GDI32!SetStretchBltMode` at `0x1800057e6`
- `GDI32!SetStretchBltMode` at `0x1800056af`
- `GDI32!SetStretchBltMode` at `0x1800057e6`
- `GDI32!CreateDIBSection` at `0x18000580b`
- `GDI32!CreateDIBSection` at `0x18000580b`
- `GDI32!CreateCompatibleBitmap` at `0x180005782`
- `GDI32!CreateCompatibleBitmap` at `0x180005782`
- `GDI32!CreateDIBitmap` at `0x1800053f7`
- `GDI32!CreateDIBitmap` at `0x1800054f8`
- `GDI32!CreateDIBitmap` at `0x180005918`
- `GDI32!CreateDIBitmap` at `0x1800053f7`
- `GDI32!CreateDIBitmap` at `0x1800054f8`
- `GDI32!CreateDIBitmap` at `0x180005918`
- `GDI32!CreateDCW` at `0x180005721`
- `GDI32!CreateDCW` at `0x180005721`
- `GDI32!DeleteDC` at `0x180005790`
- `GDI32!DeleteDC` at `0x180005790`
- `GDI32!DeleteObject` at `0x180005849`
- `GDI32!DeleteObject` at `0x180005849`

## pseudocode

```c
HBITMAP __fastcall BitmapFromDIB(
        LONG a1,
        LONG a2,
        __int16 a3,
        __int16 a4,
        __int16 a5,
        LONG a6,
        LONG cLines,
        char *a8,
        unsigned int a9,
        BITMAPINFO *lpbmi,
        struct tagBITMAPINFO *a11)
{
  HBITMAP v13; // rdi
  int v14; // r12d
  DWORD *p_biCompression; // r14
  LONG *p_biHeight; // r13
  DWORD v17; // ecx
  HBITMAP DIBitmap; // rax
  HDC DC; // rax
  HDC v20; // rcx
  HDC v21; // r14
  HBITMAP CompatibleBitmap; // rax
  int v23; // r14d
  HGDIOBJ v24; // r13
  COLORREF v25; // r12d
  int v26; // edx
  HDC v27; // rcx
  int v28; // r8d
  UINT v29; // r9d
  int v30; // eax
  BOOL v31; // esi
  int v33; // ecx
  int iUsage; // [rsp+28h] [rbp-1A0h]
  UINT ColorUse; // [rsp+30h] [rbp-198h]
  unsigned int v36; // [rsp+68h] [rbp-160h]
  unsigned int v37; // [rsp+70h] [rbp-158h]
  int v38; // [rsp+80h] [rbp-148h]
  COLORREF color; // [rsp+84h] [rbp-144h]
  COLORREF colora; // [rsp+84h] [rbp-144h]
  LONG biWidth_high; // [rsp+88h] [rbp-140h]
  DWORD v42; // [rsp+8Ch] [rbp-13Ch]
  LONG v43; // [rsp+90h] [rbp-138h]
  int v44; // [rsp+94h] [rbp-134h]
  __int16 biSize; // [rsp+98h] [rbp-130h]
  int v46; // [rsp+A0h] [rbp-128h]
  void *ppvBits; // [rsp+B8h] [rbp-110h] BYREF
  struct tagBITMAPINFO *v48; // [rsp+C0h] [rbp-108h]
  HGDIOBJ v49; // [rsp+C8h] [rbp-100h]
  BITMAPINFO pbmih; // [rsp+D8h] [rbp-F0h] BYREF
  int v51; // [rsp+104h] [rbp-C4h]
  _OWORD pbmi[6]; // [rsp+110h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+170h] [rbp-58h]

  HIWORD(v38) = a4;
  LOWORD(v38) = a3;
  v48 = a11;
  if ( (unsigned int)GdiGetBitmapBitsSize(lpbmi) > a9 || !(unsigned int)AcquireGlobalGdiResources() )
    return 0;
  v13 = 0;
  v46 = 0;
  if ( !a1 )
    a1 = a6;
  v43 = a1;
  if ( !a2 )
    a2 = cLines;
  if ( a1 == a6 && a2 == cLines )
  {
    v44 = 0;
    v14 = 1;
  }
  else
  {
    v14 = 1;
    v44 = 1;
  }
  if ( (a5 & 0x2800) != 0 )
  {
    ppvBits = 0;
    biSize = lpbmi->bmiHeader.biSize;
    p_biCompression = &lpbmi->bmiHeader.biCompression;
    if ( LOWORD(lpbmi->bmiHeader.biSize) == 12 )
    {
      v42 = 0;
      color = LOWORD(lpbmi->bmiHeader.biWidth);
      biWidth_high = HIWORD(lpbmi->bmiHeader.biWidth);
      LOWORD(lpbmi->bmiHeader.biWidth) = a1;
      HIWORD(lpbmi->bmiHeader.biWidth) = a2;
      p_biHeight = &lpbmi->bmiHeader.biHeight;
    }
    else
    {
      color = lpbmi->bmiHeader.biWidth;
      p_biHeight = &lpbmi->bmiHeader.biHeight;
      biWidth_high = lpbmi->bmiHeader.biHeight;
      v42 = *p_biCompression;
      v17 = *p_biCompression;
      lpbmi->bmiHeader.biWidth = v43;
      lpbmi->bmiHeader.biHeight = a2;
      if ( v17 != 3 )
        *p_biCompression = 0;
    }
    if ( (a5 & 0x800) != 0 )
      DIBitmap = CreateDIBitmap(ghdcBits2, &lpbmi->bmiHeader, 2u, 0, lpbmi, 0);
    else
      DIBitmap = CreateDIBSection(ghdcBits2, lpbmi, 0, &ppvBits, 0, 0);
    v13 = DIBitmap;
    if ( biSize == 12 )
    {
      LOWORD(lpbmi->bmiHeader.biWidth) = color;
      HIWORD(lpbmi->bmiHeader.biWidth) = biWidth_high;
    }
    else
    {
      lpbmi->bmiHeader.biWidth = color;
      *p_biHeight = biWidth_high;
      *p_biCompression = v42;
    }
    a1 = v43;
  }
  if ( v13 )
    goto LABEL_29;
  v13 = 0;
  if ( gfSystemInitialized )
    DC = (HDC)NtUserGetDC(0);
  else
    DC = CreateDCW(L"DISPLAY", &pszFormat, 0, 0);
  v21 = DC;
  if ( DC )
  {
    if ( v38 == 65537 )
    {
      pbmih.bmiHeader.biSize = 40;
      *(_OWORD *)&pbmih.bmiHeader.biPlanes = xmmword_1800A818C;
      *(_OWORD *)&pbmih.bmiHeader.biYPelsPerMeter = xmmword_1800A819C;
      v51 = 0xFFFFFF;
      pbmih.bmiHeader.biWidth = a1;
      pbmih.bmiHeader.biHeight = a2;
      CompatibleBitmap = CreateDIBitmap(DC, &pbmih.bmiHeader, 2u, 0, &pbmih, 0);
      v46 = 1;
    }
    else if ( (_WORD)v38 && (_WORD)v38 != *(unsigned __int8 *)(gpsi + 7002)
           || HIWORD(v38) && HIWORD(v38) != *(unsigned __int8 *)(gpsi + 7003) )
    {
      pbmi[0] = xmmword_1800A8AB0;
      pbmi[1] = xmmword_1800A8AC0;
      pbmi[2] = xmmword_1800A8AD0;
      pbmi[3] = xmmword_1800A8AE0;
      pbmi[4] = xmmword_1800A8AF0;
      pbmi[5] = xmmword_1800A8B00;
      v53 = 0xFFFFFF0000FFFFLL;
      v33 = (unsigned __int16)v38 * HIWORD(v38);
      if ( !v33 )
        LOWORD(v33) = *(_WORD *)(gpsi + 6996);
      HIWORD(pbmi[0]) = v33;
      *(_QWORD *)((char *)pbmi + 4) = __PAIR64__(a2, a1);
      CompatibleBitmap = CreateDIBitmap(DC, (const BITMAPINFOHEADER *)pbmi, 2u, 0, (const BITMAPINFO *)pbmi, 0);
    }
    else
    {
      CompatibleBitmap = CreateCompatibleBitmap(DC, a1, a2);
    }
    v13 = CompatibleBitmap;
    if ( gfSystemInitialized )
    {
      if ( g_systemCallFilterId != 5 || v21 != (HDC)-589410304LL )
      {
        GdiReleaseDC(v21);
        NtUserReleaseDC(v21);
      }
    }
    else
    {
      DeleteDC(v21);
    }
  }
  if ( v13 )
  {
LABEL_29:
    v23 = 0;
    v24 = SelectObject(ghdcBits2, v13);
    v49 = v24;
    if ( v44 )
    {
      if ( (unsigned __int16)v38 * HIWORD(v38) != 1 )
        v14 = 3;
      v23 = SetStretchBltMode(ghdcBits2, v14);
    }
    v25 = SetBkColor(ghdcBits2, 0xFFFFFFu);
    colora = SetTextColor(ghdcBits2, 0);
    if ( v44 )
    {
      v30 = SmartStretchDIBits(v27, v26, v28, v43, a2, iUsage, ColorUse, a6, cLines, a8, a9, lpbmi, v48, v36, v37);
    }
    else
    {
      v29 = -a2;
      if ( a2 > 0 )
        v29 = a2;
      v30 = SetDIBits(ghdcBits2, v13, 0, v29, a8, lpbmi, 0);
    }
    v31 = v30 <= 0;
    SetTextColor(ghdcBits2, colora);
    SetBkColor(ghdcBits2, v25);
    if ( v44 )
      SetStretchBltMode(ghdcBits2, v23);
    SelectObject(ghdcBits2, v24);
    if ( v31 )
    {
      DeleteObject(v13);
      v13 = 0;
    }
  }
  if ( v46 )
  {
    if ( v13 )
      v13 = Convert1BppToMonoBitmap(v20, v13);
  }
  RtlLeaveCriticalSection(&gcsHdc);
  return v13;
}

```

## disassembly

```asm
0x180005280  push    rbx
0x180005282  push    rsi
0x180005283  push    rdi
0x180005284  push    r12
0x180005286  push    r13
0x180005288  push    r14
0x18000528a  push    r15
0x18000528c  sub     rsp, 190h
0x180005293  mov     rax, cs:__security_cookie
0x18000529a  xor     rax, rsp
0x18000529d  mov     [rsp+1C8h+var_48], rax
0x1800052a5  mov     [rsp+1C8h+var_146], r9w
0x1800052ae  mov     [rsp+1C8h+var_148], r8w
0x1800052b7  mov     r15d, edx
0x1800052ba  mov     r13d, ecx
0x1800052bd  mov     rsi, [rsp+1C8h+lpbmi]
0x1800052c5  mov     rax, [rsp+1C8h+arg_38]
0x1800052cd  mov     [rsp+1C8h+lpBits], rax
0x1800052d5  mov     rax, [rsp+1C8h+arg_50]
0x1800052dd  mov     [rsp+1C8h+var_108], rax
0x1800052e5  mov     rcx, rsi
0x1800052e8  call    cs:__imp_GdiGetBitmapBitsSize
0x1800052ee  cmp     eax, [rsp+1C8h+arg_40]
0x1800052f5  ja      loc_1800057B4
0x1800052fb  call    ?AcquireGlobalGdiResources@@YAHXZ; AcquireGlobalGdiResources(void)
0x180005300  xor     ebx, ebx
0x180005302  test    eax, eax
0x180005304  jz      loc_1800057B4
0x18000530a  mov     edi, ebx
0x18000530c  mov     [rsp+1C8h+var_120], rbx
0x180005314  mov     [rsp+1C8h+var_128], ebx
0x18000531b  test    r13d, r13d
0x18000531e  cmovz   r13d, [rsp+1C8h+arg_28]
0x180005327  mov     [rsp+1C8h+var_138], r13d
0x18000532f  test    r15d, r15d
0x180005332  mov     eax, [rsp+1C8h+cLines]
0x180005339  cmovz   r15d, eax
0x18000533d  cmp     r13d, [rsp+1C8h+arg_28]
0x180005345  jnz     loc_18000572C
0x18000534b  cmp     r15d, eax
0x18000534e  jnz     loc_18000572C
0x180005354  mov     [rsp+1C8h+var_134], ebx
0x18000535b  lea     r12d, [rbx+1]
0x18000535f  test    dword ptr [rsp+1C8h+arg_20], 2800h
0x18000536a  jz      loc_18000543E
0x180005370  mov     [rsp+1C8h+ppvBits], rbx
0x180005378  movzx   eax, word ptr [rsi]
0x18000537b  mov     [rsp+1C8h+var_130], ax
0x180005383  lea     r14, [rsi+10h]
0x180005387  cmp     ax, 0Ch
0x18000538b  jz      loc_180005816
0x180005391  mov     eax, [rsi+4]
0x180005394  mov     [rsp+1C8h+color], eax
0x18000539b  lea     r13, [rsi+8]
0x18000539f  mov     eax, [r13+0]
0x1800053a3  mov     [rsp+1C8h+var_140], eax
0x1800053aa  mov     ecx, [r14]
0x1800053ad  mov     [rsp+1C8h+var_13C], ecx
0x1800053b4  mov     r9d, [rsp+1C8h+var_138]
0x1800053bc  mov     [rsi+4], r9d
0x1800053c0  mov     [r13+0], r15d
0x1800053c4  cmp     ecx, 3
0x1800053c7  jz      short loc_1800053CC
0x1800053c9  mov     [r14], ebx
0x1800053cc  mov     [rsp+1C8h+iUsage], ebx; offset
0x1800053d0  mov     rdx, rsi; pbmi
0x1800053d3  mov     rcx, cs:ghdcBits2; hdc
0x1800053da  test    dword ptr [rsp+1C8h+arg_20], 800h
0x1800053e5  jz      loc_1800057FB
0x1800053eb  mov     [rsp+1C8h+pbmi], rsi; pbmi
0x1800053f0  xor     r9d, r9d; pjBits
0x1800053f3  lea     r8d, [r9+2]; flInit
0x1800053f7  call    cs:__imp_CreateDIBitmap
0x1800053fd  mov     rdi, rax
0x180005400  mov     [rsp+1C8h+var_120], rax
0x180005408  mov     eax, [rsp+1C8h+color]
0x18000540f  cmp     [rsp+1C8h+var_130], 0Ch
0x180005418  jz      loc_180005923
0x18000541e  mov     [rsi+4], eax
0x180005421  mov     eax, [rsp+1C8h+var_140]
0x180005428  mov     [r13+0], eax
0x18000542c  mov     eax, [rsp+1C8h+var_13C]
0x180005433  mov     [r14], eax
0x180005436  mov     r13d, [rsp+1C8h+var_138]
0x18000543e  test    rdi, rdi
0x180005441  jnz     loc_180005545
0x180005447  mov     rdi, rbx
0x18000544a  cmp     cs:?gfSystemInitialized@@3HA, ebx; int gfSystemInitialized
0x180005450  jz      loc_18000570D
0x180005456  xor     ecx, ecx
0x180005458  call    cs:__imp_NtUserGetDC
0x18000545e  mov     r14, rax
0x180005461  test    rax, rax
0x180005464  jz      loc_180005534
0x18000546a  movzx   r8d, [rsp+1C8h+var_146]
0x180005473  movzx   edx, [rsp+1C8h+var_148]
0x18000547b  cmp     r8w, r12w
0x18000547f  jnz     loc_18000573F
0x180005485  cmp     dx, r12w
0x180005489  jnz     loc_18000573F
0x18000548f  mov     dword ptr [rsp+1C8h+pbmih], 28h ; '('
0x18000549a  movups  xmm0, cs:xmmword_1800A818C
0x1800054a1  movups  xmmword ptr [rsp+1C8h+pbmih+0Ch], xmm0
0x1800054a9  movups  xmm1, cs:xmmword_1800A819C
0x1800054b0  movups  xmmword ptr [rsp+1C8h+pbmih+1Ch], xmm1
0x1800054b8  mov     eax, cs:dword_1800A81AC
0x1800054be  mov     [rsp+1C8h+var_C4], eax
0x1800054c5  mov     dword ptr [rsp+1C8h+pbmih+4], r13d
0x1800054cd  mov     dword ptr [rsp+1C8h+pbmih+8], r15d
0x1800054d5  mov     [rsp+1C8h+iUsage], ebx; int
0x1800054d9  lea     rax, [rsp+1C8h+pbmih]
0x1800054e1  mov     [rsp+1C8h+pbmi], rax; pbmi
0x1800054e6  xor     r9d, r9d; pjBits
0x1800054e9  lea     r8d, [r9+2]; flInit
0x1800054ed  lea     rdx, [rsp+1C8h+pbmih]; pbmih
0x1800054f5  mov     rcx, r14; hdc
0x1800054f8  call    cs:__imp_CreateDIBitmap
0x1800054fe  mov     [rsp+1C8h+var_128], r12d
0x180005506  mov     rdi, rax
0x180005509  cmp     cs:?gfSystemInitialized@@3HA, ebx; int gfSystemInitialized
0x18000550f  jz      loc_18000578D
0x180005515  cmp     cs:?g_systemCallFilterId@@3KA, 5; ulong g_systemCallFilterId
0x18000551c  jz      loc_180005937
0x180005522  mov     rcx, r14
0x180005525  call    cs:__imp_GdiReleaseDC
0x18000552b  mov     rcx, r14
0x18000552e  call    cs:__imp_NtUserReleaseDC
0x180005534  mov     [rsp+1C8h+var_120], rdi
0x18000553c  test    rdi, rdi
0x18000553f  jz      loc_1800056CD
0x180005545  mov     r14d, ebx
0x180005548  mov     [rsp+1C8h+var_13C], ebx
0x18000554f  mov     rdx, rdi; h
0x180005552  mov     rcx, cs:ghdcBits2; hdc
0x180005559  call    cs:__imp_SelectObject
0x18000555f  mov     r13, rax
0x180005562  mov     [rsp+1C8h+var_100], rax
0x18000556a  cmp     [rsp+1C8h+var_134], ebx
0x180005571  jnz     loc_1800057BB
0x180005577  mov     edx, 0FFFFFFh; color
0x18000557c  mov     rcx, cs:ghdcBits2; hdc
0x180005583  call    cs:__imp_SetBkColor
0x180005589  mov     r12d, eax
0x18000558c  mov     [rsp+1C8h+var_140], eax
0x180005593  xor     edx, edx; color
0x180005595  mov     rcx, cs:ghdcBits2; hdc
0x18000559c  call    cs:__imp_SetTextColor
0x1800055a2  mov     [rsp+1C8h+color], eax
0x1800055a9  cmp     [rsp+1C8h+var_134], ebx
0x1800055b0  jnz     short loc_1800055E7
0x1800055b2  mov     r9d, r15d
0x1800055b5  neg     r9d
0x1800055b8  cmovs   r9d, r15d; cLines
0x1800055bc  mov     [rsp+1C8h+ColorUse], ebx; ColorUse
0x1800055c0  mov     qword ptr [rsp+1C8h+iUsage], rsi; lpbmi
0x1800055c5  mov     rax, [rsp+1C8h+lpBits]
0x1800055cd  mov     [rsp+1C8h+pbmi], rax; lpBits
0x1800055d2  xor     r8d, r8d; start
0x1800055d5  mov     rdx, rdi; hbm
0x1800055d8  mov     rcx, cs:ghdcBits2; hdc
0x1800055df  call    cs:__imp_SetDIBits
0x1800055e5  jmp     short loc_180005639
0x1800055e7  mov     rax, [rsp+1C8h+var_108]
0x1800055ef  mov     [rsp+1C8h+var_168], rax; struct tagBITMAPINFO *
0x1800055f4  mov     [rsp+1C8h+var_170], rsi; struct tagBITMAPINFO *
0x1800055f9  mov     eax, [rsp+1C8h+arg_40]
0x180005600  mov     [rsp+1C8h+var_178], eax; unsigned int
0x180005604  mov     rax, [rsp+1C8h+lpBits]
0x18000560c  mov     [rsp+1C8h+var_180], rax; void *
0x180005611  mov     eax, [rsp+1C8h+cLines]
0x180005618  mov     [rsp+1C8h+var_188], eax; int
0x18000561c  mov     eax, [rsp+1C8h+arg_28]
0x180005623  mov     [rsp+1C8h+var_190], eax; int
0x180005627  mov     dword ptr [rsp+1C8h+pbmi], r15d; int
0x18000562c  mov     r9d, [rsp+1C8h+var_138]; int
0x180005634  call    ?SmartStretchDIBits@@YAHPEAUHDC__@@HHHHHHHHPEAXKPEAUtagBITMAPINFO@@2IK@Z; SmartStretchDIBits(HDC__ *,int,int,int,int,int,int,int,int,void *,ulong,tagBITMAPINFO *,tagBITMAPINFO *,uint,ulong)
0x180005639  mov     esi, ebx
0x18000563b  test    eax, eax
0x18000563d  setle   sil
0x180005641  mov     [rsp+1C8h+var_12C], esi
0x180005648  jmp     short loc_180005678
0x18000564a  mov     esi, 1
0x18000564f  mov     [rsp+1C8h+var_12C], esi
0x180005656  xor     ebx, ebx
0x180005658  mov     rdi, [rsp+1C8h+var_120]
0x180005660  mov     r14d, [rsp+1C8h+var_13C]
0x180005668  mov     r13, [rsp+1C8h+var_100]
0x180005670  mov     r12d, [rsp+1C8h+var_140]
0x180005678  mov     edx, [rsp+1C8h+color]; color
0x18000567f  mov     rcx, cs:ghdcBits2; hdc
0x180005686  call    cs:__imp_SetTextColor
0x18000568c  mov     edx, r12d; color
0x18000568f  mov     rcx, cs:ghdcBits2; hdc
0x180005696  call    cs:__imp_SetBkColor
0x18000569c  cmp     [rsp+1C8h+var_134], ebx
0x1800056a3  jz      short loc_1800056B5
0x1800056a5  mov     edx, r14d; mode
0x1800056a8  mov     rcx, cs:ghdcBits2; hdc
0x1800056af  call    cs:__imp_SetStretchBltMode
0x1800056b5  mov     rdx, r13; h
0x1800056b8  mov     rcx, cs:ghdcBits2; hdc
0x1800056bf  call    cs:__imp_SelectObject
0x1800056c5  test    esi, esi
0x1800056c7  jnz     loc_180005846
0x1800056cd  cmp     [rsp+1C8h+var_128], ebx
0x1800056d4  jnz     loc_18000579B
0x1800056da  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800056e1  call    cs:__imp_RtlLeaveCriticalSection
0x1800056e7  mov     rax, rdi
0x1800056ea  mov     rcx, [rsp+1C8h+var_48]
0x1800056f2  xor     rcx, rsp; StackCookie
0x1800056f5  call    __security_check_cookie
0x1800056fa  add     rsp, 190h
0x180005701  pop     r15
0x180005703  pop     r14
0x180005705  pop     r13
0x180005707  pop     r12
0x180005709  pop     rdi
0x18000570a  pop     rsi
0x18000570b  pop     rbx
0x18000570c  retn
0x18000570d  xor     r9d, r9d; pdm
0x180005710  xor     r8d, r8d; pszPort
0x180005713  lea     rdx, pszFormat; pwszDevice
0x18000571a  lea     rcx, pwszDriver; "DISPLAY"
0x180005721  call    cs:__imp_CreateDCW
0x180005727  jmp     loc_18000545E
0x18000572c  mov     r12d, 1
0x180005732  mov     [rsp+1C8h+var_134], r12d
0x18000573a  jmp     loc_18000535F
0x18000573f  test    dx, dx
0x180005742  jz      short loc_18000575B
0x180005744  mov     rax, cs:gpsi
0x18000574b  movzx   ecx, byte ptr [rax+1B5Ah]
0x180005752  cmp     dx, cx
0x180005755  jnz     loc_180005857
0x18000575b  test    r8w, r8w
0x18000575f  jz      short loc_180005779
0x180005761  mov     rax, cs:gpsi
0x180005768  movzx   ecx, byte ptr [rax+1B5Bh]
0x18000576f  cmp     r8w, cx
0x180005773  jnz     loc_180005857
0x180005779  mov     r8d, r15d; cy
0x18000577c  mov     edx, r13d; cx
0x18000577f  mov     rcx, r14; hdc
0x180005782  call    cs:__imp_CreateCompatibleBitmap
0x180005788  jmp     loc_180005506
0x18000578d  mov     rcx, r14; hdc
0x180005790  call    cs:__imp_DeleteDC
0x180005796  jmp     loc_180005534
0x18000579b  test    rdi, rdi
0x18000579e  jz      loc_1800056DA
0x1800057a4  mov     rdx, rdi; HBITMAP
0x1800057a7  call    ?Convert1BppToMonoBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@PEAU1@@Z; Convert1BppToMonoBitmap(HDC__ *,HBITMAP__ *)
0x1800057ac  mov     rdi, rax
0x1800057af  jmp     loc_1800056DA
0x1800057b4  xor     eax, eax
0x1800057b6  jmp     loc_1800056EA
0x1800057bb  movzx   r8d, [rsp+1C8h+var_146]
0x1800057c4  movzx   ecx, [rsp+1C8h+var_148]
0x1800057cc  imul    r8d, ecx
0x1800057d0  cmp     r8d, r12d
0x1800057d3  mov     eax, 3
0x1800057d8  cmovnz  r12d, eax
0x1800057dc  mov     edx, r12d; mode
0x1800057df  mov     rcx, cs:ghdcBits2; hdc
0x1800057e6  call    cs:__imp_SetStretchBltMode
0x1800057ec  mov     r14d, eax
0x1800057ef  mov     [rsp+1C8h+var_13C], eax
0x1800057f6  jmp     loc_180005577
0x1800057fb  mov     [rsp+1C8h+pbmi], rbx; hSection
0x180005800  lea     r9, [rsp+1C8h+ppvBits]; ppvBits
0x180005808  xor     r8d, r8d; usage
0x18000580b  call    cs:__imp_CreateDIBSection
0x180005811  jmp     loc_1800053FD
0x180005816  mov     [rsp+1C8h+var_13C], ebx
0x18000581d  movzx   eax, word ptr [rsi+4]
0x180005821  mov     [rsp+1C8h+color], eax
0x180005828  movzx   eax, word ptr [rsi+6]
0x18000582c  mov     [rsp+1C8h+var_140], eax
0x180005833  mov     [rsi+4], r13w
0x180005838  mov     [rsi+6], r15w
0x18000583d  lea     r13, [rsi+8]
0x180005841  jmp     loc_1800053CC
0x180005846  mov     rcx, rdi; ho
0x180005849  call    cs:__imp_DeleteObject
0x18000584f  mov     rdi, rbx
0x180005852  jmp     loc_1800056CD
0x180005857  movaps  xmm0, cs:xmmword_1800A8AB0
0x18000585e  movaps  xmmword ptr [rsp+1C8h+var_B8.biSize], xmm0
0x180005866  movaps  xmm1, cs:xmmword_1800A8AC0
0x18000586d  movaps  xmmword ptr [rsp+1C8h+var_B8.biCompression], xmm1
0x180005875  movaps  xmm0, cs:xmmword_1800A8AD0
0x18000587c  movaps  xmmword ptr [rsp+1C8h+var_B8.biClrUsed], xmm0
0x180005884  movaps  xmm1, cs:xmmword_1800A8AE0
0x18000588b  movaps  [rsp+1C8h+var_88], xmm1
0x180005893  movaps  xmm0, cs:xmmword_1800A8AF0
0x18000589a  movaps  [rsp+1C8h+var_78], xmm0
0x1800058a2  movaps  xmm1, cs:xmmword_1800A8B00
0x1800058a9  movaps  [rsp+1C8h+var_68], xmm1
  ... truncated ...
```
