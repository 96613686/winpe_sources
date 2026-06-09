# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180005f48`
- end: `0x180005f68`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800051e0`

## callees

- `0x180005f18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f61`

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
0x180005f48  push    rbx
0x180005f4a  sub     rsp, 20h
0x180005f4e  mov     rbx, rcx
0x180005f51  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180005f56  mov     rcx, rax
0x180005f59  mov     rdx, rbx
0x180005f5c  add     rsp, 20h
0x180005f60  pop     rbx
0x180005f61  jmp     cs:__imp_GetProcAddress
```
