# CThemeThumbnail::_FreeDrawingResources(void)

- ea: `0x180057b98`
- end: `0x180057be9`
- name: `?_FreeDrawingResources@CThemeThumbnail@@AEAAXXZ`
- size: `81`
- prototype: `void __fastcall(CThemeThumbnail *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800575c0`
- `0x180057750`
- `0x180057bf0`
- `0x180057c90`

## callees

- `0x180057b98`

## import_xrefs

- `GDI32!DeleteObject` at `0x180057bd5`
- `GDI32!DeleteObject` at `0x180057bd5`
- `GDI32!RestoreDC` at `0x180057bad`
- `GDI32!RestoreDC` at `0x180057bad`
- `GDI32!DeleteDC` at `0x180057bbe`
- `GDI32!DeleteDC` at `0x180057bbe`

## pseudocode

```c
void __fastcall CThemeThumbnail::_FreeDrawingResources(CThemeThumbnail *this)
{
  HDC v2; // rcx
  HDC v3; // rcx
  void *v4; // rcx

  v2 = (HDC)*((_QWORD *)this + 12);
  if ( v2 )
  {
    RestoreDC(v2, *((_DWORD *)this + 22));
    v3 = (HDC)*((_QWORD *)this + 12);
    *((_DWORD *)this + 22) = 0;
    DeleteDC(v3);
    *((_QWORD *)this + 12) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x180057b98  push    rbx
0x180057b9a  sub     rsp, 20h
0x180057b9e  mov     rbx, rcx
0x180057ba1  mov     rcx, [rcx+60h]; hdc
0x180057ba5  test    rcx, rcx
0x180057ba8  jz      short loc_180057BCC
0x180057baa  mov     edx, [rbx+58h]; nSavedDC
0x180057bad  call    cs:__imp_RestoreDC
0x180057bb3  mov     rcx, [rbx+60h]; hdc
0x180057bb7  mov     dword ptr [rbx+58h], 0
0x180057bbe  call    cs:__imp_DeleteDC
0x180057bc4  mov     qword ptr [rbx+60h], 0
0x180057bcc  mov     rcx, [rbx+50h]; ho
0x180057bd0  test    rcx, rcx
0x180057bd3  jz      short loc_180057BE3
0x180057bd5  call    cs:__imp_DeleteObject
0x180057bdb  mov     qword ptr [rbx+50h], 0
0x180057be3  add     rsp, 20h
0x180057be7  pop     rbx
0x180057be8  retn
```
