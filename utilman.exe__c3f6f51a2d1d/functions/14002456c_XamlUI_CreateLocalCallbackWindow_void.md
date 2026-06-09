# XamlUI::CreateLocalCallbackWindow(void)

- ea: `0x14002456c`
- end: `0x1400246a8`
- name: `?CreateLocalCallbackWindow@XamlUI@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHWND__@@P6AHPEAU1@@Z$1?DestroyWindow@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `316`
- prototype: `__int64 __fastcall(LPVOID lpParam)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001ebcc`

## callees

- `0x140002fa0`
- `0x140022af0`
- `0x140022dcc`
- `0x14002456c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400245e5`
- `KERNEL32!GetLastError` at `0x1400245e5`
- `KERNEL32!GetModuleHandleW` at `0x1400245ac`
- `KERNEL32!GetModuleHandleW` at `0x140024617`
- `KERNEL32!GetModuleHandleW` at `0x1400245ac`
- `KERNEL32!GetModuleHandleW` at `0x140024617`
- `USER32!IsWindow` at `0x14002466b`
- `USER32!IsWindow` at `0x14002466b`
- `USER32!CreateWindowExW` at `0x140024659`
- `USER32!CreateWindowExW` at `0x140024659`
- `USER32!RegisterClassExW` at `0x1400245d4`
- `USER32!RegisterClassExW` at `0x1400245d4`

## string_xrefs

- `0x140024600`: `enduser\ezap\xamlcommon\xamlui.cpp`
- `0x140024683`: `enduser\ezap\xamlcommon\xamlui.cpp`
- `0x1400245b8`: `AccessibilityXamlUICallbackWindowClass`

## pseudocode

```c
HWND *__fastcall XamlUI::CreateLocalCallbackWindow(LPVOID lpParam, HWND *a2)
{
  DWORD LastError; // eax
  HMODULE hInstance; // rax
  HWND Window; // rdi
  const char *v7; // r9
  unsigned int X; // [rsp+20h] [rbp-C8h]
  WNDCLASSEXW v10; // [rsp+70h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  memset_0(&v10, 0, sizeof(v10));
  v10.cbSize = 80;
  v10.lpfnWndProc = (WNDPROC)XamlUI::s_windowProc;
  v10.style = 3;
  v10.hInstance = GetModuleHandleW(0);
  v10.lpszClassName = L"AccessibilityXamlUICallbackWindowClass";
  if ( !RegisterClassExW(&v10) )
  {
    LastError = GetLastError();
    if ( LastError != 1410 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xD9,
        (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
        (const char *)LastError,
        X);
  }
  hInstance = GetModuleHandleW(0);
  Window = CreateWindowExW(
             0,
             L"AccessibilityXamlUICallbackWindowClass",
             0,
             0xCF0000u,
             0,
             0,
             0,
             0,
             HWND_MESSAGE,
             0,
             hInstance,
             lpParam);
  if ( !IsWindow(Window) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xEB,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v7);
  *a2 = Window;
  return a2;
}

```

## disassembly

```asm
0x14002456c  push    rbx
0x14002456e  push    rbp
0x14002456f  push    rsi
0x140024570  push    rdi
0x140024571  sub     rsp, 0C8h
0x140024578  mov     rbx, rdx
0x14002457b  mov     rdi, rcx
0x14002457e  xor     ebp, ebp
0x140024580  lea     rcx, [rsp+0E8h+var_78]; void *
0x140024585  xor     edx, edx; Val
0x140024587  lea     esi, [rbp+50h]
0x14002458a  mov     r8d, esi; Size
0x14002458d  call    memset_0
0x140024592  lea     rax, ?s_windowProc@XamlUI@@CA_JPEAUHWND__@@I_K_J@Z; XamlUI::s_windowProc(HWND__ *,uint,unsigned __int64,__int64)
0x140024599  mov     [rsp+0E8h+var_78.cbSize], esi
0x14002459d  xor     ecx, ecx; lpModuleName
0x14002459f  mov     [rsp+0E8h+var_78.lpfnWndProc], rax
0x1400245a4  mov     [rsp+0E8h+var_78.style], 3
0x1400245ac  call    cs:__imp_GetModuleHandleW
0x1400245b3  nop     dword ptr [rax+rax+00h]
0x1400245b8  lea     rsi, aAccessibilityx; "AccessibilityXamlUICallbackWindowClass"
0x1400245bf  mov     [rsp+0E8h+var_78.hInstance], rax
0x1400245c7  lea     rcx, [rsp+0E8h+var_78]; WNDCLASSEXW *
0x1400245cc  mov     [rsp+0E8h+var_78.lpszClassName], rsi
0x1400245d4  call    cs:__imp_RegisterClassExW
0x1400245db  nop     dword ptr [rax+rax+00h]
0x1400245e0  test    ax, ax
0x1400245e3  jnz     short loc_140024615
0x1400245e5  call    cs:__imp_GetLastError
0x1400245ec  nop     dword ptr [rax+rax+00h]
0x1400245f1  cmp     eax, 582h
0x1400245f6  jz      short loc_140024615
0x1400245f8  mov     rcx, [rsp+0E8h]; this
0x140024600  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140024607  mov     r9d, eax; char *
0x14002460a  mov     edx, 0D9h; void *
0x14002460f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140024615  xor     ecx, ecx; lpModuleName
0x140024617  call    cs:__imp_GetModuleHandleW
0x14002461e  nop     dword ptr [rax+rax+00h]
0x140024623  mov     [rsp+0E8h+lpParam], rdi; lpParam
0x140024628  mov     r9d, 0CF0000h; dwStyle
0x14002462e  mov     [rsp+0E8h+hInstance], rax; hInstance
0x140024633  xor     r8d, r8d; lpWindowName
0x140024636  mov     [rsp+0E8h+hMenu], rbp; hMenu
0x14002463b  mov     rdx, rsi; lpClassName
0x14002463e  mov     [rsp+0E8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x140024647  xor     ecx, ecx; dwExStyle
0x140024649  mov     [rsp+0E8h+nHeight], ebp; nHeight
0x14002464d  mov     [rsp+0E8h+nWidth], ebp; nWidth
0x140024651  mov     [rsp+0E8h+Y], ebp; Y
0x140024655  mov     [rsp+0E8h+X], ebp; X
0x140024659  call    cs:__imp_CreateWindowExW
0x140024660  nop     dword ptr [rax+rax+00h]
0x140024665  mov     rcx, rax; hWnd
0x140024668  mov     rdi, rax
0x14002466b  call    cs:__imp_IsWindow
0x140024672  nop     dword ptr [rax+rax+00h]
0x140024677  test    eax, eax
0x140024679  jnz     short loc_140024695
0x14002467b  mov     rcx, [rsp+0E8h]; this
0x140024683  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x14002468a  mov     edx, 0EBh; void *
0x14002468f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140024695  mov     [rbx], rdi
0x140024698  mov     rax, rbx
0x14002469b  add     rsp, 0C8h
0x1400246a2  pop     rdi
0x1400246a3  pop     rsi
0x1400246a4  pop     rbp
0x1400246a5  pop     rbx
0x1400246a6  retn
```
