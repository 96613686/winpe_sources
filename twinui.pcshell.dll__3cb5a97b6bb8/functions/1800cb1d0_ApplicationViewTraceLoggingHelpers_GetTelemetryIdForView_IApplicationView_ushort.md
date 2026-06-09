# ApplicationViewTraceLoggingHelpers::GetTelemetryIdForView(IApplicationView *,ushort * *)

- ea: `0x1800cb1d0`
- end: `0x1800cb5cd`
- name: `?GetTelemetryIdForView@ApplicationViewTraceLoggingHelpers@@YAJPEAUIApplicationView@@PEAPEAG@Z`
- size: `1021`
- prototype: `__int64 __fastcall(ApplicationViewTraceLoggingHelpers *__hidden this, struct IApplicationView *, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18024b650`
- `0x18024c2c4`
- `0x180315fe0`
- `0x180316154`
- `0x180316384`
- `0x1803394bc`
- `0x18054da60`
- `0x180550134`
- `0x1805505a8`
- `0x18055076c`
- `0x1805508b8`

## callees

- `0x1800237c8`
- `0x180031200`
- `0x180031c70`
- `0x180086ac0`
- `0x18008a6f0`
- `0x1800cb1d0`
- `0x1800cb5d4`
- `0x1800cb8d0`
- `0x1800cbaf0`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cb25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb39e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb4d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb39e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb4d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb588`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800cb30d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1800cb30d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ApplicationViewTraceLoggingHelpers::GetTelemetryIdForView(
        ApplicationViewTraceLoggingHelpers *this,
        struct IApplicationView *a2,
        unsigned __int16 **a3)
{
  wchar_t *v5; // rsi
  __int64 v6; // rbx
  wchar_t *v7; // rax
  int v8; // edi
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  wchar_t *v11; // r8
  wchar_t v12; // ax
  wchar_t *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27[2]; // [rsp+20h] [rbp-E0h] BYREF
  HWND hWnd; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h]
  __int64 v31; // [rsp+40h] [rbp-C0h]
  LPVOID v32[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ClassName[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v5 = 0;
  pv = 0;
  v30 = 0;
  v31 = 0;
  *(_QWORD *)v27 = 0;
  if ( (**(int (__fastcall ***)(ApplicationViewTraceLoggingHelpers *, GUID *, int *))this)(
         this,
         &GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b,
         v27) >= 0 )
  {
    v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &pv,
            L"WinRT: ",
            -1);
    v15 = v23;
    if ( v23 >= 0 )
    {
      v32[0] = 0;
      v32[1] = (LPVOID)-1LL;
      v32[2] = (LPVOID)-1LL;
      if ( (*(int (__fastcall **)(ApplicationViewTraceLoggingHelpers *, LPVOID *))(*(_QWORD *)this + 136LL))(this, v32) >= 0 )
      {
        v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&pv, v32);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x13,
            (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
            (const char *)(unsigned int)v24,
            v27[0]);
      }
      if ( v32[0] )
        CoTaskMemFree(v32[0]);
      goto LABEL_18;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
      (const char *)(unsigned int)v23,
      v27[0]);
    v26 = *(_QWORD *)v27;
    if ( *(_QWORD *)v27 )
    {
      *(_QWORD *)v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( pv )
      CoTaskMemFree(pv);
    return v15;
  }
  hWnd = 0;
  v6 = 8;
  if ( is_mul_ok(8u, 2u) )
  {
    v7 = (wchar_t *)CoTaskMemAlloc(0x10u);
    if ( v7 )
    {
      v8 = 0;
      v31 = 8;
      v5 = v7;
      pv = v7;
      *v7 = 0;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v8 >= 0 )
    {
      v9 = 7;
      v10 = L"Win32: ";
      v11 = v5;
      do
      {
        if ( !v9 )
          break;
        v12 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v11++ = v12;
        --v9;
        --v6;
      }
      while ( v6 );
      v13 = v11 - 1;
      if ( v6 )
        v13 = v11;
      *v13 = 0;
      v30 = 7;
      hWnd = 0;
      v14 = (*(__int64 (__fastcall **)(ApplicationViewTraceLoggingHelpers *, HWND *))(*(_QWORD *)this + 72LL))(
              this,
              &hWnd);
      v15 = v14;
      if ( v14 >= 0 )
      {
        if ( GetClassNameW(hWnd, ClassName, 260) )
        {
          v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                  &pv,
                  L"Class[%s] ",
                  ClassName);
          if ( v16 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x20,
              (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
              (const char *)(unsigned int)v16,
              v27[0]);
        }
        v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                &pv,
                L"Window[%lx]",
                (unsigned int)hWnd);
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x23,
            (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
            (const char *)(unsigned int)v17,
            v27[0]);
LABEL_18:
        v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo(&pv, a2);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26,
            (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
            (const char *)(unsigned int)v18,
            v27[0]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v27);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          return v19;
        }
        else
        {
          v20 = *(_QWORD *)v27;
          if ( *(_QWORD *)v27 )
          {
            *(_QWORD *)v27 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( pv )
            CoTaskMemFree(pv);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
        (const char *)(unsigned int)v14,
        v27[0]);
      v25 = *(_QWORD *)v27;
      if ( *(_QWORD *)v27 )
      {
        *(_QWORD *)v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      if ( v5 )
      {
        CoTaskMemFree(v5);
        return v15;
      }
      return v15;
    }
  }
  else
  {
    v8 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19,
    (unsigned int)"desktop\\internal\\shell\\inc\\private\\ApplicationViewTraceLoggingHelpers.h",
    (const char *)(unsigned int)v8,
    v27[0]);
  v22 = *(_QWORD *)v27;
  if ( *(_QWORD *)v27 )
  {
    *(_QWORD *)v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800cb1d0  mov     [rsp-8+arg_10], rbx
0x1800cb1d5  mov     [rsp-8+arg_18], rsi
0x1800cb1da  push    rbp
0x1800cb1db  push    rdi
0x1800cb1dc  push    r12
0x1800cb1de  push    r14
0x1800cb1e0  push    r15
0x1800cb1e2  lea     rbp, [rsp-180h]
0x1800cb1ea  sub     rsp, 280h
0x1800cb1f1  mov     rax, cs:__security_cookie
0x1800cb1f8  xor     rax, rsp
0x1800cb1fb  mov     [rbp+1A0h+var_30], rax
0x1800cb202  mov     r15, rdx
0x1800cb205  mov     r14, rcx
0x1800cb208  xor     r12d, r12d
0x1800cb20b  mov     esi, r12d
0x1800cb20e  mov     [rsp+2A0h+pv], r12
0x1800cb213  mov     [rsp+2A0h+var_268], r12
0x1800cb218  mov     [rsp+2A0h+var_260], r12
0x1800cb21d  mov     qword ptr [rsp+2A0h+var_280], r12; int
0x1800cb222  mov     rax, [rcx]
0x1800cb225  lea     r8, [rsp+2A0h+var_280]
0x1800cb22a  lea     rdx, _GUID_d8b456d0_bec6_4f57_bb1d_50559a14384b
0x1800cb231  mov     rax, [rax]
0x1800cb234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb239  test    eax, eax
0x1800cb23b  jns     loc_1800CB45C
0x1800cb241  mov     [rsp+2A0h+hWnd], r12
0x1800cb246  mov     ebx, 8
0x1800cb24b  mov     eax, 2
0x1800cb250  mul     rbx
0x1800cb253  test    rdx, rdx
0x1800cb256  jnz     loc_1800CB3A8
0x1800cb25c  mov     rcx, rax; cb
0x1800cb25f  call    cs:__imp_CoTaskMemAlloc
0x1800cb265  test    rax, rax
0x1800cb268  jz      loc_1800CB452
0x1800cb26e  mov     edi, r12d
0x1800cb271  mov     [rsp+2A0h+var_260], rbx
0x1800cb276  mov     rsi, rax
0x1800cb279  mov     [rsp+2A0h+pv], rax
0x1800cb27e  mov     [rax], r12w
0x1800cb282  test    edi, edi
0x1800cb284  js      loc_1800CB3AD
0x1800cb28a  mov     ecx, 7
0x1800cb28f  lea     rdx, aWin32; "Win32: "
0x1800cb296  mov     r8, rsi
0x1800cb299  nop     dword ptr [rax+00000000h]
0x1800cb2a0  test    rcx, rcx
0x1800cb2a3  jz      short loc_1800CB2C2
0x1800cb2a5  movzx   eax, word ptr [rdx]
0x1800cb2a8  test    ax, ax
0x1800cb2ab  jz      short loc_1800CB2C2
0x1800cb2ad  add     rdx, 2
0x1800cb2b1  mov     [r8], ax
0x1800cb2b5  add     r8, 2
0x1800cb2b9  dec     rcx
0x1800cb2bc  sub     rbx, 1
0x1800cb2c0  jnz     short loc_1800CB2A0
0x1800cb2c2  lea     rcx, [r8-2]
0x1800cb2c6  test    rbx, rbx
0x1800cb2c9  cmovnz  rcx, r8
0x1800cb2cd  mov     [rcx], r12w
0x1800cb2d1  mov     [rsp+2A0h+var_268], 7
0x1800cb2da  mov     [rsp+2A0h+hWnd], r12
0x1800cb2df  mov     rax, [r14]
0x1800cb2e2  lea     rdx, [rsp+2A0h+hWnd]
0x1800cb2e7  mov     rcx, r14
0x1800cb2ea  mov     rax, [rax+48h]
0x1800cb2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb2f3  mov     ebx, eax
0x1800cb2f5  test    eax, eax
0x1800cb2f7  js      loc_1800CB4E3
0x1800cb2fd  mov     r8d, 104h; nMaxCount
0x1800cb303  lea     rdx, [rsp+2A0h+ClassName]; lpClassName
0x1800cb308  mov     rcx, [rsp+2A0h+hWnd]; hWnd
0x1800cb30d  call    cs:__imp_GetClassNameW
0x1800cb313  test    eax, eax
0x1800cb315  jz      short loc_1800CB33C
0x1800cb317  lea     r8, [rsp+2A0h+ClassName]
0x1800cb31c  lea     rdx, aClassS; "Class[%s] "
0x1800cb323  lea     rcx, [rsp+2A0h+pv]
0x1800cb328  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800cb32d  mov     rcx, [rbp+1A8h]; this
0x1800cb334  test    eax, eax
0x1800cb336  js      loc_1800CB439
0x1800cb33c  mov     r8d, dword ptr [rsp+2A0h+hWnd]
0x1800cb341  lea     rdx, aWindowLx; "Window[%lx]"
0x1800cb348  lea     rcx, [rsp+2A0h+pv]
0x1800cb34d  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800cb352  mov     rcx, [rbp+1A8h]; this
0x1800cb359  test    eax, eax
0x1800cb35b  js      loc_1800CB420
0x1800cb361  mov     rdx, r15
0x1800cb364  lea     rcx, [rsp+2A0h+pv]
0x1800cb369  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x1800cb36e  mov     ebx, eax
0x1800cb370  test    eax, eax
0x1800cb372  js      loc_1800CB595
0x1800cb378  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800cb37d  test    rcx, rcx
0x1800cb380  jz      short loc_1800CB394
0x1800cb382  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800cb387  mov     rax, [rcx]
0x1800cb38a  mov     rax, [rax+10h]
0x1800cb38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb393  nop
0x1800cb394  mov     rcx, [rsp+2A0h+pv]; pv
0x1800cb399  test    rcx, rcx
0x1800cb39c  jz      short loc_1800CB3A4
0x1800cb39e  call    cs:__imp_CoTaskMemFree
0x1800cb3a4  xor     eax, eax
0x1800cb3a6  jmp     short loc_1800CB3F5
0x1800cb3a8  mov     edi, 80070216h
0x1800cb3ad  mov     rcx, [rbp+1A8h]; this
0x1800cb3b4  mov     r9d, edi; char *
0x1800cb3b7  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb3be  mov     edx, 19h; void *
0x1800cb3c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb3c8  nop
0x1800cb3c9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800cb3ce  test    rcx, rcx
0x1800cb3d1  jz      short loc_1800CB3E5
0x1800cb3d3  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800cb3d8  mov     rax, [rcx]
0x1800cb3db  mov     rax, [rax+10h]
0x1800cb3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb3e4  nop
0x1800cb3e5  test    rsi, rsi
0x1800cb3e8  jz      short loc_1800CB3F3
0x1800cb3ea  mov     rcx, rsi; pv
0x1800cb3ed  call    cs:__imp_CoTaskMemFree
0x1800cb3f3  mov     eax, edi
0x1800cb3f5  mov     rcx, [rbp+1A0h+var_30]
0x1800cb3fc  xor     rcx, rsp; StackCookie
0x1800cb3ff  call    __security_check_cookie
0x1800cb404  lea     r11, [rsp+2A0h+var_20]
0x1800cb40c  mov     rbx, [r11+40h]
0x1800cb410  mov     rsi, [r11+48h]
0x1800cb414  mov     rsp, r11
0x1800cb417  pop     r15
0x1800cb419  pop     r14
0x1800cb41b  pop     r12
0x1800cb41d  pop     rdi
0x1800cb41e  pop     rbp
0x1800cb41f  retn
0x1800cb420  mov     r9d, eax; char *
0x1800cb423  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb42a  mov     edx, 23h ; '#'; void *
0x1800cb42f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb434  jmp     loc_1800CB361
0x1800cb439  mov     r9d, eax; char *
0x1800cb43c  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb443  mov     edx, 20h ; ' '; void *
0x1800cb448  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb44d  jmp     loc_1800CB33C
0x1800cb452  mov     edi, 8007000Eh
0x1800cb457  jmp     loc_1800CB282
0x1800cb45c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800cb463  lea     rdx, aWinrt; "WinRT: "
0x1800cb46a  lea     rcx, [rsp+2A0h+pv]
0x1800cb46f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800cb474  mov     ebx, eax
0x1800cb476  test    eax, eax
0x1800cb478  js      loc_1800CB546
0x1800cb47e  mov     [rsp+2A0h+var_258], r12
0x1800cb483  mov     [rsp+2A0h+var_250], 0FFFFFFFFFFFFFFFFh
0x1800cb48c  mov     [rsp+2A0h+var_248], 0FFFFFFFFFFFFFFFFh
0x1800cb495  mov     rax, [r14]
0x1800cb498  lea     rdx, [rsp+2A0h+var_258]
0x1800cb49d  mov     rcx, r14
0x1800cb4a0  mov     rax, [rax+88h]
0x1800cb4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb4ac  test    eax, eax
0x1800cb4ae  js      short loc_1800CB4CA
0x1800cb4b0  lea     rdx, [rsp+2A0h+var_258]
0x1800cb4b5  lea     rcx, [rsp+2A0h+pv]
0x1800cb4ba  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x1800cb4bf  mov     rcx, [rbp+1A8h]; this
0x1800cb4c6  test    eax, eax
0x1800cb4c8  js      short loc_1800CB530
0x1800cb4ca  mov     rcx, [rsp+2A0h+var_258]; pv
0x1800cb4cf  test    rcx, rcx
0x1800cb4d2  jz      loc_1800CB361
0x1800cb4d8  call    cs:__imp_CoTaskMemFree
0x1800cb4de  jmp     loc_1800CB361
0x1800cb4e3  mov     rcx, [rbp+1A8h]; this
0x1800cb4ea  mov     r9d, ebx; char *
0x1800cb4ed  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb4f4  mov     edx, 1Ch; void *
0x1800cb4f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb4fe  nop
0x1800cb4ff  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800cb504  test    rcx, rcx
0x1800cb507  jz      short loc_1800CB51B
0x1800cb509  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800cb50e  mov     rax, [rcx]
0x1800cb511  mov     rax, [rax+10h]
0x1800cb515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb51a  nop
0x1800cb51b  test    rsi, rsi
0x1800cb51e  jz      short loc_1800CB58E
0x1800cb520  mov     rcx, rsi; pv
0x1800cb523  call    cs:__imp_CoTaskMemFree
0x1800cb529  mov     eax, ebx
0x1800cb52b  jmp     loc_1800CB3F5
0x1800cb530  mov     r9d, eax; char *
0x1800cb533  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb53a  mov     edx, 13h; void *
0x1800cb53f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb544  jmp     short loc_1800CB4CA
0x1800cb546  mov     rcx, [rbp+1A8h]; this
0x1800cb54d  mov     r9d, ebx; char *
0x1800cb550  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb557  mov     edx, 0Eh; void *
0x1800cb55c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb561  nop
0x1800cb562  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800cb567  test    rcx, rcx
0x1800cb56a  jz      short loc_1800CB57E
0x1800cb56c  mov     qword ptr [rsp+2A0h+var_280], r12
0x1800cb571  mov     rax, [rcx]
0x1800cb574  mov     rax, [rax+10h]
0x1800cb578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb57d  nop
0x1800cb57e  mov     rcx, [rsp+2A0h+pv]; pv
0x1800cb583  test    rcx, rcx
0x1800cb586  jz      short loc_1800CB58E
0x1800cb588  call    cs:__imp_CoTaskMemFree
0x1800cb58e  mov     eax, ebx
0x1800cb590  jmp     loc_1800CB3F5
0x1800cb595  mov     rcx, [rbp+1A8h]; this
0x1800cb59c  mov     r9d, ebx; char *
0x1800cb59f  lea     r8, aDesktopInterna_9; "desktop\\internal\\shell\\inc\\private"...
0x1800cb5a6  mov     edx, 26h ; '&'; void *
0x1800cb5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb5b0  nop
0x1800cb5b1  lea     rcx, [rsp+2A0h+var_280]
0x1800cb5b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb5bb  nop
0x1800cb5bc  lea     rcx, [rsp+2A0h+pv]
0x1800cb5c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800cb5c6  mov     eax, ebx
0x1800cb5c8  jmp     loc_1800CB3F5
```
