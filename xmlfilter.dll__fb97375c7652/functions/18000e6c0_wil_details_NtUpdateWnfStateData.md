# wil_details_NtUpdateWnfStateData

- ea: `0x18000e6c0`
- end: `0x18000e76a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a97c`
- `0x18000df18`

## callees

- `0x18000e6c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e6f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e6f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e70e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e70e`

## string_xrefs

- `0x18000e6f0`: `ntdll.dll`
- `0x18000e704`: `NtUpdateWnfStateData`

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
0x18000e6c0  mov     [rsp+arg_0], rbx
0x18000e6c5  mov     [rsp+arg_8], rsi
0x18000e6ca  push    rdi
0x18000e6cb  sub     rsp, 40h
0x18000e6cf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e6d6  mov     ebx, r8d
0x18000e6d9  mov     rdi, rdx
0x18000e6dc  mov     rsi, rcx
0x18000e6df  test    r10, r10
0x18000e6e2  jnz     short loc_18000E72A
0x18000e6e4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e6eb  test    rax, rax
0x18000e6ee  jnz     short loc_18000E704
0x18000e6f0  lea     rcx, ModuleName; "ntdll.dll"
0x18000e6f7  call    cs:__imp_GetModuleHandleW
0x18000e6fd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e704  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e70b  mov     rcx, rax; hModule
0x18000e70e  call    cs:__imp_GetProcAddress
0x18000e714  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e71b  mov     r10, rax
0x18000e71e  test    rax, rax
0x18000e721  jnz     short loc_18000E72A
0x18000e723  mov     eax, 0C0000139h
0x18000e728  jmp     short loc_18000E75A
0x18000e72a  mov     eax, [rsp+48h+arg_30]
0x18000e731  xor     r9d, r9d
0x18000e734  mov     [rsp+48h+var_18], eax
0x18000e738  mov     r8d, ebx
0x18000e73b  mov     eax, [rsp+48h+arg_28]
0x18000e73f  mov     rdx, rdi
0x18000e742  mov     [rsp+48h+var_20], eax
0x18000e746  mov     rcx, rsi
0x18000e749  mov     rax, r10
0x18000e74c  mov     [rsp+48h+var_28], 0
0x18000e755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e75a  mov     rbx, [rsp+48h+arg_0]
0x18000e75f  mov     rsi, [rsp+48h+arg_8]
0x18000e764  add     rsp, 40h
0x18000e768  pop     rdi
0x18000e769  retn
```
