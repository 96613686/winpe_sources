# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009fcc`
- end: `0x18000a012`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009230`

## callees

- `0x180009fcc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a006`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fe8`

## string_xrefs

- `0x180009fe1`: `ntdll.dll`

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
0x180009fcc  push    rbx
0x180009fce  sub     rsp, 20h
0x180009fd2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009fd9  mov     rbx, rcx
0x180009fdc  test    rax, rax
0x180009fdf  jnz     short loc_180009FFB
0x180009fe1  lea     rcx, ModuleName; "ntdll.dll"
0x180009fe8  call    cs:__imp_GetModuleHandleW
0x180009fef  nop     dword ptr [rax+rax+00h]
0x180009ff4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ffb  mov     rdx, rbx
0x180009ffe  mov     rcx, rax
0x18000a001  add     rsp, 20h
0x18000a005  pop     rbx
0x18000a006  jmp     cs:__imp_GetProcAddress
```
