# Windows::Registry::SystemValueExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800379c0`
- end: `0x180037b3a`
- name: `?SystemValueExists@Registry@Windows@@UEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180058764`
- `0x180058c80`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x1800379c0`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037a22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037a22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037a39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037a39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037b12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037aba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037aba`

## string_xrefs

- `0x180037a7e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x180037af7`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::SystemValueExists(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  const char *v7; // r9
  char v8; // bl
  _QWORD *v9; // rdx
  LPCWSTR *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int Value; // eax
  const char *v13; // r9
  LPCWSTR *v14; // rax
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a2, a3);
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( v18 > 7 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = (const char *)v6;
  if ( v6 == 2 )
    goto LABEL_4;
  if ( a4[3] <= 7u )
    v9 = a4;
  else
    v9 = (_QWORD *)*a4;
  v10 = lpSubKey;
  if ( v18 > 7 )
    v10 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xA2,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
    v7,
    (unsigned int)"%ws[%ws]",
    (const char *)v10,
    v9);
  v11 = a4[3] <= 7u ? (const WCHAR *)a4 : (const WCHAR *)*a4;
  Value = RegQueryValueExW(hKey, v11, 0, 0, 0, 0);
  v13 = (const char *)Value;
  if ( Value == 2 )
  {
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    v8 = 0;
  }
  else
  {
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    v14 = lpSubKey;
    if ( v18 > 7 )
      v14 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
      v13,
      (unsigned int)"%ws[%ws]",
      (const char *)v14,
      a4);
    if ( hKey )
      RegCloseKey(hKey);
    v8 = 1;
  }
  std::wstring::_Tidy_deallocate(lpSubKey);
  return v8;
}

```

## disassembly

```asm
0x1800379c0  push    rbp
0x1800379c2  push    rbx
0x1800379c3  push    rsi
0x1800379c4  mov     rbp, rsp
0x1800379c7  sub     rsp, 70h
0x1800379cb  mov     rax, cs:__security_cookie
0x1800379d2  xor     rax, rsp
0x1800379d5  mov     [rbp+var_8], rax
0x1800379d9  mov     rbx, r9
0x1800379dc  mov     rax, [rcx]
0x1800379df  mov     r9, r8
0x1800379e2  mov     r8, rdx
0x1800379e5  lea     rdx, [rbp+lpSubKey]
0x1800379e9  mov     rax, [rax+58h]
0x1800379ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379f2  nop
0x1800379f3  mov     [rbp+hKey], 0
0x1800379fb  lea     rdx, [rbp+lpSubKey]
0x1800379ff  cmp     [rbp+var_10], 7
0x180037a04  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x180037a09  lea     rax, [rbp+hKey]
0x180037a0d  mov     [rsp+70h+phkResult], rax; phkResult
0x180037a12  mov     r9d, 20019h; samDesired
0x180037a18  xor     r8d, r8d; ulOptions
0x180037a1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037a22  call    cs:__imp_RegOpenKeyExW
0x180037a28  mov     r9d, eax; char *
0x180037a2b  cmp     eax, 2
0x180037a2e  jnz     short loc_180037A47
0x180037a30  mov     rcx, [rbp+hKey]; hKey
0x180037a34  test    rcx, rcx
0x180037a37  jz      short loc_180037A40
0x180037a39  call    cs:__imp_RegCloseKey
0x180037a3f  nop
0x180037a40  xor     bl, bl
0x180037a42  jmp     loc_180037B1B
0x180037a47  cmp     qword ptr [rbx+18h], 7
0x180037a4c  jbe     short loc_180037A53
0x180037a4e  mov     rdx, [rbx]
0x180037a51  jmp     short loc_180037A56
0x180037a53  mov     rdx, rbx
0x180037a56  lea     rax, [rbp+lpSubKey]
0x180037a5a  cmp     [rbp+var_10], 7
0x180037a5f  cmova   rax, [rbp+lpSubKey]
0x180037a64  mov     rcx, [rbp+18h]; this
0x180037a68  mov     [rsp+70h+var_40], rdx
0x180037a6d  mov     [rsp+70h+lpcbData], rax; char *
0x180037a72  lea     rsi, aWsWs; "%ws[%ws]"
0x180037a79  mov     [rsp+70h+phkResult], rsi; unsigned int
0x180037a7e  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180037a85  mov     edx, 0A2h; void *
0x180037a8a  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180037a8f  cmp     qword ptr [rbx+18h], 7
0x180037a94  jbe     short loc_180037A9B
0x180037a96  mov     rdx, [rbx]
0x180037a99  jmp     short loc_180037A9E
0x180037a9b  mov     rdx, rbx; lpValueName
0x180037a9e  mov     [rsp+70h+lpcbData], 0; lpcbData
0x180037aa7  mov     [rsp+70h+phkResult], 0; lpData
0x180037ab0  xor     r9d, r9d; lpType
0x180037ab3  xor     r8d, r8d; lpReserved
0x180037ab6  mov     rcx, [rbp+hKey]; hKey
0x180037aba  call    cs:__imp_RegQueryValueExW
0x180037ac0  mov     r9d, eax; char *
0x180037ac3  cmp     eax, 2
0x180037ac6  jz      loc_180037A30
0x180037acc  cmp     qword ptr [rbx+18h], 7
0x180037ad1  jbe     short loc_180037AD6
0x180037ad3  mov     rbx, [rbx]
0x180037ad6  lea     rax, [rbp+lpSubKey]
0x180037ada  cmp     [rbp+var_10], 7
0x180037adf  cmova   rax, [rbp+lpSubKey]
0x180037ae4  mov     rcx, [rbp+18h]; this
0x180037ae8  mov     [rsp+70h+var_40], rbx
0x180037aed  mov     [rsp+70h+lpcbData], rax; char *
0x180037af2  mov     [rsp+70h+phkResult], rsi; unsigned int
0x180037af7  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180037afe  mov     edx, 0AFh; void *
0x180037b03  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180037b08  nop
0x180037b09  mov     rcx, [rbp+hKey]; hKey
0x180037b0d  test    rcx, rcx
0x180037b10  jz      short loc_180037B19
0x180037b12  call    cs:__imp_RegCloseKey
0x180037b18  nop
0x180037b19  mov     bl, 1
0x180037b1b  lea     rcx, [rbp+lpSubKey]
0x180037b1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037b24  mov     al, bl
0x180037b26  mov     rcx, [rbp+var_8]
0x180037b2a  xor     rcx, rsp; StackCookie
0x180037b2d  call    __security_check_cookie
0x180037b32  add     rsp, 70h
0x180037b36  pop     rsi
0x180037b37  pop     rbx
0x180037b38  pop     rbp
0x180037b39  retn
```
