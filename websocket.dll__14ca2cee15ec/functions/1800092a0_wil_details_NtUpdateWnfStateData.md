# wil_details_NtUpdateWnfStateData

- ea: `0x1800092a0`
- end: `0x18000934a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800074e8`
- `0x180008e74`

## callees

- `0x1800092a0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800092d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800092ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800092ee`

## string_xrefs

- `0x1800092d0`: `ntdll.dll`
- `0x1800092e4`: `NtUpdateWnfStateData`

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
0x1800092a0  mov     [rsp+arg_0], rbx
0x1800092a5  mov     [rsp+arg_8], rsi
0x1800092aa  push    rdi
0x1800092ab  sub     rsp, 40h
0x1800092af  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800092b6  mov     ebx, r8d
0x1800092b9  mov     rdi, rdx
0x1800092bc  mov     rsi, rcx
0x1800092bf  test    r10, r10
0x1800092c2  jnz     short loc_18000930A
0x1800092c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800092cb  test    rax, rax
0x1800092ce  jnz     short loc_1800092E4
0x1800092d0  lea     rcx, ModuleName; "ntdll.dll"
0x1800092d7  call    cs:__imp_GetModuleHandleW
0x1800092dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800092e4  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800092eb  mov     rcx, rax; hModule
0x1800092ee  call    cs:__imp_GetProcAddress
0x1800092f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800092fb  mov     r10, rax
0x1800092fe  test    rax, rax
0x180009301  jnz     short loc_18000930A
0x180009303  mov     eax, 0C0000139h
0x180009308  jmp     short loc_18000933A
0x18000930a  mov     eax, [rsp+48h+arg_30]
0x180009311  xor     r9d, r9d
0x180009314  mov     [rsp+48h+var_18], eax
0x180009318  mov     r8d, ebx
0x18000931b  mov     eax, [rsp+48h+arg_28]
0x18000931f  mov     rdx, rdi
0x180009322  mov     [rsp+48h+var_20], eax
0x180009326  mov     rcx, rsi
0x180009329  mov     rax, r10
0x18000932c  mov     [rsp+48h+var_28], 0
0x180009335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000933a  mov     rbx, [rsp+48h+arg_0]
0x18000933f  mov     rsi, [rsp+48h+arg_8]
0x180009344  add     rsp, 40h
0x180009348  pop     rdi
0x180009349  retn
```
