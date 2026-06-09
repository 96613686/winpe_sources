# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14004b6e0`
- end: `0x14004b700`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140049620`
- `0x140049660`
- `0x140049dac`
- `0x14004ba00`
- `0x14004bb2c`
- `0x14004bbec`
- `0x14004bc64`

## callees

- `0x14004b6b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b6f9`

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
0x14004b6e0  push    rbx
0x14004b6e2  sub     rsp, 20h
0x14004b6e6  mov     rbx, rcx
0x14004b6e9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14004b6ee  mov     rcx, rax
0x14004b6f1  mov     rdx, rbx
0x14004b6f4  add     rsp, 20h
0x14004b6f8  pop     rbx
0x14004b6f9  jmp     cs:__imp_GetProcAddress
```
