# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x1800070e8`
- end: `0x180007108`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005e20`
- `0x180005e60`

## callees

- `0x1800070b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007101`

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
0x1800070e8  push    rbx
0x1800070ea  sub     rsp, 20h
0x1800070ee  mov     rbx, rcx
0x1800070f1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800070f6  mov     rcx, rax
0x1800070f9  mov     rdx, rbx
0x1800070fc  add     rsp, 20h
0x180007100  pop     rbx
0x180007101  jmp     cs:__imp_GetProcAddress
```
