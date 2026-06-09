# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009da8`
- end: `0x180009de3`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `59`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090c0`

## callees

- `0x180009da8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ddc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009dc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009dc4`

## string_xrefs

- `0x180009dbd`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
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
0x180009da8  push    rbx
0x180009daa  sub     rsp, 20h
0x180009dae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009db5  mov     rbx, rcx
0x180009db8  test    rax, rax
0x180009dbb  jnz     short loc_180009DD1
0x180009dbd  lea     rcx, ModuleName; "ntdll.dll"
0x180009dc4  call    cs:__imp_GetModuleHandleW
0x180009dca  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009dd1  mov     rdx, rbx
0x180009dd4  mov     rcx, rax
0x180009dd7  add     rsp, 20h
0x180009ddb  pop     rbx
0x180009ddc  jmp     cs:__imp_GetProcAddress
```
