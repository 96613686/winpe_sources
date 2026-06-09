# Gdiplus::Brush::Clone(void)

- ea: `0x18001dcd0`
- end: `0x18001dd37`
- name: `?Clone@Brush@Gdiplus@@UEBAPEAV12@XZ`
- size: `103`
- prototype: `struct Gdiplus::Brush *__fastcall(Gdiplus::Brush *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001dcd0`

## import_xrefs

- `gdiplus!GdipCloneBrush` at `0x18001dceb`
- `gdiplus!GdipCloneBrush` at `0x18001dceb`
- `gdiplus!GdipAlloc` at `0x18001dcfd`
- `gdiplus!GdipAlloc` at `0x18001dcfd`
- `gdiplus!GdipDeleteBrush` at `0x18001dd26`
- `gdiplus!GdipDeleteBrush` at `0x18001dd26`

## pseudocode

```c
struct Gdiplus::Brush *__fastcall Gdiplus::Brush::Clone(Gdiplus::Brush *this)
{
  int v2; // eax
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  v2 = GdipCloneBrush(*((_QWORD *)this + 1), &v8);
  if ( v2 )
    *((_DWORD *)this + 4) = v2;
  v3 = GdipAlloc(24);
  v4 = v8;
  v5 = v3;
  if ( v3 )
  {
    v6 = *((_DWORD *)this + 4);
    *(_QWORD *)v5 = &Gdiplus::SolidBrush::`vftable';
    *(_DWORD *)(v5 + 16) = v6;
    *(_QWORD *)(v5 + 8) = v4;
  }
  else
  {
    GdipDeleteBrush(v8);
    return 0;
  }
  return (struct Gdiplus::Brush *)v5;
}

```

## disassembly

```asm
0x18001dcd0  push    rbx
0x18001dcd2  sub     rsp, 20h
0x18001dcd6  mov     rbx, rcx
0x18001dcd9  mov     [rsp+28h+arg_0], 0
0x18001dce2  mov     rcx, [rcx+8]
0x18001dce6  lea     rdx, [rsp+28h+arg_0]
0x18001dceb  call    cs:__imp_GdipCloneBrush
0x18001dcf1  test    eax, eax
0x18001dcf3  jz      short loc_18001DCF8
0x18001dcf5  mov     [rbx+10h], eax
0x18001dcf8  mov     ecx, 18h
0x18001dcfd  call    cs:__imp_GdipAlloc
0x18001dd03  mov     rcx, [rsp+28h+arg_0]
0x18001dd08  mov     rdx, rax
0x18001dd0b  test    rax, rax
0x18001dd0e  jz      short loc_18001DD26
0x18001dd10  mov     eax, [rbx+10h]
0x18001dd13  lea     r8, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001dd1a  mov     [rdx], r8
0x18001dd1d  mov     [rdx+10h], eax
0x18001dd20  mov     [rdx+8], rcx
0x18001dd24  jmp     short loc_18001DD2E
0x18001dd26  call    cs:__imp_GdipDeleteBrush
0x18001dd2c  xor     edx, edx
0x18001dd2e  mov     rax, rdx
0x18001dd31  add     rsp, 20h
0x18001dd35  pop     rbx
0x18001dd36  retn
```
