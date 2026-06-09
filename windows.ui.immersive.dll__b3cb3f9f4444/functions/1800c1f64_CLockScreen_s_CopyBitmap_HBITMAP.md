# CLockScreen::_s_CopyBitmap(HBITMAP__ *)

- ea: `0x1800c1f64`
- end: `0x1800c20d8`
- name: `?_s_CopyBitmap@CLockScreen@@KAPEAUHBITMAP__@@PEAU2@@Z`
- size: `372`
- prototype: `HBITMAP __fastcall(HBITMAP h)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c2670`

## callees

- `0x1800b63c0`
- `0x1800c1f64`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800c1f82`
- `GDI32!CreateCompatibleDC` at `0x1800c1fba`
- `GDI32!CreateCompatibleDC` at `0x1800c1f82`
- `GDI32!CreateCompatibleDC` at `0x1800c1fba`
- `GDI32!DeleteDC` at `0x1800c2093`
- `GDI32!DeleteDC` at `0x1800c20b4`
- `GDI32!DeleteDC` at `0x1800c2093`
- `GDI32!DeleteDC` at `0x1800c20b4`
- `GDI32!SelectObject` at `0x1800c1fa0`
- `GDI32!SelectObject` at `0x1800c202e`
- `GDI32!SelectObject` at `0x1800c2084`
- `GDI32!SelectObject` at `0x1800c20a5`
- `GDI32!SelectObject` at `0x1800c1fa0`
- `GDI32!SelectObject` at `0x1800c202e`
- `GDI32!SelectObject` at `0x1800c2084`
- `GDI32!SelectObject` at `0x1800c20a5`
- `GDI32!GetObjectW` at `0x1800c1fe7`
- `GDI32!GetObjectW` at `0x1800c1fe7`
- `GDI32!BitBlt` at `0x1800c2072`
- `GDI32!BitBlt` at `0x1800c2072`

## pseudocode

```c
HGDIOBJ __fastcall CLockScreen::_s_CopyBitmap(HBITMAP h)
{
  HGDIOBJ v2; // rbx
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v5; // r15
  HDC v6; // rsi
  int v7; // eax
  HGDIOBJ v8; // r14
  _OWORD pv[2]; // [rsp+50h] [rbp-20h] BYREF
  HGDIOBJ ha; // [rsp+A8h] [rbp+38h] BYREF
  tagSIZE v12; // [rsp+B0h] [rbp+40h] BYREF
  void *v13; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  ha = 0;
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v5 = SelectObject(CompatibleDC, h);
    if ( v5 )
    {
      v6 = CreateCompatibleDC(0);
      if ( v6 )
      {
        memset(pv, 0, sizeof(pv));
        if ( GetObjectW(h, 32, pv) == 32 )
        {
          v12 = *(tagSIZE *)((char *)pv + 4);
          v13 = 0;
          v7 = Create32BitHBITMAP(v6, &v12, &v13, (HBITMAP *)&ha);
          v2 = ha;
          if ( v7 >= 0 )
          {
            v8 = SelectObject(v6, ha);
            if ( v8 )
            {
              BitBlt(v6, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
              SelectObject(v6, v8);
            }
          }
        }
        DeleteDC(v6);
      }
      SelectObject(hdcSrc, v5);
    }
    DeleteDC(hdcSrc);
  }
  return v2;
}

