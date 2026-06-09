# Windows::Registry::SetSystemVolatileKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180037480`
- end: `0x180037576`
- name: `?SetSystemVolatileKey@Registry@Windows@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x180037480`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037550`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037550`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037501`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037501`

## string_xrefs

- `0x180037534`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Registry::SetSystemVolatileKey(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  LPCWSTR *v5; // rdx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int64 v9; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a2, a3);
  hKey = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( v9 > 7 )
    v3 = lpSubKey[0];
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
  v5 = lpSubKey;
  if ( v9 > 7 )
    v5 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x126,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
    (const char *)v4,
    (unsigned int)"%ws",
    (const char *)v5);
  if ( hKey )
    RegCloseKey(hKey);
  return std::wstring::_Tidy_deallocate(lpSubKey);
}

```

## disassembly

```asm
0x180037480  sub     rsp, 88h
0x180037487  mov     rax, cs:__security_cookie
0x18003748e  xor     rax, rsp
0x180037491  mov     [rsp+88h+var_10], rax
0x180037496  mov     rax, [rcx]
0x180037499  mov     r9, r8
0x18003749c  mov     r8, rdx
0x18003749f  lea     rdx, [rsp+88h+lpSubKey]
0x1800374a4  mov     rax, [rax+58h]
0x1800374a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374ad  nop
0x1800374ae  mov     [rsp+88h+hKey], 0
0x1800374b7  lea     rdx, [rsp+88h+lpSubKey]
0x1800374bc  cmp     [rsp+88h+var_18], 7
0x1800374c2  cmova   rdx, [rsp+88h+lpSubKey]; lpSubKey
0x1800374c8  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800374d1  lea     rax, [rsp+88h+hKey]
0x1800374d6  mov     [rsp+88h+phkResult], rax; phkResult
0x1800374db  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800374e4  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x1800374ec  mov     [rsp+88h+dwOptions], 1; dwOptions
0x1800374f4  xor     r9d, r9d; lpClass
0x1800374f7  xor     r8d, r8d; Reserved
0x1800374fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037501  call    cs:__imp_RegCreateKeyExW
0x180037507  lea     rdx, [rsp+88h+lpSubKey]
0x18003750c  cmp     [rsp+88h+var_18], 7
0x180037512  cmova   rdx, [rsp+88h+lpSubKey]
0x180037518  mov     rcx, [rsp+88h]; this
0x180037520  mov     qword ptr [rsp+88h+samDesired], rdx; char *
0x180037525  lea     rdx, aWs; "%ws"
0x18003752c  mov     qword ptr [rsp+88h+dwOptions], rdx; unsigned int
0x180037531  mov     r9d, eax; char *
0x180037534  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003753b  mov     edx, 126h; void *
0x180037540  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180037545  nop
0x180037546  mov     rcx, [rsp+88h+hKey]; hKey
0x18003754b  test    rcx, rcx
0x18003754e  jz      short loc_180037557
0x180037550  call    cs:__imp_RegCloseKey
0x180037556  nop
0x180037557  lea     rcx, [rsp+88h+lpSubKey]
0x18003755c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037561  mov     rcx, [rsp+88h+var_10]
0x180037566  xor     rcx, rsp; StackCookie
0x180037569  call    __security_check_cookie
0x18003756e  add     rsp, 88h
0x180037575  retn
```
