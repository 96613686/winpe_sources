# Gdiplus::SolidBrush::`scalar deleting destructor'(uint)

- ea: `0x18000d820`
- end: `0x18000d85f`
- name: `??_GSolidBrush@Gdiplus@@UEAAPEAXI@Z`
- size: `63`
- prototype: `Gdiplus::SolidBrush *__fastcall(Gdiplus::SolidBrush *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d820`

## import_xrefs

- `gdiplus!GdipFree` at `0x18000d84b`
- `gdiplus!GdipFree` at `0x18000d84b`
- `gdiplus!GdipDeleteBrush` at `0x18000d83d`
- `gdiplus!GdipDeleteBrush` at `0x18000d83d`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::`scalar deleting destructor'(Gdiplus::SolidBrush *this, char a2)
{
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
  if ( (a2 & 1) != 0 )
    GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x18000d820  mov     [rsp+arg_0], rbx
0x18000d825  push    rdi
0x18000d826  sub     rsp, 20h
0x18000d82a  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18000d831  mov     rdi, rcx
0x18000d834  mov     [rcx], rax
0x18000d837  mov     ebx, edx
0x18000d839  mov     rcx, [rcx+8]
0x18000d83d  call    cs:__imp_GdipDeleteBrush
0x18000d843  test    bl, 1
0x18000d846  jz      short loc_18000D851
0x18000d848  mov     rcx, rdi
0x18000d84b  call    cs:__imp_GdipFree
0x18000d851  mov     rbx, [rsp+28h+arg_0]
0x18000d856  mov     rax, rdi
0x18000d859  add     rsp, 20h
0x18000d85d  pop     rdi
0x18000d85e  retn
```
