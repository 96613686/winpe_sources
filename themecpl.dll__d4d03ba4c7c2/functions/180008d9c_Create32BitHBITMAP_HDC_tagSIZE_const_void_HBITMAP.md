# Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)

- ea: `0x180008d9c`
- end: `0x180008e7a`
- name: `?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(HDC hDC, const struct tagSIZE *, void **, HBITMAP *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009884`

## callees

- `0x180002280`
- `0x180008d9c`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180008e31`
- `GDI32!CreateDIBSection` at `0x180008e31`
- `USER32!GetDC` at `0x180008dfe`
- `USER32!GetDC` at `0x180008dfe`
- `USER32!ReleaseDC` at `0x180008e4a`
- `USER32!ReleaseDC` at `0x180008e4a`

## pseudocode

```c
__int64 __fastcall Create32BitHBITMAP(HDC hDC, const struct tagSIZE *a2, void **a3, HBITMAP *a4)
{
  HDC DC; // rbx
  __int64 result; // rax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-68h] BYREF

  *a4 = 0;
  *(struct tagSIZE *)&pbmi.bmiHeader.biWidth = *a2;
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  if ( hDC )
  {
    DC = hDC;
  }
  else
  {
    DC = GetDC(0);
    if ( !DC )
      goto LABEL_6;
  }
  *a4 = CreateDIBSection(DC, &pbmi, 0, a3, 0, 0);
  if ( hDC != DC )
    ReleaseDC(0, DC);
LABEL_6:
  result = 2147942414LL;
  if ( *a4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180008d9c  push    rbx
0x180008d9e  push    rbp
0x180008d9f  push    rsi
0x180008da0  push    rdi
0x180008da1  sub     rsp, 78h
0x180008da5  mov     rax, cs:__security_cookie
0x180008dac  xor     rax, rsp
0x180008daf  mov     [rsp+98h+var_38], rax
0x180008db4  mov     qword ptr [r9], 0
0x180008dbb  xorps   xmm0, xmm0
0x180008dbe  mov     eax, [rdx]
0x180008dc0  mov     rsi, r9
0x180008dc3  mov     [rsp+98h+pbmi.bmiHeader.biWidth], eax
0x180008dc7  mov     rbp, r8
0x180008dca  mov     eax, [rdx+4]
0x180008dcd  mov     rdi, rcx
0x180008dd0  mov     [rsp+98h+pbmi.bmiHeader.biHeight], eax
0x180008dd4  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biClrImportant], 0
0x180008ddd  mov     [rsp+98h+pbmi.bmiHeader.biSize], 28h ; '('
0x180008de5  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biPlanes], 200001h
0x180008dee  movdqu  xmmword ptr [rsp+98h+pbmi.bmiHeader.biSizeImage], xmm0
0x180008df4  test    rcx, rcx
0x180008df7  jz      short loc_180008DFE
0x180008df9  mov     rbx, rcx
0x180008dfc  jmp     short loc_180008E12
0x180008dfe  call    cs:__imp_GetDC
0x180008e05  nop     dword ptr [rax+rax+00h]
0x180008e0a  mov     rbx, rax
0x180008e0d  test    rax, rax
0x180008e10  jz      short loc_180008E56
0x180008e12  mov     [rsp+98h+offset], 0; offset
0x180008e1a  lea     rdx, [rsp+98h+pbmi]; pbmi
0x180008e1f  mov     r9, rbp; ppvBits
0x180008e22  mov     [rsp+98h+hSection], 0; hSection
0x180008e2b  xor     r8d, r8d; usage
0x180008e2e  mov     rcx, rbx; hdc
0x180008e31  call    cs:__imp_CreateDIBSection
0x180008e38  nop     dword ptr [rax+rax+00h]
0x180008e3d  mov     [rsi], rax
0x180008e40  cmp     rdi, rbx
0x180008e43  jz      short loc_180008E56
0x180008e45  mov     rdx, rbx; hDC
0x180008e48  xor     ecx, ecx; hWnd
0x180008e4a  call    cs:__imp_ReleaseDC
0x180008e51  nop     dword ptr [rax+rax+00h]
0x180008e56  xor     ecx, ecx
0x180008e58  mov     eax, 8007000Eh
0x180008e5d  cmp     [rsi], rcx
0x180008e60  cmovnz  eax, ecx
0x180008e63  mov     rcx, [rsp+98h+var_38]
0x180008e68  xor     rcx, rsp; StackCookie
0x180008e6b  call    __security_check_cookie
0x180008e70  add     rsp, 78h
0x180008e74  pop     rdi
0x180008e75  pop     rsi
0x180008e76  pop     rbp
0x180008e77  pop     rbx
0x180008e78  retn
```
