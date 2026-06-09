# InnerGrayStringAorW(HDC__ *,HBRUSH__ *,int (*)(HDC__ *,__int64,int),__int64,int,int,int,int,int,int)

- ea: `0x1800934b8`
- end: `0x180093852`
- name: `?InnerGrayStringAorW@@YAHPEAUHDC__@@PEAUHBRUSH__@@P6AH0_JH@Z2HHHHHH@Z`
- size: `922`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, HBRUSH@<rdx>, int (*)(HDC, __int64, int)@<r8>, __int64@<r9>, int, int x, int y, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180094150`
- `0x1800941b0`

## callees

- `0x180005d48`
- `0x1800934b8`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180093833`
- `ntdll!RtlLeaveCriticalSection` at `0x180093833`
- `GDI32!SelectObject` at `0x180093624`
- `GDI32!SelectObject` at `0x180093689`
- `GDI32!SelectObject` at `0x18009369f`
- `GDI32!SelectObject` at `0x1800936b1`
- `GDI32!SelectObject` at `0x180093791`
- `GDI32!SelectObject` at `0x1800937de`
- `GDI32!SelectObject` at `0x18009380b`
- `GDI32!SelectObject` at `0x180093624`
- `GDI32!SelectObject` at `0x180093689`
- `GDI32!SelectObject` at `0x18009369f`
- `GDI32!SelectObject` at `0x1800936b1`
- `GDI32!SelectObject` at `0x180093791`
- `GDI32!SelectObject` at `0x1800937de`
- `GDI32!SelectObject` at `0x18009380b`
- `GDI32!GetStockObject` at `0x18009367a`
- `GDI32!GetStockObject` at `0x18009367a`
- `GDI32!SetBkColor` at `0x180093770`
- `GDI32!SetBkColor` at `0x1800937f5`
- `GDI32!SetBkColor` at `0x180093770`
- `GDI32!SetBkColor` at `0x1800937f5`
- `GDI32!SetTextColor` at `0x18009375f`
- `GDI32!SetTextColor` at `0x1800937ea`
- `GDI32!SetTextColor` at `0x18009375f`
- `GDI32!SetTextColor` at `0x1800937ea`
- `GDI32!GetLayout` at `0x180093652`
- `GDI32!GetLayout` at `0x180093652`
- `GDI32!TextOutA` at `0x180093713`
- `GDI32!TextOutA` at `0x180093713`
- `GDI32!SetLayoutWidth` at `0x18009366b`
- `GDI32!SetLayoutWidth` at `0x180093826`
- `GDI32!SetLayoutWidth` at `0x18009366b`
- `GDI32!SetLayoutWidth` at `0x180093826`
- `GDI32!GetTextExtentPointA` at `0x180093578`
- `GDI32!GetTextExtentPointA` at `0x180093578`
- `GDI32!TextOutW` at `0x18009371b`
- `GDI32!TextOutW` at `0x18009371b`
- `GDI32!GetTextExtentPointW` at `0x180093580`
- `GDI32!GetTextExtentPointW` at `0x180093580`
- `GDI32!CreateBitmap` at `0x18009360f`
- `GDI32!CreateBitmap` at `0x18009360f`
- `GDI32!PatBlt` at `0x1800936e5`
- `GDI32!PatBlt` at `0x180093747`
- `GDI32!PatBlt` at `0x1800936e5`
- `GDI32!PatBlt` at `0x180093747`
- `GDI32!BitBlt` at `0x1800937d2`
- `GDI32!BitBlt` at `0x1800937d2`
- `GDI32!DeleteObject` at `0x18009362d`
- `GDI32!DeleteObject` at `0x18009362d`

## pseudocode

