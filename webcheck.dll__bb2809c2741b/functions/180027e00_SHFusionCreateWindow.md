# SHFusionCreateWindow

- ea: `0x180027e00`
- end: `0x180027eab`
- name: `SHFusionCreateWindow`
- size: `171`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpClassName@<rcx>, int, int, int, int, int, int, LPVOID)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800060f8`
- `0x18001a4b0`

## callees

- `0x180027d70`
- `0x180027de0`
- `0x180027e00`
- `0x1800280ac`

## import_xrefs

- `USER32!CreateWindowExW` at `0x180027e8a`
- `USER32!CreateWindowExW` at `0x180027e8a`

## pseudocode

```c
HWND __fastcall SHFusionCreateWindow(
        LPCWSTR lpClassName,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        LPVOID lpParam)
{
  HINSTANCE hInstance; // rdi
  HWND Window; // rbx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+10h] BYREF

  hInstance = g_hInst;
  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  if ( g_hActCtx != (HANDLE)-3LL )
    DelayLoadCC();
  Window = CreateWindowExW(
             0,
             lpClassName,
             L"YO",
             0,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             0,
             0,
             hInstance,
             lpParam);
  SHDeactivateContext(ulCookie);
  return Window;
}

```

## disassembly

```asm
0x180027e00  mov     rax, rsp
0x180027e03  mov     [rax+8], rbx
0x180027e07  mov     [rax+10h], rdx
0x180027e0b  push    rdi
0x180027e0c  sub     rsp, 60h
0x180027e10  mov     rdi, cs:g_hInst
0x180027e17  mov     rbx, rcx
0x180027e1a  lea     rcx, [rax+10h]
0x180027e1e  mov     qword ptr [rax+10h], 0
0x180027e26  call    SHActivateContext
0x180027e2b  test    eax, eax
0x180027e2d  jnz     short loc_180027E33
0x180027e2f  xor     eax, eax
0x180027e31  jmp     short loc_180027EA0
0x180027e33  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x180027e3b  jz      short loc_180027E42
0x180027e3d  call    DelayLoadCC
0x180027e42  mov     rax, [rsp+68h+arg_50]
0x180027e4a  lea     r8, WindowName; "YO"
0x180027e51  mov     [rsp+68h+lpParam], rax; lpParam
0x180027e56  xor     r9d, r9d; dwStyle
0x180027e59  mov     [rsp+68h+hInstance], rdi; hInstance
0x180027e5e  mov     eax, 80000000h
0x180027e63  mov     [rsp+68h+hMenu], 0; hMenu
0x180027e6c  mov     rdx, rbx; lpClassName
0x180027e6f  mov     [rsp+68h+hWndParent], 0; hWndParent
0x180027e78  xor     ecx, ecx; dwExStyle
0x180027e7a  mov     [rsp+68h+nHeight], eax; nHeight
0x180027e7e  mov     [rsp+68h+nWidth], eax; nWidth
0x180027e82  mov     [rsp+68h+Y], eax; Y
0x180027e86  mov     [rsp+68h+X], eax; X
0x180027e8a  call    cs:__imp_CreateWindowExW
0x180027e90  mov     rcx, [rsp+68h+ulCookie]; ulCookie
0x180027e95  mov     rbx, rax
0x180027e98  call    SHDeactivateContext
0x180027e9d  mov     rax, rbx
0x180027ea0  mov     rbx, [rsp+68h+arg_0]
0x180027ea5  add     rsp, 60h
0x180027ea9  pop     rdi
0x180027eaa  retn
```
