# GamingOverlayExperienceManager::SetCombinedWindowRegion(uint,Windows::Foundation::Rect *)

- ea: `0x1803d99f0`
- end: `0x1803d9d6a`
- name: `?SetCombinedWindowRegion@GamingOverlayExperienceManager@@UEAAJIPEAURect@Foundation@Windows@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(GamingOverlayExperienceManager *__hidden this, unsigned int, struct Windows::Foundation::Rect *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x18014acc0`
- `0x1801e1b2c`
- `0x180356360`
- `0x1803d99f0`
- `0x1803dc120`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9a63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9b53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9c7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9a63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9b53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9c7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1803d9d3a`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1803d9b75`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1803d9bde`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1803d9b75`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1803d9bde`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x1803d9c37`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x1803d9c37`
- `GDI32!DeleteObject` at `0x1803d9c19`
- `GDI32!DeleteObject` at `0x1803d9c63`
- `GDI32!DeleteObject` at `0x1803d9ca9`
- `GDI32!DeleteObject` at `0x1803d9ccf`
- `GDI32!DeleteObject` at `0x1803d9c19`
- `GDI32!DeleteObject` at `0x1803d9c63`
- `GDI32!DeleteObject` at `0x1803d9ca9`
- `GDI32!DeleteObject` at `0x1803d9ccf`
- `GDI32!CombineRgn` at `0x1803d9c0c`
- `GDI32!CombineRgn` at `0x1803d9c0c`

## pseudocode

```c
__int64 __fastcall GamingOverlayExperienceManager::SetCombinedWindowRegion(
        GamingOverlayExperienceManager *this,
        unsigned int a2,
        struct Windows::Foundation::Rect *a3)
{
  int updated; // ebx
  GamingOverlayExperienceManager *v8; // r14
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  __int64 v11; // rdx
  HRGN RectRgn; // rax
  HRGN v13; // rbx
  unsigned int v14; // esi
  HRGN v15; // rax
  HRGN v16; // rdi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-30h] BYREF
  HRGN hrgnDst; // [rsp+28h] [rbp-28h] BYREF
  HWND hWnd; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 456);
  if ( !a3 )
  {
    updated = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x80004003LL,
      (int)lpCriticalSection);
LABEL_3:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)updated;
  }
  v8 = (GamingOverlayExperienceManager *)((char *)this - 136);
  v9 = *((_QWORD *)this + 35);
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x8000FFFFLL,
      (int)lpCriticalSection);
LABEL_15:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 2147549183LL;
  }
  v20 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  updated = v10(v9, &v20);
  if ( updated < 0 )
  {
    v11 = 471;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)(unsigned int)updated,
      (int)lpCriticalSection);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    goto LABEL_3;
  }
  hWnd = 0;
  updated = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v20 + 24LL))(v20, &hWnd);
  if ( updated < 0 )
  {
    v11 = 475;
    goto LABEL_10;
  }
  if ( !hWnd )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x8000FFFFLL,
      (int)lpCriticalSection);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    goto LABEL_15;
  }
  hrgnDst = 0;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(
    &hrgnDst,
    RectRgn);
  v13 = hrgnDst;
  if ( !hrgnDst )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x8007000ELL,
      (int)lpCriticalSection);
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 2147942414LL;
  }
  v14 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      hrgnDst = 0;
      v15 = CreateRectRgn(
              (int)*((float *)a3 + 4 * v14),
              (int)*((float *)a3 + 4 * v14 + 1),
              (int)(float)(*((float *)a3 + 4 * v14) + *((float *)a3 + 4 * v14 + 2)),
              (int)(float)(*((float *)a3 + 4 * v14 + 1) + *((float *)a3 + 4 * v14 + 3)));
      wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(
        &hrgnDst,
        v15);
      v16 = hrgnDst;
      if ( !hrgnDst )
        break;
      if ( !CombineRgn(v13, v13, hrgnDst, 2) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
          (const char *)0x80004005LL,
          (int)lpCriticalSection);
        DeleteObject(v16);
        goto LABEL_25;
      }
      DeleteObject(v16);
      if ( ++v14 >= a2 )
        goto LABEL_23;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x8007000ELL,
      (int)lpCriticalSection);
    DeleteObject(v13);
    goto LABEL_36;
  }
