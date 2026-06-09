# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000aac8`
- end: `0x18000aaed`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a330`
- `0x18000a370`
- `0x18000bf6c`
- `0x18001426c`
- `0x180014398`
- `0x180014480`
- `0x1800144f8`
- `0x1800146d8`

## callees

- `0x18000aa90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aae1`

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
0x18000aac8  push    rbx
0x18000aaca  sub     rsp, 20h
0x18000aace  mov     rbx, rcx
0x18000aad1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000aad6  mov     rcx, rax
0x18000aad9  mov     rdx, rbx
0x18000aadc  add     rsp, 20h
0x18000aae0  pop     rbx
0x18000aae1  jmp     cs:__imp_GetProcAddress
```