```

## disassembly

```asm
0x1800c1f64  mov     [rsp-28h+arg_0], rbx
0x1800c1f69  push    rbp
0x1800c1f6a  push    rsi
0x1800c1f6b  push    rdi
0x1800c1f6c  push    r14
0x1800c1f6e  push    r15
0x1800c1f70  mov     rbp, rsp
0x1800c1f73  sub     rsp, 70h
0x1800c1f77  mov     r14, rcx
0x1800c1f7a  xor     ebx, ebx
0x1800c1f7c  xor     ecx, ecx; hdc
0x1800c1f7e  mov     [rbp+h], rbx
0x1800c1f82  call    cs:__imp_CreateCompatibleDC
0x1800c1f89  nop     dword ptr [rax+rax+00h]
0x1800c1f8e  mov     rdi, rax
0x1800c1f91  test    rax, rax
0x1800c1f94  jz      loc_1800C20C0
0x1800c1f9a  mov     rdx, r14; h
0x1800c1f9d  mov     rcx, rax; hdc
0x1800c1fa0  call    cs:__imp_SelectObject
0x1800c1fa7  nop     dword ptr [rax+rax+00h]
0x1800c1fac  mov     r15, rax
0x1800c1faf  test    rax, rax
0x1800c1fb2  jz      loc_1800C20B1
0x1800c1fb8  xor     ecx, ecx; hdc
0x1800c1fba  call    cs:__imp_CreateCompatibleDC
0x1800c1fc1  nop     dword ptr [rax+rax+00h]
0x1800c1fc6  mov     rsi, rax
0x1800c1fc9  test    rax, rax
0x1800c1fcc  jz      loc_1800C209F
0x1800c1fd2  xorps   xmm0, xmm0
0x1800c1fd5  lea     r8, [rbp+pv]; pv
0x1800c1fd9  lea     edx, [rbx+20h]; c
0x1800c1fdc  mov     rcx, r14; h
0x1800c1fdf  movups  [rbp+pv], xmm0
0x1800c1fe3  movups  [rbp+var_10], xmm0
0x1800c1fe7  call    cs:__imp_GetObjectW
0x1800c1fee  nop     dword ptr [rax+rax+00h]
0x1800c1ff3  cmp     eax, 20h ; ' '
0x1800c1ff6  jnz     loc_1800C2090
0x1800c1ffc  mov     eax, dword ptr [rbp+pv+4]
0x1800c1fff  lea     r9, [rbp+h]; HBITMAP *
0x1800c2003  mov     [rbp+arg_10.cx], eax
0x1800c2006  lea     r8, [rbp+arg_18]; void **
0x1800c200a  mov     eax, dword ptr [rbp+pv+8]
0x1800c200d  lea     rdx, [rbp+arg_10]; struct tagSIZE *
0x1800c2011  mov     rcx, rsi; hDC
0x1800c2014  mov     [rbp+arg_10.cy], eax
0x1800c2017  mov     [rbp+arg_18], rbx
0x1800c201b  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1800c2020  mov     rbx, [rbp+h]
0x1800c2024  test    eax, eax
0x1800c2026  js      short loc_1800C2090
0x1800c2028  mov     rdx, rbx; h
0x1800c202b  mov     rcx, rsi; hdc
0x1800c202e  call    cs:__imp_SelectObject
0x1800c2035  nop     dword ptr [rax+rax+00h]
0x1800c203a  mov     r14, rax
0x1800c203d  test    rax, rax
0x1800c2040  jz      short loc_1800C2090
0x1800c2042  mov     eax, dword ptr [rbp+pv+8]
0x1800c2045  xor     r8d, r8d; y
0x1800c2048  mov     r9d, dword ptr [rbp+pv+4]; cx
0x1800c204c  xor     edx, edx; x
0x1800c204e  mov     [rsp+70h+rop], 0CC0020h; rop
0x1800c2056  mov     rcx, rsi; hdc
0x1800c2059  mov     [rsp+70h+y1], 0; y1
0x1800c2061  mov     [rsp+70h+x1], 0; x1
0x1800c2069  mov     [rsp+70h+hdcSrc], rdi; hdcSrc
0x1800c206e  mov     [rsp+70h+cy], eax; cy
0x1800c2072  call    cs:__imp_BitBlt
0x1800c2079  nop     dword ptr [rax+rax+00h]
0x1800c207e  mov     rdx, r14; h
0x1800c2081  mov     rcx, rsi; hdc
0x1800c2084  call    cs:__imp_SelectObject
0x1800c208b  nop     dword ptr [rax+rax+00h]
0x1800c2090  mov     rcx, rsi; hdc
0x1800c2093  call    cs:__imp_DeleteDC
0x1800c209a  nop     dword ptr [rax+rax+00h]
0x1800c209f  mov     rdx, r15; h
0x1800c20a2  mov     rcx, rdi; hdc
0x1800c20a5  call    cs:__imp_SelectObject
0x1800c20ac  nop     dword ptr [rax+rax+00h]
0x1800c20b1  mov     rcx, rdi; hdc
0x1800c20b4  call    cs:__imp_DeleteDC
0x1800c20bb  nop     dword ptr [rax+rax+00h]
0x1800c20c0  mov     rax, rbx
0x1800c20c3  mov     rbx, [rsp+70h+arg_0]
0x1800c20cb  add     rsp, 70h
0x1800c20cf  pop     r15
0x1800c20d1  pop     r14
0x1800c20d3  pop     rdi
0x1800c20d4  pop     rsi
0x1800c20d5  pop     rbp
0x1800c20d6  retn
```
