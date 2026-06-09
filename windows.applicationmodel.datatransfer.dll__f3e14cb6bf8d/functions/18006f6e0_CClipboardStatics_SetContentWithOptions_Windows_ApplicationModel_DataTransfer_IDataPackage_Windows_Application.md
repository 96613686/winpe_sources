# CClipboardStatics::SetContentWithOptions(Windows::ApplicationModel::DataTransfer::IDataPackage *,Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *,uchar *)

- ea: `0x18006f6e0`
- end: `0x18006fcd3`
- name: `?SetContentWithOptions@CClipboardStatics@@UEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEAUIClipboardContentOptions@345@PEAE@Z`
- size: `1523`
- prototype: `__int64 __fastcall(CClipboardStatics *__hidden this, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18005679c`
- `0x18006f6e0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f8e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f94c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006fa96`

## string_xrefs

- `0x18006fb9f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006fc2f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006fc44`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006fc97`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18006fcac`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CClipboardStatics::SetContentWithOptions(
        CClipboardStatics *this,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage *a2,
        struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *a3,
        bool *a4)
{
  CClipboardStatics *v7; // rdi
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int v23; // r14d
  int i; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, HSTRING *); // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rbx
  int v34; // eax
  int v35; // esi
  int j; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, HSTRING *); // rbx
  int v39; // eax
  int v40; // eax
  unsigned int v41; // ecx
  const char *v42; // r9
  __int64 result; // rax
  int v44; // [rsp+20h] [rbp-98h] BYREF
  int v45; // [rsp+24h] [rbp-94h] BYREF
  __int64 v46; // [rsp+28h] [rbp-90h]
  unsigned int v47; // [rsp+30h] [rbp-88h]
  HSTRING string; // [rsp+38h] [rbp-80h] BYREF
  __int64 *v49; // [rsp+40h] [rbp-78h] BYREF
  __int64 v50; // [rsp+48h] [rbp-70h] BYREF
  __int64 v51; // [rsp+50h] [rbp-68h] BYREF
  __int64 v52; // [rsp+58h] [rbp-60h] BYREF
  __int64 v53; // [rsp+60h] [rbp-58h] BYREF
  __int64 v54; // [rsp+68h] [rbp-50h] BYREF
  __int64 v55; // [rsp+70h] [rbp-48h]
  int v56; // [rsp+78h] [rbp-40h]
  __int64 v57; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v60; // [rsp+C8h] [rbp+10h] BYREF

  try
  {
    v7 = this;
    if ( a2 && a3 )
    {
      v8 = *(_QWORD *)a2;
      v54 = 0;
      v9 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 *))(v8 + 56))(
             a2,
             &v54);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x35E,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v9,
          v44);
      v49 = 0;
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v54)(
              v54,
              &GUID_77aa17b6_418f_47ec_b993_c8b13de82645,
              &v49);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v10,
          v44);
      LOBYTE(v60) = 0;
      v11 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *, int *))(*(_QWORD *)a3 + 48LL))(
              a3,
              &v60);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x362,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v11,
          v44);
      LOBYTE(v12) = v60;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v49 + 56))(v49, v12);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x363,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v13,
          v44);
      LOBYTE(v44) = 0;
      v14 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *, int *))(*(_QWORD *)a3 + 64LL))(
              a3,
              &v44);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x366,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v14,
          v44);
      LOBYTE(v15) = v44;
      v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v49 + 72))(v49, v15);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x367,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v16,
          v44);
      v17 = *(_QWORD *)a3;
      v53 = 0;
      v18 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *, __int64 *))(v17 + 80))(
              a3,
              &v53);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x36A,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v18,
          v44);
      v51 = 0;
      v19 = *v49;
      v51 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 80))(v49, &v51);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x36D,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v20,
          v44);
      v21 = v53;
      v46 = v53;
      v47 = 0;
      string = 0;
      v45 = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v45);
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v22,
          v44);
      v55 = v21;
      v23 = v45;
      v56 = v45;
      v57 = 0;
      for ( i = v47; i != v23; i = ++v47 )
      {
        v25 = v46;
        v26 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v46 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v27 = v26(v25, v47, &string);
        if ( v27 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v27,
            v44);
        v28 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v51 + 104LL))(v51, string);
        if ( v28 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x370,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
            (const char *)(unsigned int)v28,
            v44);
      }
      WindowsDeleteString(0);
      WindowsDeleteString(string);
      v29 = *(_QWORD *)a3;
      v52 = 0;
      v30 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IClipboardContentOptions *, __int64 *))(v29 + 88))(
              a3,
              &v52);
      if ( v30 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x374,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v30,
          v44);
      v50 = 0;
      v31 = *v49;
      v50 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v31 + 88))(v49, &v50);
      if ( v32 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x377,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
          (const char *)(unsigned int)v32,
          v44);
      v33 = v52;
      v46 = v52;
      v47 = 0;
      string = 0;
      v45 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 56LL))(v52, &v45);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v34,
          v44);
      v55 = v33;
      v35 = v45;
      v56 = v45;
      v57 = 0;
      for ( j = v47; j != v35; j = ++v47 )
      {
        v37 = v46;
        v38 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v46 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v39 = v38(v37, v47, &string);
        if ( v39 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v39,
            v44);
        v40 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v50 + 104LL))(v50, string);
        if ( v40 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x37A,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
            (const char *)(unsigned int)v40,
            v44);
      }
      WindowsDeleteString(0);
      WindowsDeleteString(string);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      if ( v52 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v49 )
        (*(void (__fastcall **)(__int64 *))(*v49 + 16))(v49);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v7 = this;
    }
    v41 = (*(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::DataTransfer::IDataPackage *))(*((_QWORD *)v7 - 1) + 56LL))(
            (__int64)v7 - 8,
            a2);
    *a4 = (v41 & 0x80000000) == 0;
    if ( v41 == -2147024891 || v41 == -2147221040 )
      v41 = 0;
    result = v41;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x382,
                           (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboard.cpp",
                           v42);
  }
  return result;
}

