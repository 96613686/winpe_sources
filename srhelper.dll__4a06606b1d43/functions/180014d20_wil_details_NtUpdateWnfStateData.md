# wil_details_NtUpdateWnfStateData

- ea: `0x180014d20`
- end: `0x180014dca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180013468`
- `0x180014ae0`

## callees

- `0x180014d20`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014d6e`
- `KERNEL32!GetProcAddress` at `0x180014d6e`
- `KERNEL32!GetModuleHandleW` at `0x180014d57`
- `KERNEL32!GetModuleHandleW` at `0x180014d57`

## string_xrefs

- `0x180014d50`: `ntdll.dll`
- `0x180014d64`: `NtUpdateWnfStateData`

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
0x180014d20  mov     [rsp+arg_0], rbx
0x180014d25  mov     [rsp+arg_8], rsi
0x180014d2a  push    rdi
0x180014d2b  sub     rsp, 40h
0x180014d2f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180014d36  mov     ebx, r8d
0x180014d39  mov     rdi, rdx
0x180014d3c  mov     rsi, rcx
0x180014d3f  test    r10, r10
0x180014d42  jnz     short loc_180014D8A
0x180014d44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014d4b  test    rax, rax
0x180014d4e  jnz     short loc_180014D64
0x180014d50  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180014d57  call    cs:__imp_GetModuleHandleW
0x180014d5d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014d64  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180014d6b  mov     rcx, rax; hModule
0x180014d6e  call    cs:__imp_GetProcAddress
0x180014d74  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180014d7b  mov     r10, rax
0x180014d7e  test    rax, rax
0x180014d81  jnz     short loc_180014D8A
0x180014d83  mov     eax, 0C0000139h
0x180014d88  jmp     short loc_180014DBA
0x180014d8a  mov     eax, [rsp+48h+arg_30]
0x180014d91  xor     r9d, r9d
0x180014d94  mov     [rsp+48h+var_18], eax
0x180014d98  mov     r8d, ebx
0x180014d9b  mov     eax, [rsp+48h+arg_28]
0x180014d9f  mov     rdx, rdi
0x180014da2  mov     [rsp+48h+var_20], eax
0x180014da6  mov     rcx, rsi
0x180014da9  mov     rax, r10
0x180014dac  mov     [rsp+48h+var_28], 0
0x180014db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dba  mov     rbx, [rsp+48h+arg_0]
0x180014dbf  mov     rsi, [rsp+48h+arg_8]
0x180014dc4  add     rsp, 40h
0x180014dc8  pop     rdi
0x180014dc9  retn
```
