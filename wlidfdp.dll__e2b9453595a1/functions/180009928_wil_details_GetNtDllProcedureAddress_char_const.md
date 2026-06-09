# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180009928`
- end: `0x180009948`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008640`
- `0x180009490`

## callees

- `0x1800098f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009941`

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
0x180009928  push    rbx
0x18000992a  sub     rsp, 20h
0x18000992e  mov     rbx, rcx
0x180009931  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180009936  mov     rcx, rax
0x180009939  mov     rdx, rbx
0x18000993c  add     rsp, 20h
0x180009940  pop     rbx
0x180009941  jmp     cs:__imp_GetProcAddress
```
