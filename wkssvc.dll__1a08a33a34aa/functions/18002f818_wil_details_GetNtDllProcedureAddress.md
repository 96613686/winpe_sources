# wil_details_GetNtDllProcedureAddress

- ea: `0x18002f818`
- end: `0x18002f85e`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002f018`
- `0x18002f4c0`

## callees

- `0x18002f818`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f834`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f834`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f852`

## string_xrefs

- `0x18002f82d`: `ntdll.dll`

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
0x18002f818  push    rbx
0x18002f81a  sub     rsp, 20h
0x18002f81e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002f825  mov     rbx, rcx
0x18002f828  test    rax, rax
0x18002f82b  jnz     short loc_18002F847
0x18002f82d  lea     rcx, ModuleName; "ntdll.dll"
0x18002f834  call    cs:__imp_GetModuleHandleW
0x18002f83b  nop     dword ptr [rax+rax+00h]
0x18002f840  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002f847  mov     rdx, rbx
0x18002f84a  mov     rcx, rax
0x18002f84d  add     rsp, 20h
0x18002f851  pop     rbx
0x18002f852  jmp     cs:__imp_GetProcAddress
```
