# GetFileExtensionStringForAppResolverFromStorageFile(Windows::Storage::IStorageFile *)

- ea: `0x180048d94`
- end: `0x180048eef`
- name: `?GetFileExtensionStringForAppResolverFromStorageFile@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIStorageFile@Storage@Windows@@@Z`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180047ff0`
- `0x180079650`

## callees

- `0x18000f194`
- `0x18001eb40`
- `0x180048d94`
- `0x18004a4ec`
- `0x18004a820`
- `0x18004acdc`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180048e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048e55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048ec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048dd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048ec9`

## string_xrefs

- `0x180048dfb`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048e23`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180048ea9`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HSTRING *__fastcall GetFileExtensionStringForAppResolverFromStorageFile(HSTRING *a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v7; // rcx
  HRESULT v8; // eax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  int v11; // [rsp+28h] [rbp-38h]
  HSTRING *v12; // [rsp+30h] [rbp-30h]
  PCNZWCH sourceString[2]; // [rsp+38h] [rbp-28h] BYREF
  UINT32 length; // [rsp+48h] [rbp-18h]
  unsigned __int64 v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v12 = a1;
  v11 = 0;
  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
  if ( !string )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80004005LL,
      0);
  std::wstring::wstring(sourceString);
  std::wstring::assign(sourceString, L"file:///");
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::append(sourceString, StringRawBuffer);
  *a1 = 0;
  v11 = 1;
  WindowsDeleteString(0);
  *a1 = 0;
  v7 = (const WCHAR *)sourceString;
  if ( v15 > 7 )
    v7 = sourceString[0];
  v8 = WindowsCreateString(v7, length, a1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
  std::wstring::_Tidy_deallocate(sourceString);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x180048d94  mov     [rsp-18h+arg_10], rbx
0x180048d99  push    rbp
0x180048d9a  push    rsi
0x180048d9b  push    rdi
0x180048d9c  mov     rbp, rsp
0x180048d9f  sub     rsp, 60h
0x180048da3  mov     rax, cs:__security_cookie
0x180048daa  xor     rax, rsp
0x180048dad  mov     [rbp+var_8], rax
0x180048db1  mov     rdi, rdx
0x180048db4  mov     rsi, rcx
0x180048db7  mov     [rbp+var_30], rcx
0x180048dbb  mov     [rbp+var_38], 0
0x180048dc2  mov     [rbp+string], 0
0x180048dca  mov     rax, [rdx]
0x180048dcd  mov     rbx, [rax+30h]
0x180048dd1  xor     ecx, ecx; string
0x180048dd3  call    cs:__imp_WindowsDeleteString
0x180048dd9  mov     [rbp+string], 0
0x180048de1  lea     rdx, [rbp+string]
0x180048de5  mov     rcx, rdi
0x180048de8  mov     rax, rbx
0x180048deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048df0  mov     rcx, [rbp+18h]; this
0x180048df4  test    eax, eax
0x180048df6  jns     short loc_180048E0D
0x180048df8  mov     r9d, eax; char *
0x180048dfb  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048e02  mov     edx, 114h; void *
0x180048e07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048e0d  cmp     [rbp+string], 0
0x180048e12  setnz   al
0x180048e15  mov     rcx, [rbp+18h]; this
0x180048e19  test    al, al
0x180048e1b  jnz     short loc_180048E35
0x180048e1d  mov     r9d, 80004005h; char *
0x180048e23  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048e2a  mov     edx, 115h; void *
0x180048e2f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048e35  lea     rcx, [rbp+sourceString]
0x180048e39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180048e3e  nop
0x180048e3f  lea     rdx, aFile; "file:///"
0x180048e46  lea     rcx, [rbp+sourceString]
0x180048e4a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180048e4f  xor     edx, edx; length
0x180048e51  mov     rcx, [rbp+string]; string
0x180048e55  call    cs:__imp_WindowsGetStringRawBuffer
0x180048e5b  mov     rdx, rax
0x180048e5e  lea     rcx, [rbp+sourceString]
0x180048e62  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180048e67  mov     qword ptr [rsi], 0
0x180048e6e  mov     [rbp+var_38], 1
0x180048e75  xor     ecx, ecx; string
0x180048e77  call    cs:__imp_WindowsDeleteString
0x180048e7d  mov     qword ptr [rsi], 0
0x180048e84  lea     rcx, [rbp+sourceString]
0x180048e88  cmp     [rbp+var_10], 7
0x180048e8d  cmova   rcx, [rbp+sourceString]; sourceString
0x180048e92  mov     r8, rsi; string
0x180048e95  mov     edx, [rbp+length]; length
0x180048e98  call    cs:__imp_WindowsCreateString
0x180048e9e  mov     rcx, [rbp+18h]; this
0x180048ea2  test    eax, eax
0x180048ea4  jns     short loc_180048EBB
0x180048ea6  mov     r9d, eax; char *
0x180048ea9  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180048eb0  mov     edx, 11Eh; void *
0x180048eb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048ebb  lea     rcx, [rbp+sourceString]
0x180048ebf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048ec4  nop
0x180048ec5  mov     rcx, [rbp+string]; string
0x180048ec9  call    cs:__imp_WindowsDeleteString
0x180048ecf  mov     rax, rsi
0x180048ed2  mov     rcx, [rbp+var_8]
0x180048ed6  xor     rcx, rsp; StackCookie
0x180048ed9  call    __security_check_cookie
0x180048ede  mov     rbx, [rsp+60h+arg_10]
0x180048ee6  add     rsp, 60h
0x180048eea  pop     rdi
0x180048eeb  pop     rsi
0x180048eec  pop     rbp
0x180048eed  retn
```
