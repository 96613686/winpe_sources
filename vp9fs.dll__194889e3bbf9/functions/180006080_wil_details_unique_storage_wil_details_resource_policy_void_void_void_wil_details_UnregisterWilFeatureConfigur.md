# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180006080`
- end: `0x1800060e5`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006158`

## callees

- `0x180006080`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800060c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800060c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800060ad`

## string_xrefs

- `0x1800060a6`: `ntdll.dll`
- `0x1800060ba`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180006080  push    rbx
0x180006082  sub     rsp, 20h
0x180006086  mov     rbx, [rcx]
0x180006089  test    rbx, rbx
0x18000608c  jz      short loc_1800060DF
0x18000608e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180006095  test    rax, rax
0x180006098  jnz     short loc_1800060D6
0x18000609a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800060a1  test    rax, rax
0x1800060a4  jnz     short loc_1800060BA
0x1800060a6  lea     rcx, ModuleName; "ntdll.dll"
0x1800060ad  call    cs:__imp_GetModuleHandleW
0x1800060b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800060ba  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x1800060c1  mov     rcx, rax; hModule
0x1800060c4  call    cs:__imp_GetProcAddress
0x1800060ca  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800060d1  test    rax, rax
0x1800060d4  jz      short loc_1800060DF
0x1800060d6  mov     rcx, rbx
0x1800060d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060de  nop
0x1800060df  add     rsp, 20h
0x1800060e3  pop     rbx
0x1800060e4  retn
```
