# wil_details_NtUpdateWnfStateData

- ea: `0x180039f10`
- end: `0x180039fba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18003778c`
- `0x180039a48`

## callees

- `0x180039f10`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039f5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039f5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039f47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039f47`

## string_xrefs

- `0x180039f40`: `ntdll.dll`
- `0x180039f54`: `NtUpdateWnfStateData`

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
0x180039f10  mov     [rsp+arg_0], rbx
0x180039f15  mov     [rsp+arg_8], rsi
0x180039f1a  push    rdi
0x180039f1b  sub     rsp, 40h
0x180039f1f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180039f26  mov     ebx, r8d
0x180039f29  mov     rdi, rdx
0x180039f2c  mov     rsi, rcx
0x180039f2f  test    r10, r10
0x180039f32  jnz     short loc_180039F7A
0x180039f34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039f3b  test    rax, rax
0x180039f3e  jnz     short loc_180039F54
0x180039f40  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180039f47  call    cs:__imp_GetModuleHandleW
0x180039f4d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180039f54  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180039f5b  mov     rcx, rax; hModule
0x180039f5e  call    cs:__imp_GetProcAddress
0x180039f64  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180039f6b  mov     r10, rax
0x180039f6e  test    rax, rax
0x180039f71  jnz     short loc_180039F7A
0x180039f73  mov     eax, 0C0000139h
0x180039f78  jmp     short loc_180039FAA
0x180039f7a  mov     eax, [rsp+48h+arg_30]
0x180039f81  xor     r9d, r9d
0x180039f84  mov     [rsp+48h+var_18], eax
0x180039f88  mov     r8d, ebx
0x180039f8b  mov     eax, [rsp+48h+arg_28]
0x180039f8f  mov     rdx, rdi
0x180039f92  mov     [rsp+48h+var_20], eax
0x180039f96  mov     rcx, rsi
0x180039f99  mov     rax, r10
0x180039f9c  mov     [rsp+48h+var_28], 0
0x180039fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039faa  mov     rbx, [rsp+48h+arg_0]
0x180039faf  mov     rsi, [rsp+48h+arg_8]
0x180039fb4  add     rsp, 40h
0x180039fb8  pop     rdi
0x180039fb9  retn
```
