# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180012920`
- end: `0x180012941`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cbb8`
- `0x180010cb0`
- `0x180010cf0`
- `0x1800137ec`
- `0x180013864`
- `0x180013a40`

## callees

- `0x1800128f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012934`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012934`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(LPCSTR lpProcName)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, lpProcName);
}

```

## disassembly

```asm
0x180012920  push    rbx
0x180012922  sub     rsp, 20h
0x180012926  mov     rbx, rcx
0x180012929  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001292e  mov     rcx, rax; hModule
0x180012931  mov     rdx, rbx; lpProcName
0x180012934  call    cs:__imp_GetProcAddress
0x18001293a  nop
0x18001293b  add     rsp, 20h
0x18001293f  pop     rbx
0x180012940  retn
```
