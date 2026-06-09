# wil_details_NtUpdateWnfStateData

- ea: `0x1800111e0`
- end: `0x180011294`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000dcdc`
- `0x180010d98`

## callees

- `0x1800111e0`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180011234`
- `KERNEL32!GetProcAddress` at `0x180011234`
- `KERNEL32!GetModuleHandleW` at `0x180011217`
- `KERNEL32!GetModuleHandleW` at `0x180011217`

## string_xrefs

- `0x180011210`: `ntdll.dll`
- `0x18001122a`: `NtUpdateWnfStateData`

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
0x1800111e0  mov     [rsp+arg_0], rbx
0x1800111e5  mov     [rsp+arg_8], rsi
0x1800111ea  push    rdi
0x1800111eb  sub     rsp, 40h
0x1800111ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800111f6  mov     ebx, r8d
0x1800111f9  mov     rdi, rdx
0x1800111fc  mov     rsi, rcx
0x1800111ff  test    r10, r10
0x180011202  jnz     short loc_180011256
0x180011204  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001120b  test    rax, rax
0x18001120e  jnz     short loc_18001122A
0x180011210  lea     rcx, ModuleName; "ntdll.dll"
0x180011217  call    cs:__imp_GetModuleHandleW
0x18001121e  nop     dword ptr [rax+rax+00h]
0x180011223  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001122a  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180011231  mov     rcx, rax; hModule
0x180011234  call    cs:__imp_GetProcAddress
0x18001123b  nop     dword ptr [rax+rax+00h]
0x180011240  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180011247  mov     r10, rax
0x18001124a  test    rax, rax
0x18001124d  jnz     short loc_180011256
0x18001124f  mov     eax, 0C0000139h
0x180011254  jmp     short loc_180011283
0x180011256  mov     eax, [rsp+48h+arg_30]
0x18001125d  xor     r9d, r9d
0x180011260  mov     [rsp+48h+var_18], eax
0x180011264  mov     r8d, ebx
0x180011267  mov     eax, [rsp+48h+arg_28]
0x18001126b  mov     rdx, rdi
0x18001126e  mov     [rsp+48h+var_20], eax
0x180011272  mov     rcx, rsi
0x180011275  and     [rsp+48h+var_28], 0
0x18001127b  mov     rax, r10
0x18001127e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011283  mov     rbx, [rsp+48h+arg_0]
0x180011288  mov     rsi, [rsp+48h+arg_8]
0x18001128d  add     rsp, 40h
0x180011291  pop     rdi
0x180011292  retn
```
