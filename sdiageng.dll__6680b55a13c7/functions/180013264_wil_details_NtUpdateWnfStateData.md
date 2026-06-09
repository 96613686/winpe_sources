# wil_details_NtUpdateWnfStateData

- ea: `0x180013264`
- end: `0x18001330e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f534`
- `0x180012e90`

## callees

- `0x180013264`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001329b`
- `KERNEL32!GetModuleHandleW` at `0x18001329b`
- `KERNEL32!GetProcAddress` at `0x1800132b2`
- `KERNEL32!GetProcAddress` at `0x1800132b2`

## string_xrefs

- `0x180013294`: `ntdll.dll`
- `0x1800132a8`: `NtUpdateWnfStateData`

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
0x180013264  mov     [rsp+arg_0], rbx
0x180013269  mov     [rsp+arg_8], rsi
0x18001326e  push    rdi
0x18001326f  sub     rsp, 40h
0x180013273  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001327a  mov     ebx, r8d
0x18001327d  mov     rdi, rdx
0x180013280  mov     rsi, rcx
0x180013283  test    r10, r10
0x180013286  jnz     short loc_1800132CE
0x180013288  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001328f  test    rax, rax
0x180013292  jnz     short loc_1800132A8
0x180013294  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001329b  call    cs:__imp_GetModuleHandleW
0x1800132a1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800132a8  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800132af  mov     rcx, rax; hModule
0x1800132b2  call    cs:__imp_GetProcAddress
0x1800132b8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800132bf  mov     r10, rax
0x1800132c2  test    rax, rax
0x1800132c5  jnz     short loc_1800132CE
0x1800132c7  mov     eax, 0C0000139h
0x1800132cc  jmp     short loc_1800132FE
0x1800132ce  mov     eax, [rsp+48h+arg_30]
0x1800132d5  xor     r9d, r9d
0x1800132d8  mov     [rsp+48h+var_18], eax
0x1800132dc  mov     r8d, ebx
0x1800132df  mov     eax, [rsp+48h+arg_28]
0x1800132e3  mov     rdx, rdi
0x1800132e6  mov     [rsp+48h+var_20], eax
0x1800132ea  mov     rcx, rsi
0x1800132ed  mov     rax, r10
0x1800132f0  mov     [rsp+48h+var_28], 0
0x1800132f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fe  mov     rbx, [rsp+48h+arg_0]
0x180013303  mov     rsi, [rsp+48h+arg_8]
0x180013308  add     rsp, 40h
0x18001330c  pop     rdi
0x18001330d  retn
```
