# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002f4a0`
- end: `0x18002f4c0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180023d30`
- `0x1800276fc`
- `0x18002dcb0`
- `0x18002f6c0`
- `0x18002f7ec`
- `0x18002f8ac`
- `0x18002f924`
- `0x18002fb00`

## callees

- `0x18002f470`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f4b9`

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
0x18002f4a0  push    rbx
0x18002f4a2  sub     rsp, 20h
0x18002f4a6  mov     rbx, rcx
0x18002f4a9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002f4ae  mov     rcx, rax
0x18002f4b1  mov     rdx, rbx
0x18002f4b4  add     rsp, 20h
0x18002f4b8  pop     rbx
0x18002f4b9  jmp     cs:__imp_GetProcAddress
```
