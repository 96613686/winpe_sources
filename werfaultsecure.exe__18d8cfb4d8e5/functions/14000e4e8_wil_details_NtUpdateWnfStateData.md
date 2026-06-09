# wil_details_NtUpdateWnfStateData

- ea: `0x14000e4e8`
- end: `0x14000e592`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b804`
- `0x14000e2a8`

## callees

- `0x14000e4e8`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e536`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e536`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e51f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e51f`

## string_xrefs

- `0x14000e518`: `ntdll.dll`
- `0x14000e52c`: `NtUpdateWnfStateData`

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
0x14000e4e8  mov     [rsp+arg_0], rbx
0x14000e4ed  mov     [rsp+arg_8], rsi
0x14000e4f2  push    rdi
0x14000e4f3  sub     rsp, 40h
0x14000e4f7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000e4fe  mov     ebx, r8d
0x14000e501  mov     rdi, rdx
0x14000e504  mov     rsi, rcx
0x14000e507  test    r10, r10
0x14000e50a  jnz     short loc_14000E552
0x14000e50c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e513  test    rax, rax
0x14000e516  jnz     short loc_14000E52C
0x14000e518  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000e51f  call    cs:__imp_GetModuleHandleW
0x14000e525  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000e52c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000e533  mov     rcx, rax; hModule
0x14000e536  call    cs:__imp_GetProcAddress
0x14000e53c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000e543  mov     r10, rax
0x14000e546  test    rax, rax
0x14000e549  jnz     short loc_14000E552
0x14000e54b  mov     eax, 0C0000139h
0x14000e550  jmp     short loc_14000E582
0x14000e552  mov     eax, [rsp+48h+arg_30]
0x14000e559  xor     r9d, r9d
0x14000e55c  mov     [rsp+48h+var_18], eax
0x14000e560  mov     r8d, ebx
0x14000e563  mov     eax, [rsp+48h+arg_28]
0x14000e567  mov     rdx, rdi
0x14000e56a  mov     [rsp+48h+var_20], eax
0x14000e56e  mov     rcx, rsi
0x14000e571  mov     rax, r10
0x14000e574  mov     [rsp+48h+var_28], 0
0x14000e57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e582  mov     rbx, [rsp+48h+arg_0]
0x14000e587  mov     rsi, [rsp+48h+arg_8]
0x14000e58c  add     rsp, 40h
0x14000e590  pop     rdi
0x14000e591  retn
```
