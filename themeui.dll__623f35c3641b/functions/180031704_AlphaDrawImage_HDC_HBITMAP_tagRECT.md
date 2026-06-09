# AlphaDrawImage(HDC__ *,HBITMAP__ *,tagRECT *)

- ea: `0x180031704`
- end: `0x180031809`
- name: `?AlphaDrawImage@@YAHPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(HDC hdcDest, HBITMAP h, struct tagRECT *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003394`
- `0x1800579b0`
- `0x180057d5c`
- `0x180057ea4`
- `0x1800581bc`

## callees

- `0x180031704`
- `0x1800358c0`
- `0x18003633c`

## import_xrefs

- `GDI32!GdiAlphaBlend` at `0x1800317c3`
- `GDI32!GdiAlphaBlend` at `0x1800317c3`
- `GDI32!GetObjectW` at `0x180031770`
- `GDI32!GetObjectW` at `0x180031770`
- `GDI32!SelectObject` at `0x18003174c`
- `GDI32!SelectObject` at `0x1800317d1`
- `GDI32!SelectObject` at `0x18003174c`
- `GDI32!SelectObject` at `0x1800317d1`
- `GDI32!CreateCompatibleDC` at `0x180031734`
- `GDI32!CreateCompatibleDC` at `0x180031734`
- `GDI32!DeleteDC` at `0x1800317da`
- `GDI32!DeleteDC` at `0x1800317da`

## pseudocode

```c
__int64 __fastcall AlphaDrawImage(HDC hdcDest, HBITMAP h, struct tagRECT *a3)
{
  unsigned int v6; // edi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rbx
  HGDIOBJ v9; // r14
  _BYTE pv[4]; // [rsp+70h] [rbp-A8h] BYREF
  int wSrc; // [rsp+74h] [rbp-A4h]
  int hSrc; // [rsp+78h] [rbp-A0h]

  v6 = 0;
  CompatibleDC = CreateCompatibleDC(hdcDest);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    v9 = SelectObject(CompatibleDC, h);
    memset_0(pv, 0, 0x68u);
    if ( GetObjectW(h, 104, pv) )
      v6 = GdiAlphaBlend(
             hdcDest,
             a3->left,
             a3->top,
             a3->right - a3->left,
             a3->bottom - a3->top,
             hdcSrc,
             0,
             0,
             wSrc,
             hSrc,
             (BLENDFUNCTION)33488896);
    SelectObject(hdcSrc, v9);
    DeleteDC(hdcSrc);
  }
  return v6;
}

```

## disassembly

```asm
0x180031704  mov     [rsp+arg_18], rbx
0x180031709  push    rbp
0x18003170a  push    rsi
0x18003170b  push    rdi
0x18003170c  push    r14
0x18003170e  push    r15
0x180031710  sub     rsp, 0F0h
0x180031717  mov     rax, cs:__security_cookie
0x18003171e  xor     rax, rsp
0x180031721  mov     [rsp+118h+var_38], rax
0x180031729  mov     rsi, r8
0x18003172c  mov     r15, rdx
0x18003172f  mov     rbp, rcx
0x180031732  xor     edi, edi
0x180031734  call    cs:__imp_CreateCompatibleDC
0x18003173a  mov     rbx, rax
0x18003173d  test    rax, rax
0x180031740  jz      loc_1800317E0
0x180031746  mov     rdx, r15; h
0x180031749  mov     rcx, rax; hdc
0x18003174c  call    cs:__imp_SelectObject
0x180031752  xor     edx, edx; Val
0x180031754  lea     r8d, [rdi+68h]; Size
0x180031758  lea     rcx, [rsp+118h+pv]; void *
0x18003175d  mov     r14, rax
0x180031760  call    memset_0
0x180031765  lea     r8, [rsp+118h+pv]; pv
0x18003176a  mov     rcx, r15; h
0x18003176d  lea     edx, [rdi+68h]; c
0x180031770  call    cs:__imp_GetObjectW
0x180031776  test    eax, eax
0x180031778  jz      short loc_1800317CB
0x18003177a  mov     r10d, [rsi+0Ch]
0x18003177e  mov     rcx, rbp; hdcDest
0x180031781  mov     r8d, [rsi+4]; yoriginDest
0x180031785  sub     r10d, r8d
0x180031788  mov     r9d, [rsi+8]
0x18003178c  sub     r9d, [rsi]; wDest
0x18003178f  mov     edx, [rsi]; xoriginDest
0x180031791  mov     dword ptr [rsp+118h+var_B8.BlendOp], 1FF0000h
0x180031799  mov     eax, dword ptr [rsp+118h+var_B8.BlendOp]
0x18003179d  mov     dword ptr [rsp+118h+ftn.BlendOp], eax; ftn
0x1800317a1  mov     eax, [rsp+118h+var_A0]
0x1800317a5  mov     [rsp+118h+hSrc], eax; hSrc
0x1800317a9  mov     eax, [rsp+118h+var_A4]
0x1800317ad  mov     [rsp+118h+wSrc], eax; wSrc
0x1800317b1  mov     [rsp+118h+yoriginSrc], edi; yoriginSrc
0x1800317b5  mov     [rsp+118h+xoriginSrc], edi; xoriginSrc
0x1800317b9  mov     [rsp+118h+hdcSrc], rbx; hdcSrc
0x1800317be  mov     [rsp+118h+hDest], r10d; hDest
0x1800317c3  call    cs:__imp_GdiAlphaBlend
0x1800317c9  mov     edi, eax
0x1800317cb  mov     rdx, r14; h
0x1800317ce  mov     rcx, rbx; hdc
0x1800317d1  call    cs:__imp_SelectObject
0x1800317d7  mov     rcx, rbx; hdc
0x1800317da  call    cs:__imp_DeleteDC
0x1800317e0  mov     eax, edi
0x1800317e2  mov     rcx, [rsp+118h+var_38]
0x1800317ea  xor     rcx, rsp; StackCookie
0x1800317ed  call    __security_check_cookie
0x1800317f2  mov     rbx, [rsp+118h+arg_18]
0x1800317fa  add     rsp, 0F0h
0x180031801  pop     r15
0x180031803  pop     r14
0x180031805  pop     rdi
0x180031806  pop     rsi
0x180031807  pop     rbp
0x180031808  retn
```
