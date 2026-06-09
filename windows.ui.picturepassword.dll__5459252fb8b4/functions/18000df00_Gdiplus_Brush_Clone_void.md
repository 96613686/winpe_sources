# Gdiplus::Brush::Clone(void)

- ea: `0x18000df00`
- end: `0x18000df67`
- name: `?Clone@Brush@Gdiplus@@UEBAPEAV12@XZ`
- size: `103`
- prototype: `struct Gdiplus::Brush *__fastcall(Gdiplus::Brush *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000df00`

## import_xrefs

- `gdiplus!GdipAlloc` at `0x18000df2d`
- `gdiplus!GdipAlloc` at `0x18000df2d`
- `gdiplus!GdipDeleteBrush` at `0x18000df56`
- `gdiplus!GdipDeleteBrush` at `0x18000df56`
- `gdiplus!GdipCloneBrush` at `0x18000df1b`
- `gdiplus!GdipCloneBrush` at `0x18000df1b`

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
0x18000df00  push    rbx
0x18000df02  sub     rsp, 20h
0x18000df06  mov     rbx, rcx
0x18000df09  mov     [rsp+28h+arg_0], 0
0x18000df12  mov     rcx, [rcx+8]
0x18000df16  lea     rdx, [rsp+28h+arg_0]
0x18000df1b  call    cs:__imp_GdipCloneBrush
0x18000df21  test    eax, eax
0x18000df23  jz      short loc_18000DF28
0x18000df25  mov     [rbx+10h], eax
0x18000df28  mov     ecx, 18h
0x18000df2d  call    cs:__imp_GdipAlloc
0x18000df33  mov     rcx, [rsp+28h+arg_0]
0x18000df38  mov     rdx, rax
0x18000df3b  test    rax, rax
0x18000df3e  jz      short loc_18000DF56
0x18000df40  mov     eax, [rbx+10h]
0x18000df43  lea     r8, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18000df4a  mov     [rdx], r8
0x18000df4d  mov     [rdx+10h], eax
0x18000df50  mov     [rdx+8], rcx
0x18000df54  jmp     short loc_18000DF5E
0x18000df56  call    cs:__imp_GdipDeleteBrush
0x18000df5c  xor     edx, edx
0x18000df5e  mov     rax, rdx
0x18000df61  add     rsp, 20h
0x18000df65  pop     rbx
0x18000df66  retn
```
