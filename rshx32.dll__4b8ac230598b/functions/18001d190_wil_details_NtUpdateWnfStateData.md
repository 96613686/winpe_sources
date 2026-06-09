# wil_details_NtUpdateWnfStateData

- ea: `0x18001d190`
- end: `0x18001d23a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001bcbc`
- `0x18001cd64`

## callees

- `0x18001d190`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d1de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d1de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d1c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d1c7`

## string_xrefs

- `0x18001d1c0`: `ntdll.dll`
- `0x18001d1d4`: `NtUpdateWnfStateData`

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
0x18001d190  mov     [rsp+arg_0], rbx
0x18001d195  mov     [rsp+arg_8], rsi
0x18001d19a  push    rdi
0x18001d19b  sub     rsp, 40h
0x18001d19f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001d1a6  mov     ebx, r8d
0x18001d1a9  mov     rdi, rdx
0x18001d1ac  mov     rsi, rcx
0x18001d1af  test    r10, r10
0x18001d1b2  jnz     short loc_18001D1FA
0x18001d1b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d1bb  test    rax, rax
0x18001d1be  jnz     short loc_18001D1D4
0x18001d1c0  lea     rcx, ModuleName; "ntdll.dll"
0x18001d1c7  call    cs:__imp_GetModuleHandleW
0x18001d1cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001d1d4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001d1db  mov     rcx, rax; hModule
0x18001d1de  call    cs:__imp_GetProcAddress
0x18001d1e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001d1eb  mov     r10, rax
0x18001d1ee  test    rax, rax
0x18001d1f1  jnz     short loc_18001D1FA
0x18001d1f3  mov     eax, 0C0000139h
0x18001d1f8  jmp     short loc_18001D22A
0x18001d1fa  mov     eax, [rsp+48h+arg_30]
0x18001d201  xor     r9d, r9d
0x18001d204  mov     [rsp+48h+var_18], eax
0x18001d208  mov     r8d, ebx
0x18001d20b  mov     eax, [rsp+48h+arg_28]
0x18001d20f  mov     rdx, rdi
0x18001d212  mov     [rsp+48h+var_20], eax
0x18001d216  mov     rcx, rsi
0x18001d219  mov     rax, r10
0x18001d21c  mov     [rsp+48h+var_28], 0
0x18001d225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d22a  mov     rbx, [rsp+48h+arg_0]
0x18001d22f  mov     rsi, [rsp+48h+arg_8]
0x18001d234  add     rsp, 40h
0x18001d238  pop     rdi
0x18001d239  retn
```
