# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800146d8`
- end: `0x180014734`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001033c`

## callees

- `0x18000aac8`
- `0x1800146d8`
- `0x18001e010`

## string_xrefs

- `0x1800146f4`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x1800146d8  mov     [rsp+arg_0], rbx
0x1800146dd  push    rdi
0x1800146de  sub     rsp, 30h
0x1800146e2  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800146e9  mov     rbx, r9
0x1800146ec  mov     rdi, rdx
0x1800146ef  test    rax, rax
0x1800146f2  jnz     short loc_180014713
0x1800146f4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800146fb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180014700  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180014707  test    rax, rax
0x18001470a  jnz     short loc_180014713
0x18001470c  mov     eax, 0C0000139h
0x180014711  jmp     short loc_180014728
0x180014713  mov     r9, rbx
0x180014716  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18001471d  xor     r8d, r8d
0x180014720  mov     rdx, rdi
0x180014723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014728  mov     rbx, [rsp+38h+arg_0]
0x18001472d  add     rsp, 30h
0x180014731  pop     rdi
0x180014732  retn
```
