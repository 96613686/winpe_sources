# CLightDismissClientStore::_UpdateOverlayRegion(void)

- ea: `0x180017980`
- end: `0x180017e6b`
- name: `?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ`
- size: `1259`
- prototype: `__int64 __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `8`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800169b8`
- `0x180016ac0`
- `0x180017910`
- `0x180017eb0`
- `0x18002f670`
- `0x1800476b0`
- `0x180084120`
- `0x1800842f4`

## callees

- `0x180017980`
- `0x180017e80`
- `0x18001907c`
- `0x180019218`
- `0x1800279d0`
- `0x1800307fc`
- `0x180049824`
- `0x180054130`
- `0x18008449c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d38`
- `USER32!IsRectEmpty` at `0x180017c5c`
- `USER32!IsRectEmpty` at `0x180017c5c`
- `USER32!GetWindowRgn` at `0x180017c43`
- `USER32!GetWindowRgn` at `0x180017c43`
- `USER32!SetWindowRgn` at `0x180017e4a`
- `USER32!SetWindowRgn` at `0x180017e4a`
- `USER32!GetSystemMetrics` at `0x1800179af`
- `USER32!GetSystemMetrics` at `0x1800179c2`
- `USER32!GetSystemMetrics` at `0x1800179dc`
- `USER32!GetSystemMetrics` at `0x1800179f3`
- `USER32!GetSystemMetrics` at `0x180017a06`
- `USER32!GetSystemMetrics` at `0x180017a20`
- `USER32!GetSystemMetrics` at `0x180017a39`
- `USER32!GetSystemMetrics` at `0x180017a4c`
- `USER32!GetSystemMetrics` at `0x180017a66`
- `USER32!GetSystemMetrics` at `0x1800179af`
- `USER32!GetSystemMetrics` at `0x1800179c2`
- `USER32!GetSystemMetrics` at `0x1800179dc`
- `USER32!GetSystemMetrics` at `0x1800179f3`
- `USER32!GetSystemMetrics` at `0x180017a06`
- `USER32!GetSystemMetrics` at `0x180017a20`
- `USER32!GetSystemMetrics` at `0x180017a39`
- `USER32!GetSystemMetrics` at `0x180017a4c`
- `USER32!GetSystemMetrics` at `0x180017a66`
- `USER32!GetPropW` at `0x180017d81`
- `USER32!GetPropW` at `0x180017d81`
- `USER32!GetWindowRect` at `0x180017c13`
- `USER32!GetWindowRect` at `0x180017c9b`
- `USER32!GetWindowRect` at `0x180017c13`
- `USER32!GetWindowRect` at `0x180017c9b`
- `USER32!GetWindow` at `0x180017bc6`
- `USER32!GetWindow` at `0x180017bc6`
- `USER32!DestroyWindow` at `0x180017e0b`
- `USER32!DestroyWindow` at `0x180017e0b`
- `GDI32!CreateRectRgn` at `0x180017c29`
- `GDI32!CreateRectRgn` at `0x180017c29`
- `GDI32!OffsetRgn` at `0x180017da0`
- `GDI32!OffsetRgn` at `0x180017e30`
- `GDI32!OffsetRgn` at `0x180017da0`
- `GDI32!OffsetRgn` at `0x180017e30`
- `GDI32!CreateRectRgnIndirect` at `0x180017a96`
- `GDI32!CreateRectRgnIndirect` at `0x180017db5`
- `GDI32!CreateRectRgnIndirect` at `0x180017a96`
- `GDI32!CreateRectRgnIndirect` at `0x180017db5`
- `GDI32!CombineRgn` at `0x180017cc5`
- `GDI32!CombineRgn` at `0x180017cc5`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::_UpdateOverlayRegion(CLightDismissClientStore *this)
{
  int SystemMetrics; // ebx
  int v3; // eax
  int v4; // ecx
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // ebx
  int v9; // eax
  int v10; // ecx
  unsigned __int64 v11; // rdx
  signed int Overlay; // ebx
  __int64 v13; // rdi
  unsigned __int64 i; // r8
  __int64 v15; // rax
  signed int v16; // eax
  bool v18; // zf
  __int64 v19; // rcx
  HWND v20; // rcx
  __int64 j; // r14
  HWND v22; // rdi
  HWND Window; // r15
  HWND Owner; // rdi
  HRGN RectRgn; // rax
  HRGN v26; // rax
  int v27; // edx
  int v28; // ecx
  signed int LastError; // eax
  int v30; // edx
  unsigned int v31; // r8d
  signed int v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  HRGN v35; // r14
  int v36; // eax
  HRGN v37; // r8
  __int64 v38; // [rsp+28h] [rbp-31h]
  void **v39; // [rsp+30h] [rbp-29h] BYREF
  HRGN hrgnSrc1; // [rsp+38h] [rbp-21h]
  void **v41; // [rsp+40h] [rbp-19h] BYREF
  HRGN hrgn; // [rsp+48h] [rbp-11h]
  void **v43; // [rsp+50h] [rbp-9h] BYREF
  HRGN hrgnSrc2; // [rsp+58h] [rbp-1h]
  struct tagRECT Rect; // [rsp+60h] [rbp+7h] BYREF
  RECT rect; // [rsp+70h] [rbp+17h] BYREF

  rect = 0;
  SystemMetrics = GetSystemMetrics(77);
  v3 = GetSystemMetrics(76);
  v4 = 76;
  if ( v3 >= SystemMetrics )
    v4 = 77;
  rect.left = GetSystemMetrics(v4);
  rect.top = rect.left;
  v5 = GetSystemMetrics(79);
  v6 = GetSystemMetrics(78);
  v7 = 78;
  if ( v6 <= v5 )
    v7 = 79;
  rect.right = rect.left + GetSystemMetrics(v7);
  v8 = GetSystemMetrics(79);
  v9 = GetSystemMetrics(78);
  v10 = 78;
  if ( v9 <= v8 )
    v10 = 79;
  rect.bottom = rect.top + GetSystemMetrics(v10);
  hrgnSrc1 = CreateRectRgnIndirect(&rect);
  v39 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
  if ( hrgnSrc1 )
  {
    v11 = *((_QWORD *)this + 12);
    Overlay = 0;
    v13 = 0;
    if ( v11 )
    {
      for ( i = 0; i < v11; ++i )
      {
        v15 = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * i);
        if ( v15 )
        {
          do
          {
            v18 = (*(_BYTE *)v15 & 2) == 0;
            v19 = v15;
            v15 = *(_QWORD *)(v15 + 56);
            if ( v18 )
              v19 = v13;
            v13 = v19;
          }
          while ( v15 );
          if ( v19 )
            break;
        }
      }
    }
    v20 = (HWND)*((_QWORD *)this + 4);
    if ( !v13 )
    {
      if ( v20 )
      {
        DestroyWindow(v20);
        *((_QWORD *)this + 4) = 0;
      }
      goto LABEL_35;
    }
    if ( !v20 )
      Overlay = CLightDismissClientStore::_CreateOverlay(this);
    if ( *((_DWORD *)this + 39) )
    {
      if ( Overlay < 0 )
        goto LABEL_19;
      goto LABEL_35;
    }
    if ( Overlay < 0 )
      goto LABEL_19;
    for ( j = v13; *(_QWORD *)(j + 56); j = *(_QWORD *)(j + 56) )
      ;
    v22 = *(HWND *)(v13 + 8);
    Window = GetWindow(v22, 4u);
    if ( !Window )
      Window = (HWND)GetPropW(v22, L"Shell_Logical_Owner_Window_Prop");
    Owner = *(HWND *)(j + 8);
    if ( !Owner )
    {
LABEL_35:
      if ( *((_QWORD *)this + 4) )
      {
        OffsetRgn(hrgnSrc1, -rect.left, -rect.top);
        v36 = SetWindowRgn(*((HWND *)this + 4), hrgnSrc1, 1);
        v37 = hrgnSrc1;
        if ( v36 )
          v37 = 0;
        hrgnSrc1 = v37;
      }
      CLightDismissClientStore::_UpdateOverlayVisibility(this);
      goto LABEL_19;
    }
    while ( 1 )
    {
      if ( Owner == Window )
        goto LABEL_35;
      Rect = 0;
      GetWindowRect(Owner, &Rect);
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      hrgn = RectRgn;
      if ( (unsigned int)GetWindowRgn(Owner, RectRgn) > 1 )
      {
        OffsetRgn(hrgn, Rect.left, Rect.top);
      }
      else if ( !IsRectEmpty(&Rect) )
      {
        v35 = CreateRectRgnIndirect(&Rect);
        v26 = hrgn;
        if ( v35 != hrgn )
        {
          Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::Close(&v41);
          v26 = v35;
        }
        goto LABEL_41;
      }
      v26 = hrgn;
LABEL_41:
      hrgn = 0;
      v41 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      v43 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      hrgnSrc2 = v26;
      if ( v26 )
      {
        Rect = 0;
        GetWindowRect(Owner, &Rect);
        if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        {
          LODWORD(v38) = Rect.bottom;
          McTemplateU0dddd_EventWriteTransfer(v28, v27, Rect.left, Rect.top, Rect.right, v38, v39);
        }
        CombineRgn(hrgnSrc1, hrgnSrc1, hrgnSrc2, 4);
      }
      Owner = (HWND)anonymous_namespace_::GetOwner(Owner);
      v43 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      if ( hrgnSrc2 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(&v43) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v30, v31);
          __debugbreak();
        }
        hrgnSrc2 = 0;
      }
      if ( !Owner )
        goto LABEL_35;
    }
  }
  v16 = GetLastError();
  Overlay = v16;
  if ( v16 > 0 )
    Overlay = (unsigned __int16)v16 | 0x80070000;
  if ( Overlay >= 0 )
    Overlay = -2147467259;
