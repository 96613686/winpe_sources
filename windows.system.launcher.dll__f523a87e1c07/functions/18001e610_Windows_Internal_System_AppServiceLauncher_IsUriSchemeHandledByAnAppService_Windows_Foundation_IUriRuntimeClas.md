# Windows::Internal::System::AppServiceLauncher::IsUriSchemeHandledByAnAppService(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x18001e610`
- end: `0x18001e824`
- name: `?IsUriSchemeHandledByAnAppService@AppServiceLauncher@System@Internal@Windows@@SA_NPEAUIUriRuntimeClass@Foundation@4@@Z`
- size: `532`
- prototype: `bool __fastcall(struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d790`
- `0x18001e350`
- `0x180043b30`
- `0x18009b640`

## callees

- `0x18000f194`
- `0x18001e610`
- `0x180034ba0`
- `0x18004a888`
- `0x18004a8a0`
- `0x18004aa38`
- `0x18004acdc`
- `0x1800596d8`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e754`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e779`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e7f7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e7f7`

## string_xrefs

- `0x18001e7ca`: `onecoreuap\shell\windows.system.launcher\launcherappservicelib\lib\windows.internal.system.appservicelauncher.cpp`
- `0x18001e6e0`: `SOFTWARE\Microsoft\AppServiceProtocols\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall Windows::Internal::System::AppServiceLauncher::IsUriSchemeHandledByAnAppService(
        struct Windows::Foundation::IUriRuntimeClass *a1)
{
  char v2; // di
  int (__fastcall *v3)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  const WCHAR *v9; // rdx
  LSTATUS v11; // eax
  HSTRING_HEADER *v12; // rax
  int phkResult; // [rsp+20h] [rbp-78h]
  int phkResulta; // [rsp+20h] [rbp-78h]
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-58h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+58h] [rbp-40h]
  __int64 v19; // [rsp+60h] [rbp-38h]
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-30h] BYREF
  __int128 v21; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  hKey = (HKEY)L"uri";
  if ( !a1 )
  {
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            (HSTRING_HEADER *)lpSubKey,
            (const WCHAR **)&hKey);
    RoOriginateError(2147500035LL, v12[1].Reserved.Reserved1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
      (const char *)0x80004003LL,
      phkResult);
  }
  v2 = 0;
  string = 0;
  v3 = *(int (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v3(a1, &string) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v5 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Construct<1,unsigned short const *>(&v17, v6, v5);
    *(_OWORD *)lpSubKey = 0;
    v21 = 0;
    v7 = std::_WChar_traits<unsigned short>::length(L"SOFTWARE\\Microsoft\\AppServiceProtocols\\");
    std::wstring::_Construct<1,unsigned short const *>(lpSubKey, v8, v7);
    std::wstring::_Append<unsigned short>(lpSubKey);
    hKey = 0;
    v9 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v9 = lpSubKey[0];
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey) )
    {
      v2 = 1;
      v11 = RegCloseKey(hKey);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\launcherappservicelib\\lib\\windows.internal.system."
                        "appservicelauncher.cpp",
          (const char *)(unsigned int)v11,
          phkResulta);
    }
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(&v17);
  }
  WindowsDeleteString(string);
  return v2;
}

