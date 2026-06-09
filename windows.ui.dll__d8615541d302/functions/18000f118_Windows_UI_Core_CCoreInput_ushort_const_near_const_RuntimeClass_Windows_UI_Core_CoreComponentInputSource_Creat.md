# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateNewWindow(void)

- ea: `0x18000f118`
- end: `0x18000f353`
- name: `?CreateNewWindow@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@IEAAJXZ`
- size: `571`
- prototype: `__int64 __fastcall(LPVOID lpParam)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e130`

## callees

- `0x18000f118`
- `0x1800127ec`
- `0x180012858`
- `0x180056348`
- `0x180071c60`
- `0x1800c7366`

## import_xrefs

- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000f194`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000f1a2`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000f194`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000f1a2`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x18000f1c9`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x18000f1c9`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18000f288`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18000f288`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18000f1b0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18000f1b0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000f21a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000f21a`

## string_xrefs

- `0x18000f162`: `Windows.UI.Core.CoreComponentInputSource`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::CreateNewWindow(
        _BYTE *lpParam)
{
  unsigned __int16 v2; // r8
  HWND WindowInBand; // rax
  unsigned int Error; // ebx
  __int64 v5; // rax
  int Y[2]; // [rsp+28h] [rbp-71h]
  WNDCLASSEXW v8; // [rsp+70h] [rbp-29h] BYREF

  memset_0(&v8, 0, sizeof(v8));
  v8.cbSize = 80;
  v8.cbWndExtra = 8;
  v8.lpfnWndProc = (WNDPROC)Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::WndProc;
  v8.hInstance = &_ImageBase;
  v8.lpszClassName = L"Windows.UI.Core.CoreComponentInputSource";
  v8.style = 3;
  if ( lpParam[1318] )
  {
    v8.hIconSm = 0;
    v8.hIcon = 0;
  }
  else
  {
    v8.hIcon = LoadIconW(0, (LPCWSTR)0x7F00);
    v8.hIconSm = LoadIconW(0, (LPCWSTR)0x7F00);
  }
  if ( RegisterClassExW(&v8) )
    SetClassScope(v8.lpszClassName, v8.hInstance, 2);
  if ( *((_DWORD *)lpParam + 332) )
  {
    v5 = *((_QWORD *)lpParam + 175);
    Error = -2147418113;
    if ( !v5 )
      goto LABEL_17;
    WindowInBand = (HWND)CreateWindowInBand(
                           0,
                           L"Windows.UI.Core.CoreComponentInputSource",
                           L"CoreInput",
                           1342177280,
                           0,
                           0,
                           0,
                           0,
                           v5,
                           0,
                           &_ImageBase,
                           lpParam,
                           0);
  }
  else
  {
    WindowInBand = CreateWindowExW(
                     0x8000000u,
                     L"Windows.UI.Core.CoreComponentInputSource",
                     L"CoreInput",
                     0x80000000,
                     0x80000000,
                     0x80000000,
                     0x80000000,
                     0x80000000,
                     HWND_MESSAGE,
                     0,
                     &_ImageBase,
                     lpParam);
  }
  *((_QWORD *)lpParam + 165) = WindowInBand;
  if ( WindowInBand )
  {
    Error = 0;
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids, lpParam);
    }
    return Error;
  }
  Error = ResultFromKnownLastError();
  if ( (Error & 0x80000000) == 0 )
    goto LABEL_13;
LABEL_17:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    Y[0] = Error;
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids,
      lpParam,
      *((_DWORD *)lpParam + 64),
      *(_QWORD *)Y);
  }
  Windows::UI::Core::OriginateError((Windows::UI::Core *)Error, 1005, v2);
  return Error;
}

```

## disassembly

