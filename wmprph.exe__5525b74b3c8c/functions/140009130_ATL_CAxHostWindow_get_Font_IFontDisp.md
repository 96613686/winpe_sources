# ATL::CAxHostWindow::get_Font(IFontDisp * *)

- ea: `0x140009130`
- end: `0x1400092db`
- name: `?get_Font@CAxHostWindow@ATL@@UEAAJPEAPEAUIFontDisp@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, struct IFontDisp **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001390`
- `0x140001d26`
- `0x140009130`
- `0x14000f010`

## import_xrefs

- `GDI32!GetStockObject` at `0x140009178`
- `GDI32!GetStockObject` at `0x140009189`
- `GDI32!GetStockObject` at `0x140009178`
- `GDI32!GetStockObject` at `0x140009189`
- `GDI32!GetDeviceCaps` at `0x14000921b`
- `GDI32!GetDeviceCaps` at `0x140009247`
- `GDI32!GetDeviceCaps` at `0x14000921b`
- `GDI32!GetDeviceCaps` at `0x140009247`
- `GDI32!GetObjectW` at `0x1400091b0`
- `GDI32!GetObjectW` at `0x1400091b0`
- `USER32!ReleaseDC` at `0x14000925c`
- `USER32!ReleaseDC` at `0x14000925c`
- `USER32!GetDC` at `0x14000920b`
- `USER32!GetDC` at `0x140009236`
- `USER32!GetDC` at `0x14000920b`
- `USER32!GetDC` at `0x140009236`
- `USER32!GetDesktopWindow` at `0x14000922d`
- `USER32!GetDesktopWindow` at `0x140009250`
- `USER32!GetDesktopWindow` at `0x14000922d`
- `USER32!GetDesktopWindow` at `0x140009250`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140009285`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140009285`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::get_Font(ATL::CAxHostWindow *this, LPVOID *a2)
{
  LPVOID *v2; // rdi
  HGDIOBJ StockObject; // rbx
  HWND v6; // rcx
  int v7; // r12d
  HDC DC; // rbx
  int DeviceCaps; // eax
  HWND v10; // rcx
  int v11; // r15d
  HWND DesktopWindow; // rax
  tagFONTDESC FontDesc; // [rsp+20h] [rbp-69h] BYREF
  _DWORD pv[4]; // [rsp+50h] [rbp-39h] BYREF
  SHORT v16; // [rsp+60h] [rbp-29h]
  unsigned __int8 v17; // [rsp+64h] [rbp-25h]
  unsigned __int8 v18; // [rsp+65h] [rbp-24h]
  unsigned __int8 v19; // [rsp+66h] [rbp-23h]
  unsigned __int8 v20; // [rsp+67h] [rbp-22h]
  char v21; // [rsp+6Ch] [rbp-1Dh] BYREF

  v2 = (LPVOID *)((char *)this + 168);
  if ( !*((_QWORD *)this + 21) )
  {
    StockObject = GetStockObject(17);
    if ( !StockObject )
      StockObject = GetStockObject(13);
    memset_0(pv, 0, 0x5Cu);
    GetObjectW(StockObject, 92, pv);
    v6 = (HWND)*((_QWORD *)this - 17);
    v7 = -pv[0];
    FontDesc.lpstrName = (LPOLESTR)&v21;
    if ( pv[0] > 0 )
      v7 = pv[0];
    FontDesc.sWeight = v16;
    FontDesc.sCharset = v20;
    FontDesc.fItalic = v17;
    FontDesc.fUnderline = v18;
    FontDesc.fStrikethrough = v19;
    *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
    FontDesc.cySize.int64 = 0;
    if ( v6 )
    {
      DC = GetDC(v6);
      DeviceCaps = GetDeviceCaps(DC, 90);
      v10 = (HWND)*((_QWORD *)this - 17);
      v11 = DeviceCaps;
    }
    else
    {
      DesktopWindow = GetDesktopWindow();
      DC = GetDC(DesktopWindow);
      v11 = GetDeviceCaps(DC, 90);
      v10 = GetDesktopWindow();
    }
    ReleaseDC(v10, DC);
    FontDesc.cySize.int64 = (unsigned int)(720000 * v7 / v11);
    OleCreateFontIndirect(&FontDesc, &IID_IFontDisp, v2);
  }
  if ( !a2 )
    return 2147500035LL;
  *a2 = *v2;
  if ( *v2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v2 + 8LL))(*v2);
  return 0;
}

