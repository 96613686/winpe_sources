# Windows::UI::Core::DesktopWindowContentBridge::CreateHwnd(HWND__ *)

- ea: `0x18002606c`
- end: `0x180026371`
- name: `?CreateHwnd@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJPEAUHWND__@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, HWND hWndParent)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025870`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x18002606c`
- `0x18003c6dc`
- `0x18004fc30`
- `0x180050360`
- `0x1800581b8`
- `0x1800c7366`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800260e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800260e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026097`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002614a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002614a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800262f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800262f9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800261b3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800261b3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180026205`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180026205`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoExW` at `0x1800260c8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoExW` at `0x1800260c8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180026219`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180026219`

## string_xrefs

- `0x1800260f4`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800261c6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180026278`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180026291`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180026323`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180026351`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800260b4`: `Windows.UI.Composition.DesktopWindowContentBridge`
- `0x18002633d`: `The caller must specify an HWND created on the same thread as the Compositor, and be calling from that thread.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Core::DesktopWindowContentBridge::CreateHwnd(LONG_PTR dwNewLong, HWND hWndParent)
{
  const char *v4; // r9
  int v6; // eax
  DWORD CurrentThreadId; // eax
  HWND Window; // rax
  const char *v9; // r9
  unsigned int LastError; // ebx
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, LONG_PTR); // rdi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int X; // [rsp+20h] [rbp-59h]
  int Xa; // [rsp+20h] [rbp-59h]
  const char *Y; // [rsp+28h] [rbp-51h]
  struct tagWNDCLASSEXW wcx; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v22; // [rsp+F0h] [rbp+77h] BYREF

  AcquireSRWLockExclusive(&Windows::UI::Core::DesktopWindowContentBridge::s_lockClass);
  memset_0(&wcx, 0, sizeof(wcx));
  if ( !GetClassInfoExW(&_ImageBase, L"Windows.UI.Composition.DesktopWindowContentBridge", &wcx) )
  {
    memset_0(&wcx, 0, sizeof(wcx));
    wcx.cbSize = 80;
    wcx.cbWndExtra = 0;
    wcx.hbrBackground = 0;
    wcx.hInstance = &_ImageBase;
    wcx.lpfnWndProc = (WNDPROC)Windows::UI::Core::DesktopWindowContentBridge::IslandWindowProc;
    wcx.lpszClassName = L"Windows.UI.Composition.DesktopWindowContentBridge";
    wcx.style = 3;
    Windows::UI::Core::DesktopWindowContentBridge::s_shellAtomClass = RegisterClassExW(&wcx);
  }
  ReleaseSRWLockExclusive(&Windows::UI::Core::DesktopWindowContentBridge::s_lockClass);
  if ( !Windows::UI::Core::DesktopWindowContentBridge::s_shellAtomClass )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x154,
             (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
             v4);
  if ( !hWndParent )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)0x80070057LL,
      (int)"The caller must specify an HWND when not using CoreWindow",
      Y);
    return LastError;
  }
  v22 = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>(
         dwNewLong + 136,
         &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v6,
      X);
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(dwNewLong + 112) = CurrentThreadId;
  if ( (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, CurrentThreadId) < 0 )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)0x80070057LL,
      (int)"The caller must specify an HWND created on the same thread as the Compositor, and be calling from that thread.",
      Y);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
    return LastError;
  }
  Window = CreateWindowExW(
             0x200000u,
             (LPCWSTR)Windows::UI::Core::DesktopWindowContentBridge::s_shellAtomClass,
             L"DesktopWindowXamlSource",
             0x40000000u,
             0,
             0,
             0,
             0,
             hWndParent,
             0,
             &_ImageBase,
             (LPVOID)dwNewLong);
  *(_QWORD *)(dwNewLong + 104) = Window;
  if ( !Window )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x174,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
                  v9);
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return LastError;
  }
  SetWindowLongPtrW(Window, -21, dwNewLong);
  SetPropW(*(HWND *)(dwNewLong + 104), L"MSCTFMSAAIgnore", 0);
  v12 = v22;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LONG_PTR))(*(_QWORD *)v22 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(dwNewLong + 144);
  v14 = v13(v12, *(_QWORD *)(dwNewLong + 104), 0, dwNewLong + 144);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v14,
      Xa);
    v16 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return LastError;
  }
  v15 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18002606c  mov     [rsp-8+arg_0], rbx
