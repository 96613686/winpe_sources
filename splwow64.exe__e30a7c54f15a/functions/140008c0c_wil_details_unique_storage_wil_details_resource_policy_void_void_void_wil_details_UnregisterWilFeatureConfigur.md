# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140008c0c`
- end: `0x140008c70`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140008e9c`

## callees

- `0x140008c0c`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140008c50`
- `KERNEL32!GetProcAddress` at `0x140008c50`
- `KERNEL32!GetModuleHandleW` at `0x140008c39`
- `KERNEL32!GetModuleHandleW` at `0x140008c39`

## string_xrefs

- `0x140008c32`: `ntdll.dll`
- `0x140008c46`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
      goto LABEL_6;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x140008c0c  push    rbx
0x140008c0e  sub     rsp, 20h
0x140008c12  mov     rbx, [rcx]
0x140008c15  test    rbx, rbx
0x140008c18  jz      short loc_140008C6A
0x140008c1a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140008c21  test    rax, rax
0x140008c24  jnz     short loc_140008C62
0x140008c26  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008c2d  test    rax, rax
0x140008c30  jnz     short loc_140008C46
0x140008c32  lea     rcx, ModuleName; "ntdll.dll"
0x140008c39  call    cs:__imp_GetModuleHandleW
0x140008c3f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008c46  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140008c4d  mov     rcx, rax; hModule
0x140008c50  call    cs:__imp_GetProcAddress
0x140008c56  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140008c5d  test    rax, rax
0x140008c60  jz      short loc_140008C6A
0x140008c62  mov     rcx, rbx
0x140008c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c6a  add     rsp, 20h
0x140008c6e  pop     rbx
0x140008c6f  retn
```
