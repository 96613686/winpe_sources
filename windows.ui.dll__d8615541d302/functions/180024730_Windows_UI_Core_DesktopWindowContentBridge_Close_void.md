# Windows::UI::Core::DesktopWindowContentBridge::Close(void)

- ea: `0x180024730`
- end: `0x1800249e8`
- name: `?Close@DesktopWindowContentBridge@Core@UI@Windows@@UEAAJXZ`
- size: `696`
- prototype: `int(Windows::UI::Core::DesktopWindowContentBridge *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180023f94`
- `0x180024730`
- `0x180025170`
- `0x1800251ac`
- `0x180025228`
- `0x180026aac`
- `0x180050360`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800247b0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800247b0`

## string_xrefs

- `0x18002487c`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024954`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800249a6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800249c1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800249d6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::UI::Core::DesktopWindowContentBridge::Close(
        Windows::UI::Core::DesktopWindowContentBridge *this)
{
  int v2; // eax
  unsigned int v3; // edi
  HWND v4; // rcx
  __int64 v5; // rcx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v21; // [rsp+40h] [rbp+20h] BYREF
  __int64 v22; // [rsp+48h] [rbp+28h] BYREF

  if ( (int)Windows::UI::Core::DesktopWindowContentBridge::IsValidState((Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 16)) < 0 )
    return 0;
  v2 = Windows::UI::Core::DesktopWindowContentBridge::CheckThread((Windows::UI::Core::DesktopWindowContentBridge *)((char *)this - 16));
  v3 = v2;
  if ( v2 >= 0 )
  {
    v21 = 0;
    if ( *((_QWORD *)this + 24) )
    {
      if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSite>::As<Windows::Foundation::IClosable>(
                  (char *)this + 192,
                  &v21) >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 48LL))(v21);
        v7 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 192);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 200);
    }
    if ( *((_QWORD *)this + 21) )
    {
      v22 = 0;
      v13 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironment>::As<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>(
              (char *)this + 168,
              &v22);
      if ( v13 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
          (const char *)(unsigned int)v13,
          savedregs);
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, 0);
      v10 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10D,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
          (const char *)(unsigned int)v14,
          savedregs);
        v17 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v18 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        return v10;
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 168);
      v15 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    if ( !*((_QWORD *)this + 16) )
    {
LABEL_6:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 136);
      v4 = (HWND)*((_QWORD *)this + 11);
      if ( v4 )
      {
        DestroyWindow(v4);
        *((_QWORD *)this + 11) = 0;
      }
      v5 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      return 0;
    }
    v22 = 0;
    v8 = Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(
           (char *)this + 128,
           &v22);
    if ( v8 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
        (const char *)(unsigned int)v8,
        savedregs);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 56LL))(v22, 0);
    v10 = v9;
    if ( v9 >= 0 )
    {
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 128);
      v16 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_6;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF6,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
    (const char *)(unsigned int)v2,
    savedregs);
  return v3;
}

