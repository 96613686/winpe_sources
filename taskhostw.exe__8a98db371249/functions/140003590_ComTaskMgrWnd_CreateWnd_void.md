# ComTaskMgrWnd::CreateWnd(void)

- ea: `0x140003590`
- end: `0x1400036a9`
- name: `?CreateWnd@ComTaskMgrWnd@@AEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(ComTaskMgrWnd *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003270`

## callees

- `0x140003590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000366d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000366d`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000362a`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000362a`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x1400035e4`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x1400035e4`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003690`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003690`

## string_xrefs

- `0x1400035c2`: `COMTASKSWINDOWCLASS`
- `0x1400035f8`: `Task Host Window`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::CreateWnd(ComTaskMgrWnd *this)
{
  ATOM v2; // ax
  HWND Window; // rax
  signed int v5; // eax
  signed int v6; // ebx
  signed int LastError; // eax
  const WCHAR *v8; // rcx
  WNDCLASSW v9; // [rsp+60h] [rbp-58h] BYREF

  v9.lpfnWndProc = (WNDPROC)ComTaskMgrWnd::WndProc;
  v9.hInstance = (HINSTANCE)*((_QWORD *)this + 1);
  *(_QWORD *)&v9.style = 0;
  v9.lpszClassName = L"COMTASKSWINDOWCLASS";
  *(_QWORD *)&v9.cbClsExtra = 0;
  memset(&v9.hIcon, 0, 32);
  v2 = RegisterClassW(&v9);
  *((_WORD *)this + 8) = v2;
  if ( v2 )
  {
    Window = CreateWindowExW(0, (LPCWSTR)v2, L"Task Host Window", 0, 0, 0, 0, 0, 0, 0, *((HINSTANCE *)this + 1), 0);
    *((_QWORD *)this + 3) = Window;
    if ( Window )
      return 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147024882;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      return (unsigned int)v6;
  }
  v8 = (const WCHAR *)*((unsigned __int16 *)this + 8);
  if ( (_WORD)v8 )
  {
    UnregisterClassW(v8, *((HINSTANCE *)this + 1));
    *((_WORD *)this + 8) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003590  mov     r11, rsp
0x140003593  mov     [r11+8], rbx
0x140003597  mov     [r11+10h], rsi
0x14000359b  push    rdi
0x14000359c  sub     rsp, 0B0h
0x1400035a3  lea     rax, ?WndProc@ComTaskMgrWnd@@CA_JPEAUHWND__@@I_K_J@Z; ComTaskMgrWnd::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1400035aa  mov     rdi, rcx
0x1400035ad  mov     [r11-50h], rax
0x1400035b1  xor     esi, esi
0x1400035b3  mov     rax, [rcx+8]
0x1400035b7  xorps   xmm0, xmm0
0x1400035ba  mov     [r11-40h], rax
0x1400035be  lea     rcx, [r11-58h]; lpWndClass
0x1400035c2  lea     rax, aComtaskswindow; "COMTASKSWINDOWCLASS"
0x1400035c9  mov     [r11-58h], rsi
0x1400035cd  xorps   xmm1, xmm1
0x1400035d0  mov     [r11-18h], rax
0x1400035d4  mov     [r11-48h], rsi
0x1400035d8  movdqa  xmmword ptr [r11-38h], xmm0
0x1400035de  movdqa  xmmword ptr [r11-28h], xmm1
0x1400035e4  call    cs:__imp_RegisterClassW
0x1400035ea  mov     [rdi+10h], ax
0x1400035ee  test    ax, ax
0x1400035f1  jz      short loc_140003650
0x1400035f3  mov     [rsp+0B8h+lpParam], rsi; lpParam
0x1400035f8  lea     r8, WindowName; "Task Host Window"
0x1400035ff  movzx   edx, ax; lpClassName
0x140003602  xor     r9d, r9d; dwStyle
0x140003605  mov     rax, [rdi+8]
0x140003609  xor     ecx, ecx; dwExStyle
0x14000360b  mov     [rsp+0B8h+hInstance], rax; hInstance
0x140003610  mov     [rsp+0B8h+hMenu], rsi; hMenu
0x140003615  mov     [rsp+0B8h+hWndParent], rsi; hWndParent
0x14000361a  mov     [rsp+0B8h+nHeight], esi; nHeight
0x14000361e  mov     [rsp+0B8h+nWidth], esi; nWidth
0x140003622  mov     [rsp+0B8h+Y], esi; Y
0x140003626  mov     [rsp+0B8h+X], esi; X
0x14000362a  call    cs:__imp_CreateWindowExW
0x140003630  mov     [rdi+18h], rax
0x140003634  test    rax, rax
0x140003637  jz      short loc_14000366D
0x140003639  mov     eax, esi
0x14000363b  lea     r11, [rsp+0B8h+var_8]
0x140003643  mov     rbx, [r11+10h]
0x140003647  mov     rsi, [r11+18h]
0x14000364b  mov     rsp, r11
0x14000364e  pop     rdi
0x14000364f  retn
0x140003650  call    cs:__imp_GetLastError
0x140003656  mov     ebx, eax
0x140003658  test    eax, eax
0x14000365a  jle     short loc_140003665
0x14000365c  movzx   ebx, ax
0x14000365f  or      ebx, 80070000h
0x140003665  test    ebx, ebx
0x140003667  js      short loc_140003683
0x140003669  mov     eax, ebx
0x14000366b  jmp     short loc_14000363B
0x14000366d  call    cs:__imp_GetLastError
0x140003673  mov     ebx, eax
0x140003675  test    eax, eax
0x140003677  jg      short loc_14000369E
0x140003679  test    ebx, ebx
0x14000367b  mov     eax, 8007000Eh
0x140003680  cmovns  ebx, eax
0x140003683  movzx   ecx, word ptr [rdi+10h]; lpClassName
0x140003687  cmp     si, cx
0x14000368a  jz      short loc_14000369A
0x14000368c  mov     rdx, [rdi+8]; hInstance
0x140003690  call    cs:__imp_UnregisterClassW
0x140003696  mov     [rdi+10h], si
0x14000369a  mov     eax, ebx
0x14000369c  jmp     short loc_14000363B
0x14000369e  movzx   ebx, ax
0x1400036a1  or      ebx, 80070000h
0x1400036a7  jmp     short loc_140003679
```
