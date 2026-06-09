# ?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z

- ea: `0x18042d1c4`
- end: `0x18042d274`
- name: `?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18042e86c`

## callees

- `0x18000fea0`
- `0x1800795e4`
- `0x1800e3810`
- `0x180429d48`
- `0x18042d1c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18042d1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18042d1ed`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18042d21a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18042d21a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18042d237`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18042d237`

## string_xrefs

- `0x18042d250`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x18042d262`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SingletonHelpers::details::SetPIDAndClearCommunicationHWNDForSingletonInstance(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  unsigned int v4; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( !*a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC1,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      a4);
  SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, a2, a3, 131078);
  Data = GetCurrentProcessId();
  v4 = RegSetKeyValueW(hKey, 0, L"ProcessId", 4u, &Data, 4u);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC7,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      (const char *)v4,
      lpData);
  RegDeleteKeyValueW(hKey, 0, L"CommunicationHWND");
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18042d1c4  sub     rsp, 38h
0x18042d1c8  cmp     qword ptr [rcx], 0
0x18042d1cc  setz    al
0x18042d1cf  mov     rcx, [rsp+38h]; this
0x18042d1d4  test    al, al
0x18042d1d6  jnz     loc_18042D262
0x18042d1dc  mov     r9d, 20006h
0x18042d1e2  lea     rcx, [rsp+38h+hKey]
0x18042d1e7  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)
0x18042d1ec  nop
0x18042d1ed  call    cs:__imp_GetCurrentProcessId
0x18042d1f3  mov     [rsp+38h+Data], eax
0x18042d1f7  mov     r9d, 4; dwType
0x18042d1fd  mov     [rsp+38h+cbData], r9d; cbData
0x18042d202  lea     rax, [rsp+38h+Data]
0x18042d207  mov     [rsp+38h+lpData], rax; unsigned int
0x18042d20c  mov     r8, cs:lpValue; lpValueName
0x18042d213  xor     edx, edx; lpSubKey
0x18042d215  mov     rcx, [rsp+38h+hKey]; hKey
0x18042d21a  call    cs:__imp_RegSetKeyValueW
0x18042d220  mov     rcx, [rsp+38h]; this
0x18042d225  test    eax, eax
0x18042d227  jnz     short loc_18042D24D
0x18042d229  mov     r8, cs:off_1804EACC0; lpValueName
0x18042d230  xor     edx, edx; lpSubKey
0x18042d232  mov     rcx, [rsp+38h+hKey]; hKey
0x18042d237  call    cs:__imp_RegDeleteKeyValueW
0x18042d23d  nop
0x18042d23e  lea     rcx, [rsp+38h+hKey]
0x18042d243  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18042d248  add     rsp, 38h
0x18042d24c  retn
0x18042d24d  mov     r9d, eax; char *
0x18042d250  lea     r8, aShellcommonInt_10; "shellcommon\\internal\\shell\\inc\\Sing"...
0x18042d257  mov     edx, 0C7h; void *
0x18042d25c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18042d262  lea     r8, aShellcommonInt_10; "shellcommon\\internal\\shell\\inc\\Sing"...
0x18042d269  mov     edx, 0C1h; void *
0x18042d26e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
