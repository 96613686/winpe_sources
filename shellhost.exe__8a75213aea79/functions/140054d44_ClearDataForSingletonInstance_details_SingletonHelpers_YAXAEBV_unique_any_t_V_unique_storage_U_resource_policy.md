# ?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z

- ea: `0x140054d44`
- end: `0x140054dac`
- name: `?ClearDataForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140053358`

## callees

- `0x140046a30`
- `0x140053000`
- `0x140054d44`
- `0x140057044`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140054d83`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140054d97`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140054d83`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140054d97`

## string_xrefs

- `0x140054d8e`: `CommunicationHWND`
- `0x140054d53`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
__int64 __fastcall SingletonHelpers::details::ClearDataForSingletonInstance(
        _QWORD *a1,
        __int64 *a2,
        HKEY *a3,
        const char *a4)
{
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD1,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      a4);
  SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, a2, a3, 0x20006u);
  RegDeleteKeyValueW(hKey, 0, L"ProcessId");
  RegDeleteKeyValueW(hKey, 0, L"CommunicationHWND");
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x140054d44  sub     rsp, 28h
0x140054d48  cmp     qword ptr [rcx], 0
0x140054d4c  jnz     short loc_140054D65
0x140054d4e  mov     rcx, [rsp+28h]; this
0x140054d53  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x140054d5a  mov     edx, 0D1h; void *
0x140054d5f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140054d65  mov     r9d, 20006h
0x140054d6b  lea     rcx, [rsp+28h+hKey]
0x140054d70  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)
0x140054d75  mov     r8, cs:lpValue; lpValueName
0x140054d7c  xor     edx, edx; lpSubKey
0x140054d7e  mov     rcx, [rsp+28h+hKey]; hKey
0x140054d83  call    cs:__imp_RegDeleteKeyValueW
0x140054d89  mov     rcx, [rsp+28h+hKey]; hKey
0x140054d8e  lea     r8, aCommunicationh_0; "CommunicationHWND"
0x140054d95  xor     edx, edx; lpSubKey
0x140054d97  call    cs:__imp_RegDeleteKeyValueW
0x140054d9d  lea     rcx, [rsp+28h+hKey]
0x140054da2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140054da7  add     rsp, 28h
0x140054dab  retn
```
