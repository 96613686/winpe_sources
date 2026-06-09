# _Create32BitHBITMAP

- ea: `0x18006b26c`
- end: `0x18006b32c`
- name: `_Create32BitHBITMAP`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180063840`

## callees

- `0x18006b26c`
- `0x180091ef0`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x18006b2f0`
- `GDI32!CreateDIBSection` at `0x18006b2f0`
- `USER32!GetDC` at `0x18006b2c3`
- `USER32!GetDC` at `0x18006b2c3`
- `USER32!ReleaseDC` at `0x18006b2fe`
- `USER32!ReleaseDC` at `0x18006b2fe`

## pseudocode

```c
__int64 __fastcall Create32BitHBITMAP(__int64 a1, LONG *a2, __int64 a3, HBITMAP *a4)
{
  LONG v4; // eax
  HDC DC; // rax
  HDC v7; // rdi
  __int64 result; // rax
  BITMAPINFO pbmi; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  v4 = *a2;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  pbmi.bmiHeader.biWidth = v4;
  pbmi.bmiHeader.biHeight = a2[1];
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    *a4 = CreateDIBSection(DC, &pbmi, 0, 0, 0, 0);
    ReleaseDC(0, v7);
  }
  result = 2147942414LL;
  if ( *a4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18006b26c  mov     [rsp+arg_0], rbx
0x18006b271  push    rdi
0x18006b272  sub     rsp, 70h
0x18006b276  mov     rax, cs:__security_cookie
0x18006b27d  xor     rax, rsp
0x18006b280  mov     [rsp+78h+var_18], rax
0x18006b285  xor     eax, eax
0x18006b287  mov     qword ptr [r9], 0
0x18006b28e  xorps   xmm0, xmm0
0x18006b291  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biClrImportant], rax
0x18006b296  mov     eax, [rdx]
0x18006b298  xor     ecx, ecx; hWnd
0x18006b29a  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biWidth], xmm0
0x18006b29f  mov     [rsp+78h+pbmi.bmiHeader.biWidth], eax
0x18006b2a3  mov     rbx, r9
0x18006b2a6  mov     eax, [rdx+4]
0x18006b2a9  mov     [rsp+78h+pbmi.bmiHeader.biHeight], eax
0x18006b2ad  movups  xmmword ptr [rsp+78h+pbmi.bmiHeader.biSizeImage], xmm0
0x18006b2b2  mov     [rsp+78h+pbmi.bmiHeader.biSize], 28h ; '('
0x18006b2ba  mov     qword ptr [rsp+78h+pbmi.bmiHeader.biPlanes], 200001h
0x18006b2c3  call    cs:__imp_GetDC
0x18006b2c9  mov     rdi, rax
0x18006b2cc  test    rax, rax
0x18006b2cf  jz      short loc_18006B304
0x18006b2d1  mov     [rsp+78h+offset], 0; offset
0x18006b2d9  lea     rdx, [rsp+78h+pbmi]; pbmi
0x18006b2de  xor     r9d, r9d; ppvBits
0x18006b2e1  mov     [rsp+78h+hSection], 0; hSection
0x18006b2ea  xor     r8d, r8d; usage
0x18006b2ed  mov     rcx, rax; hdc
0x18006b2f0  call    cs:__imp_CreateDIBSection
0x18006b2f6  mov     rdx, rdi; hDC
0x18006b2f9  xor     ecx, ecx; hWnd
0x18006b2fb  mov     [rbx], rax
0x18006b2fe  call    cs:__imp_ReleaseDC
0x18006b304  xor     ecx, ecx
0x18006b306  mov     eax, 8007000Eh
0x18006b30b  cmp     [rbx], rcx
0x18006b30e  cmovnz  eax, ecx
0x18006b311  mov     rcx, [rsp+78h+var_18]
0x18006b316  xor     rcx, rsp; StackCookie
0x18006b319  call    __security_check_cookie
0x18006b31e  mov     rbx, [rsp+78h+arg_0]
0x18006b326  add     rsp, 70h
0x18006b32a  pop     rdi
0x18006b32b  retn
```
