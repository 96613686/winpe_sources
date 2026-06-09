# PaintDesktop

- ea: `0x180089550`
- end: `0x180089753`
- name: `PaintDesktop`
- size: `515`
- prototype: `BOOL __stdcall(HDC hdc)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180034c90`
- `0x18004e41c`
- `0x180051a90`
- `0x180089550`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserPaintDesktop` at `0x180089729`
- `win32u!NtUserPaintDesktop` at `0x180089729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008971c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008971c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800895fc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800895fc`
- `GDI32!SelectObject` at `0x1800896a6`
- `GDI32!SelectObject` at `0x180089701`
- `GDI32!SelectObject` at `0x1800896a6`
- `GDI32!SelectObject` at `0x180089701`
- `GDI32!GetDCOrgEx` at `0x1800896b7`
- `GDI32!GetDCOrgEx` at `0x1800896b7`
- `GDI32!CreateDIBSection` at `0x18008967e`
- `GDI32!CreateDIBSection` at `0x18008967e`
- `GDI32!DeleteDC` at `0x18008970a`
- `GDI32!DeleteDC` at `0x18008970a`
- `GDI32!BitBlt` at `0x1800896f2`
- `GDI32!BitBlt` at `0x1800896f2`
- `GDI32!CreateCompatibleDC` at `0x180089692`
- `GDI32!CreateCompatibleDC` at `0x180089692`
- `GDI32!DeleteObject` at `0x180089713`
- `GDI32!DeleteObject` at `0x180089713`

## pseudocode

```c
BOOL __stdcall PaintDesktop(HDC hdc)
{
  BOOL v1; // ebx
  HWND ShellWindow; // rax
  HWND v4; // rdi
  LONG v5; // r12d
  LONG v6; // r13d
  HANDLE FileMappingW; // r15
  HBITMAP v8; // r14
  HDC CompatibleDC; // rax
  HDC v10; // rdi
  HGDIOBJ h; // [rsp+50h] [rbp-49h] BYREF
  struct tagPOINT pt; // [rsp+58h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-39h] BYREF
  void *ppvBits; // [rsp+70h] [rbp-29h] BYREF
  BITMAPINFO pbmi; // [rsp+78h] [rbp-21h] BYREF

  v1 = 0;
  ppvBits = 0;
  pt = 0;
  Rect = 0;
  h = 0;
  memset(&pbmi, 0, sizeof(pbmi));
  ShellWindow = GetShellWindow();
  v4 = ShellWindow;
  if ( !ShellWindow )
    return NtUserPaintDesktop(hdc);
  if ( !GetWindowRect(ShellWindow, &Rect) )
    return NtUserPaintDesktop(hdc);
  v5 = Rect.right - Rect.left;
  v6 = Rect.bottom - Rect.top;
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   0,
                   4u,
                   0,
                   4 * (Rect.right - Rect.left) * (Rect.bottom - Rect.top),
                   L"Local\\Microsoft-Windows-DesktopBackground");
  if ( !FileMappingW )
    return NtUserPaintDesktop(hdc);
  if ( SendMessageTimeoutWorker(v4, 0x34u, 6u, 4 * v5 * (__int64)v6, 2u, 0xBB8u, (unsigned __int64 *)&h, 0) )
  {
    if ( h )
    {
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v5;
      pbmi.bmiHeader.biHeight = v6;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      v8 = CreateDIBSection(hdc, &pbmi, 0, &ppvBits, FileMappingW, 0);
      if ( v8 )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v10 = CompatibleDC;
        if ( CompatibleDC )
        {
          h = SelectObject(CompatibleDC, v8);
          if ( GetDCOrgEx(hdc, &pt) )
            v1 = BitBlt(hdc, 0, 0, v5, v6, v10, pt.x - Rect.left, pt.y - Rect.top, 0xCC0020u);
          SelectObject(v10, h);
          DeleteDC(v10);
        }
        DeleteObject(v8);
      }
    }
  }
  CloseHandle(FileMappingW);
  if ( !v1 )
    return NtUserPaintDesktop(hdc);
  return v1;
}

