# _lambda_e38df6b79d544ed5fff633626cb07f41_::operator()

- ea: `0x1800b2ccc`
- end: `0x1800b3059`
- name: `_lambda_e38df6b79d544ed5fff633626cb07f41_::operator()`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ae208`

## callees

- `0x18000f194`
- `0x180035b50`
- `0x18003d454`
- `0x18003d498`
- `0x18004a844`
- `0x18004acdc`
- `0x180067b6c`
- `0x180070c80`
- `0x18008a030`
- `0x1800b2ccc`
- `0x1800b3060`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800b2d3b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800b2d3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2d2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2ecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b2f9a`

## string_xrefs

- `0x1800b2fc9`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b2fde`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b2ff3`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b3008`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b301d`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b3032`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800b3047`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall lambda_e38df6b79d544ed5fff633626cb07f41_::operator()(
        __int64 a1,
        struct Windows::Foundation::IExtensionRegistration *a2)
{
  int AppIdForExtensionListItem; // eax
  char v5; // di
  const WCHAR *v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v8; // r8
  _BYTE *v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // r15
  const WCHAR *v12; // r8
  __int64 (__fastcall *v13)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v14; // rbx
  int v15; // eax
  __int64 (__fastcall *v16)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v17; // rbx
  int v18; // eax
  __int64 (__fastcall *v19)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v20; // rbx
  int v21; // eax
  __int64 (__fastcall *v22)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v23; // rbx
  int v24; // eax
  __int64 (__fastcall *v25)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v26; // rbx
  int v27; // eax
  __int64 (__fastcall *v28)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v29; // rbx
  int v30; // eax
  HSTRING string; // [rsp+20h] [rbp-59h] BYREF
  _BYTE *v33; // [rsp+30h] [rbp-49h] BYREF
  _BYTE *v34; // [rsp+38h] [rbp-41h]
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  __int64 v36; // [rsp+58h] [rbp-21h]
  LPCWCH lpString2[4]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v38[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  WindowsDeleteString(0);
  string = 0;
  AppIdForExtensionListItem = GetAppIdForExtensionListItem(a2, &string);
  if ( AppIdForExtensionListItem < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)AppIdForExtensionListItem,
      (int)string);
  v5 = 1;
  v6 = **(const WCHAR ***)a1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !StrCmpIW(StringRawBuffer, v6) )
  {
    v8 = **(_QWORD **)(a1 + 8);
    if ( !v8 || **(_BYTE **)(a1 + 16) )
    {
      v25 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 72LL);
      v26 = *(HSTRING **)(a1 + 24);
      WindowsDeleteString(*v26);
      *v26 = 0;
      v27 = v25(a2, v26);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x420,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v27,
          (int)string);
      v28 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 48LL);
      v29 = *(HSTRING **)(a1 + 32);
      WindowsDeleteString(*v29);
      *v29 = 0;
      v30 = v28(a2, v29);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x421,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
          (const char *)(unsigned int)v30,
          (int)string);
      v5 = 0;
    }
    else
    {
      DeserializeExtensionPropertyValue(&v35, a2, v8, 44);
      v9 = *(_BYTE **)(a1 + 48);
      v10 = v35;
      v33 = *(_BYTE **)(a1 + 40);
      v34 = v9;
      v11 = v36;
      if ( v35 == v36 )
      {
LABEL_9:
        if ( *v9 )
        {
          std::wstring::wstring(v38);
          DeserializeExtensionPropertyValue(&v33, a2, L"Name", 0);
          if ( v33 != v34 )
          {
            std::wstring::wstring(lpString2, v33);
            v12 = (const WCHAR *)lpString2;
            if ( lpString2[3] > (LPCWCH)7 )
              v12 = lpString2[0];
            if ( IsDynamicAppUriExtension(
                   **(const unsigned __int16 ***)(a1 + 40),
                   **(const unsigned __int16 ***)(a1 + 56),
                   v12) )
            {
              v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 72LL);
              v14 = *(HSTRING **)(a1 + 24);
              WindowsDeleteString(*v14);
              *v14 = 0;
              v15 = v13(a2, v14);
              if ( v15 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x44A,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                  (const char *)(unsigned int)v15,
                  (int)string);
              v16 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 48LL);
              v17 = *(HSTRING **)(a1 + 32);
              WindowsDeleteString(*v17);
              *v17 = 0;
              v18 = v16(a2, v17);
              if ( v18 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x44B,
                  (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
                  (const char *)(unsigned int)v18,
                  (int)string);
              v5 = 0;
            }
            std::wstring::_Tidy_deallocate(lpString2);
          }
          std::vector<std::wstring>::_Tidy(&v33);
          std::wstring::_Tidy_deallocate(v38);
        }
      }
      else
      {
        while ( !(unsigned __int8)lambda_eeb3f6d8ed10b446a2eb00ae49277c78_::operator()(&v33, v10) )
        {
          v10 += 32;
          if ( v10 == v11 )
          {
            v9 = *(_BYTE **)(a1 + 48);
            goto LABEL_9;
          }
        }
        v19 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 72LL);
        v20 = *(HSTRING **)(a1 + 24);
        WindowsDeleteString(*v20);
        *v20 = 0;
        v21 = v19(a2, v20);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x43C,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v21,
            (int)string);
        v22 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 48LL);
        v23 = *(HSTRING **)(a1 + 32);
        WindowsDeleteString(*v23);
        *v23 = 0;
        v24 = v22(a2, v23);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x43D,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
            (const char *)(unsigned int)v24,
            (int)string);
        v5 = 0;
      }
      std::vector<std::wstring>::_Tidy(&v35);
    }
  }
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x1800b2ccc  mov     [rsp-8+arg_10], rbx
0x1800b2cd1  push    rbp
0x1800b2cd2  push    rsi
0x1800b2cd3  push    rdi
0x1800b2cd4  push    r14
0x1800b2cd6  push    r15
0x1800b2cd8  lea     rbp, [rsp-37h]
0x1800b2cdd  sub     rsp, 0B0h
0x1800b2ce4  mov     rax, cs:__security_cookie
0x1800b2ceb  xor     rax, rsp
0x1800b2cee  mov     [rbp+57h+var_28], rax
0x1800b2cf2  mov     r14, rdx
0x1800b2cf5  mov     rsi, rcx
0x1800b2cf8  xor     ecx, ecx; string
0x1800b2cfa  call    cs:__imp_WindowsDeleteString
0x1800b2d00  mov     [rbp+57h+string], 0
0x1800b2d08  lea     rdx, [rbp+57h+string]; HSTRING *
0x1800b2d0c  mov     rcx, r14; struct Windows::Foundation::IExtensionRegistration *
0x1800b2d0f  call    ?GetAppIdForExtensionListItem@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; GetAppIdForExtensionListItem(Windows::Foundation::IExtensionRegistration *,HSTRING__ * *)
0x1800b2d14  mov     rcx, [rbp+5Fh]; this
0x1800b2d18  test    eax, eax
0x1800b2d1a  js      loc_1800B2FDB
0x1800b2d20  mov     dil, 1
0x1800b2d23  mov     rax, [rsi]
0x1800b2d26  mov     rbx, [rax]
0x1800b2d29  xor     edx, edx; length
0x1800b2d2b  mov     rcx, [rbp+57h+string]; string
0x1800b2d2f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2d35  mov     rdx, rbx; psz2
0x1800b2d38  mov     rcx, rax; psz1
0x1800b2d3b  call    cs:__imp_StrCmpIW
0x1800b2d41  test    eax, eax
0x1800b2d43  jnz     loc_1800B2F96
0x1800b2d49  mov     rax, [rsi+8]
0x1800b2d4d  mov     r8, [rax]
0x1800b2d50  test    r8, r8
0x1800b2d53  jz      loc_1800B2F2D
0x1800b2d59  mov     rax, [rsi+10h]
0x1800b2d5d  cmp     byte ptr [rax], 0
0x1800b2d60  jnz     loc_1800B2F2D
0x1800b2d66  mov     r9d, 2Ch ; ','
0x1800b2d6c  mov     rdx, r14
0x1800b2d6f  lea     rcx, [rbp+57h+var_80]
0x1800b2d73  call    ?DeserializeExtensionPropertyValue@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUIExtensionRegistration@Foundation@Windows@@PEBGG@Z; DeserializeExtensionPropertyValue(Windows::Foundation::IExtensionRegistration *,ushort const *,ushort)
0x1800b2d78  nop
0x1800b2d79  mov     rcx, [rsi+30h]
0x1800b2d7d  mov     rbx, [rbp+57h+var_80]
0x1800b2d81  mov     rax, [rsi+28h]
0x1800b2d85  mov     [rbp+57h+var_A0], rax
0x1800b2d89  mov     [rbp+57h+var_98], rcx
0x1800b2d8d  mov     r15, [rbp+57h+var_78]
0x1800b2d91  cmp     rbx, r15
0x1800b2d94  jz      short loc_1800B2DB7
0x1800b2d96  mov     rdx, rbx
0x1800b2d99  lea     rcx, [rbp+57h+var_A0]
0x1800b2d9d  call    _lambda_eeb3f6d8ed10b446a2eb00ae49277c78___operator__
0x1800b2da2  test    al, al
0x1800b2da4  jnz     loc_1800B2EBE
0x1800b2daa  add     rbx, 20h ; ' '
0x1800b2dae  cmp     rbx, r15
0x1800b2db1  jnz     short loc_1800B2D96
0x1800b2db3  mov     rcx, [rsi+30h]
0x1800b2db7  cmp     byte ptr [rcx], 0
0x1800b2dba  jz      loc_1800B2EB0
0x1800b2dc0  mov     rdx, [rsi+28h]
0x1800b2dc4  mov     rdx, [rdx]
0x1800b2dc7  lea     rcx, [rbp+57h+var_48]
0x1800b2dcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b2dd0  nop
0x1800b2dd1  xor     r9d, r9d
0x1800b2dd4  lea     r8, aName; "Name"
0x1800b2ddb  mov     rdx, r14
0x1800b2dde  lea     rcx, [rbp+57h+var_A0]
0x1800b2de2  call    ?DeserializeExtensionPropertyValue@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUIExtensionRegistration@Foundation@Windows@@PEBGG@Z; DeserializeExtensionPropertyValue(Windows::Foundation::IExtensionRegistration *,ushort const *,ushort)
0x1800b2de7  nop
0x1800b2de8  mov     rdx, [rbp+57h+var_A0]
0x1800b2dec  cmp     rdx, [rbp+57h+var_98]
0x1800b2df0  jz      loc_1800B2E9C
0x1800b2df6  lea     rcx, [rbp+57h+lpString2]
0x1800b2dfa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b2dff  nop
0x1800b2e00  lea     r8, [rbp+57h+lpString2]
0x1800b2e04  cmp     [rbp+57h+var_50], 7
0x1800b2e09  cmova   r8, [rbp+57h+lpString2]; lpString2
0x1800b2e0e  mov     rdx, [rsi+38h]
0x1800b2e12  mov     rcx, [rsi+28h]
0x1800b2e16  mov     rdx, [rdx]; unsigned __int16 *
0x1800b2e19  mov     rcx, [rcx]; unsigned __int16 *
0x1800b2e1c  call    ?IsDynamicAppUriExtension@@YA_NPEBG00@Z; IsDynamicAppUriExtension(ushort const *,ushort const *,ushort const *)
0x1800b2e21  test    al, al
0x1800b2e23  jz      short loc_1800B2E92
0x1800b2e25  mov     rax, [r14]
0x1800b2e28  mov     rdi, [rax+48h]
0x1800b2e2c  mov     rbx, [rsi+18h]
0x1800b2e30  mov     rcx, [rbx]; string
0x1800b2e33  call    cs:__imp_WindowsDeleteString
0x1800b2e39  mov     qword ptr [rbx], 0
0x1800b2e40  mov     rdx, rbx
0x1800b2e43  mov     rcx, r14
0x1800b2e46  mov     rax, rdi
0x1800b2e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e4e  mov     rcx, [rbp+5Fh]; this
0x1800b2e52  test    eax, eax
0x1800b2e54  js      loc_1800B2FF0
0x1800b2e5a  mov     rax, [r14]
0x1800b2e5d  mov     rdi, [rax+30h]
0x1800b2e61  mov     rbx, [rsi+20h]
0x1800b2e65  mov     rcx, [rbx]; string
0x1800b2e68  call    cs:__imp_WindowsDeleteString
0x1800b2e6e  mov     qword ptr [rbx], 0
0x1800b2e75  mov     rdx, rbx
0x1800b2e78  mov     rcx, r14
0x1800b2e7b  mov     rax, rdi
0x1800b2e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e83  mov     rcx, [rbp+5Fh]; this
0x1800b2e87  test    eax, eax
0x1800b2e89  js      loc_1800B302F
0x1800b2e8f  xor     dil, dil
0x1800b2e92  lea     rcx, [rbp+57h+lpString2]
0x1800b2e96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b2e9b  nop
0x1800b2e9c  lea     rcx, [rbp+57h+var_A0]
0x1800b2ea0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800b2ea5  nop
0x1800b2ea6  lea     rcx, [rbp+57h+var_48]
0x1800b2eaa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b2eaf  nop
0x1800b2eb0  lea     rcx, [rbp+57h+var_80]
0x1800b2eb4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800b2eb9  jmp     loc_1800B2F96
0x1800b2ebe  mov     rax, [r14]
0x1800b2ec1  mov     rdi, [rax+48h]
0x1800b2ec5  mov     rbx, [rsi+18h]
0x1800b2ec9  mov     rcx, [rbx]; string
0x1800b2ecc  call    cs:__imp_WindowsDeleteString
0x1800b2ed2  mov     qword ptr [rbx], 0
0x1800b2ed9  mov     rdx, rbx
0x1800b2edc  mov     rcx, r14
0x1800b2edf  mov     rax, rdi
0x1800b2ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2ee7  mov     rcx, [rbp+5Fh]; this
0x1800b2eeb  test    eax, eax
0x1800b2eed  js      loc_1800B3005
0x1800b2ef3  mov     rax, [r14]
0x1800b2ef6  mov     rdi, [rax+30h]
0x1800b2efa  mov     rbx, [rsi+20h]
0x1800b2efe  mov     rcx, [rbx]; string
0x1800b2f01  call    cs:__imp_WindowsDeleteString
0x1800b2f07  mov     qword ptr [rbx], 0
0x1800b2f0e  mov     rdx, rbx
0x1800b2f11  mov     rcx, r14
0x1800b2f14  mov     rax, rdi
0x1800b2f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f1c  mov     rcx, [rbp+5Fh]; this
0x1800b2f20  test    eax, eax
0x1800b2f22  js      loc_1800B301A
0x1800b2f28  xor     dil, dil
0x1800b2f2b  jmp     short loc_1800B2EB0
0x1800b2f2d  mov     rax, [r14]
0x1800b2f30  mov     rdi, [rax+48h]
0x1800b2f34  mov     rbx, [rsi+18h]
0x1800b2f38  mov     rcx, [rbx]; string
0x1800b2f3b  call    cs:__imp_WindowsDeleteString
0x1800b2f41  mov     qword ptr [rbx], 0
0x1800b2f48  mov     rdx, rbx
0x1800b2f4b  mov     rcx, r14
0x1800b2f4e  mov     rax, rdi
0x1800b2f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f56  mov     rcx, [rbp+5Fh]; this
0x1800b2f5a  test    eax, eax
0x1800b2f5c  js      loc_1800B3044
0x1800b2f62  mov     rax, [r14]
0x1800b2f65  mov     rdi, [rax+30h]
0x1800b2f69  mov     rbx, [rsi+20h]
0x1800b2f6d  mov     rcx, [rbx]; string
0x1800b2f70  call    cs:__imp_WindowsDeleteString
0x1800b2f76  mov     qword ptr [rbx], 0
0x1800b2f7d  mov     rdx, rbx
0x1800b2f80  mov     rcx, r14
0x1800b2f83  mov     rax, rdi
0x1800b2f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f8b  mov     rcx, [rbp+5Fh]; this
0x1800b2f8f  test    eax, eax
0x1800b2f91  js      short loc_1800B2FC6
0x1800b2f93  xor     dil, dil
0x1800b2f96  mov     rcx, [rbp+57h+string]; string
0x1800b2f9a  call    cs:__imp_WindowsDeleteString
0x1800b2fa0  mov     al, dil
0x1800b2fa3  mov     rcx, [rbp+57h+var_28]
0x1800b2fa7  xor     rcx, rsp; StackCookie
0x1800b2faa  call    __security_check_cookie
0x1800b2faf  mov     rbx, [rsp+0D0h+arg_10]
0x1800b2fb7  add     rsp, 0B0h
0x1800b2fbe  pop     r15
0x1800b2fc0  pop     r14
0x1800b2fc2  pop     rdi
0x1800b2fc3  pop     rsi
0x1800b2fc4  pop     rbp
0x1800b2fc5  retn
0x1800b2fc6  mov     r9d, eax; char *
0x1800b2fc9  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b2fd0  mov     edx, 421h; void *
0x1800b2fd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2fdb  mov     r9d, eax; char *
0x1800b2fde  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b2fe5  mov     edx, 41Bh; void *
0x1800b2fea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b2ff0  mov     r9d, eax; char *
0x1800b2ff3  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b2ffa  mov     edx, 44Ah; void *
0x1800b2fff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3005  mov     r9d, eax; char *
0x1800b3008  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b300f  mov     edx, 43Ch; void *
0x1800b3014  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b301a  mov     r9d, eax; char *
0x1800b301d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b3024  mov     edx, 43Dh; void *
0x1800b3029  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b302f  mov     r9d, eax; char *
0x1800b3032  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b3039  mov     edx, 44Bh; void *
0x1800b303e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b3044  mov     r9d, eax; char *
0x1800b3047  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800b304e  mov     edx, 420h; void *
0x1800b3053  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
