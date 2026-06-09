# wil_details_NtUpdateWnfStateData

- ea: `0x18000bda8`
- end: `0x18000be52`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180009838`
- `0x18000bad8`

## callees

- `0x18000bda8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bdf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bdf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bddf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bddf`

## string_xrefs

- `0x18000bdd8`: `ntdll.dll`
- `0x18000bdec`: `NtUpdateWnfStateData`

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
0x18000bda8  mov     [rsp+arg_0], rbx
0x18000bdad  mov     [rsp+arg_8], rsi
0x18000bdb2  push    rdi
0x18000bdb3  sub     rsp, 40h
0x18000bdb7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bdbe  mov     ebx, r8d
0x18000bdc1  mov     rdi, rdx
0x18000bdc4  mov     rsi, rcx
0x18000bdc7  test    r10, r10
0x18000bdca  jnz     short loc_18000BE12
0x18000bdcc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bdd3  test    rax, rax
0x18000bdd6  jnz     short loc_18000BDEC
0x18000bdd8  lea     rcx, ModuleName; "ntdll.dll"
0x18000bddf  call    cs:__imp_GetModuleHandleW
0x18000bde5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bdec  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bdf3  mov     rcx, rax; hModule
0x18000bdf6  call    cs:__imp_GetProcAddress
0x18000bdfc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000be03  mov     r10, rax
0x18000be06  test    rax, rax
0x18000be09  jnz     short loc_18000BE12
0x18000be0b  mov     eax, 0C0000139h
0x18000be10  jmp     short loc_18000BE42
0x18000be12  mov     eax, [rsp+48h+arg_30]
0x18000be19  xor     r9d, r9d
0x18000be1c  mov     [rsp+48h+var_18], eax
0x18000be20  mov     r8d, ebx
0x18000be23  mov     eax, [rsp+48h+arg_28]
0x18000be27  mov     rdx, rdi
0x18000be2a  mov     [rsp+48h+var_20], eax
0x18000be2e  mov     rcx, rsi
0x18000be31  mov     rax, r10
0x18000be34  mov     [rsp+48h+var_28], 0
0x18000be3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be42  mov     rbx, [rsp+48h+arg_0]
0x18000be47  mov     rsi, [rsp+48h+arg_8]
0x18000be4c  add     rsp, 40h
0x18000be50  pop     rdi
0x18000be51  retn
```
