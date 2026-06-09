# ?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z

- ea: `0x14005ad28`
- end: `0x14005adcd`
- name: `?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005b34c`

## callees

- `0x140046a30`
- `0x140053000`
- `0x140057044`
- `0x14005ad28`
- `0x14005d1c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005ad5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005ad5f`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14005adb7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14005adb7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005ad8c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005ad8c`

## string_xrefs

- `0x14005ad3c`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

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
  unsigned int v5; // r8d
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
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC7, v5, (const char *)v4, lpData);
  RegDeleteKeyValueW(hKey, 0, L"CommunicationHWND");
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x14005ad28  sub     rsp, 38h
0x14005ad2c  cmp     qword ptr [rcx], 0
0x14005ad30  setz    al
0x14005ad33  mov     rcx, [rsp+38h]; this
0x14005ad38  test    al, al
0x14005ad3a  jz      short loc_14005AD4E
0x14005ad3c  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14005ad43  mov     edx, 0C1h; void *
0x14005ad48  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14005ad4e  mov     r9d, 20006h
0x14005ad54  lea     rcx, [rsp+38h+hKey]
0x14005ad59  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)
0x14005ad5e  nop
0x14005ad5f  call    cs:__imp_GetCurrentProcessId
0x14005ad65  mov     [rsp+38h+Data], eax
0x14005ad69  mov     r9d, 4; dwType
0x14005ad6f  mov     [rsp+38h+cbData], r9d; cbData
0x14005ad74  lea     rax, [rsp+38h+Data]
0x14005ad79  mov     [rsp+38h+lpData], rax; unsigned int
0x14005ad7e  mov     r8, cs:lpValue; lpValueName
0x14005ad85  xor     edx, edx; lpSubKey
0x14005ad87  mov     rcx, [rsp+38h+hKey]; hKey
0x14005ad8c  call    cs:__imp_RegSetKeyValueW
0x14005ad92  mov     rcx, [rsp+38h]; this
0x14005ad97  test    eax, eax
0x14005ad99  jz      short loc_14005ADA9
0x14005ad9b  mov     r9d, eax; char *
0x14005ad9e  mov     edx, 0C7h; void *
0x14005ada3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14005ada9  mov     r8, cs:lpValueName; lpValueName
0x14005adb0  xor     edx, edx; lpSubKey
0x14005adb2  mov     rcx, [rsp+38h+hKey]; hKey
0x14005adb7  call    cs:__imp_RegDeleteKeyValueW
0x14005adbd  nop
0x14005adbe  lea     rcx, [rsp+38h+hKey]
0x14005adc3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14005adc8  add     rsp, 38h
0x14005adcc  retn
```
