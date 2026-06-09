# SHCreateWorkerWindowA

- ea: `0x180024a00`
- end: `0x180024b4c`
- name: `SHCreateWorkerWindowA`
- size: `332`
- prototype: `__int64 __usercall@<rax>(LONG_PTR dwNewLong@<rcx>, HWND hWndParent@<rdx>, HMENU, LONG_PTR)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180012550`
- `0x180013066`
- `0x18002396c`
- `0x180024a00`
- `0x1800254a0`

## import_xrefs

- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180024b0b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180024b1f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180024b0b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180024b1f`
- `USER32!CreateWindowExA` at `0x180024af5`
- `USER32!CreateWindowExA` at `0x180024af5`
- `USER32!DefWindowProcA` at `0x180024a52`
- `USER32!LoadCursorW` at `0x180024a79`
- `USER32!LoadCursorW` at `0x180024a79`

## pseudocode

```c
HWND __fastcall SHCreateWorkerWindowA(
        LONG_PTR dwNewLong,
        HWND hWndParent,
        int a3,
        DWORD a4,
        HMENU hMenu,
        LONG_PTR dwNewLonga)
{
  HCURSOR CursorW; // rax
  unsigned __int16 *v11; // rcx
  int v12; // ebx
  HWND Window; // rax
  HWND v14; // rbx
  WNDCLASSA WndClass; // [rsp+60h] [rbp-A8h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.lpfnWndProc = DefWindowProcA;
  WndClass.hInstance = g_hinst;
  WndClass.cbWndExtra = 8;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)16;
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = "WorkerA";
  v12 = (unsigned int)IsBiDiLocalizedSystemEx(v11) != 0 ? 0x400000 : 0;
  SHRegisterClassA(&WndClass);
  Window = CreateWindowExA(a3 | (unsigned int)v12, "WorkerA", 0, a4, 0, 0, 0, 0, hWndParent, hMenu, g_hinst, 0);
  v14 = Window;
  if ( Window )
  {
    SetWindowLongPtrW(Window, 0, dwNewLonga);
    if ( dwNewLong )
      SetWindowLongPtrW(v14, -4, dwNewLong);
  }
  return v14;
}

```

## disassembly

```asm
0x180024a00  push    rbx
0x180024a02  push    rbp
0x180024a03  push    rsi
0x180024a04  push    rdi
0x180024a05  push    r12
0x180024a07  push    r13
0x180024a09  push    r14
0x180024a0b  push    r15
0x180024a0d  sub     rsp, 0C8h
0x180024a14  mov     rax, cs:__security_cookie
0x180024a1b  xor     rax, rsp
0x180024a1e  mov     [rsp+108h+var_58], rax
0x180024a26  mov     rdi, [rsp+108h+arg_20]
0x180024a2e  mov     rbp, rdx
0x180024a31  mov     r12, [rsp+108h+dwNewLong]
0x180024a39  xor     edx, edx; Val
0x180024a3b  mov     esi, r8d
0x180024a3e  mov     r15, rcx
0x180024a41  lea     rcx, [rsp+108h+WndClass]; void *
0x180024a46  mov     r14d, r9d
0x180024a49  lea     r8d, [rdx+48h]; Size
0x180024a4d  call    memset_0
0x180024a52  mov     rax, cs:__imp_DefWindowProcA
0x180024a59  mov     edx, 7F00h; lpCursorName
0x180024a5e  mov     [rsp+108h+WndClass.lpfnWndProc], rax
0x180024a63  xor     ecx, ecx; hInstance
0x180024a65  mov     rax, cs:g_hinst
0x180024a6c  mov     [rsp+108h+WndClass.hInstance], rax
0x180024a71  mov     [rsp+108h+WndClass.cbWndExtra], 8
0x180024a79  call    cs:__imp_LoadCursorW
0x180024a7f  lea     r13, ClassName; "WorkerA"
0x180024a86  mov     [rsp+108h+WndClass.hbrBackground], 10h
0x180024a92  mov     [rsp+108h+WndClass.hCursor], rax
0x180024a9a  mov     [rsp+108h+WndClass.lpszClassName], r13
0x180024aa2  call    ?IsBiDiLocalizedSystemEx@@YAHPEAG@Z; IsBiDiLocalizedSystemEx(ushort *)
0x180024aa7  neg     eax
0x180024aa9  lea     rcx, [rsp+108h+WndClass]; lpWndClass
0x180024aae  sbb     ebx, ebx
0x180024ab0  and     ebx, 400000h
0x180024ab6  call    SHRegisterClassA
0x180024abb  mov     rax, cs:g_hinst
0x180024ac2  or      ebx, esi
0x180024ac4  xor     esi, esi
0x180024ac6  mov     r9d, r14d; dwStyle
0x180024ac9  mov     [rsp+108h+lpParam], rsi; lpParam
0x180024ace  xor     r8d, r8d; lpWindowName
0x180024ad1  mov     [rsp+108h+hInstance], rax; hInstance
0x180024ad6  mov     rdx, r13; lpClassName
0x180024ad9  mov     [rsp+108h+hMenu], rdi; hMenu
0x180024ade  mov     ecx, ebx; dwExStyle
0x180024ae0  mov     [rsp+108h+hWndParent], rbp; hWndParent
0x180024ae5  mov     [rsp+108h+nHeight], esi; nHeight
0x180024ae9  mov     [rsp+108h+nWidth], esi; nWidth
0x180024aed  mov     [rsp+108h+Y], esi; Y
0x180024af1  mov     [rsp+108h+X], esi; X
0x180024af5  call    cs:__imp_CreateWindowExA
0x180024afb  mov     rbx, rax
0x180024afe  test    rax, rax
0x180024b01  jz      short loc_180024B25
0x180024b03  mov     r8, r12; dwNewLong
0x180024b06  xor     edx, edx; nIndex
0x180024b08  mov     rcx, rax; hWnd
0x180024b0b  call    cs:__imp_SetWindowLongPtrW
0x180024b11  test    r15, r15
0x180024b14  jz      short loc_180024B25
0x180024b16  mov     r8, r15; dwNewLong
0x180024b19  lea     edx, [rsi-4]; nIndex
0x180024b1c  mov     rcx, rbx; hWnd
0x180024b1f  call    cs:__imp_SetWindowLongPtrW
0x180024b25  mov     rax, rbx
0x180024b28  mov     rcx, [rsp+108h+var_58]
0x180024b30  xor     rcx, rsp; StackCookie
0x180024b33  call    __security_check_cookie
0x180024b38  add     rsp, 0C8h
0x180024b3f  pop     r15
0x180024b41  pop     r14
0x180024b43  pop     r13
0x180024b45  pop     r12
0x180024b47  pop     rdi
0x180024b48  pop     rsi
0x180024b49  pop     rbp
0x180024b4a  pop     rbx
0x180024b4b  retn
```
