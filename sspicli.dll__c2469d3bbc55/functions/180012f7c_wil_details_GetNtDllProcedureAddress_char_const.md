# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180012f7c`
- end: `0x180012f9c`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012ec4`
- `0x180012f40`
- `0x180017200`
- `0x18001e238`
- `0x18001f370`
- `0x18001fcb0`
- `0x18001fd10`

## callees

- `0x180012fa4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f95`

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
0x180012f7c  push    rbx
0x180012f7e  sub     rsp, 20h
0x180012f82  mov     rbx, rcx
0x180012f85  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180012f8a  mov     rcx, rax
0x180012f8d  mov     rdx, rbx
0x180012f90  add     rsp, 20h
0x180012f94  pop     rbx
0x180012f95  jmp     cs:__imp_GetProcAddress
```