```c
__int64 __fastcall InnerGrayStringAorW(
        HDC hdc,
        HBRUSH a2,
        int (*a3)(HDC, __int64, int),
        const CHAR *a4,
        int a5,
        int x,
        int y,
        unsigned int nWidth,
        LONG nHeight,
        int a10)
{
  __int64 v12; // rsi
  unsigned int cx; // ebx
  LONG cy; // r12d
  HBITMAP Bitmap; // rax
  HGDIOBJ v16; // rax
  HGDIOBJ StockObject; // rdi
  HGDIOBJ v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // edi
  COLORREF v21; // r14d
  COLORREF v22; // esi
  HBRUSH v23; // rdx
  HGDIOBJ v24; // rdi
  unsigned int v26; // [rsp+50h] [rbp-68h]
  struct tagSIZE sz; // [rsp+58h] [rbp-60h] BYREF
  HGDIOBJ h; // [rsp+60h] [rbp-58h]

  LODWORD(v12) = a5;
  if ( !a5 )
  {
    v12 = -1;
    if ( a10 )
    {
      do
        ++v12;
      while ( a4[v12] );
    }
    else
    {
      do
        ++v12;
      while ( *(_WORD *)&a4[2 * v12] );
    }
  }
  cx = nWidth;
  if ( !nWidth || (cy = nHeight) == 0 )
  {
    sz = 0;
    if ( a10 )
      GetTextExtentPointA(hdc, a4, v12, &sz);
    else
      GetTextExtentPointW(hdc, (LPCWSTR)a4, v12, &sz);
    cx = sz.cx;
    cy = sz.cy;
  }
  if ( !(unsigned int)AcquireGlobalGdiResources() )
    return 0;
  sz.cx = -1;
  if ( gcxGray < (int)cx || gcyGray < cy )
  {
    Bitmap = CreateBitmap(cx, cy, 1u, 1u, 0);
    if ( Bitmap )
    {
      v16 = SelectObject(ghdcGray, Bitmap);
      DeleteObject(v16);
      gcxGray = cx;
      gcyGray = cy;
    }
    else
    {
      cx = gcxGray;
      cy = gcyGray;
    }
  }
  if ( (GetLayout(hdc) & 1) != 0 )
    sz.cx = SetLayoutWidth(ghdcGray, cx, 1);
  StockObject = GetStockObject(13);
  v18 = SelectObject(hdc, StockObject);
  h = v18;
  if ( v18 != StockObject )
  {
    SelectObject(hdc, v18);
    h = SelectObject(ghdcGray, h);
  }
  if ( a3 )
  {
    PatBlt(ghdcGray, 0, 0, cx, cy, 0xFF0062u);
    v19 = ((__int64 (__fastcall *)(HDC, const CHAR *, _QWORD))a3)(ghdcGray, a4, (unsigned int)v12);
  }
  else if ( a10 )
  {
    v19 = TextOutA(ghdcGray, 0, 0, a4, v12);
  }
  else
  {
    v19 = TextOutW(ghdcGray, 0, 0, (LPCWSTR)a4, v12);
  }
  v20 = v19;
  v26 = v19;
  if ( v19 )
  {
    PatBlt(ghdcGray, 0, 0, cx, cy, 0xFA0000u);
LABEL_30:
    v21 = SetTextColor(hdc, 0);
    v22 = SetBkColor(hdc, 0xFFFFFFu);
    v23 = ghbrWindowText;
    if ( a2 )
      v23 = a2;
    v24 = SelectObject(hdc, v23);
    BitBlt(hdc, x, y, cx, cy, ghdcGray, 0, 0, 0xB80000u);
    SelectObject(hdc, v24);
    SetTextColor(hdc, v21);
    SetBkColor(hdc, v22);
    v20 = v26;
    goto LABEL_33;
  }
  if ( (_DWORD)v12 == -1 )
    goto LABEL_30;
LABEL_33:
  SelectObject(ghdcGray, h);
  if ( sz.cx != -1 )
    SetLayoutWidth(ghdcGray, cx, (unsigned int)sz.cx);
  RtlLeaveCriticalSection(&gcsHdc);
  return v20;
}

```

## disassembly