```

## disassembly

```asm
0x180089550  push    rbp
0x180089552  push    rbx
0x180089553  push    rsi
0x180089554  push    rdi
0x180089555  push    r12
0x180089557  push    r13
0x180089559  push    r14
0x18008955b  push    r15
0x18008955d  lea     rbp, [rsp-1Fh]
0x180089562  sub     rsp, 0B8h
0x180089569  mov     rax, cs:__security_cookie
0x180089570  xor     rax, rsp
0x180089573  mov     [rbp+57h+var_48], rax
0x180089577  xorps   xmm0, xmm0
0x18008957a  xor     ebx, ebx
0x18008957c  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm0
0x180089580  mov     rsi, rcx
0x180089583  mov     [rbp+57h+ppvBits], rbx
0x180089587  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x18008958b  mov     qword ptr [rbp+57h+pt.x], rbx
0x18008958f  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180089593  mov     [rbp+57h+h], rbx
0x180089597  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSize], xmm0
0x18008959b  call    GetShellWindow
0x1800895a0  mov     rdi, rax
0x1800895a3  test    rax, rax
0x1800895a6  jz      loc_180089726
0x1800895ac  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800895b0  mov     rcx, rax; hWnd
0x1800895b3  call    GetWindowRect
0x1800895b8  test    eax, eax
0x1800895ba  jz      loc_180089726
0x1800895c0  mov     r12d, [rbp+57h+Rect.right]
0x1800895c4  lea     r8d, [rbx+4]; flProtect
0x1800895c8  mov     r13d, [rbp+57h+Rect.bottom]
0x1800895cc  xor     r9d, r9d; dwMaximumSizeHigh
0x1800895cf  sub     r12d, [rbp+57h+Rect.left]
0x1800895d3  xor     edx, edx; lpFileMappingAttributes
0x1800895d5  sub     r13d, [rbp+57h+Rect.top]
0x1800895d9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800895dd  movsxd  rax, r12d
0x1800895e0  movsxd  r14, r13d
0x1800895e3  imul    r14, rax
0x1800895e7  lea     rax, aLocalMicrosoft; "Local\\Microsoft-Windows-DesktopBackgro"...
0x1800895ee  mov     [rsp+0F0h+lpName], rax; lpName
0x1800895f3  shl     r14, 2
0x1800895f7  mov     [rsp+0F0h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x1800895fc  call    cs:__imp_CreateFileMappingW
0x180089602  mov     r15, rax
0x180089605  test    rax, rax
0x180089608  jz      loc_180089726
0x18008960e  mov     [rsp+0F0h+y1], ebx; int
0x180089612  lea     rax, [rbp+57h+h]
0x180089616  mov     qword ptr [rsp+0F0h+x1], rax; unsigned __int64 *
0x18008961b  lea     edx, [rbx+34h]; unsigned int
0x18008961e  mov     dword ptr [rsp+0F0h+lpName], 0BB8h; unsigned int
0x180089626  lea     r8d, [rbx+6]; unsigned __int64
0x18008962a  mov     r9, r14; __int64
0x18008962d  mov     [rsp+0F0h+dwMaximumSizeLow], 2; unsigned int
0x180089635  mov     rcx, rdi; HWND
0x180089638  call    ?SendMessageTimeoutWorker@@YA_JPEAUHWND__@@I_K_JIIPEA_KH@Z; SendMessageTimeoutWorker(HWND__ *,uint,unsigned __int64,__int64,uint,uint,unsigned __int64 *,int)
0x18008963d  test    rax, rax
0x180089640  jz      loc_180089719
0x180089646  cmp     [rbp+57h+h], rbx
0x18008964a  jz      loc_180089719
0x180089650  mov     dword ptr [rsp+0F0h+lpName], ebx; offset
0x180089654  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180089658  xor     r8d, r8d; usage
0x18008965b  mov     qword ptr [rsp+0F0h+dwMaximumSizeLow], r15; hSection
0x180089660  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180089664  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18008966b  mov     rcx, rsi; hdc
0x18008966e  mov     [rbp+57h+pbmi.bmiHeader.biWidth], r12d
0x180089672  mov     [rbp+57h+pbmi.bmiHeader.biHeight], r13d
0x180089676  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18008967e  call    cs:__imp_CreateDIBSection
0x180089684  mov     r14, rax
0x180089687  test    rax, rax
0x18008968a  jz      loc_180089719
0x180089690  xor     ecx, ecx; hdc
0x180089692  call    cs:__imp_CreateCompatibleDC
0x180089698  mov     rdi, rax
0x18008969b  test    rax, rax
0x18008969e  jz      short loc_180089710
0x1800896a0  mov     rdx, r14; h
0x1800896a3  mov     rcx, rax; hdc
0x1800896a6  call    cs:__imp_SelectObject
0x1800896ac  lea     rdx, [rbp+57h+pt]; lppt
0x1800896b0  mov     rcx, rsi; hdc
0x1800896b3  mov     [rbp+57h+h], rax
0x1800896b7  call    cs:__imp_GetDCOrgEx
0x1800896bd  test    eax, eax
0x1800896bf  jz      short loc_1800896FA
0x1800896c1  mov     ecx, [rbp+57h+pt.x]
0x1800896c4  mov     r9d, r12d; cx
0x1800896c7  sub     ecx, [rbp+57h+Rect.left]
0x1800896ca  xor     r8d, r8d; y
0x1800896cd  mov     edx, [rbp+57h+pt.y]
0x1800896d0  sub     edx, [rbp+57h+Rect.top]
0x1800896d3  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1800896db  mov     [rsp+0F0h+y1], edx; y1
0x1800896df  xor     edx, edx; x
0x1800896e1  mov     [rsp+0F0h+x1], ecx; x1
0x1800896e5  mov     rcx, rsi; hdc
0x1800896e8  mov     [rsp+0F0h+lpName], rdi; hdcSrc
0x1800896ed  mov     [rsp+0F0h+dwMaximumSizeLow], r13d; cy
0x1800896f2  call    cs:__imp_BitBlt
0x1800896f8  mov     ebx, eax
0x1800896fa  mov     rdx, [rbp+57h+h]; h
0x1800896fe  mov     rcx, rdi; hdc
0x180089701  call    cs:__imp_SelectObject
0x180089707  mov     rcx, rdi; hdc
0x18008970a  call    cs:__imp_DeleteDC
0x180089710  mov     rcx, r14; ho
0x180089713  call    cs:__imp_DeleteObject
0x180089719  mov     rcx, r15; hObject
0x18008971c  call    cs:__imp_CloseHandle
0x180089722  test    ebx, ebx
0x180089724  jnz     short loc_180089731
0x180089726  mov     rcx, rsi
0x180089729  call    cs:__imp_NtUserPaintDesktop
0x18008972f  mov     ebx, eax
0x180089731  mov     eax, ebx
0x180089733  mov     rcx, [rbp+57h+var_48]
0x180089737  xor     rcx, rsp; StackCookie
0x18008973a  call    __security_check_cookie
0x18008973f  add     rsp, 0B8h
0x180089746  pop     r15
0x180089748  pop     r14
0x18008974a  pop     r13
0x18008974c  pop     r12
0x18008974e  pop     rdi
0x18008974f  pop     rsi
0x180089750  pop     rbx
0x180089751  pop     rbp
0x180089752  retn
```