LABEL_23:
  if ( SetWindowRgn(hWnd, v13, 1) )
  {
    updated = GamingOverlayExperienceManager::UpdateOverlayDisplayModeFullscreen(v8, 0);
    if ( updated < 0 )
    {
      v11 = 500;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)0x80004005LL,
      (int)lpCriticalSection);
LABEL_25:
    DeleteObject(v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1803d99f0  mov     [rsp-28h+arg_8], rbx
0x1803d99f5  mov     [rsp-28h+arg_18], rsi
0x1803d99fa  push    rbp
0x1803d99fb  push    rdi
0x1803d99fc  push    r12
0x1803d99fe  push    r14
0x1803d9a00  push    r15
0x1803d9a02  mov     rbp, rsp
0x1803d9a05  sub     rsp, 50h
0x1803d9a09  mov     rax, cs:__security_cookie
0x1803d9a10  xor     rax, rsp
0x1803d9a13  mov     [rbp+var_10], rax
0x1803d9a17  mov     r15d, edx
0x1803d9a1a  mov     [rbp+lpCriticalSection], 0
0x1803d9a22  lea     rdx, [rcx+1C8h]
0x1803d9a29  mov     rbx, rcx
0x1803d9a2c  lea     rcx, [rbp+lpCriticalSection]
0x1803d9a30  mov     r12, r8
0x1803d9a33  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1803d9a38  test    r12, r12
0x1803d9a3b  jnz     short loc_1803D9A70
0x1803d9a3d  mov     rcx, [rbp+28h]; this
0x1803d9a41  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9a48  mov     ebx, 80004003h
0x1803d9a4d  mov     edx, 1D2h; void *
0x1803d9a52  mov     r9d, ebx; char *
0x1803d9a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9a5a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1803d9a5e  test    rcx, rcx
0x1803d9a61  jz      short loc_1803D9A69
0x1803d9a63  call    cs:__imp_LeaveCriticalSection
0x1803d9a69  mov     eax, ebx
0x1803d9a6b  jmp     loc_1803D9D45
0x1803d9a70  lea     r14, [rbx-88h]
0x1803d9a77  mov     rdi, [r14+1A0h]
0x1803d9a7e  test    rdi, rdi
0x1803d9a81  jnz     short loc_1803D9AA3
0x1803d9a83  mov     rcx, [rbp+28h]; this
0x1803d9a87  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9a8e  mov     r9d, 8000FFFFh; char *
0x1803d9a94  mov     edx, 1D3h; void *
0x1803d9a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9a9e  jmp     loc_1803D9B4A
0x1803d9aa3  mov     [rbp+var_18], 0
0x1803d9aab  lea     rcx, [rbp+var_18]
0x1803d9aaf  mov     rax, [rdi]
0x1803d9ab2  mov     rbx, [rax+20h]
0x1803d9ab6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9abb  lea     rdx, [rbp+var_18]
0x1803d9abf  mov     rcx, rdi
0x1803d9ac2  mov     rax, rbx
0x1803d9ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d9aca  mov     ebx, eax
0x1803d9acc  test    eax, eax
0x1803d9ace  jns     short loc_1803D9AF6
0x1803d9ad0  mov     edx, 1D7h; void *
0x1803d9ad5  mov     rcx, [rbp+28h]; this
0x1803d9ad9  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9ae0  mov     r9d, ebx; char *
0x1803d9ae3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9ae8  lea     rcx, [rbp+var_18]
0x1803d9aec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9af1  jmp     loc_1803D9A5A
0x1803d9af6  mov     rcx, [rbp+var_18]
0x1803d9afa  lea     rdx, [rbp+hWnd]
0x1803d9afe  mov     [rbp+hWnd], 0
0x1803d9b06  mov     rax, [rcx]
0x1803d9b09  mov     rax, [rax+18h]
0x1803d9b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d9b12  mov     ebx, eax
0x1803d9b14  test    eax, eax
0x1803d9b16  jns     short loc_1803D9B1F
0x1803d9b18  mov     edx, 1DBh
0x1803d9b1d  jmp     short loc_1803D9AD5
0x1803d9b1f  cmp     [rbp+hWnd], 0
0x1803d9b24  jnz     short loc_1803D9B63
0x1803d9b26  mov     rcx, [rbp+28h]; this
0x1803d9b2a  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9b31  mov     r9d, 8000FFFFh; char *
0x1803d9b37  mov     edx, 1DCh; void *
0x1803d9b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9b41  lea     rcx, [rbp+var_18]
0x1803d9b45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9b4a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1803d9b4e  test    rcx, rcx
0x1803d9b51  jz      short loc_1803D9B59
0x1803d9b53  call    cs:__imp_LeaveCriticalSection
0x1803d9b59  mov     eax, 8000FFFFh
0x1803d9b5e  jmp     loc_1803D9D45
0x1803d9b63  xor     r9d, r9d; y2
0x1803d9b66  mov     [rbp+hrgnDst], 0
0x1803d9b6e  xor     r8d, r8d; x2
0x1803d9b71  xor     edx, edx; y1
0x1803d9b73  xor     ecx, ecx; x1
0x1803d9b75  call    cs:__imp_CreateRectRgn
0x1803d9b7b  mov     rdx, rax
0x1803d9b7e  lea     rcx, [rbp+hrgnDst]
0x1803d9b82  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHRGN__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(HRGN__ *)
0x1803d9b87  mov     rbx, [rbp+hrgnDst]
0x1803d9b8b  test    rbx, rbx
0x1803d9b8e  jz      loc_1803D9D0D
0x1803d9b94  xor     esi, esi
0x1803d9b96  test    r15d, r15d
0x1803d9b99  jz      loc_1803D9C2A
0x1803d9b9f  mov     eax, esi
0x1803d9ba1  add     rax, rax
0x1803d9ba4  mov     [rbp+hrgnDst], 0
0x1803d9bac  movss   xmm0, dword ptr [r12+rax*8+4]
0x1803d9bb3  movss   xmm1, dword ptr [r12+rax*8]
0x1803d9bb9  addss   xmm0, dword ptr [r12+rax*8+0Ch]
0x1803d9bc0  addss   xmm1, dword ptr [r12+rax*8+8]
0x1803d9bc7  cvttss2si edx, dword ptr [r12+rax*8+4]; y1
0x1803d9bce  cvttss2si ecx, dword ptr [r12+rax*8]; x1
0x1803d9bd4  cvttss2si r9d, xmm0; y2
0x1803d9bd9  cvttss2si r8d, xmm1; x2
0x1803d9bde  call    cs:__imp_CreateRectRgn
0x1803d9be4  mov     rdx, rax
0x1803d9be7  lea     rcx, [rbp+hrgnDst]
0x1803d9beb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHRGN__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(HRGN__ *)
0x1803d9bf0  mov     rdi, [rbp+hrgnDst]
0x1803d9bf4  test    rdi, rdi
0x1803d9bf7  jz      loc_1803D9CB1
0x1803d9bfd  mov     r9d, 2; iMode
0x1803d9c03  mov     r8, rdi; hrgnSrc2
0x1803d9c06  mov     rdx, rbx; hrgnSrc1
0x1803d9c09  mov     rcx, rbx; hrgnDst
0x1803d9c0c  call    cs:__imp_CombineRgn
0x1803d9c12  test    eax, eax
0x1803d9c14  jz      short loc_1803D9C8B
0x1803d9c16  mov     rcx, rdi; ho
0x1803d9c19  call    cs:__imp_DeleteObject
0x1803d9c1f  inc     esi
0x1803d9c21  cmp     esi, r15d
0x1803d9c24  jb      loc_1803D9B9F
0x1803d9c2a  mov     rcx, [rbp+hWnd]; hWnd
0x1803d9c2e  mov     r8d, 1; bRedraw
0x1803d9c34  mov     rdx, rbx; hRgn
0x1803d9c37  call    cs:__imp_SetWindowRgn
0x1803d9c3d  test    eax, eax
0x1803d9c3f  jnz     loc_1803D9CD7
0x1803d9c45  mov     rcx, [rbp+28h]; this
0x1803d9c49  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9c50  mov     r9d, 80004005h; char *
0x1803d9c56  mov     edx, 1EFh; void *
0x1803d9c5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9c60  mov     rcx, rbx; ho
0x1803d9c63  call    cs:__imp_DeleteObject
0x1803d9c69  lea     rcx, [rbp+var_18]
0x1803d9c6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9c72  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1803d9c76  test    rcx, rcx
0x1803d9c79  jz      short loc_1803D9C81
0x1803d9c7b  call    cs:__imp_LeaveCriticalSection
0x1803d9c81  mov     eax, 80004005h
0x1803d9c86  jmp     loc_1803D9D45
0x1803d9c8b  mov     rcx, [rbp+28h]; this
0x1803d9c8f  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9c96  mov     r9d, 80004005h; char *
0x1803d9c9c  mov     edx, 1ECh; void *
0x1803d9ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9ca6  mov     rcx, rdi; ho
0x1803d9ca9  call    cs:__imp_DeleteObject
0x1803d9caf  jmp     short loc_1803D9C60
0x1803d9cb1  mov     rcx, [rbp+28h]; this
0x1803d9cb5  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9cbc  mov     r9d, 8007000Eh; char *
0x1803d9cc2  mov     edx, 1E8h; void *
0x1803d9cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9ccc  mov     rcx, rbx; ho
0x1803d9ccf  call    cs:__imp_DeleteObject
0x1803d9cd5  jmp     short loc_1803D9D28
0x1803d9cd7  xor     edx, edx; bool
0x1803d9cd9  mov     rcx, r14; this
0x1803d9cdc  call    ?UpdateOverlayDisplayModeFullscreen@GamingOverlayExperienceManager@@AEAAJ_N@Z; GamingOverlayExperienceManager::UpdateOverlayDisplayModeFullscreen(bool)
0x1803d9ce1  mov     ebx, eax
0x1803d9ce3  test    eax, eax
0x1803d9ce5  jns     short loc_1803D9CF1
0x1803d9ce7  mov     edx, 1F4h
0x1803d9cec  jmp     loc_1803D9AD5
0x1803d9cf1  lea     rcx, [rbp+var_18]
0x1803d9cf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9cfa  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1803d9cfe  test    rcx, rcx
0x1803d9d01  jz      short loc_1803D9D09
0x1803d9d03  call    cs:__imp_LeaveCriticalSection
0x1803d9d09  xor     eax, eax
0x1803d9d0b  jmp     short loc_1803D9D45
0x1803d9d0d  mov     rcx, [rbp+28h]; this
0x1803d9d11  lea     r8, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d9d18  mov     r9d, 8007000Eh; char *
0x1803d9d1e  mov     edx, 1E0h; void *
0x1803d9d23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d9d28  lea     rcx, [rbp+var_18]
0x1803d9d2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d9d31  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1803d9d35  test    rcx, rcx
0x1803d9d38  jz      short loc_1803D9D40
0x1803d9d3a  call    cs:__imp_LeaveCriticalSection
0x1803d9d40  mov     eax, 8007000Eh
0x1803d9d45  mov     rcx, [rbp+var_10]
0x1803d9d49  xor     rcx, rsp; StackCookie
0x1803d9d4c  call    __security_check_cookie
0x1803d9d51  lea     r11, [rsp+50h+var_s0]
0x1803d9d56  mov     rbx, [r11+38h]
0x1803d9d5a  mov     rsi, [r11+48h]
0x1803d9d5e  mov     rsp, r11
0x1803d9d61  pop     r15
0x1803d9d63  pop     r14
0x1803d9d65  pop     r12
0x1803d9d67  pop     rdi
0x1803d9d68  pop     rbp
0x1803d9d69  retn
```
