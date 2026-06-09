# CTimer::ThreadCallback(void *)

- ea: `0x14000e5c0`
- end: `0x14000e6fd`
- name: `?ThreadCallback@CTimer@@KAKPEAX@Z`
- size: `317`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14000e5c0`
- `0x14001755a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000e64a`
- `KERNEL32!GetLastError` at `0x14000e64a`
- `KERNEL32!SetEvent` at `0x14000e644`
- `KERNEL32!SetEvent` at `0x14000e6a9`
- `KERNEL32!SetEvent` at `0x14000e644`
- `KERNEL32!SetEvent` at `0x14000e6a9`
- `USER32!GetClassInfoA` at `0x14000e603`
- `USER32!GetClassInfoA` at `0x14000e603`
- `USER32!RegisterClassA` at `0x14000e635`
- `USER32!RegisterClassA` at `0x14000e635`
- `USER32!DispatchMessageA` at `0x14000e6c9`
- `USER32!DispatchMessageA` at `0x14000e6c9`
- `USER32!GetMessageA` at `0x14000e6dc`
- `USER32!GetMessageA` at `0x14000e6dc`
- `USER32!CreateWindowExA` at `0x14000e694`
- `USER32!CreateWindowExA` at `0x14000e694`

## pseudocode

```c
DWORD __fastcall CTimer::ThreadCallback(HWND *lpThreadParameter)
{
  HWND v2; // rcx
  DWORD result; // eax
  HWND Window; // rax
  int MessageA; // eax
  MSG Msg; // [rsp+60h] [rbp-29h] BYREF
  tagWNDCLASSA WndClass; // [rsp+90h] [rbp+7h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.hInstance = Global::g_hInstance;
  WndClass.lpszClassName = "WSH-Timer";
  if ( !GetClassInfoA(Global::g_hInstance, "WSH-Timer", &WndClass) )
  {
    WndClass.style = 0;
    WndClass.lpfnWndProc = (WNDPROC)CTimer::WindowProc;
    memset(&WndClass.hIcon, 0, 32);
    *(_QWORD *)&WndClass.cbClsExtra = 0;
    if ( !RegisterClassA(&WndClass) )
    {
      v2 = lpThreadParameter[6];
LABEL_4:
      SetEvent(v2);
      result = GetLastError();
      *((_DWORD *)lpThreadParameter + 6) = result;
      return result;
    }
  }
  Window = CreateWindowExA(0, WndClass.lpszClassName, 0, 0, 0, 0, 1, 1, 0, 0, Global::g_hInstance, lpThreadParameter);
  v2 = lpThreadParameter[6];
  *lpThreadParameter = Window;
  if ( !Window )
    goto LABEL_4;
  *((_DWORD *)lpThreadParameter + 6) = 0;
  SetEvent(v2);
  memset(&Msg, 0, sizeof(Msg));
  while ( 1 )
  {
    MessageA = GetMessageA(&Msg, *lpThreadParameter, 0, 0);
    if ( !MessageA || MessageA == -1 )
      break;
    DispatchMessageA(&Msg);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e5c0  mov     [rsp-8+arg_0], rbx
0x14000e5c5  mov     [rsp-8+arg_8], rdi
0x14000e5ca  push    rbp
0x14000e5cb  lea     rbp, [rsp-57h]
0x14000e5d0  sub     rsp, 0E0h
0x14000e5d7  xor     edx, edx; Val
0x14000e5d9  mov     rbx, rcx
0x14000e5dc  lea     rcx, [rbp+57h+WndClass]; void *
0x14000e5e0  lea     r8d, [rdx+48h]; Size
0x14000e5e4  call    memset_0
0x14000e5e9  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x14000e5f0  lea     rdx, ClassName; "WSH-Timer"
0x14000e5f7  lea     r8, [rbp+57h+WndClass]; lpWndClass
0x14000e5fb  mov     [rbp+57h+WndClass.hInstance], rcx
0x14000e5ff  mov     [rbp+57h+WndClass.lpszClassName], rdx
0x14000e603  call    cs:__imp_GetClassInfoA
0x14000e609  xor     edi, edi
0x14000e60b  test    eax, eax
0x14000e60d  jnz     short loc_14000E658
0x14000e60f  lea     rax, ?WindowProc@CTimer@@KA_JPEAUHWND__@@I_K_J@Z; CTimer::WindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000e616  mov     [rbp+57h+WndClass.style], edi
0x14000e619  xorps   xmm0, xmm0
0x14000e61c  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x14000e620  xorps   xmm1, xmm1
0x14000e623  movdqa  xmmword ptr [rbp+57h+WndClass.hIcon], xmm0
0x14000e628  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x14000e62c  movdqa  xmmword ptr [rbp+57h+WndClass.hbrBackground], xmm1
0x14000e631  mov     qword ptr [rbp+57h+WndClass.cbClsExtra], rdi
0x14000e635  call    cs:__imp_RegisterClassA
0x14000e63b  test    ax, ax
0x14000e63e  jnz     short loc_14000E658
0x14000e640  mov     rcx, [rbx+30h]; hEvent
0x14000e644  call    cs:__imp_SetEvent
0x14000e64a  call    cs:__imp_GetLastError
0x14000e650  mov     [rbx+18h], eax
0x14000e653  jmp     loc_14000E6E8
0x14000e658  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x14000e65f  xor     r9d, r9d; dwStyle
0x14000e662  mov     rdx, [rbp+57h+WndClass.lpszClassName]; lpClassName
0x14000e666  xor     r8d, r8d; lpWindowName
0x14000e669  mov     [rsp+0E0h+lpParam], rbx; lpParam
0x14000e66e  xor     ecx, ecx; dwExStyle
0x14000e670  mov     [rsp+0E0h+hInstance], rax; hInstance
0x14000e675  mov     eax, 1
0x14000e67a  mov     [rsp+0E0h+hMenu], rdi; hMenu
0x14000e67f  mov     [rsp+0E0h+hWndParent], rdi; hWndParent
0x14000e684  mov     [rsp+0E0h+nHeight], eax; nHeight
0x14000e688  mov     [rsp+0E0h+nWidth], eax; nWidth
0x14000e68c  mov     [rsp+0E0h+Y], edi; Y
0x14000e690  mov     [rsp+0E0h+X], edi; X
0x14000e694  call    cs:__imp_CreateWindowExA
0x14000e69a  mov     rcx, [rbx+30h]; hEvent
0x14000e69e  mov     [rbx], rax
0x14000e6a1  test    rax, rax
0x14000e6a4  jz      short loc_14000E644
0x14000e6a6  mov     [rbx+18h], edi
0x14000e6a9  call    cs:__imp_SetEvent
0x14000e6af  xorps   xmm0, xmm0
0x14000e6b2  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000e6b6  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14000e6ba  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14000e6be  jmp     short loc_14000E6CF
0x14000e6c0  cmp     eax, 0FFFFFFFFh
0x14000e6c3  jz      short loc_14000E6E6
0x14000e6c5  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000e6c9  call    cs:__imp_DispatchMessageA
0x14000e6cf  mov     rdx, [rbx]; hWnd
0x14000e6d2  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000e6d6  xor     r9d, r9d; wMsgFilterMax
0x14000e6d9  xor     r8d, r8d; wMsgFilterMin
0x14000e6dc  call    cs:__imp_GetMessageA
0x14000e6e2  test    eax, eax
0x14000e6e4  jnz     short loc_14000E6C0
0x14000e6e6  mov     eax, edi
0x14000e6e8  lea     r11, [rsp+0E0h+var_s0]
0x14000e6f0  mov     rbx, [r11+10h]
0x14000e6f4  mov     rdi, [r11+18h]
0x14000e6f8  mov     rsp, r11
0x14000e6fb  pop     rbp
0x14000e6fc  retn
```
