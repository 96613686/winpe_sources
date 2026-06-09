# wil_details_NtUpdateWnfStateData

- ea: `0x180008990`
- end: `0x180008a3a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180006b5c`
- `0x180008558`

## callees

- `0x180008990`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800089c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089de`

## string_xrefs

- `0x1800089c0`: `ntdll.dll`
- `0x1800089d4`: `NtUpdateWnfStateData`

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
0x180008990  mov     [rsp+arg_0], rbx
0x180008995  mov     [rsp+arg_8], rsi
0x18000899a  push    rdi
0x18000899b  sub     rsp, 40h
0x18000899f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800089a6  mov     ebx, r8d
0x1800089a9  mov     rdi, rdx
0x1800089ac  mov     rsi, rcx
0x1800089af  test    r10, r10
0x1800089b2  jnz     short loc_1800089FA
0x1800089b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800089bb  test    rax, rax
0x1800089be  jnz     short loc_1800089D4
0x1800089c0  lea     rcx, ModuleName; "ntdll.dll"
0x1800089c7  call    cs:__imp_GetModuleHandleW
0x1800089cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800089d4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800089db  mov     rcx, rax; hModule
0x1800089de  call    cs:__imp_GetProcAddress
0x1800089e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800089eb  mov     r10, rax
0x1800089ee  test    rax, rax
0x1800089f1  jnz     short loc_1800089FA
0x1800089f3  mov     eax, 0C0000139h
0x1800089f8  jmp     short loc_180008A2A
0x1800089fa  mov     eax, [rsp+48h+arg_30]
0x180008a01  xor     r9d, r9d
0x180008a04  mov     [rsp+48h+var_18], eax
0x180008a08  mov     r8d, ebx
0x180008a0b  mov     eax, [rsp+48h+arg_28]
0x180008a0f  mov     rdx, rdi
0x180008a12  mov     [rsp+48h+var_20], eax
0x180008a16  mov     rcx, rsi
0x180008a19  mov     rax, r10
0x180008a1c  mov     [rsp+48h+var_28], 0
0x180008a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2a  mov     rbx, [rsp+48h+arg_0]
0x180008a2f  mov     rsi, [rsp+48h+arg_8]
0x180008a34  add     rsp, 40h
0x180008a38  pop     rdi
0x180008a39  retn
```
