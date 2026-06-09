# wil_details_GetNtDllProcedureAddress

- ea: `0x18002d030`
- end: `0x18002d06b`
- name: `wil_details_GetNtDllProcedureAddress`
- size: `59`
- prototype: `FARPROC __fastcall(const CHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c734`
- `0x18002cd18`

## callees

- `0x18002d030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d04c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d04c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d064`

## string_xrefs

- `0x18002d045`: `ntdll.dll`

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
0x18002d030  push    rbx
0x18002d032  sub     rsp, 20h
0x18002d036  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002d03d  mov     rbx, rcx
0x18002d040  test    rax, rax
0x18002d043  jnz     short loc_18002D059
0x18002d045  lea     rcx, ModuleName; "ntdll.dll"
0x18002d04c  call    cs:__imp_GetModuleHandleW
0x18002d052  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18002d059  mov     rdx, rbx
0x18002d05c  mov     rcx, rax
0x18002d05f  add     rsp, 20h
0x18002d063  pop     rbx
0x18002d064  jmp     cs:__imp_GetProcAddress
```
