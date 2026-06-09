# AccessibilityDialog::CreateParentWindow(void)

- ea: `0x14001fb44`
- end: `0x14001fcd0`
- name: `?CreateParentWindow@AccessibilityDialog@@AEAAXXZ`
- size: `396`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14001f948`
- `0x14001fb44`
- `0x140022af0`
- `0x140022dcc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001fbb8`
- `KERNEL32!GetLastError` at `0x14001fbb8`
- `USER32!MoveWindow` at `0x14001fc86`
- `USER32!MoveWindow` at `0x14001fc86`
- `USER32!IsWindow` at `0x14001fc30`
- `USER32!IsWindow` at `0x14001fc30`
- `USER32!CreateWindowExW` at `0x14001fc1d`
- `USER32!CreateWindowExW` at `0x14001fc1d`
- `USER32!RegisterClassExW` at `0x14001fba5`
- `USER32!RegisterClassExW` at `0x14001fba5`
- `dwmapi!DwmSetWindowAttribute` at `0x14001fcab`
- `dwmapi!DwmSetWindowAttribute` at `0x14001fcab`

## string_xrefs

- `0x14001fb87`: `AccessibilityDialogWindow`
- `0x14001fbcf`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x14001fc44`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
void __fastcall AccessibilityDialog::CreateParentWindow(AccessibilityDialog *this)
{
  DWORD LastError; // eax
  HWND Window; // rax
  const char *v4; // r9
  HWND v5; // rcx
  unsigned int X; // [rsp+20h] [rbp-89h]
  int pvAttribute[4]; // [rsp+60h] [rbp-49h] BYREF
  WNDCLASSEXW v8; // [rsp+70h] [rbp-39h] BYREF
  struct tagRECT v9; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  memset_0(&v8, 0, sizeof(v8));
  v8.cbSize = 80;
  v8.lpfnWndProc = (WNDPROC)AccessibilityDialog::staticWindowProc;
  v8.hInstance = (HINSTANCE)*((_QWORD *)this + 4);
  v8.lpszClassName = L"AccessibilityDialogWindow";
  v8.style = 3;
  if ( !RegisterClassExW(&v8) )
  {
    LastError = GetLastError();
    if ( LastError != 1410 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x10F,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        (const char *)LastError,
        X);
  }
  Window = CreateWindowExW(
             0x88u,
             L"AccessibilityDialogWindow",
             0,
             0x80000000,
             0,
             0,
             0,
             0,
             0,
             0,
             *((HINSTANCE *)this + 4),
             this);
  *((_QWORD *)this + 5) = Window;
  if ( !IsWindow(Window) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x122,
      (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
      v4);
  AccessibilityDialog::ComputeRectForFlyout(this, &v9);
  MoveWindow(*((HWND *)this + 5), v9.left, v9.top, v9.right - v9.left, v9.bottom - v9.top, 1);
  v5 = (HWND)*((_QWORD *)this + 5);
  pvAttribute[0] = 2;
  DwmSetWindowAttribute(v5, 0x21u, pvAttribute, 4u);
}

```

## disassembly

```asm
0x14001fb44  push    rbp
0x14001fb46  push    rbx
0x14001fb47  push    rsi
0x14001fb48  push    rdi
0x14001fb49  lea     rbp, [rsp-3Fh]
0x14001fb4e  sub     rsp, 0E8h
0x14001fb55  mov     rax, cs:__security_cookie
0x14001fb5c  xor     rax, rsp
0x14001fb5f  mov     [rbp+57h+var_30], rax
0x14001fb63  mov     rbx, rcx
0x14001fb66  mov     edi, 50h ; 'P'
0x14001fb6b  mov     r8d, edi; Size
0x14001fb6e  lea     rcx, [rbp+57h+var_90]; void *
0x14001fb72  xor     edx, edx; Val
0x14001fb74  call    memset_0
0x14001fb79  lea     rax, ?staticWindowProc@AccessibilityDialog@@CA_JPEAUHWND__@@I_K_J@Z; AccessibilityDialog::staticWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x14001fb80  mov     [rbp+57h+var_90.cbSize], edi
0x14001fb83  mov     [rbp+57h+var_90.lpfnWndProc], rax
0x14001fb87  lea     rsi, ClassName; "AccessibilityDialogWindow"
0x14001fb8e  mov     rax, [rbx+20h]
0x14001fb92  lea     rcx, [rbp+57h+var_90]; WNDCLASSEXW *
0x14001fb96  mov     [rbp+57h+var_90.hInstance], rax
0x14001fb9a  mov     [rbp+57h+var_90.lpszClassName], rsi
0x14001fb9e  mov     [rbp+57h+var_90.style], 3
0x14001fba5  call    cs:__imp_RegisterClassExW
0x14001fbac  nop     dword ptr [rax+rax+00h]
0x14001fbb1  xor     edi, edi
0x14001fbb3  test    ax, ax
0x14001fbb6  jnz     short loc_14001FBE4
0x14001fbb8  call    cs:__imp_GetLastError
0x14001fbbf  nop     dword ptr [rax+rax+00h]
0x14001fbc4  cmp     eax, 582h
0x14001fbc9  jz      short loc_14001FBE4
0x14001fbcb  mov     rcx, [rbp+5Fh]; this
0x14001fbcf  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x14001fbd6  mov     r9d, eax; char *
0x14001fbd9  mov     edx, 10Fh; void *
0x14001fbde  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14001fbe4  mov     rax, [rbx+20h]
0x14001fbe8  mov     r9d, 80000000h; dwStyle
0x14001fbee  mov     [rsp+100h+lpParam], rbx; lpParam
0x14001fbf3  xor     r8d, r8d; lpWindowName
0x14001fbf6  mov     [rsp+100h+hInstance], rax; hInstance
0x14001fbfb  mov     rdx, rsi; lpClassName
0x14001fbfe  mov     [rsp+100h+hMenu], rdi; hMenu
0x14001fc03  mov     ecx, 88h; dwExStyle
0x14001fc08  mov     [rsp+100h+hWndParent], rdi; hWndParent
0x14001fc0d  mov     [rsp+100h+nHeight], edi; nHeight
0x14001fc11  mov     [rsp+100h+nWidth], edi; nWidth
0x14001fc15  mov     [rsp+100h+Y], edi; Y
0x14001fc19  mov     [rsp+100h+X], edi; X
0x14001fc1d  call    cs:__imp_CreateWindowExW
0x14001fc24  nop     dword ptr [rax+rax+00h]
0x14001fc29  mov     rcx, rax; hWnd
0x14001fc2c  mov     [rbx+28h], rax
0x14001fc30  call    cs:__imp_IsWindow
0x14001fc37  nop     dword ptr [rax+rax+00h]
0x14001fc3c  test    eax, eax
0x14001fc3e  jnz     short loc_14001FC56
0x14001fc40  mov     rcx, [rbp+5Fh]; this
0x14001fc44  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x14001fc4b  mov     edx, 122h; void *
0x14001fc50  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x14001fc56  lea     rdx, [rbp+57h+var_40]; retstr
0x14001fc5a  mov     rcx, rbx; this
0x14001fc5d  call    ?ComputeRectForFlyout@AccessibilityDialog@@AEAA?AUtagRECT@@XZ; AccessibilityDialog::ComputeRectForFlyout(void)
0x14001fc62  mov     eax, [rbp+57h+var_40.bottom]
0x14001fc65  mov     r8d, [rbp+57h+var_40.top]; Y
0x14001fc69  sub     eax, r8d
0x14001fc6c  mov     r9d, [rbp+57h+var_40.right]
0x14001fc70  mov     edx, [rbp+57h+var_40.left]; X
0x14001fc73  sub     r9d, edx; nWidth
0x14001fc76  mov     rcx, [rbx+28h]; hWnd
0x14001fc7a  mov     [rsp+100h+Y], 1; bRepaint
0x14001fc82  mov     [rsp+100h+X], eax; nHeight
0x14001fc86  call    cs:__imp_MoveWindow
0x14001fc8d  nop     dword ptr [rax+rax+00h]
0x14001fc92  mov     rcx, [rbx+28h]; hwnd
0x14001fc96  lea     r8, [rbp+57h+pvAttribute]; pvAttribute
0x14001fc9a  mov     r9d, 4; cbAttribute
0x14001fca0  mov     [rbp+57h+pvAttribute], 2
0x14001fca7  lea     edx, [r9+1Dh]; dwAttribute
0x14001fcab  call    cs:__imp_DwmSetWindowAttribute
0x14001fcb2  nop     dword ptr [rax+rax+00h]
0x14001fcb7  mov     rcx, [rbp+57h+var_30]
0x14001fcbb  xor     rcx, rsp; StackCookie
0x14001fcbe  call    __security_check_cookie
0x14001fcc3  add     rsp, 0E8h
0x14001fcca  pop     rdi
0x14001fccb  pop     rsi
0x14001fccc  pop     rbx
0x14001fccd  pop     rbp
0x14001fcce  retn
```
