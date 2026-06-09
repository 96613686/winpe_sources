# wil_details_NtUpdateWnfStateData

- ea: `0x14000afe4`
- end: `0x14000b08e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140009d94`
- `0x14000abe4`

## callees

- `0x14000afe4`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b01b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b01b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b032`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b032`

## string_xrefs

- `0x14000b014`: `ntdll.dll`
- `0x14000b028`: `NtUpdateWnfStateData`

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
0x14000afe4  mov     [rsp+arg_0], rbx
0x14000afe9  mov     [rsp+arg_8], rsi
0x14000afee  push    rdi
0x14000afef  sub     rsp, 40h
0x14000aff3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000affa  mov     ebx, r8d
0x14000affd  mov     rdi, rdx
0x14000b000  mov     rsi, rcx
0x14000b003  test    r10, r10
0x14000b006  jnz     short loc_14000B04E
0x14000b008  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b00f  test    rax, rax
0x14000b012  jnz     short loc_14000B028
0x14000b014  lea     rcx, ModuleName; "ntdll.dll"
0x14000b01b  call    cs:__imp_GetModuleHandleW
0x14000b021  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b028  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000b02f  mov     rcx, rax; hModule
0x14000b032  call    cs:__imp_GetProcAddress
0x14000b038  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000b03f  mov     r10, rax
0x14000b042  test    rax, rax
0x14000b045  jnz     short loc_14000B04E
0x14000b047  mov     eax, 0C0000139h
0x14000b04c  jmp     short loc_14000B07E
0x14000b04e  mov     eax, [rsp+48h+arg_30]
0x14000b055  xor     r9d, r9d
0x14000b058  mov     [rsp+48h+var_18], eax
0x14000b05c  mov     r8d, ebx
0x14000b05f  mov     eax, [rsp+48h+arg_28]
0x14000b063  mov     rdx, rdi
0x14000b066  mov     [rsp+48h+var_20], eax
0x14000b06a  mov     rcx, rsi
0x14000b06d  mov     rax, r10
0x14000b070  mov     [rsp+48h+var_28], 0
0x14000b079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b07e  mov     rbx, [rsp+48h+arg_0]
0x14000b083  mov     rsi, [rsp+48h+arg_8]
0x14000b088  add     rsp, 40h
0x14000b08c  pop     rdi
0x14000b08d  retn
```
