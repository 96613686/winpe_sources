# wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180065bf0`
- end: `0x180065c38`
- name: `??R?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ad80`
- `0x180065bf0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180065c06`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180065c06`

## string_xrefs

- `0x180065c1d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall __R____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEB_WAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___2__Z___A6AJPEA_W_KPEA_K_Z___function_wistd__UEAAJ__QEAPEA_W__QEA_K__QEAPEA_K_Z(
        __int64 a1,
        LPWSTR *a2,
        DWORD *a3,
        _QWORD **a4)
{
  _QWORD *v4; // rbx
  DWORD v5; // eax
  const char *v6; // r9
  unsigned int v7; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = ExpandEnvironmentStringsW(**(LPCWSTR **)(a1 + 8), *a2, *a3);
  v7 = 0;
  *v4 = v5;
  if ( !v5 )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x181,
                           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opens"
                                         "ource\\wil\\win32_helpers.h",
                           v6);
  return v7;
}

```

## disassembly

```asm
0x180065bf0  push    rbx
0x180065bf2  sub     rsp, 20h
0x180065bf6  mov     rcx, [rcx+8]
0x180065bfa  mov     r8d, [r8]; nSize
0x180065bfd  mov     rdx, [rdx]; lpDst
0x180065c00  mov     rbx, [r9]
0x180065c03  mov     rcx, [rcx]; lpSrc
0x180065c06  call    cs:__imp_ExpandEnvironmentStringsW
0x180065c0c  mov     eax, eax
0x180065c0e  xor     ecx, ecx
0x180065c10  mov     [rbx], rax
0x180065c13  test    rax, rax
0x180065c16  jnz     short loc_180065C30
0x180065c18  mov     rcx, [rsp+28h]; this
0x180065c1d  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180065c24  mov     edx, 181h; void *
0x180065c29  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180065c2e  mov     ecx, eax
0x180065c30  mov     eax, ecx
0x180065c32  add     rsp, 20h
0x180065c36  pop     rbx
0x180065c37  retn
```
