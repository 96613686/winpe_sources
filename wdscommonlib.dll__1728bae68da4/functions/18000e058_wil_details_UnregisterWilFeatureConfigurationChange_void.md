# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000e058`
- end: `0x18000e0c4`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800097fc`

## callees

- `0x18000e058`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e09d`
- `KERNEL32!GetProcAddress` at `0x18000e09d`
- `KERNEL32!GetModuleHandleW` at `0x18000e080`
- `KERNEL32!GetModuleHandleW` at `0x18000e080`

## string_xrefs

- `0x18000e079`: `ntdll.dll`
- `0x18000e093`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000e058  push    rbx
0x18000e05a  sub     rsp, 20h
0x18000e05e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000e065  mov     rbx, rcx
0x18000e068  test    rax, rax
0x18000e06b  jnz     short loc_18000E0B5
0x18000e06d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e074  test    rax, rax
0x18000e077  jnz     short loc_18000E093
0x18000e079  lea     rcx, ModuleName; "ntdll.dll"
0x18000e080  call    cs:__imp_GetModuleHandleW
0x18000e087  nop     dword ptr [rax+rax+00h]
0x18000e08c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e093  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000e09a  mov     rcx, rax; hModule
0x18000e09d  call    cs:__imp_GetProcAddress
0x18000e0a4  nop     dword ptr [rax+rax+00h]
0x18000e0a9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000e0b0  test    rax, rax
0x18000e0b3  jz      short loc_18000E0BD
0x18000e0b5  mov     rcx, rbx
0x18000e0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bd  add     rsp, 20h
0x18000e0c1  pop     rbx
0x18000e0c2  retn
```
