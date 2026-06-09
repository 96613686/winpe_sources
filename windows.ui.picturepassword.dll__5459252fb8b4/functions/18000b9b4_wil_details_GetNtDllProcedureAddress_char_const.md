# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000b9b4`
- end: `0x18000b9d4`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009370`
- `0x1800093b0`
- `0x18000ac80`
- `0x18001ad14`
- `0x18001cfb8`
- `0x18001d018`
- `0x18001d090`
- `0x18001d11c`

## callees

- `0x18000b984`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9cd`

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
0x18000b9b4  push    rbx
0x18000b9b6  sub     rsp, 20h
0x18000b9ba  mov     rbx, rcx
0x18000b9bd  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000b9c2  mov     rcx, rax
0x18000b9c5  mov     rdx, rbx
0x18000b9c8  add     rsp, 20h
0x18000b9cc  pop     rbx
0x18000b9cd  jmp     cs:__imp_GetProcAddress
```
