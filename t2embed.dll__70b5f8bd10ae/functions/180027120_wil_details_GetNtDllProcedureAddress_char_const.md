# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180027120`
- end: `0x180027140`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180025ab0`
- `0x180026f10`

## callees

- `0x1800270f0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027139`

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
0x180027120  push    rbx
0x180027122  sub     rsp, 20h
0x180027126  mov     rbx, rcx
0x180027129  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18002712e  mov     rcx, rax
0x180027131  mov     rdx, rbx
0x180027134  add     rsp, 20h
0x180027138  pop     rbx
0x180027139  jmp     cs:__imp_GetProcAddress
```
