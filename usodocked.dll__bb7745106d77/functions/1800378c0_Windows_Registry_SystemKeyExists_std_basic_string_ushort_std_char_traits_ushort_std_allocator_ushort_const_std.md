# Windows::Registry::SystemKeyExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800378c0`
- end: `0x1800379af`
- name: `?SystemKeyExists@Registry@Windows@@UEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180035ebc`
- `0x1800590f0`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x1800378c0`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037938`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037981`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037938`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037981`

## string_xrefs

- `0x180037966`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::SystemKeyExists(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  const char *v5; // r9
  char v6; // bl
  LPCWSTR *v7; // rax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v11; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a2, a3);
  hKey = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( v11 > 7 )
    v3 = lpSubKey[0];
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = (const char *)v4;
  if ( v4 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    v6 = 0;
  }
  else
  {
    v7 = lpSubKey;
    if ( v11 > 7 )
      v7 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      v5,
      (unsigned int)"%ws",
      (const char *)v7);
    if ( hKey )
      RegCloseKey(hKey);
    v6 = 1;
  }
  std::wstring::_Tidy_deallocate(lpSubKey);
  return v6;
}

```

## disassembly

```asm
0x1800378c0  mov     [rsp-8+arg_18], rbx
0x1800378c5  push    rbp
0x1800378c6  mov     rbp, rsp
0x1800378c9  sub     rsp, 60h
0x1800378cd  mov     rax, cs:__security_cookie
0x1800378d4  xor     rax, rsp
0x1800378d7  mov     [rbp+var_8], rax
0x1800378db  mov     rax, [rcx]
0x1800378de  mov     r9, r8
0x1800378e1  mov     r8, rdx
0x1800378e4  lea     rdx, [rbp+lpSubKey]
0x1800378e8  mov     rax, [rax+58h]
0x1800378ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378f1  nop
0x1800378f2  mov     [rbp+hKey], 0
0x1800378fa  lea     rdx, [rbp+lpSubKey]
0x1800378fe  cmp     [rbp+var_10], 7
0x180037903  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x180037908  lea     rax, [rbp+hKey]
0x18003790c  mov     [rsp+60h+phkResult], rax; phkResult
0x180037911  mov     r9d, 20019h; samDesired
0x180037917  xor     r8d, r8d; ulOptions
0x18003791a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037921  call    cs:__imp_RegOpenKeyExW
0x180037927  mov     r9d, eax; char *
0x18003792a  cmp     eax, 2
0x18003792d  jnz     short loc_180037943
0x18003792f  mov     rcx, [rbp+hKey]; hKey
0x180037933  test    rcx, rcx
0x180037936  jz      short loc_18003793F
0x180037938  call    cs:__imp_RegCloseKey
0x18003793e  nop
0x18003793f  xor     bl, bl
0x180037941  jmp     short loc_18003798A
0x180037943  lea     rax, [rbp+lpSubKey]
0x180037947  cmp     [rbp+var_10], 7
0x18003794c  cmova   rax, [rbp+lpSubKey]
0x180037951  mov     rcx, [rbp+8]; this
0x180037955  mov     [rsp+60h+var_38], rax; char *
0x18003795a  lea     rax, aWs; "%ws"
0x180037961  mov     [rsp+60h+phkResult], rax; unsigned int
0x180037966  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003796d  mov     edx, 0D0h; void *
0x180037972  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180037977  nop
0x180037978  mov     rcx, [rbp+hKey]; hKey
0x18003797c  test    rcx, rcx
0x18003797f  jz      short loc_180037988
0x180037981  call    cs:__imp_RegCloseKey
0x180037987  nop
0x180037988  mov     bl, 1
0x18003798a  lea     rcx, [rbp+lpSubKey]
0x18003798e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037993  mov     al, bl
0x180037995  mov     rcx, [rbp+var_8]
0x180037999  xor     rcx, rsp; StackCookie
0x18003799c  call    __security_check_cookie
0x1800379a1  mov     rbx, [rsp+60h+arg_18]
0x1800379a9  add     rsp, 60h
0x1800379ad  pop     rbp
0x1800379ae  retn
```
