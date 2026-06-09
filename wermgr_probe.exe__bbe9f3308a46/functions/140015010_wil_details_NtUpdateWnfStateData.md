# wil_details_NtUpdateWnfStateData

- ea: `0x140015010`
- end: `0x1400150ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140012d44`
- `0x140014b48`

## callees

- `0x140015010`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001505e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001505e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015047`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015047`

## string_xrefs

- `0x140015040`: `ntdll.dll`
- `0x140015054`: `NtUpdateWnfStateData`

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
0x140015010  mov     [rsp+arg_0], rbx
0x140015015  mov     [rsp+arg_8], rsi
0x14001501a  push    rdi
0x14001501b  sub     rsp, 40h
0x14001501f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140015026  mov     ebx, r8d
0x140015029  mov     rdi, rdx
0x14001502c  mov     rsi, rcx
0x14001502f  test    r10, r10
0x140015032  jnz     short loc_14001507A
0x140015034  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001503b  test    rax, rax
0x14001503e  jnz     short loc_140015054
0x140015040  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140015047  call    cs:__imp_GetModuleHandleW
0x14001504d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140015054  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14001505b  mov     rcx, rax; hModule
0x14001505e  call    cs:__imp_GetProcAddress
0x140015064  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14001506b  mov     r10, rax
0x14001506e  test    rax, rax
0x140015071  jnz     short loc_14001507A
0x140015073  mov     eax, 0C0000139h
0x140015078  jmp     short loc_1400150AA
0x14001507a  mov     eax, [rsp+48h+arg_30]
0x140015081  xor     r9d, r9d
0x140015084  mov     [rsp+48h+var_18], eax
0x140015088  mov     r8d, ebx
0x14001508b  mov     eax, [rsp+48h+arg_28]
0x14001508f  mov     rdx, rdi
0x140015092  mov     [rsp+48h+var_20], eax
0x140015096  mov     rcx, rsi
0x140015099  mov     rax, r10
0x14001509c  mov     [rsp+48h+var_28], 0
0x1400150a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150aa  mov     rbx, [rsp+48h+arg_0]
0x1400150af  mov     rsi, [rsp+48h+arg_8]
0x1400150b4  add     rsp, 40h
0x1400150b8  pop     rdi
0x1400150b9  retn
```
