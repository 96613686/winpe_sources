# InteractiveObjectDeviceManagerServer::CreateMessageOnlyWindow(void)

- ea: `0x1800b446c`
- end: `0x1800b4594`
- name: `?CreateMessageOnlyWindow@InteractiveObjectDeviceManagerServer@@AEAAJXZ`
- size: `296`
- prototype: `__int64 __fastcall(InteractiveObjectDeviceManagerServer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b56b0`

## callees

- `0x180004dd4`
- `0x1800581b8`
- `0x1800585d0`
- `0x1800b446c`
- `0x1800c7366`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800b44d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800b44d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800b4541`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800b4541`

## pseudocode

```c
__int64 __fastcall InteractiveObjectDeviceManagerServer::CreateMessageOnlyWindow(
        InteractiveObjectDeviceManagerServer *this)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  WNDCLASSEXW v5; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  InteractiveObjectDeviceManagerServer *v7; // [rsp+E0h] [rbp+8h] BYREF

  if ( !InteractiveObjectDeviceManagerServer::s_atomClass )
  {
    memset_0(&v5, 0, sizeof(v5));
    v5.cbSize = 80;
    v5.lpfnWndProc = (WNDPROC)InteractiveObjectDeviceManagerServer::WndProc;
    v5.cbWndExtra = 8;
    v5.hInstance = &_ImageBase;
    v5.lpszClassName = L"InteractiveObjectDeviceManagerServer";
    InteractiveObjectDeviceManagerServer::s_atomClass = RegisterClassExW(&v5);
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v7 = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(&v7);
    if ( !CreateWindowExW(
            0x8000000u,
            L"InteractiveObjectDeviceManagerServer",
            L"WndProcListner",
            0x80000000,
            0x80000000,
            0x80000000,
            0x80000000,
            0x80000000,
            HWND_MESSAGE,
            0,
            &_ImageBase,
            this) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x67A,
                    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\radialdevice\\lib\\interactiveobject.cpp",
                    v2);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v7);
      return LastError;
    }
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b446c  push    rbx
0x1800b446e  push    rbp
0x1800b446f  push    rsi
0x1800b4470  push    r14
0x1800b4472  sub     rsp, 0B8h
0x1800b4479  xor     esi, esi
0x1800b447b  lea     r14, __ImageBase
0x1800b4482  cmp     cs:?s_atomClass@InteractiveObjectDeviceManagerServer@@0GA, si; ushort InteractiveObjectDeviceManagerServer::s_atomClass
0x1800b4489  lea     rbp, aInteractiveobj; "InteractiveObjectDeviceManagerServer"
0x1800b4490  mov     rbx, rcx
0x1800b4493  jnz     short loc_1800B44E0
0x1800b4495  xor     edx, edx; Val
0x1800b4497  lea     r8d, [rsi+50h]; Size
0x1800b449b  lea     rcx, [rsp+0D8h+var_78]; void *
0x1800b44a0  call    memset_0
0x1800b44a5  lea     rax, ?WndProc@InteractiveObjectDeviceManagerServer@@CA_JPEAUHWND__@@I_K_J@Z; InteractiveObjectDeviceManagerServer::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800b44ac  mov     [rsp+0D8h+var_78.cbSize], 50h ; 'P'
0x1800b44b4  lea     rcx, [rsp+0D8h+var_78]; WNDCLASSEXW *
0x1800b44b9  mov     [rsp+0D8h+var_78.lpfnWndProc], rax
0x1800b44be  mov     [rsp+0D8h+var_78.cbWndExtra], 8
0x1800b44c6  mov     [rsp+0D8h+var_78.hInstance], r14
0x1800b44cb  mov     [rsp+0D8h+var_78.lpszClassName], rbp
0x1800b44d3  call    cs:__imp_RegisterClassExW
0x1800b44d9  mov     cs:?s_atomClass@InteractiveObjectDeviceManagerServer@@0GA, ax; ushort InteractiveObjectDeviceManagerServer::s_atomClass
0x1800b44e0  cmp     [rbx+48h], rsi
0x1800b44e4  jnz     loc_1800B4585
0x1800b44ea  lea     rcx, [rsp+0D8h+arg_0]
0x1800b44f2  mov     [rsp+0D8h+arg_0], rbx
0x1800b44fa  call    ?InternalAddRef@?$ComPtr@U?$ITypedEventHandler@PEAVUISettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(void)
0x1800b44ff  mov     [rsp+0D8h+lpParam], rbx; lpParam
0x1800b4504  lea     r8, aWndproclistner; "WndProcListner"
0x1800b450b  mov     [rsp+0D8h+hInstance], r14; hInstance
0x1800b4510  mov     eax, 80000000h
0x1800b4515  mov     [rsp+0D8h+hMenu], rsi; hMenu
0x1800b451a  mov     r9d, 80000000h; dwStyle
0x1800b4520  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1800b4529  mov     rdx, rbp; lpClassName
0x1800b452c  mov     [rsp+0D8h+nHeight], eax; nHeight
0x1800b4530  mov     ecx, 8000000h; dwExStyle
0x1800b4535  mov     [rsp+0D8h+nWidth], eax; nWidth
0x1800b4539  mov     [rsp+0D8h+Y], eax; Y
0x1800b453d  mov     [rsp+0D8h+X], eax; X
0x1800b4541  call    cs:__imp_CreateWindowExW
0x1800b4547  test    rax, rax
0x1800b454a  jnz     short loc_1800B4578
0x1800b454c  mov     rcx, [rsp+0D8h]; this
0x1800b4554  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\advcore\\winrt\\ra"...
0x1800b455b  mov     edx, 67Ah; void *
0x1800b4560  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b4565  lea     rcx, [rsp+0D8h+arg_0]
0x1800b456d  mov     ebx, eax
0x1800b456f  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800b4574  mov     eax, ebx
0x1800b4576  jmp     short loc_1800B4587
0x1800b4578  lea     rcx, [rsp+0D8h+arg_0]
0x1800b4580  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800b4585  xor     eax, eax
0x1800b4587  add     rsp, 0B8h
0x1800b458e  pop     r14
0x1800b4590  pop     rsi
0x1800b4591  pop     rbp
0x1800b4592  pop     rbx
0x1800b4593  retn
```