```asm
0x18000f118  push    rbp
0x18000f11a  push    rbx
0x18000f11b  push    rsi
0x18000f11c  push    rdi
0x18000f11d  push    r14
0x18000f11f  push    r15
0x18000f121  lea     rbp, [rsp-2Fh]
0x18000f126  sub     rsp, 0C8h
0x18000f12d  mov     rdi, rcx
0x18000f130  mov     ebx, 50h ; 'P'
0x18000f135  mov     r8d, ebx; Size
0x18000f138  lea     rcx, [rbp+57h+var_80]; void *
0x18000f13c  xor     edx, edx; Val
0x18000f13e  call    memset_0
0x18000f143  xor     r14d, r14d
0x18000f146  mov     [rbp+57h+var_80.cbSize], ebx
0x18000f149  lea     rax, ?WndProc@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@KA_JPEAUHWND__@@I_K_J@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000f150  mov     [rbp+57h+var_80.cbWndExtra], 8
0x18000f157  lea     r15, __ImageBase
0x18000f15e  mov     [rbp+57h+var_80.lpfnWndProc], rax
0x18000f162  lea     rsi, ?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB; "Windows.UI.Core.CoreComponentInputSourc"...
0x18000f169  mov     [rbp+57h+var_80.hInstance], r15
0x18000f16d  mov     [rbp+57h+var_80.lpszClassName], rsi
0x18000f171  mov     [rbp+57h+var_80.style], 3
0x18000f178  cmp     [rdi+526h], r14b
0x18000f17f  jz      short loc_18000F18B
0x18000f181  mov     [rbp+57h+var_80.hIconSm], r14
0x18000f185  mov     [rbp+57h+var_80.hIcon], r14
0x18000f189  jmp     short loc_18000F1AC
0x18000f18b  mov     ebx, 7F00h
0x18000f190  xor     ecx, ecx; hInstance
0x18000f192  mov     edx, ebx; lpIconName
0x18000f194  call    cs:__imp_LoadIconW
0x18000f19a  mov     edx, ebx; lpIconName
0x18000f19c  xor     ecx, ecx; hInstance
0x18000f19e  mov     [rbp+57h+var_80.hIcon], rax
0x18000f1a2  call    cs:__imp_LoadIconW
0x18000f1a8  mov     [rbp+57h+var_80.hIconSm], rax
0x18000f1ac  lea     rcx, [rbp+57h+var_80]; WNDCLASSEXW *
0x18000f1b0  call    cs:__imp_RegisterClassExW
0x18000f1b6  test    ax, ax
0x18000f1b9  jz      short loc_18000F1CF
0x18000f1bb  mov     rdx, [rbp+57h+var_80.hInstance]
0x18000f1bf  mov     r8d, 2
0x18000f1c5  mov     rcx, [rbp+57h+var_80.lpszClassName]
0x18000f1c9  call    cs:__imp_SetClassScope
0x18000f1cf  cmp     [rdi+530h], r14d
0x18000f1d6  jnz     short loc_18000F234
0x18000f1d8  mov     [rsp+0F0h+lpParam], rdi; lpParam
0x18000f1dd  lea     r8, WindowName; "CoreInput"
0x18000f1e4  mov     [rsp+0F0h+hInstance], r15; hInstance
0x18000f1e9  mov     eax, 80000000h
0x18000f1ee  mov     [rsp+0F0h+hMenu], r14; hMenu
0x18000f1f3  mov     r9d, 80000000h; dwStyle
0x18000f1f9  mov     [rsp+0F0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18000f202  mov     rdx, rsi; lpClassName
0x18000f205  mov     [rsp+0F0h+nHeight], eax; nHeight
0x18000f209  mov     ecx, 8000000h; dwExStyle
0x18000f20e  mov     [rsp+0F0h+nWidth], eax; nWidth
0x18000f212  mov     [rsp+0F0h+Y], eax; Y
0x18000f216  mov     [rsp+0F0h+X], eax; X
0x18000f21a  call    cs:__imp_CreateWindowExW
0x18000f220  lea     rsi, [rdi+528h]
0x18000f227  mov     [rsi], rax
0x18000f22a  test    rax, rax
0x18000f22d  jz      short loc_18000F290
0x18000f22f  mov     ebx, r14d
0x18000f232  jmp     short loc_18000F29B
0x18000f234  mov     rax, [rdi+578h]
0x18000f23b  mov     ebx, 8000FFFFh
0x18000f240  test    rax, rax
0x18000f243  jz      loc_18000F2EE
0x18000f249  mov     [rsp+0F0h+var_90], r14d
0x18000f24e  lea     r8, WindowName; "CoreInput"
0x18000f255  mov     [rsp+0F0h+lpParam], rdi
0x18000f25a  mov     r9d, 50000000h
0x18000f260  mov     [rsp+0F0h+hInstance], r15
0x18000f265  mov     rdx, rsi
0x18000f268  mov     [rsp+0F0h+hMenu], r14
0x18000f26d  xor     ecx, ecx
0x18000f26f  mov     [rsp+0F0h+hWndParent], rax
0x18000f274  mov     [rsp+0F0h+nHeight], r14d
0x18000f279  mov     [rsp+0F0h+nWidth], r14d
0x18000f27e  mov     [rsp+0F0h+Y], r14d
0x18000f283  mov     [rsp+0F0h+X], r14d
0x18000f288  call    cs:__imp_CreateWindowInBand
0x18000f28e  jmp     short loc_18000F220
0x18000f290  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f295  mov     ebx, eax
0x18000f297  test    eax, eax
0x18000f299  js      short loc_18000F2EE
0x18000f29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2a2  lea     rax, WPP_GLOBAL_Control
0x18000f2a9  cmp     rcx, rax
0x18000f2ac  jz      loc_18000F341
0x18000f2b2  test    byte ptr [rcx+1Ch], 40h
0x18000f2b6  jz      loc_18000F341
0x18000f2bc  cmp     byte ptr [rcx+19h], 4
0x18000f2c0  jb      short loc_18000F341
0x18000f2c2  mov     rax, [rsi]
0x18000f2c5  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000f2cc  mov     rcx, [rcx+10h]
0x18000f2d0  mov     edx, 17h
0x18000f2d5  mov     qword ptr [rsp+0F0h+Y], rax
0x18000f2da  mov     r9, rdi
0x18000f2dd  mov     eax, [rdi+100h]
0x18000f2e3  mov     [rsp+0F0h+X], eax
0x18000f2e7  call    WPP_SF_qDq
0x18000f2ec  jmp     short loc_18000F341
0x18000f2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2f5  lea     rax, WPP_GLOBAL_Control
0x18000f2fc  cmp     rcx, rax
0x18000f2ff  jz      short loc_18000F335
0x18000f301  test    byte ptr [rcx+1Ch], 40h
0x18000f305  jz      short loc_18000F335
0x18000f307  cmp     byte ptr [rcx+19h], 4
0x18000f30b  jb      short loc_18000F335
0x18000f30d  mov     r8d, [rdi+100h]
0x18000f314  mov     edx, 18h
0x18000f319  mov     rcx, [rcx+10h]
0x18000f31d  mov     r9, rdi
0x18000f320  mov     [rsp+0F0h+Y], ebx
0x18000f324  mov     [rsp+0F0h+X], r8d
0x18000f329  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000f330  call    WPP_SF_qDD
0x18000f335  mov     edx, 3EDh; int
0x18000f33a  mov     ecx, ebx; this
0x18000f33c  call    ?OriginateError@Core@UI@Windows@@YAXJG@Z; Windows::UI::Core::OriginateError(long,ushort)
0x18000f341  mov     eax, ebx
0x18000f343  add     rsp, 0C8h
0x18000f34a  pop     r15
0x18000f34c  pop     r14
0x18000f34e  pop     rdi
0x18000f34f  pop     rsi
0x18000f350  pop     rbx
0x18000f351  pop     rbp
0x18000f352  retn
```
