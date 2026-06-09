# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180022d58`
- end: `0x180022d78`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014edc`
- `0x1800224d0`
- `0x180022510`
- `0x18002bb6c`
- `0x18002c5a0`
- `0x18002c6cc`
- `0x18002cab4`
- `0x18002cb2c`

## callees

- `0x180016710`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d71`

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
0x180022d58  push    rbx
0x180022d5a  sub     rsp, 20h
0x180022d5e  mov     rbx, rcx
0x180022d61  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180022d66  mov     rcx, rax
0x180022d69  mov     rdx, rbx
0x180022d6c  add     rsp, 20h
0x180022d70  pop     rbx
0x180022d71  jmp     cs:__imp_GetProcAddress
```
