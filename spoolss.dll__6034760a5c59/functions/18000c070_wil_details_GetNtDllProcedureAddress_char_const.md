# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000c070`
- end: `0x18000c090`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800036b0`
- `0x180004e60`
- `0x18000a8a0`
- `0x18000f2ec`
- `0x18000f418`
- `0x18000f89c`
- `0x18000f914`
- `0x18000faf0`

## callees

- `0x180002fa4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c089`

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
0x18000c070  push    rbx
0x18000c072  sub     rsp, 20h
0x18000c076  mov     rbx, rcx
0x18000c079  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000c07e  mov     rcx, rax
0x18000c081  mov     rdx, rbx
0x18000c084  add     rsp, 20h
0x18000c088  pop     rbx
0x18000c089  jmp     cs:__imp_GetProcAddress
```
