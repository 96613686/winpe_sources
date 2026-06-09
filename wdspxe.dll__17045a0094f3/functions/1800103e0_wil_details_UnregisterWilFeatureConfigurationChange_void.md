# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x1800103e0`
- end: `0x18001044c`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180009da0`

## callees

- `0x1800103e0`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010425`
- `KERNEL32!GetProcAddress` at `0x180010425`
- `KERNEL32!GetModuleHandleW` at `0x180010408`
- `KERNEL32!GetModuleHandleW` at `0x180010408`

## string_xrefs

- `0x180010401`: `ntdll.dll`
- `0x18001041b`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800103e0  push    rbx
0x1800103e2  sub     rsp, 20h
0x1800103e6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800103ed  mov     rbx, rcx
0x1800103f0  test    rax, rax
0x1800103f3  jnz     short loc_18001043D
0x1800103f5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800103fc  test    rax, rax
0x1800103ff  jnz     short loc_18001041B
0x180010401  lea     rcx, ModuleName; "ntdll.dll"
0x180010408  call    cs:__imp_GetModuleHandleW
0x18001040f  nop     dword ptr [rax+rax+00h]
0x180010414  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001041b  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180010422  mov     rcx, rax; hModule
0x180010425  call    cs:__imp_GetProcAddress
0x18001042c  nop     dword ptr [rax+rax+00h]
0x180010431  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180010438  test    rax, rax
0x18001043b  jz      short loc_180010445
0x18001043d  mov     rcx, rbx
0x180010440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010445  add     rsp, 20h
0x180010449  pop     rbx
0x18001044a  retn
```
