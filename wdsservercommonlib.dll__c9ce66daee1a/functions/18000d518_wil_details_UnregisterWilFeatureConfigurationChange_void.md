# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000d518`
- end: `0x18000d584`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180008cb8`

## callees

- `0x18000d518`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d55d`
- `KERNEL32!GetProcAddress` at `0x18000d55d`
- `KERNEL32!GetModuleHandleW` at `0x18000d540`
- `KERNEL32!GetModuleHandleW` at `0x18000d540`

## string_xrefs

- `0x18000d539`: `ntdll.dll`
- `0x18000d553`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000d518  push    rbx
0x18000d51a  sub     rsp, 20h
0x18000d51e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000d525  mov     rbx, rcx
0x18000d528  test    rax, rax
0x18000d52b  jnz     short loc_18000D575
0x18000d52d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d534  test    rax, rax
0x18000d537  jnz     short loc_18000D553
0x18000d539  lea     rcx, ModuleName; "ntdll.dll"
0x18000d540  call    cs:__imp_GetModuleHandleW
0x18000d547  nop     dword ptr [rax+rax+00h]
0x18000d54c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d553  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000d55a  mov     rcx, rax; hModule
0x18000d55d  call    cs:__imp_GetProcAddress
0x18000d564  nop     dword ptr [rax+rax+00h]
0x18000d569  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000d570  test    rax, rax
0x18000d573  jz      short loc_18000D57D
0x18000d575  mov     rcx, rbx
0x18000d578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57d  add     rsp, 20h
0x18000d581  pop     rbx
0x18000d582  retn
```
