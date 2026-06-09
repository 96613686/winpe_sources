# wil_details_NtUpdateWnfStateData

- ea: `0x18000f8e4`
- end: `0x18000f998`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c004`
- `0x18000eee8`

## callees

- `0x18000f8e4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000f91b`
- `KERNEL32!GetModuleHandleW` at `0x18000f91b`
- `KERNEL32!GetProcAddress` at `0x18000f938`
- `KERNEL32!GetProcAddress` at `0x18000f938`

## string_xrefs

- `0x18000f914`: `ntdll.dll`
- `0x18000f92e`: `NtUpdateWnfStateData`

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
0x18000f8e4  mov     [rsp+arg_0], rbx
0x18000f8e9  mov     [rsp+arg_8], rsi
0x18000f8ee  push    rdi
0x18000f8ef  sub     rsp, 40h
0x18000f8f3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f8fa  mov     ebx, r8d
0x18000f8fd  mov     rdi, rdx
0x18000f900  mov     rsi, rcx
0x18000f903  test    r10, r10
0x18000f906  jnz     short loc_18000F95A
0x18000f908  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f90f  test    rax, rax
0x18000f912  jnz     short loc_18000F92E
0x18000f914  lea     rcx, ModuleName; "ntdll.dll"
0x18000f91b  call    cs:__imp_GetModuleHandleW
0x18000f922  nop     dword ptr [rax+rax+00h]
0x18000f927  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f92e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f935  mov     rcx, rax; hModule
0x18000f938  call    cs:__imp_GetProcAddress
0x18000f93f  nop     dword ptr [rax+rax+00h]
0x18000f944  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f94b  mov     r10, rax
0x18000f94e  test    rax, rax
0x18000f951  jnz     short loc_18000F95A
0x18000f953  mov     eax, 0C0000139h
0x18000f958  jmp     short loc_18000F987
0x18000f95a  mov     eax, [rsp+48h+arg_30]
0x18000f961  xor     r9d, r9d
0x18000f964  mov     [rsp+48h+var_18], eax
0x18000f968  mov     r8d, ebx
0x18000f96b  mov     eax, [rsp+48h+arg_28]
0x18000f96f  mov     rdx, rdi
0x18000f972  mov     [rsp+48h+var_20], eax
0x18000f976  mov     rcx, rsi
0x18000f979  and     [rsp+48h+var_28], 0
0x18000f97f  mov     rax, r10
0x18000f982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f987  mov     rbx, [rsp+48h+arg_0]
0x18000f98c  mov     rsi, [rsp+48h+arg_8]
0x18000f991  add     rsp, 40h
0x18000f995  pop     rdi
0x18000f996  retn
```
