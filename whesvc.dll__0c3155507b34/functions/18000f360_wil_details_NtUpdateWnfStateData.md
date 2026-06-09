# wil_details_NtUpdateWnfStateData

- ea: `0x18000f360`
- end: `0x18000f40a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000dedc`
- `0x18000ef2c`

## callees

- `0x18000f360`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f397`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f397`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f3ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f3ae`

## string_xrefs

- `0x18000f390`: `ntdll.dll`
- `0x18000f3a4`: `NtUpdateWnfStateData`

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
0x18000f360  mov     [rsp+arg_0], rbx
0x18000f365  mov     [rsp+arg_8], rsi
0x18000f36a  push    rdi
0x18000f36b  sub     rsp, 40h
0x18000f36f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f376  mov     ebx, r8d
0x18000f379  mov     rdi, rdx
0x18000f37c  mov     rsi, rcx
0x18000f37f  test    r10, r10
0x18000f382  jnz     short loc_18000F3CA
0x18000f384  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f38b  test    rax, rax
0x18000f38e  jnz     short loc_18000F3A4
0x18000f390  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000f397  call    cs:__imp_GetModuleHandleW
0x18000f39d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f3a4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f3ab  mov     rcx, rax; hModule
0x18000f3ae  call    cs:__imp_GetProcAddress
0x18000f3b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f3bb  mov     r10, rax
0x18000f3be  test    rax, rax
0x18000f3c1  jnz     short loc_18000F3CA
0x18000f3c3  mov     eax, 0C0000139h
0x18000f3c8  jmp     short loc_18000F3FA
0x18000f3ca  mov     eax, [rsp+48h+arg_30]
0x18000f3d1  xor     r9d, r9d
0x18000f3d4  mov     [rsp+48h+var_18], eax
0x18000f3d8  mov     r8d, ebx
0x18000f3db  mov     eax, [rsp+48h+arg_28]
0x18000f3df  mov     rdx, rdi
0x18000f3e2  mov     [rsp+48h+var_20], eax
0x18000f3e6  mov     rcx, rsi
0x18000f3e9  mov     rax, r10
0x18000f3ec  mov     [rsp+48h+var_28], 0
0x18000f3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fa  mov     rbx, [rsp+48h+arg_0]
0x18000f3ff  mov     rsi, [rsp+48h+arg_8]
0x18000f404  add     rsp, 40h
0x18000f408  pop     rdi
0x18000f409  retn
```
