# Windows::UI::Core::WindowServer::CreateNewWindow(ulong,ushort const *,ulong,Windows::Foundation::Rect,ZBID,ulong)

- ea: `0x180013830`
- end: `0x180013b41`
- name: `?CreateNewWindow@WindowServer@Core@UI@Windows@@QEAAJKPEBGKURect@Foundation@4@W4ZBID@@K@Z`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d010`

## callees

- `0x1800127ec`
- `0x180012858`
- `0x180013830`
- `0x1800146fc`
- `0x18006c524`
- `0x18007f61c`
- `0x18007f7a0`
- `0x1800c7366`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ac1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ac1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800139c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800139c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a9e`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800138b3`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800138c1`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800138b3`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1800138c1`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x1800138e8`
- `ext-ms-win-rtcore-minuser-private-ext-l1-1-0!SetClassScope` at `0x1800138e8`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013915`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001399d`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013915`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001399d`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBandEx` at `0x180013990`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBandEx` at `0x180013990`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800138cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800138cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x180013a8a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x180013a8a`

## string_xrefs

- `0x1800139b2`: `user32.dll`
- `0x180013af8`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
signed int __fastcall Windows::UI::Core::WindowServer::CreateNewWindow(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        float *a5,
        int a6,
        int a7)
{
  char v11; // si
  const char *v12; // r9
  __int64 v13; // rdi
  HMODULE ModuleHandleW; // rax
  int v15; // edi
  Windows::UI::Core *v16; // rcx
  signed int result; // eax
  int Error; // eax
  unsigned __int16 v19; // r8
  FARPROC ProcAddress; // rax
  WNDCLASSEXW v21; // [rsp+70h] [rbp-51h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  memset_0(&v21, 0, sizeof(v21));
  v21.cbSize = 80;
  v21.lpfnWndProc = (WNDPROC)Windows::UI::Core::WindowServer::WndProc;
  v21.cbWndExtra = 40;
  v21.hInstance = &_ImageBase;
  v21.lpszClassName = L"Windows.UI.Core.CoreWindow";
  v21.style = 3;
  if ( *(_BYTE *)(a1 + 2172) )
  {
    v21.hIconSm = 0;
    v21.hIcon = 0;
  }
  else
  {
    v21.hIcon = LoadIconW(0, (LPCWSTR)0x7F00);
    v21.hIconSm = LoadIconW(0, (LPCWSTR)0x7F00);
  }
  if ( RegisterClassExW(&v21) )
    SetClassScope(v21.lpszClassName, v21.hInstance, 2);
  if ( !Windows::UI::Core::WindowServer::s_wmWindowPositionChanged )
  {
    Windows::UI::Core::WindowServer::s_wmWindowPositionChanged = RegisterWindowMessageW(L"{24CF051B-7E9E-4730-9B52-78E64066EE6A}");
    if ( !Windows::UI::Core::WindowServer::s_wmWindowPositionChanged )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_850f2c403a353c03d19f0821ea469488_Traceguids,
      a3,
      a6);
  }
  v11 = 1;
  if ( (unsigned int)IsOneCoreTransformMode() )
    *(_BYTE *)(a1 + 2672) = 1;
  *(_QWORD *)(a1 + 3464) = CreateWindowInBandEx(
                             a2 | 0x200000u,
                             L"Windows.UI.Core.CoreWindow",
                             a3,
                             a4,
                             (int)*a5,
                             (int)a5[1],
                             (int)a5[2],
                             (int)a5[3],
                             0,
                             0,
                             &_ImageBase,
                             a1,
                             a6,
                             a7,
                             *(_QWORD *)&v21.cbSize,
                             v21.lpfnWndProc);
  if ( (unsigned int)IsOneCoreTransformMode() )
  {
    if ( !*(_BYTE *)(a1 + 2672) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6CA,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        v12);
    *(_BYTE *)(a1 + 2672) = 0;
  }
  v13 = *(_QWORD *)(a1 + 3464);
  *(_QWORD *)(a1 + 2696) = v13;
  ModuleHandleW = GetModuleHandleW(L"user32.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, (LPCSTR)0xA0B);
    if ( ProcAddress )
      ((void (__fastcall *)(__int64, __int64))ProcAddress)(v13, 1);
  }
  if ( *(_QWORD *)(a1 + 3464) )
  {
    v15 = 0;
LABEL_13:
    v16 = (Windows::UI::Core *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_850f2c403a353c03d19f0821ea469488_Traceguids,
        *(_QWORD *)(a1 + 3464));
    }
    goto LABEL_15;
  }
  Error = ResultFromKnownLastError();
  v15 = Error;
  if ( Error >= 0 )
    goto LABEL_13;
  Windows::UI::Core::OriginateError((Windows::UI::Core *)(unsigned int)Error, 1005, v19);
LABEL_15:
  if ( Windows::UI::Core::GetDpiForThread(v16) == 0.0 )
    v11 = 0;
  *(_BYTE *)(a1 + 2173) = v11;
  return v15;
}

