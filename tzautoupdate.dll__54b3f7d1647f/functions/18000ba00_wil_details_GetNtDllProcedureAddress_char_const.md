# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000ba00`
- end: `0x18000ba20`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004670`
- `0x180008880`
- `0x1800088c0`
- `0x18000c784`
- `0x18000c8b0`
- `0x18000cd2c`
- `0x18000cda4`
- `0x18000cf80`

## callees

- `0x18000b9d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba19`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, a1);
}

```

## disassembly

```asm
0x18000ba00  push    rbx
0x18000ba02  sub     rsp, 20h
0x18000ba06  mov     rbx, rcx
0x18000ba09  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000ba0e  mov     rcx, rax
0x18000ba11  mov     rdx, rbx
0x18000ba14  add     rsp, 20h
0x18000ba18  pop     rbx
0x18000ba19  jmp     cs:__imp_GetProcAddress
```
