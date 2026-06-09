# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x180011354`
- end: `0x180011374`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d850`
- `0x18000e9fc`
- `0x1800110b4`
- `0x1800112dc`
- `0x1800160f0`
- `0x180016130`
- `0x180016538`
- `0x180018be8`
- `0x180018cac`

## callees

- `0x18000fc54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001136d`

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
0x180011354  push    rbx
0x180011356  sub     rsp, 20h
0x18001135a  mov     rbx, rcx
0x18001135d  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180011362  mov     rcx, rax
0x180011365  mov     rdx, rbx
0x180011368  add     rsp, 20h
0x18001136c  pop     rbx
0x18001136d  jmp     cs:__imp_GetProcAddress
```
