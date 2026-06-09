# wil_details_NtUpdateWnfStateData

- ea: `0x1800117f4`
- end: `0x18001189e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e75c`
- `0x18001005c`

## callees

- `0x1800117f4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180011842`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180011842`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001182b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001182b`

## string_xrefs

- `0x180011824`: `ntdll.dll`
- `0x180011838`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10
  HMODULE ModuleHandleW; // rax

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x1800117f4  mov     [rsp+arg_0], rbx
0x1800117f9  mov     [rsp+arg_8], rsi
0x1800117fe  push    rdi
0x1800117ff  sub     rsp, 40h
0x180011803  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001180a  mov     ebx, r8d
0x18001180d  mov     rdi, rdx
0x180011810  mov     rsi, rcx
0x180011813  test    r10, r10
0x180011816  jnz     short loc_18001185E
0x180011818  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001181f  test    rax, rax
0x180011822  jnz     short loc_180011838
0x180011824  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001182b  call    cs:__imp_GetModuleHandleW
0x180011831  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011838  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001183f  mov     rcx, rax; hModule
0x180011842  call    cs:__imp_GetProcAddress
0x180011848  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001184f  mov     r10, rax
0x180011852  test    rax, rax
0x180011855  jnz     short loc_18001185E
0x180011857  mov     eax, 0C0000139h
0x18001185c  jmp     short loc_18001188E
0x18001185e  mov     eax, [rsp+48h+arg_30]
0x180011865  xor     r9d, r9d
0x180011868  mov     [rsp+48h+var_18], eax
0x18001186c  mov     r8d, ebx
0x18001186f  mov     eax, [rsp+48h+arg_28]
0x180011873  mov     rdx, rdi
0x180011876  mov     [rsp+48h+var_20], eax
0x18001187a  mov     rcx, rsi
0x18001187d  mov     rax, r10
0x180011880  mov     [rsp+48h+var_28], 0
0x180011889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188e  mov     rbx, [rsp+48h+arg_0]
0x180011893  mov     rsi, [rsp+48h+arg_8]
0x180011898  add     rsp, 40h
0x18001189c  pop     rdi
0x18001189d  retn
```
