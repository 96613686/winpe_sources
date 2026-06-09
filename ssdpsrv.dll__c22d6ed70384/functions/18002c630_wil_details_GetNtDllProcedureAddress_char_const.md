# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002c630`
- end: `0x18002c650`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002600c`
- `0x18002b440`
- `0x18002b480`
- `0x18002b954`
- `0x18002d094`
- `0x18002d1c0`
- `0x18002d5a4`
- `0x18002d61c`

## callees

- `0x18002c600`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c649`

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
0x18002c630  push    rbx
0x18002c632  sub     rsp, 20h
0x18002c636  mov     rbx, rcx
0x18002c639  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002c63e  mov     rcx, rax
0x18002c641  mov     rdx, rbx
0x18002c644  add     rsp, 20h
0x18002c648  pop     rbx
0x18002c649  jmp     cs:__imp_GetProcAddress
```
