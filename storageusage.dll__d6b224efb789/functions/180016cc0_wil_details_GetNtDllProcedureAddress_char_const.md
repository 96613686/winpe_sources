# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180016cc0`
- end: `0x180016ce0`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015300`
- `0x180015340`
- `0x1800162e0`
- `0x180026fec`
- `0x18002a920`
- `0x18002a9a0`
- `0x18002aa18`
- `0x18002aaa4`

## callees

- `0x180016c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016cd9`

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
0x180016cc0  push    rbx
0x180016cc2  sub     rsp, 20h
0x180016cc6  mov     rbx, rcx
0x180016cc9  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180016cce  mov     rcx, rax
0x180016cd1  mov     rdx, rbx
0x180016cd4  add     rsp, 20h
0x180016cd8  pop     rbx
0x180016cd9  jmp     cs:__imp_GetProcAddress
```
