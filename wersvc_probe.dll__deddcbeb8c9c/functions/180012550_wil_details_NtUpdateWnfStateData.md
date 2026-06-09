# wil_details_NtUpdateWnfStateData

- ea: `0x180012550`
- end: `0x1800125fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000beac`
- `0x180011cb8`

## callees

- `0x180012550`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012587`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012587`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001259e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001259e`

## string_xrefs

- `0x180012580`: `ntdll.dll`
- `0x180012594`: `NtUpdateWnfStateData`

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
0x180012550  mov     [rsp+arg_0], rbx
0x180012555  mov     [rsp+arg_8], rsi
0x18001255a  push    rdi
0x18001255b  sub     rsp, 40h
0x18001255f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012566  mov     ebx, r8d
0x180012569  mov     rdi, rdx
0x18001256c  mov     rsi, rcx
0x18001256f  test    r10, r10
0x180012572  jnz     short loc_1800125BA
0x180012574  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001257b  test    rax, rax
0x18001257e  jnz     short loc_180012594
0x180012580  lea     rcx, Src; "ntdll.dll"
0x180012587  call    cs:__imp_GetModuleHandleW
0x18001258d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012594  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001259b  mov     rcx, rax; hModule
0x18001259e  call    cs:__imp_GetProcAddress
0x1800125a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800125ab  mov     r10, rax
0x1800125ae  test    rax, rax
0x1800125b1  jnz     short loc_1800125BA
0x1800125b3  mov     eax, 0C0000139h
0x1800125b8  jmp     short loc_1800125EA
0x1800125ba  mov     eax, [rsp+48h+arg_30]
0x1800125c1  xor     r9d, r9d
0x1800125c4  mov     [rsp+48h+var_18], eax
0x1800125c8  mov     r8d, ebx
0x1800125cb  mov     eax, [rsp+48h+arg_28]
0x1800125cf  mov     rdx, rdi
0x1800125d2  mov     [rsp+48h+var_20], eax
0x1800125d6  mov     rcx, rsi
0x1800125d9  mov     rax, r10
0x1800125dc  mov     [rsp+48h+var_28], 0
0x1800125e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ea  mov     rbx, [rsp+48h+arg_0]
0x1800125ef  mov     rsi, [rsp+48h+arg_8]
0x1800125f4  add     rsp, 40h
0x1800125f8  pop     rdi
0x1800125f9  retn
```
