# wil_details_NtQueryWnfStateData

- ea: `0x18000e05c`
- end: `0x18000e0fd`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c00c`
- `0x18000dda0`

## callees

- `0x18000e05c`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e0a8`
- `KERNEL32!GetProcAddress` at `0x18000e0a8`
- `KERNEL32!GetModuleHandleW` at `0x18000e08b`
- `KERNEL32!GetModuleHandleW` at `0x18000e08b`

## string_xrefs

- `0x18000e084`: `ntdll.dll`

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
0x18000e05c  mov     [rsp+arg_0], rbx
0x18000e061  push    rdi
0x18000e062  sub     rsp, 40h
0x18000e066  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000e06d  mov     rbx, r9
0x18000e070  mov     rdi, rcx
0x18000e073  test    r10, r10
0x18000e076  jnz     short loc_18000E0CA
0x18000e078  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e07f  test    rax, rax
0x18000e082  jnz     short loc_18000E09E
0x18000e084  lea     rcx, ModuleName; "ntdll.dll"
0x18000e08b  call    cs:__imp_GetModuleHandleW
0x18000e092  nop     dword ptr [rax+rax+00h]
0x18000e097  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e09e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000e0a5  mov     rcx, rax; hModule
0x18000e0a8  call    cs:__imp_GetProcAddress
0x18000e0af  nop     dword ptr [rax+rax+00h]
0x18000e0b4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000e0bb  mov     r10, rax
0x18000e0be  test    rax, rax
0x18000e0c1  jnz     short loc_18000E0CA
0x18000e0c3  mov     eax, 0C0000139h
0x18000e0c8  jmp     short loc_18000E0F1
0x18000e0ca  mov     rax, [rsp+48h+arg_28]
0x18000e0cf  mov     r9, rbx
0x18000e0d2  mov     [rsp+48h+var_20], rax
0x18000e0d7  xor     r8d, r8d
0x18000e0da  mov     rax, [rsp+48h+arg_20]
0x18000e0df  xor     edx, edx
0x18000e0e1  mov     [rsp+48h+var_28], rax
0x18000e0e6  mov     rcx, rdi
0x18000e0e9  mov     rax, r10
0x18000e0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f1  mov     rbx, [rsp+48h+arg_0]
0x18000e0f6  add     rsp, 40h
0x18000e0fa  pop     rdi
0x18000e0fb  retn
```
