# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18000ec48`
- end: `0x18000ec68`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000dfe0`

## callees

- `0x18000ec18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec61`

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
0x18000ec48  push    rbx
0x18000ec4a  sub     rsp, 20h
0x18000ec4e  mov     rbx, rcx
0x18000ec51  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18000ec56  mov     rcx, rax
0x18000ec59  mov     rdx, rbx
0x18000ec5c  add     rsp, 20h
0x18000ec60  pop     rbx
0x18000ec61  jmp     cs:__imp_GetProcAddress
```
