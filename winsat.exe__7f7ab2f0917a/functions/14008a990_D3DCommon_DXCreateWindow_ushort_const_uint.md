# D3DCommon::DXCreateWindow(ushort const *,uint)

- ea: `0x14008a990`
- end: `0x14008aac4`
- name: `?DXCreateWindow@D3DCommon@@YAJPEBGI@Z`
- size: `308`
- prototype: `__int64 __fastcall(LPCWSTR lpWindowName, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400852f0`
- `0x140086a74`

## callees

- `0x14008a990`
- `0x14008aacc`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14008a9c4`
- `KERNEL32!GetModuleHandleW` at `0x14008a9c4`
- `KERNEL32!GetLastError` at `0x14008aa38`
- `KERNEL32!GetLastError` at `0x14008aa45`
- `KERNEL32!GetLastError` at `0x14008aa38`
- `KERNEL32!GetLastError` at `0x14008aa45`
- `USER32!PeekMessageW` at `0x14008aa1d`
- `USER32!PeekMessageW` at `0x14008aa1d`
- `USER32!RegisterClassW` at `0x14008aa2b`
- `USER32!RegisterClassW` at `0x14008aa2b`
- `USER32!CreateWindowExW` at `0x14008aa9d`
- `USER32!CreateWindowExW` at `0x14008aa9d`
- `GDI32!GetStockObject` at `0x14008a9d8`
- `GDI32!GetStockObject` at `0x14008a9d8`

## pseudocode

```c
signed int __fastcall D3DCommon::DXCreateWindow(LPCWSTR lpWindowName, const unsigned __int16 *a2)
{
  UINT v3; // ebx
  D3DCommon *v4; // rcx
  signed int result; // eax
  struct tagMSG Msg; // [rsp+60h] [rbp-49h] BYREF
  WNDCLASSW WndClass; // [rsp+90h] [rbp-19h] BYREF

  *(_QWORD *)&WndClass.style = 0;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  WndClass.lpfnWndProc = (WNDPROC)D3DCommon::DefaultWndProc;
  v3 = (unsigned int)a2;
  WndClass.hInstance = GetModuleHandleW(0);
  *(_OWORD *)&WndClass.hIcon = 0;
  WndClass.lpszMenuName = 0;
  WndClass.hbrBackground = (HBRUSH)GetStockObject(0);
  WndClass.lpszClassName = L"DXBaseWndClass";
  D3DCommon::DXDestroyWindow(v4);
  memset(&Msg, 0, sizeof(Msg));
  while ( PeekMessageW(&Msg, 0, 0, 0, 3u) )
    ;
  if ( (RegisterClassW(&WndClass) || GetLastError() == 1410)
    && (hWnd = CreateWindowExW(
                 0,
                 L"DXBaseWndClass",
                 lpWindowName,
                 0,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 0x80000000,
                 0,
                 0,
                 0,
                 0)) != 0 )
  {
    result = 0;
    uFlags = v3;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x14008a990  push    rbp
0x14008a992  push    rbx
0x14008a993  push    rdi
0x14008a994  push    r14
0x14008a996  lea     rbp, [rsp-3Fh]
0x14008a99b  sub     rsp, 0E8h
0x14008a9a2  mov     rdi, rcx
0x14008a9a5  mov     qword ptr [rbp+57h+WndClass.style], 0
0x14008a9ad  lea     rax, ?DefaultWndProc@D3DCommon@@YA_JPEAUHWND__@@I_K_J@Z; D3DCommon::DefaultWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14008a9b4  mov     qword ptr [rbp+57h+WndClass.cbClsExtra], 0
0x14008a9bc  xor     ecx, ecx; lpModuleName
0x14008a9be  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x14008a9c2  mov     ebx, edx
0x14008a9c4  call    cs:__imp_GetModuleHandleW
0x14008a9ca  xorps   xmm0, xmm0
0x14008a9cd  xor     ecx, ecx; i
0x14008a9cf  mov     [rbp+57h+WndClass.hInstance], rax
0x14008a9d3  movdqa  xmmword ptr [rbp+57h+WndClass.hIcon], xmm0
0x14008a9d8  call    cs:__imp_GetStockObject
0x14008a9de  lea     r14, ClassName; "DXBaseWndClass"
0x14008a9e5  mov     [rbp+57h+WndClass.lpszMenuName], 0
0x14008a9ed  mov     [rbp+57h+WndClass.hbrBackground], rax
0x14008a9f1  mov     [rbp+57h+WndClass.lpszClassName], r14
0x14008a9f5  call    ?DXDestroyWindow@D3DCommon@@YAXXZ; D3DCommon::DXDestroyWindow(void)
0x14008a9fa  xorps   xmm0, xmm0
0x14008a9fd  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14008aa01  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14008aa05  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14008aa09  xor     r9d, r9d; wMsgFilterMax
0x14008aa0c  mov     [rsp+100h+wRemoveMsg], 3; wRemoveMsg
0x14008aa14  xor     r8d, r8d; wMsgFilterMin
0x14008aa17  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14008aa1b  xor     edx, edx; hWnd
0x14008aa1d  call    cs:__imp_PeekMessageW
0x14008aa23  test    eax, eax
0x14008aa25  jnz     short loc_14008AA09
0x14008aa27  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x14008aa2b  call    cs:__imp_RegisterClassW
0x14008aa31  xor     ecx, ecx
0x14008aa33  cmp     cx, ax
0x14008aa36  jnz     short loc_14008AA59
0x14008aa38  call    cs:__imp_GetLastError
0x14008aa3e  cmp     eax, 582h
0x14008aa43  jz      short loc_14008AA59
0x14008aa45  call    cs:__imp_GetLastError
0x14008aa4b  test    eax, eax
0x14008aa4d  jle     short loc_14008AAB7
0x14008aa4f  movzx   eax, ax
0x14008aa52  or      eax, 80070000h
0x14008aa57  jmp     short loc_14008AAB7
0x14008aa59  mov     [rsp+100h+lpParam], 0; lpParam
0x14008aa62  mov     eax, 80000000h
0x14008aa67  mov     [rsp+100h+hInstance], 0; hInstance
0x14008aa70  xor     r9d, r9d; dwStyle
0x14008aa73  mov     [rsp+100h+hMenu], 0; hMenu
0x14008aa7c  mov     r8, rdi; lpWindowName
0x14008aa7f  mov     [rsp+100h+hWndParent], 0; hWndParent
0x14008aa88  mov     rdx, r14; lpClassName
0x14008aa8b  mov     [rsp+100h+nHeight], eax; nHeight
0x14008aa8f  xor     ecx, ecx; dwExStyle
0x14008aa91  mov     [rsp+100h+nWidth], eax; nWidth
0x14008aa95  mov     [rsp+100h+Y], eax; Y
0x14008aa99  mov     [rsp+100h+wRemoveMsg], eax; X
0x14008aa9d  call    cs:__imp_CreateWindowExW
0x14008aaa3  mov     cs:hWnd, rax
0x14008aaaa  test    rax, rax
0x14008aaad  jz      short loc_14008AA45
0x14008aaaf  xor     eax, eax
0x14008aab1  mov     cs:uFlags, ebx
0x14008aab7  add     rsp, 0E8h
0x14008aabe  pop     r14
0x14008aac0  pop     rdi
0x14008aac1  pop     rbx
0x14008aac2  pop     rbp
0x14008aac3  retn
```
