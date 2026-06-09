# wil_details_NtUpdateWnfStateData

- ea: `0x180038678`
- end: `0x180038722`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180031eb0`
- `0x180034790`

## callees

- `0x180038678`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800386c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800386c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800386af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800386af`

## string_xrefs

- `0x1800386a8`: `ntdll.dll`
- `0x1800386bc`: `NtUpdateWnfStateData`

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
0x180038678  mov     [rsp+arg_0], rbx
0x18003867d  mov     [rsp+arg_8], rsi
0x180038682  push    rdi
0x180038683  sub     rsp, 40h
0x180038687  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18003868e  mov     ebx, r8d
0x180038691  mov     rdi, rdx
0x180038694  mov     rsi, rcx
0x180038697  test    r10, r10
0x18003869a  jnz     short loc_1800386E2
0x18003869c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800386a3  test    rax, rax
0x1800386a6  jnz     short loc_1800386BC
0x1800386a8  lea     rcx, ModuleName; "ntdll.dll"
0x1800386af  call    cs:__imp_GetModuleHandleW
0x1800386b5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800386bc  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800386c3  mov     rcx, rax; hModule
0x1800386c6  call    cs:__imp_GetProcAddress
0x1800386cc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800386d3  mov     r10, rax
0x1800386d6  test    rax, rax
0x1800386d9  jnz     short loc_1800386E2
0x1800386db  mov     eax, 0C0000139h
0x1800386e0  jmp     short loc_180038712
0x1800386e2  mov     eax, [rsp+48h+arg_30]
0x1800386e9  xor     r9d, r9d
0x1800386ec  mov     [rsp+48h+var_18], eax
0x1800386f0  mov     r8d, ebx
0x1800386f3  mov     eax, [rsp+48h+arg_28]
0x1800386f7  mov     rdx, rdi
0x1800386fa  mov     [rsp+48h+var_20], eax
0x1800386fe  mov     rcx, rsi
0x180038701  mov     rax, r10
0x180038704  mov     [rsp+48h+var_28], 0
0x18003870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038712  mov     rbx, [rsp+48h+arg_0]
0x180038717  mov     rsi, [rsp+48h+arg_8]
0x18003871c  add     rsp, 40h
0x180038720  pop     rdi
0x180038721  retn
```
