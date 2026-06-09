# DrawCommandRectangle(HWND__ *)

- ea: `0x180061988`
- end: `0x180061ab5`
- name: `?DrawCommandRectangle@@YAXPEAUHWND__@@@Z`
- size: `301`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004b590`

## callees

- `0x18000bd00`
- `0x180061988`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserEndPaint` at `0x1800619e8`
- `win32u!NtUserEndPaint` at `0x1800619e8`
- `win32u!NtUserBeginPaint` at `0x1800619c5`
- `win32u!NtUserBeginPaint` at `0x1800619c5`
- `GDI32!SelectObject` at `0x180061a2c`
- `GDI32!SelectObject` at `0x180061a4e`
- `GDI32!SelectObject` at `0x180061a8a`
- `GDI32!SelectObject` at `0x180061aa1`
- `GDI32!SelectObject` at `0x180061a2c`
- `GDI32!SelectObject` at `0x180061a4e`
- `GDI32!SelectObject` at `0x180061a8a`
- `GDI32!SelectObject` at `0x180061aa1`
- `GDI32!Rectangle` at `0x180061a7c`
- `GDI32!Rectangle` at `0x180061a7c`
- `GDI32!CreatePen` at `0x180061a3d`
- `GDI32!CreatePen` at `0x180061a3d`
- `GDI32!CreateSolidBrush` at `0x180061a1b`
- `GDI32!CreateSolidBrush` at `0x180061a1b`
- `GDI32!DeleteObject` at `0x180061a93`
- `GDI32!DeleteObject` at `0x180061aaa`
- `GDI32!DeleteObject` at `0x180061a93`
- `GDI32!DeleteObject` at `0x180061aaa`

## pseudocode

```c
void __fastcall DrawCommandRectangle(HWND hWnd)
{
  int *WindowLongPtrW; // r15
  HBRUSH SolidBrush; // rbp
  HGDIOBJ v4; // rsi
  HPEN Pen; // rdi
  HGDIOBJ v6; // rbx
  HDC hdc[10]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(hdc, 0, 0x48u);
  NtUserBeginPaint(hWnd, hdc);
  WindowLongPtrW = (int *)GetWindowLongPtrW(hWnd, -21);
  if ( WindowLongPtrW )
  {
    SolidBrush = CreateSolidBrush(*(_DWORD *)(gpsi + 4584));
    v4 = SelectObject(hdc[0], SolidBrush);
    Pen = CreatePen(5, 0, 0);
    v6 = SelectObject(hdc[0], Pen);
    Rectangle(hdc[0], WindowLongPtrW[34], WindowLongPtrW[35], WindowLongPtrW[36], WindowLongPtrW[37]);
    SelectObject(hdc[0], v6);
    DeleteObject(Pen);
    SelectObject(hdc[0], v4);
    DeleteObject(SolidBrush);
  }
  NtUserEndPaint(hWnd, hdc);
}

```

## disassembly

```asm
0x180061988  push    rbx
0x18006198a  push    rbp
0x18006198b  push    rsi
0x18006198c  push    rdi
0x18006198d  push    r14
0x18006198f  push    r15
0x180061991  sub     rsp, 98h
0x180061998  mov     rax, cs:__security_cookie
0x18006199f  xor     rax, rsp
0x1800619a2  mov     [rsp+0C8h+var_48], rax
0x1800619aa  xor     edx, edx; Val
0x1800619ac  mov     r14, rcx
0x1800619af  lea     rcx, [rsp+0C8h+hdc]; void *
0x1800619b4  lea     r8d, [rdx+48h]; Size
0x1800619b8  call    memset_0
0x1800619bd  lea     rdx, [rsp+0C8h+hdc]
0x1800619c2  mov     rcx, r14
0x1800619c5  call    cs:__imp_NtUserBeginPaint
0x1800619cb  mov     edx, 0FFFFFFEBh; nIndex
0x1800619d0  mov     rcx, r14; hWnd
0x1800619d3  call    GetWindowLongPtrW
0x1800619d8  mov     r15, rax
0x1800619db  test    rax, rax
0x1800619de  jnz     short loc_180061A0E
0x1800619e0  lea     rdx, [rsp+0C8h+hdc]
0x1800619e5  mov     rcx, r14
0x1800619e8  call    cs:__imp_NtUserEndPaint
0x1800619ee  mov     rcx, [rsp+0C8h+var_48]
0x1800619f6  xor     rcx, rsp; StackCookie
0x1800619f9  call    __security_check_cookie
0x1800619fe  add     rsp, 98h
0x180061a05  pop     r15
0x180061a07  pop     r14
0x180061a09  pop     rdi
0x180061a0a  pop     rsi
0x180061a0b  pop     rbp
0x180061a0c  pop     rbx
0x180061a0d  retn
0x180061a0e  mov     rcx, cs:gpsi
0x180061a15  mov     ecx, [rcx+11E8h]; color
0x180061a1b  call    cs:__imp_CreateSolidBrush
0x180061a21  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180061a26  mov     rdx, rax; h
0x180061a29  mov     rbp, rax
0x180061a2c  call    cs:__imp_SelectObject
0x180061a32  xor     edx, edx; cWidth
0x180061a34  xor     r8d, r8d; color
0x180061a37  mov     rsi, rax
0x180061a3a  lea     ecx, [rdx+5]; iStyle
0x180061a3d  call    cs:__imp_CreatePen
0x180061a43  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180061a48  mov     rdx, rax; h
0x180061a4b  mov     rdi, rax
0x180061a4e  call    cs:__imp_SelectObject
0x180061a54  mov     ecx, [r15+94h]
0x180061a5b  mov     rbx, rax
0x180061a5e  mov     r9d, [r15+90h]; right
0x180061a65  mov     r8d, [r15+8Ch]; top
0x180061a6c  mov     edx, [r15+88h]; left
0x180061a73  mov     [rsp+0C8h+bottom], ecx; bottom
0x180061a77  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180061a7c  call    cs:__imp_Rectangle
0x180061a82  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180061a87  mov     rdx, rbx; h
0x180061a8a  call    cs:__imp_SelectObject
0x180061a90  mov     rcx, rdi; ho
0x180061a93  call    cs:__imp_DeleteObject
0x180061a99  mov     rcx, [rsp+0C8h+hdc]; hdc
0x180061a9e  mov     rdx, rsi; h
0x180061aa1  call    cs:__imp_SelectObject
0x180061aa7  mov     rcx, rbp; ho
0x180061aaa  call    cs:__imp_DeleteObject
0x180061ab0  jmp     loc_1800619E0
```
