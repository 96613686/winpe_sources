# WdcGraph::WindowCallback(HWND__ *,uint,uint,__int64)

- ea: `0x180017e70`
- end: `0x180017f99`
- name: `?WindowCallback@WdcGraph@@SA_JPEAUHWND__@@II_J@Z`
- size: `297`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017e70`
- `0x180017fa0`
- `0x18003a3c0`
- `0x18003b0ac`

## import_xrefs

- `GDI32!DeleteObject` at `0x180017f5c`
- `GDI32!DeleteObject` at `0x180017f5c`
- `USER32!EndPaint` at `0x180017f43`
- `USER32!EndPaint` at `0x180017f43`
- `USER32!BeginPaint` at `0x180017f27`
- `USER32!BeginPaint` at `0x180017f27`
- `USER32!InvalidateRect` at `0x180017f0d`
- `USER32!InvalidateRect` at `0x180017f0d`
- `USER32!DefWindowProcW` at `0x180017f78`
- `USER32!DefWindowProcW` at `0x180017f78`
- `USER32!GetWindowLongPtrW` at `0x180017eb0`
- `USER32!GetWindowLongPtrW` at `0x180017eb0`

## pseudocode

```c
LRESULT __fastcall WdcGraph::WindowCallback(HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)
{
  WPARAM v5; // rbp
  LONG_PTR WindowLongPtrW; // rax
  WdcGraph *v9; // rbx
  HDC v11; // rax
  void *v12; // rcx
  tagPAINTSTRUCT Paint; // [rsp+20h] [rbp-88h] BYREF

  v5 = (unsigned int)hdc;
  memset_0(&Paint, 0, sizeof(Paint));
  WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
  v9 = (WdcGraph *)WindowLongPtrW;
  switch ( Msg )
  {
    case 0xFu:
      if ( WindowLongPtrW )
      {
        if ( *(_DWORD *)(WindowLongPtrW + 464) )
          *(_DWORD *)(WindowLongPtrW + 464) = 0;
        else
          InvalidateRect(hWnd, 0, 0);
        v11 = BeginPaint(hWnd, &Paint);
        WdcGraph::Draw(v9, hWnd, v11);
        EndPaint(hWnd, &Paint);
        return 0;
      }
      break;
    case 5u:
      if ( WindowLongPtrW )
      {
        v12 = *(void **)(WindowLongPtrW + 320);
        if ( v12 )
        {
          DeleteObject(v12);
          *((_QWORD *)v9 + 40) = 0;
        }
      }
      break;
    case 0x14u:
      return 1;
    case 0x318u:
      WdcGraph::Draw((WdcGraph *)WindowLongPtrW, hWnd, (HDC)(unsigned int)v5);
      return 0;
  }
  return DefWindowProcW(hWnd, Msg, v5, lParam);
}

```

## disassembly

```asm
0x180017e70  push    rbx
0x180017e72  push    rbp
0x180017e73  push    rsi
0x180017e74  push    rdi
0x180017e75  push    r14
0x180017e77  sub     rsp, 80h
0x180017e7e  mov     rax, cs:__security_cookie
0x180017e85  xor     rax, rsp
0x180017e88  mov     [rsp+0A8h+var_38], rax
0x180017e8d  mov     esi, edx
0x180017e8f  mov     ebp, r8d
0x180017e92  xor     edx, edx; Val
0x180017e94  mov     rdi, rcx
0x180017e97  lea     rcx, [rsp+0A8h+Paint]; void *
0x180017e9c  mov     r14, r9
0x180017e9f  lea     r8d, [rdx+48h]; Size
0x180017ea3  call    memset_0
0x180017ea8  mov     edx, 0FFFFFFEBh; nIndex
0x180017ead  mov     rcx, rdi; hWnd
0x180017eb0  call    cs:__imp_GetWindowLongPtrW
0x180017eb6  mov     rbx, rax
0x180017eb9  cmp     esi, 0Fh
0x180017ebc  jz      short loc_180017EF7
0x180017ebe  cmp     esi, 5
0x180017ec1  jz      loc_180017F4B
0x180017ec7  cmp     esi, 14h
0x180017eca  jz      short loc_180017EED
0x180017ecc  cmp     esi, 318h
0x180017ed2  jnz     loc_180017F6D
0x180017ed8  mov     r8d, ebp; hdc
0x180017edb  mov     rdx, rdi; hWnd
0x180017ede  mov     rcx, rax; this
0x180017ee1  call    ?Draw@WdcGraph@@QEAAJPEAUHWND__@@PEAUHDC__@@@Z; WdcGraph::Draw(HWND__ *,HDC__ *)
0x180017ee6  xor     eax, eax
0x180017ee8  jmp     loc_180017F7E
0x180017eed  mov     eax, 1
0x180017ef2  jmp     loc_180017F7E
0x180017ef7  test    rbx, rbx
0x180017efa  jz      short loc_180017F6D
0x180017efc  cmp     dword ptr [rax+1D0h], 0
0x180017f03  jnz     short loc_180017F15
0x180017f05  xor     r8d, r8d; bErase
0x180017f08  xor     edx, edx; lpRect
0x180017f0a  mov     rcx, rdi; hWnd
0x180017f0d  call    cs:__imp_InvalidateRect
0x180017f13  jmp     short loc_180017F1F
0x180017f15  mov     dword ptr [rax+1D0h], 0
0x180017f1f  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x180017f24  mov     rcx, rdi; hWnd
0x180017f27  call    cs:__imp_BeginPaint
0x180017f2d  mov     rdx, rdi; hWnd
0x180017f30  mov     rcx, rbx; this
0x180017f33  mov     r8, rax; hdc
0x180017f36  call    ?Draw@WdcGraph@@QEAAJPEAUHWND__@@PEAUHDC__@@@Z; WdcGraph::Draw(HWND__ *,HDC__ *)
0x180017f3b  lea     rdx, [rsp+0A8h+Paint]; lpPaint
0x180017f40  mov     rcx, rdi; hWnd
0x180017f43  call    cs:__imp_EndPaint
0x180017f49  jmp     short loc_180017EE6
0x180017f4b  test    rbx, rbx
0x180017f4e  jz      short loc_180017F6D
0x180017f50  mov     rcx, [rax+140h]; ho
0x180017f57  test    rcx, rcx
0x180017f5a  jz      short loc_180017F6D
0x180017f5c  call    cs:__imp_DeleteObject
0x180017f62  mov     qword ptr [rbx+140h], 0
0x180017f6d  mov     r8, rbp; wParam
0x180017f70  mov     r9, r14; lParam
0x180017f73  mov     edx, esi; Msg
0x180017f75  mov     rcx, rdi; hWnd
0x180017f78  call    cs:__imp_DefWindowProcW
0x180017f7e  mov     rcx, [rsp+0A8h+var_38]
0x180017f83  xor     rcx, rsp; StackCookie
0x180017f86  call    __security_check_cookie
0x180017f8b  add     rsp, 80h
0x180017f92  pop     r14
0x180017f94  pop     rdi
0x180017f95  pop     rsi
0x180017f96  pop     rbp
0x180017f97  pop     rbx
0x180017f98  retn
```
