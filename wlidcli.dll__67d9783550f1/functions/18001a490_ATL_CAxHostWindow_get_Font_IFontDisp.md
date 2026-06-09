# ATL::CAxHostWindow::get_Font(IFontDisp * *)

- ea: `0x18001a490`
- end: `0x18001a67f`
- name: `?get_Font@CAxHostWindow@ATL@@UEAAJPEAPEAUIFontDisp@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, struct IFontDisp **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x18000fa9c`
- `0x180013410`
- `0x18001a490`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18001a62a`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x18001a62a`
- `GDI32!GetDeviceCaps` at `0x18001a5a7`
- `GDI32!GetDeviceCaps` at `0x18001a5ec`
- `GDI32!GetDeviceCaps` at `0x18001a5a7`
- `GDI32!GetDeviceCaps` at `0x18001a5ec`
- `GDI32!GetStockObject` at `0x18001a4f6`
- `GDI32!GetStockObject` at `0x18001a507`
- `GDI32!GetStockObject` at `0x18001a4f6`
- `GDI32!GetStockObject` at `0x18001a507`
- `GDI32!GetObjectW` at `0x18001a537`
- `GDI32!GetObjectW` at `0x18001a537`
- `USER32!GetDC` at `0x18001a592`
- `USER32!GetDC` at `0x18001a5c2`
- `USER32!GetDC` at `0x18001a592`
- `USER32!GetDC` at `0x18001a5c2`
- `USER32!ReleaseDC` at `0x18001a601`
- `USER32!ReleaseDC` at `0x18001a601`
- `USER32!GetDesktopWindow` at `0x18001a5b9`
- `USER32!GetDesktopWindow` at `0x18001a5f5`
- `USER32!GetDesktopWindow` at `0x18001a5b9`
- `USER32!GetDesktopWindow` at `0x18001a5f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAxHostWindow::get_Font(ATL::CAxHostWindow *this, LPVOID *a2)
{
  LPVOID *v5; // rbx
  HGDIOBJ StockObject; // rdi
  int v7; // r12d
  HWND v8; // rcx
  HDC v9; // rax
  HDC v10; // rdi
  int DeviceCaps; // r15d
  HWND v12; // rcx
  HWND DesktopWindow; // rax
  HDC DC; // rax
  unsigned int Error; // ebx
  __int64 v16; // [rsp+20h] [rbp-69h] BYREF
  tagFONTDESC FontDesc; // [rsp+28h] [rbp-61h] BYREF
  _DWORD pv[4]; // [rsp+50h] [rbp-39h] BYREF
  SHORT v19; // [rsp+60h] [rbp-29h]
  unsigned __int8 v20; // [rsp+64h] [rbp-25h]
  unsigned __int8 v21; // [rsp+65h] [rbp-24h]
  unsigned __int8 v22; // [rsp+66h] [rbp-23h]
  unsigned __int8 v23; // [rsp+67h] [rbp-22h]
  char v24; // [rsp+6Ch] [rbp-1Dh] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (LPVOID *)((char *)this + 200);
  if ( *((_QWORD *)this + 25) )
    goto LABEL_15;
  v16 = 0;
  StockObject = GetStockObject(17);
  if ( !StockObject )
  {
    StockObject = GetStockObject(13);
    if ( !StockObject )
      goto LABEL_12;
  }
  memset_0(pv, 0, 0x5Cu);
  GetObjectW(StockObject, 92, pv);
  *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
  FontDesc.cySize.int64 = 0;
  FontDesc.lpstrName = (LPOLESTR)&v24;
  FontDesc.sWeight = v19;
  FontDesc.sCharset = v23;
  FontDesc.fItalic = v20;
  FontDesc.fUnderline = v21;
  FontDesc.fStrikethrough = v22;
  v7 = -pv[0];
  if ( pv[0] > 0 )
    v7 = pv[0];
  v8 = (HWND)*((_QWORD *)this - 18);
  if ( !v8 )
  {
    DesktopWindow = GetDesktopWindow();
    DC = GetDC(DesktopWindow);
    v10 = DC;
    if ( DC )
    {
      DeviceCaps = GetDeviceCaps(DC, 90);
      v12 = GetDesktopWindow();
      goto LABEL_14;
    }
LABEL_12:
    Error = ATL::AtlHresultFromLastError();
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v16);
    return Error;
  }
  v9 = GetDC(v8);
  v10 = v9;
  if ( !v9 )
    goto LABEL_12;
  DeviceCaps = GetDeviceCaps(v9, 90);
  v12 = (HWND)*((_QWORD *)this - 18);
LABEL_14:
  ReleaseDC(v12, v10);
  FontDesc.cySize.int64 = (unsigned int)(720000 * v7 / DeviceCaps);
  OleCreateFontIndirect(&FontDesc, &GUID_bef6e003_a874_101a_8bba_00aa00300cab, v5);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v16);
LABEL_15:
  *a2 = *v5;
  if ( *v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v5 + 8LL))(*v5);
  return 0;
}

```

