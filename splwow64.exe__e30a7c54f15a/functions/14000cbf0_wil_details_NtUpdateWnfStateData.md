# wil_details_NtUpdateWnfStateData

- ea: `0x14000cbf0`
- end: `0x14000cc9a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b058`
- `0x14000c42c`

## callees

- `0x14000cbf0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000cc3e`
- `KERNEL32!GetProcAddress` at `0x14000cc3e`
- `KERNEL32!GetModuleHandleW` at `0x14000cc27`
- `KERNEL32!GetModuleHandleW` at `0x14000cc27`

## string_xrefs

- `0x14000cc20`: `ntdll.dll`
- `0x14000cc34`: `NtUpdateWnfStateData`

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
0x14000cbf0  mov     [rsp+arg_0], rbx
0x14000cbf5  mov     [rsp+arg_8], rsi
0x14000cbfa  push    rdi
0x14000cbfb  sub     rsp, 40h
0x14000cbff  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000cc06  mov     ebx, r8d
0x14000cc09  mov     rdi, rdx
0x14000cc0c  mov     rsi, rcx
0x14000cc0f  test    r10, r10
0x14000cc12  jnz     short loc_14000CC5A
0x14000cc14  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cc1b  test    rax, rax
0x14000cc1e  jnz     short loc_14000CC34
0x14000cc20  lea     rcx, ModuleName; "ntdll.dll"
0x14000cc27  call    cs:__imp_GetModuleHandleW
0x14000cc2d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cc34  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000cc3b  mov     rcx, rax; hModule
0x14000cc3e  call    cs:__imp_GetProcAddress
0x14000cc44  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000cc4b  mov     r10, rax
0x14000cc4e  test    rax, rax
0x14000cc51  jnz     short loc_14000CC5A
0x14000cc53  mov     eax, 0C0000139h
0x14000cc58  jmp     short loc_14000CC8A
0x14000cc5a  mov     eax, [rsp+48h+arg_30]
0x14000cc61  xor     r9d, r9d
0x14000cc64  mov     [rsp+48h+var_18], eax
0x14000cc68  mov     r8d, ebx
0x14000cc6b  mov     eax, [rsp+48h+arg_28]
0x14000cc6f  mov     rdx, rdi
0x14000cc72  mov     [rsp+48h+var_20], eax
0x14000cc76  mov     rcx, rsi
0x14000cc79  mov     rax, r10
0x14000cc7c  mov     [rsp+48h+var_28], 0
0x14000cc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc8a  mov     rbx, [rsp+48h+arg_0]
0x14000cc8f  mov     rsi, [rsp+48h+arg_8]
0x14000cc94  add     rsp, 40h
0x14000cc98  pop     rdi
0x14000cc99  retn
```
