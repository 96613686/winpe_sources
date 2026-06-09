# Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)

- ea: `0x18002203c`
- end: `0x180022107`
- name: `?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(HDC hDC, const struct tagSIZE *, void **, HBITMAP *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180042ffc`
- `0x180057bf0`

## callees

- `0x18002203c`
- `0x1800358c0`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x1800220cb`
- `GDI32!CreateDIBSection` at `0x1800220cb`
- `USER32!ReleaseDC` at `0x1800220de`
- `USER32!ReleaseDC` at `0x1800220de`
- `USER32!GetDC` at `0x18002209e`
- `USER32!GetDC` at `0x18002209e`

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
0x18002203c  push    rbx
0x18002203e  push    rbp
0x18002203f  push    rsi
0x180022040  push    rdi
0x180022041  sub     rsp, 78h
0x180022045  mov     rax, cs:__security_cookie
0x18002204c  xor     rax, rsp
0x18002204f  mov     [rsp+98h+var_38], rax
0x180022054  mov     qword ptr [r9], 0
0x18002205b  xorps   xmm0, xmm0
0x18002205e  mov     eax, [rdx]
0x180022060  mov     rsi, r9
0x180022063  mov     [rsp+98h+pbmi.bmiHeader.biWidth], eax
0x180022067  mov     rbp, r8
0x18002206a  mov     eax, [rdx+4]
0x18002206d  mov     rdi, rcx
0x180022070  mov     [rsp+98h+pbmi.bmiHeader.biHeight], eax
0x180022074  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biClrImportant], 0
0x18002207d  mov     [rsp+98h+pbmi.bmiHeader.biSize], 28h ; '('
0x180022085  mov     qword ptr [rsp+98h+pbmi.bmiHeader.biPlanes], 200001h
0x18002208e  movdqu  xmmword ptr [rsp+98h+pbmi.bmiHeader.biSizeImage], xmm0
0x180022094  test    rcx, rcx
0x180022097  jz      short loc_18002209E
0x180022099  mov     rbx, rcx
0x18002209c  jmp     short loc_1800220AC
0x18002209e  call    cs:__imp_GetDC
0x1800220a4  mov     rbx, rax
0x1800220a7  test    rax, rax
0x1800220aa  jz      short loc_1800220E4
0x1800220ac  mov     [rsp+98h+offset], 0; offset
0x1800220b4  lea     rdx, [rsp+98h+pbmi]; pbmi
0x1800220b9  mov     r9, rbp; ppvBits
0x1800220bc  mov     [rsp+98h+hSection], 0; hSection
0x1800220c5  xor     r8d, r8d; usage
0x1800220c8  mov     rcx, rbx; hdc
0x1800220cb  call    cs:__imp_CreateDIBSection
0x1800220d1  mov     [rsi], rax
0x1800220d4  cmp     rdi, rbx
0x1800220d7  jz      short loc_1800220E4
0x1800220d9  mov     rdx, rbx; hDC
0x1800220dc  xor     ecx, ecx; hWnd
0x1800220de  call    cs:__imp_ReleaseDC
0x1800220e4  xor     ecx, ecx
0x1800220e6  mov     eax, 8007000Eh
0x1800220eb  cmp     [rsi], rcx
0x1800220ee  cmovnz  eax, ecx
0x1800220f1  mov     rcx, [rsp+98h+var_38]
0x1800220f6  xor     rcx, rsp; StackCookie
0x1800220f9  call    __security_check_cookie
0x1800220fe  add     rsp, 78h
0x180022102  pop     rdi
0x180022103  pop     rsi
0x180022104  pop     rbp
0x180022105  pop     rbx
0x180022106  retn
```