0x180026071  mov     [rsp-8+arg_8], rsi
0x180026076  push    rbp
0x180026077  push    rdi
0x180026078  push    r12
0x18002607a  push    r14
0x18002607c  push    r15
0x18002607e  lea     rbp, [rsp-37h]
0x180026083  sub     rsp, 0B0h
0x18002608a  mov     rbx, rdx
0x18002608d  mov     r14, rcx
0x180026090  lea     rcx, ?s_lockClass@DesktopWindowContentBridge@Core@UI@Windows@@0U_RTL_SRWLOCK@@A; SRWLock
0x180026097  call    cs:__imp_AcquireSRWLockExclusive
0x18002609d  mov     edi, 50h ; 'P'
0x1800260a2  mov     r8d, edi; Size
0x1800260a5  xor     edx, edx; Val
0x1800260a7  lea     rcx, [rbp+57h+wcx]; void *
0x1800260ab  call    memset_0
0x1800260b0  lea     r8, [rbp+57h+wcx]; lpwcx
0x1800260b4  lea     r12, szClass; "Windows.UI.Composition.DesktopWindowCon"...
0x1800260bb  mov     rdx, r12; lpszClass
0x1800260be  lea     rsi, __ImageBase
0x1800260c5  mov     rcx, rsi; hInstance
0x1800260c8  call    cs:__imp_GetClassInfoExW
0x1800260ce  xor     r15d, r15d
0x1800260d1  test    eax, eax
0x1800260d3  jz      loc_1800262C2
0x1800260d9  lea     rcx, ?s_lockClass@DesktopWindowContentBridge@Core@UI@Windows@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800260e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800260e6  cmp     cs:?s_shellAtomClass@DesktopWindowContentBridge@Core@UI@Windows@@0GA, r15w; ushort Windows::UI::Core::DesktopWindowContentBridge::s_shellAtomClass
0x1800260ee  jnz     short loc_180026121
0x1800260f0  mov     rcx, [rbp+5Fh]; this
0x1800260f4  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800260fb  mov     edx, 154h; void *
0x180026100  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026105  lea     r11, [rsp+0D0h+var_20]
0x18002610d  mov     rbx, [r11+30h]
0x180026111  mov     rsi, [r11+38h]
0x180026115  mov     rsp, r11
0x180026118  pop     r15
0x18002611a  pop     r14
0x18002611c  pop     r12
0x18002611e  pop     rdi
0x18002611f  pop     rbp
0x180026120  retn
0x180026121  test    rbx, rbx
0x180026124  jz      loc_18002630B
0x18002612a  mov     [rbp+57h+arg_10], r15
0x18002612e  lea     rcx, [r14+88h]
0x180026135  lea     rdx, [rbp+57h+arg_10]
0x180026139  call    ??$As@UICompositorDesktopInterop@Desktop@Composition@UI@Windows@@@?$ComPtr@UICompositor@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositorDesktopInterop@Desktop@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositor>::As<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::ICompositorDesktopInterop>>)
0x18002613e  mov     rcx, [rbp+5Fh]; this
0x180026142  test    eax, eax
0x180026144  js      loc_180026275
0x18002614a  call    cs:__imp_GetCurrentThreadId
0x180026150  mov     r8d, eax
0x180026153  mov     [r14+70h], eax
0x180026157  mov     rcx, [rbp+57h+arg_10]
0x18002615b  mov     rdx, [rcx]
0x18002615e  mov     rax, [rdx+20h]
0x180026162  mov     edx, r8d
0x180026165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002616a  test    eax, eax
0x18002616c  js      loc_180026339
0x180026172  movzx   edx, cs:?s_shellAtomClass@DesktopWindowContentBridge@Core@UI@Windows@@0GA; lpClassName
0x180026179  mov     [rsp+0D0h+lpParam], r14; lpParam
0x18002617e  mov     [rsp+0D0h+hInstance], rsi; hInstance
0x180026183  mov     [rsp+0D0h+hMenu], r15; hMenu
0x180026188  mov     [rsp+0D0h+hWndParent], rbx; hWndParent
0x18002618d  mov     [rsp+0D0h+nHeight], r15d; nHeight
0x180026192  mov     [rsp+0D0h+nWidth], r15d; nWidth
0x180026197  mov     dword ptr [rsp+0D0h+Y], r15d; Y
0x18002619c  mov     [rsp+0D0h+X], r15d; int
0x1800261a1  mov     r9d, 40000000h; dwStyle
0x1800261a7  lea     r8, aDesktopwindowx; "DesktopWindowXamlSource"
0x1800261ae  mov     ecx, 200000h; dwExStyle
0x1800261b3  call    cs:__imp_CreateWindowExW
0x1800261b9  mov     [r14+68h], rax
0x1800261bd  test    rax, rax
0x1800261c0  jnz     short loc_1800261FA
0x1800261c2  mov     rcx, [rbp+5Fh]; this
0x1800261c6  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800261cd  mov     edx, 174h; void *
0x1800261d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800261d7  mov     ebx, eax
0x1800261d9  mov     rcx, [rbp+57h+arg_10]
0x1800261dd  test    rcx, rcx
0x1800261e0  jz      short loc_1800261F3
0x1800261e2  mov     [rbp+57h+arg_10], r15
0x1800261e6  mov     rdx, [rcx]
0x1800261e9  mov     rax, [rdx+10h]
0x1800261ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261f2  nop
0x1800261f3  mov     eax, ebx
0x1800261f5  jmp     loc_180026105
0x1800261fa  mov     r8, r14; dwNewLong
0x1800261fd  mov     edx, 0FFFFFFEBh; nIndex
0x180026202  mov     rcx, rax; hWnd
0x180026205  call    cs:__imp_SetWindowLongPtrW
0x18002620b  xor     r8d, r8d; hData
0x18002620e  lea     rdx, aMsctfmsaaignor; "MSCTFMSAAIgnore"
0x180026215  mov     rcx, [r14+68h]; hWnd
0x180026219  call    cs:__imp_SetPropW
0x18002621f  mov     rsi, [rbp+57h+arg_10]
0x180026223  mov     rax, [rsi]
0x180026226  mov     rdi, [rax+18h]
0x18002622a  lea     rbx, [r14+90h]
0x180026231  mov     rcx, rbx
0x180026234  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180026239  mov     r9, rbx
0x18002623c  xor     r8d, r8d
0x18002623f  mov     rdx, [r14+68h]
0x180026243  mov     rcx, rsi
0x180026246  mov     rax, rdi
0x180026249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002624e  mov     ebx, eax
0x180026250  test    eax, eax
0x180026252  js      short loc_18002628A
0x180026254  mov     rcx, [rbp+57h+arg_10]
0x180026258  test    rcx, rcx
0x18002625b  jz      short loc_18002626E
0x18002625d  mov     [rbp+57h+arg_10], r15
0x180026261  mov     rax, [rcx]
0x180026264  mov     rax, [rax+10h]
0x180026268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002626d  nop
0x18002626e  xor     eax, eax
0x180026270  jmp     loc_180026105
0x180026275  mov     r9d, eax; char *
0x180026278  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002627f  mov     edx, 15Ah; void *
0x180026284  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002628a  mov     rcx, [rbp+5Fh]; this
0x18002628e  mov     r9d, ebx; char *
0x180026291  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180026298  mov     edx, 17Eh; void *
0x18002629d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262a2  nop
0x1800262a3  mov     rcx, [rbp+57h+arg_10]
0x1800262a7  test    rcx, rcx
0x1800262aa  jz      short loc_1800262BD
0x1800262ac  mov     [rbp+57h+arg_10], r15
0x1800262b0  mov     rax, [rcx]
0x1800262b3  mov     rax, [rax+10h]
0x1800262b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262bc  nop
0x1800262bd  jmp     loc_1800261F3
0x1800262c2  mov     r8, rdi; Size
0x1800262c5  xor     edx, edx; Val
0x1800262c7  lea     rcx, [rbp+57h+wcx]; void *
0x1800262cb  call    memset_0
0x1800262d0  mov     [rbp+57h+wcx.cbSize], edi
0x1800262d3  mov     [rbp+57h+wcx.cbWndExtra], r15d
0x1800262d7  mov     [rbp+57h+wcx.hbrBackground], r15
0x1800262db  mov     [rbp+57h+wcx.hInstance], rsi
0x1800262df  lea     rax, ?IslandWindowProc@DesktopWindowContentBridge@Core@UI@Windows@@CA_JPEAUHWND__@@I_K_J@Z; Windows::UI::Core::DesktopWindowContentBridge::IslandWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800262e6  mov     [rbp+57h+wcx.lpfnWndProc], rax
0x1800262ea  mov     [rbp+57h+wcx.lpszClassName], r12
0x1800262ee  mov     [rbp+57h+wcx.style], 3
0x1800262f5  lea     rcx, [rbp+57h+wcx]; WNDCLASSEXW *
0x1800262f9  call    cs:__imp_RegisterClassExW
0x1800262ff  mov     cs:?s_shellAtomClass@DesktopWindowContentBridge@Core@UI@Windows@@0GA, ax; ushort Windows::UI::Core::DesktopWindowContentBridge::s_shellAtomClass
0x180026306  jmp     loc_1800260D9
0x18002630b  mov     rcx, [rbp+5Fh]; this
0x18002630f  lea     rax, aTheCallerMustS; "The caller must specify an HWND when no"...
0x180026316  mov     qword ptr [rsp+0D0h+X], rax; int
0x18002631b  mov     ebx, 80070057h
0x180026320  mov     r9d, ebx; char *
0x180026323  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002632a  mov     edx, 157h; void *
0x18002632f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026334  jmp     loc_1800261F3
0x180026339  mov     rcx, [rbp+5Fh]; this
0x18002633d  lea     rax, aTheCallerMustS_0; "The caller must specify an HWND created"...
0x180026344  mov     qword ptr [rsp+0D0h+X], rax; int
0x180026349  mov     ebx, 80070057h
0x18002634e  mov     r9d, ebx; char *
0x180026351  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180026358  mov     edx, 163h; void *
0x18002635d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180026362  nop
0x180026363  lea     rcx, [rbp+57h+arg_10]
0x180026367  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002636c  jmp     loc_1800261F3
```
