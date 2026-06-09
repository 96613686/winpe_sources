# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000b2c8`
- end: `0x18000b334`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003694`

## callees

- `0x18000b2c8`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b30d`
- `KERNEL32!GetProcAddress` at `0x18000b30d`
- `KERNEL32!GetModuleHandleW` at `0x18000b2f0`
- `KERNEL32!GetModuleHandleW` at `0x18000b2f0`

## string_xrefs

- `0x18000b2e9`: `ntdll.dll`
- `0x18000b303`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000b2c8  push    rbx
0x18000b2ca  sub     rsp, 20h
0x18000b2ce  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000b2d5  mov     rbx, rcx
0x18000b2d8  test    rax, rax
0x18000b2db  jnz     short loc_18000B325
0x18000b2dd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b2e4  test    rax, rax
0x18000b2e7  jnz     short loc_18000B303
0x18000b2e9  lea     rcx, ModuleName; "ntdll.dll"
0x18000b2f0  call    cs:__imp_GetModuleHandleW
0x18000b2f7  nop     dword ptr [rax+rax+00h]
0x18000b2fc  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b303  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000b30a  mov     rcx, rax; hModule
0x18000b30d  call    cs:__imp_GetProcAddress
0x18000b314  nop     dword ptr [rax+rax+00h]
0x18000b319  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000b320  test    rax, rax
0x18000b323  jz      short loc_18000B32D
0x18000b325  mov     rcx, rbx
0x18000b328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32d  add     rsp, 20h
0x18000b331  pop     rbx
0x18000b332  retn
```
