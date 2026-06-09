# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180015550`
- end: `0x180015596`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `70`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013120`

## callees

- `0x180015550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001558a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001556c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001556c`

## string_xrefs

- `0x180015565`: `ntdll.dll`

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
0x180015550  push    rbx
0x180015552  sub     rsp, 20h
0x180015556  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001555d  mov     rbx, rcx
0x180015560  test    rax, rax
0x180015563  jnz     short loc_18001557F
0x180015565  lea     rcx, ModuleName; "ntdll.dll"
0x18001556c  call    cs:__imp_GetModuleHandleW
0x180015573  nop     dword ptr [rax+rax+00h]
0x180015578  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001557f  mov     rdx, rbx
0x180015582  mov     rcx, rax
0x180015585  add     rsp, 20h
0x180015589  pop     rbx
0x18001558a  jmp     cs:__imp_GetProcAddress
```
