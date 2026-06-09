# CDimmedWindow::Destroy(void)

- ea: `0x18003d774`
- end: `0x18003d810`
- name: `?Destroy@CDimmedWindow@@AEAAXXZ`
- size: `156`
- prototype: `void __fastcall(CDimmedWindow *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003d650`
- `0x18003dc00`

## callees

- `0x18003d774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d7bd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d7bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d7c7`
- `GDI32!DeleteObject` at `0x18003d7fb`
- `GDI32!DeleteObject` at `0x18003d7fb`
- `GDI32!SelectObject` at `0x18003d7de`
- `GDI32!SelectObject` at `0x18003d7de`
- `GDI32!DeleteDC` at `0x18003d7e8`
- `GDI32!DeleteDC` at `0x18003d7e8`
- `USER32!SetWindowLongPtrW` at `0x18003d792`
- `USER32!SetWindowLongPtrW` at `0x18003d792`
- `USER32!UnregisterClassW` at `0x18003d7aa`
- `USER32!UnregisterClassW` at `0x18003d7aa`

## pseudocode

```c
void __fastcall CDimmedWindow::Destroy(CDimmedWindow *this)
{
  HWND v2; // rcx
  void *v3; // rcx
  HDC v4; // rcx
  void *v5; // rcx

  v2 = (HWND)*((_QWORD *)this + 3);
  if ( v2 )
  {
    SetWindowLongPtrW(v2, -21, 0);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_WORD *)this + 8) )
  {
    UnregisterClassW((LPCWSTR)*((unsigned __int16 *)this + 8), *((HINSTANCE *)this + 1));
    *((_WORD *)this + 8) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    SetEvent(v3);
    CloseHandle(*((HANDLE *)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (HDC)*((_QWORD *)this + 5);
  if ( v4 )
  {
    SelectObject(v4, *((HGDIOBJ *)this + 7));
    DeleteDC(*((HDC *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
  {
    DeleteObject(v5);
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x18003d774  mov     [rsp+arg_0], rbx
0x18003d779  push    rdi
0x18003d77a  sub     rsp, 20h
0x18003d77e  mov     rbx, rcx
0x18003d781  xor     edi, edi
0x18003d783  mov     rcx, [rcx+18h]; hWnd
0x18003d787  test    rcx, rcx
0x18003d78a  jz      short loc_18003D79C
0x18003d78c  xor     r8d, r8d; dwNewLong
0x18003d78f  lea     edx, [rdi-15h]; nIndex
0x18003d792  call    cs:__imp_SetWindowLongPtrW
0x18003d798  mov     [rbx+18h], rdi
0x18003d79c  cmp     [rbx+10h], di
0x18003d7a0  jz      short loc_18003D7B4
0x18003d7a2  movzx   ecx, word ptr [rbx+10h]; lpClassName
0x18003d7a6  mov     rdx, [rbx+8]; hInstance
0x18003d7aa  call    cs:__imp_UnregisterClassW
0x18003d7b0  mov     [rbx+10h], di
0x18003d7b4  mov     rcx, [rbx+20h]; hEvent
0x18003d7b8  test    rcx, rcx
0x18003d7bb  jz      short loc_18003D7D1
0x18003d7bd  call    cs:__imp_SetEvent
0x18003d7c3  mov     rcx, [rbx+20h]; hObject
0x18003d7c7  call    cs:__imp_CloseHandle
0x18003d7cd  mov     [rbx+20h], rdi
0x18003d7d1  mov     rcx, [rbx+28h]; hdc
0x18003d7d5  test    rcx, rcx
0x18003d7d8  jz      short loc_18003D7F2
0x18003d7da  mov     rdx, [rbx+38h]; h
0x18003d7de  call    cs:__imp_SelectObject
0x18003d7e4  mov     rcx, [rbx+28h]; hdc
0x18003d7e8  call    cs:__imp_DeleteDC
0x18003d7ee  mov     [rbx+28h], rdi
0x18003d7f2  mov     rcx, [rbx+30h]; ho
0x18003d7f6  test    rcx, rcx
0x18003d7f9  jz      short loc_18003D805
0x18003d7fb  call    cs:__imp_DeleteObject
0x18003d801  mov     [rbx+30h], rdi
0x18003d805  mov     rbx, [rsp+28h+arg_0]
0x18003d80a  add     rsp, 20h
0x18003d80e  pop     rdi
0x18003d80f  retn
```
