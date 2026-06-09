# wil_details_NtQueryWnfStateData

- ea: `0x180011138`
- end: `0x1800111d9`
- name: `wil_details_NtQueryWnfStateData`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dcdc`
- `0x180010d98`

## callees

- `0x180011138`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180011184`
- `KERNEL32!GetProcAddress` at `0x180011184`
- `KERNEL32!GetModuleHandleW` at `0x180011167`
- `KERNEL32!GetModuleHandleW` at `0x180011167`

## string_xrefs

- `0x180011160`: `ntdll.dll`

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
0x180011138  mov     [rsp+arg_0], rbx
0x18001113d  push    rdi
0x18001113e  sub     rsp, 40h
0x180011142  mov     r10, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011149  mov     rbx, r9
0x18001114c  mov     rdi, rcx
0x18001114f  test    r10, r10
0x180011152  jnz     short loc_1800111A6
0x180011154  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001115b  test    rax, rax
0x18001115e  jnz     short loc_18001117A
0x180011160  lea     rcx, ModuleName; "ntdll.dll"
0x180011167  call    cs:__imp_GetModuleHandleW
0x18001116e  nop     dword ptr [rax+rax+00h]
0x180011173  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001117a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180011181  mov     rcx, rax; hModule
0x180011184  call    cs:__imp_GetProcAddress
0x18001118b  nop     dword ptr [rax+rax+00h]
0x180011190  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180011197  mov     r10, rax
0x18001119a  test    rax, rax
0x18001119d  jnz     short loc_1800111A6
0x18001119f  mov     eax, 0C0000139h
0x1800111a4  jmp     short loc_1800111CD
0x1800111a6  mov     rax, [rsp+48h+arg_28]
0x1800111ab  mov     r9, rbx
0x1800111ae  mov     [rsp+48h+var_20], rax
0x1800111b3  xor     r8d, r8d
0x1800111b6  mov     rax, [rsp+48h+arg_20]
0x1800111bb  xor     edx, edx
0x1800111bd  mov     [rsp+48h+var_28], rax
0x1800111c2  mov     rcx, rdi
0x1800111c5  mov     rax, r10
0x1800111c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111cd  mov     rbx, [rsp+48h+arg_0]
0x1800111d2  add     rsp, 40h
0x1800111d6  pop     rdi
0x1800111d7  retn
```
