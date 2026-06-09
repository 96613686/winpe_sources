# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000ae00`
- end: `0x18000ae21`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `33`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006680`
- `0x180006a84`
- `0x18000ad1c`
- `0x18000ad88`
- `0x18000b6fc`
- `0x180018c80`
- `0x180018cc0`
- `0x18001a1f0`
- `0x18001a37c`

## callees

- `0x1800092bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae14`

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
0x18000ae00  push    rbx
0x18000ae02  sub     rsp, 20h
0x18000ae06  mov     rbx, rcx
0x18000ae09  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000ae0e  mov     rcx, rax; hModule
0x18000ae11  mov     rdx, rbx; lpProcName
0x18000ae14  call    cs:__imp_GetProcAddress
0x18000ae1a  nop
0x18000ae1b  add     rsp, 20h
0x18000ae1f  pop     rbx
0x18000ae20  retn
```
