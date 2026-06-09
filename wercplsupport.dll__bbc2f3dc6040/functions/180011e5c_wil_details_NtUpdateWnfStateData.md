# wil_details_NtUpdateWnfStateData

- ea: `0x180011e5c`
- end: `0x180011f06`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d28c`
- `0x180011c1c`

## callees

- `0x180011e5c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011eaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011eaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011e93`

## string_xrefs

- `0x180011e8c`: `ntdll.dll`
- `0x180011ea0`: `NtUpdateWnfStateData`

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
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180011e5c  mov     [rsp+arg_0], rbx
0x180011e61  mov     [rsp+arg_8], rsi
0x180011e66  push    rdi
0x180011e67  sub     rsp, 40h
0x180011e6b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180011e72  mov     ebx, r8d
0x180011e75  mov     rdi, rdx
0x180011e78  mov     rsi, rcx
0x180011e7b  test    r10, r10
0x180011e7e  jnz     short loc_180011EC6
0x180011e80  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011e87  test    rax, rax
0x180011e8a  jnz     short loc_180011EA0
0x180011e8c  lea     rcx, ModuleName; "ntdll.dll"
0x180011e93  call    cs:__imp_GetModuleHandleW
0x180011e99  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011ea0  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180011ea7  mov     rcx, rax; hModule
0x180011eaa  call    cs:__imp_GetProcAddress
0x180011eb0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180011eb7  mov     r10, rax
0x180011eba  test    rax, rax
0x180011ebd  jnz     short loc_180011EC6
0x180011ebf  mov     eax, 0C0000139h
0x180011ec4  jmp     short loc_180011EF6
0x180011ec6  mov     eax, [rsp+48h+arg_30]
0x180011ecd  xor     r9d, r9d
0x180011ed0  mov     [rsp+48h+var_18], eax
0x180011ed4  mov     r8d, ebx
0x180011ed7  mov     eax, [rsp+48h+arg_28]
0x180011edb  mov     rdx, rdi
0x180011ede  mov     [rsp+48h+var_20], eax
0x180011ee2  mov     rcx, rsi
0x180011ee5  mov     rax, r10
0x180011ee8  mov     [rsp+48h+var_28], 0
0x180011ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef6  mov     rbx, [rsp+48h+arg_0]
0x180011efb  mov     rsi, [rsp+48h+arg_8]
0x180011f00  add     rsp, 40h
0x180011f04  pop     rdi
0x180011f05  retn
```
