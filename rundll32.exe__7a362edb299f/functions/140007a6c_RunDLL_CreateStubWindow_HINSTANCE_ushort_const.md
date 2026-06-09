# RunDLL_CreateStubWindow(HINSTANCE__ *,ushort const *)

- ea: `0x140007a6c`
- end: `0x140007b38`
- name: `?RunDLL_CreateStubWindow@@YAPEAUHWND__@@PEAUHINSTANCE__@@PEBG@Z`
- size: `204`
- prototype: `HWND __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007798`

## callees

- `0x140002254`

## import_xrefs

- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140007ade`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140007ade`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x140007b21`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x140007b21`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x140007aa8`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x140007aa8`

## string_xrefs

- `0x140007aae`: `RunDLL`

## pseudocode

```c
HWND __fastcall RunDLL_CreateStubWindow(HINSTANCE a1, const unsigned __int16 *a2)
{
  HINSTANCE hInstance; // rbx
  HCURSOR CursorW; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF

  hInstance = g_hInstance;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.hInstance = hInstance;
  WndClass.lpfnWndProc = (WNDPROC)WndProc;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = L"RunDLL";
  WndClass.cbWndExtra = 8;
  RegisterClassW(&WndClass);
  return CreateWindowExW(0x80u, L"RunDLL", &WindowName, 0, 0x80000000, 0x80000000, 0, 0, 0, 0, hInstance, 0);
}

```

## disassembly

```asm
0x140007a6c  mov     [rsp+arg_0], rbx
0x140007a71  push    rdi
0x140007a72  sub     rsp, 0B0h
0x140007a79  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x140007a80  lea     rcx, [rsp+0B8h+WndClass]; void *
0x140007a85  xor     edx, edx; Val
0x140007a87  lea     r8d, [rdx+48h]; Size
0x140007a8b  call    memset_0
0x140007a90  lea     rax, ?WndProc@@YA_JPEAUHWND__@@I_K_J@Z; WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x140007a97  mov     [rsp+0B8h+WndClass.hInstance], rbx
0x140007a9c  mov     edx, 7F00h; lpCursorName
0x140007aa1  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x140007aa6  xor     ecx, ecx; hInstance
0x140007aa8  call    cs:__imp_LoadCursorW
0x140007aae  lea     rdi, ClassName; "RunDLL"
0x140007ab5  mov     [rsp+0B8h+WndClass.hbrBackground], 6
0x140007ac1  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x140007ac6  mov     [rsp+0B8h+WndClass.hCursor], rax
0x140007ace  mov     [rsp+0B8h+WndClass.lpszClassName], rdi
0x140007ad6  mov     [rsp+0B8h+WndClass.cbWndExtra], 8
0x140007ade  call    cs:__imp_RegisterClassW
0x140007ae4  xor     eax, eax
0x140007ae6  lea     r8, WindowName; lpWindowName
0x140007aed  mov     [rsp+0B8h+lpParam], rax; lpParam
0x140007af2  xor     r9d, r9d; dwStyle
0x140007af5  mov     [rsp+0B8h+hInstance], rbx; hInstance
0x140007afa  mov     rdx, rdi; lpClassName
0x140007afd  mov     [rsp+0B8h+hMenu], rax; hMenu
0x140007b02  mov     ecx, 80h; dwExStyle
0x140007b07  mov     [rsp+0B8h+hWndParent], rax; hWndParent
0x140007b0c  mov     [rsp+0B8h+nHeight], eax; nHeight
0x140007b10  mov     [rsp+0B8h+nWidth], eax; nWidth
0x140007b14  mov     eax, 80000000h
0x140007b19  mov     [rsp+0B8h+Y], eax; Y
0x140007b1d  mov     [rsp+0B8h+X], eax; X
0x140007b21  call    cs:__imp_CreateWindowExW
0x140007b27  mov     rbx, [rsp+0B8h+arg_0]
0x140007b2f  add     rsp, 0B0h
0x140007b36  pop     rdi
0x140007b37  retn
```
