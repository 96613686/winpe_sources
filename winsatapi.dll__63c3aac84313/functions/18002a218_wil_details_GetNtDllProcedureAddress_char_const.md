# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002a218`
- end: `0x18002a238`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012684`
- `0x180026040`
- `0x180026090`
- `0x18002a56c`
- `0x18002a5cc`
- `0x18002a644`
- `0x18002a6d0`

## callees

- `0x18002a1e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a231`

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
0x18002a218  push    rbx
0x18002a21a  sub     rsp, 20h
0x18002a21e  mov     rbx, rcx
0x18002a221  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002a226  mov     rcx, rax
0x18002a229  mov     rdx, rbx
0x18002a22c  add     rsp, 20h
0x18002a230  pop     rbx
0x18002a231  jmp     cs:__imp_GetProcAddress
```