```

## disassembly

```asm
0x18001e610  mov     r11, rsp
0x18001e613  mov     [r11+10h], rbx
0x18001e617  mov     [r11+18h], rsi
0x18001e61b  push    rdi
0x18001e61c  sub     rsp, 90h
0x18001e623  mov     rax, cs:__security_cookie
0x18001e62a  xor     rax, rsp
0x18001e62d  mov     [rsp+98h+var_10], rax
0x18001e635  mov     rsi, rcx
0x18001e638  lea     rax, aUri_1; "uri"
0x18001e63f  mov     [r11-58h], rax
0x18001e643  test    rcx, rcx
0x18001e646  jz      loc_18001E7DD
0x18001e64c  xor     dil, dil
0x18001e64f  mov     [rsp+98h+var_68], dil
0x18001e654  mov     qword ptr [r11-60h], 0
0x18001e65c  mov     rax, [rcx]
0x18001e65f  mov     rbx, [rax+88h]
0x18001e666  xor     ecx, ecx; string
0x18001e668  call    cs:__imp_WindowsDeleteString
0x18001e66e  mov     [rsp+98h+string], 0
0x18001e677  lea     rdx, [rsp+98h+string]
0x18001e67c  mov     rcx, rsi
0x18001e67f  mov     rax, rbx
0x18001e682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e687  test    eax, eax
0x18001e689  js      loc_18001E774
0x18001e68f  xor     edx, edx; length
0x18001e691  mov     rcx, [rsp+98h+string]; string
0x18001e696  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e69c  mov     rcx, rax
0x18001e69f  xorps   xmm0, xmm0
0x18001e6a2  movups  [rsp+98h+var_50], xmm0
0x18001e6a7  mov     [rsp+98h+var_40], 0
0x18001e6b0  mov     [rsp+98h+var_38], 0
0x18001e6b9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001e6be  mov     r8, rax
0x18001e6c1  mov     rdx, rcx
0x18001e6c4  lea     rcx, [rsp+98h+var_50]
0x18001e6c9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e6ce  nop
0x18001e6cf  xorps   xmm0, xmm0
0x18001e6d2  movups  xmmword ptr [rsp+98h+lpSubKey], xmm0
0x18001e6d7  xorps   xmm1, xmm1
0x18001e6da  movdqu  [rsp+98h+var_20], xmm1
0x18001e6e0  lea     rcx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\AppServiceProtocol"...
0x18001e6e7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001e6ec  mov     r8, rax
0x18001e6ef  mov     rdx, rcx
0x18001e6f2  lea     rcx, [rsp+98h+lpSubKey]
0x18001e6f7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e6fc  nop
0x18001e6fd  lea     rdx, [rsp+98h+var_50]
0x18001e702  cmp     [rsp+98h+var_38], 7
0x18001e708  cmova   rdx, qword ptr [rsp+98h+var_50]
0x18001e70e  mov     r8, [rsp+98h+var_40]
0x18001e713  lea     rcx, [rsp+98h+lpSubKey]; Src
0x18001e718  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001e71d  mov     [rsp+98h+hKey], 0
0x18001e726  lea     rdx, [rsp+98h+lpSubKey]
0x18001e72b  cmp     qword ptr [rsp+98h+var_20+8], 7
0x18001e734  cmova   rdx, [rsp+98h+lpSubKey]; lpSubKey
0x18001e73a  lea     rax, [rsp+98h+hKey]
0x18001e73f  mov     qword ptr [rsp+98h+phkResult], rax; int
0x18001e744  mov     r9d, 20019h; samDesired
0x18001e74a  xor     r8d, r8d; ulOptions
0x18001e74d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e754  call    cs:__imp_RegOpenKeyExW
0x18001e75a  test    eax, eax
0x18001e75c  jz      short loc_18001E7A8
0x18001e75e  lea     rcx, [rsp+98h+lpSubKey]
0x18001e763  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e768  nop
0x18001e769  lea     rcx, [rsp+98h+var_50]
0x18001e76e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e773  nop
0x18001e774  mov     rcx, [rsp+98h+string]; string
0x18001e779  call    cs:__imp_WindowsDeleteString
0x18001e77f  nop
0x18001e780  mov     al, dil
0x18001e783  mov     rcx, [rsp+98h+var_10]
0x18001e78b  xor     rcx, rsp; StackCookie
0x18001e78e  call    __security_check_cookie
0x18001e793  lea     r11, [rsp+98h+var_8]
0x18001e79b  mov     rbx, [r11+18h]
0x18001e79f  mov     rsi, [r11+20h]
0x18001e7a3  mov     rsp, r11
0x18001e7a6  pop     rdi
0x18001e7a7  retn
0x18001e7a8  mov     dil, 1
0x18001e7ab  mov     [rsp+98h+var_68], dil
0x18001e7b0  mov     rcx, [rsp+98h+hKey]; hKey
0x18001e7b5  call    cs:__imp_RegCloseKey
0x18001e7bb  mov     rcx, [rsp+98h]; this
0x18001e7c3  test    eax, eax
0x18001e7c5  jns     short loc_18001E75E
0x18001e7c7  mov     r9d, eax; char *
0x18001e7ca  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.system.launc"...
0x18001e7d1  mov     edx, 5Ch ; '\'; void *
0x18001e7d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e7db  jmp     short loc_18001E75E
0x18001e7dd  lea     rdx, [rsp+98h+hKey]
0x18001e7e2  lea     rcx, [rsp+98h+lpSubKey]
0x18001e7e7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e7ec  mov     rdx, [rax+18h]
0x18001e7f0  mov     ebx, 80004003h
0x18001e7f5  mov     ecx, ebx
0x18001e7f7  call    cs:__imp_RoOriginateError
0x18001e7fd  mov     rcx, [rsp+98h]; this
0x18001e805  mov     r9d, ebx; char *
0x18001e808  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x18001e80f  mov     edx, 1A2h; void *
0x18001e814  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e81a  mov     dil, [rsp+98h+var_68]
0x18001e81f  jmp     loc_18001E780
```