```

## disassembly

```asm
0x180013830  push    rbp
0x180013832  push    rbx
0x180013833  push    rsi
0x180013834  push    rdi
0x180013835  push    r12
0x180013837  push    r13
0x180013839  push    r14
0x18001383b  push    r15
0x18001383d  lea     rbp, [rsp-7]
0x180013842  sub     rsp, 0C8h
0x180013849  mov     r14, r8
0x18001384c  mov     r15d, edx
0x18001384f  mov     rbx, rcx
0x180013852  mov     edi, 50h ; 'P'
0x180013857  mov     r8d, edi; Size
0x18001385a  lea     rcx, [rbp+3Fh+var_90]; void *
0x18001385e  xor     edx, edx; Val
0x180013860  mov     r12d, r9d
0x180013863  call    memset_0
0x180013868  lea     rax, ?WndProc@WindowServer@Core@UI@Windows@@CA_JPEAUHWND__@@I_K_J@Z; Windows::UI::Core::WindowServer::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001386f  mov     [rbp+3Fh+var_90.cbSize], edi
0x180013872  mov     [rbp+3Fh+var_90.lpfnWndProc], rax
0x180013876  xor     r13d, r13d
0x180013879  lea     rax, __ImageBase
0x180013880  mov     [rbp+3Fh+var_90.cbWndExtra], 28h ; '('
0x180013887  mov     [rbp+3Fh+var_90.hInstance], rax
0x18001388b  lea     rax, ClassName; "Windows.UI.Core.CoreWindow"
0x180013892  mov     [rbp+3Fh+var_90.lpszClassName], rax
0x180013896  mov     [rbp+3Fh+var_90.style], 3
0x18001389d  cmp     [rbx+87Ch], r13b
0x1800138a4  jnz     loc_180013A41
0x1800138aa  mov     edi, 7F00h
0x1800138af  xor     ecx, ecx; hInstance
0x1800138b1  mov     edx, edi; lpIconName
0x1800138b3  call    cs:__imp_LoadIconW
0x1800138b9  mov     edx, edi; lpIconName
0x1800138bb  xor     ecx, ecx; hInstance
0x1800138bd  mov     [rbp+3Fh+var_90.hIcon], rax
0x1800138c1  call    cs:__imp_LoadIconW
0x1800138c7  mov     [rbp+3Fh+var_90.hIconSm], rax
0x1800138cb  lea     rcx, [rbp+3Fh+var_90]; WNDCLASSEXW *
0x1800138cf  call    cs:__imp_RegisterClassExW
0x1800138d5  test    ax, ax
0x1800138d8  jz      short loc_1800138EE
0x1800138da  mov     rdx, [rbp+3Fh+var_90.hInstance]
0x1800138de  mov     r8d, 2
0x1800138e4  mov     rcx, [rbp+3Fh+var_90.lpszClassName]
0x1800138e8  call    cs:__imp_SetClassScope
0x1800138ee  cmp     cs:?s_wmWindowPositionChanged@WindowServer@Core@UI@Windows@@2IA, r13d; uint Windows::UI::Core::WindowServer::s_wmWindowPositionChanged
0x1800138f5  jz      loc_180013A83
0x1800138fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180013902  lea     rax, WPP_GLOBAL_Control
0x180013909  mov     edi, [rbp+3Fh+arg_28]
0x18001390c  cmp     rcx, rax
0x18001390f  jnz     loc_180013A4E
0x180013915  call    cs:__imp_IsOneCoreTransformMode
0x18001391b  mov     esi, 1
0x180013920  test    eax, eax
0x180013922  jnz     loc_180013ADF
0x180013928  mov     rax, [rbp+3Fh+arg_20]
0x18001392c  lea     rdx, ClassName; "Windows.UI.Core.CoreWindow"
0x180013933  bts     r15d, 15h
0x180013938  cvttss2si ecx, dword ptr [rax+0Ch]
0x18001393d  cvttss2si r8d, dword ptr [rax+8]
0x180013943  cvttss2si r9d, dword ptr [rax+4]
0x180013949  cvttss2si r10d, dword ptr [rax]
0x18001394e  mov     eax, [rbp+3Fh+arg_30]
0x180013951  mov     [rsp+100h+var_98], eax
0x180013955  lea     rax, __ImageBase
0x18001395c  mov     [rsp+100h+var_A0], edi
0x180013960  mov     [rsp+100h+var_A8], rbx
0x180013965  mov     [rsp+100h+var_B0], rax
0x18001396a  mov     [rsp+100h+var_B8], r13
0x18001396f  mov     [rsp+100h+var_C0], r13
0x180013974  mov     [rsp+100h+var_C8], ecx
0x180013978  mov     ecx, r15d
0x18001397b  mov     [rsp+100h+var_D0], r8d
0x180013980  mov     r8, r14
0x180013983  mov     [rsp+100h+var_D8], r9d
0x180013988  mov     r9d, r12d
0x18001398b  mov     [rsp+100h+var_E0], r10d
0x180013990  call    cs:__imp_CreateWindowInBandEx
0x180013996  mov     [rbx+0D88h], rax
0x18001399d  call    cs:__imp_IsOneCoreTransformMode
0x1800139a3  test    eax, eax
0x1800139a5  jnz     loc_180013AEB
0x1800139ab  mov     rdi, [rbx+0D88h]
0x1800139b2  lea     rcx, ModuleName; "user32.dll"
0x1800139b9  mov     [rbx+0A88h], rdi
0x1800139c0  call    cs:__imp_GetModuleHandleW
0x1800139c6  test    rax, rax
0x1800139c9  jnz     loc_180013AB9
0x1800139cf  cmp     [rbx+0D88h], r13
0x1800139d6  jz      short loc_180013A28
0x1800139d8  mov     edi, r13d
0x1800139db  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800139e2  lea     rax, WPP_GLOBAL_Control
0x1800139e9  cmp     rcx, rax
0x1800139ec  jz      short loc_1800139F8
0x1800139ee  test    byte ptr [rcx+1Ch], 2
0x1800139f2  jnz     loc_180013B16
0x1800139f8  call    ?GetDpiForThread@Core@UI@Windows@@YAMXZ; Windows::UI::Core::GetDpiForThread(void)
0x1800139fd  ucomiss xmm0, cs:__real@00000000
0x180013a04  jp      short loc_180013A0B
0x180013a06  jnz     short loc_180013A0B
0x180013a08  mov     sil, r13b
0x180013a0b  mov     [rbx+87Dh], sil
0x180013a12  mov     eax, edi
0x180013a14  add     rsp, 0C8h
0x180013a1b  pop     r15
0x180013a1d  pop     r14
0x180013a1f  pop     r13
0x180013a21  pop     r12
0x180013a23  pop     rdi
0x180013a24  pop     rsi
0x180013a25  pop     rbx
0x180013a26  pop     rbp
0x180013a27  retn
0x180013a28  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013a2d  mov     edi, eax
0x180013a2f  test    eax, eax
0x180013a31  jns     short loc_1800139DB
0x180013a33  mov     edx, 3EDh; int
0x180013a38  mov     ecx, eax; this
0x180013a3a  call    ?OriginateError@Core@UI@Windows@@YAXJG@Z; Windows::UI::Core::OriginateError(long,ushort)
0x180013a3f  jmp     short loc_1800139F8
0x180013a41  mov     [rbp+3Fh+var_90.hIconSm], r13
0x180013a45  mov     [rbp+3Fh+var_90.hIcon], r13
0x180013a49  jmp     loc_1800138CB
0x180013a4e  test    byte ptr [rcx+1Ch], 2
0x180013a52  jz      loc_180013915
0x180013a58  cmp     byte ptr [rcx+19h], 2
0x180013a5c  jb      loc_180013915
0x180013a62  mov     rcx, [rcx+10h]
0x180013a66  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x180013a6d  mov     edx, 14h
0x180013a72  mov     [rsp+100h+var_E0], edi
0x180013a76  mov     r9, r14
0x180013a79  call    WPP_SF_Sd
0x180013a7e  jmp     loc_180013915
0x180013a83  lea     rcx, a24cf051b7e9e47; "{24CF051B-7E9E-4730-9B52-78E64066EE6A}"
0x180013a8a  call    cs:__imp_RegisterWindowMessageW
0x180013a90  mov     cs:?s_wmWindowPositionChanged@WindowServer@Core@UI@Windows@@2IA, eax; uint Windows::UI::Core::WindowServer::s_wmWindowPositionChanged
0x180013a96  test    eax, eax
0x180013a98  jnz     loc_1800138FB
0x180013a9e  call    cs:__imp_GetLastError
0x180013aa4  test    eax, eax
0x180013aa6  jle     loc_180013A14
0x180013aac  movzx   eax, ax
0x180013aaf  or      eax, 80070000h
0x180013ab4  jmp     loc_180013A14
0x180013ab9  mov     edx, 0A0Bh; lpProcName
0x180013abe  mov     rcx, rax; hModule
0x180013ac1  call    cs:__imp_GetProcAddress
0x180013ac7  test    rax, rax
0x180013aca  jz      loc_1800139CF
0x180013ad0  mov     edx, esi
0x180013ad2  mov     rcx, rdi
0x180013ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ada  jmp     loc_1800139CF
0x180013adf  mov     [rbx+0A70h], sil
0x180013ae6  jmp     loc_180013928
0x180013aeb  cmp     [rbx+0A70h], r13b
0x180013af2  jnz     short loc_180013B0A
0x180013af4  mov     rcx, [rbp+47h]; this
0x180013af8  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180013aff  mov     edx, 6CAh; void *
0x180013b04  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013b0a  mov     [rbx+0A70h], r13b
0x180013b11  jmp     loc_1800139AB
0x180013b16  cmp     byte ptr [rcx+19h], 4
0x180013b1a  jb      loc_1800139F8
0x180013b20  mov     r9, [rbx+0D88h]
0x180013b27  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x180013b2e  mov     rcx, [rcx+10h]
0x180013b32  mov     edx, 15h
0x180013b37  call    WPP_SF_q
0x180013b3c  jmp     loc_1800139F8
```
