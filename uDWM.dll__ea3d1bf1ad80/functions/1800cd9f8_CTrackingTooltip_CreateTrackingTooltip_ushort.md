# CTrackingTooltip::CreateTrackingTooltip(ushort *)

- ea: `0x1800cd9f8`
- end: `0x1800cdab1`
- name: `?CreateTrackingTooltip@CTrackingTooltip@@IEAAPEAUHWND__@@PEAG@Z`
- size: `185`
- prototype: `HWND __fastcall(CTrackingTooltip *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800cdab8`

## callees

- `0x1800cd9f8`

## import_xrefs

- `USER32!CreateWindowExW` at `0x1800cda4a`
- `USER32!CreateWindowExW` at `0x1800cda4a`
- `USER32!SendMessageW` at `0x1800cda9f`
- `USER32!SendMessageW` at `0x1800cda9f`
- `USER32!GetWindowRect` at `0x1800cda8a`
- `USER32!GetWindowRect` at `0x1800cda8a`
- `USER32!GetDesktopWindow` at `0x1800cda58`
- `USER32!GetDesktopWindow` at `0x1800cda58`

## pseudocode

```c
HWND __fastcall CTrackingTooltip::CreateTrackingTooltip(CTrackingTooltip *this, unsigned __int16 *a2)
{
  HWND Window; // rsi
  HWND DesktopWindow; // rax

  Window = CreateWindowExW(
             8u,
             L"tooltips_class32",
             0,
             0x80000003,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             0,
             0,
             g_hInstance,
             0);
  if ( Window )
  {
    DesktopWindow = GetDesktopWindow();
    *((_QWORD *)this + 10) = g_hInstance;
    *((_DWORD *)this + 10) = 72;
    *((_DWORD *)this + 11) = 161;
    *((_QWORD *)this + 6) = DesktopWindow;
    *((_QWORD *)this + 11) = a2;
    *((_QWORD *)this + 7) = DesktopWindow;
    GetWindowRect(DesktopWindow, (LPRECT)this + 4);
    SendMessageW(Window, 0x432u, 0, (LPARAM)this + 40);
  }
  return Window;
}

```

## disassembly

```asm
0x1800cd9f8  mov     r11, rsp
0x1800cd9fb  push    rbx
0x1800cd9fc  push    rbp
0x1800cd9fd  push    rsi
0x1800cd9fe  push    rdi
0x1800cd9ff  sub     rsp, 68h
0x1800cda03  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800cda0a  xor     ebx, ebx
0x1800cda0c  mov     [r11-30h], rbx
0x1800cda10  mov     rbp, rdx
0x1800cda13  mov     [r11-38h], rax
0x1800cda17  lea     rdx, ClassName; "tooltips_class32"
0x1800cda1e  mov     [r11-40h], rbx
0x1800cda22  mov     eax, 80000000h
0x1800cda27  mov     [r11-48h], rbx
0x1800cda2b  mov     rdi, rcx
0x1800cda2e  mov     [rsp+88h+nHeight], eax; nHeight
0x1800cda32  lea     ecx, [rbx+8]; dwExStyle
0x1800cda35  mov     [rsp+88h+nWidth], eax; nWidth
0x1800cda39  mov     r9d, 80000003h; dwStyle
0x1800cda3f  mov     [rsp+88h+Y], eax; Y
0x1800cda43  xor     r8d, r8d; lpWindowName
0x1800cda46  mov     [rsp+88h+X], eax; X
0x1800cda4a  call    cs:__imp_CreateWindowExW
0x1800cda50  mov     rsi, rax
0x1800cda53  test    rax, rax
0x1800cda56  jz      short loc_1800CDAA5
0x1800cda58  call    cs:__imp_GetDesktopWindow
0x1800cda5e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800cda65  lea     rdx, [rdi+40h]; lpRect
0x1800cda69  mov     [rdi+50h], rcx
0x1800cda6d  mov     rcx, rax; hWnd
0x1800cda70  mov     dword ptr [rdi+28h], 48h ; 'H'
0x1800cda77  mov     dword ptr [rdi+2Ch], 0A1h
0x1800cda7e  mov     [rdi+30h], rax
0x1800cda82  mov     [rdi+58h], rbp
0x1800cda86  mov     [rdi+38h], rax
0x1800cda8a  call    cs:__imp_GetWindowRect
0x1800cda90  lea     r9, [rdi+28h]; lParam
0x1800cda94  xor     r8d, r8d; wParam
0x1800cda97  mov     edx, 432h; Msg
0x1800cda9c  mov     rcx, rsi; hWnd
0x1800cda9f  call    cs:__imp_SendMessageW
0x1800cdaa5  mov     rax, rsi
0x1800cdaa8  add     rsp, 68h
0x1800cdaac  pop     rdi
0x1800cdaad  pop     rsi
0x1800cdaae  pop     rbp
0x1800cdaaf  pop     rbx
0x1800cdab0  retn
```
