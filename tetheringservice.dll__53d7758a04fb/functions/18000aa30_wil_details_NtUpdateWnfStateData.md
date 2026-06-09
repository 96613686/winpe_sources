# wil_details_NtUpdateWnfStateData

- ea: `0x18000aa30`
- end: `0x18000aada`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180008108`
- `0x18000a568`

## callees

- `0x18000aa30`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aa7e`

## string_xrefs

- `0x18000aa60`: `ntdll.dll`
- `0x18000aa74`: `NtUpdateWnfStateData`

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
0x18000aa30  mov     [rsp+arg_0], rbx
0x18000aa35  mov     [rsp+arg_8], rsi
0x18000aa3a  push    rdi
0x18000aa3b  sub     rsp, 40h
0x18000aa3f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000aa46  mov     ebx, r8d
0x18000aa49  mov     rdi, rdx
0x18000aa4c  mov     rsi, rcx
0x18000aa4f  test    r10, r10
0x18000aa52  jnz     short loc_18000AA9A
0x18000aa54  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa5b  test    rax, rax
0x18000aa5e  jnz     short loc_18000AA74
0x18000aa60  lea     rcx, ModuleName; "ntdll.dll"
0x18000aa67  call    cs:__imp_GetModuleHandleW
0x18000aa6d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aa74  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000aa7b  mov     rcx, rax; hModule
0x18000aa7e  call    cs:__imp_GetProcAddress
0x18000aa84  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000aa8b  mov     r10, rax
0x18000aa8e  test    rax, rax
0x18000aa91  jnz     short loc_18000AA9A
0x18000aa93  mov     eax, 0C0000139h
0x18000aa98  jmp     short loc_18000AACA
0x18000aa9a  mov     eax, [rsp+48h+arg_30]
0x18000aaa1  xor     r9d, r9d
0x18000aaa4  mov     [rsp+48h+var_18], eax
0x18000aaa8  mov     r8d, ebx
0x18000aaab  mov     eax, [rsp+48h+arg_28]
0x18000aaaf  mov     rdx, rdi
0x18000aab2  mov     [rsp+48h+var_20], eax
0x18000aab6  mov     rcx, rsi
0x18000aab9  mov     rax, r10
0x18000aabc  mov     [rsp+48h+var_28], 0
0x18000aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaca  mov     rbx, [rsp+48h+arg_0]
0x18000aacf  mov     rsi, [rsp+48h+arg_8]
0x18000aad4  add     rsp, 40h
0x18000aad8  pop     rdi
0x18000aad9  retn
```
