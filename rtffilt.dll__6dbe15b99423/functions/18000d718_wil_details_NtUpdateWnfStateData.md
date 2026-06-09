# wil_details_NtUpdateWnfStateData

- ea: `0x18000d718`
- end: `0x18000d7c2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008e2c`
- `0x18000cb98`

## callees

- `0x18000d718`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d74f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d766`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d766`

## string_xrefs

- `0x18000d748`: `ntdll.dll`
- `0x18000d75c`: `NtUpdateWnfStateData`

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
0x18000d718  mov     [rsp+arg_0], rbx
0x18000d71d  mov     [rsp+arg_8], rsi
0x18000d722  push    rdi
0x18000d723  sub     rsp, 40h
0x18000d727  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d72e  mov     ebx, r8d
0x18000d731  mov     rdi, rdx
0x18000d734  mov     rsi, rcx
0x18000d737  test    r10, r10
0x18000d73a  jnz     short loc_18000D782
0x18000d73c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d743  test    rax, rax
0x18000d746  jnz     short loc_18000D75C
0x18000d748  lea     rcx, ModuleName; "ntdll.dll"
0x18000d74f  call    cs:__imp_GetModuleHandleW
0x18000d755  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d75c  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d763  mov     rcx, rax; hModule
0x18000d766  call    cs:__imp_GetProcAddress
0x18000d76c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d773  mov     r10, rax
0x18000d776  test    rax, rax
0x18000d779  jnz     short loc_18000D782
0x18000d77b  mov     eax, 0C0000139h
0x18000d780  jmp     short loc_18000D7B2
0x18000d782  mov     eax, [rsp+48h+arg_30]
0x18000d789  xor     r9d, r9d
0x18000d78c  mov     [rsp+48h+var_18], eax
0x18000d790  mov     r8d, ebx
0x18000d793  mov     eax, [rsp+48h+arg_28]
0x18000d797  mov     rdx, rdi
0x18000d79a  mov     [rsp+48h+var_20], eax
0x18000d79e  mov     rcx, rsi
0x18000d7a1  mov     rax, r10
0x18000d7a4  mov     [rsp+48h+var_28], 0
0x18000d7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7b2  mov     rbx, [rsp+48h+arg_0]
0x18000d7b7  mov     rsi, [rsp+48h+arg_8]
0x18000d7bc  add     rsp, 40h
0x18000d7c0  pop     rdi
0x18000d7c1  retn
```
