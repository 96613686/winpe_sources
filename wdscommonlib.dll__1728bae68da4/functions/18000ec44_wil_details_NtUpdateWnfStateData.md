# wil_details_NtUpdateWnfStateData

- ea: `0x18000ec44`
- end: `0x18000ecf8`
- name: `wil_details_NtUpdateWnfStateData`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cb4c`
- `0x18000e8e0`

## callees

- `0x18000ec44`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ec98`
- `KERNEL32!GetProcAddress` at `0x18000ec98`
- `KERNEL32!GetModuleHandleW` at `0x18000ec7b`
- `KERNEL32!GetModuleHandleW` at `0x18000ec7b`

## string_xrefs

- `0x18000ec74`: `ntdll.dll`
- `0x18000ec8e`: `NtUpdateWnfStateData`

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
0x18000ec44  mov     [rsp+arg_0], rbx
0x18000ec49  mov     [rsp+arg_8], rsi
0x18000ec4e  push    rdi
0x18000ec4f  sub     rsp, 40h
0x18000ec53  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000ec5a  mov     ebx, r8d
0x18000ec5d  mov     rdi, rdx
0x18000ec60  mov     rsi, rcx
0x18000ec63  test    r10, r10
0x18000ec66  jnz     short loc_18000ECBA
0x18000ec68  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ec6f  test    rax, rax
0x18000ec72  jnz     short loc_18000EC8E
0x18000ec74  lea     rcx, ModuleName; "ntdll.dll"
0x18000ec7b  call    cs:__imp_GetModuleHandleW
0x18000ec82  nop     dword ptr [rax+rax+00h]
0x18000ec87  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ec8e  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ec95  mov     rcx, rax; hModule
0x18000ec98  call    cs:__imp_GetProcAddress
0x18000ec9f  nop     dword ptr [rax+rax+00h]
0x18000eca4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ecab  mov     r10, rax
0x18000ecae  test    rax, rax
0x18000ecb1  jnz     short loc_18000ECBA
0x18000ecb3  mov     eax, 0C0000139h
0x18000ecb8  jmp     short loc_18000ECE7
0x18000ecba  mov     eax, [rsp+48h+arg_30]
0x18000ecc1  xor     r9d, r9d
0x18000ecc4  mov     [rsp+48h+var_18], eax
0x18000ecc8  mov     r8d, ebx
0x18000eccb  mov     eax, [rsp+48h+arg_28]
0x18000eccf  mov     rdx, rdi
0x18000ecd2  mov     [rsp+48h+var_20], eax
0x18000ecd6  mov     rcx, rsi
0x18000ecd9  and     [rsp+48h+var_28], 0
0x18000ecdf  mov     rax, r10
0x18000ece2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece7  mov     rbx, [rsp+48h+arg_0]
0x18000ecec  mov     rsi, [rsp+48h+arg_8]
0x18000ecf1  add     rsp, 40h
0x18000ecf5  pop     rdi
0x18000ecf6  retn
```
