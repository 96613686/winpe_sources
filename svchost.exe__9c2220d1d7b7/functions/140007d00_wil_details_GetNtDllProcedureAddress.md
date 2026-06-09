# wil_details_GetNtDllProcedureAddress

- ea: `0x140007d00`
- end: `0x140007d46`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007500`
- `0x1400079a8`

## callees

- `0x140007d00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d1c`

## string_xrefs

- `0x140007d15`: `ntdll.dll`

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
0x140007d00  push    rbx
0x140007d02  sub     rsp, 20h
0x140007d06  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140007d0d  mov     rbx, rcx
0x140007d10  test    rax, rax
0x140007d13  jnz     short loc_140007D2F
0x140007d15  lea     rcx, ModuleName; "ntdll.dll"
0x140007d1c  call    cs:__imp_GetModuleHandleW
0x140007d23  nop     dword ptr [rax+rax+00h]
0x140007d28  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x140007d2f  mov     rdx, rbx
0x140007d32  mov     rcx, rax
0x140007d35  add     rsp, 20h
0x140007d39  pop     rbx
0x140007d3a  jmp     cs:__imp_GetProcAddress
```