LABEL_19:
  v39 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
  if ( hrgnSrc1
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(&v39) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
    __debugbreak();
  }
  return (unsigned int)Overlay;
}

```

## disassembly

```asm
0x180017980  push    rbp
0x180017982  push    rbx
0x180017983  push    rsi
0x180017984  push    r12
0x180017986  lea     rbp, [rsp-3Fh]
0x18001798b  sub     rsp, 98h
0x180017992  mov     rax, cs:__security_cookie
0x180017999  xor     rax, rsp
0x18001799c  mov     [rbp+57h+var_30], rax
0x1800179a0  mov     rsi, rcx
0x1800179a3  xorps   xmm0, xmm0
0x1800179a6  mov     ecx, 4Dh ; 'M'; nIndex
0x1800179ab  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800179af  call    cs:__imp_GetSystemMetrics
0x1800179b6  nop     dword ptr [rax+rax+00h]
0x1800179bb  mov     ecx, 4Ch ; 'L'; nIndex
0x1800179c0  mov     ebx, eax
0x1800179c2  call    cs:__imp_GetSystemMetrics
0x1800179c9  nop     dword ptr [rax+rax+00h]
0x1800179ce  mov     ecx, 4Ch ; 'L'
0x1800179d3  cmp     eax, ebx
0x1800179d5  jl      short loc_1800179DC
0x1800179d7  mov     ecx, 4Dh ; 'M'; nIndex
0x1800179dc  call    cs:__imp_GetSystemMetrics
0x1800179e3  nop     dword ptr [rax+rax+00h]
0x1800179e8  mov     ecx, 4Fh ; 'O'; nIndex
0x1800179ed  mov     [rbp+57h+rect.left], eax
0x1800179f0  mov     [rbp+57h+rect.top], eax
0x1800179f3  call    cs:__imp_GetSystemMetrics
0x1800179fa  nop     dword ptr [rax+rax+00h]
0x1800179ff  mov     ecx, 4Eh ; 'N'; nIndex
0x180017a04  mov     ebx, eax
0x180017a06  call    cs:__imp_GetSystemMetrics
0x180017a0d  nop     dword ptr [rax+rax+00h]
0x180017a12  mov     ecx, 4Eh ; 'N'
0x180017a17  cmp     eax, ebx
0x180017a19  jg      short loc_180017A20
0x180017a1b  mov     ecx, 4Fh ; 'O'; nIndex
0x180017a20  call    cs:__imp_GetSystemMetrics
0x180017a27  nop     dword ptr [rax+rax+00h]
0x180017a2c  mov     ecx, eax
0x180017a2e  add     ecx, [rbp+57h+rect.left]
0x180017a31  mov     [rbp+57h+rect.right], ecx
0x180017a34  mov     ecx, 4Fh ; 'O'; nIndex
0x180017a39  call    cs:__imp_GetSystemMetrics
0x180017a40  nop     dword ptr [rax+rax+00h]
0x180017a45  mov     ecx, 4Eh ; 'N'; nIndex
0x180017a4a  mov     ebx, eax
0x180017a4c  call    cs:__imp_GetSystemMetrics
0x180017a53  nop     dword ptr [rax+rax+00h]
0x180017a58  mov     ecx, 4Eh ; 'N'
0x180017a5d  cmp     eax, ebx
0x180017a5f  jg      short loc_180017A66
0x180017a61  mov     ecx, 4Fh ; 'O'; nIndex
0x180017a66  call    cs:__imp_GetSystemMetrics
0x180017a6d  nop     dword ptr [rax+rax+00h]
0x180017a72  mov     ecx, eax
0x180017a74  mov     [rsp+0B0h+arg_8], rdi
0x180017a7c  add     ecx, [rbp+57h+rect.top]
0x180017a7f  mov     [rbp+57h+rect.bottom], ecx
0x180017a82  lea     rcx, [rbp+57h+rect]; lprect
0x180017a86  mov     [rsp+0B0h+arg_10], r14
0x180017a8e  mov     [rsp+0B0h+var_20], r15
0x180017a96  call    cs:__imp_CreateRectRgnIndirect
0x180017a9d  nop     dword ptr [rax+rax+00h]
0x180017aa2  mov     [rbp+57h+hrgnSrc1], rax
0x180017aa6  lea     r12, ??_7?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable'
0x180017aad  mov     [rbp+57h+var_80], r12
0x180017ab1  test    rax, rax
0x180017ab4  jz      short loc_180017AE8
0x180017ab6  mov     rdx, [rsi+60h]
0x180017aba  xor     ebx, ebx
0x180017abc  xor     edi, edi
0x180017abe  test    rdx, rdx
0x180017ac1  jz      loc_180017B81
0x180017ac7  mov     r9, [rsi+58h]
0x180017acb  xor     r8d, r8d
0x180017ace  mov     rax, [r9+r8*8]
0x180017ad2  test    rax, rax
0x180017ad5  jnz     loc_180017B62
0x180017adb  inc     r8
0x180017ade  cmp     r8, rdx
0x180017ae1  jb      short loc_180017ACE
0x180017ae3  jmp     loc_180017B81
0x180017ae8  call    cs:__imp_GetLastError
0x180017aef  nop     dword ptr [rax+rax+00h]
0x180017af4  mov     ebx, eax
0x180017af6  test    eax, eax
0x180017af8  jg      loc_180017D0A
0x180017afe  test    ebx, ebx
0x180017b00  mov     eax, 80004005h
0x180017b05  cmovns  ebx, eax
0x180017b08  jmp     short loc_180017B12
0x180017b0a  test    ebx, ebx
0x180017b0c  jns     loc_180017BE7
0x180017b12  cmp     [rbp+57h+hrgnSrc1], 0
0x180017b17  mov     [rbp+57h+var_80], r12
0x180017b1b  jz      short loc_180017B2E
0x180017b1d  lea     rcx, [rbp+57h+var_80]
0x180017b21  call    ?InternalClose@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(void)
0x180017b26  test    al, al
0x180017b28  jz      loc_180017D38
0x180017b2e  mov     r15, [rsp+0B0h+var_20]
0x180017b36  mov     eax, ebx
0x180017b38  mov     r14, [rsp+0B0h+arg_10]
0x180017b40  mov     rdi, [rsp+0B0h+arg_8]
0x180017b48  mov     rcx, [rbp+57h+var_30]
0x180017b4c  xor     rcx, rsp; StackCookie
0x180017b4f  call    __security_check_cookie
0x180017b54  add     rsp, 98h
0x180017b5b  pop     r12
0x180017b5d  pop     rsi
0x180017b5e  pop     rbx
0x180017b5f  pop     rbp
0x180017b60  retn
0x180017b62  test    byte ptr [rax], 2
0x180017b65  mov     rcx, rax
0x180017b68  mov     rax, [rax+38h]
0x180017b6c  cmovz   rcx, rdi
0x180017b70  mov     rdi, rcx
0x180017b73  test    rax, rax
0x180017b76  jnz     short loc_180017B62
0x180017b78  test    rcx, rcx
0x180017b7b  jz      loc_180017ADB
0x180017b81  mov     rcx, [rsi+20h]; hWnd
0x180017b85  test    rdi, rdi
0x180017b88  jz      loc_180017E02
0x180017b8e  test    rcx, rcx
0x180017b91  jz      loc_180017D58
0x180017b97  cmp     dword ptr [rsi+9Ch], 0
0x180017b9e  jnz     loc_180017B0A
0x180017ba4  test    ebx, ebx
0x180017ba6  js      loc_180017B12
0x180017bac  cmp     qword ptr [rdi+38h], 0
0x180017bb1  mov     r14, rdi
0x180017bb4  jnz     loc_180017D67
0x180017bba  mov     rdi, [rdi+8]
0x180017bbe  mov     edx, 4; uCmd
0x180017bc3  mov     rcx, rdi; hWnd
0x180017bc6  call    cs:__imp_GetWindow
0x180017bcd  nop     dword ptr [rax+rax+00h]
0x180017bd2  mov     r15, rax
0x180017bd5  test    rax, rax
0x180017bd8  jz      loc_180017D77
0x180017bde  mov     rdi, [r14+8]
0x180017be2  test    rdi, rdi
0x180017be5  jnz     short loc_180017C00
0x180017be7  cmp     qword ptr [rsi+20h], 0
0x180017bec  jnz     loc_180017E20
0x180017bf2  mov     rcx, rsi; this
0x180017bf5  call    ?_UpdateOverlayVisibility@CLightDismissClientStore@@AEAAXXZ; CLightDismissClientStore::_UpdateOverlayVisibility(void)
0x180017bfa  jmp     loc_180017B12
0x180017c00  cmp     rdi, r15
0x180017c03  jz      short loc_180017BE7
0x180017c05  xorps   xmm0, xmm0
0x180017c08  lea     rdx, [rbp+57h+Rect]; lpRect
0x180017c0c  mov     rcx, rdi; hWnd
0x180017c0f  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180017c13  call    cs:__imp_GetWindowRect
0x180017c1a  nop     dword ptr [rax+rax+00h]
0x180017c1f  xor     r9d, r9d; y2
0x180017c22  xor     r8d, r8d; x2
0x180017c25  xor     edx, edx; y1
0x180017c27  xor     ecx, ecx; x1
0x180017c29  call    cs:__imp_CreateRectRgn
0x180017c30  nop     dword ptr [rax+rax+00h]
0x180017c35  mov     rcx, rdi; hWnd
0x180017c38  mov     [rbp+57h+var_70], r12
0x180017c3c  mov     rdx, rax; hRgn
0x180017c3f  mov     [rbp+57h+hrgn], rax
0x180017c43  call    cs:__imp_GetWindowRgn
0x180017c4a  nop     dword ptr [rax+rax+00h]
0x180017c4f  cmp     eax, 1
0x180017c52  ja      loc_180017D95
0x180017c58  lea     rcx, [rbp+57h+Rect]; lprc
0x180017c5c  call    cs:__imp_IsRectEmpty
0x180017c63  nop     dword ptr [rax+rax+00h]
0x180017c68  test    eax, eax
0x180017c6a  jz      loc_180017DB1
0x180017c70  mov     rax, [rbp+57h+hrgn]
0x180017c74  mov     [rbp+57h+hrgn], 0
0x180017c7c  mov     [rbp+57h+var_70], r12
0x180017c80  mov     [rbp+57h+var_60], r12
0x180017c84  mov     [rbp+57h+hrgnSrc2], rax
0x180017c88  test    rax, rax
0x180017c8b  jz      short loc_180017CD1
0x180017c8d  xorps   xmm0, xmm0
0x180017c90  lea     rdx, [rbp+57h+Rect]; lpRect
0x180017c94  mov     rcx, rdi; hWnd
0x180017c97  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180017c9b  call    cs:__imp_GetWindowRect
0x180017ca2  nop     dword ptr [rax+rax+00h]
0x180017ca7  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, 1
0x180017cae  jnz     loc_180017DE2
0x180017cb4  mov     rcx, [rbp+57h+hrgnSrc1]; hrgnDst
0x180017cb8  mov     r9d, 4; iMode
0x180017cbe  mov     r8, [rbp+57h+hrgnSrc2]; hrgnSrc2
0x180017cc2  mov     rdx, rcx; hrgnSrc1
0x180017cc5  call    cs:__imp_CombineRgn
0x180017ccc  nop     dword ptr [rax+rax+00h]
0x180017cd1  mov     rcx, rdi; hWnd
0x180017cd4  call    _anonymous_namespace___GetOwner
0x180017cd9  cmp     [rbp+57h+hrgnSrc2], 0
0x180017cde  mov     rdi, rax
0x180017ce1  mov     [rbp+57h+var_60], r12
0x180017ce5  jz      short loc_180017CFC
0x180017ce7  lea     rcx, [rbp+57h+var_60]
0x180017ceb  call    ?InternalClose@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(void)
0x180017cf0  test    al, al
0x180017cf2  jz      short loc_180017D18
0x180017cf4  mov     [rbp+57h+hrgnSrc2], 0
0x180017cfc  test    rdi, rdi
0x180017cff  jz      loc_180017BE7
0x180017d05  jmp     loc_180017C00
0x180017d0a  movzx   ebx, ax
0x180017d0d  or      ebx, 80070000h
0x180017d13  jmp     loc_180017AFE
0x180017d18  call    cs:__imp_GetLastError
0x180017d1f  nop     dword ptr [rax+rax+00h]
0x180017d24  test    eax, eax
0x180017d26  jle     short loc_180017D30
0x180017d28  movzx   eax, ax
0x180017d2b  or      eax, 80070000h
0x180017d30  mov     ecx, eax; this
0x180017d32  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180017d37  int     3; Trap to Debugger
0x180017d38  call    cs:__imp_GetLastError
0x180017d3f  nop     dword ptr [rax+rax+00h]
0x180017d44  test    eax, eax
0x180017d46  jle     short loc_180017D50
0x180017d48  movzx   eax, ax
0x180017d4b  or      eax, 80070000h
0x180017d50  mov     ecx, eax; this
0x180017d52  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180017d57  int     3; Trap to Debugger
0x180017d58  mov     rcx, rsi; this
0x180017d5b  call    ?_CreateOverlay@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateOverlay(void)
0x180017d60  mov     ebx, eax
0x180017d62  jmp     loc_180017B97
0x180017d67  mov     r14, [r14+38h]
0x180017d6b  cmp     qword ptr [r14+38h], 0
0x180017d70  jnz     short loc_180017D67
0x180017d72  jmp     loc_180017BBA
0x180017d77  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x180017d7e  mov     rcx, rdi; hWnd
0x180017d81  call    cs:__imp_GetPropW
0x180017d88  nop     dword ptr [rax+rax+00h]
0x180017d8d  mov     r15, rax
0x180017d90  jmp     loc_180017BDE
0x180017d95  mov     r8d, [rbp+57h+Rect.top]; y
0x180017d99  mov     edx, [rbp+57h+Rect.left]; x
0x180017d9c  mov     rcx, [rbp+57h+hrgn]; hrgn
0x180017da0  call    cs:__imp_OffsetRgn
0x180017da7  nop     dword ptr [rax+rax+00h]
0x180017dac  jmp     loc_180017C70
0x180017db1  lea     rcx, [rbp+57h+Rect]; lprect
0x180017db5  call    cs:__imp_CreateRectRgnIndirect
0x180017dbc  nop     dword ptr [rax+rax+00h]
0x180017dc1  mov     r14, rax
0x180017dc4  mov     rax, [rbp+57h+hrgn]
0x180017dc8  cmp     r14, rax
0x180017dcb  jz      loc_180017C74
0x180017dd1  lea     rcx, [rbp+57h+var_70]
0x180017dd5  call    ?Close@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::Close(void)
0x180017dda  mov     rax, r14
0x180017ddd  jmp     loc_180017C74
0x180017de2  mov     eax, [rbp+57h+Rect.bottom]
0x180017de5  mov     r9d, [rbp+57h+Rect.top]
0x180017de9  mov     r8d, [rbp+57h+Rect.left]
0x180017ded  mov     dword ptr [rsp+0B0h+var_88], eax
0x180017df1  mov     eax, [rbp+57h+Rect.right]
0x180017df4  mov     [rsp+0B0h+var_90], eax
0x180017df8  call    McTemplateU0dddd_EventWriteTransfer
0x180017dfd  jmp     loc_180017CB4
0x180017e02  test    rcx, rcx
0x180017e05  jz      loc_180017BE7
0x180017e0b  call    cs:__imp_DestroyWindow
0x180017e12  nop     dword ptr [rax+rax+00h]
0x180017e17  mov     [rsi+20h], rbx
0x180017e1b  jmp     loc_180017BE7
0x180017e20  mov     r8d, [rbp+57h+rect.top]
0x180017e24  mov     edx, [rbp+57h+rect.left]
0x180017e27  neg     r8d; y
0x180017e2a  mov     rcx, [rbp+57h+hrgnSrc1]; hrgn
0x180017e2e  neg     edx; x
0x180017e30  call    cs:__imp_OffsetRgn
0x180017e37  nop     dword ptr [rax+rax+00h]
0x180017e3c  mov     rdx, [rbp+57h+hrgnSrc1]; hRgn
0x180017e40  mov     r8d, 1; bRedraw
0x180017e46  mov     rcx, [rsi+20h]; hWnd
0x180017e4a  call    cs:__imp_SetWindowRgn
0x180017e51  nop     dword ptr [rax+rax+00h]
0x180017e56  mov     r8, [rbp+57h+hrgnSrc1]
0x180017e5a  xor     edx, edx
0x180017e5c  test    eax, eax
0x180017e5e  cmovnz  r8, rdx
0x180017e62  mov     [rbp+57h+hrgnSrc1], r8
0x180017e66  jmp     loc_180017BF2
```
