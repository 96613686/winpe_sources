# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180010c90`
- end: `0x180010cb5`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800105c0`
- `0x180010600`
- `0x180010970`
- `0x180015d04`
- `0x180019b54`
- `0x180019c80`
- `0x18001a11c`
- `0x18001a194`
- `0x18001a374`

## callees

- `0x180009720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ca9`

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
0x180010c90  push    rbx
0x180010c92  sub     rsp, 20h
0x180010c96  mov     rbx, rcx
0x180010c99  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180010c9e  mov     rcx, rax
0x180010ca1  mov     rdx, rbx
0x180010ca4  add     rsp, 20h
0x180010ca8  pop     rbx
0x180010ca9  jmp     cs:__imp_GetProcAddress
```
