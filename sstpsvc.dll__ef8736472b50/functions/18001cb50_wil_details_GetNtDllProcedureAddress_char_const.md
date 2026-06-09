# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18001cb50`
- end: `0x18001cb75`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `37`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800187e0`
- `0x18001b8a0`
- `0x18001b8e0`
- `0x18001cddc`
- `0x18001ce40`
- `0x18001ceb8`
- `0x18001cf48`

## callees

- `0x18001cb18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb69`

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
0x18001cb50  push    rbx
0x18001cb52  sub     rsp, 20h
0x18001cb56  mov     rbx, rcx
0x18001cb59  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18001cb5e  mov     rcx, rax
0x18001cb61  mov     rdx, rbx
0x18001cb64  add     rsp, 20h
0x18001cb68  pop     rbx
0x18001cb69  jmp     cs:__imp_GetProcAddress
```
