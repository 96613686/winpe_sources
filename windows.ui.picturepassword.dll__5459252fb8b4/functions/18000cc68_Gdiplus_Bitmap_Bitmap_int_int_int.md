# Gdiplus::Bitmap::Bitmap(int,int,int)

- ea: `0x18000cc68`
- end: `0x18000ccc4`
- name: `??0Bitmap@Gdiplus@@QEAA@HHH@Z`
- size: `92`
- prototype: `Gdiplus::Bitmap *__fastcall(Gdiplus::Bitmap *this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180012338`
- `0x1800123dc`
- `0x180012a94`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromScan0` at `0x18000cca9`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18000cca9`

## pseudocode

```c
Gdiplus::Bitmap *__fastcall Gdiplus::Bitmap::Bitmap(Gdiplus::Bitmap *this, unsigned int a2, unsigned int a3)
{
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  *(_QWORD *)this = &Gdiplus::Image::`vftable';
  *((_DWORD *)this + 4) = GdipCreateBitmapFromScan0(a2, a3, 0, 2498570, 0, &v5);
  *((_QWORD *)this + 1) = v5;
  return this;
}

```

## disassembly

```asm
0x18000cc68  mov     r11, rsp
0x18000cc6b  push    rbx
0x18000cc6c  sub     rsp, 30h
0x18000cc70  mov     rbx, rcx
0x18000cc73  mov     qword ptr [r11+8], 0
0x18000cc7b  mov     eax, r8d
0x18000cc7e  lea     rcx, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18000cc85  mov     r10d, edx
0x18000cc88  mov     r9d, 26200Ah
0x18000cc8e  xor     r8d, r8d
0x18000cc91  mov     edx, eax
0x18000cc93  mov     [rbx], rcx
0x18000cc96  lea     rcx, [r11+8]
0x18000cc9a  mov     [r11-10h], rcx
0x18000cc9e  mov     ecx, r10d
0x18000cca1  mov     qword ptr [r11-18h], 0
0x18000cca9  call    cs:__imp_GdipCreateBitmapFromScan0
0x18000ccaf  mov     [rbx+10h], eax
0x18000ccb2  mov     rax, [rsp+38h+arg_0]
0x18000ccb7  mov     [rbx+8], rax
0x18000ccbb  mov     rax, rbx
0x18000ccbe  add     rsp, 30h
0x18000ccc2  pop     rbx
0x18000ccc3  retn
```
