# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000e1fc`
- end: `0x18000e268`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000746c`

## callees

- `0x18000e1fc`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e224`
- `KERNEL32!GetModuleHandleW` at `0x18000e224`
- `KERNEL32!GetProcAddress` at `0x18000e241`
- `KERNEL32!GetProcAddress` at `0x18000e241`

## string_xrefs

- `0x18000e21d`: `ntdll.dll`
- `0x18000e237`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::UnregisterWilFeatureConfigurationChange(wil::details *this, void *a2)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(wil::details *, void *))ProcAddress)(this, a2);
}

```

## disassembly

```asm
0x18000e1fc  push    rbx
0x18000e1fe  sub     rsp, 20h
0x18000e202  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000e209  mov     rbx, rcx
0x18000e20c  test    rax, rax
0x18000e20f  jnz     short loc_18000E259
0x18000e211  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e218  test    rax, rax
0x18000e21b  jnz     short loc_18000E237
0x18000e21d  lea     rcx, ModuleName; "ntdll.dll"
0x18000e224  call    cs:__imp_GetModuleHandleW
0x18000e22b  nop     dword ptr [rax+rax+00h]
0x18000e230  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e237  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000e23e  mov     rcx, rax; hModule
0x18000e241  call    cs:__imp_GetProcAddress
0x18000e248  nop     dword ptr [rax+rax+00h]
0x18000e24d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000e254  test    rax, rax
0x18000e257  jz      short loc_18000E261
0x18000e259  mov     rcx, rbx
0x18000e25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e261  add     rsp, 20h
0x18000e265  pop     rbx
0x18000e266  retn
```
