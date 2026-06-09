# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x14000a118`
- end: `0x14000a13d`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140008190`
- `0x1400081d0`
- `0x140009500`
- `0x14000a448`
- `0x14000a574`
- `0x14000a640`
- `0x14000a6b8`
- `0x14000a898`
- `0x14000a904`

## callees

- `0x14000a0e0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000a131`

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
0x14000a118  push    rbx
0x14000a11a  sub     rsp, 20h
0x14000a11e  mov     rbx, rcx
0x14000a121  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000a126  mov     rcx, rax
0x14000a129  mov     rdx, rbx
0x14000a12c  add     rsp, 20h
0x14000a130  pop     rbx
0x14000a131  jmp     cs:__imp_GetProcAddress
```
