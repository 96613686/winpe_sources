# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002e5fc`
- end: `0x18002e621`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180027de8`
- `0x18002d3c0`
- `0x18002d400`
- `0x18002d850`
- `0x18002de70`
- `0x18002f0c4`
- `0x18002f61c`
- `0x18002f694`

## callees

- `0x18002e5c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e615`

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
0x18002e5fc  push    rbx
0x18002e5fe  sub     rsp, 20h
0x18002e602  mov     rbx, rcx
0x18002e605  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002e60a  mov     rcx, rax
0x18002e60d  mov     rdx, rbx
0x18002e610  add     rsp, 20h
0x18002e614  pop     rbx
0x18002e615  jmp     cs:__imp_GetProcAddress
```
