# wil_details_NtQueryWnfStateData

- ea: `0x18000f83c`
- end: `0x18000f8dd`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c004`
- `0x18000eee8`

## callees

- `0x18000f83c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000f86b`
- `KERNEL32!GetModuleHandleW` at `0x18000f86b`
- `KERNEL32!GetProcAddress` at `0x18000f888`
- `KERNEL32!GetProcAddress` at `0x18000f888`

## string_xrefs

- `0x18000f864`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_NtQueryWnfStateData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64, __int64, __int64); // r10
  HMODULE ModuleHandleW; // rax

  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, __int64, __int64))g_wil_details_pfnNtQueryWnfStateData;
  if ( g_wil_details_pfnNtQueryWnfStateData )
    return v6(a1, 0, 0, a4, a5, a6);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000f83c  mov     [rsp+arg_0], rbx
0x18000f841  push    rdi
0x18000f842  sub     rsp, 40h
0x18000f846  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000f84d  mov     rbx, r9
0x18000f850  mov     rdi, rcx
0x18000f853  test    r10, r10
0x18000f856  jnz     short loc_18000F8AA
0x18000f858  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f85f  test    rax, rax
0x18000f862  jnz     short loc_18000F87E
0x18000f864  lea     rcx, ModuleName; "ntdll.dll"
0x18000f86b  call    cs:__imp_GetModuleHandleW
0x18000f872  nop     dword ptr [rax+rax+00h]
0x18000f877  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f87e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000f885  mov     rcx, rax; hModule
0x18000f888  call    cs:__imp_GetProcAddress
0x18000f88f  nop     dword ptr [rax+rax+00h]
0x18000f894  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000f89b  mov     r10, rax
0x18000f89e  test    rax, rax
0x18000f8a1  jnz     short loc_18000F8AA
0x18000f8a3  mov     eax, 0C0000139h
0x18000f8a8  jmp     short loc_18000F8D1
0x18000f8aa  mov     rax, [rsp+48h+arg_28]
0x18000f8af  mov     r9, rbx
0x18000f8b2  mov     [rsp+48h+var_20], rax
0x18000f8b7  xor     r8d, r8d
0x18000f8ba  mov     rax, [rsp+48h+arg_20]
0x18000f8bf  xor     edx, edx
0x18000f8c1  mov     [rsp+48h+var_28], rax
0x18000f8c6  mov     rcx, rdi
0x18000f8c9  mov     rax, r10
0x18000f8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d1  mov     rbx, [rsp+48h+arg_0]
0x18000f8d6  add     rsp, 40h
0x18000f8da  pop     rdi
0x18000f8db  retn
```
