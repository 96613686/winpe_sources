# wil_details_NtUpdateWnfStateData

- ea: `0x18000e104`
- end: `0x18000e1b8`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c00c`
- `0x18000dda0`

## callees

- `0x18000e104`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e158`
- `KERNEL32!GetProcAddress` at `0x18000e158`
- `KERNEL32!GetModuleHandleW` at `0x18000e13b`
- `KERNEL32!GetModuleHandleW` at `0x18000e13b`

## string_xrefs

- `0x18000e134`: `ntdll.dll`
- `0x18000e14e`: `NtUpdateWnfStateData`

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
0x18000e104  mov     [rsp+arg_0], rbx
0x18000e109  mov     [rsp+arg_8], rsi
0x18000e10e  push    rdi
0x18000e10f  sub     rsp, 40h
0x18000e113  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e11a  mov     ebx, r8d
0x18000e11d  mov     rdi, rdx
0x18000e120  mov     rsi, rcx
0x18000e123  test    r10, r10
0x18000e126  jnz     short loc_18000E17A
0x18000e128  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e12f  test    rax, rax
0x18000e132  jnz     short loc_18000E14E
0x18000e134  lea     rcx, ModuleName; "ntdll.dll"
0x18000e13b  call    cs:__imp_GetModuleHandleW
0x18000e142  nop     dword ptr [rax+rax+00h]
0x18000e147  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e14e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e155  mov     rcx, rax; hModule
0x18000e158  call    cs:__imp_GetProcAddress
0x18000e15f  nop     dword ptr [rax+rax+00h]
0x18000e164  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e16b  mov     r10, rax
0x18000e16e  test    rax, rax
0x18000e171  jnz     short loc_18000E17A
0x18000e173  mov     eax, 0C0000139h
0x18000e178  jmp     short loc_18000E1A7
0x18000e17a  mov     eax, [rsp+48h+arg_30]
0x18000e181  xor     r9d, r9d
0x18000e184  mov     [rsp+48h+var_18], eax
0x18000e188  mov     r8d, ebx
0x18000e18b  mov     eax, [rsp+48h+arg_28]
0x18000e18f  mov     rdx, rdi
0x18000e192  mov     [rsp+48h+var_20], eax
0x18000e196  mov     rcx, rsi
0x18000e199  and     [rsp+48h+var_28], 0
0x18000e19f  mov     rax, r10
0x18000e1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a7  mov     rbx, [rsp+48h+arg_0]
0x18000e1ac  mov     rsi, [rsp+48h+arg_8]
0x18000e1b1  add     rsp, 40h
0x18000e1b5  pop     rdi
0x18000e1b6  retn
```