```

## disassembly

```asm
0x140009130  mov     [rsp-8+arg_10], rbx
0x140009135  mov     [rsp-8+arg_18], rsi
0x14000913a  push    rbp
0x14000913b  push    rdi
0x14000913c  push    r12
0x14000913e  push    r14
0x140009140  push    r15
0x140009142  lea     rbp, [rsp-37h]
0x140009147  sub     rsp, 0C0h
0x14000914e  mov     rax, cs:__security_cookie
0x140009155  xor     rax, rsp
0x140009158  mov     [rbp+57h+var_30], rax
0x14000915c  lea     rdi, [rcx+0A8h]
0x140009163  mov     rsi, rdx
0x140009166  cmp     qword ptr [rdi], 0
0x14000916a  mov     r14, rcx
0x14000916d  jnz     loc_14000928B
0x140009173  mov     ecx, 11h; i
0x140009178  call    cs:__imp_GetStockObject
0x14000917e  mov     rbx, rax
0x140009181  test    rax, rax
0x140009184  jnz     short loc_140009192
0x140009186  lea     ecx, [rax+0Dh]; i
0x140009189  call    cs:__imp_GetStockObject
0x14000918f  mov     rbx, rax
0x140009192  mov     r15d, 5Ch ; '\'
0x140009198  lea     rcx, [rbp+57h+pv]; void *
0x14000919c  mov     r8d, r15d; Size
0x14000919f  xor     edx, edx; Val
0x1400091a1  call    memset_0
0x1400091a6  lea     r8, [rbp+57h+pv]; pv
0x1400091aa  mov     edx, r15d; c
0x1400091ad  mov     rcx, rbx; h
0x1400091b0  call    cs:__imp_GetObjectW
0x1400091b6  mov     r12d, [rbp+57h+pv]
0x1400091ba  lea     rax, [rbp+57h+var_74]
0x1400091be  mov     rcx, [r14-88h]; hWnd
0x1400091c5  neg     r12d
0x1400091c8  mov     [rbp+57h+FontDesc.lpstrName], rax
0x1400091cc  movzx   eax, [rbp+57h+var_80]
0x1400091d0  cmovs   r12d, [rbp+57h+pv]
0x1400091d5  mov     [rbp+57h+FontDesc.sWeight], ax
0x1400091d9  movzx   eax, [rbp+57h+var_79]
0x1400091dd  mov     [rbp+57h+FontDesc.sCharset], ax
0x1400091e1  movzx   eax, [rbp+57h+var_7C]
0x1400091e5  mov     [rbp+57h+FontDesc.fItalic], eax
0x1400091e8  movzx   eax, [rbp+57h+var_7B]
0x1400091ec  mov     [rbp+57h+FontDesc.fUnderline], eax
0x1400091ef  movzx   eax, [rbp+57h+var_7A]
0x1400091f3  mov     [rbp+57h+FontDesc.fStrikethrough], eax
0x1400091f6  mov     qword ptr [rbp+57h+FontDesc.cbSizeofstruct], 28h ; '('
0x1400091fe  mov     qword ptr [rbp+57h+FontDesc.cySize], 0
0x140009206  test    rcx, rcx
0x140009209  jz      short loc_14000922D
0x14000920b  call    cs:__imp_GetDC
0x140009211  mov     rcx, rax; hdc
0x140009214  lea     edx, [r15-2]; index
0x140009218  mov     rbx, rax
0x14000921b  call    cs:__imp_GetDeviceCaps
0x140009221  mov     rcx, [r14-88h]
0x140009228  mov     r15d, eax
0x14000922b  jmp     short loc_140009259
0x14000922d  call    cs:__imp_GetDesktopWindow
0x140009233  mov     rcx, rax; hWnd
0x140009236  call    cs:__imp_GetDC
0x14000923c  mov     rcx, rax; hdc
0x14000923f  mov     edx, 5Ah ; 'Z'; index
0x140009244  mov     rbx, rax
0x140009247  call    cs:__imp_GetDeviceCaps
0x14000924d  mov     r15d, eax
0x140009250  call    cs:__imp_GetDesktopWindow
0x140009256  mov     rcx, rax; hWnd
0x140009259  mov     rdx, rbx; hDC
0x14000925c  call    cs:__imp_ReleaseDC
0x140009262  imul    eax, r12d, 0AFC80h
0x140009269  lea     rcx, [rbp+57h+FontDesc]; lpFontDesc
0x14000926d  mov     r8, rdi; lplpvObj
0x140009270  mov     dword ptr [rbp+57h+FontDesc.cySize+4], 0
0x140009277  cdq
0x140009278  idiv    r15d
0x14000927b  lea     rdx, IID_IFontDisp; riid
0x140009282  mov     dword ptr [rbp+57h+FontDesc.cySize], eax
0x140009285  call    cs:__imp_OleCreateFontIndirect
0x14000928b  test    rsi, rsi
0x14000928e  jnz     short loc_140009297
0x140009290  mov     eax, 80004003h
0x140009295  jmp     short loc_1400092B3
0x140009297  mov     rax, [rdi]
0x14000929a  mov     [rsi], rax
0x14000929d  mov     rcx, [rdi]
0x1400092a0  test    rcx, rcx
0x1400092a3  jz      short loc_1400092B1
0x1400092a5  mov     rax, [rcx]
0x1400092a8  mov     rax, [rax+8]
0x1400092ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092b1  xor     eax, eax
0x1400092b3  mov     rcx, [rbp+57h+var_30]
0x1400092b7  xor     rcx, rsp; StackCookie
0x1400092ba  call    __security_check_cookie
0x1400092bf  lea     r11, [rsp+0E0h+var_20]
0x1400092c7  mov     rbx, [r11+40h]
0x1400092cb  mov     rsi, [r11+48h]
0x1400092cf  mov     rsp, r11
0x1400092d2  pop     r15
0x1400092d4  pop     r14
0x1400092d6  pop     r12
0x1400092d8  pop     rdi
0x1400092d9  pop     rbp
0x1400092da  retn
```
