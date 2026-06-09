# wil_details_GetNtDllProcedureAddress

- ea: `0x180015da4`
- end: `0x180015ddf`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: `FARPROC __fastcall(const CHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800154ac`
- `0x180015a7c`

## callees

- `0x180015da4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015dc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015dc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015dd8`

## string_xrefs

- `0x180015db9`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const CHAR *a1)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = (__int64)ModuleHandleW;
  }
  return GetProcAddress(ModuleHandleW, a1);
}

```

## disassembly

```asm
0x180015da4  push    rbx
0x180015da6  sub     rsp, 20h
0x180015daa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180015db1  mov     rbx, rcx
0x180015db4  test    rax, rax
0x180015db7  jnz     short loc_180015DCD
0x180015db9  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180015dc0  call    cs:__imp_GetModuleHandleW
0x180015dc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180015dcd  mov     rdx, rbx
0x180015dd0  mov     rcx, rax
0x180015dd3  add     rsp, 20h
0x180015dd7  pop     rbx
0x180015dd8  jmp     cs:__imp_GetProcAddress
```
