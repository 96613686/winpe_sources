# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18002d770`
- end: `0x18002d790`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180020948`
- `0x18002c430`
- `0x18002c470`
- `0x18002cacc`
- `0x18002d968`
- `0x18002da94`
- `0x18002db5c`
- `0x18002dbd4`

## callees

- `0x18002d740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d789`

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
0x18002d770  push    rbx
0x18002d772  sub     rsp, 20h
0x18002d776  mov     rbx, rcx
0x18002d779  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002d77e  mov     rcx, rax
0x18002d781  mov     rdx, rbx
0x18002d784  add     rsp, 20h
0x18002d788  pop     rbx
0x18002d789  jmp     cs:__imp_GetProcAddress
```
