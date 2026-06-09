# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateNewWindow(void)

- ea: `0x18000eb04`
- end: `0x18000ed3f`
- name: `?CreateNewWindow@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@IEAAJXZ`
- size: `571`
- prototype: `__int64 __fastcall(LPVOID lpParam)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e620`

## callees

- `0x18000eb04`
- `0x1800127ec`
- `0x180012858`
- `0x180056348`
- `0x180071c60`
- `0x1800c7366`

## import_xrefs

- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000eb80`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000eb8e`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000eb80`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18000eb8e`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x18000ebb5`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x18000ebb5`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18000ec74`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18000ec74`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18000eb9c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x18000eb9c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000ec06`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000ec06`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::CreateNewWindow(
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
  v8.lpfnWndProc = (WNDPROC)Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::WndProc;
  v8.hInstance = &_ImageBase;
  v8.lpszClassName = L"Windows.UI.Core.CoreIndependentInputSource";
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
                           L"Windows.UI.Core.CoreIndependentInputSource",
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
                     L"Windows.UI.Core.CoreIndependentInputSource",
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
0x18000eb04  push    rbp
0x18000eb06  push    rbx
0x18000eb07  push    rsi
0x18000eb08  push    rdi
0x18000eb09  push    r14
0x18000eb0b  push    r15
0x18000eb0d  lea     rbp, [rsp-2Fh]
0x18000eb12  sub     rsp, 0C8h
0x18000eb19  mov     rdi, rcx
0x18000eb1c  mov     ebx, 50h ; 'P'
0x18000eb21  mov     r8d, ebx; Size
0x18000eb24  lea     rcx, [rbp+57h+var_80]; void *
0x18000eb28  xor     edx, edx; Val
0x18000eb2a  call    memset_0
0x18000eb2f  xor     r14d, r14d
0x18000eb32  mov     [rbp+57h+var_80.cbSize], ebx
0x18000eb35  lea     rax, ?WndProc@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@KA_JPEAUHWND__@@I_K_J@Z; Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000eb3c  mov     [rbp+57h+var_80.cbWndExtra], 8
0x18000eb43  lea     r15, __ImageBase
0x18000eb4a  mov     [rbp+57h+var_80.lpfnWndProc], rax
0x18000eb4e  lea     rsi, ?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB; "Windows.UI.Core.CoreIndependentInputSou"...
0x18000eb55  mov     [rbp+57h+var_80.hInstance], r15
0x18000eb59  mov     [rbp+57h+var_80.lpszClassName], rsi
0x18000eb5d  mov     [rbp+57h+var_80.style], 3
0x18000eb64  cmp     [rdi+526h], r14b
0x18000eb6b  jz      short loc_18000EB77
0x18000eb6d  mov     [rbp+57h+var_80.hIconSm], r14
0x18000eb71  mov     [rbp+57h+var_80.hIcon], r14
0x18000eb75  jmp     short loc_18000EB98
0x18000eb77  mov     ebx, 7F00h
0x18000eb7c  xor     ecx, ecx; hInstance
0x18000eb7e  mov     edx, ebx; lpIconName
0x18000eb80  call    cs:__imp_LoadIconW
0x18000eb86  mov     edx, ebx; lpIconName
0x18000eb88  xor     ecx, ecx; hInstance
0x18000eb8a  mov     [rbp+57h+var_80.hIcon], rax
0x18000eb8e  call    cs:__imp_LoadIconW
0x18000eb94  mov     [rbp+57h+var_80.hIconSm], rax
0x18000eb98  lea     rcx, [rbp+57h+var_80]; WNDCLASSEXW *
0x18000eb9c  call    cs:__imp_RegisterClassExW
0x18000eba2  test    ax, ax
0x18000eba5  jz      short loc_18000EBBB
0x18000eba7  mov     rdx, [rbp+57h+var_80.hInstance]
0x18000ebab  mov     r8d, 2
0x18000ebb1  mov     rcx, [rbp+57h+var_80.lpszClassName]
0x18000ebb5  call    cs:__imp_SetClassScope
0x18000ebbb  cmp     [rdi+530h], r14d
0x18000ebc2  jnz     short loc_18000EC20
0x18000ebc4  mov     [rsp+0F0h+lpParam], rdi; lpParam
0x18000ebc9  lea     r8, WindowName; "CoreInput"
0x18000ebd0  mov     [rsp+0F0h+hInstance], r15; hInstance
0x18000ebd5  mov     eax, 80000000h
0x18000ebda  mov     [rsp+0F0h+hMenu], r14; hMenu
0x18000ebdf  mov     r9d, 80000000h; dwStyle
0x18000ebe5  mov     [rsp+0F0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18000ebee  mov     rdx, rsi; lpClassName
0x18000ebf1  mov     [rsp+0F0h+nHeight], eax; nHeight
0x18000ebf5  mov     ecx, 8000000h; dwExStyle
0x18000ebfa  mov     [rsp+0F0h+nWidth], eax; nWidth
0x18000ebfe  mov     [rsp+0F0h+Y], eax; Y
0x18000ec02  mov     [rsp+0F0h+X], eax; X
0x18000ec06  call    cs:__imp_CreateWindowExW
0x18000ec0c  lea     rsi, [rdi+528h]
0x18000ec13  mov     [rsi], rax
0x18000ec16  test    rax, rax
0x18000ec19  jz      short loc_18000EC7C
0x18000ec1b  mov     ebx, r14d
0x18000ec1e  jmp     short loc_18000EC87
0x18000ec20  mov     rax, [rdi+578h]
0x18000ec27  mov     ebx, 8000FFFFh
0x18000ec2c  test    rax, rax
0x18000ec2f  jz      loc_18000ECDA
0x18000ec35  mov     [rsp+0F0h+var_90], r14d
0x18000ec3a  lea     r8, WindowName; "CoreInput"
0x18000ec41  mov     [rsp+0F0h+lpParam], rdi
0x18000ec46  mov     r9d, 50000000h
0x18000ec4c  mov     [rsp+0F0h+hInstance], r15
0x18000ec51  mov     rdx, rsi
0x18000ec54  mov     [rsp+0F0h+hMenu], r14
0x18000ec59  xor     ecx, ecx
0x18000ec5b  mov     [rsp+0F0h+hWndParent], rax
0x18000ec60  mov     [rsp+0F0h+nHeight], r14d
0x18000ec65  mov     [rsp+0F0h+nWidth], r14d
0x18000ec6a  mov     [rsp+0F0h+Y], r14d
0x18000ec6f  mov     [rsp+0F0h+X], r14d
0x18000ec74  call    cs:__imp_CreateWindowInBand
0x18000ec7a  jmp     short loc_18000EC0C
0x18000ec7c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000ec81  mov     ebx, eax
0x18000ec83  test    eax, eax
0x18000ec85  js      short loc_18000ECDA
0x18000ec87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec8e  lea     rax, WPP_GLOBAL_Control
0x18000ec95  cmp     rcx, rax
0x18000ec98  jz      loc_18000ED2D
0x18000ec9e  test    byte ptr [rcx+1Ch], 40h
0x18000eca2  jz      loc_18000ED2D
0x18000eca8  cmp     byte ptr [rcx+19h], 4
0x18000ecac  jb      short loc_18000ED2D
0x18000ecae  mov     rax, [rsi]
0x18000ecb1  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000ecb8  mov     rcx, [rcx+10h]
0x18000ecbc  mov     edx, 17h
0x18000ecc1  mov     qword ptr [rsp+0F0h+Y], rax
0x18000ecc6  mov     r9, rdi
0x18000ecc9  mov     eax, [rdi+100h]
0x18000eccf  mov     [rsp+0F0h+X], eax
0x18000ecd3  call    WPP_SF_qDq
0x18000ecd8  jmp     short loc_18000ED2D
0x18000ecda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ece1  lea     rax, WPP_GLOBAL_Control
0x18000ece8  cmp     rcx, rax
0x18000eceb  jz      short loc_18000ED21
0x18000eced  test    byte ptr [rcx+1Ch], 40h
0x18000ecf1  jz      short loc_18000ED21
0x18000ecf3  cmp     byte ptr [rcx+19h], 4
0x18000ecf7  jb      short loc_18000ED21
0x18000ecf9  mov     r8d, [rdi+100h]
0x18000ed00  mov     edx, 18h
0x18000ed05  mov     rcx, [rcx+10h]
0x18000ed09  mov     r9, rdi
0x18000ed0c  mov     [rsp+0F0h+Y], ebx
0x18000ed10  mov     [rsp+0F0h+X], r8d
0x18000ed15  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18000ed1c  call    WPP_SF_qDD
0x18000ed21  mov     edx, 3EDh; int
0x18000ed26  mov     ecx, ebx; this
0x18000ed28  call    ?OriginateError@Core@UI@Windows@@YAXJG@Z; Windows::UI::Core::OriginateError(long,ushort)
0x18000ed2d  mov     eax, ebx
0x18000ed2f  add     rsp, 0C8h
0x18000ed36  pop     r15
0x18000ed38  pop     r14
0x18000ed3a  pop     rdi
0x18000ed3b  pop     rsi
0x18000ed3c  pop     rbx
0x18000ed3d  pop     rbp
0x18000ed3e  retn
```