```asm
0x1800934b8  mov     rax, rsp
0x1800934bb  mov     [rax+20h], r9
0x1800934bf  mov     [rax+18h], r8
0x1800934c3  mov     [rax+10h], rdx
0x1800934c7  mov     [rax+8], rcx
0x1800934cb  push    rbx
0x1800934cc  push    rsi
0x1800934cd  push    rdi
0x1800934ce  push    r12
0x1800934d0  push    r13
0x1800934d2  push    r14
0x1800934d4  push    r15
0x1800934d6  sub     rsp, 80h
0x1800934dd  mov     r14, r9
0x1800934e0  mov     r13, rcx
0x1800934e3  xor     r15d, r15d
0x1800934e6  mov     edi, r15d
0x1800934e9  mov     esi, [rax+28h]
0x1800934ec  test    esi, esi
0x1800934ee  jnz     short loc_180093543
0x1800934f0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800934f4  cmp     [rsp+0B8h+arg_48], r15d
0x1800934fc  jz      short loc_180093509
0x1800934fe  inc     rsi
0x180093501  cmp     [r9+rsi], r15b
0x180093505  jnz     short loc_1800934FE
0x180093507  jmp     short loc_180093513
0x180093509  inc     rsi
0x18009350c  cmp     [r9+rsi*2], r15w
0x180093511  jnz     short loc_180093509
0x180093513  mov     [rsp+0B8h+arg_20], esi
0x18009351a  jmp     short loc_18009353B
0x18009351c  mov     edi, 1
0x180093521  xor     r15d, r15d
0x180093524  mov     esi, [rsp+0B8h+arg_20]
0x18009352b  mov     r14, [rsp+0B8h+arg_18]
0x180093533  mov     r13, [rsp+0B8h+arg_0]
0x18009353b  test    edi, edi
0x18009353d  jnz     loc_18009383D
0x180093543  mov     ebx, [rsp+0B8h+nWidth]
0x18009354a  test    ebx, ebx
0x18009354c  jz      short loc_18009355B
0x18009354e  mov     r12d, [rsp+0B8h+nHeight]
0x180093556  test    r12d, r12d
0x180093559  jnz     short loc_1800935D7
0x18009355b  mov     qword ptr [rsp+0B8h+sz.cx], r15
0x180093560  lea     r9, [rsp+0B8h+sz]; lpsz
0x180093565  mov     r8d, esi; c
0x180093568  mov     rdx, r14; lpString
0x18009356b  mov     rcx, r13; hdc
0x18009356e  cmp     [rsp+0B8h+arg_48], r15d
0x180093576  jz      short loc_180093580
0x180093578  call    cs:__imp_GetTextExtentPointA
0x18009357e  jmp     short loc_180093586
0x180093580  call    cs:__imp_GetTextExtentPointW
0x180093586  mov     rbx, qword ptr [rsp+0B8h+sz.cx]
0x18009358b  mov     [rsp+0B8h+nWidth], ebx
0x180093592  mov     r12d, [rsp+0B8h+sz.cy]
0x180093597  mov     [rsp+0B8h+nHeight], r12d
0x18009359f  jmp     short loc_1800935CF
0x1800935a1  mov     edi, 1
0x1800935a6  xor     r15d, r15d
0x1800935a9  mov     r12d, [rsp+0B8h+nHeight]
0x1800935b1  mov     ebx, [rsp+0B8h+nWidth]
0x1800935b8  mov     esi, [rsp+0B8h+arg_20]
0x1800935bf  mov     r14, [rsp+0B8h+arg_18]
0x1800935c7  mov     r13, [rsp+0B8h+arg_0]
0x1800935cf  test    edi, edi
0x1800935d1  jnz     loc_18009383D
0x1800935d7  call    ?AcquireGlobalGdiResources@@YAHXZ; AcquireGlobalGdiResources(void)
0x1800935dc  test    eax, eax
0x1800935de  jz      loc_18009383D
0x1800935e4  or      eax, 0FFFFFFFFh
0x1800935e7  mov     [rsp+0B8h+sz.cx], eax
0x1800935eb  cmp     cs:?gcxGray@@3HA, ebx; int gcxGray
0x1800935f1  jl      short loc_1800935FC
0x1800935f3  cmp     cs:?gcyGray@@3HA, r12d; int gcyGray
0x1800935fa  jge     short loc_18009364F
0x1800935fc  mov     [rsp+0B8h+lpBits], r15; lpBits
0x180093601  mov     r9d, 1; nBitCount
0x180093607  mov     r8d, r9d; nPlanes
0x18009360a  mov     edx, r12d; nHeight
0x18009360d  mov     ecx, ebx; nWidth
0x18009360f  call    cs:__imp_CreateBitmap
0x180093615  test    rax, rax
0x180093618  jz      short loc_180093642
0x18009361a  mov     rdx, rax; h
0x18009361d  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x180093624  call    cs:__imp_SelectObject
0x18009362a  mov     rcx, rax; ho
0x18009362d  call    cs:__imp_DeleteObject
0x180093633  mov     cs:?gcxGray@@3HA, ebx; int gcxGray
0x180093639  mov     cs:?gcyGray@@3HA, r12d; int gcyGray
0x180093640  jmp     short loc_18009364F
0x180093642  mov     ebx, cs:?gcxGray@@3HA; int gcxGray
0x180093648  mov     r12d, cs:?gcyGray@@3HA; int gcyGray
0x18009364f  mov     rcx, r13; hdc
0x180093652  call    cs:__imp_GetLayout
0x180093658  test    al, 1
0x18009365a  jz      short loc_180093675
0x18009365c  mov     r8d, 1
0x180093662  mov     edx, ebx
0x180093664  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x18009366b  call    cs:__imp_SetLayoutWidth
0x180093671  mov     [rsp+0B8h+sz.cx], eax
0x180093675  mov     ecx, 0Dh; i
0x18009367a  call    cs:__imp_GetStockObject
0x180093680  mov     rdi, rax
0x180093683  mov     rdx, rax; h
0x180093686  mov     rcx, r13; hdc
0x180093689  call    cs:__imp_SelectObject
0x18009368f  mov     [rsp+0B8h+h], rax
0x180093694  cmp     rax, rdi
0x180093697  jz      short loc_1800936BC
0x180093699  mov     rdx, rax; h
0x18009369c  mov     rcx, r13; hdc
0x18009369f  call    cs:__imp_SelectObject
0x1800936a5  mov     rdx, [rsp+0B8h+h]; h
0x1800936aa  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x1800936b1  call    cs:__imp_SelectObject
0x1800936b7  mov     [rsp+0B8h+h], rax
0x1800936bc  mov     rdi, [rsp+0B8h+arg_10]
0x1800936c4  xor     r8d, r8d; y
0x1800936c7  xor     edx, edx; x
0x1800936c9  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x1800936d0  test    rdi, rdi
0x1800936d3  jz      short loc_180093702
0x1800936d5  mov     [rsp+0B8h+rop], 0FF0062h; rop
0x1800936dd  mov     dword ptr [rsp+0B8h+lpBits], r12d; h
0x1800936e2  mov     r9d, ebx; w
0x1800936e5  call    cs:__imp_PatBlt
0x1800936eb  mov     r8d, esi
0x1800936ee  mov     rdx, r14
0x1800936f1  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x1800936f8  mov     rax, rdi
0x1800936fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093700  jmp     short loc_180093721
0x180093702  mov     dword ptr [rsp+0B8h+lpBits], esi; c
0x180093706  mov     r9, r14; lpString
0x180093709  cmp     [rsp+0B8h+arg_48], r15d
0x180093711  jz      short loc_18009371B
0x180093713  call    cs:__imp_TextOutA
0x180093719  jmp     short loc_180093721
0x18009371b  call    cs:__imp_TextOutW
0x180093721  mov     edi, eax
0x180093723  mov     [rsp+0B8h+var_68], eax
0x180093727  test    eax, eax
0x180093729  jz      short loc_180093751
0x18009372b  mov     [rsp+0B8h+rop], 0FA0000h; rop
0x180093733  mov     dword ptr [rsp+0B8h+lpBits], r12d; h
0x180093738  mov     r9d, ebx; w
0x18009373b  xor     r8d, r8d; y
0x18009373e  xor     edx, edx; x
0x180093740  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x180093747  call    cs:__imp_PatBlt
0x18009374d  test    edi, edi
0x18009374f  jnz     short loc_18009375A
0x180093751  cmp     esi, 0FFFFFFFFh
0x180093754  jnz     loc_1800937FF
0x18009375a  xor     edx, edx; color
0x18009375c  mov     rcx, r13; hdc
0x18009375f  call    cs:__imp_SetTextColor
0x180093765  mov     r14d, eax
0x180093768  mov     edx, 0FFFFFFh; color
0x18009376d  mov     rcx, r13; hdc
0x180093770  call    cs:__imp_SetBkColor
0x180093776  mov     esi, eax
0x180093778  mov     rdx, cs:?ghbrWindowText@@3PEAUHBRUSH__@@EA; HBRUSH__ * ghbrWindowText
0x18009377f  mov     rax, [rsp+0B8h+arg_8]
0x180093787  test    rax, rax
0x18009378a  cmovnz  rdx, rax; h
0x18009378e  mov     rcx, r13; hdc
0x180093791  call    cs:__imp_SelectObject
0x180093797  mov     rdi, rax
0x18009379a  mov     [rsp+0B8h+var_78], 0B80000h; rop
0x1800937a2  mov     [rsp+0B8h+y1], r15d; y1
0x1800937a7  mov     [rsp+0B8h+x1], r15d; x1
0x1800937ac  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x1800937b3  mov     qword ptr [rsp+0B8h+rop], rcx; hdcSrc
0x1800937b8  mov     dword ptr [rsp+0B8h+lpBits], r12d; cy
0x1800937bd  mov     r9d, ebx; cx
0x1800937c0  mov     r8d, [rsp+0B8h+y]; y
0x1800937c8  mov     edx, [rsp+0B8h+x]; x
0x1800937cf  mov     rcx, r13; hdc
0x1800937d2  call    cs:__imp_BitBlt
0x1800937d8  mov     rdx, rdi; h
0x1800937db  mov     rcx, r13; hdc
0x1800937de  call    cs:__imp_SelectObject
0x1800937e4  mov     edx, r14d; color
0x1800937e7  mov     rcx, r13; hdc
0x1800937ea  call    cs:__imp_SetTextColor
0x1800937f0  mov     edx, esi; color
0x1800937f2  mov     rcx, r13; hdc
0x1800937f5  call    cs:__imp_SetBkColor
0x1800937fb  mov     edi, [rsp+0B8h+var_68]
0x1800937ff  mov     rdx, [rsp+0B8h+h]; h
0x180093804  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18009380b  call    cs:__imp_SelectObject
0x180093811  mov     eax, [rsp+0B8h+sz.cx]
0x180093815  cmp     eax, 0FFFFFFFFh
0x180093818  jz      short loc_18009382C
0x18009381a  mov     r8d, eax
0x18009381d  mov     edx, ebx
0x18009381f  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; HDC__ * ghdcGray
0x180093826  call    cs:__imp_SetLayoutWidth
0x18009382c  lea     rcx, ?gcsHdc@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180093833  call    cs:__imp_RtlLeaveCriticalSection
0x180093839  mov     eax, edi
0x18009383b  jmp     short loc_18009383F
0x18009383d  xor     eax, eax
0x18009383f  add     rsp, 80h
0x180093846  pop     r15
0x180093848  pop     r14
0x18009384a  pop     r13
0x18009384c  pop     r12
0x18009384e  pop     rdi
0x18009384f  pop     rsi
0x180093850  pop     rbx
0x180093851  retn
0x180097dcb  push    rbp
0x180097dcd  sub     rsp, 50h
0x180097dd1  mov     rbp, rdx
0x180097dd4  mov     eax, 1
0x180097dd9  add     rsp, 50h
0x180097ddd  pop     rbp
0x180097dde  retn
0x180097de0  push    rbp
0x180097de2  sub     rsp, 50h
0x180097de6  mov     rbp, rdx
0x180097de9  mov     eax, 1
0x180097dee  add     rsp, 50h
0x180097df2  pop     rbp
0x180097df3  retn
```
