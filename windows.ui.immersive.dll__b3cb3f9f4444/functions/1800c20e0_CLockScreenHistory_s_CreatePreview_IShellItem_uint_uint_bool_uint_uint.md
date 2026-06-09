# CLockScreenHistory::_s_CreatePreview(IShellItem *,uint,uint,bool,uint,uint)

- ea: `0x1800c20e0`
- end: `0x1800c21ea`
- name: `?_s_CreatePreview@CLockScreenHistory@@KAPEAUHBITMAP__@@PEAUIShellItem@@II_NII@Z`
- size: `266`
- prototype: `HBITMAP __fastcall(struct IShellItem *, unsigned int, unsigned int, bool, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800c04ac`

## callees

- `0x1800b63c0`
- `0x1800b7344`
- `0x1800c20e0`
- `0x1800c21f0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800c2106`
- `GDI32!CreateCompatibleDC` at `0x1800c2106`
- `GDI32!DeleteDC` at `0x1800c21cb`
- `GDI32!DeleteDC` at `0x1800c21cb`
- `GDI32!SelectObject` at `0x1800c217d`
- `GDI32!SelectObject` at `0x1800c21ac`
- `GDI32!SelectObject` at `0x1800c217d`
- `GDI32!SelectObject` at `0x1800c21ac`
- `GDI32!DeleteObject` at `0x1800c21bc`
- `GDI32!DeleteObject` at `0x1800c21bc`

## pseudocode

```c
HGDIOBJ __fastcall CLockScreenHistory::_s_CreatePreview(
        struct IShellItem *a1,
        unsigned int a2,
        unsigned int a3,
        bool a4,
        unsigned int a5,
        unsigned int a6)
{
  HGDIOBJ v7; // rsi
  HDC CompatibleDC; // rdi
  int v12; // eax
  HGDIOBJ v13; // rbx
  HGDIOBJ ho; // [rsp+40h] [rbp-20h] BYREF
  struct tagSIZE v16; // [rsp+48h] [rbp-18h] BYREF
  HGDIOBJ h; // [rsp+50h] [rbp-10h] BYREF
  void *v18; // [rsp+58h] [rbp-8h] BYREF

  v7 = 0;
  h = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    ho = 0;
    GetBitmapFromShellItem(a1, a2, a3, a5, a6, 1, (HBITMAP *)&ho);
    if ( ho )
    {
      v16.cx = a2;
      v16.cy = a3;
      v18 = 0;
      v12 = Create32BitHBITMAP(CompatibleDC, &v16, &v18, (HBITMAP *)&h);
      v7 = h;
      if ( v12 >= 0 )
      {
        v13 = SelectObject(CompatibleDC, h);
        CLockScreenHistory::_s_DrawImage(CompatibleDC, a2, a3, a4, (HBITMAP)ho);
        SelectObject(CompatibleDC, v13);
      }
      DeleteObject(ho);
    }
    DeleteDC(CompatibleDC);
  }
  return v7;
}

```

## disassembly

```asm
0x1800c20e0  push    rbp
0x1800c20e2  push    rbx
0x1800c20e3  push    rsi
0x1800c20e4  push    rdi
0x1800c20e5  push    r12
0x1800c20e7  push    r14
0x1800c20e9  push    r15
0x1800c20eb  mov     rbp, rsp
0x1800c20ee  sub     rsp, 60h
0x1800c20f2  mov     rbx, rcx
0x1800c20f5  xor     esi, esi
0x1800c20f7  xor     ecx, ecx; hdc
0x1800c20f9  mov     [rbp+h], rsi
0x1800c20fd  mov     r12b, r9b
0x1800c2100  mov     r14d, r8d
0x1800c2103  mov     r15d, edx
0x1800c2106  call    cs:__imp_CreateCompatibleDC
0x1800c210d  nop     dword ptr [rax+rax+00h]
0x1800c2112  mov     rdi, rax
0x1800c2115  test    rax, rax
0x1800c2118  jz      loc_1800C21D7
0x1800c211e  mov     r9d, [rbp+arg_20]; unsigned int
0x1800c2122  lea     rax, [rbp+ho]
0x1800c2126  mov     [rsp+60h+var_30], rax; HBITMAP *
0x1800c212b  mov     r8d, r14d; unsigned int
0x1800c212e  mov     eax, [rbp+arg_28]
0x1800c2131  mov     edx, r15d; unsigned int
0x1800c2134  mov     [rsp+60h+var_38], 1; bool
0x1800c2139  mov     rcx, rbx; struct IShellItem *
0x1800c213c  mov     dword ptr [rsp+60h+var_40], eax; unsigned int
0x1800c2140  mov     [rbp+ho], rsi
0x1800c2144  call    ?GetBitmapFromShellItem@@YAXPEAUIShellItem@@IIII_NPEAPEAUHBITMAP__@@@Z; GetBitmapFromShellItem(IShellItem *,uint,uint,uint,uint,bool,HBITMAP__ * *)
0x1800c2149  cmp     [rbp+ho], rsi
0x1800c214d  jz      short loc_1800C21C8
0x1800c214f  lea     r9, [rbp+h]; HBITMAP *
0x1800c2153  mov     [rbp+var_18.cx], r15d
0x1800c2157  lea     r8, [rbp+var_8]; void **
0x1800c215b  mov     [rbp+var_18.cy], r14d
0x1800c215f  lea     rdx, [rbp+var_18]; struct tagSIZE *
0x1800c2163  mov     [rbp+var_8], rsi
0x1800c2167  mov     rcx, rdi; hDC
0x1800c216a  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1800c216f  mov     rsi, [rbp+h]
0x1800c2173  test    eax, eax
0x1800c2175  js      short loc_1800C21B8
0x1800c2177  mov     rdx, rsi; h
0x1800c217a  mov     rcx, rdi; hdc
0x1800c217d  call    cs:__imp_SelectObject
0x1800c2184  nop     dword ptr [rax+rax+00h]
0x1800c2189  mov     r9b, r12b; bool
0x1800c218c  mov     r8d, r14d; hSrc
0x1800c218f  mov     rbx, rax
0x1800c2192  mov     edx, r15d; wDest
0x1800c2195  mov     rax, [rbp+ho]
0x1800c2199  mov     rcx, rdi; hdcDest
0x1800c219c  mov     [rsp+60h+var_40], rax; HBITMAP
0x1800c21a1  call    ?_s_DrawImage@CLockScreenHistory@@KAXPEAUHDC__@@II_NPEAUHBITMAP__@@@Z; CLockScreenHistory::_s_DrawImage(HDC__ *,uint,uint,bool,HBITMAP__ *)
0x1800c21a6  mov     rdx, rbx; h
0x1800c21a9  mov     rcx, rdi; hdc
0x1800c21ac  call    cs:__imp_SelectObject
0x1800c21b3  nop     dword ptr [rax+rax+00h]
0x1800c21b8  mov     rcx, [rbp+ho]; ho
0x1800c21bc  call    cs:__imp_DeleteObject
0x1800c21c3  nop     dword ptr [rax+rax+00h]
0x1800c21c8  mov     rcx, rdi; hdc
0x1800c21cb  call    cs:__imp_DeleteDC
0x1800c21d2  nop     dword ptr [rax+rax+00h]
0x1800c21d7  mov     rax, rsi
0x1800c21da  add     rsp, 60h
0x1800c21de  pop     r15
0x1800c21e0  pop     r14
0x1800c21e2  pop     r12
0x1800c21e4  pop     rdi
0x1800c21e5  pop     rsi
0x1800c21e6  pop     rbx
0x1800c21e7  pop     rbp
0x1800c21e8  retn
```
