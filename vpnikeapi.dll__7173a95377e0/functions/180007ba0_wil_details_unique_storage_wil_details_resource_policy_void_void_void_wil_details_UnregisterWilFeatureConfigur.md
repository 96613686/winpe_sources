# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180007ba0`
- end: `0x180007be0`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007cd0`

## callees

- `0x180007ba0`
- `0x18000c12c`
- `0x18000e010`

## string_xrefs

- `0x180007bba`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax

  v1 = *a1;
  if ( *a1 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v1);
    }
  }
}

```

## disassembly

```asm
0x180007ba0  push    rbx
0x180007ba2  sub     rsp, 20h
0x180007ba6  mov     rbx, [rcx]
0x180007ba9  test    rbx, rbx
0x180007bac  jz      short loc_180007BDA
0x180007bae  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180007bb5  test    rax, rax
0x180007bb8  jnz     short loc_180007BD2
0x180007bba  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180007bc1  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180007bc6  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180007bcd  test    rax, rax
0x180007bd0  jz      short loc_180007BDA
0x180007bd2  mov     rcx, rbx
0x180007bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bda  add     rsp, 20h
0x180007bde  pop     rbx
0x180007bdf  retn
```
