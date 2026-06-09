# Gdiplus::Bitmap::Bitmap(HINSTANCE__ *,ushort const *)

- ea: `0x18001d74c`
- end: `0x18001d796`
- name: `??0Bitmap@Gdiplus@@QEAA@PEAUHINSTANCE__@@PEBG@Z`
- size: `74`
- prototype: `Gdiplus::Bitmap *__fastcall(Gdiplus::Bitmap *this, HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800119a4`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromResource` at `0x18001d77b`
- `gdiplus!GdipCreateBitmapFromResource` at `0x18001d77b`

## pseudocode

```c
Gdiplus::Bitmap *__fastcall Gdiplus::Bitmap::Bitmap(Gdiplus::Bitmap *this, HINSTANCE a2, const unsigned __int16 *a3)
{
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  *(_QWORD *)this = &Gdiplus::Image::`vftable';
  *((_DWORD *)this + 4) = GdipCreateBitmapFromResource(g_DLLModuleHandle, a3, &v5);
  *((_QWORD *)this + 1) = v5;
  return this;
}

```

## disassembly

```asm
0x18001d74c  mov     [rsp+arg_8], rdx
0x18001d751  push    rbx
0x18001d752  sub     rsp, 20h
0x18001d756  mov     rbx, rcx
0x18001d759  mov     [rsp+28h+arg_8], 0
0x18001d762  lea     rcx, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18001d769  mov     rdx, r8
0x18001d76c  lea     r8, [rsp+28h+arg_8]
0x18001d771  mov     [rbx], rcx
0x18001d774  mov     rcx, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x18001d77b  call    cs:__imp_GdipCreateBitmapFromResource
0x18001d781  mov     [rbx+10h], eax
0x18001d784  mov     rax, [rsp+28h+arg_8]
0x18001d789  mov     [rbx+8], rax
0x18001d78d  mov     rax, rbx
0x18001d790  add     rsp, 20h
0x18001d794  pop     rbx
0x18001d795  retn
```
