# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000ca40`
- end: `0x18000ca65`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003970`
- `0x1800051c0`
- `0x18000b180`
- `0x1800103b8`
- `0x1800104e4`
- `0x18001097c`
- `0x1800109f4`
- `0x180010bd4`

## callees

- `0x180003160`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ca59`

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
0x18000ca40  push    rbx
0x18000ca42  sub     rsp, 20h
0x18000ca46  mov     rbx, rcx
0x18000ca49  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000ca4e  mov     rcx, rax
0x18000ca51  mov     rdx, rbx
0x18000ca54  add     rsp, 20h
0x18000ca58  pop     rbx
0x18000ca59  jmp     cs:__imp_GetProcAddress
```
