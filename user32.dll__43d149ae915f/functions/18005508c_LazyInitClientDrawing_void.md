# LazyInitClientDrawing(void)

- ea: `0x18005508c`
- end: `0x1800551b6`
- name: `?LazyInitClientDrawing@@YAHXZ`
- size: `298`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005d48`

## callees

- `0x18005508c`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800551a3`
- `ntdll!RtlSetLastWin32Error` at `0x1800551a3`
- `GDI32!SetBkMode` at `0x180055170`
- `GDI32!SetBkMode` at `0x180055170`
- `GDI32!SelectObject` at `0x180055128`
- `GDI32!SelectObject` at `0x180055143`
- `GDI32!SelectObject` at `0x18005515e`
- `GDI32!SelectObject` at `0x180055128`
- `GDI32!SelectObject` at `0x180055143`
- `GDI32!SelectObject` at `0x18005515e`
- `GDI32!GetStockObject` at `0x180055133`
- `GDI32!GetStockObject` at `0x180055133`
- `GDI32!SetBkColor` at `0x180055191`
- `GDI32!SetBkColor` at `0x180055191`
- `GDI32!SetTextColor` at `0x18005517f`
- `GDI32!SetTextColor` at `0x18005517f`
- `GDI32!CreateSolidBrush` at `0x1800550de`
- `GDI32!CreateSolidBrush` at `0x1800550de`
- `GDI32!CreateBitmap` at `0x1800550c8`
- `GDI32!CreateBitmap` at `0x1800550c8`
- `GDI32!CreateCompatibleDC` at `0x180055098`
- `GDI32!CreateCompatibleDC` at `0x1800550f0`
- `GDI32!CreateCompatibleDC` at `0x180055098`
- `GDI32!CreateCompatibleDC` at `0x1800550f0`

## pseudocode

```c
__int64 LazyInitClientDrawing(void)
{
  HBITMAP Bitmap; // rdi
  HBRUSH v1; // rbx
  HGDIOBJ StockObject; // rax

  ghdcBits2 = CreateCompatibleDC(0);
  if ( ghdcBits2 )
  {
    Bitmap = CreateBitmap(8, 8, 1u, 1u, "U");
    ghbrWindowText = CreateSolidBrush(*(_DWORD *)(gpsi + 4600));
    v1 = ghbrWindowText;
    ghdcGray = CreateCompatibleDC(0);
    if ( ghdcGray != 0 && Bitmap != 0 && v1 != 0 )
    {
      SelectObject(ghdcGray, Bitmap);
      StockObject = GetStockObject(13);
      SelectObject(ghdcGray, StockObject);
      SelectObject(ghdcGray, *(HGDIOBJ *)(gpsi + 4944));
      SetBkMode(ghdcGray, 2);
      SetTextColor(ghdcGray, 0);
      SetBkColor(ghdcGray, 0xFFFFFFu);
      return 1;
    }
  }
  else
  {
    RtlSetLastWin32Error(0xEu);
  }
  return 0;
}

```

## disassembly

```asm
0x18005508c  mov     [rsp+arg_0], rbx
0x180055091  push    rdi
0x180055092  sub     rsp, 30h
0x180055096  xor     ecx, ecx; hdc
0x180055098  call    cs:__imp_CreateCompatibleDC
0x18005509e  mov     cs:ghdcBits2, rax
0x1800550a5  test    rax, rax
0x1800550a8  jz      loc_18005519E
0x1800550ae  mov     ecx, 8; nWidth
0x1800550b3  lea     rax, aU; "U"
0x1800550ba  mov     edx, ecx; nHeight
0x1800550bc  mov     [rsp+38h+lpBits], rax; lpBits
0x1800550c1  lea     r9d, [rcx-7]; nBitCount
0x1800550c5  mov     r8d, r9d; nPlanes
0x1800550c8  call    cs:__imp_CreateBitmap
0x1800550ce  mov     rcx, cs:gpsi
0x1800550d5  mov     rdi, rax
0x1800550d8  mov     ecx, [rcx+11F8h]; color
0x1800550de  call    cs:__imp_CreateSolidBrush
0x1800550e4  xor     ecx, ecx; hdc
0x1800550e6  mov     cs:?ghbrWindowText@@3PEAUHBRUSH__@@EA, rax; HBRUSH__ * ghbrWindowText
0x1800550ed  mov     rbx, rax
0x1800550f0  call    cs:__imp_CreateCompatibleDC
0x1800550f6  xor     edx, edx
0x1800550f8  mov     cs:?ghdcGray@@3PEAUHDC__@@EA, rax; HDC__ * ghdcGray
0x1800550ff  test    rbx, rbx
0x180055102  mov     rcx, rax
0x180055105  mov     r8, rax
0x180055108  setnz   dl
0x18005510b  xor     eax, eax
0x18005510d  test    rdi, rdi
0x180055110  setnz   al
0x180055113  and     edx, eax
0x180055115  neg     rcx
0x180055118  sbb     eax, eax
0x18005511a  test    edx, eax
0x18005511c  jz      loc_1800551A9
0x180055122  mov     rdx, rdi; h
0x180055125  mov     rcx, r8; hdc
0x180055128  call    cs:__imp_SelectObject
0x18005512e  mov     ecx, 0Dh; i
0x180055133  call    cs:__imp_GetStockObject
0x180055139  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x180055140  mov     rdx, rax; h
0x180055143  call    cs:__imp_SelectObject
0x180055149  mov     rdx, cs:gpsi
0x180055150  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x180055157  mov     rdx, [rdx+1350h]; h
0x18005515e  call    cs:__imp_SelectObject
0x180055164  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18005516b  mov     edx, 2; mode
0x180055170  call    cs:__imp_SetBkMode
0x180055176  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18005517d  xor     edx, edx; color
0x18005517f  call    cs:__imp_SetTextColor
0x180055185  mov     rcx, cs:?ghdcGray@@3PEAUHDC__@@EA; hdc
0x18005518c  mov     edx, 0FFFFFFh; color
0x180055191  call    cs:__imp_SetBkColor
0x180055197  mov     eax, 1
0x18005519c  jmp     short loc_1800551AB
0x18005519e  mov     ecx, 0Eh; LastError
0x1800551a3  call    cs:__imp_RtlSetLastWin32Error
0x1800551a9  xor     eax, eax
0x1800551ab  mov     rbx, [rsp+38h+arg_0]
0x1800551b0  add     rsp, 30h
0x1800551b4  pop     rdi
0x1800551b5  retn
```