```

## disassembly

```asm
0x18006f6e0  mov     r11, rsp
0x18006f6e3  mov     [r11+18h], rbx
0x18006f6e7  mov     [r11+20h], rsi
0x18006f6eb  mov     [r11+8], rcx
0x18006f6ef  push    rdi
0x18006f6f0  push    r12
0x18006f6f2  push    r13
0x18006f6f4  push    r14
0x18006f6f6  push    r15
0x18006f6f8  sub     rsp, 90h
0x18006f6ff  mov     r13, r9
0x18006f702  mov     rsi, r8
0x18006f705  mov     r12, rdx
0x18006f708  mov     rdi, rcx
0x18006f70b  xor     r15d, r15d
0x18006f70e  test    rdx, rdx
0x18006f711  jz      loc_18006FB2F
0x18006f717  test    r8, r8
0x18006f71a  jz      loc_18006FB2F
0x18006f720  mov     rax, [rdx]
0x18006f723  mov     [r11-50h], r15
0x18006f727  lea     rdx, [r11-50h]
0x18006f72b  mov     rcx, r12
0x18006f72e  mov     rax, [rax+38h]
0x18006f732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f737  mov     rcx, [rsp+0B8h]; this
0x18006f73f  test    eax, eax
0x18006f741  js      loc_18006FB88
0x18006f747  mov     rcx, [rsp+0B8h+var_50]
0x18006f74c  mov     [rsp+0B8h+var_78], r15
0x18006f751  mov     rax, [rcx]
0x18006f754  lea     r8, [rsp+0B8h+var_78]
0x18006f759  lea     rdx, _GUID_77aa17b6_418f_47ec_b993_c8b13de82645
0x18006f760  mov     rax, [rax]
0x18006f763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f768  mov     rcx, [rsp+0B8h]; this
0x18006f770  test    eax, eax
0x18006f772  js      loc_18006FB9C
0x18006f778  mov     byte ptr [rsp+0B8h+arg_8], r15b
0x18006f780  mov     rax, [rsi]
0x18006f783  lea     rdx, [rsp+0B8h+arg_8]
0x18006f78b  mov     rcx, rsi
0x18006f78e  mov     rax, [rax+30h]
0x18006f792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f797  mov     rcx, [rsp+0B8h]; this
0x18006f79f  test    eax, eax
0x18006f7a1  js      loc_18006FBB1
0x18006f7a7  mov     rcx, [rsp+0B8h+var_78]
0x18006f7ac  mov     rax, [rcx]
0x18006f7af  mov     dl, byte ptr [rsp+0B8h+arg_8]
0x18006f7b6  mov     rax, [rax+38h]
0x18006f7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7bf  mov     rcx, [rsp+0B8h]; this
0x18006f7c7  test    eax, eax
0x18006f7c9  js      loc_18006FBC5
0x18006f7cf  mov     byte ptr [rsp+0B8h+var_98], r15b; int
0x18006f7d4  mov     rax, [rsi]
0x18006f7d7  lea     rdx, [rsp+0B8h+var_98]
0x18006f7dc  mov     rcx, rsi
0x18006f7df  mov     rax, [rax+40h]
0x18006f7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7e8  mov     rcx, [rsp+0B8h]; this
0x18006f7f0  test    eax, eax
0x18006f7f2  js      loc_18006FBD9
0x18006f7f8  mov     rcx, [rsp+0B8h+var_78]
0x18006f7fd  mov     rax, [rcx]
0x18006f800  mov     dl, byte ptr [rsp+0B8h+var_98]
0x18006f804  mov     rax, [rax+48h]
0x18006f808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f80d  mov     rcx, [rsp+0B8h]; this
0x18006f815  test    eax, eax
0x18006f817  js      loc_18006FBED
0x18006f81d  mov     rax, [rsi]
0x18006f820  mov     [rsp+0B8h+var_58], r15
0x18006f825  lea     rdx, [rsp+0B8h+var_58]
0x18006f82a  mov     rcx, rsi
0x18006f82d  mov     rax, [rax+50h]
0x18006f831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f836  mov     rcx, [rsp+0B8h]; this
0x18006f83e  test    eax, eax
0x18006f840  js      loc_18006FC02
0x18006f846  mov     [rsp+0B8h+var_68], r15
0x18006f84b  mov     rcx, [rsp+0B8h+var_78]
0x18006f850  mov     rax, [rcx]
0x18006f853  mov     [rsp+0B8h+var_68], r15
0x18006f858  lea     rdx, [rsp+0B8h+var_68]
0x18006f85d  mov     rax, [rax+50h]
0x18006f861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f866  mov     rcx, [rsp+0B8h]; this
0x18006f86e  test    eax, eax
0x18006f870  js      loc_18006FC17
0x18006f876  mov     rbx, [rsp+0B8h+var_58]
0x18006f87b  mov     [rsp+0B8h+var_90], rbx
0x18006f880  mov     [rsp+0B8h+var_88], r15d
0x18006f885  mov     [rsp+0B8h+string], r15
0x18006f88a  mov     [rsp+0B8h+var_94], r15d
0x18006f88f  mov     rax, [rbx]
0x18006f892  lea     rdx, [rsp+0B8h+var_94]
0x18006f897  mov     rcx, rbx
0x18006f89a  mov     rax, [rax+38h]
0x18006f89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8a3  mov     rcx, [rsp+0B8h]; this
0x18006f8ab  test    eax, eax
0x18006f8ad  js      loc_18006FC2C
0x18006f8b3  mov     [rsp+0B8h+var_48], rbx
0x18006f8b8  mov     r14d, [rsp+0B8h+var_94]
0x18006f8bd  mov     [rsp+0B8h+var_40], r14d
0x18006f8c2  mov     [rsp+0B8h+var_38], r15
0x18006f8ca  mov     eax, [rsp+0B8h+var_88]
0x18006f8ce  cmp     eax, r14d
0x18006f8d1  jz      short loc_18006F949
0x18006f8d3  mov     rdi, [rsp+0B8h+var_90]
0x18006f8d8  mov     rax, [rdi]
0x18006f8db  mov     rbx, [rax+30h]
0x18006f8df  mov     rcx, [rsp+0B8h+string]; string
0x18006f8e4  call    cs:__imp_WindowsDeleteString
0x18006f8ea  mov     [rsp+0B8h+string], 0
0x18006f8f3  lea     r8, [rsp+0B8h+string]
0x18006f8f8  mov     edx, [rsp+0B8h+var_88]
0x18006f8fc  mov     rcx, rdi
0x18006f8ff  mov     rax, rbx
0x18006f902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f907  mov     rcx, [rsp+0B8h]; this
0x18006f90f  test    eax, eax
0x18006f911  js      loc_18006FC41
0x18006f917  mov     rcx, [rsp+0B8h+var_68]
0x18006f91c  mov     rax, [rcx]
0x18006f91f  mov     rdx, [rsp+0B8h+string]
0x18006f924  mov     rax, [rax+68h]
0x18006f928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f92d  mov     rcx, [rsp+0B8h]; this
0x18006f935  test    eax, eax
0x18006f937  js      loc_18006FC55
0x18006f93d  mov     eax, [rsp+0B8h+var_88]
0x18006f941  inc     eax
0x18006f943  mov     [rsp+0B8h+var_88], eax
0x18006f947  jmp     short loc_18006F8CE
0x18006f949  mov     rcx, r15; string
0x18006f94c  call    cs:__imp_WindowsDeleteString
0x18006f952  nop
0x18006f953  mov     rcx, [rsp+0B8h+string]; string
0x18006f958  call    cs:__imp_WindowsDeleteString
0x18006f95e  nop
0x18006f95f  mov     rax, [rsi]
0x18006f962  xor     r15d, r15d
0x18006f965  mov     [rsp+0B8h+var_60], r15
0x18006f96a  lea     rdx, [rsp+0B8h+var_60]
0x18006f96f  mov     rcx, rsi
0x18006f972  mov     rax, [rax+58h]
0x18006f976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f97b  mov     rcx, [rsp+0B8h]; this
0x18006f983  test    eax, eax
0x18006f985  js      loc_18006FC6A
0x18006f98b  mov     [rsp+0B8h+var_70], r15
0x18006f990  mov     rcx, [rsp+0B8h+var_78]
0x18006f995  mov     rax, [rcx]
0x18006f998  mov     [rsp+0B8h+var_70], r15
0x18006f99d  lea     rdx, [rsp+0B8h+var_70]
0x18006f9a2  mov     rax, [rax+58h]
0x18006f9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9ab  mov     rcx, [rsp+0B8h]; this
0x18006f9b3  test    eax, eax
0x18006f9b5  js      loc_18006FC7F
0x18006f9bb  mov     rbx, [rsp+0B8h+var_60]
0x18006f9c0  mov     [rsp+0B8h+var_90], rbx
0x18006f9c5  mov     [rsp+0B8h+var_88], r15d
0x18006f9ca  mov     [rsp+0B8h+string], r15
0x18006f9cf  mov     [rsp+0B8h+var_94], r15d
0x18006f9d4  mov     rax, [rbx]
0x18006f9d7  lea     rdx, [rsp+0B8h+var_94]
0x18006f9dc  mov     rcx, rbx
0x18006f9df  mov     rax, [rax+38h]
0x18006f9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9e8  mov     rcx, [rsp+0B8h]; this
0x18006f9f0  test    eax, eax
0x18006f9f2  js      loc_18006FC94
0x18006f9f8  mov     [rsp+0B8h+var_48], rbx
0x18006f9fd  mov     esi, [rsp+0B8h+var_94]
0x18006fa01  mov     [rsp+0B8h+var_40], esi
0x18006fa05  mov     [rsp+0B8h+var_38], r15
0x18006fa0d  mov     eax, [rsp+0B8h+var_88]
0x18006fa11  cmp     eax, esi
0x18006fa13  jz      short loc_18006FA87
0x18006fa15  mov     rdi, [rsp+0B8h+var_90]
0x18006fa1a  mov     rax, [rdi]
0x18006fa1d  mov     rbx, [rax+30h]
0x18006fa21  mov     rcx, [rsp+0B8h+string]; string
0x18006fa26  call    cs:__imp_WindowsDeleteString
0x18006fa2c  mov     [rsp+0B8h+string], r15
0x18006fa31  lea     r8, [rsp+0B8h+string]
0x18006fa36  mov     edx, [rsp+0B8h+var_88]
0x18006fa3a  mov     rcx, rdi
0x18006fa3d  mov     rax, rbx
0x18006fa40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa45  mov     rcx, [rsp+0B8h]; this
0x18006fa4d  test    eax, eax
0x18006fa4f  js      loc_18006FCA9
0x18006fa55  mov     rcx, [rsp+0B8h+var_70]
0x18006fa5a  mov     rax, [rcx]
0x18006fa5d  mov     rdx, [rsp+0B8h+string]
0x18006fa62  mov     rax, [rax+68h]
0x18006fa66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa6b  mov     rcx, [rsp+0B8h]; this
0x18006fa73  test    eax, eax
0x18006fa75  js      loc_18006FCBD
0x18006fa7b  mov     eax, [rsp+0B8h+var_88]
0x18006fa7f  inc     eax
0x18006fa81  mov     [rsp+0B8h+var_88], eax
0x18006fa85  jmp     short loc_18006FA11
0x18006fa87  mov     rcx, r15; string
0x18006fa8a  call    cs:__imp_WindowsDeleteString
0x18006fa90  nop
0x18006fa91  mov     rcx, [rsp+0B8h+string]; string
0x18006fa96  call    cs:__imp_WindowsDeleteString
0x18006fa9c  nop
0x18006fa9d  mov     rcx, [rsp+0B8h+var_70]
0x18006faa2  test    rcx, rcx
0x18006faa5  jz      short loc_18006FAB4
0x18006faa7  mov     rax, [rcx]
0x18006faaa  mov     rax, [rax+10h]
0x18006faae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fab3  nop
0x18006fab4  mov     rcx, [rsp+0B8h+var_60]
0x18006fab9  test    rcx, rcx
0x18006fabc  jz      short loc_18006FACB
0x18006fabe  mov     rax, [rcx]
0x18006fac1  mov     rax, [rax+10h]
0x18006fac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006faca  nop
0x18006facb  mov     rcx, [rsp+0B8h+var_68]
0x18006fad0  test    rcx, rcx
0x18006fad3  jz      short loc_18006FAE2
0x18006fad5  mov     rax, [rcx]
0x18006fad8  mov     rax, [rax+10h]
0x18006fadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fae1  nop
0x18006fae2  mov     rcx, [rsp+0B8h+var_58]
0x18006fae7  test    rcx, rcx
0x18006faea  jz      short loc_18006FAF9
0x18006faec  mov     rax, [rcx]
0x18006faef  mov     rax, [rax+10h]
0x18006faf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006faf8  nop
0x18006faf9  mov     rcx, [rsp+0B8h+var_78]
0x18006fafe  test    rcx, rcx
0x18006fb01  jz      short loc_18006FB10
0x18006fb03  mov     rax, [rcx]
0x18006fb06  mov     rax, [rax+10h]
0x18006fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb0f  nop
0x18006fb10  mov     rcx, [rsp+0B8h+var_50]
0x18006fb15  test    rcx, rcx
0x18006fb18  jz      short loc_18006FB27
0x18006fb1a  mov     rax, [rcx]
0x18006fb1d  mov     rax, [rax+10h]
0x18006fb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb26  nop
0x18006fb27  mov     rdi, [rsp+0B8h+arg_0]
0x18006fb2f  lea     rcx, [rdi-8]
0x18006fb33  mov     rax, [rcx]
0x18006fb36  mov     rdx, r12
0x18006fb39  mov     rax, [rax+38h]
0x18006fb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb42  mov     ecx, eax
0x18006fb44  shr     eax, 1Fh
0x18006fb47  xor     al, 1
0x18006fb49  mov     [r13+0], al
0x18006fb4d  cmp     ecx, 80070005h
0x18006fb53  jz      short loc_18006FB5D
0x18006fb55  cmp     ecx, 800401D0h
0x18006fb5b  jnz     short loc_18006FB60
0x18006fb5d  mov     ecx, r15d
0x18006fb60  mov     eax, ecx
0x18006fb62  jmp     short loc_18006FB6B
0x18006fb64  mov     eax, [rsp+0B8h+arg_8]
0x18006fb6b  lea     r11, [rsp+0B8h+var_28]
0x18006fb73  mov     rbx, [r11+40h]
0x18006fb77  mov     rsi, [r11+48h]
0x18006fb7b  mov     rsp, r11
0x18006fb7e  pop     r15
0x18006fb80  pop     r14
0x18006fb82  pop     r13
0x18006fb84  pop     r12
0x18006fb86  pop     rdi
0x18006fb87  retn
0x18006fb88  mov     r9d, eax; char *
0x18006fb8b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18006fb92  mov     edx, 35Eh; void *
0x18006fb97  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006fb9c  mov     r9d, eax; char *
0x18006fb9f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006fba6  mov     edx, 1CBEh; void *
0x18006fbab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006fbb1  mov     r9d, eax; char *
0x18006fbb4  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18006fbbb  mov     edx, 362h; void *
0x18006fbc0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006fbc5  mov     r9d, eax; char *
0x18006fbc8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x18006fbcf  mov     edx, 363h; void *
  ... truncated ...
```
