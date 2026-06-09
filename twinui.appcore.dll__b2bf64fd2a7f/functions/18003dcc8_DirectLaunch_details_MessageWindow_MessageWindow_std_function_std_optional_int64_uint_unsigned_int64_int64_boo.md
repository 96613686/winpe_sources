# DirectLaunch::details::MessageWindow::MessageWindow(std::function<std::optional<__int64> (uint,unsigned __int64,__int64)> &&,bool)

- ea: `0x18003dcc8`
- end: `0x18003de17`
- name: `??0MessageWindow@details@DirectLaunch@@QEAA@$$QEAV?$function@$$A6A?AV?$optional@_J@std@@I_K_J@Z@std@@_N@Z`
- size: `335`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003cb8c`

## callees

- `0x18002b1b0`
- `0x18002bc68`
- `0x18003a1a8`
- `0x18003dcc8`
- `0x180043bf8`
- `0x180045080`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003dde8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003dde8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18003dd54`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18003dd54`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18003dda5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18003dda5`

## string_xrefs

- `0x18003ddcb`: `onecoreuap\shell\SrcPkg\DirectLaunch\inc\DirectLaunchCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG_PTR __fastcall DirectLaunch::details::MessageWindow::MessageWindow(LONG_PTR dwNewLong)
{
  HWND Window; // rax
  WNDCLASSEXW v4; // [rsp+70h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *(_QWORD *)dwNewLong = 0;
  *(_QWORD *)(dwNewLong + 64) = 0;
  std::_Func_class<std::optional<__int64>,unsigned int,unsigned __int64,__int64>::_Reset_move();
  memset_0(&v4, 0, sizeof(v4));
  v4.cbSize = 80;
  v4.lpfnWndProc = (WNDPROC)DirectLaunch::details::MessageWindow::MessageWndProc;
  v4.hInstance = &_ImageBase;
  v4.lpszClassName = L"MessageWindowClass";
  RegisterClassExW(&v4);
  Window = CreateWindowExW(0, L"MessageWindowClass", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, &_ImageBase, 0);
  wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&int DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(
    dwNewLong,
    Window);
  if ( !*(_QWORD *)dwNewLong )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\shell\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchCommon.h",
      (const char *)retaddr);
  SetWindowLongPtrW(*(HWND *)dwNewLong, -21, dwNewLong);
  return dwNewLong;
}

```

## disassembly

```asm
0x18003dcc8  mov     [rsp+arg_10], rbx
0x18003dccd  mov     [rsp+arg_18], rsi
0x18003dcd2  push    rdi
0x18003dcd3  sub     rsp, 0D0h
0x18003dcda  mov     rax, cs:__security_cookie
0x18003dce1  xor     rax, rsp
0x18003dce4  mov     [rsp+0D8h+var_18], rax
0x18003dcec  mov     rbx, rcx
0x18003dcef  mov     [rsp+0D8h+var_78], rcx
0x18003dcf4  mov     qword ptr [rcx], 0
0x18003dcfb  add     rcx, 8
0x18003dcff  mov     qword ptr [rcx+38h], 0
0x18003dd07  call    ?_Reset_move@?$_Func_class@V?$optional@_J@std@@I_K_J@std@@IEAAX$$QEAV12@@Z; std::_Func_class<std::optional<__int64>,uint,unsigned __int64,__int64>::_Reset_move(std::_Func_class<std::optional<__int64>,uint,unsigned __int64,__int64> &&)
0x18003dd0c  nop
0x18003dd0d  mov     edi, 50h ; 'P'
0x18003dd12  mov     r8d, edi; Size
0x18003dd15  xor     edx, edx; Val
0x18003dd17  lea     rcx, [rsp+0D8h+var_68]; void *
0x18003dd1c  call    memset_0
0x18003dd21  mov     [rsp+0D8h+var_68.cbSize], edi
0x18003dd25  lea     rax, ?MessageWndProc@MessageWindow@details@DirectLaunch@@CA_JPEAUHWND__@@I_K_J@Z; DirectLaunch::details::MessageWindow::MessageWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18003dd2c  mov     [rsp+0D8h+var_68.lpfnWndProc], rax
0x18003dd31  lea     rdi, __ImageBase
0x18003dd38  mov     [rsp+0D8h+var_68.hInstance], rdi
0x18003dd40  lea     rsi, ClassName; "MessageWindowClass"
0x18003dd47  mov     [rsp+0D8h+var_68.lpszClassName], rsi
0x18003dd4f  lea     rcx, [rsp+0D8h+var_68]; WNDCLASSEXW *
0x18003dd54  call    cs:__imp_RegisterClassExW
0x18003dd5a  mov     [rsp+0D8h+lpParam], 0; lpParam
0x18003dd63  mov     [rsp+0D8h+hInstance], rdi; hInstance
0x18003dd68  mov     [rsp+0D8h+hMenu], 0; hMenu
0x18003dd71  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18003dd7a  mov     [rsp+0D8h+nHeight], 0; nHeight
0x18003dd82  mov     [rsp+0D8h+nWidth], 0; nWidth
0x18003dd8a  mov     [rsp+0D8h+Y], 0; Y
0x18003dd92  mov     [rsp+0D8h+X], 0; X
0x18003dd9a  xor     r9d, r9d; dwStyle
0x18003dd9d  xor     r8d, r8d; lpWindowName
0x18003dda0  mov     rdx, rsi; lpClassName
0x18003dda3  xor     ecx, ecx; dwExStyle
0x18003dda5  call    cs:__imp_CreateWindowExW
0x18003ddab  mov     rdx, rax
0x18003ddae  mov     rcx, rbx
0x18003ddb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHWND__@@P6AHPEAU1@@Z$1?DestroyWindow@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHWND__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(HWND__ *)
0x18003ddb6  mov     rcx, [rbx]; hWnd
0x18003ddb9  test    rcx, rcx
0x18003ddbc  setz    al
0x18003ddbf  mov     r9, [rsp+0D8h]; char *
0x18003ddc7  test    al, al
0x18003ddc9  jz      short loc_18003DDE0
0x18003ddcb  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\SrcPkg\\DirectLaunch"...
0x18003ddd2  mov     edx, 55h ; 'U'; void *
0x18003ddd7  mov     rcx, r9; this
0x18003ddda  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003dde0  mov     r8, rbx; dwNewLong
0x18003dde3  mov     edx, 0FFFFFFEBh; nIndex
0x18003dde8  call    cs:__imp_SetWindowLongPtrW
0x18003ddee  nop
0x18003ddef  mov     rax, rbx
0x18003ddf2  mov     rcx, [rsp+0D8h+var_18]
0x18003ddfa  xor     rcx, rsp; StackCookie
0x18003ddfd  call    __security_check_cookie
0x18003de02  lea     r11, [rsp+0D8h+var_8]
0x18003de0a  mov     rbx, [r11+20h]
0x18003de0e  mov     rsi, [r11+28h]
0x18003de12  mov     rsp, r11
0x18003de15  pop     rdi
0x18003de16  retn
```