```

## disassembly

```asm
0x180024730  mov     [rsp-18h+arg_10], rbx
0x180024735  mov     [rsp-18h+arg_18], rsi
0x18002473a  push    rbp
0x18002473b  push    rdi
0x18002473c  push    r14; int
0x18002473e  mov     rbp, rsp
0x180024741  sub     rsp, 20h
0x180024745  mov     rbx, rcx
0x180024748  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18002474c  call    ?IsValidState@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::DesktopWindowContentBridge::IsValidState(void)
0x180024751  xor     r14d, r14d
0x180024754  test    eax, eax
0x180024756  js      short loc_1800247D4
0x180024758  lea     rcx, [rbx-10h]; this
0x18002475c  call    ?CheckThread@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::DesktopWindowContentBridge::CheckThread(void)
0x180024761  mov     edi, eax
0x180024763  test    eax, eax
0x180024765  js      loc_18002499F
0x18002476b  mov     [rbp+arg_0], r14
0x18002476f  lea     rdi, [rbx+0C0h]
0x180024776  cmp     [rdi], r14
0x180024779  jnz     short loc_1800247E9
0x18002477b  lea     rdi, [rbx+0A8h]
0x180024782  cmp     [rdi], r14
0x180024785  jnz     loc_1800248C9
0x18002478b  lea     rdi, [rbx+80h]
0x180024792  cmp     [rdi], r14
0x180024795  jnz     loc_18002483D
0x18002479b  lea     rcx, [rbx+88h]
0x1800247a2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800247a7  mov     rcx, [rbx+58h]; hWnd
0x1800247ab  test    rcx, rcx
0x1800247ae  jz      short loc_1800247BA
0x1800247b0  call    cs:__imp_DestroyWindow
0x1800247b6  mov     [rbx+58h], r14
0x1800247ba  mov     rcx, [rbp+arg_0]
0x1800247be  test    rcx, rcx
0x1800247c1  jz      short loc_1800247D4
0x1800247c3  mov     [rbp+arg_0], r14
0x1800247c7  mov     rax, [rcx]
0x1800247ca  mov     rax, [rax+10h]
0x1800247ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247d3  nop
0x1800247d4  xor     eax, eax
0x1800247d6  mov     rbx, [rsp+20h+arg_10]
0x1800247db  mov     rsi, [rsp+20h+arg_18]
0x1800247e0  add     rsp, 20h
0x1800247e4  pop     r14
0x1800247e6  pop     rdi
0x1800247e7  pop     rbp
0x1800247e8  retn
0x1800247e9  lea     rdx, [rbp+arg_0]
0x1800247ed  mov     rcx, rdi
0x1800247f0  call    ??$As@UIClosable@Foundation@Windows@@@?$ComPtr@UIInputSite@Input@Internal@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIClosable@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Internal::Input::IInputSite>::As<Windows::Foundation::IClosable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IClosable>>)
0x1800247f5  test    eax, eax
0x1800247f7  js      short loc_180024824
0x1800247f9  mov     rcx, [rbp+arg_0]
0x1800247fd  mov     rax, [rcx]
0x180024800  mov     rax, [rax+30h]
0x180024804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024809  nop
0x18002480a  mov     rcx, [rbp+arg_0]
0x18002480e  test    rcx, rcx
0x180024811  jz      short loc_180024824
0x180024813  mov     [rbp+arg_0], r14
0x180024817  mov     rax, [rcx]
0x18002481a  mov     rax, [rax+10h]
0x18002481e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024823  nop
0x180024824  mov     rcx, rdi
0x180024827  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002482c  lea     rcx, [rbx+0C8h]
0x180024833  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024838  jmp     loc_18002477B
0x18002483d  mov     [rbp+arg_8], r14
0x180024841  lea     rdx, [rbp+arg_8]
0x180024845  mov     rcx, rdi
0x180024848  call    ??$As@UICompositionTargetPartner@Private@Composition@UI@Windows@@@?$ComPtr@UIDesktopWindowTarget@Desktop@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionTargetPartner@Private@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::Desktop::IDesktopWindowTarget>::As<Windows::UI::Composition::Private::ICompositionTargetPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::Private::ICompositionTargetPartner>>)
0x18002484d  mov     rcx, [rbp+18h]; this
0x180024851  test    eax, eax
0x180024853  js      loc_1800249BE
0x180024859  mov     rcx, [rbp+arg_8]
0x18002485d  mov     rax, [rcx]
0x180024860  xor     edx, edx
0x180024862  mov     rax, [rax+38h]
0x180024866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002486b  mov     esi, eax
0x18002486d  test    eax, eax
0x18002486f  jns     loc_180024925
0x180024875  mov     rcx, [rbp+18h]; this
0x180024879  mov     r9d, eax; char *
0x18002487c  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180024883  mov     edx, 118h; void *
0x180024888  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002488d  nop
0x18002488e  mov     rcx, [rbp+arg_8]
0x180024892  test    rcx, rcx
0x180024895  jz      short loc_1800248A8
0x180024897  mov     [rbp+arg_8], r14
0x18002489b  mov     rax, [rcx]
0x18002489e  mov     rax, [rax+10h]
0x1800248a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248a7  nop
0x1800248a8  mov     rcx, [rbp+arg_0]
0x1800248ac  test    rcx, rcx
0x1800248af  jz      short loc_1800248C2
0x1800248b1  mov     [rbp+arg_0], r14
0x1800248b5  mov     rax, [rcx]
0x1800248b8  mov     rax, [rax+10h]
0x1800248bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c1  nop
0x1800248c2  mov     eax, esi
0x1800248c4  jmp     loc_1800247D6
0x1800248c9  mov     [rbp+arg_8], r14
0x1800248cd  lea     rdx, [rbp+arg_8]
0x1800248d1  mov     rcx, rdi
0x1800248d4  call    ??$As@UICompositionIslandEnvironmentPartner@Composition@UI@Windows@@@?$ComPtr@UICompositionIslandEnvironment@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionIslandEnvironmentPartner@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironment>::As<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionIslandEnvironmentPartner>>)
0x1800248d9  mov     rcx, [rbp+18h]; this
0x1800248dd  test    eax, eax
0x1800248df  js      loc_1800249D3
0x1800248e5  mov     rcx, [rbp+arg_8]
0x1800248e9  mov     rax, [rcx]
0x1800248ec  xor     edx, edx
0x1800248ee  mov     rax, [rax+38h]
0x1800248f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248f7  mov     esi, eax
0x1800248f9  test    eax, eax
0x1800248fb  js      short loc_18002494D
0x1800248fd  mov     rcx, rdi
0x180024900  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180024905  nop
0x180024906  mov     rcx, [rbp+arg_8]
0x18002490a  test    rcx, rcx
0x18002490d  jz      short loc_180024920
0x18002490f  mov     [rbp+arg_8], r14
0x180024913  mov     rax, [rcx]
0x180024916  mov     rax, [rax+10h]
0x18002491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002491f  nop
0x180024920  jmp     loc_18002478B
0x180024925  mov     rcx, rdi
0x180024928  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002492d  nop
0x18002492e  mov     rcx, [rbp+arg_8]
0x180024932  test    rcx, rcx
0x180024935  jz      short loc_180024948
0x180024937  mov     [rbp+arg_8], r14
0x18002493b  mov     rax, [rcx]
0x18002493e  mov     rax, [rax+10h]
0x180024942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024947  nop
0x180024948  jmp     loc_18002479B
0x18002494d  mov     rcx, [rbp+18h]; this
0x180024951  mov     r9d, esi; char *
0x180024954  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002495b  mov     edx, 10Dh; void *
0x180024960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024965  nop
0x180024966  mov     rcx, [rbp+arg_8]
0x18002496a  test    rcx, rcx
0x18002496d  jz      short loc_180024980
0x18002496f  mov     [rbp+arg_8], r14
0x180024973  mov     rax, [rcx]
0x180024976  mov     rax, [rax+10h]
0x18002497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002497f  nop
0x180024980  mov     rcx, [rbp+arg_0]
0x180024984  test    rcx, rcx
0x180024987  jz      short loc_18002499A
0x180024989  mov     [rbp+arg_0], r14
0x18002498d  mov     rax, [rcx]
0x180024990  mov     rax, [rax+10h]
0x180024994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024999  nop
0x18002499a  jmp     loc_1800248C2
0x18002499f  mov     rcx, [rbp+18h]; this
0x1800249a3  mov     r9d, edi; char *
0x1800249a6  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800249ad  mov     edx, 0F6h; void *
0x1800249b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800249b7  mov     eax, edi
0x1800249b9  jmp     loc_1800247D6
0x1800249be  mov     r9d, eax; char *
0x1800249c1  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800249c8  mov     edx, 114h; void *
0x1800249cd  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800249d3  mov     r9d, eax; char *
0x1800249d6  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800249dd  mov     edx, 10Ah; void *
0x1800249e2  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