## disassembly

```asm
0x18001a490  mov     [rsp-8+arg_10], rbx
0x18001a495  mov     [rsp-8+arg_18], rsi
0x18001a49a  push    rbp
0x18001a49b  push    rdi
0x18001a49c  push    r12
0x18001a49e  push    r14
0x18001a4a0  push    r15
0x18001a4a2  lea     rbp, [rsp-37h]
0x18001a4a7  sub     rsp, 0C0h
0x18001a4ae  mov     rax, cs:__security_cookie
0x18001a4b5  xor     rax, rsp
0x18001a4b8  mov     [rbp+57h+var_30], rax
0x18001a4bc  mov     rsi, rdx
0x18001a4bf  mov     r14, rcx
0x18001a4c2  test    rdx, rdx
0x18001a4c5  jnz     short loc_18001A4D1
0x18001a4c7  mov     eax, 80004003h
0x18001a4cc  jmp     loc_18001A657
0x18001a4d1  mov     qword ptr [rdx], 0
0x18001a4d8  lea     rbx, [rcx+0C8h]
0x18001a4df  cmp     qword ptr [rbx], 0
0x18001a4e3  jnz     loc_18001A63A
0x18001a4e9  mov     [rbp+57h+var_C0], 0
0x18001a4f1  mov     ecx, 11h; i
0x18001a4f6  call    cs:__imp_GetStockObject
0x18001a4fc  mov     rdi, rax
0x18001a4ff  test    rax, rax
0x18001a502  jnz     short loc_18001A519
0x18001a504  lea     ecx, [rax+0Dh]; i
0x18001a507  call    cs:__imp_GetStockObject
0x18001a50d  mov     rdi, rax
0x18001a510  test    rax, rax
0x18001a513  jz      loc_18001A5D0
0x18001a519  mov     r15d, 5Ch ; '\'
0x18001a51f  mov     r8d, r15d; Size
0x18001a522  xor     edx, edx; Val
0x18001a524  lea     rcx, [rbp+57h+pv]; void *
0x18001a528  call    memset_0
0x18001a52d  lea     r8, [rbp+57h+pv]; pv
0x18001a531  mov     edx, r15d; c
0x18001a534  mov     rcx, rdi; h
0x18001a537  call    cs:__imp_GetObjectW
0x18001a53d  mov     qword ptr [rbp+57h+FontDesc.cbSizeofstruct], 28h ; '('
0x18001a545  mov     qword ptr [rbp+57h+FontDesc.cySize], 0
0x18001a54d  lea     rax, [rbp+57h+var_74]
0x18001a551  mov     [rbp+57h+FontDesc.lpstrName], rax
0x18001a555  movzx   eax, [rbp+57h+var_80]
0x18001a559  mov     [rbp+57h+FontDesc.sWeight], ax
0x18001a55d  movzx   eax, [rbp+57h+var_79]
0x18001a561  mov     [rbp+57h+FontDesc.sCharset], ax
0x18001a565  movzx   eax, [rbp+57h+var_7C]
0x18001a569  mov     [rbp+57h+FontDesc.fItalic], eax
0x18001a56c  movzx   eax, [rbp+57h+var_7B]
0x18001a570  mov     [rbp+57h+FontDesc.fUnderline], eax
0x18001a573  movzx   eax, [rbp+57h+var_7A]
0x18001a577  mov     [rbp+57h+FontDesc.fStrikethrough], eax
0x18001a57a  mov     r12d, [rbp+57h+pv]
0x18001a57e  neg     r12d
0x18001a581  cmovs   r12d, [rbp+57h+pv]
0x18001a586  mov     rcx, [r14-90h]; hWnd
0x18001a58d  test    rcx, rcx
0x18001a590  jz      short loc_18001A5B9
0x18001a592  call    cs:__imp_GetDC
0x18001a598  mov     rdi, rax
0x18001a59b  test    rax, rax
0x18001a59e  jz      short loc_18001A5D0
0x18001a5a0  lea     edx, [r15-2]; index
0x18001a5a4  mov     rcx, rax; hdc
0x18001a5a7  call    cs:__imp_GetDeviceCaps
0x18001a5ad  mov     r15d, eax
0x18001a5b0  mov     rcx, [r14-90h]
0x18001a5b7  jmp     short loc_18001A5FE
0x18001a5b9  call    cs:__imp_GetDesktopWindow
0x18001a5bf  mov     rcx, rax; hWnd
0x18001a5c2  call    cs:__imp_GetDC
0x18001a5c8  mov     rdi, rax
0x18001a5cb  test    rax, rax
0x18001a5ce  jnz     short loc_18001A5E4
0x18001a5d0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a5d5  mov     ebx, eax
0x18001a5d7  lea     rcx, [rbp+57h+var_C0]
0x18001a5db  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a5e0  mov     eax, ebx
0x18001a5e2  jmp     short loc_18001A657
0x18001a5e4  mov     edx, 5Ah ; 'Z'; index
0x18001a5e9  mov     rcx, rdi; hdc
0x18001a5ec  call    cs:__imp_GetDeviceCaps
0x18001a5f2  mov     r15d, eax
0x18001a5f5  call    cs:__imp_GetDesktopWindow
0x18001a5fb  mov     rcx, rax; hWnd
0x18001a5fe  mov     rdx, rdi; hDC
0x18001a601  call    cs:__imp_ReleaseDC
0x18001a607  imul    eax, r12d, 0AFC80h
0x18001a60e  cdq
0x18001a60f  idiv    r15d
0x18001a612  mov     dword ptr [rbp+57h+FontDesc.cySize], eax
0x18001a615  mov     dword ptr [rbp+57h+FontDesc.cySize+4], 0
0x18001a61c  mov     r8, rbx; lplpvObj
0x18001a61f  lea     rdx, _GUID_bef6e003_a874_101a_8bba_00aa00300cab; riid
0x18001a626  lea     rcx, [rbp+57h+FontDesc]; lpFontDesc
0x18001a62a  call    cs:__imp_OleCreateFontIndirect
0x18001a630  lea     rcx, [rbp+57h+var_C0]
0x18001a634  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a639  nop
0x18001a63a  mov     rax, [rbx]
0x18001a63d  mov     [rsi], rax
0x18001a640  mov     rcx, [rbx]
0x18001a643  test    rcx, rcx
0x18001a646  jz      short loc_18001A655
0x18001a648  mov     rax, [rcx]
0x18001a64b  mov     rax, [rax+8]
0x18001a64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a654  nop
0x18001a655  xor     eax, eax
0x18001a657  mov     rcx, [rbp+57h+var_30]
0x18001a65b  xor     rcx, rsp; StackCookie
0x18001a65e  call    __security_check_cookie
0x18001a663  lea     r11, [rsp+0E0h+var_20]
0x18001a66b  mov     rbx, [r11+40h]
0x18001a66f  mov     rsi, [r11+48h]
0x18001a673  mov     rsp, r11
0x18001a676  pop     r15
0x18001a678  pop     r14
0x18001a67a  pop     r12
0x18001a67c  pop     rdi
0x18001a67d  pop     rbp
0x18001a67e  retn
```
