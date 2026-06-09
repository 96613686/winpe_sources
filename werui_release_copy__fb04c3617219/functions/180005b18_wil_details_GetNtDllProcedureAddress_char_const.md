# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180005b18`
- end: `0x180005b38`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005480`

## callees

- `0x180005ae8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005b31`

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
0x180005b18  push    rbx
0x180005b1a  sub     rsp, 20h
0x180005b1e  mov     rbx, rcx
0x180005b21  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180005b26  mov     rcx, rax
0x180005b29  mov     rdx, rbx
0x180005b2c  add     rsp, 20h
0x180005b30  pop     rbx
0x180005b31  jmp     cs:__imp_GetProcAddress
```
