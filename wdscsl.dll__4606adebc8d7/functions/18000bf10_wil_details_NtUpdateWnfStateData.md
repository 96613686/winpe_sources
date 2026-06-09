# wil_details_NtUpdateWnfStateData

- ea: `0x18000bf10`
- end: `0x18000bfc4`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800091fc`
- `0x18000bb68`

## callees

- `0x18000bf10`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000bf64`
- `KERNEL32!GetProcAddress` at `0x18000bf64`
- `KERNEL32!GetModuleHandleW` at `0x18000bf47`
- `KERNEL32!GetModuleHandleW` at `0x18000bf47`

## string_xrefs

- `0x18000bf40`: `ntdll.dll`
- `0x18000bf5a`: `NtUpdateWnfStateData`

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
0x18000bf10  mov     [rsp+arg_0], rbx
0x18000bf15  mov     [rsp+arg_8], rsi
0x18000bf1a  push    rdi
0x18000bf1b  sub     rsp, 40h
0x18000bf1f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bf26  mov     ebx, r8d
0x18000bf29  mov     rdi, rdx
0x18000bf2c  mov     rsi, rcx
0x18000bf2f  test    r10, r10
0x18000bf32  jnz     short loc_18000BF86
0x18000bf34  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf3b  test    rax, rax
0x18000bf3e  jnz     short loc_18000BF5A
0x18000bf40  lea     rcx, ModuleName; "ntdll.dll"
0x18000bf47  call    cs:__imp_GetModuleHandleW
0x18000bf4e  nop     dword ptr [rax+rax+00h]
0x18000bf53  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bf5a  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bf61  mov     rcx, rax; hModule
0x18000bf64  call    cs:__imp_GetProcAddress
0x18000bf6b  nop     dword ptr [rax+rax+00h]
0x18000bf70  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bf77  mov     r10, rax
0x18000bf7a  test    rax, rax
0x18000bf7d  jnz     short loc_18000BF86
0x18000bf7f  mov     eax, 0C0000139h
0x18000bf84  jmp     short loc_18000BFB3
0x18000bf86  mov     eax, [rsp+48h+arg_30]
0x18000bf8d  xor     r9d, r9d
0x18000bf90  mov     [rsp+48h+var_18], eax
0x18000bf94  mov     r8d, ebx
0x18000bf97  mov     eax, [rsp+48h+arg_28]
0x18000bf9b  mov     rdx, rdi
0x18000bf9e  mov     [rsp+48h+var_20], eax
0x18000bfa2  mov     rcx, rsi
0x18000bfa5  and     [rsp+48h+var_28], 0
0x18000bfab  mov     rax, r10
0x18000bfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb3  mov     rbx, [rsp+48h+arg_0]
0x18000bfb8  mov     rsi, [rsp+48h+arg_8]
0x18000bfbd  add     rsp, 40h
0x18000bfc1  pop     rdi
0x18000bfc2  retn
```
